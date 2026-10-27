<!DOCTYPE html>  
<html lang="pt-BR">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Painel Alpha - Centro de Comando</title>  
    <!-- Importando Tailwind CSS e FontAwesome para ícones -->  
    <script src="https://cdn.tailwindcss.com"></script>  
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">  
    <script>  
        tailwind.config = {  
            theme: {  
                extend: {  
                    colors: {  
                        darkBg: '#0b0f19',  
                        cardBg: '#131c2e',  
                        goldAccent: '#d4af37',  
                        siriusBlue: '#3b82f6',  
                        darkBorder: '#1e293b'  
                    }  
                }  
            }  
        }  
    </script>  
    <style>  
        body { background-color: #0b0f19; color: #f8fafc; font-family: 'Inter', sans-serif; }  
        .glow-gold { box-shadow: 0 0 20px rgba(212, 175, 55, 0.15); }  
        .glow-blue { box-shadow: 0 0 20px rgba(59, 130, 246, 0.15); }  
    </style>  
</head>  
<body class="flex h-screen overflow-hidden">  
  
    <!-- MENU LATERAL (SIDEBAR) -->  
    <aside class="w-20 bg-cardBg border-r border-darkBorder flex flex-col items-center py-6 justify-between z-10">  
        <div class="flex flex-col items-center gap-8">  
            <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-goldAccent to-amber-600 flex items-center justify-center text-darkBg font-bold text-xl glow-gold">  
                α  
            </div>  
            <nav class="flex flex-col gap-4">  
                <button onclick="mudarAba('dashboard')" id="btn-dashboard" class="w-12 h-12 rounded-xl bg-darkBg text-goldAccent flex items-center justify-center text-lg transition hover:bg-goldAccent hover:text-darkBg shadow-inner">  
                    <i class="fa-solid fa-chart-pie"></i>  
                </button>  
                <button onclick="mudarAba('leiloes')" id="btn-leiloes" class="w-12 h-12 rounded-xl text-slate-400 flex items-center justify-center text-lg transition hover:bg-slate-800 hover:text-white">  
                    <i class="fa-solid fa-gavel"></i>  
                </button>  
                <button onclick="mudarAba('compradores')" id="btn-compradores" class="w-12 h-12 rounded-xl text-slate-400 flex items-center justify-center text-lg transition hover:bg-slate-800 hover:text-white">  
                    <i class="fa-solid fa-users"></i>  
                </button>  
                <button onclick="mudarAba('tesouraria')" id="btn-tesouraria" class="w-12 h-12 rounded-xl text-slate-400 flex items-center justify-center text-lg transition hover:bg-slate-800 hover:text-white">  
                    <i class="fa-solid fa-vault"></i>  
                </button>  
            </nav>  
        </div>  
        <div class="text-slate-600 text-xs font-mono">v3.3</div>  
    </aside>  
  
    <!-- CONTEÚDO PRINCIPAL -->  
    <main class="flex-1 flex flex-col overflow-y-auto">  
          
        <!-- HEADER -->  
        <header class="h-20 border-b border-darkBorder px-8 flex items-center justify-between bg-darkBg/50 backdrop-blur sticky top-0 z-20">  
            <div>  
                <h1 id="titulo-pagina" class="text-xl font-bold tracking-wide text-white">Centro de Comando</h1>  
                <p class="text-xs text-slate-400">Operando nas sombras — Sistema Autônomo Ativo</p>  
            </div>  
            <div class="flex items-center gap-4">  
                <div class="px-3 py-1.5 rounded-lg bg-cardBg border border-darkBorder text-xs flex items-center gap-2">  
                    <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>  
                    <span class="text-slate-300">Servidores Cloud: <strong class="text-emerald-400">Online</strong></span>  
                </div>  
            </div>  
        </header>  
  
        <!-- ÁREA DAS ABAS -->  
        <div class="p-8 flex-1">  
  
            <!-- ABA 1: DASHBOARD GERAL -->  
            <section id="aba-dashboard" class="space-y-6">  
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">  
                    <div class="p-6 rounded-2xl bg-cardBg border border-darkBorder glow-gold">  
                        <p class="text-xs font-medium text-slate-400 uppercase tracking-wider">Capital Garimpado</p>  
                        <h3 class="text-3xl font-bold text-white mt-2">R$ 3.450.000</h3>  
                        <span class="text-xs text-emerald-400 mt-1 inline-block">+18% esta semana</span>  
                    </div>  
                    <div class="p-6 rounded-2xl bg-cardBg border border-darkBorder glow-blue">  
                        <p class="text-xs font-medium text-slate-400 uppercase tracking-wider">Alvos Rastreados</p>  
                        <h3 class="text-3xl font-bold text-white mt-2">142</h3>  
                        <span class="text-xs text-blue-400 mt-1 inline-block">Varredura noturna concluída</span>  
                    </div>  
                    <div class="p-6 rounded-2xl bg-cardBg border border-darkBorder">  
                        <p class="text-xs font-medium text-slate-400 uppercase tracking-wider">Leads de Alto Padrão</p>  
                        <h3 class="text-3xl font-bold text-white mt-2">38</h3>  
                        <span class="text-xs text-amber-400 mt-1 inline-block">Prontos para pitch</span>  
                    </div>  
                </div>  
  
                <div class="p-6 rounded-2xl bg-cardBg border border-darkBorder">  
                    <h3 class="text-lg font-semibold text-white mb-4">Ações Rápidas do Sistema</h3>  
                    <div class="flex flex-wrap gap-4">  
                        <button onclick="dispararNotificacao('⚠️ COMANDO MANUAL: Forçando varredura imediata de leilões.')" class="px-5 py-2.5 rounded-xl bg-goldAccent text-darkBg font-semibold text-sm transition hover:bg-amber-500">  
                            <i class="fa-solid fa-radar mr-2"></i> Forçar Varredura Agora  
                        </button>  
                        <button onclick="mudarAba('leiloes')" class="px-5 py-2.5 rounded-xl bg-slate-800 text-slate-200 font-semibold text-sm border border-darkBorder transition hover:bg-slate-700">  
                            Ver Alvos Atuais  
                        </button>  
                    </div>  
                </div>  
            </section>  
  
            <!-- ABA 2: RADAR DE LEILÕES -->  
            <section id="aba-leiloes" class="space-y-6 hidden">  
                <div class="flex justify-between items-center">  
                    <h2 class="text-lg font-bold text-white">Imóveis Subvalorizados & Leilões</h2>  
                    <span class="text-xs text-slate-400 font-mono">Atualizado às 03:00 AM</span>  
                </div>  
                  
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">  
                    <div class="p-6 rounded-2xl bg-cardBg border border-darkBorder space-y-4">  
                        <div class="flex justify-between items-start">  
                            <div>  
                                <span class="text-xs px-2.5 py-1 rounded-md bg-emerald-500/10 text-emerald-400 font-medium">Margem de 50%</span>  
                                <h3 class="text-lg font-bold text-white mt-2">Aptº Zona Sul - Cobertura</h3>  
                            </div>  
                            <span class="text-xs font-mono text-slate-400">Leilão Caixa</span>  
                        </div>  
                        <div class="grid grid-cols-2 gap-4 py-2 border-y border-darkBorder text-sm">  
                            <div>  
                                <p class="text-slate-400 text-xs">Avaliação:</p>  
                                <p class="font-semibold text-white">R$ 1.200.000</p>  
                            </div>  
                            <div>  
                                <p class="text-slate-400 text-xs">Lance Inicial:</p>  
                                <p class="font-semibold text-emerald-400">R$ 600.000</p>  
                            </div>  
                        </div>  
                        <button onclick="dispararNotificacao('🎯 ANALISANDO EDITAL: Aptº Zona Sul (Lance R$ 600k). Risco jurídico zero. Lucro projetado em R$ 400k.')" class="w-full py-2.5 rounded-xl bg-goldAccent text-darkBg font-semibold text-sm transition hover:bg-amber-500">  
                            Analisar Edital pela IA  
                        </button>  
                    </div>  
                </div>  
            </section>  
  
            <!-- ABA 3: COMPRADORES DE ALTO PADRÃO -->  
            <section id="aba-compradores" class="space-y-6 hidden">  
                <div class="flex justify-between items-center">  
                    <h2 class="text-lg font-bold text-white">Rede de Compradores (Liquidez Alta)</h2>  
                </div>  
                <div class="p-6 rounded-2xl bg-cardBg border border-darkBorder space-y-4">  
                    <div class="flex justify-between items-center">  
                        <div>  
                            <h3 class="font-bold text-white">Carlos Eduardo M.</h3>  
                            <p class="text-xs text-slate-400">Ex-CEO / Tech Founder (Liquidez Imediata)</p>  
                        </div>  
                        <span class="text-xs px-2.5 py-1 rounded-md bg-blue-500/10 text-blue-400">Perfil Premium</span>  
                    </div>  
                    <button onclick="dispararNotificacao('📤 PITCH ENVIADO: Oportunidade de imóvel Zona Sul enviada para Carlos Eduardo M.')" class="w-full py-2.5 rounded-xl bg-siriusBlue text-white font-semibold text-sm transition hover:bg-blue-600">  
                        Enviar Pitch do Imóvel  
                    </button>  
                </div>  
            </section>  
  
            <!-- ABA 4: TESOURARIA (PIX) -->  
            <section id="aba-tesouraria" class="space-y-6 hidden">  
                <div class="p-6 rounded-2xl bg-cardBg border border-darkBorder space-y-4">  
                    <h2 class="text-lg font-bold text-white">Tesouraria & Saques</h2>  
                    <p class="text-xs text-slate-400">Sua chave PIX cadastrada para recebimento automático dos lucros:</p>  
                    <div class="p-3 bg-darkBg border border-darkBorder rounded-xl font-mono text-xs text-goldAccent select-all">  
                        74137e27-014f-41af-97e1-1f162c1a925a  
                    </div>  
                </div>  
            </section>  
  
        </div>  
    </main>  
  
    <!-- SCRIPT DE NAVEGAÇÃO E INTEGRAÇÃO -->  
    <script>  
        // COFRE DE CHAVES DO TELEGRAM (Substitua se desejar usar as notificações)  
        const BOT_CONFIG = {  
            token: "SEU_TOKEN_AQUI",  
            chatId: "SEU_CHAT_ID_AQUI"  
        };  
  
        function mudarAba(aba) {  
            // Esconde todas  
            document.getElementById('aba-dashboard').classList.add('hidden');  
            document.getElementById('aba-leiloes').classList.add('hidden');  
            document.getElementById('aba-compradores').classList.add('hidden');  
            document.getElementById('aba-tesouraria').classList.add('hidden');  
  
            // Reseta cores dos botões  
            document.getElementById('btn-dashboard').className = "w-12 h-12 rounded-xl text-slate-400 flex items-center justify-center text-lg transition hover:bg-slate-800 hover:text-white";  
            document.getElementById('btn-leiloes').className = "w-12 h-  
