---
layout: default
title: "Pricing & Margin Analytics — AWS • Snowflake • dbt • Airflow • Tableau"
permalink: /pricingandmarginanalytics/
date: 2025-11-02 10:00:00 -0500
tags: [pricing, margin, analytics, snowflake, aws, dbt, airflow, tableau]
hero_image: /assets/headers/pricing-margin-hero.jpg
summary: "Margin waterfall (List → Invoice → Net → Pocket), leakage analysis (discounts, rebates, freight), and price elasticity signals powered by AWS → Snowflake → dbt → Airflow → Tableau."
seo:
  description: "Production-style Pricing & Margin Analytics project: Snowflake marts, dbt models, Airflow orchestration, Great Expectations, and Tableau dashboard."
  image: /assets/headers/pricing-margin-hero.jpg
---

<div style="display:flex;gap:10px;flex-wrap:wrap;margin:12px 0 18px;">
  <a class="btn" href="https://github.com/PawanJadhav/Finance-Analytics" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:8px 14px;border-radius:10px;border:1px solid #e5e7eb;background:#111827;color:#fff;text-decoration:none;font-size:14px;">
     💻 View Code
  </a>
  <a class="btn" href="{{ '/pricingandmarginanalytics/' | relative_url }}#dashboard" 
     style="display:inline-flex;align-items:center;justify-content:center;padding:8px 14px;border-radius:10px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">
     📊 Dashboard (screens)
  </a>
  <a class="btn" href="{{ '/case-study/pricing-margin-analytics.pdf' | relative_url }}" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:8px 14px;border-radius:10px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">
     📄 Download Case Study (PDF)
  </a>
</div>

> **TL;DR**  
> Calculates **Pocket Margin** and highlights **leakage** (discounts, promos, rebates, freight), with **elasticity** by product/category and a what-if price simulator.  
> **Stack:** AWS S3/Glue • **Snowflake** • **dbt** • **Airflow** • Python • **Tableau/Power BI**

---

## 1) Problem & Context
Leaders need clear visibility from **List Price → Pocket Margin** and to know **where** and **why** margin erodes (discounts, rebates, freight, payment fees). They also need fast feedback on **price changes** and **mix** effects.

**Objectives**
- Build a trustworthy **margin waterfall** and leakage analytics.
- Quantify **price elasticity** to guide price moves.
- Deliver a **shareable dashboard** and a reproducible data pipeline.

---

## 2) Business Entities & KPIs
**KPIs:** Revenue, Gross Margin %, **Pocket Margin %**, Leakage % by component, Contribution per unit, Elasticity by product/category, Customer profitability.

**Margin steps:** List → Invoice (−std discount) → Net (−promo −rebate) → Pocket (−COGS −var selling costs).

---

## 3) Architecture (High-level)
**Ingestion & Storage:** AWS S3 (raw/curated) → Glue (schema)  
**Warehouse/ELT:** Snowflake (Bronze → Silver → **Gold marts**) with dbt models/tests  
**Orchestration:** Airflow (MWAA) + EventBridge  
**Quality & Lineage:** Great Expectations (+ OpenLineage optional)  
**Analytics:** Python (elasticity, what-if)  
**BI:** Tableau/Power BI

![Architecture Diagram](/assets/diagrams/pricing-architecture.png)

---

## 4) Data Model (Snowflake)
**Silver layer** tables:
- `FACT_SALES_CLEAN` (invoice lines, qty, list_price, discounts, promo, rebates, freight_out, fees)
- `FACT_COST` (monthly landed cost per product)
- `FACT_PRICE_LIST` (valid_from/to pricing)
- `DIM_PRODUCT`, `DIM_CUSTOMER`, `DIM_REGION`

**Gold marts:**
- `GOLD.MART_MARGIN_WATERFALL`
- `GOLD.MART_ELASTICITY`

---

## 5) Transform Highlights
- **Waterfall math**: computes `invoice_price_unit`, `net_price_unit`, `pocket_margin_unit` and aggregates to amounts for visuals.
- **Elasticity**: weekly log-log regression per product/category `ln(Q) ~ ln(Price) + seasonality + promo_flags`.
- **Data quality**: non-null keys, non-negative prices/qty, valid pricing windows, COGS sanity checks.

---

## 6) Orchestration
Nightly DAG:
1. Generate/load data to S3  
2. Bronze → Silver standardization  
3. dbt **Silver** cleaning/conformance  
4. dbt **Gold** waterfall  
5. Python elasticity job → `GOLD.MART_ELASTICITY`  
6. Publish BI + refresh extracts  

---

## 7) What’s in the Repo
- **/src/generator** — synthetic but realistic data (12–18 months)  
- **/dbt/models/gold** — `mart_margin_waterfall.sql`, `mart_elasticity.sql`  
- **/dags** — `pricing_pipeline_dag.py`  
- **/quality/great_expectations** — basic checks  
- **/dashboards** — Tableau/Power BI files + screenshots  

---

## 8) Results & Business Impact
- **Runtime**: report time ↓ from **11m → 90s** (XS Snowflake WH)  
- **Visibility**: Top margin leakage drivers by **customer × category**  
- **Actionability**: Elasticity identifies SKUs with headroom to raise prices with limited volume impact  

---

## 9) How to Run Locally
```bash
# 1) Generate sample data
python src/generator/make_dataset.py

# 2) Load CSVs to Snowflake (via COPY INTO or DataGrip)
#    Then run dbt:
dbt run --select gold.mart_margin_waterfall

# 3) Open Tableau/Power BI and connect to PRICING_DB.GOLD
