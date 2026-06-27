# website
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Parrilladas Querétaro – Sabor a Brasas</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Inter:wght@400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --red: #C1392B;
      --dark-red: #8B1A0E;
      --orange: #E8601C;
      --black: #111111;
      --dark: #1A1A1A;
      --charcoal: #2C2C2C;
      --cream: #F7F3EE;
      --gold: #D4A843;
      --white: #FFFFFF;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Inter', sans-serif;
      background: var(--black);
      color: var(--cream);
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 16px 5%;
      background: rgba(17,17,17,0.95);
      backdrop-filter: blur(8px);
      border-bottom: 1px solid rgba(193,57,43,0.3);
    }
    .nav-logo { height: 52px; }
    .nav-links { display: flex; gap: 32px; list-style: none; }
    .nav-links a {
      color: var(--cream);
      text-decoration: none;
      font-size: 0.85rem;
      font-weight: 500;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--orange); }
    .nav-cta {
      background: var(--red);
      color: var(--white) !important;
      padding: 10px 22px;
      border-radius: 4px;
      font-weight: 600 !important;
    }
    .nav-cta:hover { background: var(--dark-red) !important; color: var(--white) !important; }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      position: relative;
      overflow: hidden;
      background:
        linear-gradient(to bottom, rgba(17,17,17,0.55) 0%, rgba(17,17,17,0.82) 100%),
        url('https://images.unsplash.com/photo-1544025162-d76694265947?w=1600&q=80') center/cover no-repeat;
    }
    .hero-content { position: relative; z-index: 2; padding: 100px 20px 60px; }
    .hero-badge {
      display: inline-block;
      border: 1px solid var(--orange);
      color: var(--orange);
      font-size: 0.72rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      padding: 6px 18px;
      border-radius: 2px;
      margin-bottom: 24px;
    }
    .hero h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.8rem, 7vw, 5.5rem);
      font-weight: 900;
      line-height: 1.05;
      margin-bottom: 20px;
      color: var(--white);
    }
    .hero h1 span { color: var(--orange); }
    .hero-sub {
      font-size: 1.1rem;
      color: rgba(247,243,238,0.8);
      max-width: 520px;
      margin: 0 auto 40px;
      line-height: 1.6;
    }
    .hero-actions { display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; }
    .btn-primary {
      display: inline-flex; align-items: center; gap: 10px;
      background: var(--red);
      color: var(--white);
      padding: 16px 32px;
      border-radius: 4px;
      text-decoration: none;
      font-weight: 600;
      font-size: 0.95rem;
      letter-spacing: 0.04em;
      transition: background 0.2s, transform 0.15s;
    }
    .btn-primary:hover { background: var(--dark-red); transform: translateY(-2px); }
    .btn-secondary {
      display: inline-flex; align-items: center; gap: 10px;
      border: 1.5px solid var(--cream);
      color: var(--cream);
      padding: 15px 32px;
      border-radius: 4px;
      text-decoration: none;
      font-weight: 500;
      font-size: 0.95rem;
      transition: border-color 0.2s, color 0.2s;
    }
    .btn-secondary:hover { border-color: var(--orange); color: var(--orange); }
    .hero-stats {
      display: flex; justify-content: center; gap: 48px;
      margin-top: 56px; flex-wrap: wrap;
    }
    .stat { text-align: center; }
    .stat-num {
      font-family: 'Playfair Display', serif;
      font-size: 2.4rem;
      font-weight: 700;
      color: var(--orange);
      line-height: 1;
    }
    .stat-label { font-size: 0.78rem; color: rgba(247,243,238,0.6); letter-spacing: 0.1em; margin-top: 4px; text-transform: uppercase; }

    /* ── SECTION COMMON ── */
    section { padding: 96px 5%; }
    .section-tag {
      display: inline-block;
      color: var(--orange);
      font-size: 0.72rem;
      font-weight: 600;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      margin-bottom: 12px;
    }
    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 4vw, 3rem);
      font-weight: 700;
      color: var(--white);
      line-height: 1.2;
      margin-bottom: 20px;
    }
    .section-sub {
      color: rgba(247,243,238,0.65);
      font-size: 1rem;
      line-height: 1.7;
      max-width: 560px;
    }
    .divider {
      width: 48px; height: 3px;
      background: linear-gradient(90deg, var(--red), var(--orange));
      border-radius: 2px;
      margin: 16px 0 32px;
    }

    /* ── NOSOTROS ── */
    #nosotros { background: var(--dark); }
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 64px;
      align-items: center;
      max-width: 1200px;
      margin: 0 auto;
    }
    .about-img-wrap {
      position: relative;
      border-radius: 8px;
      overflow: hidden;
    }
    .about-img-wrap img {
      width: 100%; height: 480px; object-fit: cover;
      display: block;
    }
    .about-img-badge {
      position: absolute; bottom: 24px; right: 24px;
      background: var(--red);
      color: var(--white);
      padding: 12px 20px;
      border-radius: 4px;
      font-weight: 700;
      font-size: 0.85rem;
    }
    .about-features { display: flex; flex-direction: column; gap: 20px; margin-top: 32px; }
    .feature-item { display: flex; align-items: flex-start; gap: 16px; }
    .feature-icon {
      width: 40px; height: 40px; flex-shrink: 0;
      background: rgba(193,57,43,0.15);
      border: 1px solid rgba(193,57,43,0.4);
      border-radius: 6px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.2rem;
    }
    .feature-title { font-weight: 600; color: var(--white); margin-bottom: 4px; }
    .feature-desc { font-size: 0.88rem; color: rgba(247,243,238,0.6); line-height: 1.5; }

    /* ── MENU ── */
    #menu { background: var(--black); }
    .menu-header { text-align: center; margin-bottom: 56px; }
    .menu-header .section-sub { margin: 0 auto; }
    .menu-header .divider { margin: 16px auto 32px; }
    .menu-tabs {
      display: flex; justify-content: center; gap: 8px; flex-wrap: wrap;
      margin-bottom: 48px;
    }
    .tab {
      padding: 10px 24px;
      border-radius: 4px;
      border: 1.5px solid rgba(247,243,238,0.2);
      background: transparent;
      color: rgba(247,243,238,0.6);
      font-size: 0.85rem;
      font-weight: 500;
      cursor: pointer;
      transition: all 0.2s;
      letter-spacing: 0.05em;
    }
    .tab.active, .tab:hover {
      background: var(--red);
      border-color: var(--red);
      color: var(--white);
    }
    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 24px;
      max-width: 1200px;
      margin: 0 auto;
    }
    .menu-card {
      background: var(--charcoal);
      border-radius: 8px;
      overflow: hidden;
      border: 1px solid rgba(255,255,255,0.06);
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .menu-card:hover { transform: translateY(-4px); box-shadow: 0 20px 40px rgba(0,0,0,0.4); }
    .menu-card-img { width: 100%; height: 200px; object-fit: cover; display: block; }
    .menu-card-body { padding: 20px; }
    .menu-card-tag {
      font-size: 0.7rem; font-weight: 600; letter-spacing: 0.15em;
      text-transform: uppercase; color: var(--orange); margin-bottom: 6px;
    }
    .menu-card-name { font-family: 'Playfair Display', serif; font-size: 1.2rem; color: var(--white); margin-bottom: 8px; }
    .menu-card-desc { font-size: 0.85rem; color: rgba(247,243,238,0.6); line-height: 1.5; margin-bottom: 16px; }
    .menu-card-footer { display: flex; align-items: center; justify-content: space-between; }
    .menu-price { font-size: 1.2rem; font-weight: 700; color: var(--gold); }
    .menu-price-note { font-size: 0.72rem; color: rgba(247,243,238,0.4); }
    .menu-order-btn {
      background: rgba(193,57,43,0.2);
      border: 1px solid rgba(193,57,43,0.5);
      color: var(--red);
      padding: 8px 16px;
      border-radius: 4px;
      font-size: 0.8rem;
      font-weight: 600;
      cursor: pointer;
      text-decoration: none;
      transition: all 0.2s;
    }
    .menu-order-btn:hover { background: var(--red); color: var(--white); }
    .menu-note {
      text-align: center;
      margin-top: 40px;
      padding: 20px;
      background: rgba(193,57,43,0.08);
      border: 1px solid rgba(193,57,43,0.2);
      border-radius: 8px;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
      font-size: 0.88rem;
      color: rgba(247,243,238,0.7);
    }
    .menu-note strong { color: var(--orange); }

    /* ── REVIEWS ── */
    #resenas { background: var(--dark); }
    .reviews-header { text-align: center; margin-bottom: 56px; }
    .reviews-header .divider { margin: 16px auto 8px; }
    .rating-summary {
      display: flex; align-items: center; justify-content: center; gap: 16px; margin-bottom: 48px;
    }
    .rating-big { font-family: 'Playfair Display', serif; font-size: 5rem; font-weight: 700; color: var(--gold); line-height: 1; }
    .rating-details { text-align: left; }
    .stars { color: var(--gold); font-size: 1.4rem; letter-spacing: 2px; }
    .rating-count { font-size: 0.85rem; color: rgba(247,243,238,0.5); margin-top: 4px; }
    .reviews-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(320px,1fr));
      gap: 24px; max-width: 1100px; margin: 0 auto;
    }
    .review-card {
      background: var(--charcoal);
      border-radius: 8px; padding: 28px;
      border: 1px solid rgba(255,255,255,0.06);
      position: relative;
    }
    .review-card::before {
      content: '\201C';
      position: absolute; top: 16px; right: 24px;
      font-family: 'Playfair Display', serif;
      font-size: 4rem; color: rgba(193,57,43,0.25);
      line-height: 1;
    }
    .reviewer { display: flex; align-items: center; gap: 14px; margin-bottom: 16px; }
    .reviewer-avatar {
      width: 44px; height: 44px; border-radius: 50%;
      background: var(--red); display: flex; align-items: center; justify-content: center;
      font-weight: 700; font-size: 1rem; color: var(--white); flex-shrink: 0;
    }
    .reviewer-name { font-weight: 600; color: var(--white); font-size: 0.95rem; }
    .reviewer-meta { font-size: 0.75rem; color: rgba(247,243,238,0.4); margin-top: 2px; }
    .review-stars { color: var(--gold); font-size: 0.9rem; margin-bottom: 12px; }
    .review-text { font-size: 0.88rem; color: rgba(247,243,238,0.75); line-height: 1.65; }
    .review-date { font-size: 0.72rem; color: rgba(247,243,238,0.35); margin-top: 14px; }

    /* ── PEDIDO ── */
    #pedido { background: var(--black); }
    .order-wrap { max-width: 1100px; margin: 0 auto; display: grid; grid-template-columns: 1fr 1fr; gap: 64px; align-items: center; }
    .order-info h2 { font-family: 'Playfair Display', serif; font-size: clamp(1.8rem,3.5vw,2.8rem); color: var(--white); margin-bottom: 16px; }
    .order-info p { color: rgba(247,243,238,0.65); line-height: 1.7; margin-bottom: 32px; }
    .contact-items { display: flex; flex-direction: column; gap: 16px; }
    .contact-item { display: flex; align-items: center; gap: 16px; }
    .contact-icon {
      width: 48px; height: 48px; border-radius: 8px;
      background: rgba(193,57,43,0.15); border: 1px solid rgba(193,57,43,0.35);
      display: flex; align-items: center; justify-content: center; font-size: 1.3rem; flex-shrink: 0;
    }
    .contact-label { font-size: 0.75rem; color: rgba(247,243,238,0.45); letter-spacing: 0.1em; text-transform: uppercase; }
    .contact-value { font-size: 0.95rem; color: var(--white); font-weight: 500; margin-top: 2px; }
    .order-card {
      background: var(--charcoal);
      border-radius: 12px; padding: 40px;
      border: 1px solid rgba(255,255,255,0.07);
    }
    .order-card h3 { font-family: 'Playfair Display', serif; font-size: 1.5rem; color: var(--white); margin-bottom: 24px; }
    .order-steps { display: flex; flex-direction: column; gap: 20px; margin-bottom: 32px; }
    .order-step { display: flex; gap: 16px; align-items: flex-start; }
    .step-num {
      width: 32px; height: 32px; border-radius: 50%;
      background: var(--red); color: var(--white); font-weight: 700; font-size: 0.85rem;
      display: flex; align-items: center; justify-content: center; flex-shrink: 0;
    }
    .step-text { font-size: 0.9rem; color: rgba(247,243,238,0.75); line-height: 1.5; padding-top: 6px; }
    .step-text strong { color: var(--white); }
    .whatsapp-btn {
      display: flex; align-items: center; justify-content: center; gap: 12px;
      background: #25D366; color: var(--white);
      padding: 16px 32px; border-radius: 8px;
      text-decoration: none; font-weight: 700; font-size: 1rem;
      width: 100%; transition: background 0.2s;
    }
    .whatsapp-btn:hover { background: #1DA851; }

    /* ── MAPA ── */
    #ubicacion { background: var(--dark); padding: 0; }
    .map-wrap {
      display: grid; grid-template-columns: 1fr 2fr;
      min-height: 400px;
    }
    .map-info {
      background: var(--charcoal);
      padding: 56px 40px;
      display: flex; flex-direction: column; justify-content: center;
    }
    .map-info .section-tag { margin-bottom: 8px; }
    .map-info h2 { font-family: 'Playfair Display', serif; font-size: 1.8rem; color: var(--white); margin-bottom: 24px; }
    .map-detail { display: flex; gap: 12px; margin-bottom: 16px; }
    .map-detail-icon { font-size: 1.1rem; flex-shrink: 0; margin-top: 2px; }
    .map-detail-text { font-size: 0.9rem; color: rgba(247,243,238,0.7); line-height: 1.5; }
    .map-detail-text strong { color: var(--white); display: block; margin-bottom: 2px; }
    .map-embed { flex: 1; }
    .map-embed iframe { width: 100%; height: 100%; min-height: 400px; border: none; display: block; }

    /* ── FOOTER ── */
    footer {
      background: #0A0A0A;
      border-top: 1px solid rgba(255,255,255,0.06);
      padding: 48px 5% 32px;
    }
    .footer-top {
      display: flex; align-items: center; justify-content: space-between;
      flex-wrap: wrap; gap: 24px; margin-bottom: 32px;
    }
    .footer-logo { height: 56px; }
    .footer-links { display: flex; gap: 28px; flex-wrap: wrap; }
    .footer-links a { color: rgba(247,243,238,0.5); text-decoration: none; font-size: 0.85rem; transition: color 0.2s; }
    .footer-links a:hover { color: var(--orange); }
    .footer-bottom {
      border-top: 1px solid rgba(255,255,255,0.06);
      padding-top: 24px;
      display: flex; align-items: center; justify-content: space-between;
      flex-wrap: wrap; gap: 12px;
    }
    .footer-copy { font-size: 0.8rem; color: rgba(247,243,238,0.3); }
    .footer-powered { font-size: 0.8rem; color: rgba(247,243,238,0.3); }

    /* ── FLOATING WA ── */
    .float-wa {
      position: fixed; bottom: 28px; right: 28px; z-index: 200;
      width: 60px; height: 60px; border-radius: 50%;
      background: #25D366; display: flex; align-items: center; justify-content: center;
      box-shadow: 0 4px 20px rgba(37,211,102,0.5);
      text-decoration: none; transition: transform 0.2s;
    }
    .float-wa:hover { transform: scale(1.1); }
    .float-wa svg { width: 30px; height: 30px; fill: white; }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      .about-grid, .order-wrap, .map-wrap { grid-template-columns: 1fr; }
      .nav-links { display: none; }
      .map-embed iframe { min-height: 300px; }
    }
    @media (max-width: 600px) {
      section { padding: 72px 6%; }
      .hero-stats { gap: 28px; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <img src="logo.png" alt="Parrilladas Querétaro" class="nav-logo" onerror="this.style.display='none'" />
  <ul class="nav-links">
    <li><a href="#nosotros">Nosotros</a></li>
    <li><a href="#menu">Menú</a></li>
    <li><a href="#resenas">Reseñas</a></li>
    <li><a href="#ubicacion">Ubicación</a></li>
    <li><a href="https://wa.me/524461483263" class="nav-cta">Pedir ahora</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="inicio">
  <div class="hero-content">
    <span class="hero-badge">🔥 Desde 2021 · Plaza Tejeda, Querétaro</span>
    <h1>El sabor de<br />la <span>parrilla</span><br />auténtica</h1>
    <p class="hero-sub">Parrilladas completas con las mejores carnes, chorizos importados y guarniciones. Entrega a domicilio en Querétaro.</p>
    <div class="hero-actions">
      <a href="https://wa.me/524461483263?text=Hola!%20Quisiera%20hacer%20un%20pedido%20%F0%9F%94%A5" class="btn-primary">
        🛒 Hacer pedido por WhatsApp
      </a>
      <a href="#menu" class="btn-secondary">
        Ver menú completo →
      </a>
    </div>
    <div class="hero-stats">
      <div class="stat">
        <div class="stat-num">4.6</div>
        <div class="stat-label">⭐ Calificación</div>
      </div>
      <div class="stat">
        <div class="stat-num">152+</div>
        <div class="stat-label">Reseñas Google</div>
      </div>
      <div class="stat">
        <div class="stat-num">3+</div>
        <div class="stat-label">Años de experiencia</div>
      </div>
    </div>
  </div>
</section>

<!-- NOSOTROS -->
<section id="nosotros">
  <div class="about-grid">
    <div class="about-img-wrap">
      <img src="https://images.unsplash.com/photo-1529193591184-b1d58069ecdd?w=800&q=80" alt="Parrillada" />
      <div class="about-img-badge">🏆 4.6 estrellas en Google</div>
    </div>
    <div>
      <span class="section-tag">Quiénes somos</span>
      <h2 class="section-title">La parrillada que<br />Querétaro recomienda</h2>
      <div class="divider"></div>
      <p class="section-sub">Somos especialistas en parrilladas a domicilio. Seleccionamos los mejores cortes y embutidos para que disfrutes una experiencia de asador premium sin salir de casa.</p>
      <div class="about-features">
        <div class="feature-item">
          <div class="feature-icon">🥩</div>
          <div>
            <div class="feature-title">Carnes de calidad</div>
            <div class="feature-desc">Arrachera, carne de res y cortes seleccionados con el mejor sazón.</div>
          </div>
        </div>
        <div class="feature-item">
          <div class="feature-icon">🌭</div>
          <div>
            <div class="feature-title">Embutidos importados</div>
            <div class="feature-desc">Chorizo español, chorizo argentino, chistorra y más variedades.</div>
          </div>
        </div>
        <div class="feature-item">
          <div class="feature-icon">🚀</div>
          <div>
            <div class="feature-title">Entrega a tiempo</div>
            <div class="feature-desc">Coordinamos la entrega para que llegue calientita a tu mesa.</div>
          </div>
        </div>
        <div class="feature-item">
          <div class="feature-icon">🎉</div>
          <div>
            <div class="feature-title">Ideal para eventos</div>
            <div class="feature-desc">Navidad, Año Nuevo, cumpleaños o reuniones familiares.</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- MENU -->
<section id="menu">
  <div class="menu-header">
    <span class="section-tag">Lo que ofrecemos</span>
    <h2 class="section-title">Nuestro Menú</h2>
    <div class="divider"></div>
    <p class="section-sub">Paquetes pensados para compartir. Todos incluyen guarniciones, salsas y tortillas.</p>
  </div>

  <div class="menu-grid">

    <div class="menu-card">
      <img class="menu-card-img" src="https://images.unsplash.com/photo-1544025162-d76694265947?w=600&q=80" alt="Parrillada para 2" />
      <div class="menu-card-body">
        <div class="menu-card-tag">Más pedido</div>
        <div class="menu-card-name">Parrillada para 2</div>
        <div class="menu-card-desc">Arrachera + chorizo español + chorizo argentino. Incluye tortillas, nopales y salsas.</div>
        <div class="menu-card-footer">
          <div>
            <div class="menu-price">$XXX</div>
            <div class="menu-price-note">precio tentativo</div>
          </div>
          <a href="https://wa.me/524461483263?text=Hola!%20Quiero%20pedir%20una%20Parrillada%20para%202%20%F0%9F%94%A5" class="menu-order-btn">Pedir</a>
        </div>
      </div>
    </div>

    <div class="menu-card">
      <img class="menu-card-img" src="https://images.unsplash.com/photo-1558030006-450675393462?w=600&q=80" alt="Parrillada para 4" />
      <div class="menu-card-body">
        <div class="menu-card-tag">Familiar</div>
        <div class="menu-card-name">Parrillada para 4</div>
        <div class="menu-card-desc">Doble porción de arrachera + mix de chorizos + chistorra. Perfecta para la familia.</div>
        <div class="menu-card-footer">
          <div>
            <div class="menu-price">$XXX</div>
            <div class="menu-price-note">precio tentativo</div>
          </div>
          <a href="https://wa.me/524461483263?text=Hola!%20Quiero%20pedir%20una%20Parrillada%20para%204%20%F0%9F%94%A5" class="menu-order-btn">Pedir</a>
        </div>
      </div>
    </div>

    <div class="menu-card">
      <img class="menu-card-img" src="https://images.unsplash.com/photo-1523986490752-c28064f26be3?w=600&q=80" alt="Parrillada Especial" />
      <div class="menu-card-body">
        <div class="menu-card-tag">Premium</div>
        <div class="menu-card-name">Parrillada Especial</div>
        <div class="menu-card-desc">Lo mejor de la parrilla: arrachera premium + todos los embutidos + guarniciones completas.</div>
        <div class="menu-card-footer">
          <div>
            <div class="menu-price">$XXX</div>
            <div class="menu-price-note">precio tentativo</div>
          </div>
          <a href="https://wa.me/524461483263?text=Hola!%20Quiero%20pedir%20la%20Parrillada%20Especial%20%F0%9F%94%A5" class="menu-order-btn">Pedir</a>
        </div>
      </div>
    </div>

    <div class="menu-card">
      <img class="menu-card-img" src="https://images.unsplash.com/photo-1611143669185-af224c5e3252?w=600&q=80" alt="Extras" />
      <div class="menu-card-body">
        <div class="menu-card-tag">Extras</div>
        <div class="menu-card-name">Porciones Extra</div>
        <div class="menu-card-desc">Chistorra, chorizo español o argentino extra. Pídelas como complemento a tu parrillada.</div>
        <div class="menu-card-footer">
          <div>
            <div class="menu-price">$XXX</div>
            <div class="menu-price-note">precio tentativo</div>
          </div>
          <a href="https://wa.me/524461483263?text=Hola!%20Quiero%20pedir%20extras%20%F0%9F%94%A5" class="menu-order-btn">Pedir</a>
        </div>
      </div>
    </div>

  </div>

  <div class="menu-note">
    <strong>¿Tienes un evento especial?</strong> Contáctanos por WhatsApp para armar un paquete a tu medida para fiestas, navidad o cualquier reunión. 🎊
  </div>
</section>

<!-- RESEÑAS -->
<section id="resenas">
  <div class="reviews-header">
    <span class="section-tag">Lo que dicen nuestros clientes</span>
    <h2 class="section-title">Reseñas</h2>
    <div class="divider"></div>
  </div>
  <div class="rating-summary">
    <div class="rating-big">4.6</div>
    <div class="rating-details">
      <div class="stars">★★★★½</div>
      <div style="color:var(--white);font-weight:600;margin-top:4px;">Excelente</div>
      <div class="rating-count">Basado en 152 reseñas en Google</div>
    </div>
  </div>
  <div class="reviews-grid">

    <div class="review-card">
      <div class="reviewer">
        <div class="reviewer-avatar">B</div>
        <div>
          <div class="reviewer-name">Brany Guzmán</div>
          <div class="reviewer-meta">Local Guide · 18 reseñas</div>
        </div>
      </div>
      <div class="review-stars">★★★★★</div>
      <div class="review-text">"Nuevamente pedimos una deliciosa parrillada de Parrilladas Querétaro (sucursal Tejeda) y quedamos encantados. Probamos arrachera, chorizo español y argentino y un extra de chistorra — todo venía con un sazón espectacular, de verdad se nota la calidad."</div>
      <div class="review-date">Hace 5 meses</div>
    </div>

    <div class="review-card">
      <div class="reviewer">
        <div class="reviewer-avatar">Z</div>
        <div>
          <div class="reviewer-name">Zahid Aparicio</div>
          <div class="reviewer-meta">Local Guide · 25 reseñas</div>
        </div>
      </div>
      <div class="review-stars">★★★★☆</div>
      <div class="review-text">"Las porciones de carne son bastante generosas. Pedí un paquete para 2-3 personas y fue suficiente. Se nota que usan buena calidad de ingredientes."</div>
      <div class="review-date">Hace 2 semanas</div>
    </div>

    <div class="review-card">
      <div class="reviewer">
        <div class="reviewer-avatar">A</div>
        <div>
          <div class="reviewer-name">Cliente satisfecho</div>
          <div class="reviewer-meta">Google Maps</div>
        </div>
      </div>
      <div class="review-stars">★★★★★</div>
      <div class="review-text">"Excelente sabor en todos los cortes. El chorizo argentino es increíble. Ya los tengo como mis favoritos para los fines de semana. 100% recomendados."</div>
      <div class="review-date">Hace 1 mes</div>
    </div>

  </div>
</section>

<!-- PEDIDO -->
<section id="pedido">
  <div class="order-wrap">
    <div class="order-info">
      <span class="section-tag">Contáctanos</span>
      <h2>¿Listo para pedir<br />tu parrillada?</h2>
      <div class="divider"></div>
      <p>Hacemos entregas a domicilio en Querétaro. Escríbenos con anticipación para garantizar tu pedido, especialmente en fechas especiales.</p>
      <div class="contact-items">
        <div class="contact-item">
          <div class="contact-icon">📱</div>
          <div>
            <div class="contact-label">WhatsApp / Teléfono</div>
            <div class="contact-value">+52 446 148 3263</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">📍</div>
          <div>
            <div class="contact-label">Ubicación</div>
            <div class="contact-value">Plaza Tejeda, Paseo de Tejeda 21,<br />Tejeda, Querétaro 76900</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">🕐</div>
          <div>
            <div class="contact-label">Horario</div>
            <div class="contact-value">Lun – Dom · [Horario por confirmar]</div>
          </div>
        </div>
      </div>
    </div>
    <div class="order-card">
      <h3>¿Cómo hacer tu pedido?</h3>
      <div class="order-steps">
        <div class="order-step">
          <div class="step-num">1</div>
          <div class="step-text"><strong>Elige tu parrillada</strong><br />Revisa el menú y decide el paquete que más te conviene.</div>
        </div>
        <div class="order-step">
          <div class="step-num">2</div>
          <div class="step-text"><strong>Escríbenos por WhatsApp</strong><br />Manda tu pedido con tu nombre, paquete y dirección de entrega.</div>
        </div>
        <div class="order-step">
          <div class="step-num">3</div>
          <div class="step-text"><strong>Coordina tu entrega</strong><br />Te confirmamos hora de entrega para que llegue caliente.</div>
        </div>
        <div class="order-step">
          <div class="step-num">4</div>
          <div class="step-text"><strong>¡A disfrutar!</strong><br />Recibe tu parrillada lista para servir y disfruta con los tuyos.</div>
        </div>
      </div>
      <a href="https://wa.me/524461483263?text=Hola!%20Quisiera%20hacer%20un%20pedido%20de%20parrillada%20%F0%9F%94%A5" class="whatsapp-btn">
        <svg viewBox="0 0 24 24" width="24" height="24" fill="white"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.127.558 4.123 1.532 5.852L.057 23.886a.5.5 0 0 0 .611.61l6.089-1.464A11.945 11.945 0 0 0 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 22c-1.927 0-3.727-.51-5.28-1.395l-.374-.217-3.867.93.96-3.793-.234-.386A9.944 9.944 0 0 1 2 12C2 6.477 6.477 2 12 2s10 4.477 10 10-4.477 10-10 10z"/></svg>
        Pedir por WhatsApp ahora
      </a>
    </div>
  </div>
</section>

<!-- UBICACIÓN -->
<div id="ubicacion">
  <div class="map-wrap">
    <div class="map-info">
      <span class="section-tag">Dónde encontrarnos</span>
      <h2>Nuestra ubicación</h2>
      <div class="map-detail">
        <div class="map-detail-icon">📍</div>
        <div class="map-detail-text">
          <strong>Dirección</strong>
          P.º de Tejeda 21, Plaza Tejeda, Tejeda, 76900 Santiago de Querétaro, Qro.
        </div>
      </div>
      <div class="map-detail">
        <div class="map-detail-icon">🚗</div>
        <div class="map-detail-text">
          <strong>Cómo llegar</strong>
          Ubicados dentro de Plaza Tejeda, fácil acceso y estacionamiento disponible.
        </div>
      </div>
      <div class="map-detail">
        <div class="map-detail-icon">🛵</div>
        <div class="map-detail-text">
          <strong>Entrega a domicilio</strong>
          Hacemos entregas en Querétaro. Pregunta por cobertura en tu zona.
        </div>
      </div>
    </div>
    <div class="map-embed">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3732.1!2d-100.4399!3d20.6445!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x85d345b9b5e8b5c9%3A0x0!2sPlaza+Tejeda%2C+P.%C2%BA+de+Tejeda+21%2C+Tejeda%2C+76900+Santiago+de+Quer%C3%A9taro!5e0!3m2!1ses!2smx!4v1"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <img src="logo.png" alt="Parrilladas Querétaro" class="footer-logo" onerror="this.style.display='none'" />
    <nav class="footer-links">
      <a href="#nosotros">Nosotros</a>
      <a href="#menu">Menú</a>
      <a href="#resenas">Reseñas</a>
      <a href="#pedido">Pedido</a>
      <a href="#ubicacion">Ubicación</a>
    </nav>
  </div>
  <div class="footer-bottom">
    <div class="footer-copy">© 2025 Parrilladas Querétaro. Todos los derechos reservados.</div>
    <div class="footer-powered">Querétaro, México 🇲🇽</div>
  </div>
</footer>

<!-- FLOATING WHATSAPP -->
<a href="https://wa.me/524461483263?text=Hola!%20Quisiera%20hacer%20un%20pedido%20%F0%9F%94%A5" class="float-wa" title="Pedir por WhatsApp">
  <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
    <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/>
    <path d="M12 0C5.373 0 0 5.373 0 12c0 2.127.558 4.123 1.532 5.852L.057 23.886a.5.5 0 0 0 .611.61l6.089-1.464A11.945 11.945 0 0 0 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 22c-1.927 0-3.727-.51-5.28-1.395l-.374-.217-3.867.93.96-3.793-.234-.386A9.944 9.944 0 0 1 2 12C2 6.477 6.477 2 12 2s10 4.477 10 10-4.477 10-10 10z"/>
  </svg>
</a>

</body>
</html>
