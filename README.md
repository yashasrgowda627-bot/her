
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday, Princess 🌸</title>
<style>
  :root {
    --deep:       #06030f;
    --dark:       #0c0818;
    --mid:        #130d22;
    --pink:       #f472b6;
    --pink-light: #fbcfe8;
    --pink-pale:  #fdf2f8;
    --blue:       #60a5fa;
    --blue-light: #bfdbfe;
    --blue-pale:  #eff6ff;
    --lavender:   #a78bfa;
    --lav-light:  #ddd6fe;
    --lav-pale:   #f5f3ff;
    --white:      #ffffff;
  }
  *, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
  html { scroll-behavior:smooth; }
  body { background:var(--deep); color:var(--white); font-family:'Cormorant Garamond',serif; overflow-x:hidden; }
  #magic-canvas { position:fixed; inset:0; z-index:0; pointer-events:none; }
  section { position:relative; z-index:1; }

  /* ── HERO ── */
  #hero {
    min-height:100vh;
    display:flex; flex-direction:column; align-items:center; justify-content:center;
    text-align:center; padding:2rem;
    background:radial-gradient(ellipse at 50% 40%, #1a0730 0%, #06030f 70%);
    overflow:hidden; position:relative;
  }
  .orb { position:absolute; border-radius:50%; filter:blur(80px); opacity:0.18; animation:orbFloat 10s ease-in-out infinite; }
  .orb1 { width:400px; height:400px; background:#f472b6; top:-15%; left:-10%; }
  .orb2 { width:300px; height:300px; background:#60a5fa; top:50%; right:-8%; animation-delay:3s; }
  .orb3 { width:350px; height:350px; background:#a78bfa; bottom:-10%; left:25%; animation-delay:6s; }
  .orb4 { width:200px; height:200px; background:#f472b6; top:20%; right:15%; animation-delay:1.5s; }
  @keyframes orbFloat {
    0%,100% { transform:translate(0,0) scale(1); }
    33% { transform:translate(20px,-20px) scale(1.05); }
    66% { transform:translate(-15px,15px) scale(0.95); }
  }

  .moon-wrap { margin-bottom:2.5rem; opacity:0; animation:fadeUp 1.4s ease forwards 0.3s; }
  .moon {
    width:clamp(100px,16vw,150px); height:clamp(100px,16vw,150px);
    border-radius:50%; margin:0 auto; position:relative;
    background:radial-gradient(circle at 35% 35%, #fdf2f8, #fbcfe8 35%, #f472b6 65%, #a78bfa 100%);
    box-shadow: 0 0 40px 15px rgba(244,114,182,0.5), 0 0 80px 30px rgba(167,139,250,0.3), 0 0 120px 50px rgba(96,165,250,0.15);
    animation:moonPulse 4s ease-in-out infinite;
  }
  .moon::after { content:''; position:absolute; top:14%; left:18%; width:24%; height:24%; border-radius:50%; background:rgba(255,255,255,0.25); }
  @keyframes moonPulse {
    0%,100% { box-shadow:0 0 40px 15px rgba(244,114,182,0.5),0 0 80px 30px rgba(167,139,250,0.3); }
    50%      { box-shadow:0 0 65px 25px rgba(244,114,182,0.7),0 0 120px 50px rgba(167,139,250,0.45),0 0 160px 70px rgba(96,165,250,0.2); }
  }

  .stars-row { display:flex; justify-content:center; gap:1.4rem; margin-top:1.2rem; }
  .star { font-size:1rem; animation:twinkle 2.2s ease-in-out infinite; }
  .star:nth-child(1){ color:var(--pink); }
  .star:nth-child(2){ color:var(--lavender); animation-delay:.5s; }
  .star:nth-child(3){ color:var(--blue); animation-delay:1s; }
  .star:nth-child(4){ color:var(--pink); animation-delay:1.5s; }
  .star:nth-child(5){ color:var(--lavender); animation-delay:.3s; }
  @keyframes twinkle { 0%,100%{opacity:.3;transform:scale(.8)} 50%{opacity:1;transform:scale(1.3)} }

  .hero-eyebrow { font-family:'Cinzel',serif; font-size:clamp(.55rem,1.4vw,.8rem); letter-spacing:.45em; color:var(--lav-light); text-transform:uppercase; opacity:0; animation:fadeUp 1s ease forwards .9s; margin-bottom:.8rem; }
  .hero-title {
    font-family:'Great Vibes',cursive; font-size:clamp(4.5rem,13vw,10rem);
    background:linear-gradient(135deg, #fbcfe8, #c4b5fd, #bfdbfe, #f9a8d4);
    -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    filter:drop-shadow(0 0 30px rgba(244,114,182,.6)); line-height:1;
    opacity:0; animation:fadeUp 1.3s ease forwards 1.1s;
  }
  .hero-name { font-family:'Cinzel',serif; font-size:clamp(1.6rem,5vw,3.8rem); font-weight:600; letter-spacing:.2em; color:#ffffff; text-shadow:0 0 25px rgba(167,139,250,.7); opacity:0; animation:fadeUp 1.2s ease forwards 1.5s; margin-top:.3em; }
  .hero-date { font-family:'Cormorant Garamond',serif; font-style:italic; font-size:clamp(1rem,2.5vw,1.5rem); color:var(--pink-light); margin-top:1.2rem; letter-spacing:.08em; opacity:0; animation:fadeUp 1s ease forwards 1.9s; }

  .scroll-hint { position:absolute; bottom:2.5rem; left:50%; transform:translateX(-50%); display:flex; flex-direction:column; align-items:center; gap:.5rem; opacity:0; animation:fadeUp 1s ease forwards 2.8s; }
  .scroll-hint span { font-family:'Cinzel',serif; font-size:.55rem; letter-spacing:.35em; color:var(--lav-light); text-transform:uppercase; }
  .scroll-line { width:1px; height:40px; background:linear-gradient(to bottom,var(--lavender),transparent); animation:scrollPulse 2s ease-in-out infinite; }
  @keyframes scrollPulse { 0%,100%{opacity:.3} 50%{opacity:1} }

  /* ── DIVIDER ── */
  .divider { display:flex; align-items:center; gap:1.2rem; padding:0 clamp(2rem,8vw,8rem); margin:1.5rem 0; }
  .divider-line { flex:1; height:1px; background:linear-gradient(to right,transparent,rgba(167,139,250,.5),rgba(244,114,182,.5),transparent); }
  .divider-gem { font-size:.9rem; background:linear-gradient(135deg,var(--pink),var(--lavender)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; }
  .section-label { font-family:'Cinzel',serif; font-size:.65rem; letter-spacing:.4em; color:var(--lav-light); text-transform:uppercase; display:block; margin-bottom:2rem; }

  /* ── COUNTDOWN ── */
  #countdown { padding:clamp(5rem,10vw,9rem) clamp(2rem,8vw,8rem); text-align:center; background:linear-gradient(180deg,#06030f 0%,#0d0520 50%,#06030f 100%); }
  .countdown-title { font-family:'Great Vibes',cursive; font-size:clamp(2.5rem,6vw,4.5rem); background:linear-gradient(135deg,#fbcfe8,#c4b5fd,#bfdbfe); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; margin-bottom:.5rem; filter:drop-shadow(0 0 15px rgba(244,114,182,.5)); }
  .countdown-sub { font-family:'Cormorant Garamond',serif; font-style:italic; font-size:clamp(1rem,2vw,1.3rem); color:var(--lav-light); margin-bottom:3.5rem; opacity:.9; }
  .countdown-grid { display:flex; justify-content:center; align-items:flex-start; gap:clamp(.8rem,3vw,2.5rem); flex-wrap:wrap; }
  .count-box {
    display:flex; flex-direction:column; align-items:center; gap:.7rem;
    background:linear-gradient(135deg,rgba(244,114,182,.07),rgba(167,139,250,.07));
    border:1px solid rgba(167,139,250,.3); border-radius:14px;
    padding:clamp(1rem,3vw,2rem) clamp(1.2rem,3vw,2.2rem);
    min-width:clamp(70px,15vw,110px); position:relative; overflow:hidden; transition:all .3s;
  }
  .count-box::before { content:''; position:absolute; inset:0; background:radial-gradient(ellipse at 50% 0%,rgba(244,114,182,.1),transparent 70%); }
  .count-box:hover { border-color:rgba(244,114,182,.6); transform:translateY(-4px); box-shadow:0 10px 30px rgba(244,114,182,.15); }
  .count-number { font-family:'Cinzel',serif; font-size:clamp(2.2rem,6vw,4.5rem); font-weight:600; background:linear-gradient(135deg,#fbcfe8,#c4b5fd,#93c5fd); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; filter:drop-shadow(0 0 10px rgba(244,114,182,.4)); line-height:1; min-width:2ch; text-align:center; }
  .count-unit { font-family:'Cinzel',serif; font-size:.55rem; letter-spacing:.25em; color:var(--lav-light); opacity:.8; text-transform:uppercase; }
  .count-sep { font-family:'Cinzel',serif; font-size:clamp(1.8rem,4vw,3rem); background:linear-gradient(135deg,var(--pink),var(--lavender)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; opacity:.6; margin-top:.5rem; }
  .countdown-msg { margin-top:2.5rem; font-family:'Great Vibes',cursive; font-size:clamp(1.6rem,4vw,2.5rem); color:var(--pink-light); animation:glowPulse 3s ease-in-out infinite; }
  @keyframes glowPulse { 0%,100%{filter:drop-shadow(0 0 6px rgba(244,114,182,.4))} 50%{filter:drop-shadow(0 0 25px rgba(244,114,182,.8))} }

  /* ── LETTER ── */
  #letter { padding:clamp(5rem,10vw,10rem) clamp(2rem,8vw,10rem); background:linear-gradient(180deg,#06030f 0%,#100520 50%,#06030f 100%); text-align:center; }
  .letter-title { font-family:'Great Vibes',cursive; font-size:clamp(3rem,7vw,5.5rem); background:linear-gradient(135deg,#fbcfe8,#c4b5fd,#93c5fd); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; filter:drop-shadow(0 0 18px rgba(244,114,182,.4)); margin-bottom:3rem; }
  .letter-body { max-width:820px; margin:0 auto; text-align:left; background:linear-gradient(135deg,rgba(244,114,182,.04),rgba(167,139,250,.04),rgba(96,165,250,.04)); border:1px solid rgba(167,139,250,.2); border-radius:20px; padding:clamp(2.5rem,6vw,5rem); position:relative; }
  .letter-body::before { content:''; position:absolute; inset:0; border-radius:20px; background:radial-gradient(ellipse at 30% 0%,rgba(244,114,182,.07),transparent 55%),radial-gradient(ellipse at 80% 100%,rgba(96,165,250,.06),transparent 55%); pointer-events:none; }
  .big-quote { font-family:'Great Vibes',cursive; font-size:8rem; background:linear-gradient(135deg,var(--pink),var(--lavender)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; opacity:.15; line-height:.5; display:block; margin-bottom:-1rem; user-select:none; }
  .letter-para { font-family:'Cormorant Garamond',serif; font-size:clamp(1.1rem,2.2vw,1.55rem); font-weight:300; line-height:2.3; color:#f0e8ff; margin-bottom:2rem; }
  .letter-para:last-child { margin-bottom:0; }
  .letter-para em { color:var(--pink-light); font-style:normal; font-weight:400; }
  .letter-para strong { color:var(--lav-light); font-weight:500; }

  /* ── REASONS ── */
  #reasons { padding:clamp(5rem,10vw,10rem) clamp(2rem,8vw,8rem); background:var(--deep); }
  .reasons-header { text-align:center; margin-bottom:5rem; }
  .reasons-title { font-family:'Great Vibes',cursive; font-size:clamp(3rem,7vw,5rem); background:linear-gradient(135deg,#f9a8d4,#c4b5fd,#93c5fd); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; filter:drop-shadow(0 0 15px rgba(244,114,182,.3)); }
  .reasons-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(280px,1fr)); gap:1.5rem; max-width:1100px; margin:0 auto; }
  .reason-card { background:linear-gradient(135deg,rgba(244,114,182,.06),rgba(167,139,250,.05),rgba(96,165,250,.04)); border:1px solid rgba(167,139,250,.18); border-radius:18px; padding:2.5rem 2rem; position:relative; overflow:hidden; transition:transform .4s,border-color .4s,box-shadow .4s; }
  .reason-card::before { content:''; position:absolute; inset:0; background:radial-gradient(circle at 50% 0%,rgba(244,114,182,.08),transparent 60%); opacity:0; transition:opacity .4s; }
  .reason-card:hover { transform:translateY(-7px); border-color:rgba(244,114,182,.45); box-shadow:0 20px 50px rgba(244,114,182,.12),0 0 0 1px rgba(167,139,250,.1); }
  .reason-card:hover::before { opacity:1; }
  .reason-icon { font-size:2.2rem; display:block; margin-bottom:1.2rem; }
  .reason-num { font-family:'Cinzel',serif; font-size:.6rem; letter-spacing:.3em; background:linear-gradient(135deg,var(--pink),var(--lavender)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; opacity:.8; display:block; margin-bottom:.8rem; }
  .reason-text { font-family:'Cormorant Garamond',serif; font-size:1.15rem; font-style:italic; line-height:1.9; color:#e8d8f8; }

  /* ── POEM ── */
  #poem { padding:clamp(5rem,10vw,10rem) clamp(2rem,8vw,8rem); background:linear-gradient(180deg,#06030f 0%,#0a0420 50%,#06030f 100%); text-align:center; }
  .poem-container { max-width:660px; margin:3rem auto 0; border-left:2px solid rgba(244,114,182,.5); padding-left:3rem; text-align:left; }
  .poem-stanza { margin-bottom:2.5rem; }
  .poem-line { font-family:'Cormorant Garamond',serif; font-size:clamp(1.05rem,2.2vw,1.5rem); font-weight:300; line-height:2.3; color:#ffffff; display:block; opacity:0; transform:translateX(-20px); transition:opacity .9s ease,transform .9s ease; }
  .poem-line.glow { color:var(--lav-light); font-style:italic; }
  .poem-line.pink { color:var(--pink-light); font-style:italic; }
  .poem-line.blue { color:var(--blue-light); font-style:italic; }
  .poem-line.visible { opacity:1; transform:translateX(0); }

  /* ── PROMISES ── */
  #promises { padding:clamp(5rem,10vw,10rem) clamp(2rem,8vw,8rem); background:var(--deep); text-align:center; }
  .promises-title { font-family:'Great Vibes',cursive; font-size:clamp(3rem,7vw,5rem); background:linear-gradient(135deg,#fbcfe8,#c4b5fd,#bfdbfe); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; filter:drop-shadow(0 0 18px rgba(167,139,250,.4)); margin-bottom:1rem; }
  .promises-sub { font-family:'Cormorant Garamond',serif; font-style:italic; font-size:clamp(1rem,2vw,1.3rem); color:var(--lav-light); opacity:.85; margin-bottom:4rem; }
  .promises-list { max-width:740px; margin:0 auto; display:flex; flex-direction:column; gap:1.5rem; }
  .promise-item { display:flex; align-items:flex-start; gap:1.5rem; background:linear-gradient(135deg,rgba(244,114,182,.05),rgba(167,139,250,.05)); border:1px solid rgba(167,139,250,.15); border-radius:14px; padding:2rem 2.5rem; text-align:left; transition:border-color .3s,transform .3s,box-shadow .3s; }
  .promise-item:hover { border-color:rgba(244,114,182,.4); transform:translateX(6px); box-shadow:0 8px 30px rgba(244,114,182,.1); }
  .promise-icon { font-size:1.6rem; flex-shrink:0; margin-top:.2rem; }
  .promise-text { font-family:'Cormorant Garamond',serif; font-size:clamp(1.05rem,2vw,1.4rem); font-style:italic; line-height:1.9; color:#e8d8f8; }

  /* ── EXTRA LOVE NOTE ── */
  #lovenote {
    padding:clamp(5rem,10vw,9rem) clamp(2rem,8vw,8rem);
    background:linear-gradient(180deg,#06030f 0%,#110626 50%,#06030f 100%);
    text-align:center;
  }
  .lovenote-inner {
    max-width:700px; margin:0 auto;
    background:linear-gradient(135deg,rgba(244,114,182,.06),rgba(167,139,250,.06),rgba(96,165,250,.04));
    border:1px solid rgba(244,114,182,.2); border-radius:20px;
    padding:clamp(3rem,6vw,5rem);
    position:relative;
  }
  .lovenote-inner::before { content:''; position:absolute; inset:0; border-radius:20px; background:radial-gradient(ellipse at 50% 0%,rgba(244,114,182,.08),transparent 60%); pointer-events:none; }
  .lovenote-icon { font-size:3rem; display:block; margin-bottom:1.5rem; animation:heartbeat 1.6s ease-in-out infinite; }
  .lovenote-title { font-family:'Great Vibes',cursive; font-size:clamp(2.5rem,6vw,4rem); background:linear-gradient(135deg,#fbcfe8,#c4b5fd); -webkit-background-clip:text; -webkit-text-fill-color:transparent; margin-bottom:2rem; }
  .lovenote-text { font-family:'Cormorant Garamond',serif; font-size:clamp(1.1rem,2.2vw,1.6rem); font-style:italic; line-height:2.2; color:#f0e8ff; }
  .lovenote-text em { color:var(--pink-light); font-style:normal; }

  /* ── FINAL ── */
  #final { min-height:85vh; display:flex; flex-direction:column; align-items:center; justify-content:center; text-align:center; padding:clamp(5rem,10vw,10rem) clamp(2rem,8vw,6rem); background:radial-gradient(ellipse at 50% 55%,#1a0530 0%,#06030f 70%); position:relative; overflow:hidden; }
  .final-eyebrow { font-family:'Cinzel',serif; font-size:.65rem; letter-spacing:.4em; color:var(--lav-light); text-transform:uppercase; margin-bottom:1.5rem; }
  .final-title { font-family:'Great Vibes',cursive; font-size:clamp(4rem,11vw,9rem); background:linear-gradient(135deg,#fce7f3,#f0abfc,#bfdbfe,#fbcfe8); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; filter:drop-shadow(0 0 35px rgba(244,114,182,.55)); animation:glowPulse 3s ease-in-out infinite; line-height:1.1; margin-bottom:1rem; }
  .final-body { font-family:'Cormorant Garamond',serif; font-size:clamp(1.1rem,2.5vw,1.7rem); font-style:italic; font-weight:300; line-height:2.2; color:#ede0ff; max-width:700px; margin:1.5rem auto; }
  .final-body em { color:var(--pink-light); font-style:normal; font-weight:400; }
  .heart { font-size:3.5rem; display:block; margin:2rem auto; animation:heartbeat 1.4s ease-in-out infinite; }
  @keyframes heartbeat { 0%,100%{transform:scale(1);filter:drop-shadow(0 0 6px rgba(244,114,182,.4))} 14%{transform:scale(1.35);filter:drop-shadow(0 0 25px rgba(244,114,182,.8))} 28%{transform:scale(1)} 42%{transform:scale(1.15)} 56%{transform:scale(1)} }
  .signature { font-family:'Great Vibes',cursive; font-size:clamp(1.8rem,4vw,3.2rem); background:linear-gradient(135deg,#fbcfe8,#c4b5fd,#93c5fd); -webkit-background-clip:text; -webkit-text-fill-color:transparent; margin-top:1rem; }
  .sparkles-row { display:flex; gap:1rem; justify-content:center; margin-top:2rem; font-size:1.3rem; animation:glowPulse 2.5s ease-in-out infinite; }

  footer { text-align:center; padding:2rem; border-top:1px solid rgba(167,139,250,.15); font-family:'Cinzel',serif; font-size:.55rem; letter-spacing:.3em; color:rgba(244,114,182,.4); text-transform:uppercase; }

  @keyframes fadeUp { from{opacity:0;transform:translateY(35px)} to{opacity:1;transform:translateY(0)} }
  .reveal { opacity:0; transform:translateY(40px); transition:opacity .9s ease,transform .9s ease; }
  .reveal.visible { opacity:1; transform:translateY(0); }
</style>
</head>
<body>

<canvas id="magic-canvas"></canvas>

<!-- ── HERO ── -->
<section id="hero">
  <div class="orb orb1"></div><div class="orb orb2"></div><div class="orb orb3"></div><div class="orb orb4"></div>
  <div class="moon-wrap">
    <div class="moon"></div>
    <div class="stars-row">
      <span class="star">✦</span><span class="star">✧</span><span class="star">✦</span><span class="star">✧</span><span class="star">✦</span>
    </div>
  </div>
  <div class="hero-eyebrow">A world of love — created just for you</div>
  <h1 class="hero-title">Happy Birthday</h1>
  <div class="hero-name">Nikitha 💗</div>
  <div style="font-family:'Great Vibes',cursive; font-size:clamp(1.8rem,4vw,2.8rem); color:var(--lav-light); opacity:0; animation:fadeUp 1.2s ease forwards 1.8s; letter-spacing:.05em;">my Niku ✨</div>
  <div class="hero-date">August 10th — the night heaven sent its finest star to Earth 🌸</div>
  <div class="scroll-hint"><span>Scroll</span><div class="scroll-line"></div></div>
</section>

<!-- ── COUNTDOWN ── -->
<section id="countdown">
  <div class="divider reveal"><div class="divider-line"></div><div class="divider-gem">✦</div><div class="divider-line"></div></div>
  <div class="countdown-title reveal">Every second, I think of you…</div>
  <p class="countdown-sub reveal">Counting down to the most beautiful day of the year</p>
  <div class="countdown-grid reveal">
    <div class="count-box"><div class="count-number" id="cd-days">--</div><div class="count-unit">Days</div></div>
    <div class="count-sep">:</div>
    <div class="count-box"><div class="count-number" id="cd-hours">--</div><div class="count-unit">Hours</div></div>
    <div class="count-sep">:</div>
    <div class="count-box"><div class="count-number" id="cd-mins">--</div><div class="count-unit">Minutes</div></div>
    <div class="count-sep">:</div>
    <div class="count-box"><div class="count-number" id="cd-secs">--</div><div class="count-unit">Seconds</div></div>
  </div>
  <div class="countdown-msg reveal" id="cd-msg">until your birthday, my Niku 🌸</div>
  <div class="divider reveal" style="margin-top:3rem"><div class="divider-line"></div><div class="divider-gem">✦</div><div class="divider-line"></div></div>
</section>

<!-- ── LETTER ── -->
<section id="letter">
  <span class="section-label reveal">From the deepest corner of my heart</span>
  <div class="letter-title reveal">A Letter to My Nikitha — My Niku 💌</div>
  <div class="letter-body reveal">
    <span class="big-quote">"</span>
    <p class="letter-para">My dearest <em>Nikitha</em>, my <em>Niku</em>,<br><br>
    I have been trying to find the right words for so long — words that could hold even a fraction of what I feel for you. But I've come to realise that no words were ever made big enough, deep enough, or beautiful enough for what you mean to me. Still, I'll try. Because you deserve every single attempt.</p>
    <p class="letter-para">Before you came into my life, I didn't know love could feel like <em>coming home</em>. I didn't know that one person could make the whole world quieter just by being in the room. You did that. You still do that. Every. Single. Day. <em>Nikitha</em>, you changed everything.</p>
    <p class="letter-para">I think about all the little things that make you, <em>you</em> — the way your eyes light up when you're excited, the warmth you carry everywhere you go, the way you laugh like nothing in the world could touch you in that moment. I fall in love with all of it, over and over again, every single day.</p>
    <p class="letter-para">There are nights when I just lie there, completely overwhelmed by how <em>lucky</em> I am. That of all the people in this world, I get to call you mine. That your hand fits in mine. That your smile is something I've seen a hundred times and still can't breathe around. <strong>You are the most beautiful thing that has ever happened to me, Nikitha.</strong></p>
    <p class="letter-para">On this birthday, I want you to feel wrapped in every prayer I have whispered for you, every dream I've dreamed about our future, every quiet moment I looked at you and thought — <em>"she is everything."</em> Because you are. You always have been and you always will be.</p>
    <p class="letter-para">I love you more than I know how to say. More than this page can hold. More than any birthday message could ever carry. But I hope that when you read this, somewhere deep in your heart — <strong>you feel every bit of it, Nikitha.</strong></p>
    <p class="letter-para" style="text-align:right; margin-top:2.5rem; color:var(--pink-light); font-style:italic; font-size:1.2em;">Yours completely, today and in every life after this 🌸</p>
  </div>
</section>

<!-- ── REASONS ── -->
<section id="reasons">
  <div class="divider reveal"><div class="divider-line"></div><div class="divider-gem">✦</div><div class="divider-line"></div></div>
  <div class="reasons-header reveal">
    <span class="section-label">Why my heart chose you</span>
    <div class="reasons-title">A thousand reasons I love you, Nikitha 💙</div>
  </div>
  <div class="reasons-grid">
    <div class="reason-card reveal"><span class="reason-icon">🌸</span><span class="reason-num">01</span><p class="reason-text">The way your smile can completely disarm me. One look and I forget every worry I ever had. You are my favourite kind of magic.</p></div>
    <div class="reason-card reveal"><span class="reason-icon">💙</span><span class="reason-num">02</span><p class="reason-text">Your laugh — pure, real, and free. It's the most beautiful sound in my entire world and I would cross oceans just to hear it.</p></div>
    <div class="reason-card reveal"><span class="reason-icon">💜</span><span class="reason-num">03</span><p class="reason-text">The way you love — fearlessly and fully. You give so much of yourself to the people you care about and it makes me love you more every time.</p></div>
    <div class="reason-card reveal"><span class="reason-icon">🌙</span><span class="reason-num">04</span><p class="reason-text">How you make ordinary moments feel like the most special things in the world. With you, even silence feels like a love song.</p></div>
    <div class="reason-card reveal"><span class="reason-icon">✨</span><span class="reason-num">05</span><p class="reason-text">Your strength — the quiet kind that holds everything together. You face the world with so much grace and I am in awe of you every single day.</p></div>
    <div class="reason-card reveal"><span class="reason-icon">🦋</span><span class="reason-num">06</span><p class="reason-text">The kindness you carry without even trying. You make the people around you feel seen, valued, and loved — and that is one of the rarest gifts.</p></div>
    <div class="reason-card reveal"><span class="reason-icon">🌺</span><span class="reason-num">07</span><p class="reason-text">Your heart — the way it's warm enough to hold everyone yet somehow it chose me. I will never stop being grateful for that.</p></div>
    <div class="reason-card reveal"><span class="reason-icon">💖</span><span class="reason-num">08</span><p class="reason-text">Simply because you exist. The world became a more beautiful, gentler, more magical place the day you came into it. I'm so glad you're here.</p></div>
  </div>
  <div class="divider reveal" style="margin-top:4rem"><div class="divider-line"></div><div class="divider-gem">✦</div><div class="divider-line"></div></div>
</section>

<!-- ── POEM ── -->
<section id="poem">
  <span class="section-label reveal">Whispered by the stars, written for you</span>
  <div class="letter-title reveal" style="font-size:clamp(2.5rem,6vw,4rem)">A Poem for My Princess 🌙</div>
  <div class="poem-container">
    <div class="poem-stanza">
      <span class="poem-line">In soft pink skies and lavender light,</span>
      <span class="poem-line glow">you are the star that owns the night,</span>
      <span class="poem-line">a blue-eyed dream the universe keeps —</span>
      <span class="poem-line pink">the promise the whole world softly speaks.</span>
    </div>
    <div class="poem-stanza">
      <span class="poem-line">You are the warmth in cold night air,</span>
      <span class="poem-line blue">the gentleness beyond compare,</span>
      <span class="poem-line">the tender hush before the dawn —</span>
      <span class="poem-line glow">the reason I keep carrying on.</span>
    </div>
    <div class="poem-stanza">
      <span class="poem-line">Another year of you — a gift</span>
      <span class="poem-line pink">that gives my tired heart a lift,</span>
      <span class="poem-line">the kind of love that stories chase —</span>
      <span class="poem-line blue">and I found mine in your sweet face.</span>
    </div>
    <div class="poem-stanza">
      <span class="poem-line">So here I am on bended heart,</span>
      <span class="poem-line glow">loving you — a lifelong art,</span>
      <span class="poem-line">and every birthday that you see —</span>
      <span class="poem-line pink">I'll love you more impossibly.</span>
    </div>
    <div class="poem-stanza">
      <span class="poem-line" style="color:var(--lav-light); font-size:1.1em; margin-top:1rem;">Happy Birthday, my love. My heart. My entire world. 💜</span>
    </div>
  </div>
</section>

<!-- ── LOVE NOTE ── -->
<section id="lovenote">
  <div class="divider reveal"><div class="divider-line"></div><div class="divider-gem">✦</div><div class="divider-line"></div></div>
  <div class="lovenote-inner reveal">
    <span class="lovenote-icon">💗</span>
    <div class="lovenote-title">Just So You Know…</div>
    <p class="lovenote-text">
      On the days you feel like you're not enough — I need you to remember that you are more than enough for me. You are <em>everything.</em><br><br>
      On the days the world feels heavy — I need you to remember that I am right here, always, ready to carry whatever you can't hold alone.<br><br>
      On the days you forget how beautiful you are — I need you to remember that I see it. I see it in the way you walk into a room, in the way you care, in the way you are simply, undeniably, breathtakingly <em>you.</em><br><br>
      I chose you. I choose you. I will always, <em>always</em> choose you.
    </p>
  </div>
  <div class="divider reveal" style="margin-top:3rem"><div class="divider-line"></div><div class="divider-gem">✦</div><div class="divider-line"></div></div>
</section>

<!-- ── PROMISES ── -->
<section id="promises">
  <span class="section-label reveal">My vows to you</span>
  <div class="promises-title reveal">Promises I Will Never Break</div>
  <p class="promises-sub reveal">Not just words. These are pieces of my heart, offered to you — today and always.</p>
  <div class="promises-list">
    <div class="promise-item reveal"><span class="promise-icon">🌸</span><p class="promise-text">I promise to be your safe place — your soft landing in a hard world, the arms that always feel like home, no matter what.</p></div>
    <div class="promise-item reveal"><span class="promise-icon">💙</span><p class="promise-text">I promise to remind you every single day how loved you are — not just in words, but in the way I look at you, hold you, choose you.</p></div>
    <div class="promise-item reveal"><span class="promise-icon">💜</span><p class="promise-text">I promise to love you on the hard days most of all — the days you're tired, broken, or unsure. Those are the days I will love you loudest.</p></div>
    <div class="promise-item reveal"><span class="promise-icon">🌙</span><p class="promise-text">I promise to make you laugh so much that your cheeks hurt, your eyes water, and you forget every sad thing that ever touched your heart.</p></div>
    <div class="promise-item reveal"><span class="promise-icon">✨</span><p class="promise-text">I promise to stand in your corner for every dream you dare to dream — cheering louder than anyone, believing in you even when you can't believe in yourself.</p></div>
    <div class="promise-item reveal"><span class="promise-icon">💖</span><p class="promise-text">I promise to never stop choosing you. Not today. Not tomorrow. Not in a hundred years. It will always, endlessly, beautifully be you.</p></div>
  </div>
  <div class="divider reveal" style="margin-top:4rem"><div class="divider-line"></div><div class="divider-gem">✦</div><div class="divider-line"></div></div>
</section>

<!-- ── PERSONAL LETTER ── -->
<section id="personalletter" style="padding:clamp(5rem,10vw,10rem) clamp(2rem,8vw,10rem); background:linear-gradient(180deg,#06030f 0%,#12062a 50%,#06030f 100%); text-align:center;">
  <div class="divider reveal"><div class="divider-line"></div><div class="divider-gem">✦</div><div class="divider-line"></div></div>
  <span class="section-label reveal">Only for you, my Niku 💗</span>
  <div class="letter-title reveal" style="font-size:clamp(2.8rem,6vw,5rem);">The Letter My Heart Wrote 💜</div>
  <div class="letter-body reveal" style="max-width:820px; margin:0 auto; border-color:rgba(244,114,182,.25);">
    <span class="big-quote">"</span>
    <p class="letter-para"><em>Nikitha</em>, my <em>Niku</em>,<br><br>
    Do you know what it feels like to look at someone and just <em>know</em>? To know that this person, this exact person in front of you, is someone your heart recognises? That's what happened to me. The moment you came into my life — something inside me exhaled. Like I had been holding my breath for years and finally found the one person who made it okay to breathe.</p>
    <p class="letter-para">I want you to know, <em>Nikitha</em> — not just today, not just on your birthday — but always — that you are loved in the deepest, most real, most honest way possible. Not because you're perfect. But because you are <em>you.</em> And you, just as you are, are more than enough. You are everything.</p>
    <p class="letter-para">When I think about the future, <em>you</em> are in every single version of it. Every dream I have is a little brighter because you're there. Every road feels less scary because I know I get to walk it with you. You are not just a part of my life, Nikitha — <strong>you are the reason my life feels worth living beautifully.</strong></p>
    <p class="letter-para">On this birthday, I want you to close your eyes and feel everything I've never been able to say out loud. Feel every time I looked at you and thought you were the most beautiful thing I'd ever seen. Feel every prayer I've whispered for your happiness. Feel every moment I chose you — quietly, completely, <em>forever.</em></p>
    <p class="letter-para" style="font-size:1.3em; text-align:center; margin-top:2rem; line-height:2.5;">
      <strong style="color:var(--pink-light);">Happy Birthday, Nikitha — my Niku.</strong><br>
      <span style="color:var(--lav-light);">You are my heart, my home, my everything.</span><br>
      <em style="color:var(--blue-light); font-size:1.2em; font-style:normal;">I love you, meri jaan. 💗</em>
    </p>
  </div>
  <div class="divider reveal" style="margin-top:3rem"><div class="divider-line"></div><div class="divider-gem">✦</div><div class="divider-line"></div></div>
</section>

<!-- ── FINAL ── -->
<section id="final">
  <div class="orb orb1" style="opacity:.1"></div><div class="orb orb2" style="opacity:.1"></div><div class="orb orb3" style="opacity:.08"></div>
  <div class="final-eyebrow reveal">And the universe whispers —</div>
  <div class="final-title reveal">Happy Birthday, Nikitha 🌸</div>
  <p class="final-body reveal">
    May this year be the most beautiful one yet, <em>Nikitha</em>.<br>
    May every single morning feel like a gift made just for you.<br>
    May love surround you the way it lives inside my heart —<br><em>endlessly</em>, completely, and without any condition.<br>
    May you always know, in your bones, in your soul —<br>
    that you are my <em>entire universe.</em>
  </p>
  <span class="heart reveal">💗</span>
  <div class="signature reveal" style="font-size:clamp(2rem,5vw,3.8rem); margin-top:1.5rem;">I love you, meri jaan 💜</div>
  <p class="reveal" style="font-family:'Cormorant Garamond',serif; font-style:italic; font-size:clamp(1rem,2vw,1.4rem); color:var(--lav-light); margin-top:1.2rem; opacity:.85;">— Always yours, forever and beyond 🌸</p>
  <div class="sparkles-row reveal">
    <span style="color:var(--pink)">✦</span>
    <span style="color:var(--lavender)">✧</span>
    <span style="color:var(--blue)">✦</span>
    <span style="color:var(--pink)">✧</span>
    <span style="color:var(--lavender)">✦</span>
    <span style="color:var(--blue)">✧</span>
    <span style="color:var(--pink)">✦</span>
  </div>
</section>

<footer>Made with every bit of love I have · For my Nikitha — my Niku · August 10 · I love you, meri jaan 💗</footer>

<script>
/* ── PARTICLES ── */
const canvas = document.getElementById('magic-canvas');
const ctx = canvas.getContext('2d');
let W, H;
function resize(){ W = canvas.width = window.innerWidth; H = canvas.height = window.innerHeight; }
resize(); window.addEventListener('resize', resize);

const COLORS = [
  'rgba(244,114,182,',   // pink
  'rgba(167,139,250,',   // lavender
  'rgba(96,165,250,',    // blue
  'rgba(249,168,212,',   // pink light
  'rgba(196,181,253,',   // lavender light
  'rgba(147,197,253,',   // blue light
  'rgba(255,255,255,',   // white sparkle
];

class Particle {
  constructor(){ this.reset(true); }
  reset(init=false){
    this.x = Math.random()*W;
    this.y = init ? Math.random()*H : H+10;
    this.r = Math.random()*2.2+0.3;
    this.vx = (Math.random()-.5)*.35;
    this.vy = -(Math.random()*.55+.15);
    this.alpha = 0;
    this.maxAlpha = Math.random()*.55+.12;
    this.phase = Math.random()*Math.PI*2;
    this.speed = Math.random()*.025+.008;
    this.color = COLORS[Math.floor(Math.random()*COLORS.length)];
    this.isGlow = Math.random()>.65;
  }
  update(){
    this.phase += this.speed;
    this.x += this.vx + Math.sin(this.phase)*.4;
    this.y += this.vy;
    this.alpha = this.maxAlpha*(0.5+0.5*Math.sin(this.phase));
    if(this.y < -10) this.reset();
  }
  draw(){
    ctx.save();
    if(this.isGlow){
      ctx.shadowBlur = 16;
      ctx.shadowColor = this.color+'0.9)';
    }
    ctx.beginPath();
    ctx.arc(this.x,this.y,this.r,0,Math.PI*2);
    ctx.fillStyle = `${this.color}${this.alpha})`;
    ctx.fill();
    ctx.restore();
  }
}
for(let i=0;i<180;i++) new Array(1).fill(0).forEach(()=>{ const p=new Particle(); canvas._particles=(canvas._particles||[]); canvas._particles.push(p); });
const particles = canvas._particles;
function animate(){ ctx.clearRect(0,0,W,H); particles.forEach(p=>{p.update();p.draw();}); requestAnimationFrame(animate); }
animate();

/* ── SCROLL REVEAL ── */
const revs = document.querySelectorAll('.reveal');
const ro = new IntersectionObserver(entries=>{
  entries.forEach(e=>{ if(e.isIntersecting) e.target.classList.add('visible'); });
},{threshold:.1});
revs.forEach(el=>ro.observe(el));

/* ── POEM REVEAL ── */
const poemSec = document.getElementById('poem');
const poemLines = poemSec.querySelectorAll('.poem-line');
const po = new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){ poemLines.forEach((l,i)=>setTimeout(()=>l.classList.add('visible'),i*230)); po.disconnect(); }
  });
},{threshold:.08});
po.observe(poemSec);

/* ── COUNTDOWN ── */
function updateCountdown(){
  const now = new Date();
  const target = new Date(now.getFullYear(),7,10,0,0,0);
  if(now >= target) target.setFullYear(target.getFullYear()+1);
  const diff = target - now;
  const days  = Math.floor(diff/86400000);
  const hours = Math.floor((diff%86400000)/3600000);
  const mins  = Math.floor((diff%3600000)/60000);
  const secs  = Math.floor((diff%60000)/1000);
  document.getElementById('cd-days').textContent  = String(days).padStart(2,'0');
  document.getElementById('cd-hours').textContent = String(hours).padStart(2,'0');
  document.getElementById('cd-mins').textContent  = String(mins).padStart(2,'0');
  document.getElementById('cd-secs').textContent  = String(secs).padStart(2,'0');
  if(days===0&&hours===0&&mins===0&&secs<10){
    document.getElementById('cd-msg').textContent='🎉 It\'s your day, Nikitha! The whole world celebrates YOU today! 💗';
  }
}
updateCountdown();
setInterval(updateCountdown,1000);
</script>
</body>
</html>
