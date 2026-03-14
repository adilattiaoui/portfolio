<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Adil Attiaoui — Research Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Source+Serif+4:ital,opsz,wght@0,8..60,300;0,8..60,400;0,8..60,600;1,8..60,300;1,8..60,400&family=Source+Sans+3:wght@300;400;500;600&family=Source+Code+Pro:wght@400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --blue: #1a56db;
      --blue-dark: #0f3d9e;
      --blue-light: #e8f0fd;
      --black: #0d0d0d;
      --ink: #1a1a1a;
      --ink2: #3d3d3d;
      --muted: #6b7280;
      --rule: #d1d5db;
      --bg: #ffffff;
      --bg2: #f8f9fb;
      --serif: 'Source Serif 4', Georgia, serif;
      --sans: 'Source Sans 3', sans-serif;
      --mono: 'Source Code Pro', monospace;
    }
    html { scroll-behavior: smooth; }
    body { background: var(--bg); color: var(--ink); font-family: var(--sans); font-weight: 300; line-height: 1.7; font-size: 16px; }

    /* ── JOURNAL STRIP ── */
    .journal-strip {
      background: var(--blue); color: white;
      font-family: var(--mono); font-size: 0.68rem; letter-spacing: 0.14em; text-transform: uppercase;
      display: flex; justify-content: space-between; align-items: center; padding: 0.45rem 3rem;
    }

    /* ── NAV ── */
    nav { position: sticky; top: 0; z-index: 500; background: var(--bg); border-bottom: 3px solid var(--blue); display: flex; align-items: stretch; }
    .nav-brand { display: flex; align-items: center; padding: 0.8rem 2rem; border-right: 1px solid var(--rule); text-decoration: none; gap: 0; flex-direction: column; justify-content: center; }
    .nav-brand-title { font-family: var(--serif); font-size: 1.05rem; font-weight: 600; color: var(--ink); }
    .nav-brand-sub { font-size: 0.68rem; color: var(--muted); font-family: var(--mono); letter-spacing: 0.06em; }
    .nav-links { display: flex; list-style: none; margin-left: auto; }
    .nav-links li a { display: flex; align-items: center; height: 100%; padding: 0 1.3rem; font-size: 0.75rem; font-weight: 500; letter-spacing: 0.04em; color: var(--muted); text-decoration: none; text-transform: uppercase; border-left: 1px solid var(--rule); transition: color 0.15s, background 0.15s; }
    .nav-links li a:hover { color: var(--blue); background: var(--blue-light); }
    .nav-cta a { background: var(--blue) !important; color: white !important; }
    .nav-cta a:hover { background: var(--blue-dark) !important; }

    /* ── HERO ── */
    #hero { border-bottom: 1px solid var(--rule); }
    .hero-inner { max-width: 1120px; margin: 0 auto; display: grid; grid-template-columns: 1fr 320px; }
    .hero-main { padding: 4rem 3rem; border-right: 1px solid var(--rule); }
    .hero-kicker { font-family: var(--mono); font-size: 0.72rem; color: var(--blue); letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 1.2rem; display: flex; align-items: center; gap: 0.8rem; }
    .hero-kicker::before { content: ''; display: inline-block; width: 1.5rem; height: 2px; background: var(--blue); }
    .hero-name { font-family: var(--serif); font-size: clamp(2.8rem, 5vw, 4.5rem); font-weight: 600; line-height: 1.05; letter-spacing: -0.03em; color: var(--black); margin-bottom: 0.5rem; }
    .hero-name em { font-style: italic; font-weight: 300; color: var(--blue); }
    .hero-divider { width: 60px; height: 3px; background: var(--blue); margin: 1.5rem 0; }
    .hero-abstract { font-family: var(--serif); font-size: 1rem; color: var(--ink2); line-height: 1.85; max-width: 600px; margin-bottom: 2rem; }
    .hero-keywords { display: flex; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 2.5rem; }
    .kw { font-family: var(--mono); font-size: 0.68rem; letter-spacing: 0.08em; padding: 0.3rem 0.8rem; border: 1px solid var(--blue); color: var(--blue); background: var(--blue-light); }
    .hero-actions { display: flex; gap: 1rem; }
    .btn-solid { font-family: var(--sans); font-size: 0.8rem; font-weight: 600; letter-spacing: 0.06em; text-transform: uppercase; padding: 0.75rem 1.8rem; background: var(--blue); color: white; text-decoration: none; border: 2px solid var(--blue); transition: all 0.15s; }
    .btn-solid:hover { background: var(--blue-dark); border-color: var(--blue-dark); }
    .btn-ghost { font-family: var(--sans); font-size: 0.8rem; font-weight: 600; letter-spacing: 0.06em; text-transform: uppercase; padding: 0.75rem 1.8rem; background: transparent; color: var(--blue); text-decoration: none; border: 2px solid var(--blue); transition: all 0.15s; }
    .btn-ghost:hover { background: var(--blue-light); }

    /* SIDEBAR */
    .hero-sidebar { padding: 2.5rem 2rem; background: var(--bg2); }
    .sidebar-section { margin-bottom: 1.8rem; padding-bottom: 1.8rem; border-bottom: 1px solid var(--rule); }
    .sidebar-section:last-child { border-bottom: none; margin-bottom: 0; }
    .sidebar-label { font-family: var(--mono); font-size: 0.65rem; color: var(--blue); letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 0.8rem; }
    .sidebar-val { font-size: 0.88rem; color: var(--ink2); line-height: 1.6; }
    .sidebar-val a { color: var(--blue); text-decoration: none; }
    .stat-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 0.6rem; }
    .stat-box { background: white; border: 1px solid var(--rule); border-top: 3px solid var(--blue); padding: 0.8rem 0.6rem; text-align: center; }
    .stat-num { font-family: var(--serif); font-size: 1.8rem; font-weight: 600; color: var(--blue); line-height: 1; }
    .stat-lbl { font-size: 0.65rem; color: var(--muted); font-family: var(--mono); letter-spacing: 0.06em; margin-top: 4px; }
    .lang-item { margin-bottom: 1rem; }
    .lang-top { display: flex; justify-content: space-between; font-size: 0.82rem; margin-bottom: 0.3rem; }
    .lang-lv { font-family: var(--mono); font-size: 0.7rem; color: var(--muted); }
    .lang-track { height: 2px; background: var(--rule); }
    .lang-fill { height: 100%; background: var(--blue); width: 0; transition: width 1s cubic-bezier(0.4,0,0.2,1); }
    .lang-fill.go { width: var(--w); }

    /* ── SECTIONS ── */
    .page-section { max-width: 1120px; margin: 0 auto; padding: 4rem 3rem; border-bottom: 1px solid var(--rule); }
    .section-eyebrow { display: flex; align-items: center; gap: 1.2rem; margin-bottom: 2.5rem; }
    .eyebrow-num { font-family: var(--mono); font-size: 0.7rem; color: var(--blue); letter-spacing: 0.1em; }
    .eyebrow-title { font-family: var(--sans); font-size: 0.72rem; font-weight: 600; letter-spacing: 0.18em; text-transform: uppercase; color: var(--muted); }
    .eyebrow-rule { flex: 1; height: 1px; background: var(--rule); }
    .section-heading { font-family: var(--serif); font-size: clamp(1.8rem, 3vw, 2.5rem); font-weight: 400; letter-spacing: -0.02em; color: var(--black); margin-bottom: 2.5rem; line-height: 1.2; }

    /* ── EDUCATION ── */
    .edu-table { width: 100%; border-collapse: collapse; }
    .edu-table tr { border-bottom: 1px solid var(--rule); opacity: 0; transform: translateY(12px); transition: opacity 0.4s, transform 0.4s; }
    .edu-table tr.visible { opacity: 1; transform: none; }
    .edu-table td { padding: 1.4rem 0; vertical-align: top; }
    .edu-date { font-family: var(--mono); font-size: 0.72rem; color: var(--blue); letter-spacing: 0.06em; white-space: nowrap; padding-right: 3rem; width: 180px; }
    .edu-degree { font-family: var(--serif); font-size: 1.05rem; font-weight: 600; color: var(--black); margin-bottom: 0.25rem; }
    .edu-institution { font-size: 0.85rem; color: var(--muted); }
    .edu-badge { display: inline-block; font-family: var(--mono); font-size: 0.62rem; letter-spacing: 0.08em; padding: 0.25rem 0.7rem; background: var(--blue); color: white; white-space: nowrap; vertical-align: top; margin-top: 0.3rem; }

    /* ── PUBLICATIONS ── */
    .pub-article { border-top: 1px solid var(--rule); padding: 1.8rem 0; display: grid; grid-template-columns: 90px 1fr; gap: 2rem; align-items: start; opacity: 0; transform: translateY(12px); transition: opacity 0.4s, transform 0.4s; }
    .pub-article.visible { opacity: 1; transform: none; }
    .pub-article:last-child { border-bottom: 1px solid var(--rule); }
    .pub-year-col { font-family: var(--mono); font-size: 0.72rem; color: var(--blue); letter-spacing: 0.06em; padding-top: 0.2rem; }
    .pub-class-badge { display: inline-block; font-size: 0.62rem; font-family: var(--mono); padding: 0.15rem 0.5rem; border: 1px solid var(--blue); color: var(--blue); margin-top: 0.5rem; }
    .pub-title { font-family: var(--serif); font-size: 1rem; font-weight: 600; color: var(--black); line-height: 1.4; margin-bottom: 0.4rem; }
    .pub-authors { font-size: 0.85rem; color: var(--ink2); margin-bottom: 0.3rem; }
    .pub-authors strong { color: var(--blue); font-weight: 500; text-decoration: underline; text-decoration-style: dotted; }
    .pub-venue { font-size: 0.82rem; color: var(--muted); font-style: italic; }
    .pub-doi { font-family: var(--mono); font-size: 0.68rem; color: var(--blue); text-decoration: none; margin-top: 0.4rem; display: inline-block; }
    .pub-doi:hover { text-decoration: underline; }

    /* ── SKILLS ── */
    .skills-cols { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 0; border: 1px solid var(--rule); }
    .skill-col { padding: 1.8rem; border-right: 1px solid var(--rule); border-bottom: 1px solid var(--rule); }
    .skill-col-head { font-family: var(--mono); font-size: 0.68rem; letter-spacing: 0.16em; text-transform: uppercase; color: white; background: var(--blue); padding: 0.35rem 0.8rem; display: inline-block; margin-bottom: 1.1rem; }
    .skill-items { list-style: none; display: grid; gap: 0.5rem; }
    .skill-items li { font-size: 0.85rem; color: var(--ink2); padding-left: 1rem; position: relative; line-height: 1.4; }
    .skill-items li::before { content: '—'; position: absolute; left: 0; color: var(--blue); font-size: 0.75rem; }

    /* ── TEACHING ── */
    .teach-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1px; background: var(--rule); border: 1px solid var(--rule); }
    .teach-item { background: var(--bg); padding: 1.5rem; display: flex; gap: 1.2rem; opacity: 0; transition: opacity 0.4s; }
    .teach-item.visible { opacity: 1; }
    .teach-num { font-family: var(--serif); font-size: 2rem; font-weight: 300; color: var(--rule); line-height: 1; min-width: 2rem; }
    .teach-role { font-size: 0.88rem; font-weight: 500; color: var(--black); margin-bottom: 0.3rem; line-height: 1.4; }
    .teach-course { font-family: var(--mono); font-size: 0.7rem; color: var(--blue); letter-spacing: 0.06em; }

    /* ── EXPERIENCE ── */
    .exp-row { display: grid; grid-template-columns: 200px 1fr; gap: 2.5rem; padding: 1.8rem 0; border-bottom: 1px solid var(--rule); }
    .exp-row:first-child { border-top: 1px solid var(--rule); }
    .exp-period { font-family: var(--mono); font-size: 0.72rem; color: var(--blue); letter-spacing: 0.06em; line-height: 1.6; }
    .exp-place { font-size: 0.75rem; color: var(--muted); margin-top: 0.3rem; }
    .exp-role-title { font-family: var(--serif); font-size: 1rem; font-weight: 600; color: var(--black); margin-bottom: 0.25rem; }
    .exp-org-name { font-size: 0.85rem; color: var(--muted); }

    /* ── CONTACT ── */
    #contact { background: var(--blue); color: white; }
    .contact-inner { max-width: 1120px; margin: 0 auto; padding: 5rem 3rem; display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start; }
    .contact-title { font-family: var(--serif); font-size: clamp(2rem, 4vw, 3.2rem); font-weight: 300; font-style: italic; line-height: 1.2; margin-bottom: 1rem; }
    .contact-sub { font-size: 0.95rem; opacity: 0.8; line-height: 1.7; }
    .contact-details { display: grid; gap: 1.2rem; }
    .contact-row { display: flex; align-items: flex-start; gap: 1.2rem; padding-bottom: 1.2rem; border-bottom: 1px solid rgba(255,255,255,0.2); }
    .contact-row:last-child { border-bottom: none; }
    .c-label { font-family: var(--mono); font-size: 0.65rem; letter-spacing: 0.15em; text-transform: uppercase; opacity: 0.6; min-width: 70px; margin-top: 2px; }
    .c-val { font-size: 0.9rem; line-height: 1.5; }
    .c-val a { color: white; text-decoration: none; border-bottom: 1px solid rgba(255,255,255,0.4); }
    .c-val a:hover { border-color: white; }

    /* ── FOOTER ── */
    footer { background: #0d0d0d; color: rgba(255,255,255,0.4); font-family: var(--mono); font-size: 0.68rem; letter-spacing: 0.1em; display: flex; justify-content: space-between; align-items: center; padding: 1.2rem 3rem; }
    footer span:last-child { color: var(--blue); }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp { from { opacity: 0; transform: translateY(16px); } to { opacity: 1; transform: none; } }
    .hero-main > * { animation: fadeUp 0.6s both; }
    .hero-kicker { animation-delay: 0.05s; }
    .hero-name { animation-delay: 0.15s; }
    .hero-divider { animation-delay: 0.25s; }
    .hero-abstract { animation-delay: 0.3s; }
    .hero-keywords { animation-delay: 0.4s; }
    .hero-actions { animation-delay: 0.5s; }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      .journal-strip { display: none; }
      .nav-links li:not(.nav-cta) { display: none; }
      .hero-inner { grid-template-columns: 1fr; }
      .hero-sidebar { border-top: 3px solid var(--blue); }
      .hero-main { border-right: none; padding: 3rem 1.5rem; }
      .page-section { padding: 3rem 1.5rem; }
      .pub-article { grid-template-columns: 1fr; }
      .teach-grid { grid-template-columns: 1fr; }
      .exp-row { grid-template-columns: 1fr; gap: 0.3rem; }
      .contact-inner { grid-template-columns: 1fr; gap: 3rem; padding: 3rem 1.5rem; }
      footer { flex-direction: column; gap: 0.5rem; padding: 1.5rem; text-align: center; }
    }
    @media (max-width: 600px) {
      .hero-main { padding: 2.5rem 1rem; }
      .page-section { padding: 2.5rem 1rem; }
      .skills-cols { grid-template-columns: 1fr; }
      .nav-brand { padding: 0.8rem 1rem; }
      footer { padding: 1.5rem 1rem; }
      .edu-date { width: auto; padding-right: 1.5rem; }
    }
  </style>
</head>
<body>

<!-- JOURNAL STRIP -->
<div class="journal-strip">
  <span>Research Portfolio · ENSIAS · Mohammed V University · Rabat, Morocco</span>
  <span>ISSN: PhD-2023 · Vol. 2025 · Issue 3</span>
</div>

<!-- NAV -->
<nav>
  <a class="nav-brand" href="#hero">
    <div class="nav-brand-title">Adil Attiaoui</div>
    <div class="nav-brand-sub">PhD Researcher</div>
  </a>
  <ul class="nav-links">
    <li><a href="#education">Education</a></li>
    <li><a href="#publications">Publications</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#teaching">Teaching</a></li>
    <li><a href="#experience">Experience</a></li>
    <li class="nav-cta"><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<div id="hero">
  <div class="hero-inner">
    <div class="hero-main">
      <div class="hero-kicker">PhD Candidate · Cybersecurity &amp; Vehicular Networks</div>
      <h1 class="hero-name">Adil<br><em>Attiaoui</em></h1>
      <div class="hero-divider"></div>
      <p class="hero-abstract">
        PhD student at the National School of Computer Science and Systems Analysis (ENSIAS),
        Mohammed V University. My research investigates <strong>misbehavior detection and mitigation
        in vehicular collective perception systems</strong>, applying game-theoretic models, Bayesian
        inference, and reputation mechanisms to secure the cooperative sensing layer of autonomous vehicle networks.
      </p>
      <div class="hero-keywords">
        <span class="kw">V2X Security</span>
        <span class="kw">Federated Learning</span>
        <span class="kw">Blockchain</span>
        <span class="kw">Game Theory</span>
        <span class="kw">Misbehavior Detection</span>
        <span class="kw">IoT</span>
        <span class="kw">CCNA</span>
        <span class="kw">ISC² Certified</span>
      </div>
      <div class="hero-actions">
        <a href="#publications" class="btn-solid">View Publications</a>
        <a href="#contact" class="btn-ghost">Contact Me</a>
      </div>
    </div>

    <div class="hero-sidebar">
      <div class="sidebar-section">
        <div class="sidebar-label">At a glance</div>
        <div class="stat-grid">
          <div class="stat-box"><div class="stat-num">5</div><div class="stat-lbl">Publications</div></div>
          <div class="stat-box"><div class="stat-num">2</div><div class="stat-lbl">Class B/C</div></div>
          <div class="stat-box"><div class="stat-num">6</div><div class="stat-lbl">Certifications</div></div>
          <div class="stat-box"><div class="stat-num">5</div><div class="stat-lbl">Degrees</div></div>
        </div>
      </div>
      <div class="sidebar-section">
        <div class="sidebar-label">Contact</div>
        <div class="sidebar-val">
          <a href="mailto:adil7attiaoui@gmail.com">adil7attiaoui@gmail.com</a><br>
          +212 0000000000<br>
          Salé, Morocco 11160
        </div>
      </div>
      <div class="sidebar-section">
        <div class="sidebar-label">Languages</div>
        <div>
          <div class="lang-item">
            <div class="lang-top"><span>Arabic</span><span class="lang-lv">Native</span></div>
            <div class="lang-track"><div class="lang-fill" style="--w:100%"></div></div>
          </div>
          <div class="lang-item">
            <div class="lang-top"><span>French</span><span class="lang-lv">Intermediate</span></div>
            <div class="lang-track"><div class="lang-fill" style="--w:65%"></div></div>
          </div>
          <div class="lang-item">
            <div class="lang-top"><span>English</span><span class="lang-lv">Intermediate</span></div>
            <div class="lang-track"><div class="lang-fill" style="--w:65%"></div></div>
          </div>
        </div>
      </div>
      <div class="sidebar-section">
        <div class="sidebar-label">Affiliation</div>
        <div class="sidebar-val">ENSIAS · Mohammed V University<br>Rabat, Morocco</div>
      </div>
    </div>
  </div>
</div>

<!-- EDUCATION -->
<div class="page-section" id="education">
  <div class="section-eyebrow">
    <span class="eyebrow-num">§1</span>
    <span class="eyebrow-title">Education</span>
    <span class="eyebrow-rule"></span>
  </div>
  <h2 class="section-heading">Academic Background</h2>
  <table class="edu-table">
    <tr>
      <td class="edu-date">2023 — Present</td>
      <td><div class="edu-degree">PhD in Vehicular Collective Perception Misbehavior Detection &amp; Mitigation</div><div class="edu-institution">National School of Computer Science and Systems Analysis (ENSIAS) · Rabat, Morocco</div></td>
      <td><span class="edu-badge">Current</span></td>
    </tr>
    <tr>
      <td class="edu-date">2021 — 2023</td>
      <td><div class="edu-degree">Research Master's in Systems and Services Security</div><div class="edu-institution">ENSIAS · Rabat, Morocco</div></td>
      <td></td>
    </tr>
    <tr>
      <td class="edu-date">2020 — 2021</td>
      <td><div class="edu-degree">Bachelor's in Software Engineering &amp; Advanced Administration of Systems and Networks</div><div class="edu-institution">Higher School of Technology (EST Casablanca) · Morocco</div></td>
      <td></td>
    </tr>
    <tr>
      <td class="edu-date">2018 — 2020</td>
      <td><div class="edu-degree">Specialized Technician Diploma in Computer Networks</div><div class="edu-institution">Specialized Institute of Applied Technology · Essaouira, Morocco</div></td>
      <td></td>
    </tr>
    <tr>
      <td class="edu-date">2017 — 2018</td>
      <td><div class="edu-degree">Scientific Baccalaureate in Mathematics</div><div class="edu-institution">Mohammed V High School · Essaouira, Morocco</div></td>
      <td></td>
    </tr>
  </table>
</div>

<!-- PUBLICATIONS -->
<div class="page-section" id="publications" style="background: var(--bg2);">
  <div class="section-eyebrow">
    <span class="eyebrow-num">§2</span>
    <span class="eyebrow-title">Publications</span>
    <span class="eyebrow-rule"></span>
  </div>
  <h2 class="section-heading">Peer-Reviewed Conference Papers</h2>

  <div class="pub-article">
    <div class="pub-year-col">2025<div class="pub-class-badge">Class C</div></div>
    <div>
      <div class="pub-title">Misbehavior Detection in Connected Vehicle: Pre-Bayesian Majority Game Framework</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, M. Elmachkour, A. Kobbane, M. Ayaida</div>
      <div class="pub-venue">11th International Conference on Vehicle Technology and Intelligent Transport Systems (VEHITS), Porto, Portugal · pp. 529–536</div>
      <a class="pub-doi" href="https://doi.org/10.5220/0013359100003941" target="_blank">doi: 10.5220/0013359100003941 →</a>
    </div>
  </div>

  <div class="pub-article">
    <div class="pub-year-col">2024</div>
    <div>
      <div class="pub-title">Strategic Trust: Reputation-Based Mechanisms for Mitigating Malicious Behavior in Vehicular Collective Perception</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, M. Elmachkour, M. Ayaida, A. Kobbane</div>
      <div class="pub-venue">16th International Conference on Communication Software and Networks (ICCSN), Ningbo, China · pp. 137–141</div>
      <a class="pub-doi" href="https://doi.org/10.1109/ICCSN63464.2024.10793308" target="_blank">doi: 10.1109/ICCSN63464.2024.10793308 →</a>
    </div>
  </div>

  <div class="pub-article">
    <div class="pub-year-col">2024</div>
    <div>
      <div class="pub-title">Securing University Diploma Management through Blockchain and InterPlanetary File System</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, A. Kobbane, M. Ayaida</div>
      <div class="pub-venue">International Conference on Ubiquitous Networking (UNet), Marrakech, Morocco · pp. 1–6</div>
      <a class="pub-doi" href="https://doi.org/10.1109/UNet62310.2024.10794707" target="_blank">doi: 10.1109/UNet62310.2024.10794707 →</a>
    </div>
  </div>

  <div class="pub-article">
    <div class="pub-year-col">2024</div>
    <div>
      <div class="pub-title">Blockchain-Enabled Defense Mechanism for Protecting Federated Learning Systems Against Malicious Node Updates</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, A. Kobbane, J. Elhachmi, M. Ayaida, K. Chougdali</div>
      <div class="pub-venue">4th Interdisciplinary Conference on Electrics and Computer (INTCEC), Chicago, IL, USA · pp. 1–6</div>
      <a class="pub-doi" href="https://doi.org/10.1109/INTCEC61833.2024.10602881" target="_blank">doi: 10.1109/INTCEC61833.2024.10602881 →</a>
    </div>
  </div>

  <div class="pub-article">
    <div class="pub-year-col">2024<div class="pub-class-badge">Class B</div></div>
    <div>
      <div class="pub-title">Efficient Collaborations through Weight-Driven Coalition Dynamics in Federated Learning Systems</div>
      <div class="pub-authors">M. E. Hanjri, H. Reguieg, <strong>A. Attiaoui</strong>, A. Abouaomar, A. Kobbane, M. E. Kamili</div>
      <div class="pub-venue">ICC 2024 — IEEE International Conference on Communications, Denver, CO, USA · pp. 3482–3487</div>
      <a class="pub-doi" href="https://doi.org/10.1109/ICC51166.2024.10623064" target="_blank">doi: 10.1109/ICC51166.2024.10623064 →</a>
    </div>
  </div>
</div>

<!-- SKILLS -->
<div class="page-section" id="skills">
  <div class="section-eyebrow">
    <span class="eyebrow-num">§3</span>
    <span class="eyebrow-title">Skills &amp; Certifications</span>
    <span class="eyebrow-rule"></span>
  </div>
  <h2 class="section-heading">Technical Expertise</h2>
  <div class="skills-cols">
    <div class="skill-col">
      <div class="skill-col-head">Networking</div>
      <ul class="skill-items">
        <li>CCNA: Enterprise Networking, Security &amp; Automation</li>
        <li>CCNA: Switching, Routing &amp; Wireless Essentials</li>
        <li>Huawei Datacom Certification</li>
        <li>Network Supervision (Nagios, ZABBIX)</li>
      </ul>
    </div>
    <div class="skill-col">
      <div class="skill-col-head">Cybersecurity</div>
      <ul class="skill-items">
        <li>Certified in Cybersecurity — (ISC)²</li>
        <li>Huawei Cybersecurity Certification</li>
        <li>Federated Learning Defense Mechanisms</li>
        <li>Blockchain Security Applications</li>
      </ul>
    </div>
    <div class="skill-col">
      <div class="skill-col-head">Programming</div>
      <ul class="skill-items">
        <li>PCEP — Certified Python Programmer</li>
        <li>Unix System Administration</li>
        <li>IoT &amp; WAN Technologies</li>
      </ul>
    </div>
    <div class="skill-col">
      <div class="skill-col-head">Research Areas</div>
      <ul class="skill-items">
        <li>Vehicular Networks &amp; V2X Security</li>
        <li>Collective Perception Misbehavior Detection</li>
        <li>Game Theory &amp; Trust Mechanisms</li>
        <li>Bayesian Inference &amp; Reputation Systems</li>
        <li>Federated Learning</li>
      </ul>
    </div>
    <div class="skill-col">
      <div class="skill-col-head">Qualities</div>
      <ul class="skill-items">
        <li>Organizational Skills</li>
        <li>Dynamic &amp; Initiative-driven</li>
        <li>Flexible &amp; Collaborative</li>
        <li>Chess — strategic thinking</li>
      </ul>
    </div>
  </div>
</div>

<!-- TEACHING -->
<div class="page-section" id="teaching" style="background: var(--bg2);">
  <div class="section-eyebrow">
    <span class="eyebrow-num">§4</span>
    <span class="eyebrow-title">Teaching</span>
    <span class="eyebrow-rule"></span>
  </div>
  <h2 class="section-heading">Teaching Experience</h2>
  <div class="teach-grid">
    <div class="teach-item">
      <div class="teach-num">01</div>
      <div><div class="teach-role">Unix System Administration — Lab Sessions</div><div class="teach-course">2nd year engineering students · ENSIAS</div></div>
    </div>
    <div class="teach-item">
      <div class="teach-num">02</div>
      <div><div class="teach-role">Enterprise Networking — Tutorials</div><div class="teach-course">CCNA 1 · 1st year engineering students · ENSIAS</div></div>
    </div>
    <div class="teach-item">
      <div class="teach-num">03</div>
      <div><div class="teach-role">Enterprise Networking — Practical Lab Sessions</div><div class="teach-course">CCNA 1 · 1st year engineering students · ENSIAS</div></div>
    </div>
    <div class="teach-item">
      <div class="teach-num">04</div>
      <div><div class="teach-role">IoT &amp; WAN Technologies — Lab Sessions</div><div class="teach-course">2nd year engineering students · ENSIAS</div></div>
    </div>
    <div class="teach-item">
      <div class="teach-num">05</div>
      <div><div class="teach-role">Final Year Project Co-Supervision (2 FYPs)</div><div class="teach-course">2nd year engineering students · ENSIAS</div></div>
    </div>
  </div>
</div>

<!-- EXPERIENCE -->
<div class="page-section" id="experience">
  <div class="section-eyebrow">
    <span class="eyebrow-num">§5</span>
    <span class="eyebrow-title">Experience</span>
    <span class="eyebrow-rule"></span>
  </div>
  <h2 class="section-heading">Professional Experience</h2>
  <div class="exp-row">
    <div><div class="exp-period">03/2023 — 10/2023</div><div class="exp-place">ENSIAS · Rabat, Morocco</div></div>
    <div><div class="exp-role-title">Research Internship</div><div class="exp-org-name">Laboratory of the National School of Computer Science and Systems Analysis (ENSIAS)</div></div>
  </div>
  <div class="exp-row">
    <div><div class="exp-period">05/2021 — 07/2021</div><div class="exp-place">El Jadida, Morocco</div></div>
    <div><div class="exp-role-title">Internship</div><div class="exp-org-name">E-Viande Company · Zaouiat SIDI ISMAIL</div></div>
  </div>
  <div class="exp-row">
    <div><div class="exp-period">10/2019 — Present</div><div class="exp-place">Essaouira, Morocco</div></div>
    <div><div class="exp-role-title">Member</div><div class="exp-org-name">Forsa Personal Development Association</div></div>
  </div>
</div>

<!-- CONTACT -->
<div id="contact">
  <div class="contact-inner">
    <div>
      <div class="contact-title">Open to research collaborations &amp; academic opportunities</div>
      <p class="contact-sub">Whether you are interested in joint research, reviewing my work, or discussing vehicular network security — I would be glad to hear from you.</p>
    </div>
    <div class="contact-details">
      <div class="contact-row"><span class="c-label">Email</span><span class="c-val"><a href="mailto:adil7attiaoui@gmail.com">adil7attiaoui@gmail.com</a></span></div>
      <div class="contact-row"><span class="c-label">Phone</span><span class="c-val"><a href="tel:+000000000">+000000000</a></span></div>
      <div class="contact-row"><span class="c-label">LinkedIn</span><span class="c-val"><a href="https://www.linkedin.com/in/" target="_blank">linkedin.com/in/adil-attiaoui</a></span></div>
      <div class="contact-row"><span class="c-label">Location</span><span class="c-val">Salé, Maroc 11160</span></div>
      <div class="contact-row"><span class="c-label">Affiliation</span><span class="c-val">ENSIAS · Mohammed V University<br>Rabat, Morocco</span></div>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <span>© 2025 Adil Attiaoui · All rights reserved</span>
  <span>Research Portfolio · ENSIAS · Mohammed V University</span>
  <span>#1a56db</span>
</footer>

<script>
  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
      }
    });
  }, { threshold: 0.12 });

  document.querySelectorAll('.edu-table tr, .pub-article, .teach-item').forEach((el, i) => {
    el.style.transitionDelay = (i % 5) * 0.07 + 's';
    io.observe(el);
  });

  setTimeout(() => {
    document.querySelectorAll('.lang-fill').forEach(b => b.classList.add('go'));
  }, 500);
</script>
</body>
</html>
