[Salon 1.html](https://github.com/user-attachments/files/29508055/Salon.1.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>NOIR & CO. — Luxury Men's Grooming</title>
<meta name="description" content="Noir & Co. — Lahore's premier luxury men's salon. Precision cuts, royal shaves, and bespoke grooming experiences crafted for the discerning gentleman." />
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400;1,600&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #0B0B0B;
    --charcoal: #1A1A1A;
    --charcoal-light: #252525;
    --gold: #C7A65A;
    --gold-dark: #A88840;
    --gold-pale: rgba(199,166,90,0.12);
    --white: #FAFAF8;
    --muted: #888;
    --border: rgba(199,166,90,0.2);
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'Inter', sans-serif;
    font-size: 15px;
    line-height: 1.65;
    overflow-x: hidden;
  }

  /* ─── TYPOGRAPHY ─── */
  .serif { font-family: 'Cormorant Garamond', Georgia, serif; }
  .gold { color: var(--gold); }

  h1, h2, h3, h4 { font-family: 'Cormorant Garamond', Georgia, serif; font-weight: 400; line-height: 1.1; }

  .eyebrow {
    font-family: 'Inter', sans-serif;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: .22em;
    text-transform: uppercase;
    color: var(--gold);
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .eyebrow::before { content: ''; display: inline-block; width: 24px; height: 1px; background: var(--gold); }

  /* ─── SCROLL ANIMATIONS ─── */
  .reveal {
    opacity: 0;
    transform: translateY(28px);
    transition: opacity .75s ease, transform .75s ease;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }
  .reveal-delay-1 { transition-delay: .1s; }
  .reveal-delay-2 { transition-delay: .2s; }
  .reveal-delay-3 { transition-delay: .32s; }
  .reveal-delay-4 { transition-delay: .44s; }

  /* ─── NAV ─── */
  #nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 1000;
    padding: 0 5vw;
    height: 70px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: background .4s, backdrop-filter .4s;
  }
  #nav.scrolled {
    background: rgba(11,11,11,.92);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid var(--border);
  }

  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 22px;
    font-weight: 600;
    letter-spacing: .12em;
    color: var(--white);
    text-decoration: none;
  }
  .nav-logo span { color: var(--gold); }

  .nav-links {
    display: flex;
    align-items: center;
    gap: 36px;
    list-style: none;
  }
  .nav-links a {
    font-size: 11px;
    font-weight: 500;
    letter-spacing: .16em;
    text-transform: uppercase;
    color: rgba(255,255,255,.72);
    text-decoration: none;
    transition: color .25s;
  }
  .nav-links a:hover { color: var(--gold); }

  .nav-cta {
    padding: 10px 26px;
    background: var(--gold);
    color: var(--black) !important;
    border-radius: 2px;
    font-weight: 600 !important;
  }
  .nav-cta:hover { background: var(--gold-dark) !important; color: var(--black) !important; }

  /* ─── HERO ─── */
  #hero {
    position: relative;
    height: 100vh;
    min-height: 700px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    overflow: hidden;
  }

  .hero-left {
    background: var(--black);
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0 6vw 0 6vw;
    position: relative;
    z-index: 2;
  }

  .hero-left::after {
    content: '';
    position: absolute;
    right: 0; top: 10%; bottom: 10%;
    width: 1px;
    background: linear-gradient(to bottom, transparent, var(--gold), transparent);
  }

  .hero-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 160px;
    font-weight: 300;
    color: rgba(199,166,90,.07);
    line-height: 1;
    position: absolute;
    top: 12%;
    left: 4vw;
    pointer-events: none;
    user-select: none;
  }

  .hero-title {
    font-size: clamp(52px, 6vw, 88px);
    font-weight: 300;
    line-height: 1.05;
    margin: 18px 0 28px;
    color: var(--white);
  }
  .hero-title em {
    font-style: italic;
    color: var(--gold);
  }

  .hero-sub {
    font-size: 14px;
    color: rgba(255,255,255,.55);
    line-height: 1.75;
    max-width: 360px;
    margin-bottom: 44px;
  }

  .hero-actions { display: flex; gap: 16px; align-items: center; }

  .btn-primary {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    padding: 15px 34px;
    background: var(--gold);
    color: var(--black);
    font-family: 'Inter', sans-serif;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: .15em;
    text-transform: uppercase;
    text-decoration: none;
    border-radius: 2px;
    transition: background .25s, transform .2s;
  }
  .btn-primary:hover { background: var(--gold-dark); transform: translateY(-1px); }
  .btn-primary svg { flex-shrink: 0; }

  .btn-ghost {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 15px 24px;
    border: 1px solid var(--border);
    color: rgba(255,255,255,.65);
    font-size: 11px;
    font-weight: 500;
    letter-spacing: .14em;
    text-transform: uppercase;
    text-decoration: none;
    border-radius: 2px;
    transition: border-color .25s, color .25s;
  }
  .btn-ghost:hover { border-color: var(--gold); color: var(--gold); }

  .hero-stats {
    display: flex;
    gap: 40px;
    margin-top: 60px;
    padding-top: 36px;
    border-top: 1px solid var(--border);
  }
  .stat-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 36px;
    font-weight: 600;
    color: var(--gold);
    line-height: 1;
  }
  .stat-label {
    font-size: 10px;
    color: var(--muted);
    letter-spacing: .12em;
    text-transform: uppercase;
    margin-top: 4px;
  }

  .hero-image {
    position: relative;
    overflow: hidden;
  }
  .hero-image img {
    width: 100%; height: 100%;
    object-fit: cover;
    filter: brightness(.75) saturate(.85);
    transform: scale(1.03);
    transition: transform 8s ease;
  }
  #hero:hover .hero-image img { transform: scale(1); }

  .hero-image-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(90deg, var(--black) 0%, transparent 30%);
  }

  .hero-badge {
    position: absolute;
    bottom: 40px;
    right: 40px;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    border: 1px solid var(--gold);
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-family: 'Cormorant Garamond', serif;
    font-size: 12px;
    line-height: 1.4;
    color: var(--gold);
    background: rgba(11,11,11,.7);
    backdrop-filter: blur(8px);
  }

  /* ─── TRUST BAR ─── */
  #trust {
    background: var(--charcoal);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 22px 6vw;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 24px;
    overflow: hidden;
  }

  .trust-item {
    display: flex;
    align-items: center;
    gap: 12px;
    white-space: nowrap;
    flex-shrink: 0;
  }
  .trust-icon {
    width: 28px;
    height: 28px;
    color: var(--gold);
    flex-shrink: 0;
  }
  .trust-text strong {
    display: block;
    font-size: 12px;
    font-weight: 600;
    letter-spacing: .05em;
    color: var(--white);
  }
  .trust-text span {
    font-size: 10px;
    color: var(--muted);
    letter-spacing: .08em;
  }

  .trust-divider {
    width: 1px;
    height: 32px;
    background: var(--border);
    flex-shrink: 0;
  }

  /* ─── SECTIONS GENERAL ─── */
  section { padding: 110px 6vw; }

  .section-header { margin-bottom: 64px; }
  .section-header .eyebrow { margin-bottom: 18px; }
  .section-title {
    font-size: clamp(38px, 4vw, 62px);
    font-weight: 300;
    line-height: 1.1;
    max-width: 600px;
  }
  .section-title em { font-style: italic; color: var(--gold); }

  .section-lead {
    font-size: 15px;
    color: rgba(255,255,255,.52);
    line-height: 1.8;
    max-width: 480px;
    margin-top: 20px;
  }

  /* ─── ABOUT ─── */
  #about {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
    padding: 110px 6vw;
  }

  .about-image-wrap {
    position: relative;
  }
  .about-image-wrap img {
    width: 100%;
    aspect-ratio: 4/5;
    object-fit: cover;
    border-radius: 3px;
    filter: brightness(.85);
  }
  .about-image-tag {
    position: absolute;
    bottom: -20px;
    right: -20px;
    background: var(--gold);
    color: var(--black);
    padding: 18px 24px;
    font-family: 'Cormorant Garamond', serif;
    font-size: 14px;
    font-weight: 600;
    border-radius: 2px;
    text-align: center;
    line-height: 1.4;
  }
  .about-image-tag strong { display: block; font-size: 28px; font-weight: 700; line-height: 1; }

  .about-text .section-title { max-width: 100%; }

  .about-copy {
    margin: 28px 0 40px;
    font-size: 15px;
    line-height: 1.9;
    color: rgba(255,255,255,.6);
  }

  .about-features {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin-top: 36px;
  }
  .about-feat {
    padding: 18px 20px;
    border: 1px solid var(--border);
    border-radius: 3px;
    background: var(--charcoal);
  }
  .about-feat-icon { color: var(--gold); margin-bottom: 8px; }
  .about-feat h4 { font-size: 16px; font-weight: 500; margin-bottom: 4px; }
  .about-feat p { font-size: 12px; color: var(--muted); line-height: 1.6; }

  /* ─── SERVICES ─── */
  #services { background: var(--charcoal); }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2px;
    margin-top: 56px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .service-card {
    background: var(--charcoal);
    padding: 40px 32px;
    position: relative;
    transition: background .3s;
    cursor: pointer;
  }
  .service-card:hover { background: var(--charcoal-light); }
  .service-card:hover .service-arrow { opacity: 1; transform: translateX(0); }

  .service-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: 11px;
    color: var(--gold);
    letter-spacing: .18em;
    margin-bottom: 24px;
  }
  .service-icon { color: var(--gold); margin-bottom: 20px; }
  .service-card h3 {
    font-size: 22px;
    font-weight: 400;
    margin-bottom: 12px;
    line-height: 1.2;
  }
  .service-desc { font-size: 12px; color: var(--muted); line-height: 1.7; margin-bottom: 28px; }

  .service-price {
    font-family: 'Cormorant Garamond', serif;
    font-size: 28px;
    font-weight: 600;
    color: var(--gold);
    line-height: 1;
  }
  .service-price span { font-size: 13px; color: var(--muted); font-family: 'Inter', sans-serif; font-weight: 400; }

  .service-arrow {
    position: absolute;
    bottom: 36px; right: 28px;
    color: var(--gold);
    opacity: 0;
    transform: translateX(-8px);
    transition: opacity .25s, transform .25s;
  }

  /* ─── WEEKEND DEALS ─── */
  #deals {
    background: linear-gradient(135deg, var(--charcoal-light) 0%, var(--black) 100%);
    position: relative;
    overflow: hidden;
  }
  #deals::before {
    content: 'OFFER';
    position: absolute;
    right: -2vw;
    top: 50%;
    transform: translateY(-50%) rotate(90deg);
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(80px, 12vw, 160px);
    font-weight: 700;
    color: rgba(199,166,90,.04);
    pointer-events: none;
    letter-spacing: .1em;
  }

  .deals-grid {
    display: grid;
    grid-template-columns: 1.4fr 1fr 1fr;
    gap: 24px;
    margin-top: 56px;
  }

  .deal-card {
    position: relative;
    border-radius: 4px;
    overflow: hidden;
    min-height: 320px;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 32px;
    background: var(--charcoal);
    border: 1px solid var(--border);
    transition: transform .3s;
  }
  .deal-card:hover { transform: translateY(-4px); }
  .deal-card.featured { border-color: var(--gold); }

  .deal-badge {
    position: absolute;
    top: 20px; right: 20px;
    background: var(--gold);
    color: var(--black);
    font-size: 10px;
    font-weight: 700;
    letter-spacing: .12em;
    text-transform: uppercase;
    padding: 5px 12px;
    border-radius: 1px;
  }

  .deal-tag { margin-bottom: 12px; }
  .deal-card h3 {
    font-size: 26px;
    font-weight: 400;
    margin-bottom: 10px;
    line-height: 1.2;
  }
  .deal-card p { font-size: 12px; color: var(--muted); margin-bottom: 22px; line-height: 1.6; }

  .deal-pricing {
    display: flex;
    align-items: baseline;
    gap: 10px;
    margin-bottom: 20px;
  }
  .deal-new {
    font-family: 'Cormorant Garamond', serif;
    font-size: 32px;
    font-weight: 600;
    color: var(--gold);
  }
  .deal-old {
    font-size: 13px;
    color: var(--muted);
    text-decoration: line-through;
  }

  /* ─── GALLERY ─── */
  #gallery { padding: 110px 0; background: var(--black); }
  #gallery .section-header { padding: 0 6vw; }

  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: 240px 240px;
    gap: 3px;
    margin-top: 48px;
  }

  .gallery-item {
    overflow: hidden;
    position: relative;
    background: var(--charcoal);
  }
  .gallery-item:nth-child(1) { grid-column: span 2; grid-row: span 2; }
  .gallery-item:nth-child(4) { grid-column: span 2; }

  .gallery-item img {
    width: 100%; height: 100%;
    object-fit: cover;
    filter: brightness(.8) saturate(.7);
    transition: filter .4s, transform .5s;
  }
  .gallery-item:hover img { filter: brightness(1) saturate(1); transform: scale(1.05); }

  .gallery-overlay {
    position: absolute;
    inset: 0;
    background: rgba(199,166,90,0);
    display: flex;
    align-items: center;
    justify-content: center;
    transition: background .3s;
  }
  .gallery-item:hover .gallery-overlay { background: rgba(199,166,90,0.1); }
  .gallery-overlay svg { color: var(--gold); opacity: 0; transition: opacity .3s; }
  .gallery-item:hover .gallery-overlay svg { opacity: 1; }

  /* ─── TEAM ─── */
  #team { background: var(--charcoal); }

  .team-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 24px;
    margin-top: 56px;
  }

  .team-card {
    background: var(--black);
    border-radius: 4px;
    overflow: hidden;
    border: 1px solid transparent;
    transition: border-color .3s, transform .3s;
  }
  .team-card:hover { border-color: var(--border); transform: translateY(-4px); }

  .team-img {
    position: relative;
    aspect-ratio: 3/4;
    overflow: hidden;
  }
  .team-img img { width: 100%; height: 100%; object-fit: cover; filter: brightness(.85) saturate(.8); transition: filter .4s; }
  .team-card:hover .team-img img { filter: brightness(1) saturate(1); }

  .team-socials {
    position: absolute;
    bottom: 16px; left: 50%;
    transform: translateX(-50%) translateY(12px);
    display: flex;
    gap: 8px;
    opacity: 0;
    transition: opacity .3s, transform .3s;
  }
  .team-card:hover .team-socials { opacity: 1; transform: translateX(-50%) translateY(0); }
  .team-socials a {
    width: 34px; height: 34px;
    background: rgba(11,11,11,.8);
    border: 1px solid var(--gold);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    color: var(--gold);
    text-decoration: none;
    backdrop-filter: blur(4px);
    font-size: 11px;
    font-weight: 700;
  }

  .team-info { padding: 22px 20px; }
  .team-info h3 { font-size: 20px; font-weight: 500; margin-bottom: 4px; }
  .team-info p { font-size: 11px; color: var(--gold); letter-spacing: .1em; text-transform: uppercase; }
  .team-spec { font-size: 11px; color: var(--muted); margin-top: 8px; line-height: 1.5; }

  /* ─── WHY CHOOSE US ─── */
  #why { background: var(--black); }

  .why-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 1px;
    margin-top: 56px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .why-item {
    padding: 48px 40px;
    background: var(--black);
    transition: background .3s;
  }
  .why-item:hover { background: var(--charcoal); }

  .why-icon {
    width: 52px; height: 52px;
    border: 1px solid var(--border);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    color: var(--gold);
    margin-bottom: 24px;
    transition: border-color .3s;
  }
  .why-item:hover .why-icon { border-color: var(--gold); }
  .why-item h3 { font-size: 22px; font-weight: 400; margin-bottom: 12px; }
  .why-item p { font-size: 13px; color: var(--muted); line-height: 1.7; }

  /* ─── PROCESS ─── */
  #process { background: var(--charcoal); }

  .process-steps {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0;
    margin-top: 64px;
    position: relative;
  }
  .process-steps::before {
    content: '';
    position: absolute;
    top: 28px; left: 10%; right: 10%;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
  }

  .process-step { padding: 0 24px; text-align: center; }
  .process-dot {
    width: 56px; height: 56px;
    border: 1px solid var(--gold);
    border-radius: 50%;
    background: var(--charcoal);
    display: flex; align-items: center; justify-content: center;
    margin: 0 auto 28px;
    color: var(--gold);
    position: relative;
    z-index: 1;
  }
  .process-step h3 { font-size: 20px; font-weight: 500; margin-bottom: 10px; }
  .process-step p { font-size: 12px; color: var(--muted); line-height: 1.7; }

  /* ─── TESTIMONIALS ─── */
  #testimonials { background: var(--black); }

  .testimonials-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    margin-top: 56px;
  }

  .testi-card {
    background: var(--charcoal);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 36px 32px;
    transition: border-color .3s;
  }
  .testi-card:hover { border-color: var(--gold); }

  .testi-stars { color: var(--gold); font-size: 14px; letter-spacing: 2px; margin-bottom: 18px; }
  .testi-quote {
    font-family: 'Cormorant Garamond', serif;
    font-size: 18px;
    font-style: italic;
    line-height: 1.65;
    color: rgba(255,255,255,.85);
    margin-bottom: 28px;
    font-weight: 300;
  }

  .testi-author { display: flex; align-items: center; gap: 14px; }
  .testi-avatar {
    width: 44px; height: 44px;
    border-radius: 50%;
    background: var(--gold-pale);
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Cormorant Garamond', serif;
    font-size: 18px;
    color: var(--gold);
    font-weight: 600;
    flex-shrink: 0;
  }
  .testi-name { font-size: 14px; font-weight: 600; }
  .testi-role { font-size: 11px; color: var(--muted); }

  /* ─── MEMBERSHIP ─── */
  #membership { background: var(--charcoal); }

  .membership-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    margin-top: 56px;
  }

  .plan-card {
    background: var(--black);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 44px 36px;
    position: relative;
    transition: border-color .3s, transform .3s;
  }
  .plan-card:hover { transform: translateY(-4px); }
  .plan-card.featured { border-color: var(--gold); }
  .plan-card.featured::before {
    content: 'Most Popular';
    position: absolute;
    top: -12px; left: 50%;
    transform: translateX(-50%);
    background: var(--gold);
    color: var(--black);
    font-size: 10px;
    font-weight: 700;
    letter-spacing: .12em;
    text-transform: uppercase;
    padding: 4px 16px;
    border-radius: 2px;
  }

  .plan-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 28px;
    font-weight: 400;
    margin-bottom: 6px;
  }
  .plan-tagline { font-size: 11px; color: var(--muted); letter-spacing: .1em; text-transform: uppercase; margin-bottom: 32px; }

  .plan-price {
    display: flex;
    align-items: baseline;
    gap: 4px;
    margin-bottom: 32px;
  }
  .plan-currency { font-size: 16px; color: var(--gold); font-weight: 600; margin-top: 6px; }
  .plan-amount {
    font-family: 'Cormorant Garamond', serif;
    font-size: 52px;
    font-weight: 600;
    color: var(--gold);
    line-height: 1;
  }
  .plan-period { font-size: 12px; color: var(--muted); align-self: flex-end; padding-bottom: 8px; }

  .plan-features { list-style: none; margin-bottom: 36px; }
  .plan-features li {
    font-size: 13px;
    color: rgba(255,255,255,.65);
    padding: 10px 0;
    border-bottom: 1px solid rgba(255,255,255,.06);
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .plan-features li::before { content: '✓'; color: var(--gold); font-weight: 700; font-size: 12px; flex-shrink: 0; }
  .plan-features li.disabled { color: var(--muted); opacity: .45; }
  .plan-features li.disabled::before { content: '—'; color: var(--muted); }

  /* ─── FAQ ─── */
  #faq { background: var(--black); }

  .faq-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    margin-top: 56px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .faq-item {
    background: var(--black);
    padding: 32px 36px;
    cursor: pointer;
    transition: background .25s;
  }
  .faq-item:hover { background: var(--charcoal); }
  .faq-q {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 16px;
    font-family: 'Cormorant Garamond', serif;
    font-size: 19px;
    font-weight: 400;
    color: var(--white);
    line-height: 1.3;
  }
  .faq-toggle {
    width: 26px; height: 26px;
    border: 1px solid var(--border);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    color: var(--gold);
    flex-shrink: 0;
    font-size: 16px;
    transition: transform .3s;
  }
  .faq-a {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.75;
    max-height: 0;
    overflow: hidden;
    transition: max-height .35s ease, margin-top .3s;
  }
  .faq-item.open .faq-toggle { transform: rotate(45deg); border-color: var(--gold); }
  .faq-item.open .faq-a { max-height: 200px; margin-top: 16px; }

  /* ─── BOOKING ─── */
  #booking {
    background: var(--charcoal);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
    padding: 0;
    overflow: hidden;
    min-height: 640px;
  }

  .booking-info {
    background: var(--gold);
    padding: 80px 6vw 80px 6vw;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .booking-info .eyebrow::before { background: var(--black); }
  .booking-info .eyebrow { color: rgba(0,0,0,.65); }
  .booking-info h2 { color: var(--black); font-size: clamp(36px, 3.5vw, 56px); margin: 18px 0 24px; }
  .booking-info p { color: rgba(0,0,0,.65); font-size: 14px; line-height: 1.75; margin-bottom: 36px; }

  .booking-contact-items { display: flex; flex-direction: column; gap: 16px; }
  .booking-contact-item {
    display: flex; align-items: center; gap: 14px;
    font-size: 13px; color: rgba(0,0,0,.7);
  }
  .booking-contact-item strong { color: var(--black); font-size: 14px; display: block; }

  .booking-form-wrap {
    background: var(--charcoal);
    padding: 80px 5vw 80px 5vw;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .booking-form-wrap h3 {
    font-size: 28px;
    font-weight: 400;
    margin-bottom: 36px;
    color: var(--white);
  }

  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 16px; }
  .form-group { display: flex; flex-direction: column; gap: 8px; margin-bottom: 16px; }
  .form-group label {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: .14em;
    text-transform: uppercase;
    color: var(--muted);
  }
  .form-group input,
  .form-group select,
  .form-group textarea {
    background: var(--black);
    border: 1px solid var(--border);
    border-radius: 2px;
    padding: 13px 16px;
    color: var(--white);
    font-family: 'Inter', sans-serif;
    font-size: 14px;
    transition: border-color .25s;
    outline: none;
    -webkit-appearance: none;
  }
  .form-group select option { background: var(--black); }
  .form-group input:focus,
  .form-group select:focus,
  .form-group textarea:focus { border-color: var(--gold); }
  .form-group textarea { resize: vertical; min-height: 80px; }

  /* ─── CONTACT / MAP ─── */
  #contact {
    background: var(--black);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
    padding: 0;
    min-height: 480px;
  }

  .map-wrap { background: var(--charcoal); position: relative; overflow: hidden; min-height: 480px; }
  .map-wrap iframe { width: 100%; height: 100%; border: none; filter: invert(0.9) hue-rotate(180deg) saturate(0.2); }
  .map-overlay-badge {
    position: absolute;
    top: 24px; left: 24px;
    background: rgba(11,11,11,.9);
    border: 1px solid var(--border);
    border-radius: 3px;
    padding: 16px 20px;
    backdrop-filter: blur(8px);
  }
  .map-overlay-badge strong { display: block; font-size: 14px; font-weight: 600; margin-bottom: 4px; }
  .map-overlay-badge span { font-size: 12px; color: var(--muted); }

  .contact-info {
    padding: 80px 5vw;
    background: var(--black);
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .contact-info .section-title { font-size: clamp(32px, 3vw, 50px); margin: 18px 0 36px; }
  .contact-details { display: flex; flex-direction: column; gap: 24px; }
  .contact-detail {
    display: flex; gap: 16px; align-items: flex-start;
  }
  .contact-detail-icon {
    width: 42px; height: 42px;
    border: 1px solid var(--border);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    color: var(--gold); flex-shrink: 0;
  }
  .contact-detail strong { display: block; font-size: 13px; font-weight: 600; margin-bottom: 3px; }
  .contact-detail p { font-size: 13px; color: var(--muted); line-height: 1.5; }

  /* ─── FOOTER ─── */
  footer {
    background: var(--charcoal);
    border-top: 1px solid var(--border);
    padding: 72px 6vw 36px;
  }

  .footer-top {
    display: grid;
    grid-template-columns: 1.6fr 1fr 1fr 1fr;
    gap: 48px;
    margin-bottom: 60px;
  }

  .footer-brand .nav-logo { font-size: 24px; display: block; margin-bottom: 16px; }
  .footer-brand p { font-size: 13px; color: var(--muted); line-height: 1.8; max-width: 280px; }
  .footer-socials { display: flex; gap: 10px; margin-top: 24px; }
  .footer-social {
    width: 36px; height: 36px;
    border: 1px solid var(--border);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    color: var(--muted);
    text-decoration: none;
    font-size: 12px;
    font-weight: 700;
    transition: border-color .2s, color .2s;
  }
  .footer-social:hover { border-color: var(--gold); color: var(--gold); }

  .footer-col h4 {
    font-family: 'Inter', sans-serif;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: .2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 20px;
  }
  .footer-col ul { list-style: none; }
  .footer-col li { margin-bottom: 10px; }
  .footer-col a {
    font-size: 13px;
    color: var(--muted);
    text-decoration: none;
    transition: color .2s;
  }
  .footer-col a:hover { color: var(--white); }

  .footer-bottom {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 28px;
    border-top: 1px solid var(--border);
  }
  .footer-bottom p { font-size: 12px; color: rgba(255,255,255,.3); }
  .footer-bottom a { color: var(--gold); text-decoration: none; }

  /* ─── FLOATING BUTTONS ─── */
  .fab-group {
    position: fixed;
    bottom: 32px;
    right: 28px;
    display: flex;
    flex-direction: column;
    gap: 12px;
    z-index: 999;
  }

  .fab {
    width: 50px; height: 50px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    cursor: pointer;
    text-decoration: none;
    transition: transform .25s, box-shadow .25s;
    box-shadow: 0 4px 20px rgba(0,0,0,.5);
  }
  .fab:hover { transform: scale(1.1); }

  .fab-whatsapp { background: #25D366; color: white; }
  .fab-top {
    background: var(--charcoal);
    border: 1px solid var(--border);
    color: var(--gold);
    opacity: 0;
    pointer-events: none;
    transition: opacity .3s, transform .25s;
  }
  .fab-top.visible { opacity: 1; pointer-events: auto; }

  /* ─── IMAGE PLACEHOLDERS ─── */
  .img-placeholder {
    background: linear-gradient(135deg, var(--charcoal) 0%, var(--charcoal-light) 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    color: rgba(199,166,90,.25);
    font-family: 'Cormorant Garamond', serif;
    font-size: 13px;
    letter-spacing: .12em;
    text-transform: uppercase;
  }
  .img-placeholder svg { opacity: .18; }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 1100px) {
    .services-grid { grid-template-columns: repeat(2, 1fr); }
    .team-grid { grid-template-columns: repeat(2, 1fr); }
    .gallery-grid { grid-template-columns: repeat(3, 1fr); grid-template-rows: auto; }
    .gallery-item:nth-child(1) { grid-column: span 1; grid-row: span 1; }
    .gallery-item:nth-child(4) { grid-column: span 1; }
    .footer-top { grid-template-columns: 1fr 1fr; }
  }

  @media (max-width: 860px) {
    #hero { grid-template-columns: 1fr; }
    .hero-image { display: none; }
    .hero-left { padding: 100px 6vw 60px; }
    #about { grid-template-columns: 1fr; }
    .about-image-wrap { display: none; }
    .deals-grid { grid-template-columns: 1fr; }
    .why-grid { grid-template-columns: 1fr; }
    .process-steps { grid-template-columns: 1fr 1fr; }
    .process-steps::before { display: none; }
    .testimonials-grid { grid-template-columns: 1fr; }
    .membership-grid { grid-template-columns: 1fr; }
    .faq-grid { grid-template-columns: 1fr; }
    #booking { grid-template-columns: 1fr; }
    #contact { grid-template-columns: 1fr; }
    .nav-links { display: none; }
    .footer-top { grid-template-columns: 1fr; gap: 32px; }
    .form-row { grid-template-columns: 1fr; }
    #trust { flex-wrap: wrap; gap: 16px; }
    .trust-divider { display: none; }
  }

  /* ─── NEWSLETTER ─── */
  #newsletter {
    background: linear-gradient(135deg, var(--charcoal) 0%, var(--charcoal-light) 100%);
    padding: 80px 6vw;
    text-align: center;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }
  #newsletter h2 { font-size: clamp(32px, 4vw, 52px); margin: 16px 0 14px; }
  #newsletter p { color: var(--muted); font-size: 14px; margin-bottom: 36px; }
  .newsletter-form { display: flex; justify-content: center; gap: 0; max-width: 440px; margin: 0 auto; }
  .newsletter-form input {
    flex: 1;
    background: var(--black);
    border: 1px solid var(--border);
    border-right: none;
    border-radius: 2px 0 0 2px;
    padding: 14px 18px;
    color: var(--white);
    font-family: 'Inter', sans-serif;
    font-size: 14px;
    outline: none;
    transition: border-color .25s;
  }
  .newsletter-form input:focus { border-color: var(--gold); }
  .newsletter-form button {
    background: var(--gold);
    color: var(--black);
    border: none;
    border-radius: 0 2px 2px 0;
    padding: 14px 22px;
    font-family: 'Inter', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: .14em;
    text-transform: uppercase;
    cursor: pointer;
    transition: background .2s;
  }
  .newsletter-form button:hover { background: var(--gold-dark); }

  /* ─── GIFT CARDS ─── */
  #giftcards { background: var(--black); padding: 110px 6vw; }
  .giftcard-wrap {
    margin-top: 56px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    align-items: center;
  }
  .giftcard-visual {
    aspect-ratio: 16/9;
    background: linear-gradient(135deg, var(--charcoal) 0%, #2a2a2a 100%);
    border: 1px solid var(--gold);
    border-radius: 12px;
    padding: 36px 40px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    position: relative;
    overflow: hidden;
  }
  .giftcard-visual::before {
    content: '';
    position: absolute;
    top: -40%; right: -20%;
    width: 280px; height: 280px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(199,166,90,.12) 0%, transparent 70%);
  }
  .giftcard-logo { font-family: 'Cormorant Garamond', serif; font-size: 20px; font-weight: 600; letter-spacing: .12em; color: var(--gold); }
  .giftcard-amount { font-family: 'Cormorant Garamond', serif; font-size: 52px; font-weight: 600; color: var(--white); line-height: 1; }
  .giftcard-bottom { display: flex; justify-content: space-between; align-items: flex-end; }
  .giftcard-tag { font-size: 10px; letter-spacing: .14em; text-transform: uppercase; color: var(--muted); }
  .giftcard-chip { width: 40px; height: 30px; background: var(--gold); border-radius: 4px; opacity: .7; }

  .giftcard-text h3 { font-size: clamp(28px, 3vw, 42px); font-weight: 300; margin-bottom: 16px; line-height: 1.2; }
  .giftcard-text p { font-size: 14px; color: var(--muted); line-height: 1.8; margin-bottom: 32px; }
  .giftcard-amounts { display: flex; gap: 10px; flex-wrap: wrap; margin-bottom: 32px; }
  .amount-pill {
    padding: 8px 20px;
    border: 1px solid var(--border);
    border-radius: 2px;
    font-size: 13px;
    color: rgba(255,255,255,.7);
    cursor: pointer;
    transition: border-color .2s, color .2s, background .2s;
  }
  .amount-pill:hover, .amount-pill.active { border-color: var(--gold); color: var(--gold); background: var(--gold-pale); }
</style>
</head>
<body>

<!-- ─── NAV ─── -->
<nav id="nav" role="navigation" aria-label="Main navigation">
  <a href="#" class="nav-logo">NOIR <span>&amp;</span> CO.</a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#team">Experts</a></li>
    <li><a href="#gallery">Gallery</a></li>
    <li><a href="#membership">Memberships</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#booking" class="nav-cta">Book Now</a></li>
  </ul>
</nav>

<!-- ─── HERO ─── -->
<section id="hero" aria-label="Hero">
  <div class="hero-left">
    <div class="hero-num" aria-hidden="true">01</div>
    <div class="eyebrow reveal">Est. 2015 — Lahore, Pakistan</div>
    <h1 class="hero-title reveal reveal-delay-1">
      The Art of<br><em>Refined</em><br>Grooming
    </h1>
    <p class="hero-sub reveal reveal-delay-2">
      Where tradition meets modernity. Precision cuts, royal shaves, and bespoke grooming rituals crafted for the discerning gentleman.
    </p>
    <div class="hero-actions reveal reveal-delay-3">
      <a href="#booking" class="btn-primary">
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M8 2v4M16 2v4M3 10h18M5 4h14a2 2 0 012 2v14a2 2 0 01-2 2H5a2 2 0 01-2-2V6a2 2 0 012-2z"/></svg>
        Book Appointment
      </a>
      <a href="#services" class="btn-ghost">
        <svg width="12" height="12" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
        Our Services
      </a>
    </div>
    <div class="hero-stats reveal reveal-delay-4">
      <div>
        <div class="stat-num">12+</div>
        <div class="stat-label">Expert Stylists</div>
      </div>
      <div>
        <div class="stat-num">8K+</div>
        <div class="stat-label">Happy Clients</div>
      </div>
      <div>
        <div class="stat-num">4.9★</div>
        <div class="stat-label">Google Rating</div>
      </div>
    </div>
  </div>

  <div class="hero-image" aria-hidden="true">
    <img src="https://images.unsplash.com/photo-1503951914875-452162b0f3f1?w=1200&q=80&fit=crop" alt="Luxury barber at work" loading="eager" />
    <div class="hero-image-overlay"></div>
    <div class="hero-badge">
      <div>Award<br/>Winner<br/><strong style="color:var(--gold);font-family:'Cormorant Garamond',serif;font-size:16px;display:block;font-weight:700">2024</strong></div>
    </div>
  </div>
</section>

<!-- ─── TRUST BAR ─── -->
<div id="trust" role="complementary" aria-label="Trust indicators">
  <div class="trust-item">
    <svg class="trust-icon" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
    <div class="trust-text"><strong>Certified Experts</strong><span>Licensed & Trained</span></div>
  </div>
  <div class="trust-divider"></div>
  <div class="trust-item">
    <svg class="trust-icon" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M5 3l14 9-14 9V3z"/></svg>
    <div class="trust-text"><strong>Premium Products</strong><span>Luxury Brands Only</span></div>
  </div>
  <div class="trust-divider"></div>
  <div class="trust-item">
    <svg class="trust-icon" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
    <div class="trust-text"><strong>100% Hygienic</strong><span>Sterilised Equipment</span></div>
  </div>
  <div class="trust-divider"></div>
  <div class="trust-item">
    <svg class="trust-icon" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
    <div class="trust-text"><strong>4.9 Star Rating</strong><span>1,200+ Reviews</span></div>
  </div>
  <div class="trust-divider"></div>
  <div class="trust-item">
    <svg class="trust-icon" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
    <div class="trust-text"><strong>Open 7 Days</strong><span>10 AM – 10 PM</span></div>
  </div>
  <div class="trust-divider"></div>
  <div class="trust-item">
    <svg class="trust-icon" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M3 10h18M7 15h1m4 0h1m-7 4h12a3 3 0 003-3V8a3 3 0 00-3-3H6a3 3 0 00-3 3v8a3 3 0 003 3z"/></svg>
    <div class="trust-text"><strong>Easy Booking</strong><span>Online & WhatsApp</span></div>
  </div>
</div>

<!-- ─── ABOUT ─── -->
<section id="about" aria-labelledby="about-title">
  <div class="about-image-wrap reveal">
    <img src="https://images.unsplash.com/photo-1585747860715-2ba37e788b70?w=900&q=80&fit=crop" alt="Classic barbershop interior" style="width:100%;aspect-ratio:4/5;object-fit:cover;border-radius:3px;display:block;" loading="lazy" />
    <div class="about-image-tag"><strong>10</strong>Years of<br/>Excellence</div>
  </div>
  <div class="about-text">
    <div class="eyebrow reveal">Our Story</div>
    <h2 id="about-title" class="section-title reveal reveal-delay-1">
      More Than a Salon —<br>A <em>Gentleman's Sanctuary</em>
    </h2>
    <p class="about-copy reveal reveal-delay-2">
      Founded in 2015, Noir & Co. was born from a singular vision: to redefine men's grooming in Pakistan. We blended European barbering heritage with the warmth of Eastern hospitality — creating a space where every visit is a ritual, not a routine.
    </p>
    <a href="#services" class="btn-primary reveal reveal-delay-3">
      Discover Our Services
      <svg width="12" height="12" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
    </a>
    <div class="about-features reveal reveal-delay-4">
      <div class="about-feat">
        <div class="about-feat-icon">
          <svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.87M16 3.13a4 4 0 010 7.75"/></svg>
        </div>
        <h4>Master Barbers</h4>
        <p>Each artist trained in London & Dubai's finest grooming houses.</p>
      </div>
      <div class="about-feat">
        <div class="about-feat-icon">
          <svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        </div>
        <h4>Private Suites</h4>
        <p>Dedicated VIP suites for those who value privacy and exclusivity.</p>
      </div>
      <div class="about-feat">
        <div class="about-feat-icon">
          <svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M20.84 4.61a5.5 5.5 0 00-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 00-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 000-7.78z"/></svg>
        </div>
        <h4>Client-First</h4>
        <p>Every service personalised to your unique style and face structure.</p>
      </div>
      <div class="about-feat">
        <div class="about-feat-icon">
          <svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
        </div>
        <h4>Always On Time</h4>
        <p>Punctual appointments. Respect for your schedule, always.</p>
      </div>
    </div>
  </div>
</section>

<!-- ─── SERVICES ─── -->
<section id="services" aria-labelledby="services-title">
  <div class="section-header">
    <div class="eyebrow reveal">What We Offer</div>
    <h2 id="services-title" class="section-title reveal reveal-delay-1">Crafted <em>Services</em><br>for Every Occasion</h2>
    <p class="section-lead reveal reveal-delay-2">From a swift express cut to our full signature experience — every service is delivered with the precision and care it deserves.</p>
  </div>
  <div class="services-grid">
    <div class="service-card reveal">
      <div class="service-number">01</div>
      <div class="service-icon"><svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M12 20h9"/><path d="M16.5 3.5a2.121 2.121 0 013 3L7 19l-4 1 1-4L16.5 3.5z"/></svg></div>
      <h3>Signature<br/>Haircut</h3>
      <p class="service-desc">Bespoke consultation, precision scissor or clipper cut, hot towel finish, and blow-dry styling.</p>
      <div class="service-price">PKR 1,800 <span>/ session</span></div>
      <div class="service-arrow"><svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg></div>
    </div>
    <div class="service-card reveal reveal-delay-1">
      <div class="service-number">02</div>
      <div class="service-icon"><svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M3 9l9-7 9 7v11a2 2 0 01-2 2H5a2 2 0 01-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg></div>
      <h3>Royal<br/>Hot Shave</h3>
      <p class="service-desc">Traditional straight-razor shave with warm lather, pre-shave oil, and post-shave balm treatment.</p>
      <div class="service-price">PKR 2,200 <span>/ session</span></div>
      <div class="service-arrow"><svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg></div>
    </div>
    <div class="service-card reveal reveal-delay-2">
      <div class="service-number">03</div>
      <div class="service-icon"><svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2z"/><path d="M8 12s1.5 2 4 2 4-2 4-2"/><line x1="9" y1="9" x2="9.01" y2="9"/><line x1="15" y1="9" x2="15.01" y2="9"/></svg></div>
      <h3>Beard<br/>Sculpting</h3>
      <p class="service-desc">Custom beard design, edging, shaping, and conditioning treatment with premium beard oils.</p>
      <div class="service-price">PKR 1,500 <span>/ session</span></div>
      <div class="service-arrow"><svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg></div>
    </div>
    <div class="service-card reveal reveal-delay-3">
      <div class="service-number">04</div>
      <div class="service-icon"><svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M20.84 4.61a5.5 5.5 0 00-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 00-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 000-7.78z"/></svg></div>
      <h3>Facial<br/>Treatment</h3>
      <p class="service-desc">Deep cleanse, exfoliation, steam, mask, and moisturising facial designed for men's skin.</p>
      <div class="service-price">PKR 2,800 <span>/ session</span></div>
      <div class="service-arrow"><svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg></div>
    </div>
    <div class="service-card reveal">
      <div class="service-number">05</div>
      <div class="service-icon"><svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><circle cx="12" cy="12" r="3"/><path d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"/></svg></div>
      <h3>Hair Colour<br/>& Highlights</h3>
      <p class="service-desc">Full colour, highlights, ombre, and grey coverage using Schwarzkopf and L'Oréal Professional.</p>
      <div class="service-price">PKR 3,500 <span>/ session</span></div>
      <div class="service-arrow"><svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg></div>
    </div>
    <div class="service-card reveal reveal-delay-1">
      <div class="service-number">06</div>
      <div class="service-icon"><svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg></div>
      <h3>Keratin<br/>Treatment</h3>
      <p class="service-desc">Professional smoothing and strengthening treatment for frizz-free, silky hair for up to 3 months.</p>
      <div class="service-price">PKR 5,500 <span>/ session</span></div>
      <div class="service-arrow"><svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg></div>
    </div>
    <div class="service-card reveal reveal-delay-2">
      <div class="service-number">07</div>
      <div class="service-icon"><svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14 2 14 8 20 8"/></svg></div>
      <h3>Scalp<br/>Massage</h3>
      <p class="service-desc">Therapeutic 30-minute scalp massage with essential oils to promote circulation and relaxation.</p>
      <div class="service-price">PKR 1,200 <span>/ session</span></div>
      <div class="service-arrow"><svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg></div>
    </div>
    <div class="service-card reveal reveal-delay-3" style="border-left:2px solid var(--gold);">
      <div class="service-number" style="color:var(--gold);">SIGNATURE</div>
      <div class="service-icon"><svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg></div>
      <h3>Full Grooming<br/><em>Experience</em></h3>
      <p class="service-desc">The complete Noir & Co. ritual: haircut, shave, facial, massage, and styling. 2.5 hours of pure indulgence.</p>
      <div class="service-price">PKR 7,500 <span>/ session</span></div>
      <div class="service-arrow"><svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg></div>
    </div>
  </div>
</section>

<!-- ─── WEEKEND DEALS ─── -->
<section id="deals" aria-labelledby="deals-title" style="position:relative;background-image:url('https://images.unsplash.com/photo-1503951914875-452162b0f3f1?w=1800&q=60&fit=crop');background-size:cover;background-position:center;background-attachment:fixed;">
  <div style="position:absolute;inset:0;background:rgba(11,11,11,0.88);z-index:0;pointer-events:none;"></div>
  <div style="position:relative;z-index:1;" class="section-header">
    <div class="eyebrow reveal">Limited Time</div>
    <h2 id="deals-title" class="section-title reveal reveal-delay-1">Weekend <em>Offers</em><br>& Special Deals</h2>
  </div>
  <div class="deals-grid">
    <div class="deal-card featured reveal">
      <div class="deal-badge">Weekend Special</div>
      <div class="deal-tag"><div class="eyebrow" style="font-size:9px;">Fri – Sun Only</div></div>
      <h3>The Royal<br/>Duo Package</h3>
      <p>Haircut + Hot Shave + Beard Sculpting. The ultimate weekend refresh before you step out.</p>
      <div class="deal-pricing">
        <span class="deal-new">PKR 3,500</span>
        <span class="deal-old">PKR 5,500</span>
      </div>
      <a href="#booking" class="btn-primary">Claim Offer</a>
    </div>
    <div class="deal-card reveal reveal-delay-1">
      <div class="deal-tag"><div class="eyebrow" style="font-size:9px;">First Visit</div></div>
      <h3>New Client<br/>Welcome</h3>
      <p>Any single service at 25% off for first-time visitors. Walk in or book online.</p>
      <div class="deal-pricing">
        <span class="deal-new">25% OFF</span>
      </div>
      <a href="#booking" class="btn-ghost" style="display:inline-flex;gap:6px;align-items:center;">Book Now →</a>
    </div>
    <div class="deal-card reveal reveal-delay-2">
      <div class="deal-tag"><div class="eyebrow" style="font-size:9px;">Loyalty Reward</div></div>
      <h3>5th Visit<br/>Free</h3>
      <p>Every 5th visit unlocks a complimentary service of your choice. Automatically tracked.</p>
      <div class="deal-pricing">
        <span class="deal-new">FREE Visit</span>
      </div>
      <a href="#membership" class="btn-ghost" style="display:inline-flex;gap:6px;align-items:center;">Learn More →</a>
    </div>
  </div>
</section>

<!-- ─── GALLERY ─── -->
<section id="gallery" aria-labelledby="gallery-title">
  <div class="section-header">
    <div class="eyebrow reveal">The Craft</div>
    <h2 id="gallery-title" class="section-title reveal reveal-delay-1">Work That <em>Speaks</em><br>for Itself</h2>
  </div>
  <div class="gallery-grid">
    <!-- Large feature item -->
    <div class="gallery-item reveal">
      <img src="https://images.unsplash.com/photo-1599351431202-1e0f0137899a?w=900&q=80&fit=crop" alt="Precision haircut" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
      <div class="gallery-overlay"><svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M15 3h6v6M9 21H3v-6M21 3l-7 7M3 21l7-7"/></svg></div>
    </div>
    <div class="gallery-item reveal reveal-delay-1">
      <img src="https://images.unsplash.com/photo-1621605815971-fbc98d665033?w=600&q=80&fit=crop" alt="Classic shave" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
      <div class="gallery-overlay"><svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M15 3h6v6M9 21H3v-6M21 3l-7 7M3 21l7-7"/></svg></div>
    </div>
    <div class="gallery-item reveal reveal-delay-2">
      <img src="https://images.unsplash.com/photo-1634449571010-02389ed0f9b0?w=600&q=80&fit=crop" alt="Beard sculpting" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
      <div class="gallery-overlay"><svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M15 3h6v6M9 21H3v-6M21 3l-7 7M3 21l7-7"/></svg></div>
    </div>
    <div class="gallery-item reveal">
      <img src="https://images.unsplash.com/photo-1581591524425-c7e0978865fc?w=900&q=80&fit=crop" alt="Grooming products" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
      <div class="gallery-overlay"><svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M15 3h6v6M9 21H3v-6M21 3l-7 7M3 21l7-7"/></svg></div>
    </div>
    <div class="gallery-item reveal reveal-delay-1">
      <img src="https://images.unsplash.com/photo-1622296089863-eb7fc530daa8?w=600&q=80&fit=crop" alt="Modern fade" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
      <div class="gallery-overlay"><svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M15 3h6v6M9 21H3v-6M21 3l-7 7M3 21l7-7"/></svg></div>
    </div>
    <div class="gallery-item reveal reveal-delay-2">
      <img src="https://images.unsplash.com/photo-1503951914875-452162b0f3f1?w=600&q=80&fit=crop" alt="Barber at work" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
      <div class="gallery-overlay"><svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M15 3h6v6M9 21H3v-6M21 3l-7 7M3 21l7-7"/></svg></div>
    </div>
  </div>
</section>

<!-- ─── TEAM ─── -->
<section id="team" aria-labelledby="team-title">
  <div class="section-header">
    <div class="eyebrow reveal">The Artisans</div>
    <h2 id="team-title" class="section-title reveal reveal-delay-1">Meet Your <em>Grooming</em><br>Experts</h2>
    <p class="section-lead reveal reveal-delay-2">Each member of our team has trained extensively — locally and abroad — to master their craft and bring it to you.</p>
  </div>
  <div class="team-grid">
    <div class="team-card reveal">
      <div class="team-img">
        <img src="https://images.unsplash.com/photo-1570295999919-56ceb5ecca61?w=600&q=80&fit=crop&crop=faces" alt="Hassan Raza - Expert Barber" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
        <div class="team-socials">
          <a href="#">IG</a><a href="#">TW</a>
        </div>
      </div>
      <div class="team-info">
        <h3>Hassan Raza</h3>
        <p>Senior Master Barber</p>
        <div class="team-spec">12 years exp. Specialises in fades & European cuts. Trained in Istanbul.</div>
      </div>
    </div>
    <div class="team-card reveal reveal-delay-1">
      <div class="team-img">
        <img src="https://images.unsplash.com/photo-1564564321837-a57b7070ac4f?w=600&q=80&fit=crop&crop=faces" alt="Ali Zafar - Expert Barber" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
        <div class="team-socials"><a href="#">IG</a><a href="#">TW</a></div>
      </div>
      <div class="team-info">
        <h3>Ali Zafar</h3>
        <p>Head Skin Specialist</p>
        <div class="team-spec">Certified dermal therapist. Expert in men's skin treatments & facials. Dubai trained.</div>
      </div>
    </div>
    <div class="team-card reveal reveal-delay-2">
      <div class="team-img">
        <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=600&q=80&fit=crop&crop=faces" alt="Usman Tariq - Expert Barber" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
        <div class="team-socials"><a href="#">IG</a><a href="#">TW</a></div>
      </div>
      <div class="team-info">
        <h3>Usman Tariq</h3>
        <p>Colour & Style Artist</p>
        <div class="team-spec">L'Oréal certified colourist. Specialist in balayage, ombre, and multi-tone colour.</div>
      </div>
    </div>
    <div class="team-card reveal reveal-delay-3">
      <div class="team-img">
        <img src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?w=600&q=80&fit=crop&crop=faces" alt="Bilal Ahmed - Expert Barber" style="width:100%;height:100%;object-fit:cover;" loading="lazy" />
        <div class="team-socials"><a href="#">IG</a><a href="#">TW</a></div>
      </div>
      <div class="team-info">
        <h3>Bilal Ahmed</h3>
        <p>Beard Design Expert</p>
        <div class="team-spec">Master of beard architecture. 8 years crafting bespoke beard shapes for every face.</div>
      </div>
    </div>
  </div>
</section>

<!-- ─── WHY CHOOSE US ─── -->
<section id="why" aria-labelledby="why-title" style="position:relative;background-image:url('https://images.unsplash.com/photo-1585747860715-2ba37e788b70?w=1800&q=50&fit=crop');background-size:cover;background-attachment:fixed;background-position:center;">
  <div style="position:absolute;inset:0;background:rgba(11,11,11,0.93);z-index:0;"></div>
  <div style="position:relative;z-index:1;">
  <div class="section-header">
    <div class="eyebrow reveal">The Difference</div>
    <h2 id="why-title" class="section-title reveal reveal-delay-1">Why <em>Noir & Co.</em><br>Stands Apart</h2>
  </div>
  <div class="why-grid">
    <div class="why-item reveal">
      <div class="why-icon"><svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg></div>
      <h3>Award-Winning Experience</h3>
      <p>Recognised as Pakistan's best luxury men's salon for three consecutive years by the Grooming Guild of South Asia.</p>
    </div>
    <div class="why-item reveal reveal-delay-1">
      <div class="why-icon"><svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg></div>
      <h3>Hygiene Without Compromise</h3>
      <p>Hospital-grade sterilisation on every tool. Single-use blades, laundered towels, and sanitised workstations after every client.</p>
    </div>
    <div class="why-item reveal reveal-delay-2">
      <div class="why-icon"><svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M20.84 4.61a5.5 5.5 0 00-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 00-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 000-7.78z"/></svg></div>
      <h3>Personalised to You</h3>
      <p>A detailed consultation before every appointment. Your face shape, lifestyle, and preferences guide every decision we make.</p>
    </div>
    <div class="why-item reveal">
      <div class="why-icon"><svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M3 6l9-4 9 4v6c0 5.25-3.75 9-9 11C6.75 21 3 17.25 3 12V6z"/></svg></div>
      <h3>Premium Products Only</h3>
      <p>We stock and use Kerastase, Bumble and bumble, American Crew, and Schwarzkopf — nothing less than the best.</p>
    </div>
    <div class="why-item reveal reveal-delay-1">
      <div class="why-icon"><svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.87M16 3.13a4 4 0 010 7.75"/></svg></div>
      <h3>Client Community</h3>
      <p>Not just a salon — a brotherhood. Our loyalty programme, events, and community connect like-minded gentlemen.</p>
    </div>
    <div class="why-item reveal reveal-delay-2">
      <div class="why-icon"><svg width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg></div>
      <h3>Punctual, Always</h3>
      <p>Your time is as valuable as ours. We run on schedule — no waiting rooms, no delays. Book and arrive confidently.</p>
    </div>
  </div>
</div>
</section>

<!-- ─── PROCESS ─── -->
<section id="process" aria-labelledby="process-title">
  <div class="section-header" style="text-align:center; max-width:600px; margin:0 auto 64px;">
    <div class="eyebrow reveal" style="justify-content:center;"><span></span>The Journey<span></span></div>
    <h2 id="process-title" class="section-title reveal reveal-delay-1" style="max-width:100%;text-align:center;margin:18px auto 0;">Your <em>Experience</em><br>Step by Step</h2>
  </div>
  <div class="process-steps">
    <div class="process-step reveal">
      <div class="process-dot"><svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M8 2v4M16 2v4M3 10h18M5 4h14a2 2 0 012 2v14a2 2 0 01-2 2H5a2 2 0 01-2-2V6a2 2 0 012-2z"/></svg></div>
      <h3>Book Online</h3>
      <p>Choose your service, preferred barber, and time slot in under 60 seconds.</p>
    </div>
    <div class="process-step reveal reveal-delay-1">
      <div class="process-dot"><svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg></div>
      <h3>Consultation</h3>
      <p>Your barber reviews your style, face structure, and goals before touching a tool.</p>
    </div>
    <div class="process-step reveal reveal-delay-2">
      <div class="process-dot"><svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 20h9"/><path d="M16.5 3.5a2.121 2.121 0 013 3L7 19l-4 1 1-4L16.5 3.5z"/></svg></div>
      <h3>The Service</h3>
      <p>Precision work. No rush, no shortcuts. Every detail attended to with mastery.</p>
    </div>
    <div class="process-step reveal reveal-delay-3">
      <div class="process-dot"><svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M20.84 4.61a5.5 5.5 0 00-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 00-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 000-7.78z"/></svg></div>
      <h3>Walk Out Proud</h3>
      <p>Leave with confidence. We finish with styling advice and product recommendations.</p>
    </div>
  </div>
</section>

<!-- ─── TESTIMONIALS ─── -->
<section id="testimonials" aria-labelledby="testi-title" style="position:relative;background-image:url('https://images.unsplash.com/photo-1621605815971-fbc98d665033?w=1800&q=40&fit=crop');background-size:cover;background-attachment:fixed;background-position:center top;">
  <div style="position:absolute;inset:0;background:rgba(11,11,11,0.95);z-index:0;"></div>
  <div style="position:relative;z-index:1;">
  <div class="section-header">
    <div class="eyebrow reveal">Client Stories</div>
    <h2 id="testi-title" class="section-title reveal reveal-delay-1">Words from Our <em>Gentlemen</em></h2>
  </div>
  <div class="testimonials-grid">
    <div class="testi-card reveal">
      <div class="testi-stars">★★★★★</div>
      <p class="testi-quote">"Walking into Noir & Co. feels like stepping into a different era — where the barber actually cares about the result. Hassan gave me the best haircut of my life."</p>
      <div class="testi-author">
        <div class="testi-avatar">A</div>
        <div><div class="testi-name">Ahsan Malik</div><div class="testi-role">CEO, Lahore</div></div>
      </div>
    </div>
    <div class="testi-card reveal reveal-delay-1">
      <div class="testi-stars">★★★★★</div>
      <p class="testi-quote">"I've been to salons in Dubai and London — Noir & Co. honestly rivals them. The hot shave ritual is something else entirely. Worth every rupee."</p>
      <div class="testi-author">
        <div class="testi-avatar">Z</div>
        <div><div class="testi-name">Zubair Khan</div><div class="testi-role">Entrepreneur</div></div>
      </div>
    </div>
    <div class="testi-card reveal reveal-delay-2">
      <div class="testi-stars">★★★★★</div>
      <p class="testi-quote">"My beard has never looked this sharp. Bilal spent 45 minutes sculpting it perfectly. The whole experience was relaxing, professional, and absolutely worth it."</p>
      <div class="testi-author">
        <div class="testi-avatar">O</div>
        <div><div class="testi-name">Omar Siddiqui</div><div class="testi-role">Architect</div></div>
      </div>
    </div>
  </div>
</div>
</section>

<!-- ─── MEMBERSHIP ─── -->
<section id="membership" aria-labelledby="membership-title">
  <div class="section-header">
    <div class="eyebrow reveal">Exclusive Access</div>
    <h2 id="membership-title" class="section-title reveal reveal-delay-1">Membership <em>Plans</em><br>for the Regular Gentleman</h2>
    <p class="section-lead reveal reveal-delay-2">Commit to looking your best, every month. Members get priority booking, exclusive discounts, and complimentary treatments.</p>
  </div>
  <div class="membership-grid">
    <div class="plan-card reveal">
      <div class="plan-name">Silver</div>
      <div class="plan-tagline">The Essentials</div>
      <div class="plan-price"><span class="plan-currency">PKR</span><span class="plan-amount">4,500</span><span class="plan-period">/ month</span></div>
      <ul class="plan-features">
        <li>2 Haircuts per month</li>
        <li>1 Beard Sculpt per month</li>
        <li>10% off all products</li>
        <li>Priority booking</li>
        <li class="disabled">Complimentary facial</li>
        <li class="disabled">VIP lounge access</li>
        <li class="disabled">Guest passes</li>
      </ul>
      <a href="#booking" class="btn-ghost" style="display:block;text-align:center;padding:14px;">Get Started</a>
    </div>
    <div class="plan-card featured reveal reveal-delay-1">
      <div class="plan-name">Gold</div>
      <div class="plan-tagline">The Complete Gentleman</div>
      <div class="plan-price"><span class="plan-currency">PKR</span><span class="plan-amount">8,000</span><span class="plan-period">/ month</span></div>
      <ul class="plan-features">
        <li>4 Haircuts per month</li>
        <li>4 Beard Sculpts per month</li>
        <li>20% off all products</li>
        <li>Priority booking + same-day</li>
        <li>1 Facial per month</li>
        <li>VIP lounge access</li>
        <li class="disabled">Guest passes</li>
      </ul>
      <a href="#booking" class="btn-primary" style="display:block;text-align:center;">Join Gold</a>
    </div>
    <div class="plan-card reveal reveal-delay-2">
      <div class="plan-name">Platinum</div>
      <div class="plan-tagline">Unlimited Indulgence</div>
      <div class="plan-price"><span class="plan-currency">PKR</span><span class="plan-amount">14,000</span><span class="plan-period">/ month</span></div>
      <ul class="plan-features">
        <li>Unlimited all services</li>
        <li>30% off all products</li>
        <li>24/7 priority booking</li>
        <li>Dedicated personal barber</li>
        <li>Monthly signature experience</li>
        <li>VIP lounge + beverages</li>
        <li>2 Guest passes per month</li>
      </ul>
      <a href="#booking" class="btn-ghost" style="display:block;text-align:center;padding:14px;">Go Platinum</a>
    </div>
  </div>
</section>

<!-- ─── GIFT CARDS ─── -->
<section id="giftcards" aria-labelledby="gc-title">
  <div class="section-header">
    <div class="eyebrow reveal">The Perfect Gift</div>
    <h2 id="gc-title" class="section-title reveal reveal-delay-1">Give the Gift of<br/><em>Grooming</em></h2>
  </div>
  <div class="giftcard-wrap">
    <div class="giftcard-visual reveal">
      <div class="giftcard-logo">NOIR &amp; CO.</div>
      <div style="text-align:center;">
        <div style="font-size:11px;letter-spacing:.12em;color:var(--muted);text-transform:uppercase;margin-bottom:8px;">Gift Card</div>
        <div class="giftcard-amount" id="gc-display">PKR 5,000</div>
      </div>
      <div class="giftcard-bottom">
        <div>
          <div class="giftcard-tag">Valid 12 months</div>
          <div class="giftcard-tag" style="margin-top:4px;">noir-and-co.pk</div>
        </div>
        <div class="giftcard-chip"></div>
      </div>
    </div>
    <div class="giftcard-text reveal reveal-delay-1">
      <h3>The Ideal Present<br/>for Every <em>Gentleman</em></h3>
      <p>Whether it's a birthday, Eid, or just because — a Noir & Co. gift card gives them the freedom to choose their perfect experience.</p>
      <div class="giftcard-amounts">
        <div class="amount-pill" onclick="updateGC(this,'PKR 2,000')">PKR 2,000</div>
        <div class="amount-pill active" onclick="updateGC(this,'PKR 5,000')">PKR 5,000</div>
        <div class="amount-pill" onclick="updateGC(this,'PKR 10,000')">PKR 10,000</div>
        <div class="amount-pill" onclick="updateGC(this,'Custom')">Custom</div>
      </div>
      <a href="#" class="btn-primary">
        Purchase Gift Card
        <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M20 12v10H4V12M22 7H2v5h20V7zM12 22V7M12 7H7.5a2.5 2.5 0 010-5C11 2 12 7 12 7zM12 7h4.5a2.5 2.5 0 000-5C13 2 12 7 12 7z"/></svg>
      </a>
    </div>
  </div>
</section>

<!-- ─── FAQ ─── -->
<section id="faq" aria-labelledby="faq-title">
  <div class="section-header">
    <div class="eyebrow reveal">Questions</div>
    <h2 id="faq-title" class="section-title reveal reveal-delay-1">Frequently <em>Asked</em></h2>
  </div>
  <div class="faq-grid">
    <div class="faq-item reveal" onclick="toggleFaq(this)">
      <div class="faq-q">Do I need to book in advance?<div class="faq-toggle">+</div></div>
      <div class="faq-a">Walk-ins are welcome for most services, but we strongly recommend booking to secure your preferred time and barber. Peak hours (evenings and weekends) fill up fast.</div>
    </div>
    <div class="faq-item reveal reveal-delay-1" onclick="toggleFaq(this)">
      <div class="faq-q">How long does a full grooming session take?<div class="faq-toggle">+</div></div>
      <div class="faq-a">A standard haircut takes 45–60 minutes. Our signature full experience (cut + shave + facial + massage) runs approximately 2.5 hours. Individual services vary.</div>
    </div>
    <div class="faq-item reveal reveal-delay-2" onclick="toggleFaq(this)">
      <div class="faq-q">Which products do you use?<div class="faq-toggle">+</div></div>
      <div class="faq-a">We exclusively use Kerastase, Bumble and bumble, American Crew, Schwarzkopf, and L'Oréal Professional. All products are also available for purchase in-salon.</div>
    </div>
    <div class="faq-item reveal reveal-delay-3" onclick="toggleFaq(this)">
      <div class="faq-q">Do you offer services for weddings or events?<div class="faq-toggle">+</div></div>
      <div class="faq-a">Absolutely. We offer bespoke bridal grooming packages for grooms and groomsmen, including on-location services for weddings. Contact us for tailored pricing.</div>
    </div>
    <div class="faq-item reveal" onclick="toggleFaq(this)">
      <div class="faq-q">What is your cancellation policy?<div class="faq-toggle">+</div></div>
      <div class="faq-a">We ask for at least 4 hours' notice to cancel or reschedule without a fee. Late cancellations or no-shows may incur a 50% charge of the booked service.</div>
    </div>
    <div class="faq-item reveal reveal-delay-1" onclick="toggleFaq(this)">
      <div class="faq-q">Can I buy a membership as a gift?<div class="faq-toggle">+</div></div>
      <div class="faq-a">Yes! Membership plans can be purchased as gifts. Simply contact us via WhatsApp or in-salon and we'll prepare a beautifully packaged membership welcome kit.</div>
    </div>
  </div>
</section>

<!-- ─── NEWSLETTER ─── -->
<div id="newsletter" style="position:relative;background-image:url('https://images.unsplash.com/photo-1599351431202-1e0f0137899a?w=1800&q=50&fit=crop');background-size:cover;background-position:center;background-attachment:fixed;"><div style="position:absolute;inset:0;background:rgba(26,26,26,0.95);z-index:0;pointer-events:none;"></div><div style="position:relative;z-index:1;width:100%;">
  <div class="eyebrow reveal" style="justify-content:center;"><span></span>Stay in the Loop<span></span></div>
  <h2 class="serif reveal reveal-delay-1">Exclusive Offers &amp; <em>Style Tips</em></h2>
  <p class="reveal reveal-delay-2">Join 4,000+ gentlemen who get our weekly grooming guide and first access to deals.</p>
  <div class="newsletter-form reveal reveal-delay-3">
    <input type="email" placeholder="Your email address" aria-label="Email address" />
    <button type="button">Subscribe</button>
  </div>
</div></div>

<!-- ─── BOOKING ─── -->
<section id="booking" aria-labelledby="booking-title" style="padding:0;">
  <div class="booking-info">
    <div class="eyebrow">Book Your Visit</div>
    <h2 id="booking-title" class="serif">Reserve Your<br/><em>Appointment</em></h2>
    <p>Ready to experience Noir & Co.? Fill in the form and we'll confirm your booking within 30 minutes. Prefer WhatsApp? Message us directly.</p>
    <div class="booking-contact-items">
      <div class="booking-contact-item">
        <svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 13a19.79 19.79 0 01-3.07-8.67A2 2 0 012 2.18h3a2 2 0 012 1.72 12.84 12.84 0 00.7 2.81 2 2 0 01-.45 2.11L6.11 9.91a16 16 0 006 6l1.27-1.27a2 2 0 012.11-.45 12.84 12.84 0 002.81.7A2 2 0 0122 16.92z"/></svg>
        <div><strong>+92 300 1234567</strong>WhatsApp & Calls</div>
      </div>
      <div class="booking-contact-item">
        <svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        <div><strong>hello@noirandco.pk</strong>Email Us</div>
      </div>
      <div class="booking-contact-item">
        <svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7z"/><circle cx="12" cy="9" r="2.5"/></svg>
        <div><strong>MM Alam Road, DHA</strong>Lahore, Punjab</div>
      </div>
    </div>
  </div>
  <div class="booking-form-wrap">
    <h3 class="serif">Fill in Your <em>Details</em></h3>
    <div class="form-row">
      <div class="form-group">
        <label for="fname">First Name</label>
        <input type="text" id="fname" placeholder="Ahmed" />
      </div>
      <div class="form-group">
        <label for="lname">Last Name</label>
        <input type="text" id="lname" placeholder="Khan" />
      </div>
    </div>
    <div class="form-row">
      <div class="form-group">
        <label for="phone">Phone / WhatsApp</label>
        <input type="tel" id="phone" placeholder="+92 300 0000000" />
      </div>
      <div class="form-group">
        <label for="bdate">Preferred Date</label>
        <input type="date" id="bdate" />
      </div>
    </div>
    <div class="form-row">
      <div class="form-group">
        <label for="service">Service</label>
        <select id="service">
          <option value="">Select a service</option>
          <option>Signature Haircut — PKR 1,800</option>
          <option>Royal Hot Shave — PKR 2,200</option>
          <option>Beard Sculpting — PKR 1,500</option>
          <option>Facial Treatment — PKR 2,800</option>
          <option>Full Grooming Experience — PKR 7,500</option>
        </select>
      </div>
      <div class="form-group">
        <label for="barber">Preferred Barber</label>
        <select id="barber">
          <option value="">No preference</option>
          <option>Hassan Raza</option>
          <option>Ali Zafar</option>
          <option>Usman Tariq</option>
          <option>Bilal Ahmed</option>
        </select>
      </div>
    </div>
    <div class="form-group">
      <label for="notes">Special Requests</label>
      <textarea id="notes" placeholder="Any requests or notes for your barber..."></textarea>
    </div>
    <button type="button" class="btn-primary" style="width:100%;justify-content:center;" onclick="this.textContent='✓ Booking Request Sent!';this.style.background='#2d5a27';">
      Confirm Appointment
      <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
    </button>
  </div>
</section>

<!-- ─── CONTACT ─── -->
<section id="contact" aria-label="Contact and location" style="padding:0;">
  <div class="map-wrap">
    <iframe
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3401.7!2d74.3587!3d31.5204!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMzHCsDMxJzEzLjQiTiA3NMKwMjEnMzEuMyJF!5e0!3m2!1sen!2spk!4v1234567890"
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade"
      title="Noir &amp; Co. Location"
      aria-label="Map showing Noir and Co. salon location on MM Alam Road, Lahore"
    ></iframe>
    <div class="map-overlay-badge">
      <strong>Noir &amp; Co. — DHA Branch</strong>
      <span>MM Alam Road, Lahore</span>
    </div>
  </div>
  <div class="contact-info">
    <div class="eyebrow reveal">Get in Touch</div>
    <h2 class="section-title reveal reveal-delay-1">Visit Us or<br/><em>Say Hello</em></h2>
    <div class="contact-details reveal reveal-delay-2">
      <div class="contact-detail">
        <div class="contact-detail-icon"><svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7z"/><circle cx="12" cy="9" r="2.5"/></svg></div>
        <div><strong>Address</strong><p>MM Alam Road, DHA Phase 4<br/>Lahore, Punjab, 54000</p></div>
      </div>
      <div class="contact-detail">
        <div class="contact-detail-icon"><svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/></svg></div>
        <div><strong>Hours</strong><p>Monday – Friday: 10 AM – 10 PM<br/>Saturday – Sunday: 9 AM – 11 PM</p></div>
      </div>
      <div class="contact-detail">
        <div class="contact-detail-icon"><svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 13a19.79 19.79 0 01-3.07-8.67A2 2 0 012 2.18h3a2 2 0 012 1.72c.127.96.361 1.903.7 2.81a2 2 0 01-.45 2.11L6.11 9.91a16 16 0 006 6l1.27-1.27a2 2 0 012.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0122 16.92z"/></svg></div>
        <div><strong>WhatsApp & Calls</strong><p>+92 300 1234567<br/>+92 42 3576 8900</p></div>
      </div>
      <div class="contact-detail">
        <div class="contact-detail-icon"><svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg></div>
        <div><strong>Email</strong><p>hello@noirandco.pk<br/>bookings@noirandco.pk</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ─── FOOTER ─── -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <a href="#" class="nav-logo">NOIR <span>&amp;</span> CO.</a>
      <p>Lahore's premier luxury men's grooming studio. Where precision meets prestige, and every visit is a ritual.</p>
      <div class="footer-socials">
        <a href="#" class="footer-social" aria-label="Instagram">IG</a>
        <a href="#" class="footer-social" aria-label="Facebook">FB</a>
        <a href="#" class="footer-social" aria-label="TikTok">TK</a>
        <a href="#" class="footer-social" aria-label="YouTube">YT</a>
      </div>
    </div>
    <div class="footer-col">
      <h4>Services</h4>
      <ul>
        <li><a href="#services">Signature Haircut</a></li>
        <li><a href="#services">Royal Hot Shave</a></li>
        <li><a href="#services">Beard Sculpting</a></li>
        <li><a href="#services">Facial Treatment</a></li>
        <li><a href="#services">Colour & Highlights</a></li>
        <li><a href="#services">Full Experience</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Navigate</h4>
      <ul>
        <li><a href="#about">About Us</a></li>
        <li><a href="#team">Meet the Team</a></li>
        <li><a href="#gallery">Gallery</a></li>
        <li><a href="#membership">Memberships</a></li>
        <li><a href="#giftcards">Gift Cards</a></li>
        <li><a href="#faq">FAQ</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Visit Us</h4>
      <ul>
        <li><a href="#">MM Alam Road, DHA</a></li>
        <li><a href="#">Lahore, Punjab</a></li>
        <li><a href="tel:+923001234567">+92 300 1234567</a></li>
        <li><a href="mailto:hello@noirandco.pk">hello@noirandco.pk</a></li>
        <li><a href="#">Mon–Fri: 10am–10pm</a></li>
        <li><a href="#">Sat–Sun: 9am–11pm</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2024 Noir & Co. All rights reserved. <a href="#">Privacy Policy</a> · <a href="#">Terms</a></p>
    <p style="font-size:11px;color:rgba(255,255,255,.2);">Crafted with care for the discerning gentleman.</p>
  </div>
</footer>

<!-- ─── FLOATING BUTTONS ─── -->
<div class="fab-group" aria-label="Floating action buttons">
  <a href="https://wa.me/923001234567" class="fab fab-whatsapp" aria-label="Chat on WhatsApp" target="_blank" rel="noopener">
    <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/></svg>
  </a>
  <button class="fab fab-top" id="scrollTopBtn" onclick="window.scrollTo({top:0,behavior:'smooth'})" aria-label="Scroll to top">
    <svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24"><path d="M18 15l-6-6-6 6"/></svg>
  </button>
</div>

<script>
  // ─── NAV SCROLL
  const nav = document.getElementById('nav');
  const scrollBtn = document.getElementById('scrollTopBtn');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('scrolled', window.scrollY > 50);
    scrollBtn.classList.toggle('visible', window.scrollY > 400);
  });

  // ─── REVEAL ON SCROLL
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); } });
  }, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });
  reveals.forEach(el => observer.observe(el));

  // ─── FAQ TOGGLE
  function toggleFaq(item) {
    const wasOpen = item.classList.contains('open');
    document.querySelectorAll('.faq-item').forEach(i => i.classList.remove('open'));
    if (!wasOpen) item.classList.add('open');
  }

  // ─── GIFT CARD AMOUNT
  function updateGC(el, val) {
    document.querySelectorAll('.amount-pill').forEach(p => p.classList.remove('active'));
    el.classList.add('active');
    document.getElementById('gc-display').textContent = val;
  }
</script>

</body>
</html>
