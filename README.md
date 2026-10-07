<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<meta name="theme-color" content="#f2c300">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Casa do Sabor">

<title>Casa do Sabor</title>

<style>
* {
  box-sizing: border-box;
}

:root {
  --amarelo: #f2c300;
  --amarelo-claro: #fff3b0;
  --marrom: #5b351e;
  --marrom-escuro: #321d10;
  --preto: #111111;
  --fundo: #f5f5f5;
  --branco: #ffffff;
  --verde: #16833b;
  --vermelho: #c62828;
  --azul: #1769aa;
  --cinza: #777777;
  --borda: #dddddd;
}

html,
body {
  margin: 0;
  padding: 0;
  background: var(--fundo);
  color: var(--preto);
  font-family:
    -apple-system,
    BlinkMacSystemFont,
    "Segoe UI",
    Arial,
    sans-serif;
}

body {
  min-height: 100vh;
  padding-bottom: 90px;
}

/* CABEÇALHO */

header {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: var(--amarelo);
  box-shadow: 0 2px 8px rgba(0,0,0,.18);
  padding:
    calc(12px + env(safe-area-inset-top))
    15px
    12px;
}

.header-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
}

.logo-area {
  display: flex;
  align-items: center;
  gap: 10px;
}

.logo {
  width: 48px;
  height: 48px;
  border-radius: 14px;
  background: var(--preto);
  color: var(--amarelo);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 24px;
  font-weight: 900;
}

.brand h1 {
  margin: 0;
  font-size: 22px;
  line-height: 1.1;
}

.brand small {
  display: block;
  margin-top: 3px;
  font-size: 12px;
  font-weight: 700;
  color: var(--marrom);
}

.header-actions {
  display: flex;
  gap: 6px;
}

.icon-button {
  border: 0;
  background: var(--branco);
  color: var(--preto);
  border-radius: 12px;
  width: 42px;
  height: 42px;
  font-size: 20px;
  font-weight: 800;
}

/* MENU */

.menu {
  display: flex;
  gap: 8px;
  overflow-x: auto;
  padding-top: 12px;
  scrollbar-width: none;
}

.menu::-webkit-scrollbar {
  display: none;
}

.menu button {
  flex: 0 0 auto;
  border: 0;
  border-radius: 12px;
  padding: 10px 14px;
  background: rgba(255,255,255,.75);
  color: var(--preto);
  font-weight: 800;
  font-size: 13px;
}

.menu button.active {
  background: var(--preto);
  color: var(--amarelo);
}

/* CONTEÚDO */

main {
  max-width: 1250px;
  margin: 0 auto;
  padding: 16px;
}

.section {
  display: none;
}

.section.active {
  display: block;
}

.section-title {
  margin: 5px 0 4px;
  font-size: 26px;
  font-weight: 900;
}

.section-subtitle {
  margin: 0 0 18px;
  color: var(--cinza);
}

/* CARDS */

.cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

.card {
  background: var(--branco);
  border: 1px solid var(--borda);
  border-radius: 16px;
  padding: 16px;
  box-shadow: 0 2px 5px rgba(0,0,0,.05);
}

.card-label {
  font-size: 13px;
  color: var(--cinza);
  font-weight: 700;
}

.card-value {
  margin-top: 7px;
  font-size: 25px;
  font-weight: 900;
}

.card-note {
  margin-top: 5px;
  font-size: 12px;
  color: var(--cinza);
}

/* PAINEL */

.panel {
  background: var(--branco);
  border: 1px solid var(--borda);
  border-radius: 16px;
  margin-top: 16px;
  padding: 16px;
  box-shadow: 0 2px 5px rgba(0,0,0,.04);
}

.panel h3 {
  margin: 0 0 14px;
}

/* BOTÕES */

button {
  cursor: pointer;
  font-family: inherit;
}

.btn {
  border: 0;
  border-radius: 10px;
  padding: 11px 15px;
  font-weight: 800;
  background: var(--amarelo);
  color: var(--preto);
}

.btn:hover {
  filter: brightness(.96);
}

.btn-dark {
  background: var(--preto);
  color: var(--branco);
}

.btn-brown {
  background: var(--marrom);
  color: var(--branco);
}

.btn-green {
  background: var(--verde);
  color: var(--branco);
}

.btn-red {
  background: var(--vermelho);
  color: var(--branco);
}

.btn-blue {
  background: var(--azul);
  color: var(--branco);
}

.btn-small {
  padding: 7px 9px;
  font-size: 12px;
}

/* MESAS */

.table-grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 12px;
}

.table-card {
  min-height: 135px;
  border-radius: 16px;
  border: 2px solid #ddd;
  background: var(--branco);
  padding: 13px;
  position: relative;
}

.table-card.open {
  border-color: var(--verde);
}

.table-card.busy {
  border-color: var(--vermelho);
}

.table-card.reserved {
  border-color: var(--azul);
}

.table-number {
  font-size: 22px;
  font-weight: 900;
}

.table-location {
  font-size: 11px;
  color: var(--cinza);
  margin-top: 2px;
}

.table-status {
  margin-top: 9px;
  font-size: 12px;
  font-weight: 900;
}

.table-total {
  margin-top: 5px;
  font-size: 17px;
  font-weight: 900;
}

.chairs {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 4px;
  margin-top: 8px;
}

.chair {
  border: 0;
  border-radius: 7px;
  background: #eee;
  padding: 5px 2px;
  font-weight: 900;
  font-size: 11px;
}

.chair.has-order {
  background: var(--amarelo);
}

/* FORMULÁRIOS */

.form-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 12px;
}

.field {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.field label {
  font-size: 12px;
  font-weight: 800;
}

input,
select,
textarea {
  width: 100%;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 11px;
  background: white;
  font: inherit;
}

textarea {
  min-height: 100px;
  resize: vertical;
}

/* PRODUTOS */

.product-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

.product-card {
  background: white;
  border: 1px solid var(--borda);
  border-radius: 14px;
  overflow: hidden;
}

.product-photo {
  height: 100px;
  background:
    linear-gradient(135deg, #fff1a1, #e7b900);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 38px;
}

.product-body {
  padding: 12px;
}

.product-name {
  font-weight: 900;
}

.product-category {
  color: var(--cinza);
  font-size: 12px;
  margin-top: 3px;
}

.product-price {
  margin-top: 8px;
  font-weight: 900;
  font-size: 18px;
}

/* TABELAS */

.table-wrap {
  overflow-x: auto;
}

.data-table {
  width: 100%;
  border-collapse: collapse;
  min-width: 600px;
}

.data-table th,
.data-table td {
  padding: 10px;
  border-bottom: 1px solid #ddd;
  text-align: left;
  font-size: 13px;
}

.data-table th {
  background: #fafafa;
  font-weight: 900;
}

/* PAGAMENTO */

.payment-options {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

.payment-option {
  border: 2px solid #ddd;
  border-radius: 12px;
  padding: 13px;
  text-align: center;
  background: white;
  font-weight: 900;
}

.payment-option.selected {
  border-color: var(--amarelo);
  background: var(--amarelo-claro);
}

/* MODAL */

.modal-backdrop {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,.55);
  z-index: 2000;
  display: none;
  align-items: center;
  justify-content: center;
  padding: 15px;
}

.modal-backdrop.show {
  display: flex;
}

.modal {
  width: min(650px, 100%);
  max-height: 90vh;
  overflow-y: auto;
  background: white;
  border-radius: 20px;
  padding: 18px;
}

.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
}

.modal-header h2 {
  margin: 0;
}

.close {
  border: 0;
  background: #eee;
  width: 38px;
  height: 38px;
  border-radius: 50%;
  font-size: 20px;
  font-weight: 900;
}

/* LISTA */

.list {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.list-item {
  background: #fafafa;
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 10px;
  display: flex;
  justify-content: space-between;
  gap: 10px;
}

/* ALERTA */

.alert {
  padding: 12px;
  border-radius: 10px;
  margin-bottom: 10px;
  font-weight: 700;
}

.alert-yellow {
  background: #fff4bd;
}

.alert-red {
  background: #ffe0e0;
  color: #8a0000;
}

.alert-green {
  background: #dff5e6;
  color: #11652d;
}

/* RODAPÉ */

.bottom-nav {
  position: fixed;
  z-index: 1500;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(255,255,255,.96);
  border-top: 1px solid #ddd;
  box-shadow: 0 -2px 8px rgba(0,0,0,.1);
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  padding:
    8px
    8px
    calc(8px + env(safe-area-inset-bottom));
}

.bottom-nav button {
  border: 0;
  background: transparent;
  padding: 5px;
  font-size: 11px;
  font-weight: 800;
}

.bottom-icon {
  display: block;
  font-size: 22px;
  margin-bottom: 2px;
}

.bottom-nav button.active {
  color: var(--marrom);
}

/* TOAST */

.toast {
  position: fixed;
  z-index: 3000;
  left: 50%;
  bottom: 100px;
  transform: translateX(-50%) translateY(20px);
  background: var(--preto);
  color: white;
  padding: 12px 18px;
  border-radius: 12px;
  opacity: 0;
  pointer-events: none;
  transition: .25s;
  font-weight: 700;
  max-width: 90%;
  text-align: center;
}

.toast.show {
  opacity: 1;
  transform: translateX(-50%) translateY(0);
}

/* RESPONSIVO */

@media (max-width: 900px) {
  .cards {
    grid-template-columns: repeat(2, 1fr);
  }

  .table-grid {
    grid-template-columns: repeat(3, 1fr);
  }

  .product-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 600px) {
  main {
    padding: 12px;
  }

  .cards {
    grid-template-columns: repeat(2, 1fr);
  }

  .card {
    padding: 12px;
  }

  .card-value {
    font-size: 20px;
  }

  .table-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 9px;
  }

  .table-card {
    min-height: 125px;
    padding: 10px;
  }

  .form-grid {
    grid-template-columns: 1fr;
  }

  .payment-options {
    grid-template-columns: repeat(2, 1fr);
  }

  .product-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .section-title {
    font-size: 23px;
  }
}

@media (max-width: 390px) {
  .table-grid {
    grid-template-columns: 1fr 1fr;
  }

  .product-grid {
    grid-template-columns: 1fr 1fr;
  }

  .brand h1 {
    font-size: 18px;
  }
}
</style>
</head>

<body>

<header>
  <div class="header-top">

    <div class="logo-area">
      <div class="logo">CS</div>

      <div class="brand">
        <h1>Casa do Sabor</h1>
        <small>Sistema de Gestão</small>
      </div>
    </div>

    <div class="header-actions">
      <button class="icon-button" onclick="showSection('config')" title="Configurações">⚙️</button>
    </div>

  </div>

  <nav class="menu">
    <button class="active" onclick="showSection('inicio', this)">Início</button>
    <button onclick="showSection('mesas', this)">Mesas</button>
    <button onclick="showSection('vendas', this)">Vendas</button>
    <button onclick="showSection('produtos', this)">Produtos</button>
    <button onclick="showSection('estoque', this)">Estoque</button>
    <button onclick="showSection('financeiro', this)">Financeiro</button>
    <button onclick="showSection('compras', this)">Compras</button>
    <button onclick="showSection('funcionarios', this)">Funcionários</button>
    <button onclick="showSection('delivery', this)">Delivery</button>
    <button onclick="showSection('relatorios', this)">Relatórios</button>
  </nav>
</header>

<main>

<!-- INÍCIO -->

<section id="inicio" class="section active">

  <h2 class="section-title">Painel do Restaurante</h2>
  <p class="section-subtitle">
    Visão geral da operação da Casa do Sabor.
  </p>

  <div class="cards">

    <div class="card">
      <div class="card-label">Vendas hoje</div>
      <div class="card-value" id="dashVendas">R$ 0,00</div>
      <div class="card-note">Total registrado</div>
    </div>

    <div class="card">
      <div class="card-label">Mesas abertas</div>
      <div class="card-value" id="dashMesas">0</div>
      <div class="card-note">De 35 mesas</div>
    </div>

    <div class="card">
      <div class="card-label">Pedidos</div>
      <div class="card-value" id="dashPedidos">0</div>
      <div class="card-note">Pedidos registrados</div>
    </div>

    <div class="card">
      <div class="card-label">Estoque baixo</div>
      <div class="card-value" id="dashEstoque">0</div>
      <div class="card-note">Produtos para comprar</div>
    </div>

  </div>

  <div class="panel">
    <h3>Acesso rápido</h3>

    <div style="display:flex;gap:8px;flex-wrap:wrap;">
      <button class="btn" onclick="showSection('mesas')">🍽️ Abrir Mesas</button>
      <button class="btn btn-green" onclick="novoPedido()">🧾 Novo Pedido</button>
      <button class="btn btn-blue" onclick="showSection('delivery')">🛵 Delivery</button>
      <button class="btn btn-brown" onclick="showSection('financeiro')">💰 Caixa</button>
    </div>
  </div>

  <div class="panel">
    <h3>Status da operação</h3>

    <div id="statusOperacao">
      <div class="alert alert-green">
        Sistema Casa do Sabor funcionando localmente neste navegador.
      </div>
    </div>
  </div>

</section>


<!-- MESAS -->

<section id="mesas" class="section">

  <h2 class="section-title">Mesas</h2>

  <p class="section-subtitle">
    35 mesas • 4 lugares individuais por mesa • A, B, C e D.
  </p>

  <div class="panel">

    <div style="display:flex;gap:8px;flex-wrap:wrap;">
      <button class="btn" onclick="filtrarMesas('todas')">Todas</button>
      <button class="btn btn-green" onclick="filtrarMesas('aberta')">Livres</button>
      <button class="btn btn-red" onclick="filtrarMesas('ocupada')">Ocupadas</button>
    </div>

  </div>

  <div id="tableGrid" class="table-grid"></div>

</section>


<!-- VENDAS -->

<section id="vendas" class="section">

  <h2 class="section-title">Vendas e Pedidos</h2>

  <p class="section-subtitle">
    Registro de pedidos, comandas e fechamento.
  </p>

  <div class="panel">

    <div style="display:flex;justify-content:space-between;align-items:center;gap:10px;flex-wrap:wrap;">
      <h3>Pedidos registrados</h3>
      <button class="btn" onclick="novoPedido()">+ Novo pedido</button>
    </div>

    <div class="table-wrap">
      <table class="data-table">
        <thead>
          <tr>
            <th>Pedido</th>
            <th>Origem</th>
            <th>Cliente/Mesa</th>
            <th>Total</th>
            <th>Status</th>
            <th>Ação</th>
          </tr>
        </thead>

        <tbody id="ordersTable"></tbody>

      </table>
    </div>

  </div>

</section>


<!-- PRODUTOS -->

<section id="produtos" class="section">

  <h2 class="section-title">Produtos e Cardápio</h2>

  <p class="section-subtitle">
    Cadastro de PF, marmitas, bebidas, salgados, sorvetes e acompanhamentos.
  </p>

  <div class="panel">

    <button class="btn" onclick="abrirProdutoModal()">
      + Cadastrar produto
    </button>

  </div>

  <div id="productGrid" class="product-grid"></div>

</section>


<!-- ESTOQUE -->

<section id="estoque" class="section">

  <h2 class="section-title">Controle de Estoque</h2>

  <p class="section-subtitle">
    Estoque atual, mínimo e necessidade de compra.
  </p>

  <div class="cards">

    <div class="card">
      <div class="card-label">Itens cadastrados</div>
      <div class="card-value" id="estoqueItens">0</div>
    </div>

    <div class="card">
      <div class="card-label">Estoque baixo</div>
      <div class="card-value" id="estoqueBaixo">0</div>
    </div>

    <div class="card">
      <div class="card-label">Valor estimado</div>
      <div class="card-value" id="estoqueValor">R$ 0,00</div>
    </div>

  </div>

  <div class="panel">

    <h3>Estoque</h3>

    <div class="table-wrap">

      <table class="data-table">

        <thead>
          <tr>
            <th>Produto</th>
            <th>Categoria</th>
            <th>Atual</th>
            <th>Mínimo</th>
            <th>Situação</th>
            <th>Ação</th>
          </tr>
        </thead>

        <tbody id="stockTable"></tbody>

      </table>

    </div>

  </div>

</section>


<!-- FINANCEIRO -->

<section id="financeiro" class="section">

  <h2 class="section-title">Caixa e Financeiro</h2>

  <p class="section-subtitle">
    Vendas, recebimentos e pagamentos.
  </p>

  <div class="cards">

    <div class="card">
      <div class="card-label">Entradas</div>
      <div class="card-value" id="financeEntradas">R$ 0,00</div>
    </div>

    <div class="card">
      <div class="card-label">Saídas</div>
      <div class="card-value" id="financeSaidas">R$ 0,00</div>
    </div>

    <div class="card">
      <div class="card-label">Saldo</div>
      <div class="card-value" id="financeSaldo">R$ 0,00</div>
    </div>

    <div class="card">
      <div class="card-label">Pix</div>
      <div class="card-value" id="financePix">R$ 0,00</div>
    </div>

  </div>

  <div class="panel">

    <h3>Pagamento dividido</h3>

    <div class="form-grid">

      <div class="field">
        <label>Dinheiro</label>
        <input id="payCash" type="number" step="0.01" value="0">
      </div>

      <div class="field">
        <label>Pix</label>
        <input id="payPix" type="number" step="0.01" value="0">
      </div>

      <div class="field">
        <label>Débito</label>
        <input id="payDebit" type="number" step="0.01" value="0">
      </div>

      <div class="field">
        <label>Crédito</label>
        <input id="payCredit" type="number" step="0.01" value="0">
      </div>

      <div class="field">
        <label>Total da conta</label>
        <input id="payTotal" type="number" step="0.01" value="0">
      </div>

      <div class="field">
        <label>Troco</label>
        <input id="payChange" type="number" step="0.01" value="0" readonly>
      </div>

    </div>

    <br>

    <button class="btn btn-green" onclick="calcularPagamento()">
      Calcular pagamento
    </button>

    <button class="btn btn-dark" onclick="registrarPagamento()">
      Registrar pagamento
    </button>

    <div id="paymentResult" style="margin-top:12px;"></div>

  </div>

  <div class="panel">

    <h3>Movimentações</h3>

    <div class="table-wrap">

      <table class="data-table">

        <thead>
          <tr>
            <th>Data</th>
            <th>Descrição</th>
            <th>Forma</th>
            <th>Valor</th>
          </tr>
        </thead>

        <tbody id="financeTable"></tbody>

      </table>

    </div>

  </div>

</section>


<!-- COMPRAS -->

<section id="compras" class="section">

  <h2 class="section-title">Compras e Fornecedores</h2>

  <p class="section-subtitle">
    Notas, fornecedores e compromissos financeiros.
  </p>

  <div class="panel">

    <button class="btn" onclick="abrirCompraModal()">
      + Lançar compra
    </button>

  </div>

  <div class="panel">

    <div class="table-wrap">

      <table class="data-table">

        <thead>
          <tr>
            <th>Fornecedor</th>
            <th>Nota</th>
            <th>Vencimento</th>
            <th>Parcelas</th>
            <th>Valor</th>
            <th>Status</th>
          </tr>
        </thead>

        <tbody id="purchaseTable"></tbody>

      </table>

    </div>

  </div>

</section>


<!-- FUNCIONÁRIOS -->

<section id="funcionarios" class="section">

  <h2 class="section-title">Funcionários</h2>

  <p class="section-subtitle">
    Equipe, ponto, horas e folha.
  </p>

  <div class="cards">

    <div class="card">
      <div class="card-label">Caixa</div>
      <div class="card-value">4</div>
    </div>

    <div class="card">
      <div class="card-label">Garçons</div>
      <div class="card-value">4</div>
    </div>

    <div class="card">
      <div class="card-label">Cozinha</div>
      <div class="card-value">2</div>
    </div>

    <div class="card">
      <div class="card-label">Total</div>
      <div class="card-value">10</div>
    </div>

  </div>

  <div class="panel">

    <h3>Ponto e horas</h3>

    <div class="form-grid">

      <div class="field">
        <label>Funcionário</label>
        <select id="employeeSelect">
          <option>Funcionário 1</option>
          <option>Funcionário 2</option>
          <option>Funcionário 3</option>
          <option>Funcionário 4</option>
        </select>
      </div>

      <div class="field">
        <label>Entrada</label>
        <input id="timeIn" type="time">
      </div>

      <div class="field">
        <label>Saída</label>
        <input id="timeOut" type="time">
      </div>

      <div class="field">
        <label>Valor por hora</label>
        <input id="hourValue" type="number" step="0.01" value="10">
      </div>

    </div>

    <br>

    <button class="btn" onclick="calcularHoras()">
      Calcular horas
    </button>

    <div id="hoursResult" style="margin-top:12px;"></div>

  </div>

</section>


<!-- DELIVERY -->

<section id="delivery" class="section">

  <h2 class="section-title">Delivery</h2>

  <p class="section-subtitle">
    Entregadores, pedidos, endereço e acompanhamento.
  </p>

  <div class="cards">

    <div class="card">
      <div class="card-label">Pedidos delivery</div>
      <div class="card-value" id="deliveryCount">0</div>
    </div>

    <div class="card">
      <div class="card-label">Em preparo</div>
      <div class="card-value">0</div>
    </div>

    <div class="card">
      <div class="card-label">Em entrega</div>
      <div class="card-value">0</div>
    </div>

    <div class="card">
      <div class="card-label">Entregadores</div>
      <div class="card-value">0</div>
    </div>

  </div>

  <div class="panel">

    <button class="btn" onclick="novoDelivery()">
      + Novo Delivery
    </button>

  </div>

  <div class="panel">

    <div class="table-wrap">

      <table class="data-table">

        <thead>
          <tr>
            <th>Pedido</th>
            <th>Cliente</th>
            <th>Endereço</th>
            <th>Taxa</th>
            <th>Status</th>
          </tr>
        </thead>

        <tbody id="deliveryTable"></tbody>

      </table>

    </div>

  </div>

</section>


<!-- RELATÓRIOS -->

<section id="relatorios" class="section">

  <h2 class="section-title">Relatórios</h2>

  <p class="section-subtitle">
    Informações gerenciais da operação.
  </p>

  <div class="cards">

    <div class="card">
      <div class="card-label">Vendas</div>
      <div class="card-value" id="reportSales">R$ 0,00</div>
    </div>

    <div class="card">
      <div class="card-label">Ticket médio</div>
      <div class="card-value" id="reportTicket">R$ 0,00</div>
    </div>

    <div class="card">
      <div class="card-label">Pedidos</div>
      <div class="card-value" id="reportOrders">0</div>
    </div>

    <div class="card">
      <div class="card-label">Mesas</div>
      <div class="card-value">35</div>
    </div>

  </div>

  <div class="panel">

    <h3>Resumo</h3>

    <div class="alert alert-yellow">
      Os dados desta versão são armazenados no navegador através do
      armazenamento local. A próxima etapa pode ligar este sistema a um
      banco de dados online.
    </div>

  </div>

</section>


<!-- CONFIGURAÇÕES -->

<section id="config" class="section">

  <h2 class="section-title">Configurações</h2>

  <p class="section-subtitle">
    Configurações básicas do sistema.
  </p>

  <div class="panel">

    <div class="form-grid">

      <div class="field">
        <label>Nome do estabelecimento</label>
        <input id="configName" value="Casa do Sabor">
      </div>

      <div class="field">
        <label>Cidade</label>
        <input id="configCity" value="Morrinhos - Goiás">
      </div>

      <div class="field">
        <label>Horário de abertura</label>
        <input value="06:00" type="time">
      </div>

      <div class="field">
        <label>Horário de fechamento</label>
        <input value="20:00" type="time">
      </div>

      <div class="field">
        <label>Quantidade de mesas</label>
        <input value="35" type="number">
      </div>

      <div class="field">
        <label>Lugares por mesa</label>
        <input value="4" type="number">
      </div>

    </div>

    <br>

    <button class="btn btn-green" onclick="salvarConfiguracoes()">
      Salvar configurações
    </button>

    <button class="btn btn-red" onclick="limparDados()">
      Limpar dados de teste
    </button>

  </div>

</section>

</main>


<!-- NAVEGAÇÃO INFERIOR -->

<nav class="bottom-nav">

  <button class="active" onclick="showSection('inicio', null, this)">
    <span class="bottom-icon">🏠</span>
    Início
  </button>

  <button onclick="showSection('mesas', null, this)">
    <span class="bottom-icon">🍽️</span>
    Mesas
  </button>

  <button onclick="showSection('vendas', null, this)">
    <span class="bottom-icon">🧾</span>
    Vendas
  </button>

  <button onclick="showSection('financeiro', null, this)">
    <span class="bottom-icon">💰</span>
    Caixa
  </button>

  <button onclick="showSection('delivery', null, this)">
    <span class="bottom-icon">🛵</span>
    Delivery
  </button>

</nav>


<!-- MODAL -->

<div id="modalBackdrop" class="modal-backdrop">

  <div class="modal">

    <div class="modal-header">
      <h2 id="modalTitle">Casa do Sabor</h2>
      <button class="close" onclick="fecharModal()">×</button>
    </div>

    <div id="modalContent"></div>

  </div>

</div>


<div id="toast" class="toast"></div>


<script>
/* =========================================================
   CASA DO SABOR
   SISTEMA WEB - VERSÃO SINGLE FILE
   ========================================================= */


/* ---------- DADOS ---------- */

let tables = [];

let products = [
  {
    id: 1,
    name: "PF",
    category: "Pratos",
    price: 25,
    stock: 20,
    min: 10,
    emoji: "🍛"
  },
  {
    id: 2,
    name: "Guaraná",
    category: "Bebidas",
    price: 6,
    stock: 15,
    min: 8,
    emoji: "🥤"
  },
  {
    id: 3,
    name: "Salgado",
    category: "Salgados",
    price: 10,
    stock: 5,
    min: 10,
    emoji: "🥟"
  },
  {
    id: 4,
    name: "Sorvete",
    category: "Sobremesas",
    price: 6,
    stock: 12,
    min: 5,
    emoji: "🍦"
  },
  {
    id: 5,
    name: "Coca-Cola 2L",
    category: "Bebidas",
    price: 15,
    stock: 7,
    min: 10,
    emoji: "🥤"
  },
  {
    id: 6,
    name: "Coca-Cola Lata",
    category: "Bebidas",
    price: 6,
    stock: 25,
    min: 10,
    emoji: "🥤"
  },
  {
    id: 7,
    name: "Suco de Laranja",
    category: "Bebidas",
    price: 8,
    stock: 10,
    min: 5,
    emoji: "🍊"
  },
  {
    id: 8,
    name: "Doce",
    category: "Sobremesas",
    price: 5,
    stock: 4,
    min: 8,
    emoji: "🍮"
  }
];

let orders = [];

let finance = [];

let purchases = [];

let deliveries = [];

let orderCounter = 1;


/* ---------- INICIALIZAÇÃO ---------- */

function initTables() {

  tables = [];

  for (let i = 1; i <= 35; i++) {

    tables.push({
      id: i,
      location: i <= 10 ? "Fundos / Caixa" : "Salão / Frente",
      status: "aberta",
      chairs: {
        A: [],
        B: [],
        C: [],
        D: []
      }
    });

  }
}


/* ---------- LOCAL STORAGE ---------- */

function saveData() {

  const data = {
    tables,
    products,
    orders,
    finance,
    purchases,
    deliveries,
    orderCounter
  };

  localStorage.setItem(
    "casa_do_sabor_data",
    JSON.stringify(data)
  );
}


function loadData() {

  try {

    const raw = localStorage.getItem("casa_do_sabor_data");

    if (!raw) {

      initTables();

      return;
    }

    const data = JSON.parse(raw);

    tables = data.tables || [];

    products = data.products || products;

    orders = data.orders || [];

    finance = data.finance || [];

    purchases = data.purchases || [];

    deliveries = data.deliveries || [];

    orderCounter = data.orderCounter || 1;

    if (!tables.length) {
      initTables();
    }

  } catch (error) {

    console.error(error);

    initTables();

  }
}


/* ---------- FORMATAÇÃO ---------- */

function money(value) {

  return Number(value || 0).toLocaleString(
    "pt-BR",
    {
      style: "currency",
      currency: "BRL"
    }
  );

}


/* ---------- NAVEGAÇÃO ---------- */

function showSection(id, clickedButton, bottomButton) {

  document.querySelectorAll(".section")
    .forEach(section => {
      section.classList.remove("active");
    });

  const section = document.getElementById(id);

  if (section) {
    section.classList.add("active");
  }

  document.querySelectorAll(".menu button")
    .forEach(button => {
      button.classList.remove("active");
    });

  if (clickedButton) {
    clickedButton.classList.add("active");
  }

  document.querySelectorAll(".bottom-nav button")
    .forEach(button => {
      button.classList.remove("active");
    });

  if (bottomButton) {
    bottomButton.classList.add("active");
  }

  refreshAll();

  window.scrollTo({
    top: 0,
    behavior: "smooth"
  });

}


/* ---------- MESAS ---------- */

function renderTables(filter = "todas") {

  const grid = document.getElementById("tableGrid");

  if (!grid) return;

  grid.innerHTML = "";

  tables
    .filter(table => {

      if (filter === "todas") return true;

      return table.status === filter;

    })
    .forEach(table => {

      const total = getTableTotal(table);

      const card = document.createElement("div");

      card.className =
        "table-card " +
        (table.status === "ocupada"
          ? "busy"
          : table.status === "aberta"
            ? "open"
            : "reserved");

      card.innerHTML = `

        <div class="table-number">
          Mesa ${table.id}
        </div>

        <div class="table-location">
          ${table.location}
        </div>

        <div class="table-status">
          ${table.status === "aberta"
            ? "LIVRE"
            : table.status === "ocupada"
              ? "OCUPADA"
              : "RESERVADA"}
        </div>

        <div class="table-total">
          ${money(total)}
        </div>

        <div class="chairs">

          ${["A","B","C","D"].map(chair => `

            <button
              class="chair ${table.chairs[chair].length ? "has-order" : ""}"
              onclick="event.stopPropagation(); abrirMesa(${table.id}, '${chair}')">
              ${chair}
            </button>

          `).join("")}

        </div>

        <br>

        <button
          class="btn btn-small"
          onclick="abrirMesa(${table.id})">
          Abrir mesa
        </button>

      `;

      grid.appendChild(card);

    });

}


function filtrarMesas(filter) {

  renderTables(filter);

}


function getTableTotal(table) {

  let total = 0;

  Object.values(table.chairs)
    .forEach(items => {

      items.forEach(item => {

        total += Number(item.price || 0) *
                 Number(item.quantity || 1);

      });

    });

  return total;

}


/* ---------- ABRIR MESA ---------- */

function abrirMesa(tableId, selectedChair) {

  const table = tables.find(t => t.id === tableId);

  if (!table) return;

  if (!selectedChair) {
    selectedChair = "A";
  }

  openModal(
    `Mesa ${tableId} • Cadeira ${selectedChair}`,
    `
      <div class="alert alert-yellow">
        Conta individual por cadeira: A, B, C e D.
      </div>

      <div class="field">
        <label>Cadeira</label>

        <select id="chairSelect">

          <option value="A" ${selectedChair === "A" ? "selected" : ""}>A</option>
          <option value="B" ${selectedChair === "B" ? "selected" : ""}>B</option>
          <option value="C" ${selectedChair === "C" ? "selected" : ""}>C</option>
          <option value="D" ${selectedChair === "D" ? "selected" : ""}>D</option>

        </select>
      </div>

      <br>

      <div class="field">

        <label>Produto</label>

        <select id="tableProduct">

          ${products.map(product => `
            <option value="${product.id}">
              ${product.name} — ${money(product.price)}
            </option>
          `).join("")}

        </select>

      </div>

      <br>

      <div class="field">

        <label>Quantidade</label>

        <input
          id="tableQuantity"
          type="number"
          min="1"
          value="1">

      </div>

      <br>

      <button
        class="btn btn-green"
        onclick="adicionarItemMesa(${tableId})">
        Adicionar ao pedido
      </button>

      <button
        class="btn btn-dark"
        onclick="fecharContaMesa(${tableId})">
        Fechar conta
      </button>

      <div id="mesaItems" style="margin-top:16px;"></div>

    `
  );

  renderMesaItems(tableId);

}


function adicionarItemMesa(tableId) {

  const table = tables.find(t => t.id === tableId);

  const chair =
    document.getElementById("chairSelect").value;

  const productId =
    Number(document.getElementById("tableProduct").value);

  const quantity =
    Number(document.getElementById("tableQuantity").value || 1);

  const product =
    products.find(p => p.id === productId);

  if (!product) return;

  table.chairs[chair].push({
    productId: product.id,
    name: product.name,
    price: product.price,
    quantity
  });

  table.status = "ocupada";

  saveData();

  renderMesaItems(tableId);

  refreshAll();

  toast(
    `${product.name} adicionado à Mesa ${tableId}, cadeira ${chair}.`
  );

}


function renderMesaItems(tableId) {

  const table = tables.find(t => t.id === tableId);

  const container =
    document.getElementById("mesaItems");

  if (!table || !container) return;

  let html = "";

  ["A","B","C","D"].forEach(chair => {

    if (!table.chairs[chair].length) return;

    html += `
      <div class="panel" style="margin-top:10px;">
        <strong>Cadeira ${chair}</strong>
    `;

    table.chairs[chair].forEach(item => {

      html += `
        <div class="list-item">
          <span>
            ${item.quantity} × ${item.name}
          </span>

          <strong>
            ${money(item.price * item.quantity)}
          </strong>
        </div>
      `;

    });

    const subtotal =
      table.chairs[chair]
        .reduce(
          (sum,item) =>
            sum + item.price * item.quantity,
          0
        );

    html += `
        <div style="text-align:right;margin-top:8px;font-weight:900;">
          ${money(subtotal)}
        </div>
      </div>
    `;

  });

  if (!html) {

    html = `
      <div class="alert alert-yellow">
        Nenhum item lançado nesta mesa.
      </div>
    `;

  }

  container.innerHTML = html;

}


function fecharContaMesa(tableId) {

  const table = tables.find(t => t.id === tableId);

  const total = getTableTotal(table);

  if (total <= 0) {

    toast("A mesa ainda não possui itens.");

    return;
  }

  openModal(
    `Fechamento Mesa ${tableId}`,
    `
      <div class="alert alert-green">
        Total da mesa: <strong>${money(total)}</strong>
      </div>

      <div class="payment-options">

        <button
          class="payment-option"
          onclick="selecionarPagamento('Dinheiro')">
          💵 Dinheiro
        </button>

        <button
          class="payment-option"
          onclick="selecionarPagamento('Pix')">
          📱 Pix
        </button>

        <button
          class="payment-option"
          onclick="selecionarPagamento('Débito')">
          💳 Débito
        </button>

        <button
          class="payment-option"
          onclick="selecionarPagamento('Crédito')">
          💳 Crédito
        </button>

      </div>

      <br>

      <div class="field">

        <label>Forma de pagamento</label>

        <select id="closePayment">

          <option>Dinheiro</option>
          <option>Pix</option>
          <option>Débito</option>
          <option>Crédito</option>

        </select>

      </div>

      <br>

      <button
        class="btn btn-green"
        onclick="confirmarFechamentoMesa(${tableId}, ${total})">
        Confirmar fechamento
      </button>
    `
  );

}


function selecionarPagamento(tipo) {

  const select =
    document.getElementById("closePayment");

  if (select) {
    select.value = tipo;
  }

}


function confirmarFechamentoMesa(tableId, total) {

  const table = tables.find(t => t.id === tableId);

  const payment =
    document.getElementById("closePayment").value;

  orders.push({
    id: orderCounter++,
    origin: "Mesa",
    customer: `Mesa ${tableId}`,
    total,
    status: "Finalizado",
    payment,
    date: new Date().toLocaleString("pt-BR")
  });

  finance.push({
    date: new Date().toLocaleString("pt-BR"),
    description: `Venda Mesa ${tableId}`,
    method: payment,
    value: total
  });

  table.status = "aberta";

  table.chairs = {
    A: [],
    B: [],
    C: [],
    D: []
  };

  saveData();

  closeModal();

  refreshAll();

  toast(
    `Mesa ${tableId} fechada em ${money(total)} — ${payment}.`
  );

}


/* ---------- PEDIDOS ---------- */

function novoPedido() {

  openModal(
    "Novo Pedido",
    `
      <div class="field">
        <label>Origem</label>

        <select id="newOrderOrigin">
          <option>Salão</option>
          <option>Delivery</option>
          <option>Retirada</option>
          <option>WhatsApp</option>
          <option>iFood</option>
        </select>
      </div>

      <br>

      <div class="field">
        <label>Cliente / Mesa</label>

        <input
          id="newOrderCustomer"
          placeholder="Ex.: Mesa 10 / João">
      </div>

      <br>

      <div class="field">
        <label>Produto</label>

        <select id="newOrderProduct">

          ${products.map(product => `
            <option value="${product.id}">
              ${product.name} — ${money(product.price)}
            </option>
          `).join("")}

        </select>
      </div>

      <br>

      <div class="field">
        <label>Quantidade</label>
        <input id="newOrderQty" type="number" value="1" min="1">
      </div>

      <br>

      <button
        class="btn btn-green"
        onclick="salvarNovoPedido()">
        Registrar pedido
      </button>
    `
  );

}


function salvarNovoPedido() {

  const origin =
    document.getElementById("newOrderOrigin").value;

  const customer =
    document.getElementById("newOrderCustomer").value ||
    "Cliente";

  const productId =
    Number(document.getElementById("newOrderProduct").value);

  const qty =
    Number(document.getElementById("newOrderQty").value || 1);

  const product =
    products.find(p => p.id === productId);

  const total =
    product.price * qty;

  orders.push({
    id: orderCounter++,
    origin,
    customer,
    total,
    status: "Novo",
    payment: "",
    date: new Date().toLocaleString("pt-BR"),
    items: [
      {
        product: product.name,
        quantity: qty,
        price: product.price
      }
    ]
  });

  saveData();

  closeModal();

  refreshAll();

  toast("Pedido registrado com sucesso.");

}


function renderOrders() {

  const tbody =
    document.getElementById("ordersTable");

  if (!tbody) return;

  tbody.innerHTML = "";

  if (!orders.length) {

    tbody.innerHTML = `
      <tr>
        <td colspan="6">
          Nenhum pedido registrado.
        </td>
      </tr>
    `;

    return;
  }

  orders
    .slice()
    .reverse()
    .forEach(order => {

      const tr =
        document.createElement("tr");

      tr.innerHTML = `

        <td>#${order.id}</td>

        <td>${order.origin}</td>

        <td>${order.customer}</td>

        <td>${money(order.total)}</td>

        <td>${order.status}</td>

        <td>
          <button
            class="btn btn-small"
            onclick="verPedido(${order.id})">
            Ver
          </button>
        </td>

      `;

      tbody.appendChild(tr);

    });

}


function verPedido(id) {

  const order =
    orders.find(o => o.id === id);

  if (!order) return;

  openModal(
    `Pedido #${order.id}`,
    `
      <div class="list">

        <div class="list-item">
          <span>Origem</span>
          <strong>${order.origin}</strong>
        </div>

        <div class="list-item">
          <span>Cliente/Mesa</span>
          <strong>${order.customer}</strong>
        </div>

        <div class="list-item">
          <span>Status</span>
          <strong>${order.status}</strong>
        </div>

        <div class="list-item">
          <span>Total</span>
          <strong>${money(order.total)}</strong>
        </div>

      </div>
    `
  );

}


/* ---------- PRODUTOS ---------- */

function renderProducts() {

  const grid =
    document.getElementById("productGrid");

  if (!grid) return;

  grid.innerHTML = "";

  products.forEach(product => {

    const card =
      document.createElement("div");

    card.className = "product-card";

    card.innerHTML = `

      <div class="product-photo">
        ${product.emoji || "🍽️"}
      </div>

      <div class="product-body">

        <div class="product-name">
          ${product.name}
        </div>

        <div class="product-category">
          ${product.category}
        </div>

        <div class="product-price">
          ${money(product.price)}
        </div>

        <div style="margin-top:8px;">
          Estoque: ${product.stock}
        </div>

      </div>
    `;

    grid.appendChild(card);

  });

}


function abrirProdutoModal() {

  openModal(
    "Cadastrar Produto",
    `
      <div class="form-grid">

        <div class="field">
          <label>Produto</label>
          <input id="productName" placeholder="Nome do produto">
        </div>

        <div class="field">
          <label>Categoria</label>

          <select id="productCategory">

            <option>Pratos</option>
            <option>Marmitas</option>
            <option>Carnes</option>
            <option>Acompanhamentos</option>
            <option>Bebidas</option>
            <option>Salgados</option>
            <option>Sorvetes</option>
            <option>Sobremesas</option>

          </select>

        </div>

        <div class="field">
          <label>Preço</label>
          <input id="productPrice" type="number" step="0.01">
        </div>

        <div class="field">
          <label>Estoque inicial</label>
          <input id="productStock" type="number" value="0">
        </div>

        <div class="field">
          <label>Estoque mínimo</label>
          <input id="productMin" type="number" value="5">
        </div>

      </div>

      <br>

      <button
        class="btn btn-green"
        onclick="salvarProduto()">
        Salvar produto
      </button>
    `
  );

}


function salvarProduto() {

  const name =
    document.getElementById("productName").value.trim();

  const category =
    document.getElementById("productCategory").value;

  const price =
    Number(document.getElementById("productPrice").value || 0);

  const stock =
    Number(document.getElementById("productStock").value || 0);

  const min =
    Number(document.getElementById("productMin").value || 0);

  if (!name) {

    toast("Informe o nome do produto.");

    return;
  }

  products.push({
    id: Date.now(),
    name,
    category,
    price,
    stock,
    min,
    emoji: "🍽️"
  });

  saveData();

  closeModal();

  refreshAll();

  toast("Produto cadastrado.");

}


/* ---------- ESTOQUE ---------- */

function renderStock() {

  const tbody =
    document.getElementById("stockTable");

  if (!tbody) return;

  tbody.innerHTML = "";

  products.forEach(product => {

    const low =
      product.stock <= product.min;

    const tr =
      document.createElement("tr");

    tr.innerHTML = `

      <td>${product.name}</td>

      <td>${product.category}</td>

      <td>${product.stock}</td>

      <td>${product.min}</td>

      <td>
        ${low
          ? '<span style="color:#c62828;font-weight:900;">COMPRAR</span>'
          : '<span style="color:#16833b;font-weight:900;">OK</span>'}
      </td>

      <td>
        <button
          class="btn btn-small"
          onclick="entradaEstoque(${product.id})">
          Entrada
        </button>
      </td>

    `;

    tbody.appendChild(tr);

  });

}


function entradaEstoque(productId) {

  const product =
    products.find(p => p.id === productId);

  if (!product) return;

  const quantity =
    Number(
      prompt(
        `Quantidade de ${product.name} para entrada:`,
        "1"
      )
    );

  if (!quantity || quantity <= 0) return;

  product.stock += quantity;

  saveData();

  refreshAll();

  toast("Estoque atualizado.");

}


/* ---------- FINANCEIRO ---------- */

function calcularPagamento() {

  const total =
    Number(document.getElementById("payTotal").value || 0);

  const cash =
    Number(document.getElementById("payCash").value || 0);

  const pix =
    Number(document.getElementById("payPix").value || 0);

  const debit =
    Number(document.getElementById("payDebit").value || 0);

  const credit =
    Number(document.getElementById("payCredit").value || 0);

  const paid =
    cash + pix + debit + credit;

  const change =
    Math.max(0, paid - total);

  document.getElementById("payChange").value =
    change.toFixed(2);

  const difference =
    total - paid;

  const result =
    document.getElementById("paymentResult");

  if (difference > 0) {

    result.innerHTML = `
      <div class="alert alert-red">
        Ainda faltam ${money(difference)}.
      </div>
    `;

  } else {

    result.innerHTML = `
      <div class="alert alert-green">
        Pagamento suficiente.
        Troco: <strong>${money(change)}</strong>
      </div>
    `;

  }

}


function registrarPagamento() {

  const total =
    Number(document.getElementById("payTotal").value || 0);

  if (total <= 0) {

    toast("Informe o total da conta.");

    return;
  }

  const cash =
    Number(document.getElementById("payCash").value || 0);

  const pix =
    Number(document.getElementById("payPix").value || 0);

  const debit =
    Number(document.getElementById("payDebit").value || 0);

  const credit =
    Number(document.getElementById("payCredit").value || 0);

  const paid =
    cash + pix + debit + credit;

  if (paid < total) {

    toast("O pagamento ainda não cobre o total.");

    return;
  }

  const date =
    new Date().toLocaleString("pt-BR");

  if (cash > 0) {

    finance.push({
      date,
      description: "Pagamento",
      method: "Dinheiro",
      value: cash
    });

  }

  if (pix > 0) {

    finance.push({
      date,
      description: "Pagamento",
      method: "Pix",
      value: pix
    });

  }

  if (debit > 0) {

    finance.push({
      date,
      description: "Pagamento",
      method: "Débito",
      value: debit
    });

  }

  if (credit > 0) {

    finance.push({
      date,
      description: "Pagamento",
      method: "Crédito",
      value: credit
    });

  }

  saveData();

  refreshAll();

  toast("Pagamento registrado.");

}


function renderFinance() {

  const tbody =
    document.getElementById("financeTable");

  if (!tbody) return;

  tbody.innerHTML = "";

  finance
    .slice()
    .reverse()
    .forEach(item => {

      const tr =
        document.createElement("tr");

      tr.innerHTML = `

        <td>${item.date}</td>
        <td>${item.description}</td>
        <td>${item.method}</td>
        <td>${money(item.value)}</td>

      `;

      tbody.appendChild(tr);

    });

  const entradas =
    finance.reduce(
      (sum,item) =>
        sum + Number(item.value || 0),
      0
    );

  const pix =
    finance
      .filter(item => item.method === "Pix")
      .reduce(
        (sum,item) =>
          sum + Number(item.value || 0),
        0
      );

  document.getElementById("financeEntradas")
    .textContent = money(entradas);

  document.getElementById("financeSaidas")
    .textContent = money(0);

  document.getElementById("financeSaldo")
    .textContent = money(entradas);

  document.getElementById("financePix")
    .textContent = money(pix);

}


/* ---------- COMPRAS ---------- */

function abrirCompraModal() {

  openModal(
    "Lançar Compra",
    `
      <div class="form-grid">

        <div class="field">
          <label>Fornecedor</label>
          <input id="purchaseSupplier">
        </div>

        <div class="field">
          <label>Número da nota</label>
          <input id="purchaseInvoice">
        </div>

        <div class="field">
          <label>Vencimento</label>
          <input id="purchaseDue" type="date">
        </div>

        <div class="field">
          <label>Parcelas</label>
          <input id="purchaseInstallments" type="number" value="1">
        </div>

        <div class="field">
          <label>Valor</label>
          <input id="purchaseValue" type="number" step="0.01">
        </div>

      </div>

      <br>

      <button
        class="btn btn-green"
        onclick="salvarCompra()">
        Registrar compra
      </button>
    `
  );

}


function salvarCompra() {

  const supplier =
    document.getElementById("purchaseSupplier").value;

  const invoice =
    document.getElementById("purchaseInvoice").value;

  const due =
    document.getElementById("purchaseDue").value;

  const installments =
    Number(
      document.getElementById("purchaseInstallments").value || 1
    );

  const value =
    Number(
      document.getElementById("purchaseValue").value || 0
    );

  purchases.push({
    supplier,
    invoice,
    due,
    installments,
    value,
    status: "Em aberto"
  });

  saveData();

  closeModal();

  refreshAll();

  toast("Compra lançada.");

}


function renderPurchases() {

  const tbody =
    document.getElementById("purchaseTable");

  if (!tbody) return;

  tbody.innerHTML = "";

  purchases.forEach(item => {

    const tr =
      document.createElement("tr");

    tr.innerHTML = `

      <td>${item.supplier}</td>
      <td>${item.invoice}</td>
      <td>${item.due || "-"}</td>
      <td>${item.installments}</td>
      <td>${money(item.value)}</td>
      <td>${item.status}</td>

    `;

    tbody.appendChild(tr);

  });

}


/* ---------- HORAS ---------- */

function calcularHoras() {

  const start =
    document.getElementById("timeIn").value;

  const end =
    document.getElementById("timeOut").value;

  const hourly =
    Number(
      document.getElementById("hourValue").value || 0
    );

  if (!start || !end) {

    toast("Informe entrada e saída.");

    return;
  }

  const [h1,m1] =
    start.split(":").map(Number);

  const [h2,m2] =
    end.split(":").map(Number);

  let minutes =
    (h2 * 60 + m2) -
    (h1 * 60 + m1);

  if (minutes < 0) {
    minutes += 24 * 60;
  }

  const hours =
    minutes / 60;

  const total =
    hours * hourly;

  document.getElementById("hoursResult")
    .innerHTML = `

      <div class="alert alert-green">

        Horas trabalhadas:
        <strong>${hours.toFixed(2)}</strong>

        <br>

        Total a pagar:
        <strong>${money(total)}</strong>

      </div>

    `;

}


/* ---------- DELIVERY ---------- */

function novoDelivery() {

  openModal(
    "Novo Delivery",
    `
      <div class="form-grid">

        <div class="field">
          <label>Cliente</label>
          <input id="deliveryCustomer">
        </div>

        <div class="field">
          <label>Telefone</label>
          <input id="deliveryPhone">
        </div>

        <div class="field">
          <label>Endereço</label>
          <input id="deliveryAddress">
        </div>

        <div class="field">
          <label>Taxa de entrega</label>
          <input id="deliveryFee" type="number" step="0.01" value="0">
        </div>

      </div>

      <br>

      <button
        class="btn btn-green"
        onclick="salvarDelivery()">
        Criar delivery
      </button>
    `
  );

}


function salvarDelivery() {

  const customer =
    document.getElementById("deliveryCustomer").value;

  const phone =
    document.getElementById("deliveryPhone").value;

  const address =
    document.getElementById("deliveryAddress").value;

  const fee =
    Number(
      document.getElementById("deliveryFee").value || 0
    );

  deliveries.push({
    id: orderCounter++,
    customer,
    phone,
    address,
    fee,
    status: "Novo"
  });

  saveData();

  closeModal();

  refreshAll();

  toast("Delivery criado.");

}


function renderDelivery() {

  const tbody =
    document.getElementById("deliveryTable");

  if (!tbody) return;

  tbody.innerHTML = "";

  deliveries.forEach(item => {

    const tr =
      document.createElement("tr");

    tr.innerHTML = `

      <td>#${item.id}</td>

      <td>${item.customer}</td>

      <td>${item.address}</td>

      <td>${money(item.fee)}</td>

      <td>${item.status}</td>

    `;

    tbody.appendChild(tr);

  });

}


/* ---------- CONFIGURAÇÕES ---------- */

function salvarConfiguracoes() {

  const name =
    document.getElementById("configName").value;

  const city =
    document.getElementById("configCity").value;

  localStorage.setItem(
    "casa_do_sabor_config",
    JSON.stringify({
      name,
      city
    })
  );

  toast("Configurações salvas.");

}


function limparDados() {

  const confirmation =
    confirm(
      "Isso apagará os dados de teste deste navegador. Continuar?"
    );

  if (!confirmation) return;

  localStorage.removeItem(
    "casa_do_sabor_data"
  );

  orders = [];
  finance = [];
  purchases = [];
  deliveries = [];
  orderCounter = 1;

  products = [
    {
      id: 1,
      name: "PF",
      category: "Pratos",
      price: 25,
      stock: 20,
      min: 10,
      emoji: "🍛"
    },
    {
      id: 2,
      name: "Guaraná",
      category: "Bebidas",
      price: 6,
      stock: 15,
      min: 8,
      emoji: "🥤"
    },
    {
      id: 3,
      name: "Salgado",
      category: "Salgados",
      price: 10,
      stock: 5,
      min: 10,
      emoji: "🥟"
    },
    {
      id: 4,
      name: "Sorvete",
      category: "Sobremesas",
      price: 6,
      stock: 12,
      min: 5,
      emoji: "🍦"
    }
  ];

  initTables();

  saveData();

  refreshAll();

  toast("Dados de teste limpos.");

}


/* ---------- MODAL ---------- */

function openModal(title, content) {

  document.getElementById("modalTitle")
    .textContent = title;

  document.getElementById("modalContent")
    .innerHTML = content;

  document.getElementById("modalBackdrop")
    .classList.add("show");

}


function closeModal() {

  document.getElementById("modalBackdrop")
    .classList.remove("show");

}


function fecharModal() {
  closeModal();
}


/* ---------- TOAST ---------- */

let toastTimer;

function toast(message) {

  const element =
    document.getElementById("toast");

  element.textContent = message;

  element.classList.add("show");

  clearTimeout(toastTimer);

  toastTimer =
    setTimeout(
      () => {
        element.classList.remove("show");
      },
      3000
    );

}


/* ---------- DASHBOARD ---------- */

function refreshDashboard() {

  const sales =
    orders
      .filter(order => order.status === "Finalizado")
      .reduce(
        (sum,order) =>
          sum + Number(order.total || 0),
        0
      );

  const occupied =
    tables.filter(
      table => table.status === "ocupada"
    ).length;

  const lowStock =
    products.filter(
      product =>
        product.stock <= product.min
    ).length;

  document.getElementById("dashVendas")
    .textContent = money(sales);

  document.getElementById("dashMesas")
    .textContent = occupied;

  document.getElementById("dashPedidos")
    .textContent = orders.length;

  document.getElementById("dashEstoque")
    .textContent = lowStock;

  document.getElementById("estoqueItens")
    .textContent = products.length;

  document.getElementById("estoqueBaixo")
    .textContent = lowStock;

  const stockValue =
    products.reduce(
      (sum,product) =>
        sum +
        Number(product.stock || 0) *
        Number(product.price || 0),
      0
    );

  document.getElementById("estoqueValor")
    .textContent = money(stockValue);

  document.getElementById("deliveryCount")
    .textContent = deliveries.length;

  document.getElementById("reportSales")
    .textContent = money(sales);

  document.getElementById("reportOrders")
    .textContent = orders.length;

  const ticket =
    orders.length
      ? sales / orders.length
      : 0;

  document.getElementById("reportTicket")
    .textContent = money(ticket);

}


/* ---------- ATUALIZAÇÃO GERAL ---------- */

function refreshAll() {

  renderTables();

  renderOrders();

  renderProducts();

  renderStock();

  renderFinance();

  renderPurchases();

  renderDelivery();

  refreshDashboard();

}


/* ---------- INICIALIZAÇÃO ---------- */

loadData();

refreshAll();


/* ---------- FECHAR MODAL AO TOCAR FORA ---------- */

document.getElementById("modalBackdrop")
  .addEventListener(
    "click",
    function(event) {

      if (event.target === this) {
        closeModal();
      }

    }
  );


/* ---------- TECLA ESC ---------- */

document.addEventListener(
  "keydown",
  function(event) {

    if (event.key === "Escape") {
      closeModal();
    }

  }
);

</script>

</body>
</html>