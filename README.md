<html lang="pt-BR">
<head>
<!-- ND BURGS: controle de versão para evitar conteúdo antigo em cache -->
<meta name="nd-site-version" content="20260907-R29">
<script>
(function () {
  const ND_SITE_VERSION = "20260907-R29";
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
</head>
<body>

<!-- ND R17: horário comercial real — terça a domingo, 18:00 às 00:30 -->

<header>
  <div class="nd-top-info" aria-label="Informações de atendimento">
    <div class="nd-top-card"><span class="nd-top-label">HORÁRIO DE ATENDIMENTO</span><strong>18:00 ÀS 00:30</strong><small>TERÇA A DOMINGO • SEGUNDA FECHADO</small><span id="statusHorario" class="nd-top-status">● VERIFICANDO HORÁRIO</span></div>
    <div class="nd-top-card"><span class="nd-top-label">TEMPO DE ENTREGA</span><strong>40 A 50 MIN</strong><small>PRAZO MÉDIO • PEDIDO FRESQUINHO</small><span class="nd-top-status nd-delivery-status">● DELIVERY</span></div>
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
<!-- ND BURGS ETAPA 18 - CATEGORIAS LATERAIS -->
<style>
#nd18Sidebar{position:fixed;left:18px;top:50%;transform:translateY(-50%);width:205px;max-height:78vh;overflow:auto;background:#050505;border:1px solid #292929;border-radius:16px;padding:10px;z-index:7000;box-shadow:0 12px 35px rgba(0,0,0,.65)}
#nd18Sidebar .nd18-title{font-size:12px;letter-spacing:1.2px;color:#888;padding:6px 9px 10px;border-bottom:1px solid #222;margin-bottom:7px}
#nd18Sidebar button{display:block;width:100%;text-align:left;background:#101010;color:#d8d8d8;border:1px solid #222;border-radius:10px;padding:11px 10px;margin:5px 0;cursor:pointer;font-size:14px;font-weight:400;transition:transform .18s,background .18s,border-color .18s,color .18s}
#nd18Sidebar button:hover{background:#0759c9;border-color:#1475ff;color:#fff;transform:translateX(3px)}
#nd18Sidebar button.ativo{background:#0759c9;border-color:#1475ff;color:#fff;box-shadow:0 5px 15px rgba(0,89,210,.25)}
#nd18Sidebar::-webkit-scrollbar{width:5px}#nd18Sidebar::-webkit-scrollbar-thumb{background:#333;border-radius:10px}
@media(min-width:901px){
 body{padding-left:235px!important}
 .container{max-width:1100px}
 #nd18Sidebar{display:block}
}
@media(max-width:900px){
 #nd18Sidebar{position:sticky;top:72px;left:auto;transform:none;width:calc(100% - 20px);max-height:none;margin:8px auto 12px;display:flex;gap:7px;overflow-x:auto;overflow-y:hidden;padding:8px;z-index:8500;border-radius:13px}
 #nd18Sidebar .nd18-title{display:none}
 #nd18Sidebar button{flex:0 0 auto;width:auto;margin:0;white-space:nowrap;padding:9px 12px;font-size:13px}
}
@media(max-width:600px){body{padding-left:0!important}#nd18Sidebar{top:65px;width:calc(100% - 14px);margin-bottom:8px}}
@media(prefers-reduced-motion:reduce){#nd18Sidebar button{transition:none}}
</style>
<script>
(function(){
 function norm(t){return (t||'').replace(/\s+/g,' ').trim()}
 function build(){
  if(document.getElementById('nd18Sidebar'))return;
  const cats=[...document.querySelectorAll('.categoria')];
  if(!cats.length)return;
  const nav=document.createElement('nav');nav.id='nd18Sidebar';nav.setAttribute('aria-label','Categorias do cardápio');
  const title=document.createElement('div');title.className='nd18-title';title.textContent='CATEGORIAS';nav.appendChild(title);
  cats.forEach((cat,i)=>{
   const heading=cat.querySelector('.categoria-titulo,h2'); if(!heading)return;
   if(!cat.id)cat.id='nd18-cat-'+i;
   const b=document.createElement('button');b.type='button';b.textContent=norm(heading.textContent).replace(/^\S+\s+/,'');b.dataset.target=cat.id;
   b.onclick=function(){document.getElementById(this.dataset.target)?.scrollIntoView({behavior:'smooth',block:'start'})};
   nav.appendChild(b);
  });
  document.body.appendChild(nav);
  const buttons=[...nav.querySelectorAll('button')];
  const io=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting){buttons.forEach(b=>b.classList.toggle('ativo',b.dataset.target===e.target.id))}})},{rootMargin:'-20% 0px -65% 0px',threshold:0});
  cats.forEach(c=>io.observe(c));
  if(buttons[0])buttons[0].classList.add('ativo');
 }
 if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',build);else build();
 setTimeout(build,700);
})();
</script>

<style id="nd-etapa19-css">
/* ND BURGS — ETAPA 19: refinamento final, sem alterar a lógica existente */
:root{--nd19-blue:#1677ff;--nd19-blue2:#0b5ed7;--nd19-border:#242424;--nd19-soft:#111;--nd19-text:#f5f5f5;--nd19-muted:#aaa}
html,body{background:#000!important;background-image:none!important}
body{overflow-x:hidden}
/* área principal mais organizada quando existe a navegação lateral da etapa 18 */
@media (min-width:901px){
 body{padding-left:210px!important}
 .nd18-cat-nav{left:14px!important;right:auto!important;top:120px!important;width:178px!important;max-height:calc(100vh - 145px)!important;border:1px solid var(--nd19-border)!important;border-radius:16px!important;background:#080808!important;box-shadow:0 8px 28px rgba(0,0,0,.65)!important;padding:10px!important;z-index:10000!important}
 .nd18-cat-nav button{width:100%!important;text-align:left!important;border-radius:10px!important;margin:3px 0!important;padding:11px 12px!important;background:#0e0e0e!important;color:#ddd!important;border:1px solid transparent!important;transition:.18s ease!important}
 .nd18-cat-nav button:hover,.nd18-cat-nav button.ativo{background:#1677ff!important;color:#fff!important;border-color:#1677ff!important;transform:translateX(3px)!important}
}
/* títulos */
h1,h2,h3{letter-spacing:.1px}
.categoria-titulo,h2{scroll-margin-top:90px}
.produto h3,.produto .nome,.produto .produto-nome{font-weight:400!important;font-size:clamp(18px,2vw,23px)!important;line-height:1.18!important}
/* preço: destaque forte, sem transformar nome em negrito */
.produto .preco,.produto .preco-produto,.produto [class*="preco"]{font-weight:800!important;font-size:clamp(19px,2.1vw,25px)!important;text-shadow:0 0 7px rgba(22,119,255,.65),0 0 16px rgba(22,119,255,.22)!important}
/* botões de produto: azul + microinteração */
.produto button{transition:transform .18s ease,filter .18s ease,background-color .18s ease,box-shadow .18s ease!important}
.produto button:hover{background:#1677ff!important;color:#fff!important;filter:brightness(1.08)!important;transform:translateY(-2px)!important;box-shadow:0 7px 18px rgba(22,119,255,.24)!important}
.produto button:active{transform:translateY(0) scale(.98)!important}
/* revisão/carrinho */
#modalCarrinho .painel-carrinho,#modalFinalizar .painel-finalizar{border:1px solid #242424!important;background:#070707!important}
#subtotalCarrinhoModal,#taxaCarrinhoModal,#totalCarrinhoModal,#ndV4Sub,#ndV4Fee,#ndV4Total{font-variant-numeric:tabular-nums}
#taxaCarrinhoModal,#ndV4Fee{color:#66a9ff!important}
#totalCarrinhoModal,#ndV4Total{font-size:clamp(22px,3vw,30px)!important;font-weight:900!important;color:#fff!important;text-shadow:0 0 8px rgba(22,119,255,.65)!important}
/* checkout */
#modalFinalizar input,#modalFinalizar select,#modalFinalizar textarea{background:#0d0d0d!important;border-color:#292929!important;color:#fff!important}
#modalFinalizar input:focus,#modalFinalizar select:focus,#modalFinalizar textarea:focus{border-color:#1677ff!important;outline:none!important;box-shadow:0 0 0 2px rgba(22,119,255,.16)!important}
/* qualquer botão de finalização */
#modalCarrinho button,#modalFinalizar button{transition:transform .18s ease,filter .18s ease,background-color .18s ease,box-shadow .18s ease!important}
#modalCarrinho button:hover,#modalFinalizar button:hover{background:#1677ff!important;color:#fff!important;transform:translateY(-2px)!important;box-shadow:0 7px 18px rgba(22,119,255,.22)!important}
/* não aplicar o azul ao coração/favoritos */
button[aria-label*="favor" i],button[title*="favor" i],.favorito,.btn-favorito{transform:none!important;box-shadow:none!important}
@media(max-width:900px){
 body{padding-left:0!important}
 .nd18-cat-nav{position:sticky!important;left:auto!important;top:0!important;width:100%!important;max-height:none!important;border-radius:0 0 14px 14px!important;background:#050505!important}
 .nd18-cat-nav button{white-space:nowrap!important}
 .produto h3,.produto .nome,.produto .produto-nome{font-size:19px!important}
 .produto .preco,.produto .preco-produto,.produto [class*="preco"]{font-size:21px!important}
}
@media(prefers-reduced-motion:reduce){.produto button,#modalCarrinho button,#modalFinalizar button{transition:none!important}}
</style>

<script id="nd-etapa19-js">
(function(){
  'use strict';
  /* ETAPA 19 — reforça apenas a apresentação e mantém o carrinho/checkout originais */
  function nd19NormalizeMoney(v){
    if(v==null)return 0;
    if(typeof v==='number')return v;
    let x=String(v).replace(/[^0-9,.-]/g,'').replace(/\./g,'').replace(',','.');
    const n=parseFloat(x); return Number.isFinite(n)?n:0;
  }
  function nd19RefreshTotals(){
    /* Não substitui funções existentes. Apenas garante que, quando os campos já existirem,
       o total visual seja subtotal + taxa. */
    const subEl=document.getElementById('subtotalCarrinhoModal');
    const feeEl=document.getElementById('taxaCarrinhoModal');
    const totalEl=document.getElementById('totalCarrinhoModal');
    if(subEl&&feeEl&&totalEl){
      const sub=nd19NormalizeMoney(subEl.textContent);
      const fee=nd19NormalizeMoney(feeEl.textContent);
      if(subEl.textContent.trim() && feeEl.textContent.trim()) totalEl.textContent=(sub+fee).toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
    }
    const sub2=document.getElementById('ndV4Sub'),fee2=document.getElementById('ndV4Fee'),tot2=document.getElementById('ndV4Total');
    if(sub2&&fee2&&tot2){
      const sub=nd19NormalizeMoney(sub2.textContent),fee=nd19NormalizeMoney(fee2.textContent);
      if(sub2.textContent.trim()&&fee2.textContent.trim())tot2.textContent=(sub+fee).toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
    }
  }
  function nd19Bind(){
    /* Observa alterações já feitas pelo sistema original sem interceptar suas funções. */
    const root=document.body;
    if(root&&!root.__nd19Observer){
      root.__nd19Observer=new MutationObserver(function(){clearTimeout(root.__nd19Timer);root.__nd19Timer=setTimeout(nd19RefreshTotals,30)});
      root.__nd19Observer.observe(root,{subtree:true,childList:true,characterData:true});
    }
    nd19RefreshTotals();
  }
  if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',nd19Bind);else nd19Bind();
  setTimeout(nd19Bind,600);
})();
</script>





<!-- =========================================================
     ND BURGS — ETAPA 23 — RECONSTRUÇÃO FINAL DA EXPERIÊNCIA
     Corrige carrinho, checkout, endereço, categorias e visual.
     Camada isolada: não substitui a lógica de produtos.
     ========================================================= -->
<style id="nd-etapa-23-final">
/* ===== LOGO NO TOPO ===== */
header{display:flex!important;align-items:center!important;justify-content:center!important;min-height:82px!important;padding:8px 14px!important;background:#000!important;border-bottom:1px solid #171717!important;box-shadow:none!important}
header .logo{display:block!important;width:min(175px,46vw)!important;height:auto!important;max-height:68px!important;object-fit:contain!important;filter:none!important;border:0!important;box-shadow:none!important;background:transparent!important;border-radius:0!important}
.nd17-brand{display:none!important}
/* ===== PREÇOS: VERDE 3D, MENORES E SEM NEON ===== */
.produto .preco,.preco,.produto .preco-produto,.produto [class*="preco"]{
  display:inline-block!important;color:#39d353!important;font-size:clamp(16px,1.55vw,20px)!important;font-weight:900!important;line-height:1!important;
  padding:7px 11px!important;margin:7px auto!important;border-radius:9px!important;
  background:linear-gradient(180deg,#12351b 0%,#08170c 100%)!important;
  border:1px solid #2da34a!important;
  box-shadow:inset 0 1px 0 rgba(255,255,255,.16),inset 0 -3px 0 rgba(0,0,0,.45),0 3px 0 #0a2410,0 5px 10px rgba(0,0,0,.45)!important;
  text-shadow:none!important;letter-spacing:.2px!important;
}
#totalCarrinhoModal,#ndV4Total,#totalFinalizarModal,#total{color:#39d353!important;text-shadow:none!important}
/* ===== CATEGORIAS LATERAIS DO TOPO AO FIM ===== */
@media(min-width:901px){
 body{padding-left:225px!important}
 #nd18Sidebar{
   position:fixed!important;left:0!important;top:82px!important;bottom:0!important;width:205px!important;height:calc(100vh - 82px)!important;max-height:none!important;
   overflow-y:auto!important;overflow-x:hidden!important;transform:none!important;margin:0!important;padding:14px 10px 20px!important;
   background:#050505!important;border:0!important;border-right:1px solid #202020!important;border-radius:0!important;box-shadow:8px 0 24px rgba(0,0,0,.35)!important;z-index:9500!important;box-sizing:border-box!important;
 }
 #nd18Sidebar .nd18-title{position:sticky!important;top:0!important;background:#050505!important;padding:7px 8px 12px!important;z-index:2!important}
 #nd18Sidebar button{width:100%!important;margin:4px 0!important}
}
@media(max-width:900px){
 body{padding-left:0!important}
 #nd18Sidebar{position:sticky!important;top:0!important;width:100%!important;max-height:none!important;height:auto!important;transform:none!important;margin:0!important;border-radius:0!important;z-index:9500!important}
}
/* ===== CARRINHO: SOMENTE ÍCONE FIXO + CONTADOR ===== */
#carrinhoFlutuante{
  left:auto!important;right:18px!important;bottom:18px!important;transform:none!important;width:62px!important;height:62px!important;max-width:none!important;
  padding:0!important;border:1px solid #2d8cff!important;border-radius:50%!important;background:#08111f!important;box-shadow:0 8px 25px rgba(0,0,0,.65),inset 0 1px 0 rgba(255,255,255,.12)!important;
  display:flex!important;align-items:center!important;justify-content:center!important;opacity:0!important;pointer-events:none!important;z-index:10000!important;
}
#carrinhoFlutuante.ativo{opacity:1!important;pointer-events:auto!important;transform:none!important}
#carrinhoFlutuante .carrinho-flutuante-info{display:block!important;min-width:0!important}
#carrinhoFlutuante .carrinho-flutuante-info strong{font-size:0!important;display:block!important;line-height:1!important}
#carrinhoFlutuante .carrinho-flutuante-info strong:after{content:'🛒';font-size:27px!important;display:block;line-height:1}
#carrinhoFlutuante .carrinho-flutuante-info span{position:absolute!important;top:-5px!important;right:-5px!important;min-width:21px!important;height:21px!important;padding:0 5px!important;display:flex!important;align-items:center!important;justify-content:center!important;background:#e50914!important;color:#fff!important;border:2px solid #000!important;border-radius:99px!important;font-size:10px!important;font-weight:900!important;box-sizing:border-box!important}
#carrinhoFlutuante .carrinho-flutuante-direita{display:none!important}
/* ===== MODAL DO CARRINHO ===== */
#modalCarrinho{z-index:100001!important}
#modalCarrinho .painel-carrinho{max-height:92vh!important;background:#0b0b0b!important;border:1px solid #303030!important;border-radius:22px 22px 0 0!important}
#itensCarrinhoModal{display:flex!important;flex-direction:column!important;gap:8px!important}
.nd23-cart-item{display:grid;grid-template-columns:72px 1fr auto;gap:11px;align-items:center;padding:10px;border:1px solid #242424;border-radius:14px;background:#111}
.nd23-cart-item img{width:72px;height:72px;object-fit:cover;border-radius:10px;background:#050505;display:block}
.nd23-cart-item .nd23-cart-info{min-width:0}
.nd23-cart-item .nd23-cart-name{display:block;color:#fff;font-size:14px;font-weight:800;line-height:1.2}
.nd23-cart-item .nd23-cart-unit{display:block;color:#aaa;font-size:11px;margin-top:5px}
.nd23-cart-item .nd23-cart-detail{display:block;color:#aaa;font-size:10px;line-height:1.4;margin-top:4px}
.nd23-cart-item .nd23-cart-total{color:#39d353;font-size:13px;font-weight:900;white-space:nowrap;align-self:start;margin-top:3px}
@media(max-width:520px){.nd23-cart-item{grid-template-columns:58px 1fr auto}.nd23-cart-item img{width:58px;height:58px}.nd23-cart-item .nd23-cart-name{font-size:12px}.nd23-cart-item .nd23-cart-total{font-size:12px}}
/* ===== AUTOCOMPLETE DE ENDEREÇO: SEMPRE VISÍVEL E ACIMA DOS OUTROS ELEMENTOS ===== */
.nd17-list,.nd17-inline-list{position:absolute!important;left:0!important;right:0!important;top:calc(100% + 5px)!important;max-height:310px!important;overflow-y:auto!important;background:#101010!important;border:1px solid #333!important;border-radius:12px!important;box-shadow:0 18px 40px rgba(0,0,0,.8)!important;z-index:100020!important;padding:5px!important;box-sizing:border-box!important}
.nd17-option{display:flex!important;justify-content:space-between!important;gap:10px!important;padding:11px 10px!important;color:#fff!important;border-radius:8px!important;cursor:pointer!important;font-size:12px!important}
.nd17-option:hover{background:#1b5fae!important}
.nd17-suggest,.nd17-inline-suggest,.address-search-wrap{position:relative!important;z-index:100010!important}
#nd17Gate{z-index:200000!important}
#nd17Gate .nd17-gate-panel{background:#080808!important;border:1px solid #292929!important}
#nd17Gate .nd17-gate-panel h2{font-size:26px!important}
#nd17Gate .nd17-kicker{color:#e50914!important}
/* ===== FINALIZAÇÃO: SUBTOTAL OCULTO APENAS NA ETAPA FINAL ===== */
#modalFinalizar .nd-v4-step-content[data-content="4"] .nd-v4-summary:nth-of-type(2)>div:first-child{display:none!important}
/* ===== BOTÕES ===== */
.btn.btn-add,.btn-finalizar-pedido,.nd-v4-next,.nd17-gate-main{border-radius:12px!important}
/* reduz qualquer neon herdado */
.produto .preco,.preco,.produto .preco-produto,.produto [class*="preco"]{filter:none!important}
@media(max-width:600px){
 header{min-height:70px!important}
 header .logo{width:min(150px,48vw)!important;max-height:58px!important}
 #carrinhoFlutuante{right:13px!important;bottom:13px!important;width:58px!important;height:58px!important}
 #carrinhoFlutuante .carrinho-flutuante-info strong:after{font-size:25px!important}
 .produto .preco,.preco,.produto .preco-produto,.produto [class*="preco"]{font-size:15px!important;padding:6px 9px!important}
}
</style>

<script id="nd-etapa-23-final-js">
(function(){
'use strict';
const $=s=>document.querySelector(s), $$=s=>Array.from(document.querySelectorAll(s));
const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');
const norm=v=>String(v||'').toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,' ').trim();
function cart(){return Array.isArray(window.carrinho)?window.carrinho:[]}
function getTaxes(){try{return typeof taxas!=='undefined'?taxas:(window.taxas||{})}catch(e){return window.taxas||{}}}
function subtotal(){return cart().reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||1),0)}
function addr(){return {type:localStorage.getItem('nd17_tipo')||'ENTREGA',street:localStorage.getItem('nd17_rua')||'',number:localStorage.getItem('nd17_numero')||''}}
function fee(){const a=addr();return a.type==='ENTREGA'&&a.street?Number(getTaxes()[a.street]||0):0}
function imageFor(item){
 const n=norm(item&&item.nome);
 const cards=$$('.produto');
 let best=null,bestScore=-1;
 cards.forEach(card=>{
   const h=norm(card.querySelector('h3')?.textContent);
   const im=card.querySelector('img.produto-imagem, img');
   if(!im||!im.src||!h)return;
   let score=-1;
   if(h===n)score=100;
   else if(n.startsWith(h))score=90+h.length;
   else if(h.startsWith(n))score=80+n.length;
   else if(n.includes(h))score=60+h.length;
   if(score>bestScore){bestScore=score;best=im.src}
 });
 return best||'';
}
function decorateModalCart(){
 const area=$('#itensCarrinhoModal'); if(!area)return;
 const rows=Array.from(area.querySelectorAll('.item-carrinho-modal'));
 rows.forEach((row,index)=>{
   const item=cart()[index]; if(!item||row.dataset.nd23==='1')return;
   row.dataset.nd23='1';
   const img=imageFor(item);
   if(img){const oldTop=row.querySelector('.item-carrinho-modal-topo'); if(oldTop){oldTop.style.gridColumn='2'; const wrap=document.createElement('div');wrap.className='nd23-cart-image';wrap.style.gridColumn='1';wrap.style.gridRow='1 / span 2';const im=document.createElement('img');im.src=img;im.alt=item.nome;im.loading='lazy';im.style.cssText='width:72px;height:72px;object-fit:cover;border-radius:10px;background:#050505;display:block';wrap.appendChild(im);row.style.display='grid';row.style.gridTemplateColumns='72px 1fr';row.style.gap='10px';row.insertBefore(wrap,row.firstChild)}}
   const price=money((Number(item.preco)||0)*(Number(item.quantidade)||1));
   let totalEl=row.querySelector('.nd23-injected-total');
   if(!totalEl){totalEl=document.createElement('div');totalEl.className='nd23-injected-total';totalEl.style.cssText='color:#39d353;font-size:13px;font-weight:900;margin-top:7px';totalEl.textContent='Total do item: '+price;const top=row.querySelector('.item-carrinho-modal-topo');if(top)top.appendChild(totalEl)}
 });
}
function forceCart(){
 const bar=$('#carrinhoFlutuante');if(!bar)return;
 const count=cart().reduce((s,i)=>s+(Number(i.quantidade)||1),0);
 bar.classList.toggle('ativo',count>0);
 const c=$('#contadorCarrinho');if(c)c.textContent=String(count);
 const t=$('#totalCarrinhoFlutuante');if(t)t.textContent=money(subtotal()+fee());
}
function patchFunction(name,after){
 const old=window[name]; if(typeof old!=='function'||old.__nd23)return;
 const wrapped=function(){const r=old.apply(this,arguments);try{after()}catch(e){}return r};
 wrapped.__nd23=true;wrapped.__nd23Original=old;window[name]=wrapped;
}
function patchCart(){
 patchFunction('atualizarCarrinho',()=>{forceCart();setTimeout(decorateModalCart,0);setTimeout(syncTotals,10)});
 patchFunction('atualizarModalCarrinho',()=>{setTimeout(decorateModalCart,0);syncTotals()});
 patchFunction('abrirCarrinho',()=>{setTimeout(()=>{forceCart();syncTotals();decorateModalCart()},20)});
 patchFunction('irParaFinalizarPedido',()=>{setTimeout(()=>{syncTotals();setupAddressInputs();decorateCheckout()},20)});
 patchFunction('buildCheckout',()=>{setTimeout(()=>{syncTotals();setupAddressInputs();decorateCheckout()},20)});
 patchFunction('ndSummary',()=>{setTimeout(decorateCheckout,0)});
}
function syncTotals(){
 const sub=subtotal(),f=fee(),total=sub+f;
 [['subtotalCarrinhoModal',sub],['taxaCarrinhoModal',f],['totalCarrinhoModal',total],['ndV4Sub',sub],['ndV4Fee',f],['ndV4Total',total],['subtotal',sub],['taxa',f],['total',total]].forEach(([id,v])=>{const e=document.getElementById(id);if(e)e.textContent=money(v)});
 forceCart();
}
function setupAddressInputs(){
 const saved=addr();
 const type=$('#tipoPedidoModal');if(type)type.value=saved.type==='RETIRADA'?'RETIRADA':'ENTREGA';
 const rua=$('#ruaModal');if(rua&&saved.street)rua.value=saved.street;
 const num=$('#numeroModal');if(num&&saved.number)num.value=saved.number;
 const type2=$('#tipoPedido');if(type2)type2.value=saved.type==='RETIRADA'?'RETIRADA':'ENTREGA';
 const rua2=$('#rua');if(rua2&&saved.street)rua2.value=saved.street;
 const num2=$('#numero');if(num2&&saved.number)num2.value=saved.number;
}
function renderSuggestions(input,list){
 if(!input||!list)return;
 const q=norm(input.value);
 const entries=Object.keys(getTaxes()).filter(k=>!['BALCAO','RETIRADA','IFOOD','99FOOD'].includes(k));
 const found=entries.filter(k=>!q||norm(k).includes(q)).slice(0,20);
 list.innerHTML='';
 found.forEach(street=>{const d=document.createElement('div');d.className='nd17-option';d.innerHTML='<span>'+street+'</span><strong>'+money(getTaxes()[street])+'</strong>';d.addEventListener('mousedown',e=>{e.preventDefault();input.value=street;input.dataset.value=street;list.classList.remove('show');input.dispatchEvent(new Event('change',{bubbles:true}));syncTotals()});list.appendChild(d)});
 list.classList.toggle('show',found.length>0 && (q.length>0 || document.activeElement===input));
}
function bindAddr(input,list){if(!input||!list||input.dataset.nd23addr)return;input.dataset.nd23addr='1';input.addEventListener('input',()=>renderSuggestions(input,list));input.addEventListener('focus',()=>renderSuggestions(input,list));input.addEventListener('keydown',e=>{if(e.key==='Escape')list.classList.remove('show')});}
function ensureList(input){if(!input)return null;let list=input.parentElement.querySelector('.nd17-inline-list');if(!list){const wrap=input.parentElement;wrap.style.position='relative';list=document.createElement('div');list.className='nd17-inline-list';wrap.appendChild(list)}return list}
function setupAddressInputs(){
 const saved=addr();
 ['#tipoPedidoModal','#tipoPedido'].forEach(sel=>{const e=$(sel);if(e)e.value=saved.type==='RETIRADA'?'RETIRADA':'ENTREGA'});
 ['#ruaModal','#rua'].forEach(sel=>{const e=$(sel);if(e&&saved.street)e.value=saved.street});
 ['#numeroModal','#numero'].forEach(sel=>{const e=$(sel);if(e&&saved.number)e.value=saved.number});
 bindAddr($('#nd17GateStreet'),$('#nd17GateList'));bindAddr($('#ruaBuscaModal'),ensureList($('#ruaBuscaModal')));bindAddr($('#ruaBusca'),ensureList($('#ruaBusca')));
}
function decorateCheckout(){
 const items=$('#ndV4Items');if(!items)return;
 // O resumo já tem os valores; esta camada só garante o preço individual/total de cada item.
 cart().forEach((it,i)=>{
   const rows=Array.from(items.children);const row=rows[i];if(!row)return;
   if(!row.querySelector('.nd23-check-price')){const s=document.createElement('div');s.className='nd23-check-price';s.style.cssText='color:#39d353;font-weight:800;font-size:12px;margin-top:3px';s.textContent=money((Number(it.preco)||0)*(Number(it.quantidade)||1));row.appendChild(s)}
 });
}
function welcomeGate(){
 const g=$('#nd17Gate');if(!g)return;
 const h=g.querySelector('h2'),p=g.querySelector('p');
 if(h)h.textContent='BEM-VINDO À ND BURGS';
 if(p)p.textContent='Antes de começar, informe onde deseja receber seu pedido. Assim já calculamos sua taxa de entrega. Se preferir, escolha retirada no local.';
}
function refresh(){patchCart();setupAddressInputs();syncTotals();decorateCheckout();decorateModalCart();welcomeGate();forceCart();}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',()=>{refresh();setTimeout(refresh,250);setTimeout(refresh,1000)});else{refresh();setTimeout(refresh,250);setTimeout(refresh,1000)}
// Atualização leve quando o carrinho/checkout muda, sem setInterval agressivo.
let timer=0;const obs=new MutationObserver(()=>{clearTimeout(timer);timer=setTimeout(()=>{forceCart();syncTotals();decorateModalCart()},80)});obs.observe(document.body,{subtree:true,childList:true,characterData:true});
})();
</script>


<script>
/* ND BURGS R10 - experiência do carrinho e melhorias de navegação */
document.addEventListener('DOMContentLoaded',function(){
  const barra=document.getElementById('carrinhoFlutuante');
  if(barra){
    barra.addEventListener('click',function(e){
      if(e.target.closest('button')) return;
      abrirCarrinho();
    });
  }
  const busca=document.getElementById('busca');
  if(busca){busca.setAttribute('aria-label','Buscar produtos');}
});
const abrirCarrinhoOriginal=abrirCarrinho;
abrirCarrinho=function(){
  atualizarModalCarrinho();
  const modal=document.getElementById('modalCarrinho');
  if(modal){modal.classList.add('ativo');document.body.style.overflow='hidden';}
};
</script>


<!-- =========================================================
     ND BURGS 2.0 — AVALIAÇÕES + CARRINHO ÚNICO + MAIS VENDIDOS
     Camada final: mantém a lógica existente e adiciona somente UI/UX.
     ========================================================= -->
<style id="nd20-pirotecnico">
/* ===== CARRINHO ÚNICO ===== */
#ndCartFab,#ndCartLabel{display:none!important}
#carrinhoFlutuante{
  display:flex!important;opacity:0;pointer-events:none;position:fixed!important;
  right:18px!important;bottom:18px!important;left:auto!important;transform:none!important;
  width:66px!important;height:66px!important;padding:0!important;border-radius:50%!important;
  align-items:center!important;justify-content:center!important;z-index:200000!important;
  background:radial-gradient(circle at 35% 25%,#ff5a2b 0,#e50914 48%,#8b0010 100%)!important;
  border:2px solid rgba(255,255,255,.85)!important;
  box-shadow:0 0 0 4px rgba(229,9,20,.13),0 0 25px rgba(229,9,20,.55),0 12px 35px rgba(0,0,0,.8)!important;
  transition:transform .2s ease,opacity .2s ease,box-shadow .2s ease!important;
  animation:nd20CartPulse 2.2s infinite;
}
#carrinhoFlutuante.ativo{opacity:1!important;pointer-events:auto!important}
#carrinhoFlutuante:hover{transform:scale(1.08)!important;box-shadow:0 0 0 5px rgba(229,9,20,.18),0 0 35px rgba(255,70,25,.85),0 14px 38px rgba(0,0,0,.85)!important}
#carrinhoFlutuante .carrinho-flutuante-info{display:block!important;min-width:0!important}
#carrinhoFlutuante .carrinho-flutuante-info strong{font-size:0!important;display:block!important}
#carrinhoFlutuante .carrinho-flutuante-info strong:after{content:'🛒';font-size:29px!important;line-height:1}
#carrinhoFlutuante .carrinho-flutuante-info span{position:absolute!important;right:-4px!important;top:-4px!important;min-width:23px!important;height:23px!important;padding:0 5px!important;display:flex!important;align-items:center!important;justify-content:center!important;background:#fff!important;color:#e50914!important;border:2px solid #000!important;border-radius:99px!important;font-size:10px!important;font-weight:1000!important}
#carrinhoFlutuante .carrinho-flutuante-direita{display:none!important}
@keyframes nd20CartPulse{0%,100%{box-shadow:0 0 0 4px rgba(229,9,20,.13),0 0 22px rgba(229,9,20,.45),0 12px 35px rgba(0,0,0,.8)}50%{box-shadow:0 0 0 7px rgba(229,9,20,.08),0 0 34px rgba(255,70,25,.7),0 12px 38px rgba(0,0,0,.8)}}

/* ===== PEDAÇO DA CATEGORIA + FINALIZAR PEDIDO ===== */
#nd20QuickNav{width:min(1180px,calc(100% - 20px));margin:12px auto 20px;position:sticky;top:8px;z-index:9490;display:flex;align-items:center;gap:8px;padding:8px;background:rgba(5,5,5,.96);border:1px solid #242424;border-radius:15px;box-shadow:0 12px 32px rgba(0,0,0,.6);backdrop-filter:blur(12px)}
#nd20QuickCats{display:flex;gap:7px;overflow:auto;scrollbar-width:none;min-width:0;flex:1}#nd20QuickCats::-webkit-scrollbar{display:none}
.nd20-qcat{flex:0 0 auto;border:1px solid #2a2a2a;background:#111;color:#aaa;border-radius:10px;padding:9px 12px;font-size:11px;font-weight:900;cursor:pointer;white-space:nowrap;transition:.18s}
.nd20-qcat:hover{color:#fff;border-color:#e50914;background:#190707;transform:translateY(-1px)}
#nd20Finish{flex:0 0 auto;border:1px solid #ffd21a;border-radius:11px;background:linear-gradient(135deg,#ffd21a,#ff8a00);color:#050505;padding:11px 14px;font-size:11px;font-weight:1000;cursor:pointer;white-space:nowrap;box-shadow:0 0 18px rgba(255,173,0,.3);animation:nd20FinishGlow 1.8s infinite}
#nd20Finish:hover{transform:translateY(-2px) scale(1.02);box-shadow:0 0 30px rgba(255,173,0,.65)}
@keyframes nd20FinishGlow{50%{box-shadow:0 0 28px rgba(255,173,0,.58)}}

/* ===== MAIS VENDIDOS DO DIA ===== */
#nd20Best{width:min(1180px,calc(100% - 20px));margin:14px auto 24px;padding:17px;border:1px solid rgba(255,90,20,.42);border-radius:20px;background:linear-gradient(135deg,#090909,#130805 60%,#090909);box-shadow:0 15px 50px rgba(0,0,0,.55),0 0 30px rgba(255,70,15,.08);scroll-margin-top:90px;position:relative;overflow:hidden}
#nd20Best:before{content:'';position:absolute;inset:-80px;background:conic-gradient(from 0deg,transparent,#e50914,transparent,#ffd21a,transparent);opacity:.07;animation:nd20Spin 8s linear infinite}
@keyframes nd20Spin{to{transform:rotate(360deg)}}
.nd20-best-head{position:relative;z-index:1;display:flex;justify-content:space-between;align-items:end;gap:10px;margin-bottom:12px}.nd20-best-kicker{font-size:9px;letter-spacing:2px;color:#ff6a30;font-weight:1000}.nd20-best-head h2{margin:2px 0 0!important;padding:0!important;border:0!important;font-size:23px!important;color:#fff!important}.nd20-best-head p{margin:0;color:#888;font-size:10px;text-align:right}.nd20-best-grid{position:relative;z-index:1;display:grid;grid-template-columns:repeat(3,1fr);gap:10px}.nd20-best-card{display:grid;grid-template-columns:78px 1fr auto;gap:10px;align-items:center;padding:9px;border:1px solid #2c1b18;border-radius:15px;background:#0d0d0d;transition:.2s;overflow:hidden}.nd20-best-card:hover{transform:translateY(-3px);border-color:#e50914;box-shadow:0 10px 30px rgba(229,9,20,.16)}.nd20-best-card img{width:78px;height:78px;object-fit:cover;border-radius:11px;background:#050505}.nd20-best-info{min-width:0}.nd20-best-info strong{display:block;color:#fff;font-size:12px;line-height:1.15}.nd20-best-info span{display:block;color:#ffd21a;font-size:13px;font-weight:1000;margin-top:4px}.nd20-best-add{border:0;border-radius:10px;background:linear-gradient(135deg,#e50914,#ff5a20);color:#fff;padding:10px 9px;font-size:10px;font-weight:1000;cursor:pointer;box-shadow:0 5px 15px rgba(229,9,20,.25)}.nd20-best-add:hover{transform:scale(1.04);filter:brightness(1.12)}

/* ===== AVALIAÇÃO PEQUENA EM TODOS OS PRODUTOS ===== */
.nd20-rating{display:flex;align-items:center;gap:2px;margin:7px 0 5px;min-height:18px}.nd20-star{appearance:none;border:0!important;background:transparent!important;color:#555!important;padding:0!important;margin:0!important;width:17px!important;height:18px!important;min-height:18px!important;font-size:16px!important;line-height:18px!important;cursor:pointer!important;box-shadow:none!important;text-shadow:none!important;transition:transform .12s,color .12s,text-shadow .12s!important}.nd20-star:hover{transform:scale(1.18)!important;color:#ffd21a!important}.nd20-star.on{color:#ffd21a!important;text-shadow:0 0 7px rgba(255,210,26,.55)!important}.nd20-rating-label{font-size:9px;color:#777;margin-left:4px;font-weight:800;white-space:nowrap}.nd20-rated .nd20-rating-label{color:#aaa}
.nd20-rated-burst{animation:nd20Rated .55s ease}.nd20-best-card.nd20-pop{animation:nd20Pop .55s ease}.produto.nd20-pop{animation:nd20Pop .55s ease}@keyframes nd20Rated{0%{transform:scale(1)}40%{transform:scale(1.035)}100%{transform:scale(1)}}@keyframes nd20Pop{0%{transform:scale(1)}35%{transform:scale(1.035) rotate(-.3deg)}70%{transform:scale(.99)}100%{transform:scale(1)}}
.nd20-confetti{position:fixed;z-index:300000;width:7px;height:13px;pointer-events:none;animation:nd20Confetti .8s cubic-bezier(.2,.8,.2,1) forwards;border-radius:2px}@keyframes nd20Confetti{0%{opacity:1;transform:translate(0,0) rotate(0)}100%{opacity:0;transform:translate(var(--x),var(--y)) rotate(620deg)}}

@media(max-width:900px){#nd20QuickNav{top:0;width:100%;margin:6px 0 15px;border-radius:0;padding:7px}.nd20-qcat{padding:9px 11px;font-size:10px}#nd20Finish{padding:10px 11px;font-size:10px}.nd20-best-grid{display:flex;overflow-x:auto;scroll-snap-type:x mandatory;padding-bottom:3px}.nd20-best-card{min-width:285px;scroll-snap-align:start}}
@media(max-width:600px){#carrinhoFlutuante{right:12px!important;bottom:12px!important;width:60px!important;height:60px!important}.nd20-best{width:calc(100% - 14px);padding:13px;border-radius:17px}.nd20-best-head{align-items:flex-start;flex-direction:column}.nd20-best-head p{text-align:left}.nd20-best-card{min-width:275px}.nd20-star{width:16px!important;font-size:15px!important}.nd20-rating{margin:6px 0 4px}}
@media(prefers-reduced-motion:reduce){#carrinhoFlutuante,#nd20Finish,#nd20Best:before,.nd20-star{animation:none!important;transition:none!important}.nd20-confetti{display:none!important}}
</style>
<script id="nd20-pirotecnico-js">
(function(){
'use strict';
const $=s=>document.querySelector(s), $$=s=>Array.from(document.querySelectorAll(s));
const norm=v=>String(v||'').normalize('NFD').replace(/[\u0300-\u036f]/g,'').toUpperCase().replace(/\s+/g,' ').trim();
const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');
const cart=()=>Array.isArray(window.carrinho)?window.carrinho:[];
const today=()=>{const d=new Date();return d.getFullYear()+'-'+String(d.getMonth()+1).padStart(2,'0')+'-'+String(d.getDate()).padStart(2,'0')};
function getProductData(card){
 const h=card?.querySelector('h3'), img=card?.querySelector('img.produto-imagem, img'), price=card?.querySelector('.preco'), btn=card?.querySelector('.btn-add');
 if(!card||!h)return null;
 const name=h.textContent.trim(); const pt=price?.textContent||''; const m=pt.match(/R\$\s*([\d\.]+,[\d]{2})/); const value=m?parseFloat(m[1].replace(/\./g,'').replace(',','.')):0; const onclick=btn?.getAttribute('onclick')||'';
 let addName=name, addValue=value; const am=onclick.match(/adicionar\((['"])(.*?)\1\s*,\s*([0-9.]+)/); if(am){addName=am[2];addValue=Number(am[3]);}
 return {name,img:img?.src||'',price:value,priceText:price?.textContent.trim()||money(value),addName,addValue,onclick};
}
function confetti(el){
 if(window.matchMedia&&window.matchMedia('(prefers-reduced-motion: reduce)').matches)return;
 const r=el?.getBoundingClientRect?.()||{left:innerWidth/2,top:innerHeight/2,width:0,height:0}; const cx=r.left+r.width/2,cy=r.top+r.height/2;
 for(let i=0;i<18;i++){const p=document.createElement('i');p.className='nd20-confetti';p.style.left=cx+'px';p.style.top=cy+'px';p.style.setProperty('--x',(Math.random()*180-90)+'px');p.style.setProperty('--y',(Math.random()*-170-35)+'px');p.style.background=['#e50914','#ffd21a','#fff','#ff6a00','#1677ff'][i%5];p.style.animationDelay=(Math.random()*.08)+'s';document.body.appendChild(p);setTimeout(()=>p.remove(),1000)}
}
function buildRatings(){
 $$('.produto').forEach(card=>{
  if(card.querySelector('.nd20-rating'))return;
  const h=card.querySelector('h3'); if(!h)return; const name=h.textContent.trim(); const key='ndburgs_rating_'+norm(name);
  let saved=0; try{saved=Number(localStorage.getItem(key)||0)}catch(e){}
  const row=document.createElement('div');row.className='nd20-rating'+(saved?' nd20-rated':'');row.setAttribute('aria-label','Avaliar '+name);
  for(let i=1;i<=5;i++){const b=document.createElement('button');b.type='button';b.className='nd20-star'+(i<=saved?' on':'');b.textContent='★';b.dataset.value=i;b.title='Dar '+i+' estrela'+(i>1?'s':'');b.setAttribute('aria-label',i+' estrela'+(i>1?'s':''));b.addEventListener('click',e=>{e.stopPropagation();const n=Number(b.dataset.value);try{localStorage.setItem(key,String(n))}catch(_){} row.classList.add('nd20-rated-burst','nd20-rated');row.querySelectorAll('.nd20-star').forEach((x,j)=>x.classList.toggle('on',j<n));const label=row.querySelector('.nd20-rating-label');if(label)label.textContent=n+'/5';confetti(row);setTimeout(()=>row.classList.remove('nd20-rated-burst'),600)});row.appendChild(b)}
  const label=document.createElement('span');label.className='nd20-rating-label';label.textContent=saved?saved+'/5':'AVALIE';row.appendChild(label);
  const anchor=card.querySelector('.preco')||card.querySelector('.btn-add'); if(anchor)anchor.parentNode.insertBefore(row,anchor);
 });
}
function seededOrder(items){
 const seed=[...today()].reduce((a,c)=>((a*31+c.charCodeAt(0))>>>0),17);let x=seed||17;const arr=items.slice();for(let i=arr.length-1;i>0;i--){x=(x*1664525+1013904223)>>>0;const j=x%(i+1);[arr[i],arr[j]]=[arr[j],arr[i]]}return arr;
}
function buildBest(){
 let sec=$('#nd20Best'); if(sec)return sec;
 const anchor=$('.categoria-menu')||$('.container'); if(!anchor)return null;
 sec=document.createElement('section');sec.id='nd20Best';sec.innerHTML='<div class="nd20-best-head"><div><div class="nd20-best-kicker">🔥 ATUALIZADO AUTOMATICAMENTE</div><h2>MAIS VENDIDOS DO DIA</h2></div><p>O Ranking é atualizado conforme as vendas do dia.</p></div><div class="nd20-best-grid" id="nd20BestGrid"></div>';
 anchor.parentNode.insertBefore(sec,anchor.nextSibling);return sec;
}
function renderBest(){
 const sec=buildBest();if(!sec)return;const grid=$('#nd20BestGrid');if(!grid)return;grid.innerHTML='';
 const all=$$('.produto').map(getProductData).filter(x=>x&&x.name&&x.price>0);const picks=seededOrder(all).slice(0,3);
 picks.forEach((d,i)=>{const card=document.createElement('article');card.className='nd20-best-card';card.innerHTML='<img loading="lazy" decoding="async" src="'+d.img+'" alt="'+d.name.replace(/"/g,'&quot;')+'"><div class="nd20-best-info"><strong>'+d.name.replace(/</g,'&lt;')+'</strong><span>'+d.priceText+'</span><div style="font-size:9px;color:#ffd21a;margin-top:3px">★★★★★ <em style="color:#777;font-style:normal">MAIS PEDIDO</em></div></div><button type="button" class="nd20-best-add">ADICIONAR</button>';card.querySelector('button').addEventListener('click',()=>{if(/abrirPersonalizacao\s*\(/.test(d.onclick)&&typeof window.abrirPersonalizacao==='function'){window.abrirPersonalizacao((d.onclick.match(/abrirPersonalizacao\(['"]([^'"]+)/)||[])[1]||d.addName)}else if(typeof window.adicionar==='function'){window.adicionar(d.addName,d.addValue)}card.classList.remove('nd20-pop');void card.offsetWidth;card.classList.add('nd20-pop');confetti(card)});grid.appendChild(card)});
}
function buildQuickNav(){
 if($('#nd20QuickNav'))return;const menu=$('.categoria-menu');if(!menu)return;const wrap=document.createElement('div');wrap.id='nd20QuickNav';wrap.innerHTML='<div id="nd20QuickCats"></div><button id="nd20Finish" type="button">FINALIZAR PEDIDO →</button>';menu.parentNode.insertBefore(wrap,menu);
 const cats=$$('.categoria');const names=['COMBOS','TRADICIONAIS','ARTESANAIS','COMBOS ARTESANAIS','PORÇÕES','PASTÉIS','AÇAÍS - MILKSHAKES E SOBREMESAS','BEBIDAS','ADICIONAIS'];const icons=['❤️','🍔','🔥','🔥','🍟','🥟','🍨','🥤','➕'];const box=$('#nd20QuickCats');cats.forEach((cat,i)=>{const b=document.createElement('button');b.type='button';b.className='nd20-qcat';b.textContent=(icons[i]||'•')+' '+(names[i]||('CATEGORIA '+(i+1)));b.onclick=()=>cat.scrollIntoView({behavior:'smooth',block:'start'});box.appendChild(b)});
 $('#nd20Finish').onclick=()=>{if(typeof window.abrirCarrinho==='function'){window.abrirCarrinho()}else{$('#modalCarrinho')?.classList.add('ativo')}};
}
function patchIntroButton(){
 const btn=$$('.ndFx-action').find(x=>norm(x.textContent).includes('VER MAIS VENDIDOS'));if(!btn)return;if(btn.dataset.ndR14==='1')return;btn.dataset.ndR14='1';btn.onclick=()=>{const sec=document.getElementById('ndAutoBest');if(sec){renderBest();sec.scrollIntoView({behavior:'smooth',block:'start'});if(typeof confetti==='function')confetti(btn)}};
}
function forceSingleCart(){
 const old=$('#ndCartFab');if(old)old.remove();const label=$('#ndCartLabel');if(label)label.remove();
 const bar=$('#carrinhoFlutuante');if(!bar)return;bar.style.display='flex';const n=cart().reduce((s,i)=>s+(Number(i.quantidade)||0),0);bar.classList.toggle('ativo',n>0);
 const c=$('#contadorCarrinho');if(c)c.textContent=n+(n===1?' item':' itens');
 const total=cart().reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||1),0);const t=$('#totalCarrinhoFlutuante');if(t)t.textContent=money(total);
}
function patchAdd(){
 if(typeof window.adicionar!=='function'||window.adicionar.__nd20)return;const old=window.adicionar;window.adicionar=function(){const r=old.apply(this,arguments);setTimeout(()=>{forceSingleCart();buildRatings()},20);return r};window.adicionar.__nd20=true;
}
function init(){buildQuickNav();buildBest();buildRatings();renderBest();patchIntroButton();patchAdd();forceSingleCart();}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',()=>{init();setTimeout(init,500);setTimeout(init,1200)});else{init();setTimeout(init,500);setTimeout(init,1200)}
setInterval(()=>{forceSingleCart();buildRatings();patchAdd()},1200);
})();
</script>

<!-- =========================================================
     ND BURGS R11 — COMBOS 100% CONFIGURÁVEIS + NOVA NAVEGAÇÃO
     ========================================================= -->
<style id="nd-r11-combos-ui">
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
</style>

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
 const item={nome:current.name,preco:current.price+extra,quantidade:1,detalhes:details};if(Array.isArray(window.carrinho))window.carrinho.push(item);if(typeof window.atualizarCarrinho==='function')window.atualizarCarrinho();close();
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
function buildBest(){if(document.getElementById('ndAutoBest'))return;const h=document.querySelector('header');if(!h)return;const s=document.createElement('section');s.id='ndAutoBest';s.innerHTML='<div class="r11-best-head"><div><small>🔥 TOP 3 DO DIA</small><h2>TOP 3 • MAIS VENDIDOS</h2></div><p>Destaques automáticos de hoje.</p></div><div class="r11-best-grid"></div>';h.insertAdjacentElement('afterend',s)}
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
 const head=s.querySelector('.r11-best-head p');if(head)head.textContent='3 destaques atualizados automaticamente todos os dias.';
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
<style id="nd-r12-cart-cleanup">
/* Remove definitivamente qualquer carrinho/atalho antigo */
#ndCartFab,#ndCartLabel,#ndFxCartbar,.nd-v3-buybar,.nd-cart-fab,.nd-cart-label{display:none!important}

/* ÚNICO botão de carrinho visível */
#carrinhoFlutuante{
  position:fixed!important;
  right:18px!important;top:18px!important;left:auto!important;bottom:auto!important;
  width:auto!important;height:auto!important;min-width:0!important;max-width:none!important;
  padding:0!important;margin:0!important;transform:none!important;
  display:flex!important;align-items:center!important;justify-content:center!important;
  background:transparent!important;border:0!important;border-radius:0!important;box-shadow:none!important;
  z-index:250000!important;
}
#carrinhoFlutuante.ativo{opacity:1!important;pointer-events:auto!important}
#carrinhoFlutuante .carrinho-flutuante-info{position:relative!important;display:flex!important;align-items:center!important}
#carrinhoFlutuante .carrinho-flutuante-info strong{
  display:flex!important;align-items:center!important;justify-content:center!important;
  min-height:44px!important;padding:10px 15px!important;
  font-size:0!important;line-height:1!important;white-space:nowrap!important;cursor:pointer!important;
  background:linear-gradient(180deg,#fff36b 0%,#ffd21a 52%,#f0a000 100%)!important;
  color:#171000!important;border:1px solid #ffe66f!important;border-radius:12px!important;
  box-shadow:inset 0 2px 0 rgba(255,255,255,.72),inset 0 -3px 0 rgba(153,92,0,.42),0 3px 0 #8d5700,0 8px 20px rgba(0,0,0,.48)!important;
}
#carrinhoFlutuante .carrinho-flutuante-info strong:after{
  content:'VER CARRINHO'!important;font-size:12px!important;font-weight:1000!important;letter-spacing:.35px!important;
}
/* contador da quantidade — sem ícone de carrinho */
#carrinhoFlutuante .carrinho-flutuante-info span{
  position:absolute!important;right:-9px!important;top:-9px!important;
  min-width:24px!important;height:24px!important;padding:0 6px!important;
  display:flex!important;align-items:center!important;justify-content:center!important;
  background:#e50914!important;color:#fff!important;border:2px solid #070707!important;border-radius:999px!important;
  font-size:10px!important;font-weight:1000!important;line-height:1!important;box-shadow:0 5px 14px rgba(0,0,0,.45)!important;
}
#carrinhoFlutuante .carrinho-flutuante-direita{display:none!important}

/* Garante que nenhum pseudo-elemento antigo volte a desenhar 🛒 */
#carrinhoFlutuante:before,#carrinhoFlutuante:after,
#carrinhoFlutuante .carrinho-flutuante-info:before,#carrinhoFlutuante .carrinho-flutuante-info:after{content:none!important;display:none!important}

/* Melhor leitura e toque sem alterar a identidade do site */
.btn-add,.categoria-btn,.btn-ver-carrinho,.btn-finalizar-pedido,.nd-v4-next,.nd-v4-back{touch-action:manipulation}
.produto h3{line-height:1.2!important}
.produto p{line-height:1.45!important}
.produto .preco{font-variant-numeric:tabular-nums!important}

@media(max-width:900px){
  #carrinhoFlutuante{right:10px!important;top:10px!important}
  .modern-search{z-index:9300!important}
}
@media(max-width:600px){
  #carrinhoFlutuante .carrinho-flutuante-info strong{min-height:42px!important;padding:9px 12px!important;border-radius:11px!important}
  #carrinhoFlutuante .carrinho-flutuante-info strong:after{font-size:10px!important}
  #carrinhoFlutuante .carrinho-flutuante-info span{right:-7px!important;top:-7px!important;min-width:22px!important;height:22px!important;font-size:9px!important}
  .produto:hover{transform:none!important}
}
@media(prefers-reduced-motion:reduce){
  #carrinhoFlutuante,.produto,.btn-add{animation:none!important;transition:none!important}
}
</style>
<script id="nd-r12-safe-improvements">
(function(){
'use strict';
function enhance(){
  /* remove resíduos de versões antigas, caso algum script velho tente recriá-los */
  ['ndCartFab','ndCartLabel','ndFxCartbar'].forEach(function(id){var el=document.getElementById(id);if(el)el.remove();});
  document.querySelectorAll('.nd-v3-buybar,.nd-cart-fab,.nd-cart-label').forEach(function(el){el.remove();});

  var cart=document.getElementById('carrinhoFlutuante');
  if(cart){
    cart.setAttribute('role','button');
    cart.setAttribute('tabindex','0');
    cart.setAttribute('aria-label','Ver carrinho');
    if(cart.dataset.r12Key!=='1'){
      cart.dataset.r12Key='1';
      cart.addEventListener('keydown',function(e){
        if(e.key==='Enter'||e.key===' '){e.preventDefault();if(typeof window.abrirCarrinho==='function')window.abrirCarrinho();}
      });
    }
  }

  /* performance: imagens fora da primeira tela carregam sob demanda */
  document.querySelectorAll('img.produto-imagem').forEach(function(img,i){
    img.decoding='async';
    if(i>3)img.loading='lazy';
  });

  /* acessibilidade básica sem alterar comportamento */
  var busca=document.getElementById('busca');if(busca&&!busca.getAttribute('aria-label'))busca.setAttribute('aria-label','Buscar no cardápio');
  document.querySelectorAll('.btn-add').forEach(function(btn){
    if(!btn.getAttribute('aria-label')){var n=btn.closest('.produto')?.querySelector('h3')?.textContent.trim()||'produto';btn.setAttribute('aria-label','Adicionar '+n);}
  });
}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',enhance);else enhance();
/* uma segunda passada cobre elementos criados dinamicamente sem manter timer contínuo */
setTimeout(enhance,900);
})();
</script>

<!-- ND BURGS — RODADA 27 / R15 — AJUSTE VISUAL DE PREÇOS -->
<style id="nd-r13-price-clean">
/* Sem sombra no valor TOTAL DO COMBO */
.r11-combo-total strong,
#r11ComboTotal{
  text-shadow:none!important;
}
/* Sem sombra no POR R$ 7,90 da Surpresa de Uva */
.r11-promo-price{
  text-shadow:none!important;
}
</style>


<!-- =========================================================
     ND BURGS — RODADA 27 / R15
     UX PREMIUM + PIX + CONFIRMAÇÃO + UPSELL INTELIGENTE
     ========================================================= -->
<style id="nd-r13-premium-upgrades">
/* Preços pedidos: sem sombra */
.r11-combo-total strong,#r11ComboTotal,.r11-promo-price{ text-shadow:none!important; }

/* Hero de entrada: brilho 3D + animações premium */
#ndFxIntro{
  position:relative;isolation:isolate;overflow:hidden;
  margin:16px auto 22px;padding:30px 22px 24px;max-width:1100px;
  border:1px solid rgba(255,157,0,.32);border-radius:24px;
  background:radial-gradient(circle at 50% 0%,rgba(255,157,0,.22),transparent 42%),linear-gradient(145deg,#17110b,#080808 62%);
  box-shadow:0 18px 55px rgba(0,0,0,.42),inset 0 1px 0 rgba(255,255,255,.08),0 0 35px rgba(255,90,0,.08);
  transform:translateZ(0);animation:ndHeroIn .7s ease both;
}
#ndFxIntro:before,#ndFxIntro:after{content:"";position:absolute;pointer-events:none;border-radius:999px;filter:blur(2px)}
#ndFxIntro:before{width:220px;height:220px;right:-80px;top:-90px;background:radial-gradient(circle,rgba(255,180,0,.26),transparent 68%);animation:ndOrb 4.5s ease-in-out infinite}
#ndFxIntro:after{width:160px;height:160px;left:-70px;bottom:-80px;background:radial-gradient(circle,rgba(255,59,0,.18),transparent 68%);animation:ndOrb 5.5s ease-in-out infinite reverse}
#ndFxIntro .ndFx-kicker{position:relative;z-index:1;display:inline-block;padding:6px 10px;border:1px solid rgba(255,210,26,.35);border-radius:999px;color:#ffd21a;font-size:10px;font-weight:1000;letter-spacing:1.6px;background:rgba(255,210,26,.06);box-shadow:0 0 18px rgba(255,210,26,.08);animation:ndGlow 2.2s ease-in-out infinite}
#ndFxIntro .ndFx-title{position:relative;z-index:1;margin-top:10px;font-size:clamp(34px,5vw,62px);font-weight:1000;line-height:.98;letter-spacing:-1.8px;text-shadow:0 3px 0 #4c2b00,0 7px 22px rgba(0,0,0,.8);animation:ndTitleFloat 3.5s ease-in-out infinite}
#ndFxIntro .ndFx-title span{display:inline-block;color:#ffd21a;background:linear-gradient(180deg,#fff6a1,#ffd21a 48%,#e59b00);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;filter:drop-shadow(0 4px 0 #805400) drop-shadow(0 8px 18px rgba(255,174,0,.18));animation:ndShine 3.8s linear infinite;background-size:180% auto}
#ndFxIntro .ndFx-sub{position:relative;z-index:1;max-width:760px;margin:14px 0 0;color:#c8c8c8;font-size:13px;line-height:1.6}
#ndFxIntro .ndFx-actions{position:relative;z-index:1;display:flex;gap:10px;flex-wrap:wrap;margin-top:18px}
#ndFxIntro .ndFx-action{position:relative;overflow:hidden;border:1px solid rgba(255,255,255,.12);border-radius:13px;padding:12px 15px;background:linear-gradient(145deg,#191919,#0c0c0c);color:#fff;font-weight:1000;cursor:pointer;box-shadow:0 5px 0 #050505,0 12px 28px rgba(0,0,0,.3);transition:transform .2s ease,box-shadow .2s ease,filter .2s ease}
#ndFxIntro .ndFx-action.primary{background:linear-gradient(145deg,#fff36b,#ffd21a 52%,#e99d00);color:#171000;border-color:#ffe66f;box-shadow:inset 0 2px 0 rgba(255,255,255,.75),0 5px 0 #8d5700,0 12px 28px rgba(255,157,0,.2)}
#ndFxIntro .ndFx-action:hover{transform:translateY(-3px) scale(1.02);filter:brightness(1.08)}
#ndFxIntro .ndFx-action:active{transform:translateY(1px) scale(.985)}

/* Caixa inteligente: só aparece para item individual que participa de combo */
#ndSmartComboOffer{position:fixed;inset:0;z-index:450000;display:none;align-items:center;justify-content:center;padding:16px;background:rgba(0,0,0,.78);backdrop-filter:blur(10px)}
#ndSmartComboOffer.show{display:flex;animation:ndFadeIn .22s ease both}
.nd-smart-panel{width:min(620px,100%);padding:22px;border:1px solid rgba(255,174,0,.55);border-radius:24px;background:radial-gradient(circle at 50% 0,rgba(255,157,0,.18),transparent 45%),linear-gradient(155deg,#1a130d,#080808 72%);box-shadow:0 30px 100px rgba(0,0,0,.82),0 0 45px rgba(255,120,0,.12);text-align:center;animation:ndSmartPop .38s cubic-bezier(.2,.8,.2,1) both}
.nd-smart-kicker{color:#ffd21a;font-size:10px;font-weight:1000;letter-spacing:1.5px}.nd-smart-panel h2{margin:7px 0 5px;font-size:clamp(25px,6vw,40px);line-height:1.02;text-shadow:0 3px 0 #4d2c00}.nd-smart-panel p{margin:0 auto;color:#aaa;font-size:12px;line-height:1.5;max-width:470px}.nd-smart-price{margin:13px 0;font-size:27px;font-weight:1000;color:#ffd21a;text-shadow:0 3px 0 #765000}.nd-smart-actions{display:grid;grid-template-columns:1fr 1fr;gap:9px}.nd-smart-actions button{border:0;border-radius:13px;padding:14px 10px;font-weight:1000;cursor:pointer}.nd-smart-keep{background:#171717;color:#fff;border:1px solid #333!important}.nd-smart-change{background:linear-gradient(145deg,#fff36b,#ffd21a,#e99d00);color:#171000;box-shadow:0 5px 0 #8d5700,0 12px 25px rgba(255,157,0,.18)}

/* PIX: aparece somente quando PIX estiver selecionado */
#ndPixBox{display:none;margin-top:13px;padding:14px;border:1px solid rgba(255,210,26,.35);border-radius:15px;background:linear-gradient(145deg,#171207,#0b0b0b);box-shadow:0 10px 28px rgba(0,0,0,.3)}
#ndPixBox.show{display:block;animation:ndSmartPop .3s ease both}
#ndPixBox .nd-pix-title{font-size:12px;font-weight:1000;color:#ffd21a}.nd-pix-key{margin:8px 0;padding:10px;border-radius:10px;background:#050505;border:1px dashed #594600;color:#fff;font-weight:1000;word-break:break-all}.nd-pix-total{font-size:19px;font-weight:1000;color:#fff}.nd-pix-total b{color:#ffd21a}.nd-pix-copy{width:100%;margin-top:9px;border:0;border-radius:11px;padding:12px;background:linear-gradient(145deg,#fff36b,#ffd21a,#e99d00);color:#171000;font-weight:1000;cursor:pointer;box-shadow:0 4px 0 #8d5700}.nd-pix-copy.copied{filter:brightness(1.12)}

/* Confirmação gigante após envio */
#ndOrderSuccess{position:fixed;inset:0;z-index:600000;display:none;place-items:center;padding:20px;background:radial-gradient(circle at 50% 42%,rgba(255,174,0,.22),transparent 34%),rgba(3,3,3,.96);backdrop-filter:blur(15px)}
#ndOrderSuccess.show{display:grid;animation:ndFadeIn .25s ease both}.nd-success-card{text-align:center;width:min(760px,100%);animation:ndSuccessPop .65s cubic-bezier(.16,1,.3,1) both}.nd-success-check{width:96px;height:96px;margin:0 auto 15px;border-radius:50%;display:grid;place-items:center;font-size:48px;background:linear-gradient(145deg,#fff36b,#ffd21a,#e99d00);color:#171000;box-shadow:inset 0 4px 0 rgba(255,255,255,.7),0 8px 0 #8d5700,0 0 55px rgba(255,174,0,.28);animation:ndCheck 1.4s ease-in-out infinite}.nd-success-card h2{margin:0;font-size:clamp(34px,7vw,72px);line-height:.94;color:#fff;text-shadow:0 4px 0 #4c2b00,0 12px 35px #000}.nd-success-card h2 span{display:block;color:#ffd21a}.nd-success-card p{margin:18px auto 0;max-width:650px;color:#ddd;font-size:clamp(14px,2.5vw,19px);font-weight:800;line-height:1.45}.nd-success-timer{margin-top:14px;color:#888;font-size:10px;font-weight:900;letter-spacing:.8px}

@keyframes ndHeroIn{from{opacity:0;transform:translateY(14px) scale(.985)}to{opacity:1;transform:none}}@keyframes ndOrb{0%,100%{transform:translate3d(0,0,0) scale(1)}50%{transform:translate3d(-15px,12px,0) scale(1.08)}}@keyframes ndGlow{0%,100%{box-shadow:0 0 10px rgba(255,210,26,.05)}50%{box-shadow:0 0 28px rgba(255,210,26,.18)}}@keyframes ndTitleFloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-2px)}}@keyframes ndShine{0%{background-position:180% 0}100%{background-position:-180% 0}}@keyframes ndFadeIn{from{opacity:0}to{opacity:1}}@keyframes ndSmartPop{from{opacity:0;transform:translateY(16px) scale(.96)}to{opacity:1;transform:none}}@keyframes ndSuccessPop{0%{opacity:0;transform:scale(.75) translateY(30px)}65%{transform:scale(1.04)}100%{opacity:1;transform:scale(1)}}@keyframes ndCheck{0%,100%{transform:scale(1) rotate(0)}50%{transform:scale(1.08) rotate(3deg)}}
@media(max-width:600px){#ndFxIntro{margin:10px 8px 18px;padding:23px 16px 18px;border-radius:20px}#ndFxIntro .ndFx-title{font-size:36px}.nd-smart-actions{grid-template-columns:1fr}.nd-smart-panel{padding:18px}.nd-success-check{width:78px;height:78px;font-size:39px}.nd-success-card h2{font-size:42px}}
@media(prefers-reduced-motion:reduce){#ndFxIntro,#ndFxIntro .ndFx-title,#ndFxIntro .ndFx-title span,#ndFxIntro .ndFx-kicker,.nd-smart-panel,#ndPixBox,#ndOrderSuccess,.nd-success-card,.nd-success-check{animation:none!important}.ndFx-action{transition:none!important}}
</style>
<script id="nd-r13-premium-js">
(function(){
'use strict';
const COMBO_MAP={
 'X-SALADA':{combo:'COMBO MAIS VENDIDO',price:20.90,kind:'trad'},
 'X-BURGUER':{combo:'COMBO MAIS VENDIDO',price:20.90,kind:'trad'},
 'X-EGG':{combo:'COMBO MAIS VENDIDO',price:20.90,kind:'trad'},
 'X-BACON':{combo:'COMBO MAIS VENDIDO',price:20.90,kind:'trad'},
 'NUNES':{combo:'COMBO MOTOCA ND',price:32.90,kind:'nunes'},
 'GAROTINHO':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80,kind:'art'},
 'DINA':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80,kind:'art'},
 'GADEIA':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80,kind:'art'},
 'PATÃO':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80,kind:'art'},
 'BERENICE':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80,kind:'art'}
};
let pending=null;
const $=s=>document.querySelector(s), $$=s=>[...document.querySelectorAll(s)];
const money=v=>Number(v||0).toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
const norm=v=>String(v||'').toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,' ').trim();
function cart(){try{return Array.isArray(window.carrinho)?window.carrinho:[]}catch(_){return[]}}
function ensureSmart(){if($('#ndSmartComboOffer'))return;const d=document.createElement('div');d.id='ndSmartComboOffer';d.innerHTML='<div class="nd-smart-panel" role="dialog" aria-modal="true"><div class="nd-smart-kicker">🔥 OPORTUNIDADE PARA SEU PEDIDO</div><h2 id="ndSmartTitle">QUER TRANSFORMAR EM COMBO?</h2><p id="ndSmartText"></p><div class="nd-smart-price" id="ndSmartPrice"></div><div class="nd-smart-actions"><button type="button" class="nd-smart-keep" id="ndSmartKeep">NÃO, MANTER ITEM</button><button type="button" class="nd-smart-change" id="ndSmartChange">SIM, TROCAR POR COMBO</button></div></div>';document.body.appendChild(d);$('#ndSmartKeep').onclick=closeSmart;$('#ndSmartChange').onclick=changeToCombo;d.addEventListener('click',e=>{if(e.target===d)closeSmart()})}
function closeSmart(){const d=$('#ndSmartComboOffer');if(d)d.classList.remove('show');pending=null}
function openSmart(name){const key=norm(name),cfg=COMBO_MAP[key];if(!cfg)return;ensureSmart();pending={name:key,cfg};$('#ndSmartText').textContent='Você adicionou '+key+' sozinho. Se quiser, pode trocar este item pelo '+cfg.combo+' e montar o combo com as opções.';$('#ndSmartPrice').textContent=cfg.combo+' • '+money(cfg.price);$('#ndSmartComboOffer').classList.add('show')}
function changeToCombo(){if(!pending)return;const p=pending;closeSmart();if(typeof window.abrirComboPersonalizacao==='function'){window.abrirComboPersonalizacao(p.cfg.combo,p.cfg.price);return}if(typeof window.adicionar==='function')window.adicionar(p.cfg.combo,p.cfg.price)}
function maybeOffer(name){const key=norm(name);const units=cart().reduce((s,i)=>s+(Number(i.quantidade)||1),0);if(COMBO_MAP[key]&&units===1)setTimeout(()=>openSmart(key),120)}
function patchAdd(){if(typeof window.adicionar!=='function'||window.adicionar.__ndR13smart)return;const old=window.adicionar;window.adicionar=function(nome,preco){const result=old.apply(this,arguments);maybeOffer(nome);return result};window.adicionar.__ndR13smart=true}

function ensurePix(){
 const step=$('[data-content="3"]');if(!step)return;let box=$('#ndPixBox');if(!box){box=document.createElement('div');box.id='ndPixBox';box.innerHTML='<div class="nd-pix-title">💠 PAGAMENTO VIA PIX</div><div style="font-size:11px;color:#aaa;margin-top:3px">Copie a chave abaixo e faça o pagamento no valor exato do pedido.</div><div class="nd-pix-key">11963973846</div><div class="nd-pix-total">Valor para pagar: <b id="ndPixTotal">R$ 0,00</b></div><button type="button" class="nd-pix-copy" id="ndPixCopy">📋 COPIAR CHAVE PIX</button><div style="font-size:9px;color:#777;margin-top:8px">SABRINA SELLIS DINIZ • CONTA NEON</div>';const select=$('#pagamentoModal');if(select)select.insertAdjacentElement('afterend',box);else step.appendChild(box);$('#ndPixCopy').onclick=async function(){try{await navigator.clipboard.writeText('11963973846');this.textContent='✅ CHAVE COPIADA!';this.classList.add('copied');setTimeout(()=>{this.textContent='📋 COPIAR CHAVE PIX';this.classList.remove('copied')},1800)}catch(_){const ta=document.createElement('textarea');ta.value='11963973846';document.body.appendChild(ta);ta.select();document.execCommand('copy');ta.remove();this.textContent='✅ CHAVE COPIADA!';setTimeout(()=>this.textContent='📋 COPIAR CHAVE PIX',1800)}}}
 const total=$('#ndV4Total')?.textContent||'R$ 0,00';const pt=$('#ndPixTotal');if(pt)pt.textContent=total;
 const pay=$('#pagamentoModal')?.value;box.classList.toggle('show',pay==='PIX');
}
function patchPay(){if(typeof window.ndPay!=='function'||window.ndPay.__ndR13)return;const old=window.ndPay;window.ndPay=function(pay){const r=old.apply(this,arguments);ensurePix();return r};window.ndPay.__ndR13=true}
function observePix(){const total=$('#ndV4Total');if(total){const ob=new MutationObserver(ensurePix);ob.observe(total,{childList:true,characterData:true,subtree:true})}const pay=$('#pagamentoModal');if(pay)pay.addEventListener('change',ensurePix);ensurePix()}

function ensureSuccess(){if($('#ndOrderSuccess'))return;const d=document.createElement('div');d.id='ndOrderSuccess';d.innerHTML='<div class="nd-success-card"><div class="nd-success-check">✓</div><h2>OBRIGADO POR ESCOLHER <span>#NDBURGS</span></h2><p>SEU PEDIDO ESTÁ <b>CONFIRMADO</b>, IRÁ PARA PRODUÇÃO E SERÁ ENTREGUE ENTRE <b>40 A 50 MINUTINHOS</b>. 🍔🔥</p><div class="nd-success-timer">ENVIANDO SEU PEDIDO PARA A ND BURGS...</div></div>';document.body.appendChild(d)}
function showSuccess(){ensureSuccess();$('#ndOrderSuccess').classList.add('show')}
function patchFinish(){if(typeof window.finalizarPedidoModal!=='function'||window.finalizarPedidoModal.__ndR13)return;const old=window.finalizarPedidoModal;window.finalizarPedidoModal=function(){
 const c=cart();if(!c.length)return alert('Seu carrinho está vazio.');
 const nome=$('#nomeModal')?.value.trim()||'',tel=($('#telefoneModal')?.value||'').replace(/\D/g,''),tipo=$('#tipoPedidoModal')?.value||'ENTREGA',rua=$('#ruaModal')?.value||'',num=$('#numeroModal')?.value.trim()||'',pay=$('#pagamentoModal')?.value||'';
 const sub=c.reduce((a,i)=>a+(Number(i.preco)||0)*(Number(i.quantidade)||1),0),fee=tipo==='ENTREGA'?Number(window.taxas?.[rua]||0):0;
 if(!nome)return alert('Digite seu nome.');if(tel.length<10||tel.length>11)return alert('Digite um WhatsApp válido com DDD.');if(tipo==='ENTREGA'&&(!rua||!num))return alert('Complete seu endereço.');if(!pay)return alert('Escolha o pagamento.');if(sub<11.90)return alert('O pedido mínimo é '+money(11.90)+'. Faltam '+money(11.90-sub)+'.');
 showSuccess();setTimeout(()=>{try{old.apply(this,arguments)}catch(e){const d=$('#ndOrderSuccess');if(d)d.classList.remove('show');throw e}},2400);
};window.finalizarPedidoModal.__ndR13=true}

function init(){patchAdd();patchPay();ensurePix();observePix();ensureSuccess();patchFinish();setTimeout(()=>{patchAdd();patchPay();ensurePix();patchFinish()},700)}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init);else init();setTimeout(init,1200);
})();
</script>

<!-- =========================================================
     ND BURGS — RODADA 27 / R15
     VISUAL 3D + DESTAQUES DIÁRIOS + PIX + CONFIRMAÇÃO
     ========================================================= -->
<style id="nd-r14-final-polish">
/* Valores sem sombra: combo e promoção */
.r11-combo-total strong,
#r11ComboTotal,
.r11-promo-price,
#ndV4Total,
.nd-v4-final-total,
.nd-smart-price,
#ndPixTotal{ text-shadow:none!important; filter:none!important; }

/* Hero/intro: tipografia 3D dourada, brilho e movimento */
#ndFxIntro .ndFx-kicker,
#ndFxIntro .ndFx-title,
#ndFxIntro .ndFx-title span,
#ndFxIntro .ndFx-sub,
#ndFxIntro .ndFx-action{will-change:transform,filter,opacity}
#ndFxIntro .ndFx-title{
  text-shadow:0 2px 0 #5b3b00,0 4px 0 #2b1c00,0 9px 24px rgba(0,0,0,.72)!important;
  animation:ndR14Title 3.8s ease-in-out infinite!important;
}
#ndFxIntro .ndFx-title span{
  color:#ffd21a!important;
  background:linear-gradient(180deg,#fffde0 0%,#fff36b 22%,#ffd21a 52%,#f2a900 78%,#a96b00 100%)!important;
  -webkit-background-clip:text!important;background-clip:text!important;
  -webkit-text-fill-color:transparent!important;
  filter:drop-shadow(0 2px 0 #8b5b00) drop-shadow(0 5px 10px rgba(255,196,0,.35))!important;
  background-size:220% auto!important;
  animation:ndR14Shine 3s linear infinite!important;
}
#ndFxIntro .ndFx-sub{animation:ndR14Fade .8s ease .15s both}
#ndFxIntro .ndFx-action.primary{
  color:#171000!important;
  text-shadow:0 1px 0 rgba(255,255,255,.55);
  box-shadow:inset 0 2px 0 rgba(255,255,255,.8),0 4px 0 #8d5700,0 10px 26px rgba(255,157,0,.22),0 0 20px rgba(255,210,26,.12)!important;
  animation:ndR14Button 2.6s ease-in-out infinite;
}
#ndFxIntro .ndFx-action:not(.primary){text-shadow:0 2px 10px rgba(255,210,26,.15)}

/* 3 cards diários: destaque forte */
#ndAutoBest .r11-best-head h2{color:#fff!important;text-shadow:0 2px 0 #4a2b00,0 0 18px rgba(255,210,26,.18)!important}
#ndAutoBest .nd-daily-best-card{position:relative;overflow:hidden;border-color:rgba(255,210,26,.38)!important;box-shadow:inset 0 1px 0 rgba(255,255,255,.06),0 12px 30px rgba(0,0,0,.35),0 0 22px rgba(255,174,0,.07)!important;animation:ndR14CardIn .55s cubic-bezier(.2,.8,.2,1) both}
#ndAutoBest .nd-daily-best-card:nth-child(2){animation-delay:.09s}
#ndAutoBest .nd-daily-best-card:nth-child(3){animation-delay:.18s}
#ndAutoBest .nd-daily-best-card:before{content:"";position:absolute;inset:-60%;background:linear-gradient(115deg,transparent 42%,rgba(255,244,130,.16) 50%,transparent 58%);transform:translateX(-45%) rotate(8deg);animation:ndR14Sweep 4.8s linear infinite;pointer-events:none}
#ndAutoBest .nd-daily-best-card>*{position:relative;z-index:1}
#ndAutoBest .nd-daily-best-card img{border:1px solid rgba(255,210,26,.20);box-shadow:0 5px 18px rgba(0,0,0,.35)}
#ndAutoBest .nd-daily-best-card strong{font-size:13px;text-shadow:0 1px 8px rgba(255,210,26,.12)}
#ndAutoBest .nd-daily-best-card span{font-size:15px!important;text-shadow:none!important}
#ndAutoBest .nd-daily-best-card small{display:block;color:#ffd21a;font-size:9px;font-weight:1000;letter-spacing:.7px;margin-top:4px}
#ndAutoBest .nd-daily-best-card button{box-shadow:0 4px 0 #8d4300,0 8px 18px rgba(255,90,0,.16);transition:.18s ease}
#ndAutoBest .nd-daily-best-card button:hover{transform:translateY(-2px);filter:brightness(1.08)}
.nd-best-rank{position:absolute!important;top:7px;left:7px;z-index:3!important;min-width:25px;padding:4px 6px;border-radius:999px;background:linear-gradient(145deg,#fff36b,#ffd21a,#e99d00);color:#171000;font-size:9px;font-weight:1000;text-align:center;box-shadow:0 3px 0 #8d5700}

/* Modal de oportunidade: deixa claro que o cliente pode manter o item */
#ndSmartComboOffer .nd-smart-panel{border-width:1px}
#ndSmartComboOffer .nd-smart-keep{box-shadow:inset 0 1px 0 rgba(255,255,255,.05)}
#ndSmartComboOffer .nd-smart-change{box-shadow:inset 0 2px 0 rgba(255,255,255,.75),0 5px 0 #8d5700,0 12px 25px rgba(255,157,0,.18)}

/* PIX: valor grande, claro e copiável */
#ndPixBox .nd-pix-total{margin-top:10px;padding:10px;border-radius:10px;background:#080808;border:1px solid rgba(255,210,26,.16)}
#ndPixBox .nd-pix-copy,#ndPixCopyValue{min-height:46px}

/* Confirmação gigante */
#ndOrderSuccess{z-index:600000!important}
#ndOrderSuccess .nd-success-card h2{letter-spacing:-1.6px;text-shadow:0 4px 0 #4c2b00,0 12px 35px #000!important}
#ndOrderSuccess .nd-success-card h2 span{filter:drop-shadow(0 4px 0 #805400) drop-shadow(0 0 20px rgba(255,210,26,.22))}

@keyframes ndR14Title{0%,100%{transform:translateY(0) rotateX(0)}50%{transform:translateY(-3px) rotateX(1deg)}}
@keyframes ndR14Shine{0%{background-position:220% 0}100%{background-position:-220% 0}}
@keyframes ndR14Button{0%,100%{transform:translateY(0)}50%{transform:translateY(-2px)}}
@keyframes ndR14Fade{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}
@keyframes ndR14CardIn{from{opacity:0;transform:translateY(12px) scale(.985)}to{opacity:1;transform:none}}
@keyframes ndR14Sweep{0%{transform:translateX(-70%) rotate(8deg)}55%,100%{transform:translateX(70%) rotate(8deg)}}
@media(max-width:700px){
 #ndAutoBest .nd-daily-best-card{min-width:285px}
 #ndFxIntro .ndFx-title{font-size:36px!important}
}
@media(prefers-reduced-motion:reduce){
 #ndFxIntro .ndFx-title,#ndFxIntro .ndFx-title span,#ndFxIntro .ndFx-action.primary,#ndFxIntro .ndFx-sub,#ndAutoBest .nd-daily-best-card,#ndAutoBest .nd-daily-best-card:before{animation:none!important}
}
</style>
<script id="nd-r14-logic">
(function(){
'use strict';
const R14_MAP={
 'X-SALADA':{combo:'COMBO MAIS VENDIDO',price:20.90},'X-BURGUER':{combo:'COMBO MAIS VENDIDO',price:20.90},'X-EGG':{combo:'COMBO MAIS VENDIDO',price:20.90},'X-BACON':{combo:'COMBO MAIS VENDIDO',price:20.90},
 'NUNES':{combo:'COMBO MOTOCA ND',price:32.90},
 'GAROTINHO':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80},'DINA':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80},'GADEIA':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80},'PATÃO':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80},'BERENICE':{combo:'ARTESANAL COMBO MAIS VENDIDO',price:34.80}
};
const norm=v=>String(v||'').toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,' ').trim();
const cart=()=>Array.isArray(window.carrinho)?window.carrinho:[];
function removeOne(name){const a=cart(),i=a.findIndex(x=>norm(x.nome)===norm(name)&&!x.detalhes);if(i<0)return false;if(Number(a[i].quantidade)>1)a[i].quantidade--;else a.splice(i,1);if(typeof window.atualizarCarrinho==='function')window.atualizarCarrinho();try{localStorage.setItem('carrinho',JSON.stringify(a));localStorage.setItem('ndburgs_carrinho',JSON.stringify(a))}catch(_){}return true}
function patchSmart(){
 if(typeof window.adicionar!=='function'||window.adicionar.__ndR14smart)return;
 const old=window.adicionar;
 window.adicionar=function(nome,preco){
   const key=norm(nome),cfg=R14_MAP[key];
   const before=cart().find(x=>norm(x.nome)===key&&!x.detalhes);
   const result=old.apply(this,arguments);
   /* Só oferece quando o cliente adiciona pela primeira vez aquele item individual. */
   const totalUnits=cart().reduce((s,i)=>s+(Number(i.quantidade)||1),0);
   if(cfg&&!before&&totalUnits===1){
     setTimeout(()=>{
       const box=document.getElementById('ndSmartComboOffer');
       const title=document.getElementById('ndSmartTitle'),text=document.getElementById('ndSmartText'),price=document.getElementById('ndSmartPrice');
       if(!box||!title||!text||!price)return;
       box.dataset.item=key;box.dataset.combo=cfg.combo;box.dataset.price=cfg.price;
       title.textContent='QUER TRANSFORMAR EM COMBO?';
       text.textContent='Você adicionou '+key+' sozinho. Se quiser, pode trocar este item pelo combo e escolher as opções incluídas.';
       price.textContent=cfg.combo+' • R$ '+cfg.price.toFixed(2).replace('.',',');
       box.classList.add('show');
       const keep=document.getElementById('ndSmartKeep'),change=document.getElementById('ndSmartChange');
       if(keep)keep.textContent='NÃO, MANTER ITEM';
       if(change){change.textContent='SIM, TROCAR POR COMBO';change.onclick=function(){const n=box.dataset.item,c=box.dataset.combo,p=Number(box.dataset.price);box.classList.remove('show');removeOne(n);setTimeout(()=>{if(typeof window.abrirComboPersonalizacao==='function')window.abrirComboPersonalizacao(c,p)},80)}}
     },140);
   }
   return result;
 };
 window.adicionar.__ndR14smart=true;
}
function patchPix(){
 if(typeof window.ndPay!=='function'||window.ndPay.__ndR14pix)return;
 const old=window.ndPay;
 window.ndPay=function(pay){const r=old.apply(this,arguments);setTimeout(refreshPix,40);return r};window.ndPay.__ndR14pix=true;
}
function refreshPix(){
 const box=document.getElementById('ndPixBox'),sel=document.getElementById('pagamentoModal');if(!box||!sel)return;
 const tipo=document.getElementById('tipoPedidoModal')?.value||'ENTREGA',rua=document.getElementById('ruaModal')?.value||'';
 const sub=cart().reduce((a,i)=>a+(Number(i.preco)||0)*(Number(i.quantidade)||1),0),fee=tipo==='ENTREGA'?Number(window.taxas?.[rua]||0):0,total=sub+fee;
 const pt=document.getElementById('ndPixTotal');if(pt)pt.textContent=total.toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
 box.classList.toggle('show',sel.value==='PIX');
 if(sel.value==='PIX'&&!document.getElementById('ndPixCopyValue')){const b=document.createElement('button');b.id='ndPixCopyValueLegacy';b.type='button';b.className='nd-pix-copy';b.textContent='💰 COPIAR VALOR';b.onclick=async()=>{const val=total.toFixed(2).replace('.',',');try{await navigator.clipboard.writeText(val)}catch(_){const ta=document.createElement('textarea');ta.value=val;document.body.appendChild(ta);ta.select();document.execCommand('copy');ta.remove()}b.textContent='✅ VALOR COPIADO!';setTimeout(()=>b.textContent='💰 COPIAR VALOR',1600)};box.appendChild(b)}
}
function patchFinish(){
 if(typeof window.finalizarPedidoModal!=='function'||window.finalizarPedidoModal.__ndR14finish)return;
 const old=window.finalizarPedidoModal;
 window.finalizarPedidoModal=function(){
   const result=old.apply(this,arguments);
   return result;
 };
 window.finalizarPedidoModal.__ndR14finish=true;
}
function patchIntro(){const btn=[...document.querySelectorAll('.ndFx-action')].find(x=>norm(x.textContent).includes('VER MAIS VENDIDOS'));if(!btn||btn.dataset.ndR14btn)return;btn.dataset.ndR14btn='1';btn.onclick=()=>{const sec=document.getElementById('ndAutoBest');if(sec)sec.scrollIntoView({behavior:'smooth',block:'start'})}}
function init(){patchSmart();patchPix();refreshPix();patchIntro();setTimeout(()=>{patchSmart();patchPix();refreshPix();patchIntro()},700)}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init);else init();
setTimeout(init,1400);
})();
</script>

<!-- =========================================================
     ND BURGS — RODADA 27 / R15
     LUZES AZUIS/ROXAS + PIX COMPLETO + ANIMAÇÃO DE ADIÇÃO
     ========================================================= -->
<style id="nd-r15-final">
/* ===== TOTAL DO COMBO E PROMOÇÃO SEM SOMBRA ===== */
.r11-combo-total strong,#r11ComboTotal,.r11-promo-price,#ndV4Total,.nd-v4-final-total,#totalCarrinhoModal,#totalFinalizarModal,#total{
  text-shadow:none!important;filter:none!important;
}

/* ===== HERO: LUZES AZUIS E ROXAS SE MOVENDO ===== */
#ndFxIntro{
  isolation:isolate!important;
  background:
    radial-gradient(circle at 15% 15%,rgba(48,105,255,.22),transparent 28%),
    radial-gradient(circle at 88% 20%,rgba(155,55,255,.25),transparent 30%),
    radial-gradient(circle at 55% 100%,rgba(46,82,255,.16),transparent 34%),
    linear-gradient(145deg,#070912,#090612 55%,#050509)!important;
  border-color:rgba(105,92,255,.38)!important;
  box-shadow:0 18px 55px rgba(0,0,0,.55),inset 0 1px 0 rgba(255,255,255,.08),0 0 42px rgba(72,86,255,.14),0 0 70px rgba(155,55,255,.08)!important;
}
#ndFxIntro:before,#ndFxIntro:after{content:""!important;pointer-events:none!important;z-index:0!important;filter:blur(2px)!important}
#ndFxIntro:before{
  width:380px!important;height:115px!important;right:-110px!important;top:18px!important;border-radius:999px!important;
  background:linear-gradient(90deg,transparent,rgba(58,103,255,.55),rgba(145,54,255,.48),transparent)!important;
  transform:rotate(-14deg)!important;animation:ndR15LightA 5.5s ease-in-out infinite!important;
}
#ndFxIntro:after{
  width:330px!important;height:95px!important;left:-100px!important;bottom:12px!important;border-radius:999px!important;
  background:linear-gradient(90deg,transparent,rgba(151,55,255,.48),rgba(49,91,255,.55),transparent)!important;
  transform:rotate(13deg)!important;animation:ndR15LightB 6.5s ease-in-out infinite!important;
}
#ndFxIntro>*{position:relative;z-index:2}
#ndFxIntro .ndFx-kicker{
  border-color:rgba(112,126,255,.5)!important;
  color:#b9c4ff!important;background:rgba(67,82,255,.08)!important;
  box-shadow:0 0 18px rgba(72,94,255,.18),0 0 30px rgba(156,58,255,.08)!important;
}
#ndFxIntro .ndFx-title span{
  background:linear-gradient(100deg,#dce4ff 0%,#7d9dff 28%,#d18cff 50%,#6e8dff 72%,#f0d7ff 100%)!important;
  background-size:220% auto!important;
  filter:drop-shadow(0 0 10px rgba(92,115,255,.42)) drop-shadow(0 0 18px rgba(174,75,255,.22))!important;
}
#ndFxIntro .ndFx-sub{color:#d1d4e6!important}
#ndFxIntro .ndFx-action.primary{
  background:linear-gradient(135deg,#dbe4ff,#8ea8ff 46%,#9b55ff)!important;
  color:#090914!important;border-color:rgba(214,224,255,.75)!important;
  box-shadow:inset 0 2px 0 rgba(255,255,255,.75),0 4px 0 #40358c,0 10px 28px rgba(79,91,255,.28),0 0 25px rgba(156,65,255,.16)!important;
}
#ndFxIntro .ndFx-action:not(.primary){
  border-color:rgba(120,123,190,.35)!important;background:linear-gradient(145deg,#121525,#090b13)!important;
  box-shadow:0 5px 0 #03040a,0 12px 28px rgba(0,0,0,.35),0 0 18px rgba(80,96,255,.08)!important;
}

/* ===== BRILHO EM TODA A FAIXA DE INTRODUÇÃO ===== */
#ndFxIntro .ndFx-title{filter:drop-shadow(0 0 7px rgba(78,99,255,.12))}

/* ===== ANIMAÇÃO AO ADICIONAR ITEM ===== */
.produto.nd-r15-added{animation:ndR15Added .55s cubic-bezier(.2,.85,.25,1) both!important}
.btn-add.nd-r15-btn-added{animation:ndR15Btn .5s ease both!important}
.nd-r15-toast{
  position:fixed;right:18px;top:18px;z-index:800000;max-width:min(360px,calc(100vw - 36px));
  padding:12px 15px;border:1px solid rgba(139,122,255,.65);border-radius:14px;
  background:linear-gradient(135deg,rgba(13,18,45,.97),rgba(31,10,55,.97));color:#fff;
  box-shadow:0 15px 40px rgba(0,0,0,.55),0 0 28px rgba(93,89,255,.22);
  font-size:12px;font-weight:1000;pointer-events:none;animation:ndR15Toast .9s ease both;
}
.nd-r15-toast b{color:#bba7ff}

/* ===== PIX: CHAVE + VALOR + BOTÕES DE CÓPIA ===== */
#ndPixBox{border-color:rgba(101,114,255,.42)!important;background:linear-gradient(145deg,#0d1020,#100918)!important;box-shadow:0 10px 30px rgba(0,0,0,.35),0 0 25px rgba(80,90,255,.09)!important}
#ndPixBox .nd-pix-title{color:#b9c4ff!important}
#ndPixBox .nd-pix-key{border-color:rgba(115,98,255,.5)!important}
#ndPixBox .nd-pix-total{border-color:rgba(115,98,255,.32)!important}
#ndPixBox .nd-pix-total b{color:#c6a8ff!important;text-shadow:none!important}
#ndPixBox .nd-pix-copy{background:linear-gradient(135deg,#dbe4ff,#91a8ff 48%,#a25cff)!important;color:#090914!important;box-shadow:0 4px 0 #40358c,0 0 20px rgba(94,100,255,.15)!important}
#ndPixBox #ndPixCopyValue{background:linear-gradient(135deg,#fff,#c7d2ff 48%,#c98cff)!important}

/* ===== CONFIRMAÇÃO GIGANTE ===== */
#ndOrderSuccess{
  background:
    radial-gradient(circle at 50% 35%,rgba(67,91,255,.25),transparent 25%),
    radial-gradient(circle at 20% 75%,rgba(163,59,255,.18),transparent 28%),
    rgba(3,3,8,.97)!important;
}
#ndOrderSuccess:before,#ndOrderSuccess:after{content:"";position:absolute;pointer-events:none;border-radius:999px;filter:blur(5px)}
#ndOrderSuccess:before{width:65vw;height:18vw;background:linear-gradient(90deg,transparent,rgba(54,96,255,.22),rgba(165,58,255,.22),transparent);animation:ndR15SuccessLight 4s ease-in-out infinite}
#ndOrderSuccess:after{width:48vw;height:12vw;background:linear-gradient(90deg,transparent,rgba(168,61,255,.16),rgba(60,93,255,.18),transparent);animation:ndR15SuccessLight 5s ease-in-out infinite reverse}
#ndOrderSuccess .nd-success-card{position:relative;z-index:2}
#ndOrderSuccess .nd-success-check{background:linear-gradient(145deg,#e2e8ff,#8ea8ff,#a55cff)!important;color:#080914!important;box-shadow:inset 0 4px 0 rgba(255,255,255,.75),0 8px 0 #40358c,0 0 55px rgba(85,103,255,.34),0 0 75px rgba(167,66,255,.18)!important}
#ndOrderSuccess .nd-success-card h2 span{color:#c5a8ff!important;filter:drop-shadow(0 0 18px rgba(156,74,255,.35))!important}
#ndOrderSuccess .nd-success-card p b{color:#aabaff!important}

@keyframes ndR15LightA{0%,100%{transform:translate3d(30px,0,0) rotate(-14deg);opacity:.35}50%{transform:translate3d(-190px,38px,0) rotate(-8deg);opacity:.85}}
@keyframes ndR15LightB{0%,100%{transform:translate3d(-20px,0,0) rotate(13deg);opacity:.3}50%{transform:translate3d(190px,-30px,0) rotate(7deg);opacity:.8}}
@keyframes ndR15Added{0%{transform:scale(1);filter:brightness(1)}35%{transform:scale(1.035);filter:brightness(1.35) drop-shadow(0 0 14px rgba(94,107,255,.5))}100%{transform:scale(1);filter:none}}
@keyframes ndR15Btn{0%{transform:scale(1)}45%{transform:scale(.94);filter:brightness(1.35)}100%{transform:scale(1)}}
@keyframes ndR15Toast{0%{opacity:0;transform:translateY(-12px) scale(.96)}18%{opacity:1;transform:none}78%{opacity:1;transform:none}100%{opacity:0;transform:translateY(-8px) scale(.98)}}
@keyframes ndR15SuccessLight{0%,100%{transform:translateX(-18%) rotate(-6deg);opacity:.35}50%{transform:translateX(18%) rotate(6deg);opacity:.85}}
@media(max-width:600px){
 #ndFxIntro:before{width:280px!important;height:90px!important}
 #ndFxIntro:after{width:250px!important;height:75px!important}
 .nd-r15-toast{top:10px;right:10px;left:10px;max-width:none;text-align:center}
}
@media(prefers-reduced-motion:reduce){
 #ndFxIntro:before,#ndFxIntro:after,.produto.nd-r15-added,.btn-add.nd-r15-btn-added,.nd-r15-toast,#ndOrderSuccess:before,#ndOrderSuccess:after{animation:none!important}
}
</style>
<script id="nd-r15-final-js">
(function(){
'use strict';
const q=s=>document.querySelector(s),qa=s=>Array.from(document.querySelectorAll(s));
function money(n){return 'R$ '+Number(n||0).toFixed(2).replace('.',',')}
function animateAdded(name){
  const key=String(name||'').trim().toUpperCase();
  const card=qa('.produto').find(c=>(c.querySelector('h3')?.textContent||'').trim().toUpperCase()===key);
  if(card){card.classList.remove('nd-r15-added');void card.offsetWidth;card.classList.add('nd-r15-added');setTimeout(()=>card.classList.remove('nd-r15-added'),650);}
  const btn=card?.querySelector('.btn-add');
  if(btn){btn.classList.remove('nd-r15-btn-added');void btn.offsetWidth;btn.classList.add('nd-r15-btn-added');setTimeout(()=>btn.classList.remove('nd-r15-btn-added'),600);}
  let t=document.querySelector('.nd-r15-toast');if(t)t.remove();
  t=document.createElement('div');t.className='nd-r15-toast';t.innerHTML='✅ <b>'+String(name).replace(/[&<>"']/g,m=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[m]))+'</b> adicionado ao carrinho';document.body.appendChild(t);setTimeout(()=>t.remove(),950);
}
function patchAdicionar(){
 if(typeof window.adicionar!=='function'||window.adicionar.__ndR15)return;
 const old=window.adicionar;
 window.adicionar=function(nome,preco){const r=old.apply(this,arguments);animateAdded(nome);return r};
 window.adicionar.__ndR15=true;
}
function patchComboConfirm(){
 if(typeof window.confirmarComboPersonalizacao!=='function'||window.confirmarComboPersonalizacao.__ndR15)return;
 const old=window.confirmarComboPersonalizacao;
 window.confirmarComboPersonalizacao=function(){const r=old.apply(this,arguments);animateAdded(document.getElementById('r11ComboTitle')?.textContent?.replace(/^🍔\s*/,'' )||'COMBO');return r};
 window.confirmarComboPersonalizacao.__ndR15=true;
}
function ensurePixButtons(){
 const box=q('#ndPixBox');if(!box)return;
 const totalText=q('#ndPixTotal')?.textContent||'R$ 0,00';
 let b=q('#ndPixCopyValue');
 if(!b){b=document.createElement('button');b.id='ndPixCopyValue';b.type='button';b.className='nd-pix-copy';b.textContent='💰 COPIAR VALOR DO PEDIDO';box.appendChild(b)}
 b.onclick=async function(){
   const raw=q('#ndPixTotal')?.textContent||totalText;
   const val=raw.replace(/[^0-9,.-]/g,'').trim();
   try{await navigator.clipboard.writeText(val)}catch(_){const ta=document.createElement('textarea');ta.value=val;document.body.appendChild(ta);ta.select();document.execCommand('copy');ta.remove()}
   b.textContent='✅ VALOR COPIADO!';setTimeout(()=>b.textContent='💰 COPIAR VALOR DO PEDIDO',1700);
 };
}
function init(){patchAdicionar();patchComboConfirm();ensurePixButtons();setTimeout(()=>{patchAdicionar();patchComboConfirm();ensurePixButtons()},800)}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init);else init();
})();
</script>


<!-- =========================================================
     ND BURGS — RODADA 28 / R16
     HERO AZUL/ROXO + SEM SOMBRAS NOS VALORES + PIX + CONFIRMAÇÃO
     + UPSELL DE COMBO SOMENTE PARA 1 ITEM INDIVIDUAL
     ========================================================= -->
<style id="nd-r16-final">
/* TOTAL DO COMBO E SURPRESA DE UVA: ZERO SOMBRA */
.r11-combo-total strong,#r11ComboTotal,.r11-promo-price,#ndUvaPromo .r11-promo-price{
  text-shadow:none!important;filter:none!important;box-shadow:none!important;
}

/* TOPO: todas as letras brancas, sem sombra, com brilho contínuo sem sombra tipográfica */
#ndFxIntro .ndFx-kicker,
#ndFxIntro .ndFx-title,
#ndFxIntro .ndFx-title span,
#ndFxIntro .ndFx-sub{
  color:#fff!important;-webkit-text-fill-color:#fff!important;background:none!important;
  text-shadow:none!important;filter:none!important;
}
#ndFxIntro .ndFx-kicker{border-color:rgba(125,135,255,.55)!important;background:rgba(75,85,255,.08)!important}
#ndFxIntro .ndFx-title,#ndFxIntro .ndFx-title span,#ndFxIntro .ndFx-kicker,#ndFxIntro .ndFx-sub{
  animation:ndR16TextGlow 2.4s ease-in-out infinite!important;
}
#ndFxIntro .ndFx-sub{animation-delay:.35s!important}
#ndFxIntro .ndFx-kicker{animation-delay:.15s!important}
#ndFxIntro{
  background:
    radial-gradient(circle at 10% 18%,rgba(47,99,255,.27),transparent 30%),
    radial-gradient(circle at 92% 22%,rgba(170,58,255,.29),transparent 32%),
    radial-gradient(circle at 48% 105%,rgba(85,69,255,.19),transparent 38%),
    linear-gradient(145deg,#050713,#0b0615 58%,#040408)!important;
  border-color:rgba(104,104,255,.48)!important;
  box-shadow:0 18px 55px rgba(0,0,0,.55),0 0 44px rgba(65,86,255,.16),0 0 75px rgba(154,56,255,.10)!important;
}
#ndFxIntro:before,#ndFxIntro:after{filter:blur(3px)!important;mix-blend-mode:screen!important}
#ndFxIntro:before{
  background:linear-gradient(90deg,transparent,rgba(42,104,255,.72),rgba(174,57,255,.62),transparent)!important;
  animation:ndR16BeamA 5.2s ease-in-out infinite!important;
}
#ndFxIntro:after{
  background:linear-gradient(90deg,transparent,rgba(175,58,255,.62),rgba(55,101,255,.70),transparent)!important;
  animation:ndR16BeamB 6.2s ease-in-out infinite!important;
}
#ndFxIntro .ndFx-action{position:relative;isolation:isolate}
#ndFxIntro .ndFx-action:before{content:"";position:absolute;inset:-2px auto -2px -55%;width:38%;background:linear-gradient(90deg,transparent,rgba(255,255,255,.7),transparent);transform:skewX(-18deg);animation:ndR16ButtonSweep 3.4s linear infinite;z-index:-1;pointer-events:none}

/* Animação extra ao adicionar: card + botão + contador do carrinho */
#carrinhoFlutuante.nd-r16-cart-pop{animation:ndR16CartPop .52s cubic-bezier(.2,.9,.25,1)!important}
.produto.nd-r16-product-pop{animation:ndR16ProductPop .58s cubic-bezier(.2,.85,.25,1)!important}

/* Oferta de combo grande e clara */
#ndSmartComboOffer .nd-smart-panel{border-color:rgba(115,108,255,.62)!important;box-shadow:0 24px 85px rgba(0,0,0,.82),0 0 40px rgba(80,90,255,.18),0 0 55px rgba(161,57,255,.10)!important}
#ndSmartComboOffer .nd-smart-kicker{color:#bfc8ff!important}
#ndSmartComboOffer .nd-smart-price{color:#fff!important;text-shadow:none!important}

/* PIX: valor e chave bem visíveis */
#ndPixBox{display:none}
#ndPixBox.show{display:block!important;animation:ndR16PixIn .35s ease both}
#ndPixBox .nd-pix-key{font-size:17px!important;letter-spacing:.7px!important;text-align:center!important}
#ndPixBox .nd-pix-total{font-size:20px!important;text-align:center!important}
#ndPixBox .nd-pix-total b{font-size:24px!important;color:#fff!important;text-shadow:none!important}

/* Confirmação final gigante */
#ndOrderSuccess.show{display:flex!important}
#ndOrderSuccess .nd-success-card{width:min(980px,94vw)!important;padding:clamp(24px,5vw,56px)!important}
#ndOrderSuccess .nd-success-card h2{font-size:clamp(44px,7vw,92px)!important;line-height:.92!important;color:#fff!important;text-shadow:none!important;animation:ndR16SuccessTitle 1.8s ease-in-out infinite!important}
#ndOrderSuccess .nd-success-card h2 span{color:#fff!important;filter:none!important;text-shadow:none!important}
#ndOrderSuccess .nd-success-card p{font-size:clamp(18px,2.5vw,31px)!important;line-height:1.3!important;color:#fff!important}
#ndOrderSuccess .nd-success-card p b{color:#fff!important;text-shadow:none!important}
#ndOrderSuccess .nd-success-timer{margin-top:18px;font-size:12px!important;color:#c7caff!important;letter-spacing:1px!important}

@keyframes ndR16TextGlow{0%,100%{opacity:.82}50%{opacity:1}}
@keyframes ndR16BeamA{0%,100%{transform:translate3d(55px,-5px,0) rotate(-14deg);opacity:.25}50%{transform:translate3d(-210px,42px,0) rotate(-8deg);opacity:.95}}
@keyframes ndR16BeamB{0%,100%{transform:translate3d(-45px,8px,0) rotate(13deg);opacity:.23}50%{transform:translate3d(215px,-35px,0) rotate(7deg);opacity:.88}}
@keyframes ndR16ButtonSweep{0%{left:-55%}65%,100%{left:135%}}
@keyframes ndR16CartPop{0%{transform:scale(1)}35%{transform:scale(1.12)}100%{transform:scale(1)}}
@keyframes ndR16ProductPop{0%{transform:scale(1)}35%{transform:scale(1.028);outline:2px solid rgba(116,107,255,.58)}100%{transform:scale(1);outline-color:transparent}}
@keyframes ndR16PixIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}
@keyframes ndR16SuccessTitle{0%,100%{transform:scale(1);opacity:.92}50%{transform:scale(1.025);opacity:1}}
@media(max-width:600px){#ndOrderSuccess .nd-success-card h2{font-size:42px!important}#ndOrderSuccess .nd-success-card p{font-size:18px!important}}
@media(prefers-reduced-motion:reduce){#ndFxIntro:before,#ndFxIntro:after,#ndFxIntro .ndFx-title,#ndFxIntro .ndFx-title span,#ndFxIntro .ndFx-kicker,#ndFxIntro .ndFx-sub,#ndFxIntro .ndFx-action:before,#ndOrderSuccess .nd-success-card h2{animation:none!important}}
</style>
<script id="nd-r16-final-js">
(function(){
'use strict';
const $=s=>document.querySelector(s), $$=s=>Array.from(document.querySelectorAll(s));
const norm=v=>String(v||'').toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,' ').trim();

/* Garante as fotos novas exatamente nos produtos enviados pelo usuário. */
const PHOTO_MAP={
 'FATIA QUEIJO CHEDDAR EXTRA':'https://i.ibb.co/ZRydT4hD/fatia-de-queijo.png',
 'POTINHO MAIONESE VERDE':'https://i.ibb.co/DDCZpVLW/potinho-maionese-verde.png',
 'HAMBURGUER EXTRA ARTESANAL':'https://i.ibb.co/wZfS9rn1/hamburguer-artesanal.png',
 'POTINHO CHEDDAR':'https://i.ibb.co/DHNQ0kwS/potinho-cheddar.png',
 'BACON':'https://i.ibb.co/6RxLhQBG/adicional-bacon.png',
 'ADICIONAL BACON':'https://i.ibb.co/6RxLhQBG/adicional-bacon.png',
 'POTINHO BARBECUE':'https://i.ibb.co/n8KHqTMg/potinho-barbecue.png',
 'ADICIONAL CHEDDAR':'https://i.ibb.co/cHt8ZjS/adicional-molho-cheddar.png',
 'POTINHO MAIONESE ARTESANAL':'https://i.ibb.co/Y4DcTLwD/maionese-artesanal.png',
 'HAMBURGUER EXTRA TRADICIONAL':'https://i.ibb.co/TqhkXgRF/HAMBURGUER-TRADICIONAL.png',
 'COCA COLA LATA':'https://i.ibb.co/r2zDycx0/Chat-GPT-Image-4-09-2026-21-18-50.png',
 'SURPRESA DE UVA':'https://i.ibb.co/9kC6V4gP/Chat-GPT-Image-5-09-2026-06-50-46.png'
};
function applyPhotos(){
 $$('.produto').forEach(card=>{const name=norm(card.querySelector('h3')?.textContent);const src=PHOTO_MAP[name];if(!src)return;let img=card.querySelector('img.produto-imagem');if(!img){img=document.createElement('img');img.className='produto-imagem';img.loading='lazy';img.decoding='async';card.insertBefore(img,card.firstChild)}img.src=src;img.alt=name;});
 const promo=$('#ndUvaPromo img');if(promo)promo.src=PHOTO_MAP['SURPRESA DE UVA'];
}

/* Botão VER MAIS VENDIDOS sempre funcional e atualiza os 3 destaques do dia antes de rolar. */
function bindBest(){
 const btn=$$('.ndFx-action').find(b=>norm(b.textContent).includes('VER MAIS VENDIDOS'));if(!btn||btn.dataset.ndR16Best)return;btn.dataset.ndR16Best='1';
 btn.onclick=function(){if(typeof window.renderBest==='function')try{window.renderBest()}catch(_){}const sec=$('#ndAutoBest');if(sec){sec.scrollIntoView({behavior:'smooth',block:'start'});sec.animate?.([{transform:'scale(1)'},{transform:'scale(1.01)'},{transform:'scale(1)'}],{duration:550})}};
}

/* Animação adicional ao adicionar qualquer item. */
function pop(name){
 const key=norm(name),card=$$('.produto').find(c=>norm(c.querySelector('h3')?.textContent)===key);if(card){card.classList.remove('nd-r16-product-pop');void card.offsetWidth;card.classList.add('nd-r16-product-pop');setTimeout(()=>card.classList.remove('nd-r16-product-pop'),650)}
 const cart=$('#carrinhoFlutuante');if(cart){cart.classList.remove('nd-r16-cart-pop');void cart.offsetWidth;cart.classList.add('nd-r16-cart-pop');setTimeout(()=>cart.classList.remove('nd-r16-cart-pop'),600)}
}
function patchAdd(){if(typeof window.adicionar!=='function'||window.adicionar.__ndR16)return;const old=window.adicionar;window.adicionar=function(nome,preco){const r=old.apply(this,arguments);pop(nome);return r};window.adicionar.__ndR16=true}

/* PIX: mantém chave e valor sincronizados com o total visível. */
function refreshPix(){
 const box=$('#ndPixBox'),pay=$('#pagamentoModal');if(!box||!pay)return;box.classList.toggle('show',pay.value==='PIX');
 const total=$('#ndV4Total')?.textContent||$('#totalFinalizarModal')?.textContent||'R$ 0,00';const out=$('#ndPixTotal');if(out)out.textContent=total;
}
function bindPix(){const pay=$('#pagamentoModal');if(pay&&!pay.dataset.ndR16){pay.dataset.ndR16='1';pay.addEventListener('change',refreshPix)}const total=$('#ndV4Total');if(total&&!total.dataset.ndR16Obs){total.dataset.ndR16Obs='1';new MutationObserver(refreshPix).observe(total,{subtree:true,childList:true,characterData:true})}refreshPix()}

/* Ajusta o texto da confirmação, inclusive se uma camada antiga recriar o modal. */
function fixSuccess(){const h=$('#ndOrderSuccess .nd-success-card h2'),p=$('#ndOrderSuccess .nd-success-card p'),t=$('#ndOrderSuccess .nd-success-timer');if(h)h.innerHTML='OBRIGADO POR ESCOLHER <span>#NDBURGS</span>';if(p)p.innerHTML='SEU PEDIDO ESTÁ <b>CONFIRMADO</b>, IRÁ PARA PRODUÇÃO E SERÁ ENTREGUE ENTRE <b>40 A 50 MINUTINHOS</b>. 🍔🔥';if(t)t.textContent='ENVIANDO SEU PEDIDO PARA A ND BURGS...'}

function init(){applyPhotos();bindBest();patchAdd();bindPix();fixSuccess();setTimeout(()=>{applyPhotos();bindBest();patchAdd();bindPix();fixSuccess()},800)}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init);else init();
})();
</script>


<script id="nd-r17-conversion-js">
(function(){
'use strict';
const R17_KEY='ndburgs_r17_favorites';
const R17_LAST='ndburgs_r17_last_order';
const money=n=>Number(n||0).toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
const norm=v=>String(v||'').toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,' ').trim();
const qs=s=>document.querySelector(s), qsa=s=>Array.from(document.querySelectorAll(s));

function getFavs(){try{const a=JSON.parse(localStorage.getItem(R17_KEY)||'[]');return Array.isArray(a)?a:[]}catch(_){return[]}}
function setFavs(a){try{localStorage.setItem(R17_KEY,JSON.stringify(a))}catch(_){}}
function getLast(){try{const a=JSON.parse(localStorage.getItem(R17_LAST)||'[]');return Array.isArray(a)?a:[]}catch(_){return[]}}

function isOpenNow(){
  const d=new Date(), day=d.getDay(), mins=d.getHours()*60+d.getMinutes();
  if(day===1)return false; // segunda fechada
  return mins>=18*60 || mins<=30; // 18:00 até 00:30
}
function nextOpening(){
  const d=new Date(), day=d.getDay(), mins=d.getHours()*60+d.getMinutes();
  if(day===1 || (mins>30 && mins<18*60)){
    let days=0;
    if(day===1) days=1;
    else if(mins>30) days=(day===0?2:1);
    const names=['DOMINGO','SEGUNDA','TERÇA','QUARTA','QUINTA','SEXTA','SÁBADO'];
    return 'Próximo atendimento: '+names[(day+days)%7]+' às 18:00.';
  }
  return 'Pedidos disponíveis agora.';
}
function updateHours(){
  const open=isOpenNow();
  const title=qs('.horarios-titulo'), line=qs('.horarios-linha'), status=qs('#statusHorario');
  if(title)title.textContent=open?'🟢 PEDIDOS ABERTOS':'🔴 PEDIDOS FECHADOS';
  if(line)line.innerHTML='📅 <b>TERÇA A DOMINGO</b> • 18:00 ÀS 00:30';
  if(status){
    status.className=open?'status-aberto':'status-fechado';
    status.textContent=open?'🟢 ESTAMOS ACEITANDO PEDIDOS • #BORADENDBURGS':'🔴 ESTAMOS FECHADOS • '+nextOpening();
  }
  const note=qs('#ndR17StatusNote');
  if(note)note.innerHTML=open?'🛵 <b>Delivery e retirada:</b> pedidos online liberados agora.':'⏰ <b>Atendimento fechado:</b> o site continua disponível para você montar seu pedido, mas o envio será liberado no horário de atendimento.';
}

function addStaticSections(){
  const hero=qs('.nd-v4-hero')||qs('#ndFxIntro');
  if(hero && !qs('#ndR17FirstBuy')){
    const s=document.createElement('section');s.id='ndR17FirstBuy';
    s.innerHTML='<div class="nd-r17-fb-kicker">🎁 PRODUTO ALEATÓRIO DO DIA</div>'+
      '<div class="nd-r17-fb-title">CASADINHO</div>'+
      '<div class="nd-r17-fb-text">Uma escolha diferente todos os dias para você descobrir um dos favoritos da <b>ND BURGS</b>.</div>'+
      '<div class="nd-r17-fb-row"><div class="nd-r17-fb-price">R$ 11,90</div><button class="nd-r17-fb-btn" type="button" id="ndR17FirstBuyBtn">🔥 QUERO O PRODUTO DE HOJE</button></div>'+
      '<div id="ndR17StatusNote"></div>';
    const dailyAnchor=document.querySelector('#sobremesas')||hero;
    dailyAnchor.insertAdjacentElement('afterend',s);
    qs('#ndR17FirstBuyBtn').onclick=()=>openBestSeller();
  }
  const first=qs('#ndR17FirstBuy');
  if(first && !qs('#ndR17Trust')){
    const t=document.createElement('section');t.id='ndR17Trust';
    t.innerHTML=
      '<div class="nd-r17-trust-card"><span class="nd-r17-trust-icon">🍔</span><strong>Monte seu pedido</strong><span>Escolha e personalize seus produtos.</span></div>'+
      '<div class="nd-r17-trust-card"><span class="nd-r17-trust-icon">🛵</span><strong>Delivery</strong><span>Consulte a taxa pela sua rua.</span></div>'+
      '<div class="nd-r17-trust-card"><span class="nd-r17-trust-icon">🏪</span><strong>Retirada</strong><span>Também dá para retirar o pedido.</span></div>'+
      '<div class="nd-r17-trust-card"><span class="nd-r17-trust-icon">📲</span><strong>WhatsApp</strong><span>Seu pedido é enviado direto para a loja.</span></div>';
    first.insertAdjacentElement('afterend',t);
  }
}

function findBest(){
  return qsa('.produto').find(c=>norm(c.querySelector('h3')?.textContent)==='COMBO MAIS VENDIDO');
}
function openBestSeller(){
  const c=findBest();
  if(!c)return;
  c.scrollIntoView({behavior:'smooth',block:'center'});
  const b=c.querySelector('.nd-fx-add,.btn-add');
  if(b){setTimeout(()=>b.click(),280)}
}
function markBest(){
  const c=findBest(); if(!c)return;
  if(!c.querySelector('.nd-r17-best-badge')){
    c.classList.add('nd-r17-best-card');
    const b=document.createElement('div');b.className='nd-r17-best-badge';b.textContent='🔥 MAIS VENDIDO';
    c.appendChild(b);
  }
}

function ensureHearts(){
  qsa('.produto').forEach(card=>{
    if(card.dataset.ndR17Heart==='1')return;
    const h3=card.querySelector('h3'); if(!h3)return;
    card.dataset.ndR17Heart='1';
    const name=h3.textContent.trim(), priceText=card.querySelector('.preco')?.textContent||'';
    const m=priceText.match(/R\$\s*([\d.]+,\d{2})/);
    const price=m?parseFloat(m[1].replace(/\./g,'').replace(',','.')):0;
    const btn=document.createElement('button');btn.type='button';btn.className='nd-r17-heart';btn.title='Adicionar aos favoritos';btn.setAttribute('aria-label','Favoritar '+name);
    btn.textContent=getFavs().some(x=>norm(x.nome)===norm(name))?'♥':'♡';
    if(btn.textContent==='♥')btn.classList.add('active');
    btn.onclick=e=>{
      e.stopPropagation();
      let a=getFavs(), i=a.findIndex(x=>norm(x.nome)===norm(name));
      if(i>=0){a.splice(i,1);btn.textContent='♡';btn.classList.remove('active')}
      else{a.push({nome:name,preco:price});btn.textContent='♥';btn.classList.add('active')}
      setFavs(a);renderFavorites();
    };
    card.appendChild(btn);
  });
}
function clickProduct(name){
  const card=qsa('.produto').find(c=>norm(c.querySelector('h3')?.textContent)===norm(name));
  if(!card)return;
  const b=card.querySelector('.nd-fx-add,.btn-add');
  if(b)b.click();
}
function renderFavorites(){
  let sec=qs('#ndR17FavSection');
  if(!sec){
    const anchor=qs('.container')||document.body;
    sec=document.createElement('section');sec.id='ndR17FavSection';
    anchor.insertBefore(sec,anchor.querySelector('.categoria')||anchor.firstChild);
  }
  const a=getFavs();
  sec.innerHTML='<div class="nd-r17-section-head"><h2>❤️ MEUS FAVORITOS</h2><small>Salvos neste aparelho</small></div>'+
    (a.length?'<div class="nd-r17-fav-grid">'+a.map((x,i)=>'<div class="nd-r17-fav-item"><div><strong>'+safe(x.nome)+'</strong><span>'+money(x.preco)+'</span></div><button type="button" data-fav-index="'+i+'">ADICIONAR</button></div>').join('')+'</div>':'<div class="nd-r17-empty">Você ainda não favoritou nenhum produto. Toque no ♡ dos produtos para salvar seus preferidos.</div>');
  qsa('[data-fav-index]').forEach(b=>b.onclick=()=>{const x=getFavs()[Number(b.dataset.favIndex)];if(x)clickProduct(x.nome)});
}
function renderLast(){
  let sec=qs('#ndR17LastSection');
  if(!sec){
    const fav=qs('#ndR17FavSection'), container=qs('.container');
    if(!container)return;
    sec=document.createElement('section');sec.id='ndR17LastSection';
    container.insertBefore(sec,fav?.nextSibling||container.querySelector('.categoria'));
  }
  const a=getLast();
  sec.innerHTML='<div class="nd-r17-section-head"><h2>🔄 PEDIR NOVAMENTE</h2><small>Seu último pedido neste aparelho</small></div>'+
    (a.length?'<div class="nd-r17-fav-grid">'+a.slice(0,8).map((x,i)=>'<div class="nd-r17-fav-item"><div><strong>'+safe(x.nome)+'</strong><span>'+money(x.preco)+' • '+(x.quantidade||1)+'x</span></div><button type="button" data-last-index="'+i+'">ADICIONAR</button></div>').join('')+'</div>':'<div class="nd-r17-empty">Seu último pedido aparecerá aqui depois de uma finalização.</div>');
  qsa('[data-last-index]').forEach(b=>b.onclick=()=>{const x=getLast()[Number(b.dataset.lastIndex)];if(x)for(let i=0;i<Math.max(1,Number(x.quantidade)||1);i++)clickProduct(x.nome)});
}
function safe(v){return String(v||'').replace(/[&<>"']/g,m=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[m]))}

function saveLastOrder(){
  try{
    const c=Array.isArray(window.carrinho)?window.carrinho:[];
    if(c.length)localStorage.setItem(R17_LAST,JSON.stringify(c.map(x=>({nome:x.nome,preco:Number(x.preco)||0,quantidade:Number(x.quantidade)||1}))));
  }catch(_){}
}
function patchFinish(){
  if(typeof window.finalizarPedidoModal!=='function'||window.finalizarPedidoModal.__ndR17)return;
  const old=window.finalizarPedidoModal;
  window.finalizarPedidoModal=function(){saveLastOrder();return old.apply(this,arguments)};
  window.finalizarPedidoModal.__ndR17=true;
}

function addBottomNav(){
  if(qs('#ndR17BottomNav'))return;
  const n=document.createElement('nav');n.id='ndR17BottomNav';n.setAttribute('aria-label','Navegação rápida');
  n.innerHTML='<button class="nd-r17-nav-btn" data-go="top"><b>🏠</b>INÍCIO</button>'+
    '<button class="nd-r17-nav-btn" data-go="search"><b>🔎</b>BUSCAR</button>'+
    '<button class="nd-r17-nav-btn" data-go="fav"><b>❤️</b>FAVORITOS</button>'+
    '<button class="nd-r17-nav-btn" data-go="cart"><b>🛒</b>CARRINHO</button>';
  document.body.appendChild(n);
  qsa('#ndR17BottomNav .nd-r17-nav-btn').forEach(b=>b.onclick=()=>{
    const g=b.dataset.go;
    if(g==='top')window.scrollTo({top:0,behavior:'smooth'});
    if(g==='search')qs('#buscaProdutos')?.focus();
    if(g==='fav')qs('#ndR17FavSection')?.scrollIntoView({behavior:'smooth',block:'start'});
    if(g==='cart'&&typeof window.abrirCarrinho==='function')window.abrirCarrinho();
  });
}

function init(){
  addStaticSections();
  updateHours();
  ensureHearts();
  markBest();
  renderFavorites();
  renderLast();
  addBottomNav();
  patchFinish();
  setTimeout(()=>{addStaticSections();updateHours();ensureHearts();markBest();renderFavorites();renderLast();addBottomNav();patchFinish()},900);
}
if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init);else init();
setInterval(updateHours,30000);
})();
</script>



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


<!-- =========================================================
     ND BURGS R21 — PRODUTO  DO DIA + MOBILE TURBO
     ========================================================= -->



<style id="nd-r22-uva-premium">
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
</style>

<!-- =========================================================
     ND BURGS R24 — POSICIONAMENTO FINAL + MELHORIAS COMPLETAS
     ========================================================= -->
<style id="nd-r24-final-upgrades">
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
</style>
<script id="nd-r24-final-logic">
(function(){
'use strict';

function q(s){return document.querySelector(s)}
function qa(s){return Array.from(document.querySelectorAll(s))}
function norm(v){return String(v||'').toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,' ').trim()}

/* 1) FORÇA AS DUAS PROMOÇÕES PARA OS LUGARES EXATOS */
function placeHighlights(){
  const artes=q('#artesanais');
  const promo=q('#ndUvaPromo');
  if(artes && promo){
    artes.insertAdjacentElement('afterend',promo);
    promo.classList.add('nd-r24-uva');
  }

  const sobrem=q('#sobremesas');
  const daily=q('#ndR17FirstBuy');
  if(!sobrem || !daily)return;

  const grid=sobrem.querySelector('.produtos');
  if(!grid)return;

  /* encontra o ÚLTIMO milkshake: os cards possuem alt começando por MILKSHAKE
     ou nomes conhecidos da linha de milkshakes */
  const milkNames=['OVOMALTINE','OREO','PAÇOCA','NESQUIK','LEITE NINHO','DE AÇAÍ'];
  const cards=Array.from(grid.querySelectorAll('.produto'));
  let milkCards=cards.filter(c=>{
    const alt=(c.querySelector('img')?.getAttribute('alt')||'').toUpperCase();
    const name=norm(c.querySelector('h3')?.textContent);
    return alt.includes('MILKSHAKE') || milkNames.includes(name);
  });
  let lastMilk=milkCards[milkCards.length-1];

  if(lastMilk){
    grid.appendChild(daily);
    lastMilk.insertAdjacentElement('afterend',daily);
  }else{
    grid.appendChild(daily);
  }
  daily.classList.add('nd-r24-daily');
}

/* 2) ORGANIZA A CATEGORIA UNIFICADA EM AÇAÍ / MILKSHAKES / SOBREMESAS */
function addSubgroups(){
  const grid=q('#sobremesas .produtos');
  if(!grid || grid.dataset.r24Groups==='1')return;
  const cards=Array.from(grid.children).filter(x=>x.classList.contains('produto'));
  if(!cards.length)return;

  const title=c=>norm(c.querySelector('h3')?.textContent);
  const insert=(beforeCard,text,sub)=>{
    if(!beforeCard)return;
    const el=document.createElement('div');
    el.className='nd-r24-subtitulo';
    el.innerHTML=text+(sub?'<small>'+sub+'</small>':'');
    grid.insertBefore(el,beforeCard);
  };

  const acai=cards.find(c=>['AÇAÍ','CASADINHO','AÇAÍ TRUFFADO','TENTAÇÃO DE MORANGO','CREME DE CUPUAÇU'].includes(title(c)));
  const milk=cards.find(c=>['OVOMALTINE','OREO','PAÇOCA','NESQUIK','LEITE NINHO','DE AÇAÍ'].includes(title(c)));
  const sweets=cards.find(c=>['KITKAT','SURPRESA DE UVA'].includes(title(c)));

  insert(acai,'🍧 AÇAÍS E CREMES','Monte seu tamanho e escolha seus acompanhamentos.');
  insert(milk,'🥤 MILKSHAKES','Escolha seu sabor favorito.');
  insert(sweets,'🍫 SOBREMESAS','Doces para completar o pedido.');

  grid.dataset.r24Groups='1';
}

/* 3) DEIXA O CTA DA PROMOÇÃO COM BADGE */
function promoBadge(){
  const p=q('#ndUvaPromo');
  if(p && !p.querySelector('.nd-r24-badge')){
    const b=document.createElement('div');
    b.className='nd-r24-badge';
    b.textContent='🔥 OFERTA EXCLUSIVA';
    p.appendChild(b);
  }
}

/* 4) FEEDBACK VISUAL AO ADICIONAR */
function addFeedback(){
  if(q('.nd-r24-added'))return;
  const el=document.createElement('div');
  el.className='nd-r24-added';
  el.id='ndR24Added';
  el.textContent='✓ ADICIONADO AO CARRINHO';
  document.body.appendChild(el);

  document.addEventListener('click',function(e){
    const b=e.target.closest('.btn-add,.nd-fx-add,#ndR17FirstBuyBtn,#ndUvaPromo button');
    if(!b)return;
    setTimeout(()=>{
      el.classList.add('show');
      clearTimeout(el._t);
      el._t=setTimeout(()=>el.classList.remove('show'),1300);
    },80);
  },true);
}

/* 5) BOTÕES DOS PRODUTOS MAIS CLAROS */
function improveButtons(){
  qa('.produto .btn-add,.produto .nd-fx-add').forEach(b=>{
    b.classList.add('nd-r24-quick-buy');
    if(!b.dataset.r24Label){
      const txt=norm(b.textContent);
      if(txt==='ADICIONAR') b.setAttribute('aria-label','Adicionar produto ao carrinho');
      else b.setAttribute('aria-label','Escolher e adicionar produto ao carrinho');
      b.dataset.r24Label='1';
    }
  });
}

/* 6) BUSCA: estado vazio mais claro */
function improveSearch(){
  const input=q('#buscaProdutos');
  if(!input || input.dataset.r24==='1')return;
  input.dataset.r24='1';
  const empty=document.createElement('div');
  empty.className='nd-r24-search-empty';
  empty.id='ndR24SearchEmpty';
  empty.innerHTML='<strong>NÃO ENCONTRAMOS ESSE PRODUTO</strong><br><small>Tente outro nome ou escolha uma categoria acima.</small>';
  input.closest('.modern-search')?.insertAdjacentElement('afterend',empty);

  input.addEventListener('input',()=>{
    const value=norm(input.value);
    if(!value){empty.style.display='none';return}
    const visible=qa('.produto').some(c=>c.style.display!=='none'&&!c.classList.contains('search-hidden'));
    empty.style.display=visible?'none':'block';
  });
}

/* 7) META/SEO básico sem alterar o conteúdo do catálogo */
function seo(){
  if(!q('meta[name="description"]')){
    const m=document.createElement('meta');
    m.name='description';
    m.content='ND BURGS — peça hambúrgueres, combos, porções, pastéis, açaís, milkshakes, sobremesas e bebidas pelo site.';
    document.head.appendChild(m);
  }
}

/* 8) GARANTE UMA ÚNICA EXECUÇÃO SEGURA */
function init(){
  placeHighlights();
  addSubgroups();
  promoBadge();
  addFeedback();
  improveButtons();
  improveSearch();
  seo();
}
if(document.readyState==='loading'){
  document.addEventListener('DOMContentLoaded',()=>{init();setTimeout(init,500);setTimeout(init,1400)});
}else{
  init();setTimeout(init,500);setTimeout(init,1400);
}
})();
</script>

<style id="nd-final-user-changes">
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
</style>

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
<style id="nd-r26-final">
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
</style>
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
<style id="nd-r27-pix-security">
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
</style>

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

<style id="nd-clean-final-ui">
html{scroll-behavior:auto!important;overflow-x:hidden}body{overflow-x:hidden}header{position:relative!important;display:flex;flex-direction:column;align-items:center;gap:10px;padding:10px 12px 14px!important;z-index:30000!important;background:#05070a!important;border-bottom:1px solid rgba(65,150,255,.28)!important;box-shadow:0 10px 35px rgba(0,0,0,.55)!important}header .logo{order:2!important;width:132px!important;max-width:46vw!important;margin:2px auto 0!important}.nd-top-info{order:1;width:min(900px,100%);display:grid;grid-template-columns:1fr 1fr;gap:10px}.nd-top-card{position:relative;overflow:hidden;min-height:94px;padding:13px 14px;border:1px solid rgba(91,167,255,.42);border-radius:16px;background:linear-gradient(145deg,#030405,#0b0f15 58%,#030405);box-shadow:inset 0 1px 0 rgba(255,255,255,.08),inset 0 -18px 35px rgba(0,71,150,.10),0 9px 24px rgba(0,0,0,.55),0 0 22px rgba(28,112,255,.10);text-align:center}.nd-top-card:before{content:"";position:absolute;left:-35%;top:-70%;width:42%;height:240%;transform:rotate(18deg);background:linear-gradient(90deg,transparent,rgba(77,160,255,.20),rgba(255,255,255,.14),transparent);animation:ndTopReflect 4.8s linear infinite;pointer-events:none}.nd-top-card:after{content:"";position:absolute;left:8%;right:8%;bottom:0;height:1px;background:linear-gradient(90deg,transparent,#2d91ff,#b9ddff,#2d91ff,transparent);box-shadow:0 0 12px rgba(45,145,255,.7)}@keyframes ndTopReflect{0%{left:-35%}55%,100%{left:135%}}.nd-top-label{position:relative;z-index:1;display:block;color:#fff;font-size:10px;font-weight:1000;letter-spacing:1.4px}.nd-top-card strong{position:relative;z-index:1;display:block;margin:5px 0 3px;color:#fff;font-size:22px;line-height:1;text-shadow:0 2px 0 #000,0 0 13px rgba(78,160,255,.28)}.nd-top-card small{position:relative;z-index:1;display:block;color:#bfc6d1;font-size:9px;letter-spacing:.3px}.nd-top-status{position:relative;z-index:1;display:inline-block;margin-top:7px;padding:4px 8px;border-radius:999px;color:#fff;background:rgba(37,211,102,.10);border:1px solid rgba(37,211,102,.28);font-size:9px;font-weight:900}.nd-top-status.closed{background:rgba(255,59,48,.10);border-color:rgba(255,59,48,.3);color:#ffaaa6}.nd-delivery-status{background:rgba(45,145,255,.10);border-color:rgba(45,145,255,.28);color:#dcecff}
#ndCleanRandom,#ndCleanUpsell{width:min(1180px,calc(100% - 28px));margin:18px auto;padding:16px;border:1px solid rgba(77,145,255,.20);border-radius:20px;background:linear-gradient(145deg,#0d0f12,#08090b);box-shadow:0 12px 35px rgba(0,0,0,.35)}.nd-clean-head{display:flex;align-items:end;justify-content:space-between;gap:10px;margin-bottom:12px}.nd-clean-head h2{margin:0!important;border:0!important;padding:0!important;color:#fff!important;font-size:22px!important}.nd-clean-head p{margin:0;color:#858b95;font-size:10px;text-align:right}.nd-clean-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:10px}.nd-clean-card{display:grid;grid-template-columns:74px 1fr auto;gap:10px;align-items:center;padding:9px;border:1px solid rgba(255,255,255,.08);border-radius:14px;background:#0b0c0f;min-width:0}.nd-clean-card img{width:74px;height:74px;object-fit:cover;border-radius:10px;background:#050505}.nd-clean-card strong{display:block;color:#fff;font-size:12px}.nd-clean-card small{display:block;color:#8f96a0;font-size:9px;margin-top:4px;line-height:1.35}.nd-clean-price{display:block;color:#fff;font-weight:1000;font-size:13px;margin-top:4px}.nd-clean-card button{border:0;border-radius:9px;background:linear-gradient(135deg,#1677ff,#39a0ff);color:#fff;font-weight:1000;font-size:10px;padding:10px 9px;cursor:pointer;min-height:42px}.nd-clean-tag{display:inline-block;margin-bottom:5px;padding:3px 6px;border-radius:999px;background:rgba(45,145,255,.10);border:1px solid rgba(45,145,255,.22);color:#9acaff;font-size:8px;font-weight:1000}
@media(max-width:700px){.nd-top-info{gap:7px}.nd-top-card{min-height:92px;padding:11px 7px}.nd-top-card strong{font-size:17px}.nd-top-label{font-size:8px;letter-spacing:.8px}.nd-top-card small{font-size:7.5px}.nd-top-status{font-size:8px;padding:4px 6px}.nd-clean-grid{display:flex;overflow-x:auto;scroll-snap-type:x proximity;padding-bottom:3px}.nd-clean-card{min-width:285px;scroll-snap-align:start}.nd-clean-head{display:block}.nd-clean-head p{text-align:left;margin-top:4px}}@media(prefers-reduced-motion:reduce){.nd-top-card:before{animation:none}}
</style>
<script id="nd-clean-final-logic">
(function(){'use strict';const $=s=>document.querySelector(s),$$=s=>Array.from(document.querySelectorAll(s));const norm=v=>String(v||'').toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,' ').trim();const money=v=>Number(v||0).toLocaleString('pt-BR',{style:'currency',currency:'BRL'});function safe(v){return String(v||'').replace(/[&<>"']/g,m=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[m]))}function cards(){return $$('.produto').map(card=>{const h=card.querySelector('h3'),p=card.querySelector('.preco'),img=card.querySelector('img'),btn=card.querySelector('.btn-add');if(!h||!p||!btn)return null;const m=p.textContent.match(/R\$\s*([\d.]+,[\d]{2})/);return {name:h.textContent.trim(),price:m?Number(m[1].replace(/\./g,'').replace(',','.')):0,img:img?.src||'',btn,cat:card.closest('.categoria')?.id||''}}).filter(Boolean)}function cartNames(){try{return (Array.isArray(window.carrinho)?window.carrinho:[]).map(x=>norm(x.nome||x.name))}catch(_){return []}}function has(re){return cartNames().some(n=>re.test(n))}function score(x){const n=norm(x.name);let s=Math.random()*2;if(has(/BURGUER|X-|NUNES|PATAO|BERENICE|GADEIA|GAROTINHO|DINA|PEZAO/)){if(/COCA|FANTA|SPRITE|GUARANA|DOLLY|DELL VALE/.test(n))s+=9;if(/BACON|CHEDDAR|QUEIJO/.test(n))s+=6;if(/KITKAT|SURPRESA DE UVA/.test(n))s+=5}if(has(/COMBO/)){if(/SURPRESA DE UVA|KITKAT/.test(n))s+=10;if(/COCA|FANTA|SPRITE|GUARANA|DOLLY/.test(n))s+=8}if(has(/ACAI|AÇAÍ|MILKSHAKE|CUPUACU|CUPUA|TRUFFADO|TENTACAO|TENTAÇÃO/)&&/KITKAT|SURPRESA DE UVA/.test(n))s+=10;if(has(/PASTEL/)){if(/COCA|FANTA|SPRITE|GUARANA|DOLLY/.test(n))s+=9;if(/SURPRESA DE UVA|KITKAT/.test(n))s+=6}return s}function section(id,title,desc,after){let e=$('#'+id);if(e)return e;e=document.createElement('section');e.id=id;e.innerHTML='<div class="nd-clean-head"><h2>'+title+'</h2><p>'+desc+'</p></div><div class="nd-clean-grid"></div>';after.insertAdjacentElement('afterend',e);return e}function direct(x){try{window.adicionar(x.name,x.price);return true}catch(_){return false}}function renderRandom(){const anchor=$('#ndAutoBest')||$('header');if(!anchor)return;const e=section('ndCleanRandom','🎲 PRODUTOS ALEATÓRIOS','Lanches, combos e sobremesas para variar o pedido.',anchor),g=e.querySelector('.nd-clean-grid'),all=cards().filter(x=>x.img&&x.cat!=='adicionais');if(!all.length)return;let pool=all.filter(x=>!cartNames().includes(norm(x.name)));if(pool.length<6)pool=all.slice();pool.sort(()=>Math.random()-.5);const picks=[];['combos','tradicionais','artesanais','sobremesas'].forEach(cat=>{const x=pool.find(y=>y.cat===cat&&!picks.includes(y));if(x)picks.push(x)});pool.forEach(x=>{if(picks.length<6&&!picks.includes(x))picks.push(x)});g.innerHTML=picks.slice(0,6).map((x,i)=>'<article class="nd-clean-card"><img loading="lazy" src="'+safe(x.img)+'" alt="'+safe(x.name)+'"><div><span class="nd-clean-tag">'+safe(x.cat==='combos'?'COMBO':x.cat==='sobremesas'?'SOBREMESA':x.cat==='artesanais'?'ARTESANAL':'LANCHE')+'</span><strong>'+safe(x.name)+'</strong><span class="nd-clean-price">'+money(x.price)+'</span><small>Uma escolha diferente para hoje.</small></div><button type="button" data-random="'+i+'">ADICIONAR</button></article>').join('');g.querySelectorAll('[data-random]').forEach((b,i)=>b.onclick=()=>{const x=picks[i];if(!x)return;try{x.btn.click()}catch(_){direct(x)};setTimeout(renderUpsell,150)})}function renderUpsell(){const anchor=$('#ndCleanRandom')||$('#ndAutoBest')||$('header');if(!anchor)return;const e=section('ndCleanUpsell','🛒 COMPLEMENTE SEU PEDIDO','Sugestões escolhidas de acordo com o que já está no carrinho.',anchor),g=e.querySelector('.nd-clean-grid'),names=new Set(cartNames());const items=cards().filter(x=>x.img&&x.price>0&&!names.has(norm(x.name))&&!x.btn.getAttribute('onclick')?.includes('abrirPersonalizacao')&&!x.btn.getAttribute('onclick')?.includes('abrirComboPersonalizacao')).sort((a,b)=>score(b)-score(a)).slice(0,4);if(!items.length){e.style.display='none';return}e.style.display='block';g.innerHTML=items.map((x,i)=>'<article class="nd-clean-card"><img loading="lazy" src="'+safe(x.img)+'" alt="'+safe(x.name)+'"><div><span class="nd-clean-tag">COMPLEMENTO</span><strong>'+safe(x.name)+'</strong><span class="nd-clean-price">'+money(x.price)+'</span><small>1 unidade • vai direto para o carrinho.</small></div><button type="button" data-upsell="'+i+'">+ ADICIONAR</button></article>').join('');g.querySelectorAll('[data-upsell]').forEach((b,i)=>b.onclick=()=>{const x=items[i];if(!x)return;direct(x);b.textContent='✓ ADICIONADO';b.disabled=true;setTimeout(renderUpsell,220)})}function updateHours(){const st=$('#statusHorario');if(!st)return;const d=new Date(),day=d.getDay(),m=d.getHours()*60+d.getMinutes();const open=(day>=2&&day<=6&&m>=1080)||(day===0&&m>=1080&&m<30);if(open){st.textContent='● ABERTO AGORA';st.classList.remove('closed')}else{st.textContent=day===1?'● FECHADO • SEGUNDA':'● FECHADO • 18:00–00:30';st.classList.add('closed')}}function init(){updateHours();renderRandom();renderUpsell();setTimeout(()=>{renderRandom();renderUpsell();updateHours()},800)}window.addEventListener('DOMContentLoaded',init,{once:true});const old=window.atualizarCarrinho;if(typeof old==='function'&&!old.__ndClean){window.atualizarCarrinho=function(){const r=old.apply(this,arguments);setTimeout(renderUpsell,0);return r};window.atualizarCarrinho.__ndClean=true}setInterval(updateHours,60000)})();
</script>


</body>

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
<style id="nd-r28-final-fixes">
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
</style>

<script id="nd-r28-final-logic">
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
</script>

</html>
