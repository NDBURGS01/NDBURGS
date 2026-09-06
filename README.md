<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#080816">
<meta name="nd-site-version" content="20260906-NOVA-R1">
<title>ND BURGS | Pedido Online</title>
<style>
:root{--bg:#080816;--panel:#111126;--panel2:#171735;--line:rgba(255,255,255,.09);--text:#f8f9ff;--muted:#a9acce;--cyan:#35e7ff;--violet:#8f5cff;--pink:#ff4fd8;--green:#31e981;--danger:#ff5f7a;--shadow:0 24px 70px rgba(0,0,0,.45)}
*{box-sizing:border-box;margin:0;padding:0}html{scroll-behavior:smooth}body{font-family:Inter,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;background:radial-gradient(900px 500px at 10% -10%,rgba(53,231,255,.13),transparent 60%),radial-gradient(900px 500px at 100% 10%,rgba(143,92,255,.16),transparent 60%),linear-gradient(180deg,#070712 0%,#0a0a18 45%,#07070f 100%);color:var(--text);padding-bottom:110px;overflow-x:hidden}
body:before{content:"";position:fixed;inset:0;pointer-events:none;opacity:.22;background-image:radial-gradient(rgba(255,255,255,.08) 1px,transparent 1px);background-size:22px 22px;mask-image:linear-gradient(to bottom,black,transparent 85%);z-index:-1}
button,input,select,textarea{font:inherit}button{cursor:pointer}img{max-width:100%;display:block}
.site-header{position:sticky;top:0;z-index:1200;background:rgba(7,7,18,.80);backdrop-filter:blur(20px);border-bottom:1px solid rgba(53,231,255,.13)}
.header-inner{max-width:1200px;margin:auto;min-height:72px;padding:10px 18px;display:flex;align-items:center;justify-content:space-between;gap:14px}.logo{width:110px;border-radius:15px;box-shadow:0 0 0 1px rgba(255,255,255,.05),0 10px 28px rgba(0,0,0,.3)}.header-actions{display:flex;gap:8px;align-items:center}.icon-btn{border:1px solid var(--line);background:rgba(255,255,255,.05);color:#fff;border-radius:12px;min-height:44px;padding:0 12px;font-weight:900}.icon-btn:hover{border-color:rgba(53,231,255,.4);background:rgba(53,231,255,.08)}
.hero{max-width:1200px;margin:18px auto 0;padding:0 16px}.hero-card{position:relative;overflow:hidden;display:grid;grid-template-columns:1.15fr .85fr;gap:20px;align-items:center;padding:28px;border-radius:30px;border:1px solid rgba(143,92,255,.22);background:linear-gradient(135deg,rgba(17,17,38,.96),rgba(10,10,24,.94));box-shadow:var(--shadow)}.hero-card:before,.hero-card:after{content:"";position:absolute;border-radius:999px;filter:blur(10px);pointer-events:none}.hero-card:before{width:280px;height:280px;right:-100px;top:-100px;background:rgba(53,231,255,.18)}.hero-card:after{width:240px;height:240px;left:-120px;bottom:-130px;background:rgba(255,79,216,.14)}.hero-copy{position:relative;z-index:1}.kicker{display:inline-flex;align-items:center;gap:7px;padding:7px 10px;border-radius:999px;border:1px solid rgba(53,231,255,.25);background:rgba(53,231,255,.08);color:var(--cyan);font-size:11px;font-weight:1000;letter-spacing:1.2px}.hero h1{margin-top:12px;font-size:clamp(36px,6vw,72px);line-height:.92;letter-spacing:-3px}.hero h1 span{display:block;background:linear-gradient(90deg,#fff,var(--cyan),#b78cff);-webkit-background-clip:text;background-clip:text;color:transparent}.hero p{margin-top:14px;color:#b9bbcd;max-width:650px;line-height:1.6;font-size:14px}.hero-actions{margin-top:20px;display:flex;gap:10px;flex-wrap:wrap}.primary{border:0;border-radius:14px;padding:13px 17px;background:linear-gradient(135deg,var(--cyan),#1db6ff);color:#06101a;font-weight:1000;box-shadow:0 12px 28px rgba(53,231,255,.2)}.secondary{border:1px solid var(--line);border-radius:14px;padding:13px 17px;background:rgba(255,255,255,.05);color:#fff;font-weight:900}.hero-art{position:relative;z-index:1;display:grid;place-items:center;min-height:280px}.hero-art img{width:min(370px,100%);filter:drop-shadow(0 25px 40px rgba(0,0,0,.7));transform:rotate(-3deg);animation:float 4s ease-in-out infinite}.hero-badge{position:absolute;right:5%;bottom:8%;padding:10px 13px;border-radius:16px;background:linear-gradient(135deg,#8f5cff,#ff4fd8);font-weight:1000;box-shadow:0 15px 35px rgba(143,92,255,.25)}@keyframes float{0%,100%{transform:translateY(0) rotate(-3deg)}50%{transform:translateY(-7px) rotate(0deg)}
.delivery-strip{max-width:1200px;margin:14px auto 0;padding:0 16px}.delivery-card{display:grid;grid-template-columns:1.2fr .8fr;gap:12px}.delivery-main,.delivery-side{border:1px solid rgba(53,231,255,.14);background:linear-gradient(135deg,rgba(20,20,45,.95),rgba(12,12,29,.95));border-radius:20px;padding:18px;box-shadow:0 18px 45px rgba(0,0,0,.22)}.delivery-main{position:relative;overflow:hidden}.delivery-main:after{content:"";position:absolute;inset:auto -30% -70% 30%;height:160px;background:radial-gradient(circle,rgba(53,231,255,.16),transparent 60%)}.delivery-tag{color:var(--cyan);font-size:10px;font-weight:1000;letter-spacing:1.5px}.delivery-main strong{display:block;font-size:clamp(24px,4vw,38px);margin-top:5px}.delivery-main p{margin-top:5px;color:#aaaec3;font-size:12px}.delivery-side{display:flex;align-items:center;justify-content:center;text-align:center;flex-direction:column;gap:6px}.delivery-side b{font-size:18px}.delivery-side span{font-size:11px;color:#aeb0c3}
.address-hero{max-width:1200px;margin:14px auto 0;padding:0 16px}.address-box{position:relative;overflow:hidden;padding:20px;border-radius:24px;border:1px solid rgba(255,79,216,.28);background:linear-gradient(135deg,rgba(37,17,54,.96),rgba(13,13,33,.96));box-shadow:0 18px 48px rgba(0,0,0,.28)}.address-box:before{content:"";position:absolute;left:-40px;top:-60px;width:190px;height:190px;border-radius:50%;background:rgba(255,79,216,.12);filter:blur(18px)}.address-head{position:relative;z-index:1;display:flex;align-items:flex-start;justify-content:space-between;gap:12px;flex-wrap:wrap}.address-title{font-size:22px;font-weight:1000;letter-spacing:-.7px}.address-title span{color:var(--pink)}.address-copy{margin-top:7px;color:#c2c3d5;font-size:12px;line-height:1.55;max-width:800px}.address-copy b{color:#fff}.address-save{border:1px solid rgba(53,231,255,.24);background:rgba(53,231,255,.08);color:var(--cyan);border-radius:13px;padding:10px 13px;font-size:11px;font-weight:1000;white-space:nowrap}.address-grid{position:relative;z-index:1;display:grid;grid-template-columns:1.5fr .5fr;gap:10px;margin-top:14px}.field{display:flex;flex-direction:column;gap:6px}.field label{font-size:10px;color:#999db2;font-weight:1000;letter-spacing:.7px}.field input,.field select,.field textarea{width:100%;min-height:48px;padding:12px 13px;border-radius:13px;border:1px solid rgba(255,255,255,.09);background:#09091a;color:#fff;outline:none}.field input:focus,.field select:focus,.field textarea:focus{border-color:rgba(53,231,255,.55);box-shadow:0 0 0 3px rgba(53,231,255,.08)}.address-status{position:relative;z-index:1;margin-top:10px;display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap;padding:10px 12px;border-radius:13px;background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.07);font-size:11px}.address-status strong{color:#fff}.address-status span{color:var(--cyan);font-weight:1000}
.main{max-width:1200px;margin:auto;padding:16px}.toolbar{position:sticky;top:72px;z-index:800;display:flex;gap:10px;align-items:center;padding:10px;margin:12px 0;background:rgba(8,8,20,.82);backdrop-filter:blur(18px);border:1px solid var(--line);border-radius:18px}.toolbar input{flex:1;min-width:0;background:#09091a;border:1px solid rgba(255,255,255,.09);color:#fff;border-radius:13px;padding:13px 15px;outline:none}.count{font-size:11px;color:#8589a0;white-space:nowrap}.category-nav{display:flex;gap:8px;overflow:auto;padding:2px 2px 10px;margin-bottom:8px;scrollbar-width:none}.category-nav::-webkit-scrollbar{display:none}.cat-btn{flex:0 0 auto;border:1px solid rgba(255,255,255,.08);background:linear-gradient(180deg,#17172e,#10101f);color:#d8d9e8;padding:11px 13px;border-radius:999px;font-size:12px;font-weight:1000}.cat-btn:hover{border-color:rgba(53,231,255,.5);color:#fff;background:rgba(53,231,255,.08)}
.categoria{scroll-margin-top:155px;margin-top:28px}.categoria-titulo{display:flex;align-items:center;gap:10px;margin-bottom:13px;font-size:clamp(22px,4vw,30px);font-weight:1000;letter-spacing:-1px;color:#fff}.categoria-titulo:before{content:"";width:6px;height:30px;border-radius:999px;background:linear-gradient(var(--cyan),var(--violet));box-shadow:0 0 18px rgba(53,231,255,.25)}.produtos{display:grid!important;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:14px!important}.produto{background:linear-gradient(160deg,#16162e,#0f0f20)!important;border:1px solid rgba(255,255,255,.075)!important;border-radius:20px!important;padding:11px!important;box-shadow:0 14px 34px rgba(0,0,0,.22)!important;transition:.2s ease!important;overflow:hidden}.produto:hover{transform:translateY(-4px);border-color:rgba(53,231,255,.3)!important;box-shadow:0 22px 45px rgba(0,0,0,.34)!important}.produto-imagem{width:100%!important;height:215px!important;object-fit:contain!important;border-radius:14px!important;background:radial-gradient(circle at 50% 45%,#24244b,#090919)!important}.produto h3{margin:11px 2px 5px!important;font-size:16px!important;font-weight:1000!important}.produto p{color:#9296af!important;font-size:11px!important;line-height:1.45!important;min-height:34px!important}.preco{color:#fff!important;font-size:22px!important;font-weight:1000!important;margin:10px 2px!important}.btn-add{width:100%!important;min-height:46px!important;border:0!important;border-radius:13px!important;background:linear-gradient(135deg,var(--violet),#6e46f5)!important;color:#fff!important;font-weight:1000!important;box-shadow:0 9px 22px rgba(143,92,255,.18)!important}.search-hidden{display:none!important}.no-results{display:none;text-align:center;padding:28px;border:1px dashed #373750;border-radius:18px;color:#999db2;margin-top:12px}
.carrinho-flutuante{position:fixed!important;right:18px;left:auto!important;bottom:18px;z-index:5000;display:flex;align-items:center;gap:10px;padding:10px 11px;border-radius:18px;border:1px solid rgba(53,231,255,.3);background:linear-gradient(135deg,#12123a,#17174a);box-shadow:0 18px 45px rgba(0,0,0,.5);opacity:0;transform:translateY(18px);pointer-events:none;transition:.25s}.carrinho-flutuante.ativo{opacity:1;transform:none;pointer-events:auto}.carrinho-flutuante:before{content:'🛒';width:44px;height:44px;border-radius:14px;display:grid;place-items:center;background:linear-gradient(135deg,var(--cyan),var(--violet));font-size:22px}.carrinho-flutuante-info{min-width:125px}.carrinho-flutuante-info strong{display:block;font-size:12px}.carrinho-flutuante-info span{display:block;color:#a6aac0;font-size:10px;margin-top:3px}.carrinho-flutuante-total{font-weight:1000;color:var(--cyan);white-space:nowrap}.btn-ver-carrinho{border:0!important;background:#fff!important;color:#090915!important;border-radius:11px!important;padding:10px 12px!important;font-size:11px!important;font-weight:1000!important}
.modal-carrinho,.modal-finalizar,.modal-personalizacao{position:fixed;inset:0;background:rgba(2,2,10,.78);z-index:10000;display:none;align-items:flex-end;justify-content:center;padding:0;backdrop-filter:blur(10px)}.modal-carrinho.ativo,.modal-finalizar.ativo,.modal-personalizacao.ativo{display:flex}.painel-carrinho,.painel-finalizar,.modal-box{width:min(760px,100%);max-height:94vh;overflow:auto;background:linear-gradient(160deg,#151532,#0b0b18);border:1px solid rgba(53,231,255,.22);border-radius:26px 26px 0 0;padding:18px;box-shadow:0 -30px 90px rgba(0,0,0,.65)}.cabecalho-carrinho,.cabecalho-finalizar,.modal-topo{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-bottom:14px}.cabecalho-carrinho h2,.cabecalho-finalizar h2,.modal-topo h2{font-size:23px}.fechar-carrinho,.btn-fechar-finalizar,.modal-fechar{width:40px;height:40px;border:1px solid rgba(255,255,255,.08);border-radius:12px;background:#23233f;color:#fff;font-size:22px}.item-carrinho-modal{border-bottom:1px solid rgba(255,255,255,.06);padding:13px 0}.item-carrinho-modal-topo{display:flex;justify-content:space-between;gap:10px}.item-carrinho-modal small{display:block;color:#8d91a7;margin-top:4px;font-size:10px;line-height:1.4}.controles-modal{display:flex;align-items:center;gap:6px;margin-top:8px}.controles-modal button,.controles button{width:34px;height:34px;border-radius:9px;border:1px solid rgba(255,255,255,.08);background:#24243d;color:#fff;font-weight:1000}.remover{background:#3d1721!important;color:#ff93a4!important}.resumo-modal{margin-top:16px;border:1px solid rgba(255,255,255,.07);border-radius:17px;padding:12px;background:#0c0c1b}.linha{display:flex;justify-content:space-between;padding:7px 0;color:#b8bbcc;font-size:12px}.linha strong{color:#fff}.linha.total-modal{border-top:1px solid rgba(255,255,255,.09);margin-top:6px;padding-top:13px}.linha.total-modal strong{font-size:28px}.nd-site-offer{color:#72dfff!important}.sheet-actions{display:grid;grid-template-columns:1fr 1fr;gap:9px;margin-top:12px}.btn-continuar-comprando,.btn-finalizar-pedido,.btn-finalizar-modal{min-height:50px;border:0!important;border-radius:13px!important;font-weight:1000!important}.btn-continuar-comprando{background:#24243d!important;color:#fff!important}.btn-finalizar-pedido,.btn-finalizar-modal{background:linear-gradient(135deg,var(--cyan),var(--violet))!important;color:#07101b!important}
.nd-address-note{margin-bottom:13px;padding:13px;border-radius:16px;border:1px solid rgba(255,79,216,.18);background:rgba(255,79,216,.05);font-size:11px;color:#c5c7d8;line-height:1.5}.nd-address-note b{color:var(--pink)}.checkout-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}.checkout-full{grid-column:1/-1}.pix-panel{display:none;margin-top:10px;padding:13px;border-radius:16px;border:1px solid rgba(53,231,255,.25);background:linear-gradient(145deg,#0d1a25,#101024)}.pix-panel.show{display:block}.pix-panel .pix-title{color:var(--cyan);font-weight:1000;font-size:13px}.pix-key{margin-top:8px;padding:10px;border-radius:10px;background:#070711;border:1px dashed rgba(53,231,255,.35);word-break:break-all;font-weight:1000}.pix-copy{margin-top:9px;width:100%;min-height:45px;border:0;border-radius:11px;background:linear-gradient(135deg,var(--cyan),#4db9ff);color:#07101a;font-weight:1000}.pix-return{margin-top:9px;padding:10px 12px;border-radius:11px;background:rgba(53,231,255,.08);border:1px solid rgba(53,231,255,.18);font-size:11px;color:#c7cada;line-height:1.45}.pix-return b{color:#fff}.success{position:fixed;inset:0;z-index:20000;display:none;place-items:center;padding:18px;background:radial-gradient(circle at 50% 45%,rgba(53,231,255,.18),transparent 32%),rgba(3,3,12,.96)}.success.show{display:grid}.success-card{width:min(680px,100%);padding:28px;border:1px solid rgba(53,231,255,.24);border-radius:28px;background:linear-gradient(160deg,#141433,#09091b);text-align:center;box-shadow:0 25px 90px rgba(0,0,0,.7)}.success-icon{width:82px;height:82px;margin:0 auto 14px;border-radius:50%;display:grid;place-items:center;font-size:40px;background:linear-gradient(135deg,var(--cyan),var(--violet));color:#07101b;box-shadow:0 0 42px rgba(53,231,255,.22)}.success h2{font-size:clamp(34px,8vw,60px);line-height:.95;letter-spacing:-2px}.success h2 span{display:block;color:var(--cyan)}.success p{margin:14px auto 0;max-width:560px;color:#c6c8d6;line-height:1.6;font-size:14px}.success button{margin-top:18px;min-height:48px;padding:0 18px;border:0;border-radius:13px;background:linear-gradient(135deg,var(--cyan),var(--violet));color:#07101b;font-weight:1000}
#modalPersonalizacao .modal-secao{margin-top:18px;padding-top:15px;border-top:1px solid rgba(255,255,255,.08)}#modalPersonalizacao .modal-secao h3{color:var(--cyan);margin-bottom:10px}.opcoes-tamanho{display:grid;grid-template-columns:repeat(3,1fr);gap:8px}.opcao-tamanho{position:relative}.opcao-tamanho input{position:absolute;opacity:0}.opcao-tamanho label{display:block;padding:12px 8px;text-align:center;border:1px solid rgba(255,255,255,.09);border-radius:10px;background:#0c0c1b;cursor:pointer}.opcao-tamanho input:checked+label{border-color:var(--cyan);background:rgba(53,231,255,.09);color:var(--cyan)}.lista-acompanhamentos{display:grid;grid-template-columns:1fr 1fr;gap:8px}.opcao-acomp{display:flex;gap:8px;align-items:center;padding:10px;border:1px solid rgba(255,255,255,.08);border-radius:10px;background:#0b0b1a}.preco-adicional{color:var(--cyan)}
.suggestions-modal{position:fixed;inset:0;z-index:15000;display:none;align-items:flex-end;justify-content:center;background:rgba(0,0,0,.78);backdrop-filter:blur(10px)}.suggestions-modal.show{display:flex}.suggestions-panel{width:min(760px,100%);max-height:90vh;overflow:auto;background:linear-gradient(160deg,#151532,#0b0b18);border:1px solid rgba(255,79,216,.2);border-radius:26px 26px 0 0;padding:18px}.suggestions-head{display:flex;align-items:center;justify-content:space-between}.suggestions-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:10px;margin-top:12px}.suggestion-card{display:flex;gap:10px;align-items:center;padding:10px;border:1px solid var(--line);border-radius:15px;background:rgba(255,255,255,.035)}.suggestion-card img{width:70px;height:70px;object-fit:contain;border-radius:10px;background:#090a0b}.suggestion-card strong{display:block;font-size:13px}.suggestion-card span{display:block;color:var(--cyan);font-weight:900;font-size:13px;margin:4px 0}.suggestion-card button{border:0;background:var(--cyan);color:#07101a;border-radius:9px;padding:8px 10px;font-weight:1000}.suggestions-close{width:36px;height:36px;border:0;border-radius:50%;background:#24243d;color:#fff;font-size:20px}.toast-carrinho{position:fixed;top:88px;left:50%;transform:translateX(-50%) translateY(-10px);z-index:21000;opacity:0;pointer-events:none;padding:10px 15px;border-radius:999px;background:linear-gradient(135deg,var(--green),#22b66e);color:#07130e;font-weight:1000;transition:.2s}.toast-carrinho.mostrar{opacity:1;transform:translateX(-50%)}
footer{max-width:1200px;margin:30px auto 0;padding:0 16px 20px}.footer-card{padding:22px;border:1px solid rgba(255,255,255,.08);border-radius:22px;background:linear-gradient(145deg,#14142b,#0b0b18);display:flex;justify-content:space-between;gap:15px;align-items:center}.footer-card strong{font-size:18px}.footer-card span{display:block;margin-top:4px;color:#8c90a5;font-size:11px}.footer-link{color:#fff;text-decoration:none;font-weight:1000}
@media(max-width:800px){.hero-card{grid-template-columns:1fr;padding:22px}.hero-art{min-height:210px;order:-1}.hero-art img{width:min(280px,82%)}.delivery-card{grid-template-columns:1fr}.address-grid{grid-template-columns:1fr}.toolbar{top:64px}.sheet-actions{grid-template-columns:1fr}.checkout-grid{grid-template-columns:1fr}.checkout-full{grid-column:auto}.footer-card{flex-direction:column;align-items:flex-start}
@media(max-width:520px){body{padding-bottom:92px}.header-inner{min-height:64px;padding:9px 12px}.logo{width:92px}.hero{padding:0 10px}.main{padding:10px}.delivery-strip,.address-hero{padding:0 10px}.hero-card{border-radius:24px;padding:18px}.hero h1{font-size:41px;letter-spacing:-2px}.address-title{font-size:19px}.address-copy{font-size:11px}.categoria{scroll-margin-top:145px}.produtos{grid-template-columns:repeat(2,minmax(0,1fr))!important;gap:9px!important}.produto{padding:8px!important;border-radius:16px!important}.produto-imagem{height:145px!important}.produto h3{font-size:13px!important}.produto p{font-size:10px!important;min-height:38px!important}.preco{font-size:17px!important}.btn-add{font-size:11px!important;min-height:45px!important}.carrinho-flutuante{left:10px!important;right:10px!important;bottom:10px}.carrinho-flutuante-total{display:none}.painel-carrinho,.painel-finalizar,.modal-box{padding:14px}.suggestions-grid{grid-template-columns:1fr}
@media(prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important;scroll-behavior:auto!important}
</style>
</head>
<body>
<header class="site-header"><div class="header-inner"><img class="logo" src="https://i.ibb.co/5gsVbBcb/corretooo.jpg" alt="ND BURGS"><div class="header-actions"><button class="icon-btn" onclick="document.getElementById('cardapio').scrollIntoView({behavior:'smooth'})">CARDÁPIO</button><button class="icon-btn" onclick="abrirCarrinho()">🛒 CARRINHO</button></div></div></header>
<section class="hero"><div class="hero-card"><div class="hero-copy"><span class="kicker">⚡ PEDIDO DIRETO • ND BURGS</span><h1>SEU PEDIDO.<span>SEU JEITO.</span></h1><p>Escolha seus favoritos, informe o endereço para calcular a entrega e conclua o pedido com um fluxo simples.</p><div class="hero-actions"><button class="primary" onclick="document.getElementById('cardapio').scrollIntoView({behavior:'smooth'})">COMEÇAR PEDIDO →</button><button class="secondary" onclick="abrirCarrinho()">VER CARRINHO</button></div></div><div class="hero-art"><img src="https://i.ibb.co/nMmfSSt1/Chat-GPT-Image-28-de-jul-de-2026-22-33-11.png" alt="Hambúrguer ND BURGS"><div class="hero-badge">#NDBURGS</div></div></div></section>
<section class="delivery-strip"><div class="delivery-card"><div class="delivery-main"><div class="delivery-tag">⏱️ PREVISÃO DE ENTREGA</div><strong>40–50 MINUTINHOS</strong><p>Tempo estimado após a confirmação do pedido.</p></div><div class="delivery-side"><b>📲 PEDIDO PELO SITE</b><span>Rápido • direto • sem complicação</span></div></div></section>
<section class="address-hero" id="endereco"><div class="address-box"><div class="address-head"><div><div class="address-title"><span>📍</span> COLOQUE SEU ENDEREÇO</div><p class="address-copy"><b>Deixe salvo aqui para próximos pedidos</b> e para somar a taxa de entrega do seu pedido de hoje. <b>Se o pedido for para outro endereço do que está salvo atualmente, por favor troque-o.</b></p></div><button class="address-save" onclick="document.getElementById('ruaBusca').focus()">EDITAR ENDEREÇO</button></div><div class="address-grid"><div class="field"><label>PESQUISAR SUA RUA</label><input id="ruaBusca" type="search" autocomplete="off" placeholder="Digite parte do nome da rua"></div><div class="field"><label>NÚMERO</label><input id="numero" type="text" inputmode="numeric" placeholder="Número"></div></div><div class="address-grid" style="grid-template-columns:1fr 1fr;margin-top:10px"><div class="field"><label>RUA SELECIONADA</label><select id="rua" onchange="calcularTaxa()"><option value="">Selecione sua rua</option></select></div><div class="field"><label>TIPO</label><select id="tipoPedido" onchange="alterarTipoPedido()"><option value="ENTREGA">🏍️ DELIVERY</option><option value="RETIRADA">🏪 RETIRADA</option></select></div></div><div id="avisoTaxa" class="address-status" style="display:none"></div><div class="address-status"><strong id="enderecoSalvoTexto">Endereço ainda não selecionado</strong><span id="taxaEndTexto">Selecione sua rua para calcular a taxa</span></div></div></section>
<main class="main" id="cardapio"><div class="toolbar"><input id="buscaProdutos" type="search" autocomplete="off" placeholder="🔎 Buscar hambúrguer, combo, açaí, pastel, bebida..."><span id="contadorBusca" class="count"></span></div><div id="semResultados" class="no-results">Nenhum produto encontrado. Tente outro nome.</div><nav class="category-nav"><button class="cat-btn" onclick="document.getElementById('combos')?.scrollIntoView({behavior:'smooth'})">❤️ COMBOS</button><button class="cat-btn" onclick="document.getElementById('tradicionais')?.scrollIntoView({behavior:'smooth'})">🍔 TRADICIONAIS</button><button class="cat-btn" onclick="document.getElementById('artesanais')?.scrollIntoView({behavior:'smooth'})">🍔 ARTESANAIS</button><button class="cat-btn" onclick="document.getElementById('combosArtesanais')?.scrollIntoView({behavior:'smooth'})">🔥 COMBOS ARTESANAIS</button><button class="cat-btn" onclick="document.getElementById('porcoes')?.scrollIntoView({behavior:'smooth'})">🍟 PORÇÕES</button><button class="cat-btn" onclick="document.getElementById('pasteis')?.scrollIntoView({behavior:'smooth'})">🥟 PASTÉIS</button><button class="cat-btn" onclick="document.getElementById('sobremesas')?.scrollIntoView({behavior:'smooth'})">🍨 AÇAÍS - MILKSHAKES E SOBREMESAS</button><button class="cat-btn" onclick="document.getElementById('bebidas')?.scrollIntoView({behavior:'smooth'})">🥤 BEBIDAS</button><button class="cat-btn" onclick="document.getElementById('adicionais')?.scrollIntoView({behavior:'smooth'})">➕ ADICIONAIS</button></nav><section class="categoria" id="combos">
<div class="categoria-titulo">
❤️ COMBOS
</div>
<div class="produtos">
<div class="produto">
<img alt="COMBO DOCE" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/wNQqzkSf/COMBO-DOCE.png"/>
<h3>COMBO DOCE</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 32,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO DOCE',32.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO GELADO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/cSLMFXtL/COMBO-GELADO.png"/>
<h3>COMBO GELADO</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 40,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO GELADO',40.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO 5 ESTRELAS" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/5WM7335K/5-ESTRELAS.png"/>
<h3>COMBO 5 ESTRELAS</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 45,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO 5 ESTRELAS',45.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO DIETA SÓ SEGUNDA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/twFJ6Vwt/COMBO-DIETA-SO-SEGUNDA.png"/>
<h3>COMBO DIETA SÓ SEGUNDA</h3>
<p>Coca lata + doce surpresa + pastel.</p>
<div class="preco">R$ 27,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO DIETA SÓ SEGUNDA',27.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO MAIS VENDIDO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/HLNHv9tt/COMBO-MAIS-VENDIDO-NOVO.png"/>
<h3>COMBO MAIS VENDIDO</h3>
<p>Um dos combos especiais da ND BURGS.</p>
<div class="preco">R$ 20,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO MAIS VENDIDO',20.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO MOTOCA ND" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/PvJqcwzb/MOTACA-ND.png"/>
<h3>COMBO MOTOCA ND</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 32,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO MOTOCA ND',32.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO SÓ LOVE" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/QR0388c/COMBO-S-LOVE.png"/>
<h3>COMBO SÓ LOVE</h3>
<p>Combo especial para compartilhar.</p>
<div class="preco">R$ 71,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO SÓ LOVE',71.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="DATE COM NDBURGS" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/23CmpQqn/DATE-COM-ND-BURGS.png"/>
<h3>DATE COM NDBURGS</h3>
<p>Combo especial para o seu date.</p>
<div class="preco">R$ 70,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('DATE COM NDBURGS',70.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="01 ND BURGS" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/Lz9JQx8f/01-NDBURGS.png"/>
<h3>01 ND BURGS</h3>
<p>Combo especial.</p>
<div class="preco">R$ 50,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('01 ND BURGS',50.90)">ADICIONAR</button>
</div>
</div>
</section>

<section class="categoria" id="tradicionais">
<div class="categoria-titulo">
🍔 TRADICIONAIS
</div>
<div class="produtos">
<div class="produto">
<img alt="X-BURGUER" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/ds9Qr0PD/BURGUER.jpg"/>
<h3>X-BURGUER</h3>
<p>Pão de hamburguer , maionese caseira ( não é verde ) , hamburguer 56gr industrializado e queijo cheddar.</p>
<div class="preco">R$ 10,90</div>
<button class="btn btn-add" onclick="adicionar('X-BURGUER',10.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="X-BACON" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/k2KQwpjp/BACON.jpg"/>
<h3>X-BACON</h3>
<p>Pão de hamburguer , molho barbecue , hamburguer 56gr industrializado , bacon e  queijo cheddar.</p>
<div class="preco">R$ 11,90</div>
<button class="btn btn-add" onclick="adicionar('X-BACON',11.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="X-SALADA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/390n5BZv/SALADA.png"/>
<h3>X-SALADA</h3>
<p>Pão de hamburguer , maionese caseira ( não é verde ) , hamburguer 56gr industrializado , alface , tomate e queijo cheddar.</p>
<div class="preco">R$ 11,90</div>
<button class="btn btn-add" onclick="adicionar('X-SALADA',11.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="X-EGG" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/NgWQv5Nm/EGG.png"/>
<h3>X-EGG</h3>
<p>Pão de hamburguer , maionese caseira ( não é verde ) , hamburguer 56gr industrializado , ovo e queijo cheddar.</p>
<div class="preco">R$ 11,90</div>
<button class="btn btn-add" onclick="adicionar('X-EGG',11.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="SELLIS" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/fGHQ9NrW/SELLIS.png"/>
<h3>SELLIS</h3>
<p>Pão de hamburguer , molho cheddar cremoso , hamburguer 56gr industrializado , alface , tomate , bacon e queijo cheddar.</p>
<div class="preco">R$ 13,90</div>
<button class="btn btn-add" onclick="adicionar('SELLIS',13.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="NUNES" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/Vszxw7h/NUNES.png"/>
<h3>NUNES</h3>
<p>Pão de brioche divido em 3 partes , maionese caseira ( não é verde ) , 4 hamburgueres 56gr industrializado , alface , tomate , cebola , ovo , bacon e queijo cheddar.</p>
<div class="preco">R$ 24,90</div>
<button class="btn btn-add" onclick="adicionar('NUNES',24.90)">ADICIONAR</button>
</div>
</div>
</section>

<section class="categoria" id="artesanais">
<div class="categoria-titulo">
🍔 ARTESANAIS
</div>
<div class="produtos">
<div class="produto">
<img alt="BERENICE" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/zW8gbZpK/BERENICE.jpg"/>
<h3>BERENICE</h3>
<p>Pão de brioche, carne artesanal 120 gr, queijo cheddar, maionese verde, alface e cebola roxa.</p>
<div class="preco">R$ 22,90</div>
<button class="btn btn-add" onclick="adicionar('BERENICE',22.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="PATAO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/tTWqZ9ST/PATAO.png"/>
<h3>PATAO</h3>
<p>Pão de brioche, carne artesanal 120 gr, queijo cheddar, molho barbecue, bacon e 2 anéis de cebola fritos.</p>
<div class="preco">R$ 23,90</div>
<button class="btn btn-add" onclick="adicionar('PATAO',23.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="DINA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/d4pD5bNc/DINA.jpg"/>
<h3>DINA</h3>
<p>Pão de brioche, filé de frango empanado, queijo cheddar, maionese verde, alface , tomate e cebola.</p>
<div class="preco">R$ 20,90</div>
<button class="btn btn-add" onclick="adicionar('DINA',20.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="GADEIA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/qLK7hWYs/GADEIA.jpg"/>
<h3>GADEIA</h3>
<p>Pão de hamburguer, carne artesanal 120 gr, maionese verde, queijo cheddar.</p>
<div class="preco">R$ 20,90</div>
<button class="btn btn-add" onclick="adicionar('GADEIA',20.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="GAROTINHO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/ymQ7sFZn/GAROTINHO.png"/>
<h3>GAROTINHO</h3>
<p>Pão de brioche, carne artesanal 120gr, molho cheddar cremoso e bacon.</p>
<div class="preco">R$ 22,90</div>
<button class="btn btn-add" onclick="adicionar('GAROTINHO',22.90)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="PÉZÃO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/0yTLwY4b/PEZAO.jpg"/>
<h3>PÉZÃO</h3>
<p>Pão de brioche dividido em 3 partes , 2 carnes artesanais 120gr , maionese, queijo cheddar, ovo, cebola, bacon, alface e tomate.</p>
<div class="preco">R$ 32,90</div>
<button class="btn btn-add" onclick="adicionar('PÉZÃO',32.90)">ADICIONAR</button>
</div>
</div>
</section>

<section class="categoria" id="combosArtesanais">
<div class="categoria-titulo">
🔥 COMBOS ARTESANAIS
</div>
<div class="produtos">
<div class="produto">
<img alt="COMBO SÓ LOVE" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/QR0388c/COMBO-S-LOVE.png"/>
<h3>ARTESANAL COMBO SÓ LOVE</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 90,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO SÓ LOVE',90.80)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO 5 ESTRELAS" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/5WM7335K/5-ESTRELAS.png"/>
<h3>ARTESANAL COMBO 5 ESTRELAS</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 70,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO 5 ESTRELAS',70.80)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO MAIS VENDIDO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/HLNHv9tt/COMBO-MAIS-VENDIDO-NOVO.png"/>
<h3>ARTESANAL COMBO MAIS VENDIDO</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 34,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO MAIS VENDIDO',34.80)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO DOCE" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/wNQqzkSf/COMBO-DOCE.png"/>
<h3>ARTESANAL COMBO DOCE</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 44,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO DOCE',44.80)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO GELADO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/cSLMFXtL/COMBO-GELADO.png"/>
<h3>ARTESANAL COMBO GELADO</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 52,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO GELADO',52.80)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="DATE COM NDBURGS" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/23CmpQqn/DATE-COM-ND-BURGS.png"/>
<h3>ARTESANAL DATE COM NDBURGS</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 91,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL DATE COM NDBURGS',91.80)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="COMBO MOTOCA ND" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/PvJqcwzb/MOTACA-ND.png"/>
<h3>ARTESANAL MOTOCA ND</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 41,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL MOTOCA ND',41.80)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="01 ND BURGS" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/Lz9JQx8f/01-NDBURGS.png"/>
<h3>ARTESANAL 01 ND BURGS</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 96,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL 01 ND BURGS',96.80)">ADICIONAR</button>
</div>
</div>
</section>

<section class="categoria" id="porcoes">
<div class="categoria-titulo">
🍟 PORÇÕES
</div>
<div class="produtos">
<div class="produto">
<img alt="BATATA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/JT71z1Y/BATATA.png"/>
<h3>BATATA</h3>
<p>Escolha o tamanho.</p>
<div class="preco">A partir de R$ 6,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('batata')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="BATATA COMPLETA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/v4QS3vVp/BATATA-COM-CHEDDAR-E-BACON.png"/>
<h3>BATATA COMPLETA</h3>
<p>Batata completa com cheddar e bacon.</p>
<div class="preco">A partir de R$ 12,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('batataCompleta')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="NUGGETS" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/39SVqYJP/NUGGETS.png"/>
<h3>NUGGETS</h3>
<p>Escolha o tamanho.</p>
<div class="preco">A partir de R$ 9,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('nuggets')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="ANEL DE CEBOLA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/Pz0W4RKj/ONION-RINGS.png"/>
<h3>ANEL DE CEBOLA</h3>
<p>Escolha o tamanho.</p>
<div class="preco">A partir de R$ 9,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('anelCebola')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="FRANGO FRITO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/Fb7LHQXC/FRANGO-PEDA-OS-EMPANADO.png"/>
<h3>FRANGO FRITO</h3>
<p>Escolha o tamanho.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('frangoFrito')">ESCOLHER</button>
</div>
</div>
</section>

<section class="categoria" id="pasteis">
<div class="categoria-titulo">
🥟 PASTÉIS
</div>
<div class="produtos">
<div class="produto">
<img alt="PASTÉIS" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/5x68nMyh/Chat-GPT-Image-25-06-2026-23-28-35.png"/>
<h3>PASTÉIS</h3>
<p>Escolha entre nossos sabores salgados e doces.</p>
<div class="preco">A partir de R$ 11,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('pasteis')">
ESCOLHER SABOR
</button>
</div>
</div>
</section>

<section class="categoria" id="sobremesas">
<div class="categoria-titulo">
🍨 AÇAÍS - MILKSHAKES E SOBREMESAS
</div>
<div class="produtos">
<div class="produto">
<img alt="AÇAÍ" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/Kxj5h5Km/Chat-GPT-Image-28-07-2026-18-32-28.png"/>
<h3>AÇAÍ</h3>
<p>Escolha o tamanho e seus acompanhamentos.</p>
<div class="preco">A partir de R$ 11,90</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('acai')">ESCOLHER</button>
</div>
<div class="produto">
<h3>CASADINHO</h3>
<p>Uma combinação cremosa de açaí e creme de cupuaçu.</p>
<div class="preco">A partir de R$ 11,90</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('casadinho')">ESCOLHER</button>
</div>
<div class="produto">
<h3>AÇAÍ TRUFFADO</h3>
<p>Açaí truffado especial.</p>
<div class="preco">A partir de R$ 26,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('truffado')">ESCOLHER</button>
</div>
<div class="produto">
<h3>TENTAÇÃO DE MORANGO</h3>
<p>Açaí com combinação especial de morango.</p>
<div class="preco">A partir de R$ 18,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('tentacao')">ESCOLHER</button>
</div>
<div class="produto">
<h3>CREME DE CUPUAÇU</h3>
<p>Escolha o tamanho e os mesmos acompanhamentos do açaí.</p>
<div class="preco">A partir de R$ 11,90</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('cupuaçu')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="MILKSHAKE OVOMALTINE" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/PZD2DtDq/MILKSHAKE-DE-OVOMALTINE.png"/>
<h3>OVOMALTINE</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkOvomaltine')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="MILKSHAKE OREO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/ZRbdHHVQ/oreo.jpg"/>
<h3>OREO</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkOreo')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="MILKSHAKE PAÇOCA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/NnyTc0wK/pa-oca.jpg"/>
<h3>PAÇOCA</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkPacoca')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="MILKSHAKE NESQUIK" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/1Ym81pQM/MILKSHAKE-MORANGO.png"/>
<h3>NESQUIK</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkNesquik')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="MILKSHAKE LEITE NINHO" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/NntDRB8q/leite-ninho.jpg"/>
<h3>LEITE NINHO</h3>
<p>Milkshake cremoso.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkNinho')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="MILKSHAKE DE AÇAÍ" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/WvRv23Y5/milk-a-ai.jpg"/>
<h3>DE AÇAÍ</h3>
<p>Milkshake de açaí.</p>
<div class="preco">A partir de R$ 15,00</div>
<button class="btn btn-add" onclick="abrirPersonalizacao('milkAcai')">ESCOLHER</button>
</div>
<div class="produto">
<img alt="KITKAT" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/ksyxPyr2/Chat-GPT-Image-26-06-2026-00-10-12.png"/>
<h3>KITKAT</h3>
<p>Doce especial.</p>
<div class="preco">R$ 7,00</div>
<button class="btn btn-add" onclick="adicionar('KITKAT',7)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="SURPRESA DE UVA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/9kC6V4gP/Chat-GPT-Image-5-09-2026-06-50-46.png"/>
<h3>SURPRESA DE UVA</h3>
<p>Sobremesa especial.</p>
<div class="preco">R$ 12,00</div>
<button class="btn btn-add" onclick="adicionar('SURPRESA DE UVA',12)">ADICIONAR</button>
</div>
</div>
</section>

<section class="categoria" id="bebidas">
<div class="categoria-titulo">
🥤 BEBIDAS
</div>
<div class="produtos">
<div class="produto">
<img alt="COCA COLA LATA 350ML" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/r2zDycx0/Chat-GPT-Image-4-09-2026-21-18-50.png"/>
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

<section class="categoria" id="adicionais">
<div class="categoria-titulo">
➕ ADICIONAIS
</div>
<div class="produtos">
<div class="produto">
<img alt="FATIA QUEIJO CHEDDAR EXTRA" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/ZRydT4hD/fatia-de-queijo.png"/>
<h3>FATIA QUEIJO CHEDDAR EXTRA</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('FATIA QUEIJO CHEDDAR EXTRA',3)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="HAMBURGUER EXTRA ARTESANAL" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/wZfS9rn1/hamburguer-artesanal.png"/>
<h3>HAMBURGUER EXTRA ARTESANAL</h3>
<p>Adicional.</p>
<div class="preco">R$ 9,00</div>
<button class="btn btn-add" onclick="adicionar('HAMBURGUER EXTRA ARTESANAL',9)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="HAMBURGUER EXTRA TRADICIONAL" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/TqhkXgRF/HAMBURGUER-TRADICIONAL.png"/>
<h3>HAMBURGUER EXTRA TRADICIONAL</h3>
<p>Adicional.</p>
<div class="preco">R$ 2,50</div>
<button class="btn btn-add" onclick="adicionar('HAMBURGUER EXTRA TRADICIONAL',2.50)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="BACON" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/6RxLhQBG/adicional-bacon.png"/>
<h3>BACON</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('BACON',3)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="POTINHO BARBECUE" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/n8KHqTMg/potinho-barbecue.png"/>
<h3>POTINHO BARBECUE</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO BARBECUE',3)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="POTINHO MAIONESE VERDE" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/DDCZpVLW/potinho-maionese-verde.png"/>
<h3>POTINHO MAIONESE VERDE</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO MAIONESE VERDE',3)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="POTINHO CHEDDAR" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/DHNQ0kwS/potinho-cheddar.png"/>
<h3>POTINHO CHEDDAR</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO CHEDDAR',3)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="POTINHO MAIONESE ARTESANAL" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/Y4DcTLwD/maionese-artesanal.png"/>
<h3>POTINHO MAIONESE ARTESANAL</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO MAIONESE ARTESANAL',3)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="ADICIONAL BACON" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/6RxLhQBG/adicional-bacon.png"/>
<h3>ADICIONAL BACON</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('ADICIONAL BACON',3)">ADICIONAR</button>
</div>
<div class="produto">
<img alt="ADICIONAL CHEDDAR" class="produto-imagem" decoding="async" loading="lazy" src="https://i.ibb.co/cHt8ZjS/adicional-molho-cheddar.png"/>
<h3>ADICIONAL CHEDDAR</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('ADICIONAL CHEDDAR',3)">ADICIONAR</button>
</div>
</div>
</section></main>
<div id="carrinhoFlutuante" class="carrinho-flutuante"><div class="carrinho-flutuante-info"><strong>SEU CARRINHO</strong><span id="contadorCarrinho">0 itens</span></div><strong id="totalCarrinhoFlutuante" class="carrinho-flutuante-total">R$ 0,00</strong><button type="button" class="btn-ver-carrinho" onclick="event.stopPropagation();abrirCarrinho()">ABRIR</button></div>
<div id="modalCarrinho" class="modal-carrinho" onclick="fecharCarrinho(event)"><div class="painel-carrinho" onclick="event.stopPropagation()"><div class="cabecalho-carrinho"><div><small style="color:var(--cyan);font-weight:1000">SEU PEDIDO</small><h2>Confira antes de concluir</h2></div><button class="fechar-carrinho" onclick="fecharCarrinho()">×</button></div><div id="itensCarrinhoModal"></div><div class="resumo-modal"><div class="linha"><span>Subtotal</span><strong id="subtotalCarrinhoModal">R$ 0,00</strong></div><div class="linha"><span>Taxa de entrega</span><strong id="taxaCarrinhoModal">R$ 0,00</strong></div><div class="linha nd-site-offer"><span>OFERTA DO SITE!</span><strong style="opacity:.2">•••</strong></div><div class="linha total-modal"><span>TOTAL</span><strong id="totalCarrinhoModal">R$ 0,00</strong></div></div><div class="sheet-actions"><button class="btn-continuar-comprando" onclick="irParaCheckout()">← CONTINUAR COMPRANDO</button><button class="btn-finalizar-pedido" onclick="irParaFinalizarPedido()">FINALIZAR PEDIDO →</button></div></div></div>
<div id="modalFinalizar" class="modal-finalizar" onclick="fecharModalFinalizar(event)"><div class="painel-finalizar" onclick="event.stopPropagation()"><div class="cabecalho-finalizar"><div><small style="color:var(--pink);font-weight:1000">ÚLTIMA ETAPA</small><h2>Finalize seu pedido</h2></div><button class="btn-fechar-finalizar" onclick="fecharModalFinalizar()">×</button></div><div class="nd-address-note"><b>📍 SEU ENDEREÇO</b><br>Confira o endereço salvo. Ele define a taxa de entrega de hoje e fica salvo para os próximos pedidos.</div><div class="checkout-grid"><div class="field"><label>NOME</label><input id="nomeModal" type="text" placeholder="Seu nome"></div><div class="field"><label>WHATSAPP</label><input id="telefoneModal" type="tel" placeholder="(11) 99999-9999"></div><div class="field"><label>TIPO DO PEDIDO</label><select id="tipoPedidoModal" onchange="alterarTipoPedidoModal()"><option value="ENTREGA">🏍️ DELIVERY</option><option value="RETIRADA">🏪 RETIRADA</option></select></div><div class="field"><label>RUA</label><select id="ruaModal" onchange="calcularTaxaModal()"><option value="">Selecione sua rua</option></select></div><div class="field"><label>NÚMERO</label><input id="numeroModal" type="text" placeholder="Número"></div><div class="field"><label>COMPLEMENTO</label><input id="complementoModal" type="text" placeholder="Casa, apto, bloco..."></div><div class="field checkout-full"><label>PAGAMENTO</label><select id="pagamentoModal" onchange="alterarPagamentoModal()"><option value="">Selecione</option><option value="PIX">PIX</option><option value="DINHEIRO">DINHEIRO</option><option value="CARTÃO">CARTÃO</option></select></div></div><div id="trocoAreaModal" style="display:none;margin-top:10px" class="field"><label>TROCO PARA QUANTO?</label><input id="trocoModal" type="number" step="0.01" placeholder="Ex.: 50"></div><div id="pixPanel" class="pix-panel"><div class="pix-title">PIX — PAGUE E VOLTE PARA ESTA TELA</div><div style="font-size:11px;color:#aeb2c5;margin-top:4px">Copie a chave, faça o pagamento no valor exato mostrado e <b style="color:#fff">volte para esta tela para concluir o pedido.</b></div><div class="pix-key">11963973846</div><button id="pixCopyBtn" type="button" class="pix-copy">📋 COPIAR CHAVE PIX</button><div class="pix-return"><b>IMPORTANTE:</b> copiar a chave não finaliza. Depois de pagar, volte aqui e toque em <b>JÁ PAGUEI • CONCLUIR PEDIDO</b>.</div></div><div class="field" style="margin-top:10px"><label>OBSERVAÇÃO</label><textarea id="observacaoModal" placeholder="Ex.: sem cebola, tocar campainha..."></textarea></div><div class="resumo-modal"><div class="linha"><span>Subtotal</span><strong id="subtotalFinalizarModal">R$ 0,00</strong></div><div class="linha"><span>Taxa</span><strong id="taxaFinalizarModal">R$ 0,00</strong></div><div class="linha nd-site-offer"><span>OFERTA DO SITE!</span><strong style="opacity:.2">•••</strong></div><div class="linha total-modal"><span>TOTAL</span><strong id="totalFinalizarModal">R$ 0,00</strong></div></div><button id="btnFinalizarNovo" class="btn-finalizar-modal" style="width:100%;margin-top:12px">JÁ PAGUEI • CONCLUIR PEDIDO →</button></div></div>
<div id="modalPersonalizacao" class="modal-personalizacao"><div class="modal-box"><div class="modal-topo"><h2 id="modalTitulo">Personalizar</h2><button class="modal-fechar" onclick="fecharPersonalizacao()">×</button></div><div id="modalConteudo"></div></div></div>
<div id="suggestionsModal" class="suggestions-modal" onclick="fecharSugestoes(event)"><div class="suggestions-panel" onclick="event.stopPropagation()"><div class="suggestions-head"><div><small style="color:var(--pink);font-weight:1000">SUGESTÃO</small><h2>Que tal levar mais um?</h2></div><button class="suggestions-close" onclick="fecharSugestoes()">×</button></div><div id="suggestionsGrid" class="suggestions-grid"></div><button class="btn-continuar-comprando" style="width:100%;margin-top:12px" onclick="fecharSugestoes()">CONTINUAR</button></div></div>
<div id="ndOrderSuccess" class="success"><div class="success-card"><div class="success-icon">✓</div><h2>PEDIDO <span>ENVIADO!</span></h2><p>Seu pedido foi enviado para a ND BURGS. Se escolheu PIX, ele deve ser pago antes de concluir. A previsão é de <b>40 a 50 minutinhos</b> após a confirmação do pedido.</p><button onclick="document.getElementById('ndOrderSuccess').classList.remove('show')">VOLTAR AO CARDÁPIO</button></div></div>
<footer><div class="footer-card"><div><strong>ND BURGS</strong><span>Pedido online • Delivery • Retirada</span></div><a class="footer-link" href="https://www.instagram.com/ndburgs/" target="_blank" rel="noopener">@ndburgs →</a></div></footer>
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

cupuaçu:{
titulo:"CREME DE CUPUAÇU",
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
  dadosIds.forEach(id=>{const el=document.getElementById(id); if(!el)return; const k='ndburgs_'+id; try{el.value|| (el.value=localStorage.getItem(k)||''); el.addEventListener('input',()=>localStorage.setItem(k,el.value));}catch(e){});
})();

</script>
<script>
(function(){
'use strict';
const OFFER=2, WA='5511963973846', PIX='11963973846';
const q=s=>document.querySelector(s), qa=s=>[...document.querySelectorAll(s)];
const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');
const cart=()=>Array.isArray(window.carrinho)?window.carrinho:[];
const sub=()=>cart().reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||1),0);
function fee(){const tipo=q('#tipoPedido')?.value||'ENTREGA';const rua=q('#rua')?.value||'';return tipo==='ENTREGA'?Number((window.taxas||{})[rua]||0):0}
function discount(){const base=sub()+fee();return cart().length?Math.min(OFFER,base):0}
function total(){return Math.max(0,sub()+fee()-discount())}
function sync(){
 const s=sub(),f=fee(),d=discount(),t=Math.max(0,s+f-d),qty=cart().reduce((a,i)=>a+(Number(i.quantidade)||1),0);
 [['#subtotalCarrinhoModal',s],['#taxaCarrinhoModal',f],['#totalCarrinhoModal',t],['#subtotalFinalizarModal',s],['#taxaFinalizarModal',f],['#totalFinalizarModal',t]].forEach(([id,v])=>{const e=q(id);if(e)e.textContent=money(v)});
 const bar=q('#carrinhoFlutuante');if(bar)bar.classList.toggle('ativo',cart().length>0);if(q('#contadorCarrinho'))q('#contadorCarrinho').textContent=qty+(qty===1?' item':' itens');if(q('#totalCarrinhoFlutuante'))q('#totalCarrinhoFlutuante').textContent=money(t);
 const rua=q('#rua')?.value||'',num=q('#numero')?.value.trim()||'';if(q('#enderecoSalvoTexto'))q('#enderecoSalvoTexto').textContent=rua?(rua+(num?', Nº '+num:'')):'Endereço ainda não selecionado';if(q('#taxaEndTexto'))q('#taxaEndTexto').textContent=rua?('Taxa hoje: '+money(f)):'Selecione sua rua para calcular a taxa';
}
function saveAddress(){try{localStorage.setItem('nd_nova_rua',q('#rua')?.value||'');localStorage.setItem('nd_nova_num',q('#numero')?.value||'')}catch(e){}
function restoreAddress(){try{const rua=localStorage.getItem('nd_nova_rua')||localStorage.getItem('nd17_rua')||'';const num=localStorage.getItem('nd_nova_num')||localStorage.getItem('nd17_numero')||'';if(rua&&q('#rua')&&[...q('#rua').options].some(o=>o.value===rua))q('#rua').value=rua;if(num&&q('#numero'))q('#numero').value=num}catch(e){}
function addressSearch(){const inp=q('#ruaBusca'),sel=q('#rua');if(!inp||!sel||inp.__b)return;inp.__b=1;inp.addEventListener('input',()=>{const t=inp.value.toLocaleLowerCase('pt-BR');[...sel.options].forEach((o,i)=>{o.hidden=i>0&&t&&!o.textContent.toLocaleLowerCase('pt-BR').includes(t)})})}
function pix(){const sel=q('#pagamentoModal'),panel=q('#pixPanel'),btn=q('#pixCopyBtn'),finish=q('#btnFinalizarNovo');if(!sel||!panel)return;const on=sel.value==='PIX';panel.classList.toggle('show',on);if(finish)finish.textContent=on?'JÁ PAGUEI • CONCLUIR PEDIDO →':'CONCLUIR PEDIDO E ENVIAR →';if(btn&&!btn.__b){btn.__b=1;btn.onclick=async()=>{try{await navigator.clipboard.writeText(PIX)}catch(e){const ta=document.createElement('textarea');ta.value=PIX;document.body.appendChild(ta);ta.select();document.execCommand('copy');ta.remove()}btn.textContent='✅ CHAVE COPIADA!';setTimeout(()=>btn.textContent='📋 COPIAR CHAVE PIX',1800)}}
function searchProducts(){const inp=q('#buscaProdutos');if(!inp||inp.__b)return;inp.__b=1;inp.addEventListener('input',()=>{const term=inp.value.trim().toLocaleLowerCase('pt-BR');let vis=0;qa('.produto').forEach(c=>{const ok=!term||c.innerText.toLocaleLowerCase('pt-BR').includes(term);c.classList.toggle('search-hidden',!ok);if(ok)vis++});if(q('#contadorBusca'))q('#contadorBusca').textContent=term?vis+' produto'+(vis===1?'':'s'):'';if(q('#semResultados'))q('#semResultados').style.display=term&&vis===0?'block':'none'})}
function patch(){
 const origUpd=window.atualizarCarrinho;if(typeof origUpd==='function'&&!origUpd.__nova){const f=origUpd;window.atualizarCarrinho=function(){f.apply(this,arguments);setTimeout(sync,0)};window.atualizarCarrinho.__nova=1}
 const origTax=window.calcularTaxa;if(typeof origTax==='function'&&!origTax.__nova){const f=origTax;window.calcularTaxa=function(){const r=f.apply(this,arguments);setTimeout(sync,0);return r};window.calcularTaxa.__nova=1}
 const origModalTax=window.calcularTaxaModal;if(typeof origModalTax==='function'&&!origModalTax.__nova){const f=origModalTax;window.calcularTaxaModal=function(){const r=f.apply(this,arguments);setTimeout(sync,0);return r};window.calcularTaxaModal.__nova=1}
 const origFinish=window.finalizarPedidoModal;if(typeof origFinish==='function'&&!origFinish.__nova){window.finalizarPedidoModal=function(){
   const c=cart();if(!c.length)return alert('Adicione pelo menos um produto ao carrinho.');
   const nome=q('#nomeModal')?.value.trim()||'', tel=(q('#telefoneModal')?.value||'').replace(/\D/g,'');const pay=q('#pagamentoModal')?.value||'';const tipo=q('#tipoPedidoModal')?.value||'ENTREGA';const rua=q('#ruaModal')?.value||'';const num=q('#numeroModal')?.value.trim()||'';
   if(!nome)return alert('Digite seu nome.');if(tel.length<10||tel.length>11)return alert('Digite um WhatsApp válido com DDD.');if(tipo==='ENTREGA'&&(!rua||!num))return alert('Complete seu endereço.');if(!pay)return alert('Escolha uma forma de pagamento.');
   const s=sub(),f=tipo==='ENTREGA'?Number((window.taxas||{})[rua]||0):0,d=Math.min(OFFER,s+f),t=Math.max(0,s+f-d),comp=q('#complementoModal')?.value.trim()||'',obs=q('#observacaoModal')?.value.trim()||'',troco=q('#trocoModal')?.value||'';
   const lines=['NOVO PEDIDO - ND BURGS','CLIENTE: '+(q('#nomeModal')?.value.trim()||''),'WHATSAPP: '+(q('#telefoneModal')?.value.trim()||''),'TIPO: '+(tipo==='ENTREGA'?'DELIVERY':'RETIRADA')];
   if(tipo==='ENTREGA'){lines.push('ENDEREÇO: '+rua+', Nº '+num);if(comp)lines.push('COMPLEMENTO: '+comp)}
   lines.push('','ITENS DO PEDIDO');c.forEach(i=>{const qty=Number(i.quantidade)||1;lines.push(qty+'x '+i.nome+' - '+money((Number(i.preco)||0)*qty));if(Array.isArray(i.detalhes)&&i.detalhes.length)lines.push('  '+i.detalhes.join(', '))});lines.push('','SUBTOTAL: '+money(s),'TAXA DE ENTREGA: '+money(f),'OFERTA DO SITE!','TOTAL DO PEDIDO: '+money(t),'PAGAMENTO: '+pay);if(pay==='DINHEIRO'&&troco)lines.push('TROCO PARA: '+money(Number(troco)||0));if(obs)lines.push('OBSERVAÇÃO: '+obs);lines.push('','ND BURGS');
   try{localStorage.setItem('ndburgs_ultimo_pedido',JSON.stringify(c));localStorage.setItem('ndburgs_pedido_enviado_at',String(Date.now()));}catch(e){}
   try{if(Array.isArray(window.carrinho))window.carrinho.length=0;localStorage.removeItem('carrinho');localStorage.removeItem('ndburgs_carrinho');}catch(e){}
   const url='https://wa.me/'+WA+'?text='+encodeURIComponent(lines.join('\n'));window.open(url,'_blank');q('#modalFinalizar')?.classList.remove('ativo');document.body.style.overflow='';q('#ndOrderSuccess')?.classList.add('show');sync();
 };window.finalizarPedidoModal.__nova=1;}
 const btn=q('#btnFinalizarNovo');if(btn&&!btn.__b){btn.__b=1;btn.onclick=()=>window.finalizarPedidoModal()}
}
function init(){
 searchProducts();addressSearch();restoreAddress();
 const rua=q('#rua'),num=q('#numero');if(rua&&!rua.__b){rua.__b=1;rua.addEventListener('change',()=>{saveAddress();sync()})}if(num&&!num.__b){num.__b=1;num.addEventListener('input',()=>{saveAddress();sync()})}
 const pay=q('#pagamentoModal');if(pay&&!pay.__b){pay.__b=1;pay.addEventListener('change',pix)}
 ['nomeModal','telefoneModal','numeroModal','complementoModal','observacaoModal'].forEach(id=>{const e=q('#'+id);if(!e)return;try{e.value|| (e.value=localStorage.getItem('ndburgs_'+id)||'')}catch(_ ){}e.addEventListener('input',()=>{try{localStorage.setItem('ndburgs_'+id,e.value)}catch(_ ){}})});
 patch();pix();sync();
 const mo=new MutationObserver(()=>{patch();pix();sync()});mo.observe(document.body,{childList:true,subtree:true});
}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init);else init();
setTimeout(()=>{patch();pix();sync()},700);
})();
</script>
</body></html>
