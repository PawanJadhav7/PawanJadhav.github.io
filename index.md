---
title: "Pawan Jadhav PMP® — Data Engineering & Analytics"
layout: default
---
<!-- ====== NAVIGATION BAR ====== -->
<nav id="navbar" style="background:#ffffff;border-bottom:1px solid #e5e7eb;box-shadow:0 2px 6px rgba(0,0,0,0.05);position:sticky;top:0;z-index:1000;">
  <div style="max-width:1100px;margin:0 auto;padding:12px 24px;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;">
    
    <!-- Logo / Name -->
    <a href="#home" style="font-weight:700;font-size:18px;color:#007ACC;text-decoration:none;">Pawan Jadhav</a>

    <!-- Navigation Links -->
    <div id="nav-links" style="display:flex;gap:20px;flex-wrap:wrap;">
      <a href="#home" class="nav-link" style="color:#374151;text-decoration:none;font-weight:500;">Home</a>
      <a href="#cloud" class="nav-link" style="color:#374151;text-decoration:none;font-weight:500;">Cloud</a>
      <a href="#healthcare" class="nav-link" style="color:#374151;text-decoration:none;font-weight:500;">Healthcare</a>
      <a href="#finance" class="nav-link" style="color:#374151;text-decoration:none;font-weight:500;">Finance</a>
      <a href="#projectmanagement" class="nav-link" style="color:#374151;text-decoration:none;font-weight:500;">Project Management</a>
    </div>
  </div>
</nav>

<style>
  html{scroll-behavior:smooth;}
  .nav-link.active {
    color:#007ACC !important;
    font-weight:600;
    text-decoration:underline;
  }
</style>

<script>
  // --- Active link highlight on scroll ---
  document.addEventListener("DOMContentLoaded", () => {
    const sections = document.querySelectorAll("section[id]");
    const navLinks = document.querySelectorAll(".nav-link");

    function activateLink() {
      let scrollPos = window.scrollY + 120; // offset for sticky navbar height

      sections.forEach((section) => {
        const top = section.offsetTop;
        const height = section.offsetHeight;
        const id = section.getAttribute("id");

        if (scrollPos >= top && scrollPos < top + height) {
          navLinks.forEach((link) => {
            link.classList.remove("active");
            if (link.getAttribute("href") === "#" + id) {
              link.classList.add("active");
            }
          });
        }
      });
    }

    window.addEventListener("scroll", activateLink);
  });
</script>




<div class="hero" style="display:flex;align-items:center;justify-content:flex-start;gap:24px;flex-wrap:nowrap;margin-top:20px;">

  <!-- Profile Image on the Left -->
  <img src="assets/images/QA_Tester.jpg" alt="Pawan Jadhav" width="160"
       style="border-radius:50%;box-shadow:0 2px 8px rgba(0,0,0,0.2);flex-shrink:0;">

  <!-- Text Content on the Right -->
  <div style="max-width:700px;">
    <h1 style="color:#007ACC;margin:0 0 8px;font-size:28px;line-height:1.2;">Pawan Jadhav PMP® — Data Engineering & Analytics</h1>
    <p style="margin:0;font-size:17px;line-height:1.6;color:#374151;">
      <strong>
        Engineering trust and intelligence in Big Data — transforming healthcare and finance through secure, insight-driven innovation.
      </strong>
    </p>
  </div>

</div>



<section id="home" style="background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);">

  <h2 style="color:#007ACC;margin-top:0;">Professional Summary</h2>

  <p style="font-size:16px;line-height:1.7;color:#374151;margin-bottom:1em;">
    I am a results-driven <strong>Data Engineering and Analytics professional</strong> and <strong>Certified Project Management Professional (PMP®)</strong> with deep experience in
    <strong>healthcare and financial data ecosystems</strong>. I specialize in designing secure, scalable, and
    cost-optimized <strong>Big Data pipelines</strong> that transform raw data into actionable insights for decision-making,
    compliance, and strategic growth.
  </p>

  <p style="font-size:16px;line-height:1.7;color:#374151;margin-bottom:1em;">
    My expertise spans <strong>ETL/ELT development</strong>, <strong>data governance</strong>, and <strong>cloud integration</strong> across
    <strong>Azure, AWS, and Snowflake</strong>, leveraging tools such as <strong>Databricks, Airflow, and SQL</strong> to build automated
    and auditable workflows. I apply project management principles to every stage of development — from scope definition to delivery — ensuring
    projects meet quality, cost, and timeline objectives.
  </p>

  <p style="font-size:16px;line-height:1.7;color:#374151;margin-bottom:0;">
    Combining strong technical acumen with <strong>leadership, stakeholder management, and agile execution</strong> skills, I bridge
    engineering precision with business strategy. Passionate about using data to improve <strong>healthcare quality, financial transparency,
    and operational efficiency</strong>, I focus on turning complex challenges into scalable, insight-driven solutions that deliver measurable impact.
  </p>

</section>
<section style="background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);">

  <h2 style="color:#007ACC;margin-top:0;">Skills</h2>

  <!-- Skill Categories -->
  <div style="display:flex;flex-wrap:wrap;gap:24px;">

    <!-- Data Engineering -->
    <div style="flex:1;min-width:250px;">
      <h3 style="margin:0 0 8px;color:#374151;">Data Engineering & ETL</h3>
      <p style="margin:0;color:#374151;line-height:1.6;">
        SQL / Python / PySpark / Databricks / Airflow / NiFi / Snowflake / DBT / Azure ADF / AWS Glue / ETL Design & Optimization
      </p>
    </div>

    <!-- Data Analytics -->
    <div style="flex:1;min-width:250px;">
      <h3 style="margin:0 0 8px;color:#374151;">Data Analytics & Visualization</h3>
      <p style="margin:0;color:#374151;line-height:1.6;">
        Power BI / Tableau / Looker Studio / Advanced Excel / Statistical Analysis / Data Modeling / KPIs & Reporting Automation
      </p>
    </div>

    <!-- Project Management -->
    <div style="flex:1;min-width:250px;">
      <h3 style="margin:0 0 8px;color:#374151;">Project Management & Leadership</h3>
      <p style="margin:0;color:#374151;line-height:1.6;">
        PMP® Certified / Agile Scrum / SDLC Lifecycle / Stakeholder Management / Risk Mitigation / Delivery Planning / Governance
      </p>
    </div>

    <!-- Tools & Platforms -->
    <div style="flex:1;min-width:250px;">
      <h3 style="margin:0 0 8px;color:#374151;">Tools & Platforms</h3>
      <p style="margin:0;color:#374151;line-height:1.6;">
        Git / GitHub Actions / Docker / Linux Shell / PyCharm / DataGrip / Jupyter / Azure DevOps / ServiceNow / Jira
      </p>
    </div>

  </div>

</section>

<section style="background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);" aria-label="Featured Projects">

  <h2 style="color:#007ACC;margin-top:0;display:flex;align-items:center;justify-content:space-between;">
    Featured Projects
    <span class="fp-nav" style="display:flex;gap:8px;">
      <button id="fp-prev" aria-label="Previous" style="border:1px solid #e5e7eb;background:#f8fafc;border-radius:10px;padding:8px 10px;cursor:pointer;">◀</button>
      <button id="fp-next" aria-label="Next" style="border:1px solid #e5e7eb;background:#f8fafc;border-radius:10px;padding:8px 10px;cursor:pointer;">▶</button>
    </span>
  </h2>

  <style>
    /* Carousel track */
    .fp-track{
      display:flex;
      gap:20px;
      overflow-x:auto;
      scroll-snap-type:x mandatory;
      scroll-behavior:smooth;
      padding:4px 2px 10px;
      -webkit-overflow-scrolling:touch;
    }
    /* Hide scrollbar (keeps accessible scrolling) */
    .fp-track::-webkit-scrollbar{height:8px}
    .fp-track::-webkit-scrollbar-thumb{background:#e5e7eb;border-radius:8px}
    /* Cards */
    .fp-card{
      flex:0 0 350px;           /* card width */
      scroll-snap-align:start;
      border:1px solid #e5e7eb;
      border-radius:12px;
      padding:18px;
      background:#fff;
      box-shadow:0 4px 8px rgba(0,0,0,0.03);
    }
    .fp-card h3{ margin:0 0 8px; color:#007ACC; font-size:18px; }
    .fp-card p{ margin:0 0 10px; color:#374151; line-height:1.6; font-size:15px; }
    .fp-impact{ font-size:14px; color:#6b7280; margin:0 0 10px; }
    .fp-btns{ display:flex; gap:10px; flex-wrap:wrap; }
    .btn{ display:inline-flex; align-items:center; justify-content:center; padding:10px 16px; border-radius:10px; border:1px solid #e5e7eb; background:#f8fafc; color:#111827; text-decoration:none; font-weight:500; transition:all .2s; }
    .btn:hover{ background:#fff; box-shadow:0 4px 14px rgba(0,0,0,.08); text-decoration:none; }
    @media (max-width:420px){ .fp-card{flex-basis:280px} }
  </style>

  <div id="fpTrack" class="fp-track" tabindex="0">
    <!-- Project 1 -->
    <article class="fp-card">
      <h3>FHIR ETL on Spark → Snowflake</h3>
      <p>End-to-end pipeline for FHIR JSON into curated Snowflake models. SCD2 for Member/Provider, DQ checks, lineage with dbt.</p>
      <p class="fp-impact"><strong>Impact:</strong> 2.5× faster loads; ~30% cost savings.</p>
      <div class="fp-btns">
        <a class="btn" href="https://github.com/PawanJadhav/FHIR-Snowflake" target="_blank" rel="noopener noreferrer">💻 Code</a>
        <a class="btn" href="/assets/diagrams/fhir_snowflake.png" target="_blank" rel="noopener noreferrer">📊 Architecture</a>
      </div>
    </article>

    <!-- Project 2 -->
    <article class="fp-card">
      <h3>Healthcare Claims Anomaly Detection</h3>
      <p>ICD-10 CM + provider signals with Python/Spark for real-time anomaly scoring across fraud, waste, abuse.</p>
      <p class="fp-impact"><strong>Impact:</strong> ↓ false positives ~18%; faster integrity reviews.</p>
      <div class="fp-btns">
        <a class="btn" href="https://github.com/PawanJadhav/Healthcare-Claims" target="_blank" rel="noopener noreferrer">💻 Code</a>
        <a class="btn" href="/projects/healthcare-claims/" target="_blank" rel="noopener noreferrer">📄 Case Study</a>
      </div>
    </article>

    <!-- Project 3 -->
    <article class="fp-card">
      <h3>Finance Pricing & Margin Analytics</h3>
      <p>Airflow + Snowflake ELT; time-series KPIs & margin forecasts; exec dashboards for decision speed.</p>
      <p class="fp-impact"><strong>Impact:</strong> p95 report time 11m → 90s.</p>
      <div class="fp-btns">
        <a class="btn" href="https://github.com/PawanJadhav/Finance-Analytics" target="_blank" rel="noopener noreferrer">💻 Code</a>
        <a class="btn" href="/projects/finance-fraud/" target="_blank" rel="noopener noreferrer">📄 Case Study</a>
      </div>
    </article>

    <!-- Copy/paste more .fp-card blocks here for additional projects -->
  </div>

  <script>
    (function(){
      const track = document.getElementById('fpTrack');
      const prev = document.getElementById('fp-prev');
      const next = document.getElementById('fp-next');

      function cardWidth(){
        const card = track.querySelector('.fp-card');
        if(!card) return 340;
        const styles = getComputedStyle(track);
        const gap = parseInt(styles.columnGap || styles.gap || 20, 10);
        return card.getBoundingClientRect().width + gap;
      }

      function scrollByCard(dir){
        track.scrollBy({ left: dir * cardWidth(), behavior: 'smooth' });
      }

      prev.addEventListener('click', () => scrollByCard(-1));
      next.addEventListener('click', () => scrollByCard(1));

      // Keyboard support (← →)
      track.addEventListener('keydown', (e) => {
        if (e.key === 'ArrowRight') { e.preventDefault(); scrollByCard(1); }
        if (e.key === 'ArrowLeft')  { e.preventDefault(); scrollByCard(-1); }
      });
    })();
  </script>
</section>

<section style="background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);" aria-label="Publications & Dashboards">

  <h2 style="color:#007ACC;margin-top:0;display:flex;align-items:center;justify-content:space-between;">
    Publications & Dashboards
    <span class="pd-nav" style="display:flex;gap:8px;">
      <button id="pd-up" aria-label="Previous" style="border:1px solid #e5e7eb;background:#f8fafc;border-radius:10px;padding:8px 10px;cursor:pointer;">▲</button>
      <button id="pd-down" aria-label="Next" style="border:1px solid #e5e7eb;background:#f8fafc;border-radius:10px;padding:8px 10px;cursor:pointer;">▼</button>
    </span>
  </h2>

  <style>
    .pd-viewport{
      /* fixed visible area; adjust height as you like */
      max-height: 420px;
      overflow-y: auto;
      padding-right: 4px;
      scroll-snap-type: y mandatory;
      scroll-behavior: smooth;
    }
    .pd-viewport::-webkit-scrollbar{ width:8px }
    .pd-viewport::-webkit-scrollbar-thumb{ background:#e5e7eb; border-radius:8px }

    .pd-stack{
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    .pd-card{
      scroll-snap-align: start;
      border:1px solid #e5e7eb;
      border-radius:12px;
      padding:14px 18px;
      background:#fff;
      box-shadow:0 2px 6px rgba(0,0,0,0.03);
    }
    .pd-card h3{
      margin:0 0 6px;
      color:#007ACC;
      font-size:17px;
      line-height:1.3;
    }
    .pd-card p{
      margin:0;
      color:#374151;
      line-height:1.6;
      font-size:15px;
    }
    .pd-links{
      margin-top:8px;
      font-size:14px;
    }
    .pd-links a{
      color:#007ACC; text-decoration:none; margin-right:10px;
      border:1px solid #e5e7eb; padding:6px 10px; border-radius:8px;
      display:inline-block;
    }
    .pd-links a:hover{ text-decoration:underline; background:#fff; box-shadow:0 4px 14px rgba(0,0,0,.06); }
  </style>

  <div id="pdViewport" class="pd-viewport" tabindex="0">
    <div id="pdStack" class="pd-stack">

      <!-- Card 1 -->
      <article class="pd-card">
        <h3>📘 ICD-10 CM Bulk Loader & Profiling</h3>
        <p>Python notebook for bulk ICD-10 CM loading, validation, and profiling to support DQ and healthcare analytics pipelines.</p>
        <p class="pd-links">
          <a href="https://nbviewer.org/..." target="_blank" rel="noopener noreferrer">View on nbviewer</a>
        </p>
      </article>

      <!-- Card 2 -->
      <article class="pd-card">
        <h3>📊 Utilization & LOS Trends Dashboard</h3>
        <p>Interactive dashboard tracking utilization, LOS, and resource efficiency using Looker Studio with healthcare claims data.</p>
        <p class="pd-links">
          <a href="https://lookerstudio.google.com/..." target="_blank" rel="noopener noreferrer">Live Dashboard</a>
          <a href="/blog/los-trends.md" target="_blank" rel="noopener noreferrer">Notes</a>
        </p>
      </article>

      <!-- Add more .pd-card blocks below as needed -->

    </div>
  </div>

  <script>
    (function(){
      const viewport = document.getElementById('pdViewport');
      const stack = document.getElementById('pdStack');
      const up = document.getElementById('pd-up');
      const down = document.getElementById('pd-down');

      function cardHeight(){
        const card = stack.querySelector('.pd-card');
        if(!card) return 160;
        const styles = getComputedStyle(stack);
        const gap = parseInt(styles.rowGap || styles.gap || 16, 10);
        return card.getBoundingClientRect().height + gap;
      }

      function scrollByCard(dir){
        viewport.scrollBy({ top: dir * cardHeight(), behavior: 'smooth' });
      }

      up.addEventListener('click', () => scrollByCard(-1));
      down.addEventListener('click', () => scrollByCard(1));

      // Keyboard support (↑ ↓)
      viewport.addEvent
</script>
</section>

<section id="certifications" style="background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);" aria-label="Certifications">

  <h2 style="color:#007ACC;margin-top:0;display:flex;align-items:center;justify-content:space-between;">
    Certifications
    <span style="display:flex;gap:8px;">
      <button type="button"
              aria-label="Previous"
              onclick="document.getElementById('certViewport').scrollBy({top:-360,behavior:'smooth'})"
              style="border:1px solid #e5e7eb;background:#f8fafc;border-radius:10px;padding:8px 10px;cursor:pointer;">▲</button>
      <button type="button"
              aria-label="Next"
              onclick="document.getElementById('certViewport').scrollBy({top:360,behavior:'smooth'})"
              style="border:1px solid #e5e7eb;background:#f8fafc;border-radius:10px;padding:8px 10px;cursor:pointer;">▼</button>
    </span>
  </h2>

  <!-- Scrollable Viewport (increase height if you want) -->
  <div id="certViewport" tabindex="0"
       style="max-height:520px;overflow-y:auto;padding-right:4px;scroll-snap-type:y mandatory;scroll-behavior:smooth;">
    
    <div style="display:flex;flex-direction:column;gap:16px;">

      <!-- 1. PMP -->
      <article style="scroll-snap-align:start;border:1px solid #e5e7eb;border-radius:12px;padding:14px 18px;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,0.03);">
        <h3 style="margin:0 0 6px;color:#007ACC;font-size:17px;">PMP® — Project Management Professional</h3>
        <p style="margin:0;color:#374151;font-size:15px;">Project Management Institute</p>
        <p style="margin:6px 0 0;font-size:13px;color:#6b7280;">Credential ID: 3787028<br>Issued: Mar 2024 · Expires: Mar 2027</p>
        <p style="margin-top:8px;">
          <a href="https://www.pmi.org/certifications/project-management-pmp" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;">About</a>
          <a href="#" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;margin-left:8px;">Verify</a>
        </p>
      </article>

      <!-- 2. DP-203 -->
      <article style="scroll-snap-align:start;border:1px solid #e5e7eb;border-radius:12px;padding:14px 18px;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,0.03);">
        <h3 style="margin:0 0 6px;color:#007ACC;font-size:17px;">DP-203 — Azure Data Engineer Associate</h3>
        <p style="margin:0;color:#374151;font-size:15px;">Microsoft</p>
        <p style="margin:6px 0 0;font-size:13px;color:#6b7280;">Credential ID: 2211773CB6CBA50F<br>Issued: Mar 2024 · Expires: Mar 2025</p>
        <p style="margin-top:8px;">
          <a href="https://learn.microsoft.com/credentials/certifications/azure-data-engineer/" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;">About</a>
          <a href="#" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;margin-left:8px;">Verify</a>
        </p>
      </article>

      <!-- 3. SnowPro Core -->
      <article style="display:none;scroll-snap-align:start;border:1px solid #e5e7eb;border-radius:12px;padding:14px 18px;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,0.03);">
        <h3 style="margin:0 0 6px;color:#007ACC;font-size:17px;">SnowPro Core Certification</h3>
        <p style="margin:0;color:#374151;font-size:15px;">Snowflake</p>
        <p style="margin:6px 0 0;font-size:13px;color:#6b7280;">Credential ID: xxxxxxx<br>Issued: 2025</p>
        <p style="margin-top:8px;">
          <a href="https://www.snowflake.com/certifications/snowpro-core/" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;">About</a>
        </p>
      </article>

      <!-- 4. Databricks DEA -->
      <article style="display:none;scroll-snap-align:start;border:1px solid #e5e7eb;border-radius:12px;padding:14px 18px;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,0.03);">
        <h3 style="margin:0 0 6px;color:#007ACC;font-size:17px;">Databricks Data Engineer Associate</h3>
        <p style="margin:0;color:#374151;font-size:15px;">Databricks</p>
        <p style="margin:6px 0 0;font-size:13px;color:#6b7280;">Credential ID: xxxxxxx<br>Issued: 2025</p>
        <p style="margin-top:8px;">
          <a href="https://www.databricks.com/learn/certification/data-engineer-associate" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;">About</a>
        </p>
      </article>

      <!-- 5. AWS CCP -->
      <article style="display:none;scroll-snap-align:start;border:1px solid #e5e7eb;border-radius:12px;padding:14px 18px;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,0.03);">
        <h3 style="margin:0 0 6px;color:#007ACC;font-size:17px;">AWS Certified Cloud Practitioner</h3>
        <p style="margin:0;color:#374151;font-size:15px;">Amazon Web Services</p>
        <p style="margin:6px 0 0;font-size:13px;color:#6b7280;">Credential ID: xxxxxxx<br>Issued: 2025</p>
        <p style="margin-top:8px;">
          <a href="https://aws.amazon.com/certification/certified-cloud-practitioner/" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;">About</a>
        </p>
      </article>

      <!-- 6. ITIL 4 Foundation -->
      <article style="display:none;scroll-snap-align:start;border:1px solid #e5e7eb;border-radius:12px;padding:14px 18px;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,0.03);">
        <h3 style="margin:0 0 6px;color:#007ACC;font-size:17px;">ITIL® 4 Foundation</h3>
        <p style="margin:0;color:#374151;font-size:15px;">AXELOS / PeopleCert</p>
        <p style="margin:6px 0 0;font-size:13px;color:#6b7280;">Credential ID: xxxxxxx<br>Issued: 2024</p>
        <p style="margin-top:8px;">
          <a href="https://www.axelos.com/certifications/itil-4-foundation" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;">About</a>
        </p>
      </article>

      <!-- 7. PSM I -->
      <article style="display:none;scroll-snap-align:start;border:1px solid #e5e7eb;border-radius:12px;padding:14px 18px;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,0.03);">
        <h3 style="margin:0 0 6px;color:#007ACC;font-size:17px;">Professional Scrum Master™ I (PSM I)</h3>
        <p style="margin:0;color:#374151;font-size:15px;">Scrum.org</p>
        <p style="margin:6px 0 0;font-size:13px;color:#6b7280;">Credential ID: xxxxxxx<br>Issued: 2024</p>
        <p style="margin-top:8px;">
          <a href="https://www.scrum.org/professional-scrum-certifications/psm-i-certification" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;">About</a>
        </p>
      </article>

      <!-- 8. HIPAA -->
      <article style="scroll-snap-align:start;border:1px solid #e5e7eb;border-radius:12px;padding:14px 18px;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,0.03);">
        <h3 style="margin:0 0 6px;color:#007ACC;font-size:17px;">HIPAA Privacy & Security Awareness</h3>
        <p style="margin:0;color:#374151;font-size:15px;">Accountable</p>
        <p style="margin:6px 0 0;font-size:13px;color:#6b7280;">Certificate #: 7a473b29-7fce-4813-a462-b7207e139c46<br>Valid: Aug 2025 – Aug 2026</p>
        <p style="margin-top:8px;">
          <a href="#" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;">About</a>
          <a href="#" target="_blank" rel="noopener noreferrer"
             style="color:#007ACC;text-decoration:none;border:1px solid #e5e7eb;padding:6px 10px;border-radius:8px;margin-left:8px;">Verify</a>
        </p>
      </article>

    </div>
  </div>
</section>



<section id="cloud" style="background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);" aria-label="Cloud Technologies">

  <h2 style="color:#007ACC;margin-top:0;display:flex;align-items:center;gap:10px;">
  <img src="/assets/images/cloud.gif" alt="Cloud Computing" width="36" height="36" style="vertical-align:middle;border-radius:6px;">
  Cloud
</h2>
  <p style="color:#374151;margin:6px 0 18px;">Platforms and tooling used to build secure, scalable data platforms.</p>

  <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:20px;">

    <!-- Azure -->
    <article id="azure" style="border:1px solid #e5e7eb;border-radius:12px;padding:18px;background:#fff;box-shadow:0 4px 8px rgba(0,0,0,0.03);">
      <h3 style="margin:0 0 10px;color:#007ACC;">Azure</h3>
      <p style="margin:0 0 10px;color:#374151;line-height:1.6;">
        ADLS • ADF • Databricks • Synapse • Azure SQL • Functions • Key Vault • DevOps (Pipelines)
      </p>
      <ul style="margin:10px 0 14px;padding-left:18px;color:#374151;line-height:1.6;">
        <li>FHIR → Bronze/Silver/Gold on Databricks (PySpark) with Delta + Medallion.</li>
        <li>ADF orchestrated ELT to Synapse/Snowflake with parameterized datasets.</li>
        <li>Event-driven Functions for micro-batch ingestion and DQ rule execution.</li>
      </ul>
      <div style="display:flex;gap:10px;flex-wrap:wrap;">
        <a class="btn" href="#featured-azure" style="display:inline-flex;align-items:center;justify-content:center;padding:10px 16px;border-radius:10px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-weight:500;">🔎 Featured</a>
        <a class="btn" href="/cloud.html#azure" target="_blank" rel="noopener noreferrer" style="display:inline-flex;align-items:center;justify-content:center;padding:10px 16px;border-radius:10px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-weight:500;">📄 View more</a>
      </div>
    </article>

    <!-- AWS -->
    <article id="aws" style="border:1px solid #e5e7eb;border-radius:12px;padding:18px;background:#fff;box-shadow:0 4px 8px rgba(0,0,0,0.03);">
      <h3 style="margin:0 0 10px;color:#007ACC;">AWS</h3>
      <p style="margin:0 0 10px;color:#374151;line-height:1.6;">
        S3 • Glue • DMS • Lambda • Step Functions • Athena • EMR • IAM
      </p>
      <ul style="margin:10px 0 14px;padding-left:18px;color:#374151;line-height:1.6;">
        <li>CDC via DMS → S3 → Glue ETL with partitioning & compaction (Parquet).</li>
        <li>Serverless Lambda validators + Step Functions for orchestration.</li>
        <li>Athena views for ad-hoc analytics; cost-aware lifecycle & Iceberg ready.</li>
      </ul>
      <div style="display:flex;gap:10px;flex-wrap:wrap;">
        <a class="btn" href="#featured-aws" style="display:inline-flex;align-items:center;justify-content:center;padding:10px 16px;border-radius:10px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-weight:500;">🔎 Featured</a>
        <a class="btn" href="/cloud.html#aws" target="_blank" rel="noopener noreferrer" style="display:inline-flex;align-items:center;justify-content:center;padding:10px 16px;border-radius:10px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-weight:500;">📄 View more</a>
      </div>
    </article>

  </div>
</section>
<section id="healthcare" style="background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);" aria-label="Healthcare Data Engineering & Analytics">

  <h2 style="color:#007ACC;margin-top:0;display:flex;align-items:center;gap:10px;">
    <img src="/assets/images/healthcare.jpg" alt="" width="36" height="36" style="vertical-align:middle;border-radius:6px;">
    Healthcare Data Engineering & Analytics
  </h2>
  <p style="color:#374151;margin:6px 0 18px;">
    Data pipelines and analytics designed for clinical, claims, and regulatory ecosystems — ensuring interoperability, integrity, and actionable intelligence.
  </p>

  <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:20px;">

    <!-- Project 1 -->
    <article style="border:1px solid #e5e7eb;border-radius:12px;padding:18px;background:#fff;box-shadow:0 4px 8px rgba(0,0,0,0.03);">
      <h3 style="color:#007ACC;margin-top:0;">FHIR ETL — Spark to Snowflake</h3>
      <p style="color:#374151;line-height:1.6;font-size:15px;">
        Built an automated ETL framework for ingesting <strong>FHIR-compliant JSON</strong> data using PySpark and Snowflake Streams/Tasks.  
        Implemented SCD2 for Member/Provider tables, dbt tests, and lineage tracking.
      </p>
      <p style="font-size:14px;color:#6b7280;"><strong>Impact:</strong> 2.5× faster loads, improved auditability, and 30% cost optimization.</p>
      <div style="display:flex;gap:10px;flex-wrap:wrap;">
        <a class="btn" href="https://github.com/PawanJadhav/FHIR-Snowflake" target="_blank" rel="noopener noreferrer">💻 Code</a>
        <a class="btn" href="/assets/diagrams/fhir_snowflake.png" target="_blank" rel="noopener noreferrer">📊 Architecture</a>
      </div>
    </article>

    <!-- Project 2 -->
    <article style="border:1px solid #e5e7eb;border-radius:12px;padding:18px;background:#fff;box-shadow:0 4px 8px rgba(0,0,0,0.03);">
      <h3 style="color:#007ACC;margin-top:0;">Claims Anomaly Detection</h3>
      <p style="color:#374151;line-height:1.6;font-size:15px;">
        Developed an anomaly detection pipeline using <strong>ICD-10 CM</strong> data to detect potential fraud, waste, and abuse in claims.  
        Integrated PySpark feature engineering, statistical modeling, and BI dashboards.
      </p>
      <p style="font-size:14px;color:#6b7280;"><strong>Impact:</strong> Reduced false positives by 18%; enabled near real-time integrity review.</p>
      <div style="display:flex;gap:10px;flex-wrap:wrap;">
        <a class="btn" href="https://github.com/PawanJadhav/Healthcare-Claims" target="_blank" rel="noopener noreferrer">💻 Code</a>
        <a class="btn" href="/projects/healthcare-claims/" target="_blank" rel="noopener noreferrer">📄 Case Study</a>
      </div>
    </article>

    <!-- Project 3 -->
    <article style="border:1px solid #e5e7eb;border-radius:12px;padding:18px;background:#fff;box-shadow:0 4px 8px rgba(0,0,0,0.03);">
      <h3 style="color:#007ACC;margin-top:0;">Patient Utilization & LOS Dashboard</h3>
      <p style="color:#374151;line-height:1.6;font-size:15px;">
        Designed a <strong>Looker Studio</strong> dashboard integrating EHR and claims data for patient utilization, LOS, and provider performance.  
        Created semantic models and data marts on Snowflake for interactive insights.
      </p>
      <p style="font-size:14px;color:#6b7280;"><strong>Impact:</strong> Streamlined operational decision-making across ACO partner networks.</p>
      <div style="display:flex;gap:10px;flex-wrap:wrap;">
        <a class="btn" href="https://lookerstudio.google.com/..." target="_blank" rel="noopener noreferrer">📊 Dashboard</a>
        <a class="btn" href="/blog/los-trends.md" target="_blank" rel="noopener noreferrer">📝 Notes</a>
      </div>
    </article>

  </div>

  <p style="text-align:right;margin-top:20px;">
    <a class="btn" href="/healthcare.html" target="_blank" rel="noopener noreferrer">📄 View More Healthcare Projects</a>
  </p>

</section>

<section id="finance" style="background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);" aria-label="Finance Data Engineering & Analytics">

  <h2 style="color:#007ACC;margin-top:0;display:flex;align-items:center;gap:10px;">
    <img src="/assets/images/finance.jpg" alt="" width="36" height="36" style="vertical-align:middle;border-radius:6px;">
    Finance Data Engineering & Analytics
  </h2>
  <p style="color:#374151;margin:6px 0 18px;">
    Scalable data systems for financial insights — integrating multi-source data for pricing, profitability, and performance intelligence.
  </p>

  <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:20px;">

    <!-- Project 1 -->
    <article style="border:1px solid #e5e7eb;border-radius:12px;padding:18px;background:#fff;box-shadow:0 4px 8px rgba(0,0,0,0.03);">
      <h3 style="color:#007ACC;margin-top:0;">Pricing & Margin Analytics</h3>
      <p style="color:#374151;line-height:1.6;font-size:15px;">
        Designed ETL pipelines for integrating product, sales, and cost data to calculate margins and KPIs.  
        Built time-series marts in Snowflake and automated reports via Airflow.
      </p>
      <p style="font-size:14px;color:#6b7280;"><strong>Impact:</strong> Report runtime improved from 11m → 90s; 40% faster KPI analysis.</p>

      <div style="margin-top:8px;display:flex;flex-wrap:wrap;gap:8px;">
      <a class="btn" href="https://github.com/PawanJadhav/Finance-Analytics" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">      💻 Code</a>
      <a class="btn" href="/projects/finance-fraud/" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">      📄 Case Study</a>
      </div>
    </article>

    <!-- Project 2 -->
    <article style="border:1px solid #e5e7eb;border-radius:12px;padding:18px;background:#fff;box-shadow:0 4px 8px rgba(0,0,0,0.03);">
      <h3 style="color:#007ACC;margin-top:0;">Financial Forecasting Pipelines</h3>
      <p style="color:#374151;line-height:1.6;font-size:15px;">
        Developed automated data ingestion and forecasting models using Snowflake Tasks and Python ARIMA for sales trend prediction.  
        Integrated outputs into Power BI dashboards for business planning.
      </p>
      <p style="font-size:14px;color:#6b7280;"><strong>Impact:</strong> Improved forecast accuracy by 22%, supporting strategic pricing decisions.</p>
      <div style="margin-top:8px;display:flex;flex-wrap:wrap;gap:8px;">
    <a class="btn" href="#" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">  💻 Code</a>
    <a class="btn" href="#" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">  📊 Dashboard</a>
    </div>
    </article>

    <!-- Project 3 -->
    <article style="border:1px solid #e5e7eb;border-radius:12px;padding:18px;background:#fff;box-shadow:0 4px 8px rgba(0,0,0,0.03);">
      <h3 style="color:#007ACC;margin-top:0;">Transaction Fraud Analytics</h3>
      <p style="color:#374151;line-height:1.6;font-size:15px;">
        Built near-real-time fraud detection workflows leveraging event streams and anomaly detection in Snowflake with ML-based thresholds.  
        Integrated dashboards to flag anomalies with root-cause drilldowns.
      </p>
      <p style="font-size:14px;color:#6b7280;"><strong>Impact:</strong> Reduced investigation time by 35%, improved detection recall by 15%.</p>

      
      <div style="margin-top:8px;display:flex;flex-wrap:wrap;gap:8px;">
     <a class="btn" href="#" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">💻 Code</a>
    <a class="btn" href="#" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">  📊 Dashboard</a>
    </div>


      
    </article>

  </div>

<p style="text-align:right;margin-top:16px;display:flex;justify-content:flex-end;">
  <a class="btn" href="/finance.html" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">📄 View More Finance Projects</a>
</p>

</section>

<section id="projectmanagement" style="display:None;background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);" aria-label="Project Management"></section>

<section style="background:#ffffff;border:1px solid #e5e7eb;border-radius:16px;padding:24px;margin:32px 0;box-shadow:0 4px 10px rgba(0,0,0,0.05);">

  <h2 style="color:#007ACC;margin-top:0;">Contact</h2>
  
  <p style="font-size:16px;line-height:1.7;color:#374151;margin-bottom:1em;">
    My approach blends <strong>engineering precision</strong> with <strong>strategic execution</strong>—bridging data pipelines, 
    analytics, and project delivery to drive measurable outcomes across <strong>healthcare</strong> and <strong>finance</strong> domains.
  </p>

  <p style="font-size:16px;line-height:1.7;color:#374151;">
    Based in Boston MA.(02135) and on <strong>STEM-OPT through March 2027</strong>, I’m open to opportunities in 
    <strong>Data Engineering, Analytics, and Project Management</strong> where data can create meaningful impact.
  </p>
   <p style="font-size:16px;line-height:1.7;color:#374151;margin-bottom:1em;">
    Thank you for visiting my portfolio – I appreciate your time and interest in my work.
    Let's stay in touch. 
    I would like to hear your thoughts and answer any questions you might have about my work and experience.
  </p>
<p style="margin-top:20px;display:flex;flex-wrap:wrap;gap:8px;justify-content:center;">

  <a class="btn" href="/assets/Resume.pdf" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">📄 Resume</a>

  <a class="btn" href="mailto:pawan.jadhav7@gmail.com"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">📧 Email</a>

  <a class="btn" href="https://www.linkedin.com/in/pawan-jadhav/" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">🔗 LinkedIn</a>

  <a class="btn" href="https://github.com/PawanJadhav7" target="_blank" rel="noopener noreferrer"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">💻 GitHub</a>

  <a class="btn" href="tel:+19142675356"
     style="display:inline-flex;align-items:center;justify-content:center;padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">📞 +1 914-267-5356</a>

</p>

</section>

<section style="text-align:center;margin:40px 0 20px;padding-top:10px;border-top:1px solid #e5e7eb;color:#6b7280;font-size:14px;">
  👁️‍🗨️ <strong>Visitors:</strong>
  <!-- Visitor badge (increments on view) -->
<img src="https://visitor-badge.laobi.icu/badge?page_id=PawanJadhav.portfolio"
     alt="Visitors"
     style="vertical-align:middle;margin-left:6px;">
  <br>
  © 2025 Pawan Jadhav — Data Engineering & Analytics Portfolio
</section>
