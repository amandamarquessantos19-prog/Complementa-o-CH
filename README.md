<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pegyes - Desapegue, Ganhe, Economize</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            line-height: 1.6;
            color: #333;
            background-color: #f8f9fa;
        }

        /* Cabeçalho e Menu de Navegação */
        header {
            background-color: #FF6B35;
            padding: 1rem 2rem;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(0,0,0,0.15);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            color: white;
            font-size: 1.8rem;
            font-weight: bold;
            text-decoration: none;
            letter-spacing: 1px;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 2rem;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: all 0.3s;
        }

        nav a:hover {
            color: #FFD7C1;
            transform: scale(1.05);
        }

        /* Seções Gerais */
        section {
            padding: 7rem 2rem 4rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        h2 {
            color: #FF6B35;
            text-align: center;
            margin-bottom: 2.5rem;
            font-size: 2.2rem;
        }

        /* Tela Inicial */
        #inicial {
            min-height: 100vh;
            background: linear-gradient(rgba(255, 107, 53, 0.08), rgba(255, 107, 53, 0.08)), url('https://picsum.photos/id/1059/1200/800') center/cover no-repeat;
            display: flex;
            align-items: center;
            text-align: center;
        }

        .inicial-content h1 {
            font-size: 3.2rem;
            margin-bottom: 1.2rem;
            color: #D14E1E;
        }

        .inicial-content p {
            font-size: 1.3rem;
            max-width: 700px;
            margin: 0 auto 2rem;
            color: #444;
        }

        .botao-principal {
            background-color: #FF6B35;
            color: white;
            padding: 1rem 2.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            transition: background 0.3s;
        }

        .botao-principal:hover {
            background-color: #D14E1E;
        }

        /* Tela Produtos */
        .produtos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .produto-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            text-align: center;
            transition: transform 0.3s;
        }

        .produto-card:hover {
            transform: translateY(-6px);
        }

        .produto-imagem {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .produto-info {
            padding: 1.2rem;
        }

        .produto-card h3 {
            color: #333;
            margin-bottom: 0.5rem;
            font-size: 1.2rem;
        }

        .produto-descricao {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 0.8rem;
        }

        .produto-preco {
            color: #2E7D32;
            font-size: 1.4rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }

        .botao-comprar {
            background-color: #2E7D32;
            color: white;
            border: none;
            padding: 0.6rem 1.2rem;
            border-radius: 6px;
            cursor: pointer;
            font-size: 1rem;
            transition: background 0.3s;
        }

        .botao-comprar:hover {
            background-color: #1B5E20;
        }

        /* Tela Contato */
        .contato-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            background: white;
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }

        .form-grupo {
            margin-bottom: 1.5rem;
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: #444;
        }

        input, textarea {
            width: 100%;
            padding: 0.9rem;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 1rem;
        }

        button[type="submit"] {
            background-color: #FF6B35;
            color: white;
            padding: 0.9rem 2rem;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-size: 1rem;
            transition: background 0.3s;
        }

        button[type="submit"]:hover {
            background-color: #D14E1E;
        }

        .contato-info h3 {
            color: #FF6B35;
            margin-bottom: 1.2rem;
        }

        .contato-info p {
            margin: 0.8rem 0;
            font-size: 1.1rem;
            color: #555;
        }

        /* Rodapé */
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 2rem;
        }

        /* Responsividade */
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                gap: 1rem;
                flex-wrap: wrap;
                justify-content: center;
            }

            .contato-container {
                grid-template-columns: 1fr;
            }

            .inicial-content h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>

    <!-- Menu de Navegação -->
    <header>
        <div class="nav-container">
            <a href="#inicial" class="logo">PEGYES</a>
            <nav>
                <ul>
                    <li><a href="#inicial">Início</a></li>
                    <li><a href="#produtos">Produtos</a></li>
                    <li><a href="#contato">Contato</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Tela Inicial -->
    <section id="inicial">
        <div class="inicial-content">
            <h1>Seu Desapego, O Achado de Alguém ✨</h1>
            <p>O Pegyes é o lugar ideal para vender e comprar coisas usadas, conservadas e com preço justo. Desapegue de objetos que não usa mais e encontre tesouros por um preço que cabe no bolso.</p>
            <a href="#produtos" class="botao-principal">Ver Produtos</a>
        </div>
    </section>

    <!-- Tela Produtos -->
    <section id="produtos">
        <h2>Itens para Desapego</h2>
        <div class="produtos-grid">
            <div class="produto-card">
                <img src="https://picsum.photos/id/21/300/200" alt="Mochila" class="produto-imagem">
                <div class="produto-info">
                    <h3>Mochila Escolar</h3>
                    <p class="produto-descricao">Usada poucas vezes, muito conservada, cor azul.</p>
                    <p class="produto-preco">R$ 35,00</p>
                    <button class="botao-comprar">Tenho Interesse</button>
                </div>
            </div>

            <div class="produto-card">
                <img src="https://picsum.photos/id/26/300/200" alt="Cadeira" class="produto-imagem">
                <div class="produto-info">
                    <h3>Cadeira de Escritório</h3>
                    <p class="produto-descricao">Estrutura perfeita, estofado sem rasgos, giratória.</p>
                    <p class="produto-preco">R$ 80,00</p>
                    <button class="botao-comprar">Tenho Interesse</button>
                </div>
            </div>

            <div class="produto-card">
                <img src="https://picsum.photos/id/96/300/200" alt="Livros" class="produto-imagem">
                <div class="produto-info">
                    <h3>Kit Livros Romance</h3>
                    <p class="produto-descricao">4 livros da mesma coleção, páginas limpas, capa dura.</p>
                    <p class="produto-preco">R$ 25,00</p>
                    <button class="botao-comprar">Tenho Interesse</button>
                </div>
            </div>

            <div class="produto-card">
                <img src="https://picsum.photos/id/114/300/200" alt="Vaso" class="produto-imagem">
                <div class="produto-info">
                    <h3>Vaso de Plantas</h3>
                    <p class="produto-descricao">Cerâmica, pintado à mão, tamanho médio.</p>
                    <p class="produto-preco">R$ 18,00</p>
                    <button class="botao-comprar">Tenho Interesse</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Tela de Contato -->
    <section id="contato">
        <h2>Fale Conosco</h2>
        <div class="contato-container">
            <form>
                <div class="form-grupo">
                    <label for="nome">Nome</label>
                    <input type="text" id="nome" name="nome" required>
                </div>
                <div class="form-grupo">
                    <label for="email">E-mail</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-grupo">
                    <label for="assunto">Assunto</label>
                    <input type="text" id="assunto" name="assunto" placeholder="Ex: Quero vender um item">
                </div>
                <div class="form-grupo">
                    <label for="mensagem">Mensagem</label>
                    <textarea id="mensagem" name="mensagem" rows="5" required placeholder="Escreva aqui sua mensagem..."></textarea>
                </div>
                <button type="submit">Enviar Mensagem</button>
            </form>
            <div class="contato-info">
                <h3>Informações</h3>
                <p>📍 Endereço: Rua Marley Grill, 1356 - Centro - Nova Daco MJ</p>
                <p>📞 Telefone: (45) 99426-5733</p>
                <p>✉️ E-mail: contato@pegyes.com.br</p>
                <p>📱 Instagram: @pegyes_oficial</p>
                <p>⏰ Atendimento: Todos os dias, das 9h às 20h</p>
            </div>
        </div>
    </section>

    <!-- Rodapé -->
    <footer>
        <p>&copy; 2026 Pegyes - Desapego e Economia | Todos os direitos reservados</p>
    </footer>

</body>
</html>
