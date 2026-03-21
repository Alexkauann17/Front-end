<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Meu Projeto Front-end</title>

  <!-- Fonte -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

  <style>
    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      background: #f5f5f5;
      color: #333;
    }

    nav {
      position: sticky;
      top: 0;
      background: white;
      padding: 15px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 1000;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }

    .hero {
      text-align: center;
      padding: 80px 20px;
    }

    button {
      background: linear-gradient(45deg, #4facfe, #00f2fe);
      border: none;
      padding: 12px 20px;
      color: white;
      border-radius: 8px;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      transform: scale(1.05);
      box-shadow: 0 10px 20px rgba(0,0,0,0.2);
    }

    .cards {
      display: flex;
      gap: 20px;
      flex-wrap: wrap;
      justify-content: center;
      padding: 20px;
    }

    .card {
      background: white;
      padding: 20px;
      border-radius: 12px;
      width: 250px;
      transition: 0.3s;
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    }

    .card:hover {
      transform: translateY(-10px);
    }

    .fade-in {
      opacity: 0;
      transform: translateY(20px);
      transition: all 0.8s ease;
    }

    .fade-in.show {
      opacity: 1;
      transform: translateY(0);
    }

    .dark {
      background: #121212;
      color: white;
    }

    .dark nav {
      background: #1e1e1e;
    }

    .dark .card {
      background: #1e1e1e;
    }

    footer {
      text-align: center;
      padding: 20px;
    }

    html {
      scroll-behavior: smooth;
    }
  </style>
</head>

<body>

  <nav>
    <h2>💻 Meu Projeto</h2>
    <button id="themeToggle">🌙</button>
  </nav>

  <section class="hero fade-in">
    <h1>Bem-vindo ao meu projeto 🚀</h1>
    <p>Desenvolvimento Front-end moderno e responsivo</p>
    <a href="#projetos"><button>Ver projetos</button></a>
  </section>

  <section id="projetos" class="fade-in">
    <h2 style="text-align:center;">📂 Projetos</h2>

    <div class="cards">

      <div class="card">
        <h3>Projeto 1</h3>
        <p>Descrição do projeto.</p>
        <button>Acessar</button>
      </div>

      <div class="card">
        <h3>Projeto 2</h3>
        <p>Descrição do projeto.</p>
        <button>Acessar</button>
      </div>

      <div class="card">
        <h3>Projeto 3</h3>
        <p>Descrição do projeto.</p>
        <button>Acessar</button>
      </div>

    </div>
  </section>

  <footer>
    <p>Feito por Alex Kauan 🚀</p>
  </footer>

  <script>
    // ANIMAÇÃO
    const elements = document.querySelectorAll('.fade-in');

    const observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('show');
        }
      });
    });

    elements.forEach(el => observer.observe(el));

    // DARK MODE
    const toggle = document.getElementById('themeToggle');

    toggle.onclick = () => {
      document.body.classList.toggle('dark');
    };
  </script>

</body>
</html>
