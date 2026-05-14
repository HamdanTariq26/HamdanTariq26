<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hamdan Tariq — Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0a0d14;
    --bg2: #0f1320;
    --bg3: #141929;
    --accent: #00f5c4;
    --accent2: #ff6b35;
    --accent3: #7c6af7;
    --text: #e8eaf0;
    --muted: #6b7395;
    --border: #1e2540;
    --mono: 'JetBrains Mono', monospace;
    --display: 'Syne', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--display);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(var(--border) 1px, transparent 1px),
      linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size: 48px 48px;
    opacity: 0.4;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 2rem;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ─────────────────────────────────────── */
  .hero {
    padding: 5rem 0 3rem;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 3rem;
    align-items: start;
  }

  .hero-label {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 0.18em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 1.2rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .hero-label::before {
    content: '';
    display: inline-block;
    width: 20px;
    height: 1px;
    background: var(--accent);
  }

  .hero h1 {
    font-family: var(--display);
    font-size: clamp(2.6rem, 5vw, 4.4rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 1.4rem;
  }

  .hero h1 span {
    display: block;
    color: var(--accent);
  }

  .hero-bio {
    font-family: var(--mono);
    font-size: 0.82rem;
    line-height: 1.9;
    color: var(--muted);
    max-width: 480px;
    border-left: 2px solid var(--border);
    padding-left: 1.2rem;
  }

  .hero-bio strong {
    color: var(--text);
    font-weight: 400;
  }

  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
  }

  .avatar-ring {
    width: 140px;
    height: 140px;
    border-radius: 50%;
    border: 1.5px solid var(--accent);
    padding: 4px;
    position: relative;
  }

  .avatar-ring::before {
    content: '';
    position: absolute;
    inset: -10px;
    border-radius: 50%;
    border: 1px dashed rgba(0,245,196,0.2);
    animation: spin 20s linear infinite;
  }

  @keyframes spin { to { transform: rotate(360deg); } }

  .avatar-ring img {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    object-fit: cover;
    display: block;
    filter: grayscale(15%);
  }

  .avatar-badge {
    position: absolute;
    bottom: 0;
    right: 0;
    background: var(--bg2);
    border: 1.5px solid var(--accent);
    border-radius: 50%;
    width: 34px;
    height: 34px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
  }

  /* ── STATUS BAR ───────────────────────────────── */
  .status-bar {
    display: flex;
    gap: 2rem;
    padding: 1.2rem 0;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    margin-bottom: 4rem;
  }

  .stat {
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .stat-val {
    font-family: var(--mono);
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--text);
    line-height: 1;
  }

  .stat-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.12em;
    color: var(--muted);
    text-transform: uppercase;
  }

  .stat-divider {
    width: 1px;
    background: var(--border);
    align-self: stretch;
  }

  .status-dot {
    display: inline-block;
    width: 6px;
    height: 6px;
    background: var(--accent);
    border-radius: 50%;
    margin-right: 6px;
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  /* ── SECTION HEADER ───────────────────────────── */
  .section-head {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-bottom: 2rem;
  }

  .section-head h2 {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 0.18em;
    color: var(--muted);
    text-transform: uppercase;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .section-num {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--accent);
    opacity: 0.6;
  }

  /* ── SKILLS ───────────────────────────────────── */
  .skills-section { margin-bottom: 4.5rem; }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 1rem;
  }

  .skill-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1rem 1.1rem;
    transition: border-color 0.2s, transform 0.2s;
    cursor: default;
  }

  .skill-card:hover {
    border-color: var(--accent);
    transform: translateY(-2px);
  }

  .skill-card:hover .skill-bar-fill { opacity: 1; }

  .skill-name {
    font-family: var(--mono);
    font-size: 0.78rem;
    color: var(--text);
    margin-bottom: 0.7rem;
    display: flex;
    justify-content: space-between;
  }

  .skill-level {
    font-size: 0.7rem;
    color: var(--accent);
  }

  .skill-track {
    height: 2px;
    background: var(--border);
    border-radius: 1px;
    overflow: hidden;
  }

  .skill-bar-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--accent), var(--accent3));
    border-radius: 1px;
    opacity: 0.7;
    transition: opacity 0.2s;
  }

  /* ── PROJECTS ─────────────────────────────────── */
  .projects-section { margin-bottom: 4.5rem; }

  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    border: 1px solid var(--border);
    background: var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .project-card {
    background: var(--bg2);
    padding: 1.4rem 1.5rem;
    text-decoration: none;
    color: inherit;
    display: block;
    transition: background 0.2s;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 0;
    background: var(--accent);
    transition: height 0.3s ease;
  }

  .project-card:hover { background: var(--bg3); }
  .project-card:hover::before { height: 100%; }

  .project-lang {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    font-family: var(--mono);
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.08em;
    margin-bottom: 0.7rem;
  }

  .lang-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }
  .lang-cpp { background: #f34b7d; }
  .lang-py  { background: #3572A5; }
  .lang-jnb { background: #DA5B0B; }
  .lang-html{ background: #e34c26; }

  .project-name {
    font-family: var(--display);
    font-size: 1rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 0.5rem;
    letter-spacing: -0.01em;
  }

  .project-desc {
    font-family: var(--mono);
    font-size: 0.73rem;
    color: var(--muted);
    line-height: 1.7;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .project-footer {
    margin-top: 1rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .project-tag {
    font-family: var(--mono);
    font-size: 9px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 2px 8px;
    border-radius: 2px;
    background: rgba(0,245,196,0.07);
    color: var(--accent);
    border: 1px solid rgba(0,245,196,0.15);
  }

  /* ── FOCUS ────────────────────────────────────── */
  .focus-section { margin-bottom: 4.5rem; }

  .focus-items {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
  }

  .focus-item {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1.2rem;
    transition: border-color 0.2s;
  }

  .focus-item:hover { border-color: var(--accent3); }

  .focus-icon {
    font-size: 1.4rem;
    margin-bottom: 0.7rem;
  }

  .focus-title {
    font-family: var(--display);
    font-size: 0.88rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 0.4rem;
  }

  .focus-desc {
    font-family: var(--mono);
    font-size: 0.7rem;
    color: var(--muted);
    line-height: 1.7;
  }

  /* ── FOOTER ───────────────────────────────────── */
  .footer {
    border-top: 1px solid var(--border);
    padding: 2rem 0;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 2rem;
  }

  .footer-name {
    font-family: var(--mono);
    font-size: 0.78rem;
    color: var(--muted);
  }

  .footer-link {
    font-family: var(--mono);
    font-size: 0.78rem;
    color: var(--accent);
    text-decoration: none;
    letter-spacing: 0.06em;
    display: flex;
    align-items: center;
    gap: 6px;
    transition: opacity 0.2s;
  }

  .footer-link:hover { opacity: 0.7; }

  /* ── TYPEWRITER ───────────────────────────────── */
  #typed-text::after {
    content: '|';
    color: var(--accent);
    animation: blink 0.8s step-end infinite;
  }

  @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

  /* ── REVEAL ───────────────────────────────────── */
  .reveal {
    opacity: 0;
    transform: translateY(18px);
    transition: opacity 0.55s ease, transform 0.55s ease;
  }

  .reveal.in { opacity: 1; transform: none; }

  @media (max-width: 640px) {
    .hero { grid-template-columns: 1fr; }
    .avatar-wrap { display: none; }
    .projects-grid { grid-template-columns: 1fr; }
    .focus-items { grid-template-columns: 1fr; }
    .status-bar { flex-wrap: wrap; gap: 1rem; }
  }
</style>
</head>
<body>

<div class="container">

  <!-- HERO -->
  <section class="hero">
    <div class="hero-left">
      <div class="hero-label">Portfolio · HamdanTariq26</div>
      <h1>
        Hamdan<br>
        <span id="typed-text"></span>
      </h1>
      <p class="hero-bio">
        <strong>C++ systems developer</strong> building with performance in mind.<br>
        Exploring the intersection of <strong>machine learning</strong>, graphics
        programming with <strong>OpenGL</strong>, and low-level systems design.
        Clean code, real-world impact.
      </p>
    </div>
    <div class="avatar-wrap">
      <div class="avatar-ring">
        <img
          src="https://avatars.githubusercontent.com/u/191759938?v=4"
          alt="Hamdan Tariq"
          onerror="this.style.display='none'; this.parentElement.innerHTML='<div style=\'width:100%;height:100%;border-radius:50%;background:#141929;display:flex;align-items:center;justify-content:center;font-family:Syne,sans-serif;font-size:2.4rem;font-weight:800;color:#00f5c4\'>HT</div>'"
        >
      </div>
      <div class="avatar-badge">🎯</div>
    </div>
  </section>

  <!-- STATUS BAR -->
  <div class="status-bar reveal">
    <div class="stat">
      <div class="stat-val">6</div>
      <div class="stat-label">Repositories</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat">
      <div class="stat-val">C++</div>
      <div class="stat-label">Primary Lang</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat">
      <div class="stat-val">AI / ML</div>
      <div class="stat-label">Focus Area</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat">
      <div class="stat-val"><span class="status-dot"></span>Active</div>
      <div class="stat-label">Status</div>
    </div>
  </div>

  <!-- SKILLS -->
  <section class="skills-section reveal">
    <div class="section-head">
      <div class="section-num">01</div>
      <h2>Tech Stack</h2>
      <div class="section-line"></div>
    </div>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-name">C++ <span class="skill-level">Expert</span></div>
        <div class="skill-track"><div class="skill-bar-fill" style="width:88%"></div></div>
      </div>
      <div class="skill-card">
        <div class="skill-name">Python / TensorFlow <span class="skill-level">Intermediate</span></div>
        <div class="skill-track"><div class="skill-bar-fill" style="width:70%"></div></div>
      </div>
      <div class="skill-card">
        <div class="skill-name">OpenGL <span class="skill-level">Learning</span></div>
        <div class="skill-track"><div class="skill-bar-fill" style="width:45%"></div></div>
      </div>
      <div class="skill-card">
        <div class="skill-name">Qt Framework <span class="skill-level">Proficient</span></div>
        <div class="skill-track"><div class="skill-bar-fill" style="width:65%"></div></div>
      </div>
      <div class="skill-card">
        <div class="skill-name">ASIO Networking <span class="skill-level">Proficient</span></div>
        <div class="skill-track"><div class="skill-bar-fill" style="width:60%"></div></div>
      </div>
      <div class="skill-card">
        <div class="skill-name">Deep Learning <span class="skill-level">Learning</span></div>
        <div class="skill-track"><div class="skill-bar-fill" style="width:55%"></div></div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="projects-section reveal">
    <div class="section-head">
      <div class="section-num">02</div>
      <h2>Projects</h2>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">

      <a class="project-card" href="https://github.com/HamdanTariq26/Chat-Me" target="_blank">
        <div class="project-lang">
          <span class="lang-dot lang-cpp"></span> C++
        </div>
        <div class="project-name">Chat-Me</div>
        <div class="project-desc">LAN chat application built with ASIO, featuring async client/server architecture for real-time communication.</div>
        <div class="project-footer">
          <span class="project-tag">Networking</span>
          <span class="project-tag">Async</span>
        </div>
      </a>

      <a class="project-card" href="https://github.com/HamdanTariq26/Character-recognition" target="_blank">
        <div class="project-lang">
          <span class="lang-dot lang-jnb"></span> Jupyter Notebook
        </div>
        <div class="project-name">Character Recognition</div>
        <div class="project-desc">Deep learning letter recognition system using TensorFlow and Keras, classifying handwritten characters from image data.</div>
        <div class="project-footer">
          <span class="project-tag">Deep Learning</span>
          <span class="project-tag">CV</span>
        </div>
      </a>

      <a class="project-card" href="https://github.com/HamdanTariq26/Conditional-Multimodal-MRI-Synthesis-and-Brain-Tumor-Segmentation" target="_blank">
        <div class="project-lang">
          <span class="lang-dot lang-jnb"></span> Jupyter Notebook
        </div>
        <div class="project-name">MRI Synthesis & Segmentation</div>
        <div class="project-desc">Dual-model system: ResNet U-Net for brain tumor segmentation + Conditional Diffusion Model for 4-modality MRI synthesis. Trained on TPU.</div>
        <div class="project-footer">
          <span class="project-tag">Medical AI</span>
          <span class="project-tag">DDPM</span>
        </div>
      </a>

      <a class="project-card" href="https://github.com/HamdanTariq26/My-Calculator" target="_blank">
        <div class="project-lang">
          <span class="lang-dot lang-cpp"></span> C++
        </div>
        <div class="project-name">My Calculator</div>
        <div class="project-desc">Lightweight desktop calculator with Qt Creator framework, supporting bracket and complex expression evaluation.</div>
        <div class="project-footer">
          <span class="project-tag">Qt</span>
          <span class="project-tag">Desktop</span>
        </div>
      </a>

      <a class="project-card" href="https://github.com/HamdanTariq26/supply-chain-pro" target="_blank">
        <div class="project-lang">
          <span class="lang-dot lang-html"></span> HTML
        </div>
        <div class="project-name">SupplyChain Pro</div>
        <div class="project-desc">Blockchain-based traceability platform using Hyperledger Fabric and IoT sensors for real-time, tamper-proof product tracking.</div>
        <div class="project-footer">
          <span class="project-tag">Blockchain</span>
          <span class="project-tag">IoT</span>
        </div>
      </a>

      <a class="project-card" href="https://github.com/HamdanTariq26/Robotic-Hand" target="_blank">
        <div class="project-lang">
          <span class="lang-dot lang-cpp"></span> C++
        </div>
        <div class="project-name">Robotic Hand</div>
        <div class="project-desc">Hardware-software robotic hand control system implemented in C++ for precise actuator and servo coordination.</div>
        <div class="project-footer">
          <span class="project-tag">Robotics</span>
          <span class="project-tag">C++</span>
        </div>
      </a>

    </div>
  </section>

  <!-- CURRENTLY EXPLORING -->
  <section class="focus-section reveal">
    <div class="section-head">
      <div class="section-num">03</div>
      <h2>Currently Exploring</h2>
      <div class="section-line"></div>
    </div>
    <div class="focus-items">
      <div class="focus-item">
        <div class="focus-icon">🧠</div>
        <div class="focus-title">Machine Learning</div>
        <div class="focus-desc">Building neural networks, working with TensorFlow and diffusion models for real-world applications.</div>
      </div>
      <div class="focus-item">
        <div class="focus-icon">🎮</div>
        <div class="focus-title">Graphics Programming</div>
        <div class="focus-desc">Learning OpenGL fundamentals — rendering pipelines, shaders, and GPU-accelerated computation.</div>
      </div>
      <div class="focus-item">
        <div class="focus-icon">⚡</div>
        <div class="focus-title">Systems Performance</div>
        <div class="focus-desc">Low-level C++ optimisation, async I/O with ASIO, and writing code that scales efficiently.</div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer reveal">
    <div class="footer-name">Hamdan Tariq · HamdanTariq26</div>
    <a class="footer-link" href="https://github.com/HamdanTariq26" target="_blank">
      github.com/HamdanTariq26 →
    </a>
  </footer>

</div>

<script>
  // Typewriter
  const words = ['Tariq.', 'Builder.', 'Learner.'];
  let wi = 0, ci = 0, del = false;
  const el = document.getElementById('typed-text');

  function type() {
    const word = words[wi];
    if (!del) {
      el.textContent = word.slice(0, ++ci);
      if (ci === word.length) { del = true; return setTimeout(type, 1800); }
    } else {
      el.textContent = word.slice(0, --ci);
      if (ci === 0) { del = false; wi = (wi + 1) % words.length; }
    }
    setTimeout(type, del ? 60 : 95);
  }
  type();

  // Reveal on scroll
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('in'); });
  }, { threshold: 0.12 });

  document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
</script>

</body>
</html>
