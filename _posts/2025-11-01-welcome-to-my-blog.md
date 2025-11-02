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
