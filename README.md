<!doctype html>
<!--
  Repo title (H1): A Process Model of AI Governance Vision Development in Public Universities using Machine Learning
  Purpose: clean, readable README-style HTML page
-->
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>A Process Model of AI Governance Vision (ML) — Public Universities</title>
  <meta name="description" content="A simple ML pipeline to predict AI governance vision indicators (VUTAI1–3) and compute an interpretable overall score." />

  <style>
    :root{
      --bg:#ffffff;
      --text:#111827;
      --muted:#6b7280;
      --border:#e5e7eb;
      --card:#f9fafb;
      --blue:#2563eb;
      --amber:#d97706;
      --green:#059669;
      --codebg:#0b1020;
      --codefg:#e5e7eb;
    }

    *{ box-sizing:border-box; }
    body{
      margin:0;
      background:var(--bg);
      color:var(--text);
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Arial, "Helvetica Neue", Helvetica, sans-serif;
      line-height:1.55;
    }

    .container{
      max-width: 1020px;
      margin: 0 auto;
      padding: 28px 18px 56px;
    }

    header{
      padding: 18px 18px 14px;
      border: 1px solid var(--border);
      border-radius: 14px;
      background: linear-gradient(180deg, #ffffff 0%, #fbfbff 100%);
    }

    h1{
      margin: 0 0 8px;
      font-size: 22px;
      letter-spacing: -0.2px;
    }

    .subtitle{
      margin: 0 0 12px;
      color: var(--muted);
      font-size: 14px;
    }

    .badges{
      display:flex;
      flex-wrap:wrap;
      gap:8px;
      margin-top: 10px;
    }

    .badge{
      display:inline-flex;
      align-items:center;
      gap:6px;
      padding: 4px 10px;
      font-size: 12px;
      border: 1px solid var(--border);
      border-radius: 999px;
      background: #fff;
      color: #111827;
      white-space: nowrap;
    }

    main{ margin-top: 18px; }

    section{
      margin-top: 18px;
      padding: 16px 18px;
      border: 1px solid var(--border);
      border-radius: 14px;
      background: #fff;
    }

    h2{
      margin: 0 0 10px;
      font-size: 16px;
      letter-spacing: -0.1px;
    }

    p{ margin: 10px 0; }

    ul{ margin: 8px 0 0 20px; }
    li{ margin: 6px 0; }

    .grid{
      display:grid;
      grid-template-columns: 1fr;
      gap: 12px;
    }

    @media (min-width: 860px){
      .grid{ grid-template-columns: 1fr 1fr; }
    }

    .callout{
      border-left: 4px solid var(--blue);
      background: #f3f7ff;
      padding: 12px 12px;
      border-radius: 12px;
    }
    .callout h3{
      margin: 0 0 6px;
      font-size: 14px;
    }

    .warn{
      border-left: 4px solid var(--amber);
      background: #fff7ed;
      padding: 12px 12px;
      border-radius: 12px;
    }

    .ok{
      border-left: 4px solid var(--green);
      background: #ecfdf5;
      padding: 12px 12px;
      border-radius: 12px;
    }

    pre, code{
      font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace;
    }

    pre{
      margin: 12px 0 0;
      padding: 14px 14px;
      border-radius: 12px;
      overflow-x: auto;
      border: 1px solid #11182722;
      background: var(--codebg);
      color: var(--codefg);
    }

    code.inline{
      padding: 2px 6px;
      border-radius: 8px;
      background: #f3f4f6;
      border: 1px solid var(--border);
      color: #111827;
    }

    .two-col{
      display:grid;
      grid-template-columns: 1fr;
      gap: 12px;
    }
    @media (min-width: 860px){
      .two-col{ grid-template-columns: 1.2fr 0.8fr; }
    }

    footer{
      margin-top: 18px;
      color: var(--muted);
      font-size: 13px;
      padding: 14px 4px 0;
    }

    hr{
      border:none;
      border-top: 1px solid var(--border);
      margin: 16px 0 0;
    }
  </style>
</head>

<body>
  <div class="container">
    <header>
      <h1>A Process Model of AI Governance Vision Development in Public Universities using Machine Learning</h1>
      <p class="subtitle">
        A small, reproducible ML decision-support pipeline to predict AI governance vision indicators
        and compute an interpretable overall score for public universities.
      </p>

      <div class="badges" aria-label="technology badges">
        <span class="badge">Python</span>
        <span class="badge">scikit-learn</span>
        <span class="badge">joblib</span>
        <span class="badge">pandas</span>
        <span class="badge">PLS-SEM / PLSpredict (context)</span>
      </div>
    </header>

    <main>
      <section class="two-col">
        <div>
          <h2>What this repository does</h2>
          <p>
            This repository contains a simple workflow to load survey data, run pre-trained models,
            and generate predictions for three vision indicators: <code class="inline">VUTAI1</code>,
            <code class="inline">VUTAI2</code>, and <code class="inline">VUTAI3</code>.
          </p>
          <p>
            The three predicted items are then aggregated into:
          </p>
          <ul>
            <li><code class="inline">AI_Governance_Vision</code> (mean on a 1–4 Likert scale)</li>
            <li><code class="inline">AI_Governance_Vision_Pct</code> (normalised to 0–100%)</li>
            <li><code class="inline">Vision_Level</code> (Low / Moderate / High)</li>
          </ul>
        </div>

        <div class="callout">
          <h3>Prediction target</h3>
          <p style="margin:0;">
            The tool predicts <strong>vision outcomes</strong> (VUTAI1–3) from a set of governance-related
            input features (EST, OUAI, PBUG items). It is designed for decision support and benchmarking
            across units, not for identifying individuals.
          </p>
        </div>
      </section>

      <section>
        <h2>Project structure</h2>
        <pre><code>integrationAIPLS/
├─ ML-Predict.ipynb          # Main prediction workflow
├─ ML-Train.ipynb            # Optional: model training workflow
├─ Models/                   # Saved .joblib models (one per target)
│  ├─ ML_BestModel_VUTAI_VUTAI1_*.joblib
│  ├─ ML_BestModel_VUTAI_VUTAI2_*.joblib
│  └─ ML_BestModel_VUTAI_VUTAI3_*.joblib
├─ Results/                  # Exported figures and tables (SVG / PDF / CSV)
└─ last_data.xlsx            # Example dataset (avoid sensitive data)</code></pre>
      </section>

      <section class="grid">
        <div>
          <h2>Requirements</h2>
          <p>Create a clean environment (recommended) and install dependencies.</p>

          <h3 style="margin:12px 0 6px;font-size:14px;">Option A: pip</h3>
          <pre><code>pip install pandas numpy scikit-learn joblib matplotlib openpyxl</code></pre>

          <h3 style="margin:12px 0 6px;font-size:14px;">Option B: conda</h3>
          <pre><code>conda create -n ai-vision python=3.11 -y
conda activate ai-vision
conda install -c conda-forge pandas numpy scikit-learn joblib matplotlib openpyxl -y</code></pre>
        </div>

        <div class="warn">
          <h3 style="margin:0 0 6px;font-size:14px;">scikit-learn version note</h3>
          <p style="margin:0;">
            If a model was trained with a different scikit-learn version, you may see a warning during
            <code class="inline">joblib.load()</code>. For strict reproducibility, pin versions in a
            <code class="inline">requirements.txt</code> (or a conda env file).
          </p>
        </div>
      </section>

      <section>
        <h2>How to use (prediction)</h2>
        <ol style="margin:8px 0 0 20px;">
          <li style="margin:8px 0;">
            Put trained models into <code class="inline">Models/</code> using the pattern:
            <pre><code>ML_BestModel_VUTAI_{target}_*.joblib</code></pre>
          </li>

          <li style="margin:8px 0;">
            Prepare your input file (Excel/CSV). It must contain the features used in training.
            Default expected order:
            <pre><code>FEATURE_ORDER = [
  "EST1", "EST3", "EST4",
  "OUAI2", "OUAI3", "OUAI4",
  "PBUG1", "PBUG2", "PBUG3", "PBUG4"
]</code></pre>
          </li>

          <li style="margin:8px 0;">
            Open <code class="inline">ML-Predict.ipynb</code> and run cells in order:
            <strong>data → models → prediction → outputs</strong>.
          </li>
        </ol>

        <div class="ok" style="margin-top:12px;">
          <h3 style="margin:0 0 6px;font-size:14px;">Outputs you will get</h3>
          <ul style="margin:0 0 0 18px;">
            <li>Predicted items: <code class="inline">VUTAI1</code>, <code class="inline">VUTAI2</code>, <code class="inline">VUTAI3</code></li>
            <li>Overall score: <code class="inline">AI_Governance_Vision</code> (1–4)</li>
            <li>Percentage: <code class="inline">AI_Governance_Vision_Pct</code> (0–100)</li>
            <li>Interpretation: <code class="inline">Vision_Level</code> (Low / Moderate / High)</li>
          </ul>
        </div>
      </section>

      <section>
        <h2>Reproducibility</h2>
        <ul>
          <li>Keep feature names and their order consistent between training and prediction.</li>
          <li>Store the exact package versions used for training and inference.</li>
          <li>Log the model filename + training date inside <code class="inline">Results/</code> for traceability.</li>
        </ul>
      </section>

      <section>
        <h2>Data privacy</h2>
        <p>
          Do not upload sensitive institutional data. Use anonymised samples and exclude raw data using
          <code class="inline">.gitignore</code>.
        </p>
      </section>

      <footer>
        <hr />
        <p style="margin:12px 0 0;">
          <em>Maintainer:</em> Amal
        </p>
      </footer>
    </main>
  </div>
</body>
</html>
