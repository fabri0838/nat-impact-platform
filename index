<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NAT Impact — Plataforma de Trazabilidad de Impacto</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Young+Serif&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&family=Roboto+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
/* ── TOKENS NAT ──────────────────────────────────────────────────── */
:root {
  --dark:    #162A0C;
  --green:   #2E7D2E;
  --bright:  #56B840;
  --mid:     #3D9B3A;
  --light:   #A8D98C;
  --pale:    #D9EDD0;
  --cream:   #F4EDD8;
  --cream2:  #EDE3CA;
  --kraft:   #C4965A;
  --kraft-lt:#EDD9B8;
  --white:   #FDFCF8;
  --text:    #162A0C;
  --text2:   #3D5A30;
  --text3:   #7A9B6A;
  --blue:    #1565C0;
  --blue-lt: #E3F2FD;
  --r:12px; --rlg:20px;
  --s1: 0 1px 4px rgba(22,42,12,.06), 0 4px 16px rgba(22,42,12,.04);
  --s2: 0 4px 12px rgba(22,42,12,.08), 0 12px 32px rgba(22,42,12,.06);
  --s3: 0 8px 24px rgba(22,42,12,.10), 0 24px 48px rgba(22,42,12,.08);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{font-size:14px;scroll-behavior:smooth}
body{font-family:'Plus Jakarta Sans',sans-serif;background:var(--cream);color:var(--text);min-height:100vh}
::-webkit-scrollbar{width:5px}
::-webkit-scrollbar-track{background:var(--cream2)}
::-webkit-scrollbar-thumb{background:var(--light);border-radius:4px}

/* ── NAV ──────────────────────────────────────────────────────────── */
.nav{background:var(--dark);padding:0 40px;height:58px;display:flex;
  align-items:center;justify-content:space-between;position:sticky;top:0;z-index:100}
.nav-brand{display:flex;align-items:center;gap:12px}
.nav-logo{width:34px;height:34px;border-radius:8px;background:var(--bright);
  display:flex;align-items:center;justify-content:center;font-size:18px}
.nav-name{font-family:'Young Serif',serif;font-size:18px;color:var(--white);letter-spacing:-.3px}
.nav-sub{font-size:10px;color:var(--light);letter-spacing:2px;text-transform:uppercase;
  font-family:'Roboto Mono',monospace;margin-top:1px}
.nav-links{display:flex;gap:4px}
.nav-link{padding:7px 14px;border-radius:8px;font-size:12.5px;font-weight:500;
  color:rgba(253,252,248,.65);cursor:pointer;transition:all .18s;text-decoration:none}
.nav-link:hover{background:rgba(255,255,255,.08);color:var(--white)}
.nav-link.active{background:var(--green);color:var(--white)}
.nav-right{display:flex;align-items:center;gap:10px}
.nav-badge{display:flex;align-items:center;gap:6px;padding:5px 12px;border-radius:20px;
  border:1px solid rgba(168,217,140,.3);font-size:11px;color:var(--light);
  font-family:'Roboto Mono',monospace}
.pulse{width:6px;height:6px;border-radius:50%;background:var(--bright);
  animation:pulse 2s ease infinite}
@keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(86,184,64,.5)}60%{box-shadow:0 0 0 7px rgba(86,184,64,0)}}
.nav-btn{background:var(--bright);color:var(--dark);border:none;padding:8px 18px;border-radius:8px;
  font-size:12px;font-weight:700;cursor:pointer;font-family:'Plus Jakarta Sans',sans-serif;transition:all .18s}
.nav-btn:hover{background:var(--light)}

/* ── HERO ──────────────────────────────────────────────────────────── */
.hero{background:var(--dark);padding:52px 40px 48px;position:relative;overflow:hidden}
.hero::before{content:'';position:absolute;right:-40px;top:-40px;width:420px;height:420px;
  background:radial-gradient(circle,rgba(86,184,64,.06) 0%,transparent 70%);border-radius:50%}
.hero-grid{display:grid;grid-template-columns:1fr auto;gap:48px;align-items:end;position:relative;z-index:1}
.hero-eyebrow{display:flex;align-items:center;gap:10px;margin-bottom:18px}
.hero-eyebrow-dot{width:8px;height:8px;border-radius:50%;background:var(--bright)}
.hero-eyebrow-txt{font-size:11px;color:var(--light);letter-spacing:2.5px;text-transform:uppercase;
  font-family:'Roboto Mono',monospace}
.hero-title{font-family:'Young Serif',serif;font-size:40px;line-height:1.1;letter-spacing:-.8px;
  color:var(--white);margin-bottom:14px}
.hero-title em{color:var(--bright);font-style:italic}
.hero-desc{font-size:14px;color:rgba(253,252,248,.65);max-width:520px;line-height:1.7;margin-bottom:24px}
.chips{display:flex;gap:8px;flex-wrap:wrap}
.chip{display:inline-flex;align-items:center;gap:5px;padding:5px 12px;border-radius:20px;
  font-size:11px;font-weight:600}
.chip-g{background:rgba(86,184,64,.15);color:var(--bright);border:1px solid rgba(86,184,64,.25)}
.chip-k{background:rgba(196,150,90,.15);color:#E8B87A;border:1px solid rgba(196,150,90,.25)}
.chip-b{background:rgba(21,101,192,.15);color:#90CAF9;border:1px solid rgba(21,101,192,.3)}
.hero-stats{display:flex;flex-direction:column;gap:18px;align-items:flex-end}
.hstat-val{font-family:'Roboto Mono',monospace;font-size:26px;font-weight:500;
  color:var(--kraft);text-align:right;line-height:1;margin-bottom:4px}
.hstat-lbl{font-size:11px;color:rgba(253,252,248,.4);text-align:right}
.hdiv{width:1px;height:40px;background:rgba(255,255,255,.1);margin:auto}

/* ── PAGE ──────────────────────────────────────────────────────────── */
.page{max-width:1160px;margin:0 auto;padding:32px 40px 48px}
.sec-hd{display:flex;align-items:baseline;justify-content:space-between;margin-bottom:16px}
.sec-title{font-family:'Young Serif',serif;font-size:19px;letter-spacing:-.2px}
.sec-sub{font-size:11px;color:var(--text3);font-family:'Roboto Mono',monospace}

/* ── IMPACT CARDS ──────────────────────────────────────────────────── */
.ic-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-bottom:32px}
.ic{background:var(--white);border-radius:var(--r);padding:20px 18px 16px;
  position:relative;overflow:hidden;box-shadow:var(--s1);
  border:1px solid rgba(22,42,12,.06);transition:box-shadow .2s,transform .2s;cursor:default}
.ic:hover{box-shadow:var(--s2);transform:translateY(-2px)}
.ic::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;border-radius:3px 3px 0 0}
.ic-g::before{background:linear-gradient(90deg,var(--green),var(--bright))}
.ic-k::before{background:linear-gradient(90deg,var(--kraft),#E8C070)}
.ic-b::before{background:linear-gradient(90deg,#1565C0,#64B5F6)}
.ic-t::before{background:linear-gradient(90deg,#7B1FA2,#CE93D8)}
.ic::after{content:'🌿';position:absolute;bottom:-8px;right:-4px;font-size:52px;
  opacity:.04;pointer-events:none;filter:grayscale(1)}
.ic-icon{font-size:22px;margin-bottom:12px;display:block;line-height:1}
.ic-val{font-family:'Roboto Mono',monospace;font-size:30px;font-weight:500;line-height:1;margin-bottom:2px}
.ic-g .ic-val{color:var(--green)} .ic-k .ic-val{color:var(--kraft)}
.ic-b .ic-val{color:#1565C0}     .ic-t .ic-val{color:#7B1FA2}
.ic-unit{font-size:12px;color:var(--text2);font-weight:500;margin-bottom:7px}
.ic-desc{font-size:11px;color:var(--text3);line-height:1.55}
.ic-badge{display:inline-flex;align-items:center;gap:4px;margin-top:11px;
  font-size:10.5px;font-weight:600;padding:3px 9px;border-radius:8px}
.ib-g{background:var(--pale);color:var(--green)}
.ib-k{background:var(--kraft-lt);color:#9B6B2A}
.ib-b{background:var(--blue-lt);color:var(--blue)}

/* ── MAP BANNER ────────────────────────────────────────────────────── */
.map-banner{background:var(--white);border-radius:var(--rlg);padding:30px 36px;
  box-shadow:var(--s1);border:1px solid rgba(22,42,12,.06);margin-bottom:30px;
  display:grid;grid-template-columns:1fr auto;gap:28px;align-items:center}
.mb-label{font-size:10px;letter-spacing:2px;text-transform:uppercase;color:var(--text3);
  font-family:'Roboto Mono',monospace;margin-bottom:10px;display:flex;align-items:center;gap:8px}
.mb-label::before{content:'';width:16px;height:1px;background:var(--text3)}
.mb-title{font-family:'Young Serif',serif;font-size:24px;color:var(--dark);
  line-height:1.2;margin-bottom:10px;letter-spacing:-.4px}
.mb-desc{font-size:13px;color:var(--text2);line-height:1.6;max-width:480px}
.mb-facts{display:flex;gap:28px;margin-top:18px;flex-wrap:wrap}
.mf-val{font-family:'Roboto Mono',monospace;font-size:20px;font-weight:500;
  color:var(--green);line-height:1;margin-bottom:3px}
.mf-lbl{font-size:11px;color:var(--text3)}

/* ── PANEL BASE ────────────────────────────────────────────────────── */
.panel{background:var(--white);border-radius:var(--r);padding:20px;
  box-shadow:var(--s1);border:1px solid rgba(22,42,12,.06)}
.p-title{font-family:'Young Serif',serif;font-size:15px;color:var(--dark);
  letter-spacing:-.2px;margin-bottom:3px}
.p-sub{font-size:11px;color:var(--text3);margin-bottom:14px}
.p-tag{display:inline-block;font-size:10px;font-weight:600;
  background:var(--pale);color:var(--green);padding:2px 8px;border-radius:6px;
  margin-top:3px;font-family:'Roboto Mono',monospace}

/* ── CHARTS ROW ────────────────────────────────────────────────────── */
.charts-row{display:grid;grid-template-columns:1.55fr 1fr;gap:14px;margin-bottom:28px}
.hbar-list{display:flex;flex-direction:column;gap:11px}
.hbar-row{display:flex;flex-direction:column;gap:4px}
.hbar-meta{display:flex;justify-content:space-between;align-items:baseline}
.hbar-lbl{font-size:12px;color:var(--text2);font-weight:500}
.hbar-val{font-family:'Roboto Mono',monospace;font-size:12px;font-weight:500}
.hb-g .hbar-val{color:var(--green)} .hb-k .hbar-val{color:var(--kraft)}
.hbar-track{height:8px;background:rgba(22,42,12,.06);border-radius:6px;overflow:hidden}
.hbar-fill{height:100%;border-radius:6px;transition:width 1.4s cubic-bezier(.4,0,.2,1)}
.hb-g .hbar-fill{background:linear-gradient(90deg,var(--green),var(--bright))}
.hb-k .hbar-fill{background:linear-gradient(90deg,var(--kraft),#E8C070)}

/* ODS */
.ods-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.ods-card{border-radius:10px;padding:11px;display:flex;gap:9px;
  align-items:flex-start;border:1px solid}
.ods-num{font-family:'Young Serif',serif;font-size:24px;line-height:1;flex-shrink:0;width:30px}
.ods-name{font-size:10.5px;font-weight:700;text-transform:uppercase;letter-spacing:.3px;line-height:1.3}
.ods-tag{font-size:9.5px;margin-top:2px;font-family:'Roboto Mono',monospace;opacity:.8}
.ods-8{background:rgba(255,182,50,.07);border-color:rgba(255,182,50,.2)}
.ods-8 .ods-num,.ods-8 .ods-name{color:#B08020}
.ods-13{background:var(--pale);border-color:rgba(61,155,58,.2)}
.ods-13 .ods-num,.ods-13 .ods-name{color:var(--green)}
.ods-15{background:rgba(22,42,12,.04);border-color:rgba(22,42,12,.1)}
.ods-15 .ods-num,.ods-15 .ods-name{color:var(--dark)}
.ods-12{background:rgba(196,150,90,.08);border-color:rgba(196,150,90,.2)}
.ods-12 .ods-num,.ods-12 .ods-name{color:var(--kraft)}

/* ── BOTTOM 3-COL ──────────────────────────────────────────────────── */
.bot-row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:28px}

/* Timeline */
.tl{display:flex;flex-direction:column}
.tl-item{display:flex;gap:11px;padding-bottom:14px;position:relative}
.tl-item:not(:last-child)::after{content:'';position:absolute;left:12px;top:26px;
  width:1px;bottom:0;background:rgba(22,42,12,.1)}
.tl-dot{width:25px;height:25px;border-radius:50%;display:flex;align-items:center;
  justify-content:center;flex-shrink:0}
.tl-done .tl-dot{background:var(--pale);border:1.5px solid var(--green)}
.tl-now .tl-dot{background:var(--pale);border:1.5px solid var(--bright);
  box-shadow:0 0 0 5px rgba(86,184,64,.12)}
.tl-next .tl-dot{background:rgba(22,42,12,.04);border:1.5px solid rgba(22,42,12,.15)}
.tl-pip{width:9px;height:9px;border-radius:50%}
.tl-done .tl-pip{background:var(--green)}
.tl-now .tl-pip{background:var(--bright);animation:blink 2s ease infinite}
.tl-next .tl-pip{background:rgba(22,42,12,.2)}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.4}}
.tl-body{flex:1;padding-top:2px}
.tl-date{font-family:'Roboto Mono',monospace;font-size:10px;color:var(--text3);margin-bottom:2px}
.tl-t{font-size:12.5px;font-weight:600;color:var(--dark);margin-bottom:2px;line-height:1.35}
.tl-d{font-size:11.5px;color:var(--text2);line-height:1.45}
.tl-tag{display:inline-flex;align-items:center;gap:3px;margin-top:5px;font-size:10px;
  font-weight:600;padding:2px 8px;border-radius:6px;font-family:'Roboto Mono',monospace}
.tt-d{background:var(--pale);color:var(--green)}
.tt-n{background:var(--kraft-lt);color:#9B6B2A}
.tt-f{background:rgba(22,42,12,.05);color:var(--text3)}

/* Certs */
.cert-list{display:flex;flex-direction:column;gap:7px}
.cert-item{display:flex;align-items:center;gap:9px;padding:9px 11px;border-radius:9px;
  background:rgba(22,42,12,.03);border:1px solid rgba(22,42,12,.06);transition:background .15s}
.cert-item:hover{background:var(--pale)}
.cert-name{font-size:12px;font-weight:600;color:var(--dark)}
.cert-org{font-size:10px;color:var(--text3);font-family:'Roboto Mono',monospace}
.cert-badge{font-size:9.5px;font-weight:700;padding:2px 8px;border-radius:7px;
  margin-left:auto;white-space:nowrap;font-family:'Roboto Mono',monospace}
.cb-ok{background:var(--pale);color:var(--green);border:1px solid rgba(61,155,58,.2)}
.cb-proc{background:var(--kraft-lt);color:#9B6B2A;border:1px solid rgba(196,150,90,.3)}
.cb-new{background:var(--blue-lt);color:var(--blue);border:1px solid rgba(21,101,192,.2)}

/* ── INSETTING PANEL (replaces carbon credits) ─────────────────────── */
.insetting-panel{background:var(--dark);border-radius:var(--r);padding:22px;color:var(--white);
  display:flex;flex-direction:column;gap:0}
.ins-label{font-size:10px;letter-spacing:2px;text-transform:uppercase;color:var(--light);
  font-family:'Roboto Mono',monospace;margin-bottom:6px}
.ins-title{font-family:'Young Serif',serif;font-size:16px;color:var(--white);margin-bottom:14px}
.ins-explain{font-size:12px;color:rgba(253,252,248,.65);line-height:1.6;margin-bottom:16px;
  padding:12px;background:rgba(255,255,255,.05);border-radius:8px;
  border-left:3px solid var(--bright)}

/* KPI-linked loan progress */
.loan-box{background:rgba(86,184,64,.08);border:1px solid rgba(86,184,64,.25);
  border-radius:10px;padding:14px;margin-bottom:12px}
.loan-label{font-size:10px;color:var(--light);font-family:'Roboto Mono',monospace;
  letter-spacing:1px;margin-bottom:6px;text-transform:uppercase}
.loan-val{font-family:'Roboto Mono',monospace;font-size:26px;font-weight:500;
  color:var(--bright);line-height:1;margin-bottom:3px}
.loan-sub{font-size:10px;color:rgba(253,252,248,.45);font-family:'Roboto Mono',monospace;
  margin-bottom:10px}
.loan-bar-track{height:6px;background:rgba(255,255,255,.1);border-radius:4px;overflow:hidden}
.loan-bar-fill{height:100%;background:linear-gradient(90deg,var(--green),var(--bright));
  border-radius:4px;width:0%;transition:width 2s cubic-bezier(.4,0,.2,1)}
.loan-bar-meta{display:flex;justify-content:space-between;margin-top:4px;
  font-size:9px;font-family:'Roboto Mono',monospace;color:rgba(253,252,248,.4)}

/* CO2 insetting metrics */
.co2-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:12px}
.co2-item{background:rgba(255,255,255,.05);border-radius:8px;padding:10px}
.co2-val{font-family:'Roboto Mono',monospace;font-size:18px;font-weight:500;
  color:var(--bright);line-height:1;margin-bottom:3px}
.co2-lbl{font-size:9.5px;color:rgba(253,252,248,.5)}

/* ESG download */
.esg-cta{margin-top:12px;padding:12px;background:rgba(255,255,255,.06);
  border-radius:10px;border:1px solid rgba(255,255,255,.1);
  display:flex;align-items:center;gap:10px}
.esg-ico{font-size:20px;flex-shrink:0}
.esg-name{font-size:12.5px;font-weight:600;color:var(--white)}
.esg-desc{font-size:10px;color:rgba(253,252,248,.45);font-family:'Roboto Mono',monospace}
.esg-btn{background:var(--bright);color:var(--dark);border:none;padding:7px 13px;
  border-radius:7px;font-size:11.5px;font-weight:700;cursor:pointer;
  font-family:'Plus Jakarta Sans',sans-serif;flex-shrink:0;transition:all .18s}
.esg-btn:hover{background:var(--light)}

/* ── FINANCIAL KPIS ────────────────────────────────────────────────── */
.fin-row{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-bottom:28px}
.fin-card{background:var(--white);border-radius:var(--r);padding:18px 18px 16px;
  box-shadow:var(--s1);border:1px solid rgba(22,42,12,.06);text-align:center;
  position:relative;overflow:hidden}
.fin-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;
  border-radius:3px 3px 0 0;background:linear-gradient(90deg,var(--green),var(--bright))}
.fin-label{font-size:10px;color:var(--text3);letter-spacing:1.5px;text-transform:uppercase;
  font-family:'Roboto Mono',monospace;margin-bottom:6px}
.fin-val{font-family:'Roboto Mono',monospace;font-size:32px;font-weight:600;
  color:var(--dark);line-height:1;margin-bottom:4px}
.fin-val span{font-size:16px;color:var(--green)}
.fin-sub{font-size:11px;color:var(--text3);line-height:1.5}
.fin-badge{display:inline-block;font-size:10px;font-weight:600;margin-top:8px;
  padding:3px 10px;border-radius:8px;background:var(--pale);color:var(--green);
  font-family:'Roboto Mono',monospace}

/* ── TICKER ────────────────────────────────────────────────────────── */
.ticker{background:var(--dark);padding:9px 40px;display:flex;
  align-items:center;gap:14px;overflow:hidden}
.tk-lbl{font-family:'Roboto Mono',monospace;font-size:10px;color:var(--bright);
  font-weight:700;white-space:nowrap;letter-spacing:1px}
.tk-scroll{flex:1;overflow:hidden}
.tk-track{display:flex;gap:26px;animation:scroll 32s linear infinite}
.tk-item{display:flex;gap:6px;white-space:nowrap;font-family:'Roboto Mono',monospace;font-size:10.5px}
.tk-k{color:rgba(253,252,248,.4)} .tk-v{color:var(--light);font-weight:500}
@keyframes scroll{from{transform:translateX(0)}to{transform:translateX(-50%)}}

/* ── ANIMATIONS ────────────────────────────────────────────────────── */
@keyframes fu{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}
.fu{animation:fu .5s ease forwards}
.d1{animation-delay:.05s;opacity:0} .d2{animation-delay:.1s;opacity:0}
.d3{animation-delay:.18s;opacity:0} .d4{animation-delay:.26s;opacity:0}
.d5{animation-delay:.34s;opacity:0} .d6{animation-delay:.42s;opacity:0}

/* ── RESPONSIVE ────────────────────────────────────────────────────── */
@media(max-width:1100px){
  .ic-grid{grid-template-columns:repeat(2,1fr)}
  .charts-row,.bot-row,.fin-row{grid-template-columns:1fr}
  .map-banner{grid-template-columns:1fr}
  .hero-grid{grid-template-columns:1fr}
  .nav-links{display:none}
  .page{padding:24px 20px}
  .nav,.ticker{padding-left:20px;padding-right:20px}
}
</style>
</head>
<body>

<!-- NAV -->
<nav class="nav">
  <div class="nav-brand">
    <div class="nav-logo">🌿</div>
    <div>
      <div class="nav-name">NAT Impact</div>
      <div class="nav-sub">Plataforma de Trazabilidad</div>
    </div>
  </div>
  <div class="nav-links">
    <a class="nav-link active">Mi Impacto</a>
    <a class="nav-link">Trazabilidad</a>
    <a class="nav-link">Insetting CO₂</a>
    <a class="nav-link">Reportes ESG</a>
    <a class="nav-link">Yungas Live</a>
  </div>
  <div class="nav-right">
    <div class="nav-badge"><div class="pulse"></div>Arcor S.A. · Contrato activo</div>
    <button class="nav-btn" onclick="alert('📊 Generando reporte ESG — Primer semestre 2026.\n\nContenido:\n• Huella de carbono verificada SCS (0,18 kg CO₂/u)\n• Cadena de custodia FSC\n• Árboles no talados certificados\n• Empleo sostenido en Jujuy\n• Reducción emisiones Alcance 3 para su reporte CSRD/GRI\n• Formato compatible con reportes de sostenibilidad corporativa')">⬇ Descargar Reporte ESG</button>
  </div>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="hero-grid">
    <div class="fu d1">
      <div class="hero-eyebrow">
        <div class="hero-eyebrow-dot"></div>
        <div class="hero-eyebrow-txt">Impacto verificado · Período activo · Jun 2026</div>
      </div>
      <h1 class="hero-title">Cada hoja que eligieron<br><em>cambió algo real</em></h1>
      <p class="hero-desc">Desde enero de 2026, cada compra de papel NAT generó impacto verificado sobre el territorio de Jujuy y las Yungas. Aquí, en tiempo real, lo que ocurrió en el mundo gracias a su decisión de compra.</p>
      <div class="chips">
        <span class="chip chip-g">✓ ISO 14001</span>
        <span class="chip chip-g">✓ FSC Cadena de Custodia</span>
        <span class="chip chip-k">✓ Sello Producto Yungas</span>
        <span class="chip chip-b">✓ SCS CO₂ Verificado</span>
      </div>
    </div>
    <div class="hero-stats fu d2">
      <div><div class="hstat-val">1.240 kg</div><div class="hstat-lbl">papel NAT comprado · Ene–May 2026</div></div>
      <div class="hdiv"></div>
      <div><div class="hstat-val">AA+(arg)</div><div class="hstat-lbl">calificación FIX SCR 2025</div></div>
      <div class="hdiv"></div>
      <div><div class="hstat-val">7 meses</div><div class="hstat-lbl">restantes en contrato vigente</div></div>
    </div>
  </div>
</div>

<!-- PAGE -->
<div class="page">

  <!-- IMPACT CARDS -->
  <div class="sec-hd fu d2">
    <div class="sec-title">Su impacto generado</div>
    <div class="sec-sub">Actualizado · 07 Jun 2026 · 09:14 hs</div>
  </div>
  <div class="ic-grid">
    <div class="ic ic-g fu d2">
      <span class="ic-icon">🌳</span>
      <div class="ic-val" id="c-trees">0</div>
      <div class="ic-unit">árboles no talados</div>
      <div class="ic-desc">Cada tonelada de bagazo reemplaza 2,8 ton de madera. Verificado por cadena de custodia FSC.</div>
      <span class="ic-badge ib-g">↑ +12% vs período anterior</span>
    </div>
    <div class="ic ic-k fu d3">
      <span class="ic-icon">🌬️</span>
      <div class="ic-val" id="c-co2">0</div>
      <div class="ic-unit">kg CO₂ evitados</div>
      <div class="ic-desc">0,18 kg CO₂/u vs 0,72 kg del papel de árbol. Verificado por SCS Global Services.</div>
      <span class="ic-badge ib-k">SCS Global Services · Verificado</span>
    </div>
    <div class="ic ic-b fu d4">
      <span class="ic-icon">👷</span>
      <div class="ic-val" id="c-jobs">0</div>
      <div class="ic-unit">días/empleo sostenidos</div>
      <div class="ic-desc">En Libertador Gral. San Martín, Jujuy. 6.000 empleos directos en el Complejo Agroindustrial.</div>
      <span class="ic-badge ib-b">6.000 empleos activos · Jujuy</span>
    </div>
    <div class="ic ic-t fu d5">
      <span class="ic-icon">🦜</span>
      <div class="ic-val" id="c-yungas">0.0</div>
      <div class="ic-unit">ha Yungas protegidas</div>
      <div class="ic-desc">Reserva de Biosfera UNESCO. Mayor biodiversidad del NOA argentino. Programa ProYungas activo.</div>
      <span class="ic-badge ib-g">Sello Producto Yungas</span>
    </div>
  </div>

  <!-- MAP BANNER -->
  <div class="map-banner fu d3">
    <div>
      <div class="mb-label">Territorio de impacto</div>
      <h2 class="mb-title">El Complejo Agroindustrial de Jujuy<br>— el origen del papel NAT</h2>
      <p class="mb-desc">Un residuo agroindustrial —el bagazo de la caña de azúcar— se convierte en papel premium libre de deforestación, en el corazón de la mayor biodiversidad del noroeste argentino, sosteniendo a una de las provincias más vulneradas del país. En el ejercicio 2024/25, las exportaciones NAT se duplicaron alcanzando el 34,7% de la producción total, con la incorporación de Portugal como nuevo mercado.</p>
      <div class="mb-facts">
        <div><div class="mf-val">7.600.000+</div><div class="mf-lbl">ha bajo protección · Yungas</div></div>
        <div><div class="mf-val">34,7%</div><div class="mf-lbl">ya exportado (2024/25) → meta 40%</div></div>
        <div><div class="mf-val">0%</div><div class="mf-lbl">deforestación en el proceso</div></div>
      </div>
    </div>
    <svg viewBox="0 0 160 200" width="150" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <radialGradient id="jg" cx="52%" cy="38%" r="45%">
          <stop offset="0%" stop-color="rgba(86,184,64,.25)"/>
          <stop offset="100%" stop-color="rgba(86,184,64,0)"/>
        </radialGradient>
      </defs>
      <path d="M72 10 L96 12 L106 24 L108 38 L104 52 L106 66 L108 82 L106 98 L108 116 L106 132 L100 150 L92 165 L82 176 L74 182 L68 176 L58 162 L50 146 L44 130 L40 114 L38 98 L36 82 L34 68 L36 54 L40 40 L48 26 L58 16 Z"
        fill="rgba(22,42,12,.05)" stroke="rgba(22,42,12,.15)" stroke-width="1.2"/>
      <path d="M72 10 L96 12 L106 24 L108 38 L102 46 L90 50 L78 48 L66 44 L58 34 L62 20 Z"
        fill="url(#jg)" stroke="#56B840" stroke-width="1.5"/>
      <circle cx="84" cy="30" r="5" fill="#56B840" opacity=".9">
        <animate attributeName="r" values="5;7;5" dur="2.2s" repeatCount="indefinite"/>
        <animate attributeName="opacity" values=".9;.5;.9" dur="2.2s" repeatCount="indefinite"/>
      </circle>
      <circle cx="84" cy="30" r="12" fill="rgba(86,184,64,.15)">
        <animate attributeName="r" values="12;18;12" dur="2.2s" repeatCount="indefinite"/>
        <animate attributeName="opacity" values=".3;0;.3" dur="2.2s" repeatCount="indefinite"/>
      </circle>
      <text x="84" y="54" text-anchor="middle" font-family="Roboto Mono,monospace" font-size="7" fill="#56B840" font-weight="600">JUJUY</text>
      <text x="84" y="63" text-anchor="middle" font-family="Roboto Mono,monospace" font-size="5.5" fill="#7A9B6A">COMPLEJO NAT</text>
    </svg>
  </div>

  <!-- CHARTS ROW -->
  <div class="charts-row fu d4">
    <div class="panel">
      <div class="p-title">Reducción de impacto ambiental</div>
      <div class="p-sub">Comparativa NAT vs. papel de fibra de árbol</div>
      <span class="p-tag">Ene–May 2026</span>
      <br><br>
      <div class="hbar-list">
        <div class="hbar-row hb-g">
          <div class="hbar-meta"><span class="hbar-lbl">Deforestación evitada</span><span class="hbar-val">–88%</span></div>
          <div class="hbar-track"><div class="hbar-fill" style="width:0%" data-w="88"></div></div>
        </div>
        <div class="hbar-row hb-g">
          <div class="hbar-meta"><span class="hbar-lbl">Huella de carbono</span><span class="hbar-val">–75%</span></div>
          <div class="hbar-track"><div class="hbar-fill" style="width:0%" data-w="75"></div></div>
        </div>
        <div class="hbar-row hb-g">
          <div class="hbar-meta"><span class="hbar-lbl">Uso de agua en producción</span><span class="hbar-val">–62%</span></div>
          <div class="hbar-track"><div class="hbar-fill" style="width:0%" data-w="62"></div></div>
        </div>
        <div class="hbar-row hb-g">
          <div class="hbar-meta"><span class="hbar-lbl">Generación de residuos</span><span class="hbar-val">–91%</span></div>
          <div class="hbar-track"><div class="hbar-fill" style="width:0%" data-w="91"></div></div>
        </div>
        <div class="hbar-row hb-k">
          <div class="hbar-meta"><span class="hbar-lbl">Impacto social positivo</span><span class="hbar-val">+78%</span></div>
          <div class="hbar-track"><div class="hbar-fill" style="width:0%" data-w="78"></div></div>
        </div>
      </div>
    </div>
    <div class="panel">
      <div class="p-title">Alineación ODS</div>
      <div class="p-sub">Objetivos de Desarrollo Sostenible — ONU</div>
      <div class="ods-grid" style="margin-top:8px">
        <div class="ods-card ods-8">
          <div class="ods-num">8</div>
          <div><div class="ods-name">Trabajo digno</div><div class="ods-tag">6.000 empleos</div></div>
        </div>
        <div class="ods-card ods-13">
          <div class="ods-num">13</div>
          <div><div class="ods-name">Acción clima</div><div class="ods-tag">–75% CO₂</div></div>
        </div>
        <div class="ods-card ods-15">
          <div class="ods-num">15</div>
          <div><div class="ods-name">Ecosistemas</div><div class="ods-tag">Yungas · UNESCO</div></div>
        </div>
        <div class="ods-card ods-12">
          <div class="ods-num">12</div>
          <div><div class="ods-name">Consumo resp.</div><div class="ods-tag">Bagazo · 0 árbol</div></div>
        </div>
      </div>
    </div>
  </div>

  <!-- FINANCIAL KPIS -->
  <div class="sec-hd fu d4">
    <div class="sec-title">Retorno del plan estratégico — Modelo insetting</div>
    <div class="sec-sub">ROI 144% · VAN USD 1.383K · Payback 11 meses</div>
  </div>
  <div class="fin-row fu d4">
    <div class="fin-card">
      <div class="fin-label">ROI — 3 años</div>
      <div class="fin-val"><span id="c-roi">0</span><span>%</span></div>
      <div class="fin-sub">Por cada USD 1 invertido, el plan retorna USD 2,44 en ingresos netos. Superior al modelo de venta de créditos (+30 pp).</div>
      <span class="fin-badge">↑ vs 114% offsetting</span>
    </div>
    <div class="fin-card">
      <div class="fin-label">VAN — Tasa 10% anual</div>
      <div class="fin-val">USD <span id="c-van">0</span><span>K</span></div>
      <div class="fin-sub">Valor presente neto positivo. 27,6% superior al modelo de venta de créditos al mercado voluntario.</div>
      <span class="fin-badge">↑ vs USD 1.084K offsetting</span>
    </div>
    <div class="fin-card">
      <div class="fin-label">Payback</div>
      <div class="fin-val">~<span id="c-pay">0</span><span> meses</span></div>
      <div class="fin-sub">Período de recupero de la inversión desde el inicio del plan. Más rápido porque el premium insetting genera ingresos desde los primeros contratos.</div>
      <span class="fin-badge">↓ 3 meses más rápido</span>
    </div>
  </div>

  <!-- BOTTOM ROW -->
  <div class="bot-row fu d5">

    <!-- Timeline -->
    <div class="panel">
      <div class="p-title">Línea de tiempo del contrato</div>
      <div class="p-sub">Hitos verificados · Arcor S.A.</div>
      <div class="tl" style="margin-top:14px">
        <div class="tl-item tl-done">
          <div class="tl-dot"><div class="tl-pip"></div></div>
          <div class="tl-body">
            <div class="tl-date">Enero 2026</div>
            <div class="tl-t">Contrato sostenible firmado</div>
            <div class="tl-d">12 meses · 1.200 kg/mes · precio premium</div>
            <span class="tl-tag tt-d">✓ Completado</span>
          </div>
        </div>
        <div class="tl-item tl-done">
          <div class="tl-dot"><div class="tl-pip"></div></div>
          <div class="tl-body">
            <div class="tl-date">Febrero 2026</div>
            <div class="tl-t">Primer despacho certificado recibido</div>
            <div class="tl-d">Doc. SCS + cadena custodia FSC entregada</div>
            <span class="tl-tag tt-d">✓ Completado</span>
          </div>
        </div>
        <div class="tl-item tl-now">
          <div class="tl-dot"><div class="tl-pip"></div></div>
          <div class="tl-body">
            <div class="tl-date">Jun 2026 · Ahora</div>
            <div class="tl-t">Seguimiento de impacto en tiempo real</div>
            <div class="tl-d">Dashboard actualizado en cada despacho</div>
            <span class="tl-tag tt-n">⏳ Activo</span>
          </div>
        </div>
        <div class="tl-item tl-next">
          <div class="tl-dot"><div class="tl-pip"></div></div>
          <div class="tl-body">
            <div class="tl-date">Julio 2026</div>
            <div class="tl-t">Reporte ESG semestral disponible</div>
            <div class="tl-d">GRI · CSRD compatible · Alcance 3 verificado</div>
            <span class="tl-tag tt-f">Próximo</span>
          </div>
        </div>
        <div class="tl-item tl-next">
          <div class="tl-dot"><div class="tl-pip"></div></div>
          <div class="tl-body">
            <div class="tl-date">Diciembre 2026</div>
            <div class="tl-t">Renovación y metas ESG 2027</div>
            <div class="tl-d">Reunión con ejecutivo de cuenta programada</div>
            <span class="tl-tag tt-f">Por coordinar</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Certs -->
    <div class="panel">
      <div class="p-title">Certificaciones activas</div>
      <div class="p-sub">Estándares que respaldan cada compra</div>
      <div class="cert-list" style="margin-top:8px">
        <div class="cert-item">
          <span style="font-size:16px">🌿</span>
          <div><div class="cert-name">ISO 14001:2015</div><div class="cert-org">IRAM · Gestión ambiental</div></div>
          <div class="cert-badge cb-ok">ACTIVA</div>
        </div>
        <div class="cert-item">
          <span style="font-size:16px">🌲</span>
          <div><div class="cert-name">FSC Cadena de Custodia</div><div class="cert-org">Forest Stewardship Council</div></div>
          <div class="cert-badge cb-ok">ACTIVA</div>
        </div>
        <div class="cert-item">
          <span style="font-size:16px">🔬</span>
          <div><div class="cert-name">SCS Huella de Carbono</div><div class="cert-org">SCS Global · 0,18 kg CO₂/u</div></div>
          <div class="cert-badge cb-ok">VERIF.</div>
        </div>
        <div class="cert-item">
          <span style="font-size:16px">🌄</span>
          <div><div class="cert-name">Sello Producto Yungas</div><div class="cert-org">Fundación ProYungas · UNESCO</div></div>
          <div class="cert-badge cb-ok">ACTIVO</div>
        </div>
        <div class="cert-item">
          <span style="font-size:16px">👁️</span>
          <div><div class="cert-name">CAO Oftalmología</div><div class="cert-org">Colegio Argentino de Oftalmología</div></div>
          <div class="cert-badge cb-ok">ACTIVA</div>
        </div>
        <div class="cert-item">
          <span style="font-size:16px">🔄</span>
          <div><div class="cert-name">SCS Alcance 3 — Insetting</div><div class="cert-org">Ampliación para reporte CSRD / GRI</div></div>
          <div class="cert-badge cb-new">EN PROCESO</div>
        </div>
        <div class="cert-item">
          <span style="font-size:16px">🏦</span>
          <div><div class="cert-name">KPI-linked Loan</div><div class="cert-org">Instrumento financiamiento sostenible</div></div>
          <div class="cert-badge cb-proc">ESTRUCTURANDO</div>
        </div>
      </div>
    </div>

    <!-- Insetting CO₂ panel -->
    <div class="insetting-panel">
      <div class="ins-label">Estrategia de Carbono · Insetting</div>
      <div class="ins-title">CO₂ como activo estratégico interno</div>
      <div class="ins-explain">
        Ledesma NAT retiene internamente sus atributos de carbono. No se venden créditos al mercado voluntario — hacerlo transferiría el derecho de declarar sostenibilidad a un tercero. En cambio, el CO₂ mitigado se usa para reducir las emisiones de Alcance 3 de los clientes y para acceder a financiamiento con tasa reducida.
      </div>

      <div class="co2-grid">
        <div class="co2-item">
          <div class="co2-val" id="c-carbon">0.00</div>
          <div class="co2-lbl">tCO₂e retenidas · período activo</div>
        </div>
        <div class="co2-item">
          <div class="co2-val">USD 90K</div>
          <div class="co2-lbl">ahorro financiamiento · Año 2</div>
        </div>
      </div>

      <div class="loan-box">
        <div class="loan-label">KPI-Linked Loan · Estructuración</div>
        <div class="loan-val">–35 bps</div>
        <div class="loan-sub">reducción tasa · tramo USD 20M · IFC / BID 2025</div>
        <div class="loan-bar-track"><div class="loan-bar-fill" id="loan-fill"></div></div>
        <div class="loan-bar-meta">
          <span>Inicio estructuración</span>
          <span style="color:var(--bright);font-weight:600">38% avanzado</span>
          <span>Cierre Dic. 2026</span>
        </div>
      </div>

      <div class="esg-cta">
        <div class="esg-ico">📄</div>
        <div>
          <div class="esg-name">Reporte Alcance 3 listo</div>
          <div class="esg-desc">CSRD · GRI · compatible reporte ESG</div>
        </div>
        <button class="esg-btn" onclick="alert('📊 Generando reporte de emisiones Alcance 3.\n\nEste reporte documenta las reducciones de emisiones en la cadena de suministro (Scope 3) derivadas de sus compras de papel NAT.\n\nContenido:\n• CO₂ evitado por sustitución de fibra de árbol\n• Trazabilidad verificada SCS Global Services\n• Formato compatible CSRD / GRI 305-3\n• Listo para incluir en reporte de sostenibilidad corporativo')">⬇ Bajar</button>
      </div>

      <div style="margin-top:12px;display:flex;flex-direction:column;gap:6px">
        <div style="display:flex;align-items:center;gap:8px;font-size:11px;color:rgba(253,252,248,.6)">
          <span style="color:var(--bright)">→</span>Premium B2B por trazabilidad: USD 15K → 120K → 210K
        </div>
        <div style="display:flex;align-items:center;gap:8px;font-size:11px;color:rgba(253,252,248,.6)">
          <span style="color:var(--bright)">→</span>Ahorro KPI-linked loan: USD 90K/año (Año 2)
        </div>
        <div style="display:flex;align-items:center;gap:8px;font-size:11px;color:rgba(253,252,248,.6)">
          <span style="color:var(--bright)">→</span>Visita Complejo Jujuy disponible · Jul 2026
        </div>
      </div>
    </div>
  </div>

</div><!-- /page -->

<!-- TICKER -->
<div class="ticker">
  <div class="tk-lbl">● LIVE</div>
  <div class="tk-scroll">
    <div class="tk-track">
      <div class="tk-item"><span class="tk-k">CO₂ evitado acumulado</span><span class="tk-v" id="tk-co2">223 kg</span></div>
      <div class="tk-item"><span class="tk-k">Árboles no talados</span><span class="tk-v">217</span></div>
      <div class="tk-item"><span class="tk-k">Precio papel exportación FOEX</span><span class="tk-v">USD 780/ton</span></div>
      <div class="tk-item"><span class="tk-k">Exportaciones NAT 2024/25</span><span class="tk-v">34,7% del total</span></div>
      <div class="tk-item"><span class="tk-k">Empleos sostenidos Jujuy</span><span class="tk-v">6.000</span></div>
      <div class="tk-item"><span class="tk-k">Producción NAT 2024/25</span><span class="tk-v">31.700 ton</span></div>
      <div class="tk-item"><span class="tk-k">Yungas bajo protección</span><span class="tk-v">7.600.000+ ha</span></div>
      <div class="tk-item"><span class="tk-k">Calificación FIX SCR</span><span class="tk-v">AA-(arg)</span></div>
      <div class="tk-item"><span class="tk-k">ROI plan insetting</span><span class="tk-v">144%</span></div>
      <div class="tk-item"><span class="tk-k">Payback</span><span class="tk-v">~11 meses</span></div>
      <!-- duplicate for loop -->
      <div class="tk-item"><span class="tk-k">CO₂ evitado acumulado</span><span class="tk-v">223 kg</span></div>
      <div class="tk-item"><span class="tk-k">Árboles no talados</span><span class="tk-v">217</span></div>
      <div class="tk-item"><span class="tk-k">Precio papel exportación FOEX</span><span class="tk-v">USD 780/ton</span></div>
      <div class="tk-item"><span class="tk-k">Exportaciones NAT 2024/25</span><span class="tk-v">34,7% del total</span></div>
      <div class="tk-item"><span class="tk-k">Empleos sostenidos Jujuy</span><span class="tk-v">6.000</span></div>
      <div class="tk-item"><span class="tk-k">Producción NAT 2024/25</span><span class="tk-v">31.700 ton</span></div>
      <div class="tk-item"><span class="tk-k">Yungas bajo protección</span><span class="tk-v">7.600.000+ ha</span></div>
      <div class="tk-item"><span class="tk-k">Calificación FIX SCR</span><span class="tk-v">AA-(arg)</span></div>
      <div class="tk-item"><span class="tk-k">ROI plan insetting</span><span class="tk-v">144%</span></div>
      <div class="tk-item"><span class="tk-k">Payback</span><span class="tk-v">~11 meses</span></div>
    </div>
  </div>
</div>

<script>
// ── COUNTERS ──────────────────────────────────────────────────────────────
function counter(id, target, duration, decimals=0) {
  const el = document.getElementById(id);
  if(!el) return;
  const start = performance.now();
  const tick = now => {
    const p = Math.min((now - start) / duration, 1);
    const e = 1 - Math.pow(1 - p, 3);
    el.textContent = decimals > 0
      ? (e * target).toFixed(decimals)
      : Math.round(e * target).toLocaleString('es-AR');
    if(p < 1) requestAnimationFrame(tick);
  };
  requestAnimationFrame(tick);
}

// ── BARS ──────────────────────────────────────────────────────────────────
function animateBars() {
  document.querySelectorAll('.hbar-fill[data-w]').forEach((bar, i) => {
    setTimeout(() => { bar.style.width = bar.dataset.w + '%'; }, 400 + i * 140);
  });
}

// ── INIT ──────────────────────────────────────────────────────────────────
window.addEventListener('load', () => {
  setTimeout(() => {
    counter('c-trees',  217,   1800);
    counter('c-co2',    223,   2000);
    counter('c-jobs',   3.2,   2200, 1);
    counter('c-yungas', 0.8,   2400, 1);
    counter('c-carbon', 10.23, 2600, 2);
    counter('c-roi',    144,   2000);
    counter('c-van',    1383,  2200);
    counter('c-pay',    11,    1600);
    animateBars();
    setTimeout(() => {
      const f = document.getElementById('loan-fill');
      if(f) f.style.width = '38%';
    }, 900);
  }, 500);

  // Live CO2 micro-increment
  let base = 223;
  setInterval(() => {
    base += Math.random() * 0.003;
    const el = document.getElementById('c-co2');
    const tk = document.getElementById('tk-co2');
    const v = Math.round(base).toLocaleString('es-AR');
    if(el) el.textContent = v;
    if(tk) tk.textContent = v + ' kg';
  }, 3500);
});
</script>
</body>
</html>
