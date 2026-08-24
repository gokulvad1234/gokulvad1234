<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Gokul Raj — Data Scientist</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@400;500;600;700;800&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#090c11;
    --panel:#10151d;
    --panel-alt:#141b25;
    --border:#212a35;
    --text:#e9eef4;
    --muted:#8493a6;
    --cyan:#49d3ff;
    --magenta:#ff3ea5;
    --lime:#c3ff5c;
    --amber:#ffb84d;
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
  ::selection{background:var(--magenta); color:#0a0a0a;}

  .bg-grid{
    position:fixed; inset:0; z-index:0; pointer-events:none;
    background-image:
      linear-gradient(rgba(73,211,255,0.045) 1px, transparent 1px),
      linear-gradient(90deg, rgba(73,211,255,0.045) 1px, transparent 1px);
    background-size:42px 42px;
    mask-image: radial-gradient(ellipse 80% 60% at 50% 0%, black 40%, transparent 90%);
  }

  .wrap{max-width:1080px; margin:0 auto; padding:0 28px; position:relative; z-index:1;}

  h1,h2,h3{font-family:'Sora', sans-serif;}
  .mono{font-family:'JetBrains Mono', monospace;}

  /* NAV */
  nav{
    position:fixed; top:0; left:0; right:0; z-index:50;
    background:rgba(9,12,17,0.82); backdrop-filter:blur(10px);
    border-bottom:1px solid var(--border);
  }
  nav .wrap{display:flex; align-items:center; justify-content:space-between; padding:16px 28px;}
  .logo{font-family:'JetBrains Mono', monospace; font-weight:700; font-size:15px; color:var(--text); letter-spacing:0.5px;}
  .logo span{color:var(--lime);}
  .navlinks{display:flex; gap:32px; list-style:none;}
  .navlinks a{color:var(--muted); text-decoration:none; font-size:14px; font-weight:500; transition:color .2s;}
  .navlinks a:hover{color:var(--cyan);}
  .nav-cta{
    font-family:'JetBrains Mono', monospace; font-size:13px; font-weight:600;
    color:var(--bg); background:var(--lime); padding:9px 18px; border-radius:5px;
    text-decoration:none; border:1px solid var(--lime);
  }
  @media(max-width:760px){ .navlinks{display:none;} }

  /* HERO */
  header.hero{
    position:relative; padding:168px 0 100px; overflow:hidden;
  }
  .badge-row{display:flex; gap:10px; align-items:center; margin-bottom:26px; flex-wrap:wrap;}
  .otw{
    display:inline-flex; align-items:center; gap:7px;
    font-family:'JetBrains Mono', monospace; font-size:12px; font-weight:600;
    color:var(--lime); border:1px solid rgba(195,255,92,0.35); background:rgba(195,255,92,0.06);
    padding:6px 12px; border-radius:20px; letter-spacing:0.3px;
  }
  .otw .dot{width:6px; height:6px; border-radius:50%; background:var(--lime); box-shadow:0 0 8px var(--lime); animation:pulse 1.8s infinite;}
  @keyframes pulse{0%,100%{opacity:1;} 50%{opacity:.3;}}
  .loc{font-family:'JetBrains Mono', monospace; font-size:12px; color:var(--muted); border:1px solid var(--border); padding:6px 12px; border-radius:20px;}

  .eyebrow{
    font-family:'JetBrains Mono', monospace; color:var(--cyan); font-size:14px; margin-bottom:14px;
    display:flex; align-items:center; gap:10px;
  }
  .eyebrow::before{content:'>'; color:var(--magenta); font-weight:700;}

  h1.name{
    font-size:clamp(46px, 8vw, 86px); font-weight:800; line-height:1.02; letter-spacing:-2px;
    background:linear-gradient(100deg, #ffffff 30%, var(--cyan) 70%, var(--magenta) 100%);
    -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent;
    margin-bottom:8px;
  }
  .role-line{
    font-family:'JetBrains Mono', monospace; font-size:clamp(17px,2.6vw,22px); font-weight:500;
    color:var(--muted); margin-bottom:28px; min-height:30px;
  }
  .role-line .cursor{color:var(--lime); animation:blink 1s step-end infinite;}
  @keyframes blink{50%{opacity:0;}}

  .hero-desc{max-width:560px; color:var(--muted); font-size:16px; margin-bottom:34px;}
  .hero-desc b{color:var(--text); font-weight:600;}

  .cta-row{display:flex; gap:14px; flex-wrap:wrap; margin-bottom:46px;}
  .btn{
    font-family:'Inter',sans-serif; font-weight:600; font-size:14.5px; text-decoration:none;
    padding:13px 24px; border-radius:6px; display:inline-flex; align-items:center; gap:8px;
    transition:transform .15s, box-shadow .15s;
  }
  .btn:hover{transform:translateY(-2px);}
  .btn-primary{background:var(--cyan); color:#04141c; box-shadow:0 0 0 rgba(73,211,255,0.4);}
  .btn-primary:hover{box-shadow:0 8px 24px rgba(73,211,255,0.25);}
  .btn-outline{border:1px solid var(--border); color:var(--text); background:var(--panel);}
  .btn-outline:hover{border-color:var(--magenta); color:var(--magenta);}

  .contact-strip{display:flex; gap:24px; flex-wrap:wrap; font-family:'JetBrains Mono', monospace; font-size:13px; color:var(--muted);}
  .contact-strip a{color:var(--muted); text-decoration:none; display:flex; align-items:center; gap:8px; transition:color .2s;}
  .contact-strip a:hover{color:var(--cyan);}
  .contact-strip svg{width:15px; height:15px; stroke:currentColor; fill:none;}

  section{position:relative; padding:90px 0; z-index:1;}
  .section-tag{
    font-family:'JetBrains Mono', monospace; font-size:13px; color:var(--magenta);
    letter-spacing:1.5px; text-transform:uppercase; margin-bottom:12px;
  }
  .section-title{font-size:clamp(28px,4vw,40px); font-weight:700; margin-bottom:46px; letter-spacing:-1px;}

  /* ABOUT */
  .about-grid{display:grid; grid-template-columns:1.3fr 1fr; gap:50px; align-items:start;}
  .about-grid p{color:var(--muted); margin-bottom:16px; font-size:16px;}
  .about-grid p b{color:var(--text);}
  .facts{background:var(--panel); border:1px solid var(--border); border-radius:10px; padding:26px;}
  .fact{display:flex; justify-content:space-between; padding:12px 0; border-bottom:1px solid var(--border); font-size:14px;}
  .fact:last-child{border-bottom:none;}
  .fact span:first-child{color:var(--muted); font-family:'JetBrains Mono', monospace;}
  .fact span:last-child{color:var(--text); font-weight:600; text-align:right;}
  @media(max-width:800px){.about-grid{grid-template-columns:1fr;}}

  /* SKILLS - dashboard tiles */
  .skills-grid{display:grid; grid-template-columns:repeat(2, 1fr); gap:20px;}
  .skill-card{
    background:var(--panel); border:1px solid var(--border); border-radius:10px; padding:22px 24px;
  }
  .skill-card h4{font-size:13px; font-family:'JetBrains Mono', monospace; color:var(--muted); text-transform:uppercase; letter-spacing:1px; margin-bottom:16px;}
  .skill-row{display:flex; align-items:center; gap:12px; margin-bottom:12px;}
  .skill-row:last-child{margin-bottom:0;}
  .skill-name{width:112px; font-size:13.5px; font-weight:500; flex-shrink:0;}
  .skill-bar{flex:1; height:6px; background:#1b232d; border-radius:4px; overflow:hidden;}
  .skill-fill{height:100%; border-radius:4px;}
  @media(max-width:760px){.skills-grid{grid-template-columns:1fr;}}

  /* SIGNATURE: terminal query */
  .terminal{
    background:#0c1017; border:1px solid var(--border); border-radius:12px; overflow:hidden;
    box-shadow:0 30px 80px -30px rgba(73,211,255,0.15);
  }
  .term-head{
    display:flex; align-items:center; gap:8px; padding:13px 18px; background:var(--panel-alt); border-bottom:1px solid var(--border);
  }
  .term-dot{width:10px; height:10px; border-radius:50%;}
  .term-title{margin-left:10px; font-family:'JetBrains Mono', monospace; font-size:12.5px; color:var(--muted);}
  .term-body{padding:26px 28px; font-family:'JetBrains Mono', monospace; font-size:14px; min-height:260px;}
  .term-line{color:var(--muted); margin-bottom:4px;}
  .term-prompt{color:var(--lime);}
  .term-query{color:var(--cyan);}
  #term-output{margin-top:14px;}
  .result-row{display:grid; grid-template-columns:34px 1fr 90px; gap:14px; padding:7px 0; border-bottom:1px solid #1b232d; opacity:0; animation:rowIn .4s forwards;}
  .result-row:last-child{border-bottom:none;}
  .result-row .idx{color:var(--muted);}
  .result-row .name{color:var(--text);}
  .result-row .lvl{color:var(--amber); text-align:right;}
  @keyframes rowIn{from{opacity:0; transform:translateY(6px);} to{opacity:1; transform:translateY(0);}}
  .term-cursor-line{display:inline-block; width:8px; height:15px; background:var(--lime); margin-left:2px; animation:blink 1s step-end infinite; vertical-align:middle;}

  /* PROJECTS */
  .projects-grid{display:grid; grid-template-columns:repeat(3, 1fr); gap:22px;}
  .proj-card{
    background:var(--panel); border:1px solid var(--border); border-radius:10px; padding:26px; transition:border-color .2s, transform .2s;
  }
  .proj-card:hover{border-color:var(--cyan); transform:translateY(-4px);}
  .proj-num{font-family:'JetBrains Mono', monospace; font-size:12px; color:var(--magenta); margin-bottom:14px;}
  .proj-card h3{font-size:19px; margin-bottom:10px;}
  .proj-card p{color:var(--muted); font-size:14px; margin-bottom:18px;}
  .tag-row{display:flex; gap:8px; flex-wrap:wrap;}
  .tag{font-family:'JetBrains Mono', monospace; font-size:11.5px; color:var(--cyan); background:rgba(73,211,255,0.08); border:1px solid rgba(73,211,255,0.25); padding:4px 9px; border-radius:5px;}
  @media(max-width:900px){.projects-grid{grid-template-columns:1fr;}}

  /* TIMELINE */
  .timeline{border-left:2px solid var(--border); padding-left:32px; margin-left:6px;}
  .tl-item{position:relative; padding-bottom:38px;}
  .tl-item:last-child{padding-bottom:0;}
  .tl-item::before{
    content:''; position:absolute; left:-39px; top:4px; width:12px; height:12px; border-radius:50%;
    background:var(--bg); border:2px solid var(--lime);
  }
  .tl-date{font-family:'JetBrains Mono', monospace; font-size:12.5px; color:var(--lime); margin-bottom:6px;}
  .tl-item h4{font-size:17px; margin-bottom:4px;}
  .tl-item .org{color:var(--muted); font-size:13.5px; margin-bottom:8px;}
  .tl-item p{color:var(--muted); font-size:14px;}

  /* CONTACT / FOOTER */
  .contact-cta{
    background:linear-gradient(135deg, var(--panel), var(--panel-alt));
    border:1px solid var(--border); border-radius:16px; padding:56px; text-align:center;
  }
  .contact-cta h2{font-size:clamp(26px,4vw,38px); margin-bottom:14px;}
  .contact-cta p{color:var(--muted); margin-bottom:30px;}
  .contact-methods{display:flex; justify-content:center; gap:16px; flex-wrap:wrap;}

  footer{text-align:center; padding:36px 0; color:var(--muted); font-family:'JetBrains Mono', monospace; font-size:12.5px; border-top:1px solid var(--border);}
  footer .dot{color:var(--magenta);}

  @media(max-width:600px){
    .term-body{font-size:12px;}
    .result-row{grid-template-columns:24px 1fr 60px; gap:8px;}
    .contact-cta{padding:34px 22px;}
  }
</style>
</head>
<body>

<div class="bg-grid"></div>

<nav>
  <div class="wrap">
    <div class="logo">GOKUL<span>.</span>RAJ</div>
    <ul class="navlinks">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#experience">Experience</a></li>
    </ul>
    <a class="nav-cta" href="#contact">Contact</a>
  </div>
</nav>

<header class="hero">
  <div class="wrap">
    <div class="badge-row">
      <span class="otw"><span class="dot"></span>OPEN TO WORK</span>
      <span class="loc">📍 Bengaluru, Karnataka, India</span>
    </div>
    <div class="eyebrow">whoami</div>
    <h1 class="name">Gokul Raj</h1>
    <div class="role-line"><span id="typed-role"></span><span class="cursor">|</span></div>
    <p class="hero-desc">
      I turn raw, messy data into <b>clear decisions</b> — building models, dashboards and pipelines
      with <b>Python, SQL and Power BI</b>. Currently sharpening my edge in Machine Learning while
      hunting for a Data Science / Data Analyst role where I can ship real impact from day one.
    </p>
    <div class="cta-row">
      <a class="btn btn-primary" href="mailto:graj58285@gmail.com">Hire Me — Email</a>
      <a class="btn btn-outline" href="https://www.linkedin.com/in/gokul-raj-2b8796280/" target="_blank" rel="noopener">View LinkedIn</a>
    </div>
    <div class="contact-strip">
      <a href="mailto:graj58285@gmail.com">
        <svg viewBox="0 0 24 24" stroke-width="2"><path d="M4 4h16v16H4z"/><path d="m4 6 8 7 8-7"/></svg>
        graj58285@gmail.com
      </a>
      <a href="tel:+919944998210">
        <svg viewBox="0 0 24 24" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.362 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.338 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
        +91 99449 98210
      </a>
      <a href="https://www.linkedin.com/in/gokul-raj-2b8796280/" target="_blank" rel="noopener">
        <svg viewBox="0 0 24 24" stroke-width="2"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
        linkedin.com/in/gokul-raj
      </a>
    </div>
  </div>
</header>

<section id="about">
  <div class="wrap">
    <div class="section-tag">01 · Profile</div>
    <h2 class="section-title">About Me</h2>
    <div class="about-grid">
      <div>
        <p>I'm a data-driven problem solver based in Bengaluru, focused on the full loop of <b>analysis → modeling → visualization</b>. I like working close to real datasets: cleaning them, questioning them, and turning them into dashboards or models that people actually use to make decisions.</p>
        <p>My core toolkit is <b>Python and SQL</b> for analysis and automation, <b>Power BI</b> for storytelling with data, and I'm actively deepening my <b>Machine Learning</b> skills — moving from analyst-style reporting into predictive, model-driven work.</p>
        <p>I trained at <b>QSpiders — Software Testing Training Institute</b>, which shaped how I think about quality, edge cases and structured problem-solving — habits I now bring into data science work.</p>
      </div>
      <div class="facts">
        <div class="fact"><span>role</span><span>Data Scientist</span></div>
        <div class="fact"><span>focus</span><span>Data Analysis · AI/ML</span></div>
        <div class="fact"><span>location</span><span>Bengaluru, India</span></div>
        <div class="fact"><span>status</span><span style="color:var(--lime)">Open to work</span></div>
        <div class="fact"><span>mode</span><span>On-site · Hybrid</span></div>
        <div class="fact"><span>network</span><span>109+ connections</span></div>
      </div>
    </div>
  </div>
</section>

<section id="skills">
  <div class="wrap">
    <div class="section-tag">02 · Toolkit</div>
    <h2 class="section-title">Skills &amp; Stack</h2>
    <div class="skills-grid">
      <div class="skill-card">
        <h4>Languages &amp; Query</h4>
        <div class="skill-row"><span class="skill-name">Python</span><div class="skill-bar"><div class="skill-fill" style="width:88%; background:var(--cyan);"></div></div></div>
        <div class="skill-row"><span class="skill-name">SQL</span><div class="skill-bar"><div class="skill-fill" style="width:85%; background:var(--cyan);"></div></div></div>
      </div>
      <div class="skill-card">
        <h4>Analytics &amp; BI</h4>
        <div class="skill-row"><span class="skill-name">Power BI</span><div class="skill-bar"><div class="skill-fill" style="width:82%; background:var(--amber);"></div></div></div>
        <div class="skill-row"><span class="skill-name">Excel</span><div class="skill-bar"><div class="skill-fill" style="width:80%; background:var(--amber);"></div></div></div>
      </div>
      <div class="skill-card">
        <h4>Machine Learning</h4>
        <div class="skill-row"><span class="skill-name">scikit-learn</span><div class="skill-bar"><div class="skill-fill" style="width:70%; background:var(--magenta);"></div></div></div>
        <div class="skill-row"><span class="skill-name">Pandas / NumPy</span><div class="skill-bar"><div class="skill-fill" style="width:80%; background:var(--magenta);"></div></div></div>
      </div>
      <div class="skill-card">
        <h4>Foundations</h4>
        <div class="skill-row"><span class="skill-name">Statistics</span><div class="skill-bar"><div class="skill-fill" style="width:72%; background:var(--lime);"></div></div></div>
        <div class="skill-row"><span class="skill-name">Data Cleaning</span><div class="skill-bar"><div class="skill-fill" style="width:86%; background:var(--lime);"></div></div></div>
      </div>
    </div>
  </div>
</section>

<section id="query">
  <div class="wrap">
    <div class="section-tag">03 · Run the query</div>
    <h2 class="section-title">What I bring to the table</h2>
    <div class="terminal">
      <div class="term-head">
        <div class="term-dot" style="background:#ff5f57;"></div>
        <div class="term-dot" style="background:#febc2e;"></div>
        <div class="term-dot" style="background:#28c840;"></div>
        <div class="term-title">gokul_raj — analytics.sql</div>
      </div>
      <div class="term-body">
        <div class="term-line"><span class="term-prompt">gokul@portfolio</span>:~$ <span id="query-text"></span></div>
        <div id="term-output"></div>
      </div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="wrap">
    <div class="section-tag">04 · Selected Work</div>
    <h2 class="section-title">Projects</h2>
    <div class="projects-grid">
      <div class="proj-card">
        <div class="proj-num">01</div>
        <h3>Project Title Here</h3>
        <p>Swap this in for a real project — e.g. a churn prediction model, sales dashboard, or an EDA deep-dive with clear before/after impact.</p>
        <div class="tag-row"><span class="tag">Python</span><span class="tag">Pandas</span><span class="tag">scikit-learn</span></div>
      </div>
      <div class="proj-card">
        <div class="proj-num">02</div>
        <h3>Project Title Here</h3>
        <p>A Power BI dashboard project — describe the business question, the data source, and the decision it enabled.</p>
        <div class="tag-row"><span class="tag">Power BI</span><span class="tag">SQL</span><span class="tag">DAX</span></div>
      </div>
      <div class="proj-card">
        <div class="proj-num">03</div>
        <h3>Project Title Here</h3>
        <p>An ML/AI mini-project — model type, dataset, accuracy/metric achieved, and what you learned building it.</p>
        <div class="tag-row"><span class="tag">Machine Learning</span><span class="tag">NumPy</span><span class="tag">Jupyter</span></div>
      </div>
    </div>
  </div>
</section>

<section id="experience">
  <div class="wrap">
    <div class="section-tag">05 · Journey</div>
    <h2 class="section-title">Experience &amp; Training</h2>
    <div class="timeline">
      <div class="tl-item">
        <div class="tl-date">CURRENT</div>
        <h4>Data Science &amp; AI/ML Upskilling</h4>
        <div class="org">Self-directed + project-based learning</div>
        <p>Deepening Machine Learning fundamentals while applying Python, SQL and Power BI to real datasets.</p>
      </div>
      <div class="tl-item">
        <div class="tl-date">TRAINING</div>
        <h4>Software Testing &amp; QA Foundations</h4>
        <div class="org">QSpiders — Software Testing Training Institute</div>
        <p>Built a strong base in structured problem-solving and quality-first thinking, now applied to data validation and analysis workflows.</p>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="wrap">
    <div class="contact-cta">
      <h2>Let's turn your data into decisions.</h2>
      <p>Open to Data Science, Data Analyst and ML opportunities in Bengaluru — on-site or hybrid.</p>
      <div class="contact-methods">
        <a class="btn btn-primary" href="mailto:graj58285@gmail.com">graj58285@gmail.com</a>
        <a class="btn btn-outline" href="tel:+919944998210">+91 99449 98210</a>
        <a class="btn btn-outline" href="https://www.linkedin.com/in/gokul-raj-2b8796280/" target="_blank" rel="noopener">LinkedIn Profile</a>
      </div>
    </div>
  </div>
</section>

<footer>
  Built by Gokul Raj <span class="dot">·</span> Bengaluru, India <span class="dot">·</span> 2026
</footer>

<script>
  // Role typing animation
  const roles = ["Data Scientist", "Data Analyst", "AI/ML Enthusiast", "Power BI Developer"];
  const typedEl = document.getElementById('typed-role');
  let ri = 0, ci = 0, deleting = false;

  function typeLoop(){
    const current = roles[ri];
    if(!deleting){
      ci++;
      typedEl.textContent = current.slice(0, ci);
      if(ci === current.length){ deleting = true; setTimeout(typeLoop, 1400); return; }
    } else {
      ci--;
      typedEl.textContent = current.slice(0, ci);
      if(ci === 0){ deleting = false; ri = (ri+1) % roles.length; }
    }
    setTimeout(typeLoop, deleting ? 40 : 75);
  }
  typeLoop();

  // Terminal query animation
  const queryStr = "SELECT skill, level FROM gokul_raj.expertise ORDER BY level DESC;";
  const queryEl = document.getElementById('query-text');
  const outputEl = document.getElementById('term-output');
  const results = [
    ["Python", "Advanced"],
    ["SQL", "Advanced"],
    ["Power BI", "Advanced"],
    ["Machine Learning", "Growing"],
    ["Statistics", "Solid"]
  ];

  function typeQuery(i, cb){
    if(i <= queryStr.length){
      queryEl.textContent = queryStr.slice(0, i);
      setTimeout(()=>typeQuery(i+1, cb), 18);
    } else { cb(); }
  }

  function runQueryAnimation(){
    queryEl.textContent = '';
    outputEl.innerHTML = '';
    typeQuery(0, () => {
      setTimeout(() => {
        const header = document.createElement('div');
        header.className = 'result-row';
        header.style.animation = 'none'; header.style.opacity = 1;
        header.style.color = 'var(--muted)';
        header.innerHTML = `<span class="idx">#</span><span class="name">skill</span><span class="lvl">level</span>`;
        outputEl.appendChild(header);
        results.forEach((r, idx) => {
          setTimeout(() => {
            const row = document.createElement('div');
            row.className = 'result-row';
            row.style.animationDelay = '0s';
            row.innerHTML = `<span class="idx">${idx+1}</span><span class="name">${r[0]}</span><span class="lvl">${r[1]}</span>`;
            outputEl.appendChild(row);
          }, idx * 260);
        });
        setTimeout(() => {
          const done = document.createElement('div');
          done.className = 'term-line';
          done.style.marginTop = '14px';
          done.innerHTML = `${results.length} rows returned <span class="term-cursor-line"></span>`;
          outputEl.appendChild(done);
        }, results.length * 260 + 200);
      }, 300);
    });
  }

  const termObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if(entry.isIntersecting){ runQueryAnimation(); termObserver.disconnect(); }
    });
  }, { threshold: 0.4 });
  termObserver.observe(document.getElementById('query'));
</script>

</body>
</html>
