<!DOCTYPE html>
<html lang="en">
<head>
<script src="/shim.js"></script>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#f6f4ee" media="(prefers-color-scheme: light)"><meta name="theme-color" content="#14151b" media="(prefers-color-scheme: dark)">
<title>Amar Hisab</title>
<style>
:root{--bg:#f6f4ee;--card:#fff;--tx:#1f2430;--mut:#666c7c;--bd:#e7e2d6;--pri:#5248c9;--pri-rgb:82,72,201;--pt:#4a42b8;--ptx:#fff;--h1:#3f37b0;--h2:#5b52d6;--ok:#0f7b53;--bad:#c62f3b;--g-rgb:13,148,104;--b-rgb:79,70,229;--p-rgb:2,132,199;--o-rgb:217,119,6;--t1:13,148,104;--t2:79,70,229;--t3:8,145,178;--t4:217,119,6;--t5:225,29,72;--t6:124,92,230;--sh:0 1px 2px rgba(31,36,48,.05),0 6px 18px rgba(31,36,48,.05);color-scheme:light dark;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#14151b;--card:#1d1f27;--tx:#eceef5;--mut:#9a9fb1;--bd:#2b2e3a;--pri:#5f5bd6;--pri-rgb:95,91,214;--pt:#b3b1ff;--h1:#3a37a8;--h2:#5f5bd6;--ok:#5ad8a8;--bad:#ff8a94;--g-rgb:52,211,153;--b-rgb:129,140,248;--p-rgb:56,189,248;--o-rgb:251,191,36;--t1:52,211,153;--t2:129,140,248;--t3:45,212,191;--t4:251,191,36;--t5:251,113,133;--t6:167,139,250;--sh:none;color-scheme:dark}}
:root[data-theme="dark"]{--bg:#14151b;--card:#1d1f27;--tx:#eceef5;--mut:#9a9fb1;--bd:#2b2e3a;--pri:#5f5bd6;--pri-rgb:95,91,214;--pt:#b3b1ff;--h1:#3a37a8;--h2:#5f5bd6;--ok:#5ad8a8;--bad:#ff8a94;--g-rgb:52,211,153;--b-rgb:129,140,248;--p-rgb:56,189,248;--o-rgb:251,191,36;--t1:52,211,153;--t2:129,140,248;--t3:45,212,191;--t4:251,191,36;--t5:251,113,133;--t6:167,139,250;--sh:none;color-scheme:dark}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--tx);font:16px/1.45 system-ui,-apple-system,"Segoe UI",Roboto,sans-serif}
main{max-width:560px;margin:0 auto;padding:14px}
h1{font-size:22px;margin:4px 0 12px;display:flex;align-items:center;flex-wrap:wrap;gap:6px}
nav{display:flex;gap:6px;margin-bottom:12px}
nav button{flex:1;display:flex;flex-direction:column;align-items:center;gap:3px;padding:8px 2px;border:1px solid var(--bd);background:var(--card);color:var(--tx);border-radius:10px;font:inherit;font-size:12px}
nav button.on{background:var(--pri);color:var(--ptx);border-color:var(--pri);font-weight:600;box-shadow:0 4px 12px rgba(var(--pri-rgb),.28)}
.card{background:var(--card);border:1px solid var(--bd);border-radius:14px;padding:12px;margin-bottom:12px;box-shadow:var(--sh)}
input,select,textarea{width:100%;padding:11px;margin-top:8px;border:1px solid var(--bd);border-radius:10px;background:var(--bg);color:var(--tx);font:inherit}
textarea{min-height:90px;font-size:13px}
input:focus,select:focus,textarea:focus{outline:none;border-color:var(--pri);box-shadow:0 0 0 3px rgba(var(--pri-rgb),.2)}
.add{width:100%;margin-top:10px;padding:13px;border:0;border-radius:10px;background:var(--pri);color:var(--ptx);font:inherit;font-weight:700}
.big{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:10px}
.big div{border-radius:10px;padding:10px;background:var(--bg)}
.big b{display:block;font-size:24px}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.grid div{display:flex;justify-content:space-between;gap:6px;font-size:14px;border-top:1px solid var(--bd);padding-top:6px}
span.l{color:var(--mut);font-size:14px}
.neg{color:var(--bad)}.pos{color:var(--ok)}
.row{display:flex;align-items:center;gap:8px;padding:9px 0;border-top:1px solid var(--bd)}
.row>div:first-child{flex:1;min-width:0;overflow-wrap:anywhere}
.row small,.mut{color:var(--mut)}
.amt{font-weight:700;white-space:nowrap}
.row button{border:0;background:none;color:var(--mut);font-size:18px;padding:6px}
#msg{color:var(--bad);min-height:20px;margin:6px 0 0;font-size:14px}
.btn{padding:10px 14px;border:1px solid var(--bd);border-radius:10px;background:var(--card);color:var(--tx);font:inherit;margin-top:8px}
#lk{position:fixed;inset:0;z-index:99;background:var(--bg);display:none;align-items:center;justify-content:center;padding:20px}#lk.on{display:flex}
.sg{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:10px}.sc{background:var(--bg);border-radius:10px;padding:10px}.sc b{display:block;font-size:19px}.ahead{background:linear-gradient(135deg,var(--h1),var(--h2));color:#fff;border:0}.ahead .mut,.ahead .sc .l{color:#e6e4ff}.ahead .sc{background:rgba(255,255,255,.16)}
#t-backup .card{border-radius:10px}#t-backup .card>b{display:block;margin-bottom:6px;color:var(--pt)}#t-backup .btn{border-color:var(--pt);color:var(--pt);background:transparent;font-weight:600}#t-backup #wp{border-color:var(--bad);color:var(--bad)}
.lcard{width:100%;max-width:380px;background:var(--card);border:1px solid var(--bd);border-radius:8px;overflow:hidden;box-shadow:0 8px 28px rgba(0,0,0,.14)}.lh{background:var(--bg);padding:16px;text-align:center;border-bottom:1px solid var(--bd);font-size:22px;font-weight:700;color:var(--pt)}.lt{padding:12px;text-align:center;background:var(--bg);border-bottom:1px solid var(--bd);font-size:16px;letter-spacing:1.5px}.lb{padding:18px}.gbtn{width:100%;margin-top:14px;padding:13px;border:0;border-radius:8px;background:var(--pri);color:var(--ptx);font:inherit;font-weight:700;font-size:17px}.ck{display:flex;align-items:center;gap:8px;font-size:14px;margin-top:14px}.ck input{width:auto;margin:0}
.kp{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:10px}.kc{position:relative;border-radius:14px;padding:12px;border:1px solid}.kc b{display:block;font-size:21px;margin-top:6px}.kc .bd{position:absolute;top:10px;right:10px;width:32px;height:32px;border-radius:9px;display:flex;align-items:center;justify-content:center}
.kc.g{background:linear-gradient(135deg,rgba(var(--g-rgb),.2),rgba(var(--g-rgb),.04));border-color:rgba(var(--g-rgb),.5)}.kc.g .bd{background:rgba(var(--g-rgb),.25);color:rgb(var(--g-rgb))}
.kc.b{background:linear-gradient(135deg,rgba(var(--b-rgb),.2),rgba(var(--b-rgb),.04));border-color:rgba(var(--b-rgb),.5)}.kc.b .bd{background:rgba(var(--b-rgb),.25);color:rgb(var(--b-rgb))}
.kc.p{background:linear-gradient(135deg,rgba(var(--p-rgb),.2),rgba(var(--p-rgb),.04));border-color:rgba(var(--p-rgb),.5)}.kc.p .bd{background:rgba(var(--p-rgb),.25);color:rgb(var(--p-rgb))}
.kc.o{background:linear-gradient(135deg,rgba(var(--o-rgb),.2),rgba(var(--o-rgb),.04));border-color:rgba(var(--o-rgb),.5)}.kc.o .bd{background:rgba(var(--o-rgb),.25);color:rgb(var(--o-rgb))}
#sum>.big{display:none}
.kc>.l{display:block;padding-right:40px}
.lgo{display:inline-flex;align-items:center;justify-content:center;width:34px;height:34px;border-radius:10px;background:var(--pri);color:var(--ptx);flex:none}.lgo.sm{width:auto;height:auto;background:none;color:inherit;vertical-align:middle}.ahead .lgo{background:rgba(255,255,255,.22)}
.lh{display:flex;justify-content:center;align-items:center;gap:10px}
.row button[aria-label="Delete entry"],.row button[aria-label="Reject"]{color:var(--bad)}.row button[aria-label="Approve"]{color:var(--ok)}
#tb svg,#lq svg{vertical-align:-3px}
h1 #ttl{color:var(--pt)}
.grid div{border:1px solid rgba(var(--t),.35);background:rgba(var(--t),.08);border-radius:10px;padding:8px 10px}.grid div:nth-child(1){--t:var(--t1)}.grid div:nth-child(2){--t:var(--t2)}.grid div:nth-child(3){--t:var(--t3)}.grid div:nth-child(4){--t:var(--t4)}.grid div:nth-child(5){--t:var(--t5)}.grid div:nth-child(6){--t:var(--t6)}
#undo{position:fixed;left:12px;right:12px;bottom:calc(12px + env(safe-area-inset-bottom,0px));background:var(--tx);color:var(--bg);padding:10px 14px;border-radius:10px;display:flex;justify-content:space-between;align-items:center;z-index:50}#undo[hidden]{display:none}#undo .btn{margin:0;padding:6px 14px}
.dt{margin-top:6px;padding:8px;background:var(--bg);border-radius:8px;font-size:13px}.dt div{padding:2px 0}
:root[data-theme="light"]{color-scheme:light}
#lg,#rl{position:fixed;inset:0;z-index:100;background:var(--bg);display:none;align-items:center;justify-content:center;padding:20px}#lg.on,#rl.on{display:flex}
body.client main>section,body.client nav,body.client #lq,body.client #sum{display:none!important}body.client #t-client{display:block!important}
body.staff nav,body.staff #t-credit,body.staff #t-hist,body.staff #t-month,body.staff #t-staff,body.staff #t-backup,body.staff #sum,body.staff #stock{display:none!important}
.row button.pay{border:1px solid var(--pt);background:transparent;color:var(--pt);font-size:13px;font-weight:700;padding:6px 12px;border-radius:10px;white-space:nowrap}.row button.pay.on{background:var(--pri);border-color:var(--pri);color:var(--ptx)}
.pf{padding:10px;margin:2px 0 8px;border:1px solid var(--pri);border-radius:10px;background:var(--bg)}.pf .pr{display:flex;justify-content:space-between;align-items:center}.pf .pr b{font-size:20px}.pf .add{margin-top:10px}.pf .btn{width:100%}.pf .full{width:auto;margin:8px 0 0;padding:6px 12px;font-size:13px;border-color:var(--pt);color:var(--pt);background:transparent}.pf .pr[hidden]{display:none}.pf .pr#pdr{margin-top:8px}.pf .pr#pdr b{color:var(--pt)}.grid div:nth-child(7){--t:var(--t1)}.grid div:nth-child(8){--t:var(--t2)}.dn{display:flex;justify-content:space-between;align-items:center;margin-top:8px}.dn[hidden]{display:none}.dn b{color:var(--pt)}
/* effects */
@keyframes rise{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:none}}
@keyframes fadein{from{opacity:0}to{opacity:1}}
@keyframes navpop{0%{transform:scale(.9)}60%{transform:scale(1.07)}100%{transform:scale(1)}}
@keyframes rowin{from{opacity:0;transform:translateY(-10px)}to{opacity:1;transform:none}}
@keyframes flash{0%{background:rgba(var(--pri-rgb),.28)}100%{background:rgba(var(--pri-rgb),0)}}
@keyframes pfin{from{opacity:0;transform:translateY(-8px) scale(.98)}to{opacity:1;transform:none}}
@keyframes pop{0%{opacity:0;transform:scale(.7)}60%{opacity:1;transform:scale(1.08)}100%{transform:scale(1)}}
@keyframes toast{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:none}}
@keyframes spin{to{transform:rotate(360deg)}}
@keyframes rp{to{transform:scale(1);opacity:0}}
@keyframes logoin{0%{opacity:0;transform:scale(.4) rotate(-20deg)}70%{transform:scale(1.1) rotate(4deg)}100%{opacity:1;transform:none}}
.anim>*{animation:rise .5s cubic-bezier(.2,.75,.25,1) both}
.anim>*:nth-child(2){animation-delay:.06s}.anim>*:nth-child(3){animation-delay:.12s}.anim>*:nth-child(4){animation-delay:.18s}.anim>*:nth-child(n+5){animation-delay:.24s}
button,.btn{transition:transform .14s ease,background-color .2s ease,border-color .2s ease,color .2s ease,box-shadow .2s ease}
button:active:not(:disabled){transform:scale(.96)}
nav button.on{animation:navpop .38s cubic-bezier(.3,1.4,.5,1)}
.add,.gbtn,.btn,nav button,.row button.pay{position:relative;overflow:hidden}
.rp{position:absolute;border-radius:50%;background:currentColor;opacity:.28;transform:scale(0);animation:rp .6s ease-out forwards;pointer-events:none}
.row.flash{animation:rowin .4s cubic-bezier(.2,.8,.2,1),flash 1.6s ease-out;border-radius:8px}
.pf{animation:pfin .3s cubic-bezier(.2,.8,.2,1)}
.pop{animation:pop .45s cubic-bezier(.3,1.4,.5,1);transform-origin:left center}
#undo:not([hidden]){animation:toast .3s cubic-bezier(.2,.8,.2,1)}
#lk.on,#lg.on,#rl.on{animation:fadein .25s ease-out}
h1 .lgo{animation:logoin .7s cubic-bezier(.3,1.3,.5,1)}
#tb.spin svg{animation:spin .55s cubic-bezier(.4,0,.2,1)}
@media (hover:hover){.kc{transition:transform .2s ease,box-shadow .2s ease}.kc:hover{transform:translateY(-2px);box-shadow:0 8px 22px rgba(0,0,0,.14)}.card{transition:box-shadow .25s ease}}
@media (prefers-reduced-motion:reduce){*,*::before,*::after{animation-duration:.01ms!important;animation-delay:0s!important;animation-iteration-count:1!important;transition-duration:.01ms!important}}
/* login effects */
@keyframes drift1{from{transform:translate(0,0) scale(1)}to{transform:translate(70px,100px) scale(1.3)}}
@keyframes drift2{from{transform:translate(0,0) scale(1.15)}to{transform:translate(-80px,-90px) scale(.9)}}
@keyframes lcin{from{opacity:0;transform:translateY(36px) scale(.93);filter:blur(8px)}to{opacity:1;transform:none;filter:blur(0)}}
@keyframes track{from{letter-spacing:8px;opacity:0}to{letter-spacing:1.5px;opacity:1}}
@keyframes ring{0%{transform:scale(.92);opacity:.9}100%{transform:scale(1.7);opacity:0}}
@keyframes shine{0%{left:-60%}55%,100%{left:140%}}
@keyframes bar{to{background-position:-200% 0}}
#lk,#lg,#rl{overflow:hidden}
#lk::before,#lg::before,#rl::before,#lk::after,#lg::after,#rl::after{content:"";position:absolute;width:380px;height:380px;border-radius:50%;pointer-events:none;will-change:transform}
#lk::before,#lg::before,#rl::before{top:-110px;left:-120px;background:radial-gradient(circle,rgba(var(--pri-rgb),.34),transparent 68%);animation:drift1 13s ease-in-out infinite alternate}
#lk::after,#lg::after,#rl::after{bottom:-120px;right:-110px;background:radial-gradient(circle,rgba(var(--p-rgb),.28),transparent 68%);animation:drift2 16s ease-in-out infinite alternate}
.lcard{position:relative;z-index:1}
.lcard::before{content:"";position:absolute;left:0;right:0;top:0;height:3px;z-index:2;background:linear-gradient(90deg,var(--h2),rgb(var(--p-rgb)),var(--h2));background-size:200% 100%;animation:bar 3.5s linear infinite}
.on .lcard{animation:lcin .65s cubic-bezier(.2,.85,.25,1)}
.on .lcard .lt{animation:track .85s cubic-bezier(.2,.8,.2,1) .15s backwards}
.on .lcard .lb>*{animation:rise .5s cubic-bezier(.2,.75,.25,1) backwards}
.on .lcard .lb>*:nth-child(1){animation-delay:.3s}.on .lcard .lb>*:nth-child(2){animation-delay:.37s}.on .lcard .lb>*:nth-child(3){animation-delay:.44s}.on .lcard .lb>*:nth-child(4){animation-delay:.51s}.on .lcard .lb>*:nth-child(n+5){animation-delay:.58s}
.lcard .lgo{position:relative}
.lcard .lgo::after{content:"";position:absolute;inset:-3px;border-radius:13px;border:2px solid rgba(var(--pri-rgb),.55);animation:ring 2.4s ease-out infinite;pointer-events:none}
.lcard input{transition:border-color .2s ease,box-shadow .2s ease,transform .2s ease}
.lcard input:focus{transform:translateY(-1px)}
.gbtn{position:relative;overflow:hidden;box-shadow:0 6px 16px rgba(var(--pri-rgb),.32)}
.gbtn::before{content:"";position:absolute;top:0;left:-60%;width:40%;height:100%;background:linear-gradient(100deg,transparent,rgba(255,255,255,.38),transparent);transform:skewX(-20deg);animation:shine 3.4s ease-in-out 1.2s infinite;pointer-events:none}
#lm,#lge{min-height:22px;margin:10px 0 0;font-size:14px}
@media (prefers-reduced-motion:reduce){.gbtn::before,.lcard .lgo::after,.lcard::before{animation:none!important}.gbtn::before,.lcard .lgo::after{display:none}}
/* receipt */
@keyframes rcprint{from{clip-path:inset(0 0 100% 0)}to{clip-path:inset(0 0 -16px 0)}}
#rc{position:fixed;inset:0;z-index:90;display:none;align-items:flex-start;justify-content:center;padding:18px 14px calc(18px + env(safe-area-inset-bottom,0px));background:rgba(12,13,24,.58);-webkit-backdrop-filter:blur(5px);backdrop-filter:blur(5px);overflow-y:auto}
#rc.on{display:flex;animation:fadein .22s ease-out}
.rcw{width:min(360px,100%);margin:auto 0}
.slip{position:relative;background:#fffdf7;color:#1c1b1a;padding:22px 18px 24px;border-radius:5px 5px 0 0;font-size:14px;line-height:1.45;box-shadow:0 14px 40px rgba(0,0,0,.35);animation:rcprint .8s cubic-bezier(.3,.7,.2,1) both}
.slip::after{content:"";position:absolute;left:0;right:0;top:100%;height:10px;background:linear-gradient(135deg,#fffdf7 5px,transparent 0) 0 0/14px 10px,linear-gradient(225deg,#fffdf7 5px,transparent 0) 0 0/14px 10px}
.slip p{margin:0}
.slip .st{text-align:center;font-weight:800;font-size:19px;letter-spacing:.2px;word-break:break-word}
.slip .ss{text-align:center;font-size:12.5px;color:#6b665c;word-break:break-word}
.slip .sh{text-align:center;font-weight:700;letter-spacing:2px;font-size:12.5px;margin:2px 0}
.slip .sp{border-top:1.5px dashed #c9c3b5;margin:11px 0}
.slip .sk,.slip .si{display:flex;justify-content:space-between;gap:12px;align-items:baseline;margin:2px 0}
.slip .sk span:first-child{color:#6b665c}
.slip .sk b,.slip .si b{text-align:right;word-break:break-word}
.slip .si span{font-weight:500;word-break:break-word}
.slip .stt{display:flex;justify-content:space-between;align-items:baseline;font-weight:800;font-size:20px;margin:8px 0 2px}
.slip .due{display:flex;justify-content:space-between;gap:12px;margin-top:8px;padding:8px 11px;border-radius:9px;background:#fdecee;color:#a1242f;font-weight:700}
.slip .due.okk{background:#e5f5ec;color:#0f6b45;justify-content:center}
.slip .sf{text-align:center;color:#6b665c;font-size:13px;margin-top:2px}
.rcm{color:#fff;text-align:center;font-size:13px;min-height:18px;margin:22px 0 0}
.rca{margin-top:2px}.rca .gbtn{margin-top:6px}
.rcr{display:flex;gap:8px;margin-top:10px}.rcr .btn{flex:1;background:var(--card);padding:11px 6px;font-size:14px}
#rcl{margin-top:8px;font-size:13.5px}
@media print{body>*:not(#rc){display:none!important}#rc{position:static!important;display:block!important;background:none!important;-webkit-backdrop-filter:none;backdrop-filter:none;padding:0;overflow:visible;animation:none}.rcw{width:100%;max-width:80mm;margin:0 auto}.slip{box-shadow:none;animation:none;clip-path:none;padding:6px 4px}.slip::after{display:none}.rca,.rcm{display:none!important}}

/* fx2: add-entry, credit search, extra effects */
html{scroll-behavior:smooth}
@keyframes barflow{to{background-position:-200% 0}}
@keyframes okring{0%{box-shadow:0 0 0 0 rgba(var(--pri-rgb),.55)}100%{box-shadow:0 0 0 18px rgba(var(--pri-rgb),0)}}
@keyframes okpop{0%{transform:scale(1)}40%{transform:scale(1.06)}100%{transform:scale(1)}}
@keyframes fillfx{0%{background:rgba(var(--pri-rgb),.32);box-shadow:0 0 0 3px rgba(var(--pri-rgb),.35)}100%{box-shadow:0 0 0 0 rgba(var(--pri-rgb),0)}}
@keyframes shakefx{0%,100%{transform:translateX(0)}20%{transform:translateX(-7px)}40%{transform:translateX(6px)}60%{transform:translateX(-4px)}80%{transform:translateX(3px)}}
@keyframes sheen{from{transform:translateX(-130%) skewX(-20deg)}to{transform:translateX(260%) skewX(-20deg)}}
@keyframes attn{0%,100%{box-shadow:0 0 0 0 rgba(198,47,59,0)}50%{box-shadow:0 0 0 6px rgba(198,47,59,.22)}}
@keyframes blinkfx{50%{opacity:.5}}
.addfx{position:relative;overflow:hidden}
.addfx::before{content:"";position:absolute;left:0;right:0;top:0;height:3px;background:linear-gradient(90deg,var(--h2),rgb(var(--p-rgb)),var(--h2));background-size:200% 100%;animation:barflow 3.5s linear infinite}
.addfx>*{animation:rise .45s cubic-bezier(.2,.75,.25,1) backwards}
.addfx>*:nth-child(2){animation-delay:.04s}.addfx>*:nth-child(3){animation-delay:.08s}.addfx>*:nth-child(4){animation-delay:.12s}.addfx>*:nth-child(5){animation-delay:.16s}.addfx>*:nth-child(6){animation-delay:.2s}.addfx>*:nth-child(n+7){animation-delay:.24s}
#itw:not([hidden]),#ctw:not([hidden]),#cw:not([hidden]),#dw:not([hidden]),#dnet:not([hidden]){animation:pfin .32s cubic-bezier(.2,.8,.2,1)}
input.fill{animation:fillfx .9s ease-out}
#sv{position:relative;overflow:hidden}
#sv.ok{animation:okring .8s ease-out,okpop .45s cubic-bezier(.3,1.4,.5,1)}
#sv.ok::after{content:"\2713";margin-left:8px;display:inline-block;animation:pop .45s cubic-bezier(.3,1.4,.5,1)}
.addfx.bad{animation:shakefx .4s}
.add,.gbtn,.btn,nav button,.row button,#lq,#tb,#lb,.kc,.tile{position:relative;overflow:hidden}
.kc::after{content:"";position:absolute;top:0;bottom:0;left:0;width:40%;pointer-events:none;background:linear-gradient(90deg,transparent,rgba(255,255,255,.28),transparent);transform:translateX(-130%) skewX(-20deg);animation:sheen 1.3s ease-out .35s 1 both}
.anim .row{animation:rowin .4s cubic-bezier(.2,.8,.2,1) both}
.anim .row:nth-child(2){animation-delay:.03s}.anim .row:nth-child(3){animation-delay:.06s}.anim .row:nth-child(4){animation-delay:.09s}.anim .row:nth-child(5){animation-delay:.12s}.anim .row:nth-child(6){animation-delay:.15s}.anim .row:nth-child(n+7){animation-delay:.18s}
.row[onclick]:active{background:rgba(var(--pri-rgb),.1)}
#sr:not([hidden]){animation:pfin .25s ease-out}#sr .row{animation:rowin .3s both}
#bkw:not([hidden]){animation:pfin .4s ease-out,attn 2.4s ease-in-out .6s 2}
#stock .neg b{animation:blinkfx 1.6s ease-in-out infinite}
input[type=checkbox]:checked{animation:pop .3s}
#cqw input{margin-top:0}
@media (hover:hover){.row:hover{background:rgba(var(--pri-rgb),.05)}.tile{transition:transform .2s ease,box-shadow .2s ease}.tile:hover{transform:translateY(-2px);box-shadow:0 6px 16px rgba(0,0,0,.12)}nav button:not(.on):hover{transform:translateY(-2px)}#t-backup .card:hover{box-shadow:0 8px 22px rgba(0,0,0,.12)}}
</style>
</head>
<body>
<div id="lk"><div class="lcard"><div class="lh"><span class="lgo" data-i="lock"></span> Admin Panel</div><div class="lt">ENTER PASSWORD</div><div class="lb"><input id="pin" type="password" maxlength="12" placeholder="Password" onkeydown="if(event.key==='Enter')unlock()"><p id="lm" class="neg"></p><button class="gbtn" onclick="unlock()">Unlock</button><button class="btn" id="lc" hidden style="width:100%" onclick="cancelLock()">Cancel</button></div></div></div>
<div id="lg"><div class="lcard"><div class="lh"><span class="lgo"></span> Amar Hisab</div><div class="lt">ADMIN LOGIN</div><div class="lb"><input id="lgu" autocomplete="username" placeholder="Username"><input id="lgp" type="password" maxlength="12" autocomplete="current-password" placeholder="Password" onkeydown="if(event.key==='Enter')login()"><label class="ck"><input type="checkbox" id="rm"> Save this phone for 30 days</label><p id="lge" class="neg"></p><button class="gbtn" onclick="login()">Login</button><p class="mut" style="text-align:center;margin:14px 0 0;font-size:13px">Developed by Tamim</p></div></div></div>
<div id="rl"><div class="lcard"><div class="lh"><span class="lgo"></span> Amar Hisab</div><div class="lt">WHO ARE YOU?</div><div class="lb"><button class="gbtn" style="margin-top:0" onclick="pickRole('staff')">I am staff</button><button class="btn" style="width:100%;margin-top:10px" onclick="pickRole('client')">I am a client</button></div></div></div>
<div id="undo" hidden><span>Entry deleted.</span><button class="btn" onclick="undoDel()">Undo</button></div>
<div id="rc" onclick="if(event.target===this)rcClose()"><div class="rcw"><div class="slip" id="slip"></div><p id="rcm" class="rcm"></p><div class="rca"><button class="gbtn" onclick="rcShare()">Share receipt</button><div class="rcr"><button class="btn" onclick="rcPrint()">Print</button><button class="btn" onclick="rcDl()">Save image</button><button class="btn" onclick="rcClose()">Close</button></div></div></div></div>
<main>
<h1><span style="display:flex;align-items:center;gap:8px"><span class="lgo"></span><span id="ttl">Amar Hisab</span></span><span style="margin-left:auto;display:flex;gap:6px;align-items:center"><button class="btn" id="tb" style="margin:0;padding:6px 10px;font-size:14px" onclick="toggleTheme()">🌙</button> <button class="btn" id="lb" style="margin:0;float:right;padding:6px 10px;font-size:14px" onclick="toggleLang()">বাংলা</button> <button class="btn" id="lq" hidden style="margin:0 6px 0 0;float:right;padding:6px 10px;font-size:14px" onclick="lockNow()" aria-label="Log out">Log out</button></span></h1>
<nav>
<button id="b-today" onclick="setTab('today')">Today</button>
<button id="b-credit" onclick="setTab('credit')">Credit</button>
<button id="b-hist" onclick="setTab('hist')">Days</button>
<button id="b-month" onclick="setTab('month')">Month</button>
<button id="b-staff" onclick="setTab('staff')">Staff</button>
<button id="b-backup" onclick="setTab('backup')">Admin</button>
</nav>
<p id="st" class="mut" style="margin:-4px 0 10px;font-size:13px"></p>

<section id="t-today">
<div class="card">
<input type="date" id="d" onchange="date=this.value||today();render()" aria-label="Date">
<div id="sum" style="margin-top:10px"></div>
</div>
<div class="card" id="bkw" hidden></div>
<div class="card"><input id="q" placeholder="Search a name or note" oninput="srch()"><div id="sr" hidden></div></div>
<div class="card"><b>Rates and stock alert</b><div style="display:flex;gap:8px"><input id="rb" type="number" inputmode="decimal" min="0" step="any" placeholder="Sell rate: Broiler"><input id="rsn" type="number" inputmode="decimal" min="0" step="any" placeholder="Sell rate: Sonali"></div><div style="display:flex;gap:8px"><input id="brb" type="number" inputmode="decimal" min="0" step="any" placeholder="Buy rate: Broiler"><input id="brsn" type="number" inputmode="decimal" min="0" step="any" placeholder="Buy rate: Sonali"></div><input id="sl" type="number" inputmode="decimal" min="0" step="any" placeholder="Alert when stock is below (kg)"><button class="btn" onclick="saveRates()">Save</button><p id="rm2" class="mut"></p><p class="mut">Buy rates fill in when you buy chicken (cash or credit). Type only the amount and the kg is worked out and added to stock.</p></div>
<div class="card addfx" id="addc">
<b>Add an entry</b>
<input id="sn" hidden placeholder="Your name">
<select id="type" aria-label="Type" onchange="tg();calc();calcNet()">
<option value="sale_cash">Cash sale</option>
<option value="sale_credit">Credit sale (due later)</option>
<option value="collect">Payment received</option>
<option value="purchase">Purchase (chicken, feed, medicine, etc.)</option>
<option value="expense">Expense (rent, labour, ice, transport)</option>
<option value="buy_credit">Purchase on credit (you owe supplier)</option>
<option value="pay_sup">Paid money to supplier</option>
<option value="cashout">Owner cash out (take money out)</option>
<option value="loss">Dead or lost chicken (kg only)</option>
</select>
<div id="itw" hidden><select id="item" aria-label="Purchase item" onchange="tg();calc()"><option value="chicken">Chicken</option><option value="feed">Feed</option><option value="medicine">Medicine</option><option value="vaccine">Vaccine</option><option value="chicks">Chicks</option><option value="other">Other cost</option></select></div>
<div id="ctw" hidden><select id="cat" aria-label="Expense category"><option value="rent">Rent</option><option value="labour">Labour</option><option value="ice">Ice</option><option value="transport">Transport</option><option value="electricity">Electricity</option><option value="other">Other expense</option></select></div>
<input id="party" list="names" placeholder="Customer or hotel (needed for credit)" autocomplete="off">
<datalist id="names"></datalist>
<div id="cw"><select id="kind" aria-label="Chicken kind" onchange="$('rate').value='';calc();calcNet()"><option value="Broiler">Broiler</option><option value="Sonali">Sonali</option><option value="Other">Other</option></select>
<div style="display:flex;gap:8px"><input id="kg" type="number" inputmode="decimal" min="0" step="any" placeholder="Kg" oninput="calc();calcNet()"><input id="rate" type="number" inputmode="decimal" min="0" step="any" placeholder="Rate ৳ per kg" oninput="calc();calcNet()"></div></div>
<input id="note" placeholder="Note (optional)">
<input id="amt" oninput="calcKg();calcNet()" type="number" inputmode="decimal" min="0" step="any" placeholder="Total amount ৳ (auto from kg × rate)">
<div id="dw" hidden><input id="disc" type="number" inputmode="decimal" min="0" step="any" placeholder="Discount ৳ (optional)" oninput="calcNet()"><div class="dn" id="dnet" hidden><span class="l">After discount</span><b id="dnv"></b></div></div>
<p id="msg"></p>
<button class="add" id="sv" onclick="add()">Save entry</button>
<label class="ck" id="rcl"><input type="checkbox" id="rca" checked onchange="rcAutoSet(this.checked)"><span>Show receipt after saving</span></label>
</div>
<div class="card" id="stock"></div>
<div class="card" id="list"></div>
</section>

<section id="t-credit" hidden><div class="card" id="cqw"><input id="cq" placeholder="Search customer or supplier name" oninput="CQ=this.value;render()" autocomplete="off"></div><div class="card" id="credit"></div></section>
<section id="t-hist" hidden><div class="card" id="hist"></div></section>
<section id="t-month" hidden><div class="card"><input type="month" id="mp" onchange="mo=this.value||today().slice(0,7);render()" aria-label="Month"><div id="month" style="margin-top:10px"></div></div></section>

<section id="t-client" hidden><div class="card" id="cl-login"><b>Client login</b><p class="mut">Enter the username and password the shop gave you. You only need to do this once.</p><input id="cu" autocomplete="username" placeholder="Username"><input id="cp" type="password" maxlength="12" autocomplete="current-password" placeholder="Password"><p id="cm2" class="neg"></p><button class="add" onclick="claimLogin()">Link my account</button><button class="btn" style="width:100%" onclick="loadClient()">Check again</button></div>
<div id="cl-view" hidden><div class="card"><b id="cl-name"></b><div id="cl-bal" style="margin-top:8px"></div><p class="mut" id="cl-upd"></p></div><div class="card"><b>Statement</b><div id="cl-rows"></div></div></div>
<p style="text-align:center"><button class="btn" onclick="switchRole()">Switch role</button></p></section>
<section id="t-staff" hidden><div class="card"><b>Staff entries waiting</b><p class="mut">Your staff send entries from their own phones. Nothing is added to your accounts until you approve it.</p><button class="btn" onclick="loadStaff()">Check for new entries</button><p id="stmsg" class="mut"></p><div id="staffbox"></div></div>
<div class="card"><b>How to add a staff member</b><p class="mut">Open the Share menu of this page, invite the person by email and choose Contributor. They open the same link on their own phone and can only send entries. They cannot see your accounts.</p></div></section>
<section id="t-backup" hidden>
<div id="adm2"><div class="card ahead"><b style="font-size:18px;display:flex;align-items:center;gap:8px"><span class="lgo" data-i="shield"></span> Admin panel</b><p class="mut" id="dstat"></p><div class="sg" id="astat"></div></div></div>
<div class="card"><b>Password</b><p id="pst" class="mut"></p>
<input id="np" type="password" maxlength="12" placeholder="New password (4 to 12 characters)">
<button class="btn" onclick="setPin()">Save password</button> <button class="btn" onclick="rmPin()">Remove password</button>
<button class="btn" id="plb" hidden onclick="togglePL()"></button><button class="btn" onclick="lockNow()">Lock now</button>
<p class="mut">The Admin and Staff tabs always ask for the password. The password is a screen lock only. Your accounts are private to your Claude account, so do not share the link while signed in.</p></div>
<div class="card gate"><b><span class="lgo sm" data-i="receipt"></span> Shop details for receipt</b><p class="mut">Your shop name, address and phone are printed at the top of every receipt.</p><input id="shn" maxlength="60" placeholder="Shop name"><input id="sha" maxlength="90" placeholder="Address"><input id="shp" maxlength="30" inputmode="tel" placeholder="Phone number"><input id="shf" maxlength="80" placeholder="Message at the bottom (e.g. Thank you)"><button class="btn" onclick="saveShop()">Save</button><p id="shm" class="mut"></p></div>
<div class="card gate" id="clcard"><b><span class="lgo sm" data-i="users"></span> Client panel</b>
<p class="mut">Give a customer or hotel their own login. They see only their own account (credit sales, payments and balance due) and cannot change anything.</p>
<input id="cn" list="names" placeholder="Customer or hotel name (as in your entries)">
<input id="cu2" autocomplete="off" placeholder="Client username">
<input id="cp2" type="password" maxlength="12" autocomplete="new-password" placeholder="Client password (4 to 12 characters)">
<button class="btn" onclick="addClient()">Add client</button> <button class="btn" onclick="syncClients()">Link and update</button>
<p id="clm" class="mut"></p><div id="clist"></div></div>
<div class="card gate"><b><span class="lgo sm" data-i="lock"></span> Login security</b><p class="mut" id="lgs"></p>
<input id="lu" autocomplete="off" placeholder="New username">
<input id="lp" type="password" maxlength="12" autocomplete="new-password" placeholder="New password (4 to 12 characters)">
<button class="btn" onclick="setLogin()">Save login</button> <button class="btn" onclick="rmLogin()">Turn off login</button> <button class="btn" onclick="logout()">Log out now</button>
<p id="lgm" class="mut"></p>
<p class="mut">When a login is set, the page asks for it each time it is opened fresh. Refreshing keeps you logged in. Use the Log out button at the top to log out.</p></div>
<div class="card gate"><b>Erase everything</b><p class="mut">Deletes all entries here and online. Make a backup first.</p><button class="btn" id="wp" onclick="wipe()">Erase all data</button></div>
<div class="card gate">
<p>Your entries are saved online in your Claude account and also on this phone. Keeping a backup copy in your notes is still a good idea.</p>
<button class="btn" onclick="showBackup()">Show my backup</button>
<textarea id="bk" readonly placeholder="Press the button, then select all and copy. Save the text in your notes."></textarea>
<p class="mut">To restore, paste a backup here. This replaces everything now on this page.</p>
<textarea id="rs" placeholder="Paste backup here"></textarea>
<button class="btn" onclick="restore()">Restore backup</button>
<p id="bmsg" class="mut"></p>
</div>
</section>
<p class="mut" style="text-align:center;margin:18px 0 6px;font-size:13px">Developed by Tamim</p>
</main>

<script>
const KEY='chicken_hisab_v1';
let S={entries:[]};
try{const r=localStorage.getItem(KEY);if(r)S=JSON.parse(r)}catch(e){}
let DB=null,UID=null,tm=0;const dirty=new Set();
const PK='hisab_pin';let PINH='';try{PINH=localStorage.getItem(PK)||''}catch(e){}
let PL=false,ADMOK=false,pend='';try{PL=localStorage.getItem('hisab_pl')==='1'}catch(e){}
let EX=null,LGU='',LGH='',LOK=false;try{LGU=localStorage.getItem('hisab_lu')||'';LGH=localStorage.getItem('hisab_lh')||'';LOK=sessionStorage.getItem('hisab_ok')==='1'||Number(localStorage.getItem('hisab_rm')||0)>Date.now()}catch(e){}
const mon=d=>(d||'').slice(0,7);
function setSt(t){const s=$('st');if(s)s.textContent=t}
function save(d){
  try{localStorage.setItem(KEY,JSON.stringify(S))}catch(e){}
  if(d)dirty.add(mon(d));
  if(!DB||!dirty.size)return;
  clearTimeout(tm);tm=setTimeout(push,600);
}
async function push(){
  const ms=[...dirty];dirty.clear();setSt('Saving online…');
  try{
    for(const m of ms){await DB.collection('data/users/'+UID).doc('m'+m).set({entries:S.entries.filter(e=>mon(e.date)===m)})}
    setSt('Saved online ✓');syncClients();
  }catch(e){ms.forEach(m=>dirty.add(m));setSt('Could not save online. Saved on this phone only.')}
}
async function initOnline(){
  try{
    const db=await claude.use('db'),user=await claude.use('user');
    if(!db||!user)return setSt('Saved on this phone only.');
    UID=await user.id();
    if(!UID)return setSt('Saved on this phone only.');
    const snap=await db.collection('data/users/'+UID).get();
    const ids=new Set();
    snap.docs.forEach(d=>((d.data()||{}).entries||[]).forEach(e=>{if(e&&e.id){ids.add(e.id);if(!S.entries.some(x=>x.id===e.id))S.entries.push(e)}}));
    S.entries.sort((a,b)=>a.date<b.date?-1:a.date>b.date?1:0);
    S.entries.forEach(e=>{if(!ids.has(e.id))dirty.add(mon(e.date))});
    DB=db;
    const sd=snap.docs.find(d=>d.id==='settings'),sp=sd?((sd.data()||{}).pin||''):'';
    if(sd){const dd=sd.data()||{},ph=dd.phones;if(ph)S.phones=Object.assign({},ph,S.phones||{});if(dd.clients&&dd.clients.length&&!(S.clients||[]).length)S.clients=dd.clients;if(dd.rates&&!Object.keys(S.rates||{}).length)S.rates=dd.rates;if(dd.brates&&!Object.keys(S.brates||{}).length)S.brates=dd.brates;if(dd.low&&!S.low)S.low=dd.low;if(dd.shop&&dd.shop.n&&!(S.shop&&S.shop.n))S.shop=dd.shop}
    {const lg=sd?(sd.data()||{}).lg:null;if(lg&&lg.h&&lg.h!==LGH){LGU=lg.u||'';LGH=lg.h;try{localStorage.setItem('hisab_lu',LGU);localStorage.setItem('hisab_lh',LGH)}catch(e){}LOK=false;lgShow()}else if(LGH&&!(lg&&lg.h))saveSet()}
    if(sp&&sp!==PINH){PINH=sp;try{localStorage.setItem(PK,sp)}catch(e){}if((sd.data()||{}).pl){PL=true;try{localStorage.setItem('hisab_pl','1')}catch(e){}lock()}}else if(PINH&&!sp)saveSet();
    try{localStorage.setItem(KEY,JSON.stringify(S))}catch(e){}
    render();
    if(dirty.size)push();else setSt('Saved online ✓');syncClients();
  }catch(e){setSt('Saved on this phone only.')}
}
const $=id=>document.getElementById(id);
const esc=s=>String(s).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const today=()=>new Date().toLocaleDateString('en-CA');
const fmt=n=>(n<0?'−':'')+'৳'+(Math.round(Math.abs(n)*100)/100).toLocaleString('en-IN');
const T={sale_cash:'Cash sale',sale_credit:'Credit sale',collect:'Payment received',purchase:'Purchase',expense:'Expense',loss:'Dead or lost',buy_credit:'Credit purchase',pay_sup:'Paid supplier',count:'Cash counted',cashout:'Owner cash out',discount:'Discount given',disc_sup:'Discount received'};
const ITEM={chicken:'Chicken',feed:'Feed',medicine:'Medicine',vaccine:'Vaccine',chicks:'Chicks',other:'Other cost'};
const CAT={rent:'Rent',labour:'Labour',ice:'Ice',transport:'Transport',electricity:'Electricity',other:'Other expense'};
const IC={home:`<path d='M15 21v-8a1 1 0 0 0-1-1h-4a1 1 0 0 0-1 1v8'/><path d='M3 10a2 2 0 0 1 .709-1.528l7-5.999a2 2 0 0 1 2.582 0l7 5.999A2 2 0 0 1 21 10v9a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z'/>`,receipt:`<path d='M4 2v20l2-1 2 1 2-1 2 1 2-1 2 1 2-1 2 1V2l-2 1-2-1-2 1-2-1-2 1-2-1-2 1Z'/><path d='M16 8h-6a2 2 0 1 0 0 4h4a2 2 0 1 1 0 4H8'/><path d='M12 17.5v-11'/>`,calendar:`<path d='M8 2v4'/><path d='M16 2v4'/><rect width='18' height='18' x='3' y='4' rx='2'/><path d='M3 10h18'/>`,chart:`<path d='M3 3v18h18'/><path d='M18 17V9'/><path d='M13 17V5'/><path d='M8 17v-3'/>`,users:`<path d='M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2'/><circle cx='9' cy='7' r='4'/><path d='M22 21v-2a4 4 0 0 0-3-3.87'/><path d='M16 3.13a4 4 0 0 1 0 7.75'/>`,shield:`<path d='M20 13c0 5-3.5 7.5-7.66 8.95a1 1 0 0 1-.67-.01C7.5 20.5 4 18 4 13V6a1 1 0 0 1 1-1c2 0 4.5-1.2 6.24-2.72a1.17 1.17 0 0 1 1.52 0C14.51 3.81 17 5 19 5a1 1 0 0 1 1 1z'/>`,wallet:`<path d='M19 7V4a1 1 0 0 0-1-1H5a2 2 0 0 0 0 4h15a1 1 0 0 1 1 1v4h-3a2 2 0 0 0 0 4h3a1 1 0 0 0 1-1v-2a1 1 0 0 0-1-1'/><path d='M3 5v14a2 2 0 0 0 2 2h15a1 1 0 0 0 1-1v-4'/>`,trending:`<polyline points='22 7 13.5 15.5 8.5 10.5 2 17'/><polyline points='16 7 22 7 22 13'/>`,cart:`<circle cx='8' cy='21' r='1'/><circle cx='19' cy='21' r='1'/><path d='M2.05 2.05h2l2.66 12.42a2 2 0 0 0 2 1.58h9.78a2 2 0 0 0 1.95-1.57l1.65-7.43H5.12'/>`,sun:`<circle cx='12' cy='12' r='4'/><path d='M12 2v2'/><path d='M12 20v2'/><path d='m4.93 4.93 1.41 1.41'/><path d='m17.66 17.66 1.41 1.41'/><path d='M2 12h2'/><path d='M20 12h2'/><path d='m6.34 17.66-1.41 1.41'/><path d='m19.07 4.93-1.41 1.41'/>`,moon:`<path d='M12 3a6 6 0 0 0 9 9 9 9 0 1 1-9-9Z'/>`,logout:`<path d='M9 21H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h4'/><polyline points='16 17 21 12 16 7'/><line x1='21' x2='9' y1='12' y2='12'/>`,lock:`<rect width='18' height='11' x='3' y='11' rx='2' ry='2'/><path d='M7 11V7a5 5 0 0 1 10 0v4'/>`,edit:`<path d='M21.174 6.812a1 1 0 0 0-3.986-3.987L3.842 16.174a2 2 0 0 0-.5.83l-1.321 4.352a.5.5 0 0 0 .623.622l4.353-1.32a2 2 0 0 0 .83-.497z'/>`,trash:`<path d='M3 6h18'/><path d='M19 6v14c0 1-1 2-2 2H7c-1 0-2-1-2-2V6'/><path d='M8 6V4c0-1 1-2 2-2h4c1 0 2 1 2 2v2'/>`,check:`<path d='M20 6 9 17l-5-5'/>`,x:`<path d='M18 6 6 18'/><path d='m6 6 12 12'/>`};
function ic(n,s){s=s||18;return `<svg xmlns='http://www.w3.org/2000/svg' width='${s}' height='${s}' viewBox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round' aria-hidden='true'>${IC[n]||''}</svg>`}
function kc(c,i,l,n){return '<div class="kc '+c+'"><span class="bd">'+ic(i,17)+'</span><span class="l">'+l+'</span><b class="'+(n<0?'neg':'')+'" data-n="'+(Number(n)||0)+'">'+fmt(n)+'</b></div>'}
function due(){let c=0;S.entries.forEach(e=>{if(e.type==='sale_credit')c+=e.amt;if(e.type==='collect'||e.type==='discount')c-=e.amt});return c}
let tab='today',date=today(),mo=today().slice(0,7),cust=null,CL=[],ed=null,wa=false,pay=null,payK='c',SA=[],OVP=false,PM='',ANIM=false,FLASH='';
function balOf(n,k){let b=0;S.entries.forEach(e=>{if(e.party!==n)return;if(k==='s'){if(e.type==='buy_credit')b+=e.amt;if(e.type==='pay_sup'||e.type==='disc_sup')b-=e.amt}else{if(e.type==='sale_credit')b+=e.amt;if(e.type==='collect'||e.type==='discount')b-=e.amt}});return Math.round(b*100)/100}
function togglePay(i,k){const L=k==='s'?SA:CL,n=L[i]?L[i][0]:null;pay=(n===null||(pay===n&&payK===k))?null:n;payK=k;OVP=false;PM='';render();if(pay){const a=$('pa');if(a){a.scrollIntoView({block:'center'})}}}
function togglePayCur(){pay=(pay===cust&&payK==='c')?null:cust;payK='c';OVP=false;PM='';render()}
function closePay(){pay=null;OVP=false;render()}
function payCalc(){const c=$('pdc'),r=$('pdr'),v=$('pdv');if(!c||!r||!v||!pay)return;const b=balOf(pay,payK);let a=parseFloat($('pa').value);if(isNaN(a))a=0;const d=Math.round((b-a)*100)/100;if(c.checked&&b>0&&a>=0&&d>0.004){r.hidden=false;v.textContent=fmt(d)}else r.hidden=true}
function fullPay(){const a=$('pa');if(a&&pay){const b=balOf(pay,payK);a.value=b>0?b:'';OVP=false;payCalc()}}
function payForm(n,k){const b=balOf(n,k),s=k==='s';return '<div class="pf"><div class="pr"><span class="l">'+(s?'Total to pay':'Total due')+'</span><b class="'+(s?'':(b>0?'neg':'pos'))+'">'+fmt(b)+'</b></div><input id="pa" type="number" inputmode="decimal" min="0" step="any" placeholder="'+(s?'Amount paid ৳':'Amount received ৳')+'" value="'+(b>0?b:'')+'" oninput="OVP=false;payCalc()"><button class="btn full" onclick="fullPay()">Full amount</button><label class="ck"><input type="checkbox" id="pdc" onchange="payCalc()"><span>Rest as discount</span></label><div class="pr" id="pdr" hidden><span class="l">Discount</span><b id="pdv"></b></div><input id="pn" placeholder="Note (optional)">'+(PINH?'<input id="pp" type="password" maxlength="12" autocomplete="off" placeholder="Admin password to confirm" onkeydown="if(event.key===\'Enter\')savePay()">':'')+'<p id="pm" class="neg" style="min-height:20px;margin:6px 0 0;font-size:14px"></p><button class="add" onclick="savePay()">Save payment</button><button class="btn" onclick="closePay()">Cancel</button></div>'}
async function savePay(){const n=pay,k=payK;if(!n)return;const m=$('pm'),b=balOf(n,k),note=$('pn').value.trim(),pw=$('pp')?$('pp').value.trim():'',dc=!!($('pdc')&&$('pdc').checked);let a=parseFloat($('pa').value);if(isNaN(a)&&dc)a=0;if(!(a>0)&&!(dc&&a===0&&b>0)){m.textContent=k==='s'?'Enter the amount paid.':'Enter the amount received.';return}if(a>b+0.004&&!OVP){OVP=true;m.textContent='This is more than the due. Tap Save payment again to confirm.';return}if(PINH){if(!pw){m.textContent='Enter the admin password to confirm.';return}let ok=false;try{ok=(await hp(pw))===PINH}catch(e){m.textContent='Cannot check the PIN on this browser.';return}if(!ok){m.textContent='Wrong password.';const pe=$('pp');if(pe)pe.value='';return}}if(pay!==n||payK!==k)return;const ar=Math.round(a*100)/100,disc=dc&&b>0&&ar<b-0.004?Math.round((b-ar)*100)/100:0,base={date:today(),party:n,note},mk=()=>Date.now().toString(36)+Math.random().toString(36).slice(2,5),tn=Date.now();let e1=null,e2=null;if(ar>0){e1=Object.assign({id:mk(),type:k==='s'?'pay_sup':'collect',amt:ar,ts:tn},base);S.entries.push(e1)}if(disc>0){e2=Object.assign({id:mk(),type:k==='s'?'disc_sup':'discount',amt:disc,ts:tn+1},base);if(e1)e2.lk=e1.id;S.entries.push(e2)}save(base.date);pay=null;OVP=false;PM='Payment saved ✓';render();if(k==='c'&&rcAutoOn()&&(e1||e2))rcOpen((e1||e2).id)}
function ageOf(n){let p=0;S.entries.forEach(e=>{if(e.party===n&&(e.type==='collect'||e.type==='discount'))p+=e.amt});const cs=S.entries.filter(e=>e.party===n&&e.type==='sale_credit').sort((a,b)=>a.date<b.date?-1:a.date>b.date?1:0);for(const e of cs){if(p>=e.amt-0.004)p-=e.amt;else return Math.max(0,Math.floor((new Date(today())-new Date(e.date))/864e5))}return 0}
function edit(id){const e=S.entries.find(x=>x.id===id);if(!e)return;ed=id;$('type').value=e.type;tg();$('party').value=e.party||'';$('note').value=e.note||'';$('kind').value=e.kind?nk(e.kind):'Broiler';$('kg').value=e.kg||'';$('rate').value=e.rate||'';$('amt').value=e.amt?Math.round((e.amt+(e.disc||0))*100)/100:'';$('disc').value=e.disc||'';$('item').value=e.item||'chicken';$('cat').value=e.cat||'other';tg();calcNet();$('sv').textContent='Update entry';$('msg').textContent='Editing an entry. Change it, then tap Update entry.';window.scrollTo(0,0)}
function count(){const v=parseFloat($('cc').value);if(!(v>=0))return;S.entries=S.entries.filter(e=>!(e.type==='count'&&e.date===date));S.entries.push({id:Date.now().toString(36)+Math.random().toString(36).slice(2,5),date,type:'count',party:'',note:'',amt:v,ts:Date.now()});save(date);render()}
async function hp(p){const b=await crypto.subtle.digest('SHA-256',new TextEncoder().encode('hisab:'+p));return [...new Uint8Array(b)].map(x=>x.toString(16).padStart(2,'0')).join('')}
function lcBad(id,mid){const m=$(mid);if(m&&m.classList){m.classList.remove('pop');void m.offsetWidth;m.classList.add('pop')}try{const el=$(id),c=el&&el.querySelector&&el.querySelector('.lcard');if(!c||!c.animate||matchMedia('(prefers-reduced-motion: reduce)').matches)return;c.animate([{transform:'translateX(0)'},{transform:'translateX(-12px)'},{transform:'translateX(10px)'},{transform:'translateX(-8px)'},{transform:'translateX(6px)'},{transform:'translateX(-3px)'},{transform:'translateX(0)'}],{duration:480,easing:'ease-out'});c.animate([{boxShadow:'0 0 0 0 rgba(220,60,70,0)'},{boxShadow:'0 0 0 4px rgba(220,60,70,.55),0 8px 30px rgba(220,60,70,.35)',offset:.25},{boxShadow:'0 0 0 0 rgba(220,60,70,0)'}],{duration:900,easing:'ease-out'})}catch(e){}}
function lcHide(id){const el=$(id);if(!el)return;const c=el.querySelector&&el.querySelector('.lcard');let rm=false;try{rm=matchMedia('(prefers-reduced-motion: reduce)').matches}catch(e){}if(!el.animate||!c||!c.animate||rm){el.classList.remove('on');return}if(el._h)return;el._h=1;const o={duration:420,easing:'cubic-bezier(.4,0,.6,1)',fill:'forwards'},as=[c.animate([{opacity:1,transform:'none',filter:'blur(0px)'},{opacity:0,transform:'scale(1.08) translateY(-8px)',filter:'blur(6px)'}],o),el.animate([{opacity:1},{opacity:0}],Object.assign({},o,{duration:480}))],fin=()=>{if(!el._h)return;el._h=0;el.classList.remove('on');as.forEach(a=>{try{a.cancel()}catch(e){}})};as[1].onfinish=fin;setTimeout(fin,700)}
function lock(p){$('lk').classList.add('on');$('lc').hidden=!p}
async function unlock(){try{if(await hp($('pin').value.trim())===PINH){ADMOK=true;lcHide('lk');$('pin').value='';$('lm').textContent='';if(pend){const t=pend;pend='';setTab(t)}}else{$('lm').textContent='Wrong PIN.';lcBad('lk','lm')}}catch(e){$('lm').textContent='Cannot check the PIN on this browser.'}}
function cancelLock(){pend='';$('lk').classList.remove('on');$('pin').value='';$('lm').textContent=''}
function togglePL(){PL=!PL;try{localStorage.setItem('hisab_pl',PL?'1':'0')}catch(e){}saveSet();render()}
function lockNow(){ADMOK=false;if(LGH){logout();return}if(!PINH)return;setTab('today');setSt('Admin and Staff tabs are locked.')}
let TH='auto';try{TH=localStorage.getItem('hisab_th')||'auto'}catch(e){}
function isDark(){const a=document.documentElement.getAttribute('data-theme');return a?a==='dark':!!(window.matchMedia&&matchMedia('(prefers-color-scheme: dark)').matches)}
function applyTheme(){const d=document.documentElement;if(TH==='auto')d.removeAttribute('data-theme');else d.setAttribute('data-theme',TH);const k=isDark();$('tb').innerHTML=ic(k?'sun':'moon',16);$('tb').setAttribute('aria-label',k?'Switch to light mode':'Switch to dark mode')}
function toggleTheme(){const tb=$('tb');if(tb&&tb.classList){tb.classList.remove('spin');void tb.offsetWidth;tb.classList.add('spin');setTimeout(()=>tb.classList.remove('spin'),700)}TH=isDark()?'light':'dark';try{localStorage.setItem('hisab_th',TH)}catch(e){}applyTheme()}
function cashOut(){if(!(window.CO>0)){$('msg').textContent='No profit or cash available to take out today.';return}$('type').value='cashout';tg();$('amt').value=window.CO;$('note').value='Profit taken';$('party').value='';$('kg').value='';$('rate').value='';$('msg').textContent='Check the amount, then tap Save entry.';$('amt').scrollIntoView({block:'center'})}
function hm(ts){try{return new Date(ts).toLocaleTimeString('en-US',{hour:'numeric',minute:'2-digit'})}catch(e){return ''}}
function fdt(ts){try{return new Date(ts).toLocaleString('en-GB',{day:'numeric',month:'short',year:'numeric',hour:'numeric',minute:'2-digit',hour12:true})}catch(e){return ''}}
function detail(e){const L=[['Date',e.date],['Entered',e.ts?fdt(e.ts):'time not recorded'],['Type',T[e.type]],ITEM[e.item]?['Item',ITEM[e.item]]:null,CAT[e.cat]?['Category',CAT[e.cat]]:null,e.party?['Name',e.party]:null,e.kind?['Kind',e.kind]:null,e.kg?['Weight',e.kg+' kg']:null,e.rate?['Rate',fmt(e.rate)+' per kg']:null,['Amount',fmt(e.amt)],e.disc>0?['Discount',fmt(e.disc)]:null,e.note?['Note',e.note]:null,e.by?['Entered by',e.by]:null,e.ap?['Approved',fdt(e.ap)]:null,e.ed?['Last edited',fdt(e.ed)]:null].filter(Boolean);return '<div class="dt">'+L.map(x=>'<div><span class="l">'+x[0]+'</span> '+esc(String(x[1]))+'</div>').join('')+'</div>'}
function tgx(id){EX=EX===id?null:id;render()}
function decorate(){const NV={today:'home',credit:'receipt',hist:'calendar',month:'chart',staff:'users',backup:'shield'};for(const k in NV){const b=$('b-'+k);if(b)b.insertAdjacentHTML('afterbegin',ic(NV[k],18))}document.querySelectorAll('.lgo').forEach(e=>{e.innerHTML=ic(e.dataset.i||'wallet',e.classList.contains('sm')?16:19)})}
function pickRole(r){try{localStorage.setItem('hisab_role',r)}catch(e){}$('rl').classList.remove('on');if(r==='client')startClient(window.NU);else startStaff(window.NU)}
function switchRole(){try{localStorage.removeItem('hisab_role')}catch(e){}location.reload()}
let CU=null,CDB=null;
async function startClient(u){document.body.classList.add('client');$('lg').classList.remove('on');$('lk').classList.remove('on');$('ttl').textContent='My account';$('t-client').hidden=false;let db=null;try{db=await claude.use('db');CU=u?await u.id():null}catch(e){}if(!db||!CU){$('cm2').textContent='Sign in to Claude to use the client panel.';showClient(null);return}CDB=db;loadClient()}
async function loadClient(){if(!CDB)return;let d=null;try{const s=await CDB.doc('statements/'+CU).get();d=s&&(typeof s.data==='function'?s.data():s.data)}catch(e){}showClient(d&&d.rows?d:null)}
function showClient(d){$('cl-login').hidden=!!d;$('cl-view').hidden=!d;if(!d)return;$('cl-name').textContent=d.name||'';$('cl-bal').innerHTML=kc('o','receipt','Total due',Number(d.bal)||0);$('cl-upd').textContent=d.upd?'Updated '+fdt(d.upd):'';$('cl-rows').innerHTML=d.rows.length?d.rows.slice().reverse().map(r=>'<div class="row"><div><b>'+(r.t==='paid'?'Payment':r.t==='disc'?'Discount':'Credit sale')+'</b><br><small>'+esc(r.d||'')+(r.kg?' · '+Number(r.kg)+' kg '+esc(r.k||''):'')+'</small></div><div class="amt '+(r.t!=='sale'?'pos':'neg')+'">'+(r.t!=='sale'?'−':'')+fmt(Number(r.a)||0)+'</div></div>').join(''):'<p class="mut">No entries yet.</p>'}
async function claimLogin(){const u=$('cu').value.trim().toLowerCase(),p=$('cp').value,m=$('cm2');if(!CDB){m.textContent='Sign in to Claude first.';return}if(u.length<3||p.length<4){m.textContent='Enter your username and password.';return}try{const h=await hp('client:'+u+':'+p);await CDB.doc('claims/'+CU).set({u,h,t:Date.now()});$('cp').value='';m.textContent='Request sent. Your account is linked when the shop owner opens the page. Tap Check again later.'}catch(e){m.textContent='Could not send the request.'}}
async function addClient(){const n=$('cn').value.trim(),u=$('cu2').value.trim().toLowerCase(),p=$('cp2').value,m=$('clm');S.clients=S.clients||[];if(!n||u.length<3||p.length<4||p.length>12){m.textContent='Enter the customer name, a username (3+ characters) and a password (4 to 12 characters).';return}if(S.clients.some(c=>c.u===u)){m.textContent='That username is already used.';return}let h;try{h=await hp('client:'+u+':'+p)}catch(e){m.textContent='Not available on this browser.';return}S.clients.push({u,h,n,uid:''});save();saveSet();$('cn').value='';$('cu2').value='';$('cp2').value='';drawClients();m.textContent='Client added. Share this page with them as Contributor and give them the username and password. After they link once, tap Link and update here.'}
function drawClients(){const b=$('clist');if(!b)return;b.innerHTML=(S.clients||[]).map((c,i)=>'<div class="row"><div><b>'+esc(c.n)+'</b><br><small>'+esc(c.u)+' · '+(c.uid?'Linked ✓':'Not linked yet')+'</small></div><button onclick="rmClient('+i+')" aria-label="Delete entry">'+ic('trash',16)+'</button></div>').join('')}
async function rmClient(i){const c=(S.clients||[])[i];if(!c)return;if(c.uid&&DB){try{await DB.doc('statements/'+c.uid).delete();await DB.doc('claims/'+c.uid).delete()}catch(e){}}S.clients.splice(i,1);save();saveSet();drawClients()}
async function syncClients(){if(!DB||!(S.clients||[]).length)return;try{const cs=await DB.collection('claims').get();let ch=false;cs.docs.forEach(d=>{const v=d.data()||{};S.clients.forEach(c=>{if(c.u===v.u&&c.h===v.h&&c.uid!==d.id){c.uid=d.id;ch=true}})});if(ch){save();saveSet()}for(const c of S.clients){if(!c.uid)continue;let bal=0;const rows=S.entries.filter(e=>e.party===c.n&&(e.type==='sale_credit'||e.type==='collect'||e.type==='discount')).sort((a,b)=>a.date<b.date?-1:a.date>b.date?1:0).map(e=>{const cr=e.type==='sale_credit';bal+=cr?e.amt:-e.amt;const r={d:e.date,t:cr?'sale':(e.type==='discount'?'disc':'paid'),a:e.amt};if(e.kg){r.kg=e.kg;r.k=e.kind||''}return r});await DB.doc('statements/'+c.uid).set({name:c.n,bal,rows:rows.slice(-200),upd:Date.now()})}drawClients();const m=$('clm');if(m)m.textContent='Clients updated.'}catch(e){const m=$('clm');if(m)m.textContent='Could not update clients.'}}
function lgShow(){$('lg').classList.add('on')}
async function login(){const u=$('lgu').value.trim(),p=$('lgp').value;try{if(await hp('login:'+u.toLowerCase()+':'+p)===LGH){LOK=true;try{sessionStorage.setItem('hisab_ok','1');if($('rm').checked)localStorage.setItem('hisab_rm',String(Date.now()+30*864e5))}catch(e){}lcHide('lg');$('lgp').value='';$('lge').textContent=''}else{$('lge').textContent='Wrong username or password.';lcBad('lg','lge')}}catch(e){$('lge').textContent='Cannot check the login on this browser.'}}
async function setLogin(){const u=$('lu').value.trim(),p=$('lp').value,m=$('lgm');if(u.length<3||p.length<4||p.length>12){m.textContent='Username: at least 3 characters. Password: 4 to 12 characters.';return}try{LGH=await hp('login:'+u.toLowerCase()+':'+p)}catch(e){m.textContent='Login does not work on this browser.';return}LGU=u;LOK=true;try{localStorage.setItem('hisab_lu',LGU);localStorage.setItem('hisab_lh',LGH);sessionStorage.setItem('hisab_ok','1')}catch(e){}$('lu').value='';$('lp').value='';saveSet();render();m.textContent='Login saved. The page will ask for it when it is opened fresh.'}
function rmLogin(){LGU='';LGH='';try{localStorage.removeItem('hisab_lu');localStorage.removeItem('hisab_lh')}catch(e){}saveSet();render();$('lgm').textContent='Login turned off.'}
function logout(){if(!LGH)return;ADMOK=false;LOK=false;try{sessionStorage.removeItem('hisab_ok');localStorage.removeItem('hisab_rm')}catch(e){}setTab('today');lgShow()}
function saveSet(){if(DB)DB.collection('data/users/'+UID).doc('settings').set({pin:PINH,phones:S.phones||{},pl:PL,lg:{u:LGU,h:LGH},clients:S.clients||[],rates:S.rates||{},brates:S.brates||{},low:S.low||0,shop:S.shop||{}}).catch(()=>{})}
async function setPin(){const v=$('np').value.trim();if(!/^.{4,12}$/.test(v)){$('pst').textContent='Password must be 4 to 12 characters.';return}try{PINH=await hp(v)}catch(e){$('pst').textContent='PIN lock does not work on this browser.';return}try{localStorage.setItem(PK,PINH)}catch(e){}$('np').value='';ADMOK=true;render();$('pst').textContent='Password saved. The Admin panel will ask for it from now on.';saveSet()}
async function rmPin(){PINH='';try{localStorage.removeItem(PK)}catch(e){}ADMOK=false;render();$('pst').textContent='Password removed. Set a new one to use the Admin panel.';saveSet()}
function wipe(){const b=$('wp');if(!wa){wa=true;b.textContent='Tap again to erase everything';return}wa=false;b.textContent='Erase all data';S.entries.forEach(e=>dirty.add(mon(e.date)));S.entries=[];save();render()}
function openCust(i){cust=CL[i]?CL[i][0]:null;render()}
function closeCust(){cust=null;render()}
function stmt(name){
  let bal=0;const lines=['Statement – '+name];
  S.entries.filter(e=>e.party===name&&(e.type==='sale_credit'||e.type==='collect'||e.type==='discount')).sort((a,b)=>a.date<b.date?-1:a.date>b.date?1:0).forEach(e=>{
    const cr=e.type==='sale_credit';bal+=cr?e.amt:-e.amt;
    lines.push(e.date+'  '+(cr?'Credit sale':(e.type==='discount'?'Discount':'Paid'))+(e.kg?' '+e.kg+' kg '+(e.kind||''):'')+(e.disc>0?' (after '+fmt(e.disc)+' discount)':'')+'  '+(cr?'':'−')+fmt(e.amt)+'  (due '+fmt(bal)+')');
  });
  lines.push('Total due: '+fmt(bal));return lines.join('\n');
}
function showCust(){
  const b=balOf(cust,'c'),pm=PM;PM='';
  $('credit').innerHTML='<button class="btn" onclick="closeCust()">‹ Back</button><h2 style="font-size:18px;margin:10px 0 0">'+esc(cust)+'</h2>'+(pm?'<p class="pos pop"><b>'+pm+'</b></p>':'')+(pay===cust&&payK==='c'?payForm(cust,'c'):(b>0?'<button class="add" onclick="togglePayCur()">Pay</button>':''))+phoneBox()+'<textarea id="stm" readonly style="min-height:200px">'+esc(stmt(cust))+'</textarea><button class="btn" onclick="copyStm()">Copy statement</button> <button class="btn" onclick="rcStmt(cust)">Print receipt</button><p id="cm" class="mut"></p><p class="mut">Paste it into WhatsApp to send to the customer.</p>';
}
function copyStm(){
  const ta=$('stm');ta.focus();ta.select();
  const ok=()=>{$('cm').textContent='Copied.'},no=()=>{$('cm').textContent='Text is selected. Press and hold, then tap Copy.'};
  const old=()=>{try{document.execCommand('copy')?ok():no()}catch(e){no()}};
  try{navigator.clipboard.writeText(ta.value).then(ok,old)}catch(e){old()}
}
function tg(){const t=$('type').value;const rl=$('rcl');if(rl)rl.hidden=STAFF;const ra=$('rca');if(ra)ra.checked=rcAutoOn();const bu=(t==='purchase'||t==='buy_credit');$('itw').hidden=!bu;$('ctw').hidden=t!=='expense';$('cw').hidden=(t==='collect'||t==='expense'||t==='pay_sup'||t==='cashout'||(bu&&$('item').value!=='chicken'));$('amt').hidden=(t==='loss');const dw=$('dw');if(dw){dw.hidden=STAFF||!(t==='sale_cash'||t==='sale_credit'||bu);if(dw.hidden){$('disc').value='';calcNet()}}}
function calc(){const t=$('type').value,k=parseFloat($('kg').value);let r=parseFloat($('rate').value);if(!(r>0)){const sr=rateFor(t,$('kind').value);if(sr>0&&!$('cw').hidden){r=sr;$('rate').value=sr;fx($('rate'),'fill')}}if(k>0&&r>0){$('amt').value=Math.round(k*r*100)/100;fx($('amt'),'fill')}else if(!(k>0)&&r>0&&parseFloat($('amt').value)>0)calcKg()}
function calcKg(){const t=$('type').value;if(!['sale_cash','sale_credit','purchase','buy_credit'].includes(t)||$('cw').hidden)return;let r=parseFloat($('rate').value);if(!(r>0)){const sr=rateFor(t,$('kind').value);if(sr>0&&!$('cw').hidden){r=sr;$('rate').value=sr;fx($('rate'),'fill')}}const a=parseFloat($('amt').value);if(a>0&&r>0){$('kg').value=Math.round(a/r*100)/100;fx($('kg'),'fill')}}

function calcNet(){const r=$('dnet'),v=$('dnv');if(!r||!v)return;const d=parseFloat($('disc').value),a=parseFloat($('amt').value);if(d>0&&a>0){r.hidden=false;v.textContent=fmt(Math.max(0,Math.round((a-d)*100)/100))}else r.hidden=true}
function sums(list){
  const r={sale_cash:0,sale_credit:0,collect:0,purchase:0,expense:0,loss:0,buy_credit:0,pay_sup:0,cashout:0,discount:0,disc_sup:0,sd:0,pd:0};
  list.forEach(e=>{r[e.type]+=e.amt;if(e.disc>0){if(e.type==='sale_cash'||e.type==='sale_credit')r.sd+=e.disc;else if(e.type==='purchase'||e.type==='buy_credit')r.pd+=e.disc}});
  r.sales=r.sale_cash+r.sale_credit;
  r.cashbuy=r.purchase;r.purchase+=r.buy_credit;r.cash=r.sale_cash+r.collect-r.cashbuy-r.expense-r.pay_sup-r.cashout;
  r.profit=r.sales-r.discount-r.purchase-r.expense+r.disc_sup;
  return r;
}
function tabFx(t){const s=$('t-'+t);if(!s||!s.classList)return;s.classList.remove('anim');void s.offsetWidth;s.classList.add('anim');clearTimeout(window.TFX);window.TFX=setTimeout(()=>s.classList.remove('anim'),900)}
function countUp(){try{if(matchMedia('(prefers-reduced-motion: reduce)').matches)return}catch(e){}if(typeof requestAnimationFrame!=='function')return;const els=$('sum').querySelectorAll('.kc b[data-n]');if(!els.length)return;const t0=performance.now(),D=800;(function f(t){const p=Math.min(1,Math.max(0,(t-t0)/D)),e=1-Math.pow(1-p,3);els.forEach(el=>{if(!el.isConnected)return;const n=parseFloat(el.dataset.n)||0;el.textContent=fmt(p<1?Math.round(n*e):n)});if(p<1)requestAnimationFrame(f)})(t0)}
if(document.addEventListener)document.addEventListener('pointerdown',e=>{const b=e.target&&e.target.closest&&e.target.closest('.add,.gbtn,.btn,nav button,.row button,#lq,#tb,#lb,.kc,.tile');if(!b||b.disabled)return;const r=b.getBoundingClientRect(),d=Math.max(r.width,r.height)*1.5,s=document.createElement('span');s.className='rp';s.style.cssText='width:'+d+'px;height:'+d+'px;left:'+(e.clientX-r.left-d/2)+'px;top:'+(e.clientY-r.top-d/2)+'px';b.appendChild(s);setTimeout(()=>s.remove(),650)});
function setTab(t){
  if((t==='backup'||t==='staff')&&PINH&&!ADMOK&&!STAFF){pend=t;lock(true);return}
  tab=t;if(t==='credit'){cust=null;pay=null;OVP=false;PM='';CQ='';const cqi=$('cq');if(cqi)cqi.value=''}ed=null;$('sv').textContent='Save entry';
  ['today','credit','hist','month','staff','backup'].forEach(k=>{$('t-'+k).hidden=k!==t;$('b-'+k).classList.toggle('on',k===t)});
  ANIM=true;render();tabFx(t);
}
function render(){
  $('lq').hidden=!(PINH||LGH)||STAFF;$('lq').innerHTML=ic(LGH?'logout':'lock',15)+' '+(LGH?'Log out':'Lock');
  if(tab==='today'){
    $('d').value=date;
    if(STAFF){renderStaff();return}
    const L=S.entries.filter(e=>e.date===date),r=sums(L);
    const cls=n=>n<0?'neg':'pos';
    const byd=(a,b)=>a.date<b.date?-1:a.date>b.date?1:0;
    const prev=S.entries.filter(e=>e.type==='count'&&e.date<date).sort(byd).pop();
    const open=(prev?prev.amt:0)+sums(S.entries.filter(e=>(!prev||e.date>prev.date)&&e.date<date)).cash;
    const cc=L.find(e=>e.type==='count'),ex=open+r.cash,co=Math.round(Math.max(0,Math.min(r.profit,ex))*100)/100;window.CO=co;window.RPT={r,ex};
    $('rb').value=(S.rates||{}).Broiler||'';$('rsn').value=(S.rates||{}).Sonali||'';$('brb').value=(S.brates||{}).Broiler||'';$('brsn').value=(S.brates||{}).Sonali||'';$('sl').value=S.low||'';{const sp=S.shop||{};$('shn').value=sp.n||'';$('sha').value=sp.a||'';$('shp').value=sp.p||'';$('shf').value=sp.f||''}
    {const es=S.entries.filter(e=>e.type!=='count'),bw=$('bkw'),dn=S.lastBackup?Math.floor((Date.now()-S.lastBackup)/864e5):-1;if(es.length>=5&&(dn<0||dn>=7)){bw.hidden=false;bw.innerHTML='<b class="neg">'+(dn<0?'No backup yet':'Last backup '+dn+' days ago')+'</b><br><button class="btn" onclick="setTab(\'backup\')">Open Admin to back up</button>'}else bw.hidden=true}
    const cashbox='<div style="margin-top:10px"><span class="l">Opening '+fmt(open)+' \u00b7 expected tonight '+fmt(ex)+'</span><div style="display:flex;gap:8px"><input id="cc" type="number" inputmode="decimal" placeholder="Cash counted \u09f3" value="'+(cc?cc.amt:'')+'"><button class="btn" style="white-space:nowrap" onclick="count()">Save count</button></div>'+(cc?'<b class="'+(cc.amt<ex-0.005?'neg':'pos')+'">'+(Math.abs(cc.amt-ex)<0.005?'Cash matches \u2713':(cc.amt<ex?'Short ':'Extra ')+fmt(Math.abs(cc.amt-ex)))+'</b>':'')+'<button class="btn" style="width:100%" onclick="cashOut()">Cash out today’s profit (up to '+fmt(co)+')</button><button class="btn" style="width:100%;margin-top:8px" onclick="copyReport()">Copy today’s report</button></div>';
    $('sum').innerHTML='<div class="kp">'+kc('g','cart','Total sales',r.sales)+kc('b','trending','Profit',r.profit)+kc('p','wallet','Cash in hand',ex)+kc('o','receipt','Customers owe you',due())+'</div><div class="big"><div><span class="l">Cash in hand</span><b class="'+cls(ex)+'">'+fmt(ex)+'</b></div><div><span class="l">Profit</span><b class="'+cls(r.profit)+'">'+fmt(r.profit)+'</b></div></div><div class="grid">'+
      [['Cash sales',r.sale_cash],['Credit sales',r.sale_credit],['Payments received',r.collect],['Purchases',r.purchase],['Expenses',r.expense],['Cash taken out',r.cashout]].concat((r.discount+r.sd)>0?[['Discount given',r.discount+r.sd]]:[],(r.disc_sup+r.pd)>0?[['Discount received',r.disc_sup+r.pd]]:[])
      .map(a=>'<div><span class="l">'+a[0]+'</span><b>'+fmt(a[1])+'</b></div>').join('')+'</div>'+cashbox;
    $('list').innerHTML='<b>Entries for this day</b>'+(L.length?L.slice().reverse().map(e=>
      '<div class="row'+(FLASH===e.id?' flash':'')+'"><div style="cursor:pointer" onclick="tgx(\''+e.id+'\')"><b>'+T[e.type]+'</b>'+(ITEM[e.item]?' · '+ITEM[e.item]:'')+(CAT[e.cat]?' · '+CAT[e.cat]:'')+(e.party?' – '+esc(e.party):'')+((e.kg||e.note)?'<br><small>'+(e.kg?esc(e.kind||'')+' '+e.kg+' kg'+(e.rate?' × ৳'+e.rate:'')+(e.note?' – ':''):'')+esc(e.note||'')+'</small>':'')+(e.disc>0?'<br><small class="mut"><span>Discount</span> '+fmt(e.disc)+'</small>':'')+(e.ts?'<br><small class="mut">🕒 '+hm(e.ts)+'</small>':'')+(EX===e.id?detail(e):'')+'</div><div class="amt">'+fmt(e.amt)+'</div>'+(rcCan(e)?'<button onclick="rcOpen(\''+e.id+'\')" aria-label="Receipt">'+ic('receipt',16)+'</button>':'')+(e.type==='count'||e.type==='discount'||e.type==='disc_sup'?'':'<button onclick="edit(\''+e.id+'\')" aria-label="Edit entry">'+ic('edit',16)+'</button>')+'<button onclick="del(\''+e.id+'\')" aria-label="Delete entry">'+ic('trash',16)+'</button></div>').join(''):'<p class="mut">Nothing saved for this day yet. Add your first entry above.</p>');
    const k={};
    S.entries.forEach(e=>{if(e.kg){const n=nk(e.kind);k[n]=(k[n]||0)+(e.type==='purchase'||e.type==='buy_credit'?e.kg:-e.kg)}});
    const tk=Object.values(k).reduce((a,b)=>a+b,0);$('stock').innerHTML='<b>Chicken stock (kg)</b>'+(S.low>0&&Object.keys(k).length&&tk<S.low?'<p class="neg"><b>Low stock · '+Math.round(tk*100)/100+' kg left</b></p>':'')+(Object.keys(k).length?Object.entries(k).map(x=>'<div class="row"><div>'+x[0]+'</div><div class="amt '+(x[1]<0?'neg':'')+'">'+Math.round(x[1]*100)/100+' kg</div></div>').join(''):'<p class="mut">Add kg to purchases and sales to see how much chicken is left.</p>')+'<p class="mut">Stock = bought − sold − lost. Count your real stock now and then.</p>';
    $('names').innerHTML=[...new Set(S.entries.map(e=>e.party).filter(Boolean))].map(n=>'<option value="'+esc(n)+'">').join('');
    if(ANIM){ANIM=false;countUp()}
  }else if(tab==='credit'){
    $('cqw').hidden=cust!==null;
    if(cust!==null){showCust();return}
    const m={};
    S.entries.forEach(e=>{
      if(e.type==='sale_credit')m[e.party]=(m[e.party]||0)+e.amt;
      if(e.type==='collect'||e.type==='discount')m[e.party]=(m[e.party]||0)-e.amt;
    });
    let a=Object.entries(m).filter(x=>Math.abs(x[1])>0.004).sort((x,y)=>(y[1]>0)-(x[1]>0)||ageOf(y[0])-ageOf(x[0])||y[1]-x[1]);
    const total=a.reduce((s,x)=>s+x[1],0);const cqv=CQ.trim().toLowerCase();a=a.filter(x=>!cqv||x[0].toLowerCase().includes(cqv));CL=a;
    const sm={};S.entries.forEach(e=>{if(e.type==='buy_credit')sm[e.party]=(sm[e.party]||0)+e.amt;if(e.type==='pay_sup'||e.type==='disc_sup')sm[e.party]=(sm[e.party]||0)-e.amt});
    const sa0=Object.entries(sm).filter(x=>Math.abs(x[1])>0.004),sa=sa0.filter(x=>!cqv||x[0].toLowerCase().includes(cqv));SA=sa;
    const sup='<p><b>You owe suppliers: '+fmt(sa0.reduce((s,x)=>s+x[1],0))+'</b></p>'+sa.map((x,i)=>'<div class="row"><div>'+esc(x[0])+'</div><div class="amt">'+fmt(x[1])+'</div><button class="pay" aria-label="Receipt" onclick="rcStmtS('+i+')">'+ic('receipt',14)+'</button>'+(x[1]>0?'<button class="pay'+(pay===x[0]&&payK==='s'?' on':'')+'" onclick="togglePay('+i+',\'s\')">Pay</button>':'')+'</div>'+(pay===x[0]&&payK==='s'&&x[1]>0?payForm(x[0],'s'):'')).join('');
    const pm=PM;PM='';$('credit').innerHTML=(pm?'<p class="pos pop"><b>'+pm+'</b></p>':'')+'<span class="l">Total to collect</span><b style="display:block;font-size:26px" class="'+(total>0?'neg':'pos')+'">'+fmt(total)+'</b>'+
      (a.length?a.map((x,i)=>'<div class="row" style="cursor:pointer" onclick="openCust('+i+')"><div>'+esc(x[0])+' <small>›</small>'+(x[1]>0?'<br><small class="'+(ageOf(x[0])>=15?'neg':'')+'">oldest due '+ageOf(x[0])+' days</small>':'')+'</div><div class="amt '+(x[1]>0?'neg':'pos')+'">'+fmt(x[1])+'</div><button class="pay" aria-label="Receipt" onclick="event.stopPropagation();rcStmtI('+i+')">'+ic('receipt',14)+'</button>'+(x[1]>0?'<button class="pay'+(pay===x[0]&&payK==='c'?' on':'')+'" onclick="event.stopPropagation();togglePay('+i+',\'c\')">Pay</button>':'')+'</div>'+(pay===x[0]&&payK==='c'&&x[1]>0?payForm(x[0],'c'):'')).join(''):(cqv?'<p class="mut">No customer found.</p>':'<p class="mut">No credit yet. Save a credit sale with a customer name and it will show here.</p>'))+
      sup+'<p class="mut">Red means they owe you. Green means they paid extra. Tap a name to see the full statement.</p>';
  }else if(tab==='hist'){
    const g={};
    S.entries.forEach(e=>{(g[e.date]=g[e.date]||[]).push(e)});
    const days=Object.keys(g).sort().reverse().slice(0,60);
    $('hist').innerHTML='<b>Past days</b>'+(days.length?days.map(d=>{
      const r=sums(g[d]);
      return '<div class="row" style="cursor:pointer" onclick="date=\''+d+'\';setTab(\'today\')"><div><b>'+d+'</b><br><small>Sales '+fmt(r.sales)+' · Spent '+fmt(r.purchase+r.expense)+'</small></div><div class="amt '+(r.profit<0?'neg':'pos')+'">'+fmt(r.profit)+'</div></div>';
    }).join(''):'<p class="mut">No days saved yet.</p>')+'<p class="mut">Tap a day to open it. The amount on the right is profit.</p>';
  }else if(tab==='month'){
    $('mp').value=mo;
    const L=S.entries.filter(e=>mon(e.date)===mo),r=sums(L);
    if(!L.length){$('month').innerHTML='<p class="mut">No entries in this month.</p>';return}
    const days=new Set(L.map(e=>e.date)).size,rd=n=>Math.round(n*100)/100,kk={};
    L.forEach(e=>{if(!e.kg)return;const n=nk(e.kind),o=kk[n]=kk[n]||{b:0,s:0,l:0};if(e.type==='purchase'||e.type==='buy_credit')o.b+=e.kg;else if(e.type==='loss')o.l+=e.kg;else o.s+=e.kg});
    const row=(a,b)=>'<div class="row"><div>'+a+'</div><div class="amt">'+b+'</div></div>';
    const pc={};L.forEach(e=>{if(e.type==='expense'){const k=CAT[e.cat]?e.cat:'other';pc[k]=(pc[k]||0)+e.amt}});const pi={};L.forEach(e=>{if(e.type==='purchase'||e.type==='buy_credit'){const k=ITEM[e.item]?e.item:'chicken';pi[k]=(pi[k]||0)+e.amt}});
    $('month').innerHTML='<div class="big"><div><span class="l">Profit</span><b class="'+(r.profit<0?'neg':'pos')+'">'+fmt(r.profit)+'</b></div><div><span class="l">Total sales</span><b>'+fmt(r.sales)+'</b></div></div>'+
      row('Cash sales',fmt(r.sale_cash))+row('Credit sales',fmt(r.sale_credit))+row('Payments received',fmt(r.collect))+row('Purchases',fmt(r.purchase))+row('Expenses',fmt(r.expense))+row('Cash taken out',fmt(r.cashout))+((r.discount+r.sd)>0?row('Discount given',fmt(r.discount+r.sd)):'')+((r.disc_sup+r.pd)>0?row('Discount received',fmt(r.disc_sup+r.pd)):'')+row('Days with entries',days)+(Object.keys(pc).length?'<p><b>Expenses by category</b></p>'+Object.entries(pc).map(x=>row(CAT[x[0]],fmt(x[1]))).join(''):'')+
      (Object.keys(pi).length?'<p><b>Purchases by item</b></p>'+Object.entries(pi).map(x=>row(ITEM[x[0]],fmt(x[1]))).join(''):'')+(Object.keys(kk).length?'<p><b>Chicken by kind (kg)</b></p>'+Object.entries(kk).map(x=>row(x[0],'bought '+rd(x[1].b)+' · sold '+rd(x[1].s)+' · lost '+rd(x[1].l))).join(''):'')+
      '<p class="mut">Profit = sales − purchases − expenses. Chicken still unsold is not counted as value.</p>';
  }else if(tab==='backup'){
    $('pst').textContent=PINH?'Password is ON.':'No password yet. Set one to open the Admin panel.';
    document.querySelectorAll('.gate,#adm2').forEach(e=>{e.hidden=!PINH});
    $('plb').textContent=PL?'Page lock on open: ON':'Page lock on open: OFF';$('lgs').textContent=LGH?'Login is ON for username: '+LGU:'Login is OFF.';drawClients();
    {const td=sums(S.entries.filter(e=>e.date===today())),mm=sums(S.entries.filter(e=>mon(e.date)===today().slice(0,7)));let cu=0,su=0;S.entries.forEach(e=>{if(e.type==='sale_credit')cu+=e.amt;if(e.type==='collect'||e.type==='discount')cu-=e.amt;if(e.type==='buy_credit')su+=e.amt;if(e.type==='pay_sup'||e.type==='disc_sup')su-=e.amt});const n=S.entries.filter(e=>e.type!=='count').length;$('astat').innerHTML=[['Today’s sales',fmt(td.sales)],['This month’s sales',fmt(mm.sales)],['This month’s profit',fmt(mm.profit)],['Customers owe you',fmt(cu)],['You owe suppliers',fmt(su)],['Entries saved',n]].map(x=>'<div class="sc"><span class="l">'+x[0]+'</span><b>'+x[1]+'</b></div>').join('')}
    const es=S.entries.filter(e=>e.type!=='count'),ds=es.map(e=>e.date).sort();
    $('dstat').textContent=es.length+' entries'+(ds.length?' from '+ds[0]+' to '+ds[ds.length-1]:'')+'.';
  }else if(tab==='staff'){loadStaff()}
}
function add(){
  const type=$('type').value,party=$('party').value.trim(),note=$('note').value.trim(),kg=parseFloat($('kg').value)||0,rate=parseFloat($('rate').value)||0,kind=$('kind').value;
  let amt=parseFloat($('amt').value);
  if(!(amt>0)&&kg>0&&rate>0)amt=Math.round(kg*rate*100)/100;
  const m=$('msg');m.textContent='';
  if(type==='loss'){if(!(kg>0)){m.textContent='Enter how many kg were lost.';return}amt=0}
  else if(!(amt>0)){m.textContent='Enter an amount, or kg and rate.';return}
  const dsc=$('dw').hidden?0:(parseFloat($('disc').value)||0);
  if(dsc>0){if(dsc>=amt){m.textContent='Discount must be less than the amount.';return}amt=Math.round((amt-dsc)*100)/100}
  if((type==='sale_credit'||type==='collect'||type==='buy_credit'||type==='pay_sup')&&!party){m.textContent='Enter the customer, hotel or supplier name.';return}
  const oi=ed?S.entries.findIndex(e=>e.id===ed):-1;
  const x={id:oi>=0?ed:Date.now().toString(36)+Math.random().toString(36).slice(2,5),date:oi>=0?S.entries[oi].date:date,type,party,note,amt};
  if(kg>0&&type!=='collect'&&type!=='expense'&&type!=='pay_sup'&&type!=='cashout'&&!((type==='purchase'||type==='buy_credit')&&$('item').value!=='chicken')){x.kg=kg;x.kind=kind;if(rate>0)x.rate=rate}
  if(type==='purchase'||type==='buy_credit')x.item=$('item').value;
  if(type==='expense')x.cat=$('cat').value;
  if(dsc>0)x.disc=Math.round(dsc*100)/100;
  if(oi>=0){const o=S.entries[oi];if(o.ts)x.ts=o.ts;if(o.by)x.by=o.by;if(o.ap)x.ap=o.ap;x.ed=Date.now()}else x.ts=Date.now();
  if(STAFF){sendStaff(x);return}
  if(oi>=0)S.entries[oi]=x;else S.entries.push(x);
  save(x.date);ed=null;$('sv').textContent='Save entry';
  $('amt').value='';$('kg').value='';$('rate').value='';$('note').value='';$('party').value='';$('disc').value='';calcNet();
  FLASH=x.id;render();FLASH='';fx($('sv'),'ok');stockMsg(x);
  if(oi<0&&rcAutoOn()&&(x.type==='sale_cash'||x.type==='sale_credit'||x.type==='collect'))rcOpen(x.id);
}
function del(id){const e=S.entries.find(x=>x.id===id);if(!e)return;S.entries=S.entries.filter(x=>x.id!==id);save(e.date);window.UNDO=e;clearTimeout(window.UT);window.UT=setTimeout(()=>{window.UNDO=null;$('undo').hidden=true},8000);$('undo').hidden=false;render()}
let CQ='';
function fx(el,c){if(!el||!el.classList)return;el.classList.remove(c);void el.offsetWidth;el.classList.add(c);setTimeout(()=>el.classList.remove(c),1000)}
try{new MutationObserver(()=>{const t=$('msg').textContent;if(/^(Enter|Discount must|Could not)/.test(t))fx($('addc'),'bad')}).observe($('msg'),{childList:true,characterData:true,subtree:true})}catch(e){}
function rcShowModel(M){RC=M;$('slip').innerHTML=RC.lines.map(rcHtml).join('');$('rcm').textContent=(S.shop&&S.shop.n)?'':B('Add your shop name in Admin to show it on receipts.');$('rc').classList.add('on');const w=$('rc');if(w)w.scrollTop=0}
function rcStmtI(i){if(CL[i])rcStmt(CL[i][0],'c')}
function rcStmtS(i){if(SA[i])rcStmt(SA[i][0],'s')}
function rcStmt(name,k){
  k=k||'c';const sh=S.shop||{},sup=k==='s',L=[];
  L.push({t:'t',s:sh.n||B('Amar Hisab')});if(sh.a)L.push({t:'s',s:sh.a});if(sh.p)L.push({t:'s',s:B('Phone')+': '+sh.p});
  L.push({t:'p'},{t:'h',s:B(sup?'Supplier statement':'Due statement')});
  L.push({t:'k',k:B('Date'),v:fdt(Date.now())},{t:'k',k:B(sup?'Supplier':'Customer'),v:name},{t:'p'});
  const up=sup?['buy_credit']:['sale_credit'],dn=sup?['pay_sup','disc_sup']:['collect','discount'];
  let bal=0;
  const rows=S.entries.filter(e=>e.party===name&&(up.includes(e.type)||dn.includes(e.type))).map((e,i)=>[e,i]).sort((a,b)=>a[0].date<b[0].date?-1:a[0].date>b[0].date?1:((a[0].ts||0)-(b[0].ts||0))||a[1]-b[1]).map(q=>{const e=q[0],cr=up.includes(e.type);bal+=cr?e.amt:-e.amt;return {e,cr}});
  bal=Math.round(bal*100)/100;
  if(rows.length>12)L.push({t:'n',s:(rows.length-12)+' '+B('earlier entries not shown')});
  rows.slice(-12).forEach(r=>{const e=r.e,lab=r.cr?B('Bill'):(e.type==='discount'||e.type==='disc_sup'?B('Discount'):B('Paid'));L.push({t:'i',s:e.date+' · '+lab+(e.kg?' · '+e.kg+' kg':''),v:(r.cr?'':'−')+fmt(e.amt)})});
  L.push({t:'p'});
  if(bal>0.004)L.push({t:'due',k:B('Total due now'),v:fmt(bal)});
  else if(bal<-0.004)L.push({t:'ok',s:B('Extra paid')+': '+fmt(-bal)});
  else L.push({t:'ok',s:B('Fully paid ✓')});
  L.push({t:'p'},{t:'f',s:sh.f||B('Thank you')});
  rcShowModel({no:(sup?'S':'D')+Date.now().toString(36).slice(-5).toUpperCase(),lines:L,shop:sh.n||''})}
function rateFor(t,kind){const buy=(t==='purchase'||t==='buy_credit'),sale=(t==='sale_cash'||t==='sale_credit');if(!buy&&!sale)return 0;return ((buy?S.brates:S.rates)||{})[kind]||0}
function stk(){const k={};S.entries.forEach(e=>{if(e.kg){const n=nk(e.kind);k[n]=(k[n]||0)+(e.type==='purchase'||e.type==='buy_credit'?e.kg:-e.kg)}});const tk=Object.values(k).reduce((a,b)=>a+b,0);return{k,tk,n:Object.keys(k).length}}
function stockMsg(x){const st=stk(),r2=n=>Math.round(n*100)/100;let t='';if((x.type==='purchase'||x.type==='buy_credit')&&x.kg>0)t='Stock updated: +'+r2(x.kg)+' kg '+nk(x.kind)+'. Total stock now '+r2(st.tk)+' kg.';if(S.low>0&&st.n&&st.tk<S.low)t+=(t?' ':'')+'Low stock: '+r2(st.tk)+' kg left.';if(t)$('msg').textContent=t}
function undoDel(){const e=window.UNDO;if(!e)return;S.entries.push(e);save(e.date);window.UNDO=null;$('undo').hidden=true;render()}
function nk(k){return {'ব্রয়লার':'Broiler','সোনালি':'Sonali','অন্য':'Other'}[k]||k||'Other'}
function saveRates(){const b=parseFloat($('rb').value)||0,s=parseFloat($('rsn').value)||0;S.rates={};if(b>0)S.rates.Broiler=b;if(s>0)S.rates.Sonali=s;const bb=parseFloat($('brb').value)||0,bs=parseFloat($('brsn').value)||0;S.brates={};if(bb>0)S.brates.Broiler=bb;if(bs>0)S.brates.Sonali=bs;S.low=parseFloat($('sl').value)||0;save();saveSet();$('rm2').textContent='Saved.'}
function copyReport(){const R=window.RPT;if(!R)return;const r=R.r,L=['Amar Hisab – '+date,'Total sales: '+fmt(r.sales)+' (cash '+fmt(r.sale_cash)+', credit '+fmt(r.sale_credit)+')','Payments received: '+fmt(r.collect),'Purchases: '+fmt(r.purchase),'Expenses: '+fmt(r.expense),'Profit: '+fmt(r.profit),'Cash in hand: '+fmt(R.ex),'Customers owe you: '+fmt(due())];if(r.cashout>0)L.splice(6,0,'Cash taken out: '+fmt(r.cashout));if(r.disc_sup+r.pd>0)L.splice(5,0,'Discount received: '+fmt(r.disc_sup+r.pd));if(r.discount+r.sd>0)L.splice(5,0,'Discount given: '+fmt(r.discount+r.sd));const t=L.join('\n'),m=$('msg');const old=()=>{const ta=document.createElement('textarea');ta.value=t;document.body.appendChild(ta);ta.select();let g=false;try{g=document.execCommand('copy')}catch(e){}ta.remove();m.textContent=g?'Report copied. Paste it in WhatsApp.':t};try{navigator.clipboard.writeText(t).then(()=>{m.textContent='Report copied. Paste it in WhatsApp.'},old)}catch(e){old()}}
function srch(){const q=$('q').value.trim().toLowerCase(),b=$('sr');if(!q){b.hidden=true;b.innerHTML='';return}const r=S.entries.filter(e=>e.type!=='count'&&((e.party||'')+' '+(e.note||'')+' '+(ITEM[e.item]||'')+' '+(CAT[e.cat]||'')).toLowerCase().includes(q)).sort((a,c)=>(c.date+String(c.ts||0))>(a.date+String(a.ts||0))?1:-1).slice(0,50);b.hidden=false;b.innerHTML='<p><b>'+r.length+' found</b></p>'+r.map(e=>'<div class="row"><div><b>'+T[e.type]+'</b>'+(e.party?' – '+esc(e.party):'')+'<br><small>'+esc(e.date)+(e.kg?' · '+e.kg+' kg':'')+(e.note?' · '+esc(e.note):'')+'</small></div><div class="amt">'+fmt(e.amt)+'</div></div>').join('')}
function showBackup(){S.lastBackup=Date.now();save();$('bk').value=JSON.stringify(S);$('bk').focus();$('bk').select()}
function restore(){
  const b=$('bmsg');
  try{
    const d=JSON.parse($('rs').value);
    if(!d||!Array.isArray(d.entries))throw 0;
    S={entries:d.entries.filter(e=>e&&e.date&&T[e.type]&&e.amt>=0),phones:d.phones||{},clients:d.clients||[],rates:d.rates||{},brates:d.brates||{},low:d.low||0,shop:d.shop||S.shop||{}};
    save();S.entries.forEach(e=>dirty.add(mon(e.date)));if(DB)push();$('rs').value='';b.textContent='Backup restored.';
  }catch(e){b.textContent='That text is not a valid backup.'}
}
let STAFF=false,UIDS=null,DBS=null,MY=[],PEND=[];
function phoneBox(){const p=(S.phones||{})[cust]||'',n=p.replace(/\D/g,''),w=n?(n.startsWith('880')?n:n.startsWith('0')?'88'+n:'880'+n):'';return '<div style="display:flex;gap:8px"><input id="ph" type="tel" inputmode="tel" placeholder="Phone number" value="'+esc(p)+'"><button class="btn" style="white-space:nowrap" onclick="savePhone()">Save</button></div>'+(w?'<p><a href="tel:+'+w+'">Call</a> · <a href="https://wa.me/'+w+'?text='+encodeURIComponent(stmt(cust))+'" target="_blank" rel="noopener">WhatsApp</a></p>':'')}
function savePhone(){S.phones=S.phones||{};S.phones[cust]=$('ph').value.trim();save();saveSet();render()}
async function loadMine(){try{const s=await DBS.collection('inbox/'+UIDS+'/items').get();MY=s.docs.map(d=>d.data()).filter(v=>v&&T[v.type]).sort((a,b)=>(b.ts||0)-(a.ts||0)).slice(0,30)}catch(e){MY=[]}renderStaff()}
function renderStaff(){const L={pending:'Waiting',approved:'Approved ✓',rejected:'Rejected'};$('list').innerHTML='<b>My sent entries</b>'+(MY.length?MY.map(v=>'<div class="row"><div><b>'+T[v.type]+'</b>'+(v.party?' – '+esc(v.party):'')+'<br><small>'+esc(v.date||'')+' · '+(L[v.status]||'')+'</small></div><div class="amt">'+fmt(Number(v.amt)||0)+'</div></div>').join(''):'<p class="mut">Nothing sent yet.</p>')+'<button class="btn" onclick="loadMine()">Refresh</button>'}
async function sendStaff(x){const m=$('msg'),nm=$('sn').value.trim();if(!nm){m.textContent='Enter your name first.';return}if(!DBS){m.textContent='Sign in to Claude to send entries.';return}try{localStorage.setItem('hisab_staff_name',nm)}catch(e){}x.by=nm;x.ts=Date.now();x.status='pending';try{await DBS.doc('inbox/'+UIDS).set({name:nm,t:x.ts});await DBS.doc('inbox/'+UIDS+'/items/'+x.id).set(x);['amt','kg','rate','note','party'].forEach(k=>{$(k).value=''});m.textContent='Sent. Waiting for the owner.';loadMine()}catch(e){m.textContent='Could not send. Check the internet, or ask the owner to share the page with you as Contributor.'}}
async function startStaff(u){STAFF=true;document.body.classList.add('staff');const cop=document.querySelector('#type option[value=cashout]');if(cop)cop.remove();$('lk').classList.remove('on');$('ttl').textContent='Staff entry';let db=null;try{db=await claude.use('db');UIDS=u?await u.id():null}catch(e){}if(!db||!UIDS){setSt('Sign in to Claude to send entries.');return}DBS=db;$('sn').hidden=false;try{$('sn').value=localStorage.getItem('hisab_staff_name')||''}catch(e){}setSt('Entries you send wait for the owner to approve them.');loadMine()}
async function loadStaff(){const sm=$('stmsg');if(!DB){$('staffbox').innerHTML='';sm.textContent='Staff entries need online saving. Open the page while signed in to Claude.';return}sm.textContent='Loading…';try{const us=await DB.collection('inbox').get(),out=[];for(const u of us.docs){if((S.clients||[]).some(c=>c.uid===u.id))continue;const it=await DB.collection('inbox/'+u.id+'/items').get();it.docs.forEach(d=>{const v=d.data();if(v&&v.status==='pending'&&T[v.type]&&v.type!=='count'&&v.type!=='cashout'&&v.type!=='discount'&&v.type!=='disc_sup'&&/^\d{4}-\d{2}-\d{2}$/.test(v.date||'')&&Number(v.amt)>=0)out.push({uid:u.id,did:d.id,v})})}PEND=out.sort((a,b)=>(a.v.ts||0)-(b.v.ts||0));drawStaff();sm.textContent=''}catch(e){sm.textContent='Could not load staff entries.'}}
function drawStaff(){$('staffbox').innerHTML=PEND.length?PEND.map((p,i)=>{const v=p.v;return '<div class="row"><div><b>'+esc(v.by||'Staff')+'</b> · '+esc(v.date)+(v.ts?' · 🕒 '+hm(v.ts):'')+'<br>'+T[v.type]+(ITEM[v.item]?' · '+ITEM[v.item]:'')+(v.party?' – '+esc(v.party):'')+(Number(v.kg)>0?' · '+Number(v.kg)+' kg '+esc(v.kind||''):'')+(v.note?'<br><small>'+esc(v.note)+'</small>':'')+'</div><div class="amt">'+fmt(Number(v.amt))+'</div><button onclick="decide('+i+',1)" aria-label="Approve">'+ic('check',18)+'</button><button onclick="decide('+i+',0)" aria-label="Reject">'+ic('x',18)+'</button></div>'}).join('')+'<button class="btn" onclick="approveAll()">Approve all</button>':'<p class="mut">No new entries from staff.</p>'}
async function decide(i,yes){const p=PEND[i];if(!p)return;try{await DB.doc('inbox/'+p.uid+'/items/'+p.did).update({status:yes?'approved':'rejected'});if(yes){const v=p.v,x={id:'s'+p.did,date:v.date,type:v.type,ts:Number(v.ts)||Date.now(),by:String(v.by||'staff').slice(0,30),ap:Date.now(),party:String(v.party||'').slice(0,60),note:(String(v.note||'').slice(0,100)+' [by '+String(v.by||'staff').slice(0,30)+']').trim(),amt:Number(v.amt)};if(ITEM[v.item]&&(v.type==='purchase'||v.type==='buy_credit'))x.item=v.item;if(CAT[v.cat]&&v.type==='expense')x.cat=v.cat;if(Number(v.kg)>0&&(!x.item||x.item==='chicken')){x.kg=Number(v.kg);x.kind=String(v.kind||'Other').slice(0,20);if(Number(v.rate)>0)x.rate=Number(v.rate)}if(!S.entries.some(e=>e.id===x.id)){S.entries.push(x);save(x.date)}}PEND.splice(i,1);drawStaff()}catch(e){$('stmsg').textContent='Could not update. Try again.'}}
async function approveAll(){for(let i=PEND.length-1;i>=0;i--)await decide(i,1)}
let LANG='en';try{LANG=localStorage.getItem('hisab_lang')||'en'}catch(e){}
const BN={'Rates and stock alert':'রেট ও স্টক সতর্কতা','Sell rate: Broiler':'বিক্রির রেট: ব্রয়লার','Sell rate: Sonali':'বিক্রির রেট: সোনালি','Buy rate: Broiler':'কেনার রেট: ব্রয়লার','Buy rate: Sonali':'কেনার রেট: সোনালি','Buy rates fill in when you buy chicken (cash or credit). Type only the amount and the kg is worked out and added to stock.':'মুরগি কেনার সময় (নগদ বা বাকি) কেনার রেট নিজে বসে যায়। শুধু টাকা লিখলেই কেজি হিসাব হয়ে স্টকে যোগ হবে।','Due statement':'বাকির হিসাব','Supplier statement':'সাপ্লায়ারের হিসাব','Supplier':'সাপ্লায়ার','Bill':'বিল','Paid':'জমা','earlier entries not shown':'টি আগের এন্ট্রি দেখানো হয়নি','Print receipt':'রশিদ প্রিন্ট করুন','Search customer or supplier name':'কাস্টমার বা সাপ্লায়ারের নাম খুঁজুন','No customer found.':'কাউকে পাওয়া যায়নি।','Copy today’s report':'আজকের রিপোর্ট কপি করুন','Sale rates and stock alert':'বিক্রির রেট ও স্টক সতর্কতা','Search a name or note':'নাম বা নোট খুঁজুন','Broiler rate':'ব্রয়লারের রেট','Sonali rate':'সোনালির রেট','Alert when stock is below (kg)':'এর নিচে স্টক নামলে জানান (কেজি)','Entry deleted.':'এন্ট্রি মুছে গেছে।','Undo':'ফেরান','Rent':'ভাড়া','Labour':'শ্রমিক','Ice':'বরফ','Transport':'পরিবহন','Electricity':'বিদ্যুৎ','Other expense':'অন্যান্য খরচ','Expenses by category':'খাত অনুযায়ী খরচ','Category':'খাত','Expense category':'খরচের খাত','No backup yet':'এখনও ব্যাকআপ নেওয়া হয়নি','Open Admin to back up':'ব্যাকআপ নিতে Admin খুলুন','Client login':'ক্লায়েন্ট লগইন','Client panel':'ক্লায়েন্ট প্যানেল','Link my account':'আমার অ্যাকাউন্ট যুক্ত করুন','Check again':'আবার দেখুন','Statement':'হিসাব','Switch role':'ভূমিকা বদলান','Total due':'মোট বাকি','Payment':'জমা','WHO ARE YOU?':'আপনি কে?','I am staff':'আমি কর্মী','I am a client':'আমি ক্লায়েন্ট','Add client':'ক্লায়েন্ট যোগ','Link and update':'যুক্ত ও আপডেট','Amar Hisab':'আমার হিসাব','Admin Panel':'অ্যাডমিন প্যানেল','Admin panel':'অ্যাডমিন প্যানেল','Login security':'লগইন সিকিউরিটি','ENTER PASSWORD':'পাসওয়ার্ড দিন','🔒 Admin Panel':'🔒 অ্যাডমিন প্যানেল','ADMIN LOGIN':'অ্যাডমিন লগইন','Login':'লগইন','Save this phone for 30 days':'এই ফোন ৩০ দিন মনে রাখুন','Date':'তারিখ','Entered':'এন্ট্রির সময়','Type':'ধরন','Item':'আইটেম','Name':'নাম','Kind':'জাত','Weight':'ওজন','Amount':'টাকা','Note':'নোট','Entered by':'কে লিখেছে','Approved':'অনুমোদনের সময়','Last edited':'শেষ এডিট','Chicken':'মুরগি','Feed':'খাবার','Medicine':'ওষুধ','Vaccine':'টিকা','Chicks':'বাচ্চা মুরগি','Other cost':'অন্যান্য','Purchase (chicken, feed, medicine, etc.)':'কেনা (মুরগি, খাবার, ওষুধ ইত্যাদি)','Purchases by item':'আইটেম অনুয়ায়ী কেনা','Purchase item':'কেনার আইটেম','Cash taken out':'ক্যাশ আউট (তোলা টাকা)','Owner cash out':'মালিকের ক্যাশ আউট','Owner cash out (take money out)':'মালিকের ক্যাশ আউট (টাকা তোলা)','Switch to light mode':'লাইট মোডে যান','Switch to dark mode':'ডার্ক মোডে যান','Log out':'লগআউট','Lock':'লক','Log out now':'এখনই লগআউট','Shop login':'দোকানের লগইন','Log in':'লগইন','Username':'ইউজারনেম','Enter your username and password to open the accounts.':'হিসাব খুলতে ইউজারনেম ও পাসওয়ার্ড দিন।','Wrong username or password.':'ইউজারনেম বা পাসওয়ার্ড ভুল।','🔐 Login security':'🔐 লগইন সিকিউরিটি','Save login':'লগইন সেভ','Turn off login':'লগইন বন্ধ','New username':'নতুন ইউজারনেম','Password':'পাসওয়ার্ড','Save password':'পাসওয়ার্ড সেভ','Remove password':'পাসওয়ার্ড বাদ','🛡️ Admin panel':'🛡️ অ্যাডমিন প্যানেল','🔒 Enter password':'🔒 পাসওয়ার্ড দিন','New password (4 to 12 characters)':'নতুন পাসওয়ার্ড (৪ থেকে ১২ অক্ষর)','Today’s sales':'আজকের বিক্রি','This month’s sales':'এই মাসের বিক্রি','This month’s profit':'এই মাসের লাভ','Customers owe you':'কাস্টমারের কাছে পাবেন','You owe suppliers':'সাপ্লায়ারকে দিতে হবে','Entries saved':'মোট এন্ট্রি','Lock now':'এখনই লক করুন','Cancel':'বাতিল','Pay':'পরিশোধ','Full amount':'পুরো টাকা','Save payment':'পরিশোধ সেভ করুন','Amount received ৳':'পাওয়া টাকা ৳','Payment saved ✓':'পরিশোধ সেভ হয়েছে ✓','Rest as discount':'বাকিটা ডিসকাউন্ট (ছাড়)','Discount':'ডিসকাউন্ট','Discount given':'ডিসকাউন্ট দেওয়া','Discount received':'ডিসকাউন্ট পাওয়া','Discount ৳ (optional)':'ডিসকাউন্ট ৳ (ইচ্ছা হলে)','After discount':'ডিসকাউন্টের পর','Discount must be less than the amount.':'ডিসকাউন্ট টাকার চেয়ে কম হতে হবে।','Total to pay':'মোট দিতে হবে','Amount paid ৳':'দেওয়া টাকা ৳','Enter the amount paid.':'কত টাকা দিয়েছেন তা লিখুন।','Admin password to confirm':'নিশ্চিত করতে অ্যাডমিন পাসওয়ার্ড','Enter the admin password to confirm.':'নিশ্চিত করতে অ্যাডমিন পাসওয়ার্ড দিন।','Wrong password.':'পাসওয়ার্ড ভুল।','Cannot check the PIN on this browser.':'এই ব্রাউজারে পাসওয়ার্ড যাচাই করা যাচ্ছে না।','Enter the amount received.':'কত টাকা পেয়েছেন তা লিখুন।','This is more than the due. Tap Save payment again to confirm.':'এটা বাকির চেয়ে বেশি। নিশ্চিত করতে আবার "পরিশোধ সেভ করুন" চাপুন।','Today':'আজ','Credit':'বাকি','Days':'দিন','Month':'মাস','Staff':'কর্মী','Admin':'অ্যাডমিন','Daily Hisab':'দৈনিক হিসাব','Staff entry':'কর্মীর এন্ট্রি','Add an entry':'এন্ট্রি যোগ করুন','Cash sale':'নগদ বিক্রি','Credit sale (due later)':'বাকি বিক্রি (পরে পাবেন)','Credit sale':'বাকি বিক্রি','Payment received':'টাকা পেয়েছি','Purchase (chickens, feed)':'কেনা (মুরগি, খাবার)','Purchase':'কেনা','Expense (rent, labour, ice, transport)':'খরচ (ভাড়া, শ্রমিক, বরফ, গাড়ি)','Expense':'খরচ','Purchase on credit (you owe supplier)':'বাকিতে কেনা (সাপ্লায়ারকে দেবেন)','Credit purchase':'বাকিতে কেনা','Paid money to supplier':'সাপ্লায়ারকে টাকা দিলাম','Paid supplier':'সাপ্লায়ারকে দেওয়া','Dead or lost chicken (kg only)':'মরা বা নষ্ট মুরগি (শুধু কেজি)','Dead or lost':'মরা বা নষ্ট','Cash counted':'গোনা ক্যাশ','Broiler':'ব্রয়লার','Sonali':'সোনালি','Other':'অন্য','Save entry':'এন্ট্রি সেভ করুন','Update entry':'এন্ট্রি আপডেট করুন','Cash in hand':'হাতে ক্যাশ','Profit':'লাভ','Cash sales':'নগদ বিক্রি (মোট)','Credit sales':'বাকি বিক্রি (মোট)','Payments received':'টাকা পাওয়া','Purchases':'মোট কেনা','Expenses':'মোট খরচ','Total sales':'মোট বিক্রি','Save count':'ক্যাশ গোনা সেভ','Chicken stock (kg)':'মুরগির স্টক (কেজি)','Entries for this day':'এই দিনের এন্ট্রি','Total to collect':'মোট পাবেন','Past days':'আগের দিনগুলো','Save PIN':'পিন সেভ','Remove PIN':'পিন বাদ','Erase all data':'সব ডেটা মুছুন','Erase everything':'সব মুছে ফেলা','Show my backup':'ব্যাকআপ দেখান','Restore backup':'ব্যাকআপ ফেরত আনুন','Copy statement':'হিসাব কপি করুন','‹ Back':'‹ ফিরুন','Unlock':'খুলুন','Refresh':'রিফ্রেশ','Save':'সেভ','Call':'কল','Approve all':'সব অনুমোদন করুন','Check for new entries':'নতুন এন্ট্রি দেখুন','Staff entries waiting':'কর্মীদের পাঠানো এন্ট্রি','My sent entries':'আমার পাঠানো এন্ট্রি','How to add a staff member':'কর্মী যোগ করার নিয়ম','No new entries from staff.':'কর্মীদের কোনো নতুন এন্ট্রি নেই।','Waiting':'অপেক্ষায়','Approved ✓':'অনুমোদিত ✓','Rejected':'বাতিল','Days with entries':'এন্ট্রি আছে এমন দিন','Chicken by kind (kg)':'ধরন অনুযায়ী মুরগি (কেজি)','🔒 Enter PIN':'🔒 পিন দিন','Cash matches ✓':'ক্যাশ মিলেছে ✓','Nothing sent yet.':'এখনও কিছু পাঠানো হয়নি।','Admin':'অ্যাডমিন','Customer or hotel (needed for credit)':'কাস্টমার বা হোটেল (বাকির জন্য দরকার)','Note (optional)':'নোট (ইচ্ছা হলে)','Kg':'কেজি','Rate ৳ per kg':'রেট ৳ প্রতি কেজি','Total amount ৳ (auto from kg × rate)':'মোট টাকা ৳ (কেজি × রেট থেকে নিজে হবে)','Phone number':'ফোন নম্বর','Your name':'আপনার নাম','Cash counted ৳':'গোনা ক্যাশ ৳','New PIN (4 to 8 digits)':'নতুন পিন (৪ থেকে ৮ সংখ্যা)','PIN':'পিন','Paste backup here':'এখানে ব্যাকআপ পেস্ট করুন','Enter your name first.':'আগে আপনার নাম লিখুন।','Sent. Waiting for the owner.':'পাঠানো হয়েছে। মালিকের অনুমোদনের অপেক্ষায়।','Enter an amount, or kg and rate.':'টাকা লিখুন, অথবা কেজি আর রেট লিখুন।','Wrong PIN.':'ভুল পিন।','No credit yet. Save a credit sale with a customer name and it will show here.':'এখনও বাকি নেই। কাস্টমারের নামসহ বাকি বিক্রি সেভ করলে এখানে দেখাবে।','Nothing saved for this day yet. Add your first entry above.':'এই দিনের কিছু সেভ হয়নি। উপরে প্রথম এন্ট্রি যোগ করুন।','Saved online ✓':'অনলাইনে সেভ হয়েছে ✓','Saved on this phone only.':'শুধু এই ফোনে সেভ আছে।','Saving online…':'অনলাইনে সেভ হচ্ছে…','Entries you send wait for the owner to approve them.':'আপনার পাঠানো এন্ট্রি মালিক অনুমোদন করলে হিসাবে যাবে।'};
const BNR=[[/^Stock updated: \+(.*) kg (.*)\. Total stock now (.*) kg\. Low stock: (.*) kg left\.$/,'স্টকে যোগ হয়েছে: +$1 কেজি $2। মোট স্টক এখন $3 কেজি। স্টক কম: $4 কেজি আছে।'],[/^Stock updated: \+(.*) kg (.*)\. Total stock now (.*) kg\.$/,'স্টকে যোগ হয়েছে: +$1 কেজি $2। মোট স্টক এখন $3 কেজি।'],[/^Low stock: (.*) kg left\.$/,'স্টক কম: $1 কেজি আছে।'],[/^Low stock · (.*) kg left$/,'স্টক কম · $1 কেজি আছে'],[/^Last backup (\d+) days ago$/,'শেষ ব্যাকআপ $1 দিন আগে'],[/^(\d+) found$/,'$1 টি পাওয়া গেছে'],[/^Cash out today’s profit \(up to (.*)\)$/,'আজকের লাভ ক্যাশ আউট (সর্বোচ্চ $1)'],[/^oldest due (\d+) days$/,'সবচেয়ে পুরনো বাকি $1 দিন'],[/^Opening (.*) · expected tonight (.*)$/,'শুরুর ক্যাশ $1 · আজ রাতে থাকার কথা $2'],[/^Short (.*)$/,'কম $1'],[/^Extra (.*)$/,'বেশি $1'],[/^You owe suppliers: (.*)$/,'সাপ্লায়ারকে দিতে হবে: $1'],[/^bought (.*) · sold (.*) · lost (.*)$/,'কেনা $1 · বিক্রি $2 · নষ্ট $3'],[/^Stock = bought/,'স্টক = কেনা'],[/^Statement /,'']];

/* ---- receipt ---- */
function B(s){return LANG==='bn'&&BN[s]?BN[s]:s}
let RC=null;
function rcAutoOn(){try{return localStorage.getItem('hisab_rca')!=='0'}catch(e){return true}}
function rcAutoSet(v){try{localStorage.setItem('hisab_rca',v?'1':'0')}catch(e){}}
function saveShop(){S.shop={n:$('shn').value.trim(),a:$('sha').value.trim(),p:$('shp').value.trim(),f:$('shf').value.trim()};save();saveSet();$('shm').textContent=B('Saved.')}
function rcPair(e){
  if(e.type==='collect'){const d=S.entries.find(x=>x.type==='discount'&&x.party===e.party&&(x.lk===e.id||(!x.lk&&x.date===e.date&&x.ts&&e.ts&&x.ts>e.ts&&x.ts-e.ts<=5)));return d||null}
  if(e.type==='discount'){const c=S.entries.find(x=>x.type==='collect'&&x.party===e.party&&(e.lk===x.id||(!e.lk&&x.date===e.date&&x.ts&&e.ts&&e.ts>x.ts&&e.ts-x.ts<=5)));return c||null}
  return null}
function rcCan(e){return e.type==='sale_cash'||e.type==='sale_credit'||e.type==='collect'||(e.type==='discount'&&!rcPair(e))}
function rcBal(party,id){
  const L=S.entries.filter(x=>x.party===party&&(x.type==='sale_credit'||x.type==='collect'||x.type==='discount')).map((x,i)=>[x,i]).sort((a,b)=>a[0].date<b[0].date?-1:a[0].date>b[0].date?1:((a[0].ts||0)-(b[0].ts||0))||a[1]-b[1]);
  let b=0;for(const q of L){const x=q[0];b+=x.type==='sale_credit'?x.amt:-x.amt;if(x.id===id)break}return Math.round(b*100)/100}
function rcModel(e){
  const sh=S.shop||{},no=String(e.id).slice(-6).toUpperCase(),when=e.ts?fdt(e.ts):e.date,L=[];
  L.push({t:'t',s:sh.n||B('Amar Hisab')});if(sh.a)L.push({t:'s',s:sh.a});if(sh.p)L.push({t:'s',s:B('Phone')+': '+sh.p});
  const sale=e.type==='sale_cash'||e.type==='sale_credit';
  L.push({t:'p'});
  L.push({t:'h',s:B(sale?(e.type==='sale_cash'?'Cash receipt':'Credit memo'):'Payment receipt')});
  L.push({t:'k',k:B('Receipt no'),v:'#'+no},{t:'k',k:B('Date'),v:when});
  if(e.party)L.push({t:'k',k:B('Customer'),v:e.party});
  L.push({t:'p'});
  if(sale){
    const dsc=e.disc>0?e.disc:0,gross=Math.round((e.amt+dsc)*100)/100;
    const d=e.kg?[B(nk(e.kind)),e.kg+' kg',e.rate?'× '+fmt(e.rate):''].filter(Boolean).join(' '):(e.note||B('Sale'));
    L.push({t:'i',s:d,v:fmt(gross)});
    if(e.kg&&e.note)L.push({t:'n',s:e.note});
    if(dsc)L.push({t:'k',k:B('Discount'),v:'−'+fmt(dsc)});
    L.push({t:'tt',k:B(e.type==='sale_cash'?'Total':'This bill'),v:fmt(e.amt)});
    if(e.type==='sale_credit'){const after=rcBal(e.party,e.id),prev=Math.round((after-e.amt)*100)/100;if(Math.abs(prev)>0.004)L.push({t:'k',k:B('Previous due'),v:fmt(prev)});L.push({t:'due',k:B('Total due now'),v:fmt(after)})}
  }else{
    const pay=e.type==='collect'?e:null,dis=e.type==='collect'?rcPair(e):e,paid=pay?pay.amt:0,dd=dis?dis.amt:0,last=dis||pay,after=rcBal(e.party,last.id),before=Math.round((after+paid+dd)*100)/100;
    L.push({t:'k',k:B('Due before'),v:fmt(before)});
    if(dd>0)L.push({t:'k',k:B('Discount'),v:'−'+fmt(dd)});
    L.push(paid>0?{t:'tt',k:B('Received'),v:fmt(paid)}:{t:'tt',k:B('Discount allowed'),v:fmt(dd)});
    if(after>0.004)L.push({t:'due',k:B('Remaining due'),v:fmt(after)});
    else if(after<-0.004)L.push({t:'ok',s:B('Extra paid')+': '+fmt(-after)});
    else L.push({t:'ok',s:B('Fully paid ✓')});
  }
  L.push({t:'p'});L.push({t:'f',s:sh.f||B('Thank you')});
  return {no,lines:L,shop:sh.n||''}}
function rcHtml(l){const e=esc;switch(l.t){
  case 't':return '<p class="st">'+e(l.s)+'</p>';
  case 's':return '<p class="ss">'+e(l.s)+'</p>';
  case 'n':return '<p class="ss" style="text-align:left">'+e(l.s)+'</p>';
  case 'h':return '<p class="sh">'+e(l.s)+'</p>';
  case 'p':return '<div class="sp"></div>';
  case 'k':return '<div class="sk"><span>'+e(l.k)+'</span><b>'+e(l.v)+'</b></div>';
  case 'i':return '<div class="si"><span>'+e(l.s)+'</span><b>'+e(l.v)+'</b></div>';
  case 'tt':return '<div class="stt"><span>'+e(l.k)+'</span><span>'+e(l.v)+'</span></div>';
  case 'due':return '<div class="due"><span>'+e(l.k)+'</span><span>'+e(l.v)+'</span></div>';
  case 'ok':return '<div class="due okk"><span>'+e(l.s)+'</span></div>';
  case 'f':return '<p class="sf">'+e(l.s)+'</p>'}return ''}
function rcOpen(id){
  let e=S.entries.find(x=>x.id===id);if(!e)return;
  if(e.type==='discount'){const c=rcPair(e);if(c)e=c}
  RC=rcModel(e);
  $('slip').innerHTML=RC.lines.map(rcHtml).join('');
  $('rcm').textContent=(S.shop&&S.shop.n)?'':B('Add your shop name in Admin to show it on receipts.');
  $('rc').classList.add('on');const w=$('rc');if(w)w.scrollTop=0}
function rcClose(){$('rc').classList.remove('on')}
function rcPrint(){try{window.print()}catch(e){}}
function rcCanvas(R){
  const W=380,P=22,M=16,SC=2,IW=W-2*P,INK='#1c1b1a',MUT='#6b665c',LINE='#c9c3b5',TH=5,
    F=(w,s)=>w+' '+s+'px system-ui,-apple-system,"Segoe UI","Noto Sans Bengali","Hind Siliguri",sans-serif',
    c=document.createElement('canvas'),x=c.getContext('2d'),ops=[],L0=M+P,R0=M+W-P,XC=M+W/2;
  let y=M+TH+24;
  const fit=(t,w,f)=>{x.font=f;const out=[];String(t).split('\n').forEach(par=>{let cur='';par.split(' ').forEach(word=>{let wd=word;while(x.measureText(wd).width>w&&wd.length>1){let k=wd.length;while(k>1&&x.measureText(wd.slice(0,k)).width>w)k--;if(cur){out.push(cur);cur=''}out.push(wd.slice(0,k));wd=wd.slice(k)}const tst=cur?cur+' '+wd:wd;if(!cur||x.measureText(tst).width<=w)cur=tst;else{out.push(cur);cur=wd}});out.push(cur)});return out};
  const txt=(s,xx,yy,f,col,al,ls)=>ops.push(()=>{x.font=f;x.fillStyle=col;x.textAlign=al;x.textBaseline='alphabetic';try{x.letterSpacing=ls||'0px'}catch(e){}x.fillText(s,xx,yy);try{x.letterSpacing='0px'}catch(e){}});
  const rr=(xx,yy,w,hh,r,col)=>ops.push(()=>{x.fillStyle=col;x.beginPath();x.moveTo(xx+r,yy);x.arcTo(xx+w,yy,xx+w,yy+hh,r);x.arcTo(xx+w,yy+hh,xx,yy+hh,r);x.arcTo(xx,yy+hh,xx,yy,r);x.arcTo(xx,yy,xx+w,yy,r);x.closePath();x.fill()});
  R.lines.forEach(l=>{
    if(l.t==='t'){const f=F('800',20);fit(l.s,IW,f).forEach(s=>{y+=26;txt(s,XC,y,f,INK,'center')});y+=4}
    else if(l.t==='s'){const f=F('400',12.5);fit(l.s,IW,f).forEach(s=>{y+=17;txt(s,XC,y,f,MUT,'center')})}
    else if(l.t==='n'){const f=F('400',12.5);fit(l.s,IW,f).forEach(s=>{y+=17;txt(s,L0,y,f,MUT,'left')})}
    else if(l.t==='h'){y+=22;txt(l.s,XC,y,F('700',12.5),INK,'center','2px');y+=6}
    else if(l.t==='p'){y+=10;const yy=y;ops.push(()=>{x.strokeStyle=LINE;x.lineWidth=1.2;x.setLineDash([6,4]);x.beginPath();x.moveTo(L0,yy);x.lineTo(R0,yy);x.stroke();x.setLineDash([])});y+=12}
    else if(l.t==='k'){const fk=F('400',14),fv=F('700',14);x.font=fk;const kw=x.measureText(l.k).width+14,vl=fit(l.v,IW-kw,fv);y+=20;txt(l.k,L0,y,fk,MUT,'left');vl.forEach((s,i)=>txt(s,R0,y+i*20,fv,INK,'right'));y+=(vl.length-1)*20+2}
    else if(l.t==='i'){const fd=F('500',14.5),fv=F('700',14.5),dl=fit(l.s,IW*0.64,fd);y+=21;dl.forEach((s,i)=>txt(s,L0,y+i*20,fd,INK,'left'));txt(l.v,R0,y,fv,INK,'right');y+=(dl.length-1)*20+3}
    else if(l.t==='tt'){y+=10;y+=24;const f=F('800',19);txt(l.k,L0,y,f,INK,'left');txt(l.v,R0,y,f,INK,'right');y+=6}
    else if(l.t==='due'||l.t==='ok'){y+=8;const top=y,hh=34,ok=l.t==='ok',col=ok?'#0f6b45':'#a1242f';rr(L0,top,IW,hh,9,ok?'#e5f5ec':'#fdecee');const f=F('700',14.5);if(ok)txt(l.s,XC,top+22,f,col,'center');else{txt(l.k,L0+11,top+22,f,col,'left');txt(l.v,R0-11,top+22,f,col,'right')}y+=hh}
    else if(l.t==='f'){const f=F('400',13);fit(l.s,IW,f).forEach(s=>{y+=18;txt(s,XC,y,f,MUT,'center')})}
  });
  const bot=y+22,n=Math.round(W/10),st=W/n;
  c.width=(W+2*M)*SC;c.height=(bot+M+6)*SC;x.scale(SC,SC);
  x.fillStyle='#ebe7dc';x.fillRect(0,0,W+2*M,bot+M+6);
  x.save();x.shadowColor='rgba(0,0,0,.2)';x.shadowBlur=14;x.shadowOffsetY=3;x.fillStyle='#fffdf7';
  x.beginPath();x.moveTo(M,M);for(let i=0;i<n;i++){x.lineTo(M+st*(i+.5),M+TH);x.lineTo(M+st*(i+1),M)}x.lineTo(M+W,bot);for(let i=n-1;i>=0;i--){x.lineTo(M+st*(i+.5),bot-TH);x.lineTo(M+st*i,bot)}x.closePath();x.fill();x.restore();
  ops.forEach(f=>f());
  return c}
function rcBlob(){return new Promise(res=>{try{rcCanvas(RC).toBlob(b=>res(b),'image/png')}catch(e){res(null)}})}
function rcSave(b){const a=document.createElement('a');a.href=URL.createObjectURL(b);a.download='receipt-'+RC.no+'.png';document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(a.href),4000)}
async function rcDl(){const m=$('rcm');if(!RC)return;const b=await rcBlob();if(!b){m.textContent=B('Could not make the image.');return}rcSave(b);m.textContent=B('Receipt saved as image.')}
async function rcShare(){const m=$('rcm');if(!RC)return;const b=await rcBlob();if(!b){m.textContent=B('Could not make the image.');return}
  const f=new File([b],'receipt-'+RC.no+'.png',{type:'image/png'});
  try{if(navigator.canShare&&navigator.canShare({files:[f]})){await navigator.share({files:[f],title:RC.shop||B('Receipt')});return}}catch(e){if(e&&e.name==='AbortError')return}
  rcSave(b);m.textContent=B('Sharing is not supported here, so the image was downloaded.')}
if(document.addEventListener)document.addEventListener('keydown',e=>{if(e.key==='Escape'){const r=$('rc');if(r&&r.classList&&r.classList.contains('on'))rcClose()}});
(function(){const X={'Cash receipt':'নগদ রশিদ','Credit memo':'বাকির রশিদ','Payment receipt':'পরিশোধের রশিদ','Receipt no':'রশিদ নং','Customer':'কাস্টমার','Total':'মোট','This bill':'এই বিলের মোট','Previous due':'আগের বাকি','Total due now':'মোট বাকি এখন','Due before':'আগে বাকি ছিল','Received':'পাওয়া গেছে','Remaining due':'এখনও বাকি','Fully paid ✓':'সম্পূর্ণ পরিশোধ ✓','Extra paid':'বেশি দিয়েছেন','Discount allowed':'ডিসকাউন্ট দেওয়া হয়েছে','Thank you':'ধন্যবাদ','Phone':'ফোন','Sale':'বিক্রি','Share receipt':'রশিদ শেয়ার করুন','Print':'প্রিন্ট','Save image':'ছবি সেভ করুন','Close':'বন্ধ করুন','Receipt':'রশিদ','Shop details for receipt':'রশিদের জন্য দোকানের তথ্য','Shop name':'দোকানের নাম','Address':'ঠিকানা','Phone number':'ফোন নম্বর','Message at the bottom (e.g. Thank you)':'নিচের লেখা (যেমন: ধন্যবাদ)','Show receipt after saving':'সেভের পর রশিদ দেখান','Saved.':'সেভ হয়েছে।','Receipt saved as image.':'রশিদের ছবি সেভ হয়েছে।','Sharing is not supported here, so the image was downloaded.':'এখানে শেয়ার করা যাচ্ছে না, তাই ছবিটি ডাউনলোড হয়েছে।','Could not make the image.':'ছবি বানানো যায়নি।','Add your shop name in Admin to show it on receipts.':'রশিদে দোকানের নাম দেখাতে অ্যাডমিনে নাম লিখুন।','Your shop name, address and phone are printed at the top of every receipt.':'আপনার দোকানের নাম, ঠিকানা ও ফোন প্রতিটি রশিদের উপরে ছাপা হবে।'};for(const k in X)if(!BN[k])BN[k]=X[k]})();
function tr(root){if(LANG!=='bn')return;const w=document.createTreeWalker(root,NodeFilter.SHOW_TEXT);let n;while(n=w.nextNode()){if(n.parentNode&&/^(SCRIPT|STYLE|TEXTAREA)$/.test(n.parentNode.nodeName))continue;const t=n.nodeValue.trim();if(!t)continue;let b=BN[t];if(!b)for(const r of BNR){if(r[0].test(t)&&r[1]){b=t.replace(r[0],r[1]);break}}if(b)n.nodeValue=n.nodeValue.replace(t,b)}root.querySelectorAll('[placeholder],[aria-label]').forEach(el=>{['placeholder','aria-label'].forEach(a=>{const v=el.getAttribute(a);if(v&&BN[v])el.setAttribute(a,BN[v])})})}
function toggleLang(){LANG=LANG==='bn'?'en':'bn';try{localStorage.setItem('hisab_lang',LANG)}catch(e){}location.reload()}
async function boot(){let u=null,own=true;try{u=await claude.use('user');if(u)own=await u.isOwner()}catch(e){}if(!own){let r='';try{r=localStorage.getItem('hisab_role')||''}catch(e){}if(r==='client')await startClient(u);else if(r==='staff')await startStaff(u);else{window.NU=u;$('rl').classList.add('on')}return}initOnline()}
setTab('today');tg();decorate();applyTheme();if(LGH&&!LOK)lgShow();boot();
if(LANG==='bn'){document.documentElement.lang='bn';document.title='আমার হিসাব';$('lb').textContent='English';const ob=new MutationObserver(()=>{ob.disconnect();tr(document.body);ob.observe(document.body,{childList:true,subtree:true,characterData:true})});tr(document.body);ob.observe(document.body,{childList:true,subtree:true,characterData:true})}
</script>
</body>
</html>
