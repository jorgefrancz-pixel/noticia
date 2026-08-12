<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Notícia Biotecnológica</title>
    <style>
        /* ==========================================
           1. ESTILOS CSS
           ========================================== */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            transition: background-color 0.4s ease, color 0.4s ease, box-shadow 0.4s ease;
        }

        body {
            background-color: #f0f2f5;
            color: #1a1a1a;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        /* CARD PRINCIPAL */
        .news-card {
            background: #ffffff;
            max-width: 720px;
            width: 100%;
            border-radius: 16px;
            padding: 32px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            position: relative;
            overflow: hidden;
        }

        /* CABEÇALHO */
        .badge {
            display: inline-block;
            background-color: #e8f5e9;
            color: #2e7d32;
            font-size: 0.85rem;
            font-weight: 700;
            padding: 6px 12px;
            border-radius: 20px;
            text-transform: uppercase;
            margin-bottom: 16px;
        }

        h1 {
            font-size: 1.65rem;
            line-height: 1.3;
            color: #111;
            margin-bottom: 12px;
        }

        h2 {
            font-size: 1.1rem;
            font-weight: 500;
            color: #555;
            line-height: 1.4;
            margin-bottom: 20px;
        }

        /* METADADOS */
        .meta-info {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.9rem;
            color: #666;
            border-top: 1px solid #eee;
            border-bottom: 1px solid #eee;
            padding: 12px 0;
            margin-bottom: 24px;
            flex-wrap: wrap;
            gap: 10px;
        }

        .author-date {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .dot {
            color: #ccc;
        }

        /* BOTÃO INTERATIVO */
        .btn-glow {
            background: #10b981;
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.85rem;
        }

        .btn-glow:hover {
            background: #059669;
        }

        /* IMAGEM REFERENTE */
        .news-image-box {
            margin-bottom: 24px;
        }

        .image-placeholder {
            background: #111827;
            color: #d1d5db;
            padding: 20px;
            border-radius: 12px;
            position: relative;
            overflow: hidden;
            border: 1px solid #374151;
        }

        .glow-effect {
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(16, 185, 129, 0.15) 0%, rgba(0,0,0,0) 70%);
            pointer-events: none;
        }

        .image-desc {
            font-size: 0.92rem;
            line-height: 1.5;
            position: relative;
            z-index: 1;
        }

        /* CONTEÚDO DA NOTÍCIA */
        .news-body p {
            font-size: 1.05rem;
            line-height: 1.7;
            color: #333;
            margin-bottom: 24px;
        }

        /* RODAPÉ E CONTADORES */
        .news-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #f9fafb;
            padding: 12px 16px;
            border-radius: 10px;
            font-size: 0.82rem;
            color: #6b7280;
            flex-wrap: wrap;
            gap: 10px;
        }

        .stats {
            display: flex;
            gap: 15px;
        }

        .btn-copy {
            background: #e5e7eb;
            color: #374151;
            border: none;
            padding: 6px 12px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 600;
        }

        .btn-copy:hover {
            background: #d1d5db;
        }

        /* MODO BIOLUMINESCENTE (TEMA ESCURO) */
        body.bioluminescence-mode {
            background-color: #030712;
            color: #f3f4f6;
        }

        body.bioluminescence-mode .news-card {
            background: #111827;
            box-shadow: 0 0 25px rgba(16, 185, 129, 0.25);
            border: 1px solid rgba(16, 185, 129, 0.3);
        }

        body.bioluminescence-mode h1 {
            color: #10b981;
            text-shadow: 0 0 8px rgba(16, 185, 129, 0.4);
        }

        body.bioluminescence-mode h2 {
            color: #9ca3af;
        }

        body.bioluminescence-mode .badge {
            background-color: rgba(16, 185, 129, 0.15);
            color: #34d399;
        }

        body.bioluminescence-mode .news-body p {
            color: #e5e7eb;
        }

        body.bioluminescence-mode .news-footer {
            background: #1f2937;
            color: #9ca3af;
        }
    </style>
</head>
<body>

    <main class="news-card">
        <header class="news-header">
            <span class="badge">Biotecnologia e Sustentabilidade</span>
            <h1 id="news-title">Avanço biotecnológico permite iluminar cidades com plantas brilhantes.</h1>
            <h2 id="news-subtitle">Cientistas desenvolvem vegetais geneticamente modificados para emitir luz suave.</h2>
        </header>

        <section class="meta-info">
            <div class="author-date">
                <span class="author">Por <strong>Lucas Silva</strong></span>
                <span class="dot">•</span>
                <time datetime="2026-08-12">12 de Agosto de 2026</time>
            </div>
            <button id="glow-toggle" class="btn-glow">✨ Modo Bioluminescente</button>
        </section>

        <figure class="news-image-box">
            <div class="image-placeholder">
                <div class="glow-effect"></div>
                <p class="image-desc">
                    📷 <strong>Descrição da Imagem:</strong> Fotografia noturna de um parque urbano sustentável, destacando canteiros e árvores que emitem um brilho verde fluorescente suave, iluminando naturalmente o caminho de pedestres.
                </p>
            </div>
        </figure>

        <article class="news-body">
            <p id="news-content">Pesquisadores criaram uma nova alternativa sustentável para a iluminação de ambientes urbanos. O projeto utiliza engenharia genética para inserir genes bioluminescentes em plantas comuns. Essa inovação visa substituir parte das lâmpadas elétricas em praças e parques, gerando economia energética e reduzindo a pegada de carbono. Os primeiros testes demonstraram um resultado ótimo e totalmente seguro.</p>
        </article>

        <footer class="news-footer">
            <div class="stats">
                <span>Título: <strong id="title-count">0</strong>/70</span>
                <span>Subtítulo: <strong id="sub-count">0</strong>/80</span>
                <span>Conteúdo: <strong id="content-count">0</strong>/400</span>
            </div>
            <button id="copy-btn" class="btn-copy">📋 Copiar Notícia</button>
        </footer>
    </main>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const titleEl = document.getElementById('news-title');
            const subEl = document.getElementById('news-subtitle');
            const contentEl = document.getElementById('news-content');

            const titleCount = document.getElementById('title-count');
            const subCount = document.getElementById('sub-count');
            const contentCount = document.getElementById('content-count');

            const glowBtn = document.getElementById('glow-toggle');
            const copyBtn = document.getElementById('copy-btn');

            // Calcula e exibe a contagem exata de caracteres
            function updateCharacterCounts() {
                titleCount.textContent = titleEl.textContent.length;
                subCount.textContent = subEl.textContent.length;
                contentCount.textContent = contentEl.textContent.length;
            }

            // Ativa/Desativa modo visual bioluminescente
            glowBtn.addEventListener('click', () => {
                document.body.classList.toggle('bioluminescence-mode');
                if (document.body.classList.contains('bioluminescence-mode')) {
                    glowBtn.textContent = '☀️ Modo Normal';
                } else {
                    glowBtn.textContent = '✨ Modo Bioluminescente';
                }
            });

            // Copia o texto da notícia
            copyBtn.addEventListener('click', () => {
                const fullNewsText = `
${titleEl.textContent}
${subEl.textContent}

Disciplina: Biotecnologia e Sustentabilidade
Autor: Lucas Silva
Data: 12 de agosto de 2026

${contentEl.textContent}
                `.trim();

                navigator.clipboard.writeText(fullNewsText).then(() => {
                    const originalText = copyBtn.textContent;
                    copyBtn.textContent = '✅ Copiado!';
                    setTimeout(() => {
                        copyBtn.textContent = originalText;
                    }, 2000);
                });
            });

            updateCharacterCounts();
        });
    </script>
</body>
</html>
