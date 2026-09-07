<!DOCTYPE html>
<html lang="pt-BR">
<head>
<!-- ND BURGS: controle de versão para evitar conteúdo antigo em cache -->
<meta content="20260907-R29" name="nd-site-version"/>

<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<title>ND BURGS | Faça seu pedido</title>


<!-- ND BURGS REDESIGN 2026 -->



<style id="nd-rodada-4-checkout">
/* =====================================================
   ND BURGS — RODADA 4
   MOBILE + CHECKOUT + CONVERSÃO
   ===================================================== */
.modal-finalizar{padding:0!important;align-items:flex-end!important;background:rgba(0,0,0,.78)!important;backdrop-filter:blur(12px)!important}
.painel-finalizar{width:min(100%,680px)!important;max-height:min(94vh,900px)!important;overflow-y:auto!important;padding:0!important;border:1px solid rgba(229,9,20,.65)!important;border-radius:24px 24px 0 0!important;background:linear-gradient(180deg,#111114 0%,#080809 100%)!important;box-shadow:0 -25px 90px rgba(0,0,0,.75)!important;overscroll-behavior:contain}
.painel-finalizar .cabecalho-finalizar{position:sticky;top:0;z-index:5;margin:0!important;padding:17px 18px 14px!important;background:rgba(12,12,14,.96)!important;border-bottom:1px solid #25252a!important;backdrop-filter:blur(14px)!important}
.painel-finalizar .cabecalho-finalizar h2{font-size:24px!important;letter-spacing:-.6px!important}
.btn-fechar-finalizar{width:42px!important;height:42px!important;border-radius:12px!important;background:#1d1d21!important;border:1px solid #34343a!important;color:#fff!important;font-size:25px!important;transition:.18s ease!important}
.btn-fechar-finalizar:hover{background:#e50914!important;border-color:#e50914!important;transform:rotate(3deg) scale(1.03)}
.nd-v4-stepbar{position:sticky;top:73px;z-index:4;display:grid!important;grid-template-columns:repeat(4,1fr);gap:6px!important;padding:10px 16px!important;background:rgba(9,9,10,.97)!important;border-bottom:1px solid #202024!important;backdrop-filter:blur(12px)!important}
.nd-v4-step{min-width:0!important;padding:9px 5px!important;border:1px solid #29292f!important;border-radius:9px!important;font-size:9px!important;letter-spacing:.3px!important;text-align:center!important;white-space:nowrap!important;color:#777!important;background:#111115!important;transition:.2s ease!important}
.nd-v4-step.active{color:#fff!important;border-color:#e50914!important;background:linear-gradient(180deg,#2a0d0f,#160a0b)!important;box-shadow:inset 0 0 0 1px rgba(229,9,20,.12),0 5px 18px rgba(229,9,20,.08)!important}
.nd-v4-step.done{color:#aaa!important;border-color:#3a3a40!important}
.nd-v4-step-content{padding:18px!important}
.nd-v4-step-content>label{display:block;margin:12px 0 7px!important;color:#eee!important;font-size:12px!important;font-weight:900!important}
.nd-v4-step-content>label:first-child{margin-top:0!important}
.nd-v4-step-content input,.nd-v4-step-content select,.nd-v4-step-content textarea{width:100%!important;box-sizing:border-box!important;min-height:48px!important;padding:13px 14px!important;border-radius:12px!important;background:#0c0c0f!important;border:1px solid #2c2c33!important;color:#fff!important;font-size:15px!important}
.nd-v4-step-content textarea{min-height:105px!important;resize:vertical!important}
.nd-v4-step-content input:focus,.nd-v4-step-content select:focus,.nd-v4-step-content textarea:focus{border-color:#e50914!important;box-shadow:0 0 0 3px rgba(229,9,20,.10)!important}
.nd-v4-delivery-estimate{margin-top:12px!important;padding:11px 12px!important;border:1px solid #28282e!important;border-radius:11px!important;background:#101014!important;color:#aaa!important;font-size:11px!important;line-height:1.5!important}
.nd-v4-delivery-estimate b{color:#ddd!important}
.nd-v4-payment-grid{gap:9px!important}
.nd-v4-pay{min-height:66px!important;border:1px solid #303037!important;background:#111115!important;transition:.18s ease!important}
.nd-v4-pay:hover{border-color:#555!important;transform:translateY(-1px)}
.nd-v4-pay.active{border-color:#e50914!important;background:linear-gradient(180deg,#2a0d0f,#160a0b)!important;color:#fff!important;box-shadow:0 8px 22px rgba(229,9,20,.10)!important}
.nd-v4-next{min-height:52px!important;margin-top:14px!important;background:linear-gradient(135deg,#e50914,#ff3038)!important;color:#fff!important;border-radius:13px!important;font-size:14px!important;letter-spacing:.2px!important;box-shadow:0 10px 26px rgba(229,9,20,.20)!important;transition:.18s ease!important}
.nd-v4-next:hover{filter:brightness(1.08);transform:translateY(-1px)}
.nd-v4-back{min-height:45px!important;margin-top:8px!important;border-radius:12px!important;background:#121216!important;border-color:#2b2b31!important;color:#aaa!important}
.nd-v4-summary{border-color:#29292f!important;background:linear-gradient(145deg,#111115,#0b0b0e)!important}
.nd-v4-summary-title{color:#888!important}
.nd-v4-final-total{color:#fff!important;font-size:30px!important}
#ndV4Total{color:#ff3038!important}
/* barra de progresso visual do checkout */
.nd-v4-stepbar:after{content:"";position:absolute;left:16px;right:16px;bottom:0;height:2px;background:linear-gradient(90deg,#e50914 25%,transparent 25%);opacity:.65;pointer-events:none}
/* evita zoom automático do iOS */
@media(max-width:760px){
 .modal-finalizar{padding:0!important}
 .painel-finalizar{max-height:96vh!important;border-radius:20px 20px 0 0!important}
 .painel-finalizar .cabecalho-finalizar{padding:14px 14px 12px!important}
 .painel-finalizar .cabecalho-finalizar h2{font-size:21px!important}
 .nd-v4-stepbar{top:67px;padding:8px 10px!important;gap:5px!important}
 .nd-v4-step{padding:8px 3px!important;font-size:8px!important}
 .nd-v4-step-content{padding:15px 13px 22px!important}
 .nd-v4-payment-grid{grid-template-columns:repeat(3,1fr)!important}
 .nd-v4-pay{min-height:68px!important;font-size:12px!important}
 .nd-v4-final-total{font-size:27px!important}
 .nd-v4-next{min-height:54px!important}
}
@media(max-width:420px){
 .nd-v4-payment-grid{grid-template-columns:1fr!important}
 .nd-v4-step{font-size:7.5px!important}
}
@media(prefers-reduced-motion:reduce){.btn-fechar-finalizar,.nd-v4-pay,.nd-v4-next{transition:none!important}}
</style>


<!-- ND BURGS R10 - MELHORIAS GERAIS -->


<style id="nd-r19-reviews">
#ndR19Reviews{
  max-width:1100px;margin:24px auto;padding:20px;
}
#ndR19Reviews .r19-head{
  display:flex;align-items:center;justify-content:space-between;gap:12px;
  flex-wrap:wrap;margin-bottom:15px
}
#ndR19Reviews h2{margin:0;font-size:25px;font-weight:1000}
#ndR19Reviews .r19-rating{
  display:flex;align-items:center;gap:9px;
  padding:9px 13px;border-radius:14px;
  background:rgba(255,210,26,.10);
  border:1px solid rgba(255,210,26,.24)
}
#ndR19Reviews .r19-rating strong{font-size:24px}
#ndR19Reviews .r19-rating span{font-size:16px;letter-spacing:1px}
#ndR19Reviews .r19-grid{
  display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:12px
}
#ndR19Reviews .r19-card{
  padding:17px;border-radius:17px;
  background:rgba(255,255,255,.055);
  border:1px solid rgba(255,255,255,.09);
  min-height:125px
}
#ndR19Reviews .r19-stars{font-size:17px;letter-spacing:1px}
#ndR19Reviews .r19-card p{
  margin:9px 0 8px;font-size:14px;line-height:1.45;font-weight:750
}
#ndR19Reviews .r19-card small{opacity:.62;font-size:11px}
#ndR19Reviews .r19-source{
  display:inline-block;margin-top:9px;padding:4px 8px;border-radius:999px;
  font-size:9px;font-weight:1000;background:rgba(255,255,255,.08)
}
@media(max-width:700px){
  #ndR19Reviews{padding:16px}
  #ndR19Reviews .r19-grid{grid-template-columns:1fr}
}
</style>

<style>
:root{--nd-gold:#f5c400;--nd-gold2:#ffd92b;--nd-bg:#080808;--nd-card:#121212;--nd-border:#292929;--nd-green:#25d366;--nd-red:#ff4545}
body{background:radial-gradient(circle at 50% -10%,rgba(245,196,0,.08),transparent 32%),#080808}
::selection{background:var(--nd-gold);color:#000}
button,input,select,textarea{font-family:inherit}
button:focus-visible,input:focus-visible,select:focus-visible,textarea:focus-visible{outline:2px solid var(--nd-gold);outline-offset:2px}
.produto{position:relative}
.produto .btn-add{transition:transform .15s,filter .15s}
.produto .btn-add:active{transform:scale(.97)}
.nd-badge{position:absolute;top:10px;left:10px;z-index:2;background:var(--nd-gold);color:#000;border-radius:999px;padding:5px 9px;font-size:11px;font-weight:900;box-shadow:0 5px 16px #0008}
.nd-fav{position:absolute;top:10px;right:10px;z-index:3;width:36px;height:36px;border:1px solid #444;border-radius:50%;background:#080808d9;color:#fff;font-size:19px;cursor:pointer;display:grid;place-items:center}
.nd-fav.ativo{color:#ff4d6d;border-color:#ff4d6d;background:#2a1018}
.nd-topbar{position:sticky;top:74px;z-index:800;background:#0b0b0bee;backdrop-filter:blur(14px);border-bottom:1px solid #252525;padding:8px 12px}
.nd-topbar-inner{max-width:1100px;margin:auto;display:flex;gap:8px;overflow:auto;scrollbar-width:none}
.nd-topbar-inner::-webkit-scrollbar{display:none}
.nd-cat-btn{white-space:nowrap;border:1px solid #333;background:#151515;color:#ddd;border-radius:999px;padding:8px 12px;font-weight:800;font-size:12px;cursor:pointer}
.nd-cat-btn.ativo{background:var(--nd-gold);border-color:var(--nd-gold);color:#000}
.nd-toast{position:fixed;left:50%;bottom:94px;transform:translate(-50%,20px);background:#151515;border:1px solid var(--nd-gold);color:#fff;padding:12px 16px;border-radius:12px;box-shadow:0 10px 35px #000b;z-index:100500;opacity:0;pointer-events:none;transition:.25s;max-width:calc(100% - 30px);text-align:center;font-weight:700;font-size:13px}
.nd-toast.show{opacity:1;transform:translate(-50%,0)}
.nd-backtop{position:fixed;right:15px;bottom:92px;width:42px;height:42px;border:1px solid #444;background:#151515;color:#fff;border-radius:50%;z-index:8800;display:none;cursor:pointer;box-shadow:0 8px 25px #0008}
.nd-backtop.show{display:block}
.nd-cart-progress{margin:12px 0;padding:10px 12px;background:#0d0d0d;border:1px solid #292929;border-radius:10px;font-size:12px;color:#bbb}
.nd-cart-progress b{color:var(--nd-gold)}
.nd-progress-track{height:6px;background:#292929;border-radius:99px;overflow:hidden;margin-top:7px}
.nd-progress-bar{height:100%;width:0;background:var(--nd-gold);transition:.3s}
.nd-empty-search{display:none;text-align:center;padding:35px 15px;color:#aaa;border:1px dashed #444;border-radius:14px;margin:15px 0}
.nd-empty-search strong{display:block;color:#fff;font-size:17px;margin-bottom:6px}
.nd-order-steps{display:flex;align-items:center;justify-content:center;gap:7px;margin:10px 0 16px;font-size:11px;color:#777}
.nd-step{padding:7px 9px;border-radius:999px;border:1px solid #333;background:#111}
.nd-step.active{border-color:var(--nd-gold);color:var(--nd-gold)}
.nd-step-line{height:1px;width:22px;background:#333}
.nd-delivery-estimate{margin:10px 0;padding:12px;border-radius:10px;background:#101010;border:1px solid #2a2a2a;color:#ccc;font-size:13px}
.nd-delivery-estimate b{color:var(--nd-gold)}
@media(max-width:700px){.nd-topbar{top:65px}.nd-order-steps{font-size:9px}.nd-step{padding:6px 7px}.nd-step-line{width:10px}.nd-toast{bottom:125px}}
</style><style id="nd-v4">
:root{
 --nd-orange:#ff6a00;
 --nd-orange2:#ff8a1f;
 --nd-orange3:#ffb35c;
 --nd-black:#050505;
 --nd-black2:#0a0a0a;
 --nd-card:#101010;
 --nd-card2:#151515;
 --nd-line:#242424;
 --nd-text:#f2f2f2;
 --nd-muted:#999;
}
html,body{background:#050505!important;color:var(--nd-text)!important}
body{background:#050505!important}
body *{scrollbar-color:#333 #050505}
header{background:#050505!important;border-bottom:2px solid var(--nd-orange)!important}
header .logo{max-height:72px}
.horarios{background:#070707!important}
.horarios-box,.produto,.carrinho,.formulario,.painel-carrinho,.painel-finalizar,.suggestions-panel{background:#0d0d0d!important;color:#f2f2f2!important;border-color:#252525!important}
input,select,textarea{background:#111!important;color:#fff!important;border:1px solid #303030!important}
input::placeholder,textarea::placeholder{color:#777!important}
select option{background:#111;color:#fff}
.container{max-width:1180px!important}
.container>h1{font-size:clamp(28px,5vw,52px)!important;letter-spacing:-1px!important;color:#fff!important}
.produtos,.grid-produtos{gap:16px!important}
.produto{border:1px solid #252525!important;border-radius:18px!important;overflow:hidden!important;box-shadow:0 12px 35px rgba(0,0,0,.28)!important;transition:transform .22s,border-color .22s,box-shadow .22s!important}
.produto:hover{transform:translateY(-4px)!important;border-color:#ff6a0066!important;box-shadow:0 18px 45px rgba(0,0,0,.5),0 0 0 1px #ff6a0018!important}
.produto img{width:100%!important;aspect-ratio:1/1!important;object-fit:cover!important;display:block!important;background:#090909!important}
.produto h3{font-size:clamp(16px,2.2vw,21px)!important;color:#fff!important}
.produto p{color:#999!important}
.preco{font-size:clamp(22px,3vw,30px)!important;font-weight:1000!important;color:var(--nd-orange2)!important;text-shadow:0 0 18px rgba(255,106,0,.15)!important}
.btn-add,.btn-finalizar-pedido,.btn-finalizar-modal{background:linear-gradient(135deg,#ff6a00,#ff8a1f)!important;color:#050505!important;border:0!important;font-weight:1000!important;box-shadow:0 8px 24px rgba(255,106,0,.2)!important}
.btn-add:hover,.btn-finalizar-pedido:hover,.btn-finalizar-modal:hover{filter:brightness(1.1)!important}
.btn-whatsapp{background:linear-gradient(135deg,#ff6a00,#ff8a1f)!important;color:#050505!important}
.btn-continuar-comprando{background:#151515!important;color:#fff!important;border:1px solid #333!important}
.categoria-btn,.nd-cat-btn{background:#111!important;color:#ddd!important;border-color:#2b2b2b!important}
.categoria-btn:hover,.nd-cat-btn:hover,.nd-cat-btn.ativo{background:var(--nd-orange)!important;color:#050505!important;border-color:var(--nd-orange)!important}
.modern-search{background:#0e0e0e!important;border-color:#2c2c2c!important}
.modern-search input{background:transparent!important;border:0!important}
.carrinho-flutuante{background:#101010!important;border-top:2px solid var(--nd-orange)!important;box-shadow:0 -12px 40px #000!important}
.carrinho-flutuante-total,#totalCarrinhoFlutuante{color:var(--nd-orange2)!important}
.status-aberto{background:#101010!important;border-color:var(--nd-orange)!important;color:var(--nd-orange2)!important}
.status-fechado{background:#101010!important}
.resumo,.resumo-modal{background:#0a0a0a!important;border-color:#252525!important}
.total strong,.total-modal strong,#total,#totalCarrinhoModal,#totalFinalizarModal{color:var(--nd-orange2)!important}
.aviso-taxa{background:#101010!important;border-color:var(--nd-orange)!important;color:#ddd!important}
.rodape-instagram,.rodape-final{background:#050505!important;color:#aaa!important;border-color:#222!important}
.nd-v4-hero{position:relative;min-height:520px;max-width:1180px;margin:0 auto;padding:58px 28px 46px;display:grid;grid-template-columns:1.05fr .95fr;align-items:center;overflow:hidden;background:#050505}
.nd-v4-hero-glow{position:absolute;width:520px;height:520px;border-radius:50%;right:-100px;top:-130px;background:radial-gradient(circle,rgba(255,106,0,.18),transparent 66%);pointer-events:none}
.nd-v4-hero-content{position:relative;z-index:2;max-width:650px}
.nd-v4-kicker{display:inline-flex;padding:7px 11px;border:1px solid #ff6a0055;border-radius:999px;color:var(--nd-orange2);font-size:12px;font-weight:1000;letter-spacing:1px;background:#ff6a000c}
.nd-v4-hero h1{font-size:clamp(44px,7vw,82px);line-height:.9;margin:18px 0;color:#fff;letter-spacing:-4px}
.nd-v4-hero h1 em{font-style:normal;color:var(--nd-orange)}
.nd-v4-hero p{max-width:570px;color:#a8a8a8;font-size:17px;line-height:1.55;margin-bottom:24px}
.nd-v4-hero-actions{display:flex;gap:10px;flex-wrap:wrap}
.nd-v4-primary,.nd-v4-secondary{border-radius:12px;padding:15px 20px;font-weight:1000;cursor:pointer}
.nd-v4-primary{background:var(--nd-orange);color:#050505;border:0;box-shadow:0 12px 30px #ff6a0033}
.nd-v4-primary span{margin-left:18px}
.nd-v4-secondary{background:#111;color:#fff;border:1px solid #333}
.nd-v4-trustline{display:flex;gap:18px;flex-wrap:wrap;margin-top:25px;color:#777;font-size:11px;font-weight:800}
.nd-v4-trustline span{display:inline-flex;align-items:center;gap:5px}
.nd-v4-hero-art{position:relative;min-height:390px;display:grid;place-items:center}
.nd-v4-art-ring{position:absolute;width:340px;height:340px;border:1px solid #ff6a0040;border-radius:50%;box-shadow:0 0 100px #ff6a0018}
.nd-v4-art-burger{font-size:180px;filter:drop-shadow(0 25px 30px #000);position:relative;z-index:2}
.nd-v4-art-price{position:absolute;right:6%;bottom:8%;z-index:3;background:#111;border:1px solid #ff6a0080;border-radius:14px;padding:12px 17px;color:#999;font-size:11px;font-weight:900;box-shadow:0 12px 30px #000}
.nd-v4-art-price strong{color:var(--nd-orange);font-size:18px}
.nd-v4-checkout{background:#0a0a0a!important;border:1px solid #262626!important}
.nd-v4-stepbar{display:grid;grid-template-columns:repeat(4,1fr);gap:6px;margin:0 0 18px}
.nd-v4-step{padding:9px 5px;text-align:center;border:1px solid #292929;border-radius:10px;background:#111;color:#666;font-size:10px;font-weight:900}
.nd-v4-step.active{border-color:var(--nd-orange);color:var(--nd-orange);background:#ff6a000d}
.nd-v4-step.done{color:#aaa;border-color:#444}
.nd-v4-step-content{display:none}
.nd-v4-step-content.active{display:block}
.nd-v4-next,.nd-v4-back{width:100%;padding:14px;border-radius:12px;font-weight:1000;cursor:pointer}
.nd-v4-next{background:var(--nd-orange);color:#050505;border:0}
.nd-v4-back{background:#111;color:#fff;border:1px solid #333;margin-top:8px}
.nd-v4-payment-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:8px}
.nd-v4-pay{padding:14px 8px;background:#111;border:1px solid #2b2b2b;border-radius:12px;color:#ddd;text-align:center;cursor:pointer;font-weight:900}
.nd-v4-pay.active{border-color:var(--nd-orange);background:#ff6a0010;color:var(--nd-orange)}
.nd-v4-summary{background:#0d0d0d;border:1px solid #292929;border-radius:14px;padding:13px;margin-bottom:14px}
.nd-v4-summary-title{font-size:11px;color:#888;text-transform:uppercase;font-weight:900;margin-bottom:8px}
.nd-v4-final-total{font-size:30px;font-weight:1000;color:var(--nd-orange);text-align:right}
.nd-v4-note{font-size:11px;color:#777;line-height:1.45;margin-top:10px}
@media(max-width:760px){
 .nd-v4-hero{min-height:auto;padding:34px 18px 28px;display:block}
 .nd-v4-hero h1{font-size:50px;letter-spacing:-3px}
 .nd-v4-hero p{font-size:14px}
 .nd-v4-hero-art{min-height:250px;margin-top:8px}
 .nd-v4-art-ring{width:220px;height:220px}
 .nd-v4-art-burger{font-size:115px}
 .nd-v4-art-price{right:12%;bottom:0}
 .produto{border-radius:14px!important}
 .produto img{aspect-ratio:1/1!important}
 .preco{font-size:24px!important}
 .btn-add{min-height:48px!important;font-size:13px!important}
 .nd-v4-payment-grid{grid-template-columns:1fr}
}
</style><style id="nd-final-layout">
/* =====================================================
   ND BURGS — NOVO LAYOUT FUTURISTA / PRETO + LARANJA
   Camada visual e funcional sobre o código existente.
   ===================================================== */
:root{
 --fx-orange:#ff6500;--fx-orange2:#ff8b1f;--fx-orange3:#ffb45c;
 --fx-black:#030303;--fx-panel:#0b0b0d;--fx-panel2:#111114;--fx-line:#25252a;
 --fx-text:#f5f5f5;--fx-muted:#92929a;--fx-green:#25d366;--fx-red:#ff3b30;
}
html{scroll-behavior:smooth;background:var(--fx-black)!important}
body{background:
 radial-gradient(circle at 50% -10%,rgba(255,101,0,.12),transparent 32%),
 radial-gradient(circle at 100% 30%,rgba(255,101,0,.05),transparent 30%),
 #030303!important;color:var(--fx-text)!important;padding-bottom:95px!important}
header{position:relative!important;top:auto!important;padding:20px 16px 16px!important;background:rgba(3,3,3,.96)!important;border-bottom:1px solid rgba(255,101,0,.35)!important;box-shadow:0 15px 45px rgba(0,0,0,.55)!important}
header .logo{width:min(245px,72vw)!important;max-width:none!important;height:auto!important;max-height:none!important;filter:drop-shadow(0 0 24px rgba(255,101,0,.25))!important}
/* O hero antigo não participa do novo layout */
.nd-v4-hero{display:none!important}
.container>h1{display:none!important}
.horarios{max-width:1180px!important;margin:12px auto!important;padding:0 12px!important}
.horarios-box{display:flex!important;align-items:center!important;justify-content:space-between!important;gap:12px!important;padding:12px 16px!important;border:1px solid var(--fx-line)!important;border-left:3px solid var(--fx-orange)!important;background:linear-gradient(135deg,#0e0e10,#080809)!important;border-radius:14px!important;box-shadow:none!important}
.horarios-titulo{color:var(--fx-orange2)!important;font-size:12px!important;margin:0!important;white-space:nowrap}
.horarios-linha{font-size:11px!important;color:#aaa!important;text-align:right!important;line-height:1.45!important}
.status-aberto,.status-fechado{font-size:11px!important;margin:0!important;padding:5px 9px!important;border-radius:999px!important;white-space:nowrap!important;background:#101010!important;border-color:var(--fx-orange)!important;color:var(--fx-orange2)!important}
.container{max-width:1240px!important;padding:10px 14px 40px!important}
/* NOVA CABEÇA DO CARDÁPIO */
#ndFxIntro{display:block;margin:18px 0 14px;padding:18px;border:1px solid var(--fx-line);border-radius:20px;background:linear-gradient(135deg,#101012,#070708);position:relative;overflow:hidden}
#ndFxIntro:after{content:"";position:absolute;right:-100px;top:-100px;width:260px;height:260px;border-radius:50%;background:radial-gradient(circle,rgba(255,101,0,.16),transparent 65%);pointer-events:none}
.ndFx-kicker{font-size:10px;font-weight:900;letter-spacing:2px;color:var(--fx-orange2)}
.ndFx-title{font-size:clamp(28px,5vw,48px);line-height:.95;margin:8px 0;color:#fff;font-weight:1000;letter-spacing:-2px}
.ndFx-title span{color:var(--fx-orange)}
.ndFx-sub{color:#8e8e95;font-size:13px;max-width:620px;line-height:1.5}
.ndFx-actions{display:flex;gap:8px;margin-top:14px;flex-wrap:wrap}
.ndFx-action{border:1px solid #2c2c31;background:#111113;color:#fff;border-radius:11px;padding:10px 13px;font-size:11px;font-weight:900;cursor:pointer}
.ndFx-action.primary{background:var(--fx-orange);border-color:var(--fx-orange);color:#050505}
/* busca + categorias */
.modern-search{position:sticky!important;top:0!important;z-index:1500!important;margin:10px 0 8px!important;background:rgba(8,8,9,.94)!important;border:1px solid #242429!important;border-radius:15px!important;padding:8px!important;box-shadow:0 12px 35px rgba(0,0,0,.5)!important;backdrop-filter:blur(18px)!important}
.modern-search input{padding:13px!important;border-radius:10px!important;background:#050506!important;color:#fff!important}
.categoria-menu{position:sticky!important;top:62px!important;z-index:1400!important;display:flex!important;gap:7px!important;overflow:auto!important;padding:7px 1px 11px!important;margin:0!important;background:linear-gradient(#030303 75%,transparent)!important}
.categoria-btn{flex:0 0 auto!important;border:1px solid #29292e!important;background:#0d0d0f!important;color:#bbb!important;border-radius:999px!important;padding:9px 12px!important;font-size:11px!important;font-weight:900!important}
.categoria-btn:hover{border-color:var(--fx-orange)!important;color:var(--fx-orange)!important;background:#16110e!important}
/* categorias */
.categoria{margin-top:28px!important;scroll-margin-top:125px!important}
.categoria-titulo{display:flex!important;align-items:center!important;gap:8px!important;border:0!important;border-bottom:1px solid #202025!important;padding:0 0 9px!important;margin-bottom:12px!important;color:#fff!important;font-size:19px!important;letter-spacing:-.3px!important}
.categoria-titulo:after{width:55px!important;background:var(--fx-orange)!important;box-shadow:0 0 18px rgba(255,101,0,.55)!important}
/* cards */
.produtos{grid-template-columns:repeat(auto-fill,minmax(215px,1fr))!important;gap:12px!important}
.produto{background:linear-gradient(160deg,#111114,#09090a)!important;border:1px solid #242429!important;border-radius:17px!important;padding:9px!important;box-shadow:0 10px 35px rgba(0,0,0,.35)!important;overflow:hidden!important}
.produto:hover{transform:translateY(-3px)!important;border-color:rgba(255,101,0,.6)!important;box-shadow:0 18px 45px rgba(0,0,0,.55),0 0 0 1px rgba(255,101,0,.08)!important}
.produto-imagem,.produto img{aspect-ratio:1/1!important;width:100%!important;height:auto!important;object-fit:cover!important;border-radius:12px!important;background:#070707!important;margin:0!important;display:block!important}
.produto h3{font-size:15px!important;line-height:1.15!important;margin:11px 2px 4px!important;color:#fff!important}
.produto p{font-size:11px!important;line-height:1.4!important;color:#85858d!important;min-height:31px!important;margin:0 2px!important}
.preco{font-size:20px!important;margin:9px 2px!important;color:var(--fx-orange2)!important;font-weight:1000!important}
/* selo de mais vendido */
.nd-fx-bestseller{position:absolute;left:15px;top:15px;z-index:8;padding:6px 9px;border-radius:8px;background:linear-gradient(135deg,var(--fx-orange),var(--fx-orange2));color:#050505;font-size:9px;font-weight:1000;letter-spacing:.4px;box-shadow:0 8px 20px rgba(0,0,0,.55);pointer-events:none}
.nd-fx-bestseller:before{content:"🔥 ";}
/* quantidade + adicionar */
.nd-fx-buyrow{display:grid;grid-template-columns:96px 1fr;gap:7px;align-items:stretch;margin-top:8px}
.nd-fx-qty{display:grid;grid-template-columns:29px 1fr 29px;align-items:center;border:1px solid #303036;background:#070708;border-radius:11px;overflow:hidden}
.nd-fx-qty button{border:0;background:#151519;color:var(--fx-orange2);font-size:19px;font-weight:900;cursor:pointer;height:100%}
.nd-fx-qty button:hover{background:#21150e}
.nd-fx-qty span{text-align:center;font-size:13px;font-weight:1000;color:#fff}
.nd-fx-add{border:0;border-radius:11px;background:linear-gradient(135deg,var(--fx-orange),var(--fx-orange2));color:#050505;font-weight:1000;font-size:11px;cursor:pointer;min-height:44px;box-shadow:0 7px 20px rgba(255,101,0,.16)}
.nd-fx-add:active,.nd-fx-qty button:active{transform:scale(.96)}
/* carrinho flutuante */
.carrinho-flutuante,.nd-v3-buybar{display:none!important}
.nd-fx-cartbar{position:fixed;left:50%;bottom:10px;transform:translateX(-50%);z-index:9900;width:min(760px,calc(100% - 18px));display:none;align-items:center;gap:10px;padding:10px 11px;border:1px solid rgba(255,101,0,.55);border-radius:17px;background:rgba(12,12,14,.96);box-shadow:0 18px 60px rgba(0,0,0,.8);backdrop-filter:blur(18px)}
.nd-fx-cartbar.show{display:flex}
.nd-fx-cart-icon{width:42px;height:42px;border-radius:12px;background:#171719;display:grid;place-items:center;font-size:20px}
.nd-fx-cart-info{flex:1;min-width:0}.nd-fx-cart-info strong{display:block;font-size:13px}.nd-fx-cart-info span{display:block;font-size:10px;color:#888;margin-top:2px}
.nd-fx-cart-total{color:var(--fx-orange2);font-weight:1000;font-size:15px;white-space:nowrap}
.nd-fx-cart-open{border:0;background:var(--fx-orange);color:#050505;border-radius:11px;padding:12px 14px;font-weight:1000;font-size:11px;cursor:pointer}
/* carrinho modal */
.modal-carrinho{z-index:100001!important;background:rgba(0,0,0,.82)!important;backdrop-filter:blur(10px)!important}
.painel-carrinho{width:min(760px,100%)!important;max-height:94vh!important;background:linear-gradient(160deg,#121214,#080809)!important;border:1px solid rgba(255,101,0,.6)!important;border-radius:22px 22px 0 0!important;padding:17px!important}
.cabecalho-carrinho h2{color:#fff!important;font-size:20px!important}.fechar-carrinho{background:#19191c!important;border:1px solid #333!important}
.item-carrinho-modal{padding:13px 0!important;border-bottom:1px solid #222!important}.item-carrinho-modal strong{font-size:14px!important}.item-carrinho-modal small{color:#777!important}
.controles-modal button,.controles button{background:#17171a!important;color:var(--fx-orange2)!important;border:1px solid #333!important}.controles-modal .remover,.controles .remover{background:#2a0d0b!important;color:#ff6b5e!important;border-color:#4a1713!important}
.btn-finalizar-pedido,.btn-finalizar-modal{background:linear-gradient(135deg,var(--fx-orange),var(--fx-orange2))!important;color:#050505!important;border:0!important}
/* checkout: só o modal novo fica ativo */
#checkout,.formulario{display:none!important}
/* modal finalizar */
.modal-finalizar{background:rgba(0,0,0,.86)!important;backdrop-filter:blur(10px)!important}
.painel-finalizar{background:linear-gradient(160deg,#121214,#080809)!important;border:1px solid rgba(255,101,0,.6)!important;border-radius:22px!important}
.nd-v4-step.active{border-color:var(--fx-orange)!important;color:var(--fx-orange)!important;background:rgba(255,101,0,.08)!important}
.nd-v4-next{background:var(--fx-orange)!important;color:#050505!important}.nd-v4-back{background:#111!important}
.nd-v4-pay.active{border-color:var(--fx-orange)!important;color:var(--fx-orange)!important;background:rgba(255,101,0,.08)!important}
.nd-v4-final-total{color:var(--fx-orange2)!important}
/* avaliações */
#ndFxReviews{margin:42px 0 15px;padding:18px;border:1px solid #242429;border-radius:20px;background:linear-gradient(160deg,#101012,#080809)}
.ndFx-review-head{display:flex;justify-content:space-between;gap:10px;align-items:end}.ndFx-review-head h2{margin:0!important;padding:0!important;border:0!important;color:#fff!important}.ndFx-review-head p{font-size:10px;color:#777;text-align:right;max-width:280px}
.ndFx-stars{display:flex;gap:5px;margin:15px 0}.ndFx-star{border:1px solid #303036;background:#0b0b0d;color:#555;border-radius:9px;width:42px;height:42px;font-size:22px;cursor:pointer}.ndFx-star.on{color:var(--fx-orange);border-color:var(--fx-orange);background:rgba(255,101,0,.08)}
#ndFxComment{min-height:90px;margin:0!important}.ndFx-review-send{margin-top:9px;width:100%;border:0;border-radius:11px;padding:13px;background:var(--fx-orange);color:#050505;font-weight:1000;cursor:pointer}
#ndFxReviewList{margin-top:15px;display:grid;gap:8px}.ndFx-review{padding:11px;border:1px solid #242429;border-radius:12px;background:#0b0b0d}.ndFx-review strong{color:var(--fx-orange2);font-size:11px}.ndFx-review p{color:#bbb;font-size:12px;margin-top:5px;line-height:1.45}.ndFx-review small{color:#666;font-size:9px}
/* footer */
.rodape-instagram{margin-top:35px!important;background:#050505!important;border-top:1px solid #18181b!important}.instagram-destaque{border-color:#29292e!important;background:#0c0c0e!important}.instagram-botao{background:var(--fx-orange)!important;color:#050505!important}
@media(max-width:700px){
 header{padding:16px 12px 13px!important} header .logo{width:min(205px,72vw)!important}
 .horarios-box{display:grid!important;grid-template-columns:1fr auto!important}.horarios-linha{text-align:left!important;grid-column:1/-1}
 .container{padding-left:8px!important;padding-right:8px!important}
 .ndFx-title{font-size:36px}.produtos{grid-template-columns:repeat(2,minmax(0,1fr))!important;gap:8px!important}.produto{padding:7px!important;border-radius:14px!important}.produto h3{font-size:13px!important}.produto p{font-size:9.5px!important;min-height:38px!important}.preco{font-size:18px!important}.nd-fx-buyrow{grid-template-columns:84px 1fr;gap:5px}.nd-fx-qty{grid-template-columns:25px 1fr 25px}.nd-fx-qty button{font-size:17px}.nd-fx-add{font-size:10px}.nd-fx-bestseller{left:11px;top:11px;font-size:8px;padding:5px 7px}
 .modern-search{top:0!important}.categoria-menu{top:61px!important}.categoria{scroll-margin-top:112px!important}
 .nd-fx-cartbar{bottom:7px}.nd-fx-cart-total{font-size:13px}.nd-fx-cart-open{padding:11px 10px;font-size:10px}
 .ndFx-review-head{display:block}.ndFx-review-head p{text-align:left;margin-top:6px}
}
</style><style id="nd-rodada-5-premium-performance">
:root{
  --nd-r5-red:#e50914;
  --nd-r5-red2:#ff3038;
  --nd-r5-gold:#f5c400;
  --nd-r5-white:#fff;
  --nd-r5-muted:#9da0a8;
  --nd-r5-surface:rgba(18,19,22,.96);
  --nd-r5-line:rgba(255,255,255,.085);
}

/* PERFORMANCE / ESTABILIDADE */
html{scroll-behavior:smooth;overscroll-behavior-x:none}
body{-webkit-tap-highlight-color:transparent}
img{content-visibility:auto}
header .logo,.nd-v4-art-burger{content-visibility:visible}
.produto{content-visibility:auto;contain-intrinsic-size:0 390px}
.categoria{contain:layout paint style}
button,a,input,select,textarea{-webkit-tap-highlight-color:transparent}
button{font-family:inherit}

/* HERO: deixa a primeira impressão mais rápida e estável */
.nd-v4-hero{contain:layout paint}
.nd-v4-art-burger{will-change:transform}

/* FEEDBACK DE TOQUE */
.btn-add,.btn-ver-carrinho,.nd-fx-add,.nd-fx-cart-open,.nd-v4-primary,.nd-v4-secondary,.categoria-btn,.nd-v3-buybar button,.nd-v4-next,.nd-v4-back,.btn-finalizar-pedido,.btn-continuar-comprando{
  position:relative;overflow:hidden;isolation:isolate;
}
.btn-add::after,.btn-ver-carrinho::after,.nd-fx-add::after,.nd-fx-cart-open::after,.nd-v4-primary::after,.nd-v4-next::after,.btn-finalizar-pedido::after{
  content:"";position:absolute;inset:0;transform:translateX(-105%);background:linear-gradient(105deg,transparent 25%,rgba(255,255,255,.20) 48%,transparent 70%);transition:transform .42s ease;pointer-events:none;z-index:2;
}
.btn-add:hover::after,.btn-ver-carrinho:hover::after,.nd-fx-add:hover::after,.nd-fx-cart-open:hover::after,.nd-v4-primary:hover::after,.nd-v4-next:hover::after,.btn-finalizar-pedido:hover::after{transform:translateX(105%)}
.btn-add:active,.btn-ver-carrinho:active,.nd-fx-add:active,.nd-fx-cart-open:active,.nd-v4-primary:active,.nd-v4-secondary:active,.categoria-btn:active,.nd-v4-next:active,.nd-v4-back:active,.btn-finalizar-pedido:active,.btn-continuar-comprando:active{transform:scale(.985)!important}

/* CARDS */
.produto{backface-visibility:hidden}
.produto::before{content:"";position:absolute;left:10%;right:10%;top:0;height:1px;background:linear-gradient(90deg,transparent,rgba(255,255,255,.16),transparent);opacity:.55}
.produto-imagem{transition:transform .28s ease,filter .28s ease}
.produto:hover .produto-imagem{transform:scale(1.025);filter:saturate(1.04)}

/* CATEGORIA ATIVA */
.categoria-btn.nd-r5-active{border-color:rgba(229,9,20,.72)!important;background:linear-gradient(180deg,#281013,#141011)!important;color:#fff!important;box-shadow:0 8px 24px rgba(229,9,20,.10)}

/* CONTADOR DE BUSCA */
.search-count{min-width:42px;text-align:right}


/* INDICADOR DE CARREGAMENTO DO SITE */
.nd-r5-loader{position:fixed;inset:0;z-index:999999;display:flex;align-items:center;justify-content:center;background:#070707;transition:opacity .28s ease,visibility .28s ease}
.nd-r5-loader.hide{opacity:0;visibility:hidden;pointer-events:none}
.nd-r5-loader-box{text-align:center}
.nd-r5-loader-mark{width:44px;height:44px;margin:auto;border:3px solid rgba(255,255,255,.10);border-top-color:#e50914;border-right-color:#f5c400;border-radius:50%;animation:ndR5Spin .75s linear infinite}
.nd-r5-loader-box span{display:block;margin-top:12px;color:#888;font-size:10px;font-weight:900;letter-spacing:2px}
@keyframes ndR5Spin{to{transform:rotate(360deg)}}

/* EVITA ANIMAÇÃO DE REVEAL EM USUÁRIOS QUE PREFEREM REDUÇÃO */
.nd-r5-reveal{opacity:0;transform:translateY(10px);transition:opacity .42s ease,transform .42s ease}
.nd-r5-reveal.nd-r5-visible{opacity:1;transform:none}

/* CARRINHO: leitura mais rápida */
.carrinho-flutuante-info span{font-variant-numeric:tabular-nums}
.carrinho-flutuante-total,.total,.total-modal,#ndV4Total{font-variant-numeric:tabular-nums}

/* FORMULÁRIOS: evita zoom e melhora digitação */
@media(max-width:760px){
  input,select,textarea{font-size:16px!important}
  .nd-r5-toast{top:72px;max-width:calc(100% - 24px);overflow:hidden;text-overflow:ellipsis}
}
@media(prefers-reduced-motion:reduce){
  .produto-imagem,.nd-r5-toast,.nd-r5-reveal{transition:none!important}
  .nd-r5-loader-mark{animation:none!important}
}
</style><style id="nd-r11-combos-ui">
:root{--r11-orange:#ff5a00;--r11-orange2:#ff9d00;--r11-yellow:#ffd21a;--r11-bg:#080808;--r11-card:#111216;--r11-line:rgba(255,255,255,.10)}
/* Busca única */
.categoria-menu,#nd20QuickNav{display:none!important}
.modern-search{position:sticky!important;top:8px!important;z-index:9400!important;margin:12px 0 16px!important}
/* Sidebar lateral: fixa do topo ao fim, com brilho laranja */
@media(min-width:901px){
 body{padding-left:232px!important}
 #nd18Sidebar{position:fixed!important;left:0!important;top:0!important;bottom:0!important;width:214px!important;height:100vh!important;max-height:none!important;overflow-y:auto!important;overflow-x:hidden!important;padding:18px 11px 22px!important;background:linear-gradient(180deg,#080808 0%,#110b07 48%,#080808 100%)!important;border:0!important;border-right:1px solid rgba(255,90,0,.42)!important;border-radius:0!important;box-shadow:8px 0 35px rgba(0,0,0,.75),inset -1px 0 0 rgba(255,157,0,.08)!important;z-index:20000!important}
 #nd18Sidebar:before{content:"";position:fixed;left:0;top:0;width:214px;height:2px;background:linear-gradient(90deg,transparent,#ff5a00,#ffd21a,#ff5a00,transparent);box-shadow:0 0 20px #ff5a00;pointer-events:none}
 #nd18Sidebar .nd18-title{position:sticky!important;top:0!important;background:linear-gradient(180deg,#080808 80%,transparent)!important;color:#ff9d00!important;font-size:12px!important;letter-spacing:1.7px!important;padding:7px 9px 14px!important;border-bottom:0!important}
 #nd18Sidebar button{position:relative!important;width:100%!important;margin:5px 0!important;padding:12px 12px!important;background:linear-gradient(135deg,#111214,#19100b)!important;color:#ddd!important;border:1px solid rgba(255,90,0,.18)!important;border-radius:12px!important;font-weight:800!important;box-shadow:inset 0 1px 0 rgba(255,255,255,.04),0 5px 15px rgba(0,0,0,.25)!important;overflow:hidden!important}
 #nd18Sidebar button:before{content:"";position:absolute;left:-45%;top:-80%;width:30%;height:260%;background:linear-gradient(90deg,transparent,rgba(255,170,0,.55),transparent);transform:rotate(18deg);animation:r11SideShine 4.5s linear infinite;pointer-events:none}
 #nd18Sidebar button:hover,#nd18Sidebar button.ativo{background:linear-gradient(135deg,#301306,#19100b)!important;color:#fff!important;border-color:#ff6500!important;transform:translateX(4px)!important;box-shadow:0 0 16px rgba(255,90,0,.22),inset 0 0 18px rgba(255,90,0,.06)!important}
 #nd18Sidebar::-webkit-scrollbar{width:5px}#nd18Sidebar::-webkit-scrollbar-thumb{background:linear-gradient(#ff5a00,#ffd21a);border-radius:10px}
}
@keyframes r11SideShine{0%{left:-55%}55%,100%{left:145%}}
@media(max-width:900px){#nd18Sidebar{position:sticky!important;top:0!important;z-index:20000!important;background:#080808!important;border-bottom:1px solid rgba(255,90,0,.45)!important}.modern-search{top:0!important}}
/* Carrinho no topo direito: texto 3D amarelo, discreto e sempre fixo */
#carrinhoFlutuante{position:fixed!important;right:18px!important;top:18px!important;left:auto!important;bottom:auto!important;width:auto!important;height:auto!important;min-width:0!important;max-width:190px!important;padding:0!important;transform:none!important;display:flex!important;opacity:0!important;pointer-events:none!important;z-index:50000!important;background:transparent!important;border:0!important;box-shadow:none!important}
#carrinhoFlutuante.ativo{opacity:1!important;pointer-events:auto!important}
#carrinhoFlutuante .carrinho-flutuante-info{display:flex!important;align-items:center!important;min-width:0!important}
#carrinhoFlutuante .carrinho-flutuante-info strong{display:block!important;font-size:0!important;line-height:1!important;background:linear-gradient(180deg,#fff79b 0%,#ffd21a 45%,#f39a00 100%);color:#161000!important;padding:10px 14px!important;border:1px solid #ffe36a!important;border-radius:12px!important;box-shadow:inset 0 2px 0 rgba(255,255,255,.65),inset 0 -4px 0 rgba(171,91,0,.65),0 3px 0 #8d5200,0 8px 18px rgba(0,0,0,.55),0 0 18px rgba(255,180,0,.22)!important;text-shadow:0 1px 0 rgba(255,255,255,.25)!important;white-space:nowrap!important;cursor:pointer!important}
#carrinhoFlutuante .carrinho-flutuante-info strong:after{content:'VER CARRINHO';font-size:12px!important;font-weight:1000!important;letter-spacing:.3px}
#carrinhoFlutuante .carrinho-flutuante-info span{position:absolute!important;right:-8px!important;top:-8px!important;min-width:23px!important;height:23px!important;padding:0 6px!important;display:flex!important;align-items:center!important;justify-content:center!important;background:#ff3b00!important;color:#fff!important;border:2px solid #080808!important;border-radius:50%!important;font-size:10px!important;font-weight:1000!important;box-shadow:0 0 12px rgba(255,70,0,.6)!important}
#carrinhoFlutuante .carrinho-flutuante-direita{display:none!important}
@media(max-width:600px){#carrinhoFlutuante{right:10px!important;top:10px!important}#carrinhoFlutuante .carrinho-flutuante-info strong{padding:9px 11px!important}#carrinhoFlutuante .carrinho-flutuante-info strong:after{font-size:10px!important}}
/* remove recomendações */
#ndR7Reco,#ndR7Recent,.nd-r3-upsell{display:none!important}
/* Destaque automático logo abaixo dos horários */
#ndAutoBest{position:relative;width:min(1180px,calc(100% - 28px));margin:15px auto 18px;padding:17px;border:1px solid rgba(255,90,0,.40);border-radius:20px;background:radial-gradient(circle at 80% 0%,rgba(255,90,0,.16),transparent 38%),linear-gradient(145deg,#0d0d0f,#170b05,#0a0a0a);box-shadow:0 12px 40px rgba(0,0,0,.55),0 0 28px rgba(255,90,0,.08);overflow:hidden}
#ndAutoBest:before{content:"";position:absolute;inset:-70px;background:conic-gradient(from 0deg,transparent,#ff5a00,transparent,#ffd21a,transparent);opacity:.08;animation:r11Spin 9s linear infinite}
@keyframes r11Spin{to{transform:rotate(360deg)}}
.r11-best-head{position:relative;z-index:1;display:flex;justify-content:space-between;align-items:end;gap:12px;margin-bottom:12px}.r11-best-head small{display:block;color:#ff7a21;font-size:9px;font-weight:1000;letter-spacing:2px}.r11-best-head h2{margin:3px 0 0!important;border:0!important;padding:0!important;font-size:24px!important;color:#fff!important}.r11-best-head p{color:#8f8f96;font-size:10px;text-align:right;margin:0}.r11-best-grid{position:relative;z-index:1;display:grid;grid-template-columns:repeat(3,1fr);gap:10px}.r11-best-card{display:grid;grid-template-columns:74px 1fr auto;gap:10px;align-items:center;padding:9px;border:1px solid rgba(255,90,0,.20);border-radius:14px;background:rgba(10,10,10,.86)}.r11-best-card img{width:74px;height:74px;object-fit:cover;border-radius:10px;background:#050505}.r11-best-card strong{display:block;font-size:12px}.r11-best-card span{display:block;color:#ffd21a;font-weight:1000;font-size:13px;margin-top:4px}.r11-best-card button{border:0;border-radius:9px;background:linear-gradient(135deg,#ff5a00,#ff9d00);color:#090909;font-weight:1000;font-size:10px;padding:10px 9px;cursor:pointer}
@media(max-width:700px){#ndAutoBest{width:calc(100% - 14px);padding:13px}.r11-best-head{align-items:flex-start;flex-direction:column}.r11-best-head p{text-align:left}.r11-best-grid{display:flex;overflow:auto}.r11-best-card{min-width:275px}}
/* Promo doce surpresa */
#ndUvaPromo{width:min(900px,calc(100% - 28px));margin:12px auto 22px;display:flex;align-items:center;justify-content:center;gap:18px;position:relative;padding:8px 14px 14px;background:radial-gradient(circle at 50% 45%,rgba(255,90,0,.10),transparent 58%);overflow:hidden}
#ndUvaPromo img{width:min(220px,34vw);height:170px;object-fit:contain;filter:drop-shadow(0 20px 18px rgba(0,0,0,.65));flex:none}
.r11-promo-copy{text-align:center}.r11-promo-copy .k{font-size:10px;font-weight:1000;letter-spacing:2px;color:#ff7a21}.r11-promo-copy h2{margin:4px 0 5px;border:0;padding:0;font-size:24px;color:#fff}.r11-promo-copy p{color:#aaa;font-size:11px;margin:0 0 8px}.r11-promo-old{text-decoration:line-through;color:#888;font-size:13px}.r11-promo-price{font-size:31px;font-weight:1000;color:#ffd21a;text-shadow:0 3px 0 #8c5c00,0 6px 12px rgba(0,0,0,.65);margin:2px 0 9px}.r11-promo-copy button{border:0;border-radius:12px;background:linear-gradient(180deg,#fff36b,#ffd21a 52%,#e59d00);color:#211700;padding:12px 18px;font-weight:1000;box-shadow:inset 0 2px 0 rgba(255,255,255,.8),0 4px 0 #996500,0 9px 20px rgba(0,0,0,.45);cursor:pointer}
@media(max-width:600px){#ndUvaPromo{gap:4px;padding:4px 2px 12px}.r11-promo-copy h2{font-size:18px}.r11-promo-price{font-size:26px}#ndUvaPromo img{width:125px;height:125px}.r11-promo-copy p{font-size:10px}}
/* Escolhas rápidas no fim */
#ndFinalQuick{width:min(1180px,calc(100% - 28px));margin:30px auto 12px;padding:16px;border:1px solid rgba(255,90,0,.25);border-radius:18px;background:linear-gradient(145deg,#111,#0b0b0b)}#ndFinalQuick h2{margin:0 0 3px;border:0;padding:0;color:#fff;font-size:21px}#ndFinalQuick>p{color:#888;font-size:10px;margin:0 0 12px}.r11-quick-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:9px}.r11-q{display:flex;align-items:center;gap:8px;padding:9px;border:1px solid #242424;border-radius:12px;background:#0d0d0d}.r11-q img{width:54px;height:54px;object-fit:cover;border-radius:8px}.r11-q div{min-width:0;flex:1}.r11-q b{display:block;font-size:11px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}.r11-q span{display:block;color:#ffd21a;font-size:11px;font-weight:900;margin:3px 0}.r11-q button{width:100%;border:0;border-radius:8px;padding:7px;background:#ff5a00;color:#fff;font-size:9px;font-weight:1000;cursor:pointer}@media(max-width:700px){.r11-quick-grid{grid-template-columns:1fr 1fr}.r11-q{flex-direction:column;align-items:stretch}.r11-q img{width:100%;height:90px}}
/* Modal de combos */
#ndComboModal{position:fixed;inset:0;z-index:400000;display:none;align-items:center;justify-content:center;padding:12px;background:rgba(0,0,0,.88);backdrop-filter:blur(12px)}#ndComboModal.show{display:flex}.r11-combo-panel{width:min(680px,100%);max-height:94vh;overflow:auto;background:linear-gradient(160deg,#17181b,#08090a);border:1px solid rgba(255,90,0,.65);border-radius:22px;box-shadow:0 25px 90px rgba(0,0,0,.8),0 0 35px rgba(255,90,0,.12);padding:18px}.r11-combo-head{display:flex;justify-content:space-between;gap:10px;align-items:flex-start;position:sticky;top:-18px;z-index:5;padding:2px 0 12px;background:linear-gradient(180deg,#17181b 75%,transparent)}.r11-combo-head h2{margin:0;border:0;padding:0;font-size:23px}.r11-combo-head small{display:block;color:#ff7a21;margin-top:4px;font-size:10px;font-weight:900}.r11-close{width:40px;height:40px;border:1px solid #333;border-radius:11px;background:#111;color:#fff;font-size:23px;cursor:pointer}.r11-section{margin:12px 0;padding:13px;border:1px solid rgba(255,255,255,.08);border-radius:15px;background:rgba(255,255,255,.025)}.r11-section h3{margin:0 0 4px;color:#ff9d00;font-size:16px}.r11-required{color:#ff5a00;font-size:9px;font-weight:1000;letter-spacing:.7px}.r11-option-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:10px}.r11-option{position:relative}.r11-option input{position:absolute;opacity:0;pointer-events:none}.r11-option label{display:block!important;margin:0!important;padding:12px 10px!important;border:1px solid #303136!important;border-radius:11px!important;background:#0c0d0f!important;color:#ddd!important;font-size:12px!important;font-weight:800!important;cursor:pointer!important;line-height:1.25!important}.r11-option input:checked+label{border-color:#ff5a00!important;background:linear-gradient(135deg,#2a1006,#17100d)!important;color:#fff!important;box-shadow:0 0 0 1px rgba(255,90,0,.22),0 7px 20px rgba(255,90,0,.10)!important}.r11-fixed{display:flex;align-items:center;justify-content:space-between;gap:8px;padding:11px;border-radius:10px;background:#0b0b0b;border:1px dashed #3a2a21;color:#ddd;font-size:12px;font-weight:900}.r11-fixed b{color:#ffd21a}.r11-addons{display:none;margin-top:11px;padding-top:11px;border-top:1px solid #272727}.r11-addons.show{display:block}.r11-bite{padding:11px;border-radius:11px;background:linear-gradient(135deg,#291006,#17100b);border:1px solid rgba(255,90,0,.35);color:#fff;font-size:13px;font-weight:1000;text-align:center;box-shadow:0 0 20px rgba(255,90,0,.06)}.r11-addon-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:7px;margin-top:9px}.r11-addon{position:relative;cursor:pointer}.r11-addon input{position:absolute;opacity:0}.r11-addon label{display:block!important;margin:0!important;height:100%!important;padding:5px!important;border:1px solid #2a2a2d!important;border-radius:10px!important;background:#0c0c0e!important;color:#ddd!important;cursor:pointer!important;text-align:center!important;font-size:9px!important;font-weight:900!important}.r11-addon img{width:100%;height:55px;object-fit:contain;border-radius:7px;margin-bottom:3px}.r11-addon input:checked+label{border-color:#ff9d00!important;background:#211208!important;color:#ffd21a!important}.r11-sauce-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-top:9px}.r11-sauce input{display:none}.r11-sauce label{display:block;padding:11px 7px;text-align:center;border:1px solid #303136;border-radius:10px;background:#0d0d0f;color:#ddd;font-size:11px;font-weight:900;cursor:pointer}.r11-sauce input:checked+label{border-color:#ffd21a;background:#251c05;color:#ffd21a}.r11-note{font-size:10px;color:#888;margin-top:8px;line-height:1.4}.r11-combo-total{display:flex;justify-content:space-between;align-items:center;padding:14px;margin-top:12px;background:#090909;border:1px solid #303030;border-radius:13px}.r11-combo-total span{font-size:11px;color:#aaa}.r11-combo-total strong{font-size:25px;color:#ffd21a;text-shadow:0 3px 0 #765000}.r11-confirm{width:100%;margin-top:10px;border:0;border-radius:13px;padding:15px;background:linear-gradient(135deg,#ff5a00,#ff9d00);color:#120a00;font-size:15px;font-weight:1000;cursor:pointer;box-shadow:0 6px 0 #8d4300,0 12px 25px rgba(255,90,0,.20)}.r11-confirm:active{transform:translateY(2px);box-shadow:0 4px 0 #8d4300}
@media(max-width:600px){#ndComboModal{padding:0;align-items:flex-end}.r11-combo-panel{max-height:96vh;border-radius:20px 20px 0 0;padding:14px}.r11-option-grid{grid-template-columns:1fr}.r11-addon-grid{grid-template-columns:repeat(4,1fr)}.r11-addon img{height:48px}.r11-combo-head h2{font-size:20px}.r11-sauce-grid{grid-template-columns:1fr 1fr}}
</style><style id="nd-r20-delivery-highlight-css">
#ndR18Delivery{display:none!important}
#ndR20DeliveryHighlight{width:min(920px,calc(100% - 28px));margin:42px auto 28px;position:relative;overflow:hidden;border-radius:24px;padding:20px 22px;box-sizing:border-box;isolation:isolate;background:radial-gradient(circle at 18% 50%,rgba(126,74,255,.28),transparent 34%),radial-gradient(circle at 82% 45%,rgba(42,116,255,.24),transparent 34%),linear-gradient(135deg,#090913,#11102a 48%,#080b18);border:1px solid rgba(149,108,255,.55);box-shadow:0 0 18px rgba(117,76,255,.32),0 0 48px rgba(45,101,255,.18),inset 0 0 30px rgba(122,83,255,.08)}
#ndR20DeliveryHighlight:before,#ndR20DeliveryHighlight:after{content:"";position:absolute;width:150px;height:150px;border-radius:50%;filter:blur(34px);opacity:.42;z-index:-1;pointer-events:none}
#ndR20DeliveryHighlight:before{background:#7a43ff;left:-55px;top:-70px}#ndR20DeliveryHighlight:after{background:#1677ff;right:-55px;bottom:-75px}
.nd-r20-spark{position:absolute;width:5px;height:5px;border-radius:50%;background:#fff;box-shadow:0 0 8px #fff,0 0 16px #8f70ff;opacity:.8;animation:ndR20Twinkle 2.8s ease-in-out infinite}.nd-r20-spark.s1{left:13%;top:18%}.nd-r20-spark.s2{left:34%;bottom:19%;animation-delay:.7s}.nd-r20-spark.s3{right:25%;top:17%;animation-delay:1.2s}.nd-r20-spark.s4{right:11%;bottom:22%;animation-delay:1.8s}@keyframes ndR20Twinkle{0%,100%{transform:scale(.6);opacity:.25}50%{transform:scale(1.35);opacity:1}}
.nd-r20-inner{display:flex;align-items:center;justify-content:center;gap:20px;position:relative;z-index:2;text-align:center}.nd-r20-icon{width:52px;height:52px;flex:0 0 52px;border-radius:16px;display:grid;place-items:center;font-size:27px;background:rgba(255,255,255,.07);border:1px solid rgba(173,139,255,.42);box-shadow:0 0 18px rgba(109,72,255,.25)}.nd-r20-copy{min-width:0}.nd-r20-kicker{margin:0 0 4px;font-size:11px;font-weight:900;letter-spacing:1.7px;color:#c8b9ff;text-transform:uppercase}.nd-r20-title{margin:0;font-size:clamp(18px,3vw,27px);font-weight:1000;letter-spacing:.2px;color:#fff;text-shadow:0 0 14px rgba(130,92,255,.45)}.nd-r20-time{display:inline-block;margin:5px 0 2px;font-size:clamp(24px,4.8vw,38px);line-height:1;font-weight:1000;letter-spacing:.4px;background:linear-gradient(90deg,#bba3ff,#fff,#7fb8ff);-webkit-background-clip:text;background-clip:text;color:transparent;filter:drop-shadow(0 0 10px rgba(116,91,255,.35))}.nd-r20-sub{margin:4px 0 0;color:rgba(255,255,255,.74);font-size:12px;font-weight:700}.nd-r20-line{width:70px;height:2px;margin:9px auto 0;border-radius:10px;background:linear-gradient(90deg,transparent,#8f6cff,#5ca4ff,transparent);box-shadow:0 0 10px rgba(111,90,255,.65)}
@media(max-width:600px){#ndR20DeliveryHighlight{margin:30px auto 22px;padding:17px 14px;border-radius:20px}.nd-r20-inner{gap:12px}.nd-r20-icon{width:43px;height:43px;flex-basis:43px;font-size:22px;border-radius:13px}.nd-r20-kicker{font-size:9px;letter-spacing:1.2px}.nd-r20-title{font-size:16px}.nd-r20-time{font-size:28px}.nd-r20-sub{font-size:10px}}
</style><style id="nd-r22-uva-premium">
/* =========================================================
   ND BURGS — RODADA 22
   DESCONTO EXCLUSIVO — DOCE SURPRESA DE UVA
   Visual inspirado no layout de referência:
   azul + roxo neon, card premium, brilho e CTA forte.
   ========================================================= */
#ndUvaPromo{
  width:min(1000px,calc(100% - 28px)) !important;
  min-height:250px !important;
  margin:18px auto 26px !important;
  padding:28px 30px !important;
  display:grid !important;
  grid-template-columns:minmax(190px,280px) minmax(0,1fr) !important;
  align-items:center !important;
  gap:28px !important;
  position:relative !important;
  overflow:hidden !important;
  isolation:isolate !important;
  border:1px solid rgba(89,109,255,.72) !important;
  border-radius:24px !important;
  background:
    radial-gradient(circle at 5% 0%,rgba(43,93,255,.34),transparent 34%),
    radial-gradient(circle at 100% 0%,rgba(145,44,255,.42),transparent 40%),
    linear-gradient(115deg,#090b1b 0%,#0c0b20 43%,#18092b 72%,#10071c 100%) !important;
  box-shadow:
    0 18px 55px rgba(0,0,0,.65),
    0 0 28px rgba(80,91,255,.16),
    inset 0 1px 0 rgba(255,255,255,.10) !important;
}
#ndUvaPromo:before{
  content:"" !important;
  position:absolute !important;
  z-index:-1 !important;
  width:72% !important;
  height:130% !important;
  right:-15% !important;
  top:-50% !important;
  background:linear-gradient(135deg,transparent 28%,rgba(119,65,255,.16) 45%,rgba(80,123,255,.10) 58%,transparent 72%) !important;
  transform:rotate(-8deg) !important;
  filter:blur(2px) !important;
}
#ndUvaPromo:after{
  content:"" !important;
  position:absolute !important;
  inset:0 !important;
  z-index:-1 !important;
  background:radial-gradient(circle at 22% 100%,rgba(36,78,255,.10),transparent 28%) !important;
  pointer-events:none !important;
}
#ndUvaPromo img{
  width:100% !important;
  max-width:280px !important;
  height:205px !important;
  object-fit:contain !important;
  filter:drop-shadow(0 22px 22px rgba(0,0,0,.75)) drop-shadow(0 0 16px rgba(102,83,255,.20)) !important;
  flex:none !important;
  justify-self:center !important;
}
#ndUvaPromo .r11-promo-copy{
  position:relative !important;
  z-index:2 !important;
  text-align:left !important;
  min-width:0 !important;
}
#ndUvaPromo .r11-promo-copy .k{
  display:inline-flex !important;
  align-items:center !important;
  min-height:30px !important;
  padding:0 12px !important;
  border:1px solid rgba(112,128,255,.72) !important;
  border-radius:999px !important;
  background:rgba(7,10,31,.58) !important;
  color:#d8dcff !important;
  font-size:10px !important;
  font-weight:1000 !important;
  letter-spacing:1.5px !important;
  box-shadow:0 0 18px rgba(75,89,255,.12),inset 0 1px 0 rgba(255,255,255,.08) !important;
}
#ndUvaPromo .r11-promo-copy h2{
  margin:12px 0 7px !important;
  padding:0 !important;
  border:0 !important;
  color:#f1f2ff !important;
  font-size:clamp(25px,3.5vw,42px) !important;
  line-height:.98 !important;
  font-weight:1000 !important;
  letter-spacing:-1px !important;
  text-transform:uppercase !important;
  text-shadow:0 5px 18px rgba(0,0,0,.55) !important;
}
#ndUvaPromo .r11-promo-copy p{
  margin:0 0 9px !important;
  color:#b9bad0 !important;
  font-size:12px !important;
  line-height:1.45 !important;
}
#ndUvaPromo .r11-promo-old{
  color:#77798d !important;
  font-size:13px !important;
  font-weight:800 !important;
  text-decoration:line-through !important;
  text-decoration-thickness:2px !important;
}
#ndUvaPromo .r11-promo-price{
  display:inline-block !important;
  margin:2px 0 13px !important;
  padding:5px 13px !important;
  border:1px solid rgba(122,100,255,.72) !important;
  border-radius:11px !important;
  background:linear-gradient(100deg,#765cff 0%,#5e8cff 52%,#9a54ff 100%) !important;
  color:#fff !important;
  font-size:clamp(25px,3vw,34px) !important;
  line-height:1.05 !important;
  font-weight:1000 !important;
  letter-spacing:-.5px !important;
  text-shadow:0 2px 10px rgba(0,0,0,.48) !important;
  box-shadow:0 0 16px rgba(91,91,255,.32),0 8px 24px rgba(0,0,0,.30),inset 0 1px 0 rgba(255,255,255,.30) !important;
}
#ndUvaPromo .r11-promo-copy button{
  display:inline-flex !important;
  align-items:center !important;
  justify-content:center !important;
  min-height:46px !important;
  padding:12px 19px !important;
  border:1px solid rgba(198,205,255,.65) !important;
  border-radius:13px !important;
  background:linear-gradient(135deg,#b5c5ff 0%,#7b83ff 44%,#a24dff 100%) !important;
  color:#08091a !important;
  font-size:11px !important;
  font-weight:1000 !important;
  letter-spacing:.25px !important;
  cursor:pointer !important;
  box-shadow:
    inset 0 2px 0 rgba(255,255,255,.72),
    0 4px 0 rgba(49,38,122,.75),
    0 10px 26px rgba(88,83,255,.30) !important;
  transition:transform .18s ease,filter .18s ease,box-shadow .18s ease !important;
}
#ndUvaPromo .r11-promo-copy button:hover{
  transform:translateY(-2px) !important;
  filter:brightness(1.08) !important;
  box-shadow:inset 0 2px 0 rgba(255,255,255,.78),0 5px 0 rgba(49,38,122,.75),0 14px 32px rgba(113,83,255,.42) !important;
}
#ndUvaPromo .r11-promo-copy button:active{transform:translateY(2px) !important;box-shadow:inset 0 2px 0 rgba(255,255,255,.65),0 2px 0 rgba(49,38,122,.75),0 7px 18px rgba(113,83,255,.25) !important}
@media(max-width:700px){
  #ndUvaPromo{
    width:calc(100% - 14px) !important;
    min-height:0 !important;
    grid-template-columns:105px minmax(0,1fr) !important;
    gap:10px !important;
    padding:18px 13px !important;
    border-radius:20px !important;
  }
  #ndUvaPromo img{width:105px !important;height:125px !important}
  #ndUvaPromo .r11-promo-copy .k{font-size:8px !important;letter-spacing:1px !important;padding:0 8px !important;min-height:26px !important;white-space:nowrap !important}
  #ndUvaPromo .r11-promo-copy h2{font-size:21px !important;line-height:1.02 !important;letter-spacing:-.4px !important;margin:8px 0 5px !important}
  #ndUvaPromo .r11-promo-copy p{font-size:9px !important;margin-bottom:5px !important}
  #ndUvaPromo .r11-promo-old{font-size:10px !important}
  #ndUvaPromo .r11-promo-price{display:block !important;width:max-content !important;max-width:100% !important;font-size:24px !important;margin:2px 0 9px !important;padding:5px 9px !important}
  #ndUvaPromo .r11-promo-copy button{width:100% !important;min-height:43px !important;padding:10px 8px !important;font-size:9px !important}
}
@media(max-width:390px){
  #ndUvaPromo{grid-template-columns:88px minmax(0,1fr) !important;padding:15px 9px !important;gap:7px !important}
  #ndUvaPromo img{width:88px !important;height:112px !important}
  #ndUvaPromo .r11-promo-copy h2{font-size:18px !important}
  #ndUvaPromo .r11-promo-copy .k{font-size:7px !important;letter-spacing:.6px !important}
  #ndUvaPromo .r11-promo-price{font-size:21px !important}
}
@media(prefers-reduced-motion:reduce){#ndUvaPromo .r11-promo-copy button{transition:none !important}}
</style><style id="nd-r24-final-upgrades">
/* POSIÇÕES EXATAS DOS DESTAQUES */
#ndUvaPromo{
  order:initial!important;
}
#ndR17FirstBuy{
  order:initial!important;
}

/* títulos internos da categoria unificada */
.nd-r24-subtitulo{
  grid-column:1/-1;
  margin:18px 0 2px;
  padding:11px 13px;
  border-left:4px solid #e50914;
  border-radius:10px;
  background:linear-gradient(90deg,rgba(229,9,20,.12),transparent);
  color:#fff;
  font-size:16px;
  font-weight:1000;
  letter-spacing:.2px;
}
.nd-r24-subtitulo small{
  display:block;
  color:#888;
  font-size:10px;
  margin-top:3px;
  font-weight:700;
}
#ndR17FirstBuy.nd-r24-daily{
  grid-column:1/-1!important;
  width:100%!important;
  margin:18px 0!important;
}
#ndUvaPromo.nd-r24-uva{
  position:relative!important;
}
.nd-r24-badge{
  position:absolute;
  top:10px;
  left:10px;
  z-index:5;
  padding:6px 9px;
  border-radius:999px;
  background:#e50914;
  color:#fff;
  font-size:9px;
  font-weight:1000;
  letter-spacing:.5px;
  box-shadow:0 5px 15px rgba(229,9,20,.3);
}
.nd-r24-added{
  position:fixed;
  left:50%;
  top:85px;
  transform:translate(-50%,-15px);
  opacity:0;
  pointer-events:none;
  z-index:100010;
  padding:11px 16px;
  border-radius:999px;
  background:#25d366;
  color:#fff;
  font-size:13px;
  font-weight:900;
  box-shadow:0 10px 30px rgba(0,0,0,.45);
  transition:.22s ease;
}
.nd-r24-added.show{opacity:1;transform:translate(-50%,0)}
.nd-r24-search-empty{
  display:none;
  margin:14px 0;
  padding:25px 15px;
  text-align:center;
  border:1px dashed #333;
  border-radius:16px;
  color:#999;
}
.nd-r24-quick-buy{
  margin-top:8px!important;
  min-height:44px!important;
}
@media(max-width:700px){
  .nd-r24-subtitulo{font-size:14px;padding:10px 11px}
  #ndR17FirstBuy.nd-r24-daily{margin:14px 0!important}
}
</style><style id="nd-final-user-changes">
/* ND BURGS — PADRÃO 06/09/2026
   Ajustes solicitados:
   - Promoção Surpresa de Uva entre Tradicionais e Artesanais
   - Remoção do Produto Aleatório do Dia
   - Foto genérica para produtos sem foto/foto quebrada
   - Checkout/WhatsApp simples, sem emojis
   - Confirmação manual após o cliente enviar no WhatsApp
   - Carrinho limpo somente após a confirmação do envio
*/
#ndR17FirstBuy,
#ndOrderSuccess,
#ndR25SendGate,
#ndR25Confirmed,
#ndR25PixPending{display:none!important}

/* Garante que a promoção não ocupe o topo */
#ndUvaPromo.nd-final-middle{
  display:grid!important;
  width:min(1000px,calc(100% - 28px))!important;
  margin:24px auto!important;
}

/* Estado de confirmação */
#ndFinalSendGate{
  position:fixed;inset:0;z-index:900000;
  display:none;align-items:center;justify-content:center;
  padding:18px;background:rgba(0,0,0,.94);
  backdrop-filter:blur(12px);
}
#ndFinalSendGate.show{display:flex}
.nd-final-send-panel{
  width:min(560px,96vw);padding:25px 20px;text-align:center;
  border:1px solid #1677ff;border-radius:22px;background:#080808;
  box-shadow:0 25px 90px rgba(0,0,0,.85);
}
.nd-final-send-panel h2{margin:0 0 10px;border:0;padding:0;color:#fff;font-size:27px}
.nd-final-send-panel p{margin:0 auto 18px;color:#aaa;font-size:13px;line-height:1.5}
.nd-final-send-panel button{
  width:100%;min-height:50px;border:0;border-radius:12px;
  padding:13px;font-weight:900;cursor:pointer;
}
#ndFinalOpenWhatsApp{background:#25d366;color:#071b0d}
#ndFinalConfirmSent{margin-top:9px;background:#1677ff;color:#fff}
#ndFinalBack{margin-top:9px;background:#171717;color:#aaa;border:1px solid #303030!important}
#ndFinalSentState{
  display:none;margin-top:12px;padding:10px;border-radius:11px;
  background:#07150c;border:1px solid rgba(37,211,102,.25);
  color:#bff5d1;font-size:11px;font-weight:800;
}
@media(max-width:600px){
  #ndUvaPromo.nd-final-middle{width:calc(100% - 14px)!important}
  .nd-final-send-panel{padding:21px 15px}
  .nd-final-send-panel h2{font-size:23px}
}
</style><style id="nd-r26-final">
/* ===== ENDEREÇO ÚNICO NO TOPO ===== */
#ndTopAddress{position:relative;z-index:1800;width:min(1180px,calc(100% - 20px));margin:12px auto 8px;padding:14px;border:1px solid rgba(75,143,255,.78);border-radius:20px;background:radial-gradient(circle at 12% 10%,rgba(51,112,255,.22),transparent 32%),radial-gradient(circle at 88% 80%,rgba(116,50,255,.20),transparent 36%),linear-gradient(145deg,#0a0d18,#07070c 58%,#090611);box-shadow:0 0 16px rgba(46,117,255,.42),0 0 38px rgba(84,43,255,.22),inset 0 1px 0 rgba(255,255,255,.14),0 16px 40px rgba(0,0,0,.42);transform:translateZ(0);overflow:visible}
#ndTopAddress:before,#ndTopAddress:after{content:"";position:absolute;pointer-events:none;border-radius:999px;filter:blur(2px);opacity:.85}
#ndTopAddress:before{width:180px;height:180px;left:-90px;top:-100px;background:radial-gradient(circle,rgba(0,156,255,.42),transparent 68%);animation:nd26Orb 4.4s ease-in-out infinite}
#ndTopAddress:after{width:170px;height:170px;right:-70px;bottom:-110px;background:radial-gradient(circle,rgba(133,48,255,.35),transparent 70%);animation:nd26Orb 5.1s ease-in-out infinite reverse}
.nd26-top-inner{position:relative;z-index:2;display:grid;grid-template-columns:1fr auto;gap:12px;align-items:end}
.nd26-kicker{font-size:10px;font-weight:1000;letter-spacing:1.8px;color:#9ec9ff;text-transform:uppercase}
.nd26-title{margin-top:4px;font-size:clamp(19px,3vw,29px);font-weight:1000;letter-spacing:-.6px;color:#fff;text-shadow:0 4px 16px rgba(52,128,255,.22)}
.nd26-title strong{color:#9fc8ff}
.nd26-sub{margin-top:5px;color:#aab1bf;font-size:11px;line-height:1.4}
.nd26-mode-row{display:flex;gap:8px;margin-top:12px;flex-wrap:wrap}
.nd26-mode{border:1px solid rgba(255,255,255,.1);background:#0d1018;color:#d8deea;border-radius:12px;padding:10px 13px;min-height:44px;font-weight:900;cursor:pointer;box-shadow:inset 0 1px 0 rgba(255,255,255,.05);transition:.18s ease}
.nd26-mode.active{border-color:#4b93ff;background:linear-gradient(135deg,#163a79,#101b31);color:#fff;box-shadow:0 0 18px rgba(58,132,255,.2),inset 0 1px 0 rgba(255,255,255,.12)}
.nd26-fields{position:relative;display:grid;grid-template-columns:minmax(0,1fr) 120px auto;gap:8px;margin-top:10px}
.nd26-field-wrap{position:relative}
.nd26-input{width:100%;margin:0!important;min-height:46px;padding:12px 13px!important;background:#070a10!important;border:1px solid rgba(255,255,255,.12)!important;border-radius:12px!important;color:#fff!important;outline:none!important;font-size:14px!important}
.nd26-input:focus{border-color:#4b93ff!important;box-shadow:0 0 0 3px rgba(75,147,255,.11)!important}
.nd26-save{min-height:46px;border:0;border-radius:12px;padding:11px 15px;background:linear-gradient(135deg,#2d7cff,#6c5cff);color:#fff;font-weight:1000;cursor:pointer;box-shadow:0 0 18px rgba(53,110,255,.3),0 7px 18px rgba(0,0,0,.28);transition:.18s ease}
.nd26-save:hover{transform:translateY(-1px);filter:brightness(1.08)}
.nd26-status{margin-top:9px;display:flex;align-items:center;justify-content:space-between;gap:10px;padding:9px 11px;border:1px solid rgba(255,255,255,.08);border-radius:11px;background:rgba(0,0,0,.22);font-size:11px;color:#b5bdca}
.nd26-status strong{color:#fff}
.nd26-status button{border:1px solid #2e3b52;background:#10151d;color:#dce6f7;border-radius:9px;padding:7px 10px;font-weight:900;cursor:pointer}
.nd26-list{position:absolute;left:0;right:0;top:calc(100% + 6px);display:none;max-height:270px;overflow:auto;padding:5px;background:#0a0c12;border:1px solid rgba(82,142,255,.5);border-radius:13px;box-shadow:0 20px 55px rgba(0,0,0,.72);z-index:500000}
.nd26-list.show{display:block}
.nd26-option{display:flex;align-items:center;justify-content:space-between;gap:8px;padding:11px 10px;border-radius:9px;color:#edf2fb;font-size:12px;cursor:pointer}
.nd26-option:hover{background:linear-gradient(90deg,rgba(44,116,255,.25),rgba(111,67,255,.17));color:#fff}
.nd26-option small{color:#7eaef9;white-space:nowrap}
.nd26-pickup-note{display:none;margin-top:10px;padding:10px 12px;border-radius:11px;background:rgba(27,28,36,.8);border:1px solid rgba(255,255,255,.09);color:#c6cad3;font-size:11px;line-height:1.45}
.nd26-pickup-note.show{display:block}
@keyframes nd26Orb{0%,100%{transform:translate3d(0,0,0);opacity:.45}50%{transform:translate3d(18px,-8px,0);opacity:.95}}

/* Esconde versões antigas que duplicavam endereço/tempo/oferta. */
#nd17AddressBar{display:none!important}
#nd17Gate{display:none!important}
#enderecoAreaModal{display:none!important}
#ndR20DeliveryHighlight{display:none!important}
#ndUvaPromo{display:none!important}
#ndFinalSendGate{display:none!important}

/* Etapa 2 do checkout: endereço somente informativo, sem segunda seleção. */
#ndV4SingleAddressSummary{margin-top:10px;padding:12px;border:1px solid rgba(75,147,255,.25);border-radius:12px;background:linear-gradient(145deg,#0d111a,#090a0f);color:#c7d0dd;font-size:11px;line-height:1.5}
#ndV4SingleAddressSummary strong{color:#fff;font-size:13px}
#ndV4SingleAddressSummary button{margin-top:8px;border:1px solid #283c60;background:#111827;color:#cfe2ff;border-radius:9px;padding:7px 10px;font-weight:900;cursor:pointer}

/* Aviso minimalista de prazo dentro do checkout. */
#nd26DeliveryMini{margin:12px 0 0;padding:9px 11px;border:1px solid rgba(75,147,255,.20);border-radius:10px;background:rgba(32,40,58,.4);color:#aebbd0;font-size:10px;line-height:1.45}
#nd26DeliveryMini b{color:#eaf2ff}

/* PIX: aviso de segurança + CTA de pagamento. */
#ndPixAttention{margin:12px 0 10px;padding:14px 13px;border:1px solid rgba(255,74,74,.55);border-radius:15px;background:radial-gradient(circle at 10% 10%,rgba(255,64,64,.12),transparent 34%),linear-gradient(145deg,#210d0f,#12090b);box-shadow:0 8px 24px rgba(0,0,0,.25)}
#ndPixAttention .nd26-attn-badge{display:inline-flex;align-items:center;gap:7px;padding:6px 9px;border-radius:999px;background:#351317;border:1px solid #7a2730;color:#ff9ca2;font-size:10px;font-weight:1000;letter-spacing:1px}
#ndPixAttention .nd26-attn-big{margin-top:9px;font-size:clamp(20px,4vw,31px);line-height:1.02;font-weight:1000;letter-spacing:-.8px;color:#fff}
#ndPixAttention .nd26-attn-big span{color:#ff626b}
#ndPixAttention p{margin-top:8px;color:#d1bfc2;font-size:11px;line-height:1.5}
#ndPixSafe{margin:9px 0 0;padding:10px 11px;border-left:3px solid #ff5b65;border-radius:9px;background:rgba(255,255,255,.035);color:#c9c9d0;font-size:10px;line-height:1.5}
#nd26AlreadyPaid{width:100%;margin-top:11px;min-height:52px;border:1px solid rgba(83,196,255,.75);border-radius:13px;background:linear-gradient(135deg,#0f66d8,#5139ff);color:#fff;font-size:13px;font-weight:1000;letter-spacing:.2px;cursor:pointer;box-shadow:0 0 22px rgba(44,121,255,.22),0 10px 26px rgba(0,0,0,.35);transition:.18s ease}
#nd26AlreadyPaid:hover{transform:translateY(-1px);filter:brightness(1.08)}
#ndPixBox .nd-pix-copy,#ndPixCopyValue{min-height:48px!important}

/* Botão da etapa 3 renomeado. */
#nd26ReviewButton{font-size:14px!important}

/* ===== SUPER OFERTA ===== */
#nd26SuperOffer{width:min(920px,calc(100% - 20px));margin:36px auto 20px;padding:18px;border:1px solid rgba(101,115,255,.72);border-radius:24px;background:radial-gradient(circle at 18% 22%,rgba(39,150,255,.18),transparent 34%),radial-gradient(circle at 84% 78%,rgba(154,57,255,.18),transparent 36%),linear-gradient(145deg,#0d1020,#09090f);box-shadow:0 0 24px rgba(59,92,255,.18),0 22px 70px rgba(0,0,0,.58),inset 0 1px 0 rgba(255,255,255,.11);overflow:hidden;position:relative}
#nd26SuperOffer:before{content:"";position:absolute;inset:-2px;background:linear-gradient(100deg,transparent 10%,rgba(120,170,255,.16) 42%,rgba(180,100,255,.16) 58%,transparent 90%);transform:translateX(-110%);animation:nd26Sweep 4.8s linear infinite;pointer-events:none}
.nd26-offer-head{position:relative;z-index:1;display:flex;align-items:center;justify-content:space-between;gap:10px}
.nd26-offer-kicker{font-size:10px;letter-spacing:1.8px;color:#9eb7ff;font-weight:1000}
.nd26-offer-title{margin-top:3px;font-size:clamp(24px,5vw,42px);font-weight:1000;letter-spacing:-1.2px;color:#fff}
.nd26-offer-badge{padding:8px 10px;border-radius:999px;border:1px solid rgba(107,160,255,.6);background:rgba(77,111,255,.12);color:#cfe0ff;font-size:10px;font-weight:1000;white-space:nowrap}
.nd26-offer-card{position:relative;z-index:1;display:grid;grid-template-columns:120px 1fr auto;align-items:center;gap:14px;margin-top:15px;padding:13px;border:1px solid rgba(255,255,255,.09);border-radius:18px;background:rgba(255,255,255,.035)}
.nd26-offer-img{width:120px;height:120px;object-fit:cover;border-radius:14px;background:#07080c}
.nd26-offer-name{font-size:18px;font-weight:1000;color:#fff;line-height:1.05}
.nd26-offer-desc{margin-top:6px;color:#969fb0;font-size:11px;line-height:1.45}
.nd26-offer-price{display:inline-block;margin-top:10px;padding:8px 10px;border-radius:11px;background:linear-gradient(135deg,#7d55ff,#287bff);color:#fff;font-size:24px;font-weight:1000;box-shadow:0 0 18px rgba(91,70,255,.22)}
.nd26-offer-btn{min-width:170px;min-height:50px;border:0;border-radius:13px;background:linear-gradient(135deg,#396eff,#8a47ff);color:#fff;font-weight:1000;cursor:pointer;box-shadow:0 10px 25px rgba(62,87,255,.25);transition:.18s ease}
.nd26-offer-btn:hover{transform:translateY(-2px);filter:brightness(1.08)}
@keyframes nd26Sweep{0%{transform:translateX(-110%)}65%,100%{transform:translateX(110%)}}
@media(max-width:720px){
 #nd26-top{} 
 .nd26-top-inner{grid-template-columns:1fr}
 .nd26-fields{grid-template-columns:1fr 100px}
 .nd26-save{grid-column:1/-1}
 .nd26-offer-card{grid-template-columns:82px 1fr}
 .nd26-offer-img{width:82px;height:82px}
 .nd26-offer-btn{grid-column:1/-1;width:100%}
}
@media(max-width:480px){
 #ndTopAddress{width:calc(100% - 14px);padding:12px;border-radius:17px}
 .nd26-fields{grid-template-columns:1fr}
 .nd26-mode{flex:1}
 .nd26-offer-name{font-size:15px}
 .nd26-offer-price{font-size:21px}
}
@media(prefers-reduced-motion:reduce){#ndTopAddress:before,#ndTopAddress:after,#nd26SuperOffer:before{animation:none!important}}
</style><style id="nd-r27-pix-security">
#ndR27PixToast{
  position:fixed;left:50%;top:50%;transform:translate(-50%,-46%) scale(.96);
  width:min(560px,calc(100% - 28px));z-index:999999;
  display:none;padding:22px 20px 18px;border-radius:20px;
  background:linear-gradient(145deg,#210d0f,#0e0e11);
  border:2px solid #ff3038;color:#fff;text-align:center;
  box-shadow:0 25px 90px rgba(0,0,0,.78),0 0 35px rgba(229,9,20,.18);
  opacity:0;transition:.2s ease;
}
#ndR27PixToast.show{display:block;opacity:1;transform:translate(-50%,-50%) scale(1)}
#ndR27PixToast .r27-pix-icon{font-size:30px;line-height:1;margin-bottom:8px}
#ndR27PixToast strong{display:block;color:#ff626b;font-size:20px;font-weight:1000;letter-spacing:-.3px}
#ndR27PixToast p{margin:9px 0 15px;color:#eee;font-size:13px;line-height:1.5}
#ndR27PixToast button{width:100%;min-height:48px;border:0;border-radius:12px;background:linear-gradient(135deg,#e50914,#ff3038);color:#fff;font-size:13px;font-weight:1000;cursor:pointer;box-shadow:0 8px 24px rgba(229,9,20,.2)}
#ndR27PixToast button:hover{filter:brightness(1.08)}
#ndR27PixSecurityNote{
  margin:13px 0 2px;padding:13px 13px;border-radius:13px;
  border:1px solid rgba(255,193,7,.48);
  background:linear-gradient(145deg,#241d08,#151208);
  color:#ddd;font-size:11px;line-height:1.5;
}
#ndR27PixSecurityNote .r27-security-title{display:flex;align-items:center;gap:7px;color:#ffd166;font-size:12px;font-weight:1000;margin-bottom:5px}
#ndR27PixSecurityNote b{color:#fff}
#nd26AlreadyPaid{position:relative;z-index:2}
@media(max-width:600px){
  #ndR27PixToast{padding:19px 16px 16px}
  #ndR27PixToast strong{font-size:18px}
  #ndR27PixToast p{font-size:12px}
}
</style><style id="nd-r28-final-fixes">
/* Header: somente o logo oficial */
header .logo{
  width:min(190px,76vw)!important;
  max-width:76vw!important;
  display:block!important;
  margin:0 auto!important;
}
@media(max-width:700px){
  header{padding:14px 10px 12px!important}
  header .logo{width:min(210px,78vw)!important;max-width:78vw!important}
}

/* Remove qualquer marca/faixa duplicada criada por camadas antigas. */
.nd-v3-strip,
.nd17-brand{
  display:none!important;
}

/* Botões de compra */
.btn-add,
.nd-fx-add,
.nd-r3-add,
.nd-r7-card button,
.nd-v3-up button,
.nd-r17-fb-btn,
.nd26-offer-btn,
.r11-promo-copy button{
  font-weight:950!important;
  letter-spacing:.25px!important;
}

/* Estado ADICIONADO */
.nd-r28-added{
  background:linear-gradient(135deg,#1fa85b,#25d366)!important;
  color:#fff!important;
  border-color:rgba(37,211,102,.45)!important;
  box-shadow:0 8px 22px rgba(37,211,102,.18)!important;
}
.nd-r28-added:hover{
  background:linear-gradient(135deg,#25d366,#31e978)!important;
  color:#fff!important;
}
.nd-r28-added::after{display:none!important}

/* Sugestões: preço sempre visível e CTA embaixo */
.nd-r7-card small,
.nd-v3-up small,
.suggestion-card span{
  display:block!important;
  color:#ffd166!important;
  font-size:13px!important;
  font-weight:950!important;
}
.nd-r7-card,
.nd-v3-up,
.suggestion-card{
  position:relative;
}
.nd-r7-card button,
.nd-v3-up button,
.suggestion-card button{
  min-height:42px!important;
}

/* Feedback discreto */
.nd-r28-flash{
  animation:ndR28Flash .45s ease;
}
@keyframes ndR28Flash{
  0%{transform:scale(1)}
  45%{transform:scale(1.035)}
  100%{transform:scale(1)}
}
@media(prefers-reduced-motion:reduce){
  .nd-r28-flash{animation:none!important}
}
</style><style id="nd-r29-clean-features">
/* =========================================================
   ND BURGS R29 — LIMPEZA + UPSELL INTELIGENTE + TOP 3
   Uma única camada atual para estas funções.
   ========================================================= */
#ndCleanUpsell{margin:14px 0 0;padding:15px;border:1px solid rgba(255,101,0,.42);border-radius:18px;background:linear-gradient(145deg,#111114,#09090a);box-shadow:0 12px 35px rgba(0,0,0,.38)}
#ndCleanUpsell .nd-upsell-head{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-bottom:10px}
#ndCleanUpsell .nd-upsell-title{font-size:15px;font-weight:1000;color:#fff}
#ndCleanUpsell .nd-upsell-sub{font-size:10px;color:#888;margin-top:3px}
#ndCleanUpsell .nd-upsell-close{border:0;background:#1b1b1e;color:#aaa;width:32px;height:32px;border-radius:9px;font-size:18px;cursor:pointer}
#ndCleanUpsell .nd-upsell-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:9px}
.nd-clean-up-card{display:grid;grid-template-columns:58px 1fr;gap:8px;align-items:center;padding:8px;border:1px solid #29292e;border-radius:13px;background:#0d0d10}
.nd-clean-up-card img{width:58px;height:58px;object-fit:cover;border-radius:10px;background:#070707}
.nd-clean-up-card strong{display:block;font-size:11px;color:#fff;line-height:1.2}
.nd-clean-up-card .nd-up-why{display:block;color:#888;font-size:9px;margin-top:3px;line-height:1.25}
.nd-clean-up-card .nd-up-price{display:block;color:#ffd166;font-size:12px;font-weight:1000;margin:4px 0 7px}
.nd-clean-up-card button{width:100%;min-height:38px;border:0;border-radius:9px;background:linear-gradient(135deg,#ff6500,#ff9a28);color:#050505;font-size:10px;font-weight:1000;cursor:pointer}
.nd-clean-up-card button.added{background:linear-gradient(135deg,#1fa85b,#25d366);color:#fff}
#ndCleanTop3{width:min(1180px,calc(100% - 28px));margin:14px auto 18px;padding:16px;border:1px solid rgba(255,101,0,.42);border-radius:20px;background:radial-gradient(circle at 80% 0%,rgba(255,101,0,.14),transparent 38%),linear-gradient(145deg,#0d0d0f,#160b05,#090909);box-shadow:0 12px 40px rgba(0,0,0,.5);overflow:hidden}
#ndCleanTop3 .nd-top3-head{display:flex;justify-content:space-between;align-items:end;gap:12px;margin-bottom:12px}
#ndCleanTop3 .nd-top3-kicker{font-size:9px;font-weight:1000;letter-spacing:2px;color:#ff8b3d}
#ndCleanTop3 h2{margin:3px 0 0!important;border:0!important;padding:0!important;color:#fff!important;font-size:24px!important}
#ndCleanTop3 .nd-top3-note{color:#888;font-size:10px;text-align:right}
#ndCleanTop3 .nd-top3-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:10px}
.nd-top3-card{display:grid;grid-template-columns:72px 1fr auto;gap:9px;align-items:center;padding:9px;border:1px solid rgba(255,101,0,.22);border-radius:14px;background:rgba(8,8,9,.9)}
.nd-top3-card img{width:72px;height:72px;object-fit:cover;border-radius:10px;background:#050505}
.nd-top3-card strong{display:block;font-size:12px;color:#fff;line-height:1.2}
.nd-top3-card .nd-top3-price{display:block;color:#ffd166;font-size:13px;font-weight:1000;margin-top:4px}
.nd-top3-card small{display:block;color:#888;font-size:9px;margin-top:3px}
.nd-top3-card button{border:0;border-radius:9px;background:linear-gradient(135deg,#ff6500,#ff9d2e);color:#050505;font-size:10px;font-weight:1000;padding:10px 9px;cursor:pointer}
.nd-top3-card button.added{background:#25d366;color:#fff}
@media(max-width:700px){#ndCleanTop3{width:calc(100% - 14px);padding:13px}.nd-top3-head{align-items:flex-start!important;flex-direction:column}.nd-top3-note{text-align:left!important}.nd-top3-grid{display:flex!important;overflow-x:auto;padding-bottom:3px}.nd-top3-card{min-width:280px}.nd-clean-up-grid{grid-template-columns:1fr!important}}
@media(max-width:520px){#ndCleanUpsell .nd-upsell-grid{display:flex;overflow-x:auto;padding-bottom:3px}.nd-clean-up-card{min-width:250px}.nd-clean-up-card img{width:62px;height:62px}}
</style></head>
<body>
<!-- ND R17: horário comercial real — terça a domingo, 18:00 às 00:30 -->
<header>
<img alt="ND BURGS" class="logo" src="https://i.ibb.co/5gsVbBcb/corretooo.jpg"/>
</header>
<section class="nd-v4-hero">
<div class="nd-v4-hero-glow"></div>
<div class="nd-v4-hero-content">
<span class="nd-v4-kicker">🔥 PEDIDOS ONLINE</span>
<h1>EAI,<br/><em>BORA DE #NDBURGS.</em></h1>
<p>Escolha seus favoritos, monte seu pedido e envie direto para a ND BURGS.</p>
<div class="nd-v4-hero-actions">
<button class="nd-v4-primary" onclick="document.getElementById('combos')?.scrollIntoView({behavior:'smooth'})" type="button">PEDIR AGORA <span>→</span></button>
<button class="nd-v4-secondary" onclick="document.getElementById('combos')?.scrollIntoView({behavior:'smooth'})" type="button">VER CARDÁPIO</button>
</div>
<div class="nd-v4-trustline">
<span>🛵 DELIVERY</span><span>🏪 RETIRADA</span><span>📲 WHATSAPP</span>
</div>
</div>
<div aria-hidden="true" class="nd-v4-hero-art">
<div class="nd-v4-art-ring"></div>
<img alt="Hambúrguer ND BURGS" class="nd-v4-art-burger" src="https://i.ibb.co/nMmfSSt1/Chat-GPT-Image-28-de-jul-de-2026-22-33-11.png"/>
<div class="nd-v4-art-price">PEÇA<br/><strong>AGORA</strong></div>
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
<div class="status-aberto" id="statusHorario">🟢 ABERTO AGORA • PEDIDOS 24H</div>
</div>
</div>
<div class="container">
<h1>🍔 FAÇA SEU PEDIDO</h1>
<div class="modern-search"><input aria-label="Buscar produtos" autocomplete="off" id="buscaProdutos" placeholder="🔎 Buscar lanche, combo, açaí, pastel, bebida..." type="search"/><span class="search-count" id="contadorBusca"></span></div>
<div class="no-results" id="semResultados">😕 Nenhum produto encontrado.<br/><small>Tente outro nome ou categoria.</small></div>
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
🍨 AÇAÍS - MILKSHAKES E SOBREMESAS
</button>
<button class="categoria-btn" onclick="irPara('adicionais')">
➕ ADICIONAIS
</button>
</div>
<section class="categoria" id="combos">
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
</section>
<div class="carrinho" id="checkout">
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
<input id="nome" placeholder="Digite seu nome" type="text"/>
<label>Telefone</label>
<input id="telefone" placeholder="Digite seu telefone" type="tel"/>
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
<div class="address-search-wrap"><input autocomplete="off" id="ruaBusca" placeholder="🔎 Pesquisar sua rua" type="search"/><small>Digite parte do nome para encontrar mais rápido.</small></div>
<select id="rua" onchange="calcularTaxa()">
<option value="">
Selecione sua rua
</option>
</select>
<label>Número</label>
<input id="numero" placeholder="Número da residência" type="text"/>
<label>Complemento</label>
<input id="complemento" placeholder="Apartamento, casa, bloco..." type="text"/>
<div class="aviso-taxa" id="avisoTaxa"></div>
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
<input id="troco" placeholder="Ex: 50" step="0.01" type="number"/>
</div>
<label>Observação</label>
<textarea id="observacao" placeholder="Ex: Sem cebola, tocar campainha..."></textarea>
<button class="btn btn-whatsapp" onclick="finalizarPedido()">
📲 ENVIAR PEDIDO PELO WHATSAPP
</button>
<button class="btn btn-limpar" onclick="limparCarrinho()">
🗑️ LIMPAR CARRINHO
</button>
</div>
</div>
<!-- CARRINHO FLUTUANTE -->
<div class="carrinho-flutuante" id="carrinhoFlutuante">
<div class="carrinho-flutuante-info">
<strong>
🛒 SEU CARRINHO
</strong>
<span id="contadorCarrinho">
0 itens
</span>
</div>
<div class="carrinho-flutuante-direita">
<strong class="carrinho-flutuante-total" id="totalCarrinhoFlutuante">
R$ 0,00
</strong>
<button class="btn-ver-carrinho" onclick="abrirCarrinho()" type="button">
VER CARRINHO
</button>
</div>
</div>
<!-- MODAL CARRINHO -->
<div class="modal-carrinho" id="modalCarrinho" onclick="fecharCarrinho(event)">
<div class="painel-carrinho" onclick="event.stopPropagation()">
<div class="cabecalho-carrinho">
<h2>
🛒 SEU PEDIDO
</h2>
<button class="fechar-carrinho" onclick="fecharCarrinho()">
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
<button class="btn btn-continuar-comprando" onclick="irParaCheckout()">
❤️ CONTINUAR COMPRANDO
</button>
<button class="btn btn-finalizar-pedido" onclick="irParaFinalizarPedido()">
📲 FINALIZAR PEDIDO
</button>
</div>
</div>
<!-- MODAL FINALIZAR PEDIDO -->
<div class="modal-finalizar" id="modalFinalizar" onclick="fecharModalFinalizar(event)">
<div class="painel-finalizar" onclick="event.stopPropagation()">
<div class="cabecalho-finalizar">
<h2>
📍 DADOS DO PEDIDO
</h2>
<button class="btn-fechar-finalizar" onclick="fecharModalFinalizar()">
×
</button>
</div>
<label>
Nome
</label>
<input id="nomeModal" placeholder="Digite seu nome" type="text"/>
<label>
Telefone
</label>
<input id="telefoneModal" placeholder="Digite seu telefone" type="tel"/>
<label>
Tipo do pedido
</label>
<select id="tipoPedidoModal" onchange="alterarTipoPedidoModal()">
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
<select id="ruaModal" onchange="calcularTaxaModal()">
<option value="">
Selecione sua rua
</option>
</select>
<label>
Número
</label>
<input id="numeroModal" placeholder="Número da residência" type="text"/>
<label>
Complemento
</label>
<input id="complementoModal" placeholder="Apartamento, casa, bloco..." type="text"/>
<div class="aviso-taxa" id="avisoTaxaModal"></div>
</div>
<label>
Forma de pagamento
</label>
<select id="pagamentoModal" onchange="alterarPagamentoModal()">
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
<div id="trocoAreaModal" style="display:none;">
<label>
Troco para quanto?
</label>
<input id="trocoModal" placeholder="Ex: 50" step="0.01" type="number"/>
</div>
<label>
Observação
</label>
<textarea id="observacaoModal" placeholder="Ex: Sem cebola, tocar campainha..."></textarea>
<div class="resumo-modal" style="margin-top:18px;">
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
<button class="btn btn-finalizar-modal" onclick="finalizarPedidoModal()">
📲 CLIQUE PARA CONFIRMAR PEDIDO 
</button>
</div>
</div>
<!-- MODAL PERSONALIZAÇÃO -->
<div class="modal-personalizacao" id="modalPersonalizacao">
<div class="modal-box">
<div class="modal-topo">
<h2 id="modalTitulo">
Personalizar
</h2>
<button class="modal-fechar" onclick="fecharPersonalizacao()">
×
</button>
</div>
<div id="modalConteudo"></div>
</div>
</div>
<div class="suggestions-modal" id="suggestionsModal" onclick="fecharSugestoes(event)"><div class="suggestions-panel" onclick="event.stopPropagation()"><div class="suggestions-head"><div><h2>❤️ QUE TAL LEVAR MAIS UM?</h2><small style="color:#999">Escolha uma sugestão e adicione ao pedido.</small></div><button class="suggestions-close" onclick="fecharSugestoes()">×</button></div><div class="suggestions-grid" id="suggestionsGrid"></div><button class="btn btn-finalizar-pedido" onclick="fecharSugestoes()" style="margin-top:12px">CONTINUAR PARA O PEDIDO</button></div></div>
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
<a class="instagram-botao" href="https://www.instagram.com/ndburgs/" rel="noopener noreferrer" target="_blank">
📲 SEGUIR NO INSTAGRAM
</a>
</div>
<div class="rodape-final">

ND BURGS © 2026
<br/>
Obrigado pela preferência ❤️
SITE 100% DESENVOLVIDO POR @NEEHDIINIZ

</div>
</footer>
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
  dadosIds.forEach(id=>{const el=document.getElementById(id); if(!el)return; const k='ndburgs_'+id; try{el.value|| (el.value=localStorage.getItem(k)||''); el.addEventListener('input',()=>localStorage.setItem(k,el.value));}catch(e){}});
})();

</script>
<!-- =========================
     ND BURGS — MELHORIAS PRO 2.0
========================= -->


<div aria-live="polite" class="nd-toast" id="ndToast" role="status"></div>
<button aria-label="Voltar ao topo" class="nd-backtop" id="ndBackTop">↑</button>

<script>
(function(){
  'use strict';
  const MIN_PEDIDO=11.90;
  const favKey='ndburgs_favoritos_v2';
  const favs=new Set(JSON.parse(localStorage.getItem(favKey)||'[]'));
  let toastTimer;
  function toast(msg){
    const el=document.getElementById('ndToast'); if(!el)return;
    el.textContent=msg; el.classList.add('show'); clearTimeout(toastTimer);
    toastTimer=setTimeout(()=>el.classList.remove('show'),2300);
  }
  window.ndToast=toast;
  function saveFavs(){localStorage.setItem(favKey,JSON.stringify([...favs]));}
  function productId(card,i){return (card.dataset.nome||card.querySelector('h3')?.textContent||'produto-'+i).trim().toUpperCase();}
  function addFavButtons(){
    document.querySelectorAll('.produto').forEach((card,i)=>{
      if(card.dataset.ndEnhanced==='1')return;
      card.dataset.ndEnhanced='1';
      const id=productId(card,i); card.dataset.ndPid=id;
      const b=document.createElement('button'); b.className='nd-fav'+(favs.has(id)?' ativo':''); b.type='button'; b.title='Favoritar'; b.setAttribute('aria-label','Favoritar '+id); b.textContent=favs.has(id)?'♥':'♡';
      b.onclick=(e)=>{e.stopPropagation(); if(favs.has(id)){favs.delete(id);b.classList.remove('ativo');b.textContent='♡';toast('Removido dos favoritos')}else{favs.add(id);b.classList.add('ativo');b.textContent='♥';toast('❤️ Adicionado aos favoritos')} saveFavs();};
      card.appendChild(b);
    });
  }
  function buildCategories(){
    const nav=document.getElementById('ndCategoryNav'); if(!nav)return;
    const cats=[...document.querySelectorAll('.categoria')]; nav.innerHTML='';
    cats.forEach((cat,i)=>{
      if(!cat.id)cat.id='nd-cat-'+i;
      const title=cat.querySelector('.categoria-titulo,h2'); if(!title)return;
      const b=document.createElement('button'); b.className='nd-cat-btn'; b.type='button'; b.textContent=title.textContent.replace(/[\n\r]+/g,' ').trim();
      b.onclick=()=>document.getElementById(cat.id)?.scrollIntoView({behavior:'smooth',block:'start'}); nav.appendChild(b);
    });
  }
  function refreshEmptyCategories(){
    document.querySelectorAll('.categoria').forEach(cat=>{
      const cards=[...cat.querySelectorAll('.produto')];
      const visible=cards.some(x=>getComputedStyle(x).display!=='none');
      cat.style.display=visible?'':'none';
    });
    const cards=[...document.querySelectorAll('.produto')];
    const any=cards.some(x=>getComputedStyle(x).display!=='none');
    let e=document.getElementById('ndEmptySearch');
    if(!e){e=document.createElement('div');e.id='ndEmptySearch';e.className='nd-empty-search';e.innerHTML='<strong>NÃO ENCONTRAMOS ESSE PRODUTO 😕</strong><span>Tente outro nome ou veja uma categoria diferente.</span>';document.querySelector('.container')?.appendChild(e)}
    e.style.display=any?'none':'';
  }
  function enhanceSearch(){
    const input=document.getElementById('buscaProdutos'); if(!input||input.dataset.ndSearch==='1')return;
    input.dataset.ndSearch='1';
    input.addEventListener('input',()=>setTimeout(refreshEmptyCategories,0));
  }
  function updateProgress(){
    const carts=typeof carrinho!=='undefined' ? carrinho : (window.carrinho||[]);
    const subtotal=(carts||[]).reduce((s,x)=>s+(Number(x.preco)||0)*(Number(x.quantidade)||1),0);
    document.querySelectorAll('.nd-cart-progress').forEach(x=>x.remove());
    const targets=[document.querySelector('.painel-carrinho'),document.getElementById('carrinho')].filter(Boolean);
    targets.forEach(t=>{
      const box=document.createElement('div');box.className='nd-cart-progress';
      const pct=Math.min(100,(subtotal/MIN_PEDIDO)*100);
      box.innerHTML=subtotal>=MIN_PEDIDO?'<b>✓ Pedido mínimo atingido!</b>':'Falta <b>'+moeda(Math.max(0,MIN_PEDIDO-subtotal))+'</b> para atingir o pedido mínimo de '+moeda(MIN_PEDIDO)+'<div class="nd-progress-track"><div class="nd-progress-bar" style="width:'+pct+'%"></div></div>';
      t.prepend(box);
    });
  }
  window.ndUpdateProgress=updateProgress;
  const oldAtualizar=window.atualizarCarrinho;
  if(typeof oldAtualizar==='function'){
    window.atualizarCarrinho=function(){const r=oldAtualizar.apply(this,arguments);setTimeout(updateProgress,20);return r;};
  }
  const back=document.getElementById('ndBackTop');
  window.addEventListener('scroll',()=>back?.classList.toggle('show',window.scrollY>600),{passive:true});
  back?.addEventListener('click',()=>window.scrollTo({top:0,behavior:'smooth'}));
  document.addEventListener('click',e=>{
    const btn=e.target.closest('.btn-add');
    if(btn){btn.style.transform='scale(.96)';setTimeout(()=>btn.style.transform='',120);}
  });
  document.addEventListener('keydown',e=>{if(e.key==='Escape'){document.querySelectorAll('.nd-toast.show').forEach(x=>x.classList.remove('show'));}});
  document.addEventListener('DOMContentLoaded',()=>{addFavButtons();buildCategories();enhanceSearch();refreshEmptyCategories();updateProgress();});
  setTimeout(()=>{addFavButtons();buildCategories();enhanceSearch();refreshEmptyCategories();updateProgress();},700);


  // Salva dados básicos digitados para facilitar o próximo pedido.
  ['nome','telefone','nomeModal','telefoneModal'].forEach(id=>{
    const el=document.getElementById(id); if(!el)return;
    const key='ndburgs_'+id;
    const saved=localStorage.getItem(key); if(saved&&!el.value)el.value=saved;
    el.addEventListener('change',()=>localStorage.setItem(key,el.value.trim()));
  });
})();
</script>


<script id="nd-v4-logic">
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
  if(Array.isArray(window.carrinho)) window.carrinho.length=0;
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
    <button class="nd-v4-next" type="button" onclick="ndNext(3)">CONFIRA SEU ITENS DO PEDIDO ANTES DE FINALIZAR→</button>
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
 const fee=tipo==='ENTREGA'?Number(window.taxas?.[rua]||0):0, sub=subtotal();
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
 const fee=tipo==='ENTREGA'?Number(window.taxas?.[rua]||0):0, sub=subtotal(), total=sub+fee;
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
</script>

<script id="nd-final-logic">
(function(){
'use strict';
const ORANGE='var(--fx-orange)';
const reviewKey='ndburgs_avaliacoes_local_v1';
let reviewStars=0;
function q(s){return document.querySelector(s)}
function qa(s){return [...document.querySelectorAll(s)]}
function money(v){return Number(v||0).toLocaleString('pt-BR',{style:'currency',currency:'BRL'})}
function getCart(){try{return (typeof carrinho!=='undefined'&&Array.isArray(carrinho))?carrinho:[]}catch(e){return []}}
function cartQty(){return getCart().reduce((s,i)=>s+(Number(i.quantidade)||0),0)}
function cartSub(){return getCart().reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||0),0)}
function safeText(v){return String(v||'').replace(/[&<>"']/g,m=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#039;'}[m]))}

/* Remove as camadas antigas de UI que duplicavam o layout, sem tocar na lógica do carrinho. */
function buildIntro(){
 if(q('#ndFxIntro'))return;
 const c=q('.container'); if(!c)return;
 const d=document.createElement('section');d.id='ndFxIntro';
 d.innerHTML='<div class="ndFx-kicker">ND BURGS • PEDIDOS ONLINE</div><div class="ndFx-title">OBRIGADO POR ESTAR AQUI<br><span>#BORA DE NDBURGS.</span></div><div class="ndFx-sub">Escolha a categoria, ajuste a quantidade e adicione ao carrinho. Tudo em uma tela rápida e direta.</div><div class="ndFx-actions"><button class="ndFx-action primary" type="button" onclick="irPara(\'combos\')">🔥 VER MAIS VENDIDOS</button><button class="ndFx-action" type="button" onclick="document.getElementById(\'ndFxReviews\')?.scrollIntoView({behavior:\'smooth\'})">⭐ AVALIAR A ND</button></div>';
 c.insertBefore(d,c.firstElementChild);
}
function setupCard(card){
 if(card.dataset.ndFxReady==='1')return;
 const old=card.querySelector('.btn-add'); if(!old)return;
 card.dataset.ndFxReady='1';
 const onclick=old.getAttribute('onclick')||'';
 const h3=card.querySelector('h3'); const priceEl=card.querySelector('.preco');
 let name=(h3?.textContent||'PRODUTO').trim();
 let price=0; const pm=(priceEl?.textContent||'').match(/R\$\s*([\d\.]+,[\d]{2})/); if(pm)price=parseFloat(pm[1].replace('.','').replace(',','.'));
 const custom=/abrirPersonalizacao\s*\(/.test(onclick);
 card.dataset.ndFxName=name; card.dataset.ndFxPrice=String(price); card.dataset.ndFxCustom=custom?'1':'0';
 old.style.display='none';
 const row=document.createElement('div');row.className='nd-fx-buyrow';
 row.innerHTML='<div class="nd-fx-qty"><button type="button" class="nd-fx-minus">−</button><span class="nd-fx-q">1</span><button type="button" class="nd-fx-plus">+</button></div><button type="button" class="nd-fx-add">ADICIONAR</button>';
 card.appendChild(row);
 const qEl=row.querySelector('.nd-fx-q');
 function setQty(n){n=Math.max(1,Math.min(99,n));qEl.textContent=n}
 row.querySelector('.nd-fx-minus').onclick=e=>{e.stopPropagation();setQty(Number(qEl.textContent)-1)};
 row.querySelector('.nd-fx-plus').onclick=e=>{e.stopPropagation();setQty(Number(qEl.textContent)+1)};
 row.querySelector('.nd-fx-add').onclick=e=>{
  e.stopPropagation(); const qty=Math.max(1,Number(qEl.textContent)||1);
  if(custom){
    window.ndPendingQty=qty;
    const key=(onclick.match(/abrirPersonalizacao\(['"]([^'"]+)/)||[])[1];
    if(key&&typeof window.abrirPersonalizacao==='function')window.abrirPersonalizacao(key);
  }else{
    if(name&&price>0&&typeof window.adicionar==='function'){
      for(let i=0;i<qty;i++)window.adicionar(name,price);
    }else if(onclick){try{Function(onclick).call(old)}catch(_){}}
  }
  setQty(1);
 };
}
function addBadges(){
 qa('.categoria').forEach((cat,ci)=>{
  const cards=qa('.produto',cat);if(!cards.length)return;
  let idx=0;
  try{
   const key='ndburgs_bestseller_'+cat.id; const saved=localStorage.getItem(key);
   if(saved!==null && Number(saved)<cards.length) idx=Number(saved); else {idx=(Math.floor(Math.random()*cards.length));localStorage.setItem(key,String(idx));}
  }catch(_){idx=(ci*3)%cards.length}
  const card=cards[idx]; if(card&&!card.querySelector('.nd-fx-bestseller')){const b=document.createElement('div');b.className='nd-fx-bestseller';b.textContent='MAIS VENDIDO DO DIA';card.appendChild(b)}
 });
}
function buildCartBar(){
 if(q('#ndFxCartbar'))return;
 const b=document.createElement('div');b.id='ndFxCartbar';b.className='nd-fx-cartbar';
 b.innerHTML='<div class="nd-fx-cart-icon">🛒</div><div class="nd-fx-cart-info"><strong id="ndFxCartQty">0 itens</strong><span>Seu pedido está salvo neste aparelho</span></div><div id="ndFxCartTotal" class="nd-fx-cart-total">R$ 0,00</div><button type="button" class="nd-fx-cart-open" onclick="abrirCarrinho()">VER CARRINHO</button>';
 document.body.appendChild(b);
}
function refreshCartBar(){
 const b=q('#ndFxCartbar');if(!b)return;const qty=cartQty(),sub=cartSub();b.classList.toggle('show',qty>0);q('#ndFxCartQty').textContent=qty+' '+(qty===1?'item':'itens');q('#ndFxCartTotal').textContent=money(sub);
}
/* Corrige o conflito V4: ele precisa enxergar a variável lexical carrinho real. */
function patchFinalize(){
 if(typeof window.irParaFinalizarPedido==='function'&&!window.irParaFinalizarPedido.__ndFx){
  const oldOpen=window.irParaFinalizarPedido;
  window.irParaFinalizarPedido=function(){if(getCart().length===0)return alert('Seu carrinho está vazio.');return oldOpen.apply(this,arguments)};
  window.irParaFinalizarPedido.__ndFx=true;
 }
 if(typeof window.finalizarPedidoModal==='function'&&!window.finalizarPedidoModal.__ndFx){
  const oldFinish=window.finalizarPedidoModal;
  window.finalizarPedidoModal=function(){if(getCart().length===0)return alert('Seu carrinho está vazio.');return oldFinish.apply(this,arguments)};
  window.finalizarPedidoModal.__ndFx=true;
 }
}
/* Quantidade escolhida no card para produtos personalizáveis. */
function patchPersonalization(){
 try{
  const src=document.documentElement.innerHTML;
 }catch(_){ }
}
function buildReviews(){
 if(q('#ndFxReviews'))return;
 const footer=q('footer'); if(!footer)return;
 const sec=document.createElement('section');sec.id='ndFxReviews';
 sec.innerHTML='<div class="ndFx-review-head"><div><div class="ndFx-kicker">SUA OPINIÃO IMPORTA</div><h2>⭐ AVALIE A ND BURGS</h2></div><p>Conte como foi seu pedido. A avaliação fica salva neste aparelho e você também pode enviar para a loja pelo WhatsApp.</p></div><div class="ndFx-stars" role="radiogroup" aria-label="Nota"><button class="ndFx-star" data-star="1">★</button><button class="ndFx-star" data-star="2">★</button><button class="ndFx-star" data-star="3">★</button><button class="ndFx-star" data-star="4">★</button><button class="ndFx-star" data-star="5">★</button></div><textarea id="ndFxComment" placeholder="Deixe seu comentário sobre o pedido..."></textarea><button class="ndFx-review-send" type="button" id="ndFxSendReview">ENVIAR AVALIAÇÃO ⭐</button><div id="ndFxReviewList"></div>';
 footer.parentNode.insertBefore(sec,footer);
 qa('.ndFx-star').forEach(st=>st.onclick=()=>{reviewStars=Number(st.dataset.star);qa('.ndFx-star').forEach(x=>x.classList.toggle('on',Number(x.dataset.star)<=reviewStars))});
 q('#ndFxSendReview').onclick=sendReview;renderReviews();
}
function loadReviews(){try{const a=JSON.parse(localStorage.getItem(reviewKey)||'[]');return Array.isArray(a)?a:[]}catch(_){return[]}}
function renderReviews(){const list=q('#ndFxReviewList');if(!list)return;const arr=loadReviews();list.innerHTML=arr.slice(-5).reverse().map(r=>'<div class="ndFx-review"><strong>'+('★'.repeat(r.stars))+'</strong><p>'+safeText(r.comment)+'</p><small>'+safeText(r.date)+'</small></div>').join('')}
function sendReview(){
 if(!reviewStars)return alert('Escolha uma nota de 1 a 5 estrelas.');
 const comment=(q('#ndFxComment')?.value||'').trim();if(!comment)return alert('Escreva um comentário antes de enviar.');
 const arr=loadReviews();arr.push({stars:reviewStars,comment,date:new Date().toLocaleDateString('pt-BR')});try{localStorage.setItem(reviewKey,JSON.stringify(arr))}catch(_){ }
 renderReviews();
 const msg='⭐ *AVALIAÇÃO — ND BURGS*\n\nNota: '+reviewStars+'/5\nComentário: '+comment;
 const wa='5511963973846';
 window.open('https://wa.me/'+wa+'?text='+encodeURIComponent(msg),'_blank');
 q('#ndFxComment').value='';reviewStars=0;qa('.ndFx-star').forEach(x=>x.classList.remove('on'));
}
function init(){
 buildIntro();buildCartBar();
 qa('.produto').forEach(setupCard);addBadges();buildReviews();patchFinalize();
 refreshCartBar();
 /* atualiza depois que a lógica original do carrinho terminar */
 if(typeof window.atualizarCarrinho==='function'&&!window.atualizarCarrinho.__ndFxCart){
  const old=window.atualizarCarrinho;window.atualizarCarrinho=function(){const r=old.apply(this,arguments);setTimeout(refreshCartBar,0);return r};window.atualizarCarrinho.__ndFxCart=true;
 }
 setTimeout(()=>{qa('.produto').forEach(setupCard);addBadges();refreshCartBar();patchFinalize()},500);
}
window.addEventListener('DOMContentLoaded',init);
setTimeout(init,900);
})();
</script>


<!-- =========================================================
     ND BURGS — RODADA 5
     EXPERIÊNCIA PREMIUM + PERFORMANCE
     Camada adicional sobre a RODADA 4 — não substitui funções existentes.
     ========================================================= -->

<script id="nd-rodada-5-performance">
(function(){
  'use strict';
  if(window.__NDBURGS_R5__) return;
  window.__NDBURGS_R5__=true;

  const HERO_IMG='https://i.ibb.co/nMmfSSt1/Chat-GPT-Image-28-de-jul-de-2026-22-33-11.png';
  const $=(s,c=document)=>c.querySelector(s);
  const $$=(s,c=document)=>Array.from(c.querySelectorAll(s));

  function addPreload(){
    if(document.head.querySelector('link[data-nd-r5-hero]')) return;
    const l=document.createElement('link');
    l.rel='preload'; l.as='image'; l.href=HERO_IMG; l.setAttribute('data-nd-r5-hero','1');
    document.head.appendChild(l);
  }

  function optimizeImages(){
    $$('img').forEach((img,i)=>{
      if(!img.hasAttribute('decoding')) img.decoding='async';
      const isHero=img.classList.contains('nd-v4-art-burger') || img.src===HERO_IMG;
      if(isHero){ img.loading='eager'; img.fetchPriority='high'; img.setAttribute('fetchpriority','high'); }
      else if(!img.closest('header') && !img.hasAttribute('loading')) img.loading='lazy';
    });
  }

  function buildLoader(){
    if($('#ndR5Loader')) return;
    const el=document.createElement('div');
    el.id='ndR5Loader'; el.className='nd-r5-loader';
    el.innerHTML='<div class="nd-r5-loader-box"><div class="nd-r5-loader-mark"></div><span>CARREGANDO ND BURGS</span></div>';
    document.body.prepend(el);
    const hide=()=>setTimeout(()=>el.classList.add('hide'),120);
    if(document.readyState==='complete') hide(); else window.addEventListener('load',hide,{once:true});
    setTimeout(hide,1800);
  }


  function setupReveal(){
    const cards=$$('.produto');
    if(!('IntersectionObserver' in window)) return;
    const io=new IntersectionObserver((entries,obs)=>{
      entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('nd-r5-visible');obs.unobserve(e.target)}});
    },{rootMargin:'120px 0px',threshold:.01});
    cards.forEach((c,i)=>{ if(i<8)return; c.classList.add('nd-r5-reveal'); io.observe(c); });
  }

  function setupCategoryActive(){
    const sections=$$('.categoria[id]');
    const buttons=$$('.categoria-btn');
    if(!sections.length||!buttons.length||!('IntersectionObserver' in window)) return;
    const map=new Map(buttons.map(b=>{const m=(b.getAttribute('onclick')||'').match(/irPara\(['"]([^'"]+)/);return [m?m[1]:null,b]}));
    const io=new IntersectionObserver(entries=>{
      entries.forEach(e=>{
        if(e.isIntersecting){
          buttons.forEach(b=>b.classList.remove('nd-r5-active'));
          const b=map.get(e.target.id); if(b)b.classList.add('nd-r5-active');
        }
      });
    },{rootMargin:'-35% 0px -55% 0px',threshold:0});
    sections.forEach(s=>io.observe(s));
  }

  function setupSearchCounter(){
    const input=$('#buscaProdutos'),count=$('#contadorBusca');
    if(!input||!count)return;
    const update=()=>{
      const visible=$$('.produto').filter(c=>!c.classList.contains('search-hidden')).length;
      const q=input.value.trim(); count.textContent=q?(visible+' resultado'+(visible===1?'':'s')):'';
    };
    input.addEventListener('input',()=>setTimeout(update,0),{passive:true});
    update();
  }

  function setupButtonFeedback(){
    document.addEventListener('click',e=>{
      const btn=e.target.closest('.btn-add,.nd-fx-add,.nd-r3-add');
      if(!btn||btn.disabled)return;
      if(btn.dataset.ndR5Busy==='1')return;
      btn.dataset.ndR5Busy='1';
      const original=btn.textContent.trim();
      if(/ADICIONAR|ESCOLHER|COMPRAR/i.test(original) && !/ESCOLHER SABOR/i.test(original)){
        btn.textContent='✓ ADICIONADO';
        setTimeout(()=>{btn.textContent=original;btn.dataset.ndR5Busy='0'},650);
      }else setTimeout(()=>{btn.dataset.ndR5Busy='0'},120);
    },{passive:true});
  }

  function setupKeyboardAndScroll(){
    document.addEventListener('keydown',e=>{
      if(e.key==='Escape'){
        const open=$$('.modal-carrinho.ativo,.modal-finalizar.ativo,.modal-personalizacao.ativo,.suggestions-modal.show');
        if(!open.length)return;
      }
    });
    let ticking=false;
    window.addEventListener('scroll',()=>{
      if(ticking)return;
      ticking=true;
      requestAnimationFrame(()=>{ticking=false});
    },{passive:true});
  }

  function markCartChanges(){}

  function init(){
    addPreload(); optimizeImages(); buildLoader(); setupReveal(); setupCategoryActive(); setupSearchCounter(); setupButtonFeedback(); setupKeyboardAndScroll(); markCartChanges();
    setTimeout(()=>{optimizeImages();setupReveal();setupCategoryActive();setupSearchCounter();markCartChanges()},900);
    setTimeout(()=>{markCartChanges()},1800);
  }

  if(document.readyState==='loading') document.addEventListener('DOMContentLoaded',init,{once:true}); else init();
})();
</script>
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


<!-- ND BURGS VERSION: 20260905-R13 -->
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

<div aria-modal="true" id="nd17Gate" role="dialog">
<div class="nd17-gate-panel">
<div class="nd17-kicker">ANTES DE MONTAR SEU PEDIDO</div>
<h2>Onde vamos entregar?</h2>
<p>Informe seu endereço agora. Assim a taxa de entrega já aparece no carrinho, na revisão e no pedido enviado para a ND BURGS.</p>
<div class="nd17-field nd17-suggest"><label>Rua / endereço</label><input autocomplete="off" id="nd17GateStreet" placeholder="Digite o nome da rua" type="search"/><div class="nd17-list" id="nd17GateList"></div></div>
<div class="nd17-field"><label>Número</label><input id="nd17GateNumber" inputmode="numeric" placeholder="Número da residência" type="text"/></div>
<button class="nd17-gate-main" id="nd17GateSave" type="button">CONTINUAR COM DELIVERY</button>
<button class="nd17-gate-retirada" id="nd17GatePickup" type="button">VOU RETIRAR NO LOCAL</button>
</div>
</div>

<!-- ND BURGS ETAPA 18 - CATEGORIAS LATERAIS -->




<!-- =========================================================
     ND BURGS — ETAPA 23 — RECONSTRUÇÃO FINAL DA EXPERIÊNCIA
     Corrige carrinho, checkout, endereço, categorias e visual.
     Camada isolada: não substitui a lógica de produtos.
     ========================================================= -->



<!-- =========================================================
     ND BURGS 2.0 — AVALIAÇÕES + CARRINHO ÚNICO + MAIS VENDIDOS
     Camada final: mantém a lógica existente e adiciona somente UI/UX.
     ========================================================= -->


<!-- =========================================================
     ND BURGS R11 — COMBOS 100% CONFIGURÁVEIS + NOVA NAVEGAÇÃO
     ========================================================= -->

<script id="nd-r11-combos-js">
(function(){
'use strict';
const DRINKS=['SPRITE','COCA-COLA LATA','COCA-COLA LATA ZERO','FANTA UVA','FANTA LARANJA','GUARANÁ ANTARCTICA','ÁGUA MINERAL'];
const TRAD=['X-SALADA','X-BURGUER','X-EGG','X-BACON'];
const ART=['GAROTINHO','DINA','GADEIA','PATÃO','BERENICE'];
const SAUCES=['CHEDDAR','BARBECUE','CATUPIRY','MAIONESE','MOSTARDA','KETCHUP','MAIONESE VERDE'];
const ADDONS=[
 ['MAIONESE ARTESANAL','3.00','https://i.ibb.co/Y4DcTLwD/maionese-artesanal.png'],
 ['MOLHO CHEDDAR','3.00','https://i.ibb.co/cHt8ZjS/adicional-molho-cheddar.png'],
 ['POTINHO BARBECUE','3.00','https://i.ibb.co/n8KHqTMg/potinho-barbecue.png'],
 ['BACON','3.00','https://i.ibb.co/6RxLhQBG/adicional-bacon.png'],
 ['POTINHO CHEDDAR','3.00','https://i.ibb.co/DHNQ0kwS/potinho-cheddar.png'],
 ['HAMBURGUER EXTRA ARTESANAL','9.00','https://i.ibb.co/wZfS9rn1/hamburguer-artesanal.png'],
 ['POTINHO MAIONESE VERDE','3.00','https://i.ibb.co/DDCZpVLW/potinho-maionese-verde.png'],
 ['FATIA QUEIJO CHEDDAR EXTRA','3.00','https://i.ibb.co/ZRydT4hD/fatia-de-queijo.png']
];
const configs={
 'COMBO MAIS VENDIDO':{price:20.90,sections:[{type:'burger',title:'ESCOLHA 1 LANCHE',options:TRAD},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA P'},{type:'drink',title:'ESCOLHA 1 REFRIGERANTE LATA',options:DRINKS}]},
 'COMBO DOCE':{price:32.90,sections:[{type:'burger',title:'ESCOLHA 1 LANCHE',options:TRAD},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA P'},{type:'drink',title:'ESCOLHA 1 REFRIGERANTE LATA',options:DRINKS},{type:'fixed',title:'SOBREMESA',value:'1 SURPRESA DE UVA'}]},
 'COMBO GELADO':{price:40.90,sections:[{type:'burger',title:'ESCOLHA 1 LANCHE',options:TRAD},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA P COMPLETA COM CHEDDAR E BACON'},{type:'drink',title:'ESCOLHA 1 REFRIGERANTE LATA',options:DRINKS},{type:'acai',title:'AÇAÍ 300ML — ESCOLHA OS ACOMPANHAMENTOS'}]},
 'COMBO 5 ESTRELAS':{price:45.90,sections:[{type:'burger2',title:'ESCOLHA 2 LANCHES',options:TRAD},{type:'fixed',title:'ACOMPANHAMENTOS FIXOS',value:'BATATA M • NUGGETS P • ANEL DE CEBOLA P'},{type:'sauces',title:'ESCOLHA 2 MOLHOS',options:SAUCES}]},
 'COMBO DIETA SÓ SEGUNDA':{price:27.90,sections:[{type:'pastel',title:'ESCOLHA 1 SABOR DE PASTEL',options:'dynamic'},{type:'drink',title:'ESCOLHA 1 REFRIGERANTE LATA',options:DRINKS},{type:'fixed',title:'SOBREMESA',value:'1 SURPRESA DE UVA'}]},
 'COMBO MOTOCA ND':{price:32.90,sections:[{type:'fixed',title:'LANCHE',value:'NUNES'},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA P'},{type:'drink',title:'ESCOLHA 1 REFRIGERANTE LATA',options:DRINKS}]},
 'COMBO SÓ LOVE':{price:71.90,sections:[{type:'burger2',title:'ESCOLHA 2 LANCHES',options:TRAD},{type:'fixed',title:'ACOMPANHAMENTOS FIXOS',value:'BATATA M COM CHEDDAR E BACON • NUGGETS P • ANEL DE CEBOLA P • FRANGO FRITO P'},{type:'sauces',title:'ESCOLHA 2 MOLHOS',options:SAUCES},{type:'fixed',title:'BRINDE',value:'1 DOLLY 2 LITROS'}]},
 'DATE COM NDBURGS':{price:70.90,sections:[{type:'burger2',title:'ESCOLHA 2 LANCHES',options:TRAD},{type:'fixed',title:'SOBREMESA',value:'2 SURPRESAS DE UVA'},{type:'fixed',title:'BRINDE',value:'1 COCA-COLA 600ML'},{type:'acai2',title:'2 AÇAÍS 300ML — ESCOLHA OS ACOMPANHAMENTOS'}]},
 '01 ND BURGS':{price:50.90,sections:[{type:'fixed',title:'LANCHES FIXOS',value:'1 X-BURGUER • 1 X-EGG • 1 X-SALADA • 1 X-BACON'},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA M COMPLETA COM CHEDDAR E BACON'}]},
 'ARTESANAL COMBO MAIS VENDIDO':{price:34.80,sections:[{type:'burger',title:'ESCOLHA 1 LANCHE ARTESANAL',options:ART},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA P'},{type:'drink',title:'ESCOLHA 1 REFRIGERANTE LATA',options:DRINKS}]},
 'ARTESANAL COMBO DOCE':{price:44.80,sections:[{type:'burger',title:'ESCOLHA 1 LANCHE ARTESANAL',options:ART},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA P'},{type:'drink',title:'ESCOLHA 1 REFRIGERANTE LATA',options:DRINKS},{type:'fixed',title:'SOBREMESA',value:'1 SURPRESA DE UVA'}]},
 'ARTESANAL COMBO GELADO':{price:52.80,sections:[{type:'burger',title:'ESCOLHA 1 LANCHE ARTESANAL',options:ART},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA P COMPLETA COM CHEDDAR E BACON'},{type:'drink',title:'ESCOLHA 1 REFRIGERANTE LATA',options:DRINKS},{type:'acai',title:'AÇAÍ 300ML — ESCOLHA OS ACOMPANHAMENTOS'}]},
 'ARTESANAL COMBO 5 ESTRELAS':{price:70.80,sections:[{type:'burger2',title:'ESCOLHA 2 LANCHES ARTESANAIS',options:ART},{type:'fixed',title:'ACOMPANHAMENTOS FIXOS',value:'BATATA M • NUGGETS P • ANEL DE CEBOLA P'},{type:'sauces',title:'ESCOLHA 2 MOLHOS',options:SAUCES}]},
 'ARTESANAL COMBO SÓ LOVE':{price:90.80,sections:[{type:'burger2',title:'ESCOLHA 2 LANCHES ARTESANAIS',options:ART},{type:'fixed',title:'ACOMPANHAMENTOS FIXOS',value:'BATATA M COM CHEDDAR E BACON • NUGGETS P • ANEL DE CEBOLA P • FRANGO FRITO P'},{type:'sauces',title:'ESCOLHA 2 MOLHOS',options:SAUCES},{type:'fixed',title:'BRINDE',value:'1 DOLLY 2 LITROS'}]},
 'ARTESANAL DATE COM NDBURGS':{price:91.80,sections:[{type:'burger2',title:'ESCOLHA 2 LANCHES ARTESANAIS',options:ART},{type:'fixed',title:'SOBREMESA',value:'2 SURPRESAS DE UVA'},{type:'fixed',title:'BRINDE',value:'1 COCA-COLA 600ML'},{type:'acai2',title:'2 AÇAÍS 300ML — ESCOLHA OS ACOMPANHAMENTOS'}]},
 'ARTESANAL MOTOCA ND':{price:41.80,sections:[{type:'fixed',title:'LANCHE FIXO',value:'PÉZÃO'},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA P'},{type:'drink',title:'ESCOLHA 1 REFRIGERANTE LATA',options:DRINKS}]},
 'ARTESANAL 01 ND BURGS':{price:96.80,sections:[{type:'fixed',title:'LANCHES FIXOS',value:'1 GAROTINHO • 1 DINA • 1 GADEIA • 1 PATÃO'},{type:'fixed',title:'ACOMPANHAMENTO',value:'BATATA M COMPLETA COM CHEDDAR E BACON'}]}
};
let current=null;
function norm(v){return String(v||'').toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,' ').trim()}
function esc(v){return String(v||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;')}
function money(v){return Number(v||0).toLocaleString('pt-BR',{style:'currency',currency:'BRL'})}
function ensureModal(){if(document.getElementById('ndComboModal'))return;const m=document.createElement('div');m.id='ndComboModal';m.innerHTML='<div class="r11-combo-panel" onclick="event.stopPropagation()"><div class="r11-combo-head"><div><h2 id="r11ComboTitle"></h2><small>ESCOLHAS OBRIGATÓRIAS • O COMBO SÓ ENTRA NO CARRINHO DEPOIS DE MONTADO</small></div><button class="r11-close" type="button" onclick="fecharComboPersonalizacao()">×</button></div><div id="r11ComboContent"></div></div>';m.addEventListener('click',e=>{if(e.target===m)fecharComboPersonalizacao()});document.body.appendChild(m)}
function optionsHtml(opts,name,prefix){return '<div class="r11-option-grid">'+opts.map((x,i)=>'<div class="r11-option"><input type="radio" id="'+prefix+'_'+i+'" name="'+name+'" value="'+esc(x)+'"><label for="'+prefix+'_'+i+'">'+esc(x)+'</label></div>').join('')+'</div>'}
function addonHtml(prefix){return '<div class="r11-addons" id="'+prefix+'_addons"><div class="r11-bite">🍔 QUER TAL ADICIONAR ITENS NO SEU LANCHE ? E DEIXAR ELE DO JEITO QUE VOCE GOSTA<br><span style="font-size:10px;color:#ffb36d">ESCOLHA SEUS ADICIONAIS</span></div><div class="r11-addon-grid">'+ADDONS.map((a,i)=>'<div class="r11-addon"><input type="checkbox" id="'+prefix+'_a_'+i+'" data-price="'+a[1]+'" data-name="'+esc(a[0])+'"><label for="'+prefix+'_a_'+i+'"><img src="'+a[2]+'" alt="'+esc(a[0])+'"><span>'+esc(a[0])+'</span><br><b>+'+money(a[1])+'</b></label></div>').join('')+'</div><div class="r11-note">Os adicionais são opcionais e entram no valor do combo apenas se forem marcados.</div></div>'}
function sectionHtml(sec,idx){
 const id='r11s'+idx;
 if(sec.type==='fixed')return '<div class="r11-section"><h3>📦 '+esc(sec.title)+'</h3><div class="r11-fixed"><span>FIXO</span><b>'+esc(sec.value)+'</b></div></div>';
 if(sec.type==='drink')return '<div class="r11-section"><h3>🥤 '+esc(sec.title)+'</h3><span class="r11-required">OBRIGATÓRIO • ESCOLHA 1</span>'+optionsHtml(sec.options,id,'r11opt'+idx)+'</div>';
 if(sec.type==='sauces')return '<div class="r11-section"><h3>🥫 '+esc(sec.title)+'</h3><span class="r11-required">OBRIGATÓRIO • MARQUE EXATAMENTE 2</span><div class="r11-sauce-grid">'+sec.options.map((x,i)=>'<div class="r11-sauce"><input type="checkbox" id="'+id+'_'+i+'" name="'+id+'" value="'+esc(x)+'"><label for="'+id+'_'+i+'">'+esc(x)+'</label></div>').join('')+'</div></div>';
 if(sec.type==='pastel')return '<div class="r11-section"><h3>🥟 '+esc(sec.title)+'</h3><span class="r11-required">OBRIGATÓRIO • SEM PASTEL ESPECIAL E SEM DOCES</span>'+optionsHtml((typeof saboresPasteis!=='undefined'?saboresPasteis.salgados:[]).filter(x=>norm(x[0])!=='PASTEL ESPECIAL').map(x=>x[0]),id,'r11opt'+idx)+'</div>';
 if(sec.type==='acai')return '<div class="r11-section"><h3>🥤 '+esc(sec.title)+'</h3><span class="r11-required">OBRIGATÓRIO • 300ML</span><div class="r11-fixed" style="margin-top:9px"><span>FIXO</span><b>AÇAÍ 300ML</b></div>'+acaiChoicesHtml(id,1)+'</div>';
 if(sec.type==='acai2')return '<div class="r11-section"><h3>🥤 '+esc(sec.title)+'</h3><span class="r11-required">OBRIGATÓRIO • 2 AÇAÍS DE 300ML</span>'+acaiChoicesHtml(id+'a',1)+acaiChoicesHtml(id+'b',2)+'</div>';
 if(sec.type==='burger')return '<div class="r11-section"><h3>🍔 '+esc(sec.title)+'</h3><span class="r11-required">OBRIGATÓRIO • ESCOLHA 1</span>'+optionsHtml(sec.options,id,'r11opt'+idx)+addonHtml(id)+'</div>';
 if(sec.type==='burger2')return '<div class="r11-section"><h3>🍔 '+esc(sec.title)+'</h3><span class="r11-required">OBRIGATÓRIO • ESCOLHA 2</span><div style="margin-top:10px;font-size:10px;color:#aaa;font-weight:900">LANCHE 1</div>'+optionsHtml(sec.options,id+'a','r11opt'+idx+'a')+addonHtml(id+'a')+'<div style="margin-top:12px;font-size:10px;color:#aaa;font-weight:900">LANCHE 2</div>'+optionsHtml(sec.options,id+'b','r11opt'+idx+'b')+addonHtml(id+'b')+'<div class="r11-note">Você pode escolher lanches diferentes. Se repetir o mesmo lanche, ele será contabilizado duas vezes.</div></div>';
 return '';
}
function acaiChoicesHtml(id,num){const list=typeof produtosPersonalizaveis!=='undefined'&&produtosPersonalizaveis.acai?produtosPersonalizaveis.acai.acompanhamentos:[];return '<div style="margin-top:10px"><div style="font-size:10px;color:#aaa;font-weight:900;margin-bottom:6px">AÇAÍ '+num+' • ACOMPANHAMENTOS</div><div class="r11-addon-grid">'+list.map((a,i)=>'<div class="r11-addon"><input type="checkbox" id="'+id+'_a_'+i+'" data-name="'+esc(a[0])+'" data-price="'+a[1]+'" data-acai="1"><label for="'+id+'_a_'+i+'"><div style="height:48px;display:grid;place-items:center;font-size:20px">🍓</div><span>'+esc(a[0])+'</span><br><b>'+((a[1]>0)?'+'+money(a[1]):'GRÁTIS')+'</b></label></div>').join('')+'</div><div class="r11-note">Até 3 acompanhamentos normais são grátis, seguindo a regra do açaí do site. Os itens pagos continuam com o valor cadastrado.</div></div>'}
function open(name,price){ensureModal();current={name,price:Number(price),cfg:configs[name]};if(!current.cfg)return;document.getElementById('r11ComboTitle').textContent='🍔 '+name;document.getElementById('r11ComboContent').innerHTML=current.cfg.sections.map(sectionHtml).join('')+'<div class="r11-combo-total"><span>TOTAL DO COMBO</span><strong id="r11ComboTotal">'+money(current.price)+'</strong></div><button class="r11-confirm" type="button" onclick="confirmarComboPersonalizacao()">✅ ADICIONAR AO CARRINHO</button>';const m=document.getElementById('ndComboModal');m.classList.add('show');document.body.style.overflow='hidden';bindDynamic();}
function bindDynamic(){document.querySelectorAll('#r11ComboContent input[type=radio]').forEach(r=>r.addEventListener('change',()=>{const sec=r.closest('.r11-section');const addon=sec?.querySelector('.r11-addons');if(addon){addon.classList.add('show')}}));document.querySelectorAll('#r11ComboContent input[type=checkbox]').forEach(c=>c.addEventListener('change',()=>{if(c.name&&c.closest('.r11-sauce')){const checked=[...document.querySelectorAll('input[name="'+c.name+'"]:checked')];if(checked.length>2)c.checked=false}}))}
function selected(name){return document.querySelector('input[name="'+name+'"]:checked')?.value||''}
function addons(prefix){return [...document.querySelectorAll('#'+prefix+'_addons input[type=checkbox]:checked')].map(x=>({name:x.dataset.name,price:Number(x.dataset.price)||0}))}
function acai(prefix){return [...document.querySelectorAll('#'+prefix+'_a_'+CSS.escape('0'))].length?[]:[...document.querySelectorAll('[id^="'+prefix+'_a_"][data-acai="1"]:checked')].map(x=>({name:x.dataset.name,price:Number(x.dataset.price)||0}))}
function allAcai(){return [...document.querySelectorAll('#r11ComboContent input[data-acai="1"]:checked')].map(x=>({id:x.id,name:x.dataset.name,price:Number(x.dataset.price)||0}));}
function validarAcai(prefix){const chosen=[...document.querySelectorAll('[id^="'+prefix+'_a_"][data-acai="1"]:checked')];return chosen.map(x=>({name:x.dataset.name,price:Number(x.dataset.price)||0}))}
function close(){const m=document.getElementById('ndComboModal');if(m)m.classList.remove('show');document.body.style.overflow='';current=null}
function confirm(){if(!current)return;const cfg=current.cfg,details=[],selectedBur=[];let ok=true;let extra=0;
 cfg.sections.forEach((sec,idx)=>{const id='r11s'+idx;
   if(sec.type==='burger'){const v=selected(id);if(!v){ok=false;return}details.push('Lanche: '+v);addons(id).forEach(a=>{details.push('Adicional no lanche: '+a.name);extra+=a.price})}
   if(sec.type==='burger2'){const a=selected(id+'a'),b=selected(id+'b');if(!a||!b){ok=false;return}details.push('Lanche 1: '+a,'Lanche 2: '+b);addons(id+'a').forEach(x=>{details.push('Adicional no Lanche 1: '+x.name);extra+=x.price});addons(id+'b').forEach(x=>{details.push('Adicional no Lanche 2: '+x.name);extra+=x.price})}
   if(sec.type==='drink'){const v=selected(id);if(!v){ok=false;return}details.push('Refrigerante: '+v)}
   if(sec.type==='sauces'){const v=[...document.querySelectorAll('input[name="'+id+'"]:checked')].map(x=>x.value);if(v.length!==2){ok=false;return}details.push('Molhos: '+v.join(' + '))}
   if(sec.type==='pastel'){const v=selected(id);if(!v){ok=false;return}details.push('Pastel: '+v)}
   if(sec.type==='fixed'){details.push(sec.title+': '+sec.value)}
   if(sec.type==='acai'){const a=validarAcai(id);if(a.length===0){ok=false;return}details.push('Açaí 300ml: '+a.map(x=>x.name).join(' + '));let normal=0;a.forEach(x=>{if(x.price>0)extra+=x.price;else normal++});if(normal>3)extra+=(normal-3)*0}
   if(sec.type==='acai2'){const a=validarAcai(id+'a'),b=validarAcai(id+'b');if(!a.length||!b.length){ok=false;return}details.push('Açaí 1 300ml: '+a.map(x=>x.name).join(' + '));details.push('Açaí 2 300ml: '+b.map(x=>x.name).join(' + '));a.concat(b).forEach(x=>{if(x.price>0)extra+=x.price})}
 });
 if(!ok){alert('⚠️ COMPLETE TODAS AS ESCOLHAS OBRIGATÓRIAS DO COMBO ANTES DE ADICIONAR.');return}
 const item={nome:current.name,preco:current.price+extra,quantidade:1,detalhes:details};if(Array.isArray(window.carrinho))window.carrinho.push(item);if(typeof window.atualizarCarrinho==='function')window.atualizarCarrinho();close();setTimeout(()=>{try{window.scrollTo({top:window.scrollY,behavior:'auto'})}catch(_){ }},0);
}
window.abrirComboPersonalizacao=open;window.fecharComboPersonalizacao=close;window.confirmarComboPersonalizacao=confirm;
// Intercepta qualquer adicionar() de combo, inclusive entradas antigas/atalhos.
const originalAdicionar=window.adicionar;
if(typeof originalAdicionar==='function'&&!originalAdicionar.__r11combo){
 window.adicionar=function(nome,preco){if(configs[nome]){open(nome,preco||configs[nome].price);return}return originalAdicionar.apply(this,arguments)};window.adicionar.__r11combo=true;
}
// Garante que os botões dos combos abram o configurador imediatamente.
function patchComboButtons(){document.querySelectorAll('.produto .btn-add').forEach(btn=>{const card=btn.closest('.produto');const name=card?.querySelector('h3')?.textContent.trim();if(configs[name]&&btn.dataset.r11combo!=='1'){btn.dataset.r11combo='1';btn.setAttribute('onclick',"abrirComboPersonalizacao('"+name.replace(/'/g,"\\'")+"',"+configs[name].price+")")}})}
// Cria/posiciona Best Sellers, promo e escolhas rápidas.
function productInfo(card){const h=card.querySelector('h3'),im=card.querySelector('img'),pr=card.querySelector('.preco');const b=card.querySelector('.btn-add');if(!h||!pr||!b)return null;return {name:h.textContent.trim(),img:im?.src||'',price:Number((b.getAttribute('onclick')||'').match(/,([0-9.]+)\)/)?.[1]||0),btn:b}}
function buildBest(){if(document.getElementById('ndAutoBest'))return;const h=document.querySelector('.horarios');if(!h)return;const s=document.createElement('section');s.id='ndAutoBest';s.innerHTML='<div class="r11-best-head"><div><small>🔥 ATUALIZADO AUTOMATICAMENTE</small><h2>MAIS VENDIDOS DO DIA</h2></div><p>Favoritos em destaque para hoje.</p></div><div class="r11-best-grid"></div>';h.insertAdjacentElement('afterend',s)}
function renderBest(){
 const s=document.getElementById('ndAutoBest');if(!s)return;
 const grid=s.querySelector('.r11-best-grid');
 const cards=[...document.querySelectorAll('.produto')].map(productInfo).filter(Boolean).filter(x=>x.img&&!/^ARTESANAL /.test(x.name)&&!['FATIA QUEIJO CHEDDAR EXTRA','HAMBURGUER EXTRA ARTESANAL','HAMBURGUER EXTRA TRADICIONAL','BACON','ADICIONAL BACON','POTINHO BARBECUE','POTINHO MAIONESE VERDE','POTINHO CHEDDAR','POTINHO MAIONESE ARTESANAL','ADICIONAL CHEDDAR'].includes(norm(x.name))&&x.btn.closest('.categoria')?.id!=='adicionais');
 if(!cards.length)return;
 const key=new Date().toLocaleDateString('en-CA');
 let seed=0;for(let i=0;i<key.length;i++)seed=(seed*31+key.charCodeAt(i))>>>0;
 const pool=cards.slice();
 for(let i=pool.length-1;i>0;i--){seed=(seed*1664525+1013904223)>>>0;const j=seed%(i+1);[pool[i],pool[j]]=[pool[j],pool[i]]}
 const picks=pool.slice(0,3);
 grid.innerHTML=picks.map((x,i)=>'<article class="r11-best-card nd-daily-best-card"><div class="nd-best-rank">#'+(i+1)+'</div><img src="'+x.img+'" alt="'+esc(x.name)+'"><div><strong>'+esc(x.name)+'</strong><span>'+esc(x.btn.closest('.produto').querySelector('.preco')?.textContent||'')+'</span><small>⭐ DESTAQUE DE HOJE</small></div><button type="button">ADICIONAR</button></article>').join('');
 grid.querySelectorAll('button').forEach((b,i)=>b.onclick=()=>{const x=picks[i];if(configs[x.name])open(x.name,configs[x.name].price);else x.btn.click()});
 const head=s.querySelector('.r11-best-head p');if(head)head.textContent='3 escolhas aleatórias atualizadas todos os dias.';
}
function buildPromo(){if(document.getElementById('ndUvaPromo'))return;const h=document.querySelector('#ndAutoBest');if(!h)return;const p=document.createElement('section');p.id='ndUvaPromo';p.innerHTML='<img src="https://i.ibb.co/9kC6V4gP/Chat-GPT-Image-5-09-2026-06-50-46.png" alt="Doce surpresa de uva"><div class="r11-promo-copy"><div class="k">🔥 DESCONTO EXCLUSIVO NO SITE</div><h2>DOCE SURPRESA DE UVA</h2><p>Somente pelo site da ND BURGS</p><div class="r11-promo-old">DE R$ 12,00</div><div class="r11-promo-price">POR R$ 7,90</div><button type="button">ADICIONAR AO CARRINHO</button></div>';const destino=document.querySelector('#artesanais');if(destino)destino.insertAdjacentElement('afterend',p);else h.insertAdjacentElement('afterend',p);p.querySelector('button').onclick=()=>{if(typeof window.adicionar==='function')window.adicionar('SURPRESA DE UVA',7.90)}}
function buildQuick(){if(document.getElementById('ndFinalQuick'))return;const footer=document.querySelector('footer');if(!footer)return;const picks=['COMBO MAIS VENDIDO','COMBO DOCE','COMBO GELADO','COMBO SÓ LOVE','X-BACON','NUNES','GADEIA','BATATA'];const cards=[...document.querySelectorAll('.produto')].map(productInfo).filter(Boolean);const data=picks.map(n=>cards.find(x=>norm(x.name)===norm(n))).filter(Boolean);const s=document.createElement('section');s.id='ndFinalQuick';s.innerHTML='<h2>⚡ ESCOLHAS RÁPIDAS</h2><p>Se já sabe o que quer, adicione em um toque.</p><div class="r11-quick-grid">'+data.map((x,i)=>'<div class="r11-q"><img src="'+x.img+'" alt="'+esc(x.name)+'"><div><b>'+esc(x.name)+'</b><span>'+esc(x.btn.closest('.produto').querySelector('.preco')?.textContent||'')+'</span><button type="button">ADICIONAR</button></div></div>').join('')+'</div>';footer.parentNode.insertBefore(s,footer);s.querySelectorAll('button').forEach((b,i)=>b.onclick=()=>{const x=data[i];if(configs[x.name])open(x.name,configs[x.name].price);else x.btn.click()})}
function hideOld(){['#nd20Best','#ndR3Quick','#ndR7Reco','#ndR7Recent','#nd20QuickNav','#ndCartFab','#ndCartLabel'].forEach(sel=>document.querySelectorAll(sel).forEach(e=>e.style.display='none'))}
function ensureStatusPosition(){const st=document.getElementById('ndR8Status');if(st)st.style.display='none'}
function init(){patchComboButtons();hideOld();buildBest();renderBest();buildPromo();buildQuick();ensureStatusPosition();}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',()=>{init();setTimeout(init,700);setTimeout(init,1500)});else{init();setTimeout(init,700);setTimeout(init,1500)}
setTimeout(()=>{patchComboButtons();hideOld();renderBest()},900);
})();
</script>
<!-- =========================================================
     ND BURGS — RODADA 27 / R15
     Carrinho único: VER CARRINHO + QUANTIDADE
     + ajustes seguros de mobile, acessibilidade e performance
     ========================================================= -->


<!-- ND BURGS — RODADA 27 / R15 — AJUSTE VISUAL DE PREÇOS -->

<!-- =========================================================
     ND BURGS — RODADA 27 / R15
     UX PREMIUM + PIX + CONFIRMAÇÃO + UPSELL INTELIGENTE
     ========================================================= -->


<!-- =========================================================
     ND BURGS — RODADA 27 / R15
     VISUAL 3D + DESTAQUES DIÁRIOS + PIX + CONFIRMAÇÃO
     ========================================================= -->


<!-- =========================================================
     ND BURGS — RODADA 27 / R15
     LUZES AZUIS/ROXAS + PIX COMPLETO + ANIMAÇÃO DE ADIÇÃO
     ========================================================= -->


<!-- =========================================================
     ND BURGS — RODADA 28 / R16
     HERO AZUL/ROXO + SEM SOMBRAS NOS VALORES + PIX + CONFIRMAÇÃO
     + UPSELL DE COMBO SOMENTE PARA 1 ITEM INDIVIDUAL
     ========================================================= -->



<script id="nd-r19-reviews-js">
(function(){
'use strict';

const R19_REVIEWS=[
  ['“Muito bom, amei!”','Cliente ND BURGS'],
  ['“Comprei a primeira vez e amei.”','Cliente ND BURGS'],
  ['“Preço e qualidade, tudo muito bom.”','Cliente ND BURGS'],
  ['“Muito gostoso, vou pedir novamente.”','Cliente ND BURGS'],
  ['“Amei o lanche! Muito caprichado.”','Cliente ND BURGS'],
  ['“Preço justo e qualidade de verdade.”','Cliente ND BURGS'],
  ['“Já virou meu lanche favorito.”','Cliente ND BURGS'],
  ['“Muito bom, chegou direitinho e estava uma delícia.”','Cliente ND BURGS'],
  ['“Primeiro pedido e já ganhou cliente.”','Cliente ND BURGS'],
  ['“Amei! Com certeza vou comprar de novo.”','Cliente ND BURGS'],
  ['“Lanche muito bom e bem feito.”','Cliente ND BURGS'],
  ['“Gostei muito da qualidade.”','Cliente ND BURGS']
];

function addR19Reviews(){
  if(document.getElementById('ndR19Reviews')) return;

  const anchor=document.getElementById('ndR18Delivery') ||
               document.querySelector('.container') ||
               document.querySelector('main') ||
               document.body;

  const section=document.createElement('section');
  section.id='ndR19Reviews';

  section.innerHTML=
    '<div class="r19-head">'+
      '<div><h2>⭐ O QUE NOSSOS CLIENTES DIZEM</h2></div>'+
      '<div class="r19-rating"><strong>4,9</strong><span>★★★★★</span><small> no iFood</small></div>'+
    '</div>'+
    '<div class="r19-grid"></div>';

  const grid=section.querySelector('.r19-grid');

  /*
   * Exibição rotativa: a cada 5 dias muda o conjunto de 6 comentários.
   * Não altera os comentários, apenas a ordem/conjunto exibido.
   */
  const fiveDays=5*24*60*60*1000;
  const cycle=Math.floor(Date.now()/fiveDays);
  const start=(cycle*6)%R19_REVIEWS.length;

  for(let i=0;i<6;i++){
    const r=R19_REVIEWS[(start+i)%R19_REVIEWS.length];
    const card=document.createElement('article');
    card.className='r19-card';
    card.innerHTML=
      '<div class="r19-stars">★★★★★</div>'+
      '<p>'+r[0]+'</p>'+
      '<small>'+r[1]+'</small><br>'+
      '<span class="r19-source">AVALIAÇÃO 5 ESTRELAS</span>';
    grid.appendChild(card);
  }

  if(anchor===document.body) document.body.appendChild(section);
  else anchor.insertAdjacentElement('afterend',section);
}

function init(){
  addR19Reviews();
  setTimeout(addR19Reviews,1200);
}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init);
else init();
})();
</script>

<section aria-label="Tempo médio de entrega" id="ndR20DeliveryHighlight"><span class="nd-r20-spark s1"></span><span class="nd-r20-spark s2"></span><span class="nd-r20-spark s3"></span><span class="nd-r20-spark s4"></span><div class="nd-r20-inner"><div aria-hidden="true" class="nd-r20-icon">🛵</div><div class="nd-r20-copy"><p class="nd-r20-kicker">⏱️ TEMPO MÉDIO DE ENTREGA HOJE</p><h2 class="nd-r20-title">SEU PEDIDO A CAMINHO</h2><div class="nd-r20-time">40 A 50 MINUTINHOS</div><p class="nd-r20-sub">ESSE PRAZO DE ENTREGA É PARA RECEBER SEU PEDIDO NDBURGS COM QUALIDADE E TUDO FRESQUINHO 💜</p><div class="nd-r20-line"></div></div></div></section>
<!-- =========================================================
     ND BURGS R21 — PRODUTO  DO DIA + MOBILE TURBO
     ========================================================= -->



<!-- =========================================================
     ND BURGS R24 — POSICIONAMENTO FINAL + MELHORIAS COMPLETAS
     ========================================================= -->



<script id="nd-final-user-changes-js">
(function(){
  'use strict';

  const $=s=>document.querySelector(s);
  const $$=s=>Array.from(document.querySelectorAll(s));
  const norm=v=>String(v||'').normalize('NFD').replace(/[\u0300-\u036f]/g,'').toUpperCase().replace(/\s+/g,' ').trim();
  const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');

  let pendingOrder=null;

  function getCart(){
    if(!Array.isArray(window.carrinho)) window.carrinho=[];
    return window.carrinho;
  }

  function getTaxes(){
    try{return typeof taxas!=='undefined'?taxas:(window.taxas||{})}
    catch(e){return window.taxas||{}}
  }

  function subtotal(c){
    return c.reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||1),0);
  }

  function addressData(){
    const tipo=$('#tipoPedidoModal')?.value||localStorage.getItem('nd17_tipo')||'ENTREGA';
    const rua=$('#ruaModal')?.value||localStorage.getItem('nd17_rua')||'';
    const numero=$('#numeroModal')?.value.trim()||localStorage.getItem('nd17_numero')||'';
    return {tipo,rua,numero};
  }

  function fee(data){
    return data.tipo==='ENTREGA' ? Number(getTaxes()[data.rua]||0) : 0;
  }

  /* 1) Remove definitivamente o "Produto aleatório do dia". */
  function removeDaily(){
    $$('#ndR17FirstBuy').forEach(el=>el.remove());
    $$('.nd-r21-daily-kicker').forEach(el=>{
      const box=el.closest('#ndR17FirstBuy');
      if(box)box.remove();
    });
  }

  /* 2) Move a Surpresa de Uva para ENTRE TRADICIONAIS e ARTESANAIS. */
  function placeUva(){
    const promo=$('#ndUvaPromo');
    const tradicionais=$('#tradicionais');
    const artesanais=$('#artesanais');
    if(!promo||!tradicionais||!artesanais)return;
    tradicionais.insertAdjacentElement('afterend',promo);
    promo.classList.add('nd-final-middle');
    /* Evita que uma camada antiga tente levá-la de volta ao topo. */
    promo.classList.remove('nd-r25-offer-top');
  }

  /* 3) Foto genérica para qualquer produto sem foto/foto quebrada. */
  const genericSvg='data:image/svg+xml;charset=UTF-8,'+encodeURIComponent(
    '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 700">'+
    '<rect width="900" height="700" fill="#090909"/>'+
    '<rect x="25" y="25" width="850" height="650" rx="28" fill="none" stroke="#ffffff" stroke-width="3"/>'+
    '<text x="450" y="365" text-anchor="middle" font-family="Arial,Helvetica,sans-serif" font-size="92" font-weight="900" fill="#ffffff">NDBURGS</text>'+
    '</svg>'
  );

  function genericImage(card){
    let img=card.querySelector('img.produto-imagem, img');
    if(!img){
      img=document.createElement('img');
      img.className='produto-imagem';
      img.loading='lazy';
      img.decoding='async';
      card.insertBefore(img,card.firstChild);
    }
    if(img.dataset.ndFinalGeneric==='1')return;
    const useGeneric=()=>{
      if(img.dataset.ndFinalGeneric==='1')return;
      img.dataset.ndFinalGeneric='1';
      img.src=genericSvg;
      img.alt='NDBURGS';
      img.classList.add('nd-r25-generic-img');
    };
    img.addEventListener('error',useGeneric,{once:true});
    const src=String(img.getAttribute('src')||'').trim();
    if(!src||src==='#'||/^javascript:/i.test(src))useGeneric();
  }

  function applyGenericImages(){
    $$('.produto').forEach(genericImage);
  }

  /* 4) Limpa textos para o WhatsApp: sem emojis, sem markdown. */
  function cleanText(value){
    return String(value||'')
      .replace(/[\u{1F000}-\u{1FAFF}]/gu,'')
      .replace(/[\u{2600}-\u{27BF}]/gu,'')
      .replace(/[*_~`]/g,'')
      .replace(/[ \t]+/g,' ')
      .trim();
  }

  function cleanDetail(detail){
    return cleanText(detail).replace(/^\s*↳\s*/,'').trim();
  }

  function buildWhatsAppMessage(){
    const c=getCart();
    const nome=$('#nomeModal')?.value.trim()||'';
    const telefone=$('#telefoneModal')?.value.trim()||'';
    const data=addressData();
    const complemento=$('#complementoModal')?.value.trim()||'';
    const pagamento=$('#pagamentoModal')?.value||'';
    const troco=$('#trocoModal')?.value||'';
    const observacao=$('#observacaoModal')?.value.trim()||'';

    const sub=subtotal(c), taxa=fee(data), total=sub+taxa;
    const lines=[
      'NOVO PEDIDO - ND BURGS',
      'Nome: '+cleanText(nome),
      'WhatsApp: '+cleanText(telefone),
      'Tipo: '+(data.tipo==='ENTREGA'?'DELIVERY':'RETIRADA')
    ];

    if(data.tipo==='ENTREGA'){
      lines.push('Endereço: '+cleanText(data.rua));
      lines.push('Número: '+cleanText(data.numero));
      if(complemento)lines.push('Complemento: '+cleanText(complemento));
    }

    lines.push('');
    lines.push('Itens:');

    c.forEach(item=>{
      const qty=Math.max(1,Number(item.quantidade)||1);
      lines.push(qty+'x '+cleanText(item.nome));
      if(Array.isArray(item.detalhes)){
        item.detalhes.forEach(detail=>{
          const d=cleanDetail(detail);
          if(d)lines.push(d);
        });
      }
    });

    lines.push('');
    lines.push('Subtotal: '+money(sub));
    lines.push('Taxa de entrega: '+money(taxa));
    lines.push('Total: '+money(total));
    lines.push('Forma de pagamento: '+cleanText(pagamento));

    if(pagamento==='DINHEIRO'&&troco){
      lines.push('Troco para: '+money(Number(String(troco).replace(',','.'))||0));
    }
    if(observacao)lines.push('Observação: '+cleanText(observacao));

    return lines.join('\n');
  }

  function validate(){
    const c=getCart();
    if(!c.length){alert('Adicione pelo menos um produto ao carrinho.');return false}

    const nome=$('#nomeModal')?.value.trim()||'';
    const tel=($('#telefoneModal')?.value||'').replace(/\D/g,'');
    const data=addressData();
    const pagamento=$('#pagamentoModal')?.value||'';

    if(!nome){alert('Digite seu nome.');$('#nomeModal')?.focus();return false}
    if(tel.length<10||tel.length>11){alert('Digite um WhatsApp válido com DDD.');$('#telefoneModal')?.focus();return false}
    if(data.tipo==='ENTREGA'&&(!data.rua||!data.numero)){alert('Complete seu endereço.');return false}
    if(!pagamento){alert('Escolha a forma de pagamento.');return false}

    const sub=subtotal(c), taxa=fee(data), total=sub+taxa;
    if(data.tipo==='ENTREGA'&&sub<11.90){
      alert('O pedido mínimo para delivery é R$ 11,90.');
      return false;
    }

    if(pagamento==='DINHEIRO'){
      const raw=String($('#trocoModal')?.value||'').replace(',','.');
      const troco=Number(raw);
      if(!troco||troco<=total){
        alert('Informe um valor de troco maior que o total do pedido.');
        $('#trocoModal')?.focus();
        return false;
      }
    }
    return true;
  }

  function ensureSendGate(){
    if($('#ndFinalSendGate'))return;

    const d=document.createElement('div');
    d.id='ndFinalSendGate';
    d.innerHTML=
      '<div class="nd-final-send-panel" role="dialog" aria-modal="true">'+
        '<h2>Enviar pedido pelo WhatsApp</h2>'+
        '<p>Seu pedido ainda não foi enviado. Clique para abrir o WhatsApp e envie a mensagem para a ND BURGS. Depois, volte para esta página e confirme que você enviou.</p>'+
        '<button id="ndFinalOpenWhatsApp" type="button">ABRIR WHATSAPP E ENVIAR</button>'+
        '<button id="ndFinalConfirmSent" type="button">JÁ ENVIEI O PEDIDO</button>'+
        '<button id="ndFinalBack" type="button">VOLTAR E CONFERIR</button>'+
        '<div id="ndFinalSentState">Pedido confirmado pelo cliente. O carrinho será limpo agora.</div>'+
      '</div>';

    document.body.appendChild(d);

    $('#ndFinalBack').onclick=()=>{
      d.classList.remove('show');
      pendingOrder=null;
    };

    $('#ndFinalOpenWhatsApp').onclick=()=>{
      if(!pendingOrder)return;
      const url='https://wa.me/5511963973846?text='+encodeURIComponent(pendingOrder.message);
      let opened=null;
      try{opened=window.open(url,'_blank','noopener,noreferrer')}catch(e){}
      if(!opened){
        try{
          window.location.href=url;
          return;
        }catch(e){
          alert('Não foi possível abrir o WhatsApp neste navegador.');
          return;
        }
      }
      $('#ndFinalSentState').style.display='block';
    };

    $('#ndFinalConfirmSent').onclick=confirmSent;
  }

  function hideSendState(){
    const d=$('#ndFinalSendGate');
    if(d)d.classList.remove('show');
    pendingOrder=null;
  }

  function clearCartAfterConfirmation(){
    const c=getCart();
    /* Guarda o último pedido para o recurso PEDIR NOVAMENTE. */
    try{
      localStorage.setItem('ndburgs_ultimo_pedido',JSON.stringify(c));
    }catch(e){}

    c.length=0;
    window.carrinho=c;

    try{
      localStorage.removeItem('carrinho');
      localStorage.removeItem('ndburgs_carrinho');
      localStorage.removeItem('ndburgs_pedido_pendente');
      localStorage.removeItem('ndburgs_pix_copiado');
    }catch(e){}

    /* Atualiza o sistema original e todos os indicadores visuais. */
    try{if(typeof window.salvarCarrinho==='function')window.salvarCarrinho()}catch(e){}
    try{if(typeof window.atualizarCarrinho==='function')window.atualizarCarrinho()}catch(e){}
    try{
      $$('.modal-carrinho,.modal-finalizar').forEach(m=>m.classList.remove('ativo'));
    }catch(e){}

    const floating=$('#carrinhoFlutuante');
    if(floating)floating.classList.remove('ativo');

    $$('#ndFinalSendGate').forEach(x=>x.classList.remove('show'));

    /* Remove qualquer mensagem antiga de "pedido confirmado". */
    const oldSuccess=$('#ndOrderSuccess');
    if(oldSuccess)oldSuccess.classList.remove('show');

    /* Re-renderiza se existirem módulos de último pedido/favoritos. */
    try{if(typeof window.renderLast==='function')window.renderLast()}catch(e){}
  }

  function confirmSent(){
    if(!pendingOrder)return;
    const state=$('#ndFinalSentState');
    if(state)state.style.display='block';

    setTimeout(()=>{
      clearCartAfterConfirmation();
      alert('Pedido confirmado. O carrinho foi limpo.');
    },180);
  }

  /*
   * Substitui a finalização antiga.
   * O pedido NÃO é considerado enviado ao apenas abrir o WhatsApp.
   * O cliente precisa confirmar manualmente depois de tocar em ENVIAR no WhatsApp.
   */
  function patchFinish(){
    const fn=window.finalizarPedidoModal;
    if(typeof fn!=='function'||fn.__ndFinalChanges)return;

    const replacement=function(){
      if(!validate())return;
      pendingOrder={message:buildWhatsAppMessage()};
      ensureSendGate();
      $('#ndFinalSendGate').classList.add('show');
    };

    replacement.__ndFinalChanges=true;
    replacement.__ndFinalOriginal=fn;
    window.finalizarPedidoModal=replacement;

    /* Também neutraliza wrappers antigos que possam ter ficado no botão. */
    $$('#modalFinalizar button[onclick*="finalizarPedidoModal"]').forEach(btn=>{
      btn.onclick=function(e){
        if(e)e.preventDefault();
        window.finalizarPedidoModal();
      };
      btn.textContent='ENVIAR PEDIDO PELO WHATSAPP';
    });
  }

  /* Impede que camadas antigas recriem o falso "pedido confirmado". */
  function removeOldSuccess(){
    const x=$('#ndOrderSuccess');
    if(x)x.remove();
    const gate=$('#ndR25SendGate');
    if(gate)gate.remove();
    const conf=$('#ndR25Confirmed');
    if(conf)conf.remove();
    const pending=$('#ndR25PixPending');
    if(pending)pending.remove();
  }

  /* Corrige carregamento do carrinho salvo caso uma camada antiga tenha reatribuído a variável. */
  function restoreCartSafely(){
    try{
      const saved=localStorage.getItem('ndburgs_carrinho');
      if(saved && (!Array.isArray(window.carrinho)||window.carrinho.length===0)){
        const parsed=JSON.parse(saved);
        if(Array.isArray(parsed))window.carrinho=parsed;
      }
    }catch(e){}
  }

  function init(){
    removeDaily();
    placeUva();
    applyGenericImages();
    removeOldSuccess();
    restoreCartSafely();
    patchFinish();

    setTimeout(()=>{
      removeDaily();
      placeUva();
      applyGenericImages();
      removeOldSuccess();
      patchFinish();
    },700);

    setTimeout(()=>{
      removeDaily();
      placeUva();
      applyGenericImages();
      patchFinish();
    },1500);
  }

  if(document.readyState==='loading'){
    document.addEventListener('DOMContentLoaded',init,{once:true});
  }else{
    init();
  }

  /* Observa somente alterações de estrutura, sem timer contínuo pesado. */
  const observer=new MutationObserver(()=>{
    removeDaily();
    placeUva();
    applyGenericImages();
    patchFinish();
  });
  if(document.body)observer.observe(document.body,{childList:true,subtree:true});

})();
</script>
<!-- =========================================================
     ND BURGS — ATUALIZAÇÃO R26
     ENDEREÇO NO TOPO + PIX + CHECKOUT + SUPER OFERTA DIÁRIA
     ========================================================= -->

<script id="nd-r26-final-js">
(function(){
'use strict';
const $=s=>document.querySelector(s), $$=s=>Array.from(document.querySelectorAll(s));
const norm=v=>String(v||'').normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,' ').toUpperCase().trim();
const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');

function taxes(){try{return typeof window.taxas!=='undefined'?window.taxas:(typeof taxas!=='undefined'?taxas:{})}catch(e){return window.taxas||{}}}
function streets(){return Object.keys(taxes()).filter(k=>!['BALCAO','RETIRADA','IFOOD','99FOOD'].includes(k));}
function getAddr(){return {type:localStorage.getItem('nd26_tipo')||localStorage.getItem('nd17_tipo')||'ENTREGA',street:localStorage.getItem('nd26_rua')||localStorage.getItem('nd17_rua')||'',number:localStorage.getItem('nd26_numero')||localStorage.getItem('nd17_numero')||''}}
function saveAddr(type,street,number){localStorage.setItem('nd26_tipo',type);localStorage.setItem('nd26_rua',street||'');localStorage.setItem('nd26_numero',number||'');localStorage.setItem('nd17_tipo',type);localStorage.setItem('nd17_rua',street||'');localStorage.setItem('nd17_numero',number||'');}
function syncCheckoutAddr(){
 const a=getAddr(),tipo=$('#tipoPedidoModal'),rua=$('#ruaModal'),num=$('#numeroModal');
 if(tipo)tipo.value=a.type==='RETIRADA'?'RETIRADA':'ENTREGA';
 if(rua)rua.value=a.street||'';
 if(num)num.value=a.number||'';
 const btns=$$('.nd-v4-pay[data-type]');btns.forEach(b=>b.classList.toggle('active',b.dataset.type===a.type));
}
function addressSummary(){
 const box=$('#ndV4SingleAddressSummary'); if(!box)return;
 const a=getAddr();
 if(a.type==='RETIRADA')box.innerHTML='<strong>🏪 RETIRADA NA LOJA</strong><br>Seu pedido será preparado para retirada no local.<br><button type="button" id="nd26EditTop">ALTERAR NO TOPO</button>';
 else box.innerHTML='<strong>🛵 DELIVERY</strong><br>'+((a.street||'Endereço não selecionado'))+(a.number?', Nº '+a.number:'')+'<br><small>Taxa: '+money(taxes()[a.street]||0)+'</small><br><button type="button" id="nd26EditTop">ALTERAR NO TOPO</button>';
 $('#nd26EditTop')?.addEventListener('click',()=>$('#ndTopStreet')?.focus());
}
function renderStreetList(input,list){
 if(!input||!list)return;
 const q=norm(input.value);
 const all=streets().filter(s=>!q||norm(s).includes(q)).slice(0,40);
 list.innerHTML=all.map(s=>'<div class="nd26-option" data-street="'+String(s).replace(/"/g,'&quot;')+'"><span>'+s+'</span><small>'+money(taxes()[s]||0)+'</small></div>').join('');
 list.classList.toggle('show',true);
 $$('.nd26-option',list).forEach(()=>{});
 list.querySelectorAll('.nd26-option').forEach(el=>el.addEventListener('click',()=>{
   input.value=el.dataset.street;input.dataset.valid='1';list.classList.remove('show');
 }));
}
function buildTopAddress(){
 if($('#ndTopAddress'))return;
 const host=$('.horarios')||$('.container'); if(!host)return;
 const d=document.createElement('section');d.id='ndTopAddress';d.setAttribute('aria-label','Endereço do pedido');
 d.innerHTML=`
  <div class="nd26-top-inner">
   <div>
    <div class="nd26-kicker">⚡ ESSA PARTE É MUITO IMPORTANTE PARA SEU PEDIDO</div>
    <div class="nd26-title">Coloque seu <strong>ENDEREÇO</strong> ou selecione <strong>RETIRADA NA LOJA</strong></div>
    <div class="nd26-sub">Escolha uma única vez aqui no topo. A taxa de delivery será calculada automaticamente.</div>
   </div>
  </div>
  <div class="nd26-mode-row">
   <button type="button" class="nd26-mode active" id="nd26DeliveryMode">🛵 DELIVERY</button>
   <button type="button" class="nd26-mode" id="nd26PickupMode">🏪 RETIRADA NA LOJA</button>
  </div>
  <div class="nd26-fields" id="nd26DeliveryFields">
   <div class="nd26-field-wrap"><input id="ndTopStreet" class="nd26-input" type="search" autocomplete="off" placeholder="🔎 Digite sua rua" aria-label="Rua"><div id="ndTopStreetList" class="nd26-list"></div></div>
   <input id="ndTopNumber" class="nd26-input" type="text" inputmode="numeric" placeholder="Número" aria-label="Número">
   <button type="button" class="nd26-save" id="nd26SaveAddress">USAR ESTE ENDEREÇO</button>
  </div>
  <div class="nd26-pickup-note" id="nd26PickupNote">🏪 <strong>Retirada selecionada.</strong> Sem taxa de entrega. Seu endereço não será solicitado.</div>
  <div class="nd26-status"><span id="nd26CurrentStatus">Nenhum endereço selecionado.</span><button type="button" id="nd26ClearAddress">TROCAR</button></div>`;
 host.parentNode.insertBefore(d,host);
 const street=$('#ndTopStreet'), list=$('#ndTopStreetList'), number=$('#ndTopNumber'), del=$('#nd26DeliveryMode'), pick=$('#nd26PickupMode'), fields=$('#nd26DeliveryFields'), note=$('#nd26PickupNote');
 function setMode(type){
   const delivery=type==='ENTREGA';del.classList.toggle('active',delivery);pick.classList.toggle('active',!delivery);fields.style.display=delivery?'grid':'none';note.classList.toggle('show',!delivery);
 }
 function updateStatus(){const a=getAddr();$('#nd26CurrentStatus').innerHTML=a.type==='RETIRADA'?'<strong>🏪 Retirada na loja</strong>':'<strong>'+ (a.street||'Nenhum endereço selecionado') + (a.number?', Nº '+a.number:'') + '</strong><br><span>Taxa: '+money(taxes()[a.street]||0)+'</span>'}
 del.onclick=()=>{setMode('ENTREGA');street.focus()};
 pick.onclick=()=>{saveAddr('RETIRADA','','');syncCheckoutAddr();setMode('RETIRADA');updateStatus();addressSummary();};
 street.addEventListener('input',()=>{street.dataset.valid='';renderStreetList(street,list)});
 street.addEventListener('focus',()=>renderStreetList(street,list));
 document.addEventListener('click',e=>{if(!d.contains(e.target))list.classList.remove('show')});
 $('#nd26SaveAddress').onclick=()=>{const s=streets().find(x=>norm(x)===norm(street.value));if(!s)return alert('Selecione uma rua da lista.');if(!number.value.trim())return alert('Digite o número do endereço.');saveAddr('ENTREGA',s,number.value.trim());syncCheckoutAddr();updateStatus();addressSummary();street.value=s;};
 $('#nd26ClearAddress').onclick=()=>street.focus();
 const a=getAddr();street.value=a.street||'';number.value=a.number||'';setMode(a.type==='RETIRADA'?'RETIRADA':'ENTREGA');updateStatus();
}

function hideLegacyAddressGate(){
 const g=$('#nd17Gate');if(g){g.classList.remove('show');g.style.display='none';}
 const bar=$('#nd17AddressBar');if(bar)bar.style.display='none';
}
function patchCheckout(){
 const original=window.buildCheckout;
 if(typeof original!=='function'||original.__nd26)return;
 const wrapped=function(){
   const r=original.apply(this,arguments);
   setTimeout(()=>{syncCheckoutAddr();decorateStep2();decoratePix();renameReview();addressSummary()},0);
   return r;
 };
 wrapped.__nd26=true;wrapped.__nd26Original=original;window.buildCheckout=wrapped;
}
function decorateStep2(){
 const step=$('#modalFinalizar .nd-v4-step-content[data-content="2"]');if(!step)return;
 ['#enderecoAreaModal','#ndRetiradaInfo'].forEach(sel=>{const x=$(sel);if(x)x.style.display='none'});
 let box=$('#ndV4SingleAddressSummary');if(!box){box=document.createElement('div');box.id='ndV4SingleAddressSummary';step.insertBefore(box,step.querySelector('.nd-v4-next'))}
 if(!$('#nd26DeliveryMini')){const m=document.createElement('div');m.id='nd26DeliveryMini';m.innerHTML='🕐 <b>Tempo de entrega:</b> 40 a 50 minutinhos para o seu pedido chegar fresquinho na sua residência.';box.insertAdjacentElement('afterend',m)}
 syncCheckoutAddr();addressSummary();
}
function renameReview(){const b=$('#modalFinalizar .nd-v4-step-content[data-content="3"] .nd-v4-next');if(b){b.id='nd26ReviewButton';b.textContent='CONCLUIR PEDIDO AGORA →'}}
function pixTotal(){
 const total=$('#ndV4Total')?.textContent||'R$ 0,00';const out=$('#ndPixTotal');if(out)out.textContent=total;
 const val=total.replace(/[^0-9,.-]/g,'').replace('.','').replace(',','.');return Number(val)||0;
}
function decoratePix(){
 const step=$('#modalFinalizar .nd-v4-step-content[data-content="3"]'),box=$('#ndPixBox');if(!step||!box)return;
 if(!$('#ndPixAttention')){
  const d=document.createElement('div');d.id='ndPixAttention';d.innerHTML='<div class="nd26-attn-badge">⚠️ ATENÇÃO</div><div class="nd26-attn-big">COPIE O PIX, FAÇA O PAGAMENTO E <span>RETORNE AQUI NO SITE</span> E CLIQUE EM FINALIZAR PEDIDO!</div><p>O pagamento é feito fora do site. Depois de pagar, volte para esta etapa e conclua o pedido.</p><div id="ndPixSafe">🛡️ <strong>ATENÇÃO PARA SUA SEGURANÇA:</strong> o pagamento não é feito pelo site. Após efetuar o pagamento, finalize o seu pedido aqui no site.</div></div>';
  box.insertAdjacentElement('afterend',d);
 }
 if(!$('#nd26AlreadyPaid')){
  const b=document.createElement('button');b.id='nd26AlreadyPaid';b.type='button';b.textContent='✅ JÁ PAGUEI • CONCLUA MEU PEDIDO';b.onclick=()=>{if(typeof window.ndStep==='function')window.ndStep(4);else document.querySelector('#modalFinalizar .nd-v4-step[data-step="4"]')?.click();};
  $('#ndPixAttention').insertAdjacentElement('afterend',b);
 }
 const pay=$('#pagamentoModal');
 const isPix=pay?.value==='PIX';$('#ndPixAttention').style.display=isPix?'block':'none';$('#nd26AlreadyPaid').style.display=isPix?'block':'none';box.classList.toggle('show',isPix);
 pixTotal();
}
function patchPay(){const pay=$('#pagamentoModal');if(!pay||pay.dataset.nd26)return;pay.dataset.nd26='1';pay.addEventListener('change',()=>setTimeout(decoratePix,30));}

function dailyOfferData(){
 const excluded=/REFRIGERANTE|COCA|PEPSI|DOLLY|GUARANA|POR[CÇ]?[AÃ]O\s*P|BATATA\s*P\b/i;
 const arr=[];
 $$('.produto').forEach(card=>{
  const name=card.querySelector('h3')?.textContent?.trim()||'';
  const priceText=card.querySelector('.preco')?.textContent||'';
  const m=priceText.match(/(\d{1,3}(?:\.\d{3})*,\d{2}|\d+\.\d{2})/);if(!name||!m||excluded.test(name))return;
  const p=parseFloat(m[1].replace(/\./g,'').replace(',','.'));if(!(p>2))return;
  const img=card.querySelector('img')?.getAttribute('src')||'';
  const addBtn=card.querySelector('.btn-add');arr.push({name,price:p,img,addBtn});
 });
 if(!arr.length)return null;
 const now=new Date(),day=now.getFullYear()+'-'+String(now.getMonth()+1).padStart(2,'0')+'-'+String(now.getDate()).padStart(2,'0'),hash=[...day].reduce((s,c)=>s+c.charCodeAt(0),0);
 return arr[hash%arr.length];
}
function buildSuperOffer(){
 let sec=$('#nd26SuperOffer');if(!sec){sec=document.createElement('section');sec.id='nd26SuperOffer';const footer=document.querySelector('footer');(footer?footer.parentNode.insertBefore(sec,footer):document.body.appendChild(sec));}
 const d=dailyOfferData();if(!d)return;
 const offerPrice=Math.max(0,d.price-2);
 sec.innerHTML='<div class="nd26-offer-head"><div><div class="nd26-offer-kicker">🔥 EXCLUSIVO NO SITE</div><div class="nd26-offer-title">SUPER OFERTA</div></div><div class="nd26-offer-badge">OFERTA DO DIA</div></div><div class="nd26-offer-card"><img class="nd26-offer-img" src="'+d.img.replace(/"/g,'&quot;')+'" alt="'+d.name.replace(/"/g,'&quot;')+'"><div><div class="nd26-offer-name">'+d.name.replace(/[<>]/g,'')+'</div><div class="nd26-offer-desc">Uma oportunidade especial para pedir hoje pelo site da ND BURGS.</div><div class="nd26-offer-price">'+money(offerPrice)+'</div></div><button type="button" class="nd26-offer-btn" id="nd26OfferBtn">QUERO ESSA OFERTA</button></div>';
 $('#nd26OfferBtn').onclick=()=>{if(typeof window.adicionar==='function'){window.adicionar(d.name,offerPrice)}};
}
function init(){
 buildTopAddress();hideLegacyAddressGate();patchCheckout();decorateStep2();patchPay();decoratePix();renameReview();addressSummary();buildSuperOffer();
 syncCheckoutAddr();
 setTimeout(()=>{buildTopAddress();hideLegacyAddressGate();patchCheckout();decorateStep2();patchPay();decoratePix();renameReview();addressSummary();buildSuperOffer();},500);
 setTimeout(()=>{buildTopAddress();hideLegacyAddressGate();decorateStep2();patchPay();decoratePix();renameReview();addressSummary();buildSuperOffer();},1300);
}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init,{once:true});else init();
})();
</script>
<!-- =========================================================
     ND BURGS R27 — PIX: AVISO APÓS CÓPIA + SEGURANÇA
     ========================================================= -->

<script id="nd-r27-pix-security-js">
(function(){
  'use strict';

  const MSG='ATENÇÃO: COPIE O PIX, FAÇA O PAGAMENTO E RETORNE AQUI NO SITE E CLIQUE EM FINALIZAR PEDIDO!';

  function toast(){
    let el=document.getElementById('ndR27PixToast');
    if(!el){
      el=document.createElement('div');
      el.id='ndR27PixToast';
      el.innerHTML='<div class="r27-pix-icon">⚠️</div><strong>ATENÇÃO</strong><p>'+MSG+'</p><button type="button" id="ndR27PixToastClose">ENTENDI • VOLTAR PARA O PAGAMENTO</button>';
      document.body.appendChild(el);
      document.getElementById('ndR27PixToastClose').onclick=function(){el.classList.remove('show');setTimeout(function(){el.style.display='none'},220)};
    }
    el.style.display='block';
    requestAnimationFrame(function(){el.classList.add('show')});
    clearTimeout(el._timer);
    el._timer=setTimeout(function(){el.classList.remove('show');setTimeout(function(){el.style.display='none'},220)},7000);
  }

  function addSecurityNote(){
    const step=document.querySelector('#modalFinalizar .nd-v4-step-content[data-content="3"]');
    if(!step || document.getElementById('ndR27PixSecurityNote'))return;
    const payGrid=step.querySelector('.nd-v4-payment-grid');
    const note=document.createElement('div');
    note.id='ndR27PixSecurityNote';
    note.innerHTML='<div class="r27-security-title">🛡️ ATENÇÃO PARA SUA SEGURANÇA</div><b>O pagamento não é feito pelo site.</b> Então, após efetuar o pagamento, finalize o seu pedido aqui no site.';
    if(payGrid)payGrid.insertAdjacentElement('afterend',note);else step.insertBefore(note,step.firstChild);
  }

  function bindCopyMessages(){
    ['ndPixCopy','ndPixCopyValue'].forEach(function(id){
      const b=document.getElementById(id);
      if(!b || b.dataset.ndR27Bound==='1')return;
      b.dataset.ndR27Bound='1';
      b.addEventListener('click',function(){setTimeout(toast,80)});
    });
  }

  function bindAlreadyPaid(){
    const b=document.getElementById('nd26AlreadyPaid');
    if(!b || b.dataset.ndR27Bound==='1')return;
    b.dataset.ndR27Bound='1';
    b.onclick=function(){
      if(typeof window.ndStep==='function'){
        window.ndStep(4);
        return;
      }
      const target=document.querySelector('#modalFinalizar .nd-v4-step[data-step="4"]');
      if(target)target.click();
    };
  }

  function addMainPaymentNote(){
    const sel=document.getElementById('pagamento');
    if(!sel || document.getElementById('ndR27MainPixSecurityNote'))return;
    const note=document.createElement('div');
    note.id='ndR27MainPixSecurityNote';
    note.innerHTML='<div class="r27-security-title">🛡️ ATENÇÃO PARA SUA SEGURANÇA</div><b>O pagamento não é feito pelo site.</b> Então, após efetuar o pagamento, finalize o seu pedido aqui no site.';
    sel.insertAdjacentElement('afterend',note);
  }

  function init(){
    addSecurityNote();
    addMainPaymentNote();
    bindCopyMessages();
    bindAlreadyPaid();
  }

  if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init,{once:true});else init();
  const obs=new MutationObserver(init);
  obs.observe(document.body,{childList:true,subtree:true});
  setTimeout(init,300);setTimeout(init,1000);setTimeout(init,2000);
})();
</script>
<script>
(function () {
  const ND_SITE_VERSION = "20260907-R28";
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
</script><script id="nd-r28-final-logic">
(function(){
  'use strict';

  const $=(s,c=document)=>c.querySelector(s);
  const $$=(s,c=document)=>Array.from(c.querySelectorAll(s));

  function cleanButtonText(btn){
    if(!btn) return;
    const txt=(btn.textContent||'').trim();

    /* Somente CTAs que realmente dizem ADICIONAR. */
    if(/\bADICIONAR\b/i.test(txt)){
      btn.textContent='COMPRAR';
    }
  }

  function cleanAllBuyButtons(){
    /* Produtos do catálogo */
    $$('.produto .btn-add,.produto .nd-fx-add,.produto .nd-r3-add').forEach(cleanButtonText);

    /* Sugestões e recomendações */
    $$('.nd-r7-card button,.nd-v3-up button,.suggestion-card button').forEach(cleanButtonText);

    /* Ofertas/destaques que são compra direta */
    $$('.nd26-offer-btn,.r11-promo-copy button').forEach(cleanButtonText);

    /* Produto do dia: mantém o CTA específico quando não for ADICIONAR. */
    $$('.nd-r17-fb-btn').forEach(btn=>{
      if(/\bADICIONAR\b/i.test(btn.textContent||'')) btn.textContent='COMPRAR';
    });
  }

  function markAdded(btn){
    if(!btn) return;
    btn.classList.add('nd-r28-added');
    btn.classList.add('nd-r28-flash');
    btn.textContent='✓ ADICIONADO';
    setTimeout(()=>btn.classList.remove('nd-r28-flash'),500);
  }

  function markSuggestionAdded(btn){
    if(!btn) return;
    btn.classList.add('nd-r28-added');
    btn.textContent='✓ ADICIONADO';
  }

  /* Observa cliques sem substituir as funções originais do site. */
  function bind(){
    if(window.__NDBURGS_R28_BIND__) return;
    window.__NDBURGS_R28_BIND__=true;

    document.addEventListener('click',function(e){
      const btn=e.target.closest(
        '.produto .btn-add,.produto .nd-fx-add,.produto .nd-r3-add,'+
        '.nd-r7-card button,.nd-v3-up button,.suggestion-card button,'+
        '.nd26-offer-btn,.r11-promo-copy button'
      );

      if(!btn) return;

      /* Sugestões: o clique deve adicionar diretamente ao carrinho. */
      if(btn.matches('.nd-r7-card button[data-r7-add]')){
        const name=btn.dataset.r7Add;
        const price=Number(btn.dataset.r7Price||0);
        if(name && typeof window.adicionar==='function'){
          window.adicionar(name,price);
          markSuggestionAdded(btn);
          return;
        }
      }

      /* Sugestão genérica com onclick existente: o onclick original
         continua rodando; apenas mudamos o estado visual. */
      if(btn.matches('.suggestion-card button,.nd-v3-up button')){
        markSuggestionAdded(btn);
        return;
      }

      /* Produtos normais e personalizáveis:
         o handler original roda primeiro; depois mostramos feedback. */
      markAdded(btn);
    },true);

    /* Captura botões criados dinamicamente. */
    const obs=new MutationObserver(()=>{
      cleanAllBuyButtons();
    });
    obs.observe(document.body,{childList:true,subtree:true});

    cleanAllBuyButtons();
    setTimeout(cleanAllBuyButtons,300);
    setTimeout(cleanAllBuyButtons,1000);
    setTimeout(cleanAllBuyButtons,2000);
  }

  /* CONTINUAR COMPRANDO:
     fecha o modal e leva de volta para o catálogo, sem apagar o carrinho. */
  function fixContinueShopping(){
    const buttons=$$('.btn-continuar-comprando');
    buttons.forEach(btn=>{
      if(btn.dataset.ndR28Continue==='1') return;
      btn.dataset.ndR28Continue='1';
      btn.textContent='❤️ CONTINUAR COMPRANDO';
      btn.onclick=function(e){
        e.preventDefault();
        e.stopPropagation();

        if(typeof window.fecharCarrinho==='function'){
          try{window.fecharCarrinho();}catch(_){}
        }else{
          const modal=$('#modalCarrinho');
          if(modal) modal.classList.remove('ativo');
          document.body.style.overflow='';
        }

        setTimeout(()=>{
          const alvo=$('.categoria[id]')||$('#combos')||$('.container');
          if(alvo){
            alvo.scrollIntoView({behavior:'smooth',block:'start'});
          }
        },120);
      };
    });
  }

  /* Preços nas recomendações: se o card tiver nome + produto no catálogo,
     recupera o preço do produto caso alguma camada antiga não tenha
     colocado o valor visível. */
  function reinforceSuggestionPrices(){
    $$('.nd-r7-card,.nd-v3-up,.suggestion-card').forEach(card=>{
      const price=card.querySelector(
        '.nd-r7-price,.suggestion-price,.preco,span'
      );
      if(price && /R\$\s*\d/i.test(price.textContent||'')) return;

      const nameEl=card.querySelector('strong,b');
      if(!nameEl) return;
      const name=(nameEl.textContent||'').trim().toUpperCase();

      const product=$$('.produto').find(p=>{
        const h=p.querySelector('h3');
        return h && h.textContent.trim().toUpperCase()===name;
      });
      const productPrice=product?.querySelector('.preco')?.textContent?.trim();
      if(!productPrice) return;

      const s=document.createElement('small');
      s.className='nd-r28-suggestion-price';
      s.textContent=productPrice;
      s.style.cssText='display:block!important;color:#ffd166!important;font-weight:950!important;margin:4px 0 8px!important;';
      const action=card.querySelector('button');
      if(action) card.insertBefore(s,action);
      else card.appendChild(s);
    });
  }

  function init(){
    cleanAllBuyButtons();
    fixContinueShopping();
    reinforceSuggestionPrices();
    bind();
  }

  if(document.readyState==='loading'){
    document.addEventListener('DOMContentLoaded',init,{once:true});
  }else{
    init();
  }

  setTimeout(init,700);
  setTimeout(init,1600);
  setTimeout(init,3000);
})();
</script><script id="nd-r29-clean-features-js">
/* ND R29 — recomendações contextuais e TOP 3 diário */
(function(){
  'use strict';
  const $=(s,c=document)=>c.querySelector(s), $$=(s,c=document)=>Array.from(c.querySelectorAll(s));
  const norm=v=>String(v||'').normalize('NFD').replace(/[\u0300-\u036f]/g,'').toUpperCase().replace(/\s+/g,' ').trim();
  const money=v=>Number(v||0).toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
  const cart=()=>Array.isArray(window.carrinho)?window.carrinho:[];
  const qty=()=>cart().reduce((s,i)=>s+(Number(i.quantidade)||1),0);
  const cartNames=()=>cart().map(i=>norm(i.nome));
  function productCards(){
    return $$('.produto').map(card=>{
      const h=card.querySelector('h3'),p=card.querySelector('p'),img=card.querySelector('img'),price=card.querySelector('.preco'),btn=card.querySelector('.btn-add');
      if(!h||!price||!btn)return null;
      const name=h.textContent.trim(), text=price.textContent||'';
      const pm=text.match(/([0-9]+(?:[.,][0-9]{2}))/); if(!pm)return null;
      const value=Number(pm[1].replace('.','').replace(',','.'));
      const section=card.closest('.categoria');
      const onclick=btn.getAttribute('onclick')||'';
      const m=onclick.match(/adicionar\((['"])(.*?)\1\s*,\s*([0-9.]+)/);
      const pkey=section?.id||'';
      return {card,name,img:img?.src||'',price:value,priceText:text.trim(),btn,onclick,addName:m?.[2]||name,addPrice:m?Number(m[3]):value,section:pkey};
    }).filter(Boolean);
  }
  function addProduct(p,button){
    if(!p)return;
    if(/abrirPersonalizacao\s*\(/.test(p.onclick) && typeof window.abrirPersonalizacao==='function'){
      const m=p.onclick.match(/abrirPersonalizacao\((['"])(.*?)\1/); if(m){window.abrirPersonalizacao(m[2]); mark(button); return;}
    }
    if(/abrirComboPersonalizacao\s*\(/.test(p.onclick) && typeof window.abrirComboPersonalizacao==='function'){
      const m=p.onclick.match(/abrirComboPersonalizacao\((['"])(.*?)\1\s*,\s*([0-9.]+)/); if(m){window.abrirComboPersonalizacao(m[2],Number(m[3])); mark(button); return;}
    }
    if(typeof window.adicionar==='function'){window.adicionar(p.addName,p.addPrice);mark(button)}
  }
  function mark(b){if(!b)return;b.classList.add('added');b.textContent='✓ ADICIONADO';setTimeout(()=>{if(b.isConnected){b.classList.remove('added');b.textContent='COMPRAR'}},1400)}
  function seed(){const d=new Date();const k=d.getFullYear()+''+(d.getMonth()+1)+''+d.getDate();let x=2166136261;for(const ch of k){x^=ch.charCodeAt(0);x=Math.imul(x,16777619)}return x>>>0}
  function shuffle(a){let x=seed(),r=a.slice();for(let i=r.length-1;i>0;i--){x=(Math.imul(x,1664525)+1013904223)>>>0;const j=x%(i+1);[r[i],r[j]]=[r[j],r[i]]}return r}
  function classify(p){
    if(p.section==='combos'||p.section==='combosArtesanais')return 'combo';
    if(p.section==='sobremesas')return 'sobremesa';
    if(['tradicionais','artesanais'].includes(p.section))return 'lanche';
    return '';
  }
  function buildTop3(){
    let sec=$('#ndCleanTop3');
    if(!sec){sec=document.createElement('section');sec.id='ndCleanTop3';const anchor=$('.horarios')||$('.container');if(!anchor)return;anchor.insertAdjacentElement('afterend',sec)}
    const products=productCards().filter(p=>p.img&&!['adicionais'].includes(p.section));
    const groups={lanche:shuffle(products.filter(p=>classify(p)==='lanche')),combo:shuffle(products.filter(p=>classify(p)==='combo')),sobremesa:shuffle(products.filter(p=>classify(p)==='sobremesa'))};
    const picks=[groups.lanche[0],groups.combo[0],groups.sobremesa[0]].filter(Boolean);
    if(picks.length<3){shuffle(products).forEach(p=>{if(picks.length<3&&!picks.includes(p))picks.push(p)})}
    sec.innerHTML='<div class="nd-top3-head"><div><div class="nd-top3-kicker">🔥 TOP 3 DO DIA</div><h2>ITENS MAIS VENDIDOS DO DIA</h2></div><div class="nd-top3-note">Lanches, combos e sobremesas em destaque.</div></div><div class="nd-top3-grid"></div>';
    const grid=$('.nd-top3-grid',sec);
    picks.slice(0,3).forEach((p,i)=>{
      const a=document.createElement('article');a.className='nd-top3-card';
      a.innerHTML='<img loading="lazy" decoding="async" src="'+p.img+'" alt="'+p.name.replace(/"/g,'&quot;')+'"><div><strong>#'+(i+1)+' '+p.name.replace(/</g,'&lt;')+'</strong><span class="nd-top3-price">'+p.priceText+'</span><small>'+({'lanche':'🍔 LANCHE','combo':'❤️ COMBO','sobremesa':'🍨 SOBREMESA'}[classify(p)]||'⭐ DESTAQUE')+'</small></div><button type="button">COMPRAR</button>';
      a.querySelector('button').onclick=()=>addProduct(p,a.querySelector('button'));
      grid.appendChild(a);
    });
  }
  function compatible(p,cartText){
    const c=cartText;
    if(p.section==='bebidas')return /tradicionais|artesanais|combos|porcoes|pasteis/.test(c)?2:1;
    if(p.section==='porcoes')return /tradicionais|artesanais|combos/.test(c)?3:1;
    if(p.section==='sobremesas')return /tradicionais|artesanais|combos|pasteis/.test(c)?3:2;
    if(p.section==='adicionais')return /tradicionais|artesanais/.test(c)?1:0;
    if(p.section==='pasteis')return /bebidas|sobremesas/.test(c)?2:1;
    if(p.section==='combos'||p.section==='combosArtesanais')return 1;
    if(p.section==='tradicionais'||p.section==='artesanais')return /sobremesas|bebidas/.test(c)?1:0;
    return 0;
  }
  function buildUpsell(){
    const modal=$('#modalCarrinho'); if(!modal)return;
    let host=$('#ndCleanUpsell');
    const panel=modal.querySelector('.painel-carrinho'); if(!panel)return;
    const c=cart();
    if(!c.length){host?.remove();return}
    if(!host){host=document.createElement('section');host.id='ndCleanUpsell';const summary=panel.querySelector('.resumo-modal');(summary?summary.parentNode:panel).appendChild(host)}
    const names=cartNames().join(' '), products=productCards();
    const candidates=shuffle(products).filter(p=>!names.includes(norm(p.name))).map(p=>({...p,score:compatible(p,names)})).filter(p=>p.score>0).sort((a,b)=>b.score-a.score).slice(0,3);
    if(!candidates.length){host.remove();return}
    host.innerHTML='<div class="nd-upsell-head"><div><div class="nd-upsell-title">🔥 COMPLETE SEU PEDIDO</div><div class="nd-upsell-sub">Sugestões com sentido para o que já está no carrinho.</div></div><button class="nd-upsell-close" type="button" aria-label="Fechar">×</button></div><div class="nd-upsell-grid"></div>';
    $('.nd-upsell-close',host).onclick=()=>host.remove();
    const grid=$('.nd-upsell-grid',host);
    candidates.forEach(p=>{const card=document.createElement('article');card.className='nd-clean-up-card';card.innerHTML=(p.img?'<img loading="lazy" src="'+p.img+'" alt="'+p.name.replace(/"/g,'&quot;')+'">':'<div></div>')+'<div><strong>'+p.name.replace(/</g,'&lt;')+'</strong><span class="nd-up-why">'+({'bebidas':'Combina com seu pedido','porcoes':'Ótimo acompanhamento','sobremesas':'Fechamento perfeito','pasteis':'Mais uma opção para acompanhar','adicionais':'Deixe seu lanche ainda melhor','combos':'Uma opção prática para compartilhar','combosArtesanais':'Uma opção completa'}[p.section]||'Pode complementar seu pedido')+'</span><span class="nd-up-price">'+p.priceText+'</span><button type="button">COMPRAR</button></div>';card.querySelector('button').onclick=()=>{addProduct(p,card.querySelector('button'));setTimeout(()=>buildUpsell(),120)};grid.appendChild(card)});
  }
  let lastSignature='';
  function refresh(){
    const c=cart(),sig=c.map(i=>norm(i.nome)+':'+(i.quantidade||1)).join('|');
    if(sig!==lastSignature){lastSignature=sig;buildUpsell();}
  }
  function init(){buildTop3();refresh();setTimeout(()=>{buildTop3();refresh()},700);setTimeout(()=>{buildTop3();refresh()},1600)}
  document.addEventListener('click',e=>{if(e.target.closest('.btn-add,.nd-fx-add,.nd-top3-card button,.nd-clean-up-card button,.nd-v3-up button,.suggestion-card button'))setTimeout(refresh,180);if(e.target.closest('#carrinhoFlutuante,.btn-ver-carrinho,.nd-fx-cart-open'))setTimeout(buildUpsell,80)});
  document.addEventListener('DOMContentLoaded',init,{once:true});
  setTimeout(init,400);
})();
</script></body>
<!-- =========================================================
     ND BURGS — R28 / AJUSTES SOLICITADOS
     - Remove qualquer faixa/brand "ND BURGS" azul do topo,
       preservando o logo oficial.
     - Aumenta o logo do header.
     - Todos os CTAs de produto: ADICIONAR -> COMPRAR.
     - Após clicar, o CTA fica ADICIONADO e muda de cor.
     - Sugestões exibem preço e adicionam diretamente ao carrinho.
     - Corrige o botão CONTINUAR COMPRANDO para voltar ao cardápio.
     ========================================================= -->


</html>
