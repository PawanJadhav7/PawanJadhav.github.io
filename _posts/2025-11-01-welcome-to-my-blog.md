---
layout: post
title: "Welcome — Data Engineering in Healthcare & Finance"
date: 2025-11-01 10:00:00 -0500
tags: [healthcare, finance, snowflake, aws, dbt]
hero_image: /assets/headers/claims-pipeline.jpg
---

> **TL;DR:** We replaced fragile full reloads with a CDC-driven pipeline:
> Oracle → (DMS) → S3 → (Glue) → Snowflake → (dbt). Result: faster loads, lower cost, audit-ready.

## Context & Problem
<!-- 3–5 sentences -->

## Architecture (High Level)
<!-- Describe; insert diagram later -->

## Build Guide: 10 Steps
<!-- Use the outline above, turn bullets into short paragraphs -->

## Snippets
```sql
-- Example Snowflake MERGE for SCD2
