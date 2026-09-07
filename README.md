<html lang="pt-BR">
<head>
<!-- ND BURGS: controle de versão para evitar conteúdo antigo em cache -->
<meta name="nd-site-version" content="20260907-R28">
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
</script>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ND BURGS | Faça seu pedido</title>

<style>
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:Arial,Helvetica,sans-serif;background:#090909;color:#fff;padding-bottom:115px}

/* HEADER */
header{background:#000;padding:12px 20px;text-align:center;border-bottom:2px solid #f5c400;position:sticky;top:0;z-index:1000}
.logo{width:150px;max-width:70%;height:auto}

/* HORÁRIOS */
.horarios{max-width:1100px;margin:15px auto 0;padding:0 15px}
.horarios-box{background:linear-gradient(145deg,#151515,#0d0d0d);border:1px solid #f5c400;border-radius:12px;padding:14px 18px;text-align:center;box-shadow:0 4px 15px rgba(0,0,0,.4)}
.horarios-titulo{color:#f5c400;font-weight:bold;font-size:17px;margin-bottom:8px}
.horarios-linha{font-size:14px;color:#ddd;line-height:1.7}
.status-aberto{color:#25d366;font-weight:bold;margin-top:5px}
.status-fechado{color:#ff4b4b;font-weight:bold;margin-top:5px}

/* CONTAINER */
.container{width:100%;max-width:1100px;margin:auto;padding:15px}
h1{text-align:center;margin:20px 0;color:#f5c400}
h2{color:#f5c400;margin:25px 0 12px;border-bottom:1px solid #333;padding-bottom:8px}

/* CATEGORIAS */
.categoria{margin-top:20px;scroll-margin-top:90px}
.categoria-titulo{display:flex;align-items:center;gap:8px;color:#f5c400;font-size:20px;font-weight:bold;border-bottom:1px solid #333;padding-bottom:8px;margin-bottom:12px}

/* PRODUTOS */
.produtos{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:15px}
.produto{background:linear-gradient(145deg,#1c1c1c,#111);border:1px solid #333;border-radius:12px;padding:12px;box-shadow:0 3px 12px rgba(0,0,0,.35);overflow:hidden;transition:.2s}
.produto:hover{transform:translateY(-2px);border-color:#f5c400}
.produto-imagem{width:100%;height:180px;object-fit:contain;display:block;background:#111;border-radius:9px;margin-bottom:10px}
.produto h3{color:#fff;margin-bottom:7px;font-size:18px}
.produto p{color:#aaa;min-height:40px;font-size:13px;line-height:1.4}
.preco{color:#f5c400;font-weight:bold;font-size:19px;margin:10px 0}
.btn{width:100%;border:none;border-radius:8px;padding:12px;cursor:pointer;font-weight:bold;font-size:15px}
.btn-add{background:#f5c400;color:#000}
.btn-add:hover{background:#ffd92b}

/* CARRINHO */
.carrinho{background:#181818;border:1px solid #333;border-radius:12px;padding:20px;margin-top:30px}
.item-carrinho{display:flex;justify-content:space-between;gap:10px;align-items:center;padding:12px 0;border-bottom:1px solid #333}
.item-info{flex:1}
.item-info strong{display:block;margin-bottom:4px}
.item-info small{color:#aaa}
.controles{display:flex;align-items:center;gap:8px}
.controles button{width:30px;height:30px;border:none;border-radius:6px;background:#f5c400;color:#000;font-weight:bold;cursor:pointer}
.remover{background:#c62828!important;color:#fff!important}
.resumo{margin-top:20px}
.linha{display:flex;justify-content:space-between;padding:8px 0}
.total{font-size:24px;font-weight:bold;color:#f5c400;border-top:1px solid #555;margin-top:10px;padding-top:15px}
.vazio{text-align:center;color:#999;padding:20px}

/* CARRINHO FLUTUANTE */
.carrinho-flutuante{position:fixed;left:50%;bottom:15px;transform:translateX(-50%) translateY(150px);width:calc(100% - 30px);max-width:650px;background:#111;border:2px solid #f5c400;border-radius:16px;padding:12px 14px;z-index:9000;box-shadow:0 8px 35px rgba(0,0,0,.75);display:flex;align-items:center;justify-content:space-between;gap:12px;opacity:0;pointer-events:none;transition:.3s ease}
.carrinho-flutuante.ativo{transform:translateX(-50%) translateY(0);opacity:1;pointer-events:auto}
.carrinho-flutuante-info{min-width:0}
.carrinho-flutuante-info strong{display:block;color:#fff;font-size:15px}
.carrinho-flutuante-info span{display:block;color:#aaa;font-size:12px;margin-top:3px}
.carrinho-flutuante-direita{display:flex;align-items:center;gap:10px}
.carrinho-flutuante-total{color:#f5c400;font-size:18px;font-weight:bold;white-space:nowrap}
.btn-ver-carrinho{border:none;background:#f5c400;color:#000;font-weight:bold;border-radius:9px;padding:11px 13px;cursor:pointer;white-space:nowrap}
.btn-ver-carrinho:hover{background:#ffd92b}

/* MODAL CARRINHO */
.modal-carrinho{position:fixed;inset:0;background:rgba(0,0,0,.82);z-index:100001;display:none;align-items:flex-end;justify-content:center;padding:0}
.modal-carrinho.ativo{display:flex}
.painel-carrinho{width:100%;max-width:650px;max-height:90vh;overflow:auto;background:#151515;border:2px solid #f5c400;border-bottom:0;border-radius:20px 20px 0 0;padding:20px;box-shadow:0 -10px 40px rgba(0,0,0,.6)}
.cabecalho-carrinho{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-bottom:15px}
.cabecalho-carrinho h2{margin:0;border:0;padding:0}
.fechar-carrinho{width:38px;height:38px;border:none;border-radius:50%;background:#8b0000;color:#fff;font-size:22px;cursor:pointer}
.item-carrinho-modal{border-bottom:1px solid #333;padding:12px 0}
.item-carrinho-modal-topo{display:flex;justify-content:space-between;gap:10px}
.item-carrinho-modal strong{font-size:14px}
.item-carrinho-modal small{display:block;color:#aaa;margin-top:4px;line-height:1.4}
.controles-modal{display:flex;align-items:center;gap:8px;margin-top:9px}
.controles-modal button{width:34px;height:34px;border:none;border-radius:7px;background:#f5c400;color:#000;font-weight:bold;font-size:17px;cursor:pointer}
.controles-modal .remover{background:#c62828!important;color:#fff!important;width:34px}
.resumo-modal{margin-top:15px;padding-top:10px;border-top:1px solid #444}
.resumo-modal .linha{padding:6px 0}
.resumo-modal .total-modal{color:#f5c400;font-size:21px;font-weight:bold;padding-top:12px;margin-top:7px;border-top:1px solid #555}

/* BOTÕES DO CARRINHO */
.btn-continuar-comprando{
margin-top:15px;
background:#ff8c00;
color:#fff;
font-size:17px
}

.btn-finalizar-pedido{
margin-top:15px;
background:#0b3d91;
color:#fff;
font-size:18px
}

.btn-finalizar-pedido:hover{
background:#124fa8;
}

/* TOAST */
.toast-carrinho{position:fixed;left:50%;top:80px;transform:translate(-50%,-20px);background:#25D366;color:#fff;font-weight:bold;padding:11px 18px;border-radius:30px;z-index:100005;opacity:0;pointer-events:none;transition:.25s ease;box-shadow:0 5px 20px rgba(0,0,0,.5)}
.toast-carrinho.mostrar{opacity:1;transform:translate(-50%,0)}

/* FORMULÁRIO */
.formulario{background:#181818;border:1px solid #333;border-radius:12px;padding:20px;margin-top:20px;scroll-margin-top:90px}
label{display:block;margin-top:14px;margin-bottom:6px;font-weight:bold}
input,select,textarea{width:100%;padding:13px;border-radius:8px;border:1px solid #444;background:#0d0d0d;color:#fff;font-size:15px}
textarea{resize:vertical;min-height:80px}
.endereco-extra{display:none}
.aviso-taxa{background:#292000;border:1px solid #f5c400;color:#f5c400;padding:12px;border-radius:8px;margin-top:12px;display:none}
.btn-whatsapp{background:#25D366;color:#fff;margin-top:20px;font-size:18px}
.btn-limpar{background:#8b0000;color:#fff;margin-top:10px}

/* MENU CATEGORIAS */
.categoria-menu{display:grid;grid-template-columns:repeat(2,1fr);gap:10px;margin-bottom:20px}
.categoria-btn{background:#181818;border:1px solid #333;color:#fff;border-radius:10px;padding:13px 10px;cursor:pointer;font-weight:bold}
.categoria-btn:hover{border-color:#f5c400;color:#f5c400}

/* INSTAGRAM */
footer{text-align:center;padding:20px 15px;color:#777;font-size:13px}
.rodape-instagram{padding:30px 15px 25px}
.instagram-destaque{width:100%;max-width:850px;margin:0 auto;padding:25px;border-radius:20px;background:linear-gradient(145deg,#181818,#0d0d0d);border:2px solid #f5c400;box-shadow:0 8px 30px rgba(0,0,0,.55);display:flex;align-items:center;justify-content:space-between;gap:20px}
.instagram-icone{width:65px;height:65px;min-width:65px;display:flex;align-items:center;justify-content:center;border-radius:18px;background:linear-gradient(135deg,#833ab4,#fd1d1d,#fcb045);font-size:32px;box-shadow:0 5px 18px rgba(0,0,0,.4)}
.instagram-texto{flex:1;text-align:left}
.instagram-texto span{display:block;color:#f5c400;font-size:13px;font-weight:900;letter-spacing:1px;margin-bottom:3px}
.instagram-texto strong{display:block;color:#fff;font-size:25px;margin-bottom:4px}
.instagram-texto p{margin:0;color:#aaa;font-size:13px;line-height:1.5}
.instagram-botao{display:inline-flex;align-items:center;justify-content:center;padding:14px 20px;border-radius:12px;background:linear-gradient(135deg,#833ab4,#fd1d1d,#fcb045);color:#fff;text-decoration:none;font-weight:900;font-size:13px;white-space:nowrap;transition:.2s;box-shadow:0 5px 18px rgba(0,0,0,.35)}
.instagram-botao:hover{transform:scale(1.04);filter:brightness(1.1)}
.instagram-botao:active{transform:scale(.98)}
.rodape-final{text-align:center;color:#777;font-size:12px;line-height:1.8;margin-top:18px}

/* BLOQUEIO HORÁRIO */
#bloqueioHorario{position:fixed;inset:0;background:rgba(0,0,0,.97);z-index:99999;display:none;align-items:center;justify-content:center;padding:20px}
.bloqueio-box{width:100%;max-width:480px;background:#151515;border:2px solid #f5c400;border-radius:18px;padding:30px 20px;text-align:center;box-shadow:0 0 40px rgba(245,196,0,.15)}
.bloqueio-box h2{border:none;color:#f5c400;margin:0 0 15px}
.bloqueio-box p{color:#ccc;line-height:1.6}
.bloqueio-horarios{margin-top:18px;padding:15px;background:#0c0c0c;border-radius:10px;color:#ddd;line-height:1.8}
.bloqueio-logo{width:130px;max-width:60%;margin-bottom:15px}

/* MOBILE */
@media(max-width:600px){
body{padding-bottom:105px}
.item-carrinho{flex-direction:column;align-items:flex-start}
.controles{width:100%}
.controles button{width:35px;height:35px}
.produtos{grid-template-columns:repeat(2,1fr);gap:8px}
.produto{padding:9px}
.produto-imagem{height:125px}
.produto h3{font-size:14px}
.produto p{font-size:11px;min-height:45px}
.preco{font-size:16px}
.btn{padding:10px 5px;font-size:12px}
.categoria-titulo{font-size:17px}
.categoria-menu{grid-template-columns:1fr 1fr}
.carrinho-flutuante{width:calc(100% - 16px);bottom:8px;padding:10px;border-radius:13px}
.carrinho-flutuante-info strong{font-size:13px}
.carrinho-flutuante-info span{font-size:11px}
.carrinho-flutuante-direita{gap:7px}
.carrinho-flutuante-total{font-size:15px}
.btn-ver-carrinho{padding:10px 9px;font-size:11px}
.painel-carrinho{padding:16px}
}

/* PERSONALIZAÇÃO */
.modal-personalizacao{position:fixed;inset:0;background:rgba(0,0,0,.82);z-index:100000;display:none;align-items:center;justify-content:center;padding:15px}
.modal-box{width:100%;max-width:560px;max-height:92vh;overflow:auto;background:#151515;border:2px solid #f5c400;border-radius:18px;padding:20px;box-shadow:0 0 40px rgba(245,196,0,.2)}
.modal-topo{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-bottom:15px}
.modal-topo h2{margin:0;border:0;padding:0}
.modal-fechar{width:38px;height:38px;border:0;border-radius:50%;background:#8b0000;color:#fff;font-size:20px;cursor:pointer}
.modal-secao{margin-top:18px;padding-top:15px;border-top:1px solid #333}
.modal-secao h3{color:#f5c400;margin-bottom:10px;font-size:17px}
.opcoes-tamanho{display:grid;grid-template-columns:repeat(3,1fr);gap:8px}
.opcao-tamanho{position:relative}
.opcao-tamanho input{position:absolute;opacity:0;pointer-events:none}
.opcao-tamanho label{margin:0;display:block;padding:12px 8px;text-align:center;border:1px solid #444;border-radius:9px;background:#0d0d0d;cursor:pointer;font-weight:bold}
.opcao-tamanho input:checked+label{border-color:#f5c400;background:#302900;color:#f5c400}
.lista-acompanhamentos{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.opcao-acomp{display:flex;align-items:center;gap:8px;padding:10px;border:1px solid #333;border-radius:8px;background:#0d0d0d;cursor:pointer}
.opcao-acomp input{width:auto;margin:0}
.opcao-acomp span{font-size:13px}
.preco-adicional{color:#f5c400;font-weight:bold}
.modal-total{display:flex;justify-content:space-between;align-items:center;margin-top:18px;padding:14px;border-radius:10px;background:#0b0b0b;border:1px solid #333;font-size:19px}
.modal-total strong:last-child{color:#f5c400}
.btn-confirmar-personalizacao{margin-top:12px;background:#f5c400;color:#000}

/* MODAL FINALIZAR PEDIDO */
.modal-finalizar{
position:fixed;
inset:0;
background:rgba(0,0,0,.88);
z-index:100002;
display:none;
align-items:center;
justify-content:center;
padding:15px;
}

.modal-finalizar.ativo{
display:flex;
}

.painel-finalizar{
width:100%;
max-width:600px;
max-height:92vh;
overflow:auto;
background:#151515;
border:2px solid #f5c400;
border-radius:18px;
padding:20px;
box-shadow:0 0 40px rgba(0,0,0,.7);
}

.cabecalho-finalizar{
display:flex;
align-items:center;
justify-content:space-between;
gap:10px;
margin-bottom:15px;
}

.cabecalho-finalizar h2{
margin:0;
border:0;
padding:0;
}

.btn-finalizar-modal{
background:#0b3d91;
color:#fff;
margin-top:20px;
font-size:18px;
}

.btn-finalizar-modal:hover{
background:#124fa8;
}

.btn-fechar-finalizar{
width:38px;
height:38px;
border:none;
border-radius:50%;
background:#8b0000;
color:#fff;
font-size:22px;
cursor:pointer;
}

@media(max-width:600px){
.lista-acompanhamentos{grid-template-columns:1fr}
.opcoes-tamanho{grid-template-columns:repeat(3,1fr)}
.modal-box{padding:16px}

.painel-finalizar{
padding:16px;
}

.instagram-destaque{
flex-direction:column;
text-align:center;
padding:25px 18px;
gap:15px;
}

.instagram-icone{
width:60px;
height:60px;
min-width:60px;
font-size:28px;
}

.instagram-texto{
text-align:center;
}

.instagram-texto strong{
font-size:23px;
}

.instagram-texto p{
font-size:12px;
}

.instagram-botao{
width:100%;
padding:15px 10px;
font-size:14px;
}
}

/* ===== ND BURGS MODERN UI 2026 ===== */
:root{--gold:#f5c400;--gold2:#ffd83d;--bg:#070707;--panel:#111214;--panel2:#17181b;--line:rgba(255,255,255,.09);--muted:#9a9da5;--green:#25d366;--danger:#ff4d4d;--shadow:0 18px 60px rgba(0,0,0,.42)}
body{background:radial-gradient(circle at 50% -10%,rgba(245,196,0,.10),transparent 34%),linear-gradient(180deg,#050505 0%,#0b0c0e 55%,#070707 100%);font-family:Inter,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;color:#fff}
header{padding:10px 16px 8px;background:rgba(4,4,4,.82);backdrop-filter:blur(18px);border-bottom:1px solid rgba(245,196,0,.35);box-shadow:0 8px 30px rgba(0,0,0,.35)}
.logo{width:125px;filter:drop-shadow(0 5px 16px rgba(245,196,0,.12))}
.horarios{margin:12px auto 0}.horarios-box{border:1px solid rgba(245,196,0,.45);background:linear-gradient(135deg,rgba(255,255,255,.055),rgba(255,255,255,.018));backdrop-filter:blur(14px);border-radius:18px;box-shadow:var(--shadow);padding:13px 16px}.status-aberto{font-size:14px;background:rgba(37,211,102,.10);border:1px solid rgba(37,211,102,.22);display:inline-block;padding:6px 11px;border-radius:999px}.status-fechado{font-size:14px;background:rgba(255,75,75,.08);border:1px solid rgba(255,75,75,.22);display:inline-block;padding:6px 11px;border-radius:999px}
.container{max-width:1180px;padding:12px 16px 30px}.container>h1{font-size:clamp(28px,5vw,46px);letter-spacing:-1.5px;margin:22px 0 10px;background:linear-gradient(90deg,#fff,var(--gold2));-webkit-background-clip:text;background-clip:text;color:transparent}.container>h1:after{content:"PEÇA PELO SITE • RÁPIDO, FÁCIL E DIRETO";display:block;color:#858890;font-size:11px;letter-spacing:2px;margin-top:8px;font-weight:800}
.modern-search{position:sticky;top:68px;z-index:800;display:flex;gap:10px;align-items:center;margin:16px 0 13px;padding:10px;border:1px solid var(--line);background:rgba(12,13,15,.88);backdrop-filter:blur(18px);border-radius:16px;box-shadow:0 10px 35px rgba(0,0,0,.28)}.modern-search input{margin:0!important;background:#08090a!important;border:1px solid rgba(255,255,255,.10)!important;border-radius:12px!important;padding:14px 15px!important}.search-count{white-space:nowrap;color:#888;font-size:12px;font-weight:700}
.categoria-menu{display:flex;overflow-x:auto;gap:8px;padding:3px 1px 12px;margin:0 0 10px;scrollbar-width:none;position:sticky;top:126px;z-index:700;background:linear-gradient(180deg,#0b0c0e 75%,transparent)}.categoria-menu::-webkit-scrollbar{display:none}.categoria-btn{flex:0 0 auto;border:1px solid var(--line);background:rgba(255,255,255,.045);padding:11px 14px;border-radius:999px;transition:.2s}.categoria-btn:hover,.categoria-btn:focus{background:rgba(245,196,0,.10);border-color:rgba(245,196,0,.55);color:var(--gold)}
.categoria{margin-top:26px;scroll-margin-top:150px}.categoria-titulo{font-size:22px;padding:0 0 10px;border-bottom:1px solid var(--line);position:relative}.categoria-titulo:after{content:"";position:absolute;left:0;bottom:-1px;width:70px;height:2px;background:var(--gold);box-shadow:0 0 16px rgba(245,196,0,.45)}
.produtos{grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:14px}.produto{position:relative;background:linear-gradient(145deg,rgba(255,255,255,.065),rgba(255,255,255,.025));border:1px solid var(--line);border-radius:18px;padding:11px;box-shadow:0 10px 35px rgba(0,0,0,.20);transition:transform .22s,border-color .22s,box-shadow .22s}.produto:hover{transform:translateY(-4px);border-color:rgba(245,196,0,.42);box-shadow:0 18px 45px rgba(0,0,0,.34)}.produto-imagem{height:205px;border-radius:14px;background:radial-gradient(circle at 50% 50%,#202124,#0b0c0d);object-fit:contain}.produto h3{font-size:17px;margin:11px 2px 5px}.produto p{font-size:12px;color:#999da6;min-height:36px}.preco{font-size:20px;margin:9px 2px;color:var(--gold2)}.btn{border-radius:12px;font-weight:900;transition:.18s}.btn-add{background:linear-gradient(135deg,var(--gold),#e9ae00);box-shadow:0 7px 18px rgba(245,196,0,.13)}.btn-add:hover{transform:translateY(-1px);filter:brightness(1.07)}
.carrinho,.formulario{background:linear-gradient(145deg,rgba(255,255,255,.055),rgba(255,255,255,.022));border:1px solid var(--line);border-radius:20px;box-shadow:var(--shadow)}.carrinho{margin-top:26px}.formulario{margin-top:16px}input,select,textarea{border:1px solid rgba(255,255,255,.10);background:#090a0b;color:#fff;outline:none;transition:.2s}input:focus,select:focus,textarea:focus{border-color:rgba(245,196,0,.65);box-shadow:0 0 0 3px rgba(245,196,0,.08)}
.carrinho-flutuante{bottom:14px;width:calc(100% - 24px);max-width:720px;background:rgba(14,15,17,.92);backdrop-filter:blur(18px);border:1px solid rgba(245,196,0,.55);box-shadow:0 18px 60px rgba(0,0,0,.65)}.btn-ver-carrinho{background:var(--gold);border-radius:11px;padding:12px 16px}.carrinho-flutuante-total{color:var(--gold2)}
.modal-carrinho,.modal-finalizar,.modal-personalizacao{backdrop-filter:blur(8px)}.painel-carrinho,.painel-finalizar,.modal-box{background:linear-gradient(160deg,#17181b,#0d0e10);border:1px solid rgba(245,196,0,.55);box-shadow:0 -20px 80px rgba(0,0,0,.65)}
.btn-whatsapp{background:linear-gradient(135deg,#25d366,#16b957);box-shadow:0 10px 28px rgba(37,211,102,.15)}.btn-finalizar-pedido,.btn-finalizar-modal{background:linear-gradient(135deg,#f5c400,#d9a900);color:#090909}.btn-continuar-comprando{background:rgba(255,255,255,.08);border:1px solid var(--line)}
.instagram-destaque{border:1px solid rgba(245,196,0,.35);background:linear-gradient(145deg,rgba(255,255,255,.05),rgba(255,255,255,.015));box-shadow:var(--shadow)}
/* address quick search */.address-search-wrap{margin:7px 0 9px}.address-search-wrap input{margin:0!important}.address-search-wrap small{display:block;color:#777;margin-top:5px;font-size:11px}
/* suggestion sheet */.suggestions-modal{position:fixed;inset:0;z-index:100006;display:none;align-items:flex-end;justify-content:center;background:rgba(0,0,0,.76);backdrop-filter:blur(8px)}.suggestions-modal.show{display:flex}.suggestions-panel{width:100%;max-width:760px;max-height:88vh;overflow:auto;background:linear-gradient(160deg,#18191c,#0d0e10);border:1px solid rgba(245,196,0,.45);border-bottom:0;border-radius:24px 24px 0 0;padding:18px;box-shadow:0 -25px 80px rgba(0,0,0,.7)}.suggestions-head{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-bottom:14px}.suggestions-head h2{margin:0;border:0;padding:0;color:#fff}.suggestions-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:10px}.suggestion-card{display:flex;gap:10px;align-items:center;padding:10px;border:1px solid var(--line);border-radius:15px;background:rgba(255,255,255,.035)}.suggestion-card img{width:70px;height:70px;object-fit:contain;border-radius:10px;background:#090a0b}.suggestion-card strong{display:block;font-size:13px}.suggestion-card span{display:block;color:var(--gold2);font-weight:900;font-size:13px;margin:4px 0}.suggestion-card button{border:0;background:var(--gold);color:#000;border-radius:9px;padding:7px 10px;font-weight:900;cursor:pointer}.suggestions-close{border:0;background:#2a2b2f;color:#fff;width:36px;height:36px;border-radius:50%;font-size:20px}
.no-results{display:none;text-align:center;padding:35px 15px;color:#999;border:1px dashed #333;border-radius:16px;margin-top:12px}.produto.search-hidden{display:none!important}
@media(max-width:600px){.modern-search{top:57px}.categoria-menu{top:116px}.produtos{grid-template-columns:repeat(2,minmax(0,1fr));gap:8px}.produto{padding:8px;border-radius:15px}.produto-imagem{height:135px}.produto h3{font-size:13px}.produto p{font-size:10px;min-height:40px}.preco{font-size:16px}.btn{font-size:11px}.container{padding-left:9px;padding-right:9px}.suggestions-grid{grid-template-columns:1fr}.suggestion-card img{width:62px;height:62px}}

</style>

<style id="nd-v3-upgrades">
:root{--nd-gold:#f5c542;--nd-bg:#080808;--nd-card:#111;--nd-line:rgba(255,255,255,.09)}
html{scroll-behavior:smooth}.categoria{scroll-margin-top:145px}
.nd-v3-strip{position:sticky;top:0;z-index:1200;background:linear-gradient(90deg,#0a0a0a,#151515,#0a0a0a);border-bottom:1px solid var(--nd-line);padding:8px 14px;text-align:center;font-size:12px;font-weight:800;letter-spacing:.3px;color:#fff}.nd-v3-strip b{color:var(--nd-gold)}
.nd-v3-progress{position:fixed;left:0;right:0;top:0;height:3px;background:transparent;z-index:3000}.nd-v3-progress span{display:block;height:100%;width:0;background:var(--nd-gold);box-shadow:0 0 12px rgba(245,197,66,.8)}
.nd-v3-buybar{position:fixed;left:50%;bottom:14px;transform:translate(-50%,130px);opacity:0;z-index:1100;width:min(560px,calc(100% - 24px));display:flex;align-items:center;gap:10px;padding:10px 12px;background:rgba(12,12,12,.94);border:1px solid rgba(245,197,66,.35);border-radius:18px;box-shadow:0 18px 55px rgba(0,0,0,.55);backdrop-filter:blur(16px);transition:.25s}.nd-v3-buybar.show{transform:translate(-50%,0);opacity:1}.nd-v3-buybar .nd-v3-buyinfo{flex:1;font-size:12px;color:#aaa}.nd-v3-buybar strong{display:block;color:#fff;font-size:16px}.nd-v3-buybar button{border:0;border-radius:13px;background:var(--nd-gold);color:#111;font-weight:900;padding:12px 18px;cursor:pointer}
.nd-v3-upsell{margin:12px 0;padding:14px;border:1px solid rgba(245,197,66,.18);border-radius:16px;background:linear-gradient(145deg,#171717,#0d0d0d)}.nd-v3-upsell h4{margin:0 0 9px;color:#fff}.nd-v3-upsell-grid{display:flex;gap:8px;overflow:auto}.nd-v3-up{min-width:145px;border:1px solid var(--nd-line);border-radius:13px;padding:10px;background:#101010}.nd-v3-up strong{display:block;font-size:13px;color:#fff}.nd-v3-up small{display:block;color:#aaa;margin:4px 0 8px}.nd-v3-up button{width:100%;border:0;border-radius:9px;padding:8px;background:#242424;color:#fff;font-weight:800;cursor:pointer}.nd-v3-up button:hover{background:var(--nd-gold);color:#111}
.nd-v3-trust{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin:18px 0}.nd-v3-trust div{padding:11px 7px;text-align:center;border:1px solid var(--nd-line);border-radius:14px;background:#101010;font-size:11px;color:#aaa}.nd-v3-trust b{display:block;color:#fff;font-size:12px;margin-bottom:3px}.nd-v3-last{margin:10px 0;padding:12px 14px;border-radius:14px;background:#121212;border:1px solid var(--nd-line);display:none}.nd-v3-last button{float:right;border:0;background:var(--nd-gold);padding:7px 10px;border-radius:9px;font-weight:900}.nd-fav{z-index:4}.produto{transition:transform .18s ease,box-shadow .18s ease}.produto:hover{transform:translateY(-3px);box-shadow:0 12px 35px rgba(0,0,0,.25)}
@media(max-width:600px){.nd-v3-trust{grid-template-columns:1fr 1fr}.nd-v3-trust div:last-child{grid-column:1/-1}.nd-v3-buybar{bottom:8px}.nd-v3-buybar button{padding:11px 13px}}
</style>

<!-- ND BURGS REDESIGN 2026 -->
<style>
:root{--bg:#09090b;--surface:#141418;--surface2:#1d1d22;--red:#ff3b30;--red2:#b90016;--orange:#ff8a00;--gold:#ffd166;--text:#fff;--muted:#b8b8c2;--green:#25d366}body{background:radial-gradient(circle at 50% -10%,#35100c 0,#09090b 38%,#050506 100%);color:var(--text)}header{background:rgba(9,9,11,.92);backdrop-filter:blur(16px);border-bottom:1px solid rgba(255,59,48,.45);box-shadow:0 8px 30px rgba(0,0,0,.35)}h1,h2,.categoria-titulo{color:#fff;border-color:#2b2b32}.horarios-box,.produto,.carrinho,.formulario{background:linear-gradient(145deg,#1a1a20,#101014);border-color:#2c2c34;box-shadow:0 12px 30px rgba(0,0,0,.22)}.horarios-titulo,.preco,.total,.carrinho-flutuante-total,.modal-total strong:last-child{color:var(--gold)}.produto{border-radius:20px;transition:transform .22s,box-shadow .22s,border-color .22s}.produto:hover{transform:translateY(-5px);border-color:var(--red);box-shadow:0 18px 40px rgba(255,59,48,.13)}.produto-imagem{border-radius:14px;background:#09090b}.btn-add,.btn-confirmar-personalizacao,.btn-ver-carrinho{background:linear-gradient(135deg,var(--red),var(--orange));color:#fff;border-radius:12px;box-shadow:0 8px 20px rgba(255,59,48,.22)}.btn-add:hover,.btn-confirmar-personalizacao:hover,.btn-ver-carrinho:hover{background:linear-gradient(135deg,#ff4b40,#ff9e1b)}.categoria-btn{border-radius:14px;background:#17171c;border-color:#2c2c34}.categoria-btn:hover{border-color:var(--red);color:#fff;background:#211317}.carrinho-flutuante{background:rgba(18,18,22,.96);border-color:var(--red);border-radius:18px;backdrop-filter:blur(14px)}.painel-carrinho,.painel-finalizar,.modal-box{background:#131318;border-color:var(--red);border-radius:24px}.btn-finalizar-pedido,.btn-finalizar-modal{background:linear-gradient(135deg,#25d366,#149c4d)}.btn-continuar-comprando{background:linear-gradient(135deg,#ff7a00,#ffad16)}.toast-carrinho{background:linear-gradient(135deg,var(--green),#159a4d)}input,select,textarea{background:#0d0d11;border-color:#34343d;border-radius:12px}.aviso-taxa{background:#2a1606;border-color:var(--orange);color:var(--gold)}.opcao-tamanho input:checked+label{border-color:var(--red);background:#2b1315;color:#fff}.modal-secao h3{color:var(--orange)}.instagram-destaque{border-color:var(--red);border-radius:24px}.categoria{scroll-margin-top:100px}@media(max-width:600px){.produto{border-radius:16px}.produto-imagem{height:145px}.preco{font-size:18px;font-weight:900}.btn-add{font-size:12px;border-radius:10px}.categoria-btn{padding:14px 8px}.produtos{gap:10px}}
</style>

<style id="nd-round-1-base">
/* RODADA 1 — base 24h, mobile, estabilidade e performance */
#bloqueioHorario{display:none!important}
html{-webkit-text-size-adjust:100%;text-size-adjust:100%}
body{overflow-x:hidden}
img{max-width:100%;height:auto}
.produto-imagem{width:100%;height:205px;object-fit:contain}
button,.btn,.categoria-btn,.nd-fx-add,.nd-fx-minus,.nd-fx-plus{touch-action:manipulation}
button:focus-visible,a:focus-visible,input:focus-visible,select:focus-visible,textarea:focus-visible{outline:3px solid #ffd166;outline-offset:3px}
.status-aberto{white-space:nowrap}
@media(max-width:600px){
  body{padding-bottom:max(105px,calc(88px + env(safe-area-inset-bottom)))}
  .container{width:100%;max-width:100%;box-sizing:border-box}
  .horarios-box{align-items:flex-start!important}
  .horarios-linha{font-size:11px!important}
  .status-aberto{font-size:11px!important;white-space:normal}
  .produto-imagem{height:145px}
  button,.btn,.categoria-btn{min-height:44px}
}
@media(prefers-reduced-motion:reduce){
  html{scroll-behavior:auto!important}
  *,*::before,*::after{animation-duration:.01ms!important;animation-iteration-count:1!important;transition-duration:.01ms!important;scroll-behavior:auto!important}
}
</style>

<style id="nd-rodada-2-visual">
:root{--nd-black:#070707;--nd-surface:#111214;--nd-surface2:#18191c;--nd-red:#e50914;--nd-red2:#ff3038;--nd-gold:#f5c400;--nd-white:#fff;--nd-muted:#9b9da4;--nd-border:rgba(255,255,255,.085)}
body{background:radial-gradient(900px 420px at 50% -80px,rgba(229,9,20,.13),transparent 65%),radial-gradient(700px 360px at 15% 20%,rgba(245,196,0,.055),transparent 70%),#070707!important}
header{background:rgba(7,7,7,.90)!important;border-bottom:1px solid rgba(229,9,20,.30)!important;box-shadow:0 10px 40px rgba(0,0,0,.45)!important}
header .logo{filter:drop-shadow(0 8px 20px rgba(229,9,20,.18))!important}
.horarios-box{border-color:rgba(229,9,20,.28)!important;background:linear-gradient(135deg,rgba(255,255,255,.055),rgba(255,255,255,.018))!important}
.container>h1{font-size:clamp(32px,5vw,52px)!important;line-height:.98!important;letter-spacing:-2px!important;background:linear-gradient(180deg,#fff 20%,#fff 52%,#ff4b51 100%)!important;-webkit-background-clip:text!important;background-clip:text!important}
.container>h1:after{color:#777!important;letter-spacing:2.4px!important}
.categoria-menu{gap:9px!important;margin-bottom:20px!important}
.categoria-btn{border:1px solid rgba(255,255,255,.08)!important;background:linear-gradient(180deg,#18191b,#101113)!important;color:#ddd!important;border-radius:13px!important;box-shadow:0 5px 18px rgba(0,0,0,.18)!important;transition:transform .18s ease,border-color .18s ease,background .18s ease!important}
.categoria-btn:hover,.categoria-btn.active{border-color:rgba(229,9,20,.65)!important;background:linear-gradient(180deg,#211012,#131011)!important;color:#fff!important;transform:translateY(-1px)}
.categoria{position:relative}
.categoria>h2{font-size:clamp(22px,3vw,30px)!important;letter-spacing:-.7px!important;margin:28px 0 13px!important;display:flex;align-items:center;gap:10px}
.categoria>h2:before{content:"";width:5px;height:25px;border-radius:99px;background:linear-gradient(#ff3038,#e50914);box-shadow:0 0 16px rgba(229,9,20,.35)}
.produtos{gap:13px!important}
.produto{background:linear-gradient(180deg,rgba(24,25,28,.98),rgba(13,14,16,.98))!important;border:1px solid rgba(255,255,255,.075)!important;border-radius:18px!important;box-shadow:0 12px 35px rgba(0,0,0,.24)!important;overflow:hidden!important;transition:transform .2s ease,border-color .2s ease,box-shadow .2s ease!important}
.produto:hover{transform:translateY(-3px);border-color:rgba(229,9,20,.38)!important;box-shadow:0 18px 45px rgba(0,0,0,.36)!important}
.produto img,.produto-imagem{border-radius:13px!important}
.produto h3{font-weight:950!important;letter-spacing:-.35px!important}
.produto p{color:#a7a9af!important;line-height:1.4!important}
.preco{color:#fff!important;font-weight:950!important;text-shadow:0 0 18px rgba(255,255,255,.08)}
.btn-add,.nd-fx-add{background:linear-gradient(135deg,#e50914,#ff3038)!important;color:#fff!important;border:0!important;box-shadow:0 7px 20px rgba(229,9,20,.20)!important;font-weight:950!important}
.btn-add:hover,.nd-fx-add:hover{filter:brightness(1.08)!important;transform:translateY(-1px)}
.modern-search{border-color:rgba(255,255,255,.10)!important;background:rgba(13,14,16,.94)!important;box-shadow:0 12px 35px rgba(0,0,0,.24)!important}
.modern-search:focus-within{border-color:rgba(229,9,20,.55)!important;box-shadow:0 0 0 3px rgba(229,9,20,.08),0 12px 35px rgba(0,0,0,.28)!important}
.nd-v3-strip{background:linear-gradient(90deg,#090909,#171011,#090909)!important;border-bottom-color:rgba(229,9,20,.22)!important}
.nd-v3-strip b{color:#ff4b51!important}
.nd-v3-progress span{background:linear-gradient(90deg,#e50914,#ff3038)!important;box-shadow:0 0 12px rgba(229,9,20,.7)!important}
.nd-v3-buybar{border-color:rgba(229,9,20,.38)!important;background:rgba(12,12,13,.96)!important}
.nd-v3-buybar button,.nd-fx-cart-open{background:linear-gradient(135deg,#e50914,#ff3038)!important;color:#fff!important}
.item-carrinho-modal,.resumo-modal,.painel-finalizar,.nd-v4-summary{border-color:rgba(255,255,255,.09)!important}
.btn-finalizar-pedido,.nd-v4-next{background:linear-gradient(135deg,#e50914,#ff3038)!important;color:#fff!important;border-color:transparent!important;box-shadow:0 10px 28px rgba(229,9,20,.22)!important}
.btn-continuar-comprando{background:#202124!important;color:#fff!important;border-color:#303136!important}
.status-aberto{color:#6ff19a!important}
@media(max-width:700px){.container>h1{font-size:38px!important}.categoria>h2{font-size:21px!important}.produto{border-radius:15px!important}.produtos{gap:9px!important}.categoria-btn{min-height:44px!important}.btn-add,.nd-fx-add{min-height:44px!important}}
@media(prefers-reduced-motion:reduce){.produto,.categoria-btn,.btn-add,.nd-fx-add{transition:none!important}.produto:hover,.categoria-btn:hover,.btn-add:hover,.nd-fx-add:hover{transform:none!important}}
</style>

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
<script id="nd-rodada-4-logic">
(function(){
'use strict';
function enhance(){
 const modal=document.getElementById('modalFinalizar');
 if(!modal||modal.dataset.r4==='1')return;
 modal.dataset.r4='1';
 modal.addEventListener('input',function(e){
  const t=e.target;
  if(t.id==='telefoneModal'){
   let v=t.value.replace(/\D/g,'').slice(0,11);
   if(v.length>10)v=v.replace(/^(\d{2})(\d{5})(\d{0,4}).*$/,'($1) $2-$3');
   else if(v.length>6)v=v.replace(/^(\d{2})(\d{4})(\d{0,4}).*$/,'($1) $2-$3');
   else if(v.length>2)v=v.replace(/^(\d{2})(\d{0,5}).*$/,'($1) $2');
   else if(v.length)v='('+v;
   t.value=v;
  }
  if(['nomeModal','telefoneModal','numeroModal','complementoModal','observacaoModal'].includes(t.id)){
   try{localStorage.setItem('ndburgs_'+t.id,t.value)}catch(_){ }
  }
 });
 modal.addEventListener('click',function(e){
  const b=e.target.closest('.nd-v4-next');
  if(b){b.dataset.originalText=b.textContent;b.disabled=true;b.style.opacity='.72';setTimeout(()=>{b.disabled=false;b.style.opacity=''},900)}
 });
}
function restore(){
 ['nomeModal','telefoneModal','numeroModal','complementoModal','observacaoModal'].forEach(id=>{
  const el=document.getElementById(id);if(!el||el.value) return;
  try{const v=localStorage.getItem('ndburgs_'+id);if(v)el.value=v}catch(_){ }
 });
}
const obs=new MutationObserver(()=>{enhance();restore()});
window.addEventListener('DOMContentLoaded',()=>{enhance();restore();obs.observe(document.body,{childList:true,subtree:true})});
})();
</script>


<style id="nd-etapa21-sidebar-fix">
@media (min-width:901px){
  body{padding-left:230px!important;}
  .categoria-menu{display:none!important;}
  #nd18Sidebar{position:fixed!important;left:16px!important;top:110px!important;width:190px!important;max-height:calc(100vh - 130px)!important;overflow-y:auto!important;display:flex!important;flex-direction:column!important;gap:4px!important;padding:12px!important;background:#070707!important;border:1px solid #242424!important;border-radius:16px!important;z-index:9999!important;box-sizing:border-box!important;}
  #nd18Sidebar .nd18-title{display:block!important;color:#fff!important;font-size:13px!important;font-weight:700!important;letter-spacing:1px!important;padding:6px 8px 10px!important;}
  #nd18Sidebar button{width:100%!important;flex:none!important;margin:0!important;text-align:left!important;padding:11px 12px!important;background:#101010!important;color:#ddd!important;border:1px solid #202020!important;border-radius:10px!important;cursor:pointer!important;transition:.18s ease!important;}
  #nd18Sidebar button:hover,#nd18Sidebar button.ativo{background:#1677ff!important;color:#fff!important;border-color:#1677ff!important;transform:translateX(2px)!important;}
}
@media(max-width:900px){
  #nd18Sidebar{position:sticky!important;top:0!important;left:auto!important;width:100%!important;max-height:none!important;overflow-x:auto!important;overflow-y:hidden!important;display:flex!important;flex-direction:row!important;gap:6px!important;padding:8px!important;background:#050505!important;border-bottom:1px solid #202020!important;border-radius:0 0 12px 12px!important;z-index:9999!important;box-sizing:border-box!important;}
  #nd18Sidebar .nd18-title{display:none!important;}
  #nd18Sidebar button{flex:0 0 auto!important;width:auto!important;white-space:nowrap!important;margin:0!important;}
  .categoria-menu{display:none!important;}
}
</style>




<!-- ND BURGS R10 - MELHORIAS GERAIS -->
<style>
:root{--nd-accent:#ff4d00;--nd-accent2:#ffb000;--nd-card:#121212;--nd-soft:#1b1b1b;--nd-muted:#a9a9a9}
body{background:radial-gradient(circle at 50% -20%,#2b1205 0,#090909 42%)!important}
.produto{transition:transform .2s ease,box-shadow .2s ease;border:1px solid rgba(255,255,255,.06)!important;overflow:hidden}
.produto:hover{transform:translateY(-3px);box-shadow:0 14px 32px rgba(0,0,0,.35)}
.produto h3{letter-spacing:.2px}.produto .preco{font-weight:900!important;color:#ffb000!important;font-size:1.12em!important}
.btn-add{min-height:48px;border-radius:14px!important;font-weight:900!important;letter-spacing:.4px;box-shadow:0 8px 20px rgba(255,77,0,.16)}
.btn-add:active{transform:scale(.98)}
/* carrinho oficial */
#carrinhoFlutuante{position:fixed!important;left:50%!important;bottom:calc(16px + env(safe-area-inset-bottom))!important;transform:translateX(-50%) translateY(130%)!important;width:min(680px,calc(100% - 24px))!important;z-index:9998!important;border:1px solid rgba(255,255,255,.12)!important;border-radius:22px!important;background:linear-gradient(135deg,#ff4d00,#b51f00)!important;box-shadow:0 18px 45px rgba(0,0,0,.48)!important;padding:12px 14px!important;transition:transform .28s ease!important}
#carrinhoFlutuante.ativo{transform:translateX(-50%) translateY(0)!important}
#carrinhoFlutuante{cursor:pointer}
#carrinhoFlutuante::before{content:'🛒';display:grid;place-items:center;width:46px;height:46px;border-radius:15px;background:rgba(0,0,0,.2);font-size:23px;margin-right:10px;flex:none}
#carrinhoFlutuante .carrinho-flutuante-info{min-width:0}
#contadorCarrinho{font-weight:800!important;color:#fff!important}
#totalCarrinhoFlutuante{font-size:1.05rem!important}
.btn-ver-carrinho{border-radius:14px!important;background:#fff!important;color:#111!important;font-weight:950!important;padding:12px 14px!important}
#contadorCarrinho::after{content:' ';display:inline-block;width:7px;height:7px;background:#fff;border-radius:50%;margin-left:7px;vertical-align:middle}
/* checkout mais limpo */
#checkout,.formulario{border-radius:22px!important;border:1px solid rgba(255,255,255,.07)!important;box-shadow:0 12px 35px rgba(0,0,0,.22)}
input,select,textarea{border-radius:12px!important}
.modal-carrinho .modal-content,.modal-carrinho > div{border-radius:24px!important}
.vazio{text-align:center;padding:28px 14px!important;color:var(--nd-muted)}
/* acessibilidade */
button:focus-visible,input:focus-visible,select:focus-visible,textarea:focus-visible{outline:3px solid rgba(255,176,0,.55)!important;outline-offset:2px}
@media(max-width:600px){body{padding-bottom:105px!important}.produto:hover{transform:none}#carrinhoFlutuante{bottom:10px!important;width:calc(100% - 16px)!important;padding:10px!important;border-radius:18px!important}.btn-ver-carrinho{padding:11px!important;font-size:12px!important}#carrinhoFlutuante::before{width:40px;height:40px;font-size:20px}.carrinho-flutuante-info strong{font-size:13px!important}.carrinho-flutuante-total{font-size:.95rem!important}}
</style>


<style id="nd-r17-conversion">
/* =========================================================
   ND BURGS R19 — CONVERSÃO + FAVORITOS + PEDIR NOVAMENTE
   + HORÁRIO REAL + PRIMEIRA COMPRA + NAVEGAÇÃO MOBILE
   ========================================================= */
#ndR17FirstBuy{
  margin:18px 0 16px;padding:18px;border-radius:22px;
  border:1px solid rgba(255,59,48,.34);
  background:
    radial-gradient(circle at 90% 10%,rgba(255,59,48,.18),transparent 32%),
    linear-gradient(145deg,#171114,#0b0b0d);
  box-shadow:0 16px 42px rgba(0,0,0,.30);
}
.nd-r17-fb-kicker{font-size:10px;font-weight:1000;letter-spacing:1.6px;color:#ff7370}
.nd-r17-fb-title{margin-top:5px;font-size:clamp(24px,4vw,34px);font-weight:1000;line-height:1.02}
.nd-r17-fb-text{margin-top:8px;color:#aaa;font-size:12px;line-height:1.5;max-width:680px}
.nd-r17-fb-row{display:flex;align-items:center;gap:10px;flex-wrap:wrap;margin-top:13px}
.nd-r17-fb-price{font-size:24px;font-weight:1000;color:#ffd166}
.nd-r17-fb-btn{border:0;border-radius:12px;padding:12px 16px;background:linear-gradient(135deg,#e50914,#ff4b40);color:#fff;font-weight:1000;cursor:pointer;box-shadow:0 8px 22px rgba(229,9,20,.20)}
.nd-r17-fb-btn:hover{filter:brightness(1.08);transform:translateY(-1px)}

#ndR17Trust{
  display:grid;grid-template-columns:repeat(4,1fr);gap:9px;margin:16px 0 20px
}
.nd-r17-trust-card{
  padding:13px 10px;border:1px solid rgba(255,255,255,.08);border-radius:15px;
  background:linear-gradient(145deg,#141418,#0d0d10);text-align:center
}
.nd-r17-trust-icon{font-size:20px;display:block;margin-bottom:5px}
.nd-r17-trust-card strong{display:block;font-size:11px;color:#fff}
.nd-r17-trust-card span{display:block;margin-top:3px;font-size:9px;color:#85858d;line-height:1.35}

#ndR17FavSection,#ndR17LastSection{
  margin:22px 0;padding:17px;border:1px solid #25252b;border-radius:20px;
  background:linear-gradient(160deg,#111114,#08080a)
}
.nd-r17-section-head{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-bottom:12px}
.nd-r17-section-head h2{margin:0!important;border:0!important;padding:0!important;color:#fff!important;font-size:21px!important}
.nd-r17-section-head small{color:#777;font-size:9px;text-align:right}
.nd-r17-fav-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:9px}
.nd-r17-fav-item{
  display:flex;align-items:center;justify-content:space-between;gap:9px;
  padding:11px;border:1px solid #28282e;border-radius:13px;background:#0d0d10
}
.nd-r17-fav-item strong{display:block;font-size:12px;color:#fff}
.nd-r17-fav-item span{display:block;color:#ffb000;font-size:11px;font-weight:900;margin-top:3px}
.nd-r17-fav-item button{
  border:0;border-radius:9px;padding:8px 9px;background:#e50914;color:#fff;font-weight:1000;cursor:pointer;white-space:nowrap
}
.nd-r17-empty{color:#777;font-size:11px;line-height:1.5;padding:6px 0}

.nd-r17-heart{
  position:absolute;right:10px;top:10px;z-index:12;width:36px;height:36px;border-radius:50%;
  border:1px solid rgba(255,255,255,.12);background:rgba(8,8,10,.88);color:#aaa;
  display:grid;place-items:center;font-size:18px;cursor:pointer;backdrop-filter:blur(8px)
}
.nd-r17-heart.active{color:#ff3b30;border-color:rgba(255,59,48,.65);background:rgba(65,10,13,.92)}
.produto{position:relative!important}

#ndR17BottomNav{
  display:none;position:fixed;left:8px;right:8px;bottom:8px;z-index:12000;
  grid-template-columns:repeat(4,1fr);gap:5px;padding:7px;
  border:1px solid rgba(255,59,48,.38);border-radius:18px;
  background:rgba(12,12,14,.96);backdrop-filter:blur(18px);box-shadow:0 15px 45px rgba(0,0,0,.72)
}
.nd-r17-nav-btn{border:0;background:transparent;color:#aaa;border-radius:12px;padding:8px 3px;min-height:48px;font-size:9px;font-weight:1000;cursor:pointer}
.nd-r17-nav-btn b{display:block;font-size:18px;margin-bottom:2px}
.nd-r17-nav-btn.active,.nd-r17-nav-btn:hover{color:#fff;background:rgba(229,9,20,.12)}

#ndR17StatusNote{
  margin-top:9px;padding:9px 11px;border-radius:11px;background:#101014;
  border:1px solid rgba(255,255,255,.07);font-size:10px;color:#999;line-height:1.45
}
#ndR17StatusNote b{color:#fff}

.nd-r17-best-card{outline:2px solid rgba(255,59,48,.18)!important;box-shadow:0 18px 45px rgba(255,59,48,.10)!important}
.nd-r17-best-badge{
  position:absolute;left:10px;top:10px;z-index:11;padding:6px 8px;border-radius:8px;
  background:linear-gradient(135deg,#ffd166,#ff9f1c);color:#171000;font-size:9px;font-weight:1000
}
.nd-r17-best-card .preco{font-size:23px!important;color:#ffd166!important}

@media(max-width:800px){
  #ndR17Trust{grid-template-columns:1fr 1fr}
  #ndR17BottomNav{display:grid}
  body{padding-bottom:145px!important}
  #ndR17FirstBuy{margin:12px 0;padding:15px}
  .nd-r17-fb-btn{width:100%}
  .nd-r17-fb-row{display:block}
  .nd-r17-fb-price{margin-bottom:9px}
  .nd-r17-fav-grid{grid-template-columns:1fr}
}
@media(prefers-reduced-motion:reduce){
  .nd-r17-fb-btn{transition:none!important}
}
</style>



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



<style id="nd-r23-menu-desserts-upgrade">
/* ND BURGS R23 — categoria unificada + ofertas em posições estratégicas */
#sobremesas .categoria-titulo{
  font-size:clamp(20px,3vw,28px)!important;
  line-height:1.15!important;
}
#ndUvaPromo{
  scroll-margin-top:110px;
}
#ndR17FirstBuy{
  scroll-margin-top:110px;
}
@media(max-width:700px){
  #sobremesas .categoria-titulo{
    font-size:19px!important;
  }
}
</style>

</head>

<body>

<!-- ND R17: horário comercial real — terça a domingo, 18:00 às 00:30 -->

<header class="nd-clean-header">
  <div class="nd-top-info" aria-label="Informações de atendimento e entrega">
    <div class="nd-info-3d">
      <span class="nd-info-icon">🕐</span>
      <div><small>HORÁRIO DE ATENDIMENTO</small><strong>TERÇA A DOMINGO • 18:00 ÀS 00:30</strong><em>SEGUNDA: FECHADO</em></div>
    </div>
    <div class="nd-info-3d">
      <span class="nd-info-icon">🛵</span>
      <div><small>TEMPO DE ENTREGA</small><strong>40–50 MINUTOS</strong><em>CONSULTE A TAXA NO CHECKOUT</em></div>
    </div>
  </div>
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


<div class="horarios" style="display:none!important"><div class="horarios-box"><div id="statusHorario" class="status-aberto">🟢 ABERTO • TERÇA A DOMINGO • 18:00 ÀS 00:30</div></div></div>

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
🍨 AÇAÍS - MILKSHAKES E SOBREMESAS
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
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO DOCE',32.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/cSLMFXtL/COMBO-GELADO.png" alt="COMBO GELADO">
<h3>COMBO GELADO</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 40,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO GELADO',40.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/5WM7335K/5-ESTRELAS.png" alt="COMBO 5 ESTRELAS">
<h3>COMBO 5 ESTRELAS</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 45,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO 5 ESTRELAS',45.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/twFJ6Vwt/COMBO-DIETA-SO-SEGUNDA.png" alt="COMBO DIETA SÓ SEGUNDA">
<h3>COMBO DIETA SÓ SEGUNDA</h3>
<p>Coca lata + doce surpresa + pastel.</p>
<div class="preco">R$ 27,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO DIETA SÓ SEGUNDA',27.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/HLNHv9tt/COMBO-MAIS-VENDIDO-NOVO.png" alt="COMBO MAIS VENDIDO">
<h3>COMBO MAIS VENDIDO</h3>
<p>Um dos combos especiais da ND BURGS.</p>
<div class="preco">R$ 20,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO MAIS VENDIDO',20.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/PvJqcwzb/MOTACA-ND.png" alt="COMBO MOTOCA ND">
<h3>COMBO MOTOCA ND</h3>
<p>Combo especial ND BURGS.</p>
<div class="preco">R$ 32,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO MOTOCA ND',32.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/QR0388c/COMBO-S-LOVE.png" alt="COMBO SÓ LOVE">
<h3>COMBO SÓ LOVE</h3>
<p>Combo especial para compartilhar.</p>
<div class="preco">R$ 71,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('COMBO SÓ LOVE',71.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/23CmpQqn/DATE-COM-ND-BURGS.png" alt="DATE COM NDBURGS">
<h3>DATE COM NDBURGS</h3>
<p>Combo especial para o seu date.</p>
<div class="preco">R$ 70,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('DATE COM NDBURGS',70.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Lz9JQx8f/01-NDBURGS.png" alt="01 ND BURGS">
<h3>01 ND BURGS</h3>
<p>Combo especial.</p>
<div class="preco">R$ 50,90</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('01 ND BURGS',50.90)">ADICIONAR</button>
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
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO SÓ LOVE',90.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/5WM7335K/5-ESTRELAS.png" alt="COMBO 5 ESTRELAS">
<h3>ARTESANAL COMBO 5 ESTRELAS</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 70,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO 5 ESTRELAS',70.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/HLNHv9tt/COMBO-MAIS-VENDIDO-NOVO.png" alt="COMBO MAIS VENDIDO">
<h3>ARTESANAL COMBO MAIS VENDIDO</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 34,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO MAIS VENDIDO',34.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/wNQqzkSf/COMBO-DOCE.png" alt="COMBO DOCE">
<h3>ARTESANAL COMBO DOCE</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 44,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO DOCE',44.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/cSLMFXtL/COMBO-GELADO.png" alt="COMBO GELADO">
<h3>ARTESANAL COMBO GELADO</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 52,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL COMBO GELADO',52.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/23CmpQqn/DATE-COM-ND-BURGS.png" alt="DATE COM NDBURGS">
<h3>ARTESANAL DATE COM NDBURGS</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 91,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL DATE COM NDBURGS',91.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/PvJqcwzb/MOTACA-ND.png" alt="COMBO MOTOCA ND">
<h3>ARTESANAL MOTOCA ND</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 41,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL MOTOCA ND',41.80)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Lz9JQx8f/01-NDBURGS.png" alt="01 ND BURGS">
<h3>ARTESANAL 01 ND BURGS</h3>
<p>Combo artesanal especial.</p>
<div class="preco">R$ 96,80</div>
<button class="btn btn-add" onclick="abrirComboPersonalizacao('ARTESANAL 01 ND BURGS',96.80)">ADICIONAR</button>
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

<section id="sobremesas" class="categoria">

<div class="categoria-titulo">
🍨 AÇAÍS - MILKSHAKES E SOBREMESAS
</div>

<div class="produtos">

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Kxj5h5Km/Chat-GPT-Image-28-07-2026-18-32-28.png" alt="AÇAÍ">
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

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/ksyxPyr2/Chat-GPT-Image-26-06-2026-00-10-12.png" alt="KITKAT">
<h3>KITKAT</h3>
<p>Doce especial.</p>
<div class="preco">R$ 7,00</div>
<button class="btn btn-add" onclick="adicionar('KITKAT',7)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/9kC6V4gP/Chat-GPT-Image-5-09-2026-06-50-46.png" alt="SURPRESA DE UVA">
<h3>SURPRESA DE UVA</h3>
<p>Sobremesa especial.</p>
<div class="preco">R$ 12,00</div>
<button class="btn btn-add" onclick="adicionar('SURPRESA DE UVA',12)">ADICIONAR</button>
</div>

</div>
</section>

<section id="bebidas" class="categoria">

<div class="categoria-titulo">
🥤 BEBIDAS
</div>

<div class="produtos">

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/r2zDycx0/Chat-GPT-Image-4-09-2026-21-18-50.png" alt="COCA COLA LATA 350ML">
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

<section id="adicionais" class="categoria">

<div class="categoria-titulo">
➕ ADICIONAIS
</div>

<div class="produtos">

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/ZRydT4hD/fatia-de-queijo.png" alt="FATIA QUEIJO CHEDDAR EXTRA">
<h3>FATIA QUEIJO CHEDDAR EXTRA</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('FATIA QUEIJO CHEDDAR EXTRA',3)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/wZfS9rn1/hamburguer-artesanal.png" alt="HAMBURGUER EXTRA ARTESANAL">
<h3>HAMBURGUER EXTRA ARTESANAL</h3>
<p>Adicional.</p>
<div class="preco">R$ 9,00</div>
<button class="btn btn-add" onclick="adicionar('HAMBURGUER EXTRA ARTESANAL',9)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/TqhkXgRF/HAMBURGUER-TRADICIONAL.png" alt="HAMBURGUER EXTRA TRADICIONAL">
<h3>HAMBURGUER EXTRA TRADICIONAL</h3>
<p>Adicional.</p>
<div class="preco">R$ 2,50</div>
<button class="btn btn-add" onclick="adicionar('HAMBURGUER EXTRA TRADICIONAL',2.50)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/6RxLhQBG/adicional-bacon.png" alt="BACON">
<h3>BACON</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('BACON',3)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/n8KHqTMg/potinho-barbecue.png" alt="POTINHO BARBECUE">
<h3>POTINHO BARBECUE</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO BARBECUE',3)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/DDCZpVLW/potinho-maionese-verde.png" alt="POTINHO MAIONESE VERDE">
<h3>POTINHO MAIONESE VERDE</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO MAIONESE VERDE',3)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/DHNQ0kwS/potinho-cheddar.png" alt="POTINHO CHEDDAR">
<h3>POTINHO CHEDDAR</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO CHEDDAR',3)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Y4DcTLwD/maionese-artesanal.png" alt="POTINHO MAIONESE ARTESANAL">
<h3>POTINHO MAIONESE ARTESANAL</h3>
<p>Molho extra.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('POTINHO MAIONESE ARTESANAL',3)">ADICIONAR</button>
</div>


<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/6RxLhQBG/adicional-bacon.png" alt="ADICIONAL BACON">
<h3>ADICIONAL BACON</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('ADICIONAL BACON',3)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/cHt8ZjS/adicional-molho-cheddar.png" alt="ADICIONAL CHEDDAR">
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
`</div></div><div class="modal-total"><span>TOTAL</span><strong id="modalTotalPastel">ESCOLHA UM SABOR</strong></div><button class="btn btn-confirmar-personalizacao" onclick="confirmarPersonalizacaoPastel()">✅ ADICIONAR AO CARRINHO</button>`;

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

<style id="nd-r29-clean">
html{scroll-behavior:auto!important;overflow-x:hidden}
body{overflow-x:hidden}
.nd-clean-header{position:sticky;top:0;z-index:10000;padding:10px 12px 12px!important;background:#05080c!important;border-bottom:1px solid rgba(42,150,255,.55)!important;box-shadow:0 8px 35px rgba(0,0,0,.65),0 0 28px rgba(0,105,255,.12)!important}
.nd-top-info{width:min(1100px,100%);margin:0 auto 10px;display:grid;grid-template-columns:1fr 1fr;gap:10px}
.nd-info-3d{min-width:0;display:flex;align-items:center;gap:10px;padding:11px 13px;border-radius:14px;color:#fff;background:linear-gradient(145deg,#020305,#11151b 55%,#030406);border:1px solid rgba(70,166,255,.65);box-shadow:inset 0 1px 0 rgba(255,255,255,.10),inset 0 -8px 18px rgba(0,0,0,.65),0 7px 18px rgba(0,0,0,.6),0 0 20px rgba(0,125,255,.12);position:relative;overflow:hidden}
.nd-info-3d:before{content:"";position:absolute;inset:-60% -20%;background:linear-gradient(105deg,transparent 42%,rgba(55,165,255,.18) 48%,rgba(255,255,255,.22) 50%,transparent 57%);transform:rotate(-8deg);animation:ndBlueRef 5s linear infinite;pointer-events:none}
@keyframes ndBlueRef{from{transform:translateX(-65%) rotate(-8deg)}to{transform:translateX(65%) rotate(-8deg)}}
.nd-info-icon{position:relative;z-index:1;font-size:25px;filter:drop-shadow(0 0 8px rgba(50,160,255,.7))}.nd-info-3d div{position:relative;z-index:1;min-width:0}.nd-info-3d small{display:block;color:#fff;font-size:9px;font-weight:900;letter-spacing:1px}.nd-info-3d strong{display:block;color:#fff;font-size:13px;margin-top:3px;white-space:nowrap}.nd-info-3d em{display:block;color:#b9c5d2;font-style:normal;font-size:9px;margin-top:3px}
.nd-clean-header .logo{display:block;margin:2px auto 0;width:125px!important;max-width:48%;filter:drop-shadow(0 8px 22px rgba(30,135,255,.28))}
.nd-r29-section{max-width:1180px;margin:14px auto;padding:14px 15px;border:1px solid rgba(65,151,255,.22);border-radius:20px;background:linear-gradient(145deg,rgba(18,22,28,.96),rgba(6,8,11,.98));box-shadow:0 15px 45px rgba(0,0,0,.32)}
.nd-r29-head{display:flex;justify-content:space-between;align-items:end;gap:10px;margin-bottom:10px}.nd-r29-head h2{margin:0;border:0;color:#fff;font-size:21px}.nd-r29-head span{color:#7dbdff;font-size:10px;font-weight:900;letter-spacing:1px}
.nd-r29-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:9px}.nd-r29-card{display:flex;gap:9px;align-items:center;padding:9px;border:1px solid rgba(255,255,255,.08);border-radius:15px;background:#0d1014;min-width:0}.nd-r29-card img{width:70px;height:70px;object-fit:contain;border-radius:10px;background:#07090b;flex:0 0 70px}.nd-r29-card-info{min-width:0;flex:1}.nd-r29-card-info strong{display:block;font-size:12px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}.nd-r29-card-info .price{display:block;color:#ffd83d;font-weight:900;margin:4px 0;font-size:13px}.nd-r29-add{width:100%;border:0;border-radius:8px;padding:8px;background:#ffd21a;color:#090909;font-weight:900;cursor:pointer}
.nd-r29-upsell{display:none}.nd-r29-upsell.show{display:block}.nd-r29-up-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:9px}.nd-r29-up{padding:10px;border:1px solid rgba(255,255,255,.08);border-radius:14px;background:#0d1014}.nd-r29-up img{width:100%;height:100px;object-fit:contain;border-radius:9px;background:#07090b}.nd-r29-up strong{display:block;font-size:12px;margin-top:7px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}.nd-r29-up .up-price{color:#ffd83d;font-weight:900;margin:4px 0;font-size:13px}.nd-r29-qty{display:flex;align-items:center;justify-content:space-between;gap:7px;margin:7px 0}.nd-r29-qty button{width:32px;height:32px;border:0;border-radius:8px;background:#252a31;color:#fff;font-weight:900;font-size:17px}.nd-r29-qty b{font-size:13px}.nd-r29-up-add{width:100%;border:0;border-radius:9px;padding:9px;background:linear-gradient(135deg,#ffd21a,#ff9e00);color:#050505;font-weight:900;cursor:pointer}.nd-r29-random .nd-r29-card{min-height:88px}
@media(max-width:600px){.nd-top-info{grid-template-columns:1fr;gap:7px}.nd-info-3d{padding:9px 10px}.nd-info-3d strong{font-size:11px}.nd-info-3d em{font-size:8px}.nd-clean-header .logo{width:112px!important}.nd-r29-section{margin:10px 8px;padding:11px}.nd-r29-grid,.nd-r29-up-grid{grid-template-columns:1fr}.nd-r29-card img{width:62px;height:62px;flex-basis:62px}.nd-r29-up img{height:120px}}
@media(prefers-reduced-motion:reduce){.nd-info-3d:before{animation:none}}
</style>
<script>
(function(){
'use strict';
const $=s=>document.querySelector(s), $$=s=>Array.from(document.querySelectorAll(s));
const norm=s=>String(s||'').normalize('NFD').replace(/[\u0300-\u036f]/g,'').toUpperCase().trim();
function money(n){return Number(n||0).toLocaleString('pt-BR',{style:'currency',currency:'BRL'});}
function cardsBy(ids){let a=[];ids.forEach(id=>{const sec=document.getElementById(id);if(sec)a.push(...sec.querySelectorAll('.produto'));});return a;}
function dataCard(c){const name=c?.querySelector('h3')?.textContent?.trim()||'';const pt=c?.querySelector('.preco')?.textContent||'';const m=pt.match(/(\d{1,3}(?:\.\d{3})*,\d{2}|\d+\.\d{2})/);if(!name||!m)return null;const price=parseFloat(m[1].replace(/\./g,'').replace(',','.'));return {c,name,price,img:c.querySelector('img')?.src||'',btn:c.querySelector('.btn-add')};}
function addDirect(d,qty){if(!d?.btn)return;for(let i=0;i<qty;i++)d.btn.click();}
function makeSection(id,title,kicker,items){if(document.getElementById(id))return;const sec=document.createElement('section');sec.id=id;sec.className='nd-r29-section';sec.innerHTML='<div class="nd-r29-head"><div><span>'+kicker+'</span><h2>'+title+'</h2></div></div><div class="nd-r29-grid"></div>';const grid=sec.querySelector('.nd-r29-grid');items.forEach((d,i)=>{const el=document.createElement('div');el.className='nd-r29-card';el.innerHTML='<img src="'+d.img.replace(/"/g,'&quot;')+'" alt=""><div class="nd-r29-card-info"><strong>'+(i+1)+'. '+d.name.replace(/[<>]/g,'')+'</strong><span class="price">'+money(d.price)+'</span><button class="nd-r29-add" type="button">ADICIONAR</button></div>';el.querySelector('button').onclick=()=>addDirect(d,1);grid.appendChild(el);});const anchor=$('.categoria-menu')||$('.container');if(anchor)anchor.parentNode.insertBefore(sec,anchor);else document.body.prepend(sec);}
function buildTop3(){const preferred=['COMBO MAIS VENDIDO','X-BACON','COMBO 5 ESTRELAS','PATAO','BERENICE','COMBO SÓ LOVE'];const all=cardsBy(['combos','tradicionais','artesanais','combosArtesanais']);const ds=all.map(dataCard).filter(Boolean);const picked=[];preferred.forEach(n=>{const d=ds.find(x=>norm(x.name)===norm(n));if(d&&!picked.some(x=>x.name===d.name))picked.push(d)});ds.forEach(d=>{if(picked.length<3&&!picked.some(x=>x.name===d.name))picked.push(d)});makeSection('ndR29Top3','TOP 3','🔥 ITENS MAIS VENDIDOS DO DIA',picked.slice(0,3));}
function buildRandom(){const groups=[cardsBy(['combos']),cardsBy(['tradicionais','artesanais','combosArtesanais']),cardsBy(['sobremesas'])];let pool=groups.flatMap(g=>g.map(dataCard).filter(Boolean));pool=pool.sort(()=>Math.random()-.5);const picks=[];groups.forEach(g=>{const x=g.map(dataCard).filter(Boolean).sort(()=>Math.random()-.5)[0];if(x)picks.push(x)});pool.forEach(d=>{if(picks.length<6&&!picks.some(x=>x.name===d.name))picks.push(d)});makeSection('ndR29Random','PRODUTOS ALEATÓRIOS','🎲 ESCOLHAS PARA VOCÊ',picks.slice(0,6));}
function classifyCart(){const names=(window.carrinho||[]).map(x=>norm(x.nome)).join(' ');if(/BATATA|NUGGET|ANEL DE CEBOLA|FRANGO FRITO|PORCAO/.test(names))return 'lanche';if(/COMBO|X-BURGUER|X-BACON|X-SALADA|X-EGG|SELLIS|PATAO|BERENICE|DINA|GADEIA|GAROTINHO|NUNES|PEZAO/.test(names))return 'lanche';if(/AÇAI|ACAI|MILKSHAKE|SOBREMESA|SURPRESA|PASTEL/.test(names))return 'doce';return 'geral';}
function buildUpsell(){let sec=document.getElementById('ndR29Upsell');if(!sec){sec=document.createElement('section');sec.id='ndR29Upsell';sec.className='nd-r29-section nd-r29-upsell';sec.innerHTML='<div class="nd-r29-head"><div><span>💡 COMPLEMENTE SEU PEDIDO</span><h2>Que tal adicionar?</h2></div></div><div class="nd-r29-up-grid"></div>';const panel=$('.painel-carrinho');if(panel)panel.prepend(sec);else document.body.appendChild(sec);}renderUpsell();}
function renderUpsell(){const sec=document.getElementById('ndR29Upsell');if(!sec)return;const grid=sec.querySelector('.nd-r29-up-grid');if(!window.carrinho?.length){sec.classList.remove('show');return}const all=cardsBy(['porcoes','sobremesas','bebidas','tradicionais','combos','artesanais','combosArtesanais']).map(dataCard).filter(Boolean);const cartNames=new Set((window.carrinho||[]).map(x=>norm(x.nome)));let preferred=classifyCart()==='lanche'?[/BATATA/,/COCA|GUARANA|FANTA|SPRITE|DOLLY/,/SURPRESA DE UVA|MILKSHAKE|PASTEL/] : [/SURPRESA DE UVA|MILKSHAKE|PASTEL/,/COCA|GUARANA|FANTA|SPRITE|DOLLY/,/BATATA|NUGGET|ANEL/];let pool=[];preferred.forEach(rx=>{const d=all.find(x=>!cartNames.has(norm(x.name))&&rx.test(norm(x.name)));if(d&&!pool.some(y=>y.name===d.name))pool.push(d)});all.forEach(d=>{if(pool.length<3&&!cartNames.has(norm(d.name))&&!pool.some(y=>y.name===d.name))pool.push(d)});grid.innerHTML='';pool.slice(0,3).forEach(d=>{const el=document.createElement('div');el.className='nd-r29-up';el.innerHTML='<img src="'+d.img.replace(/"/g,'&quot;')+'" alt=""><strong>'+d.name.replace(/[<>]/g,'')+'</strong><span class="up-price">'+money(d.price)+' cada</span><div class="nd-r29-qty"><button type="button" class="minus">−</button><b>1</b><button type="button" class="plus">+</button></div><button type="button" class="nd-r29-up-add">ADICIONAR AO CARRINHO • '+money(d.price)+'</button></div>';let q=1,b=el.querySelector('b'),btn=el.querySelector('.nd-r29-up-add');el.querySelector('.minus').onclick=()=>{q=Math.max(1,q-1);b.textContent=q;btn.textContent='ADICIONAR AO CARRINHO • '+money(d.price*q)};el.querySelector('.plus').onclick=()=>{q=Math.min(9,q+1);b.textContent=q;btn.textContent='ADICIONAR AO CARRINHO • '+money(d.price*q)};btn.onclick=()=>{addDirect(d,q);renderUpsell();};grid.appendChild(el)});sec.classList.toggle('show',pool.length>0);}
function patchCart(){if(typeof window.atualizarCarrinho!=='function'||window.atualizarCarrinho.__ndR29)return;const old=window.atualizarCarrinho;window.atualizarCarrinho=function(){const r=old.apply(this,arguments);setTimeout(renderUpsell,30);return r};window.atualizarCarrinho.__ndR29=true;}
function stableScroll(){window.irPara=function(id){const e=document.getElementById(id);if(!e)return;e.scrollIntoView({behavior:'auto',block:'start'});};window.irParaCheckout=function(){const m=document.getElementById('modalCarrinho');if(m)m.classList.remove('ativo');document.body.style.overflow='';const e=document.getElementById('checkout');if(e)e.scrollIntoView({behavior:'auto',block:'start'});};}
function hours(){const status=document.getElementById('statusHorario');if(!status)return;const d=new Date().getDay(),open=d>=2;status.className=open?'status-aberto':'status-fechado';status.textContent=open?'🟢 ABERTO • 18:00 ÀS 00:30':'🔴 FECHADO • SEGUNDA-FEIRA';}
function cleanupOldSuggestion(){const m=document.getElementById('suggestionsModal');if(m)m.remove();}
function boot(){stableScroll();cleanupOldSuggestion();hours();buildTop3();buildRandom();buildUpsell();patchCart();setTimeout(()=>{renderUpsell();hours();},300);}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',boot,{once:true});else boot();
window.addEventListener('scroll',()=>{}, {passive:true});
})();
</script>
</body>
</html>
