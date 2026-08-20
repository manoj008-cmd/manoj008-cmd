<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Manoj Kumar — Full-Stack Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg:        #0d0d0f;
    --surface:   #13131a;
    --surface2:  #1a1a24;
    --border:    #2a2a3a;
    --lavender:  #b4befe;
    --peach:     #fab387;
    --green:     #a6e3a1;
    --sky:       #89dceb;
    --blue:      #89b4fa;
    --text:      #cdd6f4;
    --muted:     #6c7086;
    --subtext:   #a6adc8;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Inter', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    font-size: 15px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── Animations ─────────────────────────────────────── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(22px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes pulse-dot {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }
  @keyframes gradient-shift {
    0%   { background-position: 0% 50%; }
    50%  { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }
  @keyframes slide-in-left {
    from { opacity: 0; transform: translateX(-16px); }
    to   { opacity: 1; transform: translateX(0); }
  }

  .fade-up { animation: fadeUp 0.6s ease both; }
  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .delay-4 { animation-delay: 0.4s; }
  .delay-5 { animation-delay: 0.5s; }
  .delay-6 { animation-delay: 0.6s; }

  /* ── Layout ─────────────────────────────────────────── */
  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 0 28px;
  }

  section { padding: 72px 0; }

  .section-label {
    font-family: var(--mono);
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--lavender);
    margin-bottom: 10px;
    opacity: 0.8;
  }

  .section-title {
    font-size: 26px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 40px;
    letter-spacing: -0.02em;
  }

  hr.divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 0;
  }

  /* ── Hero ───────────────────────────────────────────── */
  #hero {
    padding: 100px 0 80px;
    position: relative;
    overflow: hidden;
  }

  #hero::before {
    content: '';
    position: absolute;
    top: -200px; right: -200px;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(180,190,254,0.07) 0%, transparent 65%);
    pointer-events: none;
  }

  .hero-status {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: var(--mono);
    font-size: 12px;
    color: var(--green);
    background: rgba(166,227,161,0.08);
    border: 1px solid rgba(166,227,161,0.2);
    padding: 5px 14px;
    border-radius: 100px;
    margin-bottom: 28px;
  }
  .status-dot {
    width: 6px; height: 6px;
    background: var(--green);
    border-radius: 50%;
    animation: pulse-dot 1.8s ease-in-out infinite;
  }

  .hero-name {
    font-size: clamp(38px, 6vw, 58px);
    font-weight: 700;
    letter-spacing: -0.03em;
    line-height: 1.1;
    color: var(--text);
    margin-bottom: 8px;
  }
  .hero-name span {
    background: linear-gradient(135deg, var(--lavender) 0%, var(--peach) 100%);
    background-size: 200% 200%;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: gradient-shift 5s ease infinite;
  }

  .hero-role {
    font-size: 17px;
    font-weight: 400;
    color: var(--subtext);
    margin-bottom: 28px;
  }
  .hero-role strong {
    color: var(--text);
    font-weight: 500;
  }

  /* Terminal block */
  .terminal {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 36px;
    font-family: var(--mono);
    font-size: 13px;
  }
  .terminal-bar {
    background: var(--surface2);
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    border-bottom: 1px solid var(--border);
  }
  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-r { background: #f38ba8; }
  .dot-y { background: #f9e2af; }
  .dot-g { background: var(--green); }
  .terminal-title {
    flex: 1;
    text-align: center;
    font-size: 11px;
    color: var(--muted);
  }
  .terminal-body { padding: 20px 22px; line-height: 2; }
  .t-prompt { color: var(--lavender); }
  .t-cmd { color: var(--text); }
  .t-key { color: var(--muted); }
  .t-val { color: var(--peach); }
  .t-str { color: var(--green); }
  .t-com { color: var(--muted); font-style: italic; }
  .cursor {
    display: inline-block;
    width: 8px; height: 13px;
    background: var(--lavender);
    vertical-align: middle;
    animation: blink 1s step-end infinite;
  }

  /* Social links */
  .hero-links { display: flex; gap: 12px; flex-wrap: wrap; }
  .hero-link {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 9px 18px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 500;
    text-decoration: none;
    border: 1px solid var(--border);
    color: var(--subtext);
    background: var(--surface);
    transition: border-color 0.2s, color 0.2s, background 0.2s;
    font-family: var(--mono);
  }
  .hero-link:hover { border-color: var(--lavender); color: var(--lavender); background: rgba(180,190,254,0.06); }
  .hero-link.primary { background: var(--lavender); color: #1e1e2e; border-color: var(--lavender); font-weight: 600; }
  .hero-link.primary:hover { background: #cdd6f4; border-color: #cdd6f4; color: #1e1e2e; }

  /* ── What I Build ───────────────────────────────────── */
  .pillars { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }

  @media (max-width: 640px) { .pillars { grid-template-columns: 1fr; } }

  .pillar {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px 22px;
    transition: border-color 0.25s, transform 0.25s;
  }
  .pillar:hover { border-color: var(--lavender); transform: translateY(-3px); }

  .pillar-icon {
    font-size: 22px;
    margin-bottom: 12px;
    display: block;
  }
  .pillar h3 {
    font-size: 14px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 12px;
    letter-spacing: -0.01em;
  }
  .pillar ul { list-style: none; }
  .pillar ul li {
    font-size: 12.5px;
    color: var(--subtext);
    padding: 3px 0;
    display: flex;
    align-items: flex-start;
    gap: 8px;
  }
  .pillar ul li::before { content: '—'; color: var(--border); flex-shrink: 0; margin-top: 1px; }

  /* ── Projects ───────────────────────────────────────── */
  .projects { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  @media (max-width: 640px) { .projects { grid-template-columns: 1fr; } }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    display: flex;
    flex-direction: column;
    gap: 12px;
    transition: border-color 0.25s, transform 0.25s;
    position: relative;
    overflow: hidden;
  }
  .project-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(180,190,254,0.03) 0%, transparent 60%);
    pointer-events: none;
  }
  .project-card:hover { border-color: var(--lavender); transform: translateY(-2px); }
  .project-card.featured { grid-column: 1 / -1; }

  .project-header { display: flex; align-items: flex-start; justify-content: space-between; gap: 12px; }
  .project-icon { font-size: 20px; }
  .project-links { display: flex; gap: 8px; flex-shrink: 0; }
  .project-link {
    font-family: var(--mono);
    font-size: 10px;
    font-weight: 500;
    padding: 4px 10px;
    border-radius: 6px;
    text-decoration: none;
    border: 1px solid var(--border);
    color: var(--subtext);
    transition: border-color 0.2s, color 0.2s;
    letter-spacing: 0.03em;
  }
  .project-link:hover { border-color: var(--green); color: var(--green); }
  .project-link.live:hover { border-color: var(--sky); color: var(--sky); }

  .project-name {
    font-size: 16px;
    font-weight: 600;
    color: var(--text);
    letter-spacing: -0.01em;
  }
  .project-subtitle {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    margin-top: 2px;
  }
  .project-desc {
    font-size: 13px;
    color: var(--subtext);
    line-height: 1.65;
  }
  .project-tags { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag {
    font-family: var(--mono);
    font-size: 10.5px;
    padding: 3px 9px;
    border-radius: 5px;
    background: rgba(180,190,254,0.08);
    color: var(--lavender);
    border: 1px solid rgba(180,190,254,0.15);
  }

  /* ── Tech Stack ─────────────────────────────────────── */
  .stack-group { margin-bottom: 28px; }
  .stack-group:last-child { margin-bottom: 0; }
  .stack-group-label {
    font-family: var(--mono);
    font-size: 10.5px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 12px;
  }
  .stack-pills { display: flex; flex-wrap: wrap; gap: 8px; }
  .pill {
    display: flex;
    align-items: center;
    gap: 7px;
    font-size: 12.5px;
    font-weight: 500;
    padding: 7px 14px;
    border-radius: 8px;
    background: var(--surface);
    border: 1px solid var(--border);
    color: var(--subtext);
    transition: border-color 0.2s, color 0.2s;
    cursor: default;
  }
  .pill:hover { border-color: var(--lavender); color: var(--text); }
  .pill-dot {
    width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0;
  }

  /* ── Achievements ───────────────────────────────────── */
  .achievements { display: flex; flex-direction: column; gap: 12px; }
  .achievement {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 22px;
    transition: border-color 0.25s;
  }
  .achievement:hover { border-color: var(--peach); }

  .achievement-medal {
    font-size: 22px;
    flex-shrink: 0;
    margin-top: 2px;
  }
  .achievement-content {}
  .achievement-name {
    font-size: 14px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 3px;
  }
  .achievement-meta {
    font-size: 12.5px;
    color: var(--muted);
    font-family: var(--mono);
  }

  /* ── Internship ─────────────────────────────────────── */
  .experience-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 26px;
    display: flex;
    gap: 20px;
  }
  .exp-timeline {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0;
  }
  .exp-dot {
    width: 10px; height: 10px;
    background: var(--lavender);
    border-radius: 50%;
    flex-shrink: 0;
    margin-top: 5px;
  }
  .exp-line {
    width: 1px;
    flex: 1;
    background: var(--border);
    margin-top: 6px;
  }
  .exp-title {
    font-size: 15px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 3px;
  }
  .exp-org {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--lavender);
    margin-bottom: 10px;
  }
  .exp-period {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    margin-bottom: 12px;
  }
  .exp-bullets { list-style: none; }
  .exp-bullets li {
    font-size: 13px;
    color: var(--subtext);
    padding: 3px 0;
    display: flex;
    gap: 10px;
    align-items: flex-start;
  }
  .exp-bullets li::before {
    content: '▸';
    color: var(--lavender);
    flex-shrink: 0;
  }

  /* ── CTA Footer ─────────────────────────────────────── */
  #cta {
    padding: 80px 0;
    text-align: center;
  }
  .cta-inner {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 52px 40px;
    position: relative;
    overflow: hidden;
  }
  .cta-inner::before {
    content: '';
    position: absolute;
    bottom: -80px; right: -80px;
    width: 300px; height: 300px;
    background: radial-gradient(circle, rgba(250,179,135,0.07) 0%, transparent 65%);
    pointer-events: none;
  }
  .cta-inner::after {
    content: '';
    position: absolute;
    top: -80px; left: -80px;
    width: 300px; height: 300px;
    background: radial-gradient(circle, rgba(180,190,254,0.07) 0%, transparent 65%);
    pointer-events: none;
  }
  .cta-eyebrow {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--lavender);
    margin-bottom: 14px;
  }
  .cta-title {
    font-size: 28px;
    font-weight: 700;
    letter-spacing: -0.025em;
    color: var(--text);
    margin-bottom: 10px;
  }
  .cta-sub {
    font-size: 14px;
    color: var(--subtext);
    max-width: 400px;
    margin: 0 auto 30px;
  }
  .cta-links { display: flex; justify-content: center; gap: 12px; flex-wrap: wrap; }

  /* ── Scroll reveal ─────────────────────────────────── */
  .reveal {
    opacity: 0;
    transform: translateY(18px);
    transition: opacity 0.55s ease, transform 0.55s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: none;
  }
</style>
</head>
<body>

<!-- ── HERO ────────────────────────────────────────── -->
<section id="hero">
  <div class="container">
    <div class="hero-status fade-up">
      <span class="status-dot"></span>
      Open to SWE Roles &amp; Internships
    </div>

    <h1 class="hero-name fade-up delay-1">
      Manoj<br/><span>Kumar.</span>
    </h1>

    <p class="hero-role fade-up delay-2">
      <strong>Full-Stack Engineer</strong> · Java Spring Boot · React.js · AI &amp; Cybersecurity<br/>
      B.E. Computer Science @ SMVITM Bantakal · CGPA 8.0
    </p>

    <div class="terminal fade-up delay-3">
      <div class="terminal-bar">
        <span class="dot dot-r"></span>
        <span class="dot dot-y"></span>
        <span class="dot dot-g"></span>
        <span class="terminal-title">~/manoj-kumar — zsh</span>
      </div>
      <div class="terminal-body">
        <div><span class="t-prompt">❯</span> <span class="t-cmd">cat whoami.yaml</span></div>
        <div><span class="t-key">name</span><span class="t-com">:</span>        <span class="t-str">"Manoj Kumar"</span></div>
        <div><span class="t-key">stack</span><span class="t-com">:</span>       <span class="t-val">[ Java 17, Spring Boot, React.js, TypeScript, FastAPI ]</span></div>
        <div><span class="t-key">databases</span><span class="t-com">:</span>   <span class="t-val">[ MongoDB Atlas, PostgreSQL, MySQL ]</span></div>
        <div><span class="t-key">experience</span><span class="t-com">:</span>  <span class="t-str">"Java Dev Intern @ TechnoHacks Solutions (Jul–Aug 2025)"</span></div>
        <div><span class="t-key">location</span><span class="t-com">:</span>    <span class="t-str">"Karnataka, India 🇮🇳"</span></div>
        <div><span class="t-key">status</span><span class="t-com">:</span>      <span class="t-str">"available"</span>  <span class="t-com"># for full-time &amp; internships</span></div>
        <div style="margin-top:8px"><span class="t-prompt">❯</span> <span class="cursor"></span></div>
      </div>
    </div>

    <div class="hero-links fade-up delay-4">
      <a href="https://linkedin.com/in/manoj-kumar" class="hero-link primary" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="https://github.com/manoj008-cmd" class="hero-link" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
        GitHub
      </a>
      <a href="https://cyber-shield-ai-rouge.vercel.app" class="hero-link" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
        Portfolio
      </a>
      <a href="mailto:manojkumar829638@gmail.com" class="hero-link" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        Email
      </a>
    </div>
  </div>
</section>

<hr class="divider" />

<!-- ── WHAT I BUILD ──────────────────────────────── -->
<section id="build">
  <div class="container">
    <p class="section-label reveal">Capabilities</p>
    <h2 class="section-title reveal">What I Build</h2>
    <div class="pillars">
      <div class="pillar reveal">
        <span class="pillar-icon">⚙️</span>
        <h3>Backend Systems</h3>
        <ul>
          <li>Microservices with Java 17 + Spring Boot</li>
          <li>REST APIs with Spring Security &amp; JWT</li>
          <li>FastAPI Python services</li>
          <li>MySQL · PostgreSQL · MongoDB Atlas</li>
        </ul>
      </div>
      <div class="pillar reveal">
        <span class="pillar-icon">🎨</span>
        <h3>Frontend Engineering</h3>
        <ul>
          <li>React.js + TypeScript + Vite</li>
          <li>Tailwind CSS component systems</li>
          <li>Real-time WebSocket UIs</li>
          <li>Data visualization dashboards</li>
        </ul>
      </div>
      <div class="pillar reveal">
        <span class="pillar-icon">🤖</span>
        <h3>AI &amp; Security</h3>
        <ul>
          <li>5-model ML ensembles (RF, XGBoost, SVM, MLP)</li>
          <li>YOLO11 object detection + ByteTrack</li>
          <li>SOC threat telemetry &amp; alerting</li>
          <li>Automated incident reporting</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<hr class="divider" />

<!-- ── EXPERIENCE ────────────────────────────────── -->
<section id="experience">
  <div class="container">
    <p class="section-label reveal">Experience</p>
    <h2 class="section-title reveal">Internship</h2>
    <div class="experience-block reveal">
      <div class="exp-timeline">
        <div class="exp-dot"></div>
        <div class="exp-line"></div>
      </div>
      <div>
        <div class="exp-title">Java Development Intern</div>
        <div class="exp-org">TechnoHacks Solutions Pvt. Ltd.</div>
        <div class="exp-period">Jul 2025 – Aug 2025 · Remote</div>
        <ul class="exp-bullets">
          <li>Developed Java-based backend modules using core OOP principles and collections</li>
          <li>Worked with RESTful API patterns and Spring Boot fundamentals in a production codebase</li>
          <li>Collaborated on debugging, code review, and documentation workflows</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<hr class="divider" />

<!-- ── PROJECTS ───────────────────────────────────── -->
<section id="projects">
  <div class="container">
    <p class="section-label reveal">Work</p>
    <h2 class="section-title reveal">Featured Projects</h2>
    <div class="projects">

      <div class="project-card reveal">
        <div class="project-header">
          <span class="project-icon">🛡️</span>
          <div class="project-links">
            <a href="https://cyber-shield-ai-rouge.vercel.app" class="project-link live" target="_blank">Live ↗</a>
            <a href="https://github.com/manoj008-cmd/CyberShieldAI" class="project-link" target="_blank">Source</a>
          </div>
        </div>
        <div>
          <div class="project-name">CyberShield AI</div>
          <div class="project-subtitle">SOC Threat Intelligence Platform</div>
        </div>
        <p class="project-desc">Real-time system telemetry monitoring (CPU, RAM, Network I/O) with a 5-model ML ensemble for attack detection. SMTP automated alerts and PDF incident report generation.</p>
        <div class="project-tags">
          <span class="tag">React.js</span>
          <span class="tag">FastAPI</span>
          <span class="tag">Scikit-Learn</span>
          <span class="tag">Python</span>
          <span class="tag">Vercel</span>
        </div>
      </div>

      <div class="project-card reveal">
        <div class="project-header">
          <span class="project-icon">🚗</span>
          <div class="project-links">
            <a href="https://trolly-delta.vercel.app/" class="project-link live" target="_blank">Live ↗</a>
            <a href="https://github.com/manoj008-cmd/trolly" class="project-link" target="_blank">Source</a>
          </div>
        </div>
        <div>
          <div class="project-name">Trolly — Toll Engine</div>
          <div class="project-subtitle">Full-Stack Transaction Platform</div>
        </div>
        <p class="project-desc">Real-time vehicle tracking, automated toll calculation, transaction analytics, and instant digital receipt generation backed by Spring Boot REST services.</p>
        <div class="project-tags">
          <span class="tag">React.js</span>
          <span class="tag">Spring Boot</span>
          <span class="tag">MongoDB Atlas</span>
          <span class="tag">Tailwind CSS</span>
        </div>
      </div>

      <div class="project-card reveal">
        <div class="project-header">
          <span class="project-icon">👁️</span>
          <div class="project-links">
            <a href="https://algovision-jngf.vercel.app/" class="project-link live" target="_blank">Live ↗</a>
            <a href="https://github.com/manoj008-cmd/ALGOVISION" class="project-link" target="_blank">Source</a>
          </div>
        </div>
        <div>
          <div class="project-name">AlgoVision</div>
          <div class="project-subtitle">Interactive Algorithm Visualizer</div>
        </div>
        <p class="project-desc">Step-by-step graph pathfinding (Dijkstra, A*), sorting algorithms, and data structure operations with adjustable speed controls and live state visualization.</p>
        <div class="project-tags">
          <span class="tag">TypeScript</span>
          <span class="tag">React.js</span>
          <span class="tag">Tailwind CSS</span>
          <span class="tag">Vite</span>
        </div>
      </div>

      <div class="project-card reveal">
        <div class="project-header">
          <span class="project-icon">🔒</span>
          <div class="project-links">
            <a href="https://github.com/manoj008-cmd/VisionSync" class="project-link" target="_blank">Source</a>
          </div>
        </div>
        <div>
          <div class="project-name">VisionSync</div>
          <div class="project-subtitle">Real-Time CCTV Safety System</div>
        </div>
        <p class="project-desc">AI-powered threat detection using YOLO11 + ByteTrack, gender classification, and VideoMAE action recognition with live WebSocket alert feeds.</p>
        <div class="project-tags">
          <span class="tag">Python</span>
          <span class="tag">FastAPI</span>
          <span class="tag">YOLO11</span>
          <span class="tag">ByteTrack</span>
          <span class="tag">React.js</span>
        </div>
      </div>

      <div class="project-card featured reveal">
        <div class="project-header">
          <span class="project-icon">🏨</span>
          <div class="project-links">
            <a href="https://github.com/manoj008-cmd/HOTEL_MANAGEMENT" class="project-link" target="_blank">Source</a>
          </div>
        </div>
        <div>
          <div class="project-name">Hotel Administration System</div>
          <div class="project-subtitle">12-Module Operational Suite · 14 Relational DB Entities</div>
        </div>
        <p class="project-desc">Comprehensive hotel management platform: room bookings, guest records, staff assignments, food inventory, maintenance scheduling, and billing — all backed by a normalized relational schema.</p>
        <div class="project-tags">
          <span class="tag">Node.js</span>
          <span class="tag">Express.js</span>
          <span class="tag">MySQL</span>
          <span class="tag">JavaScript</span>
          <span class="tag">HTML5 / CSS3</span>
        </div>
      </div>

    </div>
  </div>
</section>

<hr class="divider" />

<!-- ── TECH STACK ─────────────────────────────────── -->
<section id="stack">
  <div class="container">
    <p class="section-label reveal">Tools</p>
    <h2 class="section-title reveal">Tech Stack</h2>

    <div class="stack-group reveal">
      <p class="stack-group-label">Languages &amp; Backend</p>
      <div class="stack-pills">
        <span class="pill"><span class="pill-dot" style="background:#f38ba8"></span>Java 17</span>
        <span class="pill"><span class="pill-dot" style="background:#a6e3a1"></span>Spring Boot</span>
        <span class="pill"><span class="pill-dot" style="background:#89b4fa"></span>Python</span>
        <span class="pill"><span class="pill-dot" style="background:#94e2d5"></span>FastAPI</span>
        <span class="pill"><span class="pill-dot" style="background:#a6e3a1"></span>Node.js</span>
        <span class="pill"><span class="pill-dot" style="background:#89b4fa"></span>C++</span>
      </div>
    </div>

    <div class="stack-group reveal">
      <p class="stack-group-label">Frontend</p>
      <div class="stack-pills">
        <span class="pill"><span class="pill-dot" style="background:#89dceb"></span>React.js</span>
        <span class="pill"><span class="pill-dot" style="background:#89b4fa"></span>TypeScript</span>
        <span class="pill"><span class="pill-dot" style="background:#89dceb"></span>Tailwind CSS</span>
        <span class="pill"><span class="pill-dot" style="background:#b4befe"></span>Vite</span>
      </div>
    </div>

    <div class="stack-group reveal">
      <p class="stack-group-label">Databases &amp; DevOps</p>
      <div class="stack-pills">
        <span class="pill"><span class="pill-dot" style="background:#a6e3a1"></span>MongoDB Atlas</span>
        <span class="pill"><span class="pill-dot" style="background:#89b4fa"></span>PostgreSQL</span>
        <span class="pill"><span class="pill-dot" style="background:#89b4fa"></span>MySQL</span>
        <span class="pill"><span class="pill-dot" style="background:#89dceb"></span>Docker</span>
        <span class="pill"><span class="pill-dot" style="background:#cdd6f4"></span>Vercel</span>
        <span class="pill"><span class="pill-dot" style="background:#fab387"></span>Git</span>
      </div>
    </div>

    <div class="stack-group reveal">
      <p class="stack-group-label">AI &amp; Security</p>
      <div class="stack-pills">
        <span class="pill"><span class="pill-dot" style="background:#fab387"></span>Scikit-Learn</span>
        <span class="pill"><span class="pill-dot" style="background:#a6e3a1"></span>Spring Security</span>
        <span class="pill"><span class="pill-dot" style="background:#f38ba8"></span>YOLO11 + OpenCV</span>
        <span class="pill"><span class="pill-dot" style="background:#b4befe"></span>XGBoost</span>
      </div>
    </div>
  </div>
</section>

<hr class="divider" />

<!-- ── ACHIEVEMENTS ───────────────────────────────── -->
<section id="achievements">
  <div class="container">
    <p class="section-label reveal">Recognition</p>
    <h2 class="section-title reveal">Achievements</h2>
    <div class="achievements">
      <div class="achievement reveal">
        <div class="achievement-medal">🥇</div>
        <div class="achievement-content">
          <div class="achievement-name">IEEE DataPort Hackathon 2026</div>
          <div class="achievement-meta">IEEE CS Bangalore Chapter · Data Science &amp; ML Engineering</div>
        </div>
      </div>
      <div class="achievement reveal">
        <div class="achievement-medal">💡</div>
        <div class="achievement-content">
          <div class="achievement-name">Tech Ideathon 2025 — Team NeuroNex</div>
          <div class="achievement-meta">SkillBolt.Dev · AI Innovation &amp; System Architecture · ID20256VWXIL</div>
        </div>
      </div>
      <div class="achievement reveal">
        <div class="achievement-medal">⚡</div>
        <div class="achievement-content">
          <div class="achievement-name">HACKOTSAVA 2025</div>
          <div class="achievement-meta">SMVITM Bantakal · National-Level Rapid Full-Stack Prototyping · SMVITM-HACK-2025-041</div>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="divider" />

<!-- ── CTA ────────────────────────────────────────── -->
<section id="cta">
  <div class="container">
    <div class="cta-inner reveal">
      <p class="cta-eyebrow">Let's work together</p>
      <h2 class="cta-title">Open to opportunities.</h2>
      <p class="cta-sub">Full-time SWE roles, backend &amp; full-stack internships, and open source collaborations.</p>
      <div class="cta-links">
        <a href="mailto:manojkumar829638@gmail.com" class="hero-link primary">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          Send Email
        </a>
        <a href="https://linkedin.com/in/manoj-kumar" class="hero-link" target="_blank">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          Connect
        </a>
      </div>
    </div>
  </div>
</section>

<script>
  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  // Respect reduced motion
  if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
    document.querySelectorAll('.reveal').forEach(el => el.classList.add('visible'));
  }
</script>
</body>
</html>
