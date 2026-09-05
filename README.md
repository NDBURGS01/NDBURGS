<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#030304">
<meta name="description" content="ND BURGS — faça seu pedido online de forma rápida, clara e direta pelo WhatsApp.">
<meta name="nd-site-version" content="20260905-PREMIUM-3D">
<title>ND BURGS | Pedido Online</title>
<style>
:root{--bg:#030304;--bg2:#070709;--panel:#0d0d10;--panel2:#121217;--panel3:#18181f;--line:rgba(255,255,255,.09);--text:#f7f7f8;--muted:#9b9ca5;--orange:#ff6a00;--orange2:#ff9d32;--red:#ff2f3d;--green:#25d366;--gold:#ffd166;--blue:#4da3ff;--shadow:0 25px 80px rgba(0,0,0,.55)}
*{box-sizing:border-box;margin:0;padding:0}html{scroll-behavior:smooth;background:var(--bg);scroll-padding-top:100px}body{font-family:Inter,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;background:radial-gradient(900px 500px at 50% -120px,rgba(255,106,0,.18),transparent 65%),radial-gradient(700px 500px at 100% 35%,rgba(255,47,61,.08),transparent 60%),#030304;color:var(--text);overflow-x:hidden;padding-bottom:110px}
body:before{content:"";position:fixed;inset:0;pointer-events:none;z-index:-1;background:linear-gradient(115deg,transparent 0 40%,rgba(255,255,255,.012) 50%,transparent 60%);opacity:.7}
a{color:inherit}button,input,select,textarea{font:inherit}button{touch-action:manipulation}button:focus-visible,a:focus-visible,input:focus-visible,select:focus-visible,textarea:focus-visible{outline:3px solid rgba(255,157,50,.7);outline-offset:3px}
header{position:sticky!important;top:0!important;z-index:3000!important;height:86px;padding:12px 20px!important;display:flex;align-items:center;justify-content:center;background:rgba(3,3,4,.82)!important;border-bottom:1px solid rgba(255,106,0,.32)!important;backdrop-filter:blur(22px)!important;box-shadow:0 15px 45px rgba(0,0,0,.45)!important}header:after{content:"";position:absolute;left:0;right:0;bottom:-1px;height:1px;background:linear-gradient(90deg,transparent,var(--orange),transparent);opacity:.7}.logo{width:min(210px,60vw)!important;max-width:none!important;filter:drop-shadow(0 0 28px rgba(255,106,0,.25))!important}
/* desktop sidebar */
@media(min-width:901px){body{padding-left:245px}.container{max-width:1280px!important}.nd-sidebar{position:fixed;left:16px;top:102px;bottom:16px;width:210px;z-index:2900;display:flex;flex-direction:column;overflow:hidden;padding:12px;border:1px solid rgba(255,255,255,.10);border-radius:24px;background:linear-gradient(180deg,rgba(20,20,24,.96),rgba(7,7,9,.97));box-shadow:0 25px 70px rgba(0,0,0,.55),inset 0 1px 0 rgba(255,255,255,.05);backdrop-filter:blur(18px)}.nd-sidebar-head{padding:10px 8px 14px}.nd-sidebar-brand{font-size:10px;letter-spacing:2px;color:var(--orange2);font-weight:1000}.nd-sidebar-title{font-size:20px;font-weight:1000;letter-spacing:-.7px;margin-top:3px}.nd-sidebar-scroll{overflow-y:auto;padding:2px 2px 8px;scrollbar-width:thin;scrollbar-color:#333 transparent}.nd-sidebar button{position:relative;width:100%;display:flex;align-items:center;gap:10px;border:1px solid transparent;background:transparent;color:#a8a8b0;border-radius:15px;padding:12px 10px;margin:3px 0;text-align:left;font-weight:900;font-size:12px;cursor:pointer;transition:.18s}.nd-sidebar button .ico{width:30px;height:30px;display:grid;place-items:center;border-radius:10px;background:#15151a;box-shadow:inset 0 1px 0 rgba(255,255,255,.05);font-size:15px}.nd-sidebar button:hover{color:#fff;background:#15151a;border-color:#2d2d34;transform:translateX(2px)}.nd-sidebar button.active{color:#fff;background:linear-gradient(135deg,rgba(255,106,0,.22),rgba(255,47,61,.10));border-color:rgba(255,106,0,.45);box-shadow:0 10px 25px rgba(255,106,0,.08)}.nd-sidebar button.active .ico{background:linear-gradient(135deg,var(--orange),var(--red));color:#050505}.nd-sidebar-foot{margin-top:auto;padding:10px 8px 4px;border-top:1px solid var(--line)}.nd-sidebar-sec{font-size:10px;color:#777;line-height:1.5}.categoria-menu{display:none!important}}
@media(max-width:900px){.nd-sidebar{position:sticky;top:86px;z-index:2800;width:100%;display:flex;overflow-x:auto;gap:7px;padding:8px 10px;background:rgba(5,5,7,.92);border-bottom:1px solid rgba(255,255,255,.08);backdrop-filter:blur(18px);scrollbar-width:none}.nd-sidebar::-webkit-scrollbar{display:none}.nd-sidebar-head,.nd-sidebar-foot{display:none}.nd-sidebar-scroll{display:flex;overflow:visible;gap:7px}.nd-sidebar button{flex:0 0 auto;display:flex;width:auto;margin:0;padding:10px 12px;border:1px solid #29292f;border-radius:999px;background:#101014;color:#bbb;font-size:11px}.nd-sidebar button .ico{display:none}.nd-sidebar button.active{background:linear-gradient(135deg,var(--orange),var(--red));border-color:transparent;color:#050505}.categoria-menu{display:none!important}}
/* hide old duplicate checkout form/floating bar; modal is the single checkout surface */
#checkout,.formulario,#carrinhoFlutuante{display:none!important}
.horarios{max-width:1280px!important;margin:14px auto!important;padding:0 16px!important}.horarios-box{display:grid!important;grid-template-columns:auto 1fr auto;align-items:center;gap:16px;padding:12px 16px!important;background:linear-gradient(135deg,#101014,#09090b)!important;border:1px solid #292930!important;border-left:3px solid var(--green)!important;border-radius:18px!important;box-shadow:0 12px 35px rgba(0,0,0,.28)!important}.horarios-titulo{margin:0!important;color:#fff!important;font-size:12px!important;font-weight:1000!important}.horarios-linha{color:#888!important;font-size:11px!important}.status-aberto{margin:0!important;padding:6px 10px!important;border-radius:999px!important;background:rgba(37,211,102,.08)!important;border:1px solid rgba(37,211,102,.25)!important;color:#6ff19a!important;font-size:11px!important;font-weight:1000!important;white-space:nowrap}
.container{max-width:1280px!important;padding:0 18px 40px!important}.container>h1{display:none!important}.modern-search{position:sticky!important;top:86px!important;z-index:2000!important;display:flex;align-items:center;gap:10px;margin:10px 0 18px!important;padding:9px!important;background:rgba(8,8,10,.90)!important;border:1px solid rgba(255,255,255,.10)!important;border-radius:18px!important;box-shadow:0 16px 45px rgba(0,0,0,.45)!important;backdrop-filter:blur(22px)!important}.modern-search:before{content:"⌕";font-size:25px;color:var(--orange2);padding-left:5px}.modern-search input{margin:0!important;border:0!important;background:#0a0a0d!important;min-height:50px!important;border-radius:13px!important;color:#fff!important;font-size:15px!important}.search-count{color:#777;font-size:11px;font-weight:900;white-space:nowrap;padding-right:8px}
#ndPremiumIntro{position:relative;display:grid;grid-template-columns:1fr auto;gap:25px;align-items:center;margin:16px 0 22px;padding:28px 30px;min-height:230px;overflow:hidden;border:1px solid rgba(255,255,255,.10);border-radius:28px;background:radial-gradient(circle at 82% 45%,rgba(255,106,0,.16),transparent 28%),linear-gradient(145deg,#151519,#070708);box-shadow:0 30px 80px rgba(0,0,0,.48),inset 0 1px 0 rgba(255,255,255,.05)}#ndPremiumIntro:before{content:"";position:absolute;width:390px;height:390px;right:-150px;top:-100px;border:1px solid rgba(255,106,0,.25);border-radius:50%;box-shadow:0 0 100px rgba(255,106,0,.10)}.nd-prem-kicker{font-size:10px;letter-spacing:2.5px;color:var(--orange2);font-weight:1000}.nd-prem-title{font-size:clamp(34px,5vw,62px);line-height:.92;letter-spacing:-3px;font-weight:1000;margin:10px 0}.nd-prem-title span{background:linear-gradient(90deg,#fff,var(--orange2),#ff4b52);-webkit-background-clip:text;background-clip:text;color:transparent}.nd-prem-sub{max-width:650px;color:#999;line-height:1.55;font-size:13px}.nd-prem-actions{display:flex;gap:8px;flex-wrap:wrap;margin-top:16px}.nd-prem-actions button{border:1px solid #303038;background:#111116;color:#fff;border-radius:12px;padding:11px 14px;font-size:11px;font-weight:1000;cursor:pointer}.nd-prem-actions .primary{background:linear-gradient(135deg,var(--orange),var(--red));border-color:transparent;color:#050505}.nd-prem-orb{width:210px;height:210px;position:relative;display:grid;place-items:center;transform:perspective(600px) rotateY(-12deg);filter:drop-shadow(0 30px 35px rgba(0,0,0,.55))}.nd-prem-orb:before,.nd-prem-orb:after{content:"";position:absolute;border-radius:50%;inset:0;border:1px solid rgba(255,106,0,.35);box-shadow:0 0 50px rgba(255,106,0,.12)}.nd-prem-orb:after{inset:20px;border-color:rgba(255,209,102,.18);transform:rotate(25deg) scaleY(.45)}.nd-prem-icon{font-size:96px;position:relative;z-index:2;filter:drop-shadow(0 20px 25px #000)}
.nd-security{display:grid;grid-template-columns:repeat(4,1fr);gap:9px;margin:0 0 25px}.nd-security-card{padding:14px;border:1px solid var(--line);border-radius:16px;background:linear-gradient(145deg,#121216,#0a0a0d);box-shadow:0 12px 30px rgba(0,0,0,.25)}.nd-security-card .sico{font-size:20px;margin-bottom:7px}.nd-security-card strong{display:block;font-size:11px}.nd-security-card span{display:block;color:#777;font-size:10px;line-height:1.4;margin-top:3px}
.categoria{margin-top:35px!important;scroll-margin-top:145px!important}.categoria-titulo{position:relative!important;display:flex!important;align-items:center!important;gap:10px!important;padding:0 0 11px!important;margin:0 0 14px!important;border:0!important;border-bottom:1px solid var(--line)!important;color:#fff!important;font-size:22px!important;font-weight:1000!important}.categoria-titulo:before{content:"";width:6px;height:28px;border-radius:99px;background:linear-gradient(var(--orange),var(--red));box-shadow:0 0 18px rgba(255,106,0,.35)}.categoria-titulo:after{content:"";position:absolute;left:0;bottom:-1px;width:75px;height:2px;background:linear-gradient(90deg,var(--orange),transparent);box-shadow:0 0 18px rgba(255,106,0,.55)}
.produtos{display:grid!important;grid-template-columns:repeat(auto-fill,minmax(220px,1fr))!important;gap:16px!important}.produto{position:relative!important;isolation:isolate;background:linear-gradient(145deg,rgba(28,28,34,.98),rgba(8,8,11,.98))!important;border:1px solid rgba(255,255,255,.09)!important;border-radius:22px!important;padding:10px!important;overflow:hidden!important;box-shadow:0 20px 45px rgba(0,0,0,.35),inset 0 1px 0 rgba(255,255,255,.035)!important;transform-style:preserve-3d;transition:transform .28s ease,border-color .28s,box-shadow .28s}.produto:before{content:"";position:absolute;inset:0;z-index:-1;background:linear-gradient(125deg,rgba(255,106,0,.10),transparent 35%,rgba(255,255,255,.025));opacity:.65}.produto:hover{transform:translateY(-7px) perspective(800px) rotateX(1.5deg);border-color:rgba(255,106,0,.45)!important;box-shadow:0 30px 65px rgba(0,0,0,.55),0 0 0 1px rgba(255,106,0,.05)!important}.produto img,.produto-imagem{width:100%!important;aspect-ratio:1/1!important;height:auto!important;object-fit:cover!important;display:block!important;border-radius:15px!important;background:radial-gradient(circle at 50% 35%,#202027,#07070a)!important;box-shadow:inset 0 0 0 1px rgba(255,255,255,.04),0 15px 25px rgba(0,0,0,.28);transform:translateZ(14px)}.produto h3{font-size:15px!important;line-height:1.18!important;margin:12px 3px 5px!important;font-weight:1000!important;color:#fff!important;transform:translateZ(10px)}.produto p{font-size:11px!important;line-height:1.42!important;min-height:32px!important;color:#85858e!important;margin:0 3px!important}.preco{font-size:21px!important;font-weight:1000!important;color:var(--orange2)!important;margin:10px 3px!important;text-shadow:0 0 18px rgba(255,106,0,.12)}.btn-add{min-height:48px!important;width:100%!important;border:0!important;border-radius:14px!important;background:linear-gradient(135deg,var(--orange),var(--red))!important;color:#050505!important;font-weight:1000!important;box-shadow:0 12px 24px rgba(255,106,0,.18)!important;cursor:pointer}.btn-add:hover{filter:brightness(1.08);transform:translateY(-1px)}
.nd-card-ribbon{position:absolute;top:14px;left:14px;z-index:8;padding:6px 9px;border-radius:9px;background:linear-gradient(135deg,#ffd166,#ff9d32);color:#111;font-size:9px;font-weight:1000;box-shadow:0 10px 25px rgba(0,0,0,.45);pointer-events:none}.nd-card-ribbon:before{content:"🔥 "}
.nd-fav{position:absolute!important;right:14px!important;top:14px!important;z-index:9!important;width:38px!important;height:38px!important;border-radius:50%!important;border:1px solid rgba(255,255,255,.16)!important;background:rgba(5,5,7,.82)!important;color:#fff!important;display:grid!important;place-items:center!important;font-size:19px!important;cursor:pointer!important;backdrop-filter:blur(10px)}.nd-fav.ativo{color:#ff5570!important;border-color:#ff5570!important;background:#281017!important}
/* 3D cart */
.nd-cart{position:fixed;right:20px;bottom:20px;z-index:9000;width:72px;height:72px;border:1px solid rgba(255,255,255,.18);border-radius:22px;background:linear-gradient(145deg,var(--orange),var(--red));color:#050505;display:grid;place-items:center;font-size:29px;cursor:pointer;box-shadow:0 20px 50px rgba(0,0,0,.55),0 12px 35px rgba(255,106,0,.24);transform:perspective(500px) rotateX(4deg);transition:.2s}.nd-cart:hover{transform:translateY(-4px) perspective(500px) rotateX(4deg) scale(1.03)}.nd-cart-badge{position:absolute;right:-5px;top:-6px;min-width:27px;height:27px;padding:0 7px;border-radius:999px;display:grid;place-items:center;background:#fff;color:#111;border:3px solid #0b0b0d;font-size:11px;font-weight:1000}.nd-cart-label{position:fixed;right:18px;bottom:101px;z-index:8999;padding:8px 11px;border-radius:999px;background:#141419;border:1px solid #303038;color:#fff;font-size:10px;font-weight:900;box-shadow:0 10px 30px rgba(0,0,0,.35)}
/* cart modal */
.modal-carrinho,.modal-personalizacao,.modal-finalizar{background:rgba(0,0,0,.82)!important;backdrop-filter:blur(14px)!important}.painel-carrinho,.modal-box,.painel-finalizar{background:linear-gradient(160deg,#17171c,#08080b)!important;border:1px solid rgba(255,106,0,.5)!important;box-shadow:0 30px 90px rgba(0,0,0,.75)!important}.painel-carrinho{width:min(760px,100%)!important;max-height:94vh!important;border-radius:26px 26px 0 0!important;padding:18px!important}.cabecalho-carrinho h2,.modal-topo h2{color:#fff!important}.fechar-carrinho,.modal-fechar,.btn-fechar-finalizar{background:#17171c!important;border:1px solid #35353d!important;color:#fff!important;border-radius:12px!important}.fechar-carrinho:hover,.modal-fechar:hover,.btn-fechar-finalizar:hover{background:var(--red)!important;border-color:var(--red)!important}.item-carrinho-modal{padding:14px 0!important;border-bottom:1px solid #25252b!important}.controles-modal button,.controles button{background:#17171b!important;color:var(--orange2)!important;border:1px solid #34343c!important}.controles-modal .remover,.controles .remover{background:#2b0e10!important;color:#ff6b60!important;border-color:#50191d!important}.btn-finalizar-pedido,.btn-finalizar-modal{background:linear-gradient(135deg,var(--orange),var(--red))!important;color:#050505!important;border:0!important;box-shadow:0 12px 28px rgba(255,106,0,.20)!important}.btn-continuar-comprando{background:#17171b!important;color:#fff!important;border:1px solid #303038!important}
/* personalization */
.modal-box{border-radius:26px!important}.modal-secao{border-color:#29292f!important}.modal-secao h3{color:var(--orange2)!important}.opcao-tamanho label,.opcao-acomp{background:#0c0c10!important;border-color:#303039!important}.opcao-tamanho input:checked+label{background:rgba(255,106,0,.10)!important;border-color:var(--orange)!important;color:#fff!important}.preco-adicional{color:var(--orange2)!important}.modal-total{background:#09090c!important;border-color:#2b2b32!important}.modal-total strong:last-child{color:var(--orange2)!important}
/* premium checkout */
.painel-finalizar{width:min(680px,100%)!important;max-height:94vh!important;overflow:auto!important;padding:0!important;border-radius:26px 26px 0 0!important}.nd-check-head{position:sticky;top:0;z-index:10;padding:18px;background:rgba(13,13,16,.96);border-bottom:1px solid #292930;backdrop-filter:blur(18px)}.nd-check-kicker{font-size:10px;letter-spacing:2px;color:var(--orange2);font-weight:1000}.nd-check-head h2{font-size:24px;margin-top:3px}.nd-stepbar{display:grid;grid-template-columns:repeat(4,1fr);gap:6px;padding:10px 15px;background:#09090c;border-bottom:1px solid #202026;position:sticky;top:76px;z-index:9}.nd-step{padding:9px 5px;border-radius:10px;border:1px solid #29292f;background:#111116;color:#666;font-size:9px;text-align:center;font-weight:1000}.nd-step.active{color:#fff;border-color:var(--orange);background:rgba(255,106,0,.10);box-shadow:0 8px 20px rgba(255,106,0,.08)}.nd-step.done{color:#aaa;border-color:#444}.nd-step-content{display:none;padding:18px}.nd-step-content.active{display:block}.nd-step-content label{display:block;margin:12px 0 7px;color:#eee;font-size:12px;font-weight:1000}.nd-step-content input,.nd-step-content select,.nd-step-content textarea{width:100%;min-height:50px;padding:13px 14px;border-radius:13px;background:#0a0a0e;color:#fff;border:1px solid #303038}.nd-step-content textarea{min-height:100px}.nd-delivery{margin-top:12px;padding:12px;border:1px solid #292930;border-radius:13px;background:#101015;color:#999;font-size:11px;line-height:1.5}.nd-delivery b{color:#fff}.nd-option-grid{display:grid;grid-template-columns:1fr 1fr;gap:9px}.nd-option{min-height:70px;border:1px solid #303038;border-radius:14px;background:#111116;color:#ddd;font-weight:1000;cursor:pointer}.nd-option.active{border-color:var(--orange);background:rgba(255,106,0,.10);color:#fff}.nd-next,.nd-back{width:100%;min-height:52px;margin-top:13px;border-radius:14px;font-weight:1000;cursor:pointer}.nd-next{border:0;background:linear-gradient(135deg,var(--orange),var(--red));color:#050505}.nd-back{border:1px solid #303038;background:#111116;color:#aaa}.nd-summary{padding:14px;border:1px solid #292930;border-radius:15px;background:#0c0c10;margin-bottom:12px}.nd-summary-title{font-size:10px;color:#777;font-weight:1000;letter-spacing:1px;text-transform:uppercase;margin-bottom:9px}.nd-summary-row{display:flex;justify-content:space-between;gap:10px;padding:7px 0;border-bottom:1px solid #202027;font-size:12px}.nd-summary-row:last-child{border-bottom:0}.nd-total{display:flex;justify-content:space-between;align-items:end;padding-top:12px;margin-top:5px}.nd-total strong:last-child{font-size:30px;color:var(--orange2)}
/* reviews / trust / footer */
#ndReviews{margin:44px 0 18px;padding:22px;border:1px solid #25252c;border-radius:24px;background:linear-gradient(145deg,#111116,#07070a);box-shadow:0 20px 55px rgba(0,0,0,.35)}#ndReviews h2{margin:0;border:0;padding:0;color:#fff}.nd-review-stars{display:flex;gap:6px;margin:14px 0}.nd-review-stars button{width:42px;height:42px;border:1px solid #303039;border-radius:11px;background:#0c0c10;color:#555;cursor:pointer;font-size:20px}.nd-review-stars button.on{color:var(--orange2);border-color:var(--orange);background:rgba(255,106,0,.08)}#ndReviewText{min-height:90px}#ndReviewSend{width:100%;margin-top:9px;padding:13px;border:0;border-radius:12px;background:var(--orange);color:#050505;font-weight:1000}.nd-review-list{display:grid;gap:8px;margin-top:14px}.nd-review{padding:11px;border:1px solid #25252c;border-radius:13px;background:#0b0b0f}.nd-review strong{color:var(--orange2)}.nd-review p{font-size:12px;color:#bbb;margin-top:5px}.rodape-instagram{margin-top:35px!important;background:#030304!important;border-top:1px solid #18181d!important}.instagram-destaque{border-color:#2a2a30!important;background:#0b0b0f!important}.instagram-botao{background:linear-gradient(135deg,var(--orange),var(--red))!important;color:#050505!important}
#ndBackTop{position:fixed;right:20px;bottom:105px;z-index:8900;width:44px;height:44px;border-radius:14px;border:1px solid #34343c;background:#15151a;color:#fff;display:none;cursor:pointer;box-shadow:0 12px 30px rgba(0,0,0,.45)}#ndBackTop.show{display:grid;place-items:center}.no-results{border-color:#333!important;background:#0d0d10!important}
@media(max-width:900px){.horarios{padding:0 10px!important}.horarios-box{grid-template-columns:1fr auto!important;gap:6px 10px!important}.horarios-linha{grid-column:1/-1}.container{padding:0 9px 30px!important}.modern-search{top:86px!important}.nd-premium{margin-top:10px}.nd-security{grid-template-columns:1fr 1fr}.nd-security-card:last-child{grid-column:1/-1}.nd-prem-orb{width:150px;height:150px}.nd-prem-icon{font-size:70px}.nd-prem-title{font-size:40px}.produtos{grid-template-columns:repeat(2,minmax(0,1fr))!important;gap:9px!important}.produto{padding:8px!important;border-radius:16px!important}.produto:hover{transform:none}.produto h3{font-size:13px!important}.produto p{font-size:9.5px!important;min-height:38px!important}.preco{font-size:18px!important}.btn-add{min-height:46px!important;font-size:11px!important}.nd-cart{width:62px;height:62px;right:14px;bottom:14px;border-radius:19px}.nd-cart-label{right:12px;bottom:86px}.nd-stepbar{top:72px;padding:8px 10px}.nd-step{font-size:8px;padding:8px 3px}.nd-step-content{padding:15px 13px 22px}.painel-finalizar{max-height:96vh!important}.nd-option-grid{grid-template-columns:1fr 1fr}}
@media(max-width:520px){.ndPremiumIntro{grid-template-columns:1fr!important}.nd-prem-orb{display:none}.nd-security{grid-template-columns:1fr 1fr}.nd-step{font-size:7px}.nd-option-grid{grid-template-columns:1fr}.horarios-titulo{font-size:10px!important}.status-aberto{font-size:9px!important}}
@media(prefers-reduced-motion:reduce){*,*:before,*:after{scroll-behavior:auto!important;transition-duration:.01ms!important;animation-duration:.01ms!important}.produto:hover{transform:none}}
</style>
</head>
<body>

<!-- RODADA 1: bloqueio por horário removido; atendimento 24h todos os dias -->

<header>

<img class="logo" src="https://i.ibb.co/5gsVbBcb/corretooo.jpg" alt="ND BURGS">


</header>

<section class="nd-v4-hero">
  <div class="nd-v4-hero-glow"></div>
  <div class="nd-v4-hero-content">
    <span class="nd-v4-kicker">🔥 PEDIDOS ONLINE</span>
    <h1>EAI,<br><em>BORA DE #NDBURGS.</em></h1>
    <p>Escolha seus favoritos, monte seu pedido e envie direto para a ND BURGS.</p>
    <div class="nd-v4-hero-actions">
      <button type="button" class="nd-v4-primary" onclick="document.getElementById('combos')?.scrollIntoView({behavior:'smooth'})">PEDIR AGORA <span>→</span></button>
      <button type="button" class="nd-v4-secondary" onclick="document.getElementById('combos')?.scrollIntoView({behavior:'smooth'})">VER CARDÁPIO</button>
    </div>
    <div class="nd-v4-trustline">
      <span>🛵 DELIVERY</span><span>🏪 RETIRADA</span><span>📲 WHATSAPP</span>
   </div>
  </div>
  <div class="nd-v4-hero-art" aria-hidden="true">
    <div class="nd-v4-art-ring"></div>
    <img
      src="https://i.ibb.co/nMmfSSt1/Chat-GPT-Image-28-de-jul-de-2026-22-33-11.png"
      alt="Hambúrguer ND BURGS"
      class="nd-v4-art-burger"
    >
    <div class="nd-v4-art-price">PEÇA<br><strong>AGORA</strong></div>
  </div>
</section>


<div class="horarios">

<div class="horarios-box">

<div class="horarios-titulo">
🟢 ATENDIMENTO 24 HORAS
</div>

<div class="horarios-linha">
📅 TODOS OS DIAS • 24 HORAS
</div>

<div id="statusHorario" class="status-aberto">🟢 ABERTO AGORA • PEDIDOS 24H</div>

</div>

</div>

<div class="container">

<h1>🍔 FAÇA SEU PEDIDO</h1>
<div class="modern-search"><input id="buscaProdutos" type="search" autocomplete="off" placeholder="🔎 Buscar lanche, combo, açaí, pastel, bebida..." aria-label="Buscar produtos"><span id="contadorBusca" class="search-count"></span></div>
<div id="semResultados" class="no-results">😕 Nenhum produto encontrado.<br><small>Tente outro nome ou categoria.</small></div>

<div class="categoria-menu">

<button class="categoria-btn" onclick="irPara('combos')">
❤️ COMBOS
</button>

<button class="categoria-btn" onclick="irPara('tradicionais')">
🍔 TRADICIONAIS
</button>

<button class="categoria-btn" onclick="irPara('artesanais')">
🍔 ARTESANAIS
</button>

<button class="categoria-btn" onclick="irPara('combosArtesanais')">
🔥 COMBOS ARTESANAIS
</button>

<button class="categoria-btn" onclick="irPara('porcoes')">
🍟 PORÇÕES
</button>

<button class="categoria-btn" onclick="irPara('pasteis')">
🥟 PASTÉIS
</button>

<button class="categoria-btn" onclick="irPara('acai')">
🥤 AÇAÍ
</button>

<button class="categoria-btn" onclick="irPara('milkshakes')">
🥤🥤 MILKSHAKES
</button>

<button class="categoria-btn" onclick="irPara('bebidas')">
🥤 BEBIDAS
</button>

<button class="categoria-btn" onclick="irPara('sobremesas')">
🍓 SOBREMESAS
</button>

<button class="categoria-btn" onclick="irPara('adicionais')">
➕ ADICIONAIS
</button>

</div>

<section id="combos" class="categoria">

<div class="categoria-titulo">
❤️ COMBOS
</div>

<div class="produtos">

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/wNQqzkSf/COMBO-DOCE.png" alt="COMBO DOCE">
<h3>COMBO DOCE</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 32,90</div>
<button class="btn btn-add" onclick="adicionar('COMBO DOCE',32.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/cSLMFXtL/COMBO-GELADO.png" alt="COMBO GELADO">
<h3>COMBO GELADO</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 40,90</div>
<button class="btn btn-add" onclick="adicionar('COMBO GELADO',40.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/5WM7335K/5-ESTRELAS.png" alt="COMBO 5 ESTRELAS">
<h3>COMBO 5 ESTRELAS</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 45,90</div>
<button class="btn btn-add" onclick="adicionar('COMBO 5 ESTRELAS',45.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/twFJ6Vwt/COMBO-DIETA-SO-SEGUNDA.png" alt="COMBO DIETA SÓ SEGUNDA">
<h3>COMBO DIETA SÓ SEGUNDA</h3>
<p>Coca lata + doce surpresa + pastel.</p>
<div class="preco">R$ 27,90</div>
<button class="btn btn-add" onclick="adicionar('COMBO DIETA SÓ SEGUNDA',27.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/HLNHv9tt/COMBO-MAIS-VENDIDO-NOVO.png" alt="COMBO MAIS VENDIDO">
<h3>COMBO MAIS VENDIDO</h3>
<p>Um dos combos especiais da ND BURGS.</p>
<div class="preco">R$ 20,90</div>
<button class="btn btn-add" onclick="adicionar('COMBO MAIS VENDIDO',20.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/PvJqcwzb/MOTACA-ND.png" alt="COMBO MOTOCA ND">
<h3>COMBO MOTOCA ND</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 32,90</div>
<button class="btn btn-add" onclick="adicionar('COMBO MOTOCA ND',32.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/QR0388c/COMBO-S-LOVE.png" alt="COMBO SÓ LOVE">
<h3>COMBO SÓ LOVE</h3>
<p>Combo especial para compartilhar.</p>
<div class="preco">R$ 71,90</div>
<button class="btn btn-add" onclick="adicionar('COMBO SÓ LOVE',71.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/23CmpQqn/DATE-COM-ND-BURGS.png" alt="DATE COM NDBURGS">
<h3>DATE COM NDBURGS</h3>
<p>Combo especial para o seu date.</p>
<div class="preco">R$ 70,90</div>
<button class="btn btn-add" onclick="adicionar('DATE COM NDBURGS',70.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Lz9JQx8f/01-NDBURGS.png" alt="01 ND BURGS">
<h3>01 ND BURGS</h3>
<p>Combo especial.</p>
<div class="preco">R$ 50,90</div>
<button class="btn btn-add" onclick="adicionar('01 ND BURGS',50.90)">ADICIONAR</button>
</div>

</div>
</section>

<section id="tradicionais" class="categoria">

<div class="categoria-titulo">
🍔 TRADICIONAIS
</div>

<div class="produtos">

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/ds9Qr0PD/BURGUER.jpg" alt="X-BURGUER">
<h3>X-BURGUER</h3>
<p>Pão de hamburguer , maionese caseira ( não é verde ) , hamburguer 56gr industrializado e queijo cheddar.</p>
<div class="preco">R$ 10,90</div>
<button class="btn btn-add" onclick="adicionar('X-BURGUER',10.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/k2KQwpjp/BACON.jpg" alt="X-BACON">
<h3>X-BACON</h3>
<p>Pão de hamburguer , molho barbecue , hamburguer 56gr industrializado , bacon e  queijo cheddar.</p>
<div class="preco">R$ 11,90</div>
<button class="btn btn-add" onclick="adicionar('X-BACON',11.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/390n5BZv/SALADA.png" alt="X-SALADA">
<h3>X-SALADA</h3>
<p>Pão de hamburguer , maionese caseira ( não é verde ) , hamburguer 56gr industrializado , alface , tomate e queijo cheddar.</p>
<div class="preco">R$ 11,90</div>
<button class="btn btn-add" onclick="adicionar('X-SALADA',11.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/NgWQv5Nm/EGG.png" alt="X-EGG">
<h3>X-EGG</h3>
<p>Pão de hamburguer , maionese caseira ( não é verde ) , hamburguer 56gr industrializado , ovo e queijo cheddar.</p>
<div class="preco">R$ 11,90</div>
<button class="btn btn-add" onclick="adicionar('X-EGG',11.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/fGHQ9NrW/SELLIS.png" alt="SELLIS">
<h3>SELLIS</h3>
<p>Pão de hamburguer , molho cheddar cremoso , hamburguer 56gr industrializado , alface , tomate , bacon e queijo cheddar.</p>
<div class="preco">R$ 13,90</div>
<button class="btn btn-add" onclick="adicionar('SELLIS',13.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Vszxw7h/NUNES.png" alt="NUNES">
<h3>NUNES</h3>
<p>Pão de brioche divido em 3 partes , maionese caseira ( não é verde ) , 4 hamburgueres 56gr industrializado , alface , tomate , cebola , ovo , bacon e queijo cheddar.</p>
<div class="preco">R$ 24,90</div>
<button class="btn btn-add" onclick="adicionar('NUNES',24.90)">ADICIONAR</button>
</div>

</div>
</section>

<section id="artesanais" class="categoria">

<div class="categoria-titulo">
🍔 ARTESANAIS
</div>

<div class="produtos">

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/zW8gbZpK/BERENICE.jpg" alt="BERENICE">
<h3>BERENICE</h3>
<p>Pão de brioche, carne artesanal 120 gr, queijo cheddar, maionese verde, alface e cebola roxa.</p>
<div class="preco">R$ 22,90</div>
<button class="btn btn-add" onclick="adicionar('BERENICE',22.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/tTWqZ9ST/PATAO.png" alt="PATAO">
<h3>PATAO</h3>
<p>Pão de brioche, carne artesanal 120 gr, queijo cheddar, molho barbecue, bacon e 2 anéis de cebola fritos.</p>
<div class="preco">R$ 23,90</div>
<button class="btn btn-add" onclick="adicionar('PATAO',23.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/d4pD5bNc/DINA.jpg" alt="DINA">
<h3>DINA</h3>
<p>Pão de brioche, filé de frango empanado, queijo cheddar, maionese verde, alface , tomate e cebola.</p>
<div class="preco">R$ 20,90</div>
<button class="btn btn-add" onclick="adicionar('DINA',20.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/qLK7hWYs/GADEIA.jpg" alt="GADEIA">
<h3>GADEIA</h3>
<p>Pão de hamburguer, carne artesanal 120 gr, maionese verde, queijo cheddar.</p>
<div class="preco">R$ 20,90</div>
<button class="btn btn-add" onclick="adicionar('GADEIA',20.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/ymQ7sFZn/GAROTINHO.png" alt="GAROTINHO">
<h3>GAROTINHO</h3>
<p>Pão de brioche, carne artesanal 120gr, molho cheddar cremoso e bacon.</p>
<div class="preco">R$ 22,90</div>
<button class="btn btn-add" onclick="adicionar('GAROTINHO',22.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/0yTLwY4b/PEZAO.jpg" alt="PÉZÃO">
<h3>PÉZÃO</h3>
<p>Pão de brioche dividido em 3 partes , 2 carnes artesanais 120gr , maionese, queijo cheddar, ovo, cebola, bacon, alface e tomate.</p>
<div class="preco">R$ 32,90</div>
<button class="btn btn-add" onclick="adicionar('PÉZÃO',32.90)">ADICIONAR</button>
</div>

</div>
</section>

<section id="combosArtesanais" class="categoria">

<div class="categoria-titulo">
🔥 COMBOS ARTESANAIS
</div>

<div class="produtos">

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/QR0388c/COMBO-S-LOVE.png" alt="COMBO SÓ LOVE">
<h3>ARTESANAL COMBO SÓ LOVE</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 90,80</div>
<button class="btn btn-add" onclick="adicionar('ARTESANAL COMBO SÓ LOVE',90.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/5WM7335K/5-ESTRELAS.png" alt="COMBO 5 ESTRELAS">
<h3>ARTESANAL COMBO 5 ESTRELAS</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 70,80</div>
<button class="btn btn-add" onclick="adicionar('ARTESANAL COMBO 5 ESTRELAS',70.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/HLNHv9tt/COMBO-MAIS-VENDIDO-NOVO.png" alt="COMBO MAIS VENDIDO">
<h3>ARTESANAL COMBO MAIS VENDIDO</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 34,80</div>
<button class="btn btn-add" onclick="adicionar('ARTESANAL COMBO MAIS VENDIDO',34.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/wNQqzkSf/COMBO-DOCE.png" alt="COMBO DOCE">
<h3>ARTESANAL COMBO DOCE</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 44,80</div>
<button class="btn btn-add" onclick="adicionar('ARTESANAL COMBO DOCE',44.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/cSLMFXtL/COMBO-GELADO.png" alt="COMBO GELADO">
<h3>ARTESANAL COMBO GELADO</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 52,80</div>
<button class="btn btn-add" onclick="adicionar('ARTESANAL COMBO GELADO',52.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/23CmpQqn/DATE-COM-ND-BURGS.png" alt="DATE COM NDBURGS">
<h3>ARTESANAL DATE COM NDBURGS</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 91,80</div>
<button class="btn btn-add" onclick="adicionar('ARTESANAL DATE COM NDBURGS',91.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/PvJqcwzb/MOTACA-ND.png" alt="COMBO MOTOCA ND">
<h3>ARTESANAL MOTOCA ND</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 41,80</div>
<button class="btn btn-add" onclick="adicionar('ARTESANAL MOTOCA ND',41.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Lz9JQx8f/01-NDBURGS.png" alt="01 ND BURGS">
<h3>ARTESANAL 01 ND BURGS</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 96,80</div>
<button class="btn btn-add" onclick="adicionar('ARTESANAL 01 ND BURGS',96.80)">ADICIONAR</button>
</div>

</div>
</section>

<section id="porcoes" class="categoria">

<div class="categoria-titulo">
🍟 PORÇÕES
</div>

<div class="produtos">

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/JT71z1Y/BATATA.png" alt="BATATA">
<h3>BATATA</h3>
<p>Escolha o tamanho.</p>
<div class="preco">A partir de R$ 6,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('batata')">ESCOLHER</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/v4QS3vVp/BATATA-COM-CHEDDAR-E-BACON.png" alt="BATATA COMPLETA">
<h3>BATATA COMPLETA</h3>
<p>Batata completa com cheddar e bacon.</p>
<div class="preco">A partir de R$ 12,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('batataCompleta')">ESCOLHER</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/39SVqYJP/NUGGETS.png" alt="NUGGETS">
<h3>NUGGETS</h3>
<p>Escolha o tamanho.</p>
<div class="preco">A partir de R$ 9,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('nuggets')">ESCOLHER</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Pz0W4RKj/ONION-RINGS.png" alt="ANEL DE CEBOLA">
<h3>ANEL DE CEBOLA</h3>
<p>Escolha o tamanho.</p>
<div class="preco">A partir de R$ 9,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('anelCebola')">ESCOLHER</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Fb7LHQXC/FRANGO-PEDA-OS-EMPANADO.png" alt="FRANGO FRITO">
<h3>FRANGO FRITO</h3>
<p>Escolha o tamanho.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('frangoFrito')">ESCOLHER</button>
</div>

</div>
</section>

<section id="pasteis" class="categoria">

<div class="categoria-titulo">
🥟 PASTÉIS
</div>

<div class="produtos">

<div class="produto">

<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/5x68nMyh/Chat-GPT-Image-25-06-2026-23-28-35.png" alt="PASTÉIS">

<h3>PASTÉIS</h3>

<p>Escolha entre nossos sabores salgados e doces.</p>

<div class="preco">A partir de R$ 11,00</div>

<button class="btn btn-add" onclick="abrirPersonalizacao('pasteis')">
ESCOLHER SABOR
</button>

</div>

</div>
</section>

<section id="acai" class="categoria">

<div class="categoria-titulo">
🥤 AÇAÍ
</div>

<div class="produtos">

<div class="produto">

<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Kxj5h5Km/Chat-GPT-Image-28-07-2026-18-32-28.png" alt="AÇAÍ">

<h3>AÇAÍ</h3>

<p>Escolha o tamanho e seus acompanhamentos.</p>

<div class="preco">A partir de R$ 11,90</div>

<button class="btn btn-add" onclick="abrirPersonalizacao('acai')">
ESCOLHER
</button>

</div>

<div class="produto">

<h3>CASADINHO</h3>

<p>Açaí casadinho.</p>

<div class="preco">R$ 11,90</div>

<button class="btn btn-add" onclick="abrirPersonalizacao('casadinho')">
ESCOLHER
</button>

</div>

<div class="produto">

<h3>AÇAÍ TRUFFADO</h3>

<p>Açaí truffado especial.</p>

<div class="preco">A partir de R$ 26,00</div>

<button class="btn btn-add" onclick="abrirPersonalizacao('truffado')">
ESCOLHER
</button>

</div>

<div class="produto">

<h3>TENTAÇÃO DE MORANGO</h3>

<p>Açaí com combinação especial de morango.</p>

<div class="preco">A partir de R$ 18,00</div>

<button class="btn btn-add" onclick="abrirPersonalizacao('tentacao')">
ESCOLHER
</button>

</div>

</div>
</section>

<section id="milkshakes" class="categoria">

<div class="categoria-titulo">
🥤 MILKSHAKES
</div>

<div class="produtos">

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/PZD2DtDq/MILKSHAKE-DE-OVOMALTINE.png" alt="MILKSHAKE OVOMALTINE">
<h3>OVOMALTINE</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkOvomaltine')">ESCOLHER</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/ZRbdHHVQ/oreo.jpg" alt="MILKSHAKE OREO">
<h3>OREO</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkOreo')">ESCOLHER</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/NnyTc0wK/pa-oca.jpg" alt="MILKSHAKE PAÇOCA">
<h3>PAÇOCA</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkPacoca')">ESCOLHER</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/1Ym81pQM/MILKSHAKE-MORANGO.png" alt="MILKSHAKE NESQUIK">
<h3>NESQUIK</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkNesquik')">ESCOLHER</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/NntDRB8q/leite-ninho.jpg" alt="MILKSHAKE LEITE NINHO">
<h3>LEITE NINHO</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkNinho')">ESCOLHER</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/WvRv23Y5/milk-a-ai.jpg" alt="MILKSHAKE DE AÇAÍ">
<h3>DE AÇAÍ</h3>
<p>Milkshake de açaí.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkAcai')">ESCOLHER</button>
</div>

</div>
</section>

<section id="bebidas" class="categoria">

<div class="categoria-titulo">
🥤 BEBIDAS
</div>

<div class="produtos">

<div class="produto">
<h3>COCA COLA LATA</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 6,00</div>
<button class="btn btn-add" onclick="adicionar('COCA COLA LATA',6)">ADICIONAR</button>
</div>

<div class="produto">
<h3>COCA COLA ZERO LATA</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 6,00</div>
<button class="btn btn-add" onclick="adicionar('COCA COLA ZERO LATA',6)">ADICIONAR</button>
</div>

<div class="produto">
<h3>SPRITE LATA</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 6,00</div>
<button class="btn btn-add" onclick="adicionar('SPRITE LATA',6)">ADICIONAR</button>
</div>

<div class="produto">
<h3>FANTA UVA LATA</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 6,00</div>
<button class="btn btn-add" onclick="adicionar('FANTA UVA LATA',6)">ADICIONAR</button>
</div>

<div class="produto">
<h3>FANTA LARANJA LATA</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 6,00</div>
<button class="btn btn-add" onclick="adicionar('FANTA LARANJA LATA',6)">ADICIONAR</button>
</div>

<div class="produto">
<h3>GUARANA LATA</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 6,00</div>
<button class="btn btn-add" onclick="adicionar('GUARANA LATA',6)">ADICIONAR</button>
</div>

<div class="produto">
<h3>DELL VALE LATA</h3>
<p>Bebida.</p>
<div class="preco">R$ 7,00</div>
<button class="btn btn-add" onclick="adicionar('DELL VALE LATA',7)">ADICIONAR</button>
</div>

<div class="produto">
<h3>ÁGUA MINERAL</h3>
<p>Água mineral.</p>
<div class="preco">R$ 3,50</div>
<button class="btn btn-add" onclick="adicionar('ÁGUA MINERAL',3.50)">ADICIONAR</button>
</div>

<div class="produto">
<h3>COCA COLA 600ML</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 10,00</div>
<button class="btn btn-add" onclick="adicionar('COCA COLA 600ML',10)">ADICIONAR</button>
</div>

<div class="produto">
<h3>COCA COLA 2 LITROS</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 15,00</div>
<button class="btn btn-add" onclick="adicionar('COCA COLA 2 LITROS',15)">ADICIONAR</button>
</div>

<div class="produto">
<h3>COCA COLA ZERO 2 LITROS</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 15,00</div>
<button class="btn btn-add" onclick="adicionar('COCA COLA ZERO 2 LITROS',15)">ADICIONAR</button>
</div>

<div class="produto">
<h3>DOLLY 2 LITROS LIMÃO</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 9,00</div>
<button class="btn btn-add" onclick="adicionar('DOLLY 2 LITROS LIMÃO',9)">ADICIONAR</button>
</div>

<div class="produto">
<h3>DOLLY 2 LITROS GUARANÁ</h3>
<p>Refrigerante.</p>
<div class="preco">R$ 9,00</div>
<button class="btn btn-add" onclick="adicionar('DOLLY 2 LITROS GUARANÁ',9)">ADICIONAR</button>
</div>

</div>
</section>

<section id="sobremesas" class="categoria">

<div class="categoria-titulo">
🍓 SOBREMESAS
</div>

<div class="produtos">

<div class="produto">

<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/ksyxPyr2/Chat-GPT-Image-26-06-2026-00-10-12.png" alt="KITKAT">

<h3>KITKAT</h3>

<p>Doce especial.</p>

<div class="preco">R$ 7,00</div>

<button class="btn btn-add" onclick="adicionar('KITKAT',7)">
ADICIONAR
</button>

</div>

<div class="produto">

<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/7x6dFWmm/Chat-GPT-Image-25-06-2026-23-14-20.png" alt="SURPRESA DE UVA">

<h3>SURPRESA DE UVA</h3>

<p>Sobremesa especial.</p>

<div class="preco">R$ 12,00</div>

<button class="btn btn-add" onclick="adicionar('SURPRESA DE UVA',12)">
ADICIONAR
</button>

</div>

</div>
</section>

<section id="adicionais" class="categoria">

<div class="categoria-titulo">
➕ ADICIONAIS
</div>

<div class="produtos">

<div class="produto">
<h3>FATIA QUEIJO CHEDDAR EXTRA</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('FATIA QUEIJO CHEDDAR EXTRA',3)">ADICIONAR</button>
</div>

<div class="produto">
<h3>HAMBURGUER EXTRA ARTESANAL</h3>
<p>Adicional.</p>
<div class="preco">R$ 9,00</div>
<button class="btn btn-add" onclick="adicionar('HAMBURGUER EXTRA ARTESANAL',9)">ADICIONAR</button>
</div>

<div class="produto">
<h3>HAMBURGUER EXTRA TRADICIONAL</h3>
<p>Adicional.</p>
<div class="preco">R$ 2,50</div>
<button class="btn btn-add" onclick="adicionar('HAMBURGUER EXTRA TRADICIONAL',2.50)">ADICIONAR</button>
</div>

<div class="produto">
<h3>BACON</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('BACON',3)">ADICIONAR</button>
</div>

<div class="produto">
<h3>POTINHO BARBECUE</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO BARBECUE',3)">ADICIONAR</button>
</div>

<div class="produto">
<h3>POTINHO MAIONESE VERDE</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO MAIONESE VERDE',3)">ADICIONAR</button>
</div>

<div class="produto">
<h3>POTINHO CHEDDAR</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO CHEDDAR',3)">ADICIONAR</button>
</div>

<div class="produto">
<h3>POTINHO MAIONESE ARTESANAL</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO MAIONESE ARTESANAL',3)">ADICIONAR</button>
</div>


<div class="produto">
<h3>ADICIONAL BACON</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('ADICIONAL BACON',3)">ADICIONAR</button>
</div>

<div class="produto">
<h3>ADICIONAL CHEDDAR</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('ADICIONAL CHEDDAR',3)">ADICIONAR</button>
</div>

</div>
</section>

<div id="checkout" class="carrinho">

<h2>🛒 SEU CARRINHO</h2>

<div id="carrinhoItens">
<div class="vazio">Seu carrinho está vazio.</div>
</div>

<div class="resumo">

<div class="linha">
<span>Subtotal</span>
<strong id="subtotal">R$ 0,00</strong>
</div>

<div class="linha">
<span>Taxa de entrega</span>
<strong id="taxa">R$ 0,00</strong>
</div>

<div class="linha total">
<span>TOTAL</span>
<strong id="total">R$ 0,00</strong>
</div>

</div>
</div>

<div class="formulario">

<h2>📍 DADOS DO PEDIDO</h2>

<label>Nome</label>
<input type="text" id="nome" placeholder="Digite seu nome">

<label>Telefone</label>
<input type="tel" id="telefone" placeholder="Digite seu telefone">

<label>Tipo do pedido</label>

<select id="tipoPedido" onchange="alterarTipoPedido()">

<option value="ENTREGA">
🏍️ DELIVERY
</option>

<option value="RETIRADA">
🏪 RETIRADA
</option>

</select>

<div id="enderecoArea">

<label>Rua</label>
<div class="address-search-wrap"><input id="ruaBusca" type="search" autocomplete="off" placeholder="🔎 Pesquisar sua rua"><small>Digite parte do nome para encontrar mais rápido.</small></div>
<select id="rua" onchange="calcularTaxa()">

<option value="">
Selecione sua rua
</option>

</select>

<label>Número</label>

<input
type="text"
id="numero"
placeholder="Número da residência"
>

<label>Complemento</label>

<input
type="text"
id="complemento"
placeholder="Apartamento, casa, bloco..."
>

<div id="avisoTaxa" class="aviso-taxa"></div>

</div>

<label>Forma de pagamento</label>

<select id="pagamento">

<option value="">
Selecione
</option>

<option value="PIX">
PIX
</option>

<option value="DINHEIRO">
DINHEIRO
</option>

<option value="CARTÃO">
CARTÃO
</option>

</select>

<div id="trocoArea" style="display:none;">

<label>Troco para quanto?</label>

<input
type="number"
id="troco"
placeholder="Ex: 50"
step="0.01"
>

</div>

<label>Observação</label>

<textarea
id="observacao"
placeholder="Ex: Sem cebola, tocar campainha..."
></textarea>

<button
class="btn btn-whatsapp"
onclick="finalizarPedido()"
>
📲 ENVIAR PEDIDO PELO WHATSAPP
</button>

<button
class="btn btn-limpar"
onclick="limparCarrinho()"
>
🗑️ LIMPAR CARRINHO
</button>

</div>

</div>

<!-- CARRINHO FLUTUANTE -->

<div id="carrinhoFlutuante" class="carrinho-flutuante">

<div class="carrinho-flutuante-info">

<strong>
🛒 SEU CARRINHO
</strong>

<span id="contadorCarrinho">
0 itens
</span>

</div>

<div class="carrinho-flutuante-direita">

<strong
id="totalCarrinhoFlutuante"
class="carrinho-flutuante-total"
>
R$ 0,00
</strong>

<button
type="button"
class="btn-ver-carrinho"
onclick="abrirCarrinho()"
>
VER CARRINHO
</button>

</div>

</div>

<!-- MODAL CARRINHO -->

<div
id="modalCarrinho"
class="modal-carrinho"
onclick="fecharCarrinho(event)"
>

<div
class="painel-carrinho"
onclick="event.stopPropagation()"
>

<div class="cabecalho-carrinho">

<h2>
🛒 SEU PEDIDO
</h2>

<button
class="fechar-carrinho"
onclick="fecharCarrinho()"
>
×
</button>

</div>

<div id="itensCarrinhoModal"></div>

<div class="resumo-modal">

<div class="linha">
<span>Subtotal</span>
<strong id="subtotalCarrinhoModal">
R$ 0,00
</strong>
</div>

<div class="linha">
<span>Taxa de entrega</span>
<strong id="taxaCarrinhoModal">
R$ 0,00
</strong>
</div>

<div class="linha total-modal">
<span>TOTAL</span>
<strong id="totalCarrinhoModal">
R$ 0,00
</strong>
</div>

</div>

<button
class="btn btn-continuar-comprando"
onclick="irParaCheckout()"
>
❤️ CONTINUAR COMPRANDO
</button>

<button
class="btn btn-finalizar-pedido"
onclick="irParaFinalizarPedido()"
>
📲 FINALIZAR PEDIDO
</button>

</div>
</div>

<!-- MODAL FINALIZAR PEDIDO -->

<div
id="modalFinalizar"
class="modal-finalizar"
onclick="fecharModalFinalizar(event)"
>

<div
class="painel-finalizar"
onclick="event.stopPropagation()"
>

<div class="cabecalho-finalizar">

<h2>
📍 DADOS DO PEDIDO
</h2>

<button
class="btn-fechar-finalizar"
onclick="fecharModalFinalizar()"
>
×
</button>

</div>

<label>
Nome
</label>

<input
type="text"
id="nomeModal"
placeholder="Digite seu nome"
>

<label>
Telefone
</label>

<input
type="tel"
id="telefoneModal"
placeholder="Digite seu telefone"
>

<label>
Tipo do pedido
</label>

<select
id="tipoPedidoModal"
onchange="alterarTipoPedidoModal()"
>

<option value="ENTREGA">
🏍️ DELIVERY
</option>

<option value="RETIRADA">
🏪 RETIRADA
</option>

</select>

<div id="enderecoAreaModal">

<label>
Rua
</label>

<select
id="ruaModal"
onchange="calcularTaxaModal()"
>

<option value="">
Selecione sua rua
</option>

</select>

<label>
Número
</label>

<input
type="text"
id="numeroModal"
placeholder="Número da residência"
>

<label>
Complemento
</label>

<input
type="text"
id="complementoModal"
placeholder="Apartamento, casa, bloco..."
>

<div
id="avisoTaxaModal"
class="aviso-taxa"
></div>

</div>

<label>
Forma de pagamento
</label>

<select
id="pagamentoModal"
onchange="alterarPagamentoModal()"
>

<option value="">
Selecione
</option>

<option value="PIX">
PIX
</option>

<option value="DINHEIRO">
DINHEIRO
</option>

<option value="CARTÃO">
CARTÃO
</option>

</select>

<div
id="trocoAreaModal"
style="display:none;"
>

<label>
Troco para quanto?
</label>

<input
type="number"
id="trocoModal"
placeholder="Ex: 50"
step="0.01"
>

</div>

<label>
Observação
</label>

<textarea
id="observacaoModal"
placeholder="Ex: Sem cebola, tocar campainha..."
></textarea>

<div
class="resumo-modal"
style="margin-top:18px;"
>

<div class="linha">
<span>Subtotal</span>

<strong id="subtotalFinalizarModal">
R$ 0,00
</strong>
</div>

<div class="linha">
<span>Taxa de entrega</span>

<strong id="taxaFinalizarModal">
R$ 0,00
</strong>
</div>

<div class="linha total-modal">
<span>TOTAL</span>

<strong id="totalFinalizarModal">
R$ 0,00
</strong>
</div>

</div>

<button
class="btn btn-finalizar-modal"
onclick="finalizarPedidoModal()"
>
📲 CLIQUE PARA CONFIRMAR PEDIDO 
</button>

</div>
</div>

<!-- MODAL PERSONALIZAÇÃO -->

<div
id="modalPersonalizacao"
class="modal-personalizacao"
>

<div class="modal-box">

<div class="modal-topo">

<h2 id="modalTitulo">
Personalizar
</h2>

<button
class="modal-fechar"
onclick="fecharPersonalizacao()"
>
×
</button>

</div>

<div id="modalConteudo"></div>

</div>
</div>

<div id="suggestionsModal" class="suggestions-modal" onclick="fecharSugestoes(event)"><div class="suggestions-panel" onclick="event.stopPropagation()"><div class="suggestions-head"><div><h2>❤️ QUE TAL LEVAR MAIS UM?</h2><small style="color:#999">Escolha uma sugestão e adicione ao pedido.</small></div><button class="suggestions-close" onclick="fecharSugestoes()">×</button></div><div id="suggestionsGrid" class="suggestions-grid"></div><button class="btn btn-finalizar-pedido" style="margin-top:12px" onclick="fecharSugestoes()">CONTINUAR PARA O PEDIDO</button></div></div>

<footer class="rodape-instagram">

<div class="instagram-destaque">

<div class="instagram-icone">
📸
</div>

<div class="instagram-texto">

<span>
SIGA A ND BURGS
</span>

<strong>
@ndburgs
</strong>

<p>
Acompanhe nossas novidades,
promoções e lançamentos!
</p>

</div>

<a
href="https://www.instagram.com/ndburgs/"
target="_blank"
rel="noopener noreferrer"
class="instagram-botao"
>
📲 SEGUIR NO INSTAGRAM
</a>

</div>

<div class="rodape-final">

ND BURGS © 2026
<br>
Obrigado pela preferência ❤️

</div>

</footer>




<!-- =========================
     ND BURGS — MELHORIAS PRO 2.0
========================= -->



</div>




















<!-- =========================================================
     ND BURGS — RODADA 5
     EXPERIÊNCIA PREMIUM + PERFORMANCE
     Camada adicional sobre a RODADA 4 — não substitui funções existentes.
     ========================================================= -->




<!-- =========================================================
     ND BURGS — RODADA 7
     CONVERSÃO INTELIGENTE + EXPERIÊNCIA PREMIUM
     Camada adicional. Não substitui funções existentes.
     ========================================================= -->




<!-- =========================================================
     ND BURGS — RODADA 8
     UX MOBILE + CHECKOUT SEM FRICÇÃO + PERFORMANCE
     Camada adicional. Preserva as rodadas anteriores.
     ========================================================= -->



<!-- =========================================================
     ND BURGS — RODADA 9
     CONVERSÃO MÁXIMA + CHECKOUT PREMIUM
     Camada adicional. Não substitui a lógica existente.
     ========================================================= -->


<!-- ND BURGS VERSION: 20260904-R10 -->


<!-- =========================================================
     ND BURGS — ETAPA 11
     INTELIGÊNCIA DE VENDAS + RETENÇÃO
     Camada adicional e independente.
     ========================================================= -->


<!-- ND BURGS VERSION: 20260904-R11 -->


<!-- ND BURGS — ETAPA 12: BLACKOUT TOTAL + REFINAMENTO VISUAL -->


<!-- ND BURGS VERSION: 20260904-R12 -->



<!-- ND BURGS — ETAPA 13: HIERARQUIA VISUAL PREMIUM NO BLACKOUT -->


<!-- ND BURGS VERSION: 20260904-R13 -->


<!-- ND BURGS — ETAPA 14: BUSCA INTELIGENTE + NAVEGAÇÃO RÁPIDA -->




<!-- ND BURGS — ETAPA 15: NAVEGAÇÃO PREMIUM POR CATEGORIAS -->


<!-- ND BURGS VERSION: 20260904-R15 -->


<!-- =========================================================
     ND BURGS — ETAPA 16
     EXPERIÊNCIA DOS PRODUTOS + TOTAL COM TAXA DE ENTREGA
     Camada adicional. Favoritos preservados integralmente.
     ========================================================= -->



<!-- =========================================================
     ND BURGS — RODADA 17
     ENDEREÇO PRIMEIRO + TAXA NO TOTAL + WHATSAPP SIMPLES
     + BOTÕES AZUIS + PREÇOS EM DESTAQUE + LOGO REPOSICIONADA
     Favoritos preservados: nenhum botão de coração é interceptado.
     ========================================================= -->


<div id="nd17Gate" aria-modal="true" role="dialog">
 <div class="nd17-gate-panel">
  <div class="nd17-kicker">ANTES DE MONTAR SEU PEDIDO</div>
  <h2>Onde vamos entregar?</h2>
  <p>Informe seu endereço agora. Assim a taxa de entrega já aparece no carrinho, na revisão e no pedido enviado para a ND BURGS.</p>
  <div class="nd17-field nd17-suggest"><label>Rua / endereço</label><input id="nd17GateStreet" type="search" autocomplete="off" placeholder="Digite o nome da rua"><div id="nd17GateList" class="nd17-list"></div></div>
  <div class="nd17-field"><label>Número</label><input id="nd17GateNumber" type="text" inputmode="numeric" placeholder="Número da residência"></div>
  <button id="nd17GateSave" class="nd17-gate-main" type="button">CONTINUAR COM DELIVERY</button>
  <button id="nd17GatePickup" class="nd17-gate-retirada" type="button">VOU RETIRAR NO LOCAL</button>
 </div>
</div>


<!-- ND BURGS ETAPA 18 - CATEGORIAS LATERAIS -->











<!-- =========================================================
     ND BURGS — ETAPA 23 — RECONSTRUÇÃO FINAL DA EXPERIÊNCIA
     Corrige carrinho, checkout, endereço, categorias e visual.
     Camada isolada: não substitui a lógica de produtos.
     ========================================================= -->







<script>

const taxas = {
"AV ATLETICO":9,
"AV LYONS":5,
"AV MARABAS":4,
"AV MARAMBAIA":4,
"AV TORRE ALBERT MUNCK":6,
"AVENIDA BRASIL":5,
"AVENIDA PROFESSOR MANOEL JOSE PEDROSO":7,
"BALCAO":0,
"CONDOMINIO PARQUE REAL":9,
"CONDOMINIO VALE VERDE":10,
"ESTRADA DO ATALAIA":6,
"ESTRADA DO MORRO GRANDE":9,
"ESTRADA DO PADRE INACIO":6,
"ESTRADA DOS FISCHER'S":7,
"ESTRADA VELHA DA OLARIA":5,
"MANDELINHA KENKIT":5,
"MANDELINHA PARTE DE CIMA":5,
"MANDELINHA PORTO ALEGRE":5,
"POINT DO DIGO":6,
"RETIRADA":0,
"RUA 7":6,
"RUA ACLIMACAO":6,
"RUA ADOVEL QUINTINO":6,
"RUA AGULHAS NEGRAS":7,
"RUA ALAGOINHAS":6,
"RUA ARCO DOURADO":5,
"RUA ARCO VERDE":5,
"RUA BELMONTE":5,
"RUA BENEDITO MARIA DE JESUS":5,
"RUA BRASILIA":7,
"RUA BRUMADO":6,
"RUA CAETETE":6,
"RUA CAIAPO":7,
"RUA CAIO GRACO":5,
"RUA CALIL FILHO":8,
"RUA CAMINHO EXISTENTE":4,
"RUA CARMEN MIRANDA":9,
"RUA CIRO MONTEIRO":9,
"RUA COAPA":6,
"RUA COMODORO":5,
"RUA DAS AMEIXEIRAS":3,
"RUA DAS BANANEIRAS":3,
"RUA DOS COQUEIRAIS":3,
"RUA DAS DAMASQUEIRAS":3,
"RUA DAS MACIEIRAS":3,
"RUA DAS MORANGUEIRAS":3,
"RUA DESPORTIVA":9,
"RUA DR APARECIDA J DOMINGUES":4,
"RUA DR ODAIR PACHECO PEDROSO":8,
"RUA ERICO VERISSIMO":7,
"RUA ERIVELTON MARTINS":7,
"RUA ESPLANADA":5,
"RUA EXISTENTE":4,
"RUA FELISBINO DE OLIVEIRA":8,
"RUA FRANCISCO ALVES":9,
"RUA FUGI":8,
"RUA GRACIANO SOARES DE ARAUJO":5,
"RUA INDUSQUIMICA":5,
"RUA IPIRANGA":6,
"RUA ISMENIA":6,
"RUA ITABUNA":6,
"RUA ITAGUAI":6,
"RUA ITAPETI":7,
"RUA ITARIRI":4,
"RUA JACOBINA":5,
"RUA JOAQUIM RUAS":6,
"RUA JUQUITIBA":4,
"RUA LAMARTINE BABO":9,
"RUA LEVER":6,
"RUA PADRE LUIZ MARTINE":5,
"RUA MADRESSILVAS":6,
"RUA MARIO ANDREATINI":4,
"RUA METAL LEVE":5,
"RUA MIL FOLHAS":9,
"RUA MIRAMAR":5,
"RUA MOÇAMBIQUE":9,
"RUA NILO":9,
"RUA NOGAM":6,
"RUA NOVA ODESSA":6,
"RUA NOVA OLINDA":6,
"RUA NOVA PATRIA":6,
"RUA NOVA SAO PAULO":6,
"RUA ODETE":6,
"RUA OMA":9,
"RUA OTELO ZELONI":7,
"RUA PACARAIMA":8,
"RUA PALMAS":9,
"RUA PARANA":7,
"RUA PAULO SERGIO LEMOS":7,
"RUA PENHA":6,
"RUA PIRINEUS":8,
"RUA PONTA GROSSA":4,
"RUA PORTO ALEGRE":5,
"RUA PROFESSOR ZOE PEREIRA BENIAMINO":6,
"RUA REGISTRO":4,
"RUA RIBEIRAO PIRES":4,
"RUA RIO BRANCO":5,
"RUA RIO CLARO":5,
"RUA MARANHAO":7,
"RUA SANTA MARIA IMACULADA":5,
"RUA SANTA MATILDE":6,
"RUA SANTO AGOSTINO":7,
"RUA SAO BENEDITO":7,
"RUA SAO CIPRIANO":6,
"RUA SAO CRISTOVAO":6,
"RUA SAO GEREMIAS":6,
"RUA SAO PAULO":6,
"RUA SAO PAULO DAS MISSOES":7,
"RUA SAO SERAFIM":6,
"RUA SERGIO CARDOSO":6,
"RUA SILVA TELES":9,
"RUA TIBERIO":5,
"RUA TORQUARO NETO":6,
"RUA UGANDA":9,
"RUA VICENTE CELESTINO":9,
"RUA VICENTE STRIFEZZI":15,
"RUA VILA VERDE":5,
"RUA VOTURAMA":7,
"RUA WELCOME":5,
"RUA ZIEMBINSKI":7,
"VIELA DOS FISCHERS":9,
"ESTRADA DAS GRAÇAS":4,
"RUA NOVA TRINDADE":6,
"RUA APENINOS":12,
"RUA VERA CRUZ":5,
"MERCADO LIVRE":15,
"RUA SANTA QUITERIA":6,
"RUA ITAPETININGA":5,
"RUA MELGAXE":9,
"RUA GETULIO VARGAS":8,
"IDOMINEU ANTUNES CALDEIRA":9,
"RUA PATATIVA":7,
"RUA MOEMA":6
};

window.taxas = taxas;

/* =========================
   CARRINHO SALVO
========================= */

const CHAVE_CARRINHO="ndburgs_carrinho";

var carrinho=[];
// Compatibilidade global: todas as camadas das Rodadas 1–23 enxergam o mesmo carrinho.
window.carrinho = carrinho;

function salvarCarrinho(){

try{

localStorage.setItem(
CHAVE_CARRINHO,
JSON.stringify(carrinho)
);

}catch(e){}

}

function carregarCarrinhoSalvo(){

try{

const salvo=
localStorage.getItem(CHAVE_CARRINHO);

if(!salvo)return;

const dados=
JSON.parse(salvo);

if(Array.isArray(dados)){
carrinho=dados; window.carrinho=carrinho;
}

}catch(e){

carrinho=[];

}

}

function moeda(valor){

return Number(valor).toLocaleString(
"pt-BR",
{
style:"currency",
currency:"BRL"
}
);

}

const produtosPersonalizaveis={

acai:{
titulo:"AÇAÍ",
tamanhos:[
["200ML",11.90],
["300ML",15.00],
["400ML",18.00],
["700ML",32.00]
],
acompanhamentos:[
["CALDA DE MORANGO",0],
["CALDA DE CHOCOLATE",0],
["LEITE CONDENSADO",0],
["PAÇOCA",0],
["OREO",0],
["CONFETE",0],
["OVOMALTINE",0],
["NESQUIK",0],
["NUTELLA",5],
["SUCRILHOS",0],
["GRANOLA",0],
["MORANGO",0],
["MANGA",0],
["BANANA",0],
["LEITE EM PÓ",0],
["KIT KAT",3],
["CHOCOBALL",0],
["DOCE DE LEITE",0],
["CREME DE NINHO",3],
["KIWI",0]
]
},

casadinho:{
titulo:"CASADINHO",
tamanhos:[
["200ML",11.90]
],
acompanhamentos:[]
},

truffado:{
titulo:"AÇAÍ TRUFFADO",
tamanhos:[
["300ML",26.00],
["400ML",29.00],
["700ML",43.00]
],
acompanhamentos:[]
},

tentacao:{
titulo:"TENTAÇÃO DE MORANGO",
tamanhos:[
["300ML",18.00],
["400ML",18.00],
["700ML",32.00]
],
acompanhamentos:[]
},

milkOvomaltine:{
titulo:"MILKSHAKE OVOMALTINE",
tamanhos:[
["300ML",15],
["400ML",18],
["700ML",30]
],
acompanhamentos:[]
},

milkOreo:{
titulo:"MILKSHAKE OREO",
tamanhos:[
["300ML",15],
["400ML",18],
["700ML",30]
],
acompanhamentos:[]
},

milkPacoca:{
titulo:"MILKSHAKE PAÇOCA",
tamanhos:[
["300ML",15],
["400ML",18],
["700ML",30]
],
acompanhamentos:[]
},

milkNesquik:{
titulo:"MILKSHAKE NESQUIK",
tamanhos:[
["300ML",15],
["400ML",18],
["700ML",30]
],
acompanhamentos:[]
},

milkNinho:{
titulo:"MILKSHAKE LEITE NINHO",
tamanhos:[
["300ML",15],
["400ML",18],
["700ML",30]
],
acompanhamentos:[]
},

milkAcai:{
titulo:"MILKSHAKE DE AÇAÍ",
tamanhos:[
["300ML",15],
["400ML",18],
["700ML",30]
],
acompanhamentos:[]
},

batata:{
titulo:"BATATA",
tamanhos:[
["P",6],
["M",15],
["G",32]
],
acompanhamentos:[]
},

batataCompleta:{
titulo:"BATATA COMPLETA",
tamanhos:[
["P",12],
["M",21],
["G",57]
],
acompanhamentos:[]
},

nuggets:{
titulo:"NUGGETS",
tamanhos:[
["P",9],
["M",16],
["G",55]
],
acompanhamentos:[]
},

anelCebola:{
titulo:"ANEL DE CEBOLA",
tamanhos:[
["P",9],
["M",16],
["G",55]
],
acompanhamentos:[]
},

frangoFrito:{
titulo:"FRANGO FRITO",
tamanhos:[
["P",15],
["M",27],
["G",70]
],
acompanhamentos:[]
}

};

const saboresPasteis={

salgados:[

["PASTEL DE CARNE",11],
["PASTEL DE CARNE COM QUEIJO",11],
["PASTEL DE CARNE COM CHEDDAR",11],
["PASTEL DE CARNE COM CATUPIRY",11],
["PASTEL DE QUEIJO",11],
["PASTEL DE FRANGO",11],
["PASTEL DE FRANGO COM QUEIJO",11],
["PASTEL DE FRANGO COM CATUPIRY",11],
["PASTEL DE FRANGO COM CHEDDAR",11],
["PASTEL DE BAURU",11],
["PASTEL DE PIZZA",11],
["PASTEL DE FRANGO COM QUEIJO E OVO",11],
["PASTEL DE CARNE COM OVO",11],
["PASTEL DE PRESUNTO COM QUEIJO",11],
["PASTEL 3 QUEIJOS",11],
["PASTEL ND",11],
["PASTEL ESPECIAL",15]

],

doces:[

["PASTEL A MODA CAROL",15],
["PASTEL DE NUTELLA COM BANANA",13],
["PASTEL DE DOCE DE LEITE COM BANANA",13],
["PASTEL DE NINHO COM MORANGO",13],
["PASTEL DE NINHO",13],
["PASTEL DE KITKAT COM NINHO",13],
["PASTEL DE NINHO COM OREO",13,"https://i.ibb.co/Hp1JT71N/Chat-GPT-Image-25-06-2026-23-40-43.png"],
["PASTEL DE NUTELLA COM MORANGO",13,"https://i.ibb.co/TMjs2Z7V/Chat-GPT-Image-25-06-2026-23-46-39.png"],
["PASTEL DE NUTELLA",13,"https://i.ibb.co/5x68nMyh/Chat-GPT-Image-25-06-2026-23-28-35.png"],
["PASTEL DUO NUTELLA COM CREME DE NINHO",13,"https://i.ibb.co/nM3ncdZ3/Chat-GPT-Image-25-06-2026-23-57-41.png"]

]

};

let produtoModalAtual=null;
let toastTimer=null;

function mostrarToast(texto){ /* feedback antigo desativado para evitar mensagens duplicadas */ }


/* =========================
   FECHAR MODAL DE PERSONALIZAÇÃO
========================= */
function fecharPersonalizacao(){

const modal =
document.getElementById("modalPersonalizacao");

if(modal){
modal.style.display="none";
}

document.body.style.overflow="";

produtoModalAtual=null;
}

function abrirPersonalizacao(chave){
if(chave==="pasteis"){

const modal=
document.getElementById("modalPersonalizacao");

const conteudo=
document.getElementById("modalConteudo");

document.getElementById("modalTitulo").innerText=
"🥟 ESCOLHA SEU PASTEL";

produtoModalAtual={
tipo:"pasteis"
};

let html=
`<div class="modal-secao" style="margin-top:0;padding-top:0;border-top:0"><h3>🥟 PASTÉIS SALGADOS</h3><div class="lista-acompanhamentos">`;

saboresPasteis.salgados.forEach((p,i)=>{

html+=
`<label class="opcao-acomp" style="justify-content:space-between"><span style="display:flex;align-items:center;gap:8px"><input type="radio" name="pastelModal" value="salgados|${i}" onchange="atualizarTotalModalPastel()"><span>${p[0]}</span></span><strong class="preco-adicional">${moeda(p[1])}</strong></label>`;

});

html+=
`</div></div><div class="modal-secao"><h3>🍫 PASTÉIS DOCES</h3><div class="lista-acompanhamentos">`;

saboresPasteis.doces.forEach((p,i)=>{

html+=
`<label class="opcao-acomp" style="justify-content:space-between"><span style="display:flex;align-items:center;gap:8px"><input type="radio" name="pastelModal" value="doces|${i}" onchange="atualizarTotalModalPastel()"><span>${p[0]}</span></span><strong class="preco-adicional">${moeda(p[1])}</strong></label>`;

});

html+=
`</div></div><div class="modal-total"><span>TOTAL</span><strong id="modalTotal">ESCOLHA UM SABOR</strong></div><button class="btn btn-confirmar-personalizacao" onclick="confirmarPersonalizacaoPastel()">✅ ADICIONAR AO CARRINHO</button>`;

conteudo.innerHTML=html;

modal.style.display="flex";

document.body.style.overflow="hidden";

return;

}

const produto=
produtosPersonalizaveis[chave];

if(!produto)return;

produtoModalAtual=produto;

const modal=
document.getElementById("modalPersonalizacao");

const conteudo=
document.getElementById("modalConteudo");

document.getElementById("modalTitulo").innerText=
produto.titulo;

let html=
`<div class="modal-secao"><h3>📏 ESCOLHA O TAMANHO</h3><div class="opcoes-tamanho">`;

produto.tamanhos.forEach((t,i)=>{

html+=
`<div class="opcao-tamanho"><input type="radio" name="tamanhoModal" id="tam_${i}" value="${i}" ${i===0?'checked':''} onchange="atualizarTotalModal()"><label for="tam_${i}">${t[0]}<br>${moeda(t[1])}</label></div>`;

});

html+=
`</div></div>`;

if(
produto.acompanhamentos &&
produto.acompanhamentos.length
){

html+=
`<div class="modal-secao"><h3>🍓 ACOMPANHAMENTOS</h3><div class="lista-acompanhamentos">`;

produto.acompanhamentos.forEach((a,i)=>{

const pago=a[1]>0;

html+=
`<label class="opcao-acomp"><input type="checkbox" name="acompModal" value="${i}" onchange="atualizarTotalModal()"><span>${a[0]} ${pago?`<span class="preco-adicional">+ ${moeda(a[1])}</span>`:`<span>GRÁTIS</span>`}</span></label>`;

});

html+=
`</div></div>`;

}

html+=
`<div class="modal-total"><span>TOTAL</span><strong id="modalTotal">${moeda(produto.tamanhos[0][1])}</strong></div><button class="btn btn-confirmar-personalizacao" onclick="confirmarPersonalizacao()">✅ ADICIONAR AO CARRINHO</button>`;

conteudo.innerHTML=html;

modal.style.display="flex";

document.body.style.overflow="hidden";

}

function atualizarTotalModalPastel(){

const selecionado=
document.querySelector(
'input[name="pastelModal"]:checked'
);

const total=
document.getElementById("modalTotal");

if(!selecionado){

total.innerText=
"ESCOLHA UM SABOR";

return;

}

const partes=
selecionado.value.split("|");

const lista=
saboresPasteis[partes[0]];

const pastel=
lista[
parseInt(partes[1],10)
];

total.innerText=
moeda(pastel[1]);

}

function confirmarPersonalizacaoPastel(){

const selecionado=
document.querySelector(
'input[name="pastelModal"]:checked'
);

if(!selecionado){

alert("Escolha o sabor do pastel.");

return;

}

const partes=
selecionado.value.split("|");

const lista=
saboresPasteis[partes[0]];

const pastel=
lista[
parseInt(partes[1],10)
];

for(let i=0;i<Math.max(1,Number(window.ndPendingQty)||1);i++) adicionar(pastel[0],pastel[1]);

window.ndPendingQty=1;

fecharPersonalizacao();

}

function atualizarTotalModal(){

if(!produtoModalAtual)return;

const tamanhoSelecionado=
document.querySelector(
'input[name="tamanhoModal"]:checked'
);

if(!tamanhoSelecionado)return;

const tamanho=
produtoModalAtual.tamanhos[
parseInt(
tamanhoSelecionado.value,
10
)
];

let total=tamanho[1];

let acompanhamentosNormais=0;

document.querySelectorAll(
'input[name="acompModal"]:checked'
).forEach(el=>{

const acomp=
produtoModalAtual.acompanhamentos[
parseInt(el.value,10)
];

const nome=
acomp[0].toUpperCase();

if(nome==="NUTELLA"){

total+=5;

}else if(
nome==="CREME DE NINHO" ||
nome==="KIT KAT"
){

total+=3;

}else{

acompanhamentosNormais++;

if(acompanhamentosNormais>3){

total+=3;

}

}

});

document.getElementById("modalTotal").innerText=
moeda(total);

}

function confirmarPersonalizacao(){

if(!produtoModalAtual)return;

const tamanhoSelecionado=
document.querySelector(
'input[name="tamanhoModal"]:checked'
);

if(!tamanhoSelecionado)return;

const tamanho=
produtoModalAtual.tamanhos[
parseInt(
tamanhoSelecionado.value,
10
)
];

let preco=tamanho[1];

const detalhes=[];

let acompanhamentosNormais=0;

document.querySelectorAll(
'input[name="acompModal"]:checked'
).forEach(el=>{

const acomp=
produtoModalAtual.acompanhamentos[
parseInt(el.value,10)
];

const nome=
acomp[0].toUpperCase();

let valorAdicional=0;

if(nome==="NUTELLA"){

valorAdicional=5;

}else if(
nome==="CREME DE NINHO" ||
nome==="KIT KAT"
){

valorAdicional=3;

}else{

acompanhamentosNormais++;

if(acompanhamentosNormais>3){

valorAdicional=3;

}

}

preco+=valorAdicional;

detalhes.push(
acomp[0]+
(valorAdicional>0?
" ("+moeda(valorAdicional)+")":
"")
);

});

carrinho.push({

nome:
produtoModalAtual.titulo+
" "+
tamanho[0],

preco:preco,

quantidade:Math.max(1,Number(window.ndPendingQty)||1),

detalhes:detalhes,

tamanho:tamanho[0]

});

atualizarCarrinho();

window.ndPendingQty=1;

fecharPersonalizacao();

}

function adicionar(nome,preco){

const existente=
carrinho.find(
item=>
item.nome===nome &&
!item.detalhes
);

if(existente){

existente.quantidade++;

}else{

carrinho.push({

nome:nome,

preco:preco,

quantidade:1

});

}

atualizarCarrinho();

mostrarToast(
"✅ "+nome+" adicionado"
);

}

function alterarQuantidade(index,valor){

if(!carrinho[index])return;

carrinho[index].quantidade+=valor;

if(
carrinho[index].quantidade<=0
){

carrinho.splice(index,1);

}

atualizarCarrinho();

}

function removerItem(index){

carrinho.splice(index,1);

atualizarCarrinho();

}

function calcularSubtotal(){

return carrinho.reduce(
(soma,item)=>
soma+
item.preco*
item.quantidade,
0
);

}

function obterTaxaEntrega(){

const tipo=
document.getElementById(
"tipoPedido"
).value;

if(tipo!=="ENTREGA")
return 0;

const selectRua=
document.getElementById("rua");

const ruaSelecionada=
selectRua?
selectRua.value:
"";

if(
ruaSelecionada &&
Object.prototype.hasOwnProperty.call(
taxas,
ruaSelecionada
)
){

return Number(
taxas[ruaSelecionada]
);

}

return 0;

}

function atualizarAvisoTaxa(){

const tipo=
document.getElementById(
"tipoPedido"
).value;

const selectRua=
document.getElementById("rua");

const aviso=
document.getElementById("avisoTaxa");

if(!aviso)return;

if(tipo!=="ENTREGA"){

aviso.style.display="none";

return;

}

const rua=
selectRua.value;

if(
rua &&
taxas[rua]!==undefined
){

const taxa=
Number(taxas[rua]);

aviso.style.display="block";

aviso.innerHTML=
"🏍️ Taxa para <strong>"+
rua+
"</strong>: <strong>"+
moeda(taxa)+
"</strong>";

}else{

aviso.style.display="none";

aviso.innerHTML="";

}

}

function atualizarCarrinho(){

const area=
document.getElementById(
"carrinhoItens"
);

area.innerHTML="";

let subtotal=0;

let quantidadeTotal=0;

if(carrinho.length===0){

area.innerHTML=
`<div class="vazio">Seu carrinho está vazio.</div>`;

}

carrinho.forEach((item,index)=>{

const totalItem=
item.preco*
item.quantidade;

subtotal+=totalItem;

quantidadeTotal+=
item.quantidade;

area.innerHTML+=`

<div class="item-carrinho">

<div class="item-info">

<strong>
${item.nome}
</strong>

<small>
${moeda(item.preco)} cada
</small>

${
item.detalhes &&
item.detalhes.length
?
`<small style="display:block;color:#f5c400;margin-top:5px;line-height:1.5;">↳ ${item.detalhes.join(", ")}</small>`
:
""
}

</div>

<div class="controles">

<button onclick="alterarQuantidade(${index},-1)">
−
</button>

<strong>
${item.quantidade}
</strong>

<button onclick="alterarQuantidade(${index},1)">
+
</button>

<button
class="remover"
onclick="removerItem(${index})"
>
X
</button>

</div>

<strong>
${moeda(totalItem)}
</strong>

</div>

`;

});

document.getElementById(
"subtotal"
).innerText=
moeda(subtotal);

atualizarCarrinhoFlutuante(
quantidadeTotal,
subtotal
);

atualizarModalCarrinho();

calcularTaxa();

salvarCarrinho();

}

function atualizarCarrinhoFlutuante(
quantidade,
subtotal
){

const barra=
document.getElementById(
"carrinhoFlutuante"
);

const contador=
document.getElementById(
"contadorCarrinho"
);

const total=
document.getElementById(
"totalCarrinhoFlutuante"
);

if(carrinho.length===0){

barra.classList.remove("ativo");

contador.innerText=
"0 itens";

total.innerText=
"R$ 0,00";

return;

}

const taxa=
obterTaxaEntrega();

const valorTotal=
subtotal+taxa;

barra.classList.add("ativo");

contador.innerText=
quantidade+
(
quantidade===1?
" item":
" itens"
);

total.innerText=
moeda(valorTotal);

}

function abrirCarrinho(){

if(carrinho.length===0)
return;

atualizarModalCarrinho();

document.getElementById(
"modalCarrinho"
).classList.add("ativo");

document.body.style.overflow=
"hidden";

}

function fecharCarrinho(event){

if(
event &&
event.target &&
event.target.id!=="modalCarrinho"
)
return;

document.getElementById(
"modalCarrinho"
).classList.remove("ativo");

document.body.style.overflow="";

}

function atualizarModalCarrinho(){

const area=
document.getElementById(
"itensCarrinhoModal"
);

if(!area)return;

area.innerHTML="";

if(carrinho.length===0){

area.innerHTML=
`<div class="vazio">Seu carrinho está vazio.</div>`;

}

let subtotal=0;

carrinho.forEach((item,index)=>{

const totalItem=
item.preco*
item.quantidade;

subtotal+=totalItem;

area.innerHTML+=`

<div class="item-carrinho-modal">

<div class="item-carrinho-modal-topo">

<div>

<strong>
${item.nome}
</strong>

<small>
${moeda(item.preco)} cada
</small>

${
item.detalhes &&
item.detalhes.length
?
`<small style="color:#f5c400">↳ ${item.detalhes.join(", ")}</small>`
:
""
}

</div>

<strong>
${moeda(totalItem)}
</strong>

</div>

<div class="controles-modal">

<button onclick="alterarQuantidade(${index},-1)">
−
</button>

<strong>
${item.quantidade}
</strong>

<button onclick="alterarQuantidade(${index},1)">
+
</button>

<button
class="remover"
onclick="removerItem(${index})"
>
X
</button>

</div>

</div>

`;

});

const taxa=
obterTaxaEntrega();

const total=
subtotal+taxa;

document.getElementById(
"subtotalCarrinhoModal"
).innerText=
moeda(subtotal);

document.getElementById(
"taxaCarrinhoModal"
).innerText=
moeda(taxa);

document.getElementById(
"totalCarrinhoModal"
).innerText=
moeda(total);

}

/* =========================
   CONTINUAR COMPRANDO
========================= */

function irParaCheckout(){

fecharCarrinho();

setTimeout(()=>{

const checkout=
document.getElementById(
"checkout"
);

if(checkout){

checkout.scrollIntoView({

behavior:"smooth",

block:"start"

});

}

},150);

}

/* =========================
   ABRIR MODAL FINALIZAÇÃO
========================= */

function irParaFinalizarPedido(){

fecharCarrinho();

const modal=
document.getElementById(
"modalFinalizar"
);

if(!modal)return;

carregarRuasModal();

copiarDadosFormularioParaModal();

atualizarResumoFinalizarModal();

modal.classList.add("ativo");

document.body.style.overflow=
"hidden";

}

/* =========================
   FECHAR MODAL FINALIZAÇÃO
========================= */

function fecharModalFinalizar(event){

if(
event &&
event.target &&
event.target.id!=="modalFinalizar"
)
return;

const modal=
document.getElementById(
"modalFinalizar"
);

if(modal){

modal.classList.remove("ativo");

}

document.body.style.overflow="";

}

/* =========================
   COPIAR DADOS EXISTENTES
========================= */

function copiarDadosFormularioParaModal(){

const pares=[

["nome","nomeModal"],
["telefone","telefoneModal"],
["tipoPedido","tipoPedidoModal"],
["rua","ruaModal"],
["numero","numeroModal"],
["complemento","complementoModal"],
["pagamento","pagamentoModal"],
["troco","trocoModal"],
["observacao","observacaoModal"]

];

pares.forEach(par=>{

const origem=
document.getElementById(par[0]);

const destino=
document.getElementById(par[1]);

if(
origem &&
destino
){

destino.value=
origem.value;

}

});

alterarTipoPedidoModal();

alterarPagamentoModal();

}

/* =========================
   RUAS DO MODAL
========================= */

function carregarRuasModal(){

const select=
document.getElementById(
"ruaModal"
);

if(!select)return;

const valorAtual=
select.value;

select.innerHTML=
'<option value="">Selecione sua rua</option>';

const ruas=
Object.keys(taxas)
.filter(
rua=>
rua!=="BALCAO" &&
rua!=="RETIRADA" &&
rua!=="IFOOD" &&
rua!=="99FOOD"
)
.sort(
(a,b)=>
a.localeCompare(
b,
"pt-BR"
)
);

ruas.forEach(rua=>{

const option=
document.createElement(
"option"
);

option.value=rua;

option.textContent=
rua+
" — "+
moeda(taxas[rua]);

select.appendChild(option);

});

if(
valorAtual &&
taxas[valorAtual]!==undefined
){

select.value=
valorAtual;

}

}

/* =========================
   TIPO PEDIDO MODAL
========================= */

function alterarTipoPedidoModal(){

const tipo=
document.getElementById(
"tipoPedidoModal"
).value;

const enderecoArea=
document.getElementById(
"enderecoAreaModal"
);

if(tipo==="ENTREGA"){

enderecoArea.style.display=
"block";

}else{

enderecoArea.style.display=
"none";

}

calcularTaxaModal();

}

/* =========================
   TAXA MODAL
========================= */

function calcularTaxaModal(){

const tipo=
document.getElementById(
"tipoPedidoModal"
).value;

const rua=
document.getElementById(
"ruaModal"
).value;

let taxa=0;

const aviso=
document.getElementById(
"avisoTaxaModal"
);

if(
tipo==="ENTREGA" &&
rua
){

taxa=
Number(
taxas[rua]||0
);

if(aviso){

aviso.style.display=
"block";

aviso.innerHTML=
"🏍️ Taxa para <strong>"+
rua+
"</strong>: <strong>"+
moeda(taxa)+
"</strong>";

}

}else{

if(aviso){

aviso.style.display=
"none";

aviso.innerHTML="";

}

}

atualizarResumoFinalizarModal();

return taxa;

}

/* =========================
   PAGAMENTO MODAL
========================= */

function alterarPagamentoModal(){

const pagamento=
document.getElementById(
"pagamentoModal"
).value;

const area=
document.getElementById(
"trocoAreaModal"
);

if(
pagamento==="DINHEIRO"
){

area.style.display=
"block";

}else{

area.style.display=
"none";

}

}

/* =========================
   RESUMO MODAL
========================= */

function atualizarResumoFinalizarModal(){

const subtotal=
calcularSubtotal();

const tipoElemento=
document.getElementById(
"tipoPedidoModal"
);

const ruaElemento=
document.getElementById(
"ruaModal"
);

let taxa=0;

if(
tipoElemento &&
ruaElemento &&
tipoElemento.value==="ENTREGA"
){

taxa=
Number(
taxas[ruaElemento.value]||0
);

}

const total=
subtotal+taxa;

const subtotalEl=
document.getElementById(
"subtotalFinalizarModal"
);

const taxaEl=
document.getElementById(
"taxaFinalizarModal"
);

const totalEl=
document.getElementById(
"totalFinalizarModal"
);

if(subtotalEl)
subtotalEl.innerText=
moeda(subtotal);

if(taxaEl)
taxaEl.innerText=
moeda(taxa);

if(totalEl)
totalEl.innerText=
moeda(total);

}

/* =========================
   FINALIZAR PELO MODAL
========================= */

function finalizarPedidoModal(){

if(carrinho.length===0){

alert(
"Adicione pelo menos um produto ao carrinho."
);

return;

}

const nome=
document.getElementById(
"nomeModal"
).value.trim();

const telefone=
document.getElementById(
"telefoneModal"
).value.trim();

const tipo=
document.getElementById(
"tipoPedidoModal"
).value;

const rua=
document.getElementById(
"ruaModal"
).value;

const numero=
document.getElementById(
"numeroModal"
).value.trim();

const complemento=
document.getElementById(
"complementoModal"
).value.trim();

const pagamento=
document.getElementById(
"pagamentoModal"
).value;

const troco=
document.getElementById(
"trocoModal"
).value;

const observacao=
document.getElementById(
"observacaoModal"
).value.trim();

if(!nome){

alert("Digite seu nome.");

document.getElementById(
"nomeModal"
).focus();

return;

}

if(!telefone){

alert(
"📱 Digite seu telefone."
);

document.getElementById(
"telefoneModal"
).focus();

return;

}

const telefoneNumeros =
telefone.replace(/\D/g,"");

if(telefoneNumeros.length<10){

alert(
"📱 TELEFONE INVÁLIDO\n\n"+
"Digite um telefone válido com DDD."
);

document.getElementById(
"telefoneModal"
).focus();

return;

}

if(telefoneNumeros.length>11){

alert(
"📱 TELEFONE INVÁLIDO\n\n"+
"Confira o número informado."
);

document.getElementById(
"telefoneModal"
).focus();

return;

}

if(tipo==="ENTREGA"){

if(!rua){

alert("Selecione sua rua.");

document.getElementById(
"ruaModal"
).focus();

return;

}

if(!numero){

alert(
"Digite o número do endereço."
);

document.getElementById(
"numeroModal"
).focus();

return;

}

}

if(tipo==="ENTREGA"){

const subtotalMinimo=11.90;

const subtotalAtual=
carrinho.reduce(
(soma,item)=>
soma+
(item.preco*item.quantidade),
0
);

if(subtotalAtual<subtotalMinimo){

const falta=
subtotalMinimo-subtotalAtual;

alert(
"🏍️ PEDIDO MÍNIMO PARA DELIVERY\n\n"+
"Para delivery, o pedido mínimo é "+
moeda(subtotalMinimo)+".\n\n"+
"Seu pedido está em "+
moeda(subtotalAtual)+".\n"+
"Faltam "+
moeda(falta)+
" para poder finalizar."
);

return;

}

}
   
if(!pagamento){

alert(
"Selecione a forma de pagamento."
);

document.getElementById(
"pagamentoModal"
).focus();

return;

}

if(
pagamento==="DINHEIRO"
){

if(!troco){

alert(
"💵 INFORME O VALOR DO TROCO\n\n"+
"Digite quanto você irá pagar em dinheiro."
);

document.getElementById(
"trocoModal"
).focus();

return;

}

const valorTroco=
parseFloat(troco);

const subtotalAtual=
carrinho.reduce(
(soma,item)=>
soma+
(item.preco*item.quantidade),
0
);

let taxaAtual=0;

if(tipo==="ENTREGA"){

taxaAtual=
Number(
taxas[rua]||0
);

}

const totalAtual=
subtotalAtual+taxaAtual;

if(
isNaN(valorTroco) ||
valorTroco<=totalAtual
){

alert(
"💵 VALOR PARA TROCO INVÁLIDO\n\n"+
"Total do pedido: "+
moeda(totalAtual)+
"\n\n"+
"Você precisa informar um valor igual ou maior que o total."
);

document.getElementById(
"trocoModal"
).focus();

return;

}

}

let subtotal=0;

let mensagem="";

mensagem+=
"🍔 *NOVO PEDIDO - ND BURGS*%0A";

mensagem+=
"==============================%0A%0A";

mensagem+=
"👤 *CLIENTE:* "+
encodeURIComponent(nome)+
"%0A";

mensagem+=
"📱 *TELEFONE:* "+
encodeURIComponent(telefone)+
"%0A";

mensagem+=
"🏍️ *TIPO:* "+
encodeURIComponent(
tipo==="ENTREGA"?
"DELIVERY":
"RETIRADA"
)+
"%0A";

if(tipo==="ENTREGA"){

mensagem+=
"📍 *ENDEREÇO:* "+
encodeURIComponent(
rua+
", Nº "+
numero
)+
"%0A";

if(complemento){

mensagem+=
"🏠 *COMPLEMENTO:* "+
encodeURIComponent(
complemento
)+
"%0A";

}

}

mensagem+=
"%0A🛒 *ITENS DO PEDIDO*%0A";

mensagem+=
"------------------------------%0A";

carrinho.forEach(item=>{

const totalItem=
item.preco*
item.quantidade;

subtotal+=
totalItem;

mensagem+=
encodeURIComponent(
item.quantidade+
"x "+
item.nome+
" — "+
moeda(totalItem)
)+
"%0A";

if(
item.detalhes &&
item.detalhes.length
){

mensagem+=
encodeURIComponent(
"   ↳ "+
item.detalhes.join(", ")
)+
"%0A";

}

});

let taxa=0;

if(tipo==="ENTREGA"){

taxa=
taxas[rua]!==undefined
?
Number(taxas[rua])
:
0;

}

const total=
subtotal+taxa;

mensagem+=
"%0A";

mensagem+=
"💰 *SUBTOTAL:* "+
encodeURIComponent(
moeda(subtotal)
)+
"%0A";

mensagem+=
"🏍️ *TAXA:* "+
encodeURIComponent(
moeda(taxa)
)+
"%0A";

mensagem+=
"💵 *TOTAL:* "+
encodeURIComponent(
moeda(total)
)+
"%0A";

mensagem+=
"💳 *PAGAMENTO:* "+
encodeURIComponent(
pagamento
)+
"%0A";

if(
pagamento==="DINHEIRO" &&
troco
){

mensagem+=
"💵 *TROCO PARA:* "+
encodeURIComponent(
moeda(
parseFloat(troco)
)
)+
"%0A";

}

if(observacao){

mensagem+=
"%0A📝 *OBSERVAÇÃO:*%0A";

mensagem+=
encodeURIComponent(
observacao
)+
"%0A";

}

mensagem+=
"%0A==============================%0A";

mensagem+=
"ND BURGS 🍔";

const whatsapp=
"5511963973846";

window.open(
"https://wa.me/"+
whatsapp+
"?text="+
mensagem,
"_blank"
);

}

/* =========================
   TAXA FORMULÁRIO ORIGINAL
========================= */

function calcularTaxa(){

const tipo=
document.getElementById(
"tipoPedido"
).value;

let taxa=0;

if(tipo==="ENTREGA"){

const ruaSelecionada=
document.getElementById(
"rua"
).value;

if(
ruaSelecionada &&
taxas[ruaSelecionada]!==undefined
){

taxa=
Number(
taxas[ruaSelecionada]
);

}

}

const subtotal=
calcularSubtotal();

const total=
subtotal+taxa;

document.getElementById(
"taxa"
).innerText=
moeda(taxa);

document.getElementById(
"total"
).innerText=
moeda(total);

atualizarAvisoTaxa();

atualizarCarrinhoFlutuante(
carrinho.reduce(
(soma,item)=>
soma+item.quantidade,
0
),
subtotal
);

atualizarModalCarrinho();

}

/* =========================
   ALTERAR TIPO PEDIDO
========================= */

function alterarTipoPedido(){

const tipo=
document.getElementById(
"tipoPedido"
).value;

const enderecoArea=
document.getElementById(
"enderecoArea"
);

if(tipo==="ENTREGA")
enderecoArea.style.display=
"block";
else
enderecoArea.style.display=
"none";

calcularTaxa();

}

/* =========================
   PAGAMENTO ORIGINAL
========================= */

document.getElementById(
"pagamento"
).addEventListener(
"change",
function(){

const trocoArea=
document.getElementById(
"trocoArea"
);

if(this.value==="DINHEIRO")
trocoArea.style.display=
"block";
else
trocoArea.style.display=
"none";

}
);

/* =========================
   CARREGAR RUAS
========================= */

function carregarRuas(){

const select=
document.getElementById(
"rua"
);

const ruas=
Object.keys(taxas)
.filter(
rua=>
rua!=="BALCAO" &&
rua!=="RETIRADA" &&
rua!=="IFOOD" &&
rua!=="99FOOD"
)
.sort(
(a,b)=>
a.localeCompare(
b,
"pt-BR"
)
);

ruas.forEach(rua=>{

const option=
document.createElement(
"option"
);

option.value=
rua;

option.textContent=
rua+
" — "+
moeda(taxas[rua]);

select.appendChild(option);

});

}

/* =========================
   LIMPAR CARRINHO
========================= */

function limparCarrinho(){

if(carrinho.length===0)
return;

if(
!confirm(
"Deseja realmente limpar o carrinho?"
)
)
return;

carrinho=[];

try{

localStorage.removeItem(
CHAVE_CARRINHO
);

}catch(e){}

atualizarCarrinho();

fecharCarrinho();

}

/* =========================
   NAVEGAÇÃO
========================= */

function irPara(id){

const elemento=
document.getElementById(id);

if(elemento){

elemento.scrollIntoView({

behavior:"smooth",

block:"start"

});

}

}

/* =========================
   HORÁRIO
========================= */

function verificarHorario(){
 const status=document.getElementById("statusHorario");
 if(status){
   status.className="status-aberto";
   status.innerHTML="🟢 ABERTO AGORA • PEDIDOS 24H";
 }
}


/* =========================
   FINALIZAR FORMULÁRIO ORIGINAL
========================= */

function finalizarPedido(){

if(carrinho.length===0){

alert(
"Adicione pelo menos um produto ao carrinho."
);

return;

}

const nome=
document.getElementById(
"nome"
).value.trim();

const telefone=
document.getElementById(
"telefone"
).value.trim();

const tipo=
document.getElementById(
"tipoPedido"
).value;

const rua=
document.getElementById(
"rua"
).value;

const numero=
document.getElementById(
"numero"
).value.trim();

const complemento=
document.getElementById(
"complemento"
).value.trim();

const pagamento=
document.getElementById(
"pagamento"
).value;

const troco=
document.getElementById(
"troco"
).value;

const observacao=
document.getElementById(
"observacao"
).value.trim();

if(!nome){

alert("Digite seu nome.");

return;

}

if(!telefone){

alert("Digite seu telefone.");

return;

}

if(tipo==="ENTREGA"){

if(!rua){

alert("Selecione sua rua.");

return;

}

if(!numero){

alert(
"Digite o número do endereço."
);

return;

}

}

if(!pagamento){

alert(
"Selecione a forma de pagamento."
);

return;

}

let subtotal=0;

let mensagem="";

mensagem+=
"🍔 *NOVO PEDIDO - ND BURGS*%0A";

mensagem+=
"==============================%0A%0A";

mensagem+=
"👤 *CLIENTE:* "+
encodeURIComponent(nome)+
"%0A";

mensagem+=
"📱 *TELEFONE:* "+
encodeURIComponent(telefone)+
"%0A";

mensagem+=
"🏍️ *TIPO:* "+
encodeURIComponent(
tipo==="ENTREGA"?
"DELIVERY":
"RETIRADA"
)+
"%0A";

if(tipo==="ENTREGA"){

mensagem+=
"📍 *ENDEREÇO:* "+
encodeURIComponent(
rua+
", Nº "+
numero
)+
"%0A";

if(complemento){

mensagem+=
"🏠 *COMPLEMENTO:* "+
encodeURIComponent(
complemento
)+
"%0A";

}

}

mensagem+=
"%0A🛒 *ITENS DO PEDIDO*%0A";

mensagem+=
"------------------------------%0A";

carrinho.forEach(item=>{

const totalItem=
item.preco*
item.quantidade;

subtotal+=
totalItem;

mensagem+=
encodeURIComponent(
item.quantidade+
"x "+
item.nome+
" — "+
moeda(totalItem)
)+
"%0A";

if(
item.detalhes &&
item.detalhes.length
){

mensagem+=
encodeURIComponent(
"   ↳ "+
item.detalhes.join(", ")
)+
"%0A";

}

});

let taxa=0;

if(tipo==="ENTREGA"){

taxa=
taxas[rua]!==undefined
?
Number(taxas[rua])
:
0;

}

const total=
subtotal+taxa;

mensagem+=
"%0A";

mensagem+=
"💰 *SUBTOTAL:* "+
encodeURIComponent(
moeda(subtotal)
)+
"%0A";

mensagem+=
"🏍️ *TAXA:* "+
encodeURIComponent(
moeda(taxa)
)+
"%0A";

mensagem+=
"💵 *TOTAL:* "+
encodeURIComponent(
moeda(total)
)+
"%0A";

mensagem+=
"💳 *PAGAMENTO:* "+
encodeURIComponent(
pagamento
)+
"%0A";

if(
pagamento==="DINHEIRO" &&
troco
){

mensagem+=
"💵 *TROCO PARA:* "+
encodeURIComponent(
moeda(
parseFloat(troco)
)
)+
"%0A";

}

if(observacao){

mensagem+=
"%0A📝 *OBSERVAÇÃO:*%0A";

mensagem+=
encodeURIComponent(
observacao
)+
"%0A";

}

mensagem+=
"%0A==============================%0A";

mensagem+=
"ND BURGS 🍔";

const whatsapp=
"5511963973846";

window.open(
"https://wa.me/"+
whatsapp+
"?text="+
mensagem,
"_blank"
);

}

/* =========================
   INICIALIZAÇÃO
========================= */

carregarCarrinhoSalvo();

carregarRuas();

carregarRuasModal();

atualizarCarrinho();

alterarTipoPedido();

verificarHorario();


/* ===== MELHORIAS ND BURGS ===== */
(function(){
  const q=document.getElementById('buscaProdutos');
  const counter=document.getElementById('contadorBusca');
  const empty=document.getElementById('semResultados');
  function filtrar(){
    const termo=(q?.value||'').trim().toLocaleLowerCase('pt-BR');
    let total=0, visiveis=0;
    document.querySelectorAll('.produto').forEach(card=>{
      total++;
      const texto=card.innerText.toLocaleLowerCase('pt-BR');
      const ok=!termo||texto.includes(termo);
      card.classList.toggle('search-hidden',!ok);
      if(ok)visiveis++;
    });
    if(counter) counter.textContent=termo?`${visiveis} produto${visiveis===1?'':'s'}`:'';
    if(empty) empty.style.display=termo&&visiveis===0?'block':'none';
  }
  q?.addEventListener('input',filtrar);

  function configurarBuscaRua(inputId,selectId){
    const input=document.getElementById(inputId), select=document.getElementById(selectId);
    if(!input||!select)return;
    input.addEventListener('input',()=>{
      const termo=input.value.trim().toLocaleLowerCase('pt-BR');
      Array.from(select.options).forEach((op,i)=>{
        if(i===0){op.hidden=false;return;}
        op.hidden=!!termo&&!op.textContent.toLocaleLowerCase('pt-BR').includes(termo);
      });
      const primeira=Array.from(select.options).find((op,i)=>i>0&&!op.hidden);
      if(termo&&primeira&&(!select.value||select.options[select.selectedIndex]?.hidden)){
        select.value=primeira.value; select.dispatchEvent(new Event('change',{bubbles:true}));
      }
    });
  }
  configurarBuscaRua('ruaBusca','rua');
  configurarBuscaRua('ruaBuscaModal','ruaModal');

  window.fecharSugestoes=function(event){
    if(event&&event.target&&event.target.id!=='suggestionsModal')return;
    const m=document.getElementById('suggestionsModal'); if(m)m.classList.remove('show');
    document.body.style.overflow='';
  };
  window.mostrarSugestoes=function(){
    const grid=document.getElementById('suggestionsGrid'), modal=document.getElementById('suggestionsModal');
    if(!grid||!modal)return;
    const cards=[...document.querySelectorAll('.produto:not(.search-hidden)')].filter(c=>!c.closest('#checkout')).filter(c=>c.querySelector('.btn-add'));
    const usados=new Set(carrinho.map(x=>x.nome));
    const candidatos=cards.filter(c=>!usados.has(c.querySelector('h3')?.innerText.trim())).sort(()=>Math.random()-.5).slice(0,4);
    grid.innerHTML=candidatos.map((c,i)=>{
      const img=c.querySelector('img')?.src||''; const nome=c.querySelector('h3')?.innerText||'Produto'; const preco=c.querySelector('.preco')?.innerText||'';
      return `<div class="suggestion-card"><img src="${img}" alt="${nome}"><div style="flex:1"><strong>${nome}</strong><span>${preco}</span><button type="button" data-sug="${i}">+ ADICIONAR</button></div></div>`;
    }).join('') || '<div style="grid-column:1/-1;text-align:center;color:#999;padding:25px">Seu pedido já está cheio de boas escolhas 😍</div>';
    candidatos.forEach((c,i)=>grid.querySelector(`[data-sug="${i}"]`)?.addEventListener('click',()=>{
      c.querySelector('.btn-add')?.click();
      setTimeout(()=>mostrarSugestoes(),120);
    }));
    modal.classList.add('show'); document.body.style.overflow='hidden';
  };
  window.irParaCheckout=function(){ mostrarSugestoes(); };

  // Máscara de telefone BR nos dois formulários.
  ['telefone','telefoneModal'].forEach(id=>{
    const el=document.getElementById(id); if(!el)return;
    el.addEventListener('input',()=>{let v=el.value.replace(/\D/g,'').slice(0,11); if(v.length<=10)v=v.replace(/(\d{2})(\d{4})(\d{0,4})/,'($1) $2-$3'); else v=v.replace(/(\d{2})(\d{5})(\d{0,4})/,'($1) $2-$3'); el.value=v;});
  });

  // Salva dados básicos do cliente para acelerar o próximo pedido.
  const dadosIds=['nome','telefone','nomeModal','telefoneModal'];
  dadosIds.forEach(id=>{const el=document.getElementById(id); if(!el)return; const k='ndburgs_'+id; try{el.value|| (el.value=localStorage.getItem(k)||''); el.addEventListener('input',()=>localStorage.setItem(k,el.value));}catch(e){}});
})();

</script><script id="nd-premium-core">
(function(){
'use strict';
const $=(s,r=document)=>r.querySelector(s), $$=(s,r=document)=>[...r.querySelectorAll(s)];
const money=v=>Number(v||0).toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
const WA='5511963973846';
function cart(){try{return Array.isArray(window.carrinho)?window.carrinho:[]}catch(e){return []}}
function sub(){return cart().reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||1),0)}
function qty(){return cart().reduce((s,i)=>s+(Number(i.quantidade)||0),0)}
function go(id){document.getElementById(id)?.scrollIntoView({behavior:'smooth',block:'start'})}
window.irPara=go;
function buildSidebar(){
 if($('#ndSidebar'))return;
 const cats=$$('.categoria'); if(!cats.length)return;
 const nav=document.createElement('aside');nav.id='ndSidebar';nav.className='nd-sidebar';
 nav.innerHTML='<div class="nd-sidebar-head"><div class="nd-sidebar-brand">ND BURGS • CARDÁPIO</div><div class="nd-sidebar-title">Escolha seu sabor</div></div><div class="nd-sidebar-scroll"></div><div class="nd-sidebar-foot"><div class="nd-sidebar-sec">🔒 Pedido direto pelo site<br>📲 Confirmação pelo WhatsApp<br>🛵 Taxa mostrada antes de enviar</div></div>';
 const list=$('.nd-sidebar-scroll',nav);
 cats.forEach(cat=>{const title=cat.querySelector('.categoria-titulo,h2');if(!title)return;const b=document.createElement('button');b.type='button';b.dataset.target=cat.id;b.innerHTML='<span class="ico">'+(title.textContent.trim().split(' ')[0]||'•')+'</span><span>'+title.textContent.trim().replace(/^\S+\s*/,'')+'</span>';b.onclick=()=>go(cat.id);list.appendChild(b)});
 document.body.appendChild(nav);
 const buttons=$$('button[data-target]',nav);
 const io=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting){buttons.forEach(b=>b.classList.toggle('active',b.dataset.target===e.target.id));const active=buttons.find(b=>b.classList.contains('active'));active?.scrollIntoView({block:'nearest',inline:'center'})}})},{rootMargin:'-20% 0px -65% 0px',threshold:0});
 cats.forEach(c=>io.observe(c));
}
function buildPremiumIntro(){
 if($('#ndPremiumIntro'))return;const c=$('.container');if(!c)return;
 const d=document.createElement('section');d.id='ndPremiumIntro';d.innerHTML='<div><div class="nd-prem-kicker">ND BURGS • PEDIDO ONLINE</div><div class="nd-prem-title">SEU PEDIDO.<br><span>DO SEU JEITO.</span></div><div class="nd-prem-sub">Escolha seus favoritos, personalize quando necessário e revise tudo antes de enviar. Uma experiência rápida, clara e feita para pedir sem complicação.</div><div class="nd-prem-actions"><button class="primary" type="button" onclick="irPara(\'combos\')">🔥 VER DESTAQUES</button><button type="button" onclick="document.getElementById(\'ndReviews\')?.scrollIntoView({behavior:\'smooth\'})">⭐ AVALIAR A ND</button></div></div><div class="nd-prem-orb" aria-hidden="true"><div class="nd-prem-icon">🍔</div></div>';
 c.insertBefore(d,c.firstElementChild);
}
function buildSecurity(){
 if($('#ndSecurity'))return;const anchor=$('#ndPremiumIntro');if(!anchor)return;const d=document.createElement('section');d.id='ndSecurity';d.className='nd-security';d.innerHTML='<div class="nd-security-card"><div class="sico">🔒</div><strong>Pedido transparente</strong><span>Você revisa os itens e o total antes de enviar.</span></div><div class="nd-security-card"><div class="sico">📲</div><strong>WhatsApp da loja</strong><span>O pedido é enviado diretamente para a ND BURGS.</span></div><div class="nd-security-card"><div class="sico">🛵</div><strong>Taxa antecipada</strong><span>Na entrega, a taxa é calculada pela rua escolhida.</span></div><div class="nd-security-card"><div class="sico">💾</div><strong>Seu carrinho fica salvo</strong><span>O carrinho pode permanecer neste aparelho para evitar perda do pedido.</span></div>';anchor.after(d)
}
function buildCart(){
 if($('#ndCart'))return;const b=document.createElement('button');b.id='ndCart';b.className='nd-cart';b.type='button';b.setAttribute('aria-label','Abrir carrinho');b.innerHTML='🛒<span id="ndCartBadge" class="nd-cart-badge">0</span>';b.onclick=()=>{if(cart().length&&typeof window.abrirCarrinho==='function')window.abrirCarrinho();else if(typeof window.abrirCarrinho==='function')window.abrirCarrinho()};document.body.appendChild(b);const l=document.createElement('div');l.id='ndCartLabel';l.className='nd-cart-label';l.textContent='Carrinho vazio';document.body.appendChild(l);updateCartUI()
}
function updateCartUI(){const q=qty(),t=sub();const b=$('#ndCartBadge'),l=$('#ndCartLabel');if(b)b.textContent=q;if(l)l.textContent=q?`${q} ${q===1?'item':'itens'} • ${money(t)}`:'Carrinho vazio'}
function patchCart(){if(typeof window.atualizarCarrinho==='function'&&!window.atualizarCarrinho.__ndPremium){const old=window.atualizarCarrinho;window.atualizarCarrinho=function(){const r=old.apply(this,arguments);setTimeout(updateCartUI,0);return r};window.atualizarCarrinho.__ndPremium=true}}
function enhanceCards(){
 $$('.produto').forEach((card,i)=>{
  if(card.dataset.ndPremium==='1')return;card.dataset.ndPremium='1';
  const h=card.querySelector('h3');if(!h)return;const name=h.textContent.trim().toUpperCase();
  const favoritesKey='ndburgs_favoritos_premium';let favs;try{favs=new Set(JSON.parse(localStorage.getItem(favoritesKey)||'[]'))}catch(e){favs=new Set()}
  const fav=document.createElement('button');fav.type='button';fav.className='nd-fav';fav.textContent=favs.has(name)?'♥':'♡';fav.classList.toggle('ativo',favs.has(name));fav.title='Favoritar '+name;fav.onclick=e=>{e.stopPropagation();if(favs.has(name)){favs.delete(name);fav.textContent='♡';fav.classList.remove('ativo')}else{favs.add(name);fav.textContent='♥';fav.classList.add('ativo')}try{localStorage.setItem(favoritesKey,JSON.stringify([...favs]))}catch(_){} };
  card.appendChild(fav);
  if(['COMBO MAIS VENDIDO','COMBO SÓ LOVE','01 ND BURGS','BERENICE','X-BURGUER'].includes(name)||i===0){if(!card.querySelector('.nd-card-ribbon')){const r=document.createElement('div');r.className='nd-card-ribbon';r.textContent='DESTAQUE';card.appendChild(r)}}
 });
}
function buildReviews(){
 if($('#ndReviews'))return;const footer=$('footer');if(!footer)return;const sec=document.createElement('section');sec.id='ndReviews';sec.innerHTML='<div class="nd-prem-kicker">SUA OPINIÃO IMPORTA</div><h2>⭐ COMO FOI SUA EXPERIÊNCIA?</h2><p style="color:#777;font-size:11px;margin-top:6px">Avaliação salva neste aparelho. Se quiser, você também pode enviar para a loja.</p><div class="nd-review-stars" role="radiogroup" aria-label="Nota de 1 a 5"><button type="button" data-star="1">★</button><button type="button" data-star="2">★</button><button type="button" data-star="3">★</button><button type="button" data-star="4">★</button><button type="button" data-star="5">★</button></div><textarea id="ndReviewText" placeholder="Conte como foi seu pedido..."></textarea><button id="ndReviewSend" type="button">ENVIAR AVALIAÇÃO ⭐</button><div id="ndReviewList" class="nd-review-list"></div>';
 footer.parentNode.insertBefore(sec,footer);let stars=0;const key='ndburgs_avaliacoes_premium';const load=()=>{try{const a=JSON.parse(localStorage.getItem(key)||'[]');return Array.isArray(a)?a:[]}catch(e){return[]}};const render=()=>{$('#ndReviewList').innerHTML=load().slice(-5).reverse().map(r=>`<div class="nd-review"><strong>${'★'.repeat(r.stars)}</strong><p>${String(r.comment||'').replace(/[&<>]/g,m=>({'&':'&amp;','<':'&lt;','>':'&gt;'}[m]))}</p><small style="color:#666">${r.date||''}</small></div>`).join('')};$$('[data-star]',sec).forEach(b=>b.onclick=()=>{stars=Number(b.dataset.star);$$('[data-star]',sec).forEach(x=>x.classList.toggle('on',Number(x.dataset.star)<=stars))});$('#ndReviewSend').onclick=()=>{const comment=$('#ndReviewText').value.trim();if(!stars)return alert('Escolha uma nota de 1 a 5 estrelas.');if(!comment)return alert('Escreva um comentário.');const a=load();a.push({stars,comment,date:new Date().toLocaleDateString('pt-BR')});try{localStorage.setItem(key,JSON.stringify(a))}catch(_){}render();window.open('https://wa.me/'+WA+'?text='+encodeURIComponent('⭐ *AVALIAÇÃO — ND BURGS*\n\nNota: '+stars+'/5\nComentário: '+comment),'_blank');$('#ndReviewText').value='';stars=0;$$('[data-star]',sec).forEach(x=>x.classList.remove('on'))};render()
}
function buildCheckout(){
 const panel=$('#modalFinalizar .painel-finalizar');if(!panel||panel.dataset.ndPremiumCheckout==='1')return;panel.dataset.ndPremiumCheckout='1';
 panel.innerHTML='<div class="nd-check-head"><div class="nd-prem-kicker">FINALIZAÇÃO SEGURA E TRANSPARENTE</div><div style="display:flex;justify-content:space-between;align-items:center;gap:10px"><h2>QUASE LÁ 🍔</h2><button type="button" class="btn-fechar-finalizar" onclick="fecharModalFinalizar()">×</button></div></div><div class="nd-stepbar"><div class="nd-step active" data-step="1">1 • DADOS</div><div class="nd-step" data-step="2">2 • ENTREGA</div><div class="nd-step" data-step="3">3 • PAGAMENTO</div><div class="nd-step" data-step="4">4 • REVISAR</div></div><div class="nd-step-content active" data-content="1"><label>Seu nome</label><input id="nomeModal" type="text" autocomplete="name" placeholder="Como podemos te chamar?"><label>WhatsApp</label><input id="telefoneModal" type="tel" inputmode="tel" autocomplete="tel" placeholder="(11) 99999-9999"><div class="nd-delivery">🔒 <b>Privacidade:</b> os dados são usados para montar e enviar este pedido. Eles podem ser salvos neste aparelho para facilitar um próximo pedido.</div><button class="nd-next" type="button" onclick="ndNext(1)">CONTINUAR →</button></div><div class="nd-step-content" data-content="2"><label>Como você quer receber?</label><div class="nd-option-grid"><button class="nd-option active" data-type="ENTREGA" type="button">🛵<br>DELIVERY</button><button class="nd-option" data-type="RETIRADA" type="button">🏪<br>RETIRADA</button></div><select id="tipoPedidoModal" style="display:none"><option value="ENTREGA">ENTREGA</option><option value="RETIRADA">RETIRADA</option></select><div id="enderecoAreaModal"><label>Pesquise sua rua</label><input id="ruaBuscaModal" type="search" autocomplete="off" placeholder="🔎 Digite parte do nome da rua"><select id="ruaModal"><option value="">Selecione sua rua</option></select><label>Número</label><input id="numeroModal" type="text" placeholder="Número"><label>Complemento <small>(opcional)</small></label><input id="complementoModal" type="text" placeholder="Casa, apto, bloco..."><div id="avisoTaxaModal" class="aviso-taxa" style="display:none"></div></div><div id="ndRetiradaInfo" class="nd-delivery" style="display:none">🏪 <b>Retirada no local</b><br>Sem taxa de entrega.</div><div class="nd-delivery">🕐 <b>Estimativa:</b> normalmente 30–50 minutos após a confirmação. O tempo pode variar conforme o movimento.</div><button class="nd-next" type="button" onclick="ndNext(2)">CONTINUAR →</button><button class="nd-back" type="button" onclick="ndBack(2)">← VOLTAR</button></div><div class="nd-step-content" data-content="3"><label>Forma de pagamento</label><div class="nd-option-grid"><button class="nd-option" data-pay="PIX" type="button">💠<br>PIX</button><button class="nd-option" data-pay="DINHEIRO" type="button">💵<br>DINHEIRO</button><button class="nd-option" data-pay="CARTÃO" type="button">💳<br>CARTÃO</button></div><select id="pagamentoModal" style="display:none"><option value="">Selecione</option><option value="PIX">PIX</option><option value="DINHEIRO">DINHEIRO</option><option value="CARTÃO">CARTÃO</option></select><div id="trocoAreaModal" style="display:none"><label>Troco para quanto?</label><input id="trocoModal" type="number" inputmode="decimal" step="0.01" placeholder="Ex.: 50"></div><label>Observação <small>(opcional)</small></label><textarea id="observacaoModal" placeholder="Ex.: sem cebola, tocar campainha..."></textarea><button class="nd-next" type="button" onclick="ndNext(3)">REVISAR PEDIDO →</button><button class="nd-back" type="button" onclick="ndBack(3)">← VOLTAR</button></div><div class="nd-step-content" data-content="4"><div class="nd-summary"><div class="nd-summary-title">Itens do pedido</div><div id="ndItems"></div></div><div class="nd-summary"><div class="nd-summary-row"><span>Subtotal</span><b id="ndSub">R$ 0,00</b></div><div class="nd-summary-row"><span>Taxa de entrega</span><b id="ndFee">R$ 0,00</b></div><div class="nd-total"><span>TOTAL</span><strong id="ndTotal">R$ 0,00</strong></div></div><div class="nd-delivery">✅ Confira nome, endereço, pagamento e itens. O site só abre o WhatsApp depois da sua revisão.</div><button class="nd-next" type="button" onclick="finalizarPedidoModal()">📲 ENVIAR PEDIDO PELO WHATSAPP</button><button class="nd-back" type="button" onclick="ndBack(4)">← VOLTAR</button></div>';
 // wire controls
 $$('[data-type]',panel).forEach(b=>b.onclick=()=>{const t=b.dataset.type;$('#tipoPedidoModal').value=t;$$('[data-type]',panel).forEach(x=>x.classList.toggle('active',x===b));$('#enderecoAreaModal').style.display=t==='ENTREGA'?'block':'none';$('#ndRetiradaInfo').style.display=t==='RETIRADA'?'block':'none';if(typeof window.calcularTaxaModal==='function')window.calcularTaxaModal();});
 $$('[data-pay]',panel).forEach(b=>b.onclick=()=>{const p=b.dataset.pay;$('#pagamentoModal').value=p;$$('[data-pay]',panel).forEach(x=>x.classList.toggle('active',x===b));$('#trocoAreaModal').style.display=p==='DINHEIRO'?'block':'none';});
 // populate streets without depending on the old modal markup
 const rs=$('#ruaModal');if(rs&&window.taxas){Object.keys(window.taxas).filter(x=>!['BALCAO','RETIRADA','IFOOD','99FOOD'].includes(x)).sort((a,b)=>a.localeCompare(b,'pt-BR')).forEach(r=>{const o=document.createElement('option');o.value=r;o.textContent=r+' — '+money(window.taxas[r]);rs.appendChild(o)});rs.onchange=()=>window.calcularTaxaModal?.()}
 const rb=$('#ruaBuscaModal');rb?.addEventListener('input',()=>{const q=rb.value.toLocaleLowerCase('pt-BR');[...rs.options].forEach((o,i)=>{if(i===0)return;o.hidden=!!q&&!o.textContent.toLocaleLowerCase('pt-BR').includes(q)})});
 loadCheckoutData();
}
function loadCheckoutData(){['nomeModal','telefoneModal'].forEach(id=>{const e=$('#'+id);if(!e)return;const v=localStorage.getItem('ndburgs_'+id)||'';if(v)e.value=v})}
function step(n){$$('.nd-step-content','#modalFinalizar').forEach(x=>x.classList.toggle('active',Number(x.dataset.content)===n));$$('.nd-step','#modalFinalizar').forEach(x=>{const v=Number(x.dataset.step);x.classList.toggle('active',v===n);x.classList.toggle('done',v<n)});const p=$('#modalFinalizar .painel-finalizar');if(p)p.scrollTop=0;if(n===4)summary()}
window.ndBack=n=>step(n-1);
window.ndNext=n=>{if(n===1){const name=$('#nomeModal').value.trim(),tel=$('#telefoneModal').value.replace(/\D/g,'');if(!name)return alert('Digite seu nome.');if(tel.length<10||tel.length>11)return alert('Digite um WhatsApp válido com DDD.');localStorage.setItem('ndburgs_nomeModal',name);localStorage.setItem('ndburgs_telefoneModal',$('#telefoneModal').value.trim())}if(n===2){const type=$('#tipoPedidoModal').value;if(type==='ENTREGA'&&(!$('#ruaModal').value||!$('#numeroModal').value.trim()))return alert('Complete seu endereço.')}if(n===3){const pay=$('#pagamentoModal').value;if(!pay)return alert('Escolha uma forma de pagamento.');if(pay==='DINHEIRO'){const change=Number($('#trocoModal').value);const totalNow=sub()+(window.taxas?.[$('#ruaModal').value]||0);if(!change||change<=totalNow)return alert('Informe um valor de troco maior que o total do pedido.')}}step(n+1)};
function summary(){const type=$('#tipoPedidoModal').value,street=$('#ruaModal').value,fee=type==='ENTREGA'?Number(window.taxas?.[street]||0):0,s=sub(),t=s+fee;$('#ndSub').textContent=money(s);$('#ndFee').textContent=money(fee);$('#ndTotal').textContent=money(t);$('#ndItems').innerHTML=cart().map(i=>`<div class="nd-summary-row"><span>${i.quantidade}x ${i.nome}${i.detalhes?.length?`<small style="display:block;color:#777;margin-top:3px">↳ ${i.detalhes.join(', ')}</small>`:''}</span><b>${money(i.preco*i.quantidade)}</b></div>`).join('')}
function patchFinalize(){
 const oldOpen=window.irParaFinalizarPedido;if(typeof oldOpen==='function'&&!oldOpen.__ndPremium){window.irParaFinalizarPedido=function(){if(!cart().length)return alert('Seu carrinho está vazio.');const m=$('#modalFinalizar');if(!m)return; m.classList.add('ativo');document.body.style.overflow='hidden';buildCheckout();step(1)};window.irParaFinalizarPedido.__ndPremium=true}
 const oldFinish=window.finalizarPedidoModal;if(typeof oldFinish==='function'&&!oldFinish.__ndPremium){window.finalizarPedidoModal=function(){if(!cart().length)return alert('Seu carrinho está vazio.');return oldFinish.apply(this,arguments)};window.finalizarPedidoModal.__ndPremium=true}
}
function backTop(){if($('#ndBackTop'))return;const b=document.createElement('button');b.id='ndBackTop';b.type='button';b.textContent='↑';b.setAttribute('aria-label','Voltar ao topo');b.onclick=()=>scrollTo({top:0,behavior:'smooth'});document.body.appendChild(b);addEventListener('scroll',()=>b.classList.toggle('show',scrollY>700),{passive:true})}
function init(){buildSidebar();buildPremiumIntro();buildSecurity();buildCart();enhanceCards();buildReviews();buildCheckout();patchCart();patchFinalize();updateCartUI()}
addEventListener('DOMContentLoaded',()=>{init();setTimeout(init,500);setTimeout(patchCart,1000)});
})();
</script>
</body>
</html>
