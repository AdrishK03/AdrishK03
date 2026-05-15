<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Adrish Karmakar – GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg: #020617;
  --bg2: #0f172a;
  --bg3: #1e293b;
  --purple: #7c3aed;
  --purple2: #9333ea;
  --cyan: #22d3ee;
  --pink: #f472b6;
  --green: #4ade80;
  --amber: #fbbf24;
  --red: #f87171;
  --text: #e2e8f0;
  --muted: #64748b;
  --border: rgba(124,58,237,0.25);
  --glow: rgba(124,58,237,0.15);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Space Grotesk', sans-serif;
  line-height: 1.6;
  overflow-x: hidden;
}

/* ── GRID CANVAS BG ── */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image:
    linear-gradient(rgba(124,58,237,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(124,58,237,0.04) 1px, transparent 1px);
  background-size: 60px 60px;
  pointer-events: none;
  z-index: 0;
}

.container {
  max-width: 960px;
  margin: 0 auto;
  padding: 0 24px;
  position: relative;
  z-index: 1;
}

/* ══════════════════════════
   HERO
══════════════════════════ */
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 80px 24px 60px;
  position: relative;
  overflow: hidden;
}

/* Animated radial pulse */
.hero::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 800px;
  height: 800px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(124,58,237,0.08) 0%, transparent 70%);
  animation: pulse 4s ease-in-out infinite;
  pointer-events: none;
}

@keyframes pulse {
  0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0.6; }
  50% { transform: translate(-50%, -50%) scale(1.15); opacity: 1; }
}

/* Floating orbs */
.orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.25;
  animation: drift 10s ease-in-out infinite;
  pointer-events: none;
}
.orb1 { width: 400px; height: 400px; background: var(--purple); top: -100px; left: -150px; animation-delay: 0s; }
.orb2 { width: 300px; height: 300px; background: var(--pink); bottom: -80px; right: -100px; animation-delay: -4s; }
.orb3 { width: 200px; height: 200px; background: var(--cyan); top: 40%; right: 5%; animation-delay: -2s; }

@keyframes drift {
  0%, 100% { transform: translate(0, 0) scale(1); }
  33% { transform: translate(30px, -30px) scale(1.05); }
  66% { transform: translate(-20px, 20px) scale(0.97); }
}

.hero-eyebrow {
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  color: var(--cyan);
  letter-spacing: 3px;
  text-transform: uppercase;
  margin-bottom: 16px;
  opacity: 0;
  animation: fadeUp 0.8s 0.2s forwards;
}

.hero-name {
  font-family: 'Syne', sans-serif;
  font-size: clamp(52px, 8vw, 96px);
  font-weight: 800;
  background: linear-gradient(135deg, #fff 0%, var(--cyan) 40%, var(--purple) 70%, var(--pink) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1.05;
  margin-bottom: 8px;
  opacity: 0;
  animation: fadeUp 0.8s 0.4s forwards;
}

.hero-sub {
  font-size: 18px;
  color: var(--muted);
  margin-bottom: 32px;
  opacity: 0;
  animation: fadeUp 0.8s 0.6s forwards;
}

.hero-sub span {
  color: var(--purple2);
  font-weight: 600;
}

/* Typing animation */
.typewriter {
  font-family: 'JetBrains Mono', monospace;
  font-size: 16px;
  color: var(--green);
  margin-bottom: 40px;
  min-height: 28px;
  opacity: 0;
  animation: fadeUp 0.8s 0.8s forwards;
}

.cursor {
  display: inline-block;
  width: 2px;
  height: 18px;
  background: var(--green);
  vertical-align: middle;
  margin-left: 2px;
  animation: blink 1s step-end infinite;
}
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

/* Status badge */
.status-row {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
  justify-content: center;
  margin-bottom: 40px;
  opacity: 0;
  animation: fadeUp 0.8s 1s forwards;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 16px;
  border-radius: 100px;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.5px;
  border: 1px solid;
  transition: all 0.3s;
}

.badge-purple { background: rgba(124,58,237,0.15); border-color: rgba(124,58,237,0.4); color: #a78bfa; }
.badge-cyan { background: rgba(34,211,238,0.1); border-color: rgba(34,211,238,0.35); color: var(--cyan); }
.badge-pink { background: rgba(244,114,182,0.1); border-color: rgba(244,114,182,0.35); color: var(--pink); }
.badge-green { background: rgba(74,222,128,0.1); border-color: rgba(74,222,128,0.35); color: var(--green); }

.badge:hover { transform: translateY(-2px); filter: brightness(1.2); }

/* Social links */
.socials {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
  justify-content: center;
  opacity: 0;
  animation: fadeUp 0.8s 1.2s forwards;
}

.social-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 20px;
  border-radius: 10px;
  font-size: 13px;
  font-weight: 600;
  text-decoration: none;
  border: 1px solid var(--border);
  background: rgba(255,255,255,0.04);
  color: var(--text);
  transition: all 0.3s cubic-bezier(0.4,0,0.2,1);
  backdrop-filter: blur(10px);
}
.social-btn:hover {
  background: rgba(124,58,237,0.2);
  border-color: var(--purple);
  transform: translateY(-3px);
  box-shadow: 0 8px 24px rgba(124,58,237,0.25);
  color: #fff;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Scroll indicator */
.scroll-hint {
  position: absolute;
  bottom: 32px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 6px;
  opacity: 0.4;
  font-size: 11px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--muted);
  animation: scrollBounce 2s ease-in-out infinite;
}
.scroll-hint svg { width: 16px; height: 16px; }
@keyframes scrollBounce { 0%,100%{transform:translateX(-50%) translateY(0)} 50%{transform:translateX(-50%) translateY(6px)} }

/* ══════════════════════════
   SECTION BASE
══════════════════════════ */
section {
  padding: 96px 0;
  position: relative;
}

.section-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--purple2);
  letter-spacing: 3px;
  text-transform: uppercase;
  margin-bottom: 12px;
}

.section-title {
  font-family: 'Syne', sans-serif;
  font-size: clamp(28px, 4vw, 40px);
  font-weight: 800;
  color: #fff;
  margin-bottom: 48px;
}

.section-title span {
  background: linear-gradient(90deg, var(--purple), var(--cyan));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* Divider */
.divider {
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--purple), transparent);
  margin: 0 0 96px;
  opacity: 0.4;
}

/* ══════════════════════════
   ABOUT
══════════════════════════ */
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 32px;
}

.about-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 28px;
  transition: all 0.4s;
  position: relative;
  overflow: hidden;
}
.about-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--purple), transparent);
  opacity: 0;
  transition: opacity 0.4s;
}
.about-card:hover { border-color: rgba(124,58,237,0.5); transform: translateY(-4px); box-shadow: 0 20px 40px rgba(124,58,237,0.1); }
.about-card:hover::before { opacity: 1; }

.about-card h3 {
  font-size: 13px;
  font-family: 'JetBrains Mono', monospace;
  color: var(--cyan);
  letter-spacing: 1.5px;
  text-transform: uppercase;
  margin-bottom: 16px;
}

.about-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.about-list li {
  font-size: 14px;
  color: var(--muted);
  display: flex;
  align-items: center;
  gap: 8px;
  transition: color 0.2s;
}
.about-list li::before {
  content: '▸';
  color: var(--purple2);
  font-size: 10px;
  flex-shrink: 0;
}
.about-list li:hover { color: var(--text); }

/* ══════════════════════════
   TECH ARSENAL
══════════════════════════ */
.tech-category {
  margin-bottom: 48px;
}

.tech-cat-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 20px;
}

.tech-cat-icon {
  font-size: 18px;
}

.tech-cat-title {
  font-size: 14px;
  font-weight: 700;
  color: var(--text);
  letter-spacing: 0.5px;
}

.tech-cat-line {
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, rgba(124,58,237,0.4), transparent);
}

.tech-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.tech-chip {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 8px 16px;
  border-radius: 10px;
  font-size: 13px;
  font-weight: 500;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);
  color: var(--text);
  transition: all 0.3s cubic-bezier(0.4,0,0.2,1);
  cursor: default;
  position: relative;
  overflow: hidden;
}
.tech-chip::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(124,58,237,0.15), transparent);
  opacity: 0;
  transition: opacity 0.3s;
}
.tech-chip:hover {
  border-color: rgba(124,58,237,0.5);
  transform: translateY(-3px) scale(1.02);
  box-shadow: 0 8px 20px rgba(124,58,237,0.2);
}
.tech-chip:hover::before { opacity: 1; }

.tech-chip img {
  width: 20px;
  height: 20px;
  object-fit: contain;
}

.tech-chip .tech-dot {
  width: 8px; height: 8px;
  border-radius: 50%;
  flex-shrink: 0;
}

/* ══════════════════════════
   PROJECTS
══════════════════════════ */
.projects-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.project-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid var(--border);
  border-radius: 20px;
  padding: 32px;
  position: relative;
  overflow: hidden;
  transition: all 0.4s cubic-bezier(0.4,0,0.2,1);
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.project-card::after {
  content: '';
  position: absolute;
  top: -1px; left: -1px; right: -1px;
  height: 2px;
  border-radius: 20px 20px 0 0;
  background: linear-gradient(90deg, var(--purple), var(--cyan));
  opacity: 0;
  transition: opacity 0.4s;
}

.project-card:hover {
  transform: translateY(-6px);
  border-color: rgba(124,58,237,0.4);
  box-shadow: 0 24px 48px rgba(0,0,0,0.4), 0 0 40px rgba(124,58,237,0.1);
}
.project-card:hover::after { opacity: 1; }

.project-glow {
  position: absolute;
  width: 200px; height: 200px;
  border-radius: 50%;
  filter: blur(60px);
  opacity: 0.08;
  top: -40px; right: -40px;
  pointer-events: none;
  transition: opacity 0.4s;
}
.project-card:hover .project-glow { opacity: 0.18; }

.project-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 12px;
}

.project-emoji {
  font-size: 28px;
  line-height: 1;
}

.live-badge {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  padding: 4px 10px;
  border-radius: 100px;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.5px;
  background: rgba(74,222,128,0.15);
  border: 1px solid rgba(74,222,128,0.3);
  color: var(--green);
  text-decoration: none;
  transition: all 0.3s;
}
.live-badge:hover { background: rgba(74,222,128,0.25); }
.live-dot {
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--green);
  animation: livePulse 2s ease-in-out infinite;
}
@keyframes livePulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.5;transform:scale(0.8)} }

.project-name {
  font-family: 'Syne', sans-serif;
  font-size: 20px;
  font-weight: 800;
  color: #fff;
}

.project-desc {
  font-size: 13px;
  color: var(--muted);
  line-height: 1.6;
}

.project-features {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.feature-tag {
  font-size: 11px;
  padding: 3px 10px;
  border-radius: 6px;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.08);
  color: #94a3b8;
}

.project-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-top: auto;
  padding-top: 16px;
  border-top: 1px solid rgba(255,255,255,0.06);
}

.stack-pill {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  font-weight: 700;
  padding: 3px 8px;
  border-radius: 5px;
  letter-spacing: 0.5px;
  text-transform: uppercase;
}

/* ══════════════════════════
   EXPERTISE
══════════════════════════ */
.expertise-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 20px;
}

.expertise-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 24px;
  transition: all 0.4s;
}
.expertise-card:hover {
  border-color: rgba(124,58,237,0.4);
  transform: translateY(-4px);
  box-shadow: 0 16px 32px rgba(124,58,237,0.08);
}

.expertise-icon {
  font-size: 24px;
  margin-bottom: 12px;
  display: block;
}

.expertise-title {
  font-size: 15px;
  font-weight: 700;
  color: #fff;
  margin-bottom: 14px;
}

.expertise-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 7px;
}
.expertise-list li {
  font-size: 12px;
  color: var(--muted);
  display: flex;
  align-items: center;
  gap: 7px;
}
.expertise-list li::before {
  content: '';
  width: 3px; height: 3px;
  border-radius: 50%;
  background: var(--purple2);
  flex-shrink: 0;
}

/* ══════════════════════════
   CURRENTLY BUILDING
══════════════════════════ */
.building-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 14px;
}

.building-item {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 18px 24px;
  background: rgba(255,255,255,0.03);
  border: 1px solid var(--border);
  border-radius: 12px;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}
.building-item::before {
  content: '';
  position: absolute;
  left: 0; top: 0; bottom: 0;
  width: 3px;
  background: linear-gradient(180deg, var(--purple), var(--cyan));
  border-radius: 3px 0 0 3px;
}
.building-item:hover {
  border-color: rgba(124,58,237,0.4);
  transform: translateX(4px);
}

.building-num {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--purple2);
  font-weight: 700;
  min-width: 24px;
}

.building-text {
  font-size: 14px;
  color: var(--text);
  font-weight: 500;
}

/* ══════════════════════════
   GITHUB STATS
══════════════════════════ */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  margin-bottom: 32px;
}

.stat-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 24px;
  text-align: center;
  transition: all 0.4s;
}
.stat-card:hover {
  border-color: rgba(124,58,237,0.4);
  transform: translateY(-4px);
  box-shadow: 0 16px 32px rgba(124,58,237,0.1);
}
.stat-val {
  font-family: 'Syne', sans-serif;
  font-size: 36px;
  font-weight: 800;
  background: linear-gradient(135deg, var(--purple), var(--cyan));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.stat-label {
  font-size: 12px;
  color: var(--muted);
  margin-top: 4px;
  letter-spacing: 0.5px;
}

.github-img-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  margin-bottom: 16px;
}

.github-img-row img {
  width: 100%;
  border-radius: 12px;
  border: 1px solid var(--border);
  transition: all 0.4s;
}
.github-img-row img:hover { border-color: rgba(124,58,237,0.5); transform: scale(1.01); }

.github-img-full img {
  width: 100%;
  border-radius: 12px;
  border: 1px solid var(--border);
  transition: all 0.4s;
}
.github-img-full img:hover { border-color: rgba(124,58,237,0.5); }

/* ══════════════════════════
   FOOTER
══════════════════════════ */
.footer {
  padding: 60px 24px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.footer::before {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 200px;
  background: linear-gradient(0deg, rgba(124,58,237,0.08), transparent);
  pointer-events: none;
}
.footer-title {
  font-family: 'Syne', sans-serif;
  font-size: clamp(24px, 4vw, 36px);
  font-weight: 800;
  color: #fff;
  margin-bottom: 12px;
}
.footer-sub {
  font-size: 14px;
  color: var(--muted);
  margin-bottom: 32px;
}
.footer-tags {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
  justify-content: center;
  margin-bottom: 40px;
}
.footer-tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--purple2);
  padding: 4px 12px;
  border-radius: 100px;
  border: 1px solid rgba(124,58,237,0.3);
  background: rgba(124,58,237,0.08);
}

/* ══════════════════════════
   SCROLL REVEAL
══════════════════════════ */
.reveal {
  opacity: 0;
  transform: translateY(32px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* ══════════════════════════
   TROPHIES
══════════════════════════ */
.trophy-row {
  border-radius: 12px;
  overflow: hidden;
  border: 1px solid var(--border);
  margin-bottom: 32px;
}
.trophy-row img { width: 100%; display: block; }

/* ══════════════════════════
   RESPONSIVE
══════════════════════════ */
@media (max-width: 768px) {
  .about-grid, .projects-grid, .expertise-grid { grid-template-columns: 1fr; }
  .stats-grid { grid-template-columns: 1fr 1fr; }
  .github-img-row { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<!-- ══ HERO ══ -->
<section class="hero">
  <div class="orb orb1"></div>
  <div class="orb orb2"></div>
  <div class="orb orb3"></div>

  <p class="hero-eyebrow">// init profile.adrish.dev</p>
  <h1 class="hero-name">Adrish Karmakar</h1>
  <p class="hero-sub">
    <span>AI Systems Engineer</span> &nbsp;•&nbsp; Full Stack Architect &nbsp;•&nbsp; ML Innovator
  </p>

  <div class="typewriter">
    <span id="typed"></span><span class="cursor"></span>
  </div>

  <div class="status-row">
    <span class="badge badge-green">⚡ Open for Collaboration</span>
    <span class="badge badge-purple">🎓 B.Tech ECS 2027</span>
    <span class="badge badge-cyan">🤖 AI + IoT Builder</span>
    <span class="badge badge-pink">🚀 Full Stack Dev</span>
  </div>

  <div class="socials">
    <a class="social-btn" href="https://portfolio-ak-ten.vercel.app/" target="_blank">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 014 10 15.3 15.3 0 01-4 10 15.3 15.3 0 01-4-10 15.3 15.3 0 014-10z"/></svg>
      Portfolio
    </a>
    <a class="social-btn" href="mailto:adrishk2003@gmail.com">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      Gmail
    </a>
    <a class="social-btn" href="https://www.linkedin.com/in/adrish-karmakar-15338428b" target="_blank">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
      LinkedIn
    </a>
    <a class="social-btn" href="https://github.com/AdrishK03" target="_blank">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22"/></svg>
      GitHub
    </a>
  </div>

  <div class="scroll-hint">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="6 9 12 15 18 9"/></svg>
    scroll
  </div>
</section>

<div class="divider"></div>

<!-- ══ ABOUT ══ -->
<section>
  <div class="container">
    <p class="section-label reveal">// about.me</p>
    <h2 class="section-title reveal">Who I <span>Am</span></h2>

    <div class="about-grid">
      <div class="about-card reveal">
        <h3>🎯 Focus Areas</h3>
        <ul class="about-list">
          <li>Artificial Intelligence & ML Systems</li>
          <li>Full Stack Development</li>
          <li>Backend Architecture & APIs</li>
          <li>IoT + Embedded Systems</li>
          <li>Real-Time Applications</li>
          <li>Scalable API Development</li>
        </ul>
      </div>
      <div class="about-card reveal" style="transition-delay:0.1s">
        <h3>🔭 Currently Exploring</h3>
        <ul class="about-list">
          <li>AI System Design & Architecture</li>
          <li>Distributed Backend Systems</li>
          <li>Real-Time ML Infrastructure</li>
          <li>AI + IoT Automation</li>
          <li>Production-Grade AI Pipelines</li>
          <li>Computer Vision at Scale</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ══ TECH ARSENAL ══ -->
<section>
  <div class="container">
    <p class="section-label reveal">// tech.arsenal</p>
    <h2 class="section-title reveal">⚡ Tech <span>Arsenal</span></h2>

    <!-- Programming Languages -->
    <div class="tech-category reveal">
      <div class="tech-cat-header">
        <span class="tech-cat-icon">👨‍💻</span>
        <span class="tech-cat-title">Programming Languages</span>
        <div class="tech-cat-line"></div>
      </div>
      <div class="tech-grid">
        <div class="tech-chip"><span class="tech-dot" style="background:#f89820"></span> Java</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#3776ab"></span> Python</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#f7df1e"></span> JavaScript</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#3178c6"></span> TypeScript</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#a8b9cc"></span> C</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#00618a"></span> MySQL</div>
      </div>
    </div>

    <!-- Frontend -->
    <div class="tech-category reveal">
      <div class="tech-cat-header">
        <span class="tech-cat-icon">🎨</span>
        <span class="tech-cat-title">Frontend Development</span>
        <div class="tech-cat-line"></div>
      </div>
      <div class="tech-grid">
        <div class="tech-chip"><span class="tech-dot" style="background:#61dafb"></span> React</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#06b6d4"></span> Tailwind CSS</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#e34f26"></span> HTML5</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#1572b6"></span> CSS3</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#646cff"></span> Vite</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#000000"></span> Next.js</div>
      </div>
    </div>

    <!-- Backend -->
    <div class="tech-category reveal">
      <div class="tech-cat-header">
        <span class="tech-cat-icon">⚙️</span>
        <span class="tech-cat-title">Backend Development</span>
        <div class="tech-cat-line"></div>
      </div>
      <div class="tech-grid">
        <div class="tech-chip"><span class="tech-dot" style="background:#339933"></span> Node.js</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#000000"></span> Express.js</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#009688"></span> FastAPI</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#ffca28"></span> Firebase</div>
      </div>
    </div>

    <!-- AI / ML -->
    <div class="tech-category reveal">
      <div class="tech-cat-header">
        <span class="tech-cat-icon">🤖</span>
        <span class="tech-cat-title">AI / Machine Learning</span>
        <div class="tech-cat-line"></div>
      </div>
      <div class="tech-grid">
        <div class="tech-chip"><span class="tech-dot" style="background:#ff6f00"></span> TensorFlow</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#ee4c2c"></span> PyTorch</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#5c3ee8"></span> OpenCV</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#f7931e"></span> Scikit-Learn</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#ff5722"></span> XGBoost</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#8e24aa"></span> NLP</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#0ea5e9"></span> Deep Learning</div>
      </div>
    </div>

    <!-- Databases -->
    <div class="tech-category reveal">
      <div class="tech-cat-header">
        <span class="tech-cat-icon">🗄️</span>
        <span class="tech-cat-title">Databases</span>
        <div class="tech-cat-line"></div>
      </div>
      <div class="tech-grid">
        <div class="tech-chip"><span class="tech-dot" style="background:#47a248"></span> MongoDB</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#00618a"></span> MySQL</div>
      </div>
    </div>

    <!-- DevOps -->
    <div class="tech-category reveal">
      <div class="tech-cat-header">
        <span class="tech-cat-icon">☁️</span>
        <span class="tech-cat-title">DevOps &amp; Deployment</span>
        <div class="tech-cat-line"></div>
      </div>
      <div class="tech-grid">
        <div class="tech-chip"><span class="tech-dot" style="background:#f05032"></span> Git</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#181717"></span> GitHub</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#2496ed"></span> Docker</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#ff6c37"></span> Postman</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#000000"></span> Vercel</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#46e3b7"></span> Render</div>
      </div>
    </div>

    <!-- IoT -->
    <div class="tech-category reveal">
      <div class="tech-cat-header">
        <span class="tech-cat-icon">🔌</span>
        <span class="tech-cat-title">IoT &amp; Embedded Systems</span>
        <div class="tech-cat-line"></div>
      </div>
      <div class="tech-grid">
        <div class="tech-chip"><span class="tech-dot" style="background:#00979c"></span> Arduino</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#c51a4a"></span> Raspberry Pi</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#111111"></span> ESP32</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#1e88e5"></span> Sensors</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#ff6f00"></span> IoT</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ══ PROJECTS ══ -->
<section>
  <div class="container">
    <p class="section-label reveal">// featured.projects</p>
    <h2 class="section-title reveal">🚀 Featured <span>Projects</span></h2>

    <div class="projects-grid">

      <!-- KrishiSahyog -->
      <div class="project-card reveal" style="transition-delay:0s">
        <div class="project-glow" style="background:var(--green)"></div>
        <div class="project-header">
          <span class="project-emoji">🌾</span>
          <a class="live-badge" href="https://krishisahyog-mauve.vercel.app/" target="_blank">
            <span class="live-dot"></span> LIVE
          </a>
        </div>
        <div class="project-name">KrishiSahyog</div>
        <div class="project-desc">AI-powered smart farming platform integrating crop advisory, plant disease detection, and IoT sensors to revolutionize agricultural decision-making.</div>
        <div class="project-features">
          <span class="feature-tag">AI Crop Advisory</span>
          <span class="feature-tag">Plant Disease Detection</span>
          <span class="feature-tag">Smart Recommendations</span>
          <span class="feature-tag">Weather Insights</span>
          <span class="feature-tag">IoT Sensor Integration</span>
        </div>
        <div class="project-stack">
          <span class="stack-pill" style="background:rgba(97,218,251,0.15);color:#61dafb;border:1px solid rgba(97,218,251,0.25)">React</span>
          <span class="stack-pill" style="background:rgba(0,150,136,0.15);color:#4db6ac;border:1px solid rgba(0,150,136,0.25)">FastAPI</span>
          <span class="stack-pill" style="background:rgba(255,111,0,0.15);color:#ffb74d;border:1px solid rgba(255,111,0,0.25)">EfficientNet</span>
          <span class="stack-pill" style="background:rgba(124,58,237,0.15);color:#a78bfa;border:1px solid rgba(124,58,237,0.25)">ML • AI</span>
        </div>
      </div>

      <!-- Citizen Grievance System -->
      <div class="project-card reveal" style="transition-delay:0.1s">
        <div class="project-glow" style="background:var(--purple)"></div>
        <div class="project-header">
          <span class="project-emoji">🧠</span>
        </div>
        <div class="project-name">Citizen Grievance System</div>
        <div class="project-desc">Intelligent complaint management system using NLP to classify, prioritize, and route citizen grievances with real-time dashboard insights.</div>
        <div class="project-features">
          <span class="feature-tag">Complaint Classification</span>
          <span class="feature-tag">NLP Processing</span>
          <span class="feature-tag">Urgency Prediction</span>
          <span class="feature-tag">Real-Time Dashboard</span>
          <span class="feature-tag">Smart Data Insights</span>
        </div>
        <div class="project-stack">
          <span class="stack-pill" style="background:rgba(0,150,136,0.15);color:#4db6ac;border:1px solid rgba(0,150,136,0.25)">FastAPI</span>
          <span class="stack-pill" style="background:rgba(142,36,170,0.15);color:#ce93d8;border:1px solid rgba(142,36,170,0.25)">NLP</span>
          <span class="stack-pill" style="background:rgba(247,147,30,0.15);color:#ffcc80;border:1px solid rgba(247,147,30,0.25)">Scikit-learn</span>
          <span class="stack-pill" style="background:rgba(255,75,107,0.15);color:#ff8a80;border:1px solid rgba(255,75,107,0.25)">Streamlit</span>
        </div>
      </div>

      <!-- SpotifyClone -->
      <div class="project-card reveal" style="transition-delay:0.2s">
        <div class="project-glow" style="background:#1DB954"></div>
        <div class="project-header">
          <span class="project-emoji">🎵</span>
        </div>
        <div class="project-name">SpotifyClone</div>
        <div class="project-desc">Full-featured music streaming clone with secure JWT authentication, playlist management, and RESTful API integration.</div>
        <div class="project-features">
          <span class="feature-tag">JWT Authentication</span>
          <span class="feature-tag">Playlist Management</span>
          <span class="feature-tag">Protected Routes</span>
          <span class="feature-tag">User Dashboard</span>
          <span class="feature-tag">REST API</span>
        </div>
        <div class="project-stack">
          <span class="stack-pill" style="background:rgba(51,153,51,0.15);color:#81c784;border:1px solid rgba(51,153,51,0.25)">Node.js</span>
          <span class="stack-pill" style="background:rgba(0,0,0,0.3);color:#b0bec5;border:1px solid rgba(255,255,255,0.12)">Express.js</span>
          <span class="stack-pill" style="background:rgba(71,162,72,0.15);color:#a5d6a7;border:1px solid rgba(71,162,72,0.25)">MongoDB</span>
        </div>
      </div>

      <!-- HospitalLink -->
      <div class="project-card reveal" style="transition-delay:0.3s">
        <div class="project-glow" style="background:var(--cyan)"></div>
        <div class="project-header">
          <span class="project-emoji">🏥</span>
        </div>
        <div class="project-name">HospitalLink</div>
        <div class="project-desc">Comprehensive healthcare workflow platform for appointment scheduling, patient data management, and streamlined admin operations.</div>
        <div class="project-features">
          <span class="feature-tag">Appointment Scheduling</span>
          <span class="feature-tag">Healthcare Workflow</span>
          <span class="feature-tag">Patient Data Handling</span>
          <span class="feature-tag">Admin Dashboard</span>
        </div>
        <div class="project-stack">
          <span class="stack-pill" style="background:rgba(227,79,38,0.15);color:#ef9a9a;border:1px solid rgba(227,79,38,0.25)">HTML</span>
          <span class="stack-pill" style="background:rgba(21,114,182,0.15);color:#90caf9;border:1px solid rgba(21,114,182,0.25)">CSS</span>
          <span class="stack-pill" style="background:rgba(247,223,30,0.15);color:#fff176;border:1px solid rgba(247,223,30,0.25)">JavaScript</span>
        </div>
      </div>

      <!-- Portfolio -->
      <div class="project-card reveal" style="transition-delay:0.4s; grid-column: 1/-1;">
        <div class="project-glow" style="background:var(--pink)"></div>
        <div class="project-header">
          <span class="project-emoji">💼</span>
          <a class="live-badge" href="https://portfolio-ak-ten.vercel.app/" target="_blank">
            <span class="live-dot"></span> LIVE
          </a>
        </div>
        <div class="project-name">MyPortfolio</div>
        <div class="project-desc">A sleek, production-grade personal portfolio with smooth animations, fully responsive design, a modern dark theme, and optimized performance. Built to leave a lasting impression.</div>
        <div class="project-features">
          <span class="feature-tag">Smooth Animations</span>
          <span class="feature-tag">Fully Responsive</span>
          <span class="feature-tag">Dark Theme</span>
          <span class="feature-tag">Optimized Performance</span>
          <span class="feature-tag">Interactive Sections</span>
        </div>
        <div class="project-stack">
          <span class="stack-pill" style="background:rgba(97,218,251,0.15);color:#61dafb;border:1px solid rgba(97,218,251,0.25)">React</span>
          <span class="stack-pill" style="background:rgba(6,182,212,0.15);color:#67e8f9;border:1px solid rgba(6,182,212,0.25)">Tailwind CSS</span>
          <span class="stack-pill" style="background:rgba(0,0,0,0.3);color:#b0bec5;border:1px solid rgba(255,255,255,0.12)">Vercel</span>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ══ EXPERTISE ══ -->
<section>
  <div class="container">
    <p class="section-label reveal">// core.expertise</p>
    <h2 class="section-title reveal">🧠 Core <span>Expertise</span></h2>

    <div class="expertise-grid">
      <!-- CS Fundamentals -->
      <div class="expertise-card reveal">
        <span class="expertise-icon">📚</span>
        <div class="expertise-title">CS Fundamentals</div>
        <ul class="expertise-list">
          <li>Data Structures &amp; Algorithms</li>
          <li>Object-Oriented Programming</li>
          <li>Database Management Systems</li>
          <li>Operating Systems</li>
          <li>Computer Networks</li>
        </ul>
      </div>
      <!-- AI Engineering -->
      <div class="expertise-card reveal" style="transition-delay:0.1s">
        <span class="expertise-icon">🤖</span>
        <div class="expertise-title">AI Engineering</div>
        <ul class="expertise-list">
          <li>Machine Learning Systems</li>
          <li>Computer Vision</li>
          <li>Intelligent Automation</li>
          <li>NLP Applications</li>
          <li>Predictive Analytics</li>
          <li>Real-Time Decision Systems</li>
        </ul>
      </div>
      <!-- Backend -->
      <div class="expertise-card reveal" style="transition-delay:0.2s">
        <span class="expertise-icon">⚙️</span>
        <div class="expertise-title">Backend Engineering</div>
        <ul class="expertise-list">
          <li>REST API Development</li>
          <li>JWT Authentication</li>
          <li>Database Design</li>
          <li>Backend Scalability</li>
          <li>API Security</li>
          <li>Microservices Fundamentals</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ══ CURRENTLY BUILDING ══ -->
<section>
  <div class="container">
    <p class="section-label reveal">// currently.building</p>
    <h2 class="section-title reveal">🔥 Currently <span>Building</span></h2>

    <div class="building-grid">
      <div class="building-item reveal" style="transition-delay:0s">
        <span class="building-num">01</span>
        <span class="building-text">AI Caretaker System for Elderly People</span>
      </div>
      <div class="building-item reveal" style="transition-delay:0.08s">
        <span class="building-num">02</span>
        <span class="building-text">Food Recommendation System using AI</span>
      </div>
      <div class="building-item reveal" style="transition-delay:0.16s">
        <span class="building-num">03</span>
        <span class="building-text">AI + IoT Smart Automation Systems</span>
      </div>
      <div class="building-item reveal" style="transition-delay:0.24s">
        <span class="building-num">04</span>
        <span class="building-text">Real-Time Backend Infrastructure</span>
      </div>
      <div class="building-item reveal" style="transition-delay:0.32s">
        <span class="building-num">05</span>
        <span class="building-text">Production-Grade Full Stack Applications</span>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ══ GITHUB STATS ══ -->
<section>
  <div class="container">
    <p class="section-label reveal">// github.analytics</p>
    <h2 class="section-title reveal">📈 GitHub <span>Analytics</span></h2>

    <div class="github-img-row reveal">
      <img src="https://github-readme-stats.vercel.app/api?username=AdrishK03&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=7c3aed&icon_color=22d3ee&text_color=e2e8f0" alt="GitHub Stats" loading="lazy"/>
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=AdrishK03&theme=tokyonight&hide_border=true&background=0D1117&ring=7c3aed&fire=f472b6&currStreakLabel=22d3ee" alt="GitHub Streak" loading="lazy"/>
    </div>

    <div class="github-img-full reveal">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=AdrishK03&layout=compact&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=7c3aed&text_color=e2e8f0" alt="Top Languages" loading="lazy"/>
    </div>

    <div style="height:20px"></div>

    <div class="trophy-row reveal">
      <img src="https://github-profile-trophy.vercel.app/?username=AdrishK03&theme=tokyonight&no-frame=true&row=1&column=7&title_color=7c3aed" alt="Trophies" loading="lazy"/>
    </div>

    <div class="github-img-full reveal">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=AdrishK03&theme=tokyo-night&hide_border=true&bg_color=0D1117&color=7c3aed&line=9333ea&point=22d3ee" alt="Activity Graph" loading="lazy"/>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ══ FOOTER ══ -->
<footer class="footer">
  <div class="container">
    <h2 class="footer-title reveal">Let's Build Something Amazing</h2>
    <p class="footer-sub reveal">Open to collaborations, projects, and exciting ideas.</p>
    <div class="footer-tags reveal">
      <span class="footer-tag">AI</span>
      <span class="footer-tag">Backend</span>
      <span class="footer-tag">Full Stack</span>
      <span class="footer-tag">IoT</span>
      <span class="footer-tag">Machine Learning</span>
    </div>
    <div class="socials reveal">
      <a class="social-btn" href="mailto:adrishk2003@gmail.com">📬 adrishk2003@gmail.com</a>
      <a class="social-btn" href="https://portfolio-ak-ten.vercel.app/" target="_blank">🌐 Portfolio</a>
    </div>
    <p style="margin-top:48px; font-family:'JetBrains Mono',monospace; font-size:11px; color:var(--muted);">
      © 2025 Adrish Karmakar &nbsp;•&nbsp; Built with passion
    </p>
  </div>
</footer>

<script>
// Typewriter
const lines = [
  'Building Production-Grade AI Systems...',
  'Full Stack Developer | Backend Engineer',
  'Machine Learning Engineer | IoT Innovator',
  'Designing Scalable Real-World Applications',
  'Creating Future-Ready Intelligent Solutions'
];
let li = 0, ci = 0, deleting = false;
const el = document.getElementById('typed');
function type() {
  const line = lines[li];
  if (!deleting) {
    el.textContent = line.slice(0, ++ci);
    if (ci === line.length) { deleting = true; setTimeout(type, 2000); return; }
  } else {
    el.textContent = line.slice(0, --ci);
    if (ci === 0) { deleting = false; li = (li + 1) % lines.length; }
  }
  setTimeout(type, deleting ? 35 : 65);
}
type();

// Scroll reveal
const obs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); } });
}, { threshold: 0.12 });
document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
</script>
</body>
</html>
