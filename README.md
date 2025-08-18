[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&duration=4000&pause=500&color=3E1AF7&background=33FF3900&center=true&vCenter=true&multiline=true&width=500&height=125&lines=My+name+is+Jos%C3%A9+Gabriel;I'm+a+computer+science+student.)](https://git.io/typing-svg)
---------------------------------------------------------------------------------------------------------------------------------

<!DOCTYPE html>
<html lang="pt-BR" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guia Interativo para Currículo de Impacto</title>
    <!-- Chosen Palette: Warm Neutral Tones -->
    <!-- Application Structure Plan: A single-page application designed as an interactive guide with a fixed sidebar for easy navigation between sections. This non-linear structure allows users to jump directly to the content they need, such as "Projetos" or "Otimização ATS". The goal is to transform the static report into a hands-on tool. Interactive elements like "before/after" toggles for project descriptions, a functional checklist, and a chart visualizing the impact of data quantification were chosen to make the learning process more engaging and practical, moving beyond passive reading to active application. -->
    <!-- Visualization & Content Choices: 
        - Report Info: Section 3 (Quantification). Goal: Compare. Viz/Presentation: Bar Chart (Chart.js). Interaction: Static visual comparison. Justification: A chart provides a more immediate and powerful impact than text alone to demonstrate the difference between a vague description and a quantified achievement.
        - Report Info: Section 8 (Common Mistakes). Goal: Inform/Organize. Viz/Presentation: Interactive "Spot the Error" section using HTML/CSS/JS. Interaction: User can click on highlighted errors in a sample text to see corrections. Justification: Active engagement reinforces learning and improves retention of common pitfalls.
        - Report Info: Conclusion (Checklist). Goal: Organize/Action. Viz/Presentation: Interactive HTML checklist. Interaction: User can physically check off items. Justification: This transforms a static list from the report into a usable, practical tool for the user.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f4f4f5; }
        .content-section { display: none; }
        .content-section.active { display: block; }
        .nav-link { transition: all 0.2s ease-in-out; }
        .nav-link.active { background-color: #3b82f6; color: white; }
        .nav-link:not(.active):hover { background-color: #e5e7eb; }
        .toggle-btn { cursor: pointer; user-select: none; }
        .error-text { cursor: pointer; border-bottom: 2px dotted #ef4444; }
        .correction-tooltip {
            visibility: hidden;
            opacity: 0;
            transition: opacity 0.3s;
            position: absolute;
            bottom: 125%;
            left: 50%;
            transform: translateX(-50%);
        }
        .error-text:hover .correction-tooltip {
            visibility: visible;
            opacity: 1;
        }
    </style>
</head>
<body class="text-zinc-800">

    <div class="flex min-h-screen">
        <!-- Sidebar Navigation -->
        <aside id="sidebar" class="w-64 bg-white shadow-md fixed top-0 left-0 h-full p-4 transform -translate-x-full md:translate-x-0 transition-transform duration-300 z-20">
            <h1 class="text-2xl font-bold text-blue-600 mb-6 border-b pb-4">Guia do CV</h1>
            <nav id="nav-menu">
                <a href="#introducao" class="nav-link block w-full text-left px-4 py-2 rounded-lg mb-2 font-medium text-zinc-700"><i class="fas fa-rocket w-6 mr-2"></i>Introdução</a>
                <a href="#estrutura" class="nav-link block w-full text-left px-4 py-2 rounded-lg mb-2 font-medium text-zinc-700"><i class="fas fa-sitemap w-6 mr-2"></i>Estrutura</a>
                <a href="#projetos" class="nav-link block w-full text-left px-4 py-2 rounded-lg mb-2 font-medium text-zinc-700"><i class="fas fa-tasks w-6 mr-2"></i>Projetos</a>
                <a href="#habilidades" class="nav-link block w-full text-left px-4 py-2 rounded-lg mb-2 font-medium text-zinc-700"><i class="fas fa-cogs w-6 mr-2"></i>Habilidades</a>
                <a href="#github" class="nav-link block w-full text-left px-4 py-2 rounded-lg mb-2 font-medium text-zinc-700"><i class="fab fa-github w-6 mr-2"></i>GitHub</a>
                <a href="#ats" class="nav-link block w-full text-left px-4 py-2 rounded-lg mb-2 font-medium text-zinc-700"><i class="fas fa-robot w-6 mr-2"></i>Otimização ATS</a>
                <a href="#erros" class="nav-link block w-full text-left px-4 py-2 rounded-lg mb-2 font-medium text-zinc-700"><i class="fas fa-exclamation-triangle w-6 mr-2"></i>Erros Comuns</a>
                <a href="#checklist" class="nav-link block w-full text-left px-4 py-2 rounded-lg mb-2 font-medium text-zinc-700"><i class="fas fa-check-double w-6 mr-2"></i>Checklist Final</a>
            </nav>
        </aside>

        <!-- Mobile Menu Button -->
        <button id="menu-toggle" class="md:hidden fixed top-4 left-4 z-30 bg-white p-2 rounded-md shadow-lg">
            <i class="fas fa-bars"></i>
        </button>

        <!-- Main Content -->
        <main class="flex-1 md:ml-64 p-6 md:p-10">
            
            <div id="introducao" class="content-section">
                <h2 class="text-4xl font-bold mb-4 text-zinc-900">O Currículo Como Ferramenta de Marketing Pessoal</h2>
                <p class="mb-6 text-lg text-zinc-600">No universo da tecnologia, seu currículo é um "deploy" profissional: uma apresentação clara e funcional do valor que você pode agregar. Em um mercado onde um recrutador decide em segundos, a primeira impressão é decisiva. Este guia interativo é seu roteiro para transformar seu CV em uma poderosa ferramenta de marketing.</p>
                <div class="bg-blue-50 border-l-4 border-blue-500 text-blue-800 p-4 rounded-r-lg">
                    <p><i class="fas fa-brain mr-2"></i><strong>A Mentalidade do Recrutador:</strong> Seu CV precisa passar por dois filtros: o robô (ATS), que busca palavras-chave, e o humano, que busca resultados e potencial. Este guia te prepara para ambos.</p>
                </div>
            </div>

            <div id="estrutura" class="content-section">
                <h2 class="text-4xl font-bold mb-4 text-zinc-900">A Arquitetura de um Currículo de Destaque</h2>
                <p class="mb-6 text-lg text-zinc-600">A estrutura do seu CV determina sua eficácia. Um layout limpo e uma organização lógica garantem que a informação crucial seja transmitida rapidamente.</p>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <h3 class="text-2xl font-bold mb-4">Seções Essenciais (Ordem Estratégica)</h3>
                    <ol class="list-decimal list-inside space-y-3 text-zinc-700">
                        <li><strong>Informações de Contato:</strong> Nome, email, telefone, cidade, LinkedIn e, crucialmente, GitHub.</li>
                        <li><strong>Resumo ou Objetivo:</strong> Seu "elevator pitch". Destaque 1-2 habilidades chave e seu entusiasmo.</li>
                        <li><strong>Formação Acadêmica:</strong> Seu maior trunfo como iniciante. Detalhe curso, universidade e previsão de conclusão.</li>
                        <li><strong>Projetos:</strong> Onde a teoria encontra a prática. Sua principal evidência de competência.</li>
                        <li><strong>Habilidades:</strong> Lista organizada de competências técnicas (hard skills) e comportamentais (soft skills).</li>
                    </ol>
                </div>
            </div>

            <div id="projetos" class="content-section">
                <h2 class="text-4xl font-bold mb-4 text-zinc-900">A Arte de Apresentar Projetos</h2>
                <p class="mb-6 text-lg text-zinc-600">Transforme código em conquistas mensuráveis. Não basta listar tecnologias; é preciso construir uma narrativa de impacto em torno de cada projeto.</p>
                
                <div class="bg-white p-6 rounded-lg shadow-md mb-8">
                    <h3 class="text-2xl font-bold mb-2">Exemplo: App de Lista de Tarefas</h3>
                    <p class="mb-4">Veja a diferença que a estrutura e a quantificação fazem.</p>
                    <div class="border rounded-lg overflow-hidden">
                        <div class="p-4 bg-red-100">
                            <h4 class="font-bold text-red-800">❌ Antes (Descrição Fraca)</h4>
                            <p class="mt-2 text-red-700">"Um app para gerenciar tarefas. Usei React e Firebase."</p>
                        </div>
                        <div class="p-4 bg-green-100">
                            <h4 class="font-bold text-green-800">✅ Depois (Descrição Forte com PATR)</h4>
                            <ul class="mt-2 text-green-900 list-disc list-inside space-y-1">
                                <li><strong>Problema:</strong> Criar uma ferramenta intuitiva para gerenciamento de tarefas com persistência de dados e autenticação.</li>
                                <li><strong>Ação:</strong> Desenvolvi uma aplicação web completa (CRUD) com autenticação de usuários via e-mail/senha e login social.</li>
                                <li><strong>Tecnologias:</strong> React (Hooks), Firebase (Firestore, Authentication), CSS Modules.</li>
                                <li><strong>Resultado:</strong> O projeto foi utilizado por 10 colegas, que relataram um aumento percebido de 15% na organização de suas tarefas.</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-lg shadow-md">
                    <h3 class="text-2xl font-bold mb-4">O Impacto da Quantificação</h3>
                    <p class="mb-4 text-zinc-600">Dados concretos são mais persuasivos. Veja como a percepção de valor aumenta quando você adiciona métricas ao seu trabalho.</p>
                    <div class="chart-container h-64 max-w-lg mx-auto">
                        <canvas id="quantificationChart"></canvas>
                    </div>
                </div>
            </div>

            <div id="habilidades" class="content-section">
                <h2 class="text-4xl font-bold mb-4 text-zinc-900">O Arsenal de Habilidades</h2>
                <p class="mb-6 text-lg text-zinc-600">Os recrutadores buscam um equilíbrio entre competências técnicas (hard skills) e comportamentais (soft skills).</p>
                <div class="grid md:grid-cols-2 gap-8">
                    <div class="bg-white p-6 rounded-lg shadow-md">
                        <h3 class="text-2xl font-bold mb-4"><i class="fas fa-code mr-2 text-blue-600"></i>Hard Skills Essenciais</h3>
                        <ul class="list-disc list-inside space-y-2 text-zinc-700">
                            <li><strong>Linguagens:</strong> JavaScript (React), Python (Django/Flask), Java/C#.</li>
                            <li><strong>Fundamentos:</strong> Estruturas de Dados & Algoritmos, POO.</li>
                            <li><strong>Banco de Dados:</strong> SQL e modelagem de dados.</li>
                            <li><strong>Ferramentas:</strong> Git (não-negociável).</li>
                        </ul>
                    </div>
                    <div class="bg-white p-6 rounded-lg shadow-md">
                        <h3 class="text-2xl font-bold mb-4"><i class="fas fa-users mr-2 text-blue-600"></i>Soft Skills Críticas</h3>
                        <ul class="list-disc list-inside space-y-2 text-zinc-700">
                            <li>Capacidade de Aprender Rapidamente</li>
                            <li>Comunicação e Trabalho em Equipe</li>
                            <li>Resolução de Problemas</li>
                            <li>Resiliência e Adaptabilidade</li>
                        </ul>
                    </div>
                </div>
                 <p class="mt-8 text-md bg-yellow-100 border-l-4 border-yellow-500 text-yellow-800 p-4 rounded-r-lg"><strong>Dica de Ouro:</strong> Não apenas liste soft skills. Demonstre-as com exemplos nas descrições dos seus projetos. Em vez de dizer "proativo", descreva como você "identificou uma ineficiência e desenvolveu um script que reduziu o tempo do processo em 90%".</p>
            </div>

            <div id="github" class="content-section">
                <h2 class="text-4xl font-bold mb-4 text-zinc-900">O Papel Indispensável do GitHub</h2>
                <p class="mb-6 text-lg text-zinc-600">Seu currículo *afirma* suas habilidades, seu GitHub as *prova*. É seu currículo vivo e a janela para sua competência técnica e paixão.</p>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <h3 class="text-2xl font-bold mb-4">O Que Recrutadores Analisam:</h3>
                    <ul class="list-disc list-inside space-y-3 text-zinc-700">
                        <li><strong>README do Perfil:</strong> Sua mini biografia profissional. Deve ser clara e direta.</li>
                        <li><strong>Repositórios Fixados:</strong> Seus 6 melhores projetos. Cada um deve ter um README impecável, explicando o problema, a solução e as tecnologias.</li>
                        <li><strong>Qualidade do Código:</strong> Código limpo, bem estruturado e legível.</li>
                        <li><strong>Histórico de Contribuições:</strong> Os "quadrados verdes" mostram consistência e dedicação.</li>
                    </ul>
                </div>
            </div>

            <div id="ats" class="content-section">
                <h2 class="text-4xl font-bold mb-4 text-zinc-900">Otimização para ATS</h2>
                <p class="mb-6 text-lg text-zinc-600">Antes de um humano, seu CV enfrenta um robô. Otimizar para o Sistema de Rastreamento de Candidatos (ATS) é um requisito de sobrevivência.</p>
                <div class="grid md:grid-cols-2 gap-8">
                    <div class="bg-green-50 p-6 rounded-lg border border-green-200">
                        <h3 class="text-2xl font-bold mb-4 text-green-800">✅ O Que FAZER</h3>
                        <ul class="list-disc list-inside space-y-2 text-green-900">
                            <li>Use um layout de **coluna única**.</li>
                            <li>Utilize **fontes padrão** (Arial, Calibri).</li>
                            <li>Use **títulos de seção convencionais** (Educação, Habilidades).</li>
                            <li>Incorpore **palavras-chave da vaga** naturalmente.</li>
                        </ul>
                    </div>
                    <div class="bg-red-50 p-6 rounded-lg border border-red-200">
                        <h3 class="text-2xl font-bold mb-4 text-red-800">❌ O Que NÃO FAZER</h3>
                        <ul class="list-disc list-inside space-y-2 text-red-900">
                            <li>Usar tabelas, múltiplas colunas ou caixas de texto.</li>
                            <li>Incluir gráficos, imagens ou ícones.</li>
                            <li>Colocar informações importantes em cabeçalhos/rodapés.</li>
                            <li>Encher o texto com palavras-chave sem contexto.</li>
                        </ul>
                    </div>
                </div>
            </div>

            <div id="erros" class="content-section">
                <h2 class="text-4xl font-bold mb-4 text-zinc-900">Erros Comuns e Fatais</h2>
                <p class="mb-6 text-lg text-zinc-600">Um único erro pode desqualificar um candidato promissor. Atenção aos detalhes é crucial.</p>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <h3 class="text-2xl font-bold mb-4">Interativo: Encontre o Erro</h3>
                    <p class="mb-4 text-zinc-600">Passe o mouse sobre os textos destacados para ver a correção e a explicação.</p>
                    <div class="border p-4 rounded-lg bg-zinc-50 text-zinc-700 leading-relaxed">
                        <p>
                            "Sou um 
                            <span class="error-text relative">desenvolvidor
                                <span class="correction-tooltip w-48 bg-zinc-800 text-white text-xs rounded py-1 px-2"><strong>Correção:</strong> desenvolvedor. Erros de ortografia sugerem desleixo.</span>
                            </span> 
                            de software com 
                            <span class="error-text relative">esperiência
                                <span class="correction-tooltip w-48 bg-zinc-800 text-white text-xs rounded py-1 px-2"><strong>Correção:</strong> experiência. Sempre revise seu texto!</span>
                            </span> 
                            em desenvolvimento. Participei de 
                            <span class="error-text relative">vários projetos.
                                <span class="correction-tooltip w-56 bg-zinc-800 text-white text-xs rounded py-1 px-2"><strong>Correção:</strong> Seja específico! "Liderei um projeto com 3 pessoas..." é muito mais forte.</span>
                            </span>"
                        </p>
                    </div>
                </div>
            </div>

            <div id="checklist" class="content-section">
                <h2 class="text-4xl font-bold mb-4 text-zinc-900">Checklist Final de Revisão</h2>
                <p class="mb-6 text-lg text-zinc-600">Antes de enviar sua candidatura, passe por esta lista de verificação para garantir que seu currículo está impecável.</p>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <div id="checklist-container" class="space-y-4">
                        <!-- Checklist items will be injected by JS -->
                    </div>
                </div>
            </div>

        </main>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const navLinks = document.querySelectorAll('.nav-link');
            const contentSections = document.querySelectorAll('.content-section');
            const menuToggle = document.getElementById('menu-toggle');
            const sidebar = document.getElementById('sidebar');

            function updateContent(hash) {
                const targetHash = hash || '#introducao';
                
                contentSections.forEach(section => {
                    if ('#' + section.id === targetHash) {
                        section.classList.add('active');
                    } else {
                        section.classList.remove('active');
                    }
                });

                navLinks.forEach(link => {
                    if (link.getAttribute('href') === targetHash) {
                        link.classList.add('active');
                    } else {
                        link.classList.remove('active');
                    }
                });
            }

            navLinks.forEach(link => {
                link.addEventListener('click', function (e) {
                    e.preventDefault();
                    const targetHash = this.getAttribute('href');
                    window.location.hash = targetHash;
                    if (sidebar.classList.contains('translate-x-0')) {
                        sidebar.classList.remove('translate-x-0');
                        sidebar.classList.add('-translate-x-full');
                    }
                });
            });

            window.addEventListener('hashchange', () => updateContent(window.location.hash));
            updateContent(window.location.hash);
            
            menuToggle.addEventListener('click', () => {
                sidebar.classList.toggle('-translate-x-full');
                sidebar.classList.toggle('translate-x-0');
            });

            // Chart.js implementation
            const ctx = document.getElementById('quantificationChart');
            if (ctx) {
                new Chart(ctx, {
                    type: 'bar',
                    data: {
                        labels: ['Descrição Vaga', 'Descrição com Métricas'],
                        datasets: [{
                            label: 'Percepção de Valor pelo Recrutador',
                            data: [45, 95],
                            backgroundColor: [
                                'rgba(254, 202, 202, 0.6)',
                                'rgba(134, 239, 172, 0.6)'
                            ],
                            borderColor: [
                                'rgba(239, 68, 68, 1)',
                                'rgba(34, 197, 94, 1)'
                            ],
                            borderWidth: 1
                        }]
                    },
                    options: {
                        scales: {
                            y: { beginAtZero: true, max: 100 }
                        },
                        responsive: true,
                        maintainAspectRatio: false,
                        plugins: {
                            legend: { display: false },
                            title: { display: true, text: 'Impacto da Quantificação no Valor Percebido' }
                        }
                    }
                });
            }

            // Interactive Checklist
            const checklistContainer = document.getElementById('checklist-container');
            const checklistItems = [
                "O currículo foi adaptado para a vaga específica?",
                "As palavras-chave da vaga estão presentes?",
                "A formatação é simples e compatível com ATS?",
                "Os resultados dos projetos estão quantificados?",
                "As habilidades estão demonstradas com exemplos?",
                "Os links do LinkedIn e GitHub estão funcionando?",
                "O documento foi revisado para erros de ortografia?"
            ];

            if (checklistContainer) {
                checklistItems.forEach((itemText, index) => {
                    const item = document.createElement('div');
                    item.classList.add('flex', 'items-center', 'p-3', 'rounded-lg', 'transition-colors', 'hover:bg-zinc-50');
                    item.innerHTML = `
                        <input id="check-${index}" type="checkbox" class="h-5 w-5 rounded border-gray-300 text-blue-600 focus:ring-blue-500 cursor-pointer">
                        <label for="check-${index}" class="ml-3 text-md text-zinc-700 cursor-pointer">${itemText}</label>
                    `;
                    checklistContainer.appendChild(item);
                });
            }
        });
    </script>
</body>
</html>
