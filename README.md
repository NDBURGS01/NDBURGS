<!doctype html><html lang="pt-BR"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width,initial-scale=1.0"><meta name="theme-color" content="#070414"><meta name="description" content="ND BURGS — cardápio online, pedido rápido, taxa transparente e finalização pelo WhatsApp."><meta name="referrer" content="strict-origin-when-cross-origin"><title>ND BURGS | Cardápio Online</title><script>
(function () {
  const ND_SITE_VERSION = "20260904-R10";
  const KEY = "ndburgs_site_version";
  try {
    const old = localStorage.getItem(KEY);
    if (old && old !== ND_SITE_VERSION) {
      localStorage.setItem(KEY, ND_SITE_VERSION);
      // Recarrega uma única vez quando a versão do site mudar.
      const u = new URL(window.location.href);
      u.searchParams.set("_ndv", ND_SITE_VERSION);
      window.location.replace(u.toString());
      return;
    }
    localStorage.setItem(KEY, ND_SITE_VERSION);
  } catch (e) {}
})();
</script><style>
:root{--bg:#05030d;--bg2:#090617;--panel:rgba(18,13,36,.78);--panel2:rgba(24,17,48,.88);--line:rgba(145,108,255,.22);--blue:#3aa7ff;--blue2:#6bd1ff;--purple:#7b3cff;--purple2:#b56cff;--pink:#d85cff;--green:#25d366;--text:#f7f4ff;--muted:#a7a1bd;--shadow:0 22px 70px rgba(0,0,0,.55)}
*{box-sizing:border-box}html{scroll-behavior:smooth;background:var(--bg)}body{margin:0;background:radial-gradient(900px 500px at 55% -10%,rgba(71,126,255,.20),transparent 60%),radial-gradient(700px 500px at 100% 35%,rgba(142,56,255,.16),transparent 62%),linear-gradient(180deg,#04020a 0%,#080512 45%,#04020a 100%);color:var(--text);font-family:Inter,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;overflow-x:hidden;padding-bottom:110px}
body:before{content:"";position:fixed;inset:0;pointer-events:none;z-index:-1;background-image:linear-gradient(rgba(255,255,255,.018) 1px,transparent 1px),linear-gradient(90deg,rgba(255,255,255,.014) 1px,transparent 1px);background-size:42px 42px;mask-image:linear-gradient(to bottom,#000,transparent 75%)}
header{position:sticky!important;top:0!important;z-index:5000;padding:15px 20px!important;background:rgba(4,2,12,.78)!important;border:0!important;border-bottom:1px solid rgba(104,155,255,.25)!important;backdrop-filter:blur(24px);box-shadow:0 10px 50px rgba(0,0,0,.45)!important;text-align:center}
.logo{width:min(190px,62vw)!important;filter:drop-shadow(0 0 25px rgba(77,153,255,.42)) drop-shadow(0 0 42px rgba(135,67,255,.25))!important}
.horarios{max-width:1240px!important;margin:14px auto!important;padding:0 18px!important}.horarios-box{position:relative;overflow:hidden;border:1px solid rgba(84,159,255,.28)!important;background:linear-gradient(135deg,rgba(25,18,52,.88),rgba(8,6,20,.88))!important;border-radius:18px!important;box-shadow:0 16px 45px rgba(0,0,0,.35),inset 0 1px 0 rgba(255,255,255,.06)!important}.horarios-box:before{content:"";position:absolute;inset:0;background:linear-gradient(100deg,transparent,rgba(94,179,255,.07),transparent);pointer-events:none}.horarios-titulo{color:#77cfff!important}.status-aberto{color:#70f6ae!important;background:rgba(37,211,102,.08)!important;border:1px solid rgba(37,211,102,.25)!important;border-radius:999px!important}
.container{max-width:1180px!important;margin:auto;padding:0 24px 50px!important}.container>h1{font-size:0!important;height:0!important;margin:0!important}
.nd-hero{position:relative;margin:22px 0 20px;padding:42px 42px 36px;min-height:430px;display:grid;grid-template-columns:1.05fr .95fr;align-items:center;overflow:hidden;border:1px solid rgba(118,91,255,.30);border-radius:30px;background:linear-gradient(135deg,rgba(22,15,48,.92),rgba(7,5,18,.96));box-shadow:var(--shadow),inset 0 1px 0 rgba(255,255,255,.08);transform-style:preserve-3d}.nd-hero:before{content:"";position:absolute;width:520px;height:520px;right:-160px;top:-190px;border-radius:50%;background:radial-gradient(circle,rgba(65,163,255,.30),rgba(117,54,255,.12) 42%,transparent 68%);filter:blur(3px)}.nd-hero:after{content:"";position:absolute;inset:auto -10% -70% -10%;height:240px;background:radial-gradient(ellipse,rgba(128,67,255,.18),transparent 68%);pointer-events:none}.nd-hero-copy{position:relative;z-index:2;transform:translateZ(28px)}.nd-kicker{display:inline-flex;padding:8px 12px;border:1px solid rgba(101,180,255,.32);border-radius:999px;background:rgba(55,128,255,.08);color:#7ed3ff;font-size:11px;font-weight:900;letter-spacing:1.5px}.nd-hero h1{font-size:clamp(42px,6vw,76px);line-height:.92;letter-spacing:-4px;margin:18px 0 14px}.nd-hero h1 span{display:block;background:linear-gradient(90deg,#fff,#70caff,#a875ff);-webkit-background-clip:text;background-clip:text;color:transparent}.nd-hero p{max-width:620px;color:#b8b2cc;font-size:15px;line-height:1.65}.nd-hero-actions{display:flex;gap:10px;flex-wrap:wrap;margin-top:22px}.nd-hero-btn{border:0;border-radius:14px;padding:14px 18px;font-weight:950;cursor:pointer}.nd-hero-btn.primary{background:linear-gradient(135deg,#3b9fff,#7b4cff);color:#fff;box-shadow:0 12px 30px rgba(76,105,255,.25)}.nd-hero-btn.secondary{background:rgba(255,255,255,.055);color:#fff;border:1px solid rgba(255,255,255,.10)}.nd-trustline{display:flex;gap:15px;flex-wrap:wrap;margin-top:22px;color:#aaa3bd;font-size:10px;font-weight:800}.nd-hero-art{position:relative;min-height:330px;display:grid;place-items:center;transform-style:preserve-3d}.nd-orbit{position:absolute;width:310px;height:310px;border-radius:50%;border:1px solid rgba(88,175,255,.28);box-shadow:0 0 70px rgba(77,113,255,.14),inset 0 0 50px rgba(130,66,255,.08);transform:rotateX(62deg) rotateZ(-15deg);animation:ndOrbit 12s linear infinite}.nd-orbit:before,.nd-orbit:after{content:"";position:absolute;width:10px;height:10px;border-radius:50%;background:#69c9ff;box-shadow:0 0 22px #69c9ff;top:14%;left:15%}.nd-orbit:after{background:#b36cff;box-shadow:0 0 22px #b36cff;right:12%;left:auto;bottom:12%;top:auto}.nd-hero-art img{position:relative;z-index:2;width:min(330px,80%);height:330px;object-fit:contain;filter:drop-shadow(0 30px 25px rgba(0,0,0,.7)) drop-shadow(0 0 35px rgba(70,130,255,.20));transform:translateZ(55px) rotate(-2deg);animation:ndFloat 4.5s ease-in-out infinite}.nd-art-chip{position:absolute;right:2%;bottom:4%;z-index:3;padding:11px 14px;border:1px solid rgba(117,88,255,.45);border-radius:14px;background:rgba(13,9,29,.90);backdrop-filter:blur(14px);box-shadow:0 15px 35px rgba(0,0,0,.5);font-size:10px;color:#aaa}.nd-art-chip b{display:block;color:#7ed3ff;font-size:15px;margin-top:2px}
@keyframes ndFloat{0%,100%{transform:translateZ(55px) translateY(0) rotate(-2deg)}50%{transform:translateZ(75px) translateY(-10px) rotate(2deg)}}@keyframes ndOrbit{to{transform:rotateX(62deg) rotateZ(345deg)}}
.nd-security{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin:18px 0 24px}.nd-security-card{padding:14px;border:1px solid rgba(125,91,255,.20);border-radius:16px;background:linear-gradient(145deg,rgba(23,16,48,.82),rgba(10,7,24,.88));box-shadow:0 12px 30px rgba(0,0,0,.25),inset 0 1px 0 rgba(255,255,255,.04);font-size:11px;color:#a9a3b8}.nd-security-card strong{display:block;color:#fff;font-size:12px;margin:5px 0 3px}.nd-security-card .ico{font-size:21px}
.modern-search{position:sticky!important;top:74px!important;z-index:2200!important;margin:12px 0!important;padding:9px!important;border:1px solid rgba(117,88,255,.25)!important;border-radius:18px!important;background:rgba(8,5,20,.86)!important;box-shadow:0 15px 40px rgba(0,0,0,.45)!important;backdrop-filter:blur(20px)}.modern-search input{border:1px solid rgba(255,255,255,.08)!important;background:rgba(255,255,255,.035)!important;border-radius:13px!important;padding:14px!important}.modern-search:focus-within{border-color:rgba(82,165,255,.55)!important;box-shadow:0 0 0 3px rgba(76,141,255,.08),0 15px 40px rgba(0,0,0,.5)!important}
/* SIDEBAR DESKTOP */
@media(min-width:901px){body{padding-left:250px!important}.nd-sidebar{position:fixed;left:14px;top:92px;bottom:14px;width:214px;z-index:4500;display:flex;flex-direction:column;padding:14px 10px;overflow-y:auto;overflow-x:hidden;border:1px solid rgba(114,86,255,.30);border-radius:24px;background:linear-gradient(180deg,rgba(18,12,40,.94),rgba(7,5,18,.97));box-shadow:20px 0 65px rgba(0,0,0,.38),inset -1px 0 0 rgba(100,150,255,.08);backdrop-filter:blur(22px);scrollbar-width:thin;scrollbar-color:#5e45a8 transparent}.nd-sidebar:before{content:"";height:110px;position:absolute;top:-40px;left:15px;right:15px;background:radial-gradient(circle,rgba(72,153,255,.22),transparent 68%);pointer-events:none}.nd-side-brand{position:relative;padding:10px 10px 14px;border-bottom:1px solid rgba(255,255,255,.07);margin-bottom:10px}.nd-side-brand b{display:block;font-size:16px;background:linear-gradient(90deg,#fff,#72caff,#a66cff);-webkit-background-clip:text;background-clip:text;color:transparent}.nd-side-brand span{display:block;color:#807a96;font-size:9px;margin-top:4px;letter-spacing:1.2px}.nd-side-btn{position:relative;width:100%;flex:none;border:1px solid transparent;background:rgba(255,255,255,.025);color:#aaa3bb;border-radius:14px;padding:12px 11px;margin:3px 0;text-align:left;font-weight:850;font-size:11px;cursor:pointer;transition:.2s;box-shadow:inset 0 1px 0 rgba(255,255,255,.025)}.nd-side-btn:hover,.nd-side-btn.active{color:#fff;border-color:rgba(91,164,255,.35);background:linear-gradient(135deg,rgba(55,130,255,.18),rgba(126,63,255,.16));transform:translateX(3px);box-shadow:0 8px 24px rgba(54,90,255,.12)}.nd-side-btn.active:before{content:"";position:absolute;left:-10px;top:9px;bottom:9px;width:3px;border-radius:99px;background:linear-gradient(#54c7ff,#974eff);box-shadow:0 0 15px rgba(88,160,255,.7)}}
.categoria-menu{display:none!important}.categoria{margin:34px 0!important;scroll-margin-top:105px}.categoria-titulo{display:flex!important;align-items:center;gap:10px;border:0!important;border-bottom:1px solid rgba(255,255,255,.08)!important;padding:0 0 11px!important;color:#fff!important;font-size:24px!important;font-weight:950!important;letter-spacing:-.6px}.categoria-titulo:after{content:"";width:75px!important;height:3px!important;margin-left:auto;background:linear-gradient(90deg,#43b8ff,#8a4cff,transparent)!important;box-shadow:0 0 18px rgba(90,126,255,.45)!important}
.produtos{grid-template-columns:repeat(auto-fill,minmax(215px,1fr))!important;gap:16px!important}.produto{position:relative;padding:10px!important;border:1px solid rgba(131,95,255,.18)!important;border-radius:21px!important;background:linear-gradient(150deg,rgba(25,18,50,.92),rgba(9,7,20,.96))!important;box-shadow:0 16px 38px rgba(0,0,0,.34),inset 0 1px 0 rgba(255,255,255,.045)!important;overflow:hidden!important;transform-style:preserve-3d;transition:transform .25s ease,border-color .25s,box-shadow .25s!important}.produto:before{content:"";position:absolute;inset:-50% -30%;background:linear-gradient(115deg,transparent 42%,rgba(103,185,255,.08) 50%,transparent 58%);transform:translateX(-30%) rotate(8deg);pointer-events:none;transition:.5s}.produto:hover{transform:translateY(-6px) rotateX(1deg) rotateY(-1deg)!important;border-color:rgba(79,165,255,.45)!important;box-shadow:0 24px 55px rgba(0,0,0,.48),0 0 30px rgba(90,74,255,.10)!important}.produto:hover:before{transform:translateX(30%) rotate(8deg)}.produto-imagem,.produto img{width:100%!important;aspect-ratio:1/1!important;height:auto!important;object-fit:cover!important;border-radius:15px!important;background:radial-gradient(circle at 50% 35%,#241b48,#090718)!important;display:block!important;box-shadow:inset 0 0 30px rgba(75,77,255,.10)}.produto h3{font-size:16px!important;line-height:1.15!important;margin:12px 3px 5px!important;color:#fff!important;font-weight:950!important}.produto p{font-size:11px!important;line-height:1.45!important;color:#9e98b1!important;min-height:34px!important;margin:0 3px!important}.preco{font-size:21px!important;color:#73caff!important;font-weight:950!important;margin:10px 3px!important;text-shadow:0 0 18px rgba(66,170,255,.20)}.btn-add{min-height:46px!important;border:0!important;border-radius:13px!important;background:linear-gradient(135deg,#319cff 0%,#694cff 52%,#a74cff 100%)!important;color:#fff!important;font-weight:950!important;box-shadow:0 10px 24px rgba(65,95,255,.22)!important;cursor:pointer}.btn-add:hover{filter:brightness(1.10);transform:translateY(-1px)}
.nd-fav{position:absolute;right:16px;top:16px;z-index:10;width:38px;height:38px;border:1px solid rgba(255,255,255,.10);border-radius:50%;background:rgba(7,5,17,.78);color:#b8b1ca;font-size:20px;display:grid;place-items:center;cursor:pointer;backdrop-filter:blur(8px)}.nd-fav.active{color:#ff72d8;border-color:rgba(255,114,216,.5);box-shadow:0 0 20px rgba(255,80,200,.15)}.nd-badge{position:absolute;left:16px;top:16px;z-index:9;padding:6px 9px;border-radius:999px;background:linear-gradient(135deg,#48b8ff,#8c4dff);color:#fff;font-size:9px;font-weight:950;box-shadow:0 7px 18px rgba(0,0,0,.4)}
/* cart */
.carrinho-flutuante{left:50%!important;bottom:15px!important;width:min(700px,calc(100% - 30px))!important;transform:translateX(-50%) translateY(150px)!important;border:1px solid rgba(100,177,255,.38)!important;border-radius:20px!important;background:linear-gradient(135deg,rgba(23,14,52,.96),rgba(8,7,20,.97))!important;box-shadow:0 22px 70px rgba(0,0,0,.68)!important;backdrop-filter:blur(22px)!important}.carrinho-flutuante.ativo{transform:translateX(-50%) translateY(0)!important}.btn-ver-carrinho{background:linear-gradient(135deg,#42a9ff,#754cff)!important;color:#fff!important;border-radius:13px!important}.carrinho-flutuante-total{color:#75caff!important}.painel-carrinho,.painel-finalizar,.modal-box{background:linear-gradient(160deg,#17102e,#080612)!important;border:1px solid rgba(111,87,255,.42)!important;box-shadow:0 -25px 90px rgba(0,0,0,.72)!important}.modal-carrinho,.modal-finalizar,.modal-personalizacao{backdrop-filter:blur(14px)!important}.fechar-carrinho,.btn-fechar-finalizar,.modal-fechar{background:rgba(255,255,255,.055)!important;border:1px solid rgba(255,255,255,.10)!important;color:#fff!important}.fechar-carrinho:hover,.btn-fechar-finalizar:hover,.modal-fechar:hover{background:linear-gradient(135deg,#347fff,#8b4dff)!important}.btn-finalizar-pedido,.btn-finalizar-modal,.nd-v4-next{background:linear-gradient(135deg,#35a9ff,#754cff,#a84cff)!important;color:#fff!important;border:0!important}.btn-continuar-comprando{background:rgba(255,255,255,.06)!important;color:#fff!important;border:1px solid rgba(255,255,255,.10)!important}.nd-v4-step.active{border-color:#5aaaff!important;color:#75caff!important;background:rgba(72,159,255,.10)!important}.nd-v4-pay.active{border-color:#7955ff!important;color:#a875ff!important;background:rgba(123,60,255,.12)!important}.nd-v4-final-total{color:#74caff!important}input,select,textarea{background:rgba(6,5,15,.92)!important;border:1px solid rgba(255,255,255,.10)!important;color:#fff!important;border-radius:13px!important}input:focus,select:focus,textarea:focus{border-color:#5aafff!important;box-shadow:0 0 0 3px rgba(72,157,255,.10)!important}
/* esconder hero antigo e checkout legado; o novo layout usa componentes únicos */.nd-v4-hero{display:none!important}
/* checkout antigo fica oculto: checkout seguro acontece no modal */#checkout,.formulario{display:none!important}
/* footer */
footer{margin-top:50px!important}.instagram-destaque{border:1px solid rgba(122,83,255,.28)!important;background:linear-gradient(135deg,rgba(24,15,48,.86),rgba(8,6,20,.92))!important;box-shadow:var(--shadow)!important}.instagram-botao{background:linear-gradient(135deg,#3b9fff,#784cff,#a84cff)!important;color:#fff!important}
.nd-backtop{position:fixed;right:18px;bottom:96px;width:44px;height:44px;border:1px solid rgba(109,88,255,.35);border-radius:50%;background:rgba(15,10,32,.90);color:#fff;z-index:9000;display:none;cursor:pointer;box-shadow:0 12px 30px rgba(0,0,0,.45)}.nd-backtop.show{display:grid;place-items:center}
@media(max-width:900px){.container{padding:0 10px 35px!important}.nd-hero{grid-template-columns:1fr;padding:28px 22px 22px;min-height:auto;border-radius:24px}.nd-hero h1{font-size:48px;letter-spacing:-3px}.nd-hero p{font-size:13px}.nd-hero-art{min-height:245px}.nd-orbit{width:210px;height:210px}.nd-hero-art img{width:240px;height:240px}.nd-security{grid-template-columns:1fr 1fr}.nd-sidebar{position:sticky;top:0;z-index:3000;display:flex;flex-direction:row;gap:7px;overflow-x:auto;overflow-y:hidden;padding:8px;border-bottom:1px solid rgba(104,82,255,.25);background:rgba(5,3,13,.94);backdrop-filter:blur(18px);scrollbar-width:none}.nd-sidebar::-webkit-scrollbar{display:none}.nd-side-brand{display:none}.nd-side-btn{width:auto;white-space:nowrap;flex:0 0 auto;margin:0;padding:11px 13px;font-size:10px;border:1px solid rgba(255,255,255,.07)}.nd-side-btn.active{transform:none}.categoria{scroll-margin-top:130px}.modern-search{top:56px!important}.produtos{grid-template-columns:repeat(2,minmax(0,1fr))!important;gap:9px!important}.produto{padding:8px!important;border-radius:16px!important}.produto:hover{transform:none!important}.produto h3{font-size:13px!important}.produto p{font-size:9.5px!important;min-height:39px!important}.preco{font-size:18px!important}.btn-add{min-height:46px!important;font-size:11px!important}.nd-fav{width:34px;height:34px;right:11px;top:11px}.nd-badge{left:11px;top:11px;font-size:8px}.carrinho-flutuante{width:calc(100% - 16px)!important;bottom:8px!important}.nd-backtop{bottom:88px;right:12px}.horarios{padding:0 9px!important}.horarios-box{display:grid!important;grid-template-columns:1fr auto!important}.horarios-linha{text-align:left!important;grid-column:1/-1}}
@media(max-width:430px){.nd-security{grid-template-columns:1fr}.nd-hero h1{font-size:42px}.nd-hero-art{min-height:215px}.nd-hero-art img{width:205px;height:205px}.produtos{gap:7px!important}.produto{padding:7px!important}.produto h3{font-size:12px!important}.produto p{font-size:9px!important}.preco{font-size:17px!important}.btn-add{font-size:10px!important}.nd-side-btn{padding:10px 11px}}
@media(prefers-reduced-motion:reduce){*,*::before,*::after{animation:none!important;transition:none!important;scroll-behavior:auto!important}.produto:hover{transform:none!important}}
</style></head><body>

<!-- RODADA 1: bloqueio por horário removido; atendimento 24h todos os dias -->

<header>

<img class="logo" src="https://i.ibb.co/5gsVbBcb/corretooo.jpg" alt="ND BURGS">


</header>

<div id="ndSidebar" class="nd-sidebar" aria-label="Categorias do cardápio"></div>
<section class="nd-hero"><div class="nd-hero-copy"><span class="nd-kicker">✨ ND BURGS • PEDIDOS ONLINE</span><h1>SEU PEDIDO.<span>DO SEU JEITO.</span></h1><p>Escolha seus favoritos, personalize quando quiser e finalize com segurança pelo WhatsApp. A taxa de entrega aparece antes da confirmação.</p><div class="nd-hero-actions"><button class="nd-hero-btn primary" type="button" onclick="irPara('combos')">🔥 VER CARDÁPIO</button><button class="nd-hero-btn secondary" type="button" onclick="abrirCarrinho()">🛒 MEU PEDIDO</button></div><div class="nd-trustline"><span>🔒 CONEXÃO HTTPS</span><span>💰 TAXA TRANSPARENTE</span><span>📲 WHATSAPP</span></div></div><div class="nd-hero-art"><div class="nd-orbit"></div><img src="https://i.ibb.co/nMmfSSt1/Chat-GPT-Image-28-de-jul-de-2026-22-33-11.png" alt="Hambúrguer ND BURGS"><div class="nd-art-chip">PEDIDO ONLINE<b>RÁPIDO & SEGURO</b></div></div></section><div id="ndSecurity" class="nd-security"></div>
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



<div id="ndToast" class="nd-toast" role="status" aria-live="polite"></div>
<button id="ndBackTop" class="nd-backtop" aria-label="Voltar ao topo">↑</button>
<div class="nd-topbar" id="ndTopbar">
  <div class="nd-topbar-inner" id="ndCategoryNav"></div>
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
(function(){'use strict';
const cats=[...document.querySelectorAll('.categoria')];
function buildSidebar(){const s=document.getElementById('ndSidebar');if(!s)return;s.innerHTML='<div class="nd-side-brand"><b>ND BURGS</b><span>CARDÁPIO PREMIUM</span></div>'+cats.map(c=>{const t=c.querySelector('.categoria-titulo');return t?'<button type="button" class="nd-side-btn" data-target="'+c.id+'">'+t.textContent.replace(/\s+/g,' ').trim()+'</button>':''}).join('');s.querySelectorAll('[data-target]').forEach(b=>b.onclick=()=>document.getElementById(b.dataset.target)?.scrollIntoView({behavior:'smooth',block:'start'}));}
function buildSecurity(){const el=document.getElementById('ndSecurity');if(!el)return;el.innerHTML='<div class="nd-security-card"><span class="ico">🔒</span><strong>Compra mais segura</strong><span>Você revisa o pedido antes de enviar.</span></div><div class="nd-security-card"><span class="ico">💰</span><strong>Taxa transparente</strong><span>A taxa é calculada pela rua escolhida.</span></div><div class="nd-security-card"><span class="ico">📲</span><strong>WhatsApp oficial</strong><span>O pedido é enviado direto para a loja.</span></div><div class="nd-security-card"><span class="ico">🧾</span><strong>Resumo completo</strong><span>Itens, valores e forma de pagamento aparecem antes da confirmação.</span></div>';}
function enhanceCards(){const favKey='ndburgs_favoritos_premium';let favs=new Set();try{favs=new Set(JSON.parse(localStorage.getItem(favKey)||'[]'))}catch(e){};document.querySelectorAll('.produto').forEach((card,i)=>{if(card.dataset.ndPremium==='1')return;card.dataset.ndPremium='1';const name=(card.querySelector('h3')?.textContent||('produto-'+i)).trim().toUpperCase();const heart=document.createElement('button');heart.type='button';heart.className='nd-fav'+(favs.has(name)?' active':'');heart.textContent=favs.has(name)?'♥':'♡';heart.setAttribute('aria-label','Favoritar '+name);heart.onclick=e=>{e.stopPropagation();if(favs.has(name)){favs.delete(name);heart.classList.remove('active');heart.textContent='♡'}else{favs.add(name);heart.classList.add('active');heart.textContent='♥'}try{localStorage.setItem(favKey,JSON.stringify([...favs]))}catch(_){};};card.appendChild(heart);if(name.includes('COMBO MAIS VENDIDO')){const b=document.createElement('span');b.className='nd-badge';b.textContent='⭐ DESTAQUE';card.appendChild(b)}});}
const top=document.createElement('button');top.id='ndBackTop';top.className='nd-backtop';top.type='button';top.textContent='↑';top.setAttribute('aria-label','Voltar ao topo');document.body.appendChild(top);top.onclick=()=>window.scrollTo({top:0,behavior:'smooth'});window.addEventListener('scroll',()=>{top.classList.toggle('show',scrollY>700);const pos=scrollY+window.innerHeight/3;cats.forEach(c=>{const b=document.querySelector('.nd-side-btn[data-target="'+c.id+'"]');if(b)b.classList.toggle('active',pos>=c.offsetTop&&pos<c.offsetTop+c.offsetHeight)})},{passive:true});
function init(){buildSidebar();buildSecurity();enhanceCards();if(location.protocol!=='https:')document.querySelectorAll('.nd-trustline span:first-child').forEach(x=>x.textContent='⚠️ CONEXÃO HTTP');}
window.addEventListener('DOMContentLoaded',init);setTimeout(init,300);
})();
</script><script>

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
carrinho=dados;
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

</script><script id="nd-v4-logic">
(function(){
'use strict';
const MIN=11.90;
const WA='5511963973846';
function cart(){try{return (typeof carrinho!=='undefined'&&Array.isArray(carrinho))?carrinho:(window.carrinho||[])}catch(e){return window.carrinho||[]}}
function money(v){return 'R$ '+Number(v||0).toFixed(2).replace('.',',')}
function subtotal(){return cart().reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||1),0)}
function saveLast(){try{localStorage.setItem('ndburgs_ultimo_pedido',JSON.stringify(cart()))}catch(e){}}
function clearCart(){
  try{localStorage.removeItem('carrinho');localStorage.removeItem('ndburgs_carrinho');}catch(e){}
  if(typeof carrinho!=="undefined" && Array.isArray(carrinho)) carrinho.length=0; if(Array.isArray(window.carrinho)) window.carrinho.length=0;
  if(typeof window.atualizarCarrinho==='function') window.atualizarCarrinho();
}
function buildCheckout(){
 const modal=document.getElementById('modalFinalizar');
 const panel=modal?.querySelector('.painel-finalizar');
 if(!panel)return;
 panel.innerHTML=`
  <div class="cabecalho-finalizar">
    <div><span style="color:#ff6a00;font-size:11px;font-weight:900">FINALIZAR PEDIDO</span><h2 style="margin-top:3px">QUASE LÁ 🍔</h2></div>
    <button class="btn-fechar-finalizar" onclick="fecharModalFinalizar()">×</button>
  </div>
  <div class="nd-v4-stepbar">
   <div class="nd-v4-step active" data-step="1">1 • DADOS</div><div class="nd-v4-step" data-step="2">2 • ENTREGA</div><div class="nd-v4-step" data-step="3">3 • PAGAMENTO</div><div class="nd-v4-step" data-step="4">4 • CONFIRMAR</div>
  </div>
  <div class="nd-v4-step-content active" data-content="1">
    <label>Seu nome</label><input id="nomeModal" type="text" placeholder="Como podemos te chamar?">
    <label>WhatsApp</label><input id="telefoneModal" type="tel" placeholder="(11) 99999-9999">
    <div class="nd-v4-delivery-estimate" style="margin-top:14px">🔒 <b>Seus dados ficam apenas para realizar seu pedido.</b></div>
    <button class="nd-v4-next" type="button" onclick="ndNext(1)">CONTINUAR →</button>
  </div>
  <div class="nd-v4-step-content" data-content="2">
    <label>Como receber?</label>
    <div class="nd-v4-payment-grid" style="grid-template-columns:1fr 1fr;margin-bottom:12px">
      <button type="button" class="nd-v4-pay active" data-type="ENTREGA" onclick="ndTipo('ENTREGA')">🛵<br>DELIVERY</button>
      <button type="button" class="nd-v4-pay" data-type="RETIRADA" onclick="ndTipo('RETIRADA')">🏪<br>RETIRADA</button>
    </div>
    <select id="tipoPedidoModal" style="display:none"><option value="ENTREGA">ENTREGA</option><option value="RETIRADA">RETIRADA</option></select>
    <div id="enderecoAreaModal">
      <label>Pesquise sua rua</label>
      <input id="ruaBuscaModal" type="search" autocomplete="off" placeholder="🔎 Digite o nome da rua">
      <select id="ruaModal" onchange="calcularTaxaModal()"><option value="">Selecione sua rua</option></select>
      <label>Número</label><input id="numeroModal" type="text" placeholder="Número">
      <label>Complemento <small>(opcional)</small></label><input id="complementoModal" type="text" placeholder="Casa, apto, bloco...">
      <div id="avisoTaxaModal" class="aviso-taxa" style="display:none"></div>
    </div>
    <div id="ndRetiradaInfo" style="display:none" class="nd-v4-delivery-estimate">🏪 <b>Retirada no local</b><br>Sem taxa de entrega.</div>
    <div class="nd-v4-delivery-estimate">🕐 <b>Estimativa:</b> normalmente 30–50 minutos após a confirmação.</div>
    <button class="nd-v4-next" type="button" onclick="ndNext(2)">CONTINUAR →</button>
    <button class="nd-v4-back" type="button" onclick="ndBack(2)">← VOLTAR</button>
  </div>
  <div class="nd-v4-step-content" data-content="3">
    <label>Escolha o pagamento</label>
    <div class="nd-v4-payment-grid">
      <button type="button" class="nd-v4-pay" data-pay="PIX" onclick="ndPay('PIX')">💠<br>PIX</button>
      <button type="button" class="nd-v4-pay" data-pay="DINHEIRO" onclick="ndPay('DINHEIRO')">💵<br>DINHEIRO</button>
      <button type="button" class="nd-v4-pay" data-pay="CARTÃO" onclick="ndPay('CARTÃO')">💳<br>CARTÃO</button>
    </div>
    <select id="pagamentoModal" style="display:none"><option value="">Selecione</option><option value="PIX">PIX</option><option value="DINHEIRO">DINHEIRO</option><option value="CARTÃO">CARTÃO</option></select>
    <div id="trocoAreaModal" style="display:none;margin-top:12px"><label>Troco para quanto?</label><input id="trocoModal" type="number" step="0.01" placeholder="Ex.: 50"></div>
    <label style="margin-top:14px">Observação <small>(opcional)</small></label>
    <textarea id="observacaoModal" placeholder="Ex.: sem cebola, tocar campainha..."></textarea>
    <button class="nd-v4-next" type="button" onclick="ndNext(3)">REVISAR PEDIDO →</button>
    <button class="nd-v4-back" type="button" onclick="ndBack(3)">← VOLTAR</button>
  </div>
  <div class="nd-v4-step-content" data-content="4">
    <div class="nd-v4-summary"><div class="nd-v4-summary-title">Seu pedido</div><div id="ndV4Items"></div></div>
    <div class="nd-v4-summary">
      <div style="display:flex;justify-content:space-between;margin-bottom:6px"><span>Subtotal</span><b id="ndV4Sub">R$ 0,00</b></div>
      <div style="display:flex;justify-content:space-between;margin-bottom:10px"><span>Taxa</span><b id="ndV4Fee">R$ 0,00</b></div>
      <div style="display:flex;justify-content:space-between;align-items:end"><span style="font-weight:900">TOTAL</span><span id="ndV4Total" class="nd-v4-final-total">R$ 0,00</span></div>
    </div>
    <div class="nd-v4-note">Ao confirmar, o pedido será aberto no WhatsApp da ND BURGS. Depois que o WhatsApp abrir, o carrinho será limpo neste aparelho.</div>
    <button class="nd-v4-next" type="button" onclick="finalizarPedidoModal()">🟢 ENVIAR PEDIDO PELO WHATSAPP</button>
    <button class="nd-v4-back" type="button" onclick="ndBack(4)">← VOLTAR</button>
  </div>`;
 loadModalData(); ndFilterStreet();
}
function loadModalData(){
 const n=localStorage.getItem('ndburgs_nome')||localStorage.getItem('ndburgs_nomeModal')||'';
 const t=localStorage.getItem('ndburgs_telefone')||localStorage.getItem('ndburgs_telefoneModal')||'';
 if(n)document.getElementById('nomeModal').value=n;if(t)document.getElementById('telefoneModal').value=t;
 if(typeof carregarRuasModal==='function') carregarRuasModal();
 document.getElementById('tipoPedidoModal').value='ENTREGA';
 document.getElementById('pagamentoModal').value='';
}
function ndStep(n){
 document.querySelectorAll('.nd-v4-step-content').forEach(x=>x.classList.toggle('active',x.dataset.content==n));
 document.querySelectorAll('.nd-v4-step').forEach(x=>{let v=Number(x.dataset.step);x.classList.toggle('active',v===n);x.classList.toggle('done',v<n)});
 const panel=document.querySelector('#modalFinalizar .painel-finalizar'); if(panel)panel.scrollTop=0;
 if(n===4)ndSummary();
}
function ndNext(n){
 if(n===1){
  const nome=document.getElementById('nomeModal').value.trim(), tel=document.getElementById('telefoneModal').value.replace(/\D/g,'');
  if(!nome)return alert('Digite seu nome.');
  if(tel.length<10||tel.length>11)return alert('Digite um WhatsApp válido com DDD.');
  localStorage.setItem('ndburgs_nomeModal',nome);localStorage.setItem('ndburgs_telefoneModal',document.getElementById('telefoneModal').value.trim());
 }
 if(n===2){
  const tipo=document.getElementById('tipoPedidoModal').value;
  if(tipo==='ENTREGA'){
   if(!document.getElementById('ruaModal').value)return alert('Selecione sua rua.');
   if(!document.getElementById('numeroModal').value.trim())return alert('Digite o número do endereço.');
  }
 }
 if(n===3){
  if(!document.getElementById('pagamentoModal').value)return alert('Escolha uma forma de pagamento.');
 }
 ndStep(n+1);
}
window.ndNext=ndNext;
window.ndBack=n=>ndStep(n-1);
window.ndTipo=function(tipo){
 document.getElementById('tipoPedidoModal').value=tipo;
 document.querySelectorAll('[data-type]').forEach(b=>b.classList.toggle('active',b.dataset.type===tipo));
 const area=document.getElementById('enderecoAreaModal'),ri=document.getElementById('ndRetiradaInfo');
 if(area)area.style.display=tipo==='ENTREGA'?'block':'none'; if(ri)ri.style.display=tipo==='RETIRADA'?'block':'none';
 if(typeof calcularTaxaModal==='function')calcularTaxaModal();
}
window.ndPay=function(pay){
 document.getElementById('pagamentoModal').value=pay;
 document.querySelectorAll('[data-pay]').forEach(b=>b.classList.toggle('active',b.dataset.pay===pay));
 document.getElementById('trocoAreaModal').style.display=pay==='DINHEIRO'?'block':'none';
}
function ndSummary(){
 const tipo=document.getElementById('tipoPedidoModal').value, rua=document.getElementById('ruaModal').value;
 const fee=tipo==='ENTREGA'?Number(taxas[rua]||0):0, sub=subtotal();
 document.getElementById('ndV4Sub').textContent=money(sub);document.getElementById('ndV4Fee').textContent=money(fee);document.getElementById('ndV4Total').textContent=money(sub+fee);
 document.getElementById('ndV4Items').innerHTML=cart().map(i=>`<div style="display:flex;justify-content:space-between;gap:10px;padding:6px 0;border-bottom:1px solid #222"><span>${i.quantidade}x ${i.nome}${i.detalhes?.length?'<small style="display:block;color:#777">↳ '+i.detalhes.join(', ')+'</small>':''}</span><b>${money(i.preco*i.quantidade)}</b></div>`).join('');
}
window.ndSummary=ndSummary;
window.finalizarPedidoModal=function(){
 if(!cart().length)return alert('Seu carrinho está vazio.');
 const nome=document.getElementById('nomeModal').value.trim();
 const telefone=document.getElementById('telefoneModal').value.trim();
 const telNum=telefone.replace(/\D/g,'');
 const tipo=document.getElementById('tipoPedidoModal').value;
 const rua=document.getElementById('ruaModal').value;
 const numero=document.getElementById('numeroModal').value.trim();
 const complemento=document.getElementById('complementoModal').value.trim();
 const pagamento=document.getElementById('pagamentoModal').value;
 const troco=document.getElementById('trocoModal').value;
 const obs=document.getElementById('observacaoModal').value.trim();
 if(!nome)return alert('Digite seu nome.');
 if(telNum.length<10||telNum.length>11)return alert('Digite um WhatsApp válido com DDD.');
 if(tipo==='ENTREGA'&&(!rua||!numero))return alert('Complete seu endereço.');
 if(!pagamento)return alert('Escolha o pagamento.');
 const fee=tipo==='ENTREGA'?Number(taxas[rua]||0):0, sub=subtotal(), total=sub+fee;
 if(sub<MIN)return alert('O pedido mínimo é '+money(MIN)+'. Faltam '+money(MIN-sub)+'.');
 const lines=[];
 lines.push('🍔 *NOVO PEDIDO - ND BURGS*','━━━━━━━━━━━━━━━━━━━━');
 lines.push('👤 *CLIENTE:* '+nome,'📱 *WHATSAPP:* '+telefone,'📦 *TIPO:* '+(tipo==='ENTREGA'?'DELIVERY':'RETIRADA'));
 if(tipo==='ENTREGA'){lines.push('📍 *ENDEREÇO:* '+rua+', Nº '+numero);if(complemento)lines.push('🏠 *COMPLEMENTO:* '+complemento)}
 lines.push('','🛒 *ITENS DO PEDIDO*','━━━━━━━━━━━━━━━━━━━━');
 cart().forEach(i=>{lines.push(`${i.quantidade}x ${i.nome} — ${money(i.preco*i.quantidade)}`);if(i.detalhes?.length)lines.push('   ↳ '+i.detalhes.join(', '));});
 lines.push('','💰 *SUBTOTAL:* '+money(sub),'🛵 *TAXA:* '+money(fee),'💵 *TOTAL:* '+money(total),'💳 *PAGAMENTO:* '+pagamento);
 if(pagamento==='DINHEIRO'&&troco)lines.push('💵 *TROCO PARA:* '+money(Number(troco)));
 if(obs)lines.push('','📝 *OBSERVAÇÃO:* '+obs);
 lines.push('','━━━━━━━━━━━━━━━━━━━━','ND BURGS 🍔');
 saveLast();
 const url='https://wa.me/'+WA+'?text='+encodeURIComponent(lines.join('\n'));
 clearCart();
 fecharModalFinalizar();
 window.location.href=url;
}
window.irParaFinalizarPedido=function(){
 if(!cart().length)return alert('Seu carrinho está vazio.');
 fecharCarrinho();
 const modal=document.getElementById('modalFinalizar');
 if(!modal)return;
 modal.classList.add('ativo');document.body.style.overflow='hidden';
 buildCheckout();ndStep(1);
}
function ndFilterStreet(){
 const inp=document.getElementById('ruaBuscaModal'),sel=document.getElementById('ruaModal');if(!inp||!sel||inp.dataset.ndV4)return;
 inp.dataset.ndV4='1';
 inp.addEventListener('input',()=>{
  const q=inp.value.toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'');
  [...sel.options].forEach((o,i)=>{if(i===0)return;o.hidden=q&&!o.textContent.normalize('NFD').replace(/[\u0300-\u036f]/g,'').includes(q)});
 });
}
window.addEventListener('DOMContentLoaded',()=>{
 setTimeout(()=>{buildCheckout();},250);
});
})();
</script></body></html>
