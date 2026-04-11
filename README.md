<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Tri Misbachul Attabik – README</title>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,400;0,700;1,400&family=IBM+Plex+Mono:wght@400;600&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:        #0d1117;
      --surface:   #161b22;
      --surface2:  #1c2333;
      --border:    #30363d;
      --text:      #c9d1d9;
      --text-dim:  #8b949e;
      --green:     #3fb950;
      --green-dim: #238636;
      --cyan:      #58a6ff;
      --yellow:    #e3b341;
      --red:       #f85149;
      --accent:    #00ff88;
      --num:       #79c0ff;
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'JetBrains Mono', monospace;
      font-size: 14px;
      line-height: 1.6;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      padding: 40px 16px;
    }

    .terminal {
      width: 100%;
      max-width: 760px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 0 0 1px #0003, 0 32px 80px #0008;
    }

    /* ── Title Bar ── */
    .titlebar {
      background: #2d333b;
      border-bottom: 1px solid var(--border);
      padding: 10px 16px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .dot { width: 12px; height: 12px; border-radius: 50%; }
    .dot-r { background: #ff5f57; }
    .dot-y { background: #ffbd2e; }
    .dot-g { background: #28c840; }
    .titlebar-label {
      flex: 1;
      text-align: center;
      font-size: 11px;
      color: var(--text-dim);
      letter-spacing: .12em;
    }

    /* ── Body ── */
    .body { padding: 32px 40px 48px; }

    /* prompt */
    .prompt {
      color: var(--accent);
      font-size: 13px;
      margin-bottom: 18px;
    }
    .prompt span { color: var(--text-dim); }

    /* hero name */
    .hero-name {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 36px;
      font-weight: 700;
      color: #e6edf3;
      letter-spacing: -.5px;
      line-height: 1.1;
      margin-bottom: 14px;
    }

    /* badges row */
    .badges {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 16px;
      flex-wrap: wrap;
    }
    .badge-active {
      background: var(--green-dim);
      color: #fff;
      font-size: 11px;
      font-weight: 700;
      padding: 2px 9px;
      border-radius: 4px;
      letter-spacing: .06em;
    }
    .badge-role {
      color: var(--cyan);
      font-size: 14px;
      font-weight: 600;
    }

    /* quote block */
    .quote-block {
      border-left: 3px solid var(--border);
      padding: 10px 16px;
      color: var(--text-dim);
      font-style: italic;
      font-size: 13px;
      margin-bottom: 0;
    }

    /* ── Divider / Section Header ── */
    .section {
      margin-top: 36px;
    }
    .section-title {
      display: flex;
      align-items: center;
      gap: 6px;
      font-size: 15px;
      font-weight: 700;
      color: #e6edf3;
      padding-bottom: 10px;
      border-bottom: 1px solid var(--border);
      margin-bottom: 20px;
    }
    .section-num {
      color: var(--green);
    }
    .section-dot {
      color: var(--text-dim);
    }

    /* about text */
    .about-text {
      color: var(--text);
      font-size: 13.5px;
      line-height: 1.8;
      margin-bottom: 20px;
    }
    .about-text a { color: var(--cyan); text-decoration: none; }
    .about-text strong { color: #e6edf3; font-weight: 700; }

    /* achievement cards */
    .cards-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
      margin-bottom: 10px;
    }
    .card-wide { grid-column: 1 / -1; }
    .card {
      background: var(--surface2);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 14px 16px;
      display: flex;
      align-items: flex-start;
      gap: 10px;
      font-size: 13px;
      color: var(--text);
      line-height: 1.55;
    }
    .card-icon {
      color: var(--green);
      margin-top: 1px;
      flex-shrink: 0;
    }

    /* ── Tech Section ── */
    .tech-cols {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }
    .tech-group {}
    .tech-label {
      font-size: 10px;
      letter-spacing: .15em;
      color: var(--text-dim);
      margin-bottom: 10px;
      display: flex;
      align-items: center;
      gap: 6px;
    }
    .tech-label svg { opacity: .6; }
    .tag-row {
      display: flex;
      flex-wrap: wrap;
      gap: 7px;
    }
    .tag {
      background: transparent;
      border: 1px solid var(--border);
      color: var(--text);
      font-family: 'JetBrains Mono', monospace;
      font-size: 12px;
      padding: 3px 10px;
      border-radius: 4px;
      white-space: nowrap;
    }

    /* ── GitHub Stats ── */
    .stats-title {
      display: flex;
      align-items: center;
      gap: 6px;
      font-size: 15px;
      font-weight: 700;
      color: #e6edf3;
      padding-bottom: 10px;
      border-bottom: 1px solid var(--border);
      margin-bottom: 20px;
    }
    .stats-placeholder {
      background: var(--surface2);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 20px 24px;
      display: flex;
      gap: 32px;
      flex-wrap: wrap;
    }
    .stat-item { text-align: left; }
    .stat-val {
      font-size: 22px;
      font-weight: 700;
      color: var(--accent);
    }
    .stat-key {
      font-size: 11px;
      color: var(--text-dim);
      margin-top: 2px;
    }

    @media (max-width: 560px) {
      .body { padding: 24px 20px 36px; }
      .hero-name { font-size: 26px; }
      .cards-grid { grid-template-columns: 1fr; }
      .tech-cols { grid-template-columns: 1fr; gap: 16px; }
      .stats-placeholder { gap: 18px; }
    }
  </style>
</head>
<body>

<div class="terminal">

  <!-- Title bar -->
  <div class="titlebar">
    <div class="dot dot-r"></div>
    <div class="dot dot-y"></div>
    <div class="dot dot-g"></div>
    <div class="titlebar-label">BASH — 80×24</div>
  </div>

  <!-- Content -->
  <div class="body">

    <!-- Prompt -->
    <div class="prompt">→ <span>~ </span>whoami</div>

    <!-- Hero -->
    <div class="hero-name">Tri Misbachul Attabik</div>
    <div class="badges">
      <span class="badge-active">Active</span>
      <span class="badge-role">IT Network &amp; DevOps Enthusiast</span>
    </div>
    <div class="quote-block">
      "Informatics Student | Former NOC Engineer | DevOps &amp; SysAdmin Enthusiast"
    </div>

    <!-- 01. Tentang Saya -->
    <div class="section">
      <div class="section-title">
        <span class="section-num">01.</span>
        <span>Tentang Saya</span>
      </div>

      <p class="about-text">
        Saya adalah mahasiswa Teknik Informatika di
        <a href="https://unisnu.ac.id" target="_blank">UNISNU Jepara</a>
        (GPA 4.00) dengan pengalaman 2,5 tahun sebagai
        <strong>NOC Engineer</strong>. Saya memiliki spesialisasi dalam menjaga stabilitas jaringan
        <strong>(99.9% uptime)</strong> dan kini sedang mendalami ekosistem
        <strong>DevOps &amp; System Administration.</strong>
      </p>

      <div class="cards-grid">
        <div class="card">
          <span class="card-icon">
            <!-- checkmark -->
            <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <circle cx="8" cy="8" r="7.5" stroke="currentColor" stroke-width="1"/>
              <path d="M4.5 8.5L7 11L11.5 5.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </span>
          <span>Pernah menangani monitoring <strong>1.000+ klien</strong> di lingkungan 24/7.</span>
        </div>
        <div class="card">
          <span class="card-icon">
            <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <circle cx="8" cy="8" r="7.5" stroke="currentColor" stroke-width="1"/>
              <path d="M4.5 8.5L7 11L11.5 5.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </span>
          <span><strong>Juara 1 LKS IT Network System Administration</strong> tingkat Kabupaten.</span>
        </div>
        <div class="card card-wide">
          <span class="card-icon">
            <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <circle cx="8" cy="8" r="7.5" stroke="currentColor" stroke-width="1"/>
              <path d="M4.5 8.5L7 11L11.5 5.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </span>
          <span>Berfokus pada automasi menggunakan <strong>Bash &amp; Python</strong> untuk efisiensi operasional.</span>
        </div>
      </div>
    </div>

    <!-- 02. Teknologi & Peralatan -->
    <div class="section">
      <div class="section-title">
        <span class="section-num">02.</span>
        <span>Teknologi &amp; Peralatan</span>
      </div>

      <div class="tech-cols">
        <!-- Networking -->
        <div class="tech-group">
          <div class="tech-label">
            <!-- globe icon -->
            <svg width="12" height="12" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0a8 8 0 1 0 0 16A8 8 0 0 0 8 0zm-.5 1.07v2.43a5.5 5.5 0 0 0-2.3.97L3.28 2.57A6.97 6.97 0 0 1 7.5 1.07zm1 0a6.97 6.97 0 0 1 4.22 1.5L10.8 4.47a5.5 5.5 0 0 0-2.3-.97V1.07zM2.57 3.28l1.9 1.9A5.5 5.5 0 0 0 3.5 7.5H1.07a6.97 6.97 0 0 1 1.5-4.22zm10.86 0a6.97 6.97 0 0 1 1.5 4.22H12.5a5.5 5.5 0 0 0-.97-2.32l1.9-1.9zM1.07 8.5H3.5a5.5 5.5 0 0 0 .97 2.32l-1.9 1.9A6.97 6.97 0 0 1 1.07 8.5zm11.43 0h2.43a6.97 6.97 0 0 1-1.5 4.22l-1.9-1.9A5.5 5.5 0 0 0 12.5 8.5zm-9 2.93a5.5 5.5 0 0 0 2.3.97v2.43a6.97 6.97 0 0 1-4.2-1.5l1.9-1.9zm5.5.97a5.5 5.5 0 0 0 2.3-.97l1.9 1.9a6.97 6.97 0 0 1-4.2 1.5v-2.43z"/></svg>
            NETWORKING
          </div>
          <div class="tag-row">
            <span class="tag">MikroTik</span>
            <span class="tag">Cisco</span>
            <span class="tag">Zabbix</span>
            <span class="tag">LibreNMS</span>
          </div>
        </div>

        <!-- DevOps -->
        <div class="tech-group">
          <div class="tech-label">
            <!-- cloud icon -->
            <svg width="12" height="12" viewBox="0 0 16 16" fill="currentColor"><path d="M4.406 3.342A5.53 5.53 0 0 1 8 2c2.69 0 4.923 2 5.166 4.579C14.758 6.804 16 8.137 16 9.773 16 11.569 14.502 13 12.687 13H3.781C1.708 13 0 11.366 0 9.318c0-1.763 1.266-3.223 2.942-3.513A5.526 5.526 0 0 1 4.406 3.342z"/></svg>
            DEVOPS
          </div>
          <div class="tag-row">
            <span class="tag">Docker</span>
            <span class="tag">Linux</span>
            <span class="tag">Vagrant</span>
            <span class="tag">VMware</span>
          </div>
        </div>

        <!-- Scripting -->
        <div class="tech-group">
          <div class="tech-label">
            <!-- code icon -->
            <svg width="12" height="12" viewBox="0 0 16 16" fill="currentColor"><path d="M10.478 1.647a.5.5 0 1 0-.956-.294l-4 13a.5.5 0 0 0 .956.294l4-13zM4.854 4.146a.5.5 0 0 1 0 .708L1.707 8l3.147 3.146a.5.5 0 0 1-.708.708l-3.5-3.5a.5.5 0 0 1 0-.708l3.5-3.5a.5.5 0 0 1 .708 0zm6.292 0a.5.5 0 0 0 0 .708L14.293 8l-3.147 3.146a.5.5 0 0 0 .708.708l3.5-3.5a.5.5 0 0 0 0-.708l-3.5-3.5a.5.5 0 0 0-.708 0z"/></svg>
            SCRIPTING
          </div>
          <div class="tag-row">
            <span class="tag">Python</span>
            <span class="tag">Bash</span>
            <span class="tag">MySQL</span>
          </div>
        </div>
      </div>
    </div>

    <!-- 03. GitHub Stats -->
    <div class="section">
      <div class="stats-title">
        <span class="section-num">03.</span>
        <span>Statistik GitHub</span>
      </div>
      <div class="stats-placeholder">
        <div class="stat-item">
          <div class="stat-val">4.00</div>
          <div class="stat-key">GPA</div>
        </div>
        <div class="stat-item">
          <div class="stat-val">2.5yr</div>
          <div class="stat-key">NOC Experience</div>
        </div>
        <div class="stat-item">
          <div class="stat-val">1000+</div>
          <div class="stat-key">Clients Monitored</div>
        </div>
        <div class="stat-item">
          <div class="stat-val">99.9%</div>
          <div class="stat-key">Network Uptime</div>
        </div>
        <div class="stat-item">
          <div class="stat-val">#1</div>
          <div class="stat-key">LKS Network — Kabupaten</div>
        </div>
      </div>
    </div>

  </div><!-- /body -->
</div><!-- /terminal -->

</body>
</html>
