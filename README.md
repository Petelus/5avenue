# 5avenue
Web šipkařského klubu
[5Avenue_Praha_Web.html](https://github.com/user-attachments/files/25598398/5Avenue_Praha_Web.html)
<!DOCTYPE html>
<html lang="cs">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🎯 5. Avenue Praha — Šipkařský klub</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Rajdhani:wght@400;600;700&family=Share+Tech+Mono&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>
<style>
:root {
  --bg: #0a0a0f;
  --bg2: #111118;
  --bg3: #16161f;
  --card: #1a1a26;
  --card2: #1e1e2e;
  --border: #2a2a40;
  --accent: #e8b84b;
  --accent2: #ff6b35;
  --accent3: #00d4ff;
  --green: #00ff88;
  --red: #ff3366;
  --yellow: #ffd700;
  --text: #e8e8f0;
  --text2: #9898b0;
  --glow: 0 0 20px rgba(232,184,75,0.3);
  --glow2: 0 0 30px rgba(0,212,255,0.2);
}

* { margin:0; padding:0; box-sizing:border-box; }

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Rajdhani', sans-serif;
  font-size: 15px;
  min-height: 100vh;
  overflow-x: hidden;
}

/* SCROLLBAR */
::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: var(--bg); }
::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 3px; }

/* HEADER */
header {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: rgba(10,10,15,0.95);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--border);
  padding: 0 20px;
}

.header-inner {
  max-width: 1400px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  gap: 20px;
  height: 64px;
}

.logo {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 28px;
  color: var(--accent);
  text-shadow: var(--glow);
  letter-spacing: 3px;
  white-space: nowrap;
}

.logo span { color: var(--accent3); }

nav {
  display: flex;
  gap: 4px;
  flex-wrap: wrap;
  margin-left: auto;
}

nav a {
  color: var(--text2);
  text-decoration: none;
  padding: 6px 12px;
  border-radius: 4px;
  font-weight: 600;
  font-size: 13px;
  letter-spacing: 1px;
  text-transform: uppercase;
  transition: all 0.2s;
  border: 1px solid transparent;
}
nav a:hover {
  color: var(--accent);
  border-color: var(--accent);
  background: rgba(232,184,75,0.08);
}

/* HERO */
.hero {
  background: linear-gradient(135deg, #0a0a0f 0%, #0f0f1e 50%, #0a0f0a 100%);
  padding: 80px 20px;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: 
    radial-gradient(ellipse at 20% 50%, rgba(232,184,75,0.08) 0%, transparent 60%),
    radial-gradient(ellipse at 80% 50%, rgba(0,212,255,0.06) 0%, transparent 60%);
  pointer-events: none;
}

.hero-dart {
  font-size: 80px;
  animation: spin 8s linear infinite;
  display: inline-block;
  filter: drop-shadow(0 0 20px var(--accent));
}

@keyframes spin {
  0% { transform: rotate(-5deg); }
  50% { transform: rotate(5deg); }
  100% { transform: rotate(-5deg); }
}

.hero h1 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(48px, 10vw, 120px);
  color: var(--accent);
  text-shadow: 0 0 40px rgba(232,184,75,0.5), 0 0 80px rgba(232,184,75,0.2);
  letter-spacing: 8px;
  line-height: 0.9;
  margin: 10px 0;
}

.hero-sub {
  font-size: clamp(14px, 3vw, 22px);
  color: var(--accent3);
  letter-spacing: 4px;
  text-transform: uppercase;
  font-weight: 600;
}

.hero-badge {
  display: inline-block;
  background: linear-gradient(135deg, rgba(232,184,75,0.15), rgba(232,184,75,0.05));
  border: 1px solid var(--accent);
  color: var(--accent);
  padding: 8px 24px;
  border-radius: 30px;
  font-size: 14px;
  font-weight: 700;
  letter-spacing: 2px;
  margin-top: 20px;
}

/* STATS ROW */
.stats-row {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  gap: 1px;
  background: var(--border);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
}

.stat-item {
  background: var(--bg2);
  padding: 24px 20px;
  text-align: center;
  transition: background 0.3s;
}

.stat-item:hover { background: var(--card); }

.stat-number {
  font-family: 'Share Tech Mono', monospace;
  font-size: 32px;
  font-weight: bold;
  color: var(--accent);
  text-shadow: 0 0 15px rgba(232,184,75,0.4);
}

.stat-label {
  font-size: 11px;
  color: var(--text2);
  text-transform: uppercase;
  letter-spacing: 2px;
  margin-top: 4px;
}

/* MAIN CONTAINER */
.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 40px 20px;
}

/* SECTION */
.section { margin-bottom: 60px; }

.section-title {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 36px;
  color: var(--accent);
  letter-spacing: 4px;
  margin-bottom: 20px;
  padding-bottom: 12px;
  border-bottom: 2px solid var(--border);
  position: relative;
  display: flex;
  align-items: center;
  gap: 12px;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 80px;
  height: 2px;
  background: var(--accent);
}

/* CARDS GRID */
.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 20px;
}

/* CARD */
.card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 24px;
  position: relative;
  overflow: hidden;
  transition: all 0.3s;
}

.card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--accent), var(--accent3));
  opacity: 0;
  transition: opacity 0.3s;
}

.card:hover {
  border-color: var(--accent);
  box-shadow: 0 8px 32px rgba(232,184,75,0.15);
  transform: translateY(-2px);
}

.card:hover::before { opacity: 1; }

/* TABLE */
.table-wrap {
  overflow-x: auto;
  border-radius: 8px;
  border: 1px solid var(--border);
}

table {
  width: 100%;
  border-collapse: collapse;
  font-family: 'Share Tech Mono', monospace;
  font-size: 13px;
}

thead tr {
  background: var(--card2);
}

thead th {
  padding: 12px 14px;
  text-align: left;
  font-family: 'Rajdhani', sans-serif;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--accent);
  white-space: nowrap;
  border-bottom: 1px solid var(--border);
}

tbody tr {
  border-bottom: 1px solid rgba(42,42,64,0.5);
  transition: background 0.2s;
}

tbody tr:hover { background: rgba(232,184,75,0.05); }

tbody td {
  padding: 10px 14px;
  color: var(--text);
  white-space: nowrap;
}

.win { color: var(--green); font-weight: 700; }
.draw { color: var(--yellow); }
.loss { color: var(--red); }
.our-team { background: rgba(232,184,75,0.08) !important; }
.our-team td:nth-child(2) { color: var(--accent); font-weight: 700; }
.rank-gold { color: var(--yellow); }
.rank-up { color: var(--green); }
.rank-down { color: var(--red); }
.rank-us { color: var(--accent); }

/* PLAYER CARDS */
.players-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 20px;
}

.player-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  overflow: hidden;
  transition: all 0.3s;
  cursor: default;
}

.player-card:hover {
  border-color: var(--accent);
  box-shadow: 0 0 30px rgba(232,184,75,0.15);
  transform: translateY(-4px);
}

.player-header {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 20px;
  background: var(--card2);
  border-bottom: 1px solid var(--border);
}

.player-photo {
  width: 72px;
  height: 72px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid var(--accent);
  flex-shrink: 0;
}

.player-no-photo {
  width: 72px;
  height: 72px;
  border-radius: 50%;
  background: var(--border);
  border: 2px solid var(--border);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 28px;
  flex-shrink: 0;
}

.player-name {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 22px;
  letter-spacing: 2px;
  color: var(--text);
  line-height: 1.1;
}

.player-role {
  font-size: 11px;
  color: var(--accent);
  letter-spacing: 2px;
  text-transform: uppercase;
  font-weight: 700;
}

.player-stats {
  padding: 16px 20px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}

.pstat {
  text-align: center;
  padding: 8px;
  background: var(--bg3);
  border-radius: 6px;
}

.pstat-val {
  font-family: 'Share Tech Mono', monospace;
  font-size: 20px;
  font-weight: bold;
  color: var(--accent);
}

.pstat-lbl {
  font-size: 10px;
  color: var(--text2);
  text-transform: uppercase;
  letter-spacing: 1px;
}

.win-bar {
  margin: 0 20px 16px;
}

.win-bar-label {
  display: flex;
  justify-content: space-between;
  font-size: 12px;
  color: var(--text2);
  margin-bottom: 6px;
}

.win-bar-track {
  height: 8px;
  background: var(--bg3);
  border-radius: 4px;
  overflow: hidden;
}

.win-bar-fill {
  height: 100%;
  border-radius: 4px;
  transition: width 1s ease;
  background: linear-gradient(90deg, var(--red), var(--yellow), var(--green));
}

.contact-actions {
  padding: 12px 20px 20px;
  display: flex;
  gap: 8px;
}

.btn-contact {
  flex: 1;
  padding: 10px;
  border-radius: 6px;
  border: none;
  cursor: pointer;
  font-family: 'Rajdhani', sans-serif;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 1px;
  text-decoration: none;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  transition: all 0.2s;
}

.btn-call {
  background: rgba(0,255,136,0.1);
  color: var(--green);
  border: 1px solid rgba(0,255,136,0.3);
}

.btn-call:hover {
  background: rgba(0,255,136,0.2);
  box-shadow: 0 0 15px rgba(0,255,136,0.2);
}

.btn-email {
  background: rgba(0,212,255,0.1);
  color: var(--accent3);
  border: 1px solid rgba(0,212,255,0.3);
}

.btn-email:hover {
  background: rgba(0,212,255,0.2);
  box-shadow: 0 0 15px rgba(0,212,255,0.2);
}

.contact-info {
  padding: 0 20px 16px;
  font-size: 12px;
  color: var(--text2);
}

.contact-info div { margin-bottom: 4px; }
.contact-info span { color: var(--accent3); font-family: 'Share Tech Mono', monospace; }

/* CHARTS */
.charts-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 20px;
}

.chart-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 24px;
}

.chart-card h3 {
  font-family: 'Rajdhani', sans-serif;
  font-size: 14px;
  font-weight: 700;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: 20px;
}

.chart-wrap {
  position: relative;
  height: 280px;
}

/* FINANCE */
.finance-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 16px;
  margin-bottom: 30px;
}

.finance-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 20px;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.finance-card::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 3px;
}

.finance-card.green::after { background: var(--green); }
.finance-card.yellow::after { background: var(--yellow); }
.finance-card.red::after { background: var(--red); }
.finance-card.blue::after { background: var(--accent3); }

.finance-amount {
  font-family: 'Share Tech Mono', monospace;
  font-size: 36px;
  font-weight: bold;
  margin-bottom: 4px;
}

.finance-card.green .finance-amount { color: var(--green); }
.finance-card.yellow .finance-amount { color: var(--yellow); }
.finance-card.red .finance-amount { color: var(--red); }
.finance-card.blue .finance-amount { color: var(--accent3); }

.finance-label {
  font-size: 11px;
  color: var(--text2);
  text-transform: uppercase;
  letter-spacing: 2px;
}

/* FINES */
.fine-match {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 8px;
  margin-bottom: 16px;
  overflow: hidden;
}

.fine-match-header {
  background: var(--card2);
  padding: 14px 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  cursor: pointer;
  user-select: none;
  transition: background 0.2s;
}

.fine-match-header:hover { background: rgba(232,184,75,0.06); }

.fine-match-title {
  font-weight: 700;
  color: var(--text);
  font-size: 15px;
}

.fine-match-date { color: var(--accent3); font-family: 'Share Tech Mono', monospace; font-size: 13px; }

.fine-match-total {
  font-family: 'Share Tech Mono', monospace;
  font-size: 18px;
  color: var(--accent);
  font-weight: bold;
}

.fine-match-body { display: none; padding: 0 4px 4px; }
.fine-match-body.open { display: block; }

.collapse-arrow { color: var(--accent); font-size: 18px; transition: transform 0.3s; }
.open-state .collapse-arrow { transform: rotate(180deg); }

/* TABS */
.tabs {
  display: flex;
  gap: 4px;
  margin-bottom: 24px;
  border-bottom: 1px solid var(--border);
  overflow-x: auto;
  padding-bottom: 0;
}

.tab-btn {
  padding: 10px 20px;
  background: none;
  border: none;
  border-bottom: 2px solid transparent;
  color: var(--text2);
  cursor: pointer;
  font-family: 'Rajdhani', sans-serif;
  font-size: 14px;
  font-weight: 700;
  letter-spacing: 1px;
  text-transform: uppercase;
  transition: all 0.2s;
  white-space: nowrap;
  margin-bottom: -1px;
}

.tab-btn:hover { color: var(--text); }
.tab-btn.active { color: var(--accent); border-bottom-color: var(--accent); }

.tab-content { display: none; }
.tab-content.active { display: block; }

/* SEARCH */
.search-box {
  display: flex;
  gap: 12px;
  margin-bottom: 20px;
  flex-wrap: wrap;
}

.search-input {
  flex: 1;
  min-width: 200px;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 6px;
  padding: 10px 16px;
  color: var(--text);
  font-family: 'Rajdhani', sans-serif;
  font-size: 14px;
  outline: none;
  transition: border-color 0.2s;
}

.search-input:focus { border-color: var(--accent); }
.search-input::placeholder { color: var(--text2); }

.filter-select {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 6px;
  padding: 10px 16px;
  color: var(--text);
  font-family: 'Rajdhani', sans-serif;
  font-size: 14px;
  outline: none;
  cursor: pointer;
}

/* LOADING ANIMATION */
@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

.fade-in {
  animation: fadeInUp 0.5s ease forwards;
}

/* COUNTER ANIM */
@keyframes countUp {
  from { opacity: 0; }
  to { opacity: 1; }
}

/* PARTICLES */
.particles {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  pointer-events: none;
  z-index: 0;
  overflow: hidden;
}

.particle {
  position: absolute;
  width: 2px;
  height: 2px;
  background: var(--accent);
  border-radius: 50%;
  animation: float linear infinite;
  opacity: 0.3;
}

@keyframes float {
  0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
  10% { opacity: 0.3; }
  90% { opacity: 0.3; }
  100% { transform: translateY(-100px) rotate(720deg); opacity: 0; }
}

/* BADGE */
.badge {
  display: inline-block;
  padding: 2px 8px;
  border-radius: 3px;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 1px;
}

.badge-green { background: rgba(0,255,136,0.15); color: var(--green); border: 1px solid rgba(0,255,136,0.3); }
.badge-red { background: rgba(255,51,102,0.15); color: var(--red); border: 1px solid rgba(255,51,102,0.3); }
.badge-yellow { background: rgba(255,215,0,0.15); color: var(--yellow); border: 1px solid rgba(255,215,0,0.3); }
.badge-blue { background: rgba(0,212,255,0.15); color: var(--accent3); border: 1px solid rgba(0,212,255,0.3); }

/* FOOTER */
footer {
  background: var(--bg2);
  border-top: 1px solid var(--border);
  padding: 40px 20px;
  text-align: center;
  color: var(--text2);
  font-size: 13px;
}

footer .footer-logo {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 32px;
  color: var(--accent);
  letter-spacing: 4px;
  margin-bottom: 10px;
}

/* RESPONSIVE */
@media (max-width: 768px) {
  nav { display: none; }
  .charts-grid { grid-template-columns: 1fr; }
  .hero-dart { font-size: 50px; }
  .players-grid { grid-template-columns: 1fr; }
}

@media (max-width: 480px) {
  .stats-row { grid-template-columns: repeat(2, 1fr); }
  table { font-size: 11px; }
  thead th, tbody td { padding: 8px 8px; }
}

/* TOP PERFORMER HIGHLIGHT */
tbody tr:first-child td:first-child::before {
  content: '';
}

.top-performer {
  background: rgba(232,184,75,0.05) !important;
}

.rank-pos {
  font-family: 'Share Tech Mono', monospace;
  font-weight: bold;
  font-size: 16px;
  color: var(--accent);
}

/* Animated border glow on hover for sections */
.glow-border {
  animation: glowPulse 3s ease-in-out infinite;
}

@keyframes glowPulse {
  0%, 100% { box-shadow: 0 0 5px rgba(232,184,75,0.1); }
  50% { box-shadow: 0 0 20px rgba(232,184,75,0.25); }
}

/* Scrollbar smooth sections */
#tab-matches, #tab-liga, #tab-players, #tab-fines, #tab-finance, #tab-contacts {
  scroll-margin-top: 80px;
}
</style>
</head>
<body>

<div class="particles" id="particles"></div>

<!-- HEADER -->
<header>
  <div class="header-inner">
    <div class="logo">🎯 5.<span>Avenue</span></div>
    <nav>
      <a href="#prehled">Přehled</a>
      <a href="#zapasy">Zápasy</a>
      <a href="#liga">Liga</a>
      <a href="#hraci">Hráči</a>
      <a href="#pokuty">Pokuty</a>
      <a href="#pokladna">Pokladna</a>
      <a href="#soupiska">Soupiska</a>
    </nav>
  </div>
</header>

<!-- HERO -->
<section class="hero">
  <div class="hero-dart">🎯</div>
  <h1>5. AVENUE</h1>
  <div class="hero-sub">Praha · 3. Liga N · Sezóna 2025/26</div>
  <div class="hero-badge">🏆 10. místo &nbsp;·&nbsp; 4V 3R 11P &nbsp;·&nbsp; 11 bodů</div>
</section>

<!-- STATS ROW -->
<div class="stats-row" id="prehled">
  <div class="stat-item">
    <div class="stat-number" id="cnt-games">18</div>
    <div class="stat-label">Odehraných zápasů</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">4</div>
    <div class="stat-label">Výher</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">3</div>
    <div class="stat-label">Remíz</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">11</div>
    <div class="stat-label">Proher</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">11</div>
    <div class="stat-label">Bodů</div>
  </div>
  <div class="stat-item">
    <div class="stat-number" style="color:var(--accent3)">68.3%</div>
    <div class="stat-label">Nejlepší hráč % výher</div>
  </div>
  <div class="stat-item">
    <div class="stat-number" style="color:var(--green)">3 059 Kč</div>
    <div class="stat-label">Stav pokladny</div>
  </div>
  <div class="stat-item">
    <div class="stat-number" style="color:var(--red)">95 Kč</div>
    <div class="stat-label">Aktuální dluhy</div>
  </div>
</div>

<!-- MAIN CONTENT -->
<div class="container">

  <!-- CHARTS -->
  <div class="section">
    <div class="section-title">📊 Statistiky & Grafy</div>
    <div class="charts-grid">

      <div class="chart-card fade-in">
        <h3>Výsledky zápasů 2025/26</h3>
        <div class="chart-wrap"><canvas id="chartResults"></canvas></div>
      </div>

      <div class="chart-card fade-in">
        <h3>% Výher hráčů</h3>
        <div class="chart-wrap"><canvas id="chartWinRate"></canvas></div>
      </div>

      <div class="chart-card fade-in">
        <h3>Průběh sezóny – naše body vs soupeřovi</h3>
        <div class="chart-wrap"><canvas id="chartSeason"></canvas></div>
      </div>

      <div class="chart-card fade-in">
        <h3>Pokuty dle hráče (celkem Kč)</h3>
        <div class="chart-wrap"><canvas id="chartFines"></canvas></div>
      </div>

      <div class="chart-card fade-in">
        <h3>Ligová tabulka – vizualizace bodů</h3>
        <div class="chart-wrap"><canvas id="chartLeague"></canvas></div>
      </div>

      <div class="chart-card fade-in">
        <h3>Legy výherní vs prohrané (hráči)</h3>
        <div class="chart-wrap"><canvas id="chartLegs"></canvas></div>
      </div>

    </div>
  </div>

  <!-- ZAPASY -->
  <div class="section" id="zapasy">
    <div class="section-title">📅 Zápasy</div>
    <div class="search-box">
      <input type="text" class="search-input" id="searchMatches" placeholder="🔍 Hledat soupeře, místo...">
      <select class="filter-select" id="filterResult">
        <option value="">Všechny výsledky</option>
        <option value="V">✅ Výhry</option>
        <option value="R">⚪ Remízy</option>
        <option value="P">❌ Prohry</option>
        <option value="–">⏳ Plánované</option>
      </select>
    </div>
    <div class="table-wrap">
      <table id="tableMatches">
        <thead>
          <tr>
            <th>Kolo</th>
            <th>Datum</th>
            <th>Domácí</th>
            <th>Hosté</th>
            <th>Body</th>
            <th>Legy</th>
            <th>Naše</th>
            <th>Jejich</th>
            <th>Výsl.</th>
            <th>Místo</th>
          </tr>
        </thead>
        <tbody id="matchesTbody">
        </tbody>
      </table>
    </div>
  </div>

  <!-- LIGA -->
  <div class="section" id="liga">
    <div class="section-title">🏆 Ligová tabulka — 3. liga N</div>
    <div class="table-wrap">
      <table>
        <thead>
          <tr>
            <th>#</th>
            <th>Tým</th>
            <th>Z</th>
            <th>V</th>
            <th>R</th>
            <th>P</th>
            <th>Body</th>
            <th>Pořadí</th>
          </tr>
        </thead>
        <tbody id="ligaTbody">
        </tbody>
      </table>
    </div>
  </div>

  <!-- HRACI STATISTIKY -->
  <div class="section" id="hraci">
    <div class="section-title">👥 Hráčské statistiky</div>
    <div class="table-wrap" style="margin-bottom:30px">
      <table>
        <thead>
          <tr>
            <th>#</th>
            <th>Hráč</th>
            <th>Kola</th>
            <th>Duely V</th>
            <th>Duely P</th>
            <th>% Výher</th>
            <th>Legy V</th>
            <th>Legy P</th>
            <th>95+</th>
            <th>133+</th>
            <th>170+</th>
          </tr>
        </thead>
        <tbody id="playerStatsTbody">
        </tbody>
      </table>
    </div>
  </div>

  <!-- POKUTY -->
  <div class="section" id="pokuty">
    <div class="section-title">⚠️ Pokutový přehled</div>
    <div id="finesContainer"></div>
  </div>

  <!-- POKLADNA -->
  <div class="section" id="pokladna">
    <div class="section-title">💰 Pokladna</div>
    <div class="finance-grid">
      <div class="finance-card green">
        <div class="finance-amount">3 059 Kč</div>
        <div class="finance-label">💎 Stav pokladny</div>
      </div>
      <div class="finance-card yellow">
        <div class="finance-amount">3 154 Kč</div>
        <div class="finance-label">📥 Vybráno celkem</div>
      </div>
      <div class="finance-card blue">
        <div class="finance-amount">0 Kč</div>
        <div class="finance-label">📤 Výdaje celkem</div>
      </div>
      <div class="finance-card red">
        <div class="finance-amount">95 Kč</div>
        <div class="finance-label">⚠️ Aktuální dluhy</div>
      </div>
    </div>
    <div class="table-wrap">
      <table id="tablePokladna">
        <thead>
          <tr>
            <th>Datum</th>
            <th>Celkem</th>
            <th>Dluh</th>
            <th>Jméno dlužníka</th>
            <th>Vybráno</th>
            <th>Výdaj</th>
            <th>Poznámka</th>
          </tr>
        </thead>
        <tbody id="pokladnaTbody">
        </tbody>
      </table>
    </div>
  </div>

  <!-- SOUPISKA / KONTAKTY -->
  <div class="section" id="soupiska">
    <div class="section-title">📋 Soupiska & Kontakty</div>
    
    <div style="margin-bottom:24px">
      <div style="font-size:13px;color:var(--text2);margin-bottom:16px;text-transform:uppercase;letter-spacing:2px;font-weight:700;">🏅 Vedení klubu</div>
      <div class="players-grid" id="managementGrid"></div>
    </div>
    
    <div>
      <div style="font-size:13px;color:var(--text2);margin-bottom:16px;text-transform:uppercase;letter-spacing:2px;font-weight:700;">🎯 Hráči</div>
      <div class="players-grid" id="playersGrid"></div>
    </div>
  </div>

</div>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">🎯 5. AVENUE PRAHA</div>
  <div style="margin-bottom:8px">3. liga N &nbsp;·&nbsp; Sezóna 2025/26 &nbsp;·&nbsp; Praha</div>
  <div style="color:var(--border);font-size:11px">© 2025/26 5. Avenue Praha Darts Club</div>
</footer>

<script>
// ===== PHOTOS DATA =====
const PHOTOS = {
  "Donat_Petr": "data:image/jpeg;base64,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",
  "Jerabek_Miroslav": "data:image/jpeg;base64,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",
  "Jurenka_Daniel": "data:image/jpeg;base64,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",
  "Knoflicek_Michal": "data:image/jpeg;base64,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",
  "Miksik_Antonin": "data:image/jpeg;base64,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",
  "Moravcova_Petra": "data:image/jpeg;base64,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",
  "Urbanovsky_Petr": "data:image/jpeg;base64,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",
  "Zelinka_Vaclav": "data:image/jpeg;base64,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",
};

// ===== MATCHES DATA =====
const MATCHES = [
  {kolo:1, datum:"7.9.2025", domaci:"Stiflerova máma Praha", hoste:"5. Avenue Praha", body:"6:12", legy:"14:26", nase:12, jejich:6, vysl:"✅ V", misto:"Club bar Pomeranč"},
  {kolo:2, datum:"14.9.2025", domaci:"5. Avenue Praha", hoste:"Monkey z 213 Praha", body:"9:9", legy:"20:21", nase:9, jejich:9, vysl:"⚪ R", misto:"5. Avenue"},
  {kolo:3, datum:"16.9.2025", domaci:"Hostivar Darts Praha", hoste:"5. Avenue Praha", body:"11:7", legy:"23:18", nase:7, jejich:11, vysl:"❌ P", misto:"Pivní bar Palma"},
  {kolo:4, datum:"5.10.2025", domaci:"5. Avenue Praha", hoste:"Worm Gang Praha", body:"9:9", legy:"20:23", nase:9, jejich:9, vysl:"⚪ R", misto:"5. Avenue"},
  {kolo:5, datum:"12.10.2025", domaci:"Silent Darts Praha", hoste:"5. Avenue Praha", body:"14:4", legy:"30:9", nase:4, jejich:14, vysl:"❌ P", misto:"Hospoda reSTART"},
  {kolo:6, datum:"19.10.2025", domaci:"Clasico My Praha", hoste:"5. Avenue Praha", body:"14:4", legy:"28:13", nase:4, jejich:14, vysl:"❌ P", misto:"Restaurace Alfa"},
  {kolo:7, datum:"2.11.2025", domaci:"5. Avenue Praha", hoste:"Stiflerova máma Modřany", body:"14:4", legy:"31:11", nase:14, jejich:4, vysl:"✅ V", misto:"5. Avenue"},
  {kolo:9, datum:"23.11.2025", domaci:"5. Avenue Praha", hoste:"Žíznivý důchodci Praha", body:"12:6", legy:"27:19", nase:12, jejich:6, vysl:"✅ V", misto:"5. Avenue"},
  {kolo:10, datum:"7.12.2025", domaci:"Tempácký hroty Praha", hoste:"5. Avenue Praha", body:"12:6", legy:"29:17", nase:6, jejich:12, vysl:"❌ P", misto:"Hotel Cham"},
  {kolo:11, datum:"14.12.2025", domaci:"5. Avenue Praha", hoste:"Otupělé hroty Praha", body:"3:15", legy:"13:32", nase:3, jejich:15, vysl:"❌ P", misto:"5. Avenue"},
  {kolo:12, datum:"21.12.2025", domaci:"Sedmá rota Praha B", hoste:"5. Avenue Praha", body:"15:3", legy:"33:10", nase:3, jejich:15, vysl:"❌ P", misto:"Pivnice Pipkin"},
  {kolo:13, datum:"4.1.2026", domaci:"5. Avenue Praha", hoste:"PLB Praha", body:"8:10", legy:"17:26", nase:8, jejich:10, vysl:"❌ P", misto:"5. Avenue"},
  {kolo:14, datum:"18.1.2026", domaci:"5. Avenue Praha", hoste:"Stiflerova máma Praha", body:"14:4", legy:"32:12", nase:14, jejich:4, vysl:"✅ V", misto:"5. Avenue"},
  {kolo:15, datum:"25.1.2026", domaci:"Monkey z 213 Praha", hoste:"5. Avenue Praha", body:"9:9", legy:"20:21", nase:9, jejich:9, vysl:"⚪ R", misto:"Hospoda 213"},
  {kolo:16, datum:"1.2.2026", domaci:"5. Avenue Praha", hoste:"Hostivar Darts Praha", body:"2:16", legy:"14:32", nase:2, jejich:16, vysl:"❌ P", misto:"5. Avenue"},
  {kolo:17, datum:"8.2.2026", domaci:"Worm Gang Praha", hoste:"5. Avenue Praha", body:"13:5", legy:"27:12", nase:5, jejich:13, vysl:"❌ P", misto:"Hotel Cham"},
  {kolo:18, datum:"15.2.2026", domaci:"5. Avenue Praha", hoste:"Silent Darts Praha", body:"8:10", legy:"20:24", nase:8, jejich:10, vysl:"❌ P", misto:"5. Avenue"},
  {kolo:19, datum:"22.2.2026", domaci:"5. Avenue Praha", hoste:"Clasico My Praha", body:"6:12", legy:"17:25", nase:6, jejich:12, vysl:"❌ P", misto:"5. Avenue"},
  {kolo:20, datum:"1.3.2026", domaci:"Stiflerova máma Modřany", hoste:"5. Avenue Praha", body:"–", legy:"–", nase:"–", jejich:"–", vysl:"–", misto:"Club bar Pomeranč"},
  {kolo:22, datum:"29.3.2026", domaci:"Žíznivý důchodci Praha", hoste:"5. Avenue Praha", body:"–", legy:"–", nase:"–", jejich:"–", vysl:"–", misto:"Hospoda 213"},
  {kolo:23, datum:"12.4.2026", domaci:"5. Avenue Praha", hoste:"Tempácký hroty Praha", body:"–", legy:"–", nase:"–", jejich:"–", vysl:"–", misto:"5. Avenue"},
  {kolo:24, datum:"19.4.2026", domaci:"Otupělé hroty Praha", hoste:"5. Avenue Praha", body:"–", legy:"–", nase:"–", jejich:"–", vysl:"–", misto:"Restaurace Šolcovna"},
  {kolo:25, datum:"26.4.2026", domaci:"5. Avenue Praha", hoste:"Sedmá rota Praha B", body:"–", legy:"–", nase:"–", jejich:"–", vysl:"–", misto:"5. Avenue"},
  {kolo:26, datum:"5.5.2026", domaci:"PLB Praha", hoste:"5. Avenue Praha", body:"–", legy:"–", nase:"–", jejich:"–", vysl:"–", misto:"Restaurace Alfa"},
];

// ===== LIGA DATA =====
const LIGA = [
  {pos:1, tym:"Silent Darts Praha", z:17, v:14, r:2, p:1, body:30, poradi:"🏆 1. místo"},
  {pos:2, tym:"Otupělé hroty Praha", z:17, v:13, r:0, p:4, body:26, poradi:"⬆️ Postup?"},
  {pos:3, tym:"Worm Gang Praha", z:17, v:12, r:1, p:4, body:25, poradi:"⬆️ Postup?"},
  {pos:4, tym:"Tempácký hroty Praha", z:17, v:11, r:2, p:4, body:24, poradi:""},
  {pos:5, tym:"PLB Praha", z:17, v:10, r:1, p:6, body:21, poradi:""},
  {pos:6, tym:"Sedmá rota Praha B", z:17, v:9, r:2, p:6, body:20, poradi:""},
  {pos:7, tym:"Clasico My Praha", z:17, v:9, r:1, p:7, body:19, poradi:""},
  {pos:8, tym:"Monkey z 213 Praha", z:17, v:7, r:5, p:5, body:19, poradi:""},
  {pos:9, tym:"Hostivar Darts Praha", z:17, v:8, r:0, p:9, body:16, poradi:""},
  {pos:10, tym:"🎯 5. Avenue Praha", z:18, v:4, r:3, p:11, body:11, poradi:"🎯 Náš tým", nase:true},
  {pos:11, tym:"Žíznivý důchodci Praha", z:17, v:4, r:2, p:11, body:10, poradi:""},
  {pos:12, tym:"Stiflerova máma Praha", z:17, v:4, r:1, p:12, body:9, poradi:"⬇️ Ohrožení"},
  {pos:13, tym:"Stiflerova máma Modřany", z:17, v:0, r:0, p:17, body:0, poradi:"⬇️ Ohrožení"},
];

// ===== PLAYERS DATA =====
const PLAYERS_STATS = [
  {pos:1, jmeno:"Donát Petr", kola:15, duelyV:41, duelyP:19, pct:0.683, legyV:98, legyP:57, p95:141, p133:30, p170:1},
  {pos:2, jmeno:"Knoflíček Michal", kola:15, duelyV:33, duelyP:27, pct:0.550, legyV:78, legyP:71, p95:75, p133:9, p170:2},
  {pos:3, jmeno:"Jurenka Daniel", kola:16, duelyV:26, duelyP:38, pct:0.406, legyV:66, legyP:91, p95:60, p133:3, p170:1},
  {pos:4, jmeno:"Zelinka Václav", kola:16, duelyV:19, duelyP:44, pct:0.302, legyV:56, legyP:96, p95:36, p133:13, p170:0},
  {pos:5, jmeno:"Jeřábek Miroslav", kola:4, duelyV:3, duelyP:11, pct:0.214, legyV:10, legyP:24, p95:11, p133:2, p170:0},
  {pos:6, jmeno:"Moravcová Petra", kola:5, duelyV:2, duelyP:13, pct:0.133, legyV:10, legyP:28, p95:14, p133:0, p170:0},
  {pos:7, jmeno:"Mikšík Antonín", kola:1, duelyV:0, duelyP:4, pct:0.000, legyV:4, legyP:8, p95:3, p133:0, p170:0},
];

// ===== CONTACTS DATA =====
const MANAGEMENT = [
  {jmeno:"Jurenka Daniel", funkce:"PŘEDSEDA KLUBU", reg:"CZE032608", obec:"Praha 4", email:"daniel.prace@seznam.cz", tel:"+420604354380", gdpr:"SOUHLAS", foto:"Jurenka_Daniel"},
  {jmeno:"Donát Petr", funkce:"VEDOUCÍ TÝMU", reg:"CZE064893", obec:"Praha 4", email:"Hruskovnik@gmail.com", tel:"+420737063613", gdpr:"SOUHLAS", foto:"Donat_Petr"},
];

const PLAYERS = [
  {jmeno:"Donát Petr", reg:"CZE064893", obec:"Praha 4", email:"Hruskovnik@gmail.com", tel:"+420737063613", gdpr:"SOUHLAS", foto:"Donat_Petr"},
  {jmeno:"Jeřábek Miroslav", reg:"CZE077190", obec:"Praha 10", email:"-", tel:"+420720234693", gdpr:"SOUHLAS", foto:"Jerabek_Miroslav"},
  {jmeno:"Jurenka Daniel", reg:"CZE032608", obec:"Praha 4", email:"daniel.prace@seznam.cz", tel:"+420604354380", gdpr:"SOUHLAS", foto:"Jurenka_Daniel"},
  {jmeno:"Michal Knoflíček", reg:"CZE072414", obec:"Praha", email:"Knoflicek.m@gmail.com", tel:"+420725811710", gdpr:"SOUHLAS", foto:"Knoflicek_Michal"},
  {jmeno:"Mikšík Antonín", reg:"CZE088331", obec:"Paseka", email:"Tonikmiksik@seznam.cz", tel:"+420605172410", gdpr:"SOUHLAS", foto:"Miksik_Antonin"},
  {jmeno:"Moravcová Petra", reg:"CZE068036", obec:"Praha 5", email:"-", tel:"+420702901139", gdpr:"SOUHLAS", foto:"Moravcova_Petra"},
  {jmeno:"Urbanovský Petr", reg:"CZE004224", obec:"Praha 4", email:"-", tel:"+420777167824", gdpr:"SOUHLAS", foto:"Urbanovsky_Petr"},
  {jmeno:"Zelinka Václav", reg:"CZE037776", obec:"Praha 4", email:"-", tel:"+420775340980", gdpr:"SOUHLAS", foto:"Zelinka_Vaclav"},
];

// ===== FINES DATA =====
const FINES = [
  {
    zápas:"Clasico My Praha", datum:"22.2.2026", celkem:245.5,
    hraci:[
      {jmeno:"Donát Petr", n011:5, n1229:15, asfalt:10, n200:null, mezisouc:30, body:0, sleva:0, uhradit:30},
      {jmeno:"Jeřábek Miroslav", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Jurenka Daniel", n011:5, n1229:57, asfalt:0, n200:20, mezisouc:82, body:1, sleva:25, uhradit:61.5},
      {jmeno:"Knoflíček Michal", n011:15, n1229:36, asfalt:0, n200:null, mezisouc:51, body:0, sleva:0, uhradit:51},
      {jmeno:"Zelinka Václav", n011:30, n1229:63, asfalt:10, n200:null, mezisouc:103, body:0, sleva:0, uhradit:103},
      {jmeno:"Moravcová Petra", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Urbanovský Petr", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Mikšík Antonín", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
    ]
  },
  {
    zápas:"Silent Darts Praha", datum:"15.2.2026", celkem:197.25,
    hraci:[
      {jmeno:"Donát Petr", n011:0, n1229:12, asfalt:0, n200:0, mezisouc:12, body:4, sleva:100, uhradit:0},
      {jmeno:"Jeřábek Miroslav", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Jurenka Daniel", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Knoflíček Michal", n011:5, n1229:24, asfalt:0, n200:0, mezisouc:29, body:3, sleva:75, uhradit:7.25},
      {jmeno:"Zelinka Václav", n011:20, n1229:45, asfalt:10, n200:20, mezisouc:95, body:0, sleva:0, uhradit:95},
      {jmeno:"Moravcová Petra", n011:20, n1229:45, asfalt:30, n200:0, mezisouc:95, body:0, sleva:0, uhradit:95, dluh:true},
      {jmeno:"Urbanovský Petr", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Mikšík Antonín", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
    ]
  },
  {
    zápas:"Worm Gang Praha", datum:"8.2.2026", celkem:272.25,
    hraci:[
      {jmeno:"Donát Petr", n011:0, n1229:33, asfalt:10, n200:0, mezisouc:43, body:3, sleva:0, uhradit:43},
      {jmeno:"Jeřábek Miroslav", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Jurenka Daniel", n011:0, n1229:66, asfalt:10, n200:20, mezisouc:96, body:1, sleva:25, uhradit:72},
      {jmeno:"Knoflíček Michal", n011:10, n1229:21, asfalt:0, n200:20, mezisouc:51, body:1, sleva:25, uhradit:38.25},
      {jmeno:"Zelinka Václav", n011:20, n1229:39, asfalt:30, n200:20, mezisouc:109, body:0, sleva:0, uhradit:109},
      {jmeno:"Moravcová Petra", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Urbanovský Petr", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Mikšík Antonín", n011:0, n1229:0, asfalt:0, n200:10, mezisouc:10, body:0, sleva:0, uhradit:10},
    ]
  },
  {
    zápas:"Hostivar Darts Praha", datum:"1.2.2026", celkem:311.75,
    hraci:[
      {jmeno:"Donát Petr", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Jeřábek Miroslav", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Jurenka Daniel", n011:5, n1229:57, asfalt:40, n200:0, mezisouc:102, body:0, sleva:0, uhradit:102},
      {jmeno:"Knoflíček Michal", n011:5, n1229:54, asfalt:10, n200:20, mezisouc:89, body:1, sleva:25, uhradit:66.75},
      {jmeno:"Zelinka Václav", n011:20, n1229:33, asfalt:0, n200:0, mezisouc:53, body:0, sleva:0, uhradit:53},
      {jmeno:"Moravcová Petra", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Urbanovský Petr", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Mikšík Antonín", n011:0, n1229:70, asfalt:20, n200:0, mezisouc:90, body:0, sleva:0, uhradit:90},
    ]
  },
  {
    zápas:"DC Monkey z 213 Praha", datum:"25.1.2026", celkem:0,
    hraci:[
      {jmeno:"Donát Petr", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Jeřábek Miroslav", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Jurenka Daniel", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Knoflíček Michal", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Zelinka Václav", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Moravcová Petra", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Urbanovský Petr", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Mikšík Antonín", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
    ]
  },
  {
    zápas:"Stiflerova máma Praha", datum:"18.1.2026", celkem:76,
    hraci:[
      {jmeno:"Donát Petr", n011:0, n1229:15, asfalt:0, n200:0, mezisouc:15, body:0, sleva:0, uhradit:15},
      {jmeno:"Jeřábek Miroslav", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Jurenka Daniel", n011:5, n1229:57, asfalt:30, n200:0, mezisouc:92, body:3, sleva:75, uhradit:23},
      {jmeno:"Knoflíček Michal", n011:0, n1229:48, asfalt:10, n200:0, mezisouc:58, body:4, sleva:100, uhradit:0},
      {jmeno:"Zelinka Václav", n011:10, n1229:66, asfalt:0, n200:0, mezisouc:76, body:2, sleva:50, uhradit:38},
      {jmeno:"Moravcová Petra", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Urbanovský Petr", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
      {jmeno:"Mikšík Antonín", n011:0, n1229:0, asfalt:0, n200:0, mezisouc:0, body:0, sleva:0, uhradit:0},
    ]
  },
];

// ===== POKLADNA DATA =====
const POKLADNA = [
  {datum:"Počáteční stav", celkem:2051, dluh:0, jmeno:"", vybrano:2051, vydaj:0, poznamka:""},
  {datum:"18.1.2026", celkem:76, dluh:0, jmeno:"", vybrano:76, vydaj:0, poznamka:"⚔️ Stiflerova máma Praha"},
  {datum:"25.1.2026", celkem:0, dluh:0, jmeno:"", vybrano:0, vydaj:0, poznamka:"⚔️ DC Monkey z 213 Praha"},
  {datum:"1.2.2026", celkem:312, dluh:0, jmeno:"", vybrano:312, vydaj:0, poznamka:"⚔️ Hostivar Darts Praha"},
  {datum:"8.2.2026", celkem:272, dluh:0, jmeno:"", vybrano:272, vydaj:0, poznamka:"⚔️ Worm Gang Praha"},
  {datum:"15.2.2026", celkem:197, dluh:95, jmeno:"Moravcová Petra", vybrano:102, vydaj:0, poznamka:"⚔️ Silent Darts Praha"},
  {datum:"22.2.2026", celkem:246, dluh:0, jmeno:"", vybrano:246, vydaj:0, poznamka:"⚔️ Clasico My Praha"},
  {datum:"1.3.2026", celkem:0, dluh:0, jmeno:"", vybrano:0, vydaj:0, poznamka:"⚔️ Stiflerova máma Modřany"},
  {datum:"29.3.2026", celkem:0, dluh:0, jmeno:"", vybrano:0, vydaj:0, poznamka:"⚔️ Žíznivý důchodci Praha"},
  {datum:"12.4.2026", celkem:0, dluh:0, jmeno:"", vybrano:0, vydaj:0, poznamka:"⚔️ Tempácký hroty Praha"},
  {datum:"19.4.2026", celkem:0, dluh:0, jmeno:"", vybrano:0, vydaj:0, poznamka:"⚔️ Otupělé hroty Praha"},
  {datum:"26.4.2026", celkem:0, dluh:0, jmeno:"", vybrano:0, vydaj:0, poznamka:"⚔️ Sedmá rota Praha B"},
  {datum:"5.5.2026", celkem:0, dluh:0, jmeno:"", vybrano:0, vydaj:0, poznamka:"⚔️ PLB Praha"},
];


// ===== RENDER FUNCTIONS =====

function renderMatches(data) {
  const tbody = document.getElementById('matchesTbody');
  tbody.innerHTML = '';
  data.forEach(m => {
    const vysl = m.vysl;
    let cls = '';
    if (vysl === '✅ V') cls = 'win';
    else if (vysl === '⚪ R') cls = 'draw';
    else if (vysl === '❌ P') cls = 'loss';
    const isHome = m.domaci.includes('5. Avenue');
    const tr = document.createElement('tr');
    tr.innerHTML = `
      <td class="rank-pos">${m.kolo}</td>
      <td style="color:var(--accent3);font-family:'Share Tech Mono',monospace">${m.datum}</td>
      <td style="${isHome?'color:var(--accent);font-weight:700':''}">${m.domaci}</td>
      <td style="${!isHome?'color:var(--accent);font-weight:700':''}">${m.hoste}</td>
      <td style="font-family:'Share Tech Mono',monospace">${m.body}</td>
      <td style="font-family:'Share Tech Mono',monospace">${m.legy}</td>
      <td style="font-family:'Share Tech Mono',monospace;color:var(--green)">${m.nase}</td>
      <td style="font-family:'Share Tech Mono',monospace;color:var(--text2)">${m.jejich}</td>
      <td class="${cls}" style="font-size:15px">${m.vysl}</td>
      <td style="color:var(--text2);font-size:12px">${m.misto}</td>
    `;
    tbody.appendChild(tr);
  });
}

function renderLiga() {
  const tbody = document.getElementById('ligaTbody');
  tbody.innerHTML = '';
  LIGA.forEach(t => {
    let rankCls = '';
    if (t.pos === 1) rankCls = 'rank-gold';
    else if (t.poradi.includes('Postup')) rankCls = 'rank-up';
    else if (t.poradi.includes('Ohrožení')) rankCls = 'rank-down';
    const tr = document.createElement('tr');
    if (t.nase) tr.className = 'our-team';
    tr.innerHTML = `
      <td class="rank-pos" style="${t.pos===1?'color:var(--yellow)':''}">
        ${t.pos===1?'🏆':t.pos===2||t.pos===3?'⬆️':''} ${t.pos}
      </td>
      <td style="font-weight:600">${t.tym}</td>
      <td style="color:var(--text2)">${t.z}</td>
      <td style="color:var(--green)">${t.v}</td>
      <td style="color:var(--yellow)">${t.r}</td>
      <td style="color:var(--red)">${t.p}</td>
      <td style="font-family:'Share Tech Mono',monospace;font-weight:bold;font-size:16px;color:var(--accent)">${t.body}</td>
      <td class="${rankCls}">${t.poradi}</td>
    `;
    tbody.appendChild(tr);
  });
}

function renderPlayerStats() {
  const tbody = document.getElementById('playerStatsTbody');
  tbody.innerHTML = '';
  PLAYERS_STATS.forEach((p, i) => {
    let pctColor = p.pct >= 0.6 ? 'var(--green)' : p.pct >= 0.4 ? 'var(--yellow)' : 'var(--red)';
    const tr = document.createElement('tr');
    if (i === 0) tr.className = 'top-performer';
    tr.innerHTML = `
      <td class="rank-pos">${p.pos}</td>
      <td style="font-weight:600">${p.jmeno}</td>
      <td style="color:var(--text2)">${p.kola}</td>
      <td style="color:var(--green)">${p.duelyV}</td>
      <td style="color:var(--red)">${p.duelyP}</td>
      <td style="color:${pctColor};font-family:'Share Tech Mono',monospace;font-weight:bold">${(p.pct*100).toFixed(1)}%</td>
      <td style="color:var(--green)">${p.legyV}</td>
      <td style="color:var(--red)">${p.legyP}</td>
      <td><span class="badge badge-blue">${p.p95}</span></td>
      <td><span class="badge badge-yellow">${p.p133}</span></td>
      <td><span class="badge ${p.p170>0?'badge-green':'badge-red'}">${p.p170}</span></td>
    `;
    tbody.appendChild(tr);
  });
}

function renderFines() {
  const container = document.getElementById('finesContainer');
  container.innerHTML = '';
  FINES.forEach((f, fi) => {
    const div = document.createElement('div');
    div.className = 'fine-match';
    const totalColor = f.celkem > 200 ? 'var(--red)' : f.celkem > 100 ? 'var(--yellow)' : 'var(--green)';
    div.innerHTML = `
      <div class="fine-match-header" onclick="toggleFine(this)">
        <div>
          <div class="fine-match-title">⚔️ ${f.zápas}</div>
          <div class="fine-match-date">📅 ${f.datum}</div>
        </div>
        <div style="display:flex;align-items:center;gap:20px">
          <div class="fine-match-total" style="color:${totalColor}">${f.celkem > 0 ? f.celkem.toFixed(2) + ' Kč' : '0 Kč'}</div>
          <span class="collapse-arrow">▼</span>
        </div>
      </div>
      <div class="fine-match-body">
        <div class="table-wrap" style="margin:8px">
          <table>
            <thead>
              <tr>
                <th>Hráč</th>
                <th>0-11 (5 Kč)</th>
                <th>12-29 (3 Kč)</th>
                <th>Asfalt (10 Kč)</th>
                <th>&gt;200 (20 Kč)</th>
                <th>Mezisoučet</th>
                <th>Body</th>
                <th>Sleva %</th>
                <th>K ÚHRADĚ</th>
              </tr>
            </thead>
            <tbody>
              ${f.hraci.map(h => `
                <tr style="${h.dluh?'background:rgba(255,51,102,0.08)':''}">
                  <td style="font-weight:600${h.dluh?';color:var(--red)':''}">${h.jmeno}${h.dluh?' ⚠️ DLUH':''}</td>
                  <td style="color:${h.n011>0?'var(--red)':'var(--text2)'}">${h.n011||'–'}</td>
                  <td style="color:${h.n1229>0?'var(--red)':'var(--text2)'}">${h.n1229||'–'}</td>
                  <td style="color:${h.asfalt>0?'var(--accent2)':'var(--text2)'}">${h.asfalt||'–'}</td>
                  <td style="color:${h.n200>0?'var(--red)':'var(--text2)'}">${h.n200||'–'}</td>
                  <td style="font-family:'Share Tech Mono',monospace;font-weight:bold">${h.mezisouc}</td>
                  <td style="color:var(--yellow)">${h.body}</td>
                  <td style="color:var(--green)">${h.sleva>0?h.sleva+'%':'–'}</td>
                  <td style="font-family:'Share Tech Mono',monospace;font-weight:bold;color:${h.uhradit>0?'var(--accent)':'var(--text2)'}">${h.uhradit.toFixed(2)} Kč</td>
                </tr>
              `).join('')}
            </tbody>
          </table>
        </div>
      </div>
    `;
    container.appendChild(div);
  });
}

function toggleFine(el) {
  const body = el.nextElementSibling;
  body.classList.toggle('open');
  el.classList.toggle('open-state');
}

function renderPokladna() {
  const tbody = document.getElementById('pokladnaTbody');
  tbody.innerHTML = '';
  POKLADNA.forEach(p => {
    const tr = document.createElement('tr');
    const hasDluh = p.dluh > 0;
    tr.innerHTML = `
      <td style="color:var(--accent3);font-family:'Share Tech Mono',monospace">${p.datum}</td>
      <td style="font-family:'Share Tech Mono',monospace;color:${p.celkem>0?'var(--green)':'var(--text2)'}">${p.celkem > 0 ? p.celkem + ' Kč' : '–'}</td>
      <td style="color:${hasDluh?'var(--red)':'var(--text2)'}${hasDluh?';font-weight:bold':''}">${hasDluh ? p.dluh + ' Kč' : '–'}</td>
      <td style="color:${hasDluh?'var(--red)':'var(--text2)'}">${p.jmeno||'–'}</td>
      <td style="color:var(--green);font-family:'Share Tech Mono',monospace">${p.vybrano > 0 ? p.vybrano + ' Kč' : '–'}</td>
      <td style="color:${p.vydaj>0?'var(--accent2)':'var(--text2)'}">${p.vydaj > 0 ? p.vydaj + ' Kč' : '–'}</td>
      <td style="color:var(--text2);font-size:12px">${p.poznamka||'–'}</td>
    `;
    tbody.appendChild(tr);
  });
}

function createContactCard(person, isManagement) {
  const hasFoto = PHOTOS[person.foto];
  const statsData = PLAYERS_STATS.find(p => {
    const pn = p.jmeno.toLowerCase();
    const cn = person.jmeno.toLowerCase();
    return pn === cn || cn.includes(pn.split(' ')[0].toLowerCase());
  });

  const card = document.createElement('div');
  card.className = 'player-card';

  const photoEl = hasFoto
    ? `<img src="${hasFoto}" class="player-photo" alt="${person.jmeno}" loading="lazy">`
    : `<div class="player-no-photo">🎯</div>`;

  const winPct = statsData ? (statsData.pct * 100).toFixed(1) : null;
  const winPctColor = statsData ? (statsData.pct >= 0.6 ? 'var(--green)' : statsData.pct >= 0.4 ? 'var(--yellow)' : 'var(--red)') : 'var(--text2)';

  const statsSection = statsData ? `
    <div class="player-stats">
      <div class="pstat">
        <div class="pstat-val">${statsData.duelyV}</div>
        <div class="pstat-lbl">Výher</div>
      </div>
      <div class="pstat">
        <div class="pstat-val">${statsData.duelyP}</div>
        <div class="pstat-lbl">Proher</div>
      </div>
      <div class="pstat">
        <div class="pstat-val" style="color:var(--accent2)">${statsData.p95}</div>
        <div class="pstat-lbl">95+</div>
      </div>
      <div class="pstat">
        <div class="pstat-val" style="color:var(--yellow)">${statsData.p133}</div>
        <div class="pstat-lbl">133+</div>
      </div>
    </div>
    <div class="win-bar">
      <div class="win-bar-label">
        <span>% Výher</span>
        <span style="color:${winPctColor};font-weight:bold">${winPct}%</span>
      </div>
      <div class="win-bar-track">
        <div class="win-bar-fill" style="width:${winPct}%"></div>
      </div>
    </div>
  ` : '';

  const emailBtn = person.email && person.email !== '-'
    ? `<a href="mailto:${person.email}" class="btn-contact btn-email">📧 Email</a>`
    : `<div class="btn-contact btn-email" style="opacity:0.3;cursor:not-allowed">📧 –</div>`;

  card.innerHTML = `
    <div class="player-header">
      ${photoEl}
      <div>
        <div class="player-name">${person.jmeno}</div>
        ${isManagement && person.funkce ? `<div class="player-role">${person.funkce}</div>` : ''}
        <div style="font-size:11px;color:var(--text2);margin-top:4px;font-family:'Share Tech Mono',monospace">${person.reg}</div>
      </div>
    </div>
    <div class="contact-info">
      <div>🏙️ <span>${person.obec}</span></div>
      ${person.email && person.email !== '-' ? `<div>📧 <span>${person.email}</span></div>` : ''}
      <div>📞 <span>${person.tel}</span></div>
      <div>✅ GDPR: <span>${person.gdpr}</span></div>
    </div>
    ${statsSection}
    <div class="contact-actions">
      <a href="tel:${person.tel}" class="btn-contact btn-call">📞 Volat</a>
      ${emailBtn}
    </div>
  `;
  return card;
}

function renderContacts() {
  const mgmtGrid = document.getElementById('managementGrid');
  MANAGEMENT.forEach(p => mgmtGrid.appendChild(createContactCard(p, true)));

  const playersGrid = document.getElementById('playersGrid');
  PLAYERS.forEach(p => playersGrid.appendChild(createContactCard(p, false)));
}

// ===== CHARTS =====
Chart.defaults.color = '#9898b0';
Chart.defaults.borderColor = '#2a2a40';

function renderCharts() {
  // Chart 1: Results pie
  new Chart(document.getElementById('chartResults'), {
    type: 'doughnut',
    data: {
      labels: ['Výhry', 'Remízy', 'Prohry'],
      datasets: [{
        data: [4, 3, 11],
        backgroundColor: ['rgba(0,255,136,0.7)', 'rgba(255,215,0,0.7)', 'rgba(255,51,102,0.7)'],
        borderColor: ['#00ff88', '#ffd700', '#ff3366'],
        borderWidth: 2,
      }]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      plugins: {
        legend: { labels: { color: '#e8e8f0', font: { family: 'Rajdhani', size: 14 } } }
      },
      animation: { animateRotate: true, duration: 1200 }
    }
  });

  // Chart 2: Win rate bar
  const playerNames = PLAYERS_STATS.map(p => p.jmeno.split(' ')[0]);
  const winRates = PLAYERS_STATS.map(p => +(p.pct * 100).toFixed(1));
  new Chart(document.getElementById('chartWinRate'), {
    type: 'bar',
    data: {
      labels: playerNames,
      datasets: [{
        label: '% Výher',
        data: winRates,
        backgroundColor: winRates.map(w => w >= 60 ? 'rgba(0,255,136,0.6)' : w >= 40 ? 'rgba(255,215,0,0.6)' : 'rgba(255,51,102,0.6)'),
        borderColor: winRates.map(w => w >= 60 ? '#00ff88' : w >= 40 ? '#ffd700' : '#ff3366'),
        borderWidth: 2,
        borderRadius: 4,
      }]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      scales: {
        y: { beginAtZero: true, max: 100, ticks: { callback: v => v + '%' } }
      },
      plugins: { legend: { display: false } },
      animation: { duration: 1000 }
    }
  });

  // Chart 3: Season progression
  const playedMatches = MATCHES.filter(m => m.vysl !== '–');
  let bodyNase = 0, bodyJejich = 0;
  const seasonLabels = [];
  const naseBody = [];
  const jejichBody = [];
  playedMatches.forEach(m => {
    if (typeof m.nase === 'number') {
      bodyNase += m.nase;
      bodyJejich += m.jejich;
    }
    seasonLabels.push('K' + m.kolo);
    naseBody.push(bodyNase);
    jejichBody.push(bodyJejich);
  });
  new Chart(document.getElementById('chartSeason'), {
    type: 'line',
    data: {
      labels: seasonLabels,
      datasets: [
        {
          label: '5. Avenue (naše)',
          data: naseBody,
          borderColor: '#e8b84b',
          backgroundColor: 'rgba(232,184,75,0.1)',
          fill: true,
          tension: 0.4,
          pointBackgroundColor: '#e8b84b',
          pointRadius: 4,
        },
        {
          label: 'Soupeři',
          data: jejichBody,
          borderColor: '#ff3366',
          backgroundColor: 'rgba(255,51,102,0.05)',
          fill: true,
          tension: 0.4,
          pointBackgroundColor: '#ff3366',
          pointRadius: 4,
        }
      ]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      plugins: { legend: { labels: { color: '#e8e8f0' } } },
      scales: { y: { beginAtZero: true } },
      animation: { duration: 1200 }
    }
  });

  // Chart 4: Fines by player
  const playerFines = {};
  FINES.forEach(f => {
    f.hraci.forEach(h => {
      const name = h.jmeno.split(' ')[0];
      playerFines[name] = (playerFines[name] || 0) + (h.uhradit || 0);
    });
  });
  const fineNames = Object.keys(playerFines);
  const fineAmounts = Object.values(playerFines);
  new Chart(document.getElementById('chartFines'), {
    type: 'bar',
    data: {
      labels: fineNames,
      datasets: [{
        label: 'Pokuty (Kč)',
        data: fineAmounts,
        backgroundColor: 'rgba(255,107,53,0.6)',
        borderColor: '#ff6b35',
        borderWidth: 2,
        borderRadius: 4,
      }]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      scales: { y: { beginAtZero: true, ticks: { callback: v => v + ' Kč' } } },
      plugins: { legend: { display: false } },
      animation: { duration: 1000 }
    }
  });

  // Chart 5: League standing horizontal bar
  const ligaNames = LIGA.map(t => t.tym.replace('🎯 ', ''));
  const ligaBody = LIGA.map(t => t.body);
  const ligaColors = LIGA.map(t => {
    if (t.pos === 1) return 'rgba(255,215,0,0.7)';
    if (t.poradi && t.poradi.includes('Postup')) return 'rgba(0,255,136,0.6)';
    if (t.poradi && t.poradi.includes('Ohrožení')) return 'rgba(255,51,102,0.6)';
    if (t.nase) return 'rgba(232,184,75,0.7)';
    return 'rgba(0,212,255,0.4)';
  });
  new Chart(document.getElementById('chartLeague'), {
    type: 'bar',
    data: {
      labels: ligaNames,
      datasets: [{
        label: 'Body',
        data: ligaBody,
        backgroundColor: ligaColors,
        borderColor: ligaColors.map(c => c.replace('0.6','1').replace('0.7','1').replace('0.4','1')),
        borderWidth: 1,
        borderRadius: 3,
      }]
    },
    options: {
      indexAxis: 'y',
      responsive: true, maintainAspectRatio: false,
      scales: { x: { beginAtZero: true } },
      plugins: { legend: { display: false } },
      animation: { duration: 1200 }
    }
  });

  // Chart 6: Legs win/loss grouped
  const legNames = PLAYERS_STATS.map(p => p.jmeno.split(' ')[0]);
  new Chart(document.getElementById('chartLegs'), {
    type: 'bar',
    data: {
      labels: legNames,
      datasets: [
        { label: 'Legy V', data: PLAYERS_STATS.map(p => p.legyV), backgroundColor: 'rgba(0,255,136,0.6)', borderColor: '#00ff88', borderWidth: 1, borderRadius: 4 },
        { label: 'Legy P', data: PLAYERS_STATS.map(p => p.legyP), backgroundColor: 'rgba(255,51,102,0.6)', borderColor: '#ff3366', borderWidth: 1, borderRadius: 4 }
      ]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      scales: { y: { beginAtZero: true } },
      plugins: { legend: { labels: { color: '#e8e8f0' } } },
      animation: { duration: 1000 }
    }
  });
}

// ===== SEARCH / FILTER =====
function setupMatchesFilter() {
  const searchInput = document.getElementById('searchMatches');
  const filterResult = document.getElementById('filterResult');

  function applyFilter() {
    const q = searchInput.value.toLowerCase();
    const f = filterResult.value;
    const filtered = MATCHES.filter(m => {
      const matchText = (m.domaci + m.hoste + m.misto).toLowerCase();
      const matchSearch = !q || matchText.includes(q);
      const matchFilter = !f || m.vysl.includes(f);
      return matchSearch && matchFilter;
    });
    renderMatches(filtered);
  }

  searchInput.addEventListener('input', applyFilter);
  filterResult.addEventListener('change', applyFilter);
}

// ===== PARTICLES =====
function createParticles() {
  const container = document.getElementById('particles');
  for (let i = 0; i < 25; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    p.style.left = Math.random() * 100 + '%';
    p.style.animationDuration = (8 + Math.random() * 15) + 's';
    p.style.animationDelay = (Math.random() * 15) + 's';
    p.style.width = (1 + Math.random() * 3) + 'px';
    p.style.height = p.style.width;
    p.style.opacity = 0.1 + Math.random() * 0.3;
    container.appendChild(p);
  }
}

// ===== INTERSECTION OBSERVER (fade-in) =====
function setupAnimations() {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.fade-in, .player-card, .chart-card, .finance-card').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(20px)';
    el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    observer.observe(el);
  });
}

// ===== COUNTER ANIMATION =====
function animateCounter(el, target, suffix='') {
  let start = 0;
  const duration = 1500;
  const step = target / (duration / 16);
  const timer = setInterval(() => {
    start += step;
    if (start >= target) { start = target; clearInterval(timer); }
    el.textContent = Math.floor(start) + suffix;
  }, 16);
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', () => {
  createParticles();
  renderMatches(MATCHES);
  renderLiga();
  renderPlayerStats();
  renderFines();
  renderPokladna();
  renderContacts();
  renderCharts();
  setupMatchesFilter();

  // Trigger animations after short delay
  setTimeout(setupAnimations, 100);
});
</script>
</body>
</html>
import { useState, useMemo, useEffect } from "react";

// ─── SEASON DATA ──────────────────────────────────────────────────────────────
const NASI_HRACI = ["Donát Petr","Jurenka Daniel","Zelinka Václav","Knoflíček Michal","Moravcová Petra","Jeřábek Miroslav","Mikšík Antonín","Urbanovský Petr"];

const SOUPEŘI = ["Stiflerova máma Praha","Monkey z 213 Praha","Hostivar Darts Praha","Worm Gang Praha","Silent Darts Praha","Clasico My Praha","Stiflerova máma Modřany","Žíznivý důchodci Praha","Tempácký hroty Praha","Otupělé hroty Praha","Sedmá rota Praha B","PLB Praha"];

const MISTNOSTI = ["5. Avenue","Club bar Pomeranč","Pivní bar Palma","Hospoda reSTART","Restaurace Alfa","Hotel Cham","Pivnice Pipkin","Hospoda 213","Jiné"];

// Completed matches data
const MATCHES_DATA = [
  {kolo:1,datum:"07.09.2025",misto:"Club bar Pomeranč",my:"Host",soupere:"Stiflerova máma Praha",skore_my:6,skore_soupere:12,
   hraci_my:{H1:"Jeřábek Miroslav",H2:"Zelinka Václav",H3:"Jurenka Daniel",H4:"Donát Petr",H5:"Moravcová Petra"},
   hraci_soupere:{D1:"Kapasná Hana",D2:"Padevět Jakub",D3:"Kapasný Vít",D4:"Žižka Václav"},
   stats:{}, singles:[{n:1,d:"D1",h:"H3",l:"1:2"},{n:2,d:"D2",h:"H4",l:"0:2"},{n:3,d:"D3",h:"H1",l:"2:0"},{n:4,d:"D4",h:"H2",l:"2:1"},{n:5,d:"D1",h:"H4",l:"0:2"},{n:6,d:"D2",h:"H3",l:"0:2"},{n:7,d:"D3",h:"H2",l:"0:2"},{n:8,d:"D4",h:"H1",l:"2:0"},{n:11,d:"D1",h:"H2",l:"0:2"},{n:12,d:"D2",h:"H1",l:"0:2"},{n:13,d:"D3",h:"H4",l:"0:2"},{n:14,d:"D4",h:"H3",l:"2:0"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"2:0"},{n:18,d:"D4",h:"H4",l:"1:2"}],
   dc:[{num:9,type:"D",score:"0:2",terče:[{d:"D1+D3",h:"H1+H5"},{d:"D2+D4",h:"H3+H4"}]},{num:10,type:"CR",score:"2:1",terče:[{d:"D3+D4",h:"H1+H4"},{d:"D1+D2",h:"H2+H3"},{d:"D3+D4",h:"H1+H4",rozh:true}]}]},
  {kolo:2,datum:"14.09.2025",misto:"5. Avenue",my:"Domácí",soupere:"Monkey z 213 Praha",skore_my:9,skore_soupere:9,
   hraci_my:{D1:"Donát Petr",D2:"Zelinka Václav",D3:"Knoflíček Michal",D4:"Jurenka Daniel"},
   hraci_soupere:{H1:"Kolárovec Jan",H2:"Volf Lukáš",H3:"Coufal Michal",H4:"Hrad Daniel"},
   stats:{},singles:[{n:1,d:"D1",h:"H3",l:"2:0"},{n:2,d:"D2",h:"H4",l:"2:1"},{n:3,d:"D3",h:"H1",l:"0:2"},{n:4,d:"D4",h:"H2",l:"1:2"},{n:5,d:"D1",h:"H4",l:"2:0"},{n:6,d:"D2",h:"H3",l:"0:2"},{n:7,d:"D3",h:"H2",l:"2:0"},{n:8,d:"D4",h:"H1",l:"0:2"},{n:11,d:"D1",h:"H2",l:"2:0"},{n:12,d:"D2",h:"H1",l:"1:2"},{n:13,d:"D3",h:"H4",l:"0:2"},{n:14,d:"D4",h:"H3",l:"2:1"},{n:15,d:"D1",h:"H2",l:"2:0"},{n:16,d:"D2",h:"H3",l:"0:2"},{n:17,d:"D3",h:"H1",l:"2:1"},{n:18,d:"D4",h:"H4",l:"0:2"}],
   dc:[{num:9,type:"D",score:"0:2",terče:[{d:"D1+D4",h:"H1+H4"},{d:"D2+D3",h:"H2+H3"}]},{num:10,type:"CR",score:"1:2",terče:[{d:"D1+D3",h:"H3+H4"},{d:"D2+D4",h:"H1+H2"},{d:"D1+D3",h:"H3+H4",rozh:true}]}]},
  {kolo:3,datum:"16.09.2025",misto:"Pivní bar Palma",my:"Host",soupere:"Hostivar Darts Praha",skore_my:7,skore_soupere:11,
   hraci_my:{H1:"Knoflíček Michal",H2:"Urbanovský Petr",H3:"Moravcová Petra",H4:"Donát Petr",H5:"Jurenka Daniel"},
   hraci_soupere:{D1:"Homola Radek",D2:"Sabo Jan",D3:"Železný Martin",D4:"Kříž František",D5:"Lukš Jiří"},
   stats:{},singles:[{n:1,d:"D1",h:"H1",l:"2:1"},{n:2,d:"D2",h:"H2",l:"2:0"},{n:3,d:"D3",h:"H3",l:"2:1"},{n:4,d:"D4",h:"H4",l:"2:0"},{n:5,d:"D1",h:"H2",l:"1:2"},{n:6,d:"D2",h:"H3",l:"0:2"},{n:7,d:"D3",h:"H4",l:"0:2"},{n:8,d:"D4",h:"H1",l:"2:0"},{n:11,d:"D1",h:"H2",l:"2:1"},{n:12,d:"D2",h:"H1",l:"0:2"},{n:13,d:"D3",h:"H4",l:"2:0"},{n:14,d:"D4",h:"H5",l:"0:2"},{n:15,d:"D1",h:"H3",l:"2:0"},{n:16,d:"D2",h:"H5",l:"2:0"},{n:17,d:"D3",h:"H1",l:"0:2"},{n:18,d:"D4",h:"H2",l:"2:1"}],
   dc:[{num:9,type:"D",score:"2:0",terče:[{d:"D1+D4",h:"H4+H5"},{d:"D2+D5",h:"H2+H3"}]},{num:10,type:"CR",score:"2:0",terče:[{d:"D2+D4",h:"H2+H5"},{d:"D1+D3",h:"H1+H4"}]}]},
  {kolo:4,datum:"28.09.2025",misto:"5. Avenue",my:"Domácí",soupere:"Worm Gang Praha",skore_my:9,skore_soupere:9,
   hraci_my:{D1:"Jeřábek Miroslav",D2:"Donát Petr",D3:"Knoflíček Michal",D4:"Zelinka Václav",D5:"Moravcová Petra"},
   hraci_soupere:{H1:"Novotná Hana",H2:"Koubek Martin",H3:"Dupal Jan",H4:"Kalenský Martin"},
   stats:{},singles:[{n:1,d:"D1",h:"H3",l:"2:1"},{n:2,d:"D2",h:"H4",l:"2:0"},{n:3,d:"D3",h:"H1",l:"2:0"},{n:4,d:"D4",h:"H2",l:"0:2"},{n:5,d:"D1",h:"H4",l:"2:0"},{n:6,d:"D2",h:"H3",l:"2:0"},{n:7,d:"D3",h:"H2",l:"2:0"},{n:8,d:"D4",h:"H1",l:"0:2"},{n:11,d:"D1",h:"H2",l:"2:1"},{n:12,d:"D2",h:"H1",l:"0:2"},{n:13,d:"D3",h:"H4",l:"0:2"},{n:14,d:"D4",h:"H3",l:"2:0"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"2:0"},{n:17,d:"D3",h:"H3",l:"2:1"},{n:18,d:"D4",h:"H4",l:"1:2"}],
   dc:[{num:9,type:"D",score:"2:1",terče:[{d:"D1+D5",h:"H4+H3"},{d:"D2+D4",h:"H1+H2"},{d:"D2+D3",h:"H3+H1",rozh:true}]},{num:10,type:"CR",score:"2:1",terče:[{d:"D1+D4",h:"H2+H4"},{d:"D2+D3",h:"H1+H3"},{d:"D1+D3",h:"H2+H4",rozh:true}]}]},
  {kolo:5,datum:"12.10.2025",misto:"Hospoda reSTART",my:"Host",soupere:"Silent Darts Praha",skore_my:4,skore_soupere:14,
   hraci_my:{H1:"Knoflíček Michal",H2:"Zelinka Václav",H3:"Jurenka Daniel",H4:"Donát Petr"},
   hraci_soupere:{D1:"Korábečný Petr",D2:"Kulich Pavel",D3:"Zimmermann Jakub",D4:"Várka Jan",D5:"Krupka Jiří"},
   stats:{},singles:[{n:1,d:"D1",h:"H1",l:"2:1"},{n:2,d:"D2",h:"H2",l:"0:2"},{n:3,d:"D3",h:"H3",l:"0:2"},{n:4,d:"D4",h:"H1",l:"2:1"},{n:5,d:"D1",h:"H2",l:"0:2"},{n:6,d:"D2",h:"H3",l:"2:0"},{n:7,d:"D3",h:"H4",l:"0:2"},{n:8,d:"D4",h:"H1",l:"2:1"},{n:11,d:"D1",h:"H2",l:"0:2"},{n:12,d:"D2",h:"H1",l:"2:0"},{n:13,d:"D3",h:"H4",l:"0:2"},{n:14,d:"D4",h:"H3",l:"0:2"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"0:2"},{n:18,d:"D4",h:"H2",l:"0:2"}],
   dc:[{num:9,type:"D",score:"2:0",terče:[{d:"D1+D5",h:"H2+H3"},{d:"D2+D4",h:"H1+H2"}]},{num:10,type:"CR",score:"2:0",terče:[{d:"D3+D4",h:"H1+H2"},{d:"D1+D2",h:"H2+H3"}]}]},
  {kolo:6,datum:"19.10.2025",misto:"Restaurace Alfa",my:"Host",soupere:"Clasico My Praha",skore_my:4,skore_soupere:14,
   hraci_my:{H1:"Moravcová Petra",H2:"Jurenka Daniel",H3:"Zelinka Václav",H4:"Donát Petr"},
   hraci_soupere:{D1:"Selucký Josef",D2:"Šál Petr",D3:"Dlouhý Milan",D4:"Henner Martin"},
   stats:{},singles:[{n:1,d:"D1",h:"H1",l:"0:2"},{n:2,d:"D2",h:"H2",l:"0:2"},{n:3,d:"D3",h:"H3",l:"0:2"},{n:4,d:"D4",h:"H4",l:"2:0"},{n:5,d:"D1",h:"H4",l:"0:2"},{n:6,d:"D2",h:"H3",l:"0:2"},{n:7,d:"D3",h:"H2",l:"0:2"},{n:8,d:"D4",h:"H1",l:"2:0"},{n:11,d:"D1",h:"H2",l:"0:2"},{n:12,d:"D2",h:"H1",l:"2:0"},{n:13,d:"D3",h:"H4",l:"0:2"},{n:14,d:"D4",h:"H3",l:"2:0"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"0:2"},{n:18,d:"D4",h:"H4",l:"0:2"}],
   dc:[{num:9,type:"D",score:"2:0",terče:[{d:"D3+D4",h:"H2+H4"},{d:"D1+D2",h:"H1+H3"}]},{num:10,type:"CR",score:"2:0",terče:[{d:"D1+D3",h:"H1+H2"},{d:"D2+D4",h:"H3+H4"}]}]},
  {kolo:7,datum:"02.11.2025",misto:"5. Avenue",my:"Domácí",soupere:"Stiflerova máma Modřany",skore_my:14,skore_soupere:4,
   hraci_my:{D1:"Donát Petr",D2:"Jurenka Daniel",D3:"Knoflíček Michal",D4:"Zelinka Václav",D5:"Jeřábek Miroslav"},
   hraci_soupere:{H1:"Kabátek Václav",H2:"Dvořák Aleš",H3:"Bělohlávek Václav",H4:"Pitelka Vladimír",H5:"Peková Žaneta"},
   stats:{},singles:[{n:1,d:"D1",h:"H3",l:"2:0"},{n:2,d:"D2",h:"H4",l:"1:2"},{n:3,d:"D3",h:"H1",l:"2:1"},{n:4,d:"D4",h:"H2",l:"1:2"},{n:5,d:"D1",h:"H4",l:"2:0"},{n:6,d:"D2",h:"H3",l:"2:0"},{n:7,d:"D3",h:"H2",l:"2:0"},{n:8,d:"D4",h:"H1",l:"2:0"},{n:11,d:"D1",h:"H2",l:"2:0"},{n:12,d:"D2",h:"H5",l:"2:0"},{n:13,d:"D3",h:"H4",l:"2:0"},{n:14,d:"D5",h:"H3",l:"1:2"},{n:15,d:"D1",h:"H5",l:"2:1"},{n:16,d:"D2",h:"H2",l:"2:0"},{n:17,d:"D3",h:"H3",l:"2:0"},{n:18,d:"D5",h:"H4",l:"0:2"}],
   dc:[{num:9,type:"D",score:"2:1",terče:[{d:"D3+D5",h:"H3+H4"},{d:"D1+D2",h:"H1+H5"},{d:"D1+D3",h:"H1+H4",rozh:true}]},{num:10,type:"CR",score:"2:0",terče:[{d:"D4+D5",h:"H2+H3"},{d:"D1+D3",h:"H1+H4"}]}]},
  {kolo:9,datum:"23.11.2025",misto:"5. Avenue",my:"Domácí",soupere:"Žíznivý důchodci Praha",skore_my:12,skore_soupere:6,
   hraci_my:{D1:"Donát Petr",D2:"Jurenka Daniel",D3:"Zelinka Václav",D4:"Moravcová Petra"},
   hraci_soupere:{H1:"Janeček Petr",H2:"Zeman Jiří",H3:"Neoveský Jan",H4:"Červinka Michal",H5:"Šťastný Petr"},
   stats:{},singles:[{n:1,d:"D1",h:"H3",l:"2:0"},{n:2,d:"D2",h:"H4",l:"2:0"},{n:3,d:"D3",h:"H1",l:"2:1"},{n:4,d:"D4",h:"H2",l:"2:0"},{n:5,d:"D1",h:"H4",l:"2:1"},{n:6,d:"D2",h:"H3",l:"0:2"},{n:7,d:"D3",h:"H2",l:"2:0"},{n:8,d:"D4",h:"H1",l:"0:2"},{n:11,d:"D1",h:"H2",l:"2:1"},{n:12,d:"D2",h:"H3",l:"0:2"},{n:13,d:"D3",h:"H4",l:"2:0"},{n:14,d:"D4",h:"H5",l:"2:0"},{n:15,d:"D1",h:"H5",l:"2:1"},{n:16,d:"D2",h:"H2",l:"2:0"},{n:17,d:"D3",h:"H3",l:"2:1"},{n:18,d:"D4",h:"H4",l:"0:2"}],
   dc:[{num:9,type:"D",score:"2:1",terče:[{d:"D3+D4",h:"H5+H1"},{d:"D1+D2",h:"H3+H4"},{d:"D1+D3",h:"H5+H3",rozh:true}]},{num:10,type:"CR",score:"2:1",terče:[{d:"D2+D4",h:"H1+H4"},{d:"D1+D3",h:"H5+H3"},{d:"D1+D3",h:"H1+H4",rozh:true}]}]},
  {kolo:10,datum:"07.12.2025",misto:"Hotel Cham",my:"Host",soupere:"Tempácký hroty Praha",skore_my:6,skore_soupere:12,
   hraci_my:{H1:"Zelinka Václav",H2:"Jurenka Daniel",H3:"Knoflíček Michal",H4:"Donát Petr",H5:"Mikšík Antonín"},
   hraci_soupere:{D1:"Kejvalová Natálie",D2:"Michlík Michal",D3:"Pytlíček Martin",D4:"Michlík Michal 71",D5:"Trajhan Jáchym"},
   stats:{},singles:[{n:1,d:"D1",h:"H3",l:"0:2"},{n:2,d:"D2",h:"H4",l:"0:2"},{n:3,d:"D3",h:"H1",l:"0:2"},{n:4,d:"D4",h:"H2",l:"2:1"},{n:5,d:"D1",h:"H4",l:"0:2"},{n:6,d:"D2",h:"H3",l:"0:2"},{n:7,d:"D3",h:"H2",l:"0:2"},{n:8,d:"D4",h:"H1",l:"2:1"},{n:11,d:"D1",h:"H2",l:"2:0"},{n:12,d:"D5",h:"H2",l:"0:2"},{n:13,d:"D3",h:"H4",l:"0:2"},{n:14,d:"D5",h:"H3",l:"2:1"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"0:2"},{n:18,d:"D5",h:"H4",l:"0:2"}],
   dc:[{num:9,type:"D",score:"2:0",terče:[{d:"D1+D3",h:"H1+H3"},{d:"D4+D5",h:"H2+H4"}]},{num:10,type:"CR",score:"1:2",terče:[{d:"D2+D4",h:"H3+H4"},{d:"D1+D3",h:"H1+H2"},{d:"D1+D3",h:"H3+H4",rozh:true}]}]},
  {kolo:11,datum:"14.12.2025",misto:"5. Avenue",my:"Host",soupere:"Otupělé hroty Praha",skore_my:3,skore_soupere:15,
   hraci_my:{H1:"Zelinka Václav",H2:"Jurenka Daniel",H3:"Knoflíček Michal",H4:"Donát Petr"},
   hraci_soupere:{D1:"Novák Petr",D2:"Jirásek Jiří",D3:"Kripner Tomáš",D4:"Zelenková Michaela",D5:"Jirásek Jiří",D6:"Verner Jiří"},
   stats:{},singles:[{n:1,d:"D3",h:"H1",l:"2:0"},{n:2,d:"D1",h:"H2",l:"2:0"},{n:3,d:"D3",h:"H3",l:"2:0"},{n:4,d:"D1",h:"H4",l:"1:2"},{n:5,d:"D3",h:"H2",l:"2:1"},{n:6,d:"D1",h:"H3",l:"0:2"},{n:7,d:"D3",h:"H4",l:"2:0"},{n:8,d:"D1",h:"H4",l:"2:1"},{n:11,d:"D6",h:"H1",l:"2:1"},{n:12,d:"D1",h:"H2",l:"2:0"},{n:13,d:"D3",h:"H4",l:"2:0"},{n:14,d:"D3",h:"H3",l:"2:1"},{n:15,d:"D3",h:"H1",l:"2:0"},{n:16,d:"D1",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"2:0"},{n:18,d:"D1",h:"H4",l:"0:2"}],
   dc:[{num:9,type:"D",score:"1:2",terče:[{d:"D1+D3",h:"H3+H6"},{d:"D2+D4",h:"H1+H5"},{d:"D3+D4",h:"H3+H5",rozh:true}]},{num:10,type:"CR",score:"1:2",terče:[{d:"D1+D2",h:"H4+H6"},{d:"D3+D4",h:"H3+H5"},{d:"D1+D2",h:"H4+H6",rozh:true}]}]},
  {kolo:12,datum:"21.12.2025",misto:"Pivnice Pipkin",my:"Host",soupere:"Sedmá rota Praha B",skore_my:3,skore_soupere:15,
   hraci_my:{H1:"Jeřábek Miroslav",H2:"Knoflíček Michal",H3:"Zelinka Václav",H4:"Jurenka Daniel"},
   hraci_soupere:{D1:"Královič Martin",D2:"Knotek Václav",D3:"Hamšík Robert",D4:"Puková Jaroslava",D5:"Polák Michal",D8:"Zbořil Karel"},
   stats:{},singles:[{n:1,d:"D1",h:"H1",l:"2:0"},{n:2,d:"D2",h:"H2",l:"0:2"},{n:3,d:"D1",h:"H3",l:"0:2"},{n:4,d:"D4",h:"H4",l:"2:1"},{n:5,d:"D1",h:"H2",l:"2:0"},{n:6,d:"D2",h:"H3",l:"0:2"},{n:7,d:"D1",h:"H4",l:"0:2"},{n:8,d:"D4",h:"H1",l:"2:1"},{n:11,d:"D1",h:"H2",l:"2:0"},{n:12,d:"D2",h:"H1",l:"0:2"},{n:13,d:"D3",h:"H4",l:"2:0"},{n:14,d:"D5",h:"H3",l:"0:2"},{n:15,d:"D1",h:"H1",l:"2:0"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"2:0"},{n:18,d:"D4",h:"H4",l:"2:1"}],
   dc:[{num:9,type:"D",score:"2:1",terče:[{d:"D1+D5",h:"H1+H2"},{d:"D3+D4",h:"H3+H4"},{d:"D1+D2",h:"H2+H3",rozh:true}]},{num:10,type:"CR",score:"2:0",terče:[{d:"D4+D8",h:"H1+H4"},{d:"D1+D2",h:"H2+H3"}]}]},
  {kolo:13,datum:"04.01.2026",misto:"5. Avenue",my:"Domácí",soupere:"PLB Praha",skore_my:8,skore_soupere:10,
   hraci_my:{D1:"Donát Petr",D2:"Jurenka Daniel",D3:"Knoflíček Michal",D4:"Zelinka Václav"},
   hraci_soupere:{H1:"Žáček Jan",H2:"Littman Petr",H3:"Hrachovina Matěj",H4:"Novák Ondřej"},
   stats:{},singles:[{n:1,d:"D1",h:"H3",l:"2:0"},{n:2,d:"D2",h:"H4",l:"0:2"},{n:3,d:"D3",h:"H1",l:"2:0"},{n:4,d:"D4",h:"H2",l:"0:2"},{n:5,d:"D1",h:"H4",l:"0:2"},{n:6,d:"D2",h:"H3",l:"2:0"},{n:7,d:"D3",h:"H2",l:"2:0"},{n:8,d:"D4",h:"H1",l:"0:2"},{n:11,d:"D1",h:"H2",l:"2:0"},{n:12,d:"D2",h:"H1",l:"0:2"},{n:13,d:"D3",h:"H4",l:"0:2"},{n:14,d:"D4",h:"H3",l:"2:0"},{n:15,d:"D1",h:"H1",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"0:2"},{n:18,d:"D4",h:"H4",l:"2:0"}],
   dc:[{num:9,type:"D",score:"0:2",terče:[{d:"D1+D3",h:"H1+H4"},{d:"D2+D4",h:"H2+H3"}]},{num:10,type:"CR",score:"2:1",terče:[{d:"D1+D3",h:"H3+H4"},{d:"D2+D4",h:"H1+H2"},{d:"D1+D3",h:"H2+H3",rozh:true}]}]},
  {kolo:14,datum:"11.01.2026",misto:"5. Avenue",my:"Domácí",soupere:"Stiflerova máma Praha",skore_my:14,skore_soupere:4,
   hraci_my:{D1:"Donát Petr",D2:"Jurenka Daniel",D3:"Knoflíček Michal",D4:"Zelinka Václav"},
   hraci_soupere:{H1:"Větrovec Tomáš",H2:"Vrňata Tomáš",H3:"Kapasný Vít",H4:"Žižka Václav"},
   stats:{},singles:[{n:1,d:"D1",h:"H3",l:"2:0"},{n:2,d:"D2",h:"H4",l:"2:0"},{n:3,d:"D3",h:"H1",l:"2:0"},{n:4,d:"D4",h:"H2",l:"1:2"},{n:5,d:"D1",h:"H4",l:"2:0"},{n:6,d:"D2",h:"H3",l:"2:0"},{n:7,d:"D3",h:"H2",l:"2:0"},{n:8,d:"D4",h:"H1",l:"1:2"},{n:11,d:"D1",h:"H2",l:"2:0"},{n:12,d:"D2",h:"H1",l:"2:1"},{n:13,d:"D3",h:"H4",l:"2:0"},{n:14,d:"D4",h:"H3",l:"2:0"},{n:15,d:"D1",h:"H5",l:"2:0"},{n:16,d:"D2",h:"H2",l:"2:0"},{n:17,d:"D3",h:"H3",l:"2:0"},{n:18,d:"D4",h:"H4",l:"0:2"}],
   dc:[{num:9,type:"D",score:"1:2",terče:[{d:"D1+D2",h:"H1+H4"},{d:"D3+D4",h:"H2+H3"},{d:"D1+D3",h:"H1+H2",rozh:true}]},{num:10,type:"CR",score:"2:1",terče:[{d:"D1+D3",h:"H1+H2"},{d:"D2+D4",h:"H3+H4"},{d:"D1+D3",h:"H2+H3",rozh:true}]}]},
  {kolo:15,datum:"25.01.2026",misto:"Hospoda 213",my:"Host",soupere:"Monkey z 213 Praha",skore_my:9,skore_soupere:9,
   hraci_my:{H1:"Knoflíček Michal",H2:"Jurenka Daniel",H3:"Donát Petr",H4:"Zelinka Václav"},
   hraci_soupere:{D1:"Hrad Daniel",D2:"Kolárovec Jan",D3:"Hrad Daniel",D4:"Coufal Michal",D6:"Pastorčák Lukáš"},
   stats:{},singles:[{n:1,d:"D1",h:"H1",l:"0:2"},{n:2,d:"D2",h:"H2",l:"0:2"},{n:3,d:"D3",h:"H3",l:"0:2"},{n:4,d:"D4",h:"H4",l:"2:1"},{n:5,d:"D1",h:"H4",l:"0:2"},{n:6,d:"D2",h:"H3",l:"2:0"},{n:7,d:"D3",h:"H2",l:"0:2"},{n:8,d:"D4",h:"H1",l:"2:1"},{n:11,d:"D6",h:"H2",l:"2:1"},{n:12,d:"D2",h:"H1",l:"0:2"},{n:13,d:"D1",h:"H4",l:"0:2"},{n:14,d:"D3",h:"H3",l:"0:2"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"2:0"},{n:18,d:"D4",h:"H4",l:"2:1"}],
   dc:[{num:9,type:"D",score:"0:2",terče:[{d:"D3+D4",h:"H1+H4"},{d:"D2+D6",h:"H2+H3"}]},{num:10,type:"CR",score:"2:0",terče:[{d:"D4+D6",h:"H2+H4"},{d:"D2+D3",h:"H1+H3"}]}]},
  {kolo:16,datum:"01.02.2026",misto:"5. Avenue",my:"Domácí",soupere:"Hostivar Darts Praha",skore_my:2,skore_soupere:16,
   hraci_my:{D1:"Zelinka Václav",D2:"Mikšík Antonín",D3:"Jurenka Daniel",D4:"Knoflíček Michal"},
   hraci_soupere:{H1:"Železný Martin",H2:"Sabo Jan",H3:"Kříž František",H4:"Homola Radek",H5:"Roza Adam"},
   stats:{},singles:[{n:1,d:"D1",h:"H3",l:"0:2"},{n:2,d:"D2",h:"H4",l:"0:2"},{n:3,d:"D3",h:"H1",l:"0:2"},{n:4,d:"D4",h:"H2",l:"0:2"},{n:5,d:"D1",h:"H4",l:"0:2"},{n:6,d:"D2",h:"H3",l:"0:2"},{n:7,d:"D3",h:"H2",l:"0:2"},{n:8,d:"D4",h:"H1",l:"1:2"},{n:11,d:"D1",h:"H2",l:"0:2"},{n:12,d:"D2",h:"H1",l:"0:2"},{n:13,d:"D3",h:"H4",l:"0:2"},{n:14,d:"D4",h:"H3",l:"2:0"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"0:2"},{n:18,d:"D4",h:"H4",l:"0:2"}],
   dc:[{num:9,type:"D",score:"2:0",terče:[{d:"D1+D2",h:"H1+H2"},{d:"D3+D4",h:"H4+H5"}]},{num:10,type:"CR",score:"1:2",terče:[{d:"D2+D3",h:"H1+H4"},{d:"D1+D4",h:"H2+H3"},{d:"D2+D3",h:"H1+H4",rozh:true}]}]},
  {kolo:17,datum:"08.02.2026",misto:"5. Avenue",my:"Host",soupere:"Worm Gang Praha",skore_my:5,skore_soupere:13,
   hraci_my:{H1:"Knoflíček Michal",H2:"Zelinka Václav",H3:"Jurenka Daniel",H4:"Donát Petr",H5:"Mikšík Antonín"},
   hraci_soupere:{D1:"Novotná Hana",D2:"Koubek Martin",D3:"Zazvonil Zdeněk",D4:"Dolínek Václav",D5:"Kalenský Martin"},
   stats:{},singles:[{n:1,d:"D1",h:"H1",l:"0:2"},{n:2,d:"D2",h:"H2",l:"0:2"},{n:3,d:"D3",h:"H3",l:"2:0"},{n:4,d:"D4",h:"H4",l:"2:0"},{n:5,d:"D1",h:"H4",l:"0:2"},{n:6,d:"D2",h:"H3",l:"2:1"},{n:7,d:"D3",h:"H2",l:"2:0"},{n:8,d:"D4",h:"H1",l:"2:0"},{n:11,d:"D1",h:"H2",l:"2:0"},{n:12,d:"D2",h:"H3",l:"2:0"},{n:13,d:"D3",h:"H4",l:"0:2"},{n:14,d:"D4",h:"H1",l:"2:0"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"0:2"},{n:18,d:"D4",h:"H4",l:"2:0"}],
   dc:[{num:9,type:"D",score:"2:0",terče:[{d:"D3+D5",h:"H1+H5"},{d:"D1+D4",h:"H1+H4"}]},{num:10,type:"CR",score:"2:0",terče:[{d:"D2+D3",h:"H2+H5"},{d:"D1+D4",h:"H1+H4"}]}]},
  {kolo:18,datum:"15.02.2026",misto:"Hospoda reSTART",my:"Host",soupere:"Silent Darts Praha",skore_my:8,skore_soupere:10,
   hraci_my:{H1:"Zelinka Václav",H2:"Kulich Pavel",H3:"Benko Zdeněk",H4:"Várka Jan",H5:"Andr Jan"},
   hraci_soupere:{D1:"Zelinka Václav",D2:"Moravcová Petra",D3:"Knoflíček Michal",D4:"Donát Petr"},
   stats:{},singles:[{n:1,d:"D1",h:"H1",l:"0:2"},{n:2,d:"D2",h:"H2",l:"0:2"},{n:3,d:"D3",h:"H3",l:"2:0"},{n:4,d:"D4",h:"H4",l:"0:2"},{n:5,d:"D1",h:"H2",l:"0:2"},{n:6,d:"D2",h:"H3",l:"0:2"},{n:7,d:"D3",h:"H4",l:"0:2"},{n:8,d:"D4",h:"H1",l:"2:0"},{n:11,d:"D1",h:"H2",l:"0:2"},{n:12,d:"D2",h:"H1",l:"2:0"},{n:13,d:"D3",h:"H3",l:"2:0"},{n:14,d:"D4",h:"H4",l:"0:2"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"2:0"},{n:18,d:"D4",h:"H4",l:"2:1"}],
   dc:[{num:9,type:"D",score:"1:2",terče:[{d:"D1+D4",h:"H2+H5"},{d:"D2+D3",h:"H3+H4"},{d:"D3+D4",h:"H3+H5",rozh:true}]},{num:10,type:"CR",score:"2:1",terče:[{d:"D1+D2",h:"H2+H4"},{d:"D3+D4",h:"H3+H5"},{d:"D1+D2",h:"H2+H4",rozh:true}]}]},
  {kolo:19,datum:"22.02.2026",misto:"Restaurace Alfa",my:"Host",soupere:"Clasico My Praha",skore_my:6,skore_soupere:12,
   hraci_my:{H1:"Donát Petr",H2:"Jurenka Daniel",H3:"Zelinka Václav",H4:"Knoflíček Michal"},
   hraci_soupere:{D1:"Selucký Josef",D2:"Šál Petr",D3:"Dlouhý Milan",D4:"Knoflíček Michal",D5:"Turnwald Jindřich"},
   stats:{},singles:[{n:1,d:"D1",h:"H1",l:"0:2"},{n:2,d:"D2",h:"H2",l:"0:2"},{n:3,d:"D3",h:"H3",l:"0:2"},{n:4,d:"D4",h:"H4",l:"0:2"},{n:5,d:"D1",h:"H4",l:"0:2"},{n:6,d:"D2",h:"H3",l:"2:0"},{n:7,d:"D3",h:"H2",l:"0:2"},{n:8,d:"D4",h:"H1",l:"1:2"},{n:11,d:"D1",h:"H1",l:"2:0"},{n:12,d:"D2",h:"H2",l:"0:2"},{n:13,d:"D3",h:"H3",l:"2:0"},{n:14,d:"D4",h:"H4",l:"0:2"},{n:15,d:"D1",h:"H5",l:"0:2"},{n:16,d:"D2",h:"H2",l:"0:2"},{n:17,d:"D3",h:"H3",l:"2:0"},{n:18,d:"D4",h:"H4",l:"2:0"}],
   dc:[{num:9,type:"D",score:"2:0",terče:[{d:"D3+D4",h:"H1+H4"},{d:"D1+D4",h:"H1+H2"}]},{num:10,type:"CR",score:"1:2",terče:[{d:"D2+D3",h:"H4+H5"},{d:"D1+D4",h:"H1+H2"},{d:"D2+D3",h:"H4+H5",rozh:true}]}]},
];

// Future matches (kolo 20-26)
const FUTURE_MATCHES = [
  {kolo:20,datum:"",misto:"",soupere:"Tempácký hroty Praha",my:"Domácí"},
  {kolo:21,datum:"",misto:"",soupere:"Otupělé hroty Praha",my:"Host"},
  {kolo:22,datum:"",misto:"",soupere:"Sedmá rota Praha B",my:"Domácí"},
  {kolo:23,datum:"",misto:"",soupere:"PLB Praha",my:"Host"},
  {kolo:24,datum:"",misto:"",soupere:"Žíznivý důchodci Praha",my:"Host"},
  {kolo:25,datum:"",misto:"",soupere:"Stiflerova máma Modřany",my:"Domácí"},
  {kolo:26,datum:"",misto:"",soupere:"Worm Gang Praha",my:"Domácí"},
];

// ─── HELPERS ──────────────────────────────────────────────────────────────────
function getResult(m){
  if(!m.skore_my&&m.skore_my!==0) return null;
  if(m.skore_my>m.skore_soupere) return "V";
  if(m.skore_my<m.skore_soupere) return "P";
  return "R";
}

function parseLegy(l){
  if(!l||!l.includes(":")) return [null,null];
  return l.split(":").map(Number);
}

function resolvePos(pos, hraci, my, m){
  // pos like "D1","H3" — look up in correct dict
  if(my==="Domácí"){
    if(pos.startsWith("D")) return hraci[pos]||pos;
    return (m.hraci_soupere||{})[pos]||pos;
  } else {
    if(pos.startsWith("H")) return hraci[pos]||pos;
    return (m.hraci_soupere||{})[pos]||pos;
  }
}

function resolvePair(pairStr, m){
  const positions = pairStr.split("+");
  return positions.map(p => {
    if(p.startsWith("D")) return m.hraci_soupere?.[p] || (m.hraci_my?.[p]) || p;
    return m.hraci_my?.[p] || (m.hraci_soupere?.[p]) || p;
  }).join(" + ");
}

// Compute player stats from all matches
function computeStats(){
  const stats = {};
  NASI_HRACI.forEach(p => stats[p] = {zapasy:0,vyhry:0,prohry:0,remizy:0,legy_pro:0,legy_proti:0,n95:0,n133:0,n170:0,body:0});
  
  MATCHES_DATA.forEach(m => {
    const myKey = m.my==="Domácí" ? "D" : "H";
    
    // Singles
    m.singles.forEach(z => {
      let ourPos = myKey==="D" ? z.d : z.h;
      let theirPos = myKey==="D" ? z.h : z.d;
      let playerName = m.hraci_my?.[ourPos];
      if(!playerName || !stats[playerName]) return;
      
      const [dl,hl] = parseLegy(z.l);
      if(dl===null) return;
      const [ourL, theirL] = myKey==="D" ? [dl,hl] : [hl,dl];
      
      stats[playerName].zapasy++;
      stats[playerName].legy_pro += ourL;
      stats[playerName].legy_proti += theirL;
      if(ourL>theirL){ stats[playerName].vyhry++; stats[playerName].body+=2; }
      else if(ourL<theirL){ stats[playerName].prohry++; }
      else{ stats[playerName].remizy++; stats[playerName].body+=1; }
    });
    
    // Stats
    if(m.stats) Object.entries(m.stats).forEach(([name,s])=>{
      if(stats[name]){
        stats[name].n95 += s.n95||0;
        stats[name].n133 += s.n133||0;
        stats[name].n170 += s.n170||0;
      }
    });
  });
  
  return stats;
}

// ─── COMPONENTS ───────────────────────────────────────────────────────────────
const COLORS = {
  bg:"#0a0f1e", card:"#111827", mid:"#1e293b", border:"#1e3a5f",
  gold:"#f59e0b", green:"#10b981", red:"#ef4444", draw:"#6366f1",
  text:"#e2e8f0", muted:"#64748b", white:"#ffffff",
  domBg:"#0f2a1a", hostBg:"#0f0f2a",
  domAcc:"#10b981", hostAcc:"#818cf8",
};

const css = {
  app: {fontFamily:"'JetBrains Mono', 'Fira Code', monospace", background:COLORS.bg, minHeight:"100vh", color:COLORS.text},
  header: {background:"linear-gradient(135deg,#0f172a,#1e3a5f)", borderBottom:`1px solid ${COLORS.border}`, padding:"12px 20px", display:"flex", alignItems:"center", gap:12, flexWrap:"wrap"},
  nav: {display:"flex", gap:8, flexWrap:"wrap"},
  navBtn: (active)=>({background:active?"#1d4ed8":"transparent", border:`1px solid ${active?"#3b82f6":COLORS.border}`, color:active?COLORS.white:COLORS.muted, padding:"6px 14px", borderRadius:6, cursor:"pointer", fontSize:13, fontFamily:"inherit"}),
  card: {background:COLORS.card, border:`1px solid ${COLORS.border}`, borderRadius:8, padding:"12px 16px", marginBottom:12},
  table: {width:"100%", borderCollapse:"collapse", fontSize:12},
  th: (bg)=>({background:bg||"#1d4ed8", color:COLORS.white, padding:"8px 10px", textAlign:"center", fontWeight:700, cursor:"pointer", whiteSpace:"nowrap", border:`1px solid ${COLORS.border}`, userSelect:"none"}),
  td: (bg)=>({background:bg||COLORS.mid, padding:"7px 10px", textAlign:"center", border:`1px solid #1a2a3a`, fontSize:12}),
  badge: (type)=>{
    const map = {V:{bg:"#14532d",c:"#86efac"},P:{bg:"#7f1d1d",c:"#fca5a5"},R:{bg:"#1e3a8a",c:"#93c5fd"}};
    const s = map[type]||{bg:COLORS.mid,c:COLORS.muted};
    return {background:s.bg, color:s.c, padding:"2px 8px", borderRadius:4, fontWeight:700, fontSize:11};
  },
  input: {background:"#0f172a", border:`1px solid ${COLORS.border}`, color:COLORS.text, padding:"6px 10px", borderRadius:6, fontFamily:"inherit", fontSize:13, width:"100%", boxSizing:"border-box"},
  select: {background:"#0f172a", border:`1px solid ${COLORS.border}`, color:COLORS.text, padding:"6px 10px", borderRadius:6, fontFamily:"inherit", fontSize:13, width:"100%", boxSizing:"border-box"},
  label: {color:COLORS.muted, fontSize:11, display:"block", marginBottom:4},
  section: {margin:"0 0 8px 0"},
  btn: (variant)=>{
    const map = {primary:{bg:"#1d4ed8",c:COLORS.white},success:{bg:"#14532d",c:"#86efac"},danger:{bg:"#7f1d1d",c:"#fca5a5"},ghost:{bg:"transparent",c:COLORS.muted,border:`1px solid ${COLORS.border}`}};
    const s = map[variant]||map.primary;
    return {background:s.bg, color:s.c, border:s.border||"none", padding:"7px 16px", borderRadius:6, cursor:"pointer", fontFamily:"inherit", fontSize:13, fontWeight:600};
  },
};

// Match row result color
function matchRowStyle(result){
  if(result==="V") return {background:"#0d2a1a"};
  if(result==="P") return {background:"#1a0d0d"};
  if(result==="R") return {background:"#0d0d2a"};
  return {background:COLORS.card};
}

function resultStyle(result){
  if(result==="V") return {...css.badge("V"), display:"inline-block"};
  if(result==="P") return {...css.badge("P"), display:"inline-block"};
  if(result==="R") return {...css.badge("R"), display:"inline-block"};
  return {};
}

// ─── MATCH LIST VIEW ──────────────────────────────────────────────────────────
function SeasonView({onSelect}){
  const [filter, setFilter] = useState("all");
  const played = MATCHES_DATA;
  const totals = useMemo(()=>({
    z:played.length,
    v:played.filter(m=>getResult(m)==="V").length,
    p:played.filter(m=>getResult(m)==="P").length,
    r:played.filter(m=>getResult(m)==="R").length,
    body_my: played.reduce((s,m)=>s+m.skore_my,0),
    body_op: played.reduce((s,m)=>s+m.skore_soupere,0),
  }),[]);
  
  const filtered = filter==="all" ? played : played.filter(m=>getResult(m)===filter);
  
  return (
    <div style={{padding:"16px 20px"}}>
      {/* Summary panels */}
      <div style={{display:"grid", gridTemplateColumns:"repeat(6,1fr)", gap:8, marginBottom:16}}>
        {[
          {label:"ZÁPASŮ", val:totals.z, bg:COLORS.card},
          {label:"VÝHER", val:totals.v, bg:"#0d2a1a", c:"#86efac"},
          {label:"PROHER", val:totals.p, bg:"#1a0d0d", c:"#fca5a5"},
          {label:"REMÍZ", val:totals.r, bg:"#0d0d2a", c:"#93c5fd"},
          {label:"BODY MY", val:totals.body_my, bg:COLORS.card, c:COLORS.gold},
          {label:"% VÝHER", val:`${Math.round(totals.v/Math.max(1,totals.v+totals.p)*100)}%`, bg:"#2a1a3a", c:"#c4b5fd"},
        ].map(({label,val,bg,c})=>(
          <div key={label} style={{background:bg, border:`1px solid ${COLORS.border}`, borderRadius:8, padding:"10px 12px", textAlign:"center"}}>
            <div style={{fontSize:10, color:COLORS.muted, marginBottom:4}}>{label}</div>
            <div style={{fontSize:24, fontWeight:700, color:c||COLORS.text}}>{val}</div>
          </div>
        ))}
      </div>
      
      {/* Filter */}
      <div style={{display:"flex", gap:8, marginBottom:12}}>
        {[["all","Vše"],["V","Výhry"],["P","Prohry"],["R","Remízy"]].map(([k,l])=>(
          <button key={k} onClick={()=>setFilter(k)} style={css.navBtn(filter===k)}>{l}</button>
        ))}
      </div>
      
      {/* Matches table */}
      <div style={{overflowX:"auto"}}>
        <table style={css.table}>
          <thead>
            <tr>
              {["Kolo","Datum","Místo","D/H","Soupeř","Výsledek","Body","Legy","Detail"].map(h=>(
                <th key={h} style={{...css.th(), fontSize:11}}>{h}</th>
              ))}
            </tr>
          </thead>
          <tbody>
            {filtered.map(m=>{
              const res = getResult(m);
              return (
                <tr key={m.kolo} style={matchRowStyle(res)}>
                  <td style={css.td()}><b style={{color:COLORS.gold}}>{m.kolo}</b></td>
                  <td style={css.td()}>{m.datum}</td>
                  <td style={{...css.td(), textAlign:"left"}}>{m.misto}</td>
                  <td style={css.td()}>{m.my==="Domácí"?"🏠 D":"✈️ H"}</td>
                  <td style={{...css.td(), textAlign:"left", fontWeight:600}}>{m.soupere}</td>
                  <td style={css.td()}><span style={resultStyle(res)}>{res}</span></td>
                  <td style={{...css.td(), fontWeight:700, color:res==="V"?"#86efac":res==="P"?"#fca5a5":"#93c5fd"}}>
                    {m.skore_my}:{m.skore_soupere}
                  </td>
                  <td style={css.td()}>
                    {(() => {
                      const lp = m.singles.reduce((s,z)=>{const [d,h]=parseLegy(z.l); return s+(m.my==="Domácí"?(d||0):(h||0));},0);
                      const lo = m.singles.reduce((s,z)=>{const [d,h]=parseLegy(z.l); return s+(m.my==="Domácí"?(h||0):(d||0));},0);
                      return <span style={{color:COLORS.muted}}>{lp}:{lo}</span>;
                    })()}
                  </td>
                  <td style={css.td()}>
                    <button onClick={()=>onSelect(m.kolo)} style={{...css.btn("ghost"), padding:"3px 10px", fontSize:11}}>📋</button>
                  </td>
                </tr>
              );
            })}
            {/* Future matches */}
            {FUTURE_MATCHES.map(m=>(
              <tr key={m.kolo} style={{background:"#0a0f1e", opacity:0.6}}>
                <td style={{...css.td(), color:COLORS.muted}}><b>{m.kolo}</b></td>
                <td style={{...css.td(), color:COLORS.muted}}>TBD</td>
                <td style={{...css.td(), color:COLORS.muted}}>—</td>
                <td style={{...css.td(), color:COLORS.muted}}>{m.my==="Domácí"?"🏠 D":"✈️ H"}</td>
                <td style={{...css.td(), textAlign:"left", color:COLORS.muted}}>{m.soupere}</td>
                <td style={css.td()}>—</td><td style={css.td()}>—</td><td style={css.td()}>—</td>
                <td style={css.td()}><span style={{color:COLORS.muted, fontSize:11}}>plánováno</span></td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
    </div>
  );
}

// ─── DC BLOCK COMPONENT ───────────────────────────────────────────────────────
function DCBlock({dc, m}){
  const typLabel = dc.type==="D" ? "🎯 DOUBLE" : "🏏 CRICKET";
  const [ds,hs] = dc.score.split(":").map(Number);
  const myWon = m.my==="Domácí" ? ds>hs : hs>ds;
  const scoreColor = myWon ? "#86efac" : ds===hs ? "#93c5fd" : "#fca5a5";
  const blockBg = dc.type==="D" ? "#0a2a1a" : "#1a0a2a";
  const accentColor = dc.type==="D" ? "#10b981" : "#a78bfa";
  
  return (
    <tr>
      <td colSpan={8} style={{padding:0, border:`1px solid ${COLORS.border}`}}>
        <div style={{background:blockBg, padding:"10px 14px"}}>
          {/* Header row */}
          <div style={{display:"flex", alignItems:"center", justifyContent:"space-between", marginBottom:8}}>
            <div style={{display:"flex", alignItems:"center", gap:10}}>
              <span style={{background:accentColor, color:"#000", padding:"2px 8px", borderRadius:4, fontSize:11, fontWeight:700}}>m{dc.num}</span>
              <span style={{color:accentColor, fontWeight:700, fontSize:13}}>{typLabel}</span>
            </div>
            <div style={{display:"flex", alignItems:"center", gap:8}}>
              <span style={{color:COLORS.muted, fontSize:11}}>
                {m.my==="Domácí" ? "Domácí":"Hosté"} {dc.score} {m.my==="Domácí" ? "Hosté":"Domácí"}
              </span>
              <span style={{fontSize:18, fontWeight:700, color:scoreColor, background:"rgba(0,0,0,0.3)", padding:"2px 10px", borderRadius:4}}>
                {dc.score}
              </span>
            </div>
          </div>
          
          {/* Terče */}
          <div style={{display:"flex", flexDirection:"column", gap:6}}>
            {dc.terče.map((t,i)=>{
              const label = t.rozh ? "⚡ ROZHODUJÍCÍ" : `TERČ ${i+1}`;
              const terčBg = t.rozh ? "rgba(251,191,36,0.1)" : (i===0 ? "rgba(0,0,0,0.2)" : "rgba(0,0,0,0.15)");
              const labelColor = t.rozh ? COLORS.gold : COLORS.muted;
              
              const domPair = m.my==="Domácí" ? t.d : t.h;
              const hostPair = m.my==="Domácí" ? t.h : t.d;
              
              const domPlayers = domPair.split("+").map(p=>{
                if(m.my==="Domácí") return m.hraci_my?.[p]||p;
                return m.hraci_soupere?.[p]||p;
              });
              const hostPlayers = hostPair.split("+").map(p=>{
                if(m.my==="Domácí") return m.hraci_soupere?.[p]||p;
                return m.hraci_my?.[p]||p;
              });
              
              return (
                <div key={i} style={{background:terčBg, border:`1px solid rgba(255,255,255,0.05)`, borderRadius:6, padding:"8px 12px", display:"grid", gridTemplateColumns:"1fr auto 1fr", gap:8, alignItems:"center"}}>
                  {/* Domácí side */}
                  <div style={{background:COLORS.domBg, borderRadius:5, padding:"6px 10px"}}>
                    <div style={{color:COLORS.domAcc, fontSize:10, fontWeight:700, marginBottom:3}}>🏠 {domPair}</div>
                    {domPlayers.map((p,j)=>(
                      <div key={j} style={{color:COLORS.white, fontSize:12}}>{p}</div>
                    ))}
                  </div>
                  
                  {/* Label */}
                  <div style={{textAlign:"center"}}>
                    <div style={{color:labelColor, fontSize:10, fontWeight:700, whiteSpace:"nowrap"}}>{label}</div>
                    <div style={{color:COLORS.muted, fontSize:11}}>vs</div>
                  </div>
                  
                  {/* Hosté side */}
                  <div style={{background:COLORS.hostBg, borderRadius:5, padding:"6px 10px"}}>
                    <div style={{color:COLORS.hostAcc, fontSize:10, fontWeight:700, marginBottom:3}}>✈️ {hostPair}</div>
                    {hostPlayers.map((p,j)=>(
                      <div key={j} style={{color:COLORS.white, fontSize:12}}>{p}</div>
                    ))}
                  </div>
                </div>
              );
            })}
          </div>
        </div>
      </td>
    </tr>
  );
}

// ─── SINGLE ROW ───────────────────────────────────────────────────────────────
function SingleRow({z, m, idx}){
  const myKey = m.my==="Domácí" ? "D" : "H";
  const ourPos = myKey==="D" ? z.d : z.h;
  const theirPos = myKey==="D" ? z.h : z.d;
  const ourName = m.hraci_my?.[ourPos] || ourPos;
  const theirName = m.hraci_soupere?.[theirPos] || theirPos;
  
  const [dl,hl] = parseLegy(z.l);
  const [ourL,theirL] = myKey==="D" ? [dl,hl] : [hl,dl];
  const won = ourL>theirL; const lost = ourL<theirL;
  
  const rowBg = won ? "#0d1f0d" : lost ? "#1f0d0d" : (idx%2===0 ? COLORS.mid : "#16213e");
  
  return (
    <tr style={{background:rowBg}}>
      <td style={{...css.td(rowBg), color:COLORS.muted, fontSize:11}}>{z.n}</td>
      <td style={{...css.td(rowBg), color:COLORS.muted, fontSize:11}}>Single</td>
      <td style={{...css.td(COLORS.domBg), textAlign:"left", color:COLORS.white}}>{z.d}: {m.my==="Domácí"?ourName:theirName}</td>
      <td style={{...css.td(COLORS.hostBg), textAlign:"left", color:COLORS.white}}>{z.h}: {m.my==="Domácí"?theirName:ourName}</td>
      <td style={{...css.td(rowBg), fontWeight:700, fontSize:14, color:won?"#86efac":lost?"#fca5a5":"#e2e8f0"}}>{z.l}</td>
      <td style={{...css.td(COLORS.domBg), fontWeight:700, color:won?"#86efac":"#fca5a5"}}>{ourL}</td>
      <td style={{...css.td(COLORS.hostBg), fontWeight:700, color:!won?"#86efac":"#fca5a5"}}>{theirL}</td>
      <td style={{...css.td(rowBg)}}>{won?"✅":"❌"}</td>
    </tr>
  );
}

// ─── MATCH DETAIL VIEW ────────────────────────────────────────────────────────
function MatchDetail({kolo, onBack, onEdit}){
  const m = useMemo(()=>MATCHES_DATA.find(x=>x.kolo===kolo),[kolo]);
  if(!m) return <div style={{padding:20}}>Zápas nenalezen</div>;
  
  const res = getResult(m);
  const resBg = res==="V"?"#0d2a1a":res==="P"?"#2a0d0d":"#0d0d2a";
  const resColor = res==="V"?"#86efac":res==="P"?"#fca5a5":"#93c5fd";
  const domName = m.my==="Domácí"?"5. Avenue Praha":m.soupere;
  const hostName = m.my==="Domácí"?m.soupere:"5. Avenue Praha";
  const domScore = m.my==="Domácí"?m.skore_my:m.skore_soupere;
  const hostScore = m.my==="Domácí"?m.skore_soupere:m.skore_my;
  
  // Build ordered matches: singles 1-8, dc m9, dc m10, singles 11-18
  const singles_1_8 = m.singles.filter(z=>z.n<=8).sort((a,b)=>a.n-b.n);
  const singles_11_18 = m.singles.filter(z=>z.n>=11).sort((a,b)=>a.n-b.n);
  
  const ourLegy = m.singles.reduce((s,z)=>{const [d,h]=parseLegy(z.l); return s+(m.my==="Domácí"?(d||0):(h||0));},0);
  const theirLegy = m.singles.reduce((s,z)=>{const [d,h]=parseLegy(z.l); return s+(m.my==="Domácí"?(h||0):(d||0));},0);
  
  return (
    <div style={{padding:"16px 20px"}}>
      <div style={{display:"flex", alignItems:"center", gap:10, marginBottom:16}}>
        <button onClick={onBack} style={css.btn("ghost")}>← Zpět</button>
        <h2 style={{margin:0, color:COLORS.gold, fontSize:16}}>Kolo {kolo}</h2>
        {onEdit && <button onClick={onEdit} style={css.btn("primary")}>✏️ Upravit</button>}
      </div>
      
      {/* Match header */}
      <div style={{background:resBg, border:`2px solid ${resColor}`, borderRadius:10, padding:"14px 18px", marginBottom:14}}>
        <div style={{display:"flex", justifyContent:"space-between", alignItems:"center", flexWrap:"wrap", gap:8}}>
          <div style={{color:COLORS.muted, fontSize:12}}>📅 {m.datum} &nbsp;|&nbsp; 📍 {m.misto}</div>
          <div style={{...css.badge(res), fontSize:13, padding:"4px 12px"}}>{res==="V"?"✅ VÝHRA":res==="P"?"❌ PROHRA":"⚖️ REMÍZA"}</div>
        </div>
        <div style={{display:"grid", gridTemplateColumns:"1fr auto 1fr", alignItems:"center", gap:12, marginTop:10}}>
          <div style={{background:COLORS.domBg, borderRadius:8, padding:"10px 14px"}}>
            <div style={{color:COLORS.domAcc, fontSize:10, fontWeight:700}}>🏠 DOMÁCÍ</div>
            <div style={{fontSize:18, fontWeight:700, color:COLORS.white, marginTop:2}}>{domName}</div>
          </div>
          <div style={{textAlign:"center"}}>
            <div style={{fontSize:32, fontWeight:700, color:COLORS.gold}}>{domScore}:{hostScore}</div>
            <div style={{color:COLORS.muted, fontSize:10}}>celkové skóre</div>
          </div>
          <div style={{background:COLORS.hostBg, borderRadius:8, padding:"10px 14px", textAlign:"right"}}>
            <div style={{color:COLORS.hostAcc, fontSize:10, fontWeight:700}}>✈️ HOSTÉ</div>
            <div style={{fontSize:18, fontWeight:700, color:COLORS.white, marginTop:2}}>{hostName}</div>
          </div>
        </div>
      </div>
      
      {/* Roster */}
      <div style={{display:"grid", gridTemplateColumns:"1fr 1fr", gap:10, marginBottom:14}}>
        <div style={{background:COLORS.domBg, borderRadius:8, padding:"10px 14px"}}>
          <div style={{color:COLORS.domAcc, fontSize:11, fontWeight:700, marginBottom:6}}>
            👥 {m.my==="Domácí"?"NÁŠ TÝM":"SOUPEŘ"} – {domName}
          </div>
          {Object.entries(m.my==="Domácí"?m.hraci_my:m.hraci_soupere).map(([pos,name])=>(
            <div key={pos} style={{display:"flex", gap:8, padding:"3px 0", borderBottom:`1px solid rgba(255,255,255,0.05)`}}>
              <span style={{color:COLORS.domAcc, fontSize:11, minWidth:28, fontWeight:700}}>{pos}</span>
              <span style={{color:COLORS.white, fontSize:12}}>{name}</span>
            </div>
          ))}
        </div>
        <div style={{background:COLORS.hostBg, borderRadius:8, padding:"10px 14px"}}>
          <div style={{color:COLORS.hostAcc, fontSize:11, fontWeight:700, marginBottom:6}}>
            👥 {m.my==="Host"?"NÁŠ TÝM":"SOUPEŘ"} – {hostName}
          </div>
          {Object.entries(m.my==="Host"?m.hraci_my:m.hraci_soupere).map(([pos,name])=>(
            <div key={pos} style={{display:"flex", gap:8, padding:"3px 0", borderBottom:`1px solid rgba(255,255,255,0.05)`}}>
              <span style={{color:COLORS.hostAcc, fontSize:11, minWidth:28, fontWeight:700}}>{pos}</span>
              <span style={{color:COLORS.white, fontSize:12}}>{name}</span>
            </div>
          ))}
        </div>
      </div>
      
      {/* Match table */}
      <div style={{overflowX:"auto"}}>
        <table style={{...css.table, borderRadius:8, overflow:"hidden"}}>
          <thead>
            <tr>
              <th style={{...css.th(), width:30}}>#</th>
              <th style={{...css.th(), width:60}}>Typ</th>
              <th style={{...css.th("rgba(16,56,26,0.8)")}}>🏠 Domácí</th>
              <th style={{...css.th("rgba(16,16,56,0.8)")}}>✈️ Hosté</th>
              <th style={{...css.th(), width:55}}>Legy</th>
              <th style={{...css.th("rgba(16,56,26,0.8)"), width:45}}>D</th>
              <th style={{...css.th("rgba(16,16,56,0.8)"), width:45}}>H</th>
              <th style={{...css.th(), width:30}}>✓</th>
            </tr>
          </thead>
          <tbody>
            {singles_1_8.map((z,i)=><SingleRow key={z.n} z={z} m={m} idx={i}/>)}
            {m.dc.filter(d=>d.num===9).map(dc=><DCBlock key={9} dc={dc} m={m}/>)}
            {m.dc.filter(d=>d.num===10).map(dc=><DCBlock key={10} dc={dc} m={m}/>)}
            {singles_11_18.map((z,i)=><SingleRow key={z.n} z={z} m={m} idx={i}/>)}
            {/* Totals */}
            <tr style={{background:resBg, border:`2px solid ${resColor}`}}>
              <td colSpan={5} style={{...css.td(resBg), textAlign:"left", fontWeight:700, color:resColor, fontSize:13}}>
                VÝSLEDEK: {res==="V"?"✅ VÝHRA":res==="P"?"❌ PROHRA":"⚖️ REMÍZA"} | 5. Avenue {m.skore_my}:{m.skore_soupere} {m.soupere}
              </td>
              <td style={{...css.td(COLORS.domBg), fontWeight:700, fontSize:16, color:COLORS.domAcc}}>{ourLegy}</td>
              <td style={{...css.td(COLORS.hostBg), fontWeight:700, fontSize:16, color:COLORS.hostAcc}}>{theirLegy}</td>
              <td style={{...css.td(resBg), fontWeight:700, color:resColor}}>{m.skore_my}:{m.skore_soupere}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  );
}

// ─── STATISTICS VIEW ──────────────────────────────────────────────────────────
function StatisticsView(){
  const [sortKey, setSortKey] = useState("vyhry");
  const [sortDir, setSortDir] = useState("desc");
  
  const stats = useMemo(()=>computeStats(),[]);
  
  const rows = useMemo(()=>{
    return Object.entries(stats)
      .map(([name,s])=>({
        name,
        ...s,
        pct: s.vyhry+s.prohry > 0 ? Math.round(s.vyhry/(s.vyhry+s.prohry)*100) : 0,
        legy_diff: s.legy_pro - s.legy_proti,
      }))
      .sort((a,b)=>sortDir==="asc" ? a[sortKey]-b[sortKey] : b[sortKey]-a[sortKey]);
  },[sortKey, sortDir, stats]);
  
  const handleSort = (k)=>{
    if(sortKey===k) setSortDir(d=>d==="asc"?"desc":"asc");
    else { setSortKey(k); setSortDir("desc"); }
  };
  
  const sortIcon = (k) => sortKey===k ? (sortDir==="asc"?"↑":"↓") : "↕";
  
  const cols = [
    {key:"name",label:"Hráč",num:false},
    {key:"zapasy",label:"Utkání",num:true},
    {key:"vyhry",label:"Výhry",num:true},
    {key:"prohry",label:"Prohry",num:true},
    {key:"remizy",label:"Remízy",num:true},
    {key:"pct",label:"% Výher",num:true},
    {key:"body",label:"Body",num:true},
    {key:"legy_pro",label:"Legy pro",num:true},
    {key:"legy_proti",label:"Legy proti",num:true},
    {key:"legy_diff",label:"±Legy",num:true},
    {key:"n95",label:"95+",num:true},
    {key:"n133",label:"133+",num:true},
    {key:"n170",label:"170+",num:true},
  ];
  
  return (
    <div style={{padding:"16px 20px"}}>
      <div style={{marginBottom:12}}>
        <h2 style={{margin:"0 0 4px", color:COLORS.gold, fontSize:16}}>📊 Statistiky hráčů – 3. Liga N 2025/2026</h2>
        <div style={{color:COLORS.muted, fontSize:11}}>Klikni na záhlaví sloupce pro řazení</div>
      </div>
      
      <div style={{overflowX:"auto"}}>
        <table style={css.table}>
          <thead>
            <tr>
              <th style={{...css.th(), width:24, textAlign:"left", paddingLeft:8}}>#</th>
              {cols.map(c=>(
                <th key={c.key} onClick={()=>c.num&&handleSort(c.key)} style={{...css.th(c.num?undefined:"#2d3748"), cursor:c.num?"pointer":"default", minWidth:c.key==="name"?120:50}}>
                  {c.label} {c.num && <span style={{opacity:0.6, fontSize:10}}>{sortIcon(c.key)}</span>}
                </th>
              ))}
            </tr>
          </thead>
          <tbody>
            {rows.map((r,i)=>{
              const rowBg = i%2===0?COLORS.mid:COLORS.card;
              return (
                <tr key={r.name} style={{background:rowBg}}>
                  <td style={{...css.td(rowBg), color:COLORS.gold, fontWeight:700, fontSize:11}}>{i+1}</td>
                  <td style={{...css.td(rowBg), textAlign:"left", fontWeight:600, color:COLORS.white}}>{r.name}</td>
                  <td style={css.td(rowBg)}>{r.zapasy}</td>
                  <td style={{...css.td(rowBg), color:"#86efac", fontWeight:700}}>{r.vyhry}</td>
                  <td style={{...css.td(rowBg), color:"#fca5a5"}}>{r.prohry}</td>
                  <td style={css.td(rowBg)}>{r.remizy}</td>
                  <td style={{...css.td(rowBg), color:r.pct>=50?"#86efac":r.pct>=30?"#fbbf24":"#fca5a5", fontWeight:700}}>
                    {r.pct}%
                  </td>
                  <td style={{...css.td(rowBg), color:COLORS.gold, fontWeight:700}}>{r.body}</td>
                  <td style={{...css.td(COLORS.domBg), color:COLORS.domAcc}}>{r.legy_pro}</td>
                  <td style={{...css.td(COLORS.hostBg), color:COLORS.hostAcc}}>{r.legy_proti}</td>
                  <td style={{...css.td(rowBg), color:r.legy_diff>0?"#86efac":r.legy_diff<0?"#fca5a5":COLORS.muted, fontWeight:r.legy_diff!==0?700:400}}>
                    {r.legy_diff>0?"+":""}{r.legy_diff}
                  </td>
                  <td style={{...css.td(rowBg), color:r.n95>0?COLORS.gold:COLORS.muted, fontWeight:r.n95>0?700:400}}>{r.n95||"—"}</td>
                  <td style={{...css.td(rowBg), color:r.n133>0?"#f97316":COLORS.muted, fontWeight:r.n133>0?700:400}}>{r.n133||"—"}</td>
                  <td style={{...css.td(rowBg), color:r.n170>0?"#ef4444":COLORS.muted, fontWeight:r.n170>0?700:400}}>{r.n170||"—"}</td>
                </tr>
              );
            })}
          </tbody>
        </table>
      </div>
    </div>
  );
}

// ─── NEW MATCH FORM ───────────────────────────────────────────────────────────
function NewMatchForm({onBack}){
  const defaultPlayers = {D1:"",D2:"",D3:"",D4:"",D5:""};
  const defaultOppPlayers = {H1:"",H2:"",H3:"",H4:"",H5:""};
  
  const [form, setForm] = useState({
    kolo:"", datum:"", misto:"", my:"Domácí", soupere:"",
    hraci_my: {...defaultPlayers}, hraci_soupere: {...defaultOppPlayers},
  });
  
  const [singles, setSingles] = useState({});
  const [dcScores, setDcScores] = useState({9:"",10:""});
  
  const update = (field, val) => setForm(f=>({...f,[field]:val}));
  const updatePlayer = (side, pos, val) => setForm(f=>({...f,[side]:{...f[side],[pos]:val}}));
  
  const isCzDate = form.datum ? form.datum.replace(/-/g,'.').split('.').reverse().join('.') : '';
  const dateVal = form.datum;
  
  const ownSide = form.my==="Domácí" ? "D" : "H";
  const oppSide = form.my==="Domácí" ? "H" : "D";
  
  // Standard 5A match layout
  const singlesLayout = [
    {n:1,d:"D1",h:"H3"},{n:2,d:"D2",h:"H4"},{n:3,d:"D3",h:"H1"},{n:4,d:"D4",h:"H2"},
    {n:5,d:"D1",h:"H4"},{n:6,d:"D2",h:"H3"},{n:7,d:"D3",h:"H2"},{n:8,d:"D4",h:"H1"},
    {n:11,d:"D1",h:"H2"},{n:12,d:"D2",h:"H1"},{n:13,d:"D3",h:"H4"},{n:14,d:"D4",h:"H3"},
    {n:15,d:"D1",h:"H5"},{n:16,d:"D2",h:"H2"},{n:17,d:"D3",h:"H3"},{n:18,d:"D4",h:"H4"},
  ];
  
  const scoreOptions = ["","2:0","2:1","1:2","0:2"];
  
  const fg = {padding:"0 20px 20px"};
  
  return (
    <div style={{padding:"16px 20px"}}>
      <div style={{display:"flex", alignItems:"center", gap:10, marginBottom:16}}>
        <button onClick={onBack} style={css.btn("ghost")}>← Zpět</button>
        <h2 style={{margin:0, color:COLORS.gold, fontSize:16}}>📝 Nový / Upravit zápas</h2>
      </div>
      
      {/* Meta info */}
      <div style={{...css.card, display:"grid", gridTemplateColumns:"repeat(3,1fr)", gap:12}}>
        <div>
          <label style={css.label}>Kolo</label>
          <input type="number" min="1" max="26" value={form.kolo} onChange={e=>update("kolo",e.target.value)} style={css.input}/>
        </div>
        <div>
          <label style={css.label}>📅 Datum</label>
          <input type="date" value={dateVal} onChange={e=>update("datum",e.target.value)} 
            style={{...css.input, colorScheme:"dark"}}/>
        </div>
        <div>
          <label style={css.label}>🏠 / ✈️ Hrajeme jako</label>
          <select value={form.my} onChange={e=>update("my",e.target.value)} style={css.select}>
            <option>Domácí</option>
            <option>Host</option>
          </select>
        </div>
        <div>
          <label style={css.label}>⚔️ Soupeř</label>
          <select value={form.soupere} onChange={e=>update("soupere",e.target.value)} style={css.select}>
            <option value="">— vybrat soupeře —</option>
            {SOUPEŘI.map(s=><option key={s}>{s}</option>)}
          </select>
        </div>
        <div style={{gridColumn:"2 / 4"}}>
          <label style={css.label}>📍 Místo</label>
          <select value={form.misto} onChange={e=>update("misto",e.target.value)} style={css.select}>
            <option value="">— vybrat místo —</option>
            {MISTNOSTI.map(s=><option key={s}>{s}</option>)}
          </select>
        </div>
      </div>
      
      {/* Rosters */}
      <div style={{display:"grid", gridTemplateColumns:"1fr 1fr", gap:12, marginBottom:12}}>
        <div style={{...css.card, background:COLORS.domBg}}>
          <div style={{color:COLORS.domAcc, fontWeight:700, fontSize:12, marginBottom:10}}>
            🏠 {form.my==="Domácí"?"NÁŠ TÝM (Domácí)":"SOUPEŘ (Domácí)"}
          </div>
          {["D1","D2","D3","D4","D5"].map(pos=>(
            <div key={pos} style={{display:"flex", alignItems:"center", gap:8, marginBottom:6}}>
              <span style={{color:COLORS.domAcc, width:24, fontWeight:700, fontSize:12}}>{pos}</span>
              {form.my==="Domácí" ? (
                <select value={form.hraci_my[pos]} onChange={e=>updatePlayer("hraci_my",pos,e.target.value)} style={{...css.select, flex:1}}>
                  <option value="">— hráč —</option>
                  {NASI_HRACI.map(h=><option key={h}>{h}</option>)}
                </select>
              ) : (
                <input placeholder="Jméno hráče" value={form.hraci_soupere[pos]||""} 
                  onChange={e=>updatePlayer("hraci_soupere",pos,e.target.value)} style={{...css.input, flex:1}}/>
              )}
            </div>
          ))}
        </div>
        <div style={{...css.card, background:COLORS.hostBg}}>
          <div style={{color:COLORS.hostAcc, fontWeight:700, fontSize:12, marginBottom:10}}>
            ✈️ {form.my==="Host"?"NÁŠ TÝM (Hosté)":"SOUPEŘ (Hosté)"}
          </div>
          {["H1","H2","H3","H4","H5"].map(pos=>(
            <div key={pos} style={{display:"flex", alignItems:"center", gap:8, marginBottom:6}}>
              <span style={{color:COLORS.hostAcc, width:24, fontWeight:700, fontSize:12}}>{pos}</span>
              {form.my==="Host" ? (
                <select value={form.hraci_my[pos]||""} onChange={e=>updatePlayer("hraci_my",pos,e.target.value)} style={{...css.select, flex:1}}>
                  <option value="">— hráč —</option>
                  {NASI_HRACI.map(h=><option key={h}>{h}</option>)}
                </select>
              ) : (
                <input placeholder="Jméno hráče" value={form.hraci_soupere[pos]||""} 
                  onChange={e=>updatePlayer("hraci_soupere",pos,e.target.value)} style={{...css.input, flex:1}}/>
              )}
            </div>
          ))}
        </div>
      </div>
      
      {/* Match table */}
      <div style={css.card}>
        <div style={{color:COLORS.gold, fontWeight:700, fontSize:12, marginBottom:10}}>📋 VÝSLEDKY ZÁPASŮ</div>
        
        <div style={{overflowX:"auto"}}>
          <table style={css.table}>
            <thead>
              <tr>
                <th style={{...css.th(), width:30}}>#</th>
                <th style={{...css.th(), width:60}}>Typ</th>
                <th style={{...css.th(COLORS.domBg)}}>Domácí</th>
                <th style={{...css.th(COLORS.hostBg)}}>Hosté</th>
                <th style={{...css.th(), width:100}}>Skóre</th>
              </tr>
            </thead>
            <tbody>
              {singlesLayout.filter(z=>z.n<=8).map(z=>{
                const dName = form.hraci_my?.[form.my==="Domácí"?z.d:z.h] || (form.hraci_soupere?.[form.my==="Host"?z.d:z.h]) || z.d;
                const hName = form.hraci_my?.[form.my==="Host"?z.h:null] || form.hraci_soupere?.[form.my==="Domácí"?z.h:null] || z.h;
                const bg = z.n%2===0?COLORS.mid:COLORS.card;
                return (
                  <tr key={z.n} style={{background:bg}}>
                    <td style={css.td(bg)}>{z.n}</td>
                    <td style={{...css.td(bg), color:COLORS.muted, fontSize:11}}>Single</td>
                    <td style={{...css.td(COLORS.domBg), textAlign:"left"}}>{z.d}: {form.hraci_my?.[z.d]||form.hraci_soupere?.[z.d]||z.d}</td>
                    <td style={{...css.td(COLORS.hostBg), textAlign:"left"}}>{z.h}: {form.hraci_my?.[z.h]||form.hraci_soupere?.[z.h]||z.h}</td>
                    <td style={css.td(bg)}>
                      <select value={singles[z.n]||""} onChange={e=>setSingles(s=>({...s,[z.n]:e.target.value}))} style={{...css.select, padding:"3px 6px", fontSize:12}}>
                        {scoreOptions.map(o=><option key={o||"x"}>{o}</option>)}
                      </select>
                    </td>
                  </tr>
                );
              })}
              
              {/* Double block */}
              <tr style={{background:"#0a2a1a"}}>
                <td colSpan={5} style={{padding:"10px 14px"}}>
                  <div style={{display:"flex", alignItems:"center", justifyContent:"space-between"}}>
                    <span style={{color:"#10b981", fontWeight:700}}>m9 🎯 DOUBLE — Terč 1: D1+D3 vs H1+H5 | Terč 2: D2+D4 vs H3+H4</span>
                    <select value={dcScores[9]} onChange={e=>setDcScores(s=>({...s,9:e.target.value}))} style={{...css.select, width:"auto", padding:"3px 10px"}}>
                      {scoreOptions.map(o=><option key={o||"x"}>{o}</option>)}
                    </select>
                  </div>
                  {(dcScores[9]==="2:1"||dcScores[9]==="1:2") && (
                    <div style={{marginTop:6, color:COLORS.gold, fontSize:11}}>⚡ Rozhodující terč: D3+D4 vs H1+H4</div>
                  )}
                </td>
              </tr>
              
              {/* Cricket block */}
              <tr style={{background:"#1a0a2a"}}>
                <td colSpan={5} style={{padding:"10px 14px"}}>
                  <div style={{display:"flex", alignItems:"center", justifyContent:"space-between"}}>
                    <span style={{color:"#a78bfa", fontWeight:700}}>m10 🏏 CRICKET — Terč 1: D3+D4 vs H1+H4 | Terč 2: D1+D2 vs H2+H3</span>
                    <select value={dcScores[10]} onChange={e=>setDcScores(s=>({...s,10:e.target.value}))} style={{...css.select, width:"auto", padding:"3px 10px"}}>
                      {scoreOptions.map(o=><option key={o||"x"}>{o}</option>)}
                    </select>
                  </div>
                  {(dcScores[10]==="2:1"||dcScores[10]==="1:2") && (
                    <div style={{marginTop:6, color:COLORS.gold, fontSize:11}}>⚡ Rozhodující terč: D3+D4 vs H1+H4</div>
                  )}
                </td>
              </tr>
              
              {singlesLayout.filter(z=>z.n>=11).map(z=>{
                const bg = z.n%2===0?COLORS.mid:COLORS.card;
                return (
                  <tr key={z.n} style={{background:bg}}>
                    <td style={css.td(bg)}>{z.n}</td>
                    <td style={{...css.td(bg), color:COLORS.muted, fontSize:11}}>Single</td>
                    <td style={{...css.td(COLORS.domBg), textAlign:"left"}}>{z.d}: {form.hraci_my?.[z.d]||form.hraci_soupere?.[z.d]||z.d}</td>
                    <td style={{...css.td(COLORS.hostBg), textAlign:"left"}}>{z.h}: {form.hraci_my?.[z.h]||form.hraci_soupere?.[z.h]||z.h}</td>
                    <td style={css.td(bg)}>
                      <select value={singles[z.n]||""} onChange={e=>setSingles(s=>({...s,[z.n]:e.target.value}))} style={{...css.select, padding:"3px 6px", fontSize:12}}>
                        {scoreOptions.map(o=><option key={o||"x"}>{o}</option>)}
                      </select>
                    </td>
                  </tr>
                );
              })}
            </tbody>
          </table>
        </div>
        
        <div style={{display:"flex", gap:8, marginTop:12, justifyContent:"flex-end"}}>
          <button onClick={onBack} style={css.btn("ghost")}>Zrušit</button>
          <button style={css.btn("success")}>💾 Uložit zápas</button>
        </div>
      </div>
    </div>
  );
}

// ─── MAIN APP ─────────────────────────────────────────────────────────────────
export default function App(){
  const [view, setView] = useState("season"); // season | match | stats | new
  const [selectedKolo, setSelectedKolo] = useState(null);
  
  const navItems = [
    {id:"season",label:"📅 Přehled sezóny"},
    {id:"stats",label:"📊 Statistiky"},
    {id:"new",label:"➕ Nový zápas"},
  ];
  
  return (
    <div style={css.app}>
      {/* Header */}
      <div style={css.header}>
        <div style={{display:"flex", alignItems:"center", gap:10}}>
          <span style={{fontSize:24}}>🎯</span>
          <div>
            <div style={{fontWeight:700, fontSize:15, color:COLORS.gold}}>5. Avenue Praha</div>
            <div style={{fontSize:11, color:COLORS.muted}}>3. Liga N · 2025/2026</div>
          </div>
        </div>
        <nav style={css.nav}>
          {navItems.map(n=>(
            <button key={n.id} onClick={()=>setView(n.id)} style={css.navBtn(view===n.id && n.id!=="match")}>
              {n.label}
            </button>
          ))}
        </nav>
      </div>
      
      {/* Content */}
      {view==="season" && (
        <SeasonView onSelect={(kolo)=>{setSelectedKolo(kolo); setView("match");}}/>
      )}
      {view==="match" && selectedKolo && (
        <MatchDetail kolo={selectedKolo} onBack={()=>setView("season")}/>
      )}
      {view==="stats" && <StatisticsView/>}
      {view==="new" && <NewMatchForm onBack={()=>setView("season")}/>}
    </div>
  );
}
