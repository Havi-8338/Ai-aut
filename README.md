<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Expert Option — Havilah Henry</title>
<link href="https://fonts.googleapis.com/css2?family=Clash+Display:wght@400;500;600;700&family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050810;
    --bg2: #080d1a;
    --card: #0d1425;
    --card2: #111827;
    --accent: #00e5ff;
    --accent2: #7b5ea7;
    --gold: #f0c060;
    --text: #f0f4ff;
    --muted: #8892a4;
    --border: rgba(0,229,255,0.12);
    --glow: 0 0 40px rgba(0,229,255,0.15);
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    overflow-x: hidden;
    line-height: 1.6;
  }

  /* ── NOISE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: 0.4;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 1.2rem 5%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: rgba(5,8,16,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
  }

  .nav-logo {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1.1rem;
    letter-spacing: -0.02em;
    color: var(--accent);
  }

  .nav-logo span { color: var(--text); }

  nav a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  nav a:hover { color: var(--accent); }

  .nav-cta {
    background: var(--accent);
    color: var(--bg) !important;
    padding: 0.5rem 1.2rem;
    border-radius: 50px;
    font-weight: 700 !important;
    transition: opacity 0.2s !important;
  }

  .nav-cta:hover { opacity: 0.85; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 7rem 5% 5rem;
    position: relative;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 60% 40%, rgba(0,229,255,0.07) 0%, transparent 70%),
      radial-gradient(ellipse 50% 50% at 20% 80%, rgba(123,94,167,0.1) 0%, transparent 60%);
  }

  .hero-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    width: 100%;
    position: relative;
    z-index: 1;
  }

  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: rgba(0,229,255,0.08);
    border: 1px solid rgba(0,229,255,0.2);
    padding: 0.4rem 1rem;
    border-radius: 50px;
    font-size: 0.78rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 1.5rem;
    animation: fadeUp 0.6s ease both;
  }

  .hero-badge::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(1.3); }
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.4rem, 5vw, 4rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 1.5rem;
    animation: fadeUp 0.6s 0.1s ease both;
  }

  h1 .highlight {
    background: linear-gradient(135deg, var(--accent), #0099ff);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-sub {
    font-size: 1.05rem;
    color: var(--muted);
    line-height: 1.7;
    max-width: 480px;
    margin-bottom: 2.5rem;
    animation: fadeUp 0.6s 0.2s ease both;
  }

  .hero-btns {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
    animation: fadeUp 0.6s 0.3s ease both;
  }

  .btn-primary {
    background: linear-gradient(135deg, var(--accent), #0099ff);
    color: var(--bg);
    padding: 0.85rem 2rem;
    border-radius: 50px;
    font-weight: 700;
    font-size: 0.95rem;
    text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 4px 20px rgba(0,229,255,0.3);
  }

  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 30px rgba(0,229,255,0.4);
  }

  .btn-ghost {
    border: 1px solid var(--border);
    color: var(--text);
    padding: 0.85rem 2rem;
    border-radius: 50px;
    font-weight: 500;
    font-size: 0.95rem;
    text-decoration: none;
    transition: border-color 0.2s, color 0.2s;
  }

  .btn-ghost:hover {
    border-color: var(--accent);
    color: var(--accent);
  }

  /* ── HERO IMAGE ── */
  .hero-visual {
    position: relative;
    animation: fadeUp 0.6s 0.2s ease both;
  }

  .hero-img-wrap {
    position: relative;
    width: 100%;
    max-width: 420px;
    margin: 0 auto;
  }

  .hero-img-wrap::before {
    content: '';
    position: absolute;
    inset: -2px;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent));
    border-radius: 24px;
    z-index: 0;
    animation: borderRotate 4s linear infinite;
  }

  @keyframes borderRotate {
    0% { background-position: 0% 50%; }
    100% { background-position: 200% 50%; }
  }

  .hero-img-wrap img {
    width: 100%;
    height: 480px;
    object-fit: cover;
    object-position: center top;
    border-radius: 22px;
    position: relative;
    z-index: 1;
    display: block;
  }

  .hero-tag {
    position: absolute;
    bottom: -16px;
    left: -16px;
    background: var(--card);
    border: 1px solid var(--border);
    padding: 0.8rem 1.2rem;
    border-radius: 14px;
    z-index: 2;
    backdrop-filter: blur(10px);
  }

  .hero-tag .label { font-size: 0.7rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.06em; }
  .hero-tag .value { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 1rem; color: var(--accent); }

  .hero-tag2 {
    position: absolute;
    top: 20px;
    right: -16px;
    background: var(--card);
    border: 1px solid var(--border);
    padding: 0.6rem 1rem;
    border-radius: 12px;
    z-index: 2;
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--gold);
    display: flex;
    align-items: center;
    gap: 0.4rem;
  }

  /* ── STATS ── */
  .stats {
    padding: 3rem 5%;
    position: relative;
    z-index: 1;
  }

  .stats-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 20px;
    overflow: hidden;
  }

  .stat {
    background: var(--card);
    padding: 2rem;
    text-align: center;
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2.2rem;
    font-weight: 800;
    color: var(--accent);
    line-height: 1;
    margin-bottom: 0.3rem;
  }

  .stat-label { font-size: 0.85rem; color: var(--muted); }

  /* ── SECTION HEADER ── */
  .section-tag {
    display: inline-block;
    font-size: 0.75rem;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.8rem;
  }

  h2 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(1.8rem, 3.5vw, 2.8rem);
    font-weight: 800;
    letter-spacing: -0.02em;
    line-height: 1.15;
    margin-bottom: 1rem;
  }

  /* ── ABOUT ── */
  .about {
    padding: 6rem 5%;
    position: relative;
    z-index: 1;
  }

  .about-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1.4fr;
    gap: 5rem;
    align-items: center;
  }

  .about-img {
    position: relative;
  }

  .about-img img {
    width: 100%;
    max-width: 360px;
    border-radius: 20px;
    object-fit: cover;
    object-position: center top;
    height: 420px;
    filter: grayscale(20%) contrast(1.05);
  }

  .about-img::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,229,255,0.1), transparent 60%);
    border-radius: 20px;
    max-width: 360px;
  }

  .about-skills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
    margin-top: 1.8rem;
  }

  .skill-tag {
    background: rgba(0,229,255,0.06);
    border: 1px solid rgba(0,229,255,0.15);
    color: var(--accent);
    padding: 0.4rem 1rem;
    border-radius: 50px;
    font-size: 0.8rem;
    font-weight: 500;
  }

  .about-text p {
    color: var(--muted);
    font-size: 1rem;
    line-height: 1.8;
    margin-bottom: 1rem;
  }

  /* ── COURSES ── */
  .courses {
    padding: 6rem 5%;
    position: relative;
    z-index: 1;
  }

  .courses::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
  }

  .courses-header {
    max-width: 1200px;
    margin: 0 auto 3.5rem;
    text-align: center;
  }

  .courses-grid {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }

  .course-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 24px;
    padding: 2.5rem;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s, border-color 0.3s, box-shadow 0.3s;
  }

  .course-card:hover {
    transform: translateY(-6px);
    border-color: rgba(0,229,255,0.3);
    box-shadow: var(--glow);
  }

  .course-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
  }

  .course-card:nth-child(2)::before {
    background: linear-gradient(90deg, var(--accent2), var(--gold));
  }

  .course-icon {
    width: 52px; height: 52px;
    border-radius: 14px;
    background: rgba(0,229,255,0.08);
    border: 1px solid rgba(0,229,255,0.15);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.4rem;
    margin-bottom: 1.5rem;
  }

  .course-card:nth-child(2) .course-icon {
    background: rgba(123,94,167,0.1);
    border-color: rgba(123,94,167,0.2);
  }

  .course-name {
    font-family: 'Syne', sans-serif;
    font-size: 1.4rem;
    font-weight: 700;
    margin-bottom: 0.8rem;
    letter-spacing: -0.01em;
  }

  .course-desc {
    color: var(--muted);
    font-size: 0.92rem;
    line-height: 1.7;
    margin-bottom: 1.5rem;
  }

  .course-features {
    list-style: none;
    margin-bottom: 2rem;
  }

  .course-features li {
    display: flex;
    align-items: flex-start;
    gap: 0.7rem;
    font-size: 0.88rem;
    color: var(--muted);
    padding: 0.45rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }

  .course-features li:last-child { border-bottom: none; }

  .course-features li::before {
    content: '✦';
    color: var(--accent);
    font-size: 0.65rem;
    margin-top: 0.25rem;
    flex-shrink: 0;
  }

  .course-card:nth-child(2) .course-features li::before {
    color: var(--accent2);
  }

  .course-footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: auto;
    padding-top: 1.5rem;
    border-top: 1px solid var(--border);
  }

  .course-price {
    font-family: 'Syne', sans-serif;
    font-size: 1.6rem;
    font-weight: 800;
    color: var(--text);
  }

  .course-price span {
    font-size: 0.85rem;
    color: var(--muted);
    font-weight: 400;
    font-family: 'DM Sans', sans-serif;
    margin-left: 0.2rem;
  }

  .btn-enroll {
    background: linear-gradient(135deg, var(--accent), #0099ff);
    color: var(--bg);
    padding: 0.7rem 1.5rem;
    border-radius: 50px;
    font-weight: 700;
    font-size: 0.85rem;
    text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 4px 15px rgba(0,229,255,0.25);
    white-space: nowrap;
  }

  .btn-enroll:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(0,229,255,0.35);
  }

  .course-card:nth-child(2) .btn-enroll {
    background: linear-gradient(135deg, var(--accent2), #9b6fd4);
    box-shadow: 0 4px 15px rgba(123,94,167,0.3);
  }

  /* ── HOW IT WORKS ── */
  .how {
    padding: 6rem 5%;
    position: relative;
    z-index: 1;
    background: var(--bg2);
  }

  .how-inner {
    max-width: 1200px;
    margin: 0 auto;
  }

  .how-header { text-align: center; margin-bottom: 3.5rem; }

  .steps {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1.5rem;
    position: relative;
  }

  .steps::before {
    content: '';
    position: absolute;
    top: 28px;
    left: 12%;
    right: 12%;
    height: 1px;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent));
    opacity: 0.3;
  }

  .step {
    text-align: center;
    position: relative;
  }

  .step-num {
    width: 56px; height: 56px;
    border-radius: 50%;
    background: var(--card);
    border: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1rem;
    color: var(--accent);
    margin: 0 auto 1rem;
    position: relative;
    z-index: 1;
  }

  .step-title {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 0.95rem;
    margin-bottom: 0.5rem;
  }

  .step-desc {
    font-size: 0.82rem;
    color: var(--muted);
    line-height: 1.6;
  }

  /* ── PAYMENT ── */
  .payment {
    padding: 6rem 5%;
    position: relative;
    z-index: 1;
  }

  .payment-inner {
    max-width: 700px;
    margin: 0 auto;
    text-align: center;
  }

  .payment-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 24px;
    padding: 3rem;
    margin-top: 2.5rem;
    position: relative;
    overflow: hidden;
  }

  .payment-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at top, rgba(0,229,255,0.05), transparent 60%);
    pointer-events: none;
  }

  .bank-details {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 1.5rem 2rem;
    margin: 1.5rem 0;
    text-align: left;
  }

  .bank-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.6rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }

  .bank-row:last-child { border-bottom: none; }

  .bank-label { font-size: 0.78rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.06em; }
  .bank-value { font-family: 'Syne', sans-serif; font-weight: 600; font-size: 0.95rem; }
  .bank-value.accent { color: var(--accent); font-size: 1.1rem; letter-spacing: 0.05em; }

  .payment-steps {
    text-align: left;
    margin-top: 1.5rem;
  }

  .payment-step {
    display: flex;
    gap: 1rem;
    align-items: flex-start;
    padding: 0.8rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }

  .payment-step:last-child { border-bottom: none; }

  .pstep-num {
    width: 28px; height: 28px;
    border-radius: 50%;
    background: rgba(0,229,255,0.1);
    border: 1px solid rgba(0,229,255,0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.75rem;
    font-weight: 700;
    color: var(--accent);
    flex-shrink: 0;
    margin-top: 0.1rem;
  }

  .pstep-text { font-size: 0.9rem; color: var(--muted); line-height: 1.6; }
  .pstep-text strong { color: var(--text); }

  .wa-btn {
    display: inline-flex;
    align-items: center;
    gap: 0.6rem;
    background: #25D366;
    color: #fff;
    padding: 0.85rem 2rem;
    border-radius: 50px;
    font-weight: 700;
    font-size: 0.95rem;
    text-decoration: none;
    margin-top: 1.5rem;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 4px 20px rgba(37,211,102,0.3);
  }

  .wa-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(37,211,102,0.4);
  }

  /* ── FAQ ── */
  .faq {
    padding: 6rem 5%;
    background: var(--bg2);
    position: relative;
    z-index: 1;
  }

  .faq-inner {
    max-width: 720px;
    margin: 0 auto;
  }

  .faq-header { text-align: center; margin-bottom: 3rem; }

  .faq-item {
    border-bottom: 1px solid var(--border);
    padding: 1.3rem 0;
  }

  .faq-q {
    font-family: 'Syne', sans-serif;
    font-weight: 600;
    font-size: 0.98rem;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
    transition: color 0.2s;
    user-select: none;
  }

  .faq-q:hover { color: var(--accent); }

  .faq-q .icon {
    color: var(--accent);
    font-size: 1.2rem;
    flex-shrink: 0;
    transition: transform 0.3s;
  }

  .faq-a {
    font-size: 0.9rem;
    color: var(--muted);
    line-height: 1.7;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.4s ease, padding 0.3s;
  }

  .faq-item.open .faq-a {
    max-height: 200px;
    padding-top: 0.8rem;
  }

  .faq-item.open .icon { transform: rotate(45deg); }

  /* ── FOOTER ── */
  footer {
    padding: 3rem 5%;
    border-top: 1px solid var(--border);
    position: relative;
    z-index: 1;
  }

  .footer-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .footer-brand {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1rem;
    color: var(--accent);
  }

  .footer-links { display: flex; gap: 1.5rem; }

  .footer-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.85rem;
    transition: color 0.2s;
  }

  .footer-links a:hover { color: var(--accent); }

  .footer-copy { font-size: 0.78rem; color: var(--muted); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    .hero-grid { grid-template-columns: 1fr; text-align: center; }
    .hero-sub { margin: 0 auto 2.5rem; }
    .hero-btns { justify-content: center; }
    .hero-visual { order: -1; }
    .hero-img-wrap { max-width: 280px; }
    .hero-img-wrap img { height: 340px; }
    .about-inner { grid-template-columns: 1fr; }
    .about-img { display: none; }
    .courses-grid { grid-template-columns: 1fr; }
    .steps { grid-template-columns: repeat(2, 1fr); }
    .steps::before { display: none; }
    .stats-inner { grid-template-columns: 1fr; }
    .footer-inner { flex-direction: column; text-align: center; }
  }

  @media (max-width: 600px) {
    .hero { padding: 6rem 5% 3rem; }
    .hero-tag, .hero-tag2 { display: none; }
    .nav-logo { font-size: 0.95rem; }
    h1 { font-size: 2rem; }
    .steps { grid-template-columns: 1fr; }
    .payment-card { padding: 1.5rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">AI<span>Expert</span>Option</div>
  <div style="display:flex;gap:2rem;align-items:center;">
    <a href="#courses">Courses</a>
    <a href="#about">About</a>
    <a href="#payment" class="nav-cta">Enroll Now</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid">
    <div class="hero-content">
      <div class="hero-badge">AI Creator & Educator</div>
      <h1>Learn How to Use AI to <span class="highlight">Create, Build & Grow</span></h1>
      <p class="hero-sub">Practical AI education for creators, entrepreneurs, and side hustlers who are ready to work smarter — not harder. No fluff. Just results.</p>
      <div class="hero-btns">
        <a href="#courses" class="btn-primary">See Courses →</a>
        <a href="#about" class="btn-ghost">About Havilah</a>
      </div>
    </div>
    <div class="hero-visual">
      <div class="hero-img-wrap">
        <img src="/mnt/user-data/uploads/IMG-20260313-WA0062.jpg" alt="Havilah Henry — AI Expert">
        <div class="hero-tag">
          <div class="label">Courses Available</div>
          <div class="value">2 Live Now</div>
        </div>
        <div class="hero-tag2">⭐ AI Expert</div>
      </div>
    </div>
  </div>
</section>

<!-- STATS -->
<section class="stats">
  <div class="stats-inner">
    <div class="stat">
      <div class="stat-num">2</div>
      <div class="stat-label">Courses Available</div>
    </div>
    <div class="stat">
      <div class="stat-num">AI</div>
      <div class="stat-label">Tools Taught Hands-On</div>
    </div>
    <div class="stat">
      <div class="stat-num">₦30K</div>
      <div class="stat-label">Per Course — One-Time Fee</div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-inner">
    <div class="about-img">
      <img src="/mnt/user-data/uploads/IMG-20260313-WA0062.jpg" alt="Havilah Henry">
    </div>
    <div class="about-text">
      <span class="section-tag">About Your Instructor</span>
      <h2>Hi, I'm Havilah 👋🏾</h2>
      <p>I'm an AI automation and video creation expert with a deep focus on using artificial intelligence to build efficient, flexible, and profitable workflows.</p>
      <p>From prompt engineering and AI-generated content to business automation and faceless video creation — I've spent years mastering the tools that are reshaping how we work and create online.</p>
      <p>My mission is simple: to show you exactly how I use AI in real life, so you can do the same — faster, smarter, and with less effort.</p>
      <div class="about-skills">
        <span class="skill-tag">AI Video Creation</span>
        <span class="skill-tag">Prompt Engineering</span>
        <span class="skill-tag">AI Automation</span>
        <span class="skill-tag">Faceless Content</span>
        <span class="skill-tag">AI Productivity</span>
        <span class="skill-tag">Business Workflows</span>
      </div>
    </div>
  </div>
</section>

<!-- COURSES -->
<section class="courses" id="courses">
  <div class="courses-header">
    <span class="section-tag">What You'll Learn</span>
    <h2>Choose Your Course</h2>
    <p style="color:var(--muted);max-width:500px;margin:0 auto;font-size:0.95rem;">Two focused, practical courses designed to give you real skills you can use immediately.</p>
  </div>
  <div class="courses-grid">

    <!-- Course 1 -->
    <div class="course-card">
      <div class="course-icon">🎬</div>
      <div class="course-name">Faceless Automation</div>
      <p class="course-desc">Learn how to create high-quality faceless videos for social media — without showing your face, without expensive equipment, and without spending hours editing. Then turn that content into income.</p>
      <ul class="course-features">
        <li>What faceless content is and why it's exploding right now</li>
        <li>The exact AI tools used to generate videos from scratch</li>
        <li>How to script, voice, and edit videos entirely with AI</li>
        <li>Best platforms to publish faceless content for growth</li>
        <li>Monetisation strategies — brand deals, digital products & more</li>
        <li>How to stay consistent without burning out</li>
      </ul>
      <div class="course-footer">
        <div class="course-price">₦30,000 <span>one-time</span></div>
        <a href="#payment" class="btn-enroll">Enroll Now →</a>
      </div>
    </div>

    <!-- Course 2 -->
    <div class="course-card">
      <div class="course-icon">⚡</div>
      <div class="course-name">Prompting Mastery</div>
      <p class="course-desc">Unlock the full power of AI by learning how to communicate with it like a pro. Prompt engineering is the most valuable skill in the AI era — and this course teaches you to use it across content, business, and productivity.</p>
      <ul class="course-features">
        <li>What prompt engineering actually is (and why most people do it wrong)</li>
        <li>The frameworks behind writing prompts that get elite results</li>
        <li>How to use AI for writing, design, research and content creation</li>
        <li>Advanced prompting for ChatGPT, Claude, Midjourney & more</li>
        <li>Real-world use cases: business, content, automation, and income</li>
        <li>Build a personal AI workflow that works for your goals</li>
      </ul>
      <div class="course-footer">
        <div class="course-price">₦30,000 <span>one-time</span></div>
        <a href="#payment" class="btn-enroll">Enroll Now →</a>
      </div>
    </div>

  </div>
</section>

<!-- HOW IT WORKS -->
<section class="how">
  <div class="how-inner">
    <div class="how-header">
      <span class="section-tag">The Process</span>
      <h2>How to Get Started</h2>
    </div>
    <div class="steps">
      <div class="step">
        <div class="step-num">01</div>
        <div class="step-title">Pick Your Course</div>
        <p class="step-desc">Choose either Faceless Automation or Prompting Mastery — or both.</p>
      </div>
      <div class="step">
        <div class="step-num">02</div>
        <div class="step-title">Make Payment</div>
        <p class="step-desc">Transfer ₦30,000 to the bank account details below.</p>
      </div>
      <div class="step">
        <div class="step-num">03</div>
        <div class="step-title">Send Proof</div>
        <p class="step-desc">Screenshot your receipt and send it to Havilah on WhatsApp.</p>
      </div>
      <div class="step">
        <div class="step-num">04</div>
        <div class="step-title">Get Instant Access</div>
        <p class="step-desc">Receive your Telegram course link and start learning immediately.</p>
      </div>
    </div>
  </div>
</section>

<!-- PAYMENT -->
<section class="payment" id="payment">
  <div class="payment-inner">
    <span class="section-tag">Secure Payment</span>
    <h2>Ready to Enroll?</h2>
    <p style="color:var(--muted);margin-top:0.5rem;font-size:0.95rem;">Make your payment below and get instant access to your chosen course.</p>

    <div class="payment-card">
      <p style="font-family:'Syne',sans-serif;font-weight:700;font-size:1rem;margin-bottom:1rem;">Bank Transfer Details</p>
      <div class="bank-details">
        <div class="bank-row">
          <span class="bank-label">Account Number</span>
          <span class="bank-value accent">6971930547</span>
        </div>
        <div class="bank-row">
          <span class="bank-label">Bank Name</span>
          <span class="bank-value">Fidelity Bank</span>
        </div>
        <div class="bank-row">
          <span class="bank-label">Account Name</span>
          <span class="bank-value">Havilah Henry Nduoyo</span>
        </div>
        <div class="bank-row">
          <span class="bank-label">Amount</span>
          <span class="bank-value accent">₦30,000</span>
        </div>
      </div>

      <div class="payment-steps">
        <p style="font-size:0.85rem;color:var(--muted);font-weight:600;text-transform:uppercase;letter-spacing:0.07em;margin-bottom:0.5rem;">After Payment</p>
        <div class="payment-step">
          <div class="pstep-num">1</div>
          <p class="pstep-text">Take a <strong>screenshot of your payment receipt</strong></p>
        </div>
        <div class="payment-step">
          <div class="pstep-num">2</div>
          <p class="pstep-text">Send the screenshot to <strong>Havilah on WhatsApp</strong> with the course name</p>
        </div>
        <div class="payment-step">
          <div class="pstep-num">3</div>
          <p class="pstep-text">Receive your <strong>Telegram course access link</strong> instantly ✅</p>
        </div>
      </div>

      <a href="https://wa.me/2349000000000?text=Hi%20Havilah!%20I%20just%20made%20payment%20for%20a%20course.%20Here%20is%20my%20proof%20of%20payment%20%F0%9F%91%87" class="wa-btn" target="_blank">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
        Send Payment Proof on WhatsApp
      </a>
      <p style="font-size:0.75rem;color:var(--muted);margin-top:1rem;">⚡ Access is granted within minutes of payment confirmation</p>
    </div>
  </div>
</section>

<!-- FAQ -->
<section class="faq">
  <div class="faq-inner">
    <div class="faq-header">
      <span class="section-tag">Questions</span>
      <h2>FAQ</h2>
    </div>

    <div class="faq-item open">
      <div class="faq-q" onclick="toggleFaq(this)">
        How do I get access after payment? <span class="icon">+</span>
      </div>
      <div class="faq-a">After you transfer ₦30,000 and send your receipt to WhatsApp, Havilah will verify your payment and send you a Telegram invite link. Access is typically granted within minutes.</div>
    </div>

    <div class="faq-item">
      <div class="faq-q" onclick="toggleFaq(this)">
        Do I need prior AI experience? <span class="icon">+</span>
      </div>
      <div class="faq-a">Not at all. Both courses are designed to take you from beginner to confident user. As long as you're willing to learn and take action, you'll get results.</div>
    </div>

    <div class="faq-item">
      <div class="faq-q" onclick="toggleFaq(this)">
        How long do I have access to the course? <span class="icon">+</span>
      </div>
      <div class="faq-a">Once you're added to the Telegram group, you have lifetime access. You can revisit the materials as many times as you need.</div>
    </div>

    <div class="faq-item">
      <div class="faq-q" onclick="toggleFaq(this)">
        Can I buy both courses? <span class="icon">+</span>
      </div>
      <div class="faq-a">Absolutely! You can purchase both courses. Simply make two separate transfers of ₦30,000 each and send proof for both in the same WhatsApp message.</div>
    </div>

    <div class="faq-item">
      <div class="faq-q" onclick="toggleFaq(this)">
        Is there a refund policy? <span class="icon">+</span>
      </div>
      <div class="faq-a">Due to the nature of digital course content, all sales are final. Please review the course descriptions carefully before purchasing. If you have questions before buying, reach out on WhatsApp first.</div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-brand">AIExpertOption</div>
    <div class="footer-links">
      <a href="https://instagram.com" target="_blank">Instagram</a>
      <a href="https://tiktok.com" target="_blank">TikTok</a>
      <a href="https://wa.me/2349036268338" target="_blank">WhatsApp</a>
    </div>
    <p class="footer-copy">© 2026 Havilah Henry Nduoyo. All rights reserved.</p>
  </div>
</footer>

<script>
  function toggleFaq(el) {
    const item = el.parentElement;
    const isOpen = item.classList.contains('open');
    document.querySelectorAll('.faq-item').forEach(i => i.classList.remove('open'));
    if (!isOpen) item.classList.add('open');
  }
</script>

</body>
</html>
