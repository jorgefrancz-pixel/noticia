<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Aviso Escolar - Ausência de Alunos</title>

  <!-- ESTILOS (CSS) -->
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      line-height: 1.6;
      background-color: #f0f4f8;
      color: #2d3748;
      padding-bottom: 40px;
    }

    .container {
      max-width: 800px;
      margin: 0 auto;
      padding: 0 20px;
    }

    /* Cabeçalho */
    .header-colegio {
      background-color: #0f172a;
      color: #ffffff;
      padding: 20px 0;
      border-bottom: 4px solid #0284c7;
      margin-bottom: 30px;
    }

    .colegio-nome {
      font-size: 1.3rem;
      font-weight: bold;
      color: #38bdf8;
    }

    .disciplina-nome {
      font-size: 0.95rem;
      color: #94a3b8;
    }

    /* Card da Notícia */
    .noticia-card {
      background: #ffffff;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
    }

    .titulo {
      font-size: 1.75rem;
      color: #0f172a;
      margin-bottom: 12px;
      line-height: 1.3;
    }

    .subtitulo {
      font-size: 1.1rem;
      color: #475569;
      margin-bottom: 18px;
    }

    .meta-info {
      font-size: 0.88rem;
      color: #64748b;
      border-top: 1px solid #e2e8f0;
      border-bottom: 1px solid #e2e8f0;
      padding: 10px 0;
      margin-bottom: 24px;
      display: flex;
      gap: 15px;
      flex-wrap: wrap;
    }

    .imagem-container {
      margin-bottom: 24px;
      overflow: hidden;
      border-radius: 8px;
    }

    .imagem-container img {
      width: 100%;
      height: auto;
      display: block;
      object-fit: cover;
    }

    .corpo-texto p {
      font-size: 1.05rem;
      text-align: justify;
      color: #334155;
    }

    /* Painel Dinâmico de Notificação */
    .painel-interativo {
      margin-top: 25px;
      padding: 15px;
      background-color: #f1f5f9;
      border-left: 4px solid #0284c7;
      border-radius: 4px;
    }

    .painel-interativo button {
      background-color: #0284c7;
      color: #fff;
      border: none;
      padding: 8px 16px;
      border-radius: 4px;
      cursor: pointer;
      font-weight: bold;
      margin-top: 8px;
    }

    .painel-interativo button:hover {
      background-color: #0369a1;
    }

    /* Responsividade */
    @media (max-width: 600px) {
      .noticia-card {
        padding: 20px;
      }

      .titulo {
        font-size: 1.35rem;
      }

      .subtitulo {
        font-size: 1rem;
      }
    }
  </style>
</head>
<body>

  <!-- Cabeçalho com dados obrigatórios -->
  <header class="header-colegio">
    <div class="container">
      <p class="colegio-nome">Colégio Frederico Guilherme Giese</p>
      <p class="disciplina-nome">Disciplina: Desenvolvimento Web</p>
    </div>
  </header>

  <main class="container">
    <article class="noticia-card">
      
      <!-- Título: 80 caracteres -->
      <h1 class="titulo">
        Estratégias Inovadoras para Combater o Alto Índice de Evasão Escolar no Brasil
      </h1>

      <!-- Subtítulo: 109 caracteres -->
      <p class="subtitulo">
        Escolas públicas e privadas adotam plataformas digitais e diálogo com famílias para reduzir faltas dos alunos.
      </p>

      <!-- Metadados de publicação -->
      <div class="meta-info">
        <span>Autor: <strong>Jorge Felipe Francz</strong></span>
        <span>•</span>
        <span>Data: <time id="data-publicacao"></time></span>
      </div>

      <!-- Imagem ilustrativa -->
      <div class="imagem-container">
        <img src="https://images.unsplash.com/photo-1580582932707-520aed937b7b?auto=format&fit=crop&w=800&q=80" alt="Sala de aula com carteiras de alunos">
      </div>

      <!-- Corpo da notícia: 744 caracteres -->
      <div class="corpo-texto">
        <p>
          A ausência frequente de alunos nas salas de aula tornou-se um dos principais desafios do sistema educacional contemporâneo. O acúmulo de faltas compromete o aprendizado, aumenta o risco de reprovação e dificulta o desenvolvimento social dos estudantes. Para reverter esse cenário preocupante, instituições de ensino estão implementando sistemas automatizados de monitoramento de frequência em tempo real. Com essas novas ferramentas, os gestores conseguem identificar padrões de ausência logo nos primeiros dias e acionar as famílias de forma rápida e preventiva. Além disso, ações pedagógicas integradas buscam criar um ambiente mais acolhedor e atrativo, garantindo que o estudante se sinta motivado a frequentar as aulas diariamente.
        </p>
      </div>

      <!-- Recursos dinâmicos JS -->
      <div class="painel-interativo">
        <p id="status-presenca">Status de monitoramento: Sistema ativo para prevenção de ausências.</p>
        <button id="btn-alerta">Simular Alerta de Ausência</button>
      </div>

    </article>
  </main>

  <!-- COMPORTAMENTO DINÂMICO (JAVASCRIPT) -->
  <script>
    document.addEventListener("DOMContentLoaded", function() {
      // Data dinâmica de publicação
      const elementoData = document.getElementById("data-publicacao");
      const dataHoje = new Date();
      
      const opcoesData = { 
        year: 'numeric', 
        month: 'long', 
        day: 'numeric' 
      };
      
      elementoData.textContent = dataHoje.toLocaleDateString('pt-BR', opcoesData);

      // Interação do botão de alerta
      const btnAlerta = document.getElementById("btn-alerta");
      const statusText = document.getElementById("status-presenca");

      btnAlerta.addEventListener("click", function() {
        statusText.style.color = "#dc2626";
        statusText.innerHTML = "<strong>Alerta enviado:</strong> Responsáveis notificados sobre faltas consecutivas do estudante.";
      });
    });
  </script>

</body>
</html>
