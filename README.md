<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Wiggly Learner – Coming Soon!</title>
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@600;700;800&family=Nunito:ital,wght@0,400;0,600;0,700;1,400&display=swap" rel="stylesheet">
<style>
  :root {
    --green:  #3dab6b;
    --green2: #2d8f55;
    --coral:  #f4845f;
    --gold:   #f0a500;
    --cream:  #fffbf5;
    --tan:    #f5ede0;
    --dark:   #2d2a26;
    --muted:  #9a8f85;
  }

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
font-family: ‘Nunito’, sans-serif;
background: var(–cream);
color: var(–dark);
overflow-x: hidden;
}

/* ── BACKGROUND DOODLES ── */
.bg-doodles {
position: fixed;
inset: 0;
pointer-events: none;
z-index: 0;
overflow: hidden;
}
.bg-doodles svg {
position: absolute;
opacity: 0.07;
}

/* ── COMING SOON BANNER ── */
.banner {
background: var(–coral);
color: white;
text-align: center;
padding: 10px 20px;
font-family: ‘Baloo 2’, cursive;
font-size: 15px;
font-weight: 700;
letter-spacing: 0.08em;
position: relative;
z-index: 10;
animation: bannerSlide 0.6s ease both;
}
.banner span { margin: 0 10px; opacity: 0.7; }
@keyframes bannerSlide {
from { transform: translateY(-100%); opacity: 0; }
to   { transform: translateY(0);     opacity: 1; }
}

/* ── HERO ── */
.hero {
position: relative;
z-index: 1;
display: flex;
flex-direction: column;
align-items: center;
padding: 60px 24px 40px;
text-align: center;
}

/* wavy top divider */
.wave-top {
width: 100%;
overflow: hidden;
line-height: 0;
margin-bottom: -2px;
}

/* ── LOGO ANIMATION (from original) ── */
@keyframes wiggle {
0%,100% { transform: rotate(-4deg) translateY(0px); }
25%      { transform: rotate(4deg)  translateY(-3px); }
50%      { transform: rotate(-3deg) translateY(2px); }
75%      { transform: rotate(3deg)  translateY(-2px); }
}
@keyframes blink {
0%,90%,100% { transform: scaleY(1); }
95%         { transform: scaleY(0.1); }
}
@keyframes float {
0%,100% { transform: translateY(0); }
50%     { transform: translateY(-8px); }
}
@keyframes pencilWrite {
0%,100% { transform: rotate(-15deg) translate(0,0); }
50%     { transform: rotate(-10deg) translate(3px, 2px); }
}
@keyframes starPop {
0%,100% { transform: scale(1) rotate(0deg); }
50%     { transform: scale(1.35) rotate(20deg); }
}
@keyframes fadeUp {
from { opacity: 0; transform: translateY(28px); }
to   { opacity: 1; transform: translateY(0); }
}

.worm-group { animation: float 3s ease-in-out infinite; }
.worm-body  { animation: wiggle 1.8s ease-in-out infinite; transform-origin: 60px 60px; }
.eye-lid    { animation: blink 4s ease-in-out infinite; transform-origin: center; }
.pencil     { animation: pencilWrite 2.5s ease-in-out infinite; transform-origin: 90px 30px; }
.star1      { animation: starPop 2.1s ease-in-out infinite; }
.star2      { animation: starPop 2.1s 0.7s ease-in-out infinite; }
.star3      { animation: starPop 2.1s 1.4s ease-in-out infinite; }

.logo-svg {
filter: drop-shadow(0 12px 28px rgba(61,171,107,0.18));
animation: fadeUp 0.8s 0.2s ease both;
}

/* ── WORDMARK ── */
.wordmark {
font-family: ‘Baloo 2’, cursive;
font-weight: 800;
font-size: clamp(36px, 8vw, 64px);
line-height: 1;
animation: fadeUp 0.8s 0.4s ease both;
margin-top: 8px;
}
.wordmark .the    { color: var(–coral); font-size: 0.55em; display: block; font-weight: 700; letter-spacing: 0.1em; }
.wordmark .wiggly { color: var(–green); }
.wordmark .learner{ color: var(–gold); }

.tagline {
font-size: clamp(13px, 2.5vw, 16px);
color: var(–muted);
letter-spacing: 0.14em;
text-transform: uppercase;
margin-top: 6px;
animation: fadeUp 0.8s 0.55s ease both;
}

/* ── DESCRIPTION CARD ── */
.description {
position: relative;
z-index: 1;
max-width: 680px;
margin: 0 auto;
padding: 0 24px 48px;
animation: fadeUp 0.8s 0.65s ease both;
}

.desc-card {
background: white;
border-radius: 24px;
padding: 36px 40px;
box-shadow: 0 6px 40px rgba(0,0,0,0.06);
border: 2px solid var(–tan);
position: relative;
}
.desc-card::before {
content: ‘✏️’;
position: absolute;
top: -18px;
left: 36px;
font-size: 28px;
}

.desc-card h2 {
font-family: ‘Baloo 2’, cursive;
font-size: clamp(20px, 4vw, 26px);
color: var(–green);
margin-bottom: 12px;
}
.desc-card p {
font-size: 16px;
line-height: 1.75;
color: #5a5550;
margin-bottom: 12px;
}
.desc-card p:last-child { margin-bottom: 0; }

.pill-list {
display: flex;
flex-wrap: wrap;
gap: 8px;
margin-top: 16px;
}
.pill {
background: var(–tan);
border-radius: 999px;
padding: 5px 14px;
font-size: 13px;
font-weight: 700;
color: var(–dark);
}
.pill.green  { background: #e2f5ea; color: var(–green2); }
.pill.coral  { background: #fdeee8; color: #c45c38; }
.pill.gold   { background: #fef3dc; color: #b07a00; }

/* ── EMAIL SECTION ── */
.email-section {
position: relative;
z-index: 1;
background: var(–green);
padding: 60px 24px;
text-align: center;
clip-path: polygon(0 5%, 100% 0%, 100% 95%, 0% 100%);
margin: 8px 0;
}

.email-section h2 {
font-family: ‘Baloo 2’, cursive;
font-size: clamp(22px, 5vw, 32px);
color: white;
margin-bottom: 8px;
}
.email-section p {
color: rgba(255,255,255,0.85);
font-size: 15px;
margin-bottom: 28px;
max-width: 460px;
margin-left: auto;
margin-right: auto;
}

.email-form {
display: flex;
gap: 0;
max-width: 460px;
margin: 0 auto;
border-radius: 999px;
overflow: hidden;
box-shadow: 0 8px 30px rgba(0,0,0,0.15);
}
.email-form input[type=“email”] {
flex: 1;
border: none;
padding: 16px 22px;
font-family: ‘Nunito’, sans-serif;
font-size: 15px;
background: white;
color: var(–dark);
outline: none;
}
.email-form input[type=“email”]::placeholder { color: #bbb; }
.email-form button {
background: var(–coral);
color: white;
border: none;
padding: 16px 26px;
font-family: ‘Baloo 2’, cursive;
font-size: 15px;
font-weight: 700;
cursor: pointer;
transition: background 0.2s, transform 0.15s;
white-space: nowrap;
}
.email-form button:hover { background: #e06d48; transform: scale(1.04); }

.email-note {
color: rgba(255,255,255,0.6);
font-size: 12px;
margin-top: 12px;
}

/* success state */
.success-msg {
display: none;
background: white;
color: var(–green2);
border-radius: 999px;
padding: 16px 28px;
font-family: ‘Baloo 2’, cursive;
font-size: 17px;
font-weight: 700;
max-width: 460px;
margin: 0 auto;
box-shadow: 0 8px 30px rgba(0,0,0,0.12);
}

/* ── ETSY CTA ── */
.etsy-section {
position: relative;
z-index: 1;
text-align: center;
padding: 56px 24px 72px;
animation: fadeUp 0.8s 0.9s ease both;
}
.etsy-section h2 {
font-family: ‘Baloo 2’, cursive;
font-size: clamp(20px, 4vw, 28px);
color: var(–dark);
margin-bottom: 8px;
}
.etsy-section p {
color: var(–muted);
font-size: 15px;
margin-bottom: 28px;
}

.etsy-btn {
display: inline-flex;
align-items: center;
gap: 10px;
background: #f1641e;
color: white;
text-decoration: none;
font-family: ‘Baloo 2’, cursive;
font-size: 18px;
font-weight: 700;
padding: 16px 36px;
border-radius: 999px;
box-shadow: 0 8px 28px rgba(241,100,30,0.35);
transition: transform 0.2s, box-shadow 0.2s;
}
.etsy-btn:hover {
transform: translateY(-3px) scale(1.03);
box-shadow: 0 14px 36px rgba(241,100,30,0.4);
}
.etsy-btn svg { width: 22px; height: 22px; }

/* ── FOOTER ── */
footer {
position: relative;
z-index: 1;
background: var(–dark);
color: rgba(255,255,255,0.45);
text-align: center;
padding: 24px 20px;
font-size: 13px;
}
footer a { color: var(–coral); text-decoration: none; }

/* ── FLOATING DOODLE ELEMENTS ── */
.doodle {
position: fixed;
pointer-events: none;
opacity: 0.09;
z-index: 0;
font-size: 48px;
}
.d1 { top: 12%; left: 4%;  animation: float 4s 0s ease-in-out infinite; }
.d2 { top: 30%; right: 3%; animation: float 4s 1s ease-in-out infinite; }
.d3 { top: 65%; left: 6%;  animation: float 4s 2s ease-in-out infinite; }
.d4 { top: 78%; right: 5%; animation: float 4s 0.5s ease-in-out infinite; }

@media (max-width: 520px) {
.desc-card { padding: 28px 22px; }
.email-form { flex-direction: column; border-radius: 16px; }
.email-form button { border-radius: 0 0 16px 16px; }
.email-form input[type=“email”] { border-radius: 16px 16px 0 0; }
}
</style>

</head>
<body>

<!-- Floating background doodles -->

<div class="doodle d1">📚</div>
<div class="doodle d2">⭐</div>
<div class="doodle d3">✏️</div>
<div class="doodle d4">🌿</div>

<!-- COMING SOON BANNER -->

<div class="banner">
  🎉 Something wonderful is on its way! <span>•</span> Full website coming soon <span>•</span> Shop open on Etsy now! 🎉
</div>

<!-- HERO -->

<section class="hero">

  <!-- Animated Logo SVG -->

  <svg class="logo-svg" width="200" height="165" viewBox="0 0 160 130" fill="none" xmlns="http://www.w3.org/2000/svg">
    <g opacity="0.15">
      <ellipse cx="80" cy="118" rx="52" ry="8" fill="#3dab6b"/>
    </g>
    <rect x="30" y="88" width="46" height="30" rx="3" fill="#ffe9c8" stroke="#f0a500" stroke-width="1.5"/>
    <rect x="84" y="88" width="46" height="30" rx="3" fill="#ffe9c8" stroke="#f0a500" stroke-width="1.5"/>
    <rect x="76" y="86" width="8" height="34" rx="4" fill="#f0a500"/>
    <line x1="36" y1="97" x2="70" y2="97" stroke="#f0a500" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/>
    <line x1="36" y1="103" x2="70" y2="103" stroke="#f0a500" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/>
    <line x1="36" y1="109" x2="70" y2="109" stroke="#f0a500" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/>
    <line x1="90" y1="97" x2="124" y2="97" stroke="#f0a500" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/>
    <line x1="90" y1="103" x2="124" y2="103" stroke="#f0a500" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/>
    <line x1="90" y1="109" x2="124" y2="109" stroke="#f0a500" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/>
    <g class="pencil">
      <rect x="98" y="18" width="9" height="52" rx="2" fill="#f4845f" transform="rotate(-15 98 18)"/>
      <polygon points="98,68 107,68 102.5,80" fill="#ffe9c8" transform="rotate(-15 102.5 68)"/>
      <rect x="98" y="18" width="9" height="7" rx="2" fill="#f7c59f" transform="rotate(-15 98 18)"/>
      <circle cx="94" cy="83" r="2" fill="#2d2a26" transform="rotate(-15 94 83)"/>
    </g>
    <g class="worm-group">
      <g class="worm-body">
        <ellipse cx="60" cy="80" rx="14" ry="10" fill="#3dab6b"/>
        <ellipse cx="50" cy="72" rx="12" ry="10" fill="#3dab6b"/>
        <ellipse cx="44" cy="62" rx="11" ry="10" fill="#3dab6b"/>
        <circle cx="44" cy="50" r="16" fill="#3dab6b"/>
        <ellipse cx="36" cy="54" rx="5" ry="3.5" fill="#f4845f" opacity="0.35"/>
        <ellipse cx="52" cy="54" rx="5" ry="3.5" fill="#f4845f" opacity="0.35"/>
        <circle cx="38" cy="47" r="5" fill="white"/>
        <circle cx="50" cy="47" r="5" fill="white"/>
        <circle cx="39" cy="47" r="2.5" fill="#2d2a26"/>
        <circle cx="51" cy="47" r="2.5" fill="#2d2a26"/>
        <circle cx="40" cy="46" r="1" fill="white"/>
        <circle cx="52" cy="46" r="1" fill="white"/>
        <g class="eye-lid">
          <rect x="33" y="42" width="10" height="5" rx="3" fill="#3dab6b"/>
          <rect x="45" y="42" width="10" height="5" rx="3" fill="#3dab6b"/>
        </g>
        <path d="M 37 55 Q 44 61 51 55" stroke="#2d2a26" stroke-width="2" stroke-linecap="round" fill="none"/>
        <line x1="38" y1="34" x2="32" y2="22" stroke="#3dab6b" stroke-width="2.5" stroke-linecap="round"/>
        <line x1="50" y1="34" x2="56" y2="22" stroke="#3dab6b" stroke-width="2.5" stroke-linecap="round"/>
        <circle cx="32" cy="20" r="4" fill="#f4845f"/>
        <circle cx="56" cy="20" r="4" fill="#f0a500"/>
      </g>
    </g>
    <g class="star1">
      <path d="M130 30 L132 36 L138 36 L133 40 L135 46 L130 42 L125 46 L127 40 L122 36 L128 36 Z" fill="#f0a500"/>
    </g>
    <g class="star2">
      <path d="M22 30 L23.5 34 L28 34 L24.5 37 L26 41 L22 38 L18 41 L19.5 37 L16 34 L20.5 34 Z" fill="#f4845f"/>
    </g>
    <g class="star3">
      <path d="M140 72 L141 75 L144 75 L142 77 L143 80 L140 78 L137 80 L138 77 L136 75 L139 75 Z" fill="#3dab6b"/>
    </g>
  </svg>

  <div class="wordmark">
    <span class="the">The</span>
    <span class="wiggly">Wiggly</span><span class="learner">Learner</span>
  </div>
  <p class="tagline">Printable worksheets for every kind of mind</p>
</section>

<!-- DESCRIPTION CARD -->

<section class="description">
  <div class="desc-card">
    <h2>Learning that fits your child — not the other way around 💛</h2>
    <p>
      Hi! I'm so glad you found us. The Wiggly Learner is a cozy corner of the internet made for the kids who learn differently — the wigglers, the dreamers, the ones who need a little more color, a little more movement, and a whole lot of encouragement.
    </p>
    <p>
      I create <strong>fun, printable worksheets</strong> designed with kids ages 5–9 in mind — especially those with ADHD, sensory differences, or who just don't thrive in traditional classroom settings. Think short bursts of learning, playful visuals, and pages that actually make your kid want to sit down and try.
    </p>
    <p>
      Whether you're a homeschool mama looking for your next morning routine staple or just need something that works — you're in the right place. 🌿
    </p>
    <div class="pill-list">
      <span class="pill green">✓ ADHD-friendly</span>
      <span class="pill green">✓ K–3 Grades</span>
      <span class="pill coral">✓ Instant Download</span>
      <span class="pill coral">✓ Printable PDFs</span>
      <span class="pill gold">✓ Homeschool-ready</span>
      <span class="pill gold">✓ Subscription coming soon</span>
    </div>
  </div>
</section>

<!-- EMAIL SIGNUP -->

<section class="email-section">
  <h2>🌟 Be the first to know!</h2>
  <p>Join our list for early access, freebies, and updates when our full worksheet library launches.</p>

  <div class="email-form" id="emailForm">
    <input type="email" id="emailInput" placeholder="yourname@email.com" autocomplete="email"/>
    <button onclick="handleSignup()">Count me in! 🎉</button>
  </div>
  <div class="success-msg" id="successMsg">
    🎊 Yay! You're on the list — talk soon!
  </div>
  <p class="email-note">No spam, ever. Just good stuff for your homeschool journey. 💌</p>
</section>

<!-- ETSY CTA -->

<section class="etsy-section">
  <h2>Shop is open on Etsy! 🛍️</h2>
  <p>Grab our first worksheets while the full website is on its way.</p>
  <a href="https://www.etsy.com/shop/TheWigglyLearner" target="_blank" rel="noopener" class="etsy-btn">
    <!-- Etsy bag icon -->
    <svg viewBox="0 0 24 24" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
      <path d="M19.5 8.5h-2.25V6.75A5.25 5.25 0 0 0 12 1.5a5.25 5.25 0 0 0-5.25 5.25V8.5H4.5a1.5 1.5 0 0 0-1.5 1.5v10a1.5 1.5 0 0 0 1.5 1.5h15a1.5 1.5 0 0 0 1.5-1.5V10a1.5 1.5 0 0 0-1.5-1.5zM8.5 6.75a3.5 3.5 0 0 1 7 0V8.5h-7V6.75zM12 16a2 2 0 1 1 0-4 2 2 0 0 1 0 4z"/>
    </svg>
    Visit Our Etsy Shop
  </a>
</section>

<!-- FOOTER -->

<footer>
  <p>© 2025 The Wiggly Learner &nbsp;·&nbsp; Made with 💚 for wiggly kids everywhere &nbsp;·&nbsp;
    <a href="https://www.etsy.com/shop/TheWigglyLearner" target="_blank">Etsy Shop</a>
  </p>
</footer>

<script>
  function handleSignup() {
    const input = document.getElementById('emailInput');
    const form  = document.getElementById('emailForm');
    const msg   = document.getElementById('successMsg');
    const email = input.value.trim();
    const valid = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);

    if (!valid) {
      input.style.outline = '3px solid #f4845f';
      input.focus();
      setTimeout(() => input.style.outline = '', 1800);
      return;
    }

    // In production, replace this with your email service (Mailchimp, ConvertKit, etc.)
    form.style.display  = 'none';
    msg.style.display   = 'block';
    console.log('Email captured:', email);
  }

  // Allow Enter key to submit
  document.getElementById('emailInput').addEventListener('keydown', function(e) {
    if (e.key === 'Enter') handleSignup();
  });
</script>

</body>
</html>
