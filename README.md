 <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Om Rawat – Animated Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600&display=swap" rel="stylesheet"/>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    background: #090e17;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    padding: 32px 16px;
  }

  .terminal {
    background: #0d1117;
    border-radius: 12px;
    border: 1px solid #30363d;
    overflow: hidden;
    font-family: 'Fira Code', monospace;
    width: 100%;
    max-width: 680px;
    box-shadow: 0 0 40px rgba(0, 180, 216, 0.08);
  }

  /* ── title bar ── */
  .titlebar {
    background: #161b22;
    border-bottom: 1px solid #30363d;
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot.r { background: #ff5f56; }
  .dot.y { background: #ffbd2e; }
  .dot.g { background: #27c93f; }
  .tab-label { color: #8b949e; font-size: 13px; margin-left: 8px; }

  /* ── body ── */
  .body {
    padding: 24px 28px 32px;
    min-height: 460px;
    position: relative;
    overflow: hidden;
  }

  /* subtle grid bg */
  .grid-bg {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,180,216,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,180,216,0.04) 1px, transparent 1px);
    background-size: 32px 32px;
    pointer-events: none;
  }

  /* ── code lines ── */
  .code-line {
    font-size: 14px;
    line-height: 1.8;
    white-space: pre;
    position: relative;
    z-index: 2;
    opacity: 0;
    transform: translateX(-8px);
    transition: opacity 0.32s ease, transform 0.32s ease;
    min-height: 25px;
  }
  .code-line.visible { opacity: 1; transform: translateX(0); }

  /* syntax colours */
  .kw   { color: #ff7b72; }
  .fn   { color: #d2a8ff; }
  .str  { color: #a5d6ff; }
  .self { color: #ffa657; }
  .punc { color: #c9d1d9; }
  .var  { color: #e3b341; }
  .cmt  { color: #8b949e; font-style: italic; }

  /* blinking cursor */
  .cursor {
    display: inline-block;
    width: 9px; height: 15px;
    background: #00b4d8;
    vertical-align: middle;
    margin-left: 2px;
    border-radius: 1px;
    animation: blink 1s step-end infinite;
  }
  @keyframes blink { 50% { opacity: 0; } }

  /* ── output box ── */
  .output-box {
    margin-top: 20px;
    padding: 14px 18px;
    border-radius: 8px;
    border: 1px solid rgba(0,180,216,0.35);
    background: rgba(0,180,216,0.06);
    display: none;
    position: relative;
    z-index: 2;
    animation: fadeSlide 0.45s ease forwards;
  }
  .output-box.show { display: block; }
  @keyframes fadeSlide {
    from { opacity: 0; transform: translateY(8px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  .output-line {
    font-size: 14px;
    line-height: 1.7;
    color: #7ee787;
    min-height: 25px;
  }

  /* ── badges ── */
  .badge-row { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 12px; }
  .badge {
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 20px;
    font-family: 'Fira Code', monospace;
    font-weight: 500;
    border: 1px solid;
    opacity: 0;
    transform: scale(0.75);
    transition: opacity 0.25s ease, transform 0.25s ease;
  }
  .badge.pop { opacity: 1; transform: scale(1); }
  .b-orange { color: #ffa657; border-color: rgba(255,166,87,.4);  background: rgba(255,166,87,.08); }
  .b-blue   { color: #79c0ff; border-color: rgba(121,192,255,.4); background: rgba(121,192,255,.08); }
  .b-green  { color: #7ee787; border-color: rgba(126,231,135,.4); background: rgba(126,231,135,.08); }
  .b-cyan   { color: #00b4d8; border-color: rgba(0,180,216,.4);   background: rgba(0,180,216,.08); }
  .b-pink   { color: #f778ba; border-color: rgba(247,120,186,.4); background: rgba(247,120,186,.08); }

  /* ── restart button ── */
  .restart-btn {
    position: absolute;
    top: 12px; right: 16px;
    background: transparent;
    border: 1px solid #30363d;
    color: #8b949e;
    font-size: 11px;
    font-family: 'Fira Code', monospace;
    padding: 4px 10px;
    border-radius: 6px;
    cursor: pointer;
    z-index: 10;
    transition: border-color .2s, color .2s;
  }
  .restart-btn:hover { border-color: #00b4d8; color: #00b4d8; }

  /* corner glow accents */
  .glow-tl, .glow-br {
    position: absolute;
    width: 160px; height: 160px;
    border-radius: 50%;
    pointer-events: none;
    z-index: 1;
    opacity: 0.07;
  }
  .glow-tl { top: -60px; left: -60px; background: #00b4d8; }
  .glow-br { bottom: -60px; right: -60px; background: #d2a8ff; }
</style>
</head>
<body>

<div class="terminal">
  <div class="titlebar">
    <span class="dot r"></span>
    <span class="dot y"></span>
    <span class="dot g"></span>
    <span class="tab-label">om_rawat.py — Python 3.11</span>
  </div>

  <div class="body" id="body">
    <div class="glow-tl"></div>
    <div class="glow-br"></div>
    <div class="grid-bg"></div>
    <button class="restart-btn" onclick="restart()">↺ restart</button>

    <div id="code-container"></div>

    <div class="output-box" id="output">
      <div class="output-line" id="out-line"></div>
      <div class="badge-row" id="badge-row"></div>
    </div>
  </div>
</div>

<script>
const lines = [
  { html: '<span class="kw">class</span> <span class="fn">OmRawat</span><span class="punc">:</span>',                                           delay: 0 },
  { html: '    <span class="kw">def</span> <span class="fn">__init__</span><span class="punc">(</span><span class="self">self</span><span class="punc">):</span>', delay: 320 },
  { html: '        <span class="self">self</span><span class="punc">.</span><span class="var">name</span>       <span class="punc">=</span> <span class="str">"Om Rawat"</span>',                    delay: 640 },
  { html: '        <span class="self">self</span><span class="punc">.</span><span class="var">role</span>       <span class="punc">=</span> <span class="str">"ML Engineer &amp; AI Developer"</span>',    delay: 960 },
  { html: '        <span class="self">self</span><span class="punc">.</span><span class="var">location</span>   <span class="punc">=</span> <span class="str">"India 🇮🇳"</span>',                    delay: 1240 },
  { html: '        <span class="self">self</span><span class="punc">.</span><span class="var">languages</span>  <span class="punc">=</span> <span class="punc">[</span><span class="str">"Python"</span><span class="punc">,</span> <span class="str">"C"</span><span class="punc">,</span> <span class="str">"SQL"</span><span class="punc">]</span>',    delay: 1540 },
  { html: '        <span class="self">self</span><span class="punc">.</span><span class="var">frameworks</span> <span class="punc">=</span> <span class="punc">[</span><span class="str">"TensorFlow"</span><span class="punc">,</span> <span class="str">"PyTorch"</span><span class="punc">,</span> <span class="str">"FastAPI"</span><span class="punc">]</span>', delay: 1840 },
  { html: '        <span class="self">self</span><span class="punc">.</span><span class="var">databases</span>  <span class="punc">=</span> <span class="punc">[</span><span class="str">"MySQL"</span><span class="punc">]</span>',                         delay: 2140 },
  { html: '        <span class="self">self</span><span class="punc">.</span><span class="var">interests</span>  <span class="punc">=</span> <span class="punc">[</span>',                                   delay: 2420 },
  { html: '            <span class="str">"Deep Learning"</span><span class="punc">,</span>',                               delay: 2680 },
  { html: '            <span class="str">"Model Dev &amp; Deployment"</span><span class="punc">,</span>',                   delay: 2900 },
  { html: '            <span class="str">"MLOps"</span><span class="punc">,</span>',                                         delay: 3100 },
  { html: '            <span class="str">"Bridging Research &amp; Real-World AI"</span>',          delay: 3300 },
  { html: '        <span class="punc">]</span>',                                                          delay: 3500 },
  { html: '',                                                                          delay: 3640 },
  { html: '    <span class="kw">def</span> <span class="fn">say_hi</span><span class="punc">(</span><span class="self">self</span><span class="punc">):</span>',              delay: 3800 },
  { html: '        <span class="fn">print</span><span class="punc">(</span><span class="str">"Thanks for dropping by! Let\'s build something intelligent 🚀"</span><span class="punc">)</span>', delay: 4100 },
  { html: '',                                                                          delay: 4320 },
  { html: '<span class="var">me</span> <span class="punc">=</span> <span class="fn">OmRawat</span><span class="punc">()</span>',                                     delay: 4520 },
  { html: '<span class="var">me</span><span class="punc">.</span><span class="fn">say_hi</span><span class="punc">()</span>',                                      delay: 4820 },
];

const badges = [
  { label: 'TensorFlow',     cls: 'b-orange' },
  { label: 'PyTorch',        cls: 'b-orange' },
  { label: 'FastAPI',        cls: 'b-green'  },
  { label: 'Python',         cls: 'b-blue'   },
  { label: 'MLOps',          cls: 'b-cyan'   },
  { label: 'Deep Learning',  cls: 'b-pink'   },
  { label: 'Streamlit',      cls: 'b-blue'   },
  { label: 'Power BI',       cls: 'b-cyan'   },
];

let timers = [];

function restart() {
  timers.forEach(clearTimeout);
  timers = [];
  document.getElementById('code-container').innerHTML = '';
  const out = document.getElementById('output');
  out.classList.remove('show');
  document.getElementById('out-line').textContent = '';
  document.getElementById('badge-row').innerHTML = '';
  run();
}

function run() {
  const container = document.getElementById('code-container');

  lines.forEach((line, i) => {
    const t = setTimeout(() => {
      const div = document.createElement('div');
      div.className = 'code-line';
      div.innerHTML = line.html || '&nbsp;';
      container.appendChild(div);

      requestAnimationFrame(() =>
        requestAnimationFrame(() => div.classList.add('visible'))
      );

      if (i === lines.length - 1) {
        const cursor = document.createElement('span');
        cursor.className = 'cursor';
        div.appendChild(cursor);

        const t2 = setTimeout(() => {
          cursor.remove();
          showOutput();
        }, 600);
        timers.push(t2);
      }
    }, line.delay);
    timers.push(t);
  });
}

function showOutput() {
  const out = document.getElementById('output');
  out.classList.add('show');

  const outLine = document.getElementById('out-line');
  const msg = '> Thanks for dropping by! Let\'s build something intelligent 🚀';
  let idx = 0;
  const iv = setInterval(() => {
    outLine.textContent += msg[idx];
    idx++;
    if (idx >= msg.length) {
      clearInterval(iv);
      showBadges();
    }
  }, 26);
}

function showBadges() {
  const row = document.getElementById('badge-row');
  badges.forEach((b, i) => {
    const t = setTimeout(() => {
      const span = document.createElement('span');
      span.className = 'badge ' + b.cls;
      span.textContent = b.label;
      row.appendChild(span);
      requestAnimationFrame(() =>
        requestAnimationFrame(() => span.classList.add('pop'))
      );
    }, i * 130);
    timers.push(t);
  });
}

run();
</script>
</body>
</html>
