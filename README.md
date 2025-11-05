<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Happy Birthday Sidra!! 🎁</title>
<style>
  :root{
    --bg: #fff6ff;
    --accent: #ff4da6;
    --pink: #ff89b8;
    --gold: #ffd57f;
    --card: #ff6fa3;
  }
  html,body{height:100%;margin:0;font-family: "Segoe UI", Roboto, system-ui, -apple-system, "Helvetica Neue", Arial;}
  body{background: linear-gradient(180deg,#fff6ff 0%, #fff0fb 100%); display:flex; align-items:center; justify-content:center; padding:24px; color:#3b1130;}

  .stage{
    width: min(820px, 95%);
    text-align:center;
  }

  h1{
    margin: 6px 0 18px;
    font-size: clamp(18px, 3.2vw, 30px);
    color: var(--accent);
    letter-spacing: 0.6px;
  }

  /* Gift container */
  .gift-wrap{
    position: relative;
    width: 320px;
    height: 320px;
    margin: 0 auto 20px;
    perspective: 900px;
  }

  /* floating effect */
  .gift{
    position:absolute;
    inset: 0;
    margin:auto;
    width: 240px;
    height: 180px;
    transform-style: preserve-3d;
    animation: float 3.6s ease-in-out infinite;
  }
  @keyframes float{
    0%{ transform: translateY(-8px) rotateX(0.02turn); }
    50%{ transform: translateY(10px) rotateX(-0.01turn); }
    100%{ transform: translateY(-8px) rotateX(0.02turn); }
  }

  /* Box base */
  .box{
    position:absolute;
    left:0; right:0; top:40px;
    margin:auto;
    width: 240px;
    height: 140px;
    background: linear-gradient(180deg, var(--card) 0%, #ff3f7f 100%);
    border-radius: 10px;
    box-shadow: 0 18px 40px rgba(60,10,40,0.18), 0 6px 12px rgba(0,0,0,0.08);
    transform-origin: center center;
    z-index: 1;
    overflow: visible;
  }

  /* lid (separate piece that will animate up/rotate) */
  .lid{
    position:absolute;
    left:0; right:0; top:0;
    margin:auto;
    width: 260px;
    height: 60px;
    background: linear-gradient(180deg,#ff3f7f 0%, #ff1155 100%);
    border-radius: 12px;
    transform-origin: 50% 90%;
    box-shadow: 0 8px 18px rgba(0,0,0,0.12);
    z-index: 3;
    transition: transform 520ms cubic-bezier(.2,.9,.2,1), top 520ms cubic-bezier(.2,.9,.2,1);
  }

  /* ribbon vertical */
  .ribbon-v{
    position:absolute;
    left:50%; transform:translateX(-50%);
    top:40px;
    width: 24px;
    height: 140px;
    background: #fff6f8;
    border-radius: 6px;
    z-index:2;
  }

  .ribbon-h{
    position:absolute;
    left: 28px; right:28px;
    top:86px;
    height: 26px;
    background: #fff6f8;
    border-radius: 6px;
    z-index:2;
  }

  /* bow */
  .bow{
    position:absolute;
    left:50%;
    transform:translateX(-50%);
    top:6px;
    width: 120px;
    height: 52px;
    z-index:4;
    pointer-events:none;
  }
  .bow:before,.bow:after{
    content:"";
    position:absolute;
    width:46px;height:34px;border-radius:46px 6px 34px 6px;
    background:#fff6f8;
    top:8px;
    box-shadow: inset -6px -4px 12px rgba(0,0,0,0.04);
  }
  .bow:before{ left:6px; transform: rotate(-20deg); }
  .bow:after{ right:6px; transform: rotate(20deg); }

  /* floating gift top text */
  .top-text{
    margin-bottom:12px;
    font-weight:700;
    font-size:1.05rem;
    color: #61153a;
  }

  /* Open button */
  .open-btn{
    display:inline-block;
    margin-top: 8px;
    background: linear-gradient(180deg,#ff8fbf,#ff4d9a);
    border: none;
    color: white;
    font-weight:700;
    padding: 12px 22px;
    border-radius: 999px;
    box-shadow: 0 8px 20px rgba(255,77,154,0.25);
    cursor:pointer;
    font-size: 1rem;
    transition: transform 140ms ease, box-shadow 140ms;
  }
  .open-btn:active{ transform: translateY(2px) scale(.995); box-shadow: 0 6px 14px rgba(255,77,154,0.2); }

  /* After opening, add class .opened on .gift to lift lid via transform */
  .gift.opened .lid{
    transform: rotateX(-52deg) translateY(-26px) translateZ(26px);
    top:-36px;
  }
  .gift.opened .bow{ transform: translateX(-50%) translateY(-18px) rotate(-6deg); transition: transform 500ms; }
  .gift.opened .box{ transform: translateY(18px) scale(1.01); }

  /* message modal */
  .message-wrap{
    position: fixed;
    left:50%; top:50%;
    transform: translate(-50%,-48%) scale(.98);
    width: min(860px, 92%);
    max-width: 860px;
    background: linear-gradient(180deg,#fff1fb,#fff8ff);
    border-radius: 18px;
    padding: 28px;
    box-shadow: 0 30px 80px rgba(40,8,40,0.14);
    opacity: 0;
    pointer-events: none;
    transition: opacity 420ms ease, transform 420ms cubic-bezier(.2,.9,.2,1);
    z-index: 1200;
  }
  .message-wrap.visible{ opacity: 1; pointer-events:auto; transform: translate(-50%,-50%) scale(1); }

  .message-inner{ display:flex; gap:18px; align-items:flex-start; }
  .avatar{
    flex: 0 0 84px;
    height: 84px;
    border-radius: 18px;
    background: linear-gradient(135deg,#ffe1f0,#ffd0b6);
    display:grid; place-items:center;
    font-size:28px; box-shadow: 0 8px 30px rgba(200,80,140,0.14);
  }
  .message-box{ text-align:left; flex:1; }
  .message-title{ font-weight:800; color:#b2166f; margin-bottom:8px; }
  .message-text{
    white-space: pre-wrap;
    line-height:1.5;
    color:#6a2740;
    font-size:15px;
    min-height: 180px;
  }
  .close-row{ display:flex; justify-content:flex-end; margin-top:12px; gap:10px; }
  .small-btn{ padding:8px 12px; border-radius:10px; border:none; cursor:pointer; font-weight:700;}
  .btn-later{ background:transparent; color:#b2166f; }
  .btn-close{ background: linear-gradient(180deg,#ff7fbf,#ff4d9a); color:white; }

  /* confetti canvas overlays */
  #confetti-canvas{
    position: fixed; left:0; top:0; width:100%; height:100%; pointer-events:none; z-index:1300;
  }

  /* responsiveness */
  @media (max-width:520px){
    .gift-wrap{ width:240px; height:260px; }
    .gift{ width:200px; height:150px; }
    .box{ width:200px; height:120px; top:36px; }
    .lid{ width:220px; height:52px; }
  }
</style>
</head>
<body>
  <div class="stage" role="main" aria-labelledby="mainTitle">
    <h1 id="mainTitle">🎁 Happy Birthday Sidra!! 🎉</h1>

    <div class="gift-wrap" aria-hidden="false">
      <div class="gift" id="gift">
        <div class="lid" id="lid" aria-hidden="true"></div>
        <div class="bow" id="bow"></div>
        <div class="box" id="box"></div>
        <div class="ribbon-v" aria-hidden="true"></div>
        <div class="ribbon-h" aria-hidden="true"></div>
      </div>
    </div>

    <div class="top-text">Tap the gift to open — or press the button below ✨</div>
    <button class="open-btn" id="openBtn" aria-controls="message" aria-expanded="false">✨ Open Me ✨</button>
  </div>

  <!-- message modal -->
  <div class="message-wrap" id="message" role="dialog" aria-modal="true" aria-labelledby="msgTitle" aria-hidden="true">
    <div class="message-inner">
      <div class="avatar">💌</div>
      <div class="message-box">
        <div id="msgTitle" class="message-title">A little message for Sidra ✨</div>
        <div id="messageText" class="message-text" aria-live="polite"></div>
        <div class="close-row">
          <button class="small-btn btn-later" id="laterBtn">Save for later</button>
          <button class="small-btn btn-close" id="closeBtn">Yay! Thanks 🎉</button>
        </div>
      </div>
    </div>
  </div>

  <canvas id="confetti-canvas" aria-hidden="true"></canvas>

<script>
  (function(){
    const gift = document.getElementById('gift');
    const openBtn = document.getElementById('openBtn');
    const messageWrap = document.getElementById('message');
    const messageText = document.getElementById('messageText');
    const closeBtn = document.getElementById('closeBtn');
    const laterBtn = document.getElementById('laterBtn');
    const confettiCanvas = document.getElementById('confetti-canvas');

    const MESSAGE = [
`Heyyy, happy 20th birthday!! 🥳🎉🎉
I told you I'd be the first to wish you, and here I am keeping my promise 😋

I can't believe the year's almost over but I'm so glad I got to meet such a sweet, genuine, and amazing person like you before it ends.

I hope your day is filled with smiles, love, surprises, and everything that makes you happiest. 💐✨

You deserve the best — may this year bring you closer to your dreams and wrap your life with joy and laughter. 🎂💫`
    ].join('\n');

    // Clicking gift also opens
    gift.addEventListener('click', triggerOpen);
    openBtn.addEventListener('click', triggerOpen);
    closeBtn.addEventListener('click', closeMessage);
    laterBtn.addEventListener('click', closeMessage);

    let opened = false;

    function triggerOpen(){
      if(opened) return;
      opened = true;
      // visual open
      gift.classList.add('opened');
      openBtn.setAttribute('disabled','true');
      openBtn.setAttribute('aria-expanded','true');

      // after lid animation, show message
      setTimeout(()=> {
        showMessage();
      }, 520);
    }

    // Typing effect
    function typeMessage(text, el, speed=28, cb){
      el.textContent = '';
      let i = 0;
      const step = ()=> {
        // type a bunch at once for better pace (preserve newlines)
        const chunk = 1; // characters per tick
        i += chunk;
        el.textContent = text.slice(0, i);
        if(i < text.length){
          requestAnimationFrame(()=> setTimeout(step, speed));
        } else {
          if(cb) cb();
        }
      };
      step();
    }

    // Show the message modal
    function showMessage(){
      messageWrap.classList.add('visible');
      messageWrap.setAttribute('aria-hidden','false');
      // center focus
      closeBtn.focus();
      // animate typing then confetti
      typeMessage(MESSAGE, messageText, 22, startConfetti);
    }

    // Close message
    function closeMessage(){
      messageWrap.classList.remove('visible');
      messageWrap.setAttribute('aria-hidden','true');
      openBtn.removeAttribute('disabled');
      openBtn.setAttribute('aria-expanded','false');
      stopConfetti();
    }

    // ---------------- Confetti system (canvas) ----------------
    const ctx = confettiCanvas.getContext('2d');
    let W = confettiCanvas.width = innerWidth;
    let H = confettiCanvas.height = innerHeight;
    window.addEventListener('resize', ()=> { W = confettiCanvas.width = innerWidth; H = confettiCanvas.height = innerHeight; });

    const colors = ['#ff7fbf','#ffd47f','#cfa6ff','#80e6ff','#ff9aa2','#ffe07a'];
    let confettiPieces = [];
    let confettiRunning = false;
    let confettiTimer;

    function rand(min, max){ return Math.random()*(max-min)+min; }

    function spawnConfetti(count=60){
      confettiPieces = [];
      for(let i=0;i<count;i++){
        confettiPieces.push({
          x: rand(0, W),
          y: rand(-H*0.6, -10),
          size: rand(6, 16),
          tilt: rand(-0.2, 0.2),
          speed: rand(1.2, 4.6),
          color: colors[Math.floor(rand(0, colors.length))],
          rotation: rand(0, Math.PI*2),
          spin: rand(-0.06, 0.06),
          shape: Math.random() > 0.5 ? 'rect' : 'circle'
        });
      }
    }

    function updateConfetti(){
      ctx.clearRect(0,0,W,H);
      for(const p of confettiPieces){
        p.x += Math.sin(p.rotation)*0.7 + Math.cos(p.tilt)*0.5;
        p.y += p.speed;
        p.rotation += p.spin;
        // if below screen, reset high
        if(p.y > H + 30){
          p.y = rand(-H*0.5, -10);
          p.x = rand(0, W);
        }
        ctx.save();
        ctx.translate(p.x, p.y);
        ctx.rotate(p.rotation);
        ctx.fillStyle = p.color;
        if(p.shape === 'rect'){
          ctx.fillRect(-p.size/2, -p.size/2, p.size, p.size*0.6);
        } else {
          ctx.beginPath();
          ctx.ellipse(0,0,p.size*0.6,p.size*0.6,0,0,Math.PI*2);
          ctx.fill();
        }
        ctx.restore();
      }
      if(confettiRunning) requestAnimationFrame(updateConfetti);
    }

    function startConfetti(){
      if(confettiRunning) return;
      confettiRunning = true;
      confettiCanvas.style.pointerEvents = 'none';
      confettiCanvas.style.opacity = 1;
      spawnConfetti(80);
      updateConfetti();
      // auto stop after X seconds but keep a gentle fall for a while
      clearTimeout(confettiTimer);
      confettiTimer = setTimeout(()=> { stopConfetti(); }, 9000);
    }

    function stopConfetti(){
      confettiRunning = false;
      // fade out
      confettiCanvas.style.transition = 'opacity 700ms';
      confettiCanvas.style.opacity = 0;
      setTimeout(()=> {
        ctx.clearRect(0,0,W,H);
      }, 800);
    }

    // Accessibility: open with Enter on focused button
    openBtn.addEventListener('keyup', (e)=> { if(e.key === 'Enter' || e.key === ' ') triggerOpen(); });
  })();
</script>
</body>
</html>
