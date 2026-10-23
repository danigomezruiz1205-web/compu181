<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aprende Computación Básica - Preparatoria</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- QRCode.js Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <!-- Marked.js -->
    <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
    <!-- Google Fonts: Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc;
            color: #1e293b;
        }
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            20%, 60% { transform: translateX(-6px); }
            40%, 80% { transform: translateX(6px); }
        }
        .animate-shake {
            animation: shake 0.4s ease-in-out;
        }
        .tab-btn.active {
            background-color: #2563eb;
            color: #ffffff;
            box-shadow: 0 4px 6px -1px rgba(37, 99, 235, 0.2);
        }
        .ai-formatted-content p { margin-bottom: 0.5rem; }
        .ai-formatted-content p:last-child { margin-bottom: 0; }
        .ai-formatted-content ul { list-style-type: disc; padding-left: 1.25rem; margin-bottom: 0.5rem; }
        .ai-formatted-content ol { list-style-type: decimal; padding-left: 1.25rem; margin-bottom: 0.5rem; }
        .ai-formatted-content code { background-color: #f1f5f9; color: #db2777; padding: 0.1rem 0.3rem; border-radius: 0.25rem; font-family: monospace; font-size: 0.85em; }
        .ai-formatted-content pre { background-color: #0f172a; color: #38bdf8; padding: 0.75rem; border-radius: 0.5rem; overflow-x: auto; margin: 0.5rem 0; font-family: monospace; font-size: 0.85em; }
        .ai-formatted-content pre code { background-color: transparent; color: inherit; padding: 0; }
        .ai-formatted-content table { border-collapse: collapse; width: 100%; margin: 0.5rem 0; font-size: 0.85rem; }
        .ai-formatted-content th, .ai-formatted-content td { border: 1px solid #cbd5e1; padding: 0.4rem 0.6rem; text-align: left; }
        .ai-formatted-content th { background-color: #f1f5f9; font-weight: 600; }
    </style>
</head>
<body class="min-h-screen flex flex-col">

    <!-- Encabezado / Navbar -->
    <header class="bg-slate-900 text-white sticky top-0 z-50 shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center gap-3">
                    <div class="bg-blue-600 p-2 rounded-xl text-white">
                        <i class="fa-solid fa-laptop-code text-xl"></i>
                    </div>
                    <div>
                        <h1 class="font-bold text-lg leading-tight">CompuPrep 181</h1>
                        <p class="text-xs text-slate-400">Portal de Computación Básica e Informática</p>
                    </div>
                </div>
                <div class="hidden md:flex items-center gap-2">
                    <span class="inline-flex items-center gap-1.5 py-1 px-3 rounded-full text-xs font-medium bg-emerald-500/10 text-emerald-400 border border-emerald-500/20">
                        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
                        Asistente Integro 100% Autónomo
                    </span>
                    <button onclick="descargarCodigoPagina()" class="py-1 px-3 rounded-xl text-xs font-semibold bg-blue-600 hover:bg-blue-500 text-white transition-all flex items-center gap-1.5 shadow-sm">
                        <i class="fa-solid fa-download"></i> Descargar Web App
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Menú de Pestañas -->
        <nav class="bg-slate-800 border-t border-slate-700/50 overflow-x-auto scrollbar-none">
            <div class="max-w-7xl mx-auto px-4 flex gap-2 py-2 min-w-max">
                <button onclick="changeTab('word')" id="tab-word" class="tab-btn active px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-file-word text-blue-400"></i> Word
                </button>
                <button onclick="changeTab('excel')" id="tab-excel" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-file-excel text-emerald-400"></i> Excel
                </button>
                <button onclick="changeTab('powerpoint')" id="tab-powerpoint" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-file-powerpoint text-orange-400"></i> PowerPoint
                </button>
                <button onclick="changeTab('libros')" id="tab-libros" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-book-bookmark text-amber-400"></i> Guías y Libros
                </button>
                <button onclick="changeTab('atajos')" id="tab-atajos" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-keyboard text-purple-400"></i> Atajos de Teclado
                </button>
                <button onclick="changeTab('juego')" id="tab-juego" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-gamepad text-pink-400"></i> Desafío Atajos
                </button>
                <button onclick="changeTab('quiz')" id="tab-quiz" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-graduation-cap text-cyan-400"></i> Quiz Evaluativo
                </button>
                <button onclick="changeTab('ia')" id="tab-ia" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-robot text-indigo-400"></i> Tutor IA Pro
                </button>
                <button onclick="changeTab('descargar')" id="tab-descargar" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-mobile-screen-button text-emerald-400"></i> Instalar / APK
                </button>
                <button onclick="changeTab('qr')" id="tab-qr" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-qrcode text-rose-400"></i> Código QR
                </button>
            </div>
        </nav>
    </header>

    <!-- Contenido Principal -->
    <main class="flex-grow max-w-7xl w-full mx-auto p-4 sm:p-6 lg:p-8">

        <!-- PESTAÑA: WORD -->
        <section id="content-word" class="tab-content block space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <div class="flex items-center gap-3 mb-4">
                    <div class="bg-blue-100 text-blue-600 p-3 rounded-xl">
                        <i class="fa-solid fa-file-word text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-800">Microsoft Word: Guía Práctica de Formato y Estilos</h2>
                        <p class="text-sm text-slate-500">Tutoriales paso a paso para edición, formato tipográfico, colores, bordes y diseño académico</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-3 gap-4 mb-6">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-font text-blue-600"></i> Cambiar Fuente, Tamaños y Colores
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Seleccionar Texto:</b> Haz clic y arrastra sobre el texto (o presiona <kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl + E</kbd>).</li>
                            <li><b>Cambiar Fuente y Tamaño:</b> En <b>Inicio</b>, usa los selectores de fuente y tamaño.</li>
                            <li><b>Color de Fuente:</b> Usa el icono <b class="text-blue-600 font-bold">A</b> con barra de color.</li>
                            <li><b>Resaltado:</b> Usa el plumón marca-textos (<b class="bg-amber-200 px-1 rounded">ab</b>).</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-align-left text-blue-600"></i> Alineación e Interlineado
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Alineaciones:</b> Izquierda (<kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl+Q</kbd>), Centrado (<kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl+T</kbd>), Derecha (<kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl+D</kbd>), Justificado (<kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl+J</kbd>).</li>
                            <li><b>Interlineado:</b> Cambia a 1.0, 1.5 o 2.0 (Doble).</li>
                            <li><b>Sangría:</b> Presiona <kbd class="px-1 bg-slate-200 rounded font-mono">Tabulador</kbd> (1.27 cm en APA).</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-wand-magic-sparkles text-blue-600"></i> Estilos e Índices
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Estilos Rápidos:</b> Usa <b>Título 1</b> y <b>Título 2</b> en la galería.</li>
                            <li><b>Índice Automático:</b> Ve a <i>Referencias > Tabla de contenido</i>.</li>
                            <li><b>Modificar Estilos:</b> Clic derecho sobre Título 1 > <i>Modificar</i>.</li>
                        </ol>
                    </div>
                </div>

                <!-- Taller Interactivo Word -->
                <div class="bg-slate-50 p-5 rounded-2xl border border-slate-200">
                    <h3 class="font-bold text-slate-800 mb-2 flex items-center gap-2">
                        <i class="fa-solid fa-eye text-blue-600"></i> Taller Interactivo: Formato de Texto
                    </h3>
                    <div class="grid md:grid-cols-4 gap-3 mb-4 bg-white p-3 rounded-xl border border-slate-200">
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Color de Letra</label>
                            <input type="color" id="demo-text-color" value="#1e293b" onchange="actualizarDemoWord()" class="w-full h-9 p-1 bg-white border border-slate-300 rounded-lg cursor-pointer">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Tipo de Fuente</label>
                            <select id="demo-text-font" onchange="actualizarDemoWord()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium">
                                <option value="Inter, sans-serif">Inter</option>
                                <option value="Times New Roman, serif">Times New Roman</option>
                                <option value="Arial, sans-serif">Arial</option>
                                <option value="Courier New, monospace">Courier New</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Tamaño</label>
                            <select id="demo-text-size" onchange="actualizarDemoWord()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium">
                                <option value="12px">12 px</option>
                                <option value="16px" selected>16 px</option>
                                <option value="20px">20 px</option>
                                <option value="24px">24 px</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Alineación</label>
                            <select id="demo-text-align" onchange="actualizarDemoWord()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium">
                                <option value="left">Izquierda</option>
                                <option value="center">Centrado</option>
                                <option value="right">Derecha</option>
                                <option value="justify">Justificado</option>
                            </select>
                        </div>
                    </div>

                    <div id="word-preview-box" class="p-6 bg-white border border-slate-300 rounded-xl shadow-inner min-h-[120px] transition-all">
                        <h4 id="demo-preview-title" class="font-bold mb-2">Título de Ejemplo en Microsoft Word</h4>
                        <p id="demo-preview-p" class="leading-relaxed">
                            Este es un párrafo de muestra. Modifica los controles superiores para observar los cambios en tiempo real.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- PESTAÑA: EXCEL -->
        <section id="content-excel" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <div class="flex items-center gap-3 mb-4">
                    <div class="bg-emerald-100 text-emerald-600 p-3 rounded-xl">
                        <i class="fa-solid fa-file-excel text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-800">Microsoft Excel: Formato, Fórmulas y Colores</h2>
                        <p class="text-sm text-slate-500">Personalización de celdas, formato condicional y funciones lógicas</p>
                    </div>
                </div>

                <!-- Simulador de Promedios -->
                <div class="bg-slate-50 p-5 rounded-2xl border border-slate-200 mb-6">
                    <h3 class="font-bold text-slate-800 mb-2 flex items-center gap-2">
                        <i class="fa-solid fa-calculator text-emerald-600"></i> Simulador Interactivo de Calificaciones (=PROMEDIO y =SI)
                    </h3>
                    <p class="text-sm text-slate-600 mb-4">Ingresa 3 calificaciones para calcular automáticamente el promedio y estatus.</p>
                    
                    <div class="grid sm:grid-cols-3 gap-4 mb-4">
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Parcial 1</label>
                            <input type="number" id="calif1" min="0" max="10" value="8" oninput="calcularPromedio()" class="w-full p-2.5 bg-white border border-slate-300 rounded-lg font-medium text-slate-800 focus:ring-2 focus:ring-emerald-500 focus:outline-none">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Parcial 2</label>
                            <input type="number" id="calif2" min="0" max="10" value="7" oninput="calcularPromedio()" class="w-full p-2.5 bg-white border border-slate-300 rounded-lg font-medium text-slate-800 focus:ring-2 focus:ring-emerald-500 focus:outline-none">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Examen Final</label>
                            <input type="number" id="calif3" min="0" max="10" value="5" oninput="calcularPromedio()" class="w-full p-2.5 bg-white border border-slate-300 rounded-lg font-medium text-slate-800 focus:ring-2 focus:ring-emerald-500 focus:outline-none">
                        </div>
                    </div>

                    <div class="p-4 bg-white rounded-xl border border-slate-200 flex flex-wrap items-center justify-between gap-4">
                        <div>
                            <span class="text-xs text-slate-500 block">Promedio Final:</span>
                            <span id
