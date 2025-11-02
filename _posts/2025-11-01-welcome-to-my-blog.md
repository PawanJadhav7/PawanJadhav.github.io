---
layout: post
title: "Data Engineering in Healthcare & Finance"
date: 2025-11-01 10:00:00 -0500
tags: [healthcare, finance, snowflake, aws, dbt]
hero_image: /assets/headers/claims-pipeline.jpg
---

> **TL;DR:** We replaced fragile full reloads with a CDC-driven pipeline:
> Oracle → (DMS) → S3 → (Glue) → Snowflake → (dbt). Result: faster loads, lower cost, audit-ready.
>
> ## 🪝 Hook
In healthcare analytics, data freshness and compliance often pull in opposite directions...
...
## 🩺 Context & Problem
The legacy setup at most payer organizations looks similar: ...
...

## 🧩 Architecture Overview

A modern healthcare data platform needs to capture changes from source systems (Oracle), land them securely on AWS, and transform them into analytics-ready data in Snowflake — all while maintaining PHI compliance and auditability.

### 🏗️ Components and Roles
![Healthcare CDC Architecture Diagram](assets/images/Architecture_Overview.png)
| Layer | Tool | Purpose |
|-------|------|----------|
| **Source (OLTP)** | Oracle | Stores raw claims, member, provider data.  CDC extracts every change. |
| **Ingestion** | **AWS DMS (CDC)** | Streams inserts/updates/deletes from Oracle to S3 in near real time. |
| **Landing Zone** | **Amazon S3** | Raw JSON/Parquet files with CDC metadata; fully encrypted (KMS). |
| **Processing Zone** | **AWS Glue (PySpark)** | Cleanses and flattens nested structures; handles schema evolution automatically via Glue Catalog. |
| **Transform / Curated Zone** | **dbt + Snowflake** | Builds incremental models (staging → dimensions/facts), applies SCD2 logic, and enforces DQ tests. |
| **Orchestration** | **MWAA (Airflow)** or **EventBridge** | Automates CDC → Glue → dbt workflow; includes retries and SLAs. |
| **Governance** | **Glue Catalog + Great Expectations + OpenLineage** | Provides lineage, schema registry, and DQ validation. |
| **Analytics / BI** | **Snowflake + Power BI / Looker Studio** | Serves curated data for actuaries, analysts, and business teams. |

### 🔐 Security & Compliance Highlights
- End-to-end encryption (KMS + Snowflake masking policies).  
- IAM least-privilege roles for DMS, Glue, and Snowflake.  
- PHI tagging for column-level access control.  
- Automated audit logs in CloudWatch and Snowflake query history.

> This architecture follows the *Medallion Lakehouse* concept — raw (bronze), validated (silver), and curated (gold) — ensuring scalability and traceability for healthcare workloads.

## Build Guide: 10 Steps
<!-- Use the outline above, turn bullets into short paragraphs -->

## Snippets
```sql
-- Example Snowflake MERGE for SCD2
