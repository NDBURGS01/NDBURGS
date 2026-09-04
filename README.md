<html lang="pt-BR">
<head>
<!-- ND BURGS: controle de versão para evitar conteúdo antigo em cache -->
<meta name="nd-site-version" content="20260904-R9">
<script>
(function () {
  const ND_SITE_VERSION = "20260904-R9";
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

<style id="nd-r9-cart-upgrade">
/* ND BURGS R9 — carrinho único com ícone e contador */
.nd-cart-fab{position:fixed;right:18px;bottom:18px;z-index:120000;width:64px;height:64px;border:0;border-radius:50%;cursor:pointer;background:linear-gradient(135deg,#e50914,#ff3038);color:#fff;box-shadow:0 14px 40px rgba(229,9,20,.38);display:flex;align-items:center;justify-content:center;font-size:28px;transition:transform .2s,box-shadow .2s}.nd-cart-fab:hover{transform:translateY(-3px) scale(1.03);box-shadow:0 20px 50px rgba(229,9,20,.5)}.nd-cart-badge{position:absolute;right:-5px;top:-5px;min-width:25px;height:25px;padding:0 6px;border-radius:999px;background:#fff;color:#111;border:3px solid #111;display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:950}.nd-cart-fab.empty{opacity:.88}.nd-cart-fab.empty .nd-cart-badge{background:#27272b;color:#aaa}.nd-cart-label{position:fixed;right:16px;bottom:90px;z-index:119999;background:#151519;border:1px solid #303038;border-radius:999px;padding:8px 12px;color:#fff;font-size:11px;font-weight:900;box-shadow:0 8px 25px rgba(0,0,0,.35)}.carrinho-flutuante,#ndFxCartbar,.nd-v3-buybar{display:none!important}.painel-carrinho{border-radius:24px 24px 0 0!important}.cabecalho-carrinho h2{font-size:24px!important}.nd-cart-countline{font-size:12px;color:#999;margin-top:3px}.nd-cart-empty-tip{margin-top:8px;color:#888;font-size:12px}@media(max-width:600px){.nd-cart-fab{width:60px;height:60px;right:14px;bottom:14px;font-size:26px}.nd-cart-label{right:12px;bottom:82px;font-size:10px}}
</style>
<script id="nd-r9-cart-upgrade-script">
(function(){
'use strict';
function getCart(){try{return Array.isArray(window.carrinho)?window.carrinho:(typeof carrinho!=='undefined'&&Array.isArray(carrinho)?carrinho:[])}catch(e){return []}}
function qty(){return getCart().reduce((s,i)=>s+(Number(i.quantidade)||0),0)}
function money(v){return Number(v||0).toLocaleString('pt-BR',{style:'currency',currency:'BRL'})}
function total(){return getCart().reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||0),0)}
function update(){const q=qty(),b=document.getElementById('ndCartBadge'),f=document.getElementById('ndCartFab'),l=document.getElementById('ndCartLabel');if(b)b.textContent=q;if(f)f.classList.toggle('empty',q===0);if(l)l.textContent=q?`${q} ${q===1?'item':'itens'} • ${money(total())}`:'Seu carrinho está vazio'}
}
function build(){if(document.getElementById('ndCartFab'))return;const f=document.createElement('button');f.type='button';f.id='ndCartFab';f.className='nd-cart-fab empty';f.setAttribute('aria-label','Abrir carrinho');f.innerHTML='🛒<span id="ndCartBadge" class="nd-cart-badge">0</span>';f.onclick=function(){if(typeof window.abrirCarrinho==='function'){window.abrirCarrinho();setTimeout(()=>{const m=document.getElementById('modalCarrinho');if(m&&!m.classList.contains('ativo')&&typeof window.atualizarModalCarrinho==='function'){window.atualizarModalCarrinho();m.classList.add('ativo');document.body.style.overflow='hidden'}},0)}};document.body.appendChild(f);const l=document.createElement('div');l.id='ndCartLabel';l.className='nd-cart-label';l.textContent='Seu carrinho está vazio';document.body.appendChild(l);update()}
function patch(){if(typeof window.atualizarCarrinho==='function'&&!window.atualizarCarrinho.__r9cart){const old=window.atualizarCarrinho;window.atualizarCarrinho=function(){const r=old.apply(this,arguments);setTimeout(update,0);return r};window.atualizarCarrinho.__r9cart=true}if(typeof window.abrirCarrinho==='function'&&!window.abrirCarrinho.__r9cart){const old=window.abrirCarrinho;window.abrirCarrinho=function(){if(getCart().length===0){if(typeof window.atualizarModalCarrinho==='function')window.atualizarModalCarrinho();const m=document.getElementById('modalCarrinho');if(m){m.classList.add('ativo');document.body.style.overflow='hidden'}return}return old.apply(this,arguments)};window.abrirCarrinho.__r9cart=true}}
window.addEventListener('DOMContentLoaded',()=>{build();patch();update();setInterval(()=>{patch();update()},700)});
})();
</script>

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
<p>Hambúrguer tradicional.</p>
<div class="preco">R$ 10,90</div>
<button class="btn btn-add" onclick="adicionar('X-BURGUER',10.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/k2KQwpjp/BACON.jpg" alt="X-BACON">
<h3>X-BACON</h3>
<p>Hambúrguer tradicional com bacon.</p>
<div class="preco">R$ 11,90</div>
<button class="btn btn-add" onclick="adicionar('X-BACON',11.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/390n5BZv/SALADA.png" alt="X-SALADA">
<h3>X-SALADA</h3>
<p>Hambúrguer tradicional com salada.</p>
<div class="preco">R$ 11,90</div>
<button class="btn btn-add" onclick="adicionar('X-SALADA',11.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/NgWQv5Nm/EGG.png" alt="X-EGG">
<h3>X-EGG</h3>
<p>Hambúrguer tradicional com ovo.</p>
<div class="preco">R$ 11,90</div>
<button class="btn btn-add" onclick="adicionar('X-EGG',11.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/fGHQ9NrW/SELLIS.png" alt="SELLIS">
<h3>SELLIS</h3>
<p>Hambúrguer tradicional especial ND BURGS.</p>
<div class="preco">R$ 13,90</div>
<button class="btn btn-add" onclick="adicionar('SELLIS',13.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/Vszxw7h/NUNES.png" alt="NUNES">
<h3>NUNES</h3>
<p>Hambúrguer especial tradicional.</p>
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
<p>Pão de brioche, carne artesanal, cheddar, maionese verde, alface e cebola roxa.</p>
<div class="preco">R$ 22,90</div>
<button class="btn btn-add" onclick="adicionar('BERENICE',22.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/tTWqZ9ST/PATAO.png" alt="PATAO">
<h3>PATAO</h3>
<p>Pão de brioche, carne artesanal, bacon, barbecue e onion rings.</p>
<div class="preco">R$ 23,90</div>
<button class="btn btn-add" onclick="adicionar('PATAO',23.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/d4pD5bNc/DINA.jpg" alt="DINA">
<h3>DINA</h3>
<p>Pão de brioche, frango empanado, cheddar, maionese verde, alface e tomate.</p>
<div class="preco">R$ 20,90</div>
<button class="btn btn-add" onclick="adicionar('DINA',20.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/qLK7hWYs/GADEIA.jpg" alt="GADEIA">
<h3>GADEIA</h3>
<p>Pão de hambúrguer, carne artesanal, maionese verde e queijo cheddar.</p>
<div class="preco">R$ 20,90</div>
<button class="btn btn-add" onclick="adicionar('GADEIA',20.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/ymQ7sFZn/GAROTINHO.png" alt="GAROTINHO">
<h3>GAROTINHO</h3>
<p>Pão de brioche, carne artesanal, molho cheddar cremoso e bacon.</p>
<div class="preco">R$ 22,90</div>
<button class="btn btn-add" onclick="adicionar('GAROTINHO',22.90)">ADICIONAR</button>
</div>

<div class="produto">
<img class="produto-imagem" loading="lazy" decoding="async" src="https://i.ibb.co/0yTLwY4b/PEZAO.jpg" alt="PÉZÃO">
<h3>PÉZÃO</h3>
<p>Pão de brioche dividido em 3, 2 carnes artesanais, maionese, cheddar, ovo, cebola, bacon, alface e tomate.</p>
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
<h3>ADICIONAL NUTELLA</h3>
<p>Adicional.</p>
<div class="preco">R$ 5,00</div>
<button class="btn btn-add" onclick="adicionar('ADICIONAL NUTELLA',5)">ADICIONAR</button>
</div>

<div class="produto">
<h3>ADICIONAL CREME DE NINHO</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('ADICIONAL CREME DE NINHO',3)">ADICIONAR</button>
</div>

<div class="produto">
<h3>ADICIONAL KITKAT</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('ADICIONAL KITKAT',3)">ADICIONAR</button>
</div>

<div class="produto">
<h3>ACOMPANHAMENTO EXTRA</h3>
<p>Adicional.</p>
<div class="preco">R$ 3,00</div>
<button class="btn btn-add" onclick="adicionar('ACOMPANHAMENTO EXTRA',3)">ADICIONAR</button>
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

</script>


<!-- =========================
     ND BURGS — MELHORIAS PRO 2.0
========================= -->
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
</style>
<style id="nd-cleanup-navigation">#ndTopbar{display:none!important}</style>

<div id="ndToast" class="nd-toast" role="status" aria-live="polite"></div>
<button id="ndBackTop" class="nd-backtop" aria-label="Voltar ao topo">↑</button>
<div class="nd-topbar" id="ndTopbar">
  <div class="nd-topbar-inner" id="ndCategoryNav"></div>
</div>

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


<script id="nd-v3-logic">
(function(){
  const MIN=11.90;
  const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');
  function cart(){return typeof window.carrinho!=='undefined'?window.carrinho:[]}
  function total(){return cart().reduce((a,i)=>a+(Number(i.preco)||0)*(Number(i.quantidade)||1),0)}
  function qty(){return cart().reduce((a,i)=>a+(Number(i.quantidade)||1),0)}
  function add(name,price){if(typeof window.adicionar==='function')window.adicionar(name,price)}
  function createUI(){
    if(!document.querySelector('.nd-v3-progress')){const p=document.createElement('div');p.className='nd-v3-progress';p.innerHTML='<span></span>';document.body.prepend(p)}
    if(!document.querySelector('.nd-v3-strip')){const x=document.createElement('div');x.className='nd-v3-strip';x.innerHTML='🟢 <b>ND BURGS ABERTO 24 HORAS</b> • TODOS OS DIAS • PEÇA PELO SITE';document.body.prepend(x)}
    if(!document.querySelector('.nd-v3-buybar')){const b=document.createElement('div');b.className='nd-v3-buybar';b.innerHTML='<div class="nd-v3-buyinfo"><strong id="ndV3BuyTotal">R$ 0,00</strong><span id="ndV3BuyQty">Seu carrinho está vazio</span></div><button type="button" id="ndV3BuyBtn">VER CARRINHO 🛒</button>';document.body.appendChild(b);b.querySelector('#ndV3BuyBtn').onclick=()=>{if(typeof window.abrirCarrinho==='function')window.abrirCarrinho();else document.getElementById('carrinhoFlutuante')?.click()}}
    addTrust(); addLastOrder();
  }
  function addTrust(){if(document.querySelector('.nd-v3-trust'))return;const anchor=document.querySelector('.categoria-menu')||document.querySelector('.container');if(!anchor)return;const d=document.createElement('div');d.className='nd-v3-trust';d.innerHTML='<div>🔒<b>Compra fácil</b>Pedido direto pelo site</div><div>🏍️<b>Delivery</b>Taxa calculada por endereço</div><div>⚡<b>Rápido</b>Checkout simples pelo WhatsApp</div>';anchor.parentNode.insertBefore(d,anchor.nextSibling)}
  function addLastOrder(){
    if(document.querySelector('.nd-v3-last'))return;const raw=localStorage.getItem('ndburgs_ultimo_pedido');if(!raw)return;let arr;try{arr=JSON.parse(raw)}catch(e){return}if(!Array.isArray(arr)||!arr.length)return;const first=arr.slice(0,2).map(x=>x.nome).join(' + ');const d=document.createElement('div');d.className='nd-v3-last';d.innerHTML='<b>🔁 Seu último pedido</b><br><small style="color:#aaa">'+first+(arr.length>2?' e mais...':'')+'</small><button type="button">PEDIR DE NOVO</button>';d.querySelector('button').onclick=()=>{arr.forEach(x=>add(x.nome,x.preco));refresh()};const a=document.querySelector('.categoria-menu');if(a)a.parentNode.insertBefore(d,a);}
  function upsell(){
    const box=document.querySelector('#carrinhoItens,#itensCarrinhoModal');if(!box)return;
    const parent=box.closest('.modal-content,.modal,.painel-carrinho')||box.parentElement;if(!parent||parent.querySelector('.nd-v3-upsell'))return;
    const names=cart().map(x=>String(x.nome).toUpperCase()).join(' ');let options=[];
    document.querySelectorAll('.produto').forEach((c,i)=>{const n=c.querySelector('h3')?.textContent?.trim();const pr=c.querySelector('.preco')?.textContent?.match(/[\d]+[,.][\d]{2}/)?.[0];const btn=c.querySelector('.btn-add');if(n&&pr&&!names.includes(n.toUpperCase())&&btn&&options.length<4)options.push({n,p:parseFloat(pr.replace('.','').replace(',','.')),btn})});
    if(!options.length)return;const d=document.createElement('div');d.className='nd-v3-upsell';d.innerHTML='<h4>👀 Que tal completar seu pedido?</h4><div class="nd-v3-upsell-grid"></div>';const g=d.querySelector('div');options.forEach(o=>{const c=document.createElement('div');c.className='nd-v3-up';c.innerHTML='<strong>'+o.n+'</strong><small>'+money(o.p)+'</small><button type="button">ADICIONAR</button>';c.querySelector('button').onclick=()=>{o.btn.click();d.remove()};g.appendChild(c)});parent.insertBefore(d,box.nextSibling)
  }
  function refresh(){
    const t=total(),q=qty(),bar=document.querySelector('.nd-v3-buybar');if(bar){bar.classList.toggle('show',q>0);document.getElementById('ndV3BuyTotal').textContent=money(t);document.getElementById('ndV3BuyQty').textContent=q? q+' item(ns) • '+(t>=MIN?'pedido mínimo atingido':'faltam '+money(MIN-t)):'Seu carrinho está vazio'}
    const prog=document.querySelector('.nd-v3-progress span');if(prog)prog.style.width=Math.min(100,(window.scrollY/(document.documentElement.scrollHeight-window.innerHeight||1))*100)+'%';
    setTimeout(upsell,80);
  }
  const old=window.atualizarCarrinho;if(typeof old==='function'&&!old.__ndv3){window.atualizarCarrinho=function(){const r=old.apply(this,arguments);refresh();return r};window.atualizarCarrinho.__ndv3=true}
  window.addEventListener('scroll',refresh,{passive:true});
  document.addEventListener('click',e=>{if(e.target.closest('.btn-add'))setTimeout(refresh,100)});
  document.addEventListener('click',e=>{if(e.target.closest('#finalizarPedido,.btn-finalizar,button[onclick*="finalizarPedido"]')){try{localStorage.setItem('ndburgs_ultimo_pedido',JSON.stringify(cart()))}catch(_){} }});
  document.addEventListener('DOMContentLoaded',()=>{createUI();refresh();setTimeout(refresh,600)});
  setTimeout(()=>{createUI();refresh()},900);
})();
</script>

<style id="nd-v4">
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
</style>

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


<style id="nd-final-layout">
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
</style>


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


<style id="nd-rodada-3-sales">
/* ===== ND BURGS RODADA 3 — VENDAS + NAVEGAÇÃO ===== */
.nd-r3-quick{margin:18px auto 24px;max-width:1100px;padding:18px;border:1px solid rgba(255,59,48,.28);border-radius:22px;background:linear-gradient(145deg,rgba(255,59,48,.10),rgba(255,255,255,.025));box-shadow:0 16px 40px rgba(0,0,0,.28)}
.nd-r3-head{display:flex;align-items:flex-end;justify-content:space-between;gap:12px;margin-bottom:13px}.nd-r3-kicker{font-size:11px;font-weight:900;letter-spacing:1.7px;color:#ff5a52}.nd-r3-head h2{margin:3px 0 0;font-size:24px;border:0;padding:0}.nd-r3-head p{margin:0;color:#aaa;font-size:12px;text-align:right}
.nd-r3-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}.nd-r3-card{display:flex;align-items:center;gap:11px;padding:11px;border:1px solid rgba(255,255,255,.08);border-radius:16px;background:#101114;transition:.2s}.nd-r3-card:hover{transform:translateY(-2px);border-color:rgba(255,59,48,.65)}.nd-r3-card img{width:62px;height:62px;object-fit:cover;border-radius:12px;background:#08090a}.nd-r3-info{min-width:0;flex:1}.nd-r3-info strong{display:block;color:#fff;font-size:13px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}.nd-r3-info span{display:block;color:#f5c400;font-weight:900;font-size:13px;margin-top:3px}.nd-r3-add{border:0;border-radius:10px;background:linear-gradient(135deg,#e50914,#ff5a20);color:#fff;font-weight:900;font-size:11px;padding:10px 9px;cursor:pointer}.nd-r3-add:active{transform:scale(.96)}
.nd-r3-badge{position:absolute;top:10px;left:10px;z-index:2;padding:6px 8px;border-radius:8px;background:linear-gradient(135deg,#e50914,#ff5a20);color:#fff;font-size:9px;font-weight:1000;letter-spacing:.6px;box-shadow:0 5px 14px rgba(0,0,0,.35)}.produto{position:relative}
.nd-r3-added{animation:ndR3Pulse .48s ease}.nd-r3-btn-added{animation:ndR3Btn .5s ease}
@keyframes ndR3Pulse{0%{transform:scale(1)}45%{transform:scale(1.025)}100%{transform:scale(1)}}@keyframes ndR3Btn{0%{transform:scale(1)}45%{transform:scale(.92)}100%{transform:scale(1)}}
.nd-r3-upsell{position:fixed;left:50%;bottom:86px;transform:translate(-50%,20px);opacity:0;pointer-events:none;z-index:100004;width:min(680px,calc(100% - 24px));padding:12px;border:1px solid rgba(255,59,48,.5);border-radius:17px;background:rgba(14,14,17,.97);backdrop-filter:blur(15px);box-shadow:0 18px 50px rgba(0,0,0,.6);transition:.25s}.nd-r3-upsell.show{opacity:1;transform:translate(-50%,0);pointer-events:auto}.nd-r3-upsell-top{display:flex;justify-content:space-between;gap:10px;align-items:center}.nd-r3-upsell-top strong{font-size:13px;color:#fff}.nd-r3-upsell-top button{border:0;background:transparent;color:#888;font-size:18px;cursor:pointer}.nd-r3-upsell-items{display:flex;gap:8px;margin-top:9px}.nd-r3-upsell-items button{flex:1;border:1px solid #34343d;background:#17171c;color:#fff;border-radius:10px;padding:10px 7px;font-size:11px;font-weight:800;cursor:pointer}.nd-r3-upsell-items button b{color:#f5c400;display:block;margin-top:3px}
@media(max-width:700px){.nd-r3-quick{margin:14px 8px 20px;padding:14px;border-radius:18px}.nd-r3-head{align-items:flex-start;flex-direction:column}.nd-r3-head p{text-align:left}.nd-r3-grid{display:flex;overflow-x:auto;scroll-snap-type:x mandatory;padding-bottom:3px}.nd-r3-card{min-width:270px;scroll-snap-align:start}.nd-r3-upsell{bottom:78px}.nd-r3-upsell-items button{font-size:10px}}
@media(prefers-reduced-motion:reduce){.nd-r3-card,.nd-r3-added,.nd-r3-btn-added{animation:none!important;transition:none!important}}
</style>
<script id="nd-rodada-3-sales-js">
(function(){
 'use strict';
 const R3={
  picks:['COMBO MAIS VENDIDO','X-BACON','NUNES','GADEIA','BATATA','COCA COLA LATA'],
  badges:{'COMBO MAIS VENDIDO':'MAIS VENDIDO','X-BACON':'QUERIDINHO','NUNES':'DESTAQUE','PÉZÃO':'DESTAQUE','COMBO DOCE':'PROMOÇÃO','COMBO 5 ESTRELAS':'PROMOÇÃO','COMBO SÓ LOVE':'PROMOÇÃO'}
 };
 const q=s=>document.querySelector(s), qa=(s,c=document)=>Array.from(c.querySelectorAll(s));
 function money(n){return 'R$ '+Number(n).toFixed(2).replace('.',',')}
 function findCard(name){return qa('.produto').find(c=>(c.querySelector('h3')?.textContent||'').trim().toUpperCase()===name.toUpperCase())}
 function cardData(card){
  const img=card?.querySelector('img'); const h=card?.querySelector('h3'); const price=card?.querySelector('.preco'); const btn=card?.querySelector('.btn-add');
  if(!card||!h||!btn)return null;
  const onclick=btn.getAttribute('onclick')||''; const m=onclick.match(/adicionar\((['"])(.*?)\1\s*,\s*([0-9.]+)/);
  return {name:h.textContent.trim(),img:img?.src||'',priceText:price?.textContent.trim()||'',add:m?m[2]:h.textContent.trim(),value:m?m[3]:null,onclick};
 }
 function buildQuick(){
  if(q('#ndR3Quick'))return;
  const menu=q('.categoria-menu'); if(!menu)return;
  const section=document.createElement('section'); section.id='ndR3Quick'; section.className='nd-r3-quick';
  section.innerHTML='<div class="nd-r3-head"><div><div class="nd-r3-kicker">ESCOLHAS RÁPIDAS</div><h2>🔥 MAIS PEDIDOS</h2></div><p>Os favoritos para você montar o pedido sem perder tempo.</p></div><div class="nd-r3-grid" id="ndR3Grid"></div>';
  menu.parentNode.insertBefore(section,menu.nextSibling);
  const grid=q('#ndR3Grid');
  R3.picks.forEach(name=>{const d=cardData(findCard(name));if(!d)return;const el=document.createElement('div');el.className='nd-r3-card';el.innerHTML='<img loading="lazy" decoding="async" src="'+d.img+'" alt="'+d.name.replace(/"/g,'&quot;')+'"><div class="nd-r3-info"><strong>'+d.name+'</strong><span>'+d.priceText+'</span></div><button class="nd-r3-add" type="button">ADICIONAR</button>';el.querySelector('button').addEventListener('click',()=>{if(d.value&&typeof window.adicionar==='function')window.adicionar(d.add,Number(d.value));});grid.appendChild(el)});
 }
 function applyBadges(){
  qa('.produto').forEach(card=>{const name=(card.querySelector('h3')?.textContent||'').trim().toUpperCase();const label=R3.badges[name];if(!label)return;card.querySelectorAll('.nd-fx-bestseller').forEach(x=>x.style.display='none');if(card.querySelector('.nd-r3-badge'))return;const b=document.createElement('span');b.className='nd-r3-badge';b.textContent=label;card.appendChild(b)});
 }
 function buildUpsell(){
  if(q('#ndR3Upsell'))return;
  const u=document.createElement('div');u.id='ndR3Upsell';u.className='nd-r3-upsell';u.innerHTML='<div class="nd-r3-upsell-top"><strong>🔥 QUE TAL COMPLETAR SEU PEDIDO?</strong><button type="button" aria-label="Fechar">×</button></div><div class="nd-r3-upsell-items"><button type="button" data-add="COCA COLA LATA" data-price="6">🥤 COCA LATA<b>R$ 6,00</b></button><button type="button" data-add="SURPRESA DE UVA" data-price="12">🍇 SURPRESA DE UVA<b>R$ 12,00</b></button><button type="button" data-batata="1">🍟 BATATA<b>ESCOLHER</b></button></div>';
  document.body.appendChild(u);u.querySelector('button[aria-label="Fechar"]').onclick=()=>u.classList.remove('show');
  u.querySelectorAll('[data-add]').forEach(b=>b.onclick=()=>{if(typeof window.adicionar==='function')window.adicionar(b.dataset.add,Number(b.dataset.price));u.classList.remove('show')});
  const bat=u.querySelector('[data-batata]');if(bat)bat.onclick=()=>{if(typeof window.abrirPersonalizacao==='function')window.abrirPersonalizacao('batata');u.classList.remove('show')};
 }
 function showUpsell(){const u=q('#ndR3Upsell');if(!u)return;clearTimeout(window.__ndR3Timer);u.classList.add('show');window.__ndR3Timer=setTimeout(()=>u.classList.remove('show'),6500)}
 function patchAdd(){
  if(typeof window.adicionar!=='function'||window.adicionar.__ndR3)return;
  const old=window.adicionar;window.adicionar=function(nome,preco){const r=old.apply(this,arguments);qa('.produto').forEach(c=>{const h=(c.querySelector('h3')?.textContent||'').trim().toUpperCase();if(h===String(nome).trim().toUpperCase()){c.classList.remove('nd-r3-added');void c.offsetWidth;c.classList.add('nd-r3-added');const b=c.querySelector('.btn-add');if(b){b.classList.remove('nd-r3-btn-added');void b.offsetWidth;b.classList.add('nd-r3-btn-added')}}});showUpsell();return r};window.adicionar.__ndR3=true;
 }
 function init(){buildQuick();applyBadges();buildUpsell();patchAdd();setTimeout(()=>{buildQuick();applyBadges();patchAdd()},700)}
 if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init);else init();
 setTimeout(init,1200);
})();
</script>

<!-- =========================================================
     ND BURGS — RODADA 5
     EXPERIÊNCIA PREMIUM + PERFORMANCE
     Camada adicional sobre a RODADA 4 — não substitui funções existentes.
     ========================================================= -->
<style id="nd-rodada-5-premium-performance">
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
</style>

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
<style id="nd-rodada-7">
#ndR7Reco{display:none;margin:18px 0 8px;padding:15px;border:1px solid rgba(229,9,20,.28);border-radius:18px;background:linear-gradient(145deg,rgba(30,16,18,.96),rgba(13,13,15,.96));box-shadow:0 12px 35px rgba(0,0,0,.25)}
#ndR7Reco.show{display:block;animation:ndR7Up .24s ease both}
#ndR7RecoHead{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-bottom:10px}
#ndR7RecoHead strong{font-size:15px;color:#fff}#ndR7RecoHead span{font-size:10px;color:#999}
.nd-r7-grid{display:flex;gap:9px;overflow:auto;scrollbar-width:none}.nd-r7-grid::-webkit-scrollbar{display:none}
.nd-r7-card{flex:0 0 185px;display:flex;flex-direction:column;padding:10px;border:1px solid rgba(255,255,255,.08);border-radius:14px;background:rgba(255,255,255,.035)}
.nd-r7-card img{width:100%;height:92px;object-fit:contain;border-radius:10px;background:#09090b;margin-bottom:8px}.nd-r7-card b{font-size:12px;color:#fff}.nd-r7-card small{color:#aaa;font-size:10px;margin:3px 0 8px}.nd-r7-card button{border:0;border-radius:9px;padding:9px;background:#e50914;color:#fff;font-weight:900;cursor:pointer;min-height:40px}
#ndR7Recent{display:none;margin:12px 0;padding:11px 13px;border:1px solid rgba(255,255,255,.07);border-radius:14px;background:rgba(255,255,255,.025);color:#aaa;font-size:11px}
#ndR7Recent.show{display:flex;align-items:center;justify-content:space-between;gap:10px}.nd-r7-recent-name{color:#fff;font-weight:900}.nd-r7-recent-btn{border:0;background:#242529;color:#fff;border-radius:9px;padding:8px 10px;font-weight:900;cursor:pointer}
.nd-r7-pulse{animation:ndR7Pulse .42s ease}.nd-r7-added{border-color:rgba(37,211,102,.45)!important;box-shadow:0 0 0 2px rgba(37,211,102,.08),0 14px 35px rgba(0,0,0,.3)!important}
@keyframes ndR7Up{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:none}}@keyframes ndR7Pulse{50%{transform:scale(1.025)}}
@media(max-width:600px){#ndR7Reco{margin-left:0;margin-right:0}.nd-r7-card{flex-basis:165px}.nd-r7-card img{height:78px}}
@media(prefers-reduced-motion:reduce){#ndR7Reco{transition:none;animation:none}.nd-r7-pulse{animation:none}}
</style>
<script id="nd-rodada-7-logic">
(function(){'use strict';
 const q=s=>document.querySelector(s), qa=s=>[...document.querySelectorAll(s)];
 const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');
 function cart(){return Array.isArray(window.carrinho)?window.carrinho:[]}
 function total(){return cart().reduce((a,i)=>a+(Number(i.preco)||0)*(Number(i.quantidade)||1),0)}
 function getRecent(){try{return JSON.parse(localStorage.getItem('ndburgs_r7_recent')||'null')}catch(_){return null}}
 function setRecent(x){try{localStorage.setItem('ndburgs_r7_recent',JSON.stringify(x))}catch(_) {}}
 function add(name,price){if(typeof window.adicionar==='function'){window.adicionar(name,price);setRecent({name,price});renderRecent()}}
 function productData(){return qa('.produto').map(c=>{let h=c.querySelector('h3'),p=c.querySelector('p'),im=c.querySelector('img'),pr=c.querySelector('.preco');if(!h||!pr)return null;let b=c.querySelector('.btn-add');if(!b)return null;let onclick=b.getAttribute('onclick')||'';let m=onclick.match(/adicionar\(\s*[\'\"]([^\'\"]+)[\'\"]\s*,\s*([0-9.]+)/);if(!m)return null;return {name:m[1],price:Number(m[2]),desc:p?.textContent?.trim()||'',img:im?.src||'',el:c}}).filter(Boolean)}
 function buildReco(){if(q('#ndR7Reco'))return;let anchor=q('.categoria-menu')||q('.container');if(!anchor)return;let d=document.createElement('section');d.id='ndR7Reco';d.innerHTML='<div id="ndR7RecoHead"><strong>🔥 PODE COMBINAR COM SEU PEDIDO</strong><span>adicione em 1 toque</span></div><div class="nd-r7-grid"></div>';anchor.parentNode.insertBefore(d,anchor.nextSibling)}
 function renderReco(){let box=q('#ndR7Reco'),grid=q('#ndR7Reco .nd-r7-grid');if(!box||!grid)return;let items=productData();let names=new Set(cart().map(i=>String(i.nome||i.name||'').toUpperCase()));let keywords=cart().map(i=>String(i.nome||i.name||'').toUpperCase()).join(' ');
   let preferred=items.filter(x=>!names.has(x.name.toUpperCase())).sort((a,b)=>{let sa=/BATATA|PORÇÃO|FRANGO|NUGGET|ANEL/.test(a.name.toUpperCase())?3:0;let sb=/BATATA|PORÇÃO|FRANGO|NUGGET|ANEL/.test(b.name.toUpperCase())?3:0;if(/AÇAÍ|MILKSHAKE|SOBREMESA|DOCE|PASTEL|BEBIDA/.test(keywords))sa+=/AÇAÍ|MILKSHAKE|SOBREMESA|DOCE|PASTEL|BEBIDA/.test(a.name.toUpperCase())?2:0,sb+=/AÇAÍ|MILKSHAKE|SOBREMESA|DOCE|PASTEL|BEBIDA/.test(b.name.toUpperCase())?2:0;return sb-sa}).slice(0,5);
   if(!preferred.length){box.classList.remove('show');return} grid.innerHTML=preferred.map(x=>'<div class="nd-r7-card"><img loading="lazy" decoding="async" src="'+x.img+'" alt="'+x.name.replace(/"/g,'&quot;')+'"><b>'+x.name+'</b><small>'+money(x.price)+'</small><button type="button" data-r7-add="'+x.name.replace(/"/g,'&quot;')+'" data-r7-price="'+x.price+'">ADICIONAR</button></div>').join('');box.classList.add('show')}
 function renderRecent(){let r=getRecent(),box=q('#ndR7Recent');if(!box||!r)return;if(cart().some(i=>String(i.nome||i.name||'').toUpperCase()===String(r.name).toUpperCase())){box.classList.remove('show');return}box.innerHTML='<span>↩️ Última escolha: <span class="nd-r7-recent-name">'+r.name+'</span></span><button class="nd-r7-recent-btn" type="button">ADICIONAR '+money(r.price)+'</button>';box.querySelector('button').onclick=()=>add(r.name,r.price);box.classList.add('show')}
 function buildRecent(){if(q('#ndR7Recent'))return;let anchor=q('.modern-search')||q('.categoria-menu');if(!anchor)return;let d=document.createElement('div');d.id='ndR7Recent';anchor.parentNode.insertBefore(d,anchor.nextSibling)}
 function observeAdd(){document.addEventListener('click',e=>{let b=e.target.closest('[data-r7-add]');if(b){add(b.dataset.r7Add,Number(b.dataset.r7Price));renderReco();return}let orig=e.target.closest('.produto .btn-add');if(orig){let card=orig.closest('.produto');card?.classList.remove('nd-r7-pulse');void card?.offsetWidth;card?.classList.add('nd-r7-pulse');setTimeout(()=>{renderReco();renderRecent()},250)}})}
 function watchCart(){let last='';setInterval(()=>{let sig=JSON.stringify(cart().map(i=>[i.nome||i.name,i.quantidade,i.preco]));if(sig!==last){last=sig;renderReco();renderRecent()}},700)}
 function init(){buildReco();buildRecent();observeAdd();renderReco();renderRecent();watchCart()}
 if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init,{once:true});else init();
 setTimeout(()=>{buildReco();buildRecent();renderReco();renderRecent()},900);
})();
</script>


<!-- =========================================================
     ND BURGS — RODADA 8
     UX MOBILE + CHECKOUT SEM FRICÇÃO + PERFORMANCE
     Camada adicional. Preserva as rodadas anteriores.
     ========================================================= -->
<style id="nd-rodada-8">
#ndR8Top{position:fixed;right:16px;bottom:92px;z-index:100015;width:44px;height:44px;border:1px solid rgba(255,255,255,.12);border-radius:50%;background:rgba(18,18,20,.94);color:#fff;display:grid;place-items:center;font-size:18px;font-weight:900;box-shadow:0 10px 30px rgba(0,0,0,.35);opacity:0;transform:translateY(12px) scale(.9);pointer-events:none;transition:.22s ease;backdrop-filter:blur(12px)}
#ndR8Top.show{opacity:1;transform:none;pointer-events:auto}
#ndR8Top:active{transform:scale(.94)}
#ndR8Status{display:none;margin:10px 0;padding:10px 12px;border-radius:12px;background:rgba(37,211,102,.07);border:1px solid rgba(37,211,102,.2);font-size:11px;color:#dfffea;font-weight:800}
#ndR8Status.show{display:flex;align-items:center;gap:7px}
#ndR8Status i{width:8px;height:8px;border-radius:50%;background:#25d366;box-shadow:0 0 12px rgba(37,211,102,.7);flex:none}
.nd-r8-focus{outline:2px solid rgba(229,9,20,.8)!important;outline-offset:3px}
.nd-r8-added{animation:ndR8Added .45s ease}
@keyframes ndR8Added{0%{transform:scale(1)}45%{transform:scale(1.025)}100%{transform:scale(1)}}
@media(max-width:600px){#ndR8Top{right:12px;bottom:86px;width:42px;height:42px}.nd-r8-focus{outline-offset:2px}}
@media(prefers-reduced-motion:reduce){#ndR8Top{transition:none}.nd-r8-added{animation:none}}
</style>
<script id="nd-rodada-8-logic">
(function(){'use strict';
 const q=s=>document.querySelector(s), qa=s=>[...document.querySelectorAll(s)];
 function buildTop(){if(q('#ndR8Top'))return;let b=document.createElement('button');b.id='ndR8Top';b.type='button';b.setAttribute('aria-label','Voltar ao topo');b.textContent='↑';b.onclick=()=>window.scrollTo({top:0,behavior:'smooth'});document.body.appendChild(b)}
 function scrollTop(){let b=q('#ndR8Top');if(!b)return;b.classList.toggle('show',window.scrollY>500)}
 function optimize(){qa('img').forEach((im,i)=>{if(!im.getAttribute('decoding'))im.setAttribute('decoding','async');if(i>1&&!im.getAttribute('loading'))im.setAttribute('loading','lazy');if(!im.getAttribute('alt'))im.setAttribute('alt','ND BURGS')});qa('a[target="_blank"]').forEach(a=>a.setAttribute('rel','noopener noreferrer'))}
 function addStatus(){if(q('#ndR8Status'))return;let anchor=q('#ndR7Reco')||q('.categoria-menu');if(!anchor||!anchor.parentNode)return;let d=document.createElement('div');d.id='ndR8Status';d.innerHTML='<i></i><span>Pedido online disponível <b>24 horas por dia, todos os dias.</b></span>';anchor.parentNode.insertBefore(d,anchor.nextSibling)}
 function refreshStatus(){let d=q('#ndR8Status');if(!d)return;d.classList.add('show')}
 function improveButtons(){document.addEventListener('click',e=>{let b=e.target.closest('.btn-add');if(!b)return;let card=b.closest('.produto');if(card){card.classList.remove('nd-r8-added');void card.offsetWidth;card.classList.add('nd-r8-added')}} ,{passive:true})}
 function focusCheckout(){document.addEventListener('keydown',e=>{if(e.key!=='Escape')return;let modal=q('.modal-carrinho');if(modal){let close=modal.querySelector('[aria-label*="Fechar"],[aria-label*="fechar"],.fechar,.close,.btn-fechar');if(close)close.click()}})}
 function init(){buildTop();optimize();addStatus();refreshStatus();improveButtons();focusCheckout();scrollTop();window.addEventListener('scroll',scrollTop,{passive:true});setTimeout(optimize,1200)}
 if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init,{once:true});else init();
})();
</script>

<!-- =========================================================
     ND BURGS — RODADA 9
     CONVERSÃO MÁXIMA + CHECKOUT PREMIUM
     Camada adicional. Não substitui a lógica existente.
     ========================================================= -->
<style id="nd-rodada-9">
#ndR9Trust{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin:12px 0 4px}
.nd-r9-trust{padding:10px 8px;border:1px solid rgba(255,255,255,.08);border-radius:12px;background:rgba(255,255,255,.025);text-align:center;color:#aaa;font-size:10px;line-height:1.25}
.nd-r9-trust strong{display:block;color:#fff;font-size:11px;margin-bottom:3px}
#ndR9Ready{display:flex;align-items:center;gap:9px;margin:10px 0;padding:11px 12px;border-radius:13px;background:rgba(37,211,102,.055);border:1px solid rgba(37,211,102,.18);color:#dfffea;font-size:11px;line-height:1.35}
#ndR9Ready i{width:9px;height:9px;border-radius:50%;background:#25d366;box-shadow:0 0 12px rgba(37,211,102,.65);flex:none}
#ndR9TotalBox{margin-top:8px;padding:10px 12px;border-radius:12px;background:linear-gradient(135deg,rgba(255,106,0,.08),rgba(255,255,255,.025));border:1px solid rgba(255,106,0,.18);font-size:11px;color:#aaa}
#ndR9TotalBox b{color:#fff}
.nd-r9-error{animation:ndR9Shake .32s ease}
@keyframes ndR9Shake{25%{transform:translateX(-4px)}50%{transform:translateX(4px)}75%{transform:translateX(-2px)}}
@media(max-width:600px){#ndR9Trust{grid-template-columns:1fr 1fr 1fr;gap:5px}.nd-r9-trust{font-size:9px;padding:9px 4px}.nd-r9-trust strong{font-size:10px}}
@media(prefers-reduced-motion:reduce){.nd-r9-error{animation:none}}
</style>
<script id="nd-rodada-9-logic">
(function(){'use strict';
 const q=s=>document.querySelector(s), qa=s=>[...document.querySelectorAll(s)];
 function cart(){try{return Array.isArray(window.carrinho)?window.carrinho:[]}catch(e){return []}}
 function money(v){return 'R$ '+Number(v||0).toFixed(2).replace('.',',')}
 function subtotal(){return cart().reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||1),0)}
 function addTrust(){
   if(q('#ndR9Trust'))return;
   const panel=q('#modalFinalizar .painel-finalizar'); if(!panel)return;
   const d=document.createElement('div'); d.id='ndR9Trust';
   d.innerHTML='<div class="nd-r9-trust"><strong>🔒 SEGURO</strong>Dados usados no pedido</div><div class="nd-r9-trust"><strong>⚡ RÁPIDO</strong>Envio direto ao WhatsApp</div><div class="nd-r9-trust"><strong>🍔 DIRETO</strong>Pedido vai para a ND BURGS</div>';
   panel.appendChild(d);
 }
 function addReady(){
   const content=q('#modalFinalizar [data-content="4"]'); if(!content||q('#ndR9Ready'))return;
   const note=content.querySelector('.nd-v4-note'); if(!note)return;
   const d=document.createElement('div');d.id='ndR9Ready';d.innerHTML='<i></i><span><b>Seu pedido está pronto para ser enviado.</b><br>Confira os dados abaixo e toque no botão verde.</span>';
   note.parentNode.insertBefore(d,note);
 }
 function addTotalHint(){
   const content=q('#modalFinalizar [data-content="4"]');if(!content||q('#ndR9TotalBox'))return;
   const box=document.createElement('div');box.id='ndR9TotalBox';box.innerHTML='🧾 <b>Conferência final:</b> itens, taxa e total serão enviados juntos no WhatsApp.';
   const btn=content.querySelector('button[onclick*="finalizarPedidoModal"]');if(btn)btn.parentNode.insertBefore(box,btn);else content.appendChild(box);
 }
 function refresh(){addTrust();addReady();addTotalHint()}
 function maskPhone(inp){if(!inp||inp.dataset.ndR9Mask)return;inp.dataset.ndR9Mask='1';inp.addEventListener('input',()=>{let v=inp.value.replace(/\D/g,'').slice(0,11);if(v.length<=10){v=v.replace(/(\d{2})(\d{4})(\d{0,4})/,'($1) $2-$3')}else{v=v.replace(/(\d{2})(\d{5})(\d{0,4})/,'($1) $2-$3')}inp.value=v.replace(/-$/,'').replace(/ $/,'')})}
 function improvePhone(){maskPhone(q('#telefoneModal'))}
 function keyboard(){document.addEventListener('keydown',e=>{if(e.key!=='Enter'||e.shiftKey||e.ctrlKey||e.altKey)return;const t=e.target;if(t.tagName==='TEXTAREA')return;const next=t.closest('.nd-v4-step-content')?.querySelector('.nd-v4-next');if(next&&document.activeElement===t){e.preventDefault();next.click()}})}
 function animateValidation(){document.addEventListener('click',e=>{const b=e.target.closest('.nd-v4-next');if(!b)return;setTimeout(()=>{const active=q('#modalFinalizar .nd-v4-step-content.active');if(active&&!active.querySelector(':focus')){const bad=active.querySelector('input:invalid,select:invalid,textarea:invalid');if(bad){bad.classList.remove('nd-r9-error');void bad.offsetWidth;bad.classList.add('nd-r9-error')}}},80)})}
 function watch(){const mo=new MutationObserver(()=>{refresh();improvePhone()});const m=q('#modalFinalizar');if(m)mo.observe(m,{childList:true,subtree:true})}
 function init(){refresh();improvePhone();keyboard();animateValidation();watch();setTimeout(refresh,500);setTimeout(refresh,1500)}
 if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init,{once:true});else init();
})();
</script>
<!-- ND BURGS VERSION: 20260904-R9 -->


<!-- =========================================================
     ND BURGS — ETAPA 11
     INTELIGÊNCIA DE VENDAS + RETENÇÃO
     Camada adicional e independente.
     ========================================================= -->
<style id="nd-rodada-11">
#ndR11Box{display:none;position:fixed;left:14px;right:14px;bottom:calc(78px + env(safe-area-inset-bottom));z-index:9998;max-width:520px;margin:auto;padding:13px 14px;border:1px solid rgba(255,180,0,.28);border-radius:17px;background:linear-gradient(135deg,rgba(20,20,20,.98),rgba(42,28,8,.97));box-shadow:0 14px 45px rgba(0,0,0,.42);color:#fff}
#ndR11Box.show{display:block;animation:ndR11in .28s ease}
#ndR11Box .r11-head{display:flex;align-items:center;gap:9px}.r11-fire{font-size:20px}.r11-title{font-weight:900;font-size:13px}.r11-close{margin-left:auto;border:0;background:transparent;color:#aaa;font-size:20px;cursor:pointer}
#ndR11Box .r11-sub{font-size:10px;color:#aaa;margin:4px 0 9px 29px}
#ndR11Item{display:flex;align-items:center;gap:10px}.r11-name{font-weight:800;font-size:12px;flex:1}.r11-price{font-size:11px;color:#ffd15a;font-weight:900}.r11-add{border:0;border-radius:11px;padding:9px 12px;background:#ffd21a;color:#111;font-weight:900;font-size:11px;cursor:pointer}.r11-add:active{transform:scale(.97)}
#ndR11Mini{display:none;margin:8px 0 0;padding:9px 11px;border-radius:12px;background:rgba(255,210,26,.07);border:1px solid rgba(255,210,26,.16);font-size:10px;color:#bbb}#ndR11Mini b{color:#fff}
@keyframes ndR11in{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:none}}
@media(min-width:800px){#ndR11Box{left:auto;right:22px;bottom:22px;width:430px}}
@media(prefers-reduced-motion:reduce){#ndR11Box.show{animation:none}}
</style>
<script id="nd-rodada-11-logic">
(function(){'use strict';
 const KEY='ndburgs_r11_dismissed'; let lastKey=''; let timer;
 const q=s=>document.querySelector(s), qa=s=>[...document.querySelectorAll(s)];
 const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');
 function getCart(){try{return Array.isArray(window.carrinho)?window.carrinho:[]}catch(e){return[]}}
 function total(){return getCart().reduce((a,i)=>a+(Number(i.preco)||0)*(Number(i.quantidade)||1),0)}
 function ensure(){if(q('#ndR11Box'))return; const d=document.createElement('div');d.id='ndR11Box';d.innerHTML='<div class="r11-head"><span class="r11-fire">🔥</span><span class="r11-title">COMPLETE SEU PEDIDO</span><button class="r11-close" type="button" aria-label="Fechar">×</button></div><div class="r11-sub">Uma sugestão que combina com o que você já escolheu.</div><div id="ndR11Item"></div><div id="ndR11Mini"></div>';document.body.appendChild(d);d.querySelector('.r11-close').onclick=()=>{d.classList.remove('show');try{sessionStorage.setItem(KEY,'1')}catch(e){}}}
 function catalog(){
   const out=[]; const seen=new Set();
   qa('button[onclick*="adicionar("]').forEach(b=>{const m=b.getAttribute('onclick').match(/adicionar\((['"])(.*?)\1\s*,\s*([0-9.]+)/);if(!m)return;const nome=m[2],preco=Number(m[3]);if(!nome||!preco||seen.has(nome))return;seen.add(nome);out.push({nome,preco,btn:b})}); return out;
 }
 function choose(){
   const c=getCart(), names=c.map(i=>String(i.nome||'').toUpperCase()).join(' | '), cat=catalog();
   if(!c.length)return null;
   const rules=names.includes('AÇA')||names.includes('AÇAI')?[ 'DOCE','SOBREMESA','BRIGADEIRO','UVA','BROWNIE','COMBO']:
     names.includes('BURGER')||names.includes('X-')||names.includes('X ')||names.includes('GADEIA')||names.includes('PATÃO')||names.includes('BERENICE')||names.includes('DINA')||names.includes('GAROTINHO')?[ 'BATATA','REFRI','COCA','BEBIDA','DOCE','SOBREMESA','COMBO']:
     names.includes('PASTEL')?[ 'REFRI','COCA','DOCE','AÇA','COMBO']:['BATATA','REFRI','COCA','DOCE','SOBREMESA','COMBO'];
   const inCart=new Set(c.map(i=>String(i.nome||'').toUpperCase()));
   let best=cat.find(x=>!inCart.has(x.nome.toUpperCase())&&rules.some(r=>x.nome.toUpperCase().includes(r)));
   if(!best)best=cat.find(x=>!inCart.has(x.nome.toUpperCase()));
   return best||null;
 }
 function show(){
   ensure(); const box=q('#ndR11Box'), item=q('#ndR11Item'); if(!box||!item)return;
   if(!getCart().length){box.classList.remove('show');return}
   let pick=choose(); if(!pick){box.classList.remove('show');return}
   const k=pick.nome+'|'+total(); if(k===lastKey)return; lastKey=k;
   let dismissed=false;try{dismissed=sessionStorage.getItem(KEY)==='1'}catch(e){}
   if(dismissed)return;
   item.innerHTML='<span class="r11-name">'+pick.nome+'</span><span class="r11-price">'+money(pick.preco)+'</span><button class="r11-add" type="button">+ ADICIONAR</button>';
   item.querySelector('.r11-add').onclick=()=>{try{window.adicionar(pick.nome,pick.preco)}catch(e){if(pick.btn)pick.btn.click()}box.classList.remove('show');try{sessionStorage.removeItem(KEY)}catch(e){}};
   clearTimeout(timer);timer=setTimeout(()=>box.classList.add('show'),350);
 }
 function mini(){
   const el=q('#ndR11Mini');if(!el)return;const c=getCart(),n=c.reduce((a,i)=>a+(Number(i.quantidade)||1),0);if(!n){el.style.display='none';return}el.style.display='block';el.innerHTML='🛒 <b>'+n+' item'+(n>1?'s':'')+'</b> no seu pedido • subtotal <b>'+money(total())+'</b>';
 }
 function patch(){if(window.__ndR11Patched)return; if(typeof window.atualizarCarrinho!=='function')return;const original=window.atualizarCarrinho;window.atualizarCarrinho=function(){const r=original.apply(this,arguments);setTimeout(()=>{mini();show()},0);return r};window.__ndR11Patched=true;setTimeout(()=>{mini();show()},500)}
 function init(){ensure();patch();mini();show();setInterval(()=>{patch();mini()},1200)}
 if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init,{once:true});else init();
})();
</script>
<!-- ND BURGS VERSION: 20260904-R11 -->


<!-- ND BURGS — ETAPA 12: BLACKOUT TOTAL + REFINAMENTO VISUAL -->
<style id="nd-etapa-12-blackout">
/* FUNDO 100% PRETO — sem gradientes, brilhos, estrelas ou efeitos de luz */
html,body{background:#000!important;background-image:none!important}
body::before,body::after,html::before,html::after{content:none!important;display:none!important;background:none!important;box-shadow:none!important;filter:none!important}
/* Remove somente efeitos luminosos do fundo, preservando cards e botões */
body,[class*="background"],[class*="bg-"]{background-image:none!important}
/* Áreas principais da página */
main,header,footer,section,.container,.conteudo,.pagina,.page{background-image:none!important}
/* Desliga overlays de luz/gradientes usados como decoração */
[class*="glow"],[class*="shine"],[class*="light"],[class*="stars"],[class*="starfield"]{background-image:none!important}
/* Mantém leitura e contraste */
body{background-color:#000!important;color:#fff}
</style>
<script id="nd-etapa-12-logic">
(function(){'use strict';
  /* Restaura o preto caso algum componente tente inserir fundo luminoso dinamicamente. */
  function enforceBlack(){
    document.documentElement.style.setProperty('background','#000','important');
    document.body.style.setProperty('background','#000','important');
    document.body.style.setProperty('background-image','none','important');
  }
  if(document.readyState==='loading') document.addEventListener('DOMContentLoaded',enforceBlack,{once:true}); else enforceBlack();
  window.addEventListener('pageshow',enforceBlack,{passive:true});
})();
</script>
<!-- ND BURGS VERSION: 20260904-R12 -->



<!-- ND BURGS — ETAPA 13: HIERARQUIA VISUAL PREMIUM NO BLACKOUT -->
<style id="nd-etapa-13-visual">
/* Tudo abaixo é uma camada visual: não altera preços, produtos, carrinho ou checkout. */
:root{--nd13-radius:16px;--nd13-gap:14px}
html{scroll-behavior:smooth}
body{background:#000!important;color:#fff!important}
/* Seções mais organizadas */
section{border-radius:var(--nd13-radius);}
/* Títulos com hierarquia mais limpa */
section h1,section h2{letter-spacing:.2px;line-height:1.12}
section h3{line-height:1.2}
/* Cards de produto: aparência mais sólida, sem glow */
.produto{border-radius:18px!important;overflow:hidden;position:relative;transition:transform .18s ease,border-color .18s ease,box-shadow .18s ease!important}
.produto:hover{transform:translateY(-2px)!important;box-shadow:0 8px 24px rgba(0,0,0,.55)!important}
.produto-imagem{overflow:hidden}
.produto-imagem img{display:block;width:100%;transition:transform .22s ease!important}
.produto:hover .produto-imagem img{transform:scale(1.025)}
/* Preço ganha leitura sem mexer no valor */
.produto .preco{font-weight:800;letter-spacing:.2px}
/* Botões: área de toque mais confortável */
button,.btn,.botao{min-height:42px}
.produto button{border-radius:12px!important;font-weight:800!important;transition:transform .14s ease,filter .14s ease!important}
.produto button:active{transform:scale(.97)!important}
/* Inputs do checkout */
input,select,textarea{border-radius:11px!important;outline:none!important}
input:focus,select:focus,textarea:focus{box-shadow:0 0 0 2px rgba(255,255,255,.16)!important}
/* Separação visual entre blocos */
section+section{margin-top:18px}
/* Cabeçalhos fixos/menus continuam visíveis sem adicionar efeitos */
header{z-index:50}
/* Reduz animações quando o usuário preferir */
@media (prefers-reduced-motion:reduce){html{scroll-behavior:auto}.produto,.produto-imagem img,button,.btn,.botao{transition:none!important}.produto:hover{transform:none!important}.produto:hover .produto-imagem img{transform:none!important}}
/* Mobile */
@media(max-width:600px){
  .produto{border-radius:15px!important}
  .produto button{min-height:44px!important}
  section+section{margin-top:14px}
  section h1,section h2{margin-bottom:10px}
}
</style>
<script id="nd-etapa-13-logic">
(function(){'use strict';
  /* Camada defensiva: mantém o blackout sem interferir no restante do sistema. */
  function nd13Black(){
    document.documentElement.style.setProperty('background','#000','important');
    if(document.body){document.body.style.setProperty('background','#000','important');document.body.style.setProperty('background-image','none','important');}
  }
  function nd13Init(){nd13Black();}
  if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',nd13Init,{once:true});else nd13Init();
  window.addEventListener('pageshow',nd13Black,{passive:true});
})();
</script>
<!-- ND BURGS VERSION: 20260904-R13 -->


<!-- ND BURGS — ETAPA 14: BUSCA INTELIGENTE + NAVEGAÇÃO RÁPIDA -->
<style id="nd-etapa-14-style">
#nd14SearchWrap{width:min(100%,980px);margin:16px auto 18px;padding:0 12px;box-sizing:border-box;position:relative;z-index:10}
#nd14SearchBox{background:#0b0b0b;border:1px solid #292929;border-radius:16px;padding:10px;display:flex;align-items:center;gap:9px;box-shadow:0 8px 24px rgba(0,0,0,.35)}
#nd14SearchIcon{font-size:20px;line-height:1;flex:0 0 auto}
#nd14Search{width:100%;min-width:0;background:#000!important;color:#fff!important;border:0!important;outline:0!important;box-shadow:none!important;font-size:16px;font-weight:600;padding:9px 4px}
#nd14Search::placeholder{color:#8a8a8a}
#nd14Clear{display:none;flex:0 0 auto;border:1px solid #333;background:#151515;color:#fff;border-radius:10px;min-height:38px;padding:0 12px;font-weight:800;cursor:pointer}
#nd14Meta{display:flex;justify-content:space-between;gap:10px;padding:8px 4px 0;color:#8f8f8f;font-size:12px;font-weight:700}
#nd14Count{color:#fff}
.nd14-hidden{display:none!important}
.nd14-no-results{width:min(100%,980px);margin:12px auto;padding:28px 18px;text-align:center;border:1px solid #252525;border-radius:16px;background:#080808;color:#aaa}
.nd14-no-results strong{display:block;color:#fff;font-size:17px;margin-bottom:6px}
@media(max-width:600px){#nd14SearchWrap{padding:0 9px;margin:12px auto 15px}#nd14SearchBox{border-radius:14px;padding:8px}#nd14Search{font-size:15px}#nd14Clear{min-height:36px;padding:0 10px}#nd14Meta{font-size:11px}}
@media(prefers-reduced-motion:reduce){#nd14SearchBox{scroll-behavior:auto}}
</style>
<script id="nd-etapa-14-logic">
(function(){'use strict';
  function norm(v){return (v||'').toString().normalize('NFD').replace(/[\u0300-\u036f]/g,'').toLowerCase().trim();}
  function init(){
    if(document.getElementById('nd14SearchWrap')) return;
    var products=Array.prototype.slice.call(document.querySelectorAll('.produto'));
    if(!products.length) return;
    var first=products[0];
    var wrap=document.createElement('div');
    wrap.id='nd14SearchWrap';
    wrap.innerHTML='<div id="nd14SearchBox"><span id="nd14SearchIcon">🔎</span><input id="nd14Search" type="search" inputmode="search" autocomplete="off" placeholder="Buscar no cardápio..." aria-label="Buscar no cardápio"><button id="nd14Clear" type="button" aria-label="Limpar busca">LIMPAR</button></div><div id="nd14Meta"><span id="nd14Hint">Digite o nome do produto</span><span id="nd14Count"></span></div>';
    first.parentNode.insertBefore(wrap,first);
    var input=document.getElementById('nd14Search'), clear=document.getElementById('nd14Clear'), count=document.getElementById('nd14Count'), hint=document.getElementById('nd14Hint');
    var empty=document.createElement('div'); empty.className='nd14-no-results nd14-hidden'; empty.innerHTML='<strong>Nenhum produto encontrado</strong><span>Tente outro nome ou confira a escrita.</span>'; wrap.parentNode.insertBefore(empty,wrap.nextSibling);
    var data=products.map(function(el){return {el:el,text:norm(el.innerText||el.textContent)};});
    function apply(){
      var q=norm(input.value), shown=0;
      data.forEach(function(item){var ok=!q||item.text.indexOf(q)!==-1; item.el.classList.toggle('nd14-hidden',!ok); if(ok) shown++;});
      var active=!!q;
      clear.style.display=active?'block':'none';
      empty.classList.toggle('nd14-hidden',!active||shown!==0);
      count.textContent=active?(shown+' produto'+(shown===1?'':'s')):'';
      hint.textContent=active?'Resultados para: "'+input.value+'"':'Digite o nome do produto';
    }
    input.addEventListener('input',apply);
    clear.addEventListener('click',function(){input.value='';apply();input.focus();});
    input.addEventListener('keydown',function(e){if(e.key==='Escape'){input.value='';apply();input.blur();}});
  }
  if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init,{once:true});else init();
})();
</script>


<!-- ND BURGS — ETAPA 15: NAVEGAÇÃO PREMIUM POR CATEGORIAS -->
<style id="nd-etapa-15-style">
#nd15NavWrap{width:min(100%,1180px);margin:10px auto 20px;padding:0 10px;box-sizing:border-box;position:sticky;top:8px;z-index:45}
#nd15Nav{background:#050505;border:1px solid #252525;border-radius:16px;padding:8px;display:flex;gap:7px;overflow-x:auto;scrollbar-width:none;box-shadow:0 10px 28px rgba(0,0,0,.5)}
#nd15Nav::-webkit-scrollbar{display:none}
.nd15-btn{appearance:none;border:1px solid #292929;background:#101010;color:#aaa;border-radius:11px;min-height:40px;padding:0 14px;white-space:nowrap;font-size:13px;font-weight:800;cursor:pointer;transition:background .16s ease,color .16s ease,border-color .16s ease,transform .16s ease}
.nd15-btn:hover{color:#fff;border-color:#444;background:#181818}
.nd15-btn:active{transform:scale(.97)}
.nd15-btn.nd15-active{background:#fff;color:#000;border-color:#fff}
.nd15-top{margin-left:auto;flex:0 0 auto;min-width:40px;padding:0 11px}
section.categoria.nd15-target{scroll-margin-top:78px}
section.categoria.nd15-target.nd15-highlight{animation:nd15Flash .7s ease}
@keyframes nd15Flash{0%{outline:2px solid rgba(255,255,255,.0);outline-offset:0}35%{outline:2px solid rgba(255,255,255,.22);outline-offset:4px}100%{outline:2px solid rgba(255,255,255,0);outline-offset:0}}
@media(max-width:600px){
 #nd15NavWrap{top:5px;padding:0 7px;margin:8px auto 15px}
 #nd15Nav{border-radius:14px;padding:7px;gap:6px}
 .nd15-btn{min-height:38px;padding:0 12px;font-size:12px;border-radius:10px}
}
@media(prefers-reduced-motion:reduce){.nd15-btn{transition:none!important}section.categoria.nd15-target.nd15-highlight{animation:none!important}}
</style>
<script id="nd-etapa-15-logic">
(function(){'use strict';
  function init(){
    if(document.getElementById('nd15NavWrap')) return;
    var sections=Array.prototype.slice.call(document.querySelectorAll('section.categoria'));
    if(!sections.length) return;
    var names=['Combos','Tradicionais','Artesanais','Combos Artesanais','Porções','Pastéis','Açaí','Milkshakes','Bebidas','Sobremesas','Adicionais'];
    var icons=['❤️','🍔','🔥','🔥','🍟','🥟','🥤','🥤','🥤','🍓','➕'];
    var used=[], nav=document.createElement('div'); nav.id='nd15NavWrap';
    var bar=document.createElement('nav'); bar.id='nd15Nav'; bar.setAttribute('aria-label','Categorias do cardápio');
    sections.forEach(function(sec,i){
      var title=sec.querySelector('h2,h3');
      var raw=(title?title.textContent:'').replace(/\s+/g,' ').trim();
      var label=names[i]||raw.replace(/^[^A-Za-zÀ-ÿ0-9]+/,'').trim()||('Categoria '+(i+1));
      var id='nd15-'+label.normalize('NFD').replace(/[\u0300-\u036f]/g,'').toLowerCase().replace(/[^a-z0-9]+/g,'-').replace(/^-|-$/g,'')+'-'+i;
      sec.id=id; sec.classList.add('nd15-target');
      var btn=document.createElement('button'); btn.type='button'; btn.className='nd15-btn'; btn.dataset.target=id; btn.setAttribute('aria-label','Ir para '+label); btn.innerHTML=(icons[i]||'•')+' '+label;
      btn.addEventListener('click',function(){
        var target=document.getElementById(id); if(!target) return;
        var top=target.getBoundingClientRect().top+window.pageYOffset-78;
        window.scrollTo({top:Math.max(0,top),behavior:window.matchMedia('(prefers-reduced-motion: reduce)').matches?'auto':'smooth'});
        sections.forEach(function(x){x.classList.remove('nd15-highlight')});
        target.classList.add('nd15-highlight');
        setTimeout(function(){target.classList.remove('nd15-highlight')},800);
        setActive(btn);
      });
      bar.appendChild(btn); used.push(btn);
    });
    var top=document.createElement('button'); top.type='button'; top.className='nd15-btn nd15-top'; top.title='Voltar ao topo'; top.setAttribute('aria-label','Voltar ao topo'); top.textContent='↑';
    top.addEventListener('click',function(){window.scrollTo({top:0,behavior:window.matchMedia('(prefers-reduced-motion: reduce)').matches?'auto':'smooth'}); setActive(used[0]);});
    bar.appendChild(top); nav.appendChild(bar);
    var first=sections[0]; first.parentNode.insertBefore(nav,first);
    function setActive(btn){used.forEach(function(b){var on=b===btn;b.classList.toggle('nd15-active',on);b.setAttribute('aria-current',on?'true':'false')}); if(btn&&btn.scrollIntoView){btn.scrollIntoView({behavior:'smooth',block:'nearest',inline:'center'})}}
    setActive(used[0]);
    if('IntersectionObserver' in window){
      var obs=new IntersectionObserver(function(entries){
        entries.forEach(function(entry){if(entry.isIntersecting){var idx=sections.indexOf(entry.target);if(idx>-1)setActive(used[idx]);}});
      },{root:null,rootMargin:'-92px 0px -55% 0px',threshold:0});
      sections.forEach(function(sec){obs.observe(sec)});
    }
    window.addEventListener('keydown',function(e){if(e.key==='Home'&&!e.ctrlKey&&!e.metaKey&&document.activeElement&&document.activeElement.tagName!=='INPUT'&&document.activeElement.tagName!=='TEXTAREA'){e.preventDefault();window.scrollTo({top:0,behavior:'smooth'});}}, {passive:false});
  }
  if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init,{once:true});else init();
})();
</script>
<!-- ND BURGS VERSION: 20260904-R15 -->


<!-- =========================================================
     ND BURGS — ETAPA 16
     EXPERIÊNCIA DOS PRODUTOS + TOTAL COM TAXA DE ENTREGA
     Camada adicional. Favoritos preservados integralmente.
     ========================================================= -->
<style id="nd-etapa-16">
/* ===== PRODUTOS: hierarquia premium, sem brilho ===== */
.produto{
  position:relative;
  overflow:hidden;
  border-radius:18px!important;
  transition:transform .18s ease,border-color .18s ease,box-shadow .18s ease!important;
}
.produto:hover{transform:translateY(-2px);border-color:rgba(255,210,26,.32)!important;box-shadow:0 10px 28px rgba(0,0,0,.42)!important}
.produto .produto-imagem{overflow:hidden;border-radius:14px}
.produto .produto-imagem img{transition:transform .22s ease!important}
.produto:hover .produto-imagem img{transform:scale(1.025)}
.produto h3{font-weight:900!important;letter-spacing:.1px}
.produto .preco{font-size:1.08rem!important;font-weight:950!important}
.produto .btn-add,.produto button[onclick*="adicionar("]{
  min-height:44px!important;
  border-radius:12px!important;
  font-weight:950!important;
  letter-spacing:.2px;
  transition:transform .14s ease,filter .14s ease!important;
}
.produto .btn-add:hover,.produto button[onclick*="adicionar("]:hover{filter:brightness(1.06);transform:translateY(-1px)}
.produto .btn-add:active,.produto button[onclick*="adicionar("]:active{transform:scale(.98)}

/* ===== RESUMOS: total sempre em destaque ===== */
#total,#totalCarrinhoModal,#totalFinalizarModal,#ndV4Total{
  font-weight:950!important;
  font-size:1.18rem!important;
}
#taxa,#taxaCarrinhoModal,#taxaFinalizarModal,#ndV4Fee{font-weight:850!important}

/* Caixa visual para deixar claro que a taxa entra no total */
.nd16-total-note{
  display:flex;align-items:center;justify-content:space-between;gap:12px;
  margin-top:8px;padding:9px 11px;border:1px solid #242424;border-radius:11px;
  background:#070707;color:#aaa;font-size:11px;line-height:1.35;
}
.nd16-total-note b{color:#fff}
.nd16-total-note strong{color:#ffd21a;white-space:nowrap}

@media(max-width:600px){
  .produto{border-radius:15px!important}
  .produto .produto-imagem{border-radius:12px}
  .produto .btn-add,.produto button[onclick*="adicionar("]{min-height:46px!important}
}
@media(prefers-reduced-motion:reduce){
  .produto,.produto .produto-imagem img,.produto .btn-add,.produto button[onclick*="adicionar("]{transition:none!important}
}
</style>
<script id="nd-etapa-16-logic">
(function(){'use strict';
  /* Favoritos: esta etapa NÃO altera nem intercepta os botões de coração. */
  const q=s=>document.querySelector(s);
  const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');
  function cart(){return Array.isArray(window.carrinho)?window.carrinho:[]}
  function subtotal(){return cart().reduce((a,i)=>a+(Number(i.preco)||0)*(Number(i.quantidade)||1),0)}
  function fee(){
    try{
      if(typeof window.obterTaxaEntrega==='function')return Number(window.obterTaxaEntrega()||0);
      const tipo=q('#tipoPedidoModal'), rua=q('#ruaModal');
      if(tipo&&tipo.value==='ENTREGA'&&rua&&window.taxas)return Number(window.taxas[rua.value]||0);
      const rua2=q('#rua'); return rua2&&window.taxas?Number(window.taxas[rua2.value]||0):0;
    }catch(e){return 0}
  }
  function syncTotal(){
    if(!cart().length)return;
    const sub=subtotal(), taxa=fee(), total=sub+taxa;
    /* Reforça todos os totais já existentes, sem substituir as funções originais. */
    const pairs=[
      ['#subtotalCarrinhoModal',sub],['#taxaCarrinhoModal',taxa],['#totalCarrinhoModal',total],
      ['#subtotalFinalizarModal',sub],['#taxaFinalizarModal',taxa],['#totalFinalizarModal',total],
      ['#ndV4Sub',sub],['#ndV4Fee',taxa],['#ndV4Total',total]
    ];
    pairs.forEach(([sel,val])=>{const el=q(sel);if(el)el.textContent=money(val)});
    const note=q('#nd16TotalNote');
    if(note){
      note.innerHTML='<span>Subtotal + taxa de entrega</span><strong>'+money(total)+'</strong>';
    }
  }
  function ensureNote(){
    const target=q('#totalCarrinhoModal')?.closest('.total-modal')||q('#totalCarrinhoModal')?.parentElement;
    if(!target||q('#nd16TotalNote'))return;
    const d=document.createElement('div');d.id='nd16TotalNote';d.className='nd16-total-note';
    d.innerHTML='<span>Subtotal + taxa de entrega</span><strong>R$ 0,00</strong>';
    target.parentNode.insertBefore(d,target.nextSibling);
  }
  function refresh(){ensureNote();syncTotal()}
  function patch(){
    if(window.__nd16Patched)return;
    const original=window.atualizarCarrinho;
    if(typeof original!=='function')return;
    window.atualizarCarrinho=function(){const r=original.apply(this,arguments);setTimeout(refresh,0);return r};
    window.__nd16Patched=true;
  }
  function init(){patch();refresh();setTimeout(refresh,300);setTimeout(refresh,1000);setInterval(()=>{patch();refresh()},1500)}
  if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init,{once:true});else init();
})();
</script>

<!-- =========================================================
     ND BURGS — RODADA 17
     ENDEREÇO PRIMEIRO + TAXA NO TOTAL + WHATSAPP SIMPLES
     + BOTÕES AZUIS + PREÇOS EM DESTAQUE + LOGO REPOSICIONADA
     Favoritos preservados: nenhum botão de coração é interceptado.
     ========================================================= -->
<style id="nd-rodada-17">
:root{--nd17-blue:#1677ff;--nd17-blue2:#2f8cff;--nd17-gold:#ffd21a;--nd17-black:#000;--nd17-panel:#0b0b0b;--nd17-line:#252525}
/* Página continua preta; sem novos efeitos de fundo */
html,body{background:#000!important;background-image:none!important}
/* Logo: menor, centralizada e separada do conteúdo */
header{display:flex!important;justify-content:center!important;align-items:center!important;padding:10px 14px 8px!important;background:#000!important;border-bottom:1px solid #181818!important;box-shadow:none!important}
header .logo{display:none!important}
.nd17-brand{display:flex;justify-content:center;align-items:center;padding:8px 0 2px}.nd17-brand img{width:min(190px,52vw);max-height:72px;object-fit:contain;border-radius:10px}
/* Nomes maiores, sem negrito pesado */
.produto h3{font-size:clamp(17px,1.65vw,21px)!important;font-weight:500!important;line-height:1.16!important;letter-spacing:.1px!important}
/* Preços brilhando sem iluminar o fundo */
.produto .preco,.preco,#totalCarrinhoModal,#ndV4Total,#totalFinalizarModal,#total{
 color:#fff!important;font-weight:1000!important;font-size:clamp(22px,2.2vw,30px)!important;
 text-shadow:0 0 6px rgba(255,210,26,.95),0 0 16px rgba(255,210,26,.55),0 0 30px rgba(255,210,26,.28)!important;
}
/* Todos os botões de produtos: azul no mouse/toque */
.produto .btn-add,.produto button[onclick*="adicionar("],.btn-add{
 background:var(--nd17-blue)!important;color:#fff!important;border:1px solid #3f98ff!important;
 transition:transform .16s ease,background-color .16s ease,box-shadow .16s ease,filter .16s ease!important;
}
.produto .btn-add:hover,.produto button[onclick*="adicionar("]:hover,.btn-add:hover{
 background:var(--nd17-blue2)!important;transform:translateY(-2px) scale(1.015)!important;
 box-shadow:0 8px 22px rgba(22,119,255,.28)!important;filter:none!important;
}
.produto .btn-add:active,.produto button[onclick*="adicionar("]:active,.btn-add:active{transform:scale(.97)!important}
/* Botões de checkout/WhatsApp também ficam azuis */
.nd-v4-next,.btn-whatsapp,#finalizarPedido,.btn-finalizar,.btn-finalizar-pedido{
 background:var(--nd17-blue)!important;color:#fff!important;border-color:#3f98ff!important;
 transition:transform .16s ease,background-color .16s ease,box-shadow .16s ease!important;
}
.nd-v4-next:hover,.btn-whatsapp:hover,#finalizarPedido:hover,.btn-finalizar:hover,.btn-finalizar-pedido:hover{
 background:var(--nd17-blue2)!important;transform:translateY(-2px)!important;box-shadow:0 8px 24px rgba(22,119,255,.3)!important;
}
/* Etiquetas: somente MAIS VENDIDO */
.nd-r3-badge{display:none!important}
.nd-fx-bestseller{display:none!important}
.nd17-best{display:block!important;position:absolute;left:12px;top:12px;z-index:9;padding:6px 9px;border-radius:8px;background:#ffd21a;color:#000;font-size:9px;font-weight:900;letter-spacing:.3px;box-shadow:0 5px 15px rgba(0,0,0,.5)}
/* Caixa fixa de endereço escolhido */
#nd17AddressBar{display:flex;align-items:center;justify-content:space-between;gap:12px;max-width:1180px;margin:10px auto;padding:10px 14px;background:#080808;border:1px solid #202020;border-radius:12px;color:#ddd}
#nd17AddressBar strong{color:#fff;font-size:13px}.nd17-address-edit{border:1px solid #333;background:#111;color:#fff;border-radius:9px;padding:8px 11px;cursor:pointer;font-weight:800}
/* Modal inicial de endereço */
#nd17Gate{position:fixed;inset:0;z-index:100000;background:rgba(0,0,0,.96);display:none;align-items:center;justify-content:center;padding:18px}
#nd17Gate.show{display:flex}
.nd17-gate-panel{width:min(470px,100%);background:#090909;border:1px solid #292929;border-radius:20px;padding:24px;box-shadow:0 25px 80px rgba(0,0,0,.8)}
.nd17-kicker{font-size:10px;color:#8e8e8e;font-weight:900;letter-spacing:1.2px}.nd17-gate-panel h2{font-size:27px;margin:6px 0 8px}.nd17-gate-panel p{font-size:13px;color:#999;line-height:1.45;margin:0 0 18px}
.nd17-field{margin:11px 0}.nd17-field label{display:block;font-size:11px;color:#aaa;font-weight:800;margin-bottom:6px}.nd17-field input{width:100%;box-sizing:border-box;background:#111;border:1px solid #2b2b2b;color:#fff;border-radius:11px;padding:13px;font-size:15px;outline:none}.nd17-field input:focus{border-color:var(--nd17-blue)}
.nd17-suggest{position:relative}.nd17-list{position:absolute;left:0;right:0;top:calc(100% + 4px);z-index:100002;max-height:210px;overflow:auto;background:#111;border:1px solid #303030;border-radius:11px;display:none}.nd17-list.show{display:block}.nd17-option{padding:12px 13px;color:#eee;border-bottom:1px solid #222;cursor:pointer;font-size:13px}.nd17-option:last-child{border-bottom:0}.nd17-option:hover{background:#1677ff;color:#fff}
.nd17-gate-main{width:100%;border:0;border-radius:12px;background:var(--nd17-blue);color:#fff;padding:14px;font-weight:900;font-size:14px;cursor:pointer}.nd17-gate-main:hover{background:var(--nd17-blue2)}
.nd17-gate-retirada{width:100%;margin-top:8px;border:1px solid #333;border-radius:12px;background:#111;color:#ddd;padding:12px;font-weight:800;cursor:pointer}
/* Resumo do carrinho: taxa e total visualmente inequívocos */
#nd17CartAddress{margin:10px 0;padding:10px 12px;border:1px solid #242424;border-radius:10px;background:#080808;font-size:11px;color:#aaa}
#nd17CartAddress b{color:#fff}#nd17CartAddress strong{color:#ffd21a}
.nd17-total-label{font-size:11px;color:#aaa}.nd17-total-value{font-size:28px!important}
/* Sugestões nos campos de rua existentes */
.nd17-inline-suggest{position:relative}.nd17-inline-list{position:absolute;left:0;right:0;top:100%;z-index:5000;background:#111;border:1px solid #303030;border-radius:10px;max-height:190px;overflow:auto;display:none}.nd17-inline-list.show{display:block}
@media(max-width:600px){.nd17-brand img{width:155px;max-height:58px}#nd17AddressBar{margin:8px 8px;padding:9px 10px}.produto h3{font-size:17px!important}.produto .preco,.preco{font-size:23px!important}.nd17-gate-panel{padding:20px}.nd17-option{padding:13px}.nd17-total-value{font-size:25px!important}}
@media(prefers-reduced-motion:reduce){.produto .btn-add,.produto button[onclick*="adicionar("),.btn-add,.nd-v4-next,.btn-whatsapp,#finalizarPedido,.btn-finalizar,.btn-finalizar-pedido{transition:none!important}}
</style>

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

<script id="nd-rodada-17-logic">
(function(){'use strict';
 const $=s=>document.querySelector(s), $$=s=>Array.from(document.querySelectorAll(s));
 const money=v=>'R$ '+Number(v||0).toFixed(2).replace('.',',');
 const norm=v=>String(v||'').toUpperCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'');
 const cart=()=>Array.isArray(window.carrinho)?window.carrinho:[];
 const subtotal=()=>cart().reduce((s,i)=>s+(Number(i.preco)||0)*(Number(i.quantidade)||1),0);
 function streets(){try{return typeof taxas!=='undefined'?Object.keys(taxas).filter(x=>!['BALCAO','RETIRADA','IFOOD','99FOOD'].includes(x)):Object.keys(window.taxas||{}).filter(x=>!['BALCAO','RETIRADA','IFOOD','99FOOD'].includes(x))}catch(e){return []}}
 try{if(typeof taxas!=='undefined')window.taxas=taxas}catch(e){}
 function saveAddr(street,number,type){localStorage.setItem('nd17_tipo',type);localStorage.setItem('nd17_rua',street||'');localStorage.setItem('nd17_numero',number||'');}
 function addr(){return {type:localStorage.getItem('nd17_tipo')||'ENTREGA',street:localStorage.getItem('nd17_rua')||'',number:localStorage.getItem('nd17_numero')||''}}
 function fee(){const a=addr();if(a.type!=='ENTREGA'||!a.street)return 0;try{return Number((window.taxas||{})[a.street]||0)}catch(e){return 0}}
 function ensureMainForms(){const a=addr();
   const type=$('#tipoPedido'); if(type){type.value=a.type==='RETIRADA'?'RETIRADA':'ENTREGA';}
   const rua=$('#rua'); if(rua&&a.street&&[...rua.options].some(o=>o.value===a.street))rua.value=a.street;
   const num=$('#numero'); if(num&&a.number)num.value=a.number;
   const typeM=$('#tipoPedidoModal'); if(typeM)typeM.value=a.type==='RETIRADA'?'RETIRADA':'ENTREGA';
   const ruaM=$('#ruaModal'); if(ruaM&&a.street&&[...ruaM.options].some(o=>o.value===a.street))ruaM.value=a.street;
   const numM=$('#numeroModal'); if(numM&&a.number)numM.value=a.number;
 }
 function cartTotalSync(){
   ensureMainForms(); const sub=subtotal(), f=fee(), total=sub+f;
   [['#subtotalCarrinhoModal',sub],['#taxaCarrinhoModal',f],['#totalCarrinhoModal',total],['#ndV4Sub',sub],['#ndV4Fee',f],['#ndV4Total',total]].forEach(([s,v])=>{const e=$(s);if(e)e.textContent=money(v)});
   const panel=$('#modalCarrinho'); if(panel){let box=$('#nd17CartAddress');if(!box){const sum=panel.querySelector('.resumo-modal');if(sum){box=document.createElement('div');box.id='nd17CartAddress';sum.parentNode.insertBefore(box,sum)}}if(box){const a=addr();box.innerHTML=a.type==='RETIRADA'?'<b>Retirada no local</b><br>Sem taxa de entrega.':'<b>Entrega:</b> '+(a.street||'Endereço não informado')+(a.number?', Nº '+a.number:'')+'<br><strong>Taxa de entrega: '+money(f)+'</strong> · Total com taxa: <strong>'+money(total)+'</strong>'}}
 }
 function showGate(){const g=$('#nd17Gate');if(g)g.classList.add('show');document.body.style.overflow='hidden';setTimeout(()=>$('#nd17GateStreet')?.focus(),80)}
 function hideGate(){const g=$('#nd17Gate');if(g)g.classList.remove('show');document.body.style.overflow=''}
 function renderList(input,list){if(!input||!list)return;const q=norm(input.value).trim();const arr=streets().filter(s=>!q||norm(s).includes(q)).slice(0,12);list.innerHTML='';arr.forEach(s=>{const d=document.createElement('div');d.className='nd17-option';d.textContent=s+' — '+money((window.taxas||{})[s]);d.addEventListener('click',()=>{input.value=s;input.dataset.value=s;list.classList.remove('show');input.dispatchEvent(new Event('change',{bubbles:true}));cartTotalSync()});list.appendChild(d)});list.classList.toggle('show',!!q&&arr.length>0)}
 function bindAutocomplete(input,list){if(!input||input.dataset.nd17bound)return;input.dataset.nd17bound='1';input.addEventListener('input',()=>renderList(input,list));input.addEventListener('focus',()=>{if(input.value)renderList(input,list)});document.addEventListener('click',e=>{if(!input.contains(e.target)&&!list.contains(e.target))list.classList.remove('show')})}
 function setupAutocomplete(){bindAutocomplete($('#nd17GateStreet'),$('#nd17GateList'));bindAutocomplete($('#ruaBuscaModal'),ensureInline($('#ruaBuscaModal')));bindAutocomplete($('#ruaBusca'),ensureInline($('#ruaBusca')))}
 function ensureInline(input){if(!input)return null;let list=input.parentElement.querySelector('.nd17-inline-list');if(!list){const wrap=document.createElement('div');wrap.className='nd17-inline-suggest';input.parentNode.insertBefore(wrap,input);wrap.appendChild(input);list=document.createElement('div');list.className='nd17-inline-list';wrap.appendChild(list)}return list}
 function saveGate(type){const street=$('#nd17GateStreet')?.value.trim().toUpperCase()||'', num=$('#nd17GateNumber')?.value.trim()||'';if(type==='ENTREGA'){const key=streets().find(s=>norm(s)===norm(street));if(!key)return alert('Selecione uma rua da lista de sugestões.');if(!num)return alert('Digite o número do endereço.');saveAddr(key,num,'ENTREGA')}else saveAddr('','', 'RETIRADA');ensureMainForms();cartTotalSync();hideGate();updateBar();}
 function ensureBrand(){if($('.nd17-brand'))return;const logo=$('header .logo'),search=$('.modern-search');if(!logo||!search)return;const b=document.createElement('div');b.className='nd17-brand';const im=logo.cloneNode(true);im.removeAttribute('class');im.alt='ND BURGS';b.appendChild(im);search.parentNode.insertBefore(b,search)}
 function updateBar(){ensureBrand();let b=$('#nd17AddressBar');if(!b){const h=$('.horarios');if(!h)return;b=document.createElement('div');b.id='nd17AddressBar';h.parentNode.insertBefore(b,h.nextSibling)}const a=addr(),f=fee();b.innerHTML=a.type==='RETIRADA'?'<span><strong>Retirada no local</strong></span><button class="nd17-address-edit" type="button">ALTERAR</button>':'<span><strong>'+a.street+(a.number?', Nº '+a.number:'')+'</strong><br><small>Taxa de entrega: '+money(f)+'</small></span><button class="nd17-address-edit" type="button">ALTERAR</button>';b.querySelector('button').onclick=()=>showGate()}
 function openGateIfNeeded(){if(!localStorage.getItem('nd17_tipo'))showGate();else{ensureMainForms();updateBar();cartTotalSync()}}
 function patchOpenCart(){if(window.__nd17Cart)return;const old=window.abrirCarrinho;if(typeof old!=='function')return;window.abrirCarrinho=function(){ensureMainForms();const r=old.apply(this,arguments);setTimeout(cartTotalSync,30);return r};window.__nd17Cart=true}
 function patchBuildCheckout(){if(typeof window.buildCheckout==='function'&&!window.buildCheckout.__nd17){const old=window.buildCheckout;window.buildCheckout=function(){const r=old.apply(this,arguments);setTimeout(()=>{ensureMainForms();cartTotalSync();setupAutocomplete();bindFinishButton()},20);return r};window.buildCheckout.__nd17=true}}
 function bindFinishButton(){const btn=$('#modalFinalizar button[onclick*="finalizarPedidoModal"]');if(btn){btn.textContent='CONCLUIR PEDIDO E ENVIAR PARA NDBURGS';btn.onclick=ndFinish}}
 function ndFinish(){
   if(!cart().length)return alert('Seu carrinho está vazio.');
   const nome=$('#nomeModal')?.value.trim()||'', tel=$('#telefoneModal')?.value.trim()||'', tipo=$('#tipoPedidoModal')?.value||'ENTREGA', rua=$('#ruaModal')?.value||'', numero=$('#numeroModal')?.value.trim()||'', comp=$('#complementoModal')?.value.trim()||'', pagamento=$('#pagamentoModal')?.value||'', troco=$('#trocoModal')?.value||'', obs=$('#observacaoModal')?.value.trim()||'';
   if(!nome)return alert('Digite seu nome.'); const td=tel.replace(/\D/g,'');if(td.length<10||td.length>11)return alert('Digite um WhatsApp válido com DDD.');
   const aStreet=tipo==='ENTREGA'?(rua||addr().street):'';if(tipo==='ENTREGA'&&(!aStreet||!numero))return alert('Complete seu endereço.');if(!pagamento)return alert('Escolha uma forma de pagamento.');
   const f=tipo==='ENTREGA'?Number((window.taxas||{})[aStreet]||0):0,sub=subtotal(),total=sub+f;if(sub<11.90)return alert('O pedido mínimo é R$ 11,90. Faltam '+money(11.90-sub)+'.');
   const lines=['NOVO PEDIDO - ND BURGS','CLIENTE: '+nome,'WHATSAPP: '+tel,'TIPO: '+(tipo==='ENTREGA'?'DELIVERY':'RETIRADA')];
   if(tipo==='ENTREGA'){lines.push('ENDEREÇO: '+aStreet+', Nº '+numero);if(comp)lines.push('COMPLEMENTO: '+comp)}
   lines.push('', 'ITENS DO PEDIDO');
   cart().forEach(i=>{
     const qty=Number(i.quantidade)||1;
     const itemTotal=(Number(i.preco)||0)*qty;
     lines.push(qty+'x '+i.nome+' - '+money(itemTotal));
     if(Array.isArray(i.detalhes)&&i.detalhes.length) lines.push('  '+i.detalhes.join(', '));
   });
   lines.push('','SUBTOTAL: '+money(sub),'TAXA DE ENTREGA: '+money(f),'TOTAL DO PEDIDO: '+money(total),'PAGAMENTO: '+pagamento);if(pagamento==='DINHEIRO'&&troco)lines.push('TROCO PARA: '+money(Number(troco)));if(obs)lines.push('OBSERVAÇÃO: '+obs);lines.push('','ND BURGS');
   try{localStorage.setItem('ndburgs_ultimo_pedido',JSON.stringify(cart()))}catch(e){}
   try{if(Array.isArray(window.carrinho))window.carrinho.length=0;localStorage.removeItem('carrinho');localStorage.removeItem('ndburgs_carrinho')}catch(e){}
   const url='https://wa.me/5511963973846?text='+encodeURIComponent(lines.join('\n'));try{if(typeof window.clearCart==='function')window.clearCart()}catch(e){};window.location.href=url;
 }
 window.nd17Finish=ndFinish;
 function keepOnlyBest(){
   $$('.nd-fx-bestseller').forEach(x=>x.style.display='none');
   $$('.nd-r3-badge').forEach(x=>x.style.display='none');
   $$('.produto').forEach(card=>{const n=norm(card.querySelector('h3')?.textContent);if(n==='COMBO MAIS VENDIDO'&&!card.querySelector('.nd17-best')){const b=document.createElement('span');b.className='nd17-best';b.textContent='MAIS VENDIDO';card.appendChild(b)}})
 }
 function init(){
   setupAutocomplete();patchOpenCart();patchBuildCheckout();keepOnlyBest();ensureMainForms();cartTotalSync();updateBar();bindFinishButton();
   if(!localStorage.getItem('nd17_tipo'))showGate();
   setTimeout(()=>{patchOpenCart();patchBuildCheckout();setupAutocomplete();keepOnlyBest();ensureMainForms();cartTotalSync();bindFinishButton()},500);
   setInterval(()=>{patchOpenCart();patchBuildCheckout();keepOnlyBest();ensureMainForms();cartTotalSync();bindFinishButton()},1000);
 }
 document.addEventListener('DOMContentLoaded',()=>{init();$('#nd17GateSave')?.addEventListener('click',()=>saveGate('ENTREGA'));$('#nd17GatePickup')?.addEventListener('click',()=>saveGate('RETIRADA'));});
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

</body>
</html>
