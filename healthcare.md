---
title: "Healthcare — Data Engineering & Analytics"
layout: default
permalink: /healthcare.html
description: "Portfolio projects in healthcare data engineering — FHIR, claims, clinical analytics, and quality."
---

<p style="margin:16px 0;">
  <a href="/" class="btn" style="display:inline-flex;align-items:center;gap:6px;
      padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;
      background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">
    ← Back to Home
  </a>
</p>

<section style="background:#fff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:24px 0;box-shadow:0 4px 10px rgba(0,0,0,.05);max-width:1100px;margin-left:auto;margin-right:auto;">
  <h1 style="color:#007ACC;margin:0 0 8px;">Healthcare — Data Engineering & Analytics</h1>
  <p style="color:#374151;margin:0;">
    Projects across <strong>FHIR, claims, EHR, and quality</strong> — enabling interoperable data platforms, integrity monitoring, and care performance.
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
  <h2 style="color:#007ACC;margin:0 0 12px;max-width:1100px;margin-left:auto;margin-right:auto;">Featured Healthcare Projects</h2>

  <div class="grid">

    <!-- 1. FHIR ETL — Spark to Snowflake (matches home) -->
    <article class="card">
      <span class="pill">FHIR</span><span class="pill">Spark</span><span class="pill">Snowflake</span>
      <h3>FHIR ETL — Spark to Snowflake</h3>
      <div class="meta">Tech: PySpark, Delta/Parquet, Snowflake Streams/Tasks, dbt</div>
      <p>
        End-to-end ingestion of <strong>FHIR resources (Patient, Encounter, Observation, Claim)</strong> into curated Snowflake models.
        Includes flattening, schema validation, ICD-10 / LOINC enrichment, SCD2 dimensions, and dbt tests for data quality.
      </p>
      <p>
        <a class="btn" href="https://github.com/PawanJadhav7/fhir-enrichment-pipeline/blob/main/README.md" target="_blank" rel="noopener">💻 Code</a>
        <a class="btn" href="/assets/diagrams/fhir_snowflake.png" target="_blank" rel="noopener">📊 Architecture</a>
        <a class="btn" href="/projects/healthcare-fhir-etl/" target="_blank" rel="noopener">📄 Case Study</a>
      </p>
    </article>

    <!-- 2. Healthcare Claims — Anomaly Detection (matches home) -->
    <article class="card">
      <span class="pill">Claims</span><span class="pill">ICD-10</span><span class="pill">Anomaly</span>
      <h3>Healthcare Claims — Anomaly Detection</h3>
      <div class="meta">Tech: Python (pandas/PySpark), feature engineering, BI</div>
      <p>
        Claims profiling and anomaly scoring using <strong>ICD-10 groupers, utilization patterns, cost outliers, and frequency spikes</strong>.
        Generates prioritized review queues and summary dashboards for integrity teams (FWA).
      </p>
      <p>
        <a class="btn" href="https://github.com/PawanJadhav7/healthcare-claims-anomaly-detection/blob/main/README.md" target="_blank" rel="noopener">💻 Code</a>
        <a class="btn" href="{{ '/healthcare-claims-anomaly-detection/' | relative_url }}" target="_blank" rel="noopener">📄 Case Study</a>
      </p>
    </article>

    <!-- 3. Patient Utilization & LOS Dashboard -->
    <article class="card">
      <span class="pill">Utilization</span><span class="pill">LOS</span>
      <h3>Patient Utilization & LOS Dashboard</h3>
      <div class="meta">Tech: Snowflake, semantic layer, Looker Studio</div>
      <p>
        Combines <strong>EHR encounters, claims, and provider data</strong> into marts for utilization, length of stay (LOS),
        readmissions, and throughput. Exposes flexible filters for payer type, diagnosis groups, and service lines.
      </p>
      <p>
        <a class="btn" href="https://lookerstudio.google.com/..." target="_blank" rel="noopener">📊 Live Dashboard</a>
        <a class="btn" href="/blog/los-trends.md" target="_blank" rel="noopener">📝 Design Notes</a>
      </p>
    </article>

    <!-- 4. Provider Network & Leakage Analytics -->
    <article class="card">
      <span class="pill">Network</span><span class="pill">Leakage</span>
      <h3>Provider Network & Leakage Analytics</h3>
      <div class="meta">Tech: SQL, graph-style modeling, BI</div>
      <p>
        Models patient flows across <strong>in-network and out-of-network providers</strong> to quantify leakage, referral patterns,
        and high-opportunity service lines. Supports network optimization and contracting strategy.
      </p>
      <p>
        <a class="btn" href="#" target="_blank" rel="noopener">💻 Code</a>
        <a class="btn" href="#" target="_blank" rel="noopener">📊 Network Dashboard</a>
      </p>
    </article>

    <!-- 5. Readmission Risk & Care Management Feature Store -->
    <article class="card">
      <span class="pill">Feature Store</span><span class="pill">Readmission</span>
      <h3>Readmission Risk & Care Management Feature Store</h3>
      <div class="meta">Tech: Databricks, Delta Lake, feature store</div>
      <p>
        Curates patient-level features like <strong>comorbidities, prior utilization, SDoH proxies, and discharge disposition</strong>
        into an ML-ready feature store for 30-day readmission and care management prioritization models.
      </p>
      <p>
        <a class="btn" href="#" target="_blank" rel="noopener">💻 Feature Engineering</a>
        <a class="btn" href="#" target="_blank" rel="noopener">📄 Data Dictionary</a>
      </p>
    </article>

  </div>
</section>

<section style="margin:24px 0;">
  <h2 style="color:#007ACC;margin:0 0 12px;max-width:1100px;margin-left:auto;margin-right:auto;">What this demonstrates</h2>
  <ul style="margin:0;color:#374151;line-height:1.8;max-width:1100px;margin-left:auto;margin-right:auto;">
    <li>Designing <strong>healthcare-native data models</strong> across FHIR, claims, and EHR sources.</li>
    <li>Building <strong>cloud data platforms</strong> for quality, utilization, and integrity analytics.</li>
    <li>Preparing <strong>ML-ready feature layers</strong> for risk, readmission, and network optimization.</li>
  </ul>
</section>

<section style="text-align:center;margin:36px 0 10px;color:#6b7280;font-size:14px;">
  © 2025 Pawan Jadhav — Healthcare Portfolio
</section>
