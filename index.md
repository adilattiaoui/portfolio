<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Adil Attiaoui — PhD Researcher</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@300;400;500&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #ffffff;
      --bg2: #f5f7fa;
      --surface: #f0f4f8;
      --surface2: #e8edf3;
      --border: rgba(26,86,219,0.15);
      --accent: #1a56db;
      --accent2: #0891b2;
      --text: #0f172a;
      --muted: #64748b;
      --serif: 'DM Serif Display', Georgia, serif;
      --mono: 'DM Mono', monospace;
      --sans: 'Outfit', sans-serif;
    }

    html { scroll-behavior: smooth; }
    body { background: var(--bg); color: var(--text); font-family: var(--sans); font-weight: 300; line-height: 1.7; overflow-x: hidden; }
    body::after { content: ''; position: fixed; inset: 0; background-image: radial-gradient(circle, rgba(26,86,219,0.06) 1px, transparent 1px); background-size: 28px 28px; pointer-events: none; z-index: 0; }

    /* NAV */
    nav { position: fixed; top: 0; left: 0; right: 0; z-index: 500; display: flex; align-items: center; justify-content: space-between; padding: 1.2rem 3rem; background: rgba(255,255,255,0.92); backdrop-filter: blur(16px); border-bottom: 1px solid var(--border); box-shadow: 0 1px 12px rgba(26,86,219,0.06); }
    .nav-logo { font-family: var(--mono); font-size: 0.85rem; color: var(--accent); letter-spacing: 0.15em; }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a { font-family: var(--mono); font-size: 0.75rem; color: var(--muted); text-decoration: none; letter-spacing: 0.1em; text-transform: uppercase; transition: color 0.2s; }
    .nav-links a:hover { color: var(--accent); }

    /* HERO */
    #hero { min-height: 100vh; display: flex; align-items: center; gap: 4rem; position: relative; padding: 8rem 6rem 5rem; overflow: hidden; }
    .hero-glow { position: absolute; width: 700px; height: 700px; border-radius: 50%; background: radial-gradient(circle, rgba(26,86,219,0.07) 0%, transparent 70%); top: -100px; right: -200px; pointer-events: none; animation: pulse-glow 6s ease-in-out infinite; }
    .hero-glow2 { position: absolute; width: 400px; height: 400px; border-radius: 50%; background: radial-gradient(circle, rgba(8,145,178,0.05) 0%, transparent 70%); bottom: 0; left: 20%; pointer-events: none; animation: pulse-glow 8s ease-in-out infinite reverse; }
    @keyframes pulse-glow { 0%, 100% { transform: scale(1); opacity: 1; } 50% { transform: scale(1.1); opacity: 0.7; } }

    .hero-photo-wrap { position: relative; flex-shrink: 0; z-index: 2; opacity: 0; animation: fade-up 0.8s 0.2s forwards; }
    .hero-photo-frame { width: 240px; height: 240px; border-radius: 50%; border: 3px solid var(--accent); padding: 4px; background: var(--bg); box-shadow: 0 0 0 1px rgba(26,86,219,0.15), 0 16px 48px rgba(26,86,219,0.14); position: relative; }
    .hero-photo-frame::after { content: ''; position: absolute; inset: -10px; border-radius: 50%; border: 1px dashed rgba(26,86,219,0.25); animation: spin-ring 18s linear infinite; }
    @keyframes spin-ring { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
    .hero-photo-frame img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; object-position: center top; display: block; }
    .hero-photo-caption { text-align: center; margin-top: 1rem; font-family: var(--mono); font-size: 0.65rem; color: var(--muted); letter-spacing: 0.12em; text-transform: uppercase; }

    .hero-content { position: relative; z-index: 2; flex: 1; min-width: 0; }
    .hero-tag { font-family: var(--mono); font-size: 0.75rem; color: var(--accent2); letter-spacing: 0.25em; text-transform: uppercase; margin-bottom: 1.5rem; display: flex; align-items: center; gap: 0.8rem; opacity: 0; animation: fade-up 0.8s 0.3s forwards; }
    .hero-tag::before { content: ''; display: inline-block; width: 2rem; height: 1px; background: var(--accent2); }
    .hero-name { font-family: var(--serif); font-size: clamp(3.5rem, 8vw, 7rem); line-height: 1.05; letter-spacing: -0.02em; margin-bottom: 1.5rem; color: var(--text); opacity: 0; animation: fade-up 0.8s 0.45s forwards; }
    .hero-name em { font-style: italic; color: var(--accent); }
    .hero-subtitle { font-size: 1.05rem; color: var(--muted); max-width: 560px; margin-bottom: 2.5rem; line-height: 1.8; opacity: 0; animation: fade-up 0.8s 0.6s forwards; }
    .hero-subtitle strong { color: var(--text); font-weight: 500; }
    .hero-badges { display: flex; flex-wrap: wrap; gap: 0.75rem; margin-bottom: 2.5rem; opacity: 0; animation: fade-up 0.8s 0.75s forwards; }
    .badge { font-family: var(--mono); font-size: 0.72rem; padding: 0.4rem 1rem; border: 1px solid rgba(26,86,219,0.25); border-radius: 2px; color: var(--muted); letter-spacing: 0.08em; transition: all 0.2s; background: var(--bg); }
    .badge:hover { border-color: var(--accent); color: var(--accent); background: rgba(26,86,219,0.05); }
    .hero-ctas { display: flex; gap: 1.2rem; flex-wrap: wrap; opacity: 0; animation: fade-up 0.8s 0.9s forwards; }
    .btn-primary { font-family: var(--mono); font-size: 0.8rem; letter-spacing: 0.12em; text-transform: uppercase; padding: 0.9rem 2rem; background: var(--accent); color: #fff; border: none; cursor: pointer; text-decoration: none; transition: all 0.2s; font-weight: 500; }
    .btn-primary:hover { background: #1340b0; transform: translateY(-2px); }
    .btn-outline { font-family: var(--mono); font-size: 0.8rem; letter-spacing: 0.12em; text-transform: uppercase; padding: 0.9rem 2rem; border: 1px solid rgba(26,86,219,0.3); color: var(--muted); cursor: pointer; text-decoration: none; transition: all 0.2s; }
    .btn-outline:hover { border-color: var(--accent); color: var(--accent); background: rgba(26,86,219,0.04); }
    .scroll-indicator { position: absolute; bottom: 2.5rem; left: 6rem; display: flex; align-items: center; gap: 0.8rem; font-family: var(--mono); font-size: 0.7rem; color: var(--muted); letter-spacing: 0.15em; opacity: 0; animation: fade-up 1s 1.4s forwards; z-index: 3; }
    .scroll-line { width: 40px; height: 1px; background: #cbd5e1; position: relative; overflow: hidden; }
    .scroll-line::after { content: ''; position: absolute; left: -100%; top: 0; width: 100%; height: 100%; background: var(--accent); animation: slide-line 2s 2s infinite; }
    @keyframes slide-line { 0% { left: -100%; } 100% { left: 100%; } }

    /* SECTIONS */
    section { position: relative; z-index: 2; padding: 6rem 3rem; max-width: 1100px; margin: 0 auto; }
    .section-header { display: flex; align-items: baseline; gap: 1.5rem; margin-bottom: 4rem; }
    .section-num { font-family: var(--mono); font-size: 0.75rem; color: var(--accent); opacity: 0.5; }
    .section-title { font-family: var(--serif); font-size: clamp(2rem, 4vw, 3rem); letter-spacing: -0.02em; color: var(--text); }
    .section-line { flex: 1; height: 1px; background: rgba(26,86,219,0.15); margin-left: 1rem; }

    /* ABOUT */
    #about .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start; }
    .about-text p { color: var(--muted); margin-bottom: 1.2rem; font-size: 1rem; line-height: 1.85; }
    .about-text p strong { color: var(--text); font-weight: 500; }
    .info-grid { display: grid; gap: 1rem; }
    .info-item { display: flex; gap: 1rem; align-items: flex-start; padding: 1rem 1.2rem; border: 1px solid rgba(26,86,219,0.15); border-left: 3px solid var(--accent); background: var(--surface); }
    .info-label { font-family: var(--mono); font-size: 0.7rem; color: var(--accent); letter-spacing: 0.1em; text-transform: uppercase; min-width: 80px; margin-top: 0.15rem; }
    .info-val { font-size: 0.9rem; color: var(--text); }

    /* EDUCATION */
    #education .timeline { position: relative; padding-left: 2rem; }
    #education .timeline::before { content: ''; position: absolute; left: 0; top: 0.5rem; bottom: 0; width: 1px; background: linear-gradient(to bottom, var(--accent), transparent); }
    .timeline-item { position: relative; margin-bottom: 3rem; padding-left: 2.5rem; }
    .timeline-dot { position: absolute; left: -2.5rem; top: 0.4rem; width: 10px; height: 10px; border: 2px solid var(--accent); background: var(--bg); border-radius: 50%; }
    .tl-date { font-family: var(--mono); font-size: 0.72rem; color: var(--accent2); letter-spacing: 0.1em; margin-bottom: 0.4rem; }
    .tl-degree { font-family: var(--serif); font-size: 1.15rem; margin-bottom: 0.3rem; color: var(--text); }
    .tl-school { font-size: 0.85rem; color: var(--muted); }
    .tl-school + .tl-school { margin-top: 0.2rem; }

    /* PUBLICATIONS */
    #publications .pub-list { display: grid; gap: 1.5rem; }
    .pub-card { padding: 1.8rem 2rem; border: 1px solid rgba(26,86,219,0.15); background: var(--surface); position: relative; overflow: hidden; transition: all 0.3s; }
    .pub-card::before { content: ''; position: absolute; left: 0; top: 0; bottom: 0; width: 3px; background: var(--accent); }
    .pub-card:hover { border-color: rgba(26,86,219,0.35); background: var(--surface2); transform: translateX(4px); box-shadow: 0 4px 20px rgba(26,86,219,0.08); }
    .pub-venue { font-family: var(--mono); font-size: 0.68rem; color: var(--accent2); letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 0.6rem; display: flex; align-items: center; gap: 0.8rem; }
    .pub-class { padding: 0.15rem 0.5rem; border: 1px solid var(--accent2); border-radius: 2px; font-size: 0.65rem; }
    .pub-class.q1 { border-color: #059669; color: #059669; }
    .pub-title { font-size: 0.95rem; font-weight: 500; margin-bottom: 0.6rem; line-height: 1.5; color: var(--text); }
    .pub-authors { font-size: 0.82rem; color: var(--muted); }
    .pub-authors strong { color: var(--accent); font-weight: 500; }
    .pub-doi { font-family: var(--mono); font-size: 0.68rem; color: var(--muted); margin-top: 0.6rem; display: block; }
    .pub-doi a { color: var(--accent2); text-decoration: none; }
    .pub-doi a:hover { text-decoration: underline; }

    /* SKILLS — tabbed grid */
    .skills-tabs { display: flex; gap: 0; margin-bottom: 2rem; border-bottom: 2px solid rgba(26,86,219,0.12); flex-wrap: wrap; }
    .skills-tab { font-family: var(--mono); font-size: 0.72rem; letter-spacing: 0.1em; text-transform: uppercase; padding: 0.7rem 1.4rem; cursor: pointer; color: var(--muted); border-bottom: 2px solid transparent; margin-bottom: -2px; transition: all 0.2s; background: none; border-top: none; border-left: none; border-right: none; }
    .skills-tab:hover { color: var(--accent); }
    .skills-tab.active { color: var(--accent); border-bottom-color: var(--accent); }
    .skills-panel { display: none; }
    .skills-panel.active { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 1.5rem; }

    .skill-group { padding: 1.8rem; border: 1px solid rgba(26,86,219,0.15); background: var(--surface); transition: border-color 0.3s; }
    .skill-group:hover { border-color: rgba(26,86,219,0.35); box-shadow: 0 4px 16px rgba(26,86,219,0.07); }
    .skill-group-title { font-family: var(--mono); font-size: 0.72rem; color: var(--accent); letter-spacing: 0.15em; text-transform: uppercase; margin-bottom: 1.2rem; display: flex; align-items: center; gap: 0.6rem; }
    .skill-group-title::after { content: ''; flex: 1; height: 1px; background: rgba(26,86,219,0.15); }
    .cert-list { list-style: none; display: grid; gap: 0.6rem; }
    .cert-list li { font-size: 0.85rem; color: var(--muted); display: flex; align-items: flex-start; gap: 0.6rem; line-height: 1.4; }
    .cert-list li::before { content: '→'; color: var(--accent2); font-family: var(--mono); font-size: 0.8rem; flex-shrink: 0; margin-top: 0.05rem; }

    /* cert badge inside list */
    .cert-badge { display: inline-block; font-family: var(--mono); font-size: 0.6rem; letter-spacing: 0.06em; padding: 0.1rem 0.45rem; border-radius: 2px; margin-left: 0.4rem; vertical-align: middle; }
    .cert-badge.cisco { background: #e8f0fd; color: #1a56db; border: 1px solid rgba(26,86,219,0.3); }
    .cert-badge.huawei { background: #fef3c7; color: #92400e; border: 1px solid #f59e0b; }
    .cert-badge.isc { background: #ede9fe; color: #5b21b6; border: 1px solid #8b5cf6; }
    .cert-badge.python { background: #ecfdf5; color: #065f46; border: 1px solid #059669; }

    /* Professional Skills / Soft Skills cards */
    .soft-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; }
    .soft-card { padding: 1.8rem; border: 1px solid rgba(26,86,219,0.15); background: var(--surface); }
    .soft-card-title { font-family: var(--mono); font-size: 0.72rem; color: var(--accent); letter-spacing: 0.15em; text-transform: uppercase; margin-bottom: 1.2rem; padding-bottom: 0.7rem; border-bottom: 1px solid rgba(26,86,219,0.15); }
    .soft-items { display: grid; gap: 0.9rem; }
    .soft-item { display: flex; align-items: flex-start; gap: 0.8rem; }
    .soft-icon { font-size: 1rem; min-width: 1.6rem; text-align: center; margin-top: 0.1rem; }
    .soft-label { font-size: 0.88rem; font-weight: 500; color: var(--text); margin-bottom: 0.1rem; }
    .soft-desc { font-size: 0.78rem; color: var(--muted); line-height: 1.4; }

    /* TEACHING */
    #teaching .teach-list { display: grid; gap: 1rem; }
    .teach-item { display: flex; gap: 1.5rem; align-items: flex-start; padding: 1.4rem 1.5rem; border: 1px solid rgba(26,86,219,0.15); background: var(--surface); transition: all 0.3s; }
    .teach-item:hover { border-color: rgba(26,86,219,0.35); box-shadow: 0 4px 16px rgba(26,86,219,0.07); }
    .teach-icon { font-size: 1.2rem; min-width: 2rem; text-align: center; margin-top: 0.15rem; }
    .teach-body { flex: 1; }
    .teach-title { font-size: 0.92rem; font-weight: 500; color: var(--text); margin-bottom: 0.3rem; }
    .teach-meta { font-family: var(--mono); font-size: 0.68rem; color: var(--accent2); letter-spacing: 0.08em; text-transform: uppercase; margin-bottom: 0.5rem; }
    .teach-desc { font-size: 0.85rem; color: var(--muted); line-height: 1.65; }

    /* FYP cards */
    .fyp-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 2.5rem; }
    .fyp-label { font-family: var(--mono); font-size: 0.68rem; color: var(--accent); letter-spacing: 0.15em; text-transform: uppercase; margin-bottom: 1.5rem; display: flex; align-items: center; gap: 0.8rem; }
    .fyp-label::after { content: ''; flex: 1; height: 1px; background: rgba(26,86,219,0.15); }
    .fyp-card { padding: 1.6rem; border: 1px solid rgba(26,86,219,0.2); border-top: 3px solid var(--accent); background: var(--bg); transition: all 0.3s; }
    .fyp-card:hover { box-shadow: 0 6px 24px rgba(26,86,219,0.1); transform: translateY(-2px); }
    .fyp-num { font-family: var(--mono); font-size: 0.65rem; color: var(--accent2); letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 0.6rem; }
    .fyp-title { font-family: var(--serif); font-size: 1rem; color: var(--text); margin-bottom: 0.6rem; line-height: 1.4; }
    .fyp-student { font-size: 0.82rem; color: var(--muted); margin-bottom: 0.4rem; }
    .fyp-student strong { color: var(--text); }
    .fyp-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-top: 0.8rem; }
    .fyp-tag { font-family: var(--mono); font-size: 0.62rem; padding: 0.2rem 0.6rem; border: 1px solid rgba(26,86,219,0.2); color: var(--muted); border-radius: 2px; }

    /* EXPERIENCE */
    #experience .exp-list { display: grid; gap: 1.5rem; }
    .exp-item { display: grid; grid-template-columns: 160px 1fr; gap: 2rem; padding-bottom: 1.5rem; border-bottom: 1px solid rgba(26,86,219,0.12); }
    .exp-item:last-child { border-bottom: none; }
    .exp-date { font-family: var(--mono); font-size: 0.72rem; color: var(--accent); letter-spacing: 0.08em; line-height: 1.5; padding-top: 0.2rem; }
    .exp-role { font-weight: 500; margin-bottom: 0.3rem; color: var(--text); }
    .exp-org { font-size: 0.85rem; color: var(--muted); }

    /* CONTACT */
    #contact { text-align: center; padding-bottom: 8rem; }
    #contact .contact-inner { max-width: 600px; margin: 0 auto; }
    #contact .contact-title { font-family: var(--serif); font-size: clamp(2.5rem, 5vw, 4rem); margin-bottom: 1rem; color: var(--text); }
    #contact .contact-sub { color: var(--muted); margin-bottom: 3rem; font-size: 1rem; }
    .contact-links { display: flex; justify-content: center; gap: 1.5rem; flex-wrap: wrap; }
    .contact-link { font-family: var(--mono); font-size: 0.8rem; letter-spacing: 0.1em; text-decoration: none; color: var(--muted); border: 1px solid rgba(26,86,219,0.2); padding: 0.8rem 1.8rem; transition: all 0.2s; display: flex; align-items: center; gap: 0.5rem; }
    .contact-link:hover { color: var(--accent); border-color: var(--accent); background: rgba(26,86,219,0.04); }

    /* FOOTER */
    footer { position: relative; z-index: 2; text-align: center; padding: 2rem; border-top: 1px solid rgba(26,86,219,0.12); font-family: var(--mono); font-size: 0.72rem; color: var(--muted); letter-spacing: 0.1em; background: var(--bg2); }

    @keyframes fade-up { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
    .divider { position: relative; z-index: 2; height: 1px; background: rgba(26,86,219,0.12); max-width: 1100px; margin: 0 auto; }

    /* LANG BARS */
    .lang-item { margin-bottom: 1.2rem; }
    .lang-name { display: flex; justify-content: space-between; font-size: 0.85rem; margin-bottom: 0.4rem; color: var(--text); }
    .lang-level { color: var(--muted); font-size: 0.8rem; }
    .lang-bar-bg { height: 3px; background: #e2e8f0; border-radius: 2px; overflow: hidden; }
    .lang-bar-fill { height: 100%; background: linear-gradient(90deg, var(--accent), var(--accent2)); border-radius: 2px; width: 0; transition: width 1.2s cubic-bezier(0.4,0,0.2,1); }
    .lang-bar-fill.animate { width: var(--w); }

    /* RESPONSIVE */
    @media (max-width: 900px) {
      #hero { flex-direction: column; align-items: flex-start; gap: 2.5rem; padding: 7rem 2rem 4rem; }
      .hero-photo-frame { width: 160px; height: 160px; }
      .scroll-indicator { left: 2rem; }
      .fyp-grid { grid-template-columns: 1fr; }
      .soft-grid { grid-template-columns: 1fr; }
    }
    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { display: none; }
      section { padding: 4rem 1.5rem; }
      #about .about-grid { grid-template-columns: 1fr; gap: 3rem; }
      .exp-item { grid-template-columns: 1fr; gap: 0.5rem; }
    }
    @media (max-width: 600px) {
      .hero-photo-frame { width: 120px; height: 120px; }
      #hero { padding: 7rem 1.5rem 4rem; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <span class="nav-logo">A.ATTIAOUI</span>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#publications">Publications</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#teaching">Teaching</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero" style="max-width:100%;">
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>
  <div class="hero-photo-wrap">
    <div class="hero-photo-frame">
      <img src="1757092051673.jfif" alt="Adil Attiaoui" />
    </div>
    <div class="hero-photo-caption">Adil Attiaoui · PhD</div>
  </div>
  <div class="hero-content">
    <div class="hero-tag">PhD Researcher · ENSIAS–UM5 &amp; INSA–UPHF</div>
    <h1 class="hero-name">Adil <em>Attiaoui</em></h1>
    <p class="hero-subtitle">
      Researching <strong>Vehicular Collective Perception Misbehavior Detection &amp; Mitigation</strong>
      in a co-tutelle PhD between <strong>ENSIAS, Mohammed V University in Rabat</strong> (Morocco) and
      <strong>INSA Hauts-de-France, Polytechnic University of Hauts-de-France</strong> (France). Exploring the intersection of cybersecurity, federated learning, and intelligent transportation systems.
    </p>
    <div class="hero-badges">
      <span class="badge">V2X Security</span>
      <span class="badge">Federated Learning</span>
      <span class="badge">Blockchain</span>
      <span class="badge">Game Theory</span>
      <span class="badge">IoT</span>
      <span class="badge">CCNA Certified</span>
    </div>
    <div class="hero-ctas">
      <a href="#publications" class="btn-primary">View Publications</a>
      <a href="#contact" class="btn-outline">Get in Touch</a>
    </div>
  </div>
  <div class="scroll-indicator">
    <span class="scroll-line"></span>
    <span>Scroll</span>
  </div>
</section>

<div class="divider"></div>

<!-- ABOUT -->
<section id="about">
  <div class="section-header">
    <span class="section-num">01</span>
    <h2 class="section-title">About</h2>
    <div class="section-line"></div>
  </div>
  <div class="about-grid">
    <div class="about-text">
      <p>I am a <strong>PhD student</strong> in a co-tutelle program between the National School of Computer Science and Systems Analysis (<strong>ENSIAS</strong>), Mohammed V University in Rabat, Morocco, and the <strong>Institut National des Sciences Appliquées de Hauts-de-France (INSA–UPHF)</strong> in France — specializing in vehicular network security and misbehavior detection.</p>
      <p>My research focuses on designing robust detection and mitigation mechanisms for <strong>misbehaving nodes in vehicular collective perception systems</strong> — a critical challenge as autonomous vehicles become increasingly reliant on cooperative sensor data.</p>
      <p>I combine formal approaches from <strong>game theory</strong>, <strong>Bayesian inference</strong>, and <strong>reputation systems</strong> to model adversarial behavior and engineer trust-based defenses for connected vehicle environments.</p>
      <p>Beyond research, I am an active <strong>teaching assistant</strong> mentoring engineering students in networking, Unix systems, and IoT — and an avid chess player.</p>
    </div>
    <div class="info-grid">
      <div class="info-item">
        <span class="info-label">Email</span>
        <span class="info-val">adil7attiaoui@gmail.com</span>
      </div>
      <div class="info-item">
        <span class="info-label">Phone</span>
        <span class="info-val">+33 765 124 470</span>
      </div>
      <div class="info-item">
        <span class="info-label">Location</span>
        <span class="info-val">Rabat, Morocco</span>
      </div>
      <div class="info-item">
        <span class="info-label">Status</span>
        <span class="info-val">PhD Candidate (2023 – Present)<br><span style="font-size:0.82rem;color:var(--muted)">ENSIAS × INSA–UPHF · Co-tutelle</span></span>
      </div>
      <div class="info-item">
        <span class="info-label">Languages</span>
        <div class="info-val" style="width:100%">
          <div class="lang-item">
            <div class="lang-name"><span>Arabic</span><span class="lang-level">Native</span></div>
            <div class="lang-bar-bg"><div class="lang-bar-fill" style="--w:100%"></div></div>
          </div>
          <div class="lang-item">
            <div class="lang-name"><span>French</span><span class="lang-level">Intermediate</span></div>
            <div class="lang-bar-bg"><div class="lang-bar-fill" style="--w:65%"></div></div>
          </div>
          <div class="lang-item">
            <div class="lang-name"><span>English</span><span class="lang-level">Intermediate</span></div>
            <div class="lang-bar-bg"><div class="lang-bar-fill" style="--w:65%"></div></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- EDUCATION -->
<section id="education">
  <div class="section-header">
    <span class="section-num">02</span>
    <h2 class="section-title">Education</h2>
    <div class="section-line"></div>
  </div>
  <div class="timeline">
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="tl-date">10/2023 — Present</div>
      <div class="tl-degree">PhD in Vehicular Collective Perception Misbehavior Detection &amp; Mitigation</div>
      <div class="tl-school">ENSIAS, Mohammed V University · Rabat, Morocco</div>
      <div class="tl-school">in co-tutelle with INSA Hauts-de-France, Polytechnic University of Hauts-de-France · Valenciennes, France</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="tl-date">10/2021 — 10/2023</div>
      <div class="tl-degree">Research Master's in Systems and Services Security</div>
      <div class="tl-school">National School of Computer Science and Systems Analysis (ENSIAS) · Rabat, Morocco</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="tl-date">12/2020 — 08/2021</div>
      <div class="tl-degree">Bachelor's in Software Engineering &amp; Advanced Administration of Systems and Networks</div>
      <div class="tl-school">Higher School of Technology (EST Casablanca) · Casablanca, Morocco</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="tl-date">09/2018 — 08/2020</div>
      <div class="tl-degree">Specialized Technician Diploma in Computer Networks</div>
      <div class="tl-school">Specialized Institute of Applied Technology · Essaouira, Morocco</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="tl-date">09/2017 — 06/2018</div>
      <div class="tl-degree">Scientific Baccalaureate in Mathematics</div>
      <div class="tl-school">Mohammed V High School · Essaouira, Morocco</div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- PUBLICATIONS -->
<section id="publications">
  <div class="section-header">
    <span class="section-num">03</span>
    <h2 class="section-title">Publications</h2>
    <div class="section-line"></div>
  </div>
  <div class="pub-list">

    <div class="pub-card">
      <div class="pub-venue">Internet of Things · Volume 34, November 2025 <span class="pub-class q1">Q1 Journal</span></div>
      <div class="pub-title">Trust-aware and game-theoretic cooperative detection of misbehavior in connected vehicles</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, M. Elmachkour, A. Kobbane, M. Ayaida, H. Tembine</div>
      <div class="pub-doi"><a href="https://doi.org/10.1016/j.iot.2025.101799">doi: 10.1016/j.iot.2025.101799</a></div>
    </div>

    <div class="pub-card">
      <div class="pub-venue">CommNet 2025 · Rabat, Morocco</div>
      <div class="pub-title">Blockchained Federated Learning for Secure and Privacy-Preserving Internet of Vehicles: A Comprehensive Review</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, A. Kobbane, M. Ayaida, M. Elmachkour, Y. El Hillali</div>
      <div class="pub-doi"><a href="https://doi.org/10.1109/CommNet68224.2025.11288848">doi: 10.1109/CommNet68224.2025.11288848</a></div>
    </div>

    <div class="pub-card">
      <div class="pub-venue">VEHITS 2025 · Porto, Portugal <span class="pub-class">Class C</span></div>
      <div class="pub-title">Misbehavior Detection in Connected Vehicle: Pre-Bayesian Majority Game Framework</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, M. Elmachkour, A. Kobbane, M. Ayaida</div>
      <div class="pub-doi"><a href="https://doi.org/10.5220/0013359100003941">doi: 10.5220/0013359100003941</a></div>
    </div>

    <div class="pub-card">
      <div class="pub-venue">ICCSN 2024 · Ningbo, China</div>
      <div class="pub-title">Strategic Trust: Reputation-Based Mechanisms for Mitigating Malicious Behavior in Vehicular Collective Perception</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, M. Elmachkour, M. Ayaida, A. Kobbane</div>
      <div class="pub-doi"><a href="https://doi.org/10.1109/ICCSN63464.2024.10793308">doi: 10.1109/ICCSN63464.2024.10793308</a></div>
    </div>

    <div class="pub-card">
      <div class="pub-venue">UNet 2024 · Marrakech, Morocco</div>
      <div class="pub-title">Securing University Diploma Management through Blockchain and InterPlanetary File System</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, A. Kobbane, M. Ayaida</div>
      <div class="pub-doi"><a href="https://doi.org/10.1109/UNet62310.2024.10794707">doi: 10.1109/UNet62310.2024.10794707</a></div>
    </div>

    <div class="pub-card">
      <div class="pub-venue">INTCEC 2024 · Chicago, IL, USA</div>
      <div class="pub-title">Blockchain-Enabled Defense Mechanism for Protecting Federated Learning Systems Against Malicious Node Updates</div>
      <div class="pub-authors"><strong>A. Attiaoui</strong>, A. Kobbane, J. Elhachmi, M. Ayaida, K. Chougdali</div>
      <div class="pub-doi"><a href="https://doi.org/10.1109/INTCEC61833.2024.10602881">doi: 10.1109/INTCEC61833.2024.10602881</a></div>
    </div>

    <div class="pub-card">
      <div class="pub-venue">ICC 2024 · Denver, CO, USA <span class="pub-class">Class B</span></div>
      <div class="pub-title">Efficient Collaborations through Weight-Driven Coalition Dynamics in Federated Learning Systems</div>
      <div class="pub-authors">M. E. Hanjri, H. Reguieg, <strong>A. Attiaoui</strong>, A. Abouaomar, A. Kobbane, M. E. Kamili</div>
      <div class="pub-doi"><a href="https://doi.org/10.1109/ICC51166.2024.10623064">doi: 10.1109/ICC51166.2024.10623064</a></div>
    </div>

  </div>
</section>

<div class="divider"></div>

<!-- SKILLS -->
<section id="skills">
  <div class="section-header">
    <span class="section-num">04</span>
    <h2 class="section-title">Skills &amp; Competencies</h2>
    <div class="section-line"></div>
  </div>

  <!-- Tab buttons -->
  <div class="skills-tabs">
    <button class="skills-tab active" onclick="showTab('certifications')">Certifications</button>
    <button class="skills-tab" onclick="showTab('savoirfaire')">Professional Skills</button>
    <button class="skills-tab " onclick="showTab('technical')">Technical Skills</button>
    <button class="skills-tab" onclick="showTab('savoiretre')">Soft Skills</button>
  </div>
  <!-- Certifications -->
  <div id="tab-certifications" class="skills-panel">
    <div class="skill-group">
      <div class="skill-group-title">Cisco</div>
      <ul class="cert-list">
        <li>CCNA: Enterprise Networking, Security &amp; Automation <span class="cert-badge cisco">CISCO</span></li>
        <li>CCNA: Switching, Routing &amp; Wireless Essentials <span class="cert-badge cisco">CISCO</span></li>
        <li>Introduction to Networks (ITN) <span class="cert-badge cisco">CISCO</span></li>
        <li>Network Security <span class="cert-badge cisco">CISCO</span></li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Huawei</div>
      <ul class="cert-list">
        <li>Huawei Datacom Certification <span class="cert-badge huawei">HUAWEI</span></li>
        <li>Huawei Cybersecurity Certification <span class="cert-badge huawei">HUAWEI</span></li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Security</div>
      <ul class="cert-list">
        <li>Certified in Cybersecurity (CC) <span class="cert-badge isc">(ISC)²</span></li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Programming</div>
      <ul class="cert-list">
        <li>PCEP – Certified Entry-Level Python Programmer <span class="cert-badge python">PYTHON INSTITUTE</span></li>
      </ul>
    </div>
  </div>
  <!-- Technical -->
  <div id="tab-technical" class="skills-panel active">
    <div class="skill-group">
      <div class="skill-group-title">Networking &amp; Protocols</div>
      <ul class="cert-list">
        <li>TCP/IP, OSPF, EIGRP, BGP, VLAN, STP, VPN</li>
        <li>Wireless Networking — 802.11, WPA2/3</li>
        <li>V2X Communication — ETSI ITS-G5, IEEE 802.11p, C-V2X</li>
        <li>Network Supervision — Nagios, ZABBIX</li>
        <li>Packet Tracer, GNS3, Wireshark</li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Cybersecurity</div>
      <ul class="cert-list">
        <li>Intrusion Detection &amp; Prevention Systems (IDS/IPS)</li>
        <li>PKI, TLS/SSL, Certificate Management</li>
        <li>Misbehavior Detection in Vehicular Networks</li>
        <li>Federated Learning Security &amp; Poisoning Attacks</li>
        <li>Blockchain-based Security Architectures</li>
        <li>Trust &amp; Reputation Management Systems</li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Programming &amp; Tools</div>
      <ul class="cert-list">
        <li>Python — NumPy, Pandas, Matplotlib, Scikit-learn</li>
        <li>SUMO — Urban Mobility Simulator</li>
        <li>NS-3 / Veins — Network Simulation</li>
        <li>TensorFlow / PyTorch — Federated Learning</li>
        <li>Solidity — Smart Contract Development</li>
        <li>Git, LaTeX, Linux/Unix Administration</li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Research Methods</div>
      <ul class="cert-list">
        <li>Game Theory — Nash Equilibrium, Bayesian Games</li>
        <li>Bayesian Inference &amp; Probabilistic Modeling</li>
        <li>Federated Learning Architectures (FL, FedAvg)</li>
        <li>Machine Learning for Anomaly Detection</li>
        <li>ETSI TR 103 460 — MBS Standard</li>
        <li>Academic Writing &amp; Scientific Communication</li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">IoT &amp; Embedded Systems</div>
      <ul class="cert-list">
        <li>IoT Architectures — MQTT, CoAP, REST</li>
        <li>WAN Technologies — LoRaWAN, NB-IoT</li>
        <li>Raspberry Pi, Arduino Prototyping</li>
        <li>Edge Computing Concepts</li>
      </ul>
    </div>
  </div>

  

  <!-- Savoir-faire -->
  <div id="tab-savoirfaire" class="skills-panel">
    <div class="skill-group">
      <div class="skill-group-title">Research &amp; Analysis</div>
      <ul class="cert-list">
        <li>Design and implementation of detection algorithms for vehicular misbehavior</li>
        <li>Modeling adversarial behaviors using game-theoretic frameworks</li>
        <li>Literature review, state-of-the-art synthesis, and scientific writing</li>
        <li>Experimental evaluation through simulation (SUMO, NS-3, Veins)</li>
        <li>Statistical analysis and result interpretation</li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Teaching &amp; Supervision</div>
      <ul class="cert-list">
        <li>Design and delivery of lab sessions and tutorials for engineering students</li>
        <li>Pedagogy adapted to different student levels </li>
        <li>Mentoring and academic supervision of Final Year Projects</li>
        <li>Assessment and evaluation of student practical work</li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Technical &amp; Engineering</div>
      <ul class="cert-list">
        <li>Network architecture design and configuration</li>
        <li>Security audit and vulnerability assessment</li>
        <li>Blockchain smart contract design and deployment</li>
        <li>Federated learning pipeline implementation and testing</li>
        <li>IoT system prototyping and monitoring</li>
      </ul>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Communication &amp; Dissemination</div>
      <ul class="cert-list">
        <li>Scientific paper writing and submission to peer-reviewed venues</li>
        <li>Oral presentation at international conferences</li>
        <li>Technical documentation and reporting in French and English</li>
        <li>Preparation of research posters and slides</li>
      </ul>
    </div>
  </div>

  <!-- Savoir-être -->
  <div id="tab-savoiretre" class="skills-panel" style="display:none;">
    <div class="soft-grid" style="grid-column: 1 / -1;">
      <div class="soft-card">
        <div class="soft-card-title">Interpersonal &amp; Relational</div>
        <div class="soft-items">
          <div class="soft-item">
            <div class="soft-icon">🤝</div>
            <div>
              <div class="soft-label">Collaboration &amp; Team Spirit</div>
              <div class="soft-desc">Experienced in working within multi-disciplinary teams across two countries (Morocco &amp; France), fostering constructive exchanges between research groups.</div>
            </div>
          </div>
          <div class="soft-item">
            <div class="soft-icon">🗣️</div>
            <div>
              <div class="soft-label">Communication</div>
              <div class="soft-desc">Ability to present complex technical concepts clearly to diverse audiences — students, academics, and conference attendees alike.</div>
            </div>
          </div>
          <div class="soft-item">
            <div class="soft-icon">🌍</div>
            <div>
              <div class="soft-label">Intercultural Openness</div>
              <div class="soft-desc">At ease navigating different academic and cultural environments, enriched by international mobility between Morocco and France.</div>
            </div>
          </div>
        </div>
      </div>
      <div class="soft-card">
        <div class="soft-card-title">Professional &amp; Intellectual</div>
        <div class="soft-items">
          <div class="soft-item">
            <div class="soft-icon">🎯</div>
            <div>
              <div class="soft-label">Rigor &amp; Analytical Thinking</div>
              <div class="soft-desc">Strong capacity for structured problem decomposition, formal modeling, and systematic validation of research hypotheses.</div>
            </div>
          </div>
          <div class="soft-item">
            <div class="soft-icon">💡</div>
            <div>
              <div class="soft-label">Initiative &amp; Autonomy</div>
              <div class="soft-desc">Proactive in identifying research gaps, proposing solutions, and managing independent workstreams within a co-tutelle PhD framework.</div>
            </div>
          </div>
          <div class="soft-item">
            <div class="soft-icon">🔄</div>
            <div>
              <div class="soft-label">Adaptability</div>
              <div class="soft-desc">Capable of quickly adapting to new research directions, tools, and academic environments — including transitions between Morocco and French institutions.</div>
            </div>
          </div>
        </div>
      </div>
      <div class="soft-card">
        <div class="soft-card-title">Organization &amp; Commitment</div>
        <div class="soft-items">
          <div class="soft-item">
            <div class="soft-icon">📋</div>
            <div>
              <div class="soft-label">Organization &amp; Planning</div>
              <div class="soft-desc">Ability to manage simultaneous responsibilities — research, teaching, publication, and supervision — while respecting deadlines.</div>
            </div>
          </div>
          <div class="soft-item">
            <div class="soft-icon">♟️</div>
            <div>
              <div class="soft-label">Strategic Thinking</div>
              <div class="soft-desc">Chess practitioner — cultivates a disciplined, anticipatory mindset transferable to research planning and problem-solving.</div>
            </div>
          </div>
          <div class="soft-item">
            <div class="soft-icon">📈</div>
            <div>
              <div class="soft-label">Continuous Learning</div>
              <div class="soft-desc">Committed to staying current with fast-evolving fields — regularly pursuing certifications, reading recent literature, and attending international events.</div>
            </div>
          </div>
        </div>
      </div>
      <div class="soft-card">
        <div class="soft-card-title">Academic Integrity &amp; Ethics</div>
        <div class="soft-items">
          <div class="soft-item">
            <div class="soft-icon">🧭</div>
            <div>
              <div class="soft-label">Research Ethics</div>
              <div class="soft-desc">Committed to reproducibility, proper attribution, and transparent reporting in all scientific work.</div>
            </div>
          </div>
          <div class="soft-item">
            <div class="soft-icon">🎓</div>
            <div>
              <div class="soft-label">Pedagogical Responsibility</div>
              <div class="soft-desc">Takes teaching duties seriously — investing time in preparing quality lab materials and providing constructive feedback to students.</div>
            </div>
          </div>
          <div class="soft-item">
            <div class="soft-icon">👨‍💼</div>
            <div>
              <div class="soft-label">Engagement &amp; Citizenship</div>
              <div class="soft-desc">Active member of the Forsa Personal Development Association, contributing to community mentoring and youth empowerment initiatives.</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- TEACHING -->
<section id="teaching">
  <div class="section-header">
    <span class="section-num">05</span>
    <h2 class="section-title">Teaching Experience</h2>
    <div class="section-line"></div>
  </div>

  <div class="teach-list">

    <div class="teach-item">
      <div class="teach-icon">🖥️</div>
      <div class="teach-body">
        <div class="teach-title">Unix System Administration — Lab Sessions</div>
        <div class="teach-meta">2nd year engineering · ENSIAS · Rabat</div>
        <div class="teach-desc">Delivered hands-on laboratory sessions covering Unix/Linux system administration fundamentals: file system management, user &amp; group permissions, process management, shell scripting (Bash), cron jobs, and network configuration using command-line tools. Students practiced on virtual machines and were evaluated on practical system setup exercises.</div>
      </div>
    </div>

    <div class="teach-item">
      <div class="teach-icon">📡</div>
      <div class="teach-body">
        <div class="teach-title">Enterprise Networking (CCNA 1) — Tutorials</div>
        <div class="teach-meta">1st year engineering · ENSIAS · Rabat</div>
        <div class="teach-desc">Conducted tutorial sessions aligned with the Cisco CCNA 1 curriculum, covering OSI and TCP/IP models, IPv4/IPv6 addressing and subnetting, Ethernet fundamentals, and introduction to routing concepts. Assisted students in understanding theoretical foundations and solving problem sets related to network design and addressing schemes.</div>
      </div>
    </div>

    <div class="teach-item">
      <div class="teach-icon">🔬</div>
      <div class="teach-body">
        <div class="teach-title">Enterprise Networking (CCNA 1) — Practical Lab Sessions</div>
        <div class="teach-meta">1st year engineering · ENSIAS · Rabat</div>
        <div class="teach-desc">Led practical labs using Cisco Packet Tracer, guiding students through router and switch configuration, VLAN setup, static routing, and basic network troubleshooting. Evaluated lab reports and provided individual feedback on topology design and configuration accuracy.</div>
      </div>
    </div>

    <div class="teach-item">
      <div class="teach-icon">🌐</div>
      <div class="teach-body">
        <div class="teach-title">IoT &amp; WAN Technologies — Lab Sessions</div>
        <div class="teach-meta">2nd year engineering · ENSIAS · Rabat</div>
        <div class="teach-desc">Facilitated lab sessions on Internet of Things architectures and Wide Area Network technologies. Topics included MQTT and CoAP protocols, sensor integration, cloud connectivity, LoRaWAN and NB-IoT fundamentals, and end-to-end IoT system prototyping. Students developed small-scale IoT projects from sensor data acquisition to remote monitoring dashboards.</div>
      </div>
    </div>

    <div class="teach-item">
      <div class="teach-icon">🎓</div>
      <div class="teach-body">
        <div class="teach-title">Final Year Project Co-Supervision (FYPs)</div>
        <div class="teach-meta">2nd year engineering · ENSIAS · Rabat</div>
        <div class="teach-desc">Co-supervised two end-of-study engineering projects, providing regular technical guidance, research methodology support, and feedback on written reports and oral presentations. Ensured alignment with academic standards and real-world applicability throughout the project lifecycle.</div>
      </div>
    </div>

  </div>

  <!-- FYP Details -->
  <div style="margin-top: 3rem;">
    <div class="fyp-label">Co-Supervised Final Year Projects</div>
    <div class="fyp-grid">

      <div class="fyp-card">
        <div class="fyp-num">FYP 01 · 2023–2024</div>
        <div class="fyp-title">Development of a Secure Application for the Management and Storage of Sensitive Documents</div>
        <div class="fyp-student">Supervised student: <strong>2nd year engineering — ENSIAS</strong></div>
        <div class="fyp-student" style="margin-top:0.3rem; font-size:0.82rem; color:var(--muted);">Designed and implemented a secure web-based application for managing and storing sensitive documents. The system ensures data confidentiality, integrity, and controlled access through authentication and encryption mechanisms. Key features include role-based access control, secure file upload/download, and audit logging to track user activities. The project focused on enhancing data protection and reliability in document management systems.</div>
        <div class="fyp-tags">
          <span class="fyp-tag">Machine Learning</span>
          <span class="fyp-tag">IoT Security</span>
          <span class="fyp-tag">IDS</span>
          <span class="fyp-tag">Python</span>
          <span class="fyp-tag">Network Traffic Analysis</span>
        </div>
      </div>

      <div class="fyp-card">
        <div class="fyp-num">FYP 02 · 2023–2024</div>
        <div class="fyp-title">Diploma Management Application Using Blockchain Technology and NFTs</div>
        <div class="fyp-student">Supervised student: <strong>2nd year engineering — ENSIAS</strong></div>
        <div class="fyp-student" style="margin-top:0.3rem; font-size:0.82rem; color:var(--muted);">Developed a decentralized application for the secure management and verification of academic diplomas using blockchain technology. The system leverages smart contracts to ensure authenticity and immutability of records, while NFTs are used to represent unique digital diplomas. The solution enables transparent verification, prevents fraud, and enhances trust between institutions and stakeholders.</div>
        <div class="fyp-tags">
          <span class="fyp-tag">Blockchain</span>
          <span class="fyp-tag">V2X</span>
          <span class="fyp-tag">Smart Contracts</span>
          <span class="fyp-tag">Solidity</span>
          <span class="fyp-tag">Data Integrity</span>
        </div>
      </div>

    </div>
  </div>
</section>

<div class="divider"></div>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-header">
    <span class="section-num">06</span>
    <h2 class="section-title">Experience</h2>
    <div class="section-line"></div>
  </div>
  <div class="exp-list">
    <div class="exp-item">
      <div class="exp-date">03/2023 – 10/2023<br>ENSIAS, Rabat</div>
      <div>
        <div class="exp-role">Research Internship</div>
        <div class="exp-org">Laboratory of ENSIAS — National School of Computer Science and Systems Analysis</div>
         <div class="fyp-student" style="margin-top:0.3rem; font-size:0.82rem; color:var(--muted);">Conducted research on a blockchain-enabled defense mechanism for securing federated learning systems against malicious node updates. The work focused on enhancing trust, integrity, and robustness in decentralized learning environments by detecting and mitigating adversarial contributions. Implemented and evaluated security strategies combining federated learning with blockchain technologies to ensure reliable model aggregation.</div>
      </div>
    </div>
    <div class="exp-item">
      <div class="exp-date">05/2021 – 07/2021<br>El Jadida, Morocco</div>
      <div>
        <div class="exp-role">Internship</div>
        <div class="exp-org">E-Viande Company, Zaouiat SIDI ISMAIL</div>
         <div class="exp-org" style="margin-top:0.3rem; font-size:0.82rem; color:var(--muted);">Developed an IoT-based system for monitoring the availability of electrical energy. The solution involved real-time data acquisition from sensors, system integration, and visualization of energy status to improve operational efficiency and reliability. The project demonstrated practical applications of IoT in industrial environments.</div>
      </div>
    </div>
    <div class="exp-item">
      <div class="exp-date">10/2019 – Present<br>Essaouira, Morocco</div>
      <div>
        <div class="exp-role">Member</div>
        <div class="exp-org">Forsa Personal Development Association</div>
         <div class="fyp-student" style="margin-top:0.3rem; font-size:0.82rem; color:var(--muted);">Active member of the Projects Monitoring and Evaluation Committee, contributing to the planning, follow-up, and assessment of community and development projects. Participated in organizing activities, supporting team coordination, and improving project impact through structured evaluation processes.</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-inner">
    <h2 class="contact-title">Let's <em style="font-family:var(--serif); font-style:italic; color:var(--accent)">Connect</em></h2>
    <p class="contact-sub">Interested in collaboration, research discussions, or academic opportunities? Reach out.</p>
    <div class="contact-links">
      <a class="contact-link" href="mailto:adil7attiaoui@gmail.com">✉ adil7attiaoui@gmail.com</a>
      <a class="contact-link" href="https://www.linkedin.com/in/adil-attiaoui" target="_blank">in LinkedIn</a>
      <a class="contact-link" href="tel:+33765124470">☎ +33 765 124 470</a>
    </div>
  </div>
</section>

<footer>
  <span style="color:var(--accent)">©</span> 2025 Adil Attiaoui · PhD Researcher · ENSIAS × INSA–UPHF
</footer>

<script>
  // Tab switcher for skills
  function showTab(name) {
    document.querySelectorAll('.skills-panel').forEach(p => { p.classList.remove('active'); p.style.display = 'none'; });
    document.querySelectorAll('.skills-tab').forEach(t => t.classList.remove('active'));
    const panel = document.getElementById('tab-' + name);
    if (panel) { panel.classList.add('active'); panel.style.display = 'grid'; }
    event.target.classList.add('active');
  }
  // init savoir-être panel as grid when shown
  document.getElementById('tab-savoiretre').style.display = 'none';

  // Scroll animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(el => {
      if (el.isIntersecting) { el.target.style.opacity = '1'; el.target.style.transform = 'none'; }
    });
  }, { threshold: 0.08 });

  document.querySelectorAll('.timeline-item').forEach((el, i) => {
    el.style.opacity = '0'; el.style.transform = 'translateX(-20px)';
    el.style.transition = `opacity 0.5s ${i * 0.1}s, transform 0.5s ${i * 0.1}s`;
    observer.observe(el);
  });
  document.querySelectorAll('.pub-card').forEach((el, i) => {
    el.style.opacity = '0'; el.style.transform = 'translateY(20px)';
    el.style.transition = `opacity 0.4s ${i * 0.08}s, transform 0.4s ${i * 0.08}s`;
    observer.observe(el);
  });
  document.querySelectorAll('.teach-item, .fyp-card').forEach((el, i) => {
    el.style.opacity = '0'; el.style.transform = 'translateY(15px)';
    el.style.transition = `opacity 0.4s ${i * 0.07}s, transform 0.4s ${i * 0.07}s`;
    observer.observe(el);
  });

  const langObserver = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.querySelectorAll('.lang-bar-fill').forEach(b => b.classList.add('animate')); }
    });
  }, { threshold: 0.3 });
  document.querySelectorAll('#about .info-item').forEach(el => langObserver.observe(el));
</script>
</body>
</html>
