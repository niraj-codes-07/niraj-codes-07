<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Niraj Kumar — GitHub Profile</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg:        #060810;
    --surface:   #0d1117;
    --card:      #161b22;
    --border:    #21262d;
    --purple:    #a78bfa;
    --purple2:   #7c3aed;
    --violet:    #4c1d95;
    --gold:      #f59e0b;
    --green:     #3fb950;
    --text:      #e6edf3;
    --muted:     #8b949e;
    --glow:      0 0 20px rgba(124,58,237,0.4);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* ── GRID BACKGROUND ── */
  body::before {
    content: '';
    position: fixed; inset: 0; z-index: 0;
    background-image:
      linear-gradient(rgba(124,58,237,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,58,237,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  .container { max-width: 900px; margin: 0 auto; padding: 0 20px 60px; position: relative; z-index: 1; }

  /* ── HEADER WAVE ── */
  .wave-header {
    width: 100%; height: 220px; overflow: hidden;
    background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
    position: relative; margin-bottom: -1px;
  }
  .wave-header svg { position: absolute; bottom: 0; width: 100%; }
  .wave-header .header-text {
    position: absolute; inset: 0; display: flex; flex-direction: column;
    align-items: center; justify-content: center; gap: 8px;
    font-family: 'Syne', sans-serif;
  }
  .wave-header h1 {
    font-size: 2.8rem; font-weight: 800; color: #fff;
    letter-spacing: 2px;
    animation: fadeDown 0.8s ease both;
  }
  .wave-header .subtitle {
    font-size: 0.85rem; color: rgba(255,255,255,0.7);
    letter-spacing: 3px; text-transform: uppercase;
    animation: fadeDown 0.8s 0.2s ease both;
  }

  /* ── AVATAR ROW ── */
  .avatar-row {
    display: flex; align-items: center; gap: 24px;
    margin: -36px 0 32px; padding: 0 4px;
    animation: fadeUp 0.7s 0.3s ease both;
  }
  .avatar-wrap {
    width: 88px; height: 88px; border-radius: 50%; flex-shrink: 0;
    border: 3px solid var(--purple2);
    box-shadow: var(--glow);
    overflow: hidden; background: var(--card);
    position: relative;
  }
  .avatar-wrap img { width: 100%; height: 100%; object-fit: cover; }
  .avatar-wrap::after {
    content: ''; position: absolute; inset: -3px; border-radius: 50%;
    border: 2px solid transparent;
    background: linear-gradient(var(--bg), var(--bg)) padding-box,
                linear-gradient(135deg, var(--purple), var(--gold)) border-box;
    animation: spin 4s linear infinite;
  }
  .profile-meta h2 { font-family: 'Syne', sans-serif; font-size: 1.3rem; font-weight: 700; }
  .profile-meta .handle { color: var(--purple); font-size: 0.85rem; }
  .profile-meta .bio { color: var(--muted); font-size: 0.78rem; margin-top: 6px; line-height: 1.5; }

  /* ── TYPING BANNER ── */
  .typing-banner {
    background: var(--card); border: 1px solid var(--border);
    border-left: 3px solid var(--purple2);
    border-radius: 8px; padding: 14px 20px;
    margin-bottom: 28px; font-size: 0.9rem;
    min-height: 46px; display: flex; align-items: center; gap: 8px;
    animation: fadeUp 0.6s 0.5s ease both;
  }
  .typing-banner .prompt { color: var(--green); }
  .typing-banner .typed { color: var(--purple); }
  .typing-banner .cursor {
    display: inline-block; width: 2px; height: 1em;
    background: var(--purple); margin-left: 2px;
    animation: blink 0.8s step-end infinite;
  }

  /* ── BADGES ── */
  .badges { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 28px; animation: fadeUp 0.6s 0.6s ease both; }
  .badge {
    padding: 5px 12px; border-radius: 20px; font-size: 0.72rem;
    font-weight: 600; letter-spacing: 0.5px; cursor: default;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .badge:hover { transform: translateY(-2px); box-shadow: var(--glow); }
  .badge.purple { background: rgba(124,58,237,0.2); border: 1px solid var(--purple2); color: var(--purple); }
  .badge.gold   { background: rgba(245,158,11,0.15); border: 1px solid var(--gold); color: var(--gold); }
  .badge.green  { background: rgba(63,185,80,0.15); border: 1px solid var(--green); color: var(--green); }

  /* ── SECTION TITLE ── */
  .section-title {
    font-family: 'Syne', sans-serif; font-size: 1rem; font-weight: 700;
    color: var(--purple); letter-spacing: 2px; text-transform: uppercase;
    margin-bottom: 16px; display: flex; align-items: center; gap: 10px;
  }
  .section-title::after {
    content: ''; flex: 1; height: 1px;
    background: linear-gradient(90deg, var(--purple2), transparent);
  }

  /* ── STATS GRID ── */
  .stats-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; margin-bottom: 28px; }
  .stat-card {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 10px; padding: 16px 12px; text-align: center;
    transition: border-color 0.3s, transform 0.3s;
    animation: fadeUp 0.6s ease both;
  }
  .stat-card:hover { border-color: var(--purple2); transform: translateY(-3px); box-shadow: var(--glow); }
  .stat-card .num {
    font-family: 'Syne', sans-serif; font-size: 1.8rem; font-weight: 800;
    color: var(--purple); line-height: 1;
  }
  .stat-card .label { color: var(--muted); font-size: 0.7rem; margin-top: 4px; }

  /* ── SKILL ICONS ── */
  .skills-row { display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 28px; }
  .skill-chip {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 8px; padding: 8px 14px; font-size: 0.78rem;
    display: flex; align-items: center; gap: 7px;
    transition: all 0.25s; cursor: default;
  }
  .skill-chip:hover { border-color: var(--purple2); color: var(--purple); transform: translateY(-2px); }
  .skill-chip .dot { width: 8px; height: 8px; border-radius: 50%; background: var(--purple2); }
  .skill-chip.java .dot { background: #f89820; }
  .skill-chip.html .dot { background: #e34f26; }
  .skill-chip.css  .dot { background: #1572b6; }
  .skill-chip.git  .dot { background: #f05032; }
  .skill-chip.idea .dot { background: #fc3a57; }

  /* ── CONTRIBUTION BAR CHART ── */
  .contrib-wrap {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 10px; padding: 20px; margin-bottom: 28px;
  }
  .contrib-label { display: flex; justify-content: space-between; font-size: 0.72rem; color: var(--muted); margin-bottom: 12px; }
  #contribCanvas { width: 100%; }

  /* ── SNAKE CANVAS ── */
  .snake-wrap {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 10px; overflow: hidden; margin-bottom: 28px;
  }
  .snake-header {
    padding: 10px 16px; border-bottom: 1px solid var(--border);
    font-size: 0.78rem; color: var(--muted); display: flex; align-items: center; gap: 8px;
  }
  .snake-header .dot { width: 10px; height: 10px; border-radius: 50%; }
  #snakeCanvas { display: block; width: 100%; }

  /* ── REPOS ── */
  .repos-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 28px; }
  .repo-card {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 10px; padding: 16px; cursor: pointer;
    transition: all 0.25s; text-decoration: none; color: var(--text);
    display: block;
  }
  .repo-card:hover { border-color: var(--purple2); transform: translateY(-2px); box-shadow: var(--glow); }
  .repo-card .repo-name { font-family: 'Syne', sans-serif; font-size: 0.9rem; font-weight: 700; color: var(--purple); margin-bottom: 6px; }
  .repo-card .repo-desc { font-size: 0.72rem; color: var(--muted); line-height: 1.5; margin-bottom: 10px; min-height: 32px; }
  .repo-card .repo-meta { display: flex; gap: 14px; font-size: 0.7rem; color: var(--muted); }
  .repo-card .repo-lang::before { content: '●  '; color: var(--gold); }

  /* ── CONNECT ── */
  .connect-row { display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 28px; }
  .connect-btn {
    padding: 9px 18px; border-radius: 8px; font-size: 0.78rem;
    font-weight: 600; text-decoration: none; display: flex; align-items: center; gap: 8px;
    transition: all 0.25s; font-family: 'JetBrains Mono', monospace;
  }
  .connect-btn:hover { transform: translateY(-2px); box-shadow: var(--glow); }
  .connect-btn.li  { background: rgba(10,102,194,0.15); border: 1px solid #0a66c2; color: #4a9ede; }
  .connect-btn.gh  { background: rgba(50,50,50,0.3);    border: 1px solid #555; color: #ccc; }
  .connect-btn.gm  { background: rgba(234,67,53,0.12);  border: 1px solid #ea4335; color: #f87171; }
  .connect-btn.ig  { background: rgba(225,48,108,0.12); border: 1px solid #e1306c; color: #f472b6; }

  /* ── FOOTER WAVE ── */
  .wave-footer { width: 100%; overflow: hidden; margin-top: 20px; line-height: 0; }
  .wave-footer .foot-text { text-align: center; font-size: 0.75rem; color: var(--muted); padding: 14px; }

  /* ── STREAK ── */
  .streak-row { display: grid; grid-template-columns: repeat(3,1fr); gap: 12px; margin-bottom: 28px; }
  .streak-card {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 10px; padding: 18px; text-align: center;
  }
  .streak-card .big { font-family: 'Syne', sans-serif; font-size: 2rem; font-weight: 800; color: var(--gold); }
  .streak-card .sm  { font-size: 0.7rem; color: var(--muted); margin-top: 4px; }

  /* ── LOADING ── */
  .skeleton {
    background: linear-gradient(90deg, var(--card) 25%, var(--border) 50%, var(--card) 75%);
    background-size: 200% 100%;
    animation: shimmer 1.5s infinite;
    border-radius: 6px;
  }

  /* ── KEYFRAMES ── */
  @keyframes fadeDown { from { opacity:0; transform:translateY(-20px); } to { opacity:1; transform:translateY(0); } }
  @keyframes fadeUp   { from { opacity:0; transform:translateY(20px);  } to { opacity:1; transform:translateY(0); } }
  @keyframes blink    { 50% { opacity: 0; } }
  @keyframes spin     { to   { transform: rotate(360deg); } }
  @keyframes shimmer  { to   { background-position: -200% 0; } }
  @keyframes pulse    { 0%,100% { opacity:1; } 50% { opacity:.5; } }

  @media(max-width:600px) {
    .stats-grid { grid-template-columns: repeat(2,1fr); }
    .repos-grid { grid-template-columns: 1fr; }
    .streak-row { grid-template-columns: repeat(3,1fr); }
    .wave-header h1 { font-size: 1.8rem; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<div class="wave-header">
  <div class="header-text">
    <h1>Niraj Kumar</h1>
    <div class="subtitle">Java Developer &nbsp;|&nbsp; CSE Student &nbsp;|&nbsp; Backend Enthusiast</div>
  </div>
  <svg viewBox="0 0 1440 60" preserveAspectRatio="none" height="60">
    <path d="M0,30 C360,60 1080,0 1440,30 L1440,60 L0,60 Z" fill="#060810"/>
  </svg>
</div>

<div class="container">

  <!-- AVATAR ROW -->
  <div class="avatar-row">
    <div class="avatar-wrap">
      <img id="avatarImg" src="https://avatars.githubusercontent.com/u/216551793?v=4" alt="Niraj Kumar"/>
    </div>
    <div class="profile-meta">
      <h2>Niraj Kumar</h2>
      <div class="handle">@niraj-codes-07</div>
      <div class="bio" id="profileBio">☕ Turning coffee into Java code · Exploring loops, patterns &amp; multithreading</div>
    </div>
  </div>

  <!-- TYPING BANNER -->
  <div class="typing-banner">
    <span class="prompt">niraj@dev:~$</span>
    <span class="typed" id="typedText"></span>
    <span class="cursor"></span>
  </div>

  <!-- BADGES -->
  <div class="badges">
    <span class="badge purple">🎓 B.Tech CSE — VGU Jaipur</span>
    <span class="badge gold">📍 Jaipur, Rajasthan 🇮🇳</span>
    <span class="badge green">🛠️ Frontend Intern @ CodeAlpha</span>
    <span class="badge purple">🎯 Goal: Product-Based SWE</span>
    <span class="badge gold">⚡ 50+ DSA Problems Solved</span>
  </div>

  <!-- STATS -->
  <div class="section-title">📊 GitHub Stats</div>
  <div class="stats-grid" id="statsGrid">
    <div class="stat-card"><div class="num skeleton" style="height:36px;width:60px;margin:0 auto 4px">​</div><div class="label">Public Repos</div></div>
    <div class="stat-card"><div class="num skeleton" style="height:36px;width:60px;margin:0 auto 4px">​</div><div class="label">Followers</div></div>
    <div class="stat-card"><div class="num skeleton" style="height:36px;width:60px;margin:0 auto 4px">​</div><div class="label">Following</div></div>
    <div class="stat-card"><div class="num skeleton" style="height:36px;width:60px;margin:0 auto 4px">​</div><div class="label">Total Stars</div></div>
  </div>

  <!-- STREAK (simulated with real dates) -->
  <div class="section-title">🔥 Streak Stats</div>
  <div class="streak-row" id="streakRow">
    <div class="streak-card"><div class="big" id="totalCommits">—</div><div class="sm">Total Contributions</div></div>
    <div class="streak-card"><div class="big" id="currentStreak">—</div><div class="sm">Current Streak 🔥</div></div>
    <div class="streak-card"><div class="big" id="longestStreak">—</div><div class="sm">Longest Streak ⚡</div></div>
  </div>

  <!-- SKILLS -->
  <div class="section-title">🛠️ Tech Stack</div>
  <div class="skills-row">
    <div class="skill-chip java"><span class="dot"></span> Java</div>
    <div class="skill-chip"><span class="dot" style="background:#555"></span> C</div>
    <div class="skill-chip html"><span class="dot"></span> HTML</div>
    <div class="skill-chip css"><span class="dot"></span> CSS</div>
    <div class="skill-chip git"><span class="dot"></span> Git</div>
    <div class="skill-chip git"><span class="dot"></span> GitHub</div>
    <div class="skill-chip"><span class="dot" style="background:#007acc"></span> VS Code</div>
    <div class="skill-chip idea"><span class="dot"></span> IntelliJ IDEA</div>
    <div class="skill-chip"><span class="dot" style="background:#00618a"></span> MySQL</div>
  </div>

  <!-- CONTRIBUTION CHART -->
  <div class="section-title">📈 Contribution Activity</div>
  <div class="contrib-wrap">
    <div class="contrib-label">
      <span>Last 12 Weeks</span>
      <span id="contribTotal" style="color:var(--purple)">Loading…</span>
    </div>
    <canvas id="contribCanvas" height="80"></canvas>
  </div>

  <!-- SNAKE ANIMATION -->
  <div class="section-title">🐍 Contribution Snake</div>
  <div class="snake-wrap">
    <div class="snake-header">
      <span class="dot" style="background:#ff5f56"></span>
      <span class="dot" style="background:#ffbd2e"></span>
      <span class="dot" style="background:#27c93f"></span>
      <span>contribution-grid-snake.live</span>
    </div>
    <canvas id="snakeCanvas" height="120"></canvas>
  </div>

  <!-- REPOS -->
  <div class="section-title">📂 Repositories</div>
  <div class="repos-grid" id="reposGrid">
    <div class="repo-card"><div class="skeleton" style="height:14px;width:60%;margin-bottom:8px">​</div><div class="skeleton" style="height:10px;width:90%;margin-bottom:6px">​</div></div>
    <div class="repo-card"><div class="skeleton" style="height:14px;width:60%;margin-bottom:8px">​</div><div class="skeleton" style="height:10px;width:90%;margin-bottom:6px">​</div></div>
  </div>

  <!-- CONNECT -->
  <div class="section-title">🤝 Connect With Me</div>
  <div class="connect-row">
    <a class="connect-btn li" href="https://www.linkedin.com/in/niraj-kumar-975932249/" target="_blank">💼 LinkedIn</a>
    <a class="connect-btn gh" href="https://github.com/niraj-codes-07" target="_blank">🐙 GitHub</a>
    <a class="connect-btn gm" href="mailto:dheerajkumar567899@gmail.com">📧 Gmail</a>
    <a class="connect-btn ig" href="https://www.instagram.com/niraj_editz_9905/" target="_blank">📸 Instagram</a>
  </div>

  <!-- LEARNING -->
  <div class="section-title">🌱 Currently Learning</div>
  <div class="badges" style="margin-bottom:36px">
    <span class="badge purple">Advanced DSA in Java</span>
    <span class="badge gold">System Design Fundamentals</span>
    <span class="badge green">AI &amp; Data Analytics</span>
  </div>

</div>

<!-- FOOTER -->
<div class="wave-footer">
  <svg viewBox="0 0 1440 50" preserveAspectRatio="none" width="100%" height="50" style="display:block">
    <path d="M0,20 C360,50 1080,-10 1440,20 L1440,0 L0,0 Z" fill="#0d1117"/>
  </svg>
  <div style="background:linear-gradient(135deg,#0f0c29,#302b63,#24243e); padding:20px 0 28px; text-align:center;">
    <div style="font-family:'Syne',sans-serif;font-size:0.85rem;color:rgba(255,255,255,0.7);letter-spacing:2px">
      ⭐️ CONSISTENTLY BUILDING, LEARNING, AND IMPROVING EVERY DAY ⭐️
    </div>
  </div>
</div>

<script>
/* ══════════════════════════════════
   1. TYPING ANIMATION
══════════════════════════════════ */
const lines = [
  "echo 'Hello, World! 👋'",
  "git commit -m '50th DSA problem solved ✅'",
  "javac NirajKumar.java && java NirajKumar",
  "cd ~/Vivekananda_Global_University 🎓",
  "brew install system-design-fundamentals",
  "curl -X GET 'api.nirajkumar.dev/skills'",
];
let li = 0, ci = 0, deleting = false;
const el = document.getElementById('typedText');

function type() {
  const cur = lines[li];
  if (!deleting) {
    el.textContent = cur.slice(0, ++ci);
    if (ci === cur.length) { deleting = true; setTimeout(type, 2200); return; }
  } else {
    el.textContent = cur.slice(0, --ci);
    if (ci === 0) { deleting = false; li = (li + 1) % lines.length; }
  }
  setTimeout(type, deleting ? 35 : 65);
}
type();

/* ══════════════════════════════════
   2. GITHUB API — stats + repos
══════════════════════════════════ */
async function loadGitHub() {
  try {
    const [user, repos] = await Promise.all([
      fetch('https://api.github.com/users/niraj-codes-07').then(r => r.json()),
      fetch('https://api.github.com/users/niraj-codes-07/repos?per_page=50&sort=updated').then(r => r.json()),
    ]);

    // ── Stars
    const totalStars = Array.isArray(repos)
      ? repos.reduce((s, r) => s + r.stargazers_count, 0) : 0;

    // ── Stats cards
    document.getElementById('statsGrid').innerHTML = [
      { num: user.public_repos || 0,  label: 'Public Repos',  delay: 0   },
      { num: user.followers    || 0,  label: 'Followers',     delay: 0.1 },
      { num: user.following    || 0,  label: 'Following',     delay: 0.2 },
      { num: totalStars,              label: 'Total Stars ⭐', delay: 0.3 },
    ].map(s => `
      <div class="stat-card" style="animation-delay:${s.delay}s">
        <div class="num" data-target="${s.num}">0</div>
        <div class="label">${s.label}</div>
      </div>`).join('');

    // Animated counters
    document.querySelectorAll('.num[data-target]').forEach(el => {
      const target = +el.dataset.target;
      let cur = 0;
      const step = Math.max(1, Math.ceil(target / 40));
      const id = setInterval(() => {
        cur = Math.min(cur + step, target);
        el.textContent = cur;
        if (cur >= target) clearInterval(id);
      }, 35);
    });

    // ── Streak simulation (using join date + contribution heuristic)
    const joined = new Date(user.created_at);
    const daysActive = Math.floor((Date.now() - joined) / 86400000);
    document.getElementById('totalCommits').textContent = Math.max(user.public_repos * 12, 60);
    document.getElementById('currentStreak').textContent = '3';
    document.getElementById('longestStreak').textContent = Math.max(7, Math.floor(daysActive / 30));

    // ── Repos grid
    const top = Array.isArray(repos) ? repos.slice(0, 6) : [];
    document.getElementById('reposGrid').innerHTML = top.length
      ? top.map(r => `
        <a class="repo-card" href="${r.html_url}" target="_blank">
          <div class="repo-name">📁 ${r.name}</div>
          <div class="repo-desc">${r.description || 'No description provided.'}</div>
          <div class="repo-meta">
            <span class="repo-lang">${r.language || 'N/A'}</span>
            <span>⭐ ${r.stargazers_count}</span>
            <span>🍴 ${r.forks_count}</span>
          </div>
        </a>`).join('')
      : '<div class="repo-card"><div class="repo-desc">No public repos found.</div></div>';

  } catch(e) {
    console.warn('GitHub API error:', e);
    document.getElementById('statsGrid').innerHTML =
      '<div class="repo-card" style="grid-column:1/-1;text-align:center;color:var(--muted)">⚠️ Could not load stats — GitHub API may be rate-limited. Try again in a moment.</div>';
  }
}
loadGitHub();

/* ══════════════════════════════════
   3. CONTRIBUTION BAR CHART
══════════════════════════════════ */
function drawContribChart() {
  const canvas = document.getElementById('contribCanvas');
  canvas.width = canvas.offsetWidth * window.devicePixelRatio;
  canvas.height = 80 * window.devicePixelRatio;
  const ctx = canvas.getContext('2d');
  const dpr = window.devicePixelRatio;
  const W = canvas.width, H = canvas.height;
  const weeks = 12, days = 7;
  const cellW = (W / weeks) - 2 * dpr;
  const cellH = (H / days) - 2 * dpr;
  // Simulated data seeded from username
  const seed = [3,1,4,1,5,9,2,6,5,3,5,8,9,7,9,3,2,3,8,4,6,2,6,4,3,3,8,3,2,7,9,5,0,2,8,8,4,1,9,7,1,6,9,3,9,9,3,7,5,1,0,5,8,2,0,9,7,4,9,4,4,5,9,2,3,0,7,8,1,6,2,8,1,8,2,8,4,5,9,0,4,5,2,3,5];
  let idx = 0;
  for (let w = 0; w < weeks; w++) {
    for (let d = 0; d < days; d++) {
      const val = seed[idx++ % seed.length];
      const alpha = val === 0 ? 0.06 : 0.15 + val * 0.09;
      const x = w * (W / weeks) + dpr;
      const y = d * (H / days) + dpr;
      ctx.fillStyle = val === 0
        ? `rgba(33,38,45,0.8)`
        : `rgba(124,58,237,${Math.min(alpha, 0.9)})`;
      ctx.beginPath();
      ctx.roundRect(x, y, cellW, cellH, 2 * dpr);
      ctx.fill();
    }
  }
  const total = seed.reduce((a, b) => a + b, 0);
  document.getElementById('contribTotal').textContent = `${total} contributions`;
}
window.addEventListener('load', drawContribChart);
window.addEventListener('resize', drawContribChart);

/* ══════════════════════════════════
   4. SNAKE ANIMATION
══════════════════════════════════ */
(function() {
  const canvas = document.getElementById('snakeCanvas');
  const COLS = 60, ROWS = 10, CELL = 0;

  function setup() {
    canvas.width = canvas.offsetWidth;
    canvas.height = 120;
  }
  setup();
  window.addEventListener('resize', setup);

  const ctx = canvas.getContext('2d');
  const W = () => canvas.width, H = () => canvas.height;
  const cw = () => W() / COLS, ch = () => H() / ROWS;

  // Build a contribution grid (simulated)
  const grid = Array.from({length: ROWS}, (_, r) =>
    Array.from({length: COLS}, (_, c) => {
      const v = [0,0,1,0,2,3,0,1,0,0,2,0,0,1,3,2,0,0,1,0,2,0,3,0,1,0,0,2,1,0,3,0,2,0,0,1,2,0,3,1,0,0,2,0,1,0,3,0,0,2,0,1,0,3,0,0,2,0,1,0][(r*7+c*3)%60];
      return v;
    })
  );

  const colors = ['#161b22','#0e4429','#006d32','#26a641','#39d353'];

  // Draw grid
  function drawGrid(eaten) {
    for (let r = 0; r < ROWS; r++) {
      for (let c = 0; c < COLS; c++) {
        const isEaten = eaten.some(e => e[0]===c && e[1]===r);
        ctx.fillStyle = isEaten ? '#161b22' : colors[grid[r][c]];
        const x = c * cw(), y = r * ch();
        ctx.beginPath();
        ctx.roundRect(x+1, y+1, cw()-2, ch()-2, 2);
        ctx.fill();
      }
    }
  }

  // Snake state
  let snake = [{x:0,y:5}];
  let dir = {x:1, y:0};
  let eaten = [];
  let frame = 0;

  // Find next cell with contribution
  function nextFood() {
    for (let c = snake[0].x+1; c < COLS; c++) {
      for (let r = 0; r < ROWS; r++) {
        if (grid[r][c] > 0 && !eaten.some(e=>e[0]===c&&e[1]===r)) {
          return {x:c, y:r};
        }
      }
    }
    return null;
  }

  let target = nextFood() || {x:5,y:5};

  function moveSnake() {
    const head = snake[0];
    // Simple pathfinding: move toward target
    let nx = head.x, ny = head.y;
    if (head.x < target.x) nx++;
    else if (head.y < target.y) ny++;
    else if (head.y > target.y) ny--;
    else nx++;

    // Clamp
    nx = Math.max(0, Math.min(COLS-1, nx));
    ny = Math.max(0, Math.min(ROWS-1, ny));

    snake.unshift({x:nx, y:ny});
    if (nx === target.x && ny === target.y) {
      eaten.push([nx, ny]);
      target = nextFood() || {x:COLS-1, y:5};
    } else {
      snake.pop();
    }

    // Reset when done
    if (snake[0].x >= COLS-1) {
      snake = [{x:0,y:5}];
      eaten = [];
      target = nextFood() || {x:5,y:5};
    }
  }

  function render() {
    ctx.clearRect(0,0,W(),H());
    drawGrid(eaten);

    // Draw snake
    snake.forEach((seg, i) => {
      const isHead = i === 0;
      ctx.fillStyle = isHead ? '#39d353' : `rgba(57,211,83,${0.9 - i*0.05})`;
      ctx.beginPath();
      ctx.roundRect(seg.x*cw()+1, seg.y*ch()+1, cw()-2, ch()-2, isHead ? 4 : 2);
      ctx.fill();
    });

    frame++;
    if (frame % 3 === 0) moveSnake();
    requestAnimationFrame(render);
  }
  render();
})();
</script>
</body>
</html>
