# planilha<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Impressão Rápida</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f0f0;
      margin: 0;
      padding: 0;
    }
    header {
      background: #ff6600;
      color: white;
      padding: 20px;
      text-align: center;
      font-size: 24px;
    }
    .container {
      max-width: 800px;
      margin: 30px auto;
      background: white;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    }
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 20px;
    }
    table, th, td {
      border: 1px solid #ddd;
    }
    th, td {
      padding: 10px;
      text-align: left;
    }
    th {
      background: #ff6600;
      color: white;
    }
    input, button {
      padding: 10px;
      margin: 5px 0;
    }
    button {
      background: #ff6600;
      color: white;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background: #e65c00;
    }
  </style>
</head>
<body>

<header>Impressão Rápida</header>

<div class="container">
  <h2>Adicionar Agendamento</h2>
  <input type="text" id="nome" placeholder="Nome da pessoa">
  <input type="text" id="servico" placeholder="Serviço">
  <button onclick="adicionarAgendamento()">Adicionar</button>

  <table id="tabela">
    <thead>
      <tr>
        <th>Nome</th>
        <th>Serviço</th>
      </tr>
    </thead>
    <tbody>
      <!-- Linhas adicionadas aqui -->
    </tbody>
  </table>
</div>

<script>
  function adicionarAgendamento() {
    const nome = document.getElementById('nome').value;
    const servico = document.getElementById('servico').value;
    if(nome && servico) {
      const tabela = document.getElementById('tabela').getElementsByTagName('tbody')[0];
      const linha = tabela.insertRow();
      linha.insertCell(0).innerText = nome;
      linha.insertCell(1).innerText = servico;
      document.getElementById('nome').value = '';
      document.getElementById('servico').value = '';
    } else {
      alert('Preencha os campos!');
    }
  }
</script>

</body>
</html>
