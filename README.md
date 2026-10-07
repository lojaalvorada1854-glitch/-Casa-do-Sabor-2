# -Casa-do-Sabor-2
Sistema Casa do Sabor dois
-Casa-do-Sabor-2/
├── index.html
├── README.md
└── ... 
index.html
<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<meta name="theme-color" content="#f2c300">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<title>Casa do Sabor</title>

<style>
*{box-sizing:border-box}

body{
  margin:0;
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;
  background:#f5f3ee;
  color:#171717;
}

header{
  background:#f2c300;
  padding:18px 15px;
  position:sticky;
  top:0;
  z-index:10;
  box-shadow:0 2px 8px #0002;
}

h1{
  margin:0;
  font-size:25px;
}

.sub{
  margin-top:4px;
  color:#5b351e;
  font-weight:600;
}

nav{
  display:flex;
  gap:8px;
  overflow-x:auto;
  padding:12px 0 0;
}

nav button{
  border:0;
  border-radius:10px;
  padding:10px 13px;
  font-weight:800;
  background:#fff;
  white-space:nowrap;
}

main{
  max-width:1100px;
  margin:auto;
  padding:15px;
}

.view{
  display:none;
}

.view.active{
  display:block;
}

.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(150px,1fr));
  gap:12px;
}

.card{
  background:#fff;
  border-radius:15px;
  padding:15px;
  margin-bottom:12px;
  box-shadow:0 2px 8px #0001;
}

.kpi{
  font-size:26px;
  font-weight:900;
}

.muted{
  color:#666;
  font-size:13px;
}

button{
  cursor:pointer;
}

.btn{
  border:0;
  border-radius:11px;
  padding:11px 14px;
  font-weight:800;
}

.primary{
  background:#f2c300;
  color:#171717;
}

.dark{
  background:#171717;
  color:#fff;
}

.light{
  background:#eee;
}

.danger{
  background:#c62828;
  color:#fff;
}

.table{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(140px,1fr));
  gap:10px;
}

.mesa{
  background:#fff;
  border:2px solid #ddd;
  border-radius:14px;
  padding:13px;
}

.aberta{
  border-color:#f2c300;
}

input,select{
  width:100%;
  padding:11px;
  border:1px solid #ccc;
  border-radius:10px;
  font-size:16px;
  margin:5px 0 10px;
  background:#fff;
}

.row{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
}

.item{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
  padding:9px 0;
  border-bottom:1px solid #eee;
}

.total{
  text-align:right;
  font-size:22px;
  font-weight:900;
  margin-top:12px;
}

.badge{
  display:inline-block;
  padding:5px 8px;
  border-radius:20px;
  background:#eee;
  font-size:12px;
  font-weight:800;
}

.badge.open{
  background:#f2c300;
}

footer{
  text-align:center;
  color:#777;
  padding:25px;
}

hr{
  border:0;
  border-top:1px solid #eee;
  margin:15px 0;
}

@media(max-width:600px){
  .row{
    grid-template-columns:1fr;
  }

  h1{
    font-size:22px;
  }

  .btn{
    padding:10px 12px;
  }
}
</style>
</head>

<body>

<header>
  <h1>🍽️ Casa do Sabor</h1>
  <div class="sub">Sistema de Gestão • Versão Web</div>

  <nav>
    <button onclick="show('inicio')">Início</button>
    <button onclick="show('mesas')">Mesas</button>
    <button onclick="show('vendas')">Vendas</button>
    <button onclick="show('caixa')">Caixa</button>
    <button onclick="show('produtos')">Produtos</button>
    <button onclick="show('estoque')">Estoque</button>
  </nav>
</header>

<main>

<!-- INÍCIO -->

<section id="inicio" class="view active">

  <h2>Painel da Casa do Sabor</h2>

  <div class="grid">

    <div class="card">
      <div class="muted">Mesas abertas</div>
      <div class="kpi" id="openTables">0</div>
      <div class="muted">de 35 mesas</div>
    </div>

    <div class="card">
      <div class="muted">Total de vendas</div>
      <div class="kpi" id="salesTotal">R$ 0,00</div>
    </div>

    <div class="card">
      <div class="muted">Total recebido</div>
      <div class="kpi" id="cashTotal">R$ 0,00</div>
    </div>

    <div class="card">
      <div class="muted">Pedidos</div>
      <div class="kpi" id="orderCount">0</div>
    </div>

  </div>

  <div class="card">

    <h3>Acesso rápido</h3>

    <button class="btn primary" onclick="show('mesas')">
      🪑 Abrir mesas
    </button>

    <button class="btn dark" onclick="show('vendas')">
      🧾 Novo pedido
    </button>

    <button class="btn light" onclick="show('caixa')">
      💰 Caixa
    </button>

  </div>

  <div class="card">

    <h3>Casa do Sabor</h3>

    <p>
      Sistema preparado para uso no celular, iPhone, computador e Safari.
    </p>

    <p class="muted">
      Esta versão funciona diretamente no navegador e salva os dados
      localmente neste aparelho.
    </p>

  </div>

</section>


<!-- MESAS -->

<section id="mesas" class="view">

  <h2>🪑 35 Mesas</h2>

  <div class="card">

    <p class="muted">
      Mesas 1 a 10: fundos / próximo ao caixa.
      Mesas 11 a 35: frente do restaurante.
    </p>

    <p class="muted">
      Cada mesa possui as cadeiras A, B, C e D para contas individuais.
    </p>

  </div>

  <div id="tableGrid" class="table"></div>

</section>


<!-- VENDAS -->

<section id="vendas" class="view">

  <h2>🧾 Novo Pedido</h2>

  <div class="card">

    <label><b>Mesa</b></label>

    <select id="saleTable"></select>


    <label><b>Cadeira</b></label>

    <select id="saleSeat">

      <option>A</option>
      <option>B</option>
      <option>C</option>
      <option>D</option>

    </select>

    <hr>

    <h3>Produtos</h3>

    <div id="saleProducts"></div>

    <hr>

    <h3>Pedido atual</h3>

    <div id="draft"></div>

    <div class="total" id="draftTotal">
      Total: R$ 0,00
    </div>

    <br>

    <button class="btn primary" onclick="saveOrder()">
      ✅ Registrar pedido
    </button>

    <button class="btn light" onclick="clearDraft()">
      Limpar
    </button>

  </div>

</section>


<!-- CAIXA -->

<section id="caixa" class="view">

  <h2>💰 Caixa e Pagamento</h2>

  <div class="card">

    <div class="row">

      <div>

        <label><b>Valor recebido</b></label>

        <input
          id="payValue"
          type="number"
          step="0.01"
          placeholder="0,00"
        >

      </div>

      <div>

        <label><b>Forma de pagamento</b></label>

        <select id="payMethod">

          <option>Dinheiro</option>
          <option>Pix</option>
          <option>Débito</option>
          <option>Crédito</option>

        </select>

      </div>

    </div>

    <button class="btn primary" onclick="addPayment()">
      Registrar recebimento
    </button>

  </div>


  <div class="card">

    <h3>Recebimentos</h3>

    <div id="payments"></div>

  </div>

</section>


<!-- PRODUTOS -->

<section id="produtos" class="view">

  <h2>🍛 Cadastro de Produtos</h2>

  <div class="card">

    <div class="row">

      <div>

        <label><b>Produto</b></label>

        <input
          id="newName"
          placeholder="Ex.: PF"
        >

      </div>

      <div>

        <label><b>Preço</b></label>

        <input
          id="newPrice"
          type="number"
          step="0.01"
          placeholder="25,00"
        >

      </div>

    </div>

    <button class="btn primary" onclick="addProduct()">
      Cadastrar produto
    </button>

  </div>


  <div id="productList" class="grid"></div>

</section>


<!-- ESTOQUE -->

<section id="estoque" class="view">

  <h2>📦 Estoque</h2>

  <div class="card">

    <p>
      Produtos cadastrados no sistema:
    </p>

    <p class="muted">
      A estrutura está preparada para evoluir para compras,
      fornecedores, notas fiscais, estoque mínimo, entradas,
      saídas e financeiro completo.
    </p>

    <div id="stockList"></div>

  </div>

</section>

</main>


<footer>
  Casa do Sabor • Sistema de Gestão • 2026
</footer>


<script>

/* =====================================================
   BANCO LOCAL DO SISTEMA
   ===================================================== */

var KEY = "casa_sabor_web_v2";


var db =
JSON.parse(localStorage.getItem(KEY) || "null")
||
{
  products:[
    ["PF",25],
    ["Coca-Cola 2L",15],
    ["Coca-Cola lata",6],
    ["Guaraná",6],
    ["Salgado",10],
    ["Sorvete",6],
    ["Suco de laranja",8],
    ["Doce",5]
  ],

  orders:[],

  payments:[],

  tables:{}
};


var draft=[];


/* =====================================================
   SALVAR
   ===================================================== */

function save(){

  localStorage.setItem(
    KEY,
    JSON.stringify(db)
  );

  render();

}


/* =====================================================
   FORMATAÇÃO DE DINHEIRO
   ===================================================== */

function money(value){

  return Number(value || 0).toLocaleString(
    "pt-BR",
    {
      style:"currency",
      currency:"BRL"
    }
  );

}


/* =====================================================
   NAVEGAÇÃO
   ===================================================== */

function show(id){

  document
    .querySelectorAll(".view")
    .forEach(function(section){

      section.classList.remove("active");

    });


  var target=document.getElementById(id);

  if(target){
    target.classList.add("active");
  }


  render();

}


/* =====================================================
   RENDER PRINCIPAL
   ===================================================== */

function render(){

  var totalSales =
    db.orders.reduce(
      function(total,order){
        return total + Number(order.total || 0);
      },
      0
    );


  var totalCash =
    db.payments.reduce(
      function(total,payment){
        return total + Number(payment.value || 0);
      },
      0
    );


  document.getElementById(
    "salesTotal"
  ).textContent=money(totalSales);


  document.getElementById(
    "cashTotal"
  ).textContent=money(totalCash);


  document.getElementById(
    "orderCount"
  ).textContent=db.orders.length;


  var open=Object.keys(db.tables)
    .filter(function(key){

      return db.tables[key] &&
             db.tables[key].open;

    }).length;


  document.getElementById(
    "openTables"
  ).textContent=open;


  renderTables();

  renderSaleProducts();

  renderDraft();

  renderProducts();

  renderPayments();

  renderStock();

}


/* =====================================================
   MESAS
   ===================================================== */

function renderTables(){

  var html="";


  for(var i=1;i<=35;i++){

    var table=db.tables[i];

    var open =
      table &&
      table.open;


    html +=

      '<div class="mesa '+
      (open ? "aberta" : "")+
      '">' +

      '<b>Mesa '+i+'</b>' +

      '<div class="muted">'+
      (i<=10
        ? "Fundos / caixa"
        : "Frente")+
      '</div>' +

      '<br>' +

      '<span class="badge '+
      (open ? "open" : "")+
      '">'+
      (open ? "ABERTA" : "LIVRE")+
      '</span>' +

      '<br><br>' +

      '<button class="btn primary" '+
      'onclick="openTable('+i+')">'+

      (open
        ? "Fazer pedido"
        : "Abrir mesa")+

      '</button>' +

      '</div>';

  }


  document.getElementById(
    "tableGrid"
  ).innerHTML=html;

}


/* =====================================================
   ABRIR MESA
   ===================================================== */

function openTable(number){

  if(!db.tables[number]){

    db.tables[number]={
      open:true,
      items:[]
    };

  }else{

    db.tables[number].open=true;

  }


  save();


  document.getElementById(
    "saleTable"
  ).value=number;


  show("vendas");

}


/* =====================================================
   PRODUTOS DO PEDIDO
   ===================================================== */

function renderSaleProducts(){

  var tableOptions="";


  for(var i=1;i<=35;i++){

    tableOptions +=
      '<option value="'+i+'">'+
      'Mesa '+i+
      '</option>';

  }


  document.getElementById(
    "saleTable"
  ).innerHTML=tableOptions;


  var html="";


  for(var j=0;
      j<db.products.length;
      j++){

    var product=db.products[j];


    html +=

      '<div class="item">' +

      '<span>' +

      '<b>'+escapeHtml(product[0])+'</b>' +

      '<br>' +

      '<span class="muted">'+
      money(product[1])+
      '</span>' +

      '</span>' +

      '<button class="btn primary" '+
      'onclick="addDraft('+j+')">'+

      'Adicionar'+

      '</button>' +

      '</div>';

  }


  document.getElementById(
    "saleProducts"
  ).innerHTML=html;

}


/* =====================================================
   ADICIONAR ITEM AO PEDIDO
   ===================================================== */

function addDraft(index){

  var product=db.products[index];

  var found=null;


  for(var i=0;i<draft.length;i++){

    if(
      draft[i].name === product[0]
    ){

      found=draft[i];

      break;

    }

  }


  if(found){

    found.qty++;

  }else{

    draft.push({

      name:product[0],

      price:Number(product[1]),

      qty:1

    });

  }


  renderDraft();

}


/* =====================================================
   MOSTRAR PEDIDO
   ===================================================== */

function renderDraft(){

  var html="";

  var total=0;


  for(var i=0;i<draft.length;i++){

    var item=draft[i];

    var value=
      Number(item.price) *
      Number(item.qty);


    total += value;


    html +=

      '<div class="item">' +

      '<span>' +

      item.qty+
      "x "+
      escapeHtml(item.name) +

      '</span>' +

      '<b>'+
      money(value)+
      '</b>' +

      '</div>';

  }


  if(!html){

    html=
      '<p class="muted">'+
      'Nenhum item adicionado.'+
      '</p>';

  }


  document.getElementById(
    "draft"
  ).innerHTML=html;


  document.getElementById(
    "draftTotal"
  ).textContent=
    "Total: "+money(total);

}


/* =====================================================
   LIMPAR PEDIDO
   ===================================================== */

function clearDraft(){

  draft=[];

  renderDraft();

}


/* =====================================================
   REGISTRAR PEDIDO
   ===================================================== */

function saveOrder(){

  if(!draft.length){

    alert(
      "Adicione pelo menos um produto."
    );

    return;

  }


  var table=
    Number(
      document.getElementById(
        "saleTable"
      ).value
    );


  var seat=
    document.getElementById(
      "saleSeat"
    ).value;


  var total=
    draft.reduce(
      function(sum,item){

        return sum +
          Number(item.price) *
          Number(item.qty);

      },
      0
    );


  if(!db.tables[table]){

    db.tables[table]={
      open:true,
      items:[]
    };

  }


  db.tables[table].open=true;


  draft.forEach(function(item){

    db.tables[table].items.push({

      seat:seat,

      name:item.name,

      price:item.price,

      qty:item.qty

    });

  });


  db.orders.push({

    date:new Date().toISOString(),

    table:table,

    seat:seat,

    total:total,

    items:JSON.parse(
      JSON.stringify(draft)
    )

  });


  draft=[];


  save();


  alert(
    "Pedido registrado na Mesa "+
    table+
    ", cadeira "+
    seat+
    "."
  );


  show("mesas");

}


/* =====================================================
   PAGAMENTO
   ===================================================== */

function addPayment(){

  var value=
    Number(
      document.getElementById(
        "payValue"
      ).value
    );


  var method=
    document.getElementById(
      "payMethod"
    ).value;


  if(!value || value<=0){

    alert(
      "Informe um valor válido."
    );

    return;

  }


  db.payments.push({

    date:new Date().toISOString(),

    value:value,

    method:method

  });


  document.getElementById(
    "payValue"
  ).value="";


  save();


  alert(
    "Recebimento registrado."
  );

}


/* =====================================================
   LISTA DE PAGAMENTOS
   ===================================================== */

function renderPayments(){

  var html="";


  var start=
    Math.max(
      0,
      db.payments.length-20
    );


  for(
    var i=db.payments.length-1;
    i>=start;
    i--
  ){

    var payment=db.payments[i];


    html +=

      '<div class="item">' +

      '<span>' +

      '<b>'+
      escapeHtml(payment.method)+
      '</b>' +

      '<br>' +

      '<small>'+
      new Date(
        payment.date
      ).toLocaleString("pt-BR")+
      '</small>' +

      '</span>' +

      '<b>'+
      money(payment.value)+
      '</b>' +

      '</div>';

  }


  if(!html){

    html=
      '<p class="muted">'+
      'Nenhum recebimento registrado.'+
      '</p>';

  }


  document.getElementById(
    "payments"
  ).innerHTML=html;

}


/* =====================================================
   CADASTRO DE PRODUTO
   ===================================================== */

function addProduct(){

  var name=
    document.getElementById(
      "newName"
    ).value.trim();


  var price=
    Number(
      document.getElementById(
        "newPrice"
      ).value
    );


  if(!name){

    alert(
      "Informe o nome do produto."
    );

    return;

  }


  if(!price || price<=0){

    alert(
      "Informe um preço válido."
    );

    return;

  }


  db.products.push([
    name,
    price
  ]);


  document.getElementById(
    "newName"
  ).value="";


  document.getElementById(
    "newPrice"
  ).value="";


  save();


  alert(
    "Produto cadastrado."
  );

}


/* =====================================================
   LISTA DE PRODUTOS
   ===================================================== */

function renderProducts(){

  var html="";


  for(
    var i=0;
    i<db.products.length;
    i++
  ){

    var product=db.products[i];


    html +=

      '<div class="card">' +

      '<b>'+
      escapeHtml(product[0])+
      '</b>' +

      '<div class="muted">'+
      money(product[1])+
      '</div>' +

      '</div>';

  }


  document.getElementById(
    "productList"
  ).innerHTML=html;

}


/* =====================================================
   ESTOQUE
   ===================================================== */

function renderStock(){

  var html="";


  for(
    var i=0;
    i<db.products.length;
    i++
  ){

    var product=db.products[i];


    html +=

      '<div class="item">' +

      '<span>'+
      escapeHtml(product[0])+
      '</span>' +

      '<b>'+
      'Cadastrado'+
      '</b>' +

      '</div>';

  }


  document.getElementById(
    "stockList"
  ).innerHTML=
    html ||
    '<p class="muted">Nenhum produto.</p>';

}


/* =====================================================
   SEGURANÇA PARA TEXTO DIGITADO
   ===================================================== */

function escapeHtml(text){

  return String(text)
    .replace(/&/g,"&amp;")
    .replace(/</g,"&lt;")
    .replace(/>/g,"&gt;")
    .replace(/"/g,"&quot;")
    .replace(/'/g,"&#039;");

}


/* =====================================================
   INICIALIZAÇÃO
   ===================================================== */

render();

</script>

</body>
</html>