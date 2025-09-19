<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Impressão Rápida</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6f8;
      margin: 0;
      padding: 20px;
    }
    h1 {
      text-align: center;
      color: #2c3e50;
    }
    table {
      width: 100%;
      border-collapse: collapse;
      margin: 20px auto;
      background: #fff;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
      border-radius: 10px;
      overflow: hidden;
    }
    th, td {
      padding: 12px;
      border: 1px solid #ddd;
      text-align: center;
    }
    th {
      background: #2c3e50;
      color: #fff;
    }
    tr:nth-child(even) {
      background: #f9f9f9;
    }
    .btn {
      display: inline-block;
      background: #27ae60;
      color: #fff;
      padding: 10px 20px;
      margin: 10px 5px;
      border-radius: 8px;
      border: none;
      cursor: pointer;
      transition: 0.3s;
    }
    .btn:hover {
      background: #2ecc71;
    }
    .logo {
      display: none; /* logo está oculta */
    }
  </style>
</head>
<body>
  <h1>📑 Impressão Rápida</h1>

  <!-- Logo oculta -->
  <img src="logo.png" alt="Logo Impressão Rápida" class="logo">

  <table id="planilha">
    <tr>
      <th>Nome</th>
      <th>Serviço</th>
      <th>Horário</th>
      <th>Data</th>
      <th>Qtd. Páginas</th>
    </tr>
  </table>

  <div style="text-align:center;">
    <button class="btn" onclick="adicionarLinha()">➕ Adicionar Linha</button>
    <button class="btn" onclick="copiarTabela()">📋 Copiar Dados</button>
  </div>

  <script>
    function adicionarLinha() {
      const tabela = document.getElementById("planilha");
      const linha = tabela.insertRow(-1);
      for (let i = 0; i < 5; i++) {
        const celula = linha.insertCell(i);
        celula.contentEditable = "true";
        celula.style.background = "#fffbe7";
      }
    }

    function copiarTabela() {
      const tabela = document.getElementById("planilha");
      let texto = "";
      for (let row of tabela.rows) {
        let cols = [];
        for (let cell of row.cells) {
          cols.push(cell.innerText);
        }
        texto += cols.join(" | ") + "\n";
      }
      navigator.clipboard.writeText(texto).then(() => {
        alert("✅ Dados copiados!");
      });<style>
  #planilha {
    width: 100vw;         /* Ocupa toda a largura da tela */
    max-width: none;      /* Remove limite máximo */
    margin: 0 auto;       /* Centraliza horizontalmente */
    table-layout: fixed;  /* Faz todas as colunas se distribuírem igualmente */
  }

  #planilha th, #planilha td {
    width: 20%;           /* Cada coluna ocupa 20% da tabela (5 colunas) */
    min-width: 120px;     /* Garante que não fique apertada */
  }
</style>
