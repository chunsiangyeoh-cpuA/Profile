<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yeoh Chun Siang — Fund Management Associate</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,400;0,500;0,600;1,400&family=IBM+Plex+Sans:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#0D1B2A;
    --panel:#132A3E;
    --paper:#EDEAE2;
    --paper-dim:#B7C0C9;
    --brass:#B08D57;
    --brass-bright:#D4AF6A;
    --teal:#4A7C6F;
    --rule:rgba(237,234,226,0.14);
    --serif:'Newsreader', serif;
    --sans:'IBM Plex Sans', sans-serif;
    --mono:'IBM Plex Mono', monospace;
  }

  *{margin:0;padding:0;box-sizing:border-box;}

  html{scroll-behavior:smooth;}

  body{
    background:var(--ink);
    color:var(--paper);
    font-family:var(--sans);
    line-height:1.6;
    overflow-x:hidden;
  }

  @media (prefers-reduced-motion: reduce){
    html{scroll-behavior:auto;}
    *{animation-duration:0.01ms !important; animation-iteration-count:1 !important; transition-duration:0.01ms !important;}
  }

  a{color:inherit;text-decoration:none;}
  ::selection{background:var(--brass); color:var(--ink);}

  /* scroll progress rail */
  #rail{
    position:fixed; top:0; left:0; height:2px; width:0%;
    background:var(--brass-bright); z-index:200; transition:width 0.1s linear;
  }

  /* NAV */
  header{
    position:fixed; top:0; left:0; right:0; z-index:100;
    display:flex; align-items:center; justify-content:space-between;
    padding:22px 6vw;
    background:rgba(13,27,42,0.86);
    backdrop-filter:blur(8px);
    border-bottom:1px solid var(--rule);
  }
  .logo{
    font-family:var(--serif); font-size:1.05rem; letter-spacing:0.02em;
    font-style:italic; color:var(--paper);
  }
  nav ul{list-style:none; display:flex; gap:36px;}
  nav a{
    font-size:0.85rem; color:var(--paper-dim); position:relative; padding-bottom:4px;
  }
  nav a:hover{color:var(--paper);}
  nav a::after{
    content:''; position:absolute; left:0; bottom:0; width:0; height:1px;
    background:var(--brass-bright); transition:width 0.25s ease;
  }
  nav a:hover::after{width:100%;}

  section{padding:120px 6vw; max-width:1180px; margin:0 auto;}

  /* HERO */
  #hero{
    min-height:100vh; display:flex; flex-direction:column; justify-content:center;
    padding-top:120px; position:relative;
  }
  .eyebrow-line{
    font-family:var(--mono); font-size:0.78rem; color:var(--brass);
    letter-spacing:0.06em; margin-bottom:22px;
    opacity:0; animation:riseIn 0.8s ease forwards;
  }
  h1.name{
    font-family:var(--serif); font-weight:500; font-size:clamp(2.8rem,7vw,5.6rem);
    line-height:1.03; letter-spacing:-0.01em; max-width:14ch;
    opacity:0; animation:riseIn 0.9s ease 0.15s forwards;
  }
  .role{
    font-family:var(--serif); font-style:italic; font-weight:400;
    font-size:clamp(1.2rem,2.4vw,1.7rem); color:var(--paper-dim);
    margin-top:18px; max-width:40ch;
    opacity:0; animation:riseIn 0.9s ease 0.3s forwards;
  }
  .ticker-wrap{
    margin-top:44px; display:flex; align-items:center; gap:14px;
    font-family:var(--mono); font-size:0.9rem; color:var(--paper-dim);
    opacity:0; animation:riseIn 0.9s ease 0.45s forwards;
  }
  .ticker-dot{width:7px; height:7px; border-radius:50%; background:var(--teal); flex-shrink:0;}
  #ticker-text{color:var(--brass-bright); min-width:1px;}
  #ticker-text::after{
    content:''; display:inline-block; width:2px; height:1em; background:var(--brass-bright);
    margin-left:2px; vertical-align:-2px; animation:blink 1s step-end infinite;
  }

  .hero-cta{
    margin-top:52px; display:flex; gap:16px; flex-wrap:wrap;
    opacity:0; animation:riseIn 0.9s ease 0.6s forwards;
  }
  .btn{
    font-family:var(--sans); font-size:0.9rem; font-weight:500;
    padding:13px 26px; border:1px solid var(--rule); display:inline-flex; align-items:center; gap:8px;
    transition:all 0.25s ease;
  }
  .btn-primary{background:var(--brass); color:var(--ink); border-color:var(--brass);}
  .btn-primary:hover{background:var(--brass-bright); border-color:var(--brass-bright);}
  .btn-ghost{color:var(--paper); border-color:var(--rule);}
  .btn-ghost:hover{border-color:var(--paper-dim); background:rgba(237,234,226,0.04);}

  @keyframes riseIn{
    from{opacity:0; transform:translateY(14px);}
    to{opacity:1; transform:translateY(0);}
  }
  @keyframes blink{50%{opacity:0;}}

  /* SECTION LABEL */
  .section-head{
    display:flex; align-items:baseline; justify-content:space-between;
    border-bottom:1px solid var(--rule); padding-bottom:18px; margin-bottom:56px;
    flex-wrap:wrap; gap:10px;
  }
  .section-head h2{
    font-family:var(--serif); font-weight:500; font-style:italic;
    font-size:clamp(1.8rem,3.4vw,2.6rem);
  }
  .section-index{font-family:var(--mono); font-size:0.8rem; color:var(--brass);}

  /* ABOUT */
  #about .about-grid{
    display:grid; grid-template-columns:1.1fr 0.9fr; gap:80px;
  }
  #about p{color:var(--paper-dim); font-size:1.05rem; max-width:52ch;}
  #about p + p{margin-top:18px;}

  .ledger{border-top:1px solid var(--rule);}
  .ledger-row{
    display:flex; justify-content:space-between; align-items:center;
    padding:16px 0; border-bottom:1px solid var(--rule);
    font-size:0.95rem;
  }
  .ledger-row span:first-child{color:var(--paper);}
  .ledger-row span:last-child{
    font-family:var(--mono); font-size:0.75rem; color:var(--teal);
  }

  /* HIGHLIGHTS TIMELINE */
  #highlights{padding-top:100px;}
  .timeline{position:relative;}
  .timeline::before{
    content:''; position:absolute; left:120px; top:6px; bottom:6px; width:1px;
    background:var(--rule);
  }
  .tl-item{
    display:grid; grid-template-columns:120px 1fr; gap:0 40px;
    padding-bottom:80px; position:relative;
    opacity:0; transform:translateY(24px);
    transition:opacity 0.7s ease, transform 0.7s ease;
  }
  .tl-item:last-child{padding-bottom:0;}
  .tl-item.visible{opacity:1; transform:translateY(0);}
  .tl-date{
    font-family:var(--mono); font-size:0.82rem; color:var(--brass);
    padding-top:6px;
  }
  .tl-dot{
    position:absolute; left:116px; top:10px; width:9px; height:9px;
    border-radius:50%; background:var(--ink); border:1px solid var(--brass);
    transition:background 0.4s ease;
  }
  .tl-item.visible .tl-dot{background:var(--brass);}
  .tl-body{
    display:grid; grid-template-columns:1fr 220px; gap:32px;
    align-items:start;
  }
  .tl-body h3{
    font-family:var(--serif); font-weight:500; font-size:1.4rem; margin-bottom:12px;
    max-width:26ch;
  }
  .tl-body p{color:var(--paper-dim); font-size:0.98rem; max-width:48ch;}
  .tl-tag{
    display:inline-block; margin-top:16px; font-family:var(--mono); font-size:0.72rem;
    color:var(--teal); border:1px solid rgba(74,124,111,0.4); padding:4px 10px;
  }

  .photo-slot{
    aspect-ratio:4/3; border:1px dashed var(--rule);
    display:flex; align-items:center; justify-content:center; text-align:center;
    color:var(--paper-dim); font-family:var(--mono); font-size:0.7rem;
    padding:16px; line-height:1.5; background:rgba(237,234,226,0.02);
  }

  @media (max-width:820px){
    .timeline::before{left:0; display:none;}
    .tl-item{grid-template-columns:1fr;}
    .tl-dot{display:none;}
    .tl-body{grid-template-columns:1fr;}
    .photo-slot{max-width:280px;}
    #about .about-grid{grid-template-columns:1fr; gap:48px;}
  }

  /* CONTACT */
  #contact{
    border-top:1px solid var(--rule); text-align:left;
  }
  #contact h2{
    font-family:var(--serif); font-style:italic; font-weight:500;
    font-size:clamp(2rem,5vw,3.4rem); max-width:16ch; margin-bottom:40px;
  }
  footer{
    padding:36px 6vw; border-top:1px solid var(--rule);
    display:flex; justify-content:space-between; align-items:center;
    font-family:var(--mono); font-size:0.75rem; color:var(--paper-dim);
    flex-wrap:wrap; gap:10px;
  }
</style>
</head>
<body>

<div id="rail"></div>

<header>
  <div class="logo">Yeoh Chun Siang</div>
  <nav>
    <ul>
      <li><a href="#about">About</a></li>
      <li><a href="#highlights">Highlights</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</header>

<section id="hero">
  <div class="eyebrow-line">Client Services · Fund Management</div>
  <h1 class="name">Yeoh Chun Siang</h1>
  <p class="role">Fund Management Associate — Client Services</p>
  <div class="ticker-wrap">
    <span class="ticker-dot"></span>
    <span>Currently focused on</span>
    <span id="ticker-text"></span>
  </div>
  <div class="hero-cta">
    <a class="btn btn-primary" href="https://www.linkedin.com/in/yeoh-chun-siang/" target="_blank" rel="noopener">View LinkedIn</a>
    <a class="btn btn-ghost" href="mailto:Greggyeoh@gmail.com">Greggyeoh@gmail.com</a>
  </div>
</section>

<section id="about">
  <div class="section-head">
    <h2>About</h2>
    <span class="section-index">01</span>
  </div>
  <div class="about-grid">
    <div>
      <p>Chun Siang works in fund management client services, where the job is part translator and part analyst — turning market and portfolio detail into something a client can act on with confidence.</p>
      <p>Outside of client work, he builds his own financial models to understand companies beyond the headline numbers, and keeps his market read current through equity and stock analysis.</p>
    </div>
    <div class="ledger">
      <div class="ledger-row"><span>Financial Analysis</span><span>CORE</span></div>
      <div class="ledger-row"><span>Financial Modelling</span><span>CORE</span></div>
      <div class="ledger-row"><span>Stock Analysis</span><span>CORE</span></div>
      <div class="ledger-row"><span>Microsoft Office Suite</span><span>TOOLS</span></div>
      <div class="ledger-row"><span>Client Communication</span><span>SOFT</span></div>
    </div>
  </div>
</section>

<section id="highlights">
  <div class="section-head">
    <h2>Highlights</h2>
    <span class="section-index">02</span>
  </div>
  <div class="timeline">

    <div class="tl-item">
      <div class="tl-date">Feb 2026</div>
      <div class="tl-dot"></div>
      <div class="tl-body">
        <div>
          <h3>Built an independent financial model for SOFI Technologies Inc.</h3>
          <p>Constructed a full financial model for SOFI Technologies Inc. from the ground up — a self-directed project to sharpen valuation and forecasting skills outside of day-to-day work.</p>
          <span class="tl-tag">Financial Modelling</span>
        </div>
        <div class="photo-slot">PHOTO PLACEHOLDER<br>Add a screenshot of the model or LinkedIn post here</div>
      </div>
    </div>

    <div class="tl-item">
      <div class="tl-date">Mar 2026</div>
      <div class="tl-dot"></div>
      <div class="tl-body">
        <div>
          <h3>Forage Job Simulation — Bank of America Global Markets</h3>
          <p>Completed Bank of America's Global Markets Sales and Trading Analyst job simulation on Forage, working through the kind of tasks a trading floor analyst handles day to day.</p>
          <span class="tl-tag">Sales &amp; Trading</span>
        </div>
        <div class="photo-slot">PHOTO PLACEHOLDER<br>Add your Forage certificate or LinkedIn post image here</div>
      </div>
    </div>

    <div class="tl-item">
      <div class="tl-date">Jul 2026</div>
      <div class="tl-dot"></div>
      <div class="tl-body">
        <div>
          <h3>Bursa Malaysia MIS Programme</h3>
          <p>Attended the Bursa Malaysia Market Intermediaries Series (MIS) Programme, deepening market structure and intermediary-side knowledge.</p>
          <span class="tl-tag">Market Structure</span>
        </div>
        <div class="photo-slot">PHOTO PLACEHOLDER<br>Add a programme photo or LinkedIn post image here</div>
      </div>
    </div>

  </div>
</section>

<section id="contact">
  <div class="section-head">
    <h2>Contact</h2>
    <span class="section-index">03</span>
  </div>
  <h2>Open to connecting on client services, markets, and fund management.</h2>
  <div class="hero-cta">
    <a class="btn btn-primary" href="https://www.linkedin.com/in/yeoh-chun-siang/" target="_blank" rel="noopener">Connect on LinkedIn</a>
    <a class="btn btn-ghost" href="mailto:Greggyeoh@gmail.com">Send an email</a>
  </div>
</section>

<footer>
  <span>© 2026 Yeoh Chun Siang</span>
  <span>Built with HTML, CSS &amp; JS</span>
</footer>

<script>
  // scroll progress rail
  const rail = document.getElementById('rail');
  window.addEventListener('scroll', () => {
    const h = document.documentElement;
    const scrolled = (h.scrollTop) / (h.scrollHeight - h.clientHeight) * 100;
    rail.style.width = scrolled + '%';
  });

  // hero ticker cycling
  const words = ['Financial Analysis', 'Financial Modelling', 'Stock Analysis', 'Client Relationships'];
  const tickerEl = document.getElementById('ticker-text');
  let wIndex = 0, charIndex = 0, deleting = false;

  function tick(){
    const current = words[wIndex];
    if(!deleting){
      charIndex++;
      tickerEl.textContent = current.slice(0, charIndex);
      if(charIndex === current.length){
        deleting = true;
        setTimeout(tick, 1400);
        return;
      }
    } else {
      charIndex--;
      tickerEl.textContent = current.slice(0, charIndex);
      if(charIndex === 0){
        deleting = false;
        wIndex = (wIndex + 1) % words.length;
      }
    }
    setTimeout(tick, deleting ? 35 : 55);
  }
  tick();

  // timeline reveal on scroll
  const items = document.querySelectorAll('.tl-item');
  const io = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if(entry.isIntersecting){
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
        io.unobserve(entry.target);
      }
    });
  }, { threshold: 0.25 });
  items.forEach(item => io.observe(item));
</script>

</body>
</html>
