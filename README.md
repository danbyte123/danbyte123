<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Dan — Developer Profile</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:         #0d0f14;
      --bg-card:    #13161e;
      --bg-sec:     #1a1d27;
      --border:     rgba(255,255,255,0.08);
      --border-md:  rgba(255,255,255,0.14);
      --text:       #e8eaf0;
      --text-sec:   #8b90a0;
      --text-ter:   #555b6e;
      --accent:     #1D9E75;
      --accent-dim: rgba(29,158,117,0.15);
      --info:       #378ADD;
      --info-dim:   rgba(55,138,221,0.12);
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Syne', sans-serif;
      min-height: 100vh;
      padding: 2.5rem 1rem;
    }

    .container {
      max-width: 720px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 14px;
    }

    /* CARDS */
    .card {
      background: var(--bg-card);
      border: 0.5px solid var(--border);
      border-radius: 16px;
      padding: 1.5rem;
    }

    /* HEADER */
    .header-badge {
      display: inline-block;
      font-family: 'JetBrains Mono', monospace;
      font-size: 11px;
      padding: 4px 10px;
      border-radius: 4px;
      background: var(--info-dim);
      color: var(--info);
      border: 0.5px solid rgba(55,138,221,0.3);
      margin-bottom: 14px;
    }

    .header-inner {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 16px;
    }

    .avatar {
      width: 52px;
      height: 52px;
      border-radius: 50%;
      background: var(--info-dim);
      border: 0.5px solid rgba(55,138,221,0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 800;
      font-size: 18px;
      color: var(--info);
      font-family: 'JetBrains Mono', monospace;
      flex-shrink: 0;
    }

    .name {
      font-size: 42px;
      font-weight: 800;
      line-height: 1.1;
      color: var(--text);
    }

    .role {
      font-size: 15px;
      color: var(--text-sec);
      margin-top: 4px;
    }

    .learning-badge {
      display: inline-block;
      font-family: 'JetBrains Mono', monospace;
      font-size: 12px;
      padding: 5px 12px;
      border-radius: 6px;
      border: 0.5px solid rgba(29,158,117,0.4);
      color: var(--accent);
      background: var(--accent-dim);
      margin: 8px 4px 0 0;
    }

    /* LINKS */
    .link-btn {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-size: 13px;
      font-weight: 500;
      font-family: 'Syne', sans-serif;
      padding: 8px 16px;
      border-radius: 8px;
      border: 0.5px solid var(--border-md);
      color: var(--text);
      text-decoration: none;
      background: var(--bg-sec);
      transition: background 0.15s, border-color 0.15s;
      margin: 4px 6px 4px 0;
    }

    .link-btn:hover {
      background: rgba(255,255,255,0.06);
      border-color: rgba(255,255,255,0.22);
    }

    .email-text {
      font-family: 'JetBrains Mono', monospace;
      font-size: 12px;
      color: var(--text-ter);
      margin-top: 8px;
      display: block;
    }

    /* TERMINAL */
    .terminal-block {
      font-family: 'JetBrains Mono', monospace;
      font-size: 13px;
      background: var(--bg-card);
      border: 0.5px solid var(--border);
      border-radius: 12px;
      padding: 1rem 1.25rem;
      line-height: 1.9;
    }

    .terminal-block .prompt { color: var(--accent); }
    .terminal-block .path   { color: var(--info); }
    .terminal-block .cmd    { color: var(--text); }
    .terminal-block .out    { color: var(--text-sec); }

    /* SKILLS */
    .skill-section { margin-bottom: 1.1rem; }
    .skill-section:last-child { margin-bottom: 0; }

    .skill-label {
      font-family: 'JetBrains Mono', monospace;
      font-size: 10px;
      color: var(--text-ter);
      text-transform: uppercase;
      letter-spacing: 0.12em;
      margin-bottom: 8px;
    }

    .skill-pill {
      display: inline-block;
      font-size: 13px;
      font-weight: 500;
      padding: 5px 13px;
      border-radius: 20px;
      margin: 3px 3px;
      border: 0.5px solid var(--border-md);
      color: var(--text);
      background: var(--bg-sec);
      transition: background 0.15s, border-color 0.15s;
      cursor: default;
    }

    .skill-pill:hover {
      background: rgba(255,255,255,0.06);
      border-color: rgba(255,255,255,0.2);
    }

    .skill-pill.accent {
      border-color: rgba(29,158,117,0.5);
      color: var(--accent);
      background: var(--accent-dim);
    }

    .skill-pill .tag-note {
      font-size: 10px;
      color: var(--text-ter);
      margin-left: 4px;
    }

    /* STATS */
    .stats-row {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .stat-card {
      flex: 1;
      min-width: 130px;
      background: var(--bg-card);
      border: 0.5px solid var(--border);
      border-radius: 14px;
      padding: 1.1rem 1.25rem;
    }

    .stat-label {
      font-family: 'JetBrains Mono', monospace;
      font-size: 10px;
      color: var(--text-ter);
      text-transform: uppercase;
      letter-spacing: 0.1em;
      margin-bottom: 6px;
    }

    .stat-num {
      font-size: 26px;
      font-weight: 800;
      color: var(--text);
      line-height: 1;
    }

    .stat-sub {
      font-family: 'JetBrains Mono', monospace;
      font-size: 11px;
      color: var(--text-ter);
      margin-top: 5px;
    }

    /* DIVIDER */
    .divider {
      border: none;
      border-top: 0.5px solid var(--border);
      margin: 1.1rem 0;
    }

    /* FOOTER */
    .footer {
      text-align: center;
      font-family: 'JetBrains Mono', monospace;
      font-size: 11px;
      color: var(--text-ter);
      padding-top: 0.5rem;
    }

    @media (max-width: 480px) {
      .name { font-size: 30px; }
      .header-inner { flex-direction: column; }
    }
  </style>
</head>
<body>
  <div class="container">

    <!-- HEADER CARD -->
    <div class="card">
      <div class="header-badge">// PROFILE.md</div>
      <div class="header-inner">
        <div>
          <div style="display:flex; align-items:center; gap:14px; margin-bottom:10px;">
            <div class="avatar">D</div>
            <h1 class="name">Dan</h1>
          </div>
          <p class="role">Full-stack &amp; low-level systems developer &mdash; Jordan</p>
          <div>
            <span class="learning-badge">&#9654; learning Assembly</span>
            <span class="learning-badge">&#9654; learning Three.js</span>
          </div>
        </div>

        <div>
          <a class="link-btn" href="https://jo.linkedin.com/in/mohamed-khateb-009650284" target="_blank" rel="noreferrer">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
            LinkedIn
          </a>
          <a class="link-btn" href="https://github.com/danbyte123" target="_blank" rel="noreferrer">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
            GitHub
          </a>
          <a class="link-btn" href="https://profiles.topcoder.com/danbyte123" target="_blank" rel="noreferrer">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2a10 10 0 100 20A10 10 0 0012 2zm0 2a8 8 0 110 16A8 8 0 0112 4zm-1 3v10l7-5-7-5z"/></svg>
            Topcoder
          </a>
          <span class="email-text">mokj2019@gmail.com</span>
        </div>
      </div>
    </div>

    <!-- TERMINAL -->
    <div class="terminal-block">
      <div><span class="prompt">dan@dev</span>:<span class="path">~/stack</span>$ <span class="cmd">whoami</span></div>
      <div class="out">Full-stack engineer who goes deep &mdash; from web interfaces to bare metal.</div>
      <div style="margin-top:4px;"><span class="prompt">dan@dev</span>:<span class="path">~/stack</span>$ <span class="cmd">cat current.log</span></div>
      <div class="out">Studying Assembly &amp; building 3D interfaces with Three.js</div>
    </div>

    <!-- SKILLS CARD -->
    <div class="card">

      <div class="skill-section">
        <div class="skill-label">Systems &amp; Low-level</div>
        <span class="skill-pill accent">C</span>
        <span class="skill-pill accent">C++</span>
        <span class="skill-pill">Assembly<span class="tag-note">learning</span></span>
        <span class="skill-pill">Linux</span>
        <span class="skill-pill">Bash</span>
        <span class="skill-pill">Arduino</span>
      </div>

      <hr class="divider" />

      <div class="skill-section">
        <div class="skill-label">Backend</div>
        <span class="skill-pill accent">Node.js</span>
        <span class="skill-pill accent">Go</span>
        <span class="skill-pill">Python</span>
        <span class="skill-pill">PHP</span>
        <span class="skill-pill">Express.js</span>
        <span class="skill-pill">Docker</span>
        <span class="skill-pill">Kubernetes</span>
      </div>

      <hr class="divider" />

      <div class="skill-section">
        <div class="skill-label">Frontend</div>
        <span class="skill-pill">HTML5</span>
        <span class="skill-pill">CSS3</span>
        <span class="skill-pill">JavaScript</span>
        <span class="skill-pill">Tailwind CSS</span>
        <span class="skill-pill">Three.js<span class="tag-note">learning</span></span>
        <span class="skill-pill">Figma</span>
      </div>

      <hr class="divider" />

      <div class="skill-section">
        <div class="skill-label">Data &amp; Databases</div>
        <span class="skill-pill">MongoDB</span>
        <span class="skill-pill">MySQL</span>
        <span class="skill-pill">SQLite</span>
        <span class="skill-pill">Pandas</span>
        <span class="skill-pill">OpenCV</span>
      </div>

      <hr class="divider" />

      <div class="skill-section">
        <div class="skill-label">Tools &amp; Other</div>
        <span class="skill-pill">Git</span>
        <span class="skill-pill">Unity</span>
      </div>

    </div>

    <!-- STATS ROW -->
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-label">depth</div>
        <div class="stat-num" style="color:var(--accent); font-size:18px;">Low → High</div>
        <div class="stat-sub">Assembly to cloud</div>
      </div>
      <div class="stat-card">
        <div class="stat-label">stack</div>
        <div class="stat-num">20+</div>
        <div class="stat-sub">languages &amp; tools</div>
      </div>
      <div class="stat-card">
        <div class="stat-label">location</div>
        <div class="stat-num" style="font-size:20px;">🇯🇴 Jordan</div>
        <div class="stat-sub">Amman</div>
      </div>
    </div>

    <p class="footer">built with &lt;/&gt; by Dan &bull; danbyte123</p>

  </div>
</body>
</html>
