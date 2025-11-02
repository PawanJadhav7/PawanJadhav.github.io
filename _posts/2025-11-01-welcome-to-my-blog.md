---
layout: post
title: "Data Engineering in Healthcare & Finance"
date: 2025-11-01 10:00:00 -0500
tags: [healthcare, finance, snowflake, aws, dbt]
hero_image: /assets/headers/claims-pipeline.jpg
---

> **TL;DR:** We replaced fragile full reloads with a CDC-driven pipeline:
> Oracle → (DMS) → S3 → (Glue) → Snowflake → (dbt).  
> **Result:** Faster loads, lower cost, audit-ready.

## 🪝 Hook
In healthcare analytics, data freshness and compliance often pull in opposite directions.  
Our claims warehouse was always a day behind because we reloaded everything from Oracle each night.  
As claims volumes grew, that nightly job became a six-hour bottleneck and a security headache.  

We rebuilt it as a near–real-time CDC pipeline using **AWS DMS, Glue, and dbt** — reducing load times from hours to minutes, improving auditability, and aligning perfectly with HIPAA and CMS traceability requirements.

## 🩺 Context & Problem
The legacy setup at most payer organizations looks similar:
- An **Oracle OLTP** database stores claim, member, and provider data.  
- Data engineers run full extracts to a warehouse for analytics.  
- Any schema change or large claim cycle causes a complete reload.  
- The ETL scripts are brittle, slow, and impossible to audit end-to-end.  

In our case, the daily claim extracts (~50M rows) took over 5 hours and frequently missed the SLA.  
Because we lacked incremental logic, even small updates triggered full refreshes — wasting compute and increasing risk of PHI exposure during intermediate loads.

We needed a **streaming-style, schema-aware, auditable** data movement pattern:
- **Change Data Capture (CDC)** from Oracle → S3 → Snowflake  
- **Schema evolution handling** for new claim fields  
- **Automated transformations** via dbt (dim/fact/star schema)  
- **End-to-end lineage and data quality validation**  

That’s where **AWS DMS** and **Glue** came together as a cost-efficient, HIPAA-compliant bridge.
## 🧩 Architecture Overview

A modern healthcare data platform needs to capture changes from source systems (Oracle), land them securely on AWS, and transform them into analytics-ready data in Snowflake — all while maintaining PHI compliance and auditability.

![Healthcare CDC Architecture Diagram]({{ '/assets/images/Architecture_Overview.png' | relative_url }})

### 🏗️ Components and Roles

| Layer                     | Tool                                  | Purpose                                                                 |
|---------------------------|---------------------------------------|-------------------------------------------------------------------------|
| Source (OLTP)             | Oracle                                | Stores raw claims, member, provider data. CDC extracts every change.    |
| Ingestion                 | AWS DMS (CDC)                         | Streams inserts/updates/deletes from Oracle to S3 in near real time.    |
| Landing Zone              | Amazon S3                             | Raw JSON/Parquet with CDC metadata; encrypted with KMS.                 |
| Processing Zone           | AWS Glue (PySpark)                    | Cleans/ﬂattens; handles schema evolution automatically via Glue Catalog.|
| Transform / Curated Zone  | dbt + Snowflake                       | Incremental models; SCD2 for dims; DQ tests enforced.                   |
| Orchestration             | MWAA (Airflow) or EventBridge         | Automates CDC → Glue → dbt workflow with retries and SLAs.              |
| Governance                | Glue Catalog, Great Expectations, OpenLineage | Lineage, schema registry, and data-quality validation.          |
| Analytics / BI            | Snowflake + Power BI / Looker Studio  | Curated data for actuaries, analysts, and business teams.               |

### 🔐 Security & Compliance Highlights
- End-to-end encryption (KMS + Snowflake masking policies).  
- IAM least-privilege roles for DMS, Glue, and Snowflake.  
- PHI tagging for column-level access control.  
- Automated audit logs in CloudWatch and Snowflake query history.

> This architecture follows the *Medallion Lakehouse* concept — raw (bronze), validated (silver), and curated (gold) — ensuring scalability and traceability for healthcare workloads.

## 🧱 Build Guide: 10 Steps

Below is the simplified 10-step path we followed to design a HIPAA-compliant,
incremental pipeline from Oracle → AWS → Snowflake → dbt.

### 1️⃣ Provision Secure Landing & Processing Zones
Create three S3 buckets — `landing`, `processing`, `curated` — all
encrypted with AWS KMS and versioned for audit.
Attach least-privilege IAM roles for DMS and Glue.

### 2️⃣ Configure AWS DMS for CDC
Set up Oracle source & S3 target endpoints.
Enable full load + ongoing replication.
Tune task settings for batch apply and LOB handling.

### 3️⃣ Create Change Table Structure
DMS writes JSON/Parquet files containing `before_image`, `after_image`,
and operation type.  
We store them in S3 `landing` with partition folders (`year/month/day`).

### 4️⃣ Automate Schema Registration
Glue Crawler registers new objects in Glue Catalog daily.
This allows automatic schema evolution when new columns appear in Oracle.

### 5️⃣ Normalize and Flatten with Glue (PySpark)
Glue job reads landing data, cleans metadata, flattens nested records,
and writes partitioned Parquet to `processing` zone.

```python
df = spark.read.json("s3://landing/claims/")
df_clean = df.dropDuplicates().withColumn("load_dt", current_date())
df_clean.write.mode("overwrite").parquet("s3://processing/claims/")
