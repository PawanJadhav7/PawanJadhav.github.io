---
title: "Finance — Data Engineering & Analytics"
layout: default
permalink: /finance.html
description: "Portfolio projects in finance data engineering — pricing, forecasting, fraud, and valuation."
---

<p style="margin:16px 0;">
  <a href="/" class="btn" style="display:inline-flex;align-items:center;gap:6px;
      padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;
      background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">
    ← Back to Home
  </a>
</p>

<section style="background:#fff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:24px 0;box-shadow:0 4px 10px rgba(0,0,0,.05);max-width:1100px;margin-left:auto;margin-right:auto;">
  <h1 style="color:#007ACC;margin:0 0 8px;">Finance — Data Engineering & Analytics</h1>
  <p style="color:#374151;margin:0;">
    Projects spanning <strong>pricing, forecasting, fraud, and valuation</strong> — building data foundations for financial decision-making.
  </p>
</section>

<style>
  .grid{
    display:grid;
    grid-template-columns:repeat(2,minmax(260px,1fr));
    gap:16px;
    max-width:1100px;
    margin:0 auto;
  }
  @media(max-width:800px){
    .grid{grid-template-columns:1fr}
  }
  .card{
    border:1px solid #e5e7eb;
    border-radius:12px;
    background:#fff;
    padding:16px;
    box-shadow:0 2px 6px rgba(0,0,0,.04)
  }
  .card h3{margin:0 0 6px;color:#1f2937}
  .card p{margin:0 0 10px;color:#374151;line-height:1.6}
  .meta{font-size:12px;color:#6b7280;margin-bottom:6px}
  .btn{
    display:inline-flex;align-items:center;justify-content:center;
    padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;
    background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;
    margin-right:8px;margin-bottom:6px;
  }
  .btn:hover{background:#fff;box-shadow:0 4px 14px rgba(0,0,0,.08)}
  .pill{
    display:inline-block;background:#eff6ff;color:#0f2e5e;
    border:1px solid #dbeafe;padding:2px 8px;
    border-radius:999px;font-size:12px;margin-right:6px;margin-bottom:4px;
  }
</style>

<section style="margin:24px 0;">
  <h2 style="color:#007ACC;margin:0 0 12px;max-width:1100px;margin-left:auto;margin-right:auto;">Featured Finance Projects</h2>

  <div class="grid">

    <!-- 1. Pricing & Margin Analytics (matches home) -->
    <article class="card">
      <span class="pill">Pricing</span><span class="pill">Margin</span>
      <h3>Pricing & Margin Analytics</h3>
      <div class="meta">Tech: Snowflake, Airflow, dbt, Power BI</div>
      <p>
        Integrates product, list price, discount, rebate, and cost data to compute <strong>net price, margin, and waterfall KPIs</strong>.
        Provides time-series marts by region, segment, and channel, powering exec dashboards and pricing playbooks.
      </p>
      <p>
        <a class="btn" href="https://github.com/PawanJadhav7/pricing-margin-analytics/blob/main/README.md" target="_blank" rel="noopener">💻 Code</a>
        <a class="btn" href="/pricingandmarginanalytics/" target="_self" rel="noopener">📄 Case Study</a>
      </p>
    </article>

    <!-- 2. Financial Forecasting Pipelines -->
    <article class="card">
      <span class="pill">Forecasting</span><span class="pill">Time-series</span>
      <h3>Financial Forecasting Pipelines</h3>
      <div class="meta">Tech: Snowflake Tasks, Python (ARIMA/Prophet), BI</div>
      <p>
        Automated ingestion and modeling for <strong>sales and margin forecasts</strong> by product and region.
        Uses Python-based models scheduled via Snowflake Tasks / Airflow, with outputs feeding planning dashboards.
      </p>
      <p>
        <a class="btn" href="#" target="_blank" rel="noopener">💻 Code</a>
        <a class="btn" href="#" target="_blank" rel="noopener">📊 Forecast Dashboard</a>
      </p>
    </article>

    <!-- 3. Transaction Fraud Analytics (matches home) -->
    <article class="card">
      <span class="pill">Fraud</span><span class="pill">Realtime</span>
      <h3>Transaction Fraud Analytics</h3>
      <div class="meta">Tech: event streams, Snowflake, Python</div>
      <p>
        Processes streaming transaction events into a <strong>fraud monitoring mart</strong> with features like velocity, geo-distance,
        device fingerprints, merchant risk, and rule/ML scores. Supports alert queues and analyst workflows.
      </p>
      <p>
        <a class="btn" href="#" target="_blank" rel="noopener">💻 Code</a>
        <a class="btn" href="#" target="_blank" rel="noopener">📊 Fraud Dashboard</a>
      </p>
    </article>

    <!-- 4. Treasury Cash Flow & Liquidity Analytics -->
    <article class="card">
      <span class="pill">Liquidity</span><span class="pill">Treasury</span>
      <h3>Treasury Cash Flow & Liquidity Analytics</h3>
      <div class="meta">Tech: SQL, Snowflake, scheduled exports</div>
      <p>
        Consolidates <strong>AP, AR, and bank statement</strong> data into a unified view of <strong>cash position, short-term forecasts, and covenant metrics</strong>.  
        Supports working capital analysis and scenario planning.
      </p>
      <p>
        <a class="btn" href="#" target="_blank" rel="noopener">📄 Data Model</a>
        <a class="btn" href="#" target="_blank" rel="noopener">📊 Liquidity Dashboard</a>
      </p>
    </article>

    <!-- 5. Valuation & DCF Analytics Workspace -->
    <article class="card">
      <span class="pill">DCF</span><span class="pill">Valuation</span>
      <h3>Valuation & DCF Analytics Workspace</h3>
      <div class="meta">Tech: Python, pandas, Excel/Power BI</div>
      <p>
        Python-based toolkit for <strong>DCF valuation</strong> including UFCF modeling, WACC, sensitivity tables, and scenario analysis.
        Integrates with spreadsheets / BI for analyst-friendly interfaces and audit trails.
      </p>
      <p>
        <a class="btn" href="#" target="_blank" rel="noopener">💻 DCF Code</a>
        <a class="btn" href="assets/DCFValuation.pdf" target="_blank" rel="noopener">📄 Sample Certification</a>
      </p>
    </article>

  </div>
</section>

<section style="margin:24px 0;">
  <h2 style="color:#007ACC;margin:0 0 12px;max-width:1100px;margin-left:auto;margin-right:auto;">What this demonstrates</h2>
  <ul style="margin:0;color:#374151;line-height:1.8;max-width:1100px;margin-left:auto;margin-right:auto;">
    <li>Designing <strong>financial data models</strong> for pricing, forecasting, treasury, and fraud.</li>
    <li>Combining <strong>SQL, Python, and BI</strong> for end-to-end analytics delivery.</li>
    <li>Building <strong>valuation and DCF tooling</strong> aligned with finance practice.</li>
  </ul>
</section>

<section style="text-align:center;margin:36px 0 10px;color:#6b7280;font-size:14px;">
  © 2025 Pawan Jadhav — Finance Portfolio
</section>
