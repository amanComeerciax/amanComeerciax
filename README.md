
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mo_Amaan — GitHub README Preview</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --border: #1e1e2e;
    --accent: #00f5a0;
    --accent2: #00d4ff;
    --accent3: #ff6b6b;
    --text: #e0e0f0;
    --muted: #666680;
    --card: #13131f;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,245,160,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,245,160,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    text-align: center;
    margin-bottom: 60px;
    animation: fadeUp 0.8s ease both;
  }

  .greeting {
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
    opacity: 0.8;
  }

  .name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(42px, 8vw, 80px);
    font-weight: 800;
    line-height: 1;
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 50%, #a78bfa 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
  }

  .tagline {
    font-size: 14px;
    color: var(--muted);
    letter-spacing: 2px;
    margin-bottom: 32px;
  }

  /* Typing animation */
  .typing-wrapper {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 10px 20px;
    font-size: 13px;
    color: var(--accent);
    margin-bottom: 40px;
  }

  .typing-wrapper::before {
    content: '>';
    color: var(--accent3);
  }

  .typed-text {
    border-right: 2px solid var(--accent);
    white-space: nowrap;
    overflow: hidden;
    animation: typing 3s steps(40, end) infinite, blink 0.75s step-end infinite;
    width: 0;
    animation-fill-mode: forwards;
  }

  @keyframes typing {
    0% { width: 0 }
    40% { width: 100% }
    80% { width: 100% }
    100% { width: 0 }
  }

  @keyframes blink {
    50% { border-color: transparent }
  }

  /* ── BADGES ── */
  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
    margin-bottom: 60px;
    animation: fadeUp 0.8s 0.2s ease both;
    opacity: 0;
  }

  .badge {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 6px 14px;
    font-size: 11px;
    letter-spacing: 1px;
    color: var(--muted);
    transition: all 0.2s;
    cursor: default;
  }

  .badge:hover {
    border-color: var(--accent);
    color: var(--accent);
    box-shadow: 0 0 12px rgba(0,245,160,0.15);
  }

  .badge.highlight {
    border-color: rgba(0,245,160,0.3);
    color: var(--accent);
  }

  /* ── SECTION TITLES ── */
  .section {
    margin-bottom: 50px;
    animation: fadeUp 0.8s ease both;
  }

  .section-label {
    font-size: 11px;
    letter-spacing: 3px;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border) 0%, transparent 100%);
  }

  /* ── ABOUT ── */
  .about-text {
    font-size: 14px;
    line-height: 1.9;
    color: #9898b8;
    border-left: 2px solid var(--accent);
    padding-left: 20px;
  }

  .about-text strong {
    color: var(--text);
  }

  /* ── SKILLS ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 16px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .skill-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }

  .skill-card:hover {
    border-color: rgba(0,245,160,0.3);
    transform: translateY(-2px);
    box-shadow: 0 8px 24px rgba(0,0,0,0.4);
  }

  .skill-card:hover::before { transform: scaleX(1); }

  .skill-icon { font-size: 22px; margin-bottom: 8px; }
  .skill-name { font-size: 12px; color: var(--text); font-weight: 700; margin-bottom: 4px; }
  .skill-desc { font-size: 11px; color: var(--muted); }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  @media (max-width: 600px) { .projects-grid { grid-template-columns: 1fr; } }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    text-decoration: none;
    display: block;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .project-card::after {
    content: '↗';
    position: absolute;
    top: 16px; right: 16px;
    color: var(--muted);
    font-size: 16px;
    transition: all 0.2s;
  }

  .project-card:hover {
    border-color: rgba(0,212,255,0.4);
    box-shadow: 0 0 30px rgba(0,212,255,0.08);
    transform: translateY(-3px);
  }

  .project-card:hover::after { color: var(--accent2); transform: translate(2px, -2px); }

  .project-tag {
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--accent2);
    margin-bottom: 10px;
    text-transform: uppercase;
  }

  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 16px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 8px;
  }

  .project-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.7;
  }

  .project-lang {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    margin-top: 14px;
    font-size: 11px;
    color: var(--muted);
  }

  .lang-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: #f0db4f;
  }

  .lang-dot.ts { background: #3178c6; }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
  }

  .stat-box {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 20px;
    text-align: center;
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 32px;
    font-weight: 800;
    color: var(--accent);
    line-height: 1;
    margin-bottom: 6px;
  }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 1px;
  }

  /* ── CONNECT ── */
  .connect-row {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .connect-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: transparent;
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 10px 20px;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    text-decoration: none;
    cursor: pointer;
    transition: all 0.2s;
  }

  .connect-btn:hover {
    border-color: var(--accent);
    color: var(--accent);
    box-shadow: 0 0 16px rgba(0,245,160,0.15);
  }

  /* ── FOOTER ── */
  .footer {
    margin-top: 70px;
    padding-top: 30px;
    border-top: 1px solid var(--border);
    text-align: center;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 2px;
  }

  .footer span { color: var(--accent3); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .delay-4 { animation-delay: 0.4s; }

  /* ── COPY INFO BOX ── */
  .info-box {
    background: rgba(0,245,160,0.05);
    border: 1px solid rgba(0,245,160,0.2);
    border-radius: 6px;
    padding: 16px 20px;
    margin-bottom: 40px;
    font-size: 12px;
    color: var(--accent);
    text-align: center;
    line-height: 1.7;
  }

  .info-box strong { color: var(--text); }
</style>
</head>
<body>
<div class="container">

  <!-- Info Box for user -->
  <div class="info-box">
    <strong>📋 How to use this README:</strong><br>
    Copy the markdown content below into your <code>amanComeerciax/README.md</code> file on GitHub.<br>
    The preview above shows how it'll look visually — the actual README uses GitHub-flavored Markdown.
  </div>

  <!-- HEADER -->
  <div class="header">
    <div class="greeting">// Hello World 👋</div>
    <div class="name">Mo_Amaan</div>
    <div class="tagline">FULL STACK DEVELOPER  ·  AI BUILDER  ·  MERN STACK</div>
    <div class="typing-wrapper">
      <span class="typed-text">Building AI-powered products that matter</span>
    </div>
  </div>

  <!-- BADGES -->
  <div class="badges">
    <span class="badge highlight">🤖 AI/ML</span>
    <span class="badge">⚛️ React</span>
    <span class="badge">🟢 Node.js</span>
    <span class="badge">📘 TypeScript</span>
    <span class="badge">🐳 Docker</span>
    <span class="badge highlight">🔍 RAG Systems</span>
    <span class="badge">🍃 MongoDB</span>
    <span class="badge">🚀 Open to Work</span>
  </div>

  <!-- ABOUT -->
  <div class="section delay-1">
    <div class="section-label">About Me</div>
    <p class="about-text">
      I'm <strong>Mo Amaan</strong>, a passionate Full Stack Developer focused on building <strong>AI-powered web applications</strong>.
      I love turning ideas into products — from MERN stack apps to intelligent AI systems using RAG, LLMs, and modern web tech.
      Currently exploring the intersection of <strong>AI + E-commerce</strong> to build smarter user experiences.
    </p>
  </div>

  <!-- STATS -->
  <div class="section delay-2">
    <div class="section-label">Stats</div>
    <div class="stats-row">
      <div class="stat-box">
        <div class="stat-num">7</div>
        <div class="stat-label">Repositories</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">11</div>
        <div class="stat-label">Stars Earned</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">3+</div>
        <div class="stat-label">AI Projects</div>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section delay-2">
    <div class="section-label">Tech Stack</div>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-icon">⚛️</div>
        <div class="skill-name">React / Next.js</div>
        <div class="skill-desc">Frontend UI development</div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🟢</div>
        <div class="skill-name">Node.js / Express</div>
        <div class="skill-desc">REST APIs & backend logic</div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">📘</div>
        <div class="skill-name">TypeScript</div>
        <div class="skill-desc">Type-safe development</div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🍃</div>
        <div class="skill-name">MongoDB</div>
        <div class="skill-desc">NoSQL database design</div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🤖</div>
        <div class="skill-name">AI / RAG</div>
        <div class="skill-desc">LLMs, embeddings, vector DBs</div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🐳</div>
        <div class="skill-name">Docker</div>
        <div class="skill-desc">Containerized deployments</div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section delay-3">
    <div class="section-label">Featured Projects</div>
    <div class="projects-grid">

      <a class="project-card" href="https://github.com/amanComeerciax/Ai_Upsell_Engine" target="_blank">
        <div class="project-tag">TypeScript · AI</div>
        <div class="project-name">AI Upsell Engine</div>
        <div class="project-desc">Intelligent upsell recommendation system powered by AI to boost e-commerce revenue.</div>
        <div class="project-lang"><span class="lang-dot ts"></span> TypeScript</div>
      </a>

      <a class="project-card" href="https://github.com/amanComeerciax/LeadFinder-AI" target="_blank">
        <div class="project-tag">JavaScript · AI</div>
        <div class="project-name">LeadFinder AI</div>
        <div class="project-desc">AI-powered lead generation tool to find and qualify potential customers automatically.</div>
        <div class="project-lang"><span class="lang-dot"></span> JavaScript</div>
      </a>

      <a class="project-card" href="https://github.com/amanComeerciax/Machine_Learning_AI_RAG_Basics" target="_blank">
        <div class="project-tag">JavaScript · ML/RAG</div>
        <div class="project-name">ML & RAG Basics</div>
        <div class="project-desc">Hands-on exploration of Machine Learning and Retrieval-Augmented Generation fundamentals.</div>
        <div class="project-lang"><span class="lang-dot"></span> JavaScript</div>
      </a>

      <a class="project-card" href="https://github.com/amanComeerciax/day1_chatbot_mern_ai" target="_blank">
        <div class="project-tag">MERN · Chatbot</div>
        <div class="project-name">MERN AI Chatbot</div>
        <div class="project-desc">Full-stack AI chatbot built with the MERN stack — the project that started it all.</div>
        <div class="project-lang"><span class="lang-dot"></span> JavaScript</div>
      </a>

    </div>
  </div>

  <!-- CONNECT -->
  <div class="section delay-4">
    <div class="section-label">Connect</div>
    <div class="connect-row">
      <a class="connect-btn" href="https://github.com/amanComeerciax" target="_blank">
        ⌂ GitHub
      </a>
      <a class="connect-btn" href="#" target="_blank">
        💼 LinkedIn
      </a>
      <a class="connect-btn" href="mailto:your@email.com">
        ✉ Email
      </a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    Built with <span>♥</span> by Mo_Amaan · 2026
  </div>

</div>
</body>
</html>
