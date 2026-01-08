---
layout: default
title: "Healthcare Claims Anomaly Detection — Python • ML • BI"
permalink: /healthcare-claims-anomaly-detection/
date: 2025-11-10 10:00:00 -0500
tags: [healthcare, claims, fraud, fwa, anomaly-detection, python, machine-learning, analytics]
hero_image: /assets/headers/healthcare-claims-hero.jpg
summary: "Recognizing abnormal utilization, coding, and cost patterns in healthcare claims using explainable anomaly detection for SIU and program integrity teams."
seo:
  description: "Production-style healthcare claims anomaly detection project using ICD-10, utilization signals, peer benchmarking, Isolation Forest, and BI dashboards."
  image: /assets/headers/healthcare-claims-hero.jpg
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

  <a class="btn" href="https://github.com/PawanJadhav7/healthcare-claims-anomaly-detection" target="_blank" rel="noopener noreferrer"
     style="flex:1 1 200px;max-width:240px;
            display:inline-flex;align-items:center;justify-content:center;gap:6px;
            padding:8px 14px;border-radius:8px;border:1px solid #e5e7eb;
            background:#f8fafc;color:#111827;text-decoration:none;
            font-size:14px;line-height:1;font-weight:500;">
     💻 Code
  </a>

  <a class="btn" href="{{ '/healthcare-claims-anomaly-detection/' | relative_url }}#dashboard" 
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
  <div style="background:#0F766E;color:#ffffff;padding:10px 16px;font-weight:600;font-size:15px;letter-spacing:0.3px;">
    ⚡ TL;DR — Executive Summary:
  </div>
  
  <!-- Body -->
  <div style="padding:16px 20px;color:#374151;font-size:15px;line-height:1.4;">
    <strong>Healthcare Claims Anomaly Detection for Fraud, Waste & Abuse (FWA)</strong><br><br>
    Builds an <strong>explainable anomaly detection pipeline</strong> to flag abnormal provider and member behavior using
    <strong>ICD-10 coding patterns, utilization intensity, cost signals, and peer benchmarks</strong>.<br><br>
    Designed for <strong>SIU / Program Integrity teams</strong> to prioritize investigations with transparent drivers
    rather than opaque black-box scores.<br><br>
    <strong>Stack:</strong> Python (pandas, scikit-learn) • Feature Engineering • Isolation Forest • Robust Peer Z-Scores • Tableau / Power BI
  </div>
</div>

---

## Contents
- [1) Business Problem](#business-problem)
- [2) Objectives & KPIs](#objectives--kpis)
- [3) Data Sources](#data-sources)
- [4) Architecture](#architecture)
- [5) Feature Store Design](#feature-store-design)
- [6) Anomaly Detection Logic](#anomaly-detection-logic)
- [7) Explainability & Governance](#explainability--governance)
- [8) Results & Impact](#results--impact)
- [9) How to Run](#how-to-run)
- [10) Dashboard (Screens)](#dashboard)
- [11) Credits & Contact](#credits--contact)

---

## 1) Business Problem

Healthcare payers process **millions of claims per day**, making manual detection of fraud, waste, and abuse impractical.

Traditional rule-based systems:
- Generate **high false positives**
- Miss emerging patterns
- Provide limited explainability for audits and appeals

**SIU teams need** a ranked, explainable view of *which provider-months or member-months deserve attention first*.

---

## 2) Objectives & KPIs

### Objectives
- Identify abnormal **utilization, cost, and coding behavior**
- Benchmark providers against **true peers** (specialty + state + time)
- Reduce noise while preserving investigatory explainability
- Produce **BI-ready outputs** for operational triage

### Core KPIs / Signals
- Claims per member
- Cost per claim (mean & p95)
- Weekend billing %
- E/M upcoding mix (99214 vs 99213)
- ICD-10 entropy & rare diagnosis rate
- Provider hopping index (members)
- Composite anomaly risk score

---

## 3) Data Sources

**Synthetic / De-identified Healthcare Claims**
- Medical claims (ICD-10-CM, CPT, POS)
- Provider attributes (specialty, state)
- Member attributes (state, utilization)
- Allowed & paid amounts

> Demo uses **synthetic claims generated via Python** to mirror real payer data structures.

---

## 4) Architecture

<div style="display:flex;flex-wrap:wrap;align-items:center;justify-content:space-between;gap:24px;margin-top:12px;">
  <div style="flex:1 1 320px;min-width:300px;max-width:520px;">
    <p style="margin:0 0 8px;color:#374151;line-height:1.6;">
      <strong>- Ingestion:</strong> Python generators & CSV inputs<br>
      <strong>- Profiling:</strong> Data quality, distributions, baselines<br>
      <strong>- Feature Store:</strong> Provider-month & member-month marts<br>
      <strong>- Detection:</strong> Peer robust z-scores + Isolation Forest<br>
      <strong>- Outputs:</strong> Ranked risk tables for BI<br>
      <strong>- Analytics:</strong> Tableau / Power BI dashboards
    </p>
  </div>

  <div style="flex:1 1 420px;min-width:360px;display:flex;justify-content:center;align-items:flex-start;margin-top:-20px;">
    <img src="/assets/images/healthcare-claims-architecture.png" 
         alt="Healthcare Claims Anomaly Detection Architecture"
         style="width:420px;max-width:100%;height:auto;border:1px solid #e5e7eb;
                border-radius:12px;box-shadow:0 4px 10px rgba(0,0,0,0.05);">
  </div>
</div>

---

## 5) Feature Store Design

### Provider-Month Features
- Claims, members, claims/member
- Allowed & paid cost aggregates
- Weekend billing %
- E/M mix & imaging rates
- ICD-10 entropy & rare diagnosis rate
- Rolling 3- and 6-month baselines
- Spike & shift indicators

### Member-Month Features
- Claims & providers visited
- Provider hopping index
- Utilization & cost spikes
- Specialty diversity

---

## 6) Anomaly Detection Logic

**Explainable Layer (Peer Benchmarking)**
- Robust z-scores within:
  `specialty × state × month`
- Highlights behavior *above peer norms*

**Multivariate Layer (ML)**
- Isolation Forest on utilization + cost + coding signals
- Captures nonlinear interactions missed by rules

**Composite Risk Score**
