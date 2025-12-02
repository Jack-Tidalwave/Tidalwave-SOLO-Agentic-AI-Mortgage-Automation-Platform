<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Tidalwave SOLO™ on Google Cloud – Solution Overview</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="description" content="Tidalwave SOLO™ is an agentic AI mortgage automation platform built on Google Cloud, removing bottlenecks from the home loan process for lenders and borrowers." />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet" />
  <style>
    :root {
      --blue-dark: #0b1a33;
      --blue: #1664ff;
      --blue-soft: #e5f0ff;
      --white: #ffffff;
      --gray: #9ca3af;
      --border: #1f2933;
      --card-bg: #0f172a;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: "Inter", system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: radial-gradient(circle at top left, #102a6b 0, #020617 45%, #020617 100%);
      color: var(--white);
      line-height: 1.6;
    }

    a {
      color: var(--blue-soft);
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
    }

    .page {
      max-width: 1120px;
      margin: 0 auto;
      padding: 32px 20px 56px;
    }

    header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 32px;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 700;
      font-size: 20px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    .logo-mark {
      width: 28px;
      height: 28px;
      border-radius: 999px;
      background: radial-gradient(circle at 30% 30%, #60a5ff, #1d4ed8 55%, #020617 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 16px;
    }

    .tagline {
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: var(--gray);
    }

    .pill {
      font-size: 12px;
      padding: 6px 12px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.45);
      color: var(--blue-soft);
      background: rgba(15, 23, 42, 0.8);
    }

    .hero {
      display: grid;
      gap: 24px;
      grid-template-columns: minmax(0, 3fr) minmax(0, 2fr);
      align-items: center;
      margin-bottom: 40px;
    }

    .hero-title {
      font-size: clamp(28px, 3.2vw, 34px);
      font-weight: 700;
      margin-bottom: 14px;
    }

    .hero-badge-row {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-bottom: 12px;
    }

    .hero-subtitle {
      color: var(--gray);
      max-width: 520px;
      margin-bottom: 18px;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      align-items: center;
    }

    .btn-primary {
      padding: 10px 18px;
      border-radius: 999px;
      border: none;
      background: linear-gradient(135deg, #1d4ed8, #38bdf8);
      color: var(--white);
      font-weight: 500;
      font-size: 14px;
      cursor: pointer;
    }

    .btn-primary:hover {
      opacity: 0.92;
    }

    .btn-ghost {
      padding: 9px 16px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.6);
      background: transparent;
      color: var(--blue-soft);
      font-size: 13px;
      cursor: pointer;
    }

    .hero-meta {
      font-size: 12px;
      color: var(--gray);
    }

    .hero-card {
      border-radius: 18px;
      background: radial-gradient(circle at top left, #1d4ed8 0, #020617 55%);
      border: 1px solid rgba(148, 163, 184, 0.35);
      padding: 18px 18px 16px;
      box-shadow: 0 22px 40px rgba(15, 23, 42, 0.7);
    }

    .hero-card-title {
      font-size: 14px;
      font-weight: 600;
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .hero-metric-row {
      display: flex;
      justify-content: space-between;
      gap: 12px;
      margin-bottom: 10px;
      font-size: 12px;
    }

    .metric-label {
      color: var(--blue-soft);
      opacity: 0.86;
    }

    .metric-value {
      font-weight: 600;
    }

    .gcp-pill-row {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 4px;
      font-size: 11px;
    }

    .gcp-pill {
      padding: 3px 8px;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.75);
      border: 1px solid rgba(148, 163, 184, 0.4);
    }

    .section {
      margin-bottom: 32px;
      padding: 22px 20px 20px;
      border-radius: 18px;
      background: linear-gradient(135deg, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.86));
      border: 1px solid rgba(31, 41, 55, 0.9);
    }

    .section-header {
      display: flex;
      align-items: baseline;
      justify-content: space-between;
      gap: 16px;
      margin-bottom: 16px;
    }

    .section-title {
      font-size: 16px;
      font-weight: 600;
    }

    .section-kicker {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      color: var(--gray);
    }

    .section-body {
      font-size: 14px;
      color: #e5e7eb;
    }

    .grid-2 {
      display: grid;
      grid-template-columns: minmax(0, 1.6fr) minmax(0, 1.4fr);
      gap: 22px;
    }

    .list {
      list-style: none;
      margin-top: 6px;
      display: grid;
      gap: 6px;
    }

    .list li::before {
      content: "•";
      color: var(--blue);
      margin-right: 6px;
    }

    .pill-outline {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 4px 9px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.6);
      font-size: 11px;
      color: var(--gray);
      margin-top: 4px;
    }

    .pill-dot {
      width: 6px;
      height: 6px;
      border-radius: 999px;
      background: var(--blue);
    }

    .contact-grid {
      display: grid;
      gap: 14px;
      grid-template-columns: minmax(0, 2.1fr) minmax(0, 1.2fr);
      align-items: center;
    }

    .contact-links {
      font-size: 14px;
    }

    .contact-links span {
      display: inline-block;
      min-width: 80px;
      color: var(--gray);
    }

    .contact-links div + div {
      margin-top: 4px;
    }

    .badge-row {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      font-size: 11px;
      color: var(--gray);
    }

    .footnote {
      margin-top: 20px;
      font-size: 11px;
      color: #6b7280;
    }

    @media (max-width: 880px) {
      .hero {
        grid-template-columns: minmax(0, 1fr);
      }

      .grid-2 {
        grid-template-columns: minmax(0, 1fr);
      }

      .contact-grid {
        grid-template-columns: minmax(0, 1fr);
      }

      header {
        flex-direction: column;
        align-items: flex-start;
        gap: 8px;
      }
    }
  </style>
</head>
<body>
  <div class="page">
    <header>
      <div>
        <div class="logo">
          <div class="logo-mark">T</div>
          <div>
            <div>Tidalwave</div>
            <div class="tagline">Agentic AI for Mortgage Lending</div>
          </div>
        </div>
      </div>
      <div class="pill">Built on Google Cloud</div>
    </header>

    <main>
      <!-- HERO -->
      <section class="hero">
        <div>
          <div class="hero-badge-row">
            <span class="pill-outline">
              <span class="pill-dot"></span>
              Solution qualification – Google Cloud product family
            </span>
          </div>
          <h1 class="hero-title">
            Tidalwave SOLO™ – Agentic AI Mortgage Automation on Google Cloud
          </h1>
          <p class="hero-subtitle">
            Tidalwave is an agentic AI company dedicated to eliminating bottlenecks in the mortgage process.
            Our SOLO™ platform automates outdated workflows and connects directly to Fannie Mae DU®, Freddie Mac
            LPA℠, and verification partners including Plaid, Argyle, and Truv, all orchestrated on Google Cloud.
          </p>
          <div class="hero-actions">
            <a href="mailto:jack@tidalwave.work">
              <button class="btn-primary">Contact sales &amp; partnerships</button>
            </a>
            <a href="https://tidalwave.work/" target="_blank" rel="noopener">
              <button class="btn-ghost">Visit tidalwave.work</button>
            </a>
          </div>
          <p class="hero-meta">
            Designed for lenders who want faster, more accurate underwriting and a simpler, more accessible borrower experience.
          </p>
        </div>

        <aside class="hero-card" aria-label="Google Cloud architecture summary">
          <div class="hero-card-title">
            <span>Google Cloud architecture at a glance</span>
            <span style="font-size:11px; color:#e5e7eb;">Tidalwave SOLO™</span>
          </div>
          <div class="hero-metric-row">
            <div>
              <div class="metric-label">Core AI services</div>
              <div class="metric-value">Vertex AI, Document AI</div>
            </div>
            <div>
              <div class="metric-label">Data &amp; processing</div>
              <div class="metric-value">BigQuery, Cloud Run, Cloud Functions</div>
            </div>
          </div>
          <div class="hero-metric-row">
            <div>
              <div class="metric-label">Integration fabric</div>
              <div class="metric-value">REST APIs to DU® &amp; LPA℠, Plaid, Argyle, Truv</div>
            </div>
          </div>
          <div class="gcp-pill-row">
            <span class="gcp-pill">Identity &amp; security via Cloud IAM</span>
            <span class="gcp-pill">Monitoring with Cloud Logging &amp; Cloud Monitoring</span>
            <span class="gcp-pill">Encrypted storage on Cloud Storage</span>
          </div>
        </aside>
      </section>

      <!-- OVERVIEW & HOW IT WORKS -->
      <section class="section">
        <div class="section-header">
          <div>
            <div class="section-kicker">Solution overview</div>
            <h2 class="section-title">End-to-end mortgage automation powered by agentic AI</h2>
          </div>
        </div>
        <div class="section-body grid-2">
          <div>
            <p>
              Tidalwave’s mission is to accelerate homeownership by eliminating friction in the mortgage journey.
              Our agentic AI platform SOLO™ acts as a co-pilot for loan officers, processors, and underwriters,
              while guiding borrowers in plain language—including tailored support for Spanish-speaking clients.
              By connecting directly to Fannie Mae DU®, Freddie Mac LPA℠, and trusted verification providers,
              SOLO™ retrieves income, employment, and asset data in real time and transforms it into actionable,
              explainable insights.
            </p>
            <ul class="list">
              <li>Automates document collection, classification, and data extraction using Google Cloud’s Vertex AI and Document AI.</li>
              <li>Reduces manual data entry and repetitive checks across LOS and servicing systems.</li>
              <li>Shortens cycle times from application to clear-to-close while improving loan quality.</li>
            </ul>
          </div>
          <div>
            <p>
              SOLO™ breaks down the mortgage workflow into agent-driven tasks: gathering documents, validating
              data, explaining DU®/LPA℠ findings, and recommending next steps. These agents run on Google Cloud,
              where scalable serverless services orchestrate each interaction securely and reliably.
            </p>
            <ul class="list">
              <li>Borrower-facing assistant simplifies applications and improves completion rates.</li>
              <li>Internal co-pilot surfaces risks, conditions, and compensating factors for underwriting teams.</li>
              <li>Built-in multilingual support helps lenders better serve diverse, underserved communities.</li>
            </ul>
          </div>
        </div>
      </section>

      <!-- GOOGLE CLOUD ARCHITECTURE -->
      <section class="section">
        <div class="section-header">
          <div>
            <div class="section-kicker">Google Cloud integration</div>
            <h2 class="section-title">Modern, secure architecture on Google Cloud</h2>
          </div>
        </div>
        <div class="section-body grid-2">
          <div>
            <p><strong>AI &amp; automation</strong></p>
            <ul class="list">
              <li><strong>Vertex AI</strong> hosts and orchestrates our agentic AI models that power borrower guidance and the underwriting co-pilot.</li>
              <li><strong>Document AI</strong> ingests paystubs, bank statements, W-2s, tax returns, and closing packages with high-accuracy parsing and classification.</li>
              <li><strong>Cloud Functions</strong> triggers downstream workflows as new documents, verification events, or DU®/LPA℠ findings arrive.</li>
            </ul>
            <p style="margin-top:10px;"><strong>Data &amp; analytics</strong></p>
            <ul class="list">
              <li><strong>BigQuery</strong> serves as the analytical backbone for pipeline performance, pricing strategies, and portfolio risk insights.</li>
              <li><strong>Cloud Storage</strong> stores encrypted documents and intermediate artifacts with lifecycle policies and fine-grained IAM.</li>
            </ul>
          </div>
          <div>
            <p><strong>Application fabric &amp; operations</strong></p>
            <ul class="list">
              <li><strong>Cloud Run</strong> hosts stateless APIs for lenders, DU®/LPA℠ integrations, and third-party verification partners.</li>
              <li><strong>Cloud IAM</strong> enforces least-privilege access for lender teams, service accounts, and partner connections.</li>
              <li><strong>Cloud Logging &amp; Cloud Monitoring</strong> provide observability across the full workflow, from borrower events to underwriting decisions.</li>
            </ul>
            <p style="margin-top:10px;">
              This architecture allows Tidalwave to scale from boutique lenders to large national institutions while maintaining
              predictable performance, resilience, and a strong security posture aligned with financial-services requirements.
            </p>
          </div>
        </div>
      </section>

      <!-- BUSINESS IMPACT -->
      <section class="section">
        <div class="section-header">
          <div>
            <div class="section-kicker">Business outcomes</div>
            <h2 class="section-title">Designed for lenders, optimized for borrowers</h2>
          </div>
        </div>
        <div class="section-body grid-2">
          <div>
            <p><strong>For lenders</strong></p>
            <ul class="list">
              <li>Faster underwriting decisions through real-time verification and automated condition checks.</li>
              <li>Higher pull-through rates by reducing time-to-approval and friction in communication with borrowers.</li>
              <li>Lower operational costs by minimizing manual review, re-keying, and exception handling work.</li>
            </ul>
          </div>
          <div>
            <p><strong>For borrowers</strong></p>
            <ul class="list">
              <li>Guided digital application with clear explanations instead of jargon, across web and mobile channels.</li>
              <li>Support for Spanish-speaking and other multilingual experiences, reducing confusion and drop-off.</li>
              <li>Increased transparency into what is needed, why it is needed, and where they are in the process.</li>
            </ul>
          </div>
        </div>
      </section>

      <!-- COMPLIANCE & SECURITY -->
      <section class="section">
        <div class="section-header">
          <div>
            <div class="section-kicker">Security &amp; trust</div>
            <h2 class="section-title">Compliance-aware design for financial services</h2>
          </div>
        </div>
        <div class="section-body grid-2">
          <div>
            <p>
              Mortgage data is highly sensitive. Tidalwave implements security controls on top of Google Cloud’s
              shared-responsibility model to help lenders meet their regulatory and compliance obligations.
            </p>
            <ul class="list">
              <li>All data in transit is secured with TLS; data at rest is encrypted using Google-managed keys with the option for CMEK.</li>
              <li>Role-based access control via Cloud IAM, including separation of duties between operations and underwriting teams.</li>
              <li>Audit trails for critical actions captured through Cloud Logging and made available for lender compliance teams.</li>
            </ul>
          </div>
          <div>
            <p>
              Tidalwave also adopts privacy-by-design principles:
            </p>
            <ul class="list">
              <li>Minimization of retained personally identifiable information where possible.</li>
              <li>Configurable retention policies using Cloud Storage and BigQuery.</li>
              <li>Regional deployment options to align with data residency requirements.</li>
            </ul>
            <p style="margin-top:8px;">
              Together, these controls support lenders as they align with US and global regulations governing consumer financial data.
            </p>
          </div>
        </div>
      </section>

      <!-- CONTACT -->
      <section class="section">
        <div class="section-header">
          <div>
            <div class="section-kicker">Get in touch</div>
            <h2 class="section-title">Work with Tidalwave</h2>
          </div>
        </div>
        <div class="section-body contact-grid">
          <div class="contact-links">
            <div><span>Website</span><a href="https://tidalwave.work/" target="_blank" rel="noopener">https://tidalwave.work/</a></div>
            <div><span>Email</span><a href="mailto:jack@tidalwave.work">jack@tidalwave.work</a></div>
            <div><span>Use case</span>Agentic AI mortgage automation for lenders and borrowers</div>
          </div>
          <div>
            <div class="badge-row">
              <span class="pill">Built on Google Cloud</span>
              <span class="pill">Vertex AI &amp; Document AI</span>
              <span class="pill">BigQuery analytics</span>
            </div>
          </div>
        </div>
        <p class="footnote">
          Tidalwave was co-founded by industry veterans including Diane Yu, former CTO of digital mortgage startup Better.com and co-founder of FreeWheel (acquired by Comcast).
          SOLO™ combines this deep domain expertise with Google Cloud’s AI platform to bring a new standard of intelligence and automation to mortgage lending.
        </p>
      </section>
    </main>
  </div>
</body>
</html>
