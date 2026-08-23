<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ANKIT DUTT — AI/ML Student</title>
<meta name="description" content="Portfolio of ANKIT DUTT, B.Tech AI/ML student.">

<!-- ============================================================
     HOW TO CUSTOMIZE THIS FILE — read this first
     1. Search for "EDIT:" comments — every one marks something
        you should personalize (name, links, project text, etc.)
     2. Your name / role / tagline are set in the HERO section.
     3. Projects, skills, and experience are plain HTML lists —
        copy a block and edit it to add more entries.
     4. Colors and fonts are defined once at the top of the CSS,
        under ":root" — change them there and they update everywhere.
     5. Replace the placeholder photo circle in the hero (search
        "profile-photo") with an <img> tag if you want a headshot.
     ============================================================ -->

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<!-- Devicon: gives each skill tag a real language/tool icon -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/devicon/2.15.1/devicon.min.css">

<style>
  :root {
    /* ---- EDIT: palette ---- */
    --paper:      #FAFAF6;
    --paper-dim:  #F2F1EA;
    --ink:        #16171D;
    --ink-soft:   #52545E;
    --line:       #DEDDD2;
    --accent:     #2D4FFF;   /* electric blue — links, highlights */
    --accent-2:   #FF6A3D;   /* warm coral — tags, small marks */
    --accent-soft:#E7EBFF;

    /* ---- type scale ---- */
    --display: 'Space Grotesk', sans-serif;
    --body:    'Inter', sans-serif;
    --mono:    'JetBrains Mono', monospace;
  }

  * { margin:0; padding:0; box-sizing:border-box; }

  html { scroll-behavior:smooth; }

  body {
    background:
      linear-gradient(var(--paper) 1px, transparent 1px) 0 0/100% 32px,
      linear-gradient(90deg, var(--paper) 1px, transparent 1px) 0 0/32px 100%,
      var(--paper-dim);
    background-color: var(--paper);
    background-image:
      linear-gradient(var(--line) 1px, transparent 1px),
      linear-gradient(90deg, var(--line) 1px, transparent 1px);
    background-size: 32px 32px;
    color: var(--ink);
    font-family: var(--body);
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
    animation: gridDrift 50s linear infinite;
  }

  /* Grid paper slowly panning — barely perceptible, keeps the page feeling "on" */
  @keyframes gridDrift {
    from { background-position: 0 0, 0 0, 0 0; }
    to   { background-position: 0 0, 0 0, 320px 320px; }
  }

  a { color: inherit; text-decoration: none; }
  ::selection { background: var(--accent); color: var(--paper); }

  /* ---------------- ambient background orbs ---------------- */
  .bg-orbs {
    position: fixed; inset: 0; z-index: -1;
    overflow: hidden; pointer-events: none;
  }
  .orb {
    position: absolute; border-radius: 50%;
    filter: blur(70px); opacity: 0.28; mix-blend-mode: multiply;
  }
  .orb-a {
    width: 420px; height: 420px; top: -120px; left: -100px;
    background: var(--accent);
    animation: driftA 26s ease-in-out infinite alternate;
  }
  .orb-b {
    width: 380px; height: 380px; bottom: -140px; right: -80px;
    background: var(--accent-2);
    animation: driftB 32s ease-in-out infinite alternate;
  }
  @keyframes driftA {
    from { transform: translate(0, 0) scale(1); }
    to   { transform: translate(70px, 90px) scale(1.15); }
  }
  @keyframes driftB {
    from { transform: translate(0, 0) scale(1); }
    to   { transform: translate(-60px, -70px) scale(1.1); }
  }

  .wrap {
    max-width: 920px;
    margin: 0 auto;
    padding: 0 28px;
  }

  /* ---------------- focus visibility ---------------- */
  a:focus-visible, button:focus-visible {
    outline: 2px solid var(--accent);
    outline-offset: 3px;
  }

  /* ---------------- NAV ---------------- */
  header {
    position: sticky; top: 0; z-index: 50;
    background: rgba(250,250,246,0.88);
    backdrop-filter: blur(6px);
    border-bottom: 1px solid var(--line);
  }
  nav.wrap {
    display:flex; align-items:center; justify-content:space-between;
    height: 64px;
  }
  .logo {
    font-family: var(--mono); font-weight:600; font-size:0.95rem;
    letter-spacing:0.02em;
  }
  .logo span { color: var(--accent); }
  .nav-links { display:flex; gap:28px; font-family:var(--mono); font-size:0.85rem; }
  .nav-links a { color: var(--ink-soft); position:relative; padding:4px 0; }
  .nav-links a:hover { color: var(--ink); }
  .nav-links a::after {
    content:""; position:absolute; left:0; bottom:0; width:0; height:1px;
    background:var(--accent); transition:width .2s ease;
  }
  .nav-links a:hover::after { width:100%; }
  .nav-toggle { display:none; }

  /* ---------------- HERO ---------------- */
  .hero { padding: 96px 0 72px; }
  .eyebrow {
    font-family: var(--mono); font-size:0.85rem; color: var(--ink-soft);
    display:flex; align-items:center; gap:10px; margin-bottom:22px;
  }
  .eyebrow .dot {
    width:8px; height:8px; border-radius:50%; background:#2FBF71;
    box-shadow: 0 0 0 3px #2FBF7122;
  }

  .terminal {
    font-family: var(--mono); font-size:1rem; color: var(--ink-soft);
    margin-bottom: 18px; min-height: 1.4em;
  }
  .terminal .prompt { color: var(--accent-2); }
  .terminal .caret {
    display:inline-block; width:8px; height:1.1em; background:var(--ink);
    margin-left:2px; vertical-align:-2px;
    animation: blink 1s steps(1) infinite;
  }
  @keyframes blink { 50% { opacity:0; } }

  h1.name {
    font-family: var(--display); font-weight:700;
    font-size: clamp(2.6rem, 6vw, 4.4rem);
    line-height: 1.02; letter-spacing:-0.02em;
    margin-bottom: 14px;
  }
  .role {
    font-family: var(--display); font-weight:500;
    font-size: clamp(1.1rem, 2.4vw, 1.5rem);
    color: var(--accent);
    margin-bottom: 22px;
  }
  .tagline {
    max-width: 560px; color: var(--ink-soft); font-size:1.05rem;
    margin-bottom: 34px;
  }
  .hero-cta { display:flex; gap:14px; flex-wrap:wrap; }
  .btn {
    font-family: var(--mono); font-size:0.9rem;
    padding: 12px 22px; border-radius: 3px;
    border: 1.5px solid var(--ink);
    transition: transform .15s ease, background .15s ease, color .15s ease;
    display:inline-flex; align-items:center; gap:8px;
  }
  .btn.primary { background: var(--ink); color: var(--paper); }
  .btn.primary:hover { background: var(--accent); border-color:var(--accent); transform:translateY(-2px); }
  .btn.ghost:hover { background: var(--ink); color: var(--paper); transform:translateY(-2px); }

  /* ---------------- SECTION shell ---------------- */
  section { padding: 68px 0; border-top: 1px solid var(--line); }
  .section-head {
    display:flex; align-items:baseline; gap:14px; margin-bottom:40px;
  }
  .section-num { font-family:var(--mono); color:var(--accent-2); font-size:0.9rem; }
  .section-title {
    font-family: var(--display); font-weight:600;
    font-size: clamp(1.5rem, 3vw, 2rem);
  }

  .reveal { opacity:0; transform: translateY(18px); transition: opacity .6s ease, transform .6s ease; }
  .reveal.in { opacity:1; transform:none; }

  /* ---------------- ABOUT ---------------- */
  .about-grid {
    display:grid; grid-template-columns: 1.3fr 1fr; gap:48px;
  }
  .about-text p { color: var(--ink-soft); margin-bottom:14px; max-width:56ch; }
  .about-text strong { color: var(--ink); font-weight:600; }

  .fact-list { font-family: var(--mono); font-size:0.88rem; }
  .fact-list div { display:flex; justify-content:space-between; padding:10px 0; border-bottom:1px dashed var(--line); gap:12px; }
  .fact-list span:first-child { color: var(--ink-soft); }
  .fact-list span:last-child { text-align:right; }

  /* ---------------- SKILLS ---------------- */
  .skill-groups { display:grid; grid-template-columns: repeat(3, 1fr); gap:28px; }
  .skill-group h3 {
    font-family: var(--mono); font-size:0.82rem; text-transform:uppercase;
    letter-spacing:0.08em; color: var(--ink-soft); margin-bottom:14px;
  }
  .tag-row { display:flex; flex-wrap:wrap; gap:8px; }
  .tag {
    font-family: var(--mono); font-size:0.82rem;
    padding: 7px 13px 7px 10px; border:1px solid var(--line); border-radius:3px;
    background: var(--paper); transition: border-color .15s ease, color .15s ease, transform .15s ease;
    display:inline-flex; align-items:center; gap:7px;
  }
  .tag i { font-size:1rem; }
  .tag:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

  /* ---------------- PROJECTS ---------------- */
  .project-list { display:flex; flex-direction:column; gap:1px; background:var(--line); border:1px solid var(--line); }
  .project {
    background: var(--paper); padding: 26px 26px; display:grid;
    grid-template-columns: 120px 1fr; gap: 22px;
    transition: background .15s ease;
  }
  .project:hover { background: var(--paper-dim); }
  .project-meta { font-family: var(--mono); font-size:0.78rem; color: var(--ink-soft); }
  .project-meta .hash { color: var(--accent-2); display:block; margin-bottom:6px; }
  .project-title {
    font-family: var(--display); font-weight:600; font-size:1.2rem; margin-bottom:8px;
    display:flex; align-items:center; gap:10px;
  }
  .project-title a:hover { color: var(--accent); }
  .project-desc { color: var(--ink-soft); font-size:0.95rem; margin-bottom:12px; max-width:60ch; }
  .project-stack { display:flex; gap:8px; flex-wrap:wrap; }
  .project-stack span {
    font-family:var(--mono); font-size:0.74rem; color:var(--accent);
    background: var(--accent-soft); padding:3px 9px; border-radius:2px;
  }
  .project-links { margin-top:12px; display:flex; gap:16px; font-family:var(--mono); font-size:0.8rem; }
  .project-links a { color: var(--ink); border-bottom:1px solid var(--ink); }
  .project-links a:hover { color: var(--accent); border-color: var(--accent); }

  /* ---------------- CERTIFICATIONS ---------------- */
  .cert-list { display:flex; flex-direction:column; gap:1px; background:var(--line); border:1px solid var(--line); }
  .cert-card {
    background: var(--paper); padding: 22px 26px; display:flex;
    align-items:center; gap: 22px; transition: background .15s ease;
  }
  .cert-card:hover { background: var(--paper-dim); }
  .cert-badge {
    flex-shrink:0; width:52px; height:52px; border-radius:50%;
    border:2px dashed var(--accent-2); color:var(--accent-2);
    display:flex; align-items:center; justify-content:center;
    transform: rotate(-8deg); background: var(--paper);
  }
  .cert-body { flex:1; min-width:0; }
  .cert-title { font-family: var(--display); font-weight:600; font-size:1.05rem; }
  .cert-meta {
    font-family: var(--mono); font-size:0.8rem; color: var(--ink-soft);
    margin-top:4px; display:flex; gap:10px; flex-wrap:wrap;
  }
  .cert-link {
    font-family: var(--mono); font-size:0.8rem; color: var(--ink);
    border-bottom:1px solid var(--ink); white-space:nowrap; flex-shrink:0;
  }
  .cert-link:hover { color: var(--accent); border-color: var(--accent); }
  @media (max-width: 560px) {
    .cert-card { flex-wrap:wrap; }
  }

  /* ---------------- CONTACT / FOOTER ---------------- */
  footer { padding: 64px 0 48px; }
  .contact-box {
    border: 1.5px solid var(--ink); border-radius:4px; padding: 44px 36px;
    display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:24px;
    background: var(--paper);
  }
  .contact-box h2 {
    font-family: var(--display); font-weight:600;
    font-size: clamp(1.5rem, 3.4vw, 2.2rem); max-width: 480px;
  }
  .contact-links { display:flex; flex-direction:column; gap:10px; font-family:var(--mono); font-size:0.92rem; }
  .contact-links a { display:flex; align-items:center; gap:8px; }
  .contact-links a:hover { color: var(--accent); }
  .foot-note {
    text-align:center; font-family:var(--mono); font-size:0.78rem; color:var(--ink-soft);
    margin-top: 36px;
  }

  /* ---------------- responsive ---------------- */
  @media (max-width: 760px) {
    .nav-links { display:none; }
    .about-grid { grid-template-columns:1fr; }
    .skill-groups { grid-template-columns:1fr 1fr; }
    .project { grid-template-columns:1fr; }
    .contact-box { flex-direction:column; align-items:flex-start; }
  }
  @media (max-width: 480px) {
    .skill-groups { grid-template-columns:1fr; }
  }

  @media (prefers-reduced-motion: reduce) {
    * { animation-duration:0.01ms !important; transition-duration:0.01ms !important; scroll-behavior:auto !important; }
    body, .orb { animation: none !important; }
  }
</style>
</head>
<body>

<!-- Ambient drifting color — purely decorative, ignored by screen readers -->
<div class="bg-orbs" aria-hidden="true">
  <div class="orb orb-a"></div>
  <div class="orb orb-b"></div>
</div>

<header>
  <nav class="wrap">
    <!-- 🔴 EDIT HERE — YOUR NAME / PORTFOLIO LOGO -->
    <div class="logo">ANKIT DUTT<span>.dev</span></div>
    <div class="nav-links">
      <a href="#about">about</a>
      <a href="#skills">skills</a>
      <a href="#projects">projects</a>
      <a href="#certifications">certifications</a>
      <a href="#contact">contact</a>
    </div>
  </nav>
</header>

<main>
  <!-- ================= HERO ================= -->
  <section class="hero wrap" style="border-top:none;">
    <!-- 🔴 EDIT HERE — YOUR CURRENT STATUS -->
    <div class="eyebrow"><span class="dot"></span> AI/ML Student · Open to Opportunities</div>
    <div class="terminal">
      <span class="prompt">&gt;</span> <span id="typed"></span><span class="caret"></span>
    </div>
    <!-- 🔴 EDIT HERE — YOUR FULL NAME -->
    <h1 class="name">ANKIT DUTT</h1>
    <!-- 🔴 EDIT HERE — YOUR DEGREE / SPECIALIZATION / GRADUATION YEAR -->
    <div class="role">B.Tech Artificial Intelligence &amp; Machine Learning, 2029</div>
    <!-- 🔴 EDIT HERE — SHORT PROFESSIONAL INTRODUCTION -->
    <p class="tagline">
      I am a second-year AI/ML student interested in machine learning,
      computer vision, and building practical AI systems that solve real-world problems.
    </p>
    <div class="hero-cta">
      <!-- 🔴 EDIT HERE — REPLACE # WITH YOUR RESUME PDF LINK/PATH -->
    <a href="#" class="btn primary">↓ Download resume</a>
      <a href="#projects" class="btn ghost">View projects</a>
    </div>
  </section>

  <!-- ================= ABOUT ================= -->
  <section id="about" class="wrap">
    <div class="section-head">
      <span class="section-num">01</span>
      <h2 class="section-title">About</h2>
    </div>
    <div class="about-grid reveal">
      <div class="about-text">
        <!-- 🔴 EDIT HERE — ABOUT YOURSELF -->
        <p>
          I'm a second-year B.Tech student specializing in Artificial Intelligence
          and Machine Learning at <strong>Lovely Professional University</strong>. I am currently
          building my foundation in programming, machine learning, data structures,
          and problem-solving.
        </p>
        <p>
          I enjoy learning by building practical projects and exploring how AI can
          be applied to real-world problems. My current interests include machine
          learning, computer vision, and AI-based systems.
        </p>
      </div>
      <div class="fact-list">
        <!-- 🔴 EDIT HERE — YOUR CITY / COUNTRY -->
        <div><span>Location</span><span>Haryana, India</span></div>
        <!-- 🔴 EDIT HERE — YOUR COLLEGE AND GRADUATION YEAR -->
        <div><span>Education</span><span>Lovely Professional University, 2029</span></div>
        <!-- 🔴 EDIT HERE — YOUR CGPA (REMOVE THIS ROW IF YOU DO NOT WANT TO SHOW IT) -->
        <div><span>CGPA</span><span>[8.33 / 10]</span></div>
        <div><span>Focus</span><span>AI / Machine Learning</span></div>
        <!-- 🔴 EDIT HERE — YOUR PROGRAMMING LANGUAGES -->
        <div><span>Languages</span><span>C++, Python</span></div>
        <!-- 🔴 EDIT HERE — WHAT YOU ARE CURRENTLY LEARNING -->
        <div><span>Currently</span><span>Learning Machine Learning &amp; Computer Vision</span></div>
      </div>
    </div>
  </section>

  <!-- ================= SKILLS ================= -->
  <section id="skills" class="wrap">
    <div class="section-head">
      <span class="section-num">02</span>
      <h2 class="section-title">Skills</h2>
    </div>
    <div class="skill-groups reveal">
      <!-- 🔴 EDIT HERE — PROGRAMMING LANGUAGES YOU ACTUALLY KNOW -->
      <div class="skill-group">
        <h3>Programming</h3>
        <div class="tag-row">
          <span class="tag"><i class="devicon-c-plain colored"></i>C</span>
          <span class="tag"><i class="devicon-cplusplus-plain colored"></i>C++</span>
          <span class="tag"><i class="devicon-python-plain colored"></i>Python</span>
          <!-- 🔴 ADD / REMOVE SKILLS HERE — find matching icon names at devicon.dev -->
        </div>
      </div>
      <!-- 🔴 EDIT HERE — AI/ML TOOLS AND LIBRARIES -->
      <div class="skill-group">
        <h3>AI / ML</h3>
        <div class="tag-row">
          <span class="tag"><i class="devicon-opencv-plain colored"></i>OpenCV</span>
          <span class="tag"><i class="devicon-tensorflow-original colored"></i>TensorFlow</span>
          <span class="tag"><svg viewBox="0 0 24 24" width="14" height="14" fill="none" stroke="currentColor" stroke-width="2"><rect x="4" y="4" width="16" height="16" rx="2"/><path d="M9 2v2M15 2v2M9 20v2M15 20v2M2 9h2M2 15h2M20 9h2M20 15h2"/></svg>Machine Learning</span>
          <span class="tag"><svg viewBox="0 0 24 24" width="14" height="14" fill="none" stroke="currentColor" stroke-width="2"><path d="M1 12s4-7 11-7 11 7 11 7-4 7-11 7-11-7-11-7z"/><circle cx="12" cy="12" r="3"/></svg>Computer Vision</span>
          <!-- 🔴 ADD / REMOVE SKILLS HERE -->
        </div>
      </div>
      <!-- 🔴 EDIT HERE — OTHER TECHNICAL SKILLS -->
      <div class="skill-group">
        <h3>Core &amp; Tools</h3>
        <div class="tag-row">
          <span class="tag"><svg viewBox="0 0 24 24" width="14" height="14" fill="none" stroke="currentColor" stroke-width="2"><circle cx="5" cy="6" r="2"/><circle cx="19" cy="6" r="2"/><circle cx="12" cy="18" r="2"/><path d="M5 8l7 8M19 8l-7 8"/></svg>Data Structures</span>
          <span class="tag"><i class="devicon-git-plain colored"></i>Git</span>
          <span class="tag"><i class="devicon-arduino-plain colored"></i>Arduino / ESP32</span>
          <span class="tag"><i class="devicon-github-original"></i>GitHub</span>
          <span class="tag"><svg viewBox="0 0 24 24" width="14" height="14" fill="currentColor"><path d="M12 2l1.6 6.4L20 10l-6.4 1.6L12 18l-1.6-6.4L4 10l6.4-1.6L12 2z"/></svg>Claude</span>
          <!-- 🔴 ADD / REMOVE SKILLS HERE -->
        </div>
      </div>
    </div>
  </section>

  <!-- ================= PROJECTS ================= -->
  <section id="projects" class="wrap">
    <div class="section-head">
      <span class="section-num">03</span>
      <h2 class="section-title">Projects</h2>
    </div>
    <div class="project-list reveal">

      <!-- 🔴 EDIT HERE — PROJECT YEAR -->
      <article class="project">
        <div class="project-meta">
          <!-- 🔴 EDIT HERE — OPTIONAL PROJECT IDENTIFIER -->
          <span class="hash">#water-ai</span>
          2026
        </div>
        <div>
          <!-- 🔴 EDIT HERE — PROJECT TITLE -->
          <div class="project-title"><a href="#">AI-Based Water Analysis System</a></div>
          <p class="project-desc">
            An AI-based water analysis system designed to detect microplastic particles
            and analyze water quality using computer vision. The system uses a camera
            for image input, processes the captured data with AI/ML techniques, and
            provides the analysis result through the connected hardware/output system 
            and alert the user by showing the red light if the water is unsafe.
          </p>
          <div class="project-stack">
            <!-- 🔴 EDIT HERE — ADD / REMOVE TECHNOLOGIES USED IN YOUR PROJECT -->
            <span>Python</span><span>OpenCV</span><span>TensorFlow</span>
            <span>Computer Vision</span><span>ESP32</span><span>LCD</span>
          </div>
          <div class="project-links">
            <!-- 🔴 EDIT HERE — REPLACE # WITH YOUR GITHUB LINK -->
            <a href="#">Source →</a>
            <!-- 🔴 EDIT HERE — ADD A LIVE DEMO LINK IF AVAILABLE -->
            <a href="#">Demo →</a>
          </div>
        </div>
      </article>

      <!-- 🔴 OPTIONAL — COPY THE PROJECT BLOCK ABOVE TO ADD ANOTHER PROJECT -->

    </div>
  </section>

  <!-- ================= CERTIFICATIONS ================= -->
  <section id="certifications" class="wrap">
    <div class="section-head">
      <span class="section-num">04</span>
      <h2 class="section-title">Certifications</h2>
    </div>
    <div class="cert-list reveal">

      <!-- 🔴 EDIT HERE — duplicate this .cert-card block for each certificate -->
      <article class="cert-card">
        <div class="cert-badge" aria-hidden="true">
          <svg viewBox="0 0 24 24" width="22" height="22" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round">
            <polyline points="4 12 9 17 20 6"/>
          </svg>
        </div>
        <div class="cert-body">
          <!-- 🔴 EDIT HERE — CERTIFICATE NAME -->
          <div class="cert-title">Introduction to AI</div>
          <!-- 🔴 EDIT HERE — ISSUER AND DATE -->
          <div class="cert-meta"><span>Infosys springboard ·AI</span><span>Issued 2026</span></div>
        </div>
        <!-- 🔴 EDIT HERE — REPLACE # WITH YOUR CREDENTIAL VERIFY LINK -->
        <a href="#" class="https://infyspringboard.onwingspan.com/public-assets/infosysheadstart/cert/lex_3388902307073574000_shared/6f2ad04f-8058-41ef-9f2d-de666af08b2f.pdf">Verify →</a>
      </article>

      <article class="cert-card">
        <div class="cert-badge" aria-hidden="true">
          <svg viewBox="0 0 24 24" width="22" height="22" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round">
            <polyline points="4 12 9 17 20 6"/>
          </svg>
        </div>
        <div class="cert-body">
          <div class="cert-title">Python for Data Science, AI &amp; Development</div>
          <div class="cert-meta"><span>IBM · Coursera</span><span>Issued 2025</span></div>
        </div>
        <a href="#" class="cert-link">Verify →</a>
      </article>

      <article class="cert-card">
        <div class="cert-badge" aria-hidden="true">
          <svg viewBox="0 0 24 24" width="22" height="22" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round">
            <polyline points="4 12 9 17 20 6"/>
          </svg>
        </div>
        <div class="cert-body">
          <div class="cert-title">Introduction to Computer Vision</div>
          <div class="cert-meta"><span>NPTEL</span><span>Issued 2025</span></div>
        </div>
        <a href="#" class="cert-link">Verify →</a>
      </article>

      <!-- 🔴 OPTIONAL — COPY A .cert-card BLOCK ABOVE TO ADD MORE CERTIFICATES -->

    </div>
  </section>

  <!-- ================= CONTACT ================= -->
  <footer id="contact" class="wrap">
    <div class="contact-box reveal">
      <!-- 🔴 EDIT HERE — YOUR CONTACT MESSAGE -->
      <h2>Interested in AI, machine learning, or building something together? Let's connect.</h2>
      <div class="contact-links">
        <!-- 🔴 EDIT HERE — YOUR EMAIL ADDRESS -->
        <a href="mailto:your.email@example.com">✉ your.email@example.com</a>
        <!-- 🔴 EDIT HERE — YOUR GITHUB URL AND DISPLAY TEXT -->
        <a href="#">↗ github.com/yourhandle</a>
        <!-- 🔴 EDIT HERE — YOUR LINKEDIN URL AND DISPLAY TEXT -->
        <a href="#">↗ linkedin.com/in/yourhandle</a>
      </div>
    </div>
    <!-- 🔴 EDIT HERE — YOUR NAME AND LAST UPDATED DATE -->
    <p class="foot-note">Built by ANKIT DUTT · Last updated August 2026</p>
  </footer>
</main>

<script>
  // ---- Hero terminal typing effect ----
  const phrases = ["whoami", "cat interests.txt", "python ai_water.py"];
  const typedEl = document.getElementById('typed');
  const reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

  if (reduceMotion) {
    typedEl.textContent = phrases[0];
  } else {
    let phraseIndex = 0, charIndex = 0, deleting = false;
    function tick() {
      const current = phrases[phraseIndex];
      if (!deleting) {
        charIndex++;
        typedEl.textContent = current.slice(0, charIndex);
        if (charIndex === current.length) {
          deleting = true;
          setTimeout(tick, 1400);
          return;
        }
      } else {
        charIndex--;
        typedEl.textContent = current.slice(0, charIndex);
        if (charIndex === 0) {
          deleting = false;
          phraseIndex = (phraseIndex + 1) % phrases.length;
        }
      }
      setTimeout(tick, deleting ? 35 : 55);
    }
    tick();
  }

  // ---- Scroll reveal ----
  const revealEls = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('in'); });
  }, { threshold: 0.15 });
  revealEls.forEach(el => io.observe(el));
</script>

</body>
</html>
