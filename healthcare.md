---
title: "Healthcare — Data Engineering & Analytics"
layout: default
permalink: /healthcare.html
description: "Portfolio projects in healthcare data engineering, FHIR, and analytics."
---

<section style="background:#fff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:24px 0;box-shadow:0 4px 10px rgba(0,0,0,.05);">
  <h1 style="color:#007ACC;margin:0 0 8px;">Healthcare — Data Engineering & Analytics</h1>
  <p style="color:#374151;margin:0;">
    Selected projects across FHIR ETL, claims analytics, and healthcare data quality — built with modern cloud platforms and best practices.
  </p>
</section>

<style>
  .grid{display:grid;grid-template-columns:repeat(2,minmax(260px,1fr));gap:16px}
  @media(max-width:800px){.grid{grid-template-columns:1fr}}
  .card{border:1px solid #e5e7eb;border-radius:12px;background:#fff;padding:16px;box-shadow:0 2px 6px rgba(0,0,0,.04)}
  .card h3{margin:0 0 6px;color:#1f2937}
  .card p{margin:0 0 10px;color:#374151;line-height:1.6}
  .meta{font-size:12px;color:#6b7280;margin-bottom:6px}
  .btn{display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;margin-right:8px}
  .btn:hover{background:#fff;box-shadow:0 4px 14px rgba(0,0,0,.08)}
  .pill{display:inline-block;background:#eff6ff;color:#0f2e5e;border:1px solid #dbeafe;padding:2px 8px;border-radius:999px;font-size:12px;margin-right:6px}
</style>

<section style="margin:24px 0;">
  <h2 style="color:#007ACC;margin:0 0 12px;">Featured Healthcare Projects</h2>
  <div class="grid">

    <!-- Project 1: FHIR ETL -->
    <article class="card">
      <span class="pill">FHIR</span><span class="pill">ETL</span><span class="pill">Snowflake</span>
      <h3>FHIR ETL on Spark → Snowflake</h3>
      <div class="meta">Tech: Spark, PyArrow, Pandera, dbt (optional), Snowflake</div>
      <p>
        End-to-end ingestion of HL7 FHIR (Patient, Encounter, Observation) JSON into curated Snowflake models.
        Includes flattening, DQ checks, ICD-10/LOINC enrichment, features (e.g., lactate flags), and star schema for analytics.
      </p>
      <p>
        <a class="btn" href="https://github.com/PawanJadhav7/fhir-enrichment-pipeline" target="_blank" rel="noopener">💻 Code</a>
        <a class="btn" href="/assets/diagrams/fhir_enrichment_arch.png" target="_blank" rel="noopener">📊 Architecture</a>
        <a class="btn" href="/projects/healthcare-fhir-etl/" target="_blank" rel="noopener">📄 Case Study</a>
      </p>
    </article>

    <!-- Project 2: Claims Anomaly Detection -->
    <article class="card">
      <span class="pill">Claims</span><span class="pill">ICD-10</span><span class="pill">Anomaly</span>
      <h3>Healthcare Claims — Anomaly Detection</h3>
      <div class="meta">Tech: Python (pandas), feature engineering, dashboard</div>
      <p>
        Profiling and anomaly signals across claim lines using ICD-10 and utilization patterns (cost outliers, frequency spikes).
        Delivers prioritized review lists and a lightweight monitoring dashboard.
      </p>
      <p>
        <a class="btn" href="https://github.com/PawanJadhav/Healthcare-Claims" target="_blank" rel="noopener">💻 Code</a>
        <a class="btn" href="/projects/healthcare-claims/" target="_blank" rel="noopener">📄 Case Study</a>
      </p>
    </article>

  </div>
</section>

<section style="margin:24px 0;">
  <h2 style="color:#007ACC;margin:0 0 12px;">What this demonstrates</h2>
  <ul style="margin:0;color:#374151;line-height:1.8;">
    <li>FHIR/HL7 interoperability, vocabulary enrichment (ICD-10, LOINC)</li>
    <li>Cloud-ready pipelines with schema validation and curated models</li>
    <li>Analytics delivery for clinical and operational decisions</li>
  </ul>
</section>

<section style="text-align:center;margin:36px 0 10px;color:#6b7280;font-size:14px;">
  © 2025 Pawan Jadhav — Healthcare Portfolio
</section>
