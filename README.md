
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>La' Soh</title>

  <style>
    body {
      font-family: Arial;
      margin: 0;
      background: #f5f5f5;
    }

    search {
      width: 80%;
      padding: 10px;
      border-radius: 20px;
      border: none;
    }

    main {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 15px;
      padding: 20px;
      padding-bottom: 140px;
    }

    .card {
      background: #7a0f2b;
      color: white;
      padding: 10px;
      text-align: center;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s;
    }

    .card:hover {
      transform: scale(1.03);
    }

    .card img {
      width: 100%;
      border-radius: 10px;
      height: 220px;
      object-fit: cover;
    }

    footer {
      background: #7a0f2b;
      color: white;
      padding: 20px;
      text-align: center;
    }

    footer h3 {
      margin-top: 0;
    }

    footer p {
      margin: 6px 0;
    }

    button {
      background: black;
      color: white;
      padding: 10px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
    }

    #naoEncontrado {
      display: none;
      text-align: center;
      padding: 50px;
      font-size: 22px;
      color: #7a0f2b;
      font-weight: bold;
    }

    .carrinho-btn {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: black;
      color: white;
      border-radius: 50%;
      width: 60px;
      height: 60px;
      font-size: 25px;
    }
  </style>
</head>

<body>

<header>
  <input type="text" id="search" placeholder="Buscar na La' Soh">
</header>

<!-- PRODUTOS -->
<main id="produtos">

  <div class="card" onclick="abrirProduto(1)">
    <img src="https://i.pinimg.com/originals/dd/0e/bd/dd0ebd864de762efc5e14b59997c8185.jpg">
    <p>Brinco de Sol</p>
    <span>R$12</span>
  </div>

  <div class="card" onclick="abrirProduto(2)">
    <img src="https://down-br.img.susercontent.com/file/sg-11134201-7rdy0-md1tx79sp9a4f9">
    <p>Óculos de Sol</p>
    <span>R$83</span>
  </div>

  <div class="card" onclick="abrirProduto(3)">
    <img src="https://tse1.mm.bing.net/th/id/OIP.KxtAqMZSPJsFU5phLSLSUwHaHa?pid=Api&P=0&h=180">
    <p>Anéis Personalizados</p>
    <span>R$14,60</span>
  </div>

</main>

<section id="naoEncontrado">
  Não temos isto na loja, sinto muito.
</section>

<button class="carrinho-btn" onclick="irCarrinho()">🛒</button>


<footer>

  <h3>La' Soh</h3>
 <p>
    Local fictício: Avenida Cristal Azul, nº 777 — Bairro Lua Dourada — Cidade fictícia de Solare
  </p>

  <p>
    Número: (45)99116-4________
  </p>

  <p>
    Instagram: @_La'Soh.-.Brasil_______
  </p>

</footer>

<script>

  function abrirProduto(id) {
    alert("Abrindo produto " + id);
  }

  function irCarrinho() {
    alert("Abrindo carrinho...");
  }
  
  const search = document.getElementById("search");
  const produtos = document.getElementById("produtos");
  const naoEncontrado = document.getElementById("naoEncontrado");

  search.addEventListener("input", function() {

    let valor = search.value.trim();

    if(valor.length > 0) {
      produtos.style.display = "none";
      naoEncontrado.style.display = "block";
    } else {
      produtos.style.display = "grid";
      naoEncontrado.style.display = "none";
    }

  });

</script>

</body>
