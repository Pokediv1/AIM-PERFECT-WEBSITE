<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover"/>
<meta name="theme-color" content="#08080f"/>
<meta name="apple-mobile-web-app-capable" content="yes"/>
<title>AIM PERFECT™</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;600;700;800;900&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
html{scroll-behavior:smooth;-webkit-text-size-adjust:100%;-webkit-tap-highlight-color:transparent;}
:root{
  --bg:#08080f;
  --card:#0f0f1b;
  --card2:#13131f;
  --border:rgba(255,255,255,0.07);
  --red:#e31c2e;
  --red-glow:rgba(227,28,46,0.35);
  --gold:#ffc940;
  --gold2:#ff9500;
  --txt:#f0f0fa;
  --sub:#52526a;
  --r:16px;
}
body{
  background:var(--bg);
  color:var(--txt);
  font-family:'Outfit',sans-serif;
  font-size:16px;
  line-height:1.5;
  overflow-x:hidden;
  -webkit-font-smoothing:antialiased;
}

/* ─── NAV ─── */
.nav{
  position:fixed;top:0;left:0;right:0;z-index:200;
  height:54px;
  display:flex;align-items:center;justify-content:space-between;
  padding:0 16px;
  background:rgba(8,8,15,0.96);
  backdrop-filter:blur(20px);
  -webkit-backdrop-filter:blur(20px);
  border-bottom:1px solid rgba(227,28,46,0.1);
}
.nav-brand{
  font-weight:900;font-size:18px;letter-spacing:-.03em;
  color:var(--txt);text-decoration:none;
}
.nav-brand sup{font-size:10px;font-weight:400;color:var(--sub);letter-spacing:0;}
.nav-gold{
  background:linear-gradient(135deg,var(--gold),var(--gold2));
  color:#000;font-weight:700;font-size:13px;
  padding:8px 16px;border-radius:100px;
  border:none;cursor:pointer;text-decoration:none;
  display:inline-block;
  transition:opacity .15s;
}
.nav-gold:active{opacity:.75;}

/* ─── HERO ─── */
.hero{
  min-height:100svh;
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  text-align:center;
  padding:80px 20px 56px;
  position:relative;overflow:hidden;
}
.hero-glow{
  position:absolute;
  width:600px;height:600px;
  border-radius:50%;
  background:radial-gradient(circle,rgba(227,28,46,0.14) 0%,transparent 65%);
  top:-200px;left:50%;transform:translateX(-50%);
  pointer-events:none;
}
.hero-glow2{
  position:absolute;
  width:400px;height:400px;
  border-radius:50%;
  background:radial-gradient(circle,rgba(180,10,20,0.09) 0%,transparent 65%);
  bottom:-100px;left:50%;transform:translateX(-50%);
  pointer-events:none;
}
.hero-tag{
  display:inline-block;
  font-family:'JetBrains Mono',monospace;
  font-size:10px;letter-spacing:.18em;
  color:rgba(255,100,100,.55);
  text-transform:uppercase;
  margin-bottom:20px;
  opacity:0;animation:up .5s .05s forwards;
}
.hero-h{
  font-weight:900;
  font-size:clamp(64px,18vw,108px);
  line-height:.85;
  letter-spacing:-.05em;
  margin-bottom:18px;
  opacity:0;animation:up .5s .15s forwards;
}
.hero-h .solid{display:block;color:var(--txt);}
.hero-h .outline{
  display:block;
  color:transparent;
  -webkit-text-stroke:2.5px var(--red);
  text-shadow:0 0 60px rgba(227,28,46,0.2);
}
.hero-h .tm{
  font-size:.22em;
  color:rgba(255,255,255,.1);
  -webkit-text-stroke:.5px rgba(255,255,255,.1);
  vertical-align:super;
  letter-spacing:0;
}
.hero-p{
  font-size:15px;font-weight:400;color:var(--sub);
  max-width:300px;margin:0 auto 32px;
  opacity:0;animation:up .5s .25s forwards;
}
.hero-p b{color:rgba(255,255,255,.65);font-weight:600;}
.hero-btns{
  display:flex;gap:10px;justify-content:center;
  margin-bottom:40px;
  opacity:0;animation:up .5s .33s forwards;
}
.btn-r{
  background:var(--red);color:#fff;
  font-family:'Outfit',sans-serif;
  font-weight:700;font-size:15px;
  padding:14px 28px;border-radius:100px;
  border:none;cursor:pointer;
  box-shadow:0 4px 28px var(--red-glow);
  transition:transform .15s,box-shadow .15s;
  touch-action:manipulation;
}
.btn-r:active{transform:scale(.96);box-shadow:0 2px 14px var(--red-glow);}
.btn-b{
  background:transparent;color:var(--txt);
  font-family:'Outfit',sans-serif;
  font-weight:600;font-size:15px;
  padding:14px 28px;border-radius:100px;
  border:1.5px solid rgba(255,255,255,.1);
  cursor:pointer;transition:border-color .15s,transform .15s;
  touch-action:manipulation;
}
.btn-b:active{transform:scale(.96);border-color:rgba(255,255,255,.3);}

.hero-pills{
  display:flex;gap:0;
  border:1px solid rgba(227,28,46,.14);
  border-radius:14px;overflow:hidden;
  max-width:360px;width:100%;
  opacity:0;animation:up .5s .41s forwards;
}
.pill{
  flex:1;padding:13px 6px;text-align:center;
  border-right:1px solid rgba(255,255,255,.05);
}
.pill:last-child{border-right:none;}
.pill-n{
  display:block;font-weight:800;font-size:20px;line-height:1;
  color:var(--red);
}
.pill-l{
  display:block;
  font-family:'JetBrains Mono',monospace;
  font-size:8px;letter-spacing:.12em;color:var(--sub);
  text-transform:uppercase;margin-top:3px;
}

@keyframes up{
  from{opacity:0;transform:translateY(16px);}
  to{opacity:1;transform:none;}
}

/* ─── DIVIDER ─── */
.hr{
  height:1px;
  background:linear-gradient(90deg,transparent,rgba(227,28,46,.25) 50%,transparent);
}

/* ─── SECTION ─── */
.sec{max-width:640px;margin:0 auto;padding:60px 16px;}
.eyebrow{
  font-family:'JetBrains Mono',monospace;
  font-size:10px;letter-spacing:.2em;
  color:rgba(255,100,100,.5);text-transform:uppercase;
  margin-bottom:8px;
}
.heading{
  font-weight:800;
  font-size:clamp(24px,7vw,36px);
  letter-spacing:-.03em;line-height:1;
  margin-bottom:10px;
}
.body-txt{
  font-size:14px;color:var(--sub);
  margin-bottom:28px;line-height:1.65;
}

/* ─── GRID ─── */
.grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
}
@media(min-width:480px){.grid{grid-template-columns:repeat(3,1fr);}}

.ccard{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:var(--r);
  display:flex;flex-direction:column;
  position:relative;overflow:hidden;
  transition:border-color .2s,transform .2s;
  will-change:transform;
}
.ccard:active{transform:scale(.98);}
.ccard.unlocked-card{border-color:rgba(227,28,46,.2);}
.ccard-new::after{
  content:'NEW';
  position:absolute;top:10px;right:0;
  background:var(--red);color:#fff;
  font-family:'JetBrains Mono',monospace;
  font-size:7px;letter-spacing:.1em;
  padding:3px 8px;border-radius:3px 0 0 3px;
}
.ccard-body{padding:14px 12px 10px;flex:1;}
.ccard-ico{
  width:36px;height:36px;border-radius:9px;
  background:rgba(227,28,46,.08);
  border:1px solid rgba(227,28,46,.12);
  display:flex;align-items:center;justify-content:center;
  font-size:17px;margin-bottom:9px;
}
.ccard-name{font-weight:800;font-size:13px;margin-bottom:2px;}
.ccard-desc{font-size:11px;color:var(--sub);margin-bottom:8px;line-height:1.4;}
.ccard-tags{display:flex;flex-wrap:wrap;gap:3px;}
.ctag{
  font-size:9px;padding:2px 6px;border-radius:4px;
  background:rgba(255,255,255,.04);
  border:1px solid rgba(255,255,255,.06);
  color:rgba(255,255,255,.3);
}
.ccard-foot{
  padding:10px 12px;
  border-top:1px solid rgba(255,255,255,.05);
}
.ccard-btn{
  width:100%;padding:11px 8px;
  border-radius:10px;border:none;cursor:pointer;
  font-family:'Outfit',sans-serif;font-weight:700;font-size:12px;
  display:flex;align-items:center;justify-content:center;gap:5px;
  transition:opacity .15s,transform .15s;
  touch-action:manipulation;
}
.ccard-btn:active{transform:scale(.97);}
.btn-locked{
  background:rgba(255,255,255,.04);
  color:var(--sub);
  border:1px solid rgba(255,255,255,.07);
}
.btn-unlocked{
  background:var(--red);color:#fff;
  box-shadow:0 2px 16px rgba(227,28,46,.25);
}
.btn-unlocked:active{opacity:.85;}

/* ─── BOTTOM SHEET ─── */
.overlay{
  position:fixed;inset:0;z-index:300;
  background:rgba(0,0,0,.78);
  backdrop-filter:blur(10px);
  -webkit-backdrop-filter:blur(10px);
  opacity:0;pointer-events:none;
  transition:opacity .25s;
  display:flex;align-items:flex-end;justify-content:center;
}
.overlay.on{opacity:1;pointer-events:all;}
.sheet{
  width:100%;max-width:520px;
  background:var(--card);
  border:1px solid rgba(255,255,255,.07);
  border-radius:22px 22px 0 0;
  padding:0 0 max(32px, env(safe-area-inset-bottom));
  transform:translateY(100%);
  transition:transform .35s cubic-bezier(.16,1,.3,1);
}
.overlay.on .sheet{transform:translateY(0);}
.sheet-pill{
  width:32px;height:3px;border-radius:2px;
  background:rgba(255,255,255,.1);
  margin:14px auto 0;
}
.sheet-top{
  display:flex;align-items:center;justify-content:space-between;
  padding:16px 18px 4px;
}
.sheet-title{font-weight:800;font-size:16px;letter-spacing:-.01em;}
.sheet-close{
  width:28px;height:28px;border-radius:50%;
  background:rgba(255,255,255,.06);border:none;
  color:var(--sub);font-size:16px;cursor:pointer;
  display:flex;align-items:center;justify-content:center;
  touch-action:manipulation;
  flex-shrink:0;
}
.sheet-close:active{background:rgba(255,255,255,.12);}
.sheet-sub{
  font-size:12px;color:var(--sub);
  padding:0 18px 14px;line-height:1.6;
}
.sheet-prog{
  height:2px;background:rgba(255,255,255,.06);
  margin:0 18px 16px;border-radius:1px;overflow:hidden;
}
.sheet-prog-fill{
  height:100%;width:0%;
  background:linear-gradient(90deg,#00cc88,#00ffaa);
  border-radius:1px;
  transition:width .45s cubic-bezier(.16,1,.3,1);
}
.sheet-body{padding:0 14px;}

.trow{
  display:flex;align-items:center;gap:11px;
  padding:12px 13px;border-radius:12px;
  background:var(--bg);
  border:1.5px solid rgba(255,255,255,.06);
  margin-bottom:8px;
  text-decoration:none;color:var(--txt);
  transition:border-color .2s,background .2s;
  touch-action:manipulation;
}
.trow.done{
  border-color:rgba(0,255,170,.28);
  background:rgba(0,255,170,.04);
}
.trow-ico{
  width:40px;height:40px;border-radius:11px;
  flex-shrink:0;
  display:flex;align-items:center;justify-content:center;
  font-size:18px;
}
.ico-tg{background:rgba(0,136,204,.1);border:1px solid rgba(0,136,204,.16);}
.ico-yt{background:rgba(255,0,0,.08);border:1px solid rgba(255,0,0,.14);}
.trow-info{flex:1;min-width:0;}
.trow-name{font-weight:700;font-size:13px;margin-bottom:1px;}
.trow-hint{font-size:11px;color:var(--sub);}
.trow-check{
  width:24px;height:24px;border-radius:50%;flex-shrink:0;
  border:1.5px solid rgba(255,255,255,.12);
  display:flex;align-items:center;justify-content:center;
  font-size:11px;font-weight:700;
  transition:all .2s;
}
.trow.done .trow-check{
  background:#00ffaa;border-color:#00ffaa;color:#000;
}

.vbtns{display:flex;flex-direction:column;gap:6px;margin:12px 0 10px;}
.vbtn{
  width:100%;padding:12px;border-radius:11px;border:none;
  font-family:'Outfit',sans-serif;font-weight:600;font-size:13px;
  display:flex;align-items:center;justify-content:center;gap:6px;
  cursor:pointer;touch-action:manipulation;
  transition:opacity .15s,transform .15s;
}
.vbtn:active{transform:scale(.97);}
.vbtn:disabled{opacity:.3;cursor:not-allowed;transform:none!important;}
.vbtn-tg{background:rgba(0,136,204,.12);color:#44aadd;border:1px solid rgba(0,136,204,.18);}
.vbtn-yt{background:rgba(255,0,0,.1);color:#ff5555;border:1px solid rgba(255,0,0,.15);}

.dl-btn{
  width:100%;padding:15px;border-radius:12px;border:none;
  font-family:'Outfit',sans-serif;font-weight:700;font-size:15px;
  display:flex;align-items:center;justify-content:center;gap:7px;
  cursor:pointer;touch-action:manipulation;
  background:rgba(255,255,255,.05);
  color:rgba(255,255,255,.2);
  border:1px solid rgba(255,255,255,.07);
  pointer-events:none;
  transition:all .28s;
}
.dl-btn.go{
  background:var(--red);color:#fff;
  pointer-events:all;
  box-shadow:0 4px 28px var(--red-glow);
  border-color:transparent;
}
.dl-btn.go:active{transform:scale(.97);box-shadow:0 2px 14px var(--red-glow);}

/* ─── PREMIUM ─── */
.prem{
  background:linear-gradient(145deg,#0d0d1e,#180e28);
  border:1px solid rgba(255,201,64,.15);
  border-radius:var(--r);padding:24px 18px;
  position:relative;overflow:hidden;
}
.prem::before{
  content:'';position:absolute;
  top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,rgba(255,201,64,.45),transparent);
}
.prem-hd{display:flex;align-items:center;gap:11px;margin-bottom:14px;}
.prem-ico{
  width:46px;height:46px;border-radius:12px;flex-shrink:0;
  background:rgba(255,201,64,.1);border:1px solid rgba(255,201,64,.18);
  display:flex;align-items:center;justify-content:center;font-size:21px;
}
.prem-ey{
  font-family:'JetBrains Mono',monospace;
  font-size:9px;letter-spacing:.17em;
  color:rgba(255,201,64,.5);text-transform:uppercase;margin-bottom:3px;
}
.prem-name{
  font-weight:900;font-size:19px;letter-spacing:-.02em;
  background:linear-gradient(135deg,var(--gold),var(--gold2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;
}
.prem-txt{font-size:13px;color:var(--sub);margin-bottom:16px;line-height:1.65;}
.prem-list{display:flex;flex-direction:column;gap:7px;margin-bottom:20px;}
.pli{
  display:flex;align-items:flex-start;gap:10px;
  font-size:13px;padding:9px 12px;
  border-radius:10px;
  background:rgba(255,201,64,.04);
  border:1px solid rgba(255,201,64,.07);
  line-height:1.45;
}
.pli::before{
  content:'';width:5px;height:5px;border-radius:50%;
  background:var(--gold);flex-shrink:0;margin-top:4px;
  box-shadow:0 0 7px var(--gold);
}
.prem-btn{
  display:flex;align-items:center;justify-content:center;gap:8px;
  width:100%;padding:15px;border-radius:12px;border:none;
  font-family:'Outfit',sans-serif;font-weight:700;font-size:15px;
  background:linear-gradient(135deg,var(--gold),var(--gold2));color:#000;
  text-decoration:none;cursor:pointer;
  transition:opacity .15s,transform .15s;
  touch-action:manipulation;
}
.prem-btn:active{opacity:.8;transform:scale(.98);}
.prem-note{
  font-size:11px;color:var(--sub);
  text-align:center;margin-top:8px;
}

/* ─── FOOTER ─── */
.footer{
  padding:44px 20px 40px;
  text-align:center;
  border-top:1px solid rgba(255,255,255,.04);
}
.footer-name{
  font-weight:900;font-size:17px;letter-spacing:-.02em;
  color:var(--txt);margin-bottom:16px;
}
.footer-name span{color:var(--sub);font-weight:400;font-size:12px;}
.footer-links{
  display:flex;gap:0;
  justify-content:center;flex-wrap:wrap;
  margin-bottom:18px;
}
.footer-links a{
  font-size:14px;color:var(--sub);text-decoration:none;
  padding:6px 14px;
  transition:color .2s;
}
.footer-links a:active{color:var(--txt);}
.footer-copy{font-size:11px;color:rgba(255,255,255,.12);}

/* ─── REVEAL ─── */
.rev{opacity:0;transform:translateY(16px);transition:opacity .5s,transform .5s;}
.rev.show{opacity:1;transform:none;}
.r1{transition-delay:.06s;}
.r2{transition-delay:.12s;}
.r3{transition-delay:.18s;}

/* ─── TOAST ─── */
.toast{
  position:fixed;
  bottom:calc(20px + env(safe-area-inset-bottom));
  left:50%;
  transform:translateX(-50%) translateY(50px);
  z-index:500;
  padding:10px 20px;border-radius:100px;
  font-family:'Outfit',sans-serif;
  font-weight:700;font-size:13px;
  white-space:nowrap;
  pointer-events:none;opacity:0;
  transition:transform .35s cubic-bezier(.16,1,.3,1),opacity .25s;
}
.toast.show{transform:translateX(-50%) translateY(0);opacity:1;}
.toast.green{background:#00ffaa;color:#000;}
.toast.orange{background:#ff9500;color:#000;}
.toast.dark{background:#1e1e2e;color:var(--txt);border:1px solid rgba(255,255,255,.1);}

@keyframes spin{to{transform:rotate(360deg);}}
.spin{display:inline-block;animation:spin .7s linear infinite;}
</style>
</head>
<body>

<div class="toast" id="toast"></div>

<!-- NAV -->
<nav class="nav">
  <a class="nav-brand" href="#">AIM PERFECT<sup>™</sup></a>
  <a class="nav-gold" href="#premium">✦ Premium</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>
  <p class="hero-tag">Red-Union · Config Hub</p>
  <h1 class="hero-h">
    <span class="solid">AIM</span>
    <span class="outline">PERFECT<span class="tm">™</span></span>
  </h1>
  <p class="hero-p"><b>Free &amp; Premium</b> CODM configs.<br>Better aim. Smoother feel.</p>
  <div class="hero-btns">
    <button class="btn-r" onclick="document.getElementById('configs').scrollIntoView({behavior:'smooth'})">Get Free Configs</button>
    <button class="btn-b" onclick="document.getElementById('premium').scrollIntoView({behavior:'smooth'})">✦ Premium</button>
  </div>
  <div class="hero-pills">
    <div class="pill"><span class="pill-n">6</span><span class="pill-l">Free Packs</span></div>
    <div class="pill"><span class="pill-n">29</span><span class="pill-l">Weapons</span></div>
    <div class="pill"><span class="pill-n">Free</span><span class="pill-l">Always</span></div>
    <div class="pill"><span class="pill-n">Pro</span><span class="pill-l">Premium</span></div>
  </div>
</section>

<div class="hr"></div>

<!-- CONFIGS -->
<section id="configs" style="background:var(--bg);">
<div class="sec">
  <p class="eyebrow rev">Free Configs</p>
  <h2 class="heading rev r1">Pick Your Pack</h2>
  <p class="body-txt rev r2">Each pack is free. Tap one, complete 2 quick tasks, and download that specific pack.</p>
  <div class="grid rev r3" id="cfg-grid">

    <div class="ccard" id="card-c1">
      <div class="ccard-body">
        <div class="ccard-ico">🎯</div>
        <div class="ccard-name">Config Pack 1</div>
        <div class="ccard-desc">Core aim &amp; recoil</div>
        <div class="ccard-tags">
          <span class="ctag">Aim</span><span class="ctag">Recoil</span><span class="ctag">ADS</span>
        </div>
      </div>
      <div class="ccard-foot">
        <button class="ccard-btn btn-locked" id="cbtn-c1"
          onclick="openSheet('c1')">🔒 Unlock</button>
      </div>
    </div>

    <div class="ccard" id="card-c2">
      <div class="ccard-body">
        <div class="ccard-ico">⚡</div>
        <div class="ccard-name">Config Pack 2</div>
        <div class="ccard-desc">Better tracking</div>
        <div class="ccard-tags">
          <span class="ctag">Aim</span><span class="ctag">Stability</span><span class="ctag">FPS</span>
        </div>
      </div>
      <div class="ccard-foot">
        <button class="ccard-btn btn-locked" id="cbtn-c2"
          onclick="openSheet('c2')">🔒 Unlock</button>
      </div>
    </div>

    <div class="ccard" id="card-c3">
      <div class="ccard-body">
        <div class="ccard-ico">🔥</div>
        <div class="ccard-name">Config Pack 3</div>
        <div class="ccard-desc">Spray &amp; hip fire</div>
        <div class="ccard-tags">
          <span class="ctag">Spray</span><span class="ctag">Hip Fire</span><span class="ctag">Scope</span>
        </div>
      </div>
      <div class="ccard-foot">
        <button class="ccard-btn btn-locked" id="cbtn-c3"
          onclick="openSheet('c3')">🔒 Unlock</button>
      </div>
    </div>

    <div class="ccard" id="card-c4">
      <div class="ccard-body">
        <div class="ccard-ico">💎</div>
        <div class="ccard-name">Config Pack 4</div>
        <div class="ccard-desc">Balanced all-round</div>
        <div class="ccard-tags">
          <span class="ctag">Aim</span><span class="ctag">Recoil</span><span class="ctag">Sensitivity</span>
        </div>
      </div>
      <div class="ccard-foot">
        <button class="ccard-btn btn-locked" id="cbtn-c4"
          onclick="openSheet('c4')">🔒 Unlock</button>
      </div>
    </div>

    <div class="ccard" id="card-c5">
      <div class="ccard-body">
        <div class="ccard-ico">🎮</div>
        <div class="ccard-name">Config Pack 5</div>
        <div class="ccard-desc">Refined engine</div>
        <div class="ccard-tags">
          <span class="ctag">Aim</span><span class="ctag">ADS Speed</span><span class="ctag">FPS</span>
        </div>
      </div>
      <div class="ccard-foot">
        <button class="ccard-btn btn-locked" id="cbtn-c5"
          onclick="openSheet('c5')">🔒 Unlock</button>
      </div>
    </div>

    <div class="ccard ccard-new" id="card-c6">
      <div class="ccard-body">
        <div class="ccard-ico">🚀</div>
        <div class="ccard-name">Config Pack 6</div>
        <div class="ccard-desc">Latest &amp; best yet</div>
        <div class="ccard-tags">
          <span class="ctag">All Features</span><span class="ctag">29 Guns</span>
        </div>
      </div>
      <div class="ccard-foot">
        <button class="ccard-btn btn-locked" id="cbtn-c6"
          onclick="openSheet('c6')">🔒 Unlock</button>
      </div>
    </div>

  </div>
</div>
</section>

<div class="hr"></div>

<!-- PREMIUM -->
<section id="premium" style="background:#0a0a14;">
<div class="sec">
  <p class="eyebrow rev">Premium</p>
  <h2 class="heading rev r1" style="background:linear-gradient(135deg,var(--gold),var(--gold2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">Premium Configs ✦</h2>
  <div class="rev r2">
  <div class="prem">
    <div class="prem-hd">
      <div class="prem-ico">👑</div>
      <div>
        <div class="prem-ey">Exclusive</div>
        <div class="prem-name">ULTRA CONFIG PACK</div>
      </div>
    </div>
    <p class="prem-txt">The most advanced version — privately sent to you on Telegram. More refined than any free pack.</p>
    <div class="prem-list">
      <div class="pli">More refined aim smoothness than any free version</div>
      <div class="pli">Individual configs for all 29 weapons</div>
      <div class="pli">Multiple strength levels to match your style</div>
      <div class="pli">Private updates before public release</div>
      <div class="pli">Direct support from Red-Union</div>
    </div>
    <a href="https://t.me/Redunion1" target="_blank" rel="noopener" class="prem-btn">
      💬 DM @Redunion1 on Telegram
    </a>
    <p class="prem-note">Ask about pricing &amp; availability</p>
  </div>
  </div>
</div>
</section>

<div class="hr"></div>

<!-- FOOTER -->
<footer class="footer">
  <div class="footer-name">AIM PERFECT™ <span>by Red-Union</span></div>
  <div class="footer-links">
    <a href="https://t.me/+re8tFFBQgY4wZTc1" target="_blank" rel="noopener">📢 Telegram</a>
    <a href="https://youtube.com/@redunionagency?si=YoM6feKc2Y1Vu3ow" target="_blank" rel="noopener">▶️ YouTube</a>
    <a href="https://t.me/Redunion1" target="_blank" rel="noopener">💬 Premium</a>
  </div>
  <p class="footer-copy">© 2026 Red-Union</p>
</footer>

<!-- BOTTOM SHEET -->
<div class="overlay" id="overlay">
  <div class="sheet">
    <div class="sheet-pill"></div>
    <div class="sheet-top">
      <div class="sheet-title" id="sheet-title">Unlock Config</div>
      <button class="sheet-close" onclick="closeSheet()">✕</button>
    </div>
    <p class="sheet-sub">Complete both tasks below to unlock this pack. Each config needs its own unlock.</p>
    <div class="sheet-prog"><div class="sheet-prog-fill" id="spfill"></div></div>
    <div class="sheet-body">
      <a id="trow-tg" class="trow" href="https://t.me/+re8tFFBQgY4wZTc1" target="_blank" rel="noopener" onclick="didOpen('tg')">
        <div class="trow-ico ico-tg">✈️</div>
        <div class="trow-info">
          <div class="trow-name">Join Telegram Channel</div>
          <div class="trow-hint" id="hint-tg">Tap to open, then verify below</div>
        </div>
        <div class="trow-check" id="chk-tg"></div>
      </a>
      <a id="trow-yt" class="trow" href="https://youtube.com/@redunionagency?si=YoM6feKc2Y1Vu3ow" target="_blank" rel="noopener" onclick="didOpen('yt')">
        <div class="trow-ico ico-yt">▶️</div>
        <div class="trow-info">
          <div class="trow-name">Subscribe on YouTube</div>
          <div class="trow-hint" id="hint-yt">Tap to open, then verify below</div>
        </div>
        <div class="trow-check" id="chk-yt"></div>
      </a>
      <div class="vbtns">
        <button class="vbtn vbtn-tg" id="vbtn-tg" onclick="verify('tg')" disabled>✓ I joined Telegram</button>
        <button class="vbtn vbtn-yt" id="vbtn-yt" onclick="verify('yt')" disabled>✓ I subscribed on YouTube</button>
      </div>
      <button class="dl-btn" id="dl-btn" onclick="doDownload()">🔒 Complete tasks to unlock</button>
    </div>
  </div>
</div>

<script>
var CONFIGS = {
  c1:{name:"Config Pack 1",url:"https://www.mediafire.com/file/68eb9n9m5u7s2j3/Aim_Perfecr_Free_Config_v10.zip/file"},
  c2:{name:"Config Pack 2",url:"https://www.mediafire.com/file/mc1ftlhej8km5t2/Aim_Perfecr_Free_Config_v11.zip/file"},
  c3:{name:"Config Pack 3",url:"https://www.mediafire.com/file/d606krz5ysfs1l3/Aim_Perfecr_Free_Config_v12.zip/file"},
  c4:{name:"Config Pack 4",url:"https://www.mediafire.com/file/opekyyexrlbrw8t/Aim_Perfecr_Free_Config_v13.zip/file"},
  c5:{name:"Config Pack 5",url:"https://www.mediafire.com/file/as8y1fv80xjhfp3/Aim_Perfecr_Free_Config_v14.zip/file"},
  c6:{name:"Config Pack 6",url:"https://www.mediafire.com/file/5unn5uwns7o9088/Aim_Perfecr_Free_Config_v15.zip/file"}
};
var cur = "";

function gs(k){try{return JSON.parse(localStorage.getItem("ap_"+k)||"{}");}catch(e){return {};}}
function ss(k,v){localStorage.setItem("ap_"+k,JSON.stringify(v));}

function openSheet(key){
  cur = key;
  document.getElementById("sheet-title").textContent = CONFIGS[key].name;
  render();
  document.getElementById("overlay").classList.add("on");
  document.body.style.overflow = "hidden";
}
function closeSheet(){
  document.getElementById("overlay").classList.remove("on");
  document.body.style.overflow = "";
}
document.getElementById("overlay").addEventListener("click",function(e){if(e.target===this)closeSheet();});

function render(){
  var s = gs(cur);
  var tg = !!s.tgDone, yt = !!s.ytDone;

  // TG row
  var rTg = document.getElementById("trow-tg");
  var cTg = document.getElementById("chk-tg");
  var vTg = document.getElementById("vbtn-tg");
  if(tg){
    rTg.classList.add("done"); cTg.textContent="✓";
    vTg.disabled=true; vTg.textContent="✓ Telegram verified"; vTg.style.opacity=".3";
    document.getElementById("hint-tg").textContent="Verified ✓";
  } else {
    rTg.classList.remove("done"); cTg.textContent="";
    var op=!!s.tgOpened; vTg.disabled=!op; vTg.style.opacity=op?"1":".3";
    vTg.textContent="✓ I joined Telegram";
    document.getElementById("hint-tg").textContent="Tap to open, then verify below";
  }

  // YT row
  var rYt = document.getElementById("trow-yt");
  var cYt = document.getElementById("chk-yt");
  var vYt = document.getElementById("vbtn-yt");
  if(yt){
    rYt.classList.add("done"); cYt.textContent="✓";
    vYt.disabled=true; vYt.textContent="✓ YouTube verified"; vYt.style.opacity=".3";
    document.getElementById("hint-yt").textContent="Verified ✓";
  } else {
    rYt.classList.remove("done"); cYt.textContent="";
    var oy=!!s.ytOpened; vYt.disabled=!oy; vYt.style.opacity=oy?"1":".3";
    vYt.textContent="✓ I subscribed on YouTube";
    document.getElementById("hint-yt").textContent="Tap to open, then verify below";
  }

  // Progress
  var done=(tg?1:0)+(yt?1:0);
  document.getElementById("spfill").style.width=(done*50)+"%";

  // DL button
  var db = document.getElementById("dl-btn");
  if(tg&&yt){
    db.className="dl-btn go";
    db.textContent="⬇  Download "+CONFIGS[cur].name;
  } else {
    db.className="dl-btn";
    db.textContent="🔒 Complete tasks to unlock";
  }

  // Update card button
  var btn=document.getElementById("cbtn-"+cur);
  if(btn){
    if(tg&&yt){btn.className="ccard-btn btn-unlocked";btn.textContent="⬇ Download";}
    else{btn.className="ccard-btn btn-locked";btn.textContent="🔒 Unlock";}
  }
}

function didOpen(task){
  var s=gs(cur); s[task+"Opened"]=true; ss(cur,s);
  setTimeout(function(){render();toast("Now tap verify below","dark");},800);
}

function verify(task){
  var s=gs(cur);
  if(!s[task+"Opened"]){
    toast("Open the "+(task==="tg"?"Telegram channel":"YouTube channel")+" first","orange");
    return;
  }
  if(s[task+"Done"])return;
  var btn=document.getElementById("vbtn-"+task);
  btn.disabled=true;
  btn.innerHTML='<span class="spin">⟳</span> Checking…';
  setTimeout(function(){
    s[task+"Done"]=true; ss(cur,s);
    render();
    toast((task==="tg"?"Telegram":"YouTube")+" verified ✓","green");
  },1500);
}

function doDownload(){
  var s=gs(cur);
  if(!s.tgDone||!s.ytDone)return;
  window.open(CONFIGS[cur].url,"_blank");
  closeSheet();
  toast("Opening download…","green");
}

// Restore unlocked cards on load
(function(){
  Object.keys(CONFIGS).forEach(function(k){
    var s=gs(k);
    if(s.tgDone&&s.ytDone){
      var btn=document.getElementById("cbtn-"+k);
      if(btn){btn.className="ccard-btn btn-unlocked";btn.textContent="⬇ Download";}
      var card=document.getElementById("card-"+k);
      if(card)card.classList.add("unlocked-card");
    }
  });
})();

// Scroll reveal
var els=document.querySelectorAll(".rev");
var io=new IntersectionObserver(function(entries){
  entries.forEach(function(e){if(e.isIntersecting){e.target.classList.add("show");io.unobserve(e.target);}});
},{threshold:0.07});
els.forEach(function(el){io.observe(el);});

// Stagger grid
var g=document.getElementById("cfg-grid");
if(g)Array.from(g.children).forEach(function(c,i){c.style.transitionDelay=(i*0.06)+"s";});

// Toast
function toast(msg,type){
  var t=document.getElementById("toast");
  t.textContent=msg;t.className="toast show "+(type||"dark");
  clearTimeout(t._t);
  t._t=setTimeout(function(){t.className="toast";},2500);
}

// Reduce motion
if(window.matchMedia("(prefers-reduced-motion:reduce)").matches){
  document.querySelectorAll(".hero-glow,.hero-glow2").forEach(function(el){el.style.animation="none";});
}
</script>
</body>
</html>
