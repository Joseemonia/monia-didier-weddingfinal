<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Monia & Didier — Wedding Invitation · 26 July 2026</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400;1,500&family=Montserrat:wght@300;400;500;600&family=Great+Vibes&display=swap" rel="stylesheet"/>
<style>
  :root {
    --blush: #f2ddd5;
    --rose: #c9897a;
    --gold: #b8955a;
    --cream: #fdf8f4;
    --dark: #2c1f1a;
    --warm-gray: #8a7570;
    --petal: #f7ece8;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--cream);
    color: var(--dark);
    font-family: 'Montserrat', sans-serif;
    overflow-x: hidden;
  }

  /* ── PETALS ── */
  .petal-container {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }

  .petal {
    position: absolute;
    top: -60px;
    width: 18px;
    height: 22px;
    background: radial-gradient(ellipse at 40% 30%, #f5c6b8 0%, #e8a090 60%, #d4887a 100%);
    border-radius: 60% 40% 70% 30% / 50% 60% 40% 50%;
    opacity: 0.55;
    animation: petalFall linear infinite;
  }

  @keyframes petalFall {
    0%   { transform: translateY(0) rotate(0deg) translateX(0); opacity: 0; }
    10%  { opacity: 0.55; }
    90%  { opacity: 0.4; }
    100% { transform: translateY(110vh) rotate(360deg) translateX(80px); opacity: 0; }
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 60px 20px;
    background: linear-gradient(160deg, #fdf8f4 0%, #f7ece8 40%, #f2ddd5 100%);
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 40% at 20% 80%, rgba(201,137,122,0.12) 0%, transparent 70%),
      radial-gradient(ellipse 50% 50% at 80% 20%, rgba(184,149,90,0.10) 0%, transparent 70%);
  }

  .hero-border {
    position: absolute;
    inset: 20px;
    border: 1px solid rgba(184,149,90,0.3);
    border-radius: 2px;
    pointer-events: none;
  }
  .hero-border::before {
    content: '';
    position: absolute;
    inset: 6px;
    border: 1px solid rgba(184,149,90,0.15);
    border-radius: 2px;
  }

  .hero-content { position: relative; z-index: 1; }

  .we-are-getting-married {
    font-family: 'Montserrat', sans-serif;
    font-size: 0.65rem;
    font-weight: 600;
    letter-spacing: 0.35em;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 28px;
    opacity: 0;
    animation: fadeUp 1s 0.3s forwards;
  }

  .hero-names {
    font-family: 'Great Vibes', cursive;
    font-size: clamp(4rem, 12vw, 9rem);
    color: var(--dark);
    line-height: 1.1;
    opacity: 0;
    animation: fadeUp 1.2s 0.6s forwards;
  }

  .hero-ampersand {
    color: var(--rose);
  }

  .hero-divider {
    display: flex;
    align-items: center;
    gap: 16px;
    margin: 28px auto;
    width: 280px;
    opacity: 0;
    animation: fadeUp 1s 0.9s forwards;
  }

  .hero-divider-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
  }

  .hero-divider-ornament {
    color: var(--gold);
    font-size: 1rem;
  }

  .hero-date {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(1rem, 3vw, 1.4rem);
    font-weight: 300;
    letter-spacing: 0.25em;
    color: var(--warm-gray);
    opacity: 0;
    animation: fadeUp 1s 1.1s forwards;
  }

  .hero-location {
    font-family: 'Montserrat', sans-serif;
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.3em;
    color: var(--rose);
    text-transform: uppercase;
    margin-top: 10px;
    opacity: 0;
    animation: fadeUp 1s 1.3s forwards;
  }

  .hero-hashtag {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1rem;
    font-style: italic;
    color: var(--gold);
    margin-top: 32px;
    opacity: 0;
    animation: fadeUp 1s 1.5s forwards;
  }

  .scroll-cue {
    position: absolute;
    bottom: 36px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
    opacity: 0;
    animation: fadeUp 1s 2s forwards;
  }

  .scroll-cue span {
    font-size: 0.6rem;
    letter-spacing: 0.25em;
    color: var(--warm-gray);
    text-transform: uppercase;
  }

  .scroll-line {
    width: 1px;
    height: 40px;
    background: linear-gradient(to bottom, var(--gold), transparent);
    animation: scrollPulse 2s ease-in-out infinite;
  }

  @keyframes scrollPulse {
    0%, 100% { opacity: 0.4; transform: scaleY(1); }
    50% { opacity: 1; transform: scaleY(1.1); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ── SECTIONS ── */
  section {
    position: relative;
    padding: 90px 20px;
  }

  .section-inner {
    max-width: 780px;
    margin: 0 auto;
    text-align: center;
  }

  .section-label {
    font-size: 0.6rem;
    font-weight: 600;
    letter-spacing: 0.4em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 16px;
  }

  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 300;
    color: var(--dark);
    margin-bottom: 24px;
    line-height: 1.2;
  }

  .section-title em {
    color: var(--rose);
    font-style: italic;
  }

  .divider-ornament {
    display: flex;
    align-items: center;
    gap: 12px;
    justify-content: center;
    margin: 20px auto 36px;
  }

  .divider-ornament-line {
    width: 80px;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--gold));
  }

  .divider-ornament-line.r {
    background: linear-gradient(90deg, var(--gold), transparent);
  }

  .divider-ornament-icon { color: var(--gold); font-size: 0.9rem; }

  /* ── INVITATION TEXT ── */
  .invite-section {
    background: var(--cream);
  }

  .invite-card {
    background: white;
    border: 1px solid rgba(184,149,90,0.2);
    padding: 56px 48px;
    position: relative;
    max-width: 600px;
    margin: 0 auto;
    box-shadow: 0 8px 40px rgba(44,31,26,0.06);
  }

  .invite-card::before {
    content: '';
    position: absolute;
    inset: 8px;
    border: 1px solid rgba(184,149,90,0.1);
    pointer-events: none;
  }

  .invite-card p {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.15rem;
    font-weight: 300;
    line-height: 1.9;
    color: var(--warm-gray);
  }

  .invite-card p strong {
    color: var(--dark);
    font-weight: 500;
  }

  .invite-card .couple-names {
    font-family: 'Great Vibes', cursive;
    font-size: 2.8rem;
    color: var(--rose);
    display: block;
    margin: 16px 0;
    line-height: 1.2;
  }

  /* ── COUNTDOWN ── */
  .countdown-section {
    background: linear-gradient(135deg, #2c1f1a 0%, #3d2b24 100%);
    color: white;
  }

  .countdown-section .section-title { color: white; }
  .countdown-section .section-label { color: var(--gold); }

  .countdown-grid {
    display: flex;
    gap: 24px;
    justify-content: center;
    flex-wrap: wrap;
    margin-top: 40px;
  }

  .countdown-item {
    text-align: center;
    min-width: 90px;
  }

  .countdown-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3rem, 8vw, 5rem);
    font-weight: 300;
    color: var(--gold);
    line-height: 1;
    display: block;
  }

  .countdown-label {
    font-size: 0.6rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.5);
    margin-top: 8px;
    display: block;
  }

  .countdown-separator {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3rem;
    color: var(--rose);
    align-self: flex-start;
    padding-top: 16px;
  }

  /* ── SCHEDULE ── */
  .schedule-section { background: var(--petal); }

  .timeline {
    position: relative;
    max-width: 500px;
    margin: 0 auto;
    padding: 0 20px;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 50%;
    top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, transparent, var(--gold) 20%, var(--gold) 80%, transparent);
    transform: translateX(-50%);
  }

  .timeline-item {
    display: flex;
    align-items: flex-start;
    margin-bottom: 48px;
    position: relative;
  }

  .timeline-item:nth-child(odd) { flex-direction: row-reverse; }

  .timeline-item:nth-child(odd) .timeline-content { text-align: right; }

  .timeline-dot {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: var(--gold);
    border: 3px solid var(--cream);
    box-shadow: 0 0 0 1px var(--gold);
    z-index: 1;
    top: 4px;
  }

  .timeline-content {
    width: calc(50% - 24px);
    padding: 0 16px;
  }

  .timeline-time {
    font-size: 0.6rem;
    letter-spacing: 0.25em;
    color: var(--gold);
    text-transform: uppercase;
    font-weight: 600;
    margin-bottom: 4px;
  }

  .timeline-event {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.15rem;
    color: var(--dark);
    font-weight: 500;
  }

  .timeline-desc {
    font-size: 0.72rem;
    color: var(--warm-gray);
    margin-top: 2px;
    line-height: 1.6;
  }

  /* ── VENUES ── */
  .venues-section { background: var(--cream); }

  .venues-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 32px;
    max-width: 700px;
    margin: 0 auto;
  }

  @media (max-width: 600px) {
    .venues-grid { grid-template-columns: 1fr; }
  }

  .venue-card {
    border: 1px solid rgba(184,149,90,0.25);
    padding: 36px 28px;
    position: relative;
    background: white;
    box-shadow: 0 4px 24px rgba(44,31,26,0.05);
    transition: transform 0.3s, box-shadow 0.3s;
  }

  .venue-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 12px 40px rgba(44,31,26,0.1);
  }

  .venue-icon {
    font-size: 1.8rem;
    margin-bottom: 16px;
    display: block;
  }

  .venue-type {
    font-size: 0.58rem;
    letter-spacing: 0.35em;
    text-transform: uppercase;
    color: var(--gold);
    font-weight: 600;
    margin-bottom: 8px;
  }

  .venue-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.2rem;
    color: var(--dark);
    font-weight: 500;
    line-height: 1.3;
    margin-bottom: 8px;
  }

  .venue-address {
    font-size: 0.72rem;
    color: var(--warm-gray);
    line-height: 1.6;
  }

  .venue-map-link {
    display: inline-block;
    margin-top: 16px;
    font-size: 0.62rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--rose);
    text-decoration: none;
    border-bottom: 1px solid rgba(201,137,122,0.3);
    padding-bottom: 2px;
    transition: color 0.2s, border-color 0.2s;
  }

  .venue-map-link:hover { color: var(--gold); border-color: var(--gold); }

  /* ── RSVP ── */
  .rsvp-section {
    background: linear-gradient(160deg, #f7ece8 0%, #f2ddd5 100%);
  }

  .rsvp-text {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.1rem;
    color: var(--warm-gray);
    line-height: 1.9;
    margin-bottom: 36px;
    font-weight: 300;
  }

  .rsvp-btn {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: #25D366;
    color: white;
    text-decoration: none;
    padding: 16px 36px;
    font-family: 'Montserrat', sans-serif;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    border-radius: 2px;
    transition: background 0.3s, transform 0.2s, box-shadow 0.3s;
    box-shadow: 0 4px 20px rgba(37,211,102,0.3);
  }

  .rsvp-btn:hover {
    background: #1db954;
    transform: translateY(-2px);
    box-shadow: 0 8px 30px rgba(37,211,102,0.4);
  }

  .rsvp-deadline {
    margin-top: 20px;
    font-size: 0.65rem;
    color: var(--warm-gray);
    letter-spacing: 0.15em;
  }

  /* ── FOOTER ── */
  footer {
    background: var(--dark);
    color: white;
    text-align: center;
    padding: 64px 20px;
  }

  footer .footer-names {
    font-family: 'Great Vibes', cursive;
    font-size: 3.5rem;
    color: var(--gold);
    margin-bottom: 8px;
  }

  footer .footer-hashtag {
    font-family: 'Cormorant Garamond', serif;
    font-style: italic;
    color: rgba(255,255,255,0.4);
    font-size: 0.9rem;
    letter-spacing: 0.15em;
  }

  footer .footer-date {
    font-size: 0.6rem;
    letter-spacing: 0.35em;
    color: rgba(255,255,255,0.25);
    text-transform: uppercase;
    margin-top: 16px;
  }

  /* ── SCROLL REVEAL ── */
  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.8s ease, transform 0.8s ease;
  }

  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 500px) {
    .invite-card { padding: 36px 24px; }
    .timeline::before { left: 20px; }
    .timeline-item, .timeline-item:nth-child(odd) { flex-direction: column; padding-left: 50px; }
    .timeline-item:nth-child(odd) .timeline-content { text-align: left; }
    .timeline-dot { left: 20px; }
    .timeline-content { width: 100%; }
    .countdown-separator { display: none; }
  }
</style>
</head>
<body>

<!-- Falling petals -->
<div class="petal-container" id="petals"></div>

<!-- ══ HERO ══ -->
<section class="hero">
  <div class="hero-border"></div>
  <div class="hero-content">
    <p class="we-are-getting-married">We are getting married</p>
    <h1 class="hero-names">
      Monia <span class="hero-ampersand">&</span> Didier
    </h1>
    <div class="hero-divider">
      <div class="hero-divider-line"></div>
      <span class="hero-divider-ornament">✦</span>
      <div class="hero-divider-line"></div>
    </div>
    <p class="hero-date">26/07/2026</p>
    <p class="hero-location">Kigali, Rwanda</p>
    <p class="hero-hashtag">#DM4EVER</p>
  </div>
  <div class="scroll-cue">
    <span>Scroll</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- ══ INVITATION TEXT ══ -->
<section class="invite-section">
  <div class="section-inner reveal">
    <p class="section-label">With joy in our hearts</p>
    <h2 class="section-title">You are <em>Invited</em></h2>
    <div class="divider-ornament">
      <div class="divider-ornament-line"></div>
      <span class="divider-ornament-icon">❦</span>
      <div class="divider-ornament-line r"></div>
    </div>
    <div class="invite-card">
      <p>
        Together with their families, we joyfully invite you to celebrate the marriage of<br/>
        <span class="couple-names">Monia & Didier</span>
        as they begin their journey as one.<br/><br/>
        Your presence would be the greatest gift — please join us for a day filled with love, laughter, and lifelong memories.
      </p>
    </div>
  </div>
</section>

<!-- ══ COUNTDOWN ══ -->
<section class="countdown-section">
  <div class="section-inner reveal">
    <p class="section-label">Counting down to forever</p>
    <h2 class="section-title">The Big Day</h2>
    <div class="countdown-grid">
      <div class="countdown-item">
        <span class="countdown-number" id="cd-days">—</span>
        <span class="countdown-label">Days</span>
      </div>
      <span class="countdown-separator">:</span>
      <div class="countdown-item">
        <span class="countdown-number" id="cd-hours">—</span>
        <span class="countdown-label">Hours</span>
      </div>
      <span class="countdown-separator">:</span>
      <div class="countdown-item">
        <span class="countdown-number" id="cd-minutes">—</span>
        <span class="countdown-label">Minutes</span>
      </div>
      <span class="countdown-separator">:</span>
      <div class="countdown-item">
        <span class="countdown-number" id="cd-seconds">—</span>
        <span class="countdown-label">Seconds</span>
      </div>
    </div>
  </div>
</section>

<!-- ══ SCHEDULE ══ -->
<section class="schedule-section">
  <div class="section-inner reveal">
    <p class="section-label">The celebration</p>
    <h2 class="section-title">Day <em>Schedule</em></h2>
    <div class="divider-ornament">
      <div class="divider-ornament-line"></div>
      <span class="divider-ornament-icon">✦</span>
      <div class="divider-ornament-line r"></div>
    </div>
    <div class="timeline">
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <p class="timeline-time">9:00 AM</p>
          <p class="timeline-event">Traditional Wedding</p>
        </div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <p class="timeline-time">2:00 PM</p>
          <p class="timeline-event">Church Ceremony</p>
        </div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <p class="timeline-time">5:00 PM</p>
          <p class="timeline-event">Reception</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ══ VENUES ══ -->
<section class="venues-section">
  <div class="section-inner reveal">
    <p class="section-label">Where to find us</p>
    <h2 class="section-title">The <em>Venues</em></h2>
    <div class="divider-ornament">
      <div class="divider-ornament-line"></div>
      <span class="divider-ornament-icon">❦</span>
      <div class="divider-ornament-line r"></div>
    </div>
    <div class="venues-grid">
      <div class="venue-card">
        <p class="venue-type">Traditional Wedding · 9:00 AM</p>
        <p class="venue-name">Amashyo Ground</p>
        <p class="venue-address">Kimironko, Kigali</p>
        <a class="venue-map-link" href="https://maps.google.com/?q=Amashyo+Ground+Kimironko+Kigali" target="_blank">📍 Google Maps</a>
      </div>
      <div class="venue-card">
        <p class="venue-type">Church Ceremony · 2:00 PM</p>
        <p class="venue-name">Chapelle Christus</p>
        <p class="venue-address">Remera, Kigali</p>
        <a class="venue-map-link" href="https://maps.google.com/?q=Chapelle+Christus+Remera+Kigali" target="_blank">📍 Google Maps</a>
      </div>
      <div class="venue-card" style="grid-column: 1 / -1; max-width: 340px; margin: 0 auto;">
        <p class="venue-type">Reception · 5:00 PM</p>
        <p class="venue-name">Amashyo Ground</p>
        <p class="venue-address">Kimironko, Kigali</p>
        <a class="venue-map-link" href="https://maps.google.com/?q=Amashyo+Ground+Kimironko+Kigali" target="_blank">📍 Google Maps</a>
      </div>
    </div>
  </div>
</section>



<!-- ══ FOOTER ══ -->
<footer>
  <p class="footer-names">Monia & Didier</p>
  <p class="footer-hashtag">#DM4EVER</p>
  <p class="footer-date">26/07/2026 · Kigali, Rwanda</p>
</footer>

<script>
  // ── PETALS ──
  const container = document.getElementById('petals');
  for (let i = 0; i < 18; i++) {
    const p = document.createElement('div');
    p.className = 'petal';
    p.style.left = Math.random() * 100 + '%';
    p.style.animationDuration = (8 + Math.random() * 10) + 's';
    p.style.animationDelay = (Math.random() * 12) + 's';
    p.style.width = (12 + Math.random() * 14) + 'px';
    p.style.height = (16 + Math.random() * 16) + 'px';
    p.style.opacity = 0.3 + Math.random() * 0.4;
    container.appendChild(p);
  }

  // ── COUNTDOWN ──
  function updateCountdown() {
    const target = new Date('2026-07-26T10:00:00').getTime();
    const now = new Date().getTime();
    const diff = target - now;
    if (diff <= 0) {
      document.getElementById('cd-days').textContent = '0';
      document.getElementById('cd-hours').textContent = '0';
      document.getElementById('cd-minutes').textContent = '0';
      document.getElementById('cd-seconds').textContent = '0';
      return;
    }
    const d = Math.floor(diff / (1000*60*60*24));
    const h = Math.floor((diff % (1000*60*60*24)) / (1000*60*60));
    const m = Math.floor((diff % (1000*60*60)) / (1000*60));
    const s = Math.floor((diff % (1000*60)) / 1000);
    document.getElementById('cd-days').textContent = String(d).padStart(2,'0');
    document.getElementById('cd-hours').textContent = String(h).padStart(2,'0');
    document.getElementById('cd-minutes').textContent = String(m).padStart(2,'0');
    document.getElementById('cd-seconds').textContent = String(s).padStart(2,'0');
  }
  updateCountdown();
  setInterval(updateCountdown, 1000);

  // ── SCROLL REVEAL ──
  const revealEls = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); }
    });
  }, { threshold: 0.15 });
  revealEls.forEach(el => observer.observe(el));
</script>
</body>
</html>
