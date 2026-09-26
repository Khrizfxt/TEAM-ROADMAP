<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover" />
<title>Team Roadmap</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,600;14..32,700;14..32,800;14..32,900&display=swap" rel="stylesheet" />
<style>
  :root{
    --bg:#0f0a07; --panel:rgba(58,40,28,0.4); --panel-strong:rgba(58,40,28,0.7);
    --border:rgba(255,255,255,0.04); --gold:#f5c518; --gold-dim:#d4880f;
    --text:#f5e6c8; --text-dim:#d4b483; --text-faint:#a68b6a;
    --green:#4cdf8b; --box-shadow-gold:rgba(245,197,24,0.2);
    box-sizing:border-box;
  }
  *{margin:0;padding:0;box-sizing:border-box}
  html{scroll-padding-top:env(safe-area-inset-top,0px)}
  body{
    font-family:'Inter',sans-serif;background:var(--bg);color:var(--text);
    min-height:100%;display:flex;justify-content:center;padding:20px;
    padding-top:calc(20px + env(safe-area-inset-top,0px));
    padding-bottom:calc(20px + env(safe-area-inset-bottom,0px));
    overflow-x:hidden;
  }
  body::before{
    content:'';position:fixed;top:-50%;left:-50%;width:200%;height:200%;
    background:radial-gradient(circle at 30% 40%, rgba(245,197,24,0.15), transparent 60%),
      radial-gradient(circle at 70% 80%, rgba(212,136,15,0.1), transparent 50%);
    z-index:0;pointer-events:none;
  }
  .container{max-width:820px;width:100%;position:relative;z-index:1;padding:10px 0 40px}
  ::-webkit-scrollbar{width:6px}
  ::-webkit-scrollbar-track{background:#1a110b}
  ::-webkit-scrollbar-thumb{background:var(--gold);border-radius:10px}

  header{text-align:center;margin-bottom:30px}
  .logo-badge{
    width:90px;height:90px;border-radius:50%;margin:0 auto 16px;display:flex;
    align-items:center;justify-content:center;font-size:2.2rem;font-weight:900;color:var(--gold);
    background:rgba(245,197,24,0.08);border:3px solid rgba(255,215,0,0.5);
    box-shadow:0 0 50px var(--box-shadow-gold), 0 0 100px rgba(245,197,24,0.1);
  }
  .logo-text{font-size:2.6rem;font-weight:900;color:var(--gold);letter-spacing:-1px}
  .ticker{
    display:inline-block;background:rgba(245,197,24,0.1);color:var(--gold);padding:6px 22px;
    border-radius:999px;font-size:0.8rem;font-weight:700;border:1px solid rgba(245,197,24,0.2);
    margin-top:8px;letter-spacing:0.5px;text-transform:uppercase;
  }
  .tagline{font-size:1.1rem;color:var(--text-dim);margin-top:12px}

  .stats-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:14px;margin-bottom:45px}
  .stat-card{
    background:var(--panel);border:1px solid var(--border);border-radius:18px;padding:18px 12px;
    text-align:center;transition:0.3s ease;
  }
  .stat-card:hover{border-color:rgba(245,197,24,0.2);transform:translateY(-4px);background:var(--panel-strong)}
  .stat-number{font-size:1.8rem;font-weight:800;color:var(--gold);display:block;line-height:1.2}
  .stat-label{font-size:0.68rem;text-transform:uppercase;letter-spacing:0.8px;color:var(--text-faint);margin-top:6px;font-weight:600}

  section{margin-bottom:44px}
  h2{font-size:1.5rem;font-weight:800;margin-bottom:20px;color:var(--gold);display:flex;align-items:center;gap:14px;letter-spacing:-0.5px}
  h2::after{content:'';flex:1;height:2px;background:linear-gradient(90deg, rgba(245,197,24,0.3), transparent)}

  .roadmap-timeline{position:relative;padding-left:34px}
  .roadmap-timeline::before{
    content:'';position:absolute;left:8px;top:12px;bottom:12px;width:3px;
    background:linear-gradient(180deg, var(--gold), var(--gold-dim), rgba(245,197,24,0.1));border-radius:10px;
  }
  .phase{
    background:var(--panel);border:1px solid var(--border);border-radius:18px;padding:22px 26px;
    margin-bottom:18px;position:relative;transition:0.3s ease;
  }
  .phase:hover{border-color:rgba(245,197,24,0.3);background:var(--panel-strong)}
  .phase::before{
    content:'';position:absolute;left:-30px;top:28px;width:16px;height:16px;border-radius:50%;
    background:#2c1e14;border:3px solid var(--gold);
  }
  .phase.current::before{background:var(--gold);box-shadow:0 0 0 6px rgba(245,197,24,0.15)}
  .phase-header{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:8px;margin-bottom:6px}
  .phase-title{font-weight:700;font-size:1.1rem;color:var(--text)}
  .phase-status{font-size:0.63rem;font-weight:700;padding:4px 14px;border-radius:999px;text-transform:uppercase;letter-spacing:0.5px}
  .status-live{background:rgba(34,197,94,0.15);color:var(--green);border:1px solid rgba(34,197,94,0.2)}
  .status-progress{background:rgba(245,197,24,0.12);color:var(--gold);border:1px solid rgba(245,197,24,0.15)}
  .status-upcoming{background:rgba(255,255,255,0.03);color:#6a5a44;border:1px solid rgba(255,255,255,0.04)}
  .phase-desc{color:var(--text-dim);font-size:0.92rem;margin-top:4px}

  .checklist{list-style:none;margin-top:14px;display:flex;flex-direction:column;gap:8px}
  .checklist li{display:flex;align-items:center;gap:10px;font-size:0.9rem;color:var(--text);cursor:pointer}
  .checklist li .box{
    width:18px;height:18px;border-radius:6px;border:2px solid var(--gold);flex-shrink:0;
    display:flex;align-items:center;justify-content:center;font-size:0.75rem;color:var(--bg);
  }
  .checklist li.done .box{background:var(--gold)}
  .checklist li.done span.label{color:var(--text-faint);text-decoration:line-through}

  .note{
    background:var(--panel);border:1px solid var(--border);border-radius:18px;padding:22px 26px;
    text-align:center;color:var(--text-dim);font-size:1rem;
  }
  .note strong{color:var(--gold)}

  footer{
    text-align:center;margin-top:35px;color:#4a3a2a;font-size:0.85rem;
    border-top:1px solid rgba(255,255,255,0.03);padding-top:30px;
  }

  @media (max-width:640px){
    .logo-badge{width:76px;height:76px}
    .logo-text{font-size:2.1rem}
    .phase{padding:16px 18px}
    .roadmap-timeline{padding-left:22px}
    .phase::before{left:-18px;width:12px;height:12px;top:22px}
    h2{font-size:1.25rem}
    .stats-grid{grid-template-columns:1fr 1fr}
  }
  @media (max-width:400px){.stats-grid{grid-template-columns:1fr}}
</style>
</head>
<body>
<div class="container">

  <header>
    <div class="logo-badge">💡</div>
    <div class="logo-text">Team Roadmap</div>
    <div class="ticker">🛠️ Internal — 3 Founders</div>
    <p class="tagline">What we actually need to ship, in order.</p>
  </header>

  <div class="stats-grid">
    <div class="stat-card"><span class="stat-number" id="phasesDone">0/4</span><span class="stat-label">Phases Complete</span></div>
    <div class="stat-card"><span class="stat-number" id="tasksDone">0/0</span><span class="stat-label">Tasks Done</span></div>
    <div class="stat-card"><span class="stat-number">3</span><span class="stat-label">Team Size</span></div>
    <div class="stat-card"><span class="stat-number">🎯</span><span class="stat-label">Ship It</span></div>
  </div>

  <section>
    <h2>🗺️ Roadmap</h2>
    <div class="roadmap-timeline" id="timeline">

      <div class="phase current" data-phase="0">
        <div class="phase-header">
          <div class="phase-title">Phase 1 — Foundation</div>
          <div class="phase-status status-live">⏳ In Progress</div>
        </div>
        <p class="phase-desc">Lock the basics before anything else moves forward.</p>
        <ul class="checklist">
          <li data-id="p1-1"><span class="box"></span><span class="label">Agree on scope & what we're actually building</span></li>
          <li data-id="p1-2"><span class="box"></span><span class="label">Split roles & responsibilities across the 3 of us</span></li>
          <li data-id="p1-3"><span class="box"></span><span class="label">Set up shared tools (repo, docs, comms)</span></li>
          <li data-id="p1-4"><span class="box"></span><span class="label">Write down what "done" looks like for v1</span></li>
        </ul>
      </div>

      <div class="phase" data-phase="1">
        <div class="phase-header">
          <div class="phase-title">Phase 2 — Build</div>
          <div class="phase-status status-progress">🔮 Upcoming</div>
        </div>
        <p class="phase-desc">Get a working version into our own hands.</p>
        <ul class="checklist">
          <li data-id="p2-1"><span class="box"></span><span class="label">Core functionality built end-to-end</span></li>
          <li data-id="p2-2"><span class="box"></span><span class="label">Internal test with just the 3 of us</span></li>
          <li data-id="p2-3"><span class="box"></span><span class="label">Fix the obvious breakages</span></li>
          <li data-id="p2-4"><span class="box"></span><span class="label">Basic docs / instructions written</span></li>
        </ul>
      </div>

      <div class="phase" data-phase="2">
        <div class="phase-header">
          <div class="phase-title">Phase 3 — Launch</div>
          <div class="phase-status status-upcoming">🔮 Upcoming</div>
        </div>
        <p class="phase-desc">Put it in front of real people.</p>
        <ul class="checklist">
          <li data-id="p3-1"><span class="box"></span><span class="label">Small closed group of test users</span></li>
          <li data-id="p3-2"><span class="box"></span><span class="label">Collect & act on feedback</span></li>
          <li data-id="p3-3"><span class="box"></span><span class="label">Public launch announcement</span></li>
        </ul>
      </div>

      <div class="phase" data-phase="3">
        <div class="phase-header">
          <div class="phase-title">Phase 4 — Grow</div>
          <div class="phase-status status-upcoming">🔮 Upcoming</div>
        </div>
        <p class="phase-desc">Keep it alive and moving after launch.</p>
        <ul class="checklist">
          <li data-id="p4-1"><span class="box"></span><span class="label">Set a weekly check-in rhythm</span></li>
          <li data-id="p4-2"><span class="box"></span><span class="label">Track what's working / what isn't</span></li>
          <li data-id="p4-3"><span class="box"></span><span class="label">Decide on next big feature or pivot</span></li>
        </ul>
      </div>

    </div>
  </section>

  <div class="note">
    We're <strong>three friends</strong> building this together. No shortcuts on the plan — if it's not on this list, it's not the priority yet.
  </div>

  <footer>Team Roadmap • updated as we go</footer>
</div>

<script>
(function(){
  const STORAGE_KEY = 'team-roadmap-checklist';
  let state = {};
  try {
    state = JSON.parse(localStorage.getItem(STORAGE_KEY)) || {};
  } catch(e) { state = {}; }

  const items = document.querySelectorAll('.checklist li');
  const phases = document.querySelectorAll('.phase');

  function save(){
    try { localStorage.setItem(STORAGE_KEY, JSON.stringify(state)); } catch(e) {}
  }

  function updateStats(){
    let totalDone = 0, total = items.length;
    let phasesDone = 0;
    phases.forEach(phase => {
      const lis = phase.querySelectorAll('.checklist li');
      const done = Array.from(lis).every(li => state[li.dataset.id]);
      if (done) phasesDone++;
      const statusEl = phase.querySelector('.phase-status');
      if (done) {
        statusEl.textContent = '✅ Done';
        statusEl.className = 'phase-status status-live';
        phase.classList.remove('current');
      }
    });
    // mark the first not-fully-done phase as current
    let markedCurrent = false;
    phases.forEach(phase => {
      const lis = phase.querySelectorAll('.checklist li');
      const done = Array.from(lis).every(li => state[li.dataset.id]);
      if (!done && !markedCurrent) {
        phase.classList.add('current');
        const statusEl = phase.querySelector('.phase-status');
        if (statusEl.textContent !== '✅ Done') {
          statusEl.textContent = '⏳ In Progress';
          statusEl.className = 'phase-status status-live';
        }
        markedCurrent = true;
      } else if (!done) {
        phase.classList.remove('current');
      }
    });
    items.forEach(li => { if (state[li.dataset.id]) totalDone++; });
    document.getElementById('tasksDone').textContent = totalDone + '/' + total;
    document.getElementById('phasesDone').textContent = phasesDone + '/' + phases.length;
  }

  items.forEach(li => {
    const id = li.dataset.id;
    if (state[id]) li.classList.add('done');
    li.addEventListener('click', () => {
      state[id] = !state[id];
      li.classList.toggle('done', !!state[id]);
      save();
      updateStats();
    });
  });

  updateStats();
})();
</script>
</body>
</html>
# TEAM-ROADMAP