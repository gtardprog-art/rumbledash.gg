# rumbledash.gg
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="Content-Security-Policy" content="default-src 'self' 'unsafe-inline' 'unsafe-eval' https://fonts.googleapis.com https://fonts.gstatic.com https://discord.gg https://www.tiktok.com; img-src 'self' data: blob:;">
<meta name="referrer" content="no-referrer">
<title>Rumble Dash — Loja Oficial</title>
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@400;600;700&family=Orbitron:wght@400;700;900&family=Inter:wght@400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --purple: #9b30ff;
    --purple-light: #c77dff;
    --purple-dark: #5a00b5;
    --purple-glow: rgba(155, 48, 255, 0.55);
    --black: #080808;
    --surface: #111118;
    --surface2: #16161f;
    --white: #f0f0f8;
    --grey: #888899;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', sans-serif;
    background-color: var(--black);
    color: var(--white);
    overflow-x: hidden;
    min-height: 100vh;
    position: relative;
  }

  /* === GRID TEXTURE === */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(255,255,255,0.035) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.035) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  /* Subtle purple corner radiance */
  body::after {
    content: '';
    position: fixed;
    top: -200px; left: -200px;
    width: 700px; height: 700px;
    background: radial-gradient(circle, rgba(155,48,255,0.18) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
    animation: driftLight 10s ease-in-out infinite alternate;
  }

  @keyframes driftLight {
    from { transform: translate(0,0); }
    to   { transform: translate(120px, 80px); }
  }

  /* === NAVBAR === */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 100;
    background: rgba(8,8,8,0.85);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid rgba(155,48,255,0.25);
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 2rem;
    height: 64px;
  }

  .nav-logo {
    display: flex; align-items: center; gap: 10px;
    font-family: 'Orbitron', sans-serif;
    font-weight: 900; font-size: 1.1rem;
    color: var(--purple-light);
    letter-spacing: 2px;
    text-shadow: 0 0 10px var(--purple-glow);
  }

  .nav-logo img { height: 38px; border-radius: 6px; }

  .nav-links { display: flex; gap: 0.25rem; }

  .nav-links a {
    font-family: 'Rajdhani', sans-serif;
    font-weight: 600; font-size: 0.9rem;
    color: var(--grey);
    text-decoration: none;
    padding: 0.5rem 1rem;
    border-radius: 6px;
    letter-spacing: 1px;
    text-transform: uppercase;
    transition: color 0.25s, background 0.25s;
  }

  .nav-links a:hover, .nav-links a.active {
    color: var(--purple-light);
    background: rgba(155,48,255,0.12);
  }

  /* === HERO === */
  .hero {
    position: relative; z-index: 1;
    min-height: 100vh;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    text-align: center;
    padding: 6rem 2rem 4rem;
    overflow: hidden;
  }

  .hero-bg-img {
    position: absolute; inset: 0;
    background: url('data:image/jpeg;base64,PLACEHOLDER') center/cover no-repeat;
    opacity: 0.07;
    filter: blur(4px);
    z-index: 0;
  }

  .hero-logo {
    width: min(340px, 72vw);
    position: relative; z-index: 1;
    filter: drop-shadow(0 0 30px var(--purple-glow));
    animation: logoFloat 4s ease-in-out infinite alternate;
  }

  @keyframes logoFloat {
    from { transform: translateY(0px); filter: drop-shadow(0 0 20px var(--purple-glow)); }
    to   { transform: translateY(-12px); filter: drop-shadow(0 0 40px rgba(155,48,255,0.9)); }
  }

  .hero-tagline {
    font-family: 'Rajdhani', sans-serif;
    font-size: clamp(0.85rem, 2vw, 1.05rem);
    color: var(--grey);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-top: 1.4rem;
    position: relative; z-index: 1;
  }

  .hero-tagline span { color: var(--purple-light); }

  .hero-cta {
    position: relative; z-index: 1;
    margin-top: 2.5rem;
    display: flex; flex-direction: column; align-items: center; gap: 0.7rem;
  }

  .hero-cta-label {
    font-family: 'Rajdhani', sans-serif;
    font-size: 0.95rem;
    color: var(--grey);
    letter-spacing: 1px;
  }

  /* Botão principal */
  .btn-primary {
    font-family: 'Orbitron', sans-serif;
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: #fff;
    background: linear-gradient(135deg, var(--purple-dark), var(--purple));
    border: none;
    border-radius: 8px;
    padding: 0.85rem 2.2rem;
    cursor: pointer;
    position: relative;
    overflow: hidden;
    text-decoration: none;
    display: inline-block;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 0 20px rgba(155,48,255,0.5), inset 0 1px 0 rgba(255,255,255,0.15);
  }

  .btn-primary::before {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(90deg, transparent 0%, rgba(255,255,255,0.18) 50%, transparent 100%);
    transform: translateX(-100%);
    transition: transform 0.5s;
  }

  .btn-primary:hover::before { transform: translateX(100%); }
  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 0 36px rgba(155,48,255,0.75), inset 0 1px 0 rgba(255,255,255,0.2);
  }
  .btn-primary:active { transform: scale(0.97); }

  /* Botão cupom */
  .btn-coupon {
    font-family: 'Orbitron', sans-serif;
    font-weight: 700; font-size: 0.85rem;
    letter-spacing: 2px; text-transform: uppercase;
    color: var(--purple-light);
    background: transparent;
    border: 1.5px solid var(--purple);
    border-radius: 8px;
    padding: 0.8rem 2rem;
    cursor: pointer;
    transition: all 0.25s;
    box-shadow: 0 0 10px rgba(155,48,255,0.2);
    margin-top: 0.5rem;
  }

  .btn-coupon:hover {
    background: rgba(155,48,255,0.12);
    box-shadow: 0 0 22px rgba(155,48,255,0.45);
    transform: translateY(-2px);
  }

  /* === COUPON MODAL === */
  .modal-overlay {
    position: fixed; inset: 0;
    background: rgba(0,0,0,0.75);
    backdrop-filter: blur(6px);
    z-index: 999;
    display: flex; align-items: center; justify-content: center;
    opacity: 0; pointer-events: none;
    transition: opacity 0.3s;
  }

  .modal-overlay.open { opacity: 1; pointer-events: all; }

  .modal {
    background: var(--surface2);
    border: 1px solid rgba(155,48,255,0.5);
    border-radius: 16px;
    padding: 2.5rem 2.8rem;
    text-align: center;
    max-width: 360px; width: 90%;
    box-shadow: 0 0 60px rgba(155,48,255,0.4);
    transform: scale(0.85);
    transition: transform 0.3s;
    position: relative;
  }

  .modal-overlay.open .modal { transform: scale(1); }

  .modal h2 {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.05rem;
    color: var(--purple-light);
    letter-spacing: 2px;
    margin-bottom: 1rem;
  }

  .modal-code {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.6rem; font-weight: 900;
    color: #fff;
    letter-spacing: 4px;
    background: linear-gradient(135deg, var(--purple-dark), var(--purple));
    padding: 0.6rem 1.4rem;
    border-radius: 8px;
    display: inline-block;
    margin: 0.8rem 0;
    box-shadow: 0 0 20px rgba(155,48,255,0.6);
  }

  .modal-disc {
    font-size: 1rem; color: var(--purple-light);
    font-family: 'Rajdhani', sans-serif;
    font-weight: 600; letter-spacing: 1px;
    margin-top: 0.5rem;
  }

  .modal-close {
    position: absolute; top: 12px; right: 16px;
    background: none; border: none; color: var(--grey);
    font-size: 1.3rem; cursor: pointer;
    transition: color 0.2s;
  }

  .modal-close:hover { color: var(--white); }

  /* === SECTIONS === */
  section {
    position: relative; z-index: 1;
    padding: 5rem 2rem;
  }

  .section-title {
    font-family: 'Orbitron', sans-serif;
    font-size: clamp(1.2rem, 3vw, 1.65rem);
    font-weight: 900; letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--white);
    text-align: center;
    margin-bottom: 0.5rem;
  }

  .section-title span { color: var(--purple-light); }

  .section-divider {
    width: 60px; height: 3px;
    background: linear-gradient(90deg, var(--purple-dark), var(--purple-light));
    border-radius: 2px;
    margin: 0.8rem auto 3rem;
    box-shadow: 0 0 10px var(--purple-glow);
  }

  /* === FAQ === */
  #faq { background: rgba(17,17,24,0.7); }

  .faq-grid {
    max-width: 750px; margin: 0 auto;
    display: flex; flex-direction: column; gap: 1rem;
  }

  .faq-item {
    background: var(--surface);
    border: 1px solid rgba(155,48,255,0.2);
    border-radius: 10px;
    overflow: hidden;
    transition: border-color 0.25s;
  }

  .faq-item:hover { border-color: rgba(155,48,255,0.5); }

  .faq-question {
    font-family: 'Rajdhani', sans-serif;
    font-weight: 700; font-size: 1.05rem;
    letter-spacing: 0.5px;
    color: var(--purple-light);
    padding: 1.1rem 1.4rem;
    cursor: pointer;
    display: flex; align-items: center; justify-content: space-between;
    user-select: none;
    background: none; border: none; width: 100%; text-align: left;
    transition: background 0.2s;
  }

  .faq-question:hover { background: rgba(155,48,255,0.07); }

  .faq-icon {
    font-size: 1.2rem; transition: transform 0.3s;
    flex-shrink: 0; margin-left: 1rem;
  }

  .faq-item.open .faq-icon { transform: rotate(45deg); }

  .faq-answer {
    max-height: 0; overflow: hidden;
    transition: max-height 0.4s ease, padding 0.3s;
    font-size: 0.95rem; line-height: 1.7; color: var(--grey);
    padding: 0 1.4rem;
  }

  .faq-item.open .faq-answer {
    max-height: 200px;
    padding: 0 1.4rem 1.2rem;
  }

  /* === REDES === */
  #redes { text-align: center; }

  .social-cards {
    display: flex; justify-content: center; gap: 1.5rem; flex-wrap: wrap;
    max-width: 700px; margin: 0 auto;
  }

  .social-card {
    background: var(--surface);
    border: 1px solid rgba(155,48,255,0.2);
    border-radius: 14px;
    padding: 2rem 2.5rem;
    text-align: center;
    text-decoration: none;
    color: var(--white);
    transition: all 0.3s;
    display: flex; flex-direction: column; align-items: center; gap: 0.8rem;
    min-width: 180px;
  }

  .social-card:hover {
    border-color: var(--purple);
    background: rgba(155,48,255,0.1);
    transform: translateY(-6px);
    box-shadow: 0 12px 32px rgba(155,48,255,0.3);
  }

  .social-icon { font-size: 2.2rem; }

  .social-name {
    font-family: 'Orbitron', sans-serif;
    font-size: 0.75rem; font-weight: 700;
    letter-spacing: 2px; text-transform: uppercase;
    color: var(--purple-light);
  }

  .social-label {
    font-size: 0.8rem; color: var(--grey);
    font-family: 'Rajdhani', sans-serif;
  }

  /* === SERVIDOR === */
  #servidor {
    background: rgba(17,17,24,0.7);
    text-align: center;
  }

  .server-box {
    max-width: 500px; margin: 0 auto;
    background: var(--surface);
    border: 1px solid rgba(155,48,255,0.3);
    border-radius: 16px;
    padding: 2.5rem 2rem;
    box-shadow: 0 0 40px rgba(155,48,255,0.15);
  }

  .server-box p {
    color: var(--grey); font-size: 0.95rem; line-height: 1.7;
    margin-bottom: 1.8rem;
    font-family: 'Rajdhani', sans-serif;
    font-weight: 500; font-size: 1rem;
    letter-spacing: 0.5px;
  }

  .server-link {
    font-family: 'Rajdhani', sans-serif;
    font-size: 0.85rem;
    color: rgba(155,48,255,0.7);
    margin-bottom: 1.2rem; display: block;
    letter-spacing: 1px;
  }

  /* === FOOTER === */
  footer {
    position: relative; z-index: 1;
    text-align: center;
    padding: 2rem;
    border-top: 1px solid rgba(155,48,255,0.15);
    color: var(--grey);
    font-size: 0.8rem;
    font-family: 'Rajdhani', sans-serif;
    letter-spacing: 1px;
  }

  footer span { color: var(--purple-light); }

  /* === PARTICLES === */
  #particles {
    position: fixed; inset: 0; z-index: 0; pointer-events: none;
  }

  /* === SCROLL ANIMATIONS === */
  .reveal {
    opacity: 0; transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }

  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* === RESPONSIVO === */
  @media (max-width: 600px) {
    .nav-links a { padding: 0.4rem 0.6rem; font-size: 0.75rem; }
    .hero-cta { flex-direction: column; }
    .modal { padding: 2rem 1.5rem; }
  }
</style>
</head>
<body>

<!-- CANVAS PARTICLES -->
<canvas id="particles"></canvas>

<!-- COUPON MODAL -->
<div class="modal-overlay" id="couponModal" role="dialog" aria-modal="true" aria-labelledby="modalTitle">
  <div class="modal">
    <button class="modal-close" id="modalClose" aria-label="Fechar">✕</button>
    <h2 id="modalTitle">🎉 Você liberou o cupom!</h2>
    <div class="modal-code">RUMO AO HEXA</div>
    <div class="modal-disc">5% de desconto!</div>
    <p style="margin-top:1.2rem; font-size:0.8rem; color:var(--grey); font-family:'Rajdhani',sans-serif;">
      Use no servidor oficial da loja para resgatar.
    </p>
  </div>
</div>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    <img src="1000152273.png" alt="Rumble Dash Logo" onerror="this.style.display='none'">
    RUMBLE DASH
  </div>
  <div class="nav-links">
    <a href="#faq">FAQ</a>
    <a href="#redes">Redes</a>
    <a href="#servidor">Servidor</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <img class="hero-logo" src="1000152273.png" alt="Rumble Dash" onerror="this.src='data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 width=%22300%22 height=%22200%22><text y=%22100%22 font-size=%2260%22 fill=%22%239b30ff%22 font-family=%22sans-serif%22>RD</text></svg>'">

  <p class="hero-tagline">Os melhores preços para <span>você</span></p>

  <div class="hero-cta">
    <p class="hero-cta-label">Venha conhecer nossa loja oficial!</p>
    <a class="btn-primary" href="https://discord.gg/C8twuEHbzs" target="_blank" rel="noopener noreferrer">
      Visitar Loja
    </a>
    <button class="btn-coupon" id="couponBtn">Liberar Cupom</button>
  </div>
</section>

<!-- FAQ -->
<section id="faq">
  <h2 class="section-title reveal">Perguntas <span>Frequentes</span></h2>
  <div class="section-divider reveal"></div>

  <div class="faq-grid">

    <div class="faq-item reveal">
      <button class="faq-question">
        Demora a entrega?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        Depende da alta-demanda, geralmente leva em torno de 1–3 horas a entrega.
      </div>
    </div>

    <div class="faq-item reveal">
      <button class="faq-question">
        Quais jogos vocês vendem?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        A nossa variedade de jogos são grandes, alguns deles são: Blox Fruits, GaG2, Sailor Piece e muito mais, além dos Robux que iremos começar a vender também!
      </div>
    </div>

    <div class="faq-item reveal">
      <button class="faq-question">
        São confiáveis?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        Sim! Temos muitos clientes diariamente. Vocês podem verificar os feedbacks da loja também.
      </div>
    </div>

    <div class="faq-item reveal">
      <button class="faq-question">
        Vende fora do discord?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        Não, apenas dentro do servidor. Caso vejam alguma "loja" copiando a Rumble Dash, entre em contato imediatamente pelo servidor!
      </div>
    </div>

  </div>
</section>

<!-- REDES -->
<section id="redes">
  <h2 class="section-title reveal">Nossas <span>Redes</span></h2>
  <div class="section-divider reveal"></div>

  <div class="social-cards">
    <a class="social-card reveal" href="https://www.tiktok.com/@rumble.dash?_r=1&_t=ZS-97LrPpReyxB" target="_blank" rel="noopener noreferrer">
      <div class="social-icon">🎵</div>
      <div class="social-name">TikTok</div>
      <div class="social-label">Siga-nos</div>
    </a>
    <a class="social-card reveal" href="https://discord.gg/C8twuEHbzs" target="_blank" rel="noopener noreferrer">
      <div class="social-icon">💬</div>
      <div class="social-name">Discord</div>
      <div class="social-label">Entre no servidor</div>
    </a>
  </div>
</section>

<!-- SERVIDOR -->
<section id="servidor">
  <h2 class="section-title reveal">Nosso <span>Servidor</span></h2>
  <div class="section-divider reveal"></div>

  <div class="server-box reveal">
    <p>
      Todas as compras são realizadas exclusivamente dentro do nosso servidor Discord oficial.
      Lá você encontra suporte, feedbacks de clientes e os melhores preços do mercado!
    </p>
    <span class="server-link">discord.gg/C8twuEHbzs</span>
    <a class="btn-primary" href="https://discord.gg/C8twuEHbzs" target="_blank" rel="noopener noreferrer">
      Entrar no Servidor
    </a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  © 2025 <span>Rumble Dash</span> — Todos os direitos reservados.
  Desenvolvido com 💜 para a melhor loja do Roblox.
</footer>

<script>
/* ============================================
   ANTI-TAMPER / BASIC SECURITY LAYER
   ============================================ */
(function() {
  'use strict';

  // Disable right-click
  document.addEventListener('contextmenu', e => e.preventDefault());

  // Disable common devtools shortcuts
  document.addEventListener('keydown', e => {
    if (
      e.key === 'F12' ||
      (e.ctrlKey && e.shiftKey && ['I','J','C','U'].includes(e.key.toUpperCase())) ||
      (e.ctrlKey && e.key.toUpperCase() === 'U')
    ) {
      e.preventDefault();
      return false;
    }
  });

  // Console warning
  const style = 'color:#9b30ff;font-size:20px;font-weight:bold;';
  console.log('%c⚠️ RUMBLE DASH — ÁREA RESTRITA', style);
  console.log('%cSe alguém mandou você abrir isso, pode ser uma tentativa de fraude!', 'color:#ff4466;font-size:13px;');

  // Detect devtools open via size difference
  let devtoolsOpen = false;
  setInterval(() => {
    const threshold = 160;
    const widthDiff = window.outerWidth - window.innerWidth > threshold;
    const heightDiff = window.outerHeight - window.innerHeight > threshold;
    if ((widthDiff || heightDiff) && !devtoolsOpen) {
      devtoolsOpen = true;
    }
  }, 1000);

  // Block drag of images
  document.addEventListener('dragstart', e => e.preventDefault());

})();

/* ============================================
   PARTICLES
   ============================================ */
(function() {
  const canvas = document.getElementById('particles');
  const ctx = canvas.getContext('2d');
  let particles = [];
  const NUM = 55;

  function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }

  resize();
  window.addEventListener('resize', resize);

  for (let i = 0; i < NUM; i++) {
    particles.push({
      x: Math.random() * window.innerWidth,
      y: Math.random() * window.innerHeight,
      r: Math.random() * 1.8 + 0.4,
      dx: (Math.random() - 0.5) * 0.4,
      dy: (Math.random() - 0.5) * 0.4,
      opacity: Math.random() * 0.5 + 0.1,
    });
  }

  function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    particles.forEach(p => {
      ctx.beginPath();
      ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(155, 48, 255, ${p.opacity})`;
      ctx.fill();
      p.x += p.dx; p.y += p.dy;
      if (p.x < 0) p.x = canvas.width;
      if (p.x > canvas.width) p.x = 0;
      if (p.y < 0) p.y = canvas.height;
      if (p.y > canvas.height) p.y = 0;
    });
    requestAnimationFrame(draw);
  }

  draw();
})();

/* ============================================
   COUPON MODAL
   ============================================ */
(function() {
  const btn = document.getElementById('couponBtn');
  const overlay = document.getElementById('couponModal');
  const closeBtn = document.getElementById('modalClose');

  btn.addEventListener('click', () => {
    overlay.classList.add('open');
    document.body.style.overflow = 'hidden';
  });

  function closeModal() {
    overlay.classList.remove('open');
    document.body.style.overflow = '';
  }

  closeBtn.addEventListener('click', closeModal);
  overlay.addEventListener('click', e => {
    if (e.target === overlay) closeModal();
  });
  document.addEventListener('keydown', e => {
    if (e.key === 'Escape') closeModal();
  });
})();

/* ============================================
   FAQ ACCORDION
   ============================================ */
(function() {
  document.querySelectorAll('.faq-question').forEach(btn => {
    btn.addEventListener('click', () => {
      const item = btn.closest('.faq-item');
      const isOpen = item.classList.contains('open');
      document.querySelectorAll('.faq-item').forEach(i => i.classList.remove('open'));
      if (!isOpen) item.classList.add('open');
    });
  });
})();

/* ============================================
   SCROLL REVEAL
   ============================================ */
(function() {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
    });
  }, { threshold: 0.12 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
})();

/* ============================================
   ACTIVE NAV LINK
   ============================================ */
(function() {
  const sections = document.querySelectorAll('section[id]');
  const links = document.querySelectorAll('.nav-links a');

  const obs = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        links.forEach(l => l.classList.remove('active'));
        const active = document.querySelector(`.nav-links a[href="#${entry.target.id}"]`);
        if (active) active.classList.add('active');
      }
    });
  }, { threshold: 0.5 });

  sections.forEach(s => obs.observe(s));
})();
</script>
</body>
</html>
