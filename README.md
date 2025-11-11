<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Samuel | Tech & Nerd Hub</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Montserrat:wght@300;600&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0b0f1a;
      --panel:#11162a;
      --accent:#00e0ff;
      --accent2:#7cffb2;
      --text:#e6f0ff;
      --muted:#9bb3d6;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      background: radial-gradient(1200px 600px at 10% 10%, rgba(0,224,255,0.08), transparent 60%),
                  radial-gradient(900px 500px at 90% 80%, rgba(124,255,178,0.08), transparent 60%),
                  var(--bg);
      color:var(--text);
      font-family: Montserrat, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, sans-serif;
      overflow-x:hidden;
    }

    /* Neon scanline glow */
    .scanline::before{
      content:"";
      position:fixed; inset:0;
      background: repeating-linear-gradient(
        to bottom,
        rgba(255,255,255,0.05) 0px,
        rgba(255,255,255,0.05) 1px,
        transparent 2px,
        transparent 4px
      );
      mix-blend-mode: soft-light;
      pointer-events:none;
    }

    /* Header */
    header{
      position:relative;
      padding:48px 24px 24px;
      display:flex; align-items:center; justify-content:space-between;
    }
    .brand{
      display:flex; align-items:center; gap:12px;
      text-transform:uppercase;
      letter-spacing:2px;
      font-family: Orbitron, monospace;
    }
    .logo{
      width:40px; height:40px; border-radius:8px;
      background:
        conic-gradient(from 200deg, var(--accent), var(--accent2), var(--accent), var(--accent2));
      filter: drop-shadow(0 0 8px rgba(0,224,255,0.7));
      animation: spin 8s linear infinite;
    }
    @keyframes spin{to{transform:rotate(360deg)}}

    nav a{
      color:var(--muted); text-decoration:none; margin:0 10px; font-weight:600;
      border-bottom:2px solid transparent; padding-bottom:4px;
    }
    nav a:hover{color:var(--text); border-color:var(--accent)}

    /* Hero */
    .hero{
      padding:40px 24px 60px;
      display:grid; grid-template-columns: 1.1fr 0.9fr; gap:24px;
    }
    .card{
      background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));
      border:1px solid rgba(124,255,178,0.2);
      border-radius:16px; padding:24px; backdrop-filter: blur(6px);
      box-shadow: 0 20px 60px rgba(0,0,0,0.5), 0 0 20px rgba(0,224,255,0.18);
    }
    .title{
      font-family: Orbitron, monospace;
      font-size: clamp(28px, 4.5vw, 48px);
      margin:0 0 10px;
    }
    .subtitle{color:var(--muted); margin:0 0 20px}
    .badges{display:flex; flex-wrap:wrap; gap:10px; margin-top:16px}
    .badge{
      border:1px solid rgba(0,224,255,0.35);
      color:var(--accent);
      padding:8px 12px; border-radius:999px; font-size:14px; font-weight:600;
      background: rgba(0,224,255,0.06);
    }

    /* Animated binary rain */
    .matrix{
      position:relative; min-height:280px; border-radius:16px; overflow:hidden;
      background: #0a1224; border:1px solid rgba(0,224,255,0.15);
    }
    .stream{
      position:absolute; top:-100%; width:2px; background: linear-gradient(to bottom, transparent, var(--accent));
      box-shadow: 0 0 8px rgba(0,224,255,0.8);
      animation: fall linear infinite;
      opacity:0.8;
    }
    @keyframes fall{
      0%{transform:translateY(-120%)}
      100%{transform:translateY(220%)}
    }

    /* Sections */
    section{padding:24px}
    h2{
      font-family: Orbitron, monospace; font-size:22px; margin:0 0 12px;
      border-left:4px solid var(--accent); padding-left:10px;
    }
    .grid{display:grid; grid-template-columns: repeat(3, 1fr); gap:16px}
    .tile{
      background: var(--panel); border:1px solid rgba(255,255,255,0.08);
      padding:16px; border-radius:12px;
      transition: transform 200ms ease, box-shadow 200ms ease;
    }
    .tile:hover{transform: translateY(-4px); box-shadow: 0 12px 24px rgba(0,0,0,0.35)}

    /* Footer */
    footer{
      padding:20px 24px 40px; color:var(--muted); font-size:14px;
      display:flex; justify-content:space-between; align-items:center;
    }
    .pulse{
      display:inline-block; width:8px; height:8px; border-radius:50%;
      background: var(--accent2);
      box-shadow: 0 0 10px var(--accent2);
      animation: pulse 1.4s ease-in-out infinite;
    }
    @keyframes pulse{
      0%{transform:scale(0.9); opacity:0.8}
      50%{transform:scale(1.2); opacity:1}
      100%{transform:scale(0.9); opacity:0.8}
    }

    /* Responsiveness */
    @media (max-width: 900px){
      .hero{grid-template-columns: 1fr}
      .grid{grid-template-columns: 1fr 1fr}
    }
    @media (max-width: 600px){
      nav{display:none}
      .grid{grid-template-columns: 1fr}
    }

    /* Fancy accent underline */
    .accent-underline{
      position:relative; display:inline-block;
    }
    .accent-underline::after{
      content:""; position:absolute; left:0; bottom:-6px; height:2px; width:100%;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      box-shadow: 0 0 10px rgba(0,224,255,0.6);
    }
  </style>
</head>
<body class="scanline">
  <header>
    <div class="brand">
      <div class="logo" aria-hidden="true"></div>
      <div>Samuel.tech</div>
    </div>
    <nav aria-label="primary">
      <a href="#about">About</a>
      <a href="#stack">Stack</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <main>
    <div class="hero">
      <div class="card">
        <h1 class="title">Hi, I'm <span class="accent-underline">Samuel</span> — Tech Explorer</h1>
        <p class="subtitle">
          I'm 27 and currently diving deep into IT through a technical course. Every module pushes me further into the world of systems, networks, and code — and I love it.
        </p>
        <div class="badges">
          <span class="badge">IT Student</span>
          <span class="badge">Nerd Culture</span>
          <span class="badge">Cyberpunk Aesthetics</span>
          <span class="badge">Open Source Spirit</span>
        </div>
      </div>

      <div class="matrix" aria-hidden="true" id="matrix"></div>
    </div>

    <section id="about" class="card" style="margin:0 24px 24px">
      <h2>About Samuel</h2>
      <p>
        Based in Santo André, São Paulo, I’m building a solid foundation in IT: understanding how computers talk, how networks breathe, and how software evolves from ideas into tools. I enjoy solving problems with clean logic and a bit of creativity.
      </p>
      <p>
        I’m into nerdy stuff—think Linux terminals, cyberpunk themes, retro consoles, and sci-fi that questions the future. My goal is to become the kind of professional who ships reliable systems and helps people through technology.
      </p>
    </section>

    <section id="stack" style="margin:0 24px">
      <h2>Tech stack and interests</h2>
      <div class="grid">
        <div class="tile">
          <strong>Systems & OS</strong>
          <p>Linux (shell basics), Windows administration, virtualization, and the art of not breaking production.</p>
        </div>
        <div class="tile">
          <strong>Networking</strong>
          <p>TCP/IP fundamentals, subnets, routing, and practical troubleshooting with ping, traceroute, and wireshark vibes.</p>
        </div>
        <div class="tile">
          <strong>Programming</strong>
          <p>Learning Python and JavaScript—writing readable code, testing early, and automating boring tasks.</p>
        </div>
        <div class="tile">
          <strong>Security mindset</strong>
          <p>Basic hardening, least privilege, backups, and thinking like both the defender and the curious hacker.</p>
        </div>
        <div class="tile">
          <strong>Tools I like</strong>
          <p>Git, VS Code, Docker, Postman, and a terminal with neon themes that makes me feel faster.</p>
        </div>
        <div class="tile">
          <strong>Nerd culture</strong>
          <p>Cyberpunk, retro emulators, pixel art, and tech documentaries that make command lines look cinematic.</p>
        </div>
      </div>
    </section>

    <section id="projects" class="card" style="margin:24px">
      <h2>Practice projects</h2>
      <ul>
        <li><strong>Home lab:</strong> A local environment for VMs, Docker containers, and network experiments.</li>
        <li><strong>Automation scripts:</strong> Small Python tools to clean files, check services, and monitor logs.</li>
        <li><strong>Portfolio site:</strong> This page—polished with animations, accessibility, and responsive design.</li>
      </ul>
    </section>

    <section id="contact" class="card" style="margin:24px">
      <h2>Contact</h2>
      <p>
        Want to geek out over infrastructure, scripting, or sci‑fi aesthetics? Reach me and let’s build something cool.
      </p>
      <div style="display:flex; gap:12px; flex-wrap:wrap">
        <a class="badge" href="#" aria-label="Email">Email</a>
        <a class="badge" href="#" aria-label="LinkedIn">LinkedIn</a>
        <a class="badge" href="#" aria-label="GitHub">GitHub</a>
      </div>
    </section>
  </main>

  <footer>
    <div>© 2025 Samuel • Crafted with code and curiosity</div>
    <div><span class="pulse" aria-hidden="true"></span> System online</div>
  </footer>

  <script>
    // Generate animated binary "matrix" streams
    const matrix = document.getElementById('matrix');
    const columns = 28;
    const speedMin = 6, speedMax = 12; // seconds

    function makeStream(x){
      const s = document.createElement('div');
      s.className = 'stream';
      s.style.left = x + 'px';
      const length = Math.random() * 70 + 120; // px
      s.style.height = length + 'px';
      s.style.animationDuration = (Math.random() * (speedMax - speedMin) + speedMin) + 's';
      matrix.appendChild(s);

      // occasional glow pulses
      setInterval(() => {
        s.style.boxShadow = Math.random() > 0.6
          ? '0 0 14px rgba(124,255,178,0.9)'
          : '0 0 8px rgba(0,224,255,0.8)';
      }, 800 + Math.random()*1200);
    }

    function initMatrix(){
      const width = matrix.clientWidth;
      const spacing = width / columns;
      for(let i=0;i<columns;i++){
        const jitter = (Math.random() - 0.5) * spacing * 0.4;
        makeStream(i * spacing + jitter);
      }
      // binary glyphs
      const glyph = document.createElement('div');
      glyph.style.position = 'absolute';
      glyph.style.inset = 0;
      glyph.style.fontFamily = 'Orbitron, monospace';
      glyph.style.color = 'rgba(255,255,255,0.12)';
      glyph.style.pointerEvents = 'none';
      glyph.style.lineHeight = '22px';
      glyph.style.fontSize = '16px';
      glyph.style.padding = '8px';
      glyph.style.whiteSpace = 'pre-wrap';

      function randomBits(rows=16, cols=30){
        let out = '';
        for(let r=0;r<rows;r++){
          for(let c=0;c<cols;c++){
            out += Math.random() > 0.5 ? '1' : '0';
          }
          out += '\n';
        }
        return out;
      }
      glyph.textContent = randomBits();
      matrix.appendChild(glyph);
      setInterval(()=> glyph.textContent = randomBits(), 1200);
    }

    window.addEventListener('load', initMatrix);
  </script>
</body>
</html>
