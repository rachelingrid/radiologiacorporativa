<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Radiologia Corporativa — Radiologia Móvel In-Company</title>
  <meta name="description" content="Serviço de radiologia digital in-company com van equipada com tecnologia DR. Exames admissionais, periódicos e demissionais sem deslocamento. Conformidade NR-7 e RDC 611/2022." />

  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet" />

  <style>
    /* ── RESET & TOKENS ─────────────────────────────────────── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }

    :root {
      --navy:   #003D5C;
      --navy-d: #002A45;
      --amber:  #FF9F43;
      --green:  #27AE60;
      --cream:  #F4E8D8;
      --white:  #FFFFFF;
      --gray-1: #F8F8F6;
      --gray-2: #EBEBEB;
      --text:   #1A1A1A;
      --muted:  #555555;
      --light:  #888888;

      --font-display: 'DM Serif Display', Georgia, serif;
      --font-body:    'DM Sans', system-ui, sans-serif;

      --r-sm: 8px;
      --r-md: 14px;
      --r-lg: 20px;
      --r-xl: 28px;

      --shadow-sm: 0 2px 8px rgba(0,61,92,.08);
      --shadow-md: 0 6px 24px rgba(0,61,92,.12);
      --shadow-lg: 0 16px 48px rgba(0,61,92,.16);

      --transition: 240ms cubic-bezier(.4,0,.2,1);
    }

    body {
      font-family: var(--font-body);
      color: var(--text);
      background: var(--white);
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }

    /* ── TYPOGRAPHY ─────────────────────────────────────────── */
    h1, h2, h3, h4 { font-family: var(--font-display); line-height: 1.15; }
    h1 { font-size: clamp(2.6rem, 6vw, 4.2rem); }
    h2 { font-size: clamp(2rem, 4.5vw, 3rem); }
    h3 { font-size: clamp(1.2rem, 2.5vw, 1.6rem); }
    p  { color: var(--muted); }

    /* ── LAYOUT ─────────────────────────────────────────────── */
    .container {
      max-width: 1120px;
      margin: 0 auto;
      padding: 0 clamp(1.25rem, 4vw, 3rem);
    }

    section { padding: clamp(4rem, 8vw, 7rem) 0; }

    /* ── NAV ────────────────────────────────────────────────── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 900;
      background: rgba(255,255,255,.92);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--gray-2);
    }
    .nav-inner {
      display: flex; align-items: center; justify-content: space-between;
      padding: 1.1rem clamp(1.25rem,4vw,3rem);
      max-width: 1120px; margin: 0 auto;
    }
    .nav-logo {
      font-family: var(--font-display);
      font-size: 1.5rem;
      color: var(--navy);
      text-decoration: none;
      letter-spacing: -.01em;
    }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      text-decoration: none; color: var(--muted); font-size: .95rem; font-weight: 500;
      transition: color var(--transition);
    }
    .nav-links a:hover { color: var(--navy); }

    .btn {
      display: inline-flex; align-items: center; gap: .45rem;
      font-family: var(--font-body); font-weight: 600; font-size: .93rem;
      padding: .7rem 1.55rem; border-radius: var(--r-md);
      cursor: pointer; border: none; transition: all var(--transition);
      text-decoration: none; white-space: nowrap;
    }
    .btn-primary   { background: var(--navy); color: #fff; }
    .btn-primary:hover { background: var(--navy-d); box-shadow: var(--shadow-md); }
    .btn-outline   { background: transparent; color: var(--navy); border: 2px solid var(--navy); }
    .btn-outline:hover { background: var(--navy); color: #fff; }
    .btn-lg { padding: .9rem 2.1rem; font-size: 1rem; }

    .nav-cta { display: none; }
    @media(min-width:768px){ .nav-cta { display: inline-flex; } }

    /* hamburger */
    .hamburger { display: none; flex-direction: column; gap: 5px; background: none; border: none; cursor: pointer; padding: 4px; }
    .hamburger span { display: block; width: 22px; height: 2px; background: var(--navy); border-radius: 2px; transition: all .3s; }
    @media(max-width:767px){ .hamburger { display: flex; } .nav-links { display: none; } }
    .mobile-menu {
      display: none;
      flex-direction: column;
      gap: 0;
      background: var(--white);
      border-top: 1px solid var(--gray-2);
      padding: 1rem clamp(1.25rem,4vw,3rem);
    }
    .mobile-menu.open { display: flex; }
    .mobile-menu a {
      display: block; padding: .85rem 0;
      text-decoration: none; color: var(--text); font-weight: 500;
      border-bottom: 1px solid var(--gray-2);
    }
    .mobile-menu a:last-child { border-bottom: none; }

    /* ── HERO ───────────────────────────────────────────────── */
    #hero {
      padding-top: calc(5rem + clamp(4rem,8vw,7rem));
      background: linear-gradient(160deg, #fff 0%, var(--cream) 100%);
      overflow: hidden;
      position: relative;
    }
    #hero::before {
      content: '';
      position: absolute; inset: 0;
      background: radial-gradient(ellipse 60% 50% at 80% 40%, rgba(0,61,92,.06) 0%, transparent 70%);
      pointer-events: none;
    }
    .hero-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 3rem;
      align-items: center;
    }
    @media(min-width:768px){ .hero-grid { grid-template-columns: 1fr 1fr; } }

    .hero-badge {
      display: inline-flex; align-items: center; gap: .5rem;
      background: rgba(0,61,92,.08);
      color: var(--navy); font-size: .8rem; font-weight: 600;
      padding: .35rem 1rem; border-radius: 99px;
      letter-spacing: .04em; text-transform: uppercase;
      margin-bottom: 1.4rem;
    }
    .hero-badge span { width: 7px; height: 7px; border-radius: 50%; background: var(--amber); display: inline-block; }

    #hero h1 { color: var(--navy); margin-bottom: 1.2rem; }
    #hero h1 em { font-style: italic; color: var(--amber); }

    .hero-desc { font-size: 1.1rem; margin-bottom: 2rem; max-width: 480px; }

    .hero-btns { display: flex; flex-wrap: wrap; gap: .9rem; margin-bottom: 2.5rem; }

    .hero-stats { display: flex; flex-wrap: wrap; gap: 2rem; }
    .stat-item { }
    .stat-num { font-family: var(--font-display); font-size: 1.9rem; color: var(--navy); line-height: 1; }
    .stat-label { font-size: .78rem; color: var(--muted); font-weight: 500; text-transform: uppercase; letter-spacing: .05em; }

    .hero-img-wrap { position: relative; }
    .hero-img-wrap img {
      width: 100%; border-radius: var(--r-xl);
      box-shadow: var(--shadow-lg);
      object-fit: cover; aspect-ratio: 16/10;
    }
    .hero-chip {
      position: absolute; bottom: -1.2rem; left: 1.5rem;
      background: var(--white); border-radius: var(--r-md);
      padding: .9rem 1.3rem; box-shadow: var(--shadow-md);
      display: flex; align-items: center; gap: .75rem;
    }
    .hero-chip-icon { font-size: 1.8rem; }
    .hero-chip-text { font-size: .82rem; font-weight: 600; color: var(--navy); line-height: 1.3; }
    .hero-chip-sub  { font-size: .75rem; color: var(--muted); font-weight: 400; }

    /* ── COMO FUNCIONA ──────────────────────────────────────── */
    #como { background: var(--white); }
    .section-label {
      font-size: .78rem; font-weight: 700; letter-spacing: .1em;
      text-transform: uppercase; color: var(--amber);
      margin-bottom: .5rem; display: block;
    }
    .section-title { color: var(--navy); margin-bottom: 1rem; }
    .section-desc  { font-size: 1.05rem; max-width: 520px; }

    .steps-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 1.5rem; margin-top: 3.5rem;
    }
    .step-card {
      background: var(--gray-1); border-radius: var(--r-lg);
      padding: 2rem; position: relative; overflow: hidden;
      transition: box-shadow var(--transition), transform var(--transition);
    }
    .step-card:hover { box-shadow: var(--shadow-md); transform: translateY(-3px); }
    .step-number {
      position: absolute; top: 1.2rem; right: 1.4rem;
      font-family: var(--font-display); font-size: 3.5rem;
      color: rgba(0,61,92,.07); line-height: 1; font-style: italic;
    }
    .step-icon { font-size: 2.2rem; margin-bottom: 1rem; }
    .step-card h3 { color: var(--navy); margin-bottom: .6rem; font-size: 1.15rem; }
    .step-card p  { font-size: .93rem; }

    /* ── FUSÃO / EXPERTISE ──────────────────────────────────── */
    #expertise { background: var(--cream); }
    .expertise-grid {
      display: grid; grid-template-columns: 1fr;
      gap: 3rem; align-items: center;
    }
    @media(min-width:768px){ .expertise-grid { grid-template-columns: 1fr 1fr; } }

    .expertise-img {
      width: 100%; border-radius: var(--r-xl);
      box-shadow: var(--shadow-lg); object-fit: cover;
      aspect-ratio: 4/3;
    }

    .expertise-points { display: flex; flex-direction: column; gap: 1.5rem; margin-top: 2rem; }
    .exp-point {
      display: flex; gap: 1rem; align-items: flex-start;
      background: rgba(255,255,255,.7); border-radius: var(--r-md);
      padding: 1.3rem; backdrop-filter: blur(4px);
      border: 1px solid rgba(255,255,255,.9);
    }
    .exp-icon {
      width: 44px; height: 44px; border-radius: var(--r-sm);
      display: flex; align-items: center; justify-content: center;
      font-size: 1.4rem; flex-shrink: 0;
    }
    .exp-icon.amber { background: rgba(255,159,67,.15); }
    .exp-icon.green { background: rgba(39,174,96,.15); }
    .exp-icon.navy  { background: rgba(0,61,92,.10); }
    .exp-text h4 { font-family: var(--font-body); font-weight: 700; font-size: 1rem; color: var(--navy); margin-bottom: .3rem; }
    .exp-text p  { font-size: .9rem; line-height: 1.55; }

    /* fusão destaque */
    .merger-box {
      margin-bottom: 1.8rem;
      background: linear-gradient(135deg, rgba(0,61,92,.06), rgba(255,159,67,.08));
      border: 1px solid rgba(0,61,92,.14);
      border-radius: var(--r-md);
      padding: 1.2rem 1.5rem;
    }
    .merger-box strong { color: var(--navy); }
    .merger-box p { font-size: .92rem; margin-top: .3rem; }

    /* ── BENEFÍCIOS ─────────────────────────────────────────── */
    #beneficios { background: var(--white); }
    .ben-grid {
      display: grid; grid-template-columns: 1fr;
      gap: 3rem; align-items: center;
    }
    @media(min-width:768px){ .ben-grid { grid-template-columns: 1fr 1fr; } }

    .ben-img { width: 100%; border-radius: var(--r-xl); box-shadow: var(--shadow-lg); object-fit: cover; aspect-ratio: 4/3; }

    .ben-list { display: flex; flex-direction: column; gap: 1.2rem; margin-top: 1.5rem; }
    .ben-item {
      display: flex; gap: 1.1rem; align-items: flex-start;
      padding: 1.2rem; border-radius: var(--r-md);
      background: var(--gray-1);
      border-left: 4px solid transparent;
      transition: box-shadow var(--transition);
    }
    .ben-item:hover { box-shadow: var(--shadow-sm); }
    .ben-item.amber { border-color: var(--amber); }
    .ben-item.green { border-color: var(--green); }
    .ben-item.navy  { border-color: var(--navy);  }
    .ben-num { font-family: var(--font-display); font-size: 1.7rem; color: var(--navy); line-height: 1; min-width: 80px; }
    .ben-detail h4 { font-family: var(--font-body); font-weight: 700; color: var(--navy); margin-bottom: .2rem; }
    .ben-detail p { font-size: .88rem; }

    /* ── TECNOLOGIA ─────────────────────────────────────────── */
    #tecnologia {
      background: var(--navy);
      color: var(--white);
    }
    #tecnologia .section-label { color: var(--amber); }
    #tecnologia .section-title { color: var(--white); }
    #tecnologia .section-desc  { color: rgba(255,255,255,.7); }

    .tech-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1.2rem; margin-top: 3.5rem;
    }
    .tech-card {
      background: rgba(255,255,255,.06);
      border: 1px solid rgba(255,255,255,.1);
      border-radius: var(--r-lg); padding: 1.7rem 1.4rem;
      text-align: center;
      transition: background var(--transition), transform var(--transition);
    }
    .tech-card:hover { background: rgba(255,255,255,.1); transform: translateY(-3px); }
    .tech-card-icon { font-size: 2rem; margin-bottom: 1rem; }
    .tech-card h4 { color: var(--white); font-family: var(--font-body); font-weight: 700; font-size: .97rem; margin-bottom: .4rem; }
    .tech-card p  { color: rgba(255,255,255,.6); font-size: .85rem; }

    /* ── PREÇOS ─────────────────────────────────────────────── */
    #precos { background: var(--cream); }
    .price-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 1.5rem; margin-top: 3rem;
    }
    .price-card {
      background: var(--white); border-radius: var(--r-lg); padding: 2rem;
      box-shadow: var(--shadow-sm);
      transition: box-shadow var(--transition), transform var(--transition);
      border: 1px solid var(--gray-2);
      position: relative;
    }
    .price-card:hover { box-shadow: var(--shadow-md); transform: translateY(-4px); }
    .price-card.featured {
      border: 2px solid var(--navy); background: var(--navy);
    }
    .price-card.featured h3,
    .price-card.featured .price-value,
    .price-card.featured .price-desc { color: var(--white); }
    .price-card.featured p { color: rgba(255,255,255,.75); }
    .price-badge {
      position: absolute; top: -12px; left: 50%; transform: translateX(-50%);
      background: var(--amber); color: var(--white); font-size: .72rem; font-weight: 700;
      padding: .25rem .85rem; border-radius: 99px; letter-spacing: .06em; text-transform: uppercase;
      white-space: nowrap;
    }
    .price-value { font-family: var(--font-display); font-size: 2.2rem; color: var(--navy); line-height: 1; margin: .8rem 0 .4rem; }
    .price-value small { font-size: 1rem; font-family: var(--font-body); }
    .price-desc { font-size: .82rem; color: var(--muted); margin-bottom: 1.2rem; }
    .price-list { list-style: none; display: flex; flex-direction: column; gap: .55rem; }
    .price-list li { font-size: .88rem; color: var(--muted); display: flex; gap: .5rem; align-items: flex-start; }
    .price-list li::before { content: '✓'; color: var(--green); font-weight: 700; flex-shrink: 0; }
    .price-card.featured .price-list li { color: rgba(255,255,255,.8); }
    .price-card.featured .price-list li::before { color: var(--amber); }
    .price-note { margin-top: 2rem; font-size: .85rem; color: var(--muted); text-align: center; }

    /* ── SETORES ────────────────────────────────────────────── */
    #setores { background: var(--white); }
    .setores-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1.2rem; margin-top: 3rem;
    }
    .setor-card {
      border: 1px solid var(--gray-2); border-radius: var(--r-md);
      padding: 1.4rem; display: flex; gap: .85rem; align-items: flex-start;
      transition: all var(--transition);
    }
    .setor-card:hover { border-color: var(--navy); box-shadow: var(--shadow-sm); }
    .setor-icon { font-size: 1.7rem; }
    .setor-name { font-weight: 700; color: var(--navy); font-size: .95rem; margin-bottom: .2rem; }
    .setor-desc { font-size: .82rem; color: var(--muted); }

    /* ── CONTATO ────────────────────────────────────────────── */
    #contato { background: var(--cream); }
    .contato-inner {
      max-width: 680px; margin: 0 auto; text-align: center;
    }
    .contato-inner h2 { margin-bottom: 1rem; }
    .contato-inner p  { font-size: 1.05rem; margin-bottom: 2.2rem; }

    .contato-cards {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1rem; margin-bottom: 2.5rem;
    }
    .contato-card {
      background: var(--white); border-radius: var(--r-md); padding: 1.4rem;
      box-shadow: var(--shadow-sm); text-align: center;
    }
    .contato-card-icon { font-size: 1.6rem; margin-bottom: .7rem; }
    .contato-card-label { font-size: .75rem; font-weight: 600; color: var(--muted); text-transform: uppercase; letter-spacing: .06em; }
    .contato-card-val   { font-size: .97rem; font-weight: 600; color: var(--navy); margin-top: .25rem; text-decoration: none; }
    a.contato-card-val:hover { text-decoration: underline; }

    .contato-btns { display: flex; flex-wrap: wrap; justify-content: center; gap: 1rem; }

    /* ── FOOTER ─────────────────────────────────────────────── */
    footer { background: var(--navy); color: rgba(255,255,255,.7); padding: 3.5rem 0 1.5rem; }
    .footer-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 2.5rem; margin-bottom: 2.5rem;
    }
    .footer-brand { font-family: var(--font-display); font-size: 1.4rem; color: var(--white); margin-bottom: .7rem; }
    .footer-tagline { font-size: .88rem; }
    .footer-col h5 { color: var(--white); font-weight: 700; font-size: .85rem; text-transform: uppercase; letter-spacing: .07em; margin-bottom: .9rem; }
    .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: .55rem; }
    .footer-col ul a { color: rgba(255,255,255,.65); text-decoration: none; font-size: .88rem; transition: color var(--transition); }
    .footer-col ul a:hover { color: var(--white); }
    .footer-bottom { border-top: 1px solid rgba(255,255,255,.12); padding-top: 1.5rem; text-align: center; font-size: .82rem; }

    /* ── DIVIDER ────────────────────────────────────────────── */
    .divider {
      height: 1px; background: var(--gray-2);
      margin: 0;
    }

    /* ── ANIMATIONS ─────────────────────────────────────────── */
    .fade-up {
      opacity: 0; transform: translateY(24px);
      transition: opacity .6s ease, transform .6s ease;
    }
    .fade-up.visible { opacity: 1; transform: none; }

    /* ── UTILS ──────────────────────────────────────────────── */
    .text-center { text-align: center; }
    .mb-sm { margin-bottom: .6rem; }
    .mb-md { margin-bottom: 1.2rem; }
    .mt-lg { margin-top: 2.5rem; }

    /* ── WHATSAPP FLOAT ─────────────────────────────────────── */
    .wa-float {
      position: fixed; bottom: 1.8rem; right: 1.8rem; z-index: 800;
      width: 56px; height: 56px; border-radius: 50%;
      background: #25D366; display: flex; align-items: center; justify-content: center;
      box-shadow: 0 4px 20px rgba(37,211,102,.45);
      text-decoration: none; transition: transform var(--transition);
    }
    .wa-float:hover { transform: scale(1.08); }
    .wa-float svg { width: 28px; height: 28px; fill: #fff; }
  </style>
</head>

<body>

<!-- ── NAV ──────────────────────────────────────────────────── -->
<nav id="navbar">
  <div class="nav-inner">
    <a class="nav-logo" href="#hero">RC</a>
    <ul class="nav-links">
      <li><a href="#como">Serviço</a></li>
      <li><a href="#expertise">Expertise</a></li>
      <li><a href="#beneficios">Benefícios</a></li>
      <li><a href="#precos">Preços</a></li>
      <li><a href="#contato">Contato</a></li>
    </ul>
    <a class="btn btn-primary nav-cta" href="#contato">Solicitar Demo</a>
    <button class="hamburger" id="hamburger" aria-label="Menu">
      <span></span><span></span><span></span>
    </button>
  </div>
  <div class="mobile-menu" id="mobile-menu">
    <a href="#como" onclick="closeMobile()">Serviço</a>
    <a href="#expertise" onclick="closeMobile()">Expertise</a>
    <a href="#beneficios" onclick="closeMobile()">Benefícios</a>
    <a href="#precos" onclick="closeMobile()">Preços</a>
    <a href="#contato" onclick="closeMobile()">Contato</a>
  </div>
</nav>

<!-- ── HERO ─────────────────────────────────────────────────── -->
<section id="hero">
  <div class="container">
    <div class="hero-grid">
      <div class="fade-up">
        <div class="hero-badge"><span></span> Novo Modelo Corporativo</div>
        <h1>Radiologia na <em>Empresa,</em><br/>sem deslocamento</h1>
        <p class="hero-desc">Van equipada com tecnologia DR estaciona no seu pátio. Exames admissionais, periódicos e demissionais com laudo digital em até 48h — 100% em conformidade com NR-7 e RDC 611/2022.</p>
        <div class="hero-btns">
          <a href="#contato" class="btn btn-primary btn-lg">Agendar Consulta →</a>
          <a href="#beneficios" class="btn btn-outline btn-lg">Ver Benefícios</a>
        </div>
        <div class="hero-stats">
          <div class="stat-item">
            <div class="stat-num">R$&nbsp;60</div>
            <div class="stat-label">a partir de / exame</div>
          </div>
          <div class="stat-item">
            <div class="stat-num">48h</div>
            <div class="stat-label">entrega do laudo</div>
          </div>
          <div class="stat-item">
            <div class="stat-num">100%</div>
            <div class="stat-label">conformidade NR-7</div>
          </div>
        </div>
      </div>

      <div class="hero-img-wrap fade-up" style="transition-delay:.15s">
        <img
          src="https://radcorpsite-nxn4kbdg.manus.space/assets/hero-van-radiologia-Tdw7Fvd6gaqJFsfEZoUA9H.webp"
          alt="Van Radiologia Corporativa estacionada em empresa corporativa"
          width="640" height="400"
          onerror="this.style.display='none'"
        />
        <div class="hero-chip">
          <div class="hero-chip-icon">🚐</div>
          <div>
            <div class="hero-chip-text">Van equipada com DR</div>
            <div class="hero-chip-sub">Pronta para ir até você</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ── COMO FUNCIONA ─────────────────────────────────────────── -->
<section id="como">
  <div class="container">
    <div class="text-center fade-up">
      <span class="section-label">Como Funciona</span>
      <h2 class="section-title">Três passos,<br/>zero burocracia</h2>
      <p class="section-desc" style="margin:0 auto;">Do agendamento ao laudo, cuidamos de tudo. Seu RH agenda, a van vai, o resultado chega digital.</p>
    </div>

    <div class="steps-grid">
      <div class="step-card fade-up">
        <div class="step-number">01</div>
        <div class="step-icon">📅</div>
        <h3>Agendamento</h3>
        <p>Coordenamos com seu RH ou SESMT o cronograma, lista de colaboradores e tipo de exame — admissional, periódico ou demissional.</p>
      </div>
      <div class="step-card fade-up" style="transition-delay:.1s">
        <div class="step-number">02</div>
        <div class="step-icon">🚐</div>
        <h3>Van no local</h3>
        <p>Nossa van com tecnologia DR estaciona no pátio da empresa. Conexão elétrica à rede local ou gerador próprio. Nenhum colaborador precisa sair.</p>
      </div>
      <div class="step-card fade-up" style="transition-delay:.2s">
        <div class="step-number">03</div>
        <div class="step-icon">📋</div>
        <h3>Laudo digital</h3>
        <p>Imagem transmitida ao servidor PACS. Radiologista habilitado emite laudo assinado digitalmente. Entrega em até 48 horas úteis.</p>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ── EXPERTISE / FUSÃO ────────────────────────────────────── -->
<section id="expertise">
  <div class="container">
    <div class="expertise-grid">
      <div class="fade-up">
        <img
          class="expertise-img"
          src="https://radcorpsite-nxn4kbdg.manus.space/assets/expertise-rachel-francisco-JQM3yqWQmiNpmYnfcG3si5.webp"
          alt="Equipe Radiologia Corporativa — médica e técnico"
          width="560" height="420"
          onerror="this.style.background='var(--gray-2)'"
        />
      </div>

      <div class="fade-up" style="transition-delay:.12s">
        <span class="section-label">Quem Somos</span>
        <h2 class="section-title">Expertise que<br/>transforma</h2>

        <div class="merger-box">
          <strong>Uma fusão única no mercado:</strong>
          <p>A <strong>RR Soluções em Saúde — Radiologia Domiciliar</strong> une forças com mais de <strong>20 anos de experiência</strong> na gestão de serviços de radiologia à frente da <strong>Rede Memória</strong>. Inovação disruptiva encontra excelência operacional de larga escala.</p>
        </div>

        <div class="expertise-points">
          <div class="exp-point">
            <div class="exp-icon amber">🚀</div>
            <div class="exp-text">
              <h4>RR Soluções — Radiologia Domiciliar</h4>
              <p>Pioneira em radiologia digital home care no Rio de Janeiro. Mudou o cenário da radiologia com inovação disruptiva antes mesmo da chegada massiva da radiologia digital ao mercado.</p>
            </div>
          </div>
          <div class="exp-point">
            <div class="exp-icon green">🏥</div>
            <div class="exp-text">
              <h4>Rede Memória — 20+ anos de Gestão</h4>
              <p>Expertise consolidada na gestão de radiologia em redes de saúde de grande porte. Domínio completo de conformidade regulatória, RDC 611/2022, PCMSO e laudos OIT.</p>
            </div>
          </div>
          <div class="exp-point">
            <div class="exp-icon navy">🤝</div>
            <div class="exp-text">
              <h4>Juntos — Inovação Corporativa</h4>
              <p>Levando radiologia digital diretamente às empresas, eliminando deslocamento de colaboradores e gerando economia significativa em custo-benefício.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ── BENEFÍCIOS ────────────────────────────────────────────── -->
<section id="beneficios">
  <div class="container">
    <div class="ben-grid">
      <div class="fade-up">
        <span class="section-label">Benefícios Comprovados</span>
        <h2 class="section-title">Números que<br/>convencem</h2>

        <div class="ben-list">
          <div class="ben-item amber">
            <div class="ben-num">R$&thinsp;1.550</div>
            <div class="ben-detail">
              <h4>Economia por colaborador/ano</h4>
              <p>Comparado ao modelo de reconvocação e deslocamento tradicional para clínicas externas.</p>
            </div>
          </div>
          <div class="ben-item green">
            <div class="ben-num">86%</div>
            <div class="ben-detail">
              <h4>Redução do custo operacional</h4>
              <p>Em relação ao modelo atual de exames em clínicas particulares com transporte de colaboradores.</p>
            </div>
          </div>
          <div class="ben-item navy">
            <div class="ben-num">0h</div>
            <div class="ben-detail">
              <h4>Perda de produtividade</h4>
              <p>Exame realizado no local de trabalho, sem deslocamento, sem fila de clínica, sem dia perdido.</p>
            </div>
          </div>
          <div class="ben-item amber">
            <div class="ben-num">100%</div>
            <div class="ben-detail">
              <h4>Conformidade regulatória</h4>
              <p>RDC 611/2022, NR-7, PCMSO e laudos OIT para expostos a sílica, asbesto e agentes ocupacionais.</p>
            </div>
          </div>
        </div>
      </div>

      <div class="fade-up" style="transition-delay:.12s">
        <img
          class="ben-img"
          src="https://radcorpsite-nxn4kbdg.manus.space/assets/economia-beneficio-HjWSqDyN7LiNB9HLtS2Ykv.webp"
          alt="Gráfico de economia e eficiência operacional"
          width="560" height="420"
          onerror="this.style.background='var(--gray-2)'"
        />
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ── TECNOLOGIA ────────────────────────────────────────────── -->
<section id="tecnologia">
  <div class="container">
    <div class="text-center fade-up">
      <span class="section-label">Tecnologia</span>
      <h2 class="section-title" style="color:var(--white);">Infraestrutura<br/>de ponta</h2>
      <p class="section-desc" style="margin:0 auto;color:rgba(255,255,255,.7)">Van equipada com os mesmos padrões de uma sala de radiologia fixa — e tudo isso vai até você.</p>
    </div>
    <div class="tech-grid">
      <div class="tech-card fade-up">
        <div class="tech-card-icon">📡</div>
        <h4>DR Digital</h4>
        <p>Detector de painel plano de alta resolução. Sem filmes, sem processadora. Imagens DICOM imediatas.</p>
      </div>
      <div class="tech-card fade-up" style="transition-delay:.08s">
        <div class="tech-card-icon">🛡️</div>
        <h4>Blindagem Radiológica</h4>
        <p>Proteção interna certificada conforme RDC 611/2022. Laudo de levantamento radiométrico aprovado.</p>
      </div>
      <div class="tech-card fade-up" style="transition-delay:.16s">
        <div class="tech-card-icon">💻</div>
        <h4>Telerradiologia PACS</h4>
        <p>Transmissão instantânea ao servidor PACS. Laudagem remota por radiologista habilitado (CFM 2.314/2022).</p>
      </div>
      <div class="tech-card fade-up" style="transition-delay:.24s">
        <div class="tech-card-icon">⚡</div>
        <h4>Gerador Próprio</h4>
        <p>Operação autônoma ou integrada à rede da empresa. Nenhuma interrupção no ambiente de trabalho.</p>
      </div>
      <div class="tech-card fade-up" style="transition-delay:.32s">
        <div class="tech-card-icon">📊</div>
        <h4>Dosimetria Certificada</h4>
        <p>Monitoramento mensal conforme CNEN. Todos os profissionais usam dosímetro individual.</p>
      </div>
      <div class="tech-card fade-up" style="transition-delay:.40s">
        <div class="tech-card-icon">📁</div>
        <h4>Arquivo 20+ Anos</h4>
        <p>Imagens armazenadas eletronicamente por mínimo de 20 anos após o desligamento, conforme NR-7.</p>
      </div>
    </div>
  </div>
</section>

<div class="divider" style="background:rgba(255,255,255,.1)"></div>

<!-- ── PREÇOS ─────────────────────────────────────────────────── -->
<section id="precos">
  <div class="container">
    <div class="text-center fade-up">
      <span class="section-label">Tabela de Preços</span>
      <h2 class="section-title">Transparência<br/>desde o início</h2>
      <p class="section-desc" style="margin:0 auto;">Valores indicativos para contratos corporativos. Desconto por volume e frequência. Consulte-nos para proposta personalizada.</p>
    </div>

    <div class="price-grid mt-lg">
      <div class="price-card fade-up">
        <h3 style="color:var(--navy);font-family:var(--font-body);font-weight:700">RX Tórax PA</h3>
        <div class="price-value"><small>a partir de </small>R$&thinsp;60</div>
        <div class="price-desc">por exame · laudo descritivo</div>
        <ul class="price-list">
          <li>1 incidência posteroanterior</li>
          <li>Laudo descritivo clínico</li>
          <li>Entrega em até 48h úteis</li>
          <li>Válido para admissional e periódico</li>
        </ul>
      </div>

      <div class="price-card featured fade-up" style="transition-delay:.08s">
        <div class="price-badge">Mais Solicitado</div>
        <h3>RX Tórax Padrão OIT</h3>
        <div class="price-value">A&nbsp;combinar</div>
        <div class="price-desc">laudo classificatório · expostos a silica/asbesto</div>
        <ul class="price-list">
          <li>Radiologista certificado OIT</li>
          <li>Formulário OIT preenchido</li>
          <li>Validade legal em perícias</li>
          <li>Obrigatório para NR-7 Anexo III</li>
        </ul>
      </div>

      <div class="price-card fade-up" style="transition-delay:.16s">
        <h3 style="color:var(--navy);font-family:var(--font-body);font-weight:700">Pacotes e Volume</h3>
        <div class="price-value">Sob<small>&nbsp;consulta</small></div>
        <div class="price-desc">desconto progressivo por volume</div>
        <ul class="price-list">
          <li>RX Tórax PA + Perfil (2 inc.)</li>
          <li>RX Coluna por segmento</li>
          <li>RX Articular bilateral</li>
          <li>Campanhas admissionais em massa</li>
        </ul>
      </div>
    </div>

    <p class="price-note fade-up">
      ✓ Preços incluem execução, controle de qualidade, PACS e laudo digital assinado.<br/>
      Taxa de mobilização (deslocamento) negociada por visita. Emissão do ASO a cargo do médico do trabalho da contratante.
    </p>
  </div>
</section>

<div class="divider"></div>

<!-- ── SETORES ────────────────────────────────────────────────── -->
<section id="setores">
  <div class="container">
    <div class="text-center fade-up">
      <span class="section-label">Setores Atendidos</span>
      <h2 class="section-title">Onde atuamos</h2>
      <p class="section-desc" style="margin:0 auto;">Qualquer empresa com colaboradores CLT precisa cumprir a NR-7. Mas alguns setores têm exigências ainda mais específicas.</p>
    </div>

    <div class="setores-grid mt-lg">
      <div class="setor-card fade-up">
        <div class="setor-icon">🛢️</div>
        <div>
          <div class="setor-name">Petróleo e Gás</div>
          <div class="setor-desc">RX tórax, coluna e articular. Hiperbáricas (NR-7 Anexo IV). Petrobras e empresas de apoio offshore.</div>
        </div>
      </div>
      <div class="setor-card fade-up" style="transition-delay:.06s">
        <div class="setor-icon">⛏️</div>
        <div>
          <div class="setor-name">Mineração e Metalurgia</div>
          <div class="setor-desc">Laudo OIT obrigatório. Silicose, asbestose — NR-7 Anexo III.</div>
        </div>
      </div>
      <div class="setor-card fade-up" style="transition-delay:.12s">
        <div class="setor-icon">🏗️</div>
        <div>
          <div class="setor-name">Construção Pesada</div>
          <div class="setor-desc">Grande volume de admissionais. Exposição a sílica em escavação e jateamento.</div>
        </div>
      </div>
      <div class="setor-card fade-up" style="transition-delay:.18s">
        <div class="setor-icon">🧪</div>
        <div>
          <div class="setor-name">Indústria Química</div>
          <div class="setor-desc">Riscos inalatórios. Monitoramento periódico radiológico e espirometria.</div>
        </div>
      </div>
      <div class="setor-card fade-up" style="transition-delay:.24s">
        <div class="setor-icon">🚢</div>
        <div>
          <div class="setor-name">Portos e Logística</div>
          <div class="setor-desc">Grandes contingentes. Estivadores, motoristas e operários. Campanhas em massa.</div>
        </div>
      </div>
      <div class="setor-card fade-up" style="transition-delay:.30s">
        <div class="setor-icon">🏭</div>
        <div>
          <div class="setor-name">Indústria em Geral</div>
          <div class="setor-desc">Qualquer empresa CLT. Admissional, periódico e demissional conforme PCMSO.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ── CONTATO ────────────────────────────────────────────────── -->
<section id="contato">
  <div class="container">
    <div class="contato-inner fade-up">
      <span class="section-label" style="display:block;text-align:center">Fale Conosco</span>
      <h2 class="section-title">Pronto para transformar<br/>a radiologia da sua empresa?</h2>
      <p>Converse com nossa equipe. Elaboramos uma proposta personalizada com base no seu volume de colaboradores, setores de risco e frequência de exames.</p>

      <div class="contato-cards">
        <div class="contato-card">
          <div class="contato-card-icon">📱</div>
          <div class="contato-card-label">WhatsApp / Telefone</div>
          <a class="contato-card-val" href="https://wa.me/5521967269228" target="_blank" rel="noopener">(21) 96726-9228</a>
        </div>
        <div class="contato-card">
          <div class="contato-card-icon">✉️</div>
          <div class="contato-card-label">E-mail</div>
          <a class="contato-card-val" href="mailto:contato.radcorp@gmail.com">contato.radcorp@gmail.com</a>
        </div>
        <div class="contato-card">
          <div class="contato-card-icon">🌐</div>
          <div class="contato-card-label">Site</div>
          <a class="contato-card-val" href="https://www.radiologiacorporativa.com.br" target="_blank" rel="noopener">radiologiacorporativa.com.br</a>
        </div>
      </div>

      <div class="contato-btns">
        <a href="https://wa.me/5521967269228?text=Olá%2C%20gostaria%20de%20conhecer%20o%20serviço%20de%20radiologia%20corporativa" class="btn btn-primary btn-lg" target="_blank" rel="noopener">💬 Falar no WhatsApp</a>
        <a href="mailto:contato.radcorp@gmail.com" class="btn btn-outline btn-lg">📧 Enviar E-mail</a>
      </div>
    </div>
  </div>
</section>

<!-- ── FOOTER ─────────────────────────────────────────────────── -->
<footer>
  <div class="container">
    <div class="footer-grid">
      <div>
        <div class="footer-brand">Radiologia Corporativa</div>
        <p class="footer-tagline">Radiologia digital in-company para empresas que valorizam a saúde ocupacional dos colaboradores.</p>
      </div>
      <div class="footer-col">
        <h5>Serviços</h5>
        <ul>
          <li><a href="#como">RX de Tórax PA</a></li>
          <li><a href="#como">Laudo Padrão OIT</a></li>
          <li><a href="#como">RX de Coluna</a></li>
          <li><a href="#como">RX Articular</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Empresa</h5>
        <ul>
          <li><a href="#expertise">Sobre Nós</a></li>
          <li><a href="#tecnologia">Tecnologia</a></li>
          <li><a href="#setores">Setores</a></li>
          <li><a href="#contato">Contato</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Contato</h5>
        <ul>
          <li><a href="https://wa.me/5521967269228">(21) 96726-9228</a></li>
          <li><a href="mailto:contato.radcorp@gmail.com">contato.radcorp@gmail.com</a></li>
          <li><a href="https://www.radiologiacorporativa.com.br">radiologiacorporativa.com.br</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2025 Radiologia Corporativa. Todos os direitos reservados. &nbsp;|&nbsp; Conformidade NR-7 · RDC 611/2022 · PCMSO</p>
    </div>
  </div>
</footer>

<!-- ── WHATSAPP FLOAT ──────────────────────────────────────────── -->
<a class="wa-float" href="https://wa.me/5521967269228?text=Olá%2C%20gostaria%20de%20conhecer%20o%20serviço%20de%20radiologia%20corporativa" target="_blank" rel="noopener" aria-label="WhatsApp">
  <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
    <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
  </svg>
</a>

<!-- ── JS ─────────────────────────────────────────────────────── -->
<script>
  /* Mobile Menu */
  const ham = document.getElementById('hamburger');
  const menu = document.getElementById('mobile-menu');
  ham.addEventListener('click', () => menu.classList.toggle('open'));
  function closeMobile() { menu.classList.remove('open'); }

  /* Scroll animation */
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); } });
  }, { threshold: 0.12 });
  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  /* Nav shadow on scroll */
  window.addEventListener('scroll', () => {
    document.getElementById('navbar').style.boxShadow = window.scrollY > 20 ? '0 2px 16px rgba(0,61,92,.1)' : 'none';
  });
</script>
</body>
</html>
