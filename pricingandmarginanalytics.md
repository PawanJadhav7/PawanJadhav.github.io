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

<!-- ===== HERO / QUICK ACTIONS ===== -->
<div style="display:flex;gap:12px;flex-wrap:wrap;justify-content:center;
            margin:10px 0 18px;align-items:center;text-align:center;">
  <a href="/" class="btn"
     style="flex:1 1 200px;max-width:240px;
            display:inline-flex;align-items:center;justify-content:center;gap:6px;
            padding:8px 14px;border-radius:8px;border:1px solid #e5e7eb;
            background:#f8fafc;color:#111827;text-decoration:none;
            font-size:14px;line-height:1;font-weight:500;">
    ← Back to Home
  </a>

  <a class="btn" href="https://github.com/PawanJadhav/Finance-Analytics" target="_blank" rel="noopener noreferrer"
     style="flex:1 1 200px;max-width:240px;
            display:inline-flex;align-items:center;justify-content:center;gap:6px;
            padding:8px 14px;border-radius:8px;border:1px solid #e5e7eb;
            background:#f8fafc;color:#111827;text-decoration:none;
            font-size:14px;line-height:1;font-weight:500;">
     💻 Code
  </a>

  <a class="btn" href="{{ '/pricingandmarginanalytics/' | relative_url }}#dashboard" 
     style="flex:1 1 200px;max-width:240px;
            display:inline-flex;align-items:center;justify-content:center;gap:6px;
            padding:8px 14px;border-radius:8px;border:1px solid #e5e7eb;
            background:#f8fafc;color:#111827;text-decoration:none;
            font-size:14px;line-height:1;font-weight:500;">
     📊 Dashboard (screens)
  </a>
</div>

<div style="border:1px solid #e5e7eb;border-radius:14px;background:#ffffff;box-shadow:0 4px 10px rgba(0,0,0,0.05);overflow:hidden;margin:22px 0;">
  <!-- Header Bar -->
  <div style="background:#007ACC;color:#ffffff;padding:10px 16px;font-weight:600;font-size:15px;letter-spacing:0.3px;">
    ⚡ TL;DR — Executive Summary: Pricing & Margin Analytics using data to make smarter pricing decisions and protect profit
  </div>
  
  <!-- Body -->
  <div style="padding:16px 20px;color:#374151;font-size:15px;line-height:1.7;">
    Calculates <strong>Pocket Margin</strong> and identifies <strong>leakage drivers</strong> such as discounts, promotions, rebates, freight, and payment fees.<br><br>
    Includes <strong>price elasticity analysis</strong> by product and category, plus a lightweight <strong>what-if simulator</strong> for pricing scenarios.<br><br>
    <strong>Stack:</strong> AWS (S3, Glue) • <strong>Snowflake</strong> • <strong>dbt</strong> • <strong>Airflow</strong> • <strong>Python</strong> • <strong>Tableau/Power BI</strong>
  </div>
</div>

---

## Contents
- [1) Business Problem](#business-problem)
- [2) Objectives & KPIs](#objectives--kpis)
- [3) Data Sources](#data-sources)
- [4) Architecture](#architecture)
- [5) Data Model](#data-model)
- [6) Transform Logic (Gold)](#transform-logic-gold)
- [7) Orchestration & Quality](#orchestration--quality)
- [8) Security & Cost](#security--cost)
- [9) Results](#results)
- [10) How to Run](#how-to-run)
- [11) Dashboard (Screens)](#dashboard)
- [12) Credits & Contact](#credits--contact)

---

## 1) Business Problem
Decision makers need a transparent view of **how price leaks** from **List** to **Pocket** and which levers (discounts, rebates, freight, fees, cost) most affect profitability. They also need **elasticity signals** to guide price actions without sacrificing volume.

---

## 2) Objectives & KPIs
**Objectives**
- Production-style **margin waterfall** and leakage analytics.
- **Elasticity** by product/category; baseline for what-if pricing.
- Reproducible pipeline with orchestration, tests, and BI.

**Core KPIs**
- Revenue, Net Revenue, **Pocket Margin (Amt & %)**  
- **Leakage %** (Std Discount, Promo, Rebate, Freight/Fees)  
- Contribution per unit, Elasticity (β\_price), Customer profitability

---

## 3) Data Sources
- **Sales/Invoices:** product, customer, region, qty, price & discount components  
- **Costs:** monthly COGS, freight-in, duty (landed cost per unit)  
- **Price Lists:** validity windows by region/channel  
- **Dimensions:** product, customer, region

> Demo uses **synthetic CSVs** (generated via Python) → Snowflake.

---

## 4) Architecture
**Ingestion & Storage:** AWS S3 (raw/curated), optional Glue for schema  
**Warehouse/ELT:** Snowflake (Bronze → Silver → **Gold**) with dbt models/tests  
**Orchestration:** Airflow (MWAA) + EventBridge triggers  
**Quality/Lineage:** Great Expectations, OpenLineage (optional)  
**Analytics:** Python (elasticity, what-if)  
**BI:** Tableau / Power BI

![Architecture Diagram](/assets/diagrams/pricing-architecture.png)

---

## 5) Data Model
**Silver layer**
- `FACT_SALES_CLEAN` — invoice lines with qty, list_price, discounts, promo, rebate, freight_out, fees  
- `FACT_COST` — monthly landed cost per product  
- `FACT_PRICE_LIST` — pricing validity windows  
- `DIM_PRODUCT`, `DIM_CUSTOMER`, `DIM_REGION`

**Gold marts**
- `GOLD.MART_MARGIN_WATERFALL`  
- `GOLD.MART_ELASTICITY`

---

## 6) Transform Logic (Gold)
**Waterfall (List → Invoice → Net → Pocket)**
- `invoice_price_unit = list_price − (std_discount_amt / qty)`  
- `net_price_unit = list_price − ((std_discount_amt + promo_amt + rebate_accrual_amt) / qty)`  
- `landed_cost_unit = cogs + freight_in + duty`  
- `var_selling_cost_unit = (freight_out_amt + payment_fees_amt) / qty`  
- **Pocket Margin / unit** = `net_price_unit − landed_cost_unit − var_selling_cost_unit`  

**Elasticity (sketch)**
- Weekly log-log regression per product/category:  
  `ln(Q) ~ ln(Price) + seasonality + promo_flags`  
- Output to `GOLD.MART_ELASTICITY` with β\_price, R², significance.

---

## 7) Orchestration & Quality
**Airflow DAG (nightly)**
1. Generate/load data to S3  
2. Bronze → Silver standardization  
3. dbt **Silver** conformance  
4. dbt **Gold** waterfall  
5. Python elasticity job → `GOLD.MART_ELASTICITY`  
6. Publish BI / refresh extracts

**Data Quality (Great Expectations)**
- Non-null keys (invoice_id, product_id, customer_id)  
- Non-negative qty & price  
- Pricing windows valid (from ≤ to)  
- Cost sanity: landed_cost_unit within expected band

---

## 8) Security & Cost
- **RBAC:** INGEST / TRANSFORM / ANALYST roles, least privilege  
- **Warehouses:** XSMALL auto-suspend (60s) per tier  
- **S3:** private buckets, lifecycle for cold storage  
- **KMS & Secrets:** keys/creds outside code; parameterized connections  
- **Cost levers:** partition pruning, small WH for transforms, BI extracts off-peak

---

## 9) Results
- **Runtime:** p95 report time ↓ **11m → ~90s** (XS Snowflake WH)  
- **Visibility:** Top leakage drivers by **customer × category**  
- **Actionability:** Elasticity flags SKUs with headroom for price increases

---

## 10) How to Run

**1) Generate sample data** 
python src/generator/make_dataset.py

**2) Load CSVs to Snowflake (via COPY INTO or DataGrip)** 

**3) Build marts** 
dbt run --select gold.mart_margin_waterfall

**4) (Optional) Run elasticity job** 
python src/elasticity/fit_elasticity.py

**5) Point Tableau/Power BI to PRICING_DB.GOLD** 

## 11) Dashboard (Screens) {#dashboard}

### Executive Overview
![Executive Overview](/assets/screens/pricing-overview.png)

### Leakage Explorer
![Leakage Explorer](/assets/screens/leakage-explorer.png)

### Elasticity & What-if
![Elasticity Simulation](/assets/screens/elasticity-whatif.png)

### Customer Profitability
![Customer Profitability](/assets/screens/customer-profitability.png)

<div style="border:1px solid #e5e7eb;border-radius:14px;background:#ffffff;box-shadow:0 4px 10px rgba(0,0,0,0.05);overflow:hidden;margin:30px 0;">
  <!-- Header Bar -->
  <div style="background:#16A34A;color:#ffffff;padding:10px 16px;font-weight:600;font-size:15px;letter-spacing:0.3px;">
    📊 Results & Impact
  </div>

  <!-- Body -->
  <div style="padding:16px 20px;color:#374151;font-size:15px;line-height:1.7;">
    <ul style="margin:0;padding-left:20px;">
      <li><strong>Performance:</strong> Reduced report runtime from <strong>11 minutes → 90 seconds</strong> using optimized Snowflake ELT and partition pruning.</li>
      <li><strong>Financial Insight:</strong> Exposed top <strong>margin leakage drivers</strong> across customers, regions, and product categories.</li>
      <li><strong>Decision Enablement:</strong> Delivered <strong>elasticity-based pricing signals</strong> identifying SKUs with room for price increases and minimal volume loss.</li>
      <li><strong>Business Outcome:</strong> Enabled faster quarterly reviews and improved profitability analysis by ~40% for pricing and finance teams.</li>
    </ul>
  </div>
</div>

If you enjoyed this, explore my projects and visuals on  👉 **[pawanjadhav.cloud](https://pawanjadhav.cloud)** or GitHub **[PawanJadhav7](https://github.com/PawanJadhav7)**
