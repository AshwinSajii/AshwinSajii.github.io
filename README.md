<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ashwin Saji — Cloud Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600;700&family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#000000;
    --panel:#0A0A0A;
    --line:#2A2A2A;
    --text:#D4D4D4;
    --dim:#7A7A7A;
    --white:#FFFFFF;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:'Inter', sans-serif;
    line-height:1.6;
    overflow-x:hidden;
  }
  ::selection{ background:var(--white); color:#000; }
  a{ color:inherit; text-decoration:none; }
  .mono{ font-family:'IBM Plex Mono', monospace; }
  a:focus-visible, button:focus-visible{ outline:2px solid var(--white); outline-offset:3px; }

  .wrap{ max-width:920px; margin:0 auto; padding:0 28px; }

  /* NAV */
  nav{
    position:fixed; top:0; left:0; right:0; z-index:50;
    background:rgba(0,0,0,0.85);
    backdrop-filter:blur(8px);
    border-bottom:1px solid var(--line);
  }
  nav .wrap{ display:flex; align-items:center; justify-content:space-between; height:56px; }
  .nav-id{
    font-family:'IBM Plex Mono', monospace; font-size:13px;
    color:var(--white); display:flex; align-items:center; gap:8px;
  }
  .dot{ width:7px; height:7px; border-radius:50%; background:var(--white); }
  .nav-links{ display:flex; gap:28px; font-family:'IBM Plex Mono', monospace; font-size:12.5px; color:var(--dim); }
  .nav-links a{ transition:color .15s; }
  .nav-links a:hover{ color:var(--white); }
  @media (max-width:600px){ .nav-links{ gap:16px; font-size:11px; } }

  /* HERO */
  header.hero{
    min-height:100vh; display:flex; flex-direction:column; justify-content:center;
    padding-top:56px; position:relative;
  }
  .hero-eyebrow{
    font-family:'IBM Plex Mono', monospace; font-size:12.5px;
    color:var(--dim); letter-spacing:.06em; margin-bottom:18px;
  }
  h1.name{
    font-family:'IBM Plex Mono', monospace; font-weight:700;
    font-size:clamp(38px, 7.5vw, 68px);
    color:var(--white); letter-spacing:-0.01em; line-height:1.05;
  }
  .role-line{ font-size:clamp(17px, 2.6vw, 22px); color:var(--text); margin-top:14px; font-weight:500; }
  .role-line span{ color:var(--dim); }

  .boot-panel{
    margin-top:44px; background:var(--panel); border:1px solid var(--line);
    border-radius:8px; padding:20px 22px; max-width:560px;
    font-family:'IBM Plex Mono', monospace; font-size:13px;
  }
  .boot-panel .bar{ display:flex; gap:6px; margin-bottom:14px; }
  .bar span{ width:9px; height:9px; border-radius:50%; background:var(--line); }
  .boot-line{ display:flex; gap:10px; color:var(--dim); opacity:0; animation:appear .35s forwards; padding:2px 0; }
  .boot-line .ok{ color:var(--white); }
  .boot-line .tag{ color:var(--text); }
  .boot-line:nth-child(2){ animation-delay:.15s; }
  .boot-line:nth-child(3){ animation-delay:.45s; }
  .boot-line:nth-child(4){ animation-delay:.75s; }
  .boot-line:nth-child(5){ animation-delay:1.05s; }
  .boot-line:nth-child(6){
    animation-delay:1.35s; color:var(--white); margin-top:10px; padding-top:10px;
    border-top:1px dashed var(--line);
  }
  @keyframes appear{ to{ opacity:1; } }
  .cursor{
    display:inline-block; width:7px; height:14px; background:var(--white);
    margin-left:2px; animation:blink 1s steps(1) infinite; vertical-align:middle;
  }
  @keyframes blink{ 50%{ opacity:0; } }
  @media (prefers-reduced-motion: reduce){
    .boot-line{ animation:none !important; opacity:1 !important; }
    .cursor{ animation:none; }
  }

  .scroll-hint{ position:absolute; bottom:36px; left:28px; font-family:'IBM Plex Mono', monospace; font-size:11.5px; color:var(--dim); }

  /* SECTIONS */
  section{ padding:90px 0; border-top:1px solid var(--line); }
  .eyebrow{ font-family:'IBM Plex Mono', monospace; font-size:12px; color:var(--dim); letter-spacing:.08em; margin-bottom:10px; }
  h2{ font-size:clamp(26px,4vw,34px); color:var(--white); font-weight:700; margin-bottom:28px; letter-spacing:-0.01em; }

  /* about */
  .about-grid{ display:grid; grid-template-columns:1.3fr 1fr; gap:48px; }
  .about-grid p{ color:var(--text); font-size:15.5px; margin-bottom:14px; }
  .stat-panel{ background:var(--panel); border:1px solid var(--line); border-radius:8px; padding:20px; }
  .stat-row{ display:flex; justify-content:space-between; padding:11px 0; border-bottom:1px solid var(--line); font-size:13.5px; }
  .stat-row:last-child{ border-bottom:none; }
  .stat-row .label{ color:var(--dim); font-family:'IBM Plex Mono', monospace; font-size:12px; }
  .stat-row .val{ color:var(--white); font-weight:600; }
  @media (max-width:720px){ .about-grid{ grid-template-columns:1fr; } }

  /* skills */
  .skill-groups{ display:grid; grid-template-columns:repeat(2, 1fr); gap:16px; }
  .skill-card{ background:var(--panel); border:1px solid var(--line); border-radius:8px; padding:20px; transition:border-color .15s, transform .15s; }
  .skill-card:hover{ border-color:var(--white); transform:translateY(-2px); }
  .skill-card .cat{ font-family:'IBM Plex Mono', monospace; font-size:11.5px; color:var(--white); letter-spacing:.05em; margin-bottom:10px; }
  .skill-card ul{ list-style:none; }
  .skill-card li{ color:var(--text); font-size:14px; padding:3px 0; }
  @media (max-width:600px){ .skill-groups{ grid-template-columns:1fr; } }

  /* projects */
  .project-card{ background:var(--panel); border:1px solid var(--line); border-radius:10px; padding:28px; }
  .project-head{ display:flex; align-items:center; justify-content:space-between; flex-wrap:wrap; gap:10px; margin-bottom:14px; }
  .project-title{ font-family:'IBM Plex Mono', monospace; font-size:19px; color:var(--white); font-weight:600; }
  .project-tag{ font-family:'IBM Plex Mono', monospace; font-size:11px; color:var(--white); border:1px solid var(--line); border-radius:20px; padding:3px 10px; }
  .project-card p{ color:var(--text); font-size:14.5px; margin-bottom:16px; }
  .project-tools{ display:flex; gap:8px; flex-wrap:wrap; margin-bottom:20px; }
  .project-tools span{ font-family:'IBM Plex Mono', monospace; font-size:11.5px; color:var(--dim); background:#000; border:1px solid var(--line); padding:4px 10px; border-radius:5px; }
  .project-link{ font-family:'IBM Plex Mono', monospace; font-size:13px; color:var(--white); border-bottom:1px solid var(--white); padding-bottom:2px; }
  .project-link:hover{ color:var(--dim); border-color:var(--dim); }

  /* certifications */
  .cert-list{ display:flex; flex-direction:column; gap:2px; }
  .cert-row{ display:flex; align-items:center; gap:16px; padding:16px 4px; border-bottom:1px solid var(--line); }
  .cert-row:last-child{ border-bottom:none; }
  .cert-icon{ width:34px; height:34px; flex:none; border:1px solid var(--line); border-radius:6px; display:flex; align-items:center; justify-content:center; font-family:'IBM Plex Mono', monospace; font-size:13px; color:var(--white); }
  .cert-name{ color:var(--white); font-size:15px; font-weight:600; }
  .cert-issuer{ color:var(--dim); font-size:12.5px; font-family:'IBM Plex Mono', monospace; }

  /* contact */
  .contact-panel{ background:var(--panel); border:1px solid var(--line); border-radius:10px; padding:40px; text-align:center; }
  .contact-panel p{ color:var(--dim); margin-bottom:26px; font-size:15px; }
  .contact-links{ display:flex; gap:14px; justify-content:center; flex-wrap:wrap; }
  .contact-links a{ font-family:'IBM Plex Mono', monospace; font-size:13.5px; color:var(--white); border:1px solid var(--line); padding:10px 20px; border-radius:6px; transition:border-color .15s, color .15s; }
  .contact-links a:hover{ border-color:var(--white); color:var(--dim); }

  footer{ text-align:center; padding:32px 0 48px; color:var(--dim); font-family:'IBM Plex Mono', monospace; font-size:11.5px; }
</style>
</head>
<body>

<nav>
  <div class="wrap">
    <div class="nav-id"><span class="dot"></span> ashwin@infra</div>
    <div class="nav-links">
      <a href="#about">about</a>
      <a href="#skills">skills</a>
      <a href="#projects">projects</a>
      <a href="#certs">certs</a>
      <a href="#contact">contact</a>
    </div>
  </div>
</nav>

<header class="hero">
  <div class="wrap">
    <div class="hero-eyebrow">// cloud engineering</div>
    <h1 class="name">ASHWIN SAJI</h1>
    <div class="role-line">Cloud Engineer <span>— Azure Virtual Desktop · DevOps · Terraform · CyberArk PIM</span></div>

    <div class="boot-panel">
      <div class="bar"><span></span><span></span><span></span></div>
      <div class="boot-line"><span class="tag">$</span> checking systems...</div>
      <div class="boot-line"><span class="ok">[OK]</span> Azure Virtual Desktop</div>
      <div class="boot-line"><span class="ok">[OK]</span> Terraform · Azure DevOps</div>
      <div class="boot-line"><span class="ok">[OK]</span> CyberArk PIM · Ansible · Docker</div>
      <div class="boot-line">status: open to new opportunities<span class="cursor"></span></div>
    </div>
  </div>
  <div class="scroll-hint">↓ scroll</div>
</header>

<section id="about">
  <div class="wrap">
    <div class="eyebrow">01 / about</div>
    <h2>Focused on Azure Virtual Desktop.</h2>
    <div class="about-grid">
      <div>
        <p>I'm a Cloud Engineer at TCS, working with Azure Virtual Desktop.</p>
        <p>My core stack includes Azure DevOps, Terraform, and CyberArk PIM for access management, alongside Ansible and Docker for automation and containerization.</p>
        <p>Outside my core role, I build my own tooling — like PatchMgr, an Ansible-based patch management system — to solve real operational problems rather than just ticket them.</p>
      </div>
      <div class="stat-panel mono">
        <div class="stat-row"><span class="label">ROLE</span><span class="val">Cloud Engineer, TCS</span></div>
        <div class="stat-row"><span class="label">EDUCATION</span><span class="val">BCA, Marian College</span></div>
        <div class="stat-row"><span class="label">BASED IN</span><span class="val">India</span></div>
        <div class="stat-row"><span class="label">TARGET CITIES</span><span class="val">Kochi · Blr · Chennai</span></div>
      </div>
    </div>
  </div>
</section>

<section id="skills">
  <div class="wrap">
    <div class="eyebrow">02 / skills</div>
    <h2>Stack</h2>
    <div class="skill-groups">
      <div class="skill-card">
        <div class="cat">CLOUD &amp; VIRTUALIZATION</div>
        <ul><li>Azure Virtual Desktop</li><li>Azure DevOps</li></ul>
      </div>
      <div class="skill-card">
        <div class="cat">IaC &amp; AUTOMATION</div>
        <ul><li>Terraform</li><li>Ansible</li><li>Docker</li></ul>
      </div>
      <div class="skill-card">
        <div class="cat">SECURITY &amp; ACCESS</div>
        <ul><li>CyberArk PIM</li></ul>
      </div>
      <div class="skill-card">
        <div class="cat">EDUCATION</div>
        <ul><li>BCA — Marian College</li></ul>
      </div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="wrap">
    <div class="eyebrow">03 / projects</div>
    <h2>Featured build</h2>
    <div class="project-card">
      <div class="project-head">
        <div class="project-title">PatchMgr</div>
        <div class="project-tag">SELF-INITIATED</div>
      </div>
      <p>An Ansible-based patch management tool built to automate and standardize patching across server environments — reducing manual overhead on a recurring, high-friction operational task.</p>
      <div class="project-tools">
        <span>Ansible</span><span>Linux</span><span>Automation</span>
      </div>
      <a class="project-link" href="https://github.com/yourusername/patchmgr" target="_blank" rel="noopener">view repo →</a>
    </div>
  </div>
</section>

<section id="certs">
  <div class="wrap">
    <div class="eyebrow">04 / certifications</div>
    <h2>Certifications &amp; awards</h2>
    <div class="cert-list">
      <div class="cert-row">
        <div class="cert-icon">AI</div>
        <div>
          <div class="cert-name">Azure AI Fundamentals (AI-900)</div>
          <div class="cert-issuer">Microsoft</div>
        </div>
      </div>
      <div class="cert-row">
        <div class="cert-icon">◎</div>
        <div>
          <div class="cert-name">Ansible Certification</div>
          <div class="cert-issuer">Coursera</div>
        </div>
      </div>
      <div class="cert-row">
        <div class="cert-icon">★</div>
        <div>
          <div class="cert-name">TCS Star Team Award</div>
          <div class="cert-issuer">Tata Consultancy Services</div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="wrap">
    <div class="eyebrow">05 / contact</div>
    <h2>Let's talk infrastructure</h2>
    <div class="contact-panel">
      <p>Open to Cloud Engineer, Infrastructure Engineer, and IT Operations roles — based in India, targeting Kochi, Trivandrum, Bengaluru &amp; Chennai.</p>
      <div class="contact-links">
        <a href="mailto:ashwinsaji017@gmail.com">Email</a>
        <a href="https://linkedin.com/in/yourprofile" target="_blank" rel="noopener">LinkedIn</a>
        <a href="https://github.com/yourusername" target="_blank" rel="noopener">GitHub</a>
      </div>
    </div>
  </div>
</section>

<footer>Ashwin Saji — built with Ansible-grade reliability in mind.</footer>

</body>
</html>
