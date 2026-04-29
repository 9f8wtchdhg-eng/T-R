<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>T&R Junk Removal – Fast. Clean. Gone.</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --black: #0e0e0e;
      --white: #f5f3ee;
      --accent: #e8420a;
      --accent-dim: #c23508;
      --gray: #888;
      --light-gray: #e8e5df;
      --section-pad: clamp(4rem, 8vw, 8rem);
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--white);
      color: var(--black);
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1.25rem 5%;
      background: var(--white);
      border-bottom: 1px solid var(--light-gray);
      backdrop-filter: blur(6px);
      animation: fadeDown .5s ease both;
    }
    @keyframes fadeDown { from { opacity:0; transform:translateY(-16px); } to { opacity:1; transform:none; } }

    .logo {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.7rem;
      letter-spacing: .04em;
      color: var(--black);
      text-decoration: none;
    }
    .logo span { color: var(--accent); }

    nav ul { list-style: none; display: flex; gap: 2.5rem; }
    nav a { text-decoration: none; color: var(--black); font-size: .9rem; font-weight: 500; letter-spacing: .03em; transition: color .2s; }
    nav a:hover { color: var(--accent); }

    .nav-cta {
      background: var(--accent);
      color: #fff !important;
      padding: .55rem 1.4rem;
      border-radius: 4px;
      transition: background .2s !important;
    }
    .nav-cta:hover { background: var(--accent-dim) !important; color: #fff !important; }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      align-items: center;
      padding: 7rem 5% 4rem;
      gap: 4rem;
      position: relative;
      overflow: hidden;
    }

    #hero::before {
      content: '';
      position: absolute; inset: 0;
      background: repeating-linear-gradient(
        90deg,
        transparent,
        transparent 79px,
        rgba(0,0,0,.03) 80px
      );
      pointer-events: none;
    }

    .hero-text { animation: slideUp .7s .1s ease both; }
    @keyframes slideUp { from { opacity:0; transform:translateY(32px); } to { opacity:1; transform:none; } }

    .hero-eyebrow {
      display: inline-block;
      font-size: .78rem;
      font-weight: 600;
      letter-spacing: .18em;
      text-transform: uppercase;
      color: var(--accent);
      background: rgba(232,66,10,.08);
      padding: .35rem .9rem;
      border-radius: 2px;
      margin-bottom: 1.4rem;
    }

    h1 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(4rem, 8vw, 7.5rem);
      line-height: .95;
      letter-spacing: .02em;
      margin-bottom: 1.5rem;
    }
    h1 em { color: var(--accent); font-style: normal; }

    .hero-sub {
      font-size: 1.05rem;
      font-weight: 300;
      color: #444;
      line-height: 1.7;
      max-width: 420px;
      margin-bottom: 2.5rem;
    }

    .btn-group { display: flex; gap: 1rem; flex-wrap: wrap; }

    .btn {
      display: inline-flex; align-items: center; gap: .5rem;
      padding: .85rem 2rem;
      border-radius: 4px;
      font-size: .95rem;
      font-weight: 600;
      text-decoration: none;
      letter-spacing: .02em;
      transition: all .2s;
    }
    .btn-primary { background: var(--accent); color: #fff; }
    .btn-primary:hover { background: var(--accent-dim); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(232,66,10,.3); }
    .btn-outline { border: 2px solid var(--black); color: var(--black); }
    .btn-outline:hover { background: var(--black); color: var(--white); transform: translateY(-2px); }

    /* Hero Visual */
    .hero-visual {
      animation: slideUp .7s .25s ease both;
      position: relative;
    }

    .hero-card {
      background: var(--black);
      color: var(--white);
      border-radius: 12px;
      padding: 2.5rem;
      position: relative;
      overflow: hidden;
    }
    .hero-card::after {
      content: '';
      position: absolute; bottom: -40px; right: -40px;
      width: 200px; height: 200px;
      background: var(--accent);
      border-radius: 50%;
      opacity: .12;
    }

    .hero-card h3 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.4rem;
      letter-spacing: .06em;
      margin-bottom: 1.8rem;
      color: var(--gray);
    }

    .stat-row {
      display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem;
      margin-bottom: 2rem;
    }
    .stat { }
    .stat-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 3.2rem;
      color: var(--white);
      line-height: 1;
    }
    .stat-num span { color: var(--accent); }
    .stat-label { font-size: .8rem; color: var(--gray); letter-spacing: .05em; text-transform: uppercase; margin-top: .25rem; }

    .badge-row { display: flex; gap: .75rem; flex-wrap: wrap; }
    .badge {
      padding: .4rem 1rem;
      border: 1px solid rgba(255,255,255,.12);
      border-radius: 100px;
      font-size: .78rem;
      color: rgba(255,255,255,.7);
      letter-spacing: .04em;
    }

    /* ── TRUST BAR ── */
    .trust-bar {
      background: var(--black);
      padding: 1.2rem 5%;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 3rem;
      flex-wrap: wrap;
    }
    .trust-item {
      display: flex; align-items: center; gap: .6rem;
      font-size: .82rem;
      color: rgba(255,255,255,.6);
      letter-spacing: .06em;
      text-transform: uppercase;
      font-weight: 500;
    }
    .trust-item svg { color: var(--accent); }

    /* ── SERVICES ── */
    #services {
      padding: var(--section-pad) 5%;
    }

    .section-label {
      font-size: .78rem;
      font-weight: 600;
      letter-spacing: .18em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: .75rem;
    }

    .section-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(2.8rem, 5vw, 4.5rem);
      letter-spacing: .02em;
      line-height: 1;
      margin-bottom: 3.5rem;
    }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 1.5px;
      background: var(--light-gray);
      border: 1.5px solid var(--light-gray);
    }

    .service-card {
      background: var(--white);
      padding: 2.5rem 2rem;
      transition: background .25s;
      position: relative;
      overflow: hidden;
    }
    .service-card:hover { background: var(--black); }
    .service-card:hover .sc-title,
    .service-card:hover .sc-desc { color: var(--white); }
    .service-card:hover .sc-num { color: var(--accent); opacity: 1; }
    .service-card:hover .sc-icon { background: var(--accent); }

    .sc-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: .85rem;
      letter-spacing: .15em;
      color: var(--light-gray);
      opacity: .6;
      margin-bottom: 1.4rem;
      transition: color .25s;
    }

    .sc-icon {
      width: 48px; height: 48px;
      background: var(--light-gray);
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      margin-bottom: 1.2rem;
      font-size: 1.4rem;
      transition: background .25s;
    }

    .sc-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.55rem;
      letter-spacing: .04em;
      margin-bottom: .75rem;
      transition: color .25s;
    }
    .sc-desc {
      font-size: .88rem;
      line-height: 1.65;
      color: #555;
      transition: color .25s;
    }

    /* ── HOW IT WORKS ── */
    #how {
      padding: var(--section-pad) 5%;
      background: var(--black);
      color: var(--white);
    }
    #how .section-title { color: var(--white); }

    .steps {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 3rem;
      margin-top: 3rem;
      position: relative;
    }

    .step { position: relative; }
    .step-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 5rem;
      color: rgba(255,255,255,.06);
      line-height: 1;
      margin-bottom: -.5rem;
    }
    .step-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.6rem;
      letter-spacing: .04em;
      color: var(--white);
      margin-bottom: .6rem;
    }
    .step-desc { font-size: .88rem; color: var(--gray); line-height: 1.65; }
    .step-accent { color: var(--accent); }

    /* ── WHY US ── */
    #why {
      padding: var(--section-pad) 5%;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
    }

    .why-list { list-style: none; display: flex; flex-direction: column; gap: 1.5rem; margin-top: 2rem; }
    .why-item {
      display: flex; gap: 1.2rem; align-items: flex-start;
      padding: 1.5rem;
      border: 1px solid var(--light-gray);
      border-radius: 8px;
      transition: border-color .2s, box-shadow .2s;
    }
    .why-item:hover { border-color: var(--accent); box-shadow: 0 4px 20px rgba(232,66,10,.08); }
    .why-icon { font-size: 1.5rem; flex-shrink: 0; margin-top: .1rem; }
    .why-title { font-weight: 600; font-size: .95rem; margin-bottom: .3rem; }
    .why-desc { font-size: .85rem; color: #666; line-height: 1.6; }

    .why-visual {
      background: var(--black);
      border-radius: 12px;
      padding: 3rem;
      color: var(--white);
      text-align: center;
    }
    .big-stat {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 7rem;
      color: var(--accent);
      line-height: 1;
    }
    .big-stat-label {
      font-size: 1rem;
      color: var(--gray);
      margin-top: .5rem;
      letter-spacing: .05em;
    }
    .divider { width: 40px; height: 2px; background: var(--accent); margin: 1.8rem auto; }

    /* ── CTA ── */
    #contact {
      padding: var(--section-pad) 5%;
      background: var(--accent);
      color: var(--white);
      text-align: center;
    }
    #contact .section-title { color: var(--white); }
    #contact p { font-size: 1.05rem; opacity: .85; max-width: 480px; margin: 0 auto 2.5rem; line-height: 1.7; }

    .contact-btn {
      display: inline-flex; align-items: center; gap: .6rem;
      background: var(--white);
      color: var(--accent);
      padding: 1rem 2.5rem;
      border-radius: 4px;
      font-size: 1rem;
      font-weight: 700;
      text-decoration: none;
      letter-spacing: .03em;
      transition: all .2s;
    }
    .contact-btn:hover { transform: translateY(-3px); box-shadow: 0 12px 32px rgba(0,0,0,.2); }

    .phone-display {
      margin-top: 2rem;
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(2rem, 5vw, 3.5rem);
      letter-spacing: .06em;
      opacity: .9;
    }

    /* ── FOOTER ── */
    footer {
      background: #080808;
      color: rgba(255,255,255,.4);
      padding: 2rem 5%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 1rem;
      font-size: .82rem;
    }
    footer .logo { color: rgba(255,255,255,.5); font-size: 1.2rem; }
    footer .logo span { color: var(--accent); }

    /* ── SCROLL REVEALS ── */
    .reveal { opacity: 0; transform: translateY(28px); transition: opacity .6s ease, transform .6s ease; }
    .reveal.visible { opacity: 1; transform: none; }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      #hero { grid-template-columns: 1fr; padding-top: 6rem; }
      .hero-visual { display: none; }
      #why { grid-template-columns: 1fr; }
      .why-visual { order: -1; }
      nav ul { display: none; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="logo">T<span>&</span>R</a>
  <ul>
    <li><a href="#services">Services</a></li>
    <li><a href="#how">How It Works</a></li>
    <li><a href="#why">Why Us</a></li>
    <li><a href="#contact" class="nav-cta">Get a Quote</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-text">
    <span class="hero-eyebrow">Serving Your Local Area</span>
    <h1>Junk<br><em>Gone.</em><br>Today.</h1>
    <p class="hero-sub">T&R Junk Removal hauls away anything you don't want — fast, affordable, and with zero hassle. One call and we handle the rest.</p>
    <div class="btn-group">
      <a href="#contact" class="btn btn-primary">📞 Get a Free Quote</a>
      <a href="#services" class="btn btn-outline">See Services</a>
    </div>
  </div>

  <div class="hero-visual">
    <div class="hero-card">
      <h3>WHY T&R</h3>
      <div class="stat-row">
        <div class="stat">
          <div class="stat-num">24<span>hr</span></div>
          <div class="stat-label">Same-Day Available</div>
        </div>
        <div class="stat">
          <div class="stat-num">100<span>%</span></div>
          <div class="stat-label">Satisfaction Rate</div>
        </div>
        <div class="stat">
          <div class="stat-num">$0</div>
          <div class="stat-label">Hidden Fees</div>
        </div>
        <div class="stat">
          <div class="stat-num">5<span>★</span></div>
          <div class="stat-label">Customer Rating</div>
        </div>
      </div>
      <div class="badge-row">
        <span class="badge">✓ Fully Insured</span>
        <span class="badge">✓ Local & Reliable</span>
        <span class="badge">✓ Eco-Friendly Disposal</span>
      </div>
    </div>
  </div>
</section>

<!-- TRUST BAR -->
<div class="trust-bar">
  <div class="trust-item">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41L9 16.17z"/></svg>
    Same-Day Service
  </div>
  <div class="trust-item">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41L9 16.17z"/></svg>
    Upfront Pricing
  </div>
  <div class="trust-item">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41L9 16.17z"/></svg>
    Fully Insured
  </div>
  <div class="trust-item">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41L9 16.17z"/></svg>
    Eco-Friendly Disposal
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="reveal">
    <div class="section-label">What We Do</div>
    <div class="section-title">Our Services</div>
  </div>
  <div class="services-grid reveal">
    <div class="service-card">
      <div class="sc-num">01</div>
      <div class="sc-icon">🛋️</div>
      <div class="sc-title">Furniture Removal</div>
      <p class="sc-desc">Sofas, mattresses, dressers, tables — we lift it all out so you don't have to. No job too big or awkward.</p>
    </div>
    <div class="service-card">
      <div class="sc-num">02</div>
      <div class="sc-icon">🏚️</div>
      <div class="sc-title">Estate Cleanouts</div>
      <p class="sc-desc">Full property cleanouts after a move, estate sale, or foreclosure. We clear the whole space quickly and respectfully.</p>
    </div>
    <div class="service-card">
      <div class="sc-num">03</div>
      <div class="sc-icon">🏗️</div>
      <div class="sc-title">Construction Debris</div>
      <p class="sc-desc">Drywall, lumber, tile, concrete — post-renovation debris hauled away same day so your project keeps moving.</p>
    </div>
    <div class="service-card">
      <div class="sc-num">04</div>
      <div class="sc-icon">📦</div>
      <div class="sc-title">Appliance Hauling</div>
      <p class="sc-desc">Old fridges, washers, dryers, and ovens removed safely. We dispose of them the right way, every time.</p>
    </div>
    <div class="service-card">
      <div class="sc-num">05</div>
      <div class="sc-icon">🏠</div>
      <div class="sc-title">Garage Cleanouts</div>
      <p class="sc-desc">Years of buildup cleared out in hours. We haul the junk, sweep the space, and leave it fresh.</p>
    </div>
    <div class="service-card">
      <div class="sc-num">06</div>
      <div class="sc-icon">🗑️</div>
      <div class="sc-title">General Junk Removal</div>
      <p class="sc-desc">Anything else taking up space — boxes, electronics, scrap, yard waste, or miscellaneous clutter. If you don't want it, we'll take it.</p>
    </div>
  </div>
</section>

<!-- HOW IT WORKS -->
<section id="how">
  <div class="reveal">
    <div class="section-label" style="color:rgba(255,255,255,.4)">The Process</div>
    <div class="section-title">How It Works</div>
  </div>
  <div class="steps">
    <div class="step reveal">
      <div class="step-num">01</div>
      <div class="step-title"><span class="step-accent">Call</span> or Text Us</div>
      <p class="step-desc">Reach out and tell us what you need gone. We'll give you a free, no-obligation quote on the spot.</p>
    </div>
    <div class="step reveal">
      <div class="step-num">02</div>
      <div class="step-title"><span class="step-accent">Book</span> a Time</div>
      <p class="step-desc">Pick a time that works for you — including same-day appointments. We show up on time, every time.</p>
    </div>
    <div class="step reveal">
      <div class="step-num">03</div>
      <div class="step-title"><span class="step-accent">We</span> Do the Work</div>
      <p class="step-desc">Our crew loads everything up fast. You don't have to lift a finger or even be home.</p>
    </div>
    <div class="step reveal">
      <div class="step-num">04</div>
      <div class="step-title"><span class="step-accent">It's</span> Gone</div>
      <p class="step-desc">We haul it away, dispose of it responsibly, and leave your space clean. Done.</p>
    </div>
  </div>
</section>

<!-- WHY US -->
<section id="why">
  <div class="reveal">
    <div class="section-label">The Difference</div>
    <div class="section-title">Why Choose<br>T&R?</div>
    <ul class="why-list">
      <li class="why-item">
        <div class="why-icon">⚡</div>
        <div>
          <div class="why-title">Same-Day Availability</div>
          <p class="why-desc">Need it gone today? We offer same-day service — just call and we'll make it happen.</p>
        </div>
      </li>
      <li class="why-item">
        <div class="why-icon">💵</div>
        <div>
          <div class="why-title">Upfront, Honest Pricing</div>
          <p class="why-desc">No surprises. We quote you before we start. The price we say is the price you pay.</p>
        </div>
      </li>
      <li class="why-item">
        <div class="why-icon">♻️</div>
        <div>
          <div class="why-title">Responsible Disposal</div>
          <p class="why-desc">We donate, recycle, or properly dispose of your junk — not just dump it in a landfill.</p>
        </div>
      </li>
      <li class="why-item">
        <div class="why-icon">🛡️</div>
        <div>
          <div class="why-title">Fully Insured & Professional</div>
          <p class="why-desc">We're insured so your property is protected. Our crew is courteous, clean, and efficient.</p>
        </div>
      </li>
    </ul>
  </div>
  <div class="why-visual reveal">
    <div class="big-stat">100%</div>
    <div class="big-stat-label">SATISFACTION GUARANTEED</div>
    <div class="divider"></div>
    <p style="color:rgba(255,255,255,.55);font-size:.9rem;line-height:1.7;">Not happy? We'll make it right. We stand behind every job we do — no questions asked.</p>
  </div>
</section>

<!-- CONTACT / CTA -->
<section id="contact">
  <div class="section-label" style="color:rgba(255,255,255,.6)">Get Started</div>
  <div class="section-title reveal">Ready to Clear<br>the Clutter?</div>
  <p class="reveal">Get a free quote in minutes. No pressure, no commitment. Just tell us what you need gone and we'll handle it.</p>
  <a href="tel:+10000000000" class="contact-btn reveal">📞 Call for a Free Quote</a>
  <div class="phone-display reveal">(000) 000-0000</div>
</section>

<!-- FOOTER -->
<footer>
  <a href="#" class="logo">T<span>&</span>R Junk Removal</a>
  <span>© 2025 T&R Junk Removal. All rights reserved.</span>
  <span>Fast. Clean. Gone.</span>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); }
    });
  }, { threshold: 0.1 });
  reveals.forEach(r => observer.observe(r));
</script>
</body>
</html>