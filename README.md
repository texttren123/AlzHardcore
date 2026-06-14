<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
<title>ALZHARDCORE • FASE 4 — RULES</title>

<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #05010a;
  color: #e2e2e2;
  font-family: 'Orbitron', monospace;
  overflow-x: hidden;
  font-smooth: always;
  -webkit-font-smoothing: antialiased;
}

/* GRID DARK VIBE */
body::before {
  content: "";
  position: fixed;
  inset: 0;
  background-image: 
    linear-gradient(rgba(168, 85, 247, 0.07) 1px, transparent 1px),
    linear-gradient(90deg, rgba(168, 85, 247, 0.07) 1px, transparent 1px);
  background-size: 42px 42px;
  pointer-events: none;
  z-index: -3;
}

/* GLOW ORB */
.orb {
  position: fixed;
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, #a855f7, #4a1d8c 70%, transparent 85%);
  filter: blur(100px);
  top: 20%;
  left: 50%;
  transform: translateX(-50%);
  animation: orbFloat 9s ease-in-out infinite;
  z-index: -2;
  opacity: 0.5;
}

@keyframes orbFloat {
  0%, 100% { transform: translateX(-50%) translateY(0px) scale(1); }
  50% { transform: translateX(-50%) translateY(-45px) scale(1.05); }
}

/* LOADING */
#loading {
  position: fixed;
  inset: 0;
  background: #030008;
  backdrop-filter: blur(2px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  z-index: 9999;
  transition: opacity 0.6s cubic-bezier(0.2, 0.9, 0.4, 1.1);
}

.spinner {
  width: 80px;
  height: 80px;
  border: 2px solid rgba(168, 85, 247, 0.2);
  border-top: 3px solid #a855f7;
  border-radius: 50%;
  animation: spin 0.9s linear infinite;
  box-shadow: 0 0 15px rgba(168, 85, 247, 0.5);
}

@keyframes spin { 100% { transform: rotate(360deg); } }

.loading-text {
  margin-top: 24px;
  font-size: 14px;
  letter-spacing: 3px;
  font-variant: small-caps;
  background: linear-gradient(135deg, #c084fc, #a855f7);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-weight: 600;
}

/* NAVIGATION */
nav {
  position: fixed;
  top: 0;
  width: 100%;
  padding: 16px 32px;
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  flex-wrap: wrap;
  background: rgba(3, 1, 10, 0.75);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid rgba(168, 85, 247, 0.35);
  z-index: 1000;
  font-weight: 500;
}

nav h1 {
  font-size: 15px;
  font-variant: small-caps;
  letter-spacing: 2.5px;
  color: #d9a7ff;
  text-shadow: 0 0 6px #a855f7;
}

nav span {
  font-size: 11px;
  font-variant: small-caps;
  background: rgba(168, 85, 247, 0.2);
  padding: 4px 12px;
  border-radius: 40px;
  letter-spacing: 1px;
  border: 0.5px solid rgba(168, 85, 247, 0.5);
  color: #ccc;
}

/* HERO */
header {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 20px;
}

.title {
  font-size: 70px;
  font-weight: 900;
  background: linear-gradient(135deg, #ffffff, #c084fc, #a855f7);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  text-shadow: 0 0 20px rgba(168, 85, 247, 0.6);
  letter-spacing: 6px;
  animation: titleGlow 2.4s infinite alternate;
  margin-bottom: 15px;
}

@keyframes titleGlow {
  0% { text-shadow: 0 0 8px #a855f7; opacity: 0.95; }
  100% { text-shadow: 0 0 35px #c084fc; opacity: 1; }
}

.sub {
  font-variant: small-caps;
  letter-spacing: 2px;
  font-size: 14px;
  color: #bbb9ce;
  background: rgba(0, 0, 0, 0.4);
  backdrop-filter: blur(6px);
  padding: 10px 24px;
  border-radius: 60px;
  border: 0.5px solid rgba(168, 85, 247, 0.4);
}

/* CONTAINER & CARDS */
.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 30px 24px 70px;
}

.card {
  background: rgba(12, 8, 22, 0.55);
  backdrop-filter: blur(14px);
  border: 1px solid rgba(168, 85, 247, 0.3);
  border-radius: 28px;
  padding: 26px 28px;
  margin: 28px 0;
  transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
}

.card:hover {
  transform: translateY(-6px);
  border-color: #b05eff;
  box-shadow: 0 0 28px rgba(168, 85, 247, 0.3);
  background: rgba(18, 10, 32, 0.7);
}

h2 {
  font-size: 20px;
  font-weight: 700;
  font-variant: small-caps;
  letter-spacing: 2px;
  color: #e3b3ff;
  margin-bottom: 22px;
  border-left: 4px solid #a855f7;
  padding-left: 16px;
}

/* RULES STYLING - PRESISI DENGAN SMALLCAPS */
.rule-block {
  margin-bottom: 24px;
}

.rule-title {
  font-variant: small-caps;
  font-weight: 800;
  letter-spacing: 1.5px;
  color: #f0c6ff;
  margin-bottom: 12px;
  font-size: 18px;
  display: flex;
  align-items: center;
  gap: 10px;
  border-bottom: 1px dashed rgba(168,85,247,0.5);
  padding-bottom: 5px;
}

.rule-list {
  list-style: none;
  padding-left: 8px;
}

.rule-list li {
  margin: 12px 0;
  font-size: 14px;
  font-variant: small-caps;
  letter-spacing: 0.4px;
  display: flex;
  align-items: baseline;
  gap: 8px;
  flex-wrap: wrap;
  color: #cfcaff;
}

.rule-list li strong {
  color: #ffd966;
  font-weight: 700;
  font-variant: small-caps;
  min-width: 70px;
}

.bullet {
  color: #c084fc;
  font-weight: bold;
  margin-right: 6px;
}

/* BADGE UNTUK FREE RANK */
.rank-badge {
  background: linear-gradient(145deg, #a855f730, #3b0764);
  padding: 12px 20px;
  border-radius: 60px;
  display: inline-block;
  font-variant: small-caps;
  font-weight: bold;
  margin: 16px 0 10px;
  border: 1px solid #a855f7;
}

/* GATEWAY LINKS */
.link {
  display: block;
  padding: 14px 20px;
  margin: 14px 0;
  border-radius: 40px;
  background: rgba(168, 85, 247, 0.08);
  border: 1px solid rgba(168, 85, 247, 0.45);
  text-decoration: none;
  color: #f2eaff;
  font-variant: small-caps;
  font-weight: 600;
  letter-spacing: 1.2px;
  transition: all 0.25s ease;
  text-align: center;
  backdrop-filter: blur(4px);
}

.link:hover {
  background: #a855f7;
  color: #010101;
  border-color: white;
  transform: scale(1.02);
  box-shadow: 0 6px 18px #a855f780;
}

footer {
  text-align: center;
  padding: 30px 20px 50px;
  font-variant: small-caps;
  font-size: 11px;
  letter-spacing: 2px;
  color: #7d6b97;
  border-top: 1px dashed rgba(168,85,247,0.3);
  margin-top: 20px;
}

/* FADE SCROLL */
.fade {
  opacity: 0;
  transform: translateY(36px);
  transition: opacity 0.7s ease, transform 0.7s cubic-bezier(0.2, 0.8, 0.3, 1);
}

.fade.show {
  opacity: 1;
  transform: translateY(0);
}

@media (max-width: 700px) {
  .title { font-size: 44px; letter-spacing: 3px; }
  .card { padding: 20px; }
  nav { flex-direction: column; align-items: center; gap: 8px; text-align: center; }
  h2 { font-size: 18px; }
  .rule-list li { font-size: 12px; }
}

::-webkit-scrollbar {
  width: 5px;
}
::-webkit-scrollbar-track {
  background: #0b041a;
}
::-webkit-scrollbar-thumb {
  background: #a855f7;
  border-radius: 20px;
}
</style>
</head>
<body>

<div id="loading">
  <div class="spinner"></div>
  <div class="loading-text">memuat aturan pertempuran</div>
</div>

<div class="orb"></div>

<nav>
  <h1>⚡ ALZHARDCORE • FASE 4</h1>
  <span>medium-1.mineidhost.icu:19144</span>
</nav>

<header>
  <div class="title">ALZHARDCORE</div>
  <div class="sub">Fase 4 — Zero Mercy — Rule of War</div>
</header>

<div class="container">

  <!-- LORE RINGKAS -->
  <div class="card fade">
    <h2>📖 ▸ NARASI KEHANCURAN</h2>
    <p>Dunia hancur. Hukum lama lenyap. Di FASE 4, hanya yang disiplin dan haus darah yang bertahan. <strong>Roleplay & konflik</strong> adalah nyawa server.</p>
  </div>

  <!-- ========== RULES SERVER (NEW) ========== -->
  <div class="card fade">
    <h2>📜 ▸ RULES SERVER — KODE ETIK ABSOLUT</h2>
    
    <div class="rule-block">
      <div class="rule-title">✅ WAJIB ROLEPLAY</div>
      <ul class="rule-list">
        <li><span class="bullet">⚔️</span> <strong>PVP / KILL</strong> — Harus ada konflik RP yang jelas. Tidak boleh kill tanpa alasan cerita.</li>
      </ul>
    </div>

    <div class="rule-block">
      <div class="rule-title">❌ HARAM (ZERO TOLERANSI)</div>
      <ul class="rule-list">
        <li><span class="bullet">⚠️</span> Hack • X-Ray • Reach • Hitbox • Elytra fly • Exploit apapun.</li>
      </ul>
    </div>

    <div class="rule-block">
      <div class="rule-title">❌ DILARANG</div>
      <ul class="rule-list">
        <li><span class="bullet">🎣</span> Hit AFK Fishing / Mob farm berlebihan tanpa izin.</li>
        <li><span class="bullet">🛡️</span> Bully / malak (merampok paksa) newbie tanpa alasan RP.</li>
        <li><span class="bullet">⚡</span> Dilarang pakai Enchant Thorns pada armor (mengganggu keseimbangan PvP).</li>
      </ul>
    </div>

    <div class="rule-block">
      <div class="rule-title">🚫 NO TOXIC</div>
      <ul class="rule-list">
        <li><span class="bullet">💬</span> Rasisme, baperan berlebihan, kata kasar & harassment = mute/ban.</li>
      </ul>
    </div>

    <div class="rule-block">
      <div class="rule-title">🤝 RESPECT & NO GRIEF</div>
      <ul class="rule-list">
        <li><span class="bullet">👑</span> Hormati player lag & sesama member.</li>
        <li><span class="bullet">🏚️</span> <strong>NO GRIEF</strong> — Dilarang hancurkan base tanpa sistem perang resmi.</li>
      </ul>
    </div>
  </div>

  <!-- ========== RULES GRUP ========== -->
  <div class="card fade">
    <h2>💬 ▸ RULES GRUP WHATSAPP & DISCORD</h2>
    <ul class="rule-list" style="list-style: none;">
      <li><span class="bullet">❌</span> <strong>SPAM</strong> | Promosi liar | Link 18+ | Bawa orang tua</li>
      <li><span class="bullet">❌</span> <strong>DEBAT KUSIR</strong> | Spam tag admin tanpa alasan jelas</li>
      <li><span class="bullet">⚡</span> <strong>PAKAI BAHASA SOPAN</strong> | Ikuti arahan admin & moderator</li>
      <li><span class="bullet">🗣️</span> Ada masalah? <strong>DM ADMIN</strong> — Jangan drama di grup.</li>
    </ul>
  </div>

  <!-- ========== FREE RANK CREATOR ========== -->
  <div class="card fade">
    <h2>🎬 ▸ FREE RANK CREATOR</h2>
    <div class="rank-badge">✦ SPECIAL PROGRAM ✦</div>
    <p style="margin: 12px 0; font-variant: small-caps; font-size: 14px;">
      Untuk <strong>Youtuber / Tiktoker / Content Creator</strong> yang ingin support server.
    </p>
    <ul class="rule-list" style="margin-bottom: 12px;">
      <li>📌 <strong>Syarat & Benefit?</strong> — Dapatkan rank eksklusif + exposure.</li>
      <li>💬 <strong>Chat admin via WhatsApp / Discord</strong> untuk info lengkap.</li>
    </ul>
    <div style="margin-top: 16px;">
      <a class="link" href="https://chat.whatsapp.com/DM3pYGUoSwg9Aojwk6ERSn" style="display: inline-block; width: auto; padding: 10px 24px;">📢 Hubungi Admin (Whitelist)</a>
    </div>
  </div>

  <!-- GATEWAY / KOMUNITAS -->
  <div class="card fade">
    <h2>📡 ▸ GERBONG KOMUNITAS</h2>
    <a class="link" href="https://chat.whatsapp.com/F0vqI0gK5hxGqDo7P0eHLN">⟐ Grup utama WhatsApp</a>
    <a class="link" href="https://chat.whatsapp.com/DM3pYGUoSwg9Aojwk6ERSn">⚙️ Whitelist & Verifikasi</a>
    <a class="link" href="https://discord.gg/cmGwdzEj7f">🎙️ Discord Server — War Room</a>
    <a class="link" href="https://saweria.co/alzhardcore">☠️ Support Server (Donasi)</a>
  </div>
</div>

<footer>
  © ALZHARDCORE — FASE 4 | RULES & ORDER IN CHAOS
</footer>

<script>
  const loadingDiv = document.getElementById("loading");
  window.addEventListener("load", function() {
    setTimeout(() => {
      loadingDiv.style.opacity = "0";
      setTimeout(() => {
        if (loadingDiv && loadingDiv.remove) loadingDiv.remove();
      }, 500);
    }, 1100);
  });

  const fadeElements = document.querySelectorAll('.fade');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('show');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1, rootMargin: "0px 0px -20px 0px" });

  fadeElements.forEach(el => observer.observe(el));

  setTimeout(() => {
    fadeElements.forEach(el => {
      const rect = el.getBoundingClientRect();
      if (rect.top < window.innerHeight - 100) {
        el.classList.add('show');
      }
    });
  }, 200);
</script>
</body>
</html>
