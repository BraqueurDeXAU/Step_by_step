<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Escalier d'objectifs</title>
<style>
  :root {
    --paper: #191919;
    --ink: #e9e9e7;
    --ink-soft: #9b9a97;
    --line: #3a3a3a;
    --step-done: #6b8f6a;
    --step-todo: #3f3f3f;
    --flag: #4a90d9;
    --person: #8a86c9;
    --card: #2c2c2c;
  }
  * { box-sizing: border-box; }
  html, body {
    margin: 0;
    padding: 0;
    background: var(--paper);
    color: var(--ink);
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
  }
  .wrap {
    max-width: 760px;
    margin: 0 auto;
    padding: 28px 20px 48px;
  }
  .goal-row {
    display: flex;
    align-items: baseline;
    gap: 10px;
    margin-bottom: 6px;
  }
  .goal-label {
    font-size: 12px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--ink-soft);
  }
  input[type="text"] {
    font-family: inherit;
    font-size: 15px;
    border: none;
    border-bottom: 1px solid var(--line);
    background: transparent;
    padding: 6px 2px;
    color: var(--ink);
    outline: none;
  }
  input[type="text"]:focus {
    border-bottom: 1px solid var(--ink);
  }
  #goalTitle {
    font-size: 22px;
    font-weight: 600;
    width: 100%;
    margin-bottom: 24px;
    border-bottom: 1px solid var(--line);
  }
  .board {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  .stair-col {
    width: 100%;
    max-width: 640px;
    margin: 0 auto;
  }
  .steps-col {
    width: 100%;
    min-width: 0;
  }
  .progress-head {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: 10px;
  }
  .progress-head span:first-child {
    font-size: 12px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--ink-soft);
  }
  .progress-head span:last-child {
    font-size: 15px;
    font-weight: 600;
  }
  .step-row {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 9px 10px;
    background: var(--card);
    border: 1px solid var(--line);
    border-radius: 8px;
    margin-bottom: 6px;
  }
  .step-row input[type="checkbox"] {
    width: 17px;
    height: 17px;
    accent-color: var(--step-done);
    flex: 0 0 auto;
  }
  .step-row .label {
    flex: 1;
    font-size: 14px;
  }
  .step-row.done .label {
    color: var(--ink-soft);
    text-decoration: line-through;
  }
  .step-row button {
    border: none;
    background: transparent;
    color: var(--ink-soft);
    cursor: pointer;
    font-size: 15px;
    padding: 2px 6px;
    line-height: 1;
  }
  .step-row button:hover { color: var(--flag); }
  .add-row {
    display: flex;
    gap: 8px;
    margin-top: 10px;
  }
  .add-row input {
    flex: 1;
    border: 1px solid var(--line);
    border-radius: 8px;
    padding: 8px 10px;
  }
  .add-row button {
    border: 1px solid var(--ink);
    background: var(--ink);
    color: var(--paper);
    border-radius: 8px;
    padding: 8px 14px;
    font-size: 14px;
    cursor: pointer;
    white-space: nowrap;
  }
  .add-row button:hover { opacity: 0.85; }
  svg text { font-family: inherit; }
  .hint {
    margin-top: 22px;
    font-size: 12px;
    color: var(--ink-soft);
  }
</style>
</head>
<body>
<div class="wrap">

  <div class="goal-row">
    <span class="goal-label">Objectif final</span>
  </div>
  <input id="goalTitle" type="text" value="Courir un marathon" />

  <div class="board">
    <div class="stair-col">
      <svg id="stairSvg" viewBox="0 0 600 380" style="width:100%; height:auto;" role="img" aria-label="Escalier de progression vers l'objectif"></svg>
    </div>
    <div class="steps-col">
      <div class="progress-head">
        <span>Étapes</span>
        <span id="progressLabel">0 %</span>
      </div>
      <div id="stepsList"></div>
      <div class="add-row">
        <input id="newStepInput" type="text" placeholder="Ajouter une étape" />
        <button id="addStepBtn">Ajouter</button>
      </div>
    </div>
  </div>

  <p class="hint">Tes données restent dans ce navigateur (sauvegarde locale). Si tu changes d'appareil, elles ne se retrouvent pas automatiquement.</p>
</div>

<script>
const STORAGE_KEY = 'escalier-objectifs-v1';

function loadState() {
  try {
    const raw = localStorage.getItem(STORAGE_KEY);
    if (raw) return JSON.parse(raw);
  } catch (e) {}
  return {
    goalTitle: "Courir un marathon",
    steps: [
      { id: 1, label: "S'inscrire à une course", done: false },
      { id: 2, label: "Courir 5 km sans s'arrêter", done: false },
      { id: 3, label: "Courir 10 km", done: false },
      { id: 4, label: "Courir un semi-marathon", done: false },
      { id: 5, label: "Suivre un plan d'entraînement complet", done: false }
    ]
  };
}

function saveState() {
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify({ goalTitle, steps }));
  } catch (e) {}
}

let state = loadState();
let goalTitle = state.goalTitle;
let steps = state.steps;
let nextId = steps.reduce((m, s) => Math.max(m, s.id), 0) + 1;

document.getElementById('goalTitle').value = goalTitle;
document.getElementById('goalTitle').addEventListener('input', (e) => {
  goalTitle = e.target.value;
  saveState();
});

function renderStepsList() {
  const list = document.getElementById('stepsList');
  list.innerHTML = '';
  steps.forEach((s, i) => {
    const row = document.createElement('div');
    row.className = 'step-row' + (s.done ? ' done' : '');

    const cb = document.createElement('input');
    cb.type = 'checkbox';
    cb.checked = s.done;
    cb.addEventListener('change', () => {
      s.done = cb.checked;
      saveState();
      renderAll();
    });

    const label = document.createElement('span');
    label.className = 'label';
    label.textContent = (i + 1) + '. ' + s.label;

    const del = document.createElement('button');
    del.textContent = '\u00D7';
    del.setAttribute('aria-label', "Supprimer l'étape");
    del.addEventListener('click', () => {
      steps = steps.filter(x => x.id !== s.id);
      saveState();
      renderAll();
    });

    row.appendChild(cb);
    row.appendChild(label);
    row.appendChild(del);
    list.appendChild(row);
  });
}

function renderStair() {
  const svg = document.getElementById('stairSvg');
  const n = Math.max(steps.length, 1);
  const doneCount = steps.filter(s => s.done).length;
  const W = 600, H = 380;
  const marginX = 40, marginBottom = 50, topY = 40;
  const usableW = W - marginX * 2;
  const usableH = H - topY - marginBottom;
  const stepW = usableW / n;
  const stepH = usableH / n;

  let content = '';

  for (let i = 0; i < n; i++) {
    const x = marginX + i * stepW;
    const stepTopY = (H - marginBottom) - (i + 1) * stepH;
    const isDone = i < doneCount;
    const fill = isDone ? 'var(--step-done)' : 'var(--step-todo)';
    content += '<rect x="' + x + '" y="' + stepTopY + '" width="' + stepW + '" height="' + ((H - marginBottom) - stepTopY) + '" fill="' + fill + '" rx="6"></rect>';
  }

  const flagIndex = n - 1;
  const flagX = marginX + flagIndex * stepW + stepW / 2;
  const flagY = (H - marginBottom) - (flagIndex + 1) * stepH - 26;
  content += '<circle cx="' + flagX + '" cy="' + flagY + '" r="24" fill="var(--flag)"></circle>';
  content += '<text x="' + flagX + '" y="' + (flagY + 7) + '" fill="white" text-anchor="middle" font-size="24" font-weight="600">7</text>';

  const personIndex = Math.min(doneCount, n - 1);
  const personX = marginX + personIndex * stepW + stepW / 2;
  const personTopY = (H - marginBottom) - (personIndex + 1) * stepH;
  const py = personTopY - 16;

  content += '<g stroke="var(--person)" stroke-width="7" stroke-linecap="round" fill="none">' +
    '<circle cx="' + personX + '" cy="' + (py - 26) + '" r="12" fill="var(--person)" stroke="none"></circle>' +
    '<line x1="' + personX + '" y1="' + (py - 13) + '" x2="' + personX + '" y2="' + (py + 20) + '"></line>' +
    '<line x1="' + personX + '" y1="' + (py + 20) + '" x2="' + (personX - 14) + '" y2="' + (py + 40) + '"></line>' +
    '<line x1="' + personX + '" y1="' + (py + 20) + '" x2="' + (personX + 14) + '" y2="' + (py + 40) + '"></line>' +
    '<line x1="' + personX + '" y1="' + (py - 2) + '" x2="' + (personX - 18) + '" y2="' + (py + 12) + '"></line>' +
    '<line x1="' + personX + '" y1="' + (py - 2) + '" x2="' + (personX + 18) + '" y2="' + (py + 12) + '"></line>' +
    '</g>';

  svg.innerHTML = content;
}

function renderAll() {
  renderStepsList();
  renderStair();
  const doneCount = steps.filter(s => s.done).length;
  const pct = steps.length ? Math.round((doneCount / steps.length) * 100) : 0;
  document.getElementById('progressLabel').textContent = pct + ' %';
}

document.getElementById('addStepBtn').addEventListener('click', () => {
  const input = document.getElementById('newStepInput');
  const val = input.value.trim();
  if (!val) return;
  steps.push({ id: nextId++, label: val, done: false });
  input.value = '';
  saveState();
  renderAll();
});

document.getElementById('newStepInput').addEventListener('keydown', (e) => {
  if (e.key === 'Enter') document.getElementById('addStepBtn').click();
});

renderAll();
</script>
</body>
</html>
