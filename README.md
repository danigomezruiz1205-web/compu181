[889.html](https://github.com/user-attachments/files/33849834/889.html)
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
                        Asistente IA Offline Activo
                    </span>
                </div>
            </div>
        </div>
        
        <!-- Menú de Pestañas Navegables -->
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
                    <i class="fa-solid fa-robot text-indigo-400"></i> Preguntas a IA
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
                        <h2 class="text-xl font-bold text-slate-800">Procesador de Textos: Microsoft Word</h2>
                        <p class="text-sm text-slate-500">Fundamentos de edición, formatos académicos y estructura de documentos</p>
                    </div>
                </div>
                <div class="grid md:grid-cols-2 gap-6">
                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
                        <h3 class="font-semibold text-slate-700 mb-2"><i class="fa-solid fa-check-circle text-blue-500 mr-2"></i>Formato de Trabajos Escolares</h3>
                        <ul class="text-sm text-slate-600 space-y-2 list-disc list-inside">
                            <li><b>Márgenes oficiales:</b> 2.54 cm por cada lado (Estándar APA).</li>
                            <li><b>Tipografía recomendada:</b> Arial 11pt, Calibri 11pt o Times New Roman 12pt.</li>
                            <li><b>Interlineado:</b> 1.5 o 2.0 líneas según la indicación del profesor.</li>
                            <li><b>Alineación:</b> Izquierda con sangría de primera línea en párrafos principales.</li>
                        </ul>
                    </div>
                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
                        <h3 class="font-semibold text-slate-700 mb-2"><i class="fa-solid fa-list-ol text-blue-500 mr-2"></i>Índices Automáticos</h3>
                        <p class="text-sm text-slate-600 leading-relaxed mb-2">
                            Para evitar hacer un índice de forma manual, utiliza los <b>Estilos de Título</b>:
                        </p>
                        <ol class="text-sm text-slate-600 space-y-1 list-decimal list-inside">
                            <li>Selecciona tus temas y aplica el estilo <b>Título 1</b> o <b>Título 2</b> en la pestaña <i>Inicio</i>.</li>
                            <li>Coloca el cursor donde irá tu índice.</li>
                            <li>Ve a la pestaña <b>Referencias</b> &gt; <b>Tabla de contenido</b> &gt; Selecciona <i>Tabla automática</i>.</li>
                        </ol>
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
                        <h2 class="text-xl font-bold text-slate-800">Hojas de Cálculo: Microsoft Excel</h2>
                        <p class="text-sm text-slate-500">Fórmulas básicas, condicionales y simulador dinámico de promedios</p>
                    </div>
                </div>

                <!-- Simulador de Promedios -->
                <div class="bg-slate-50 p-5 rounded-2xl border border-slate-200 mb-6">
                    <h3 class="font-bold text-slate-800 mb-2 flex items-center gap-2">
                        <i class="fa-solid fa-calculator text-emerald-600"></i> Simulador Interactivo de Calificaciones (=PROMEDIO y =SI)
                    </h3>
                    <p class="text-sm text-slate-600 mb-4">Ingresa 3 calificaciones para calcular automáticamente el promedio y determinar la condición académica usando la fórmula <code>=SI(PROMEDIO&gt;=6, "Aprobado", "Reprobado")</code>.</p>
                    
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
                            <span class="text-xs text-slate-500 block">Promedio Final Obtenido:</span>
                            <span id="res-promedio" class="text-2xl font-extrabold text-slate-800">6.67</span>
                        </div>
                        <div>
                            <span class="text-xs text-slate-500 block">Resultado Función =SI:</span>
                            <span id="res-estatus" class="px-3 py-1 rounded-full text-xs font-bold bg-emerald-100 text-emerald-700">APROBADO</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- PESTAÑA: POWERPOINT -->
        <section id="content-powerpoint" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <div class="flex items-center gap-3 mb-4">
                    <div class="bg-orange-100 text-orange-600 p-3 rounded-xl">
                        <i class="fa-solid fa-file-powerpoint text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-800">Presentaciones Digitales: PowerPoint</h2>
                        <p class="text-sm text-slate-500">Reglas de diseño visual, contraste y exposición efectiva</p>
                    </div>
                </div>
                <div class="grid sm:grid-cols-2 gap-4">
                    <div class="p-4 rounded-xl bg-orange-50/50 border border-orange-100">
                        <h3 class="font-bold text-orange-900 mb-1">La Regla del 6x6</h3>
                        <p class="text-sm text-slate-600">Máximo 6 líneas de texto por diapositiva y aproximadamente 6 palabras por línea. Evita saturar con párrafos largos.</p>
                    </div>
                    <div class="p-4 rounded-xl bg-blue-50/50 border border-blue-100">
                        <h3 class="font-bold text-blue-900 mb-1">Regla de Contraste</h3>
                        <p class="text-sm text-slate-600">Usa fondo claro con texto oscuro o fondo oscuro con texto blanco para asegurar visibilidad con proyector.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- PESTAÑA: LIBROS Y GUÍAS -->
        <section id="content-libros" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <div class="flex items-center gap-3 mb-4">
                    <div class="bg-amber-100 text-amber-600 p-3 rounded-xl">
                        <i class="fa-solid fa-book-bookmark text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-800">Guías de Estudio y Libros Recomendados</h2>
                        <p class="text-sm text-slate-500">Recursos de consulta rápida y manuales para preparatoria</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-3 gap-4">
                    <div class="p-4 border border-slate-200 rounded-xl bg-slate-50">
                        <span class="text-xs font-bold text-blue-600 uppercase tracking-wide">Manual Escolar</span>
                        <h3 class="font-bold text-slate-800 my-1">Guía Rápida Formato APA 7</h3>
                        <p class="text-xs text-slate-600 mb-3">Estructura para trabajos, citas textuales y bibliografía formal.</p>
                        <span class="text-xs bg-slate-200 text-slate-700 px-2 py-1 rounded">PDF Consultable</span>
                    </div>
                    <div class="p-4 border border-slate-200 rounded-xl bg-slate-50">
                        <span class="text-xs font-bold text-emerald-600 uppercase tracking-wide">Excel de Cero a Cien</span>
                        <h3 class="font-bold text-slate-800 my-1">Compendio de Fórmulas Prácticas</h3>
                        <p class="text-xs text-slate-600 mb-3">Explicación concisa de =SUMA, =PROMEDIO, =SI, =CONTAR.SI y =BUSCARV.</p>
                        <span class="text-xs bg-slate-200 text-slate-700 px-2 py-1 rounded">Manual Digital</span>
                    </div>
                    <div class="p-4 border border-slate-200 rounded-xl bg-slate-50">
                        <span class="text-xs font-bold text-purple-600 uppercase tracking-wide">Ciberseguridad</span>
                        <h3 class="font-bold text-slate-800 my-1">Ciudadanía Digital Segura</h3>
                        <p class="text-xs text-slate-600 mb-3">Protección de datos personales, autenticación de dos pasos y redes sociales.</p>
                        <span class="text-xs bg-slate-200 text-slate-700 px-2 py-1 rounded">Guía Preventiva</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- PESTAÑA: ATAJOS DE TECLADO -->
        <section id="content-atajos" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <div class="flex items-center justify-between gap-4 mb-4 flex-wrap">
                    <div class="flex items-center gap-3">
                        <div class="bg-purple-100 text-purple-600 p-3 rounded-xl">
                            <i class="fa-solid fa-keyboard text-2xl"></i>
                        </div>
                        <div>
                            <h2 class="text-xl font-bold text-slate-800">Atajos de Teclado Universales</h2>
                            <p class="text-sm text-slate-500">Agiliza tu trabajo en Windows y la suite de Office</p>
                        </div>
                    </div>
                    <input type="text" id="shortcut-search" oninput="filtrarAtajos()" placeholder="Buscar atajo (ej. Copiar, Guardar)..." class="p-2.5 bg-slate-50 border border-slate-300 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-purple-500 w-full sm:w-64">
                </div>

                <div class="overflow-x-auto">
                    <table class="w-full text-left border-collapse">
                        <thead>
                            <tr class="bg-slate-100 text-slate-700 text-xs uppercase font-bold border-b border-slate-200">
                                <th class="p-3 rounded-l-lg">Atajo</th>
                                <th class="p-3">Función</th>
                                <th class="p-3 rounded-r-lg">Programa</th>
                            </tr>
                        </thead>
                        <tbody id="shortcuts-table-body" class="text-sm divide-y divide-slate-100">
                            <!-- Inserción dinámica de atajos -->
                        </tbody>
                    </table>
                </div>
            </div>
        </section>

        <!-- PESTAÑA: DESAFÍO DE ATAJOS (MINIJUÉGO) -->
        <section id="content-juego" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm max-w-2xl mx-auto">
                <div class="text-center mb-6">
                    <div class="inline-flex bg-pink-100 text-pink-600 p-4 rounded-2xl mb-2">
                        <i class="fa-solid fa-gamepad text-3xl"></i>
                    </div>
                    <h2 class="text-2xl font-bold text-slate-800">Desafío de Velocidad: Atajos</h2>
                    <p class="text-sm text-slate-500">Responde correctamente antes de que el tiempo se agote</p>
                </div>

                <div id="game-card" class="bg-slate-50 p-6 rounded-2xl border border-slate-200 transition-all">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-xs font-bold text-slate-500" id="game-progress">Pregunta 1 de 5</span>
                        <span class="text-xs font-bold bg-amber-100 text-amber-800 px-3 py-1 rounded-full" id="game-timer"><i class="fa-regular fa-clock mr-1"></i>10s</span>
                    </div>

                    <h3 class="text-lg font-bold text-slate-800 mb-4" id="game-question">¿Cuál es el atajo para copiar texto seleccionado?</h3>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 mb-4" id="game-options">
                        <!-- Opciones de juego dinámicas -->
                    </div>

                    <div id="game-feedback" class="min-h-[2.5rem] flex items-center justify-center text-sm font-bold text-center"></div>
                </div>

                <div class="mt-4 text-center">
                    <button onclick="iniciarMinijuego()" class="px-5 py-2.5 bg-slate-800 hover:bg-slate-900 text-white font-medium text-sm rounded-xl shadow-sm transition-all">
                        <i class="fa-solid fa-rotate-right mr-2"></i>Reiniciar Juego
                    </button>
                </div>
            </div>
        </section>

        <!-- PESTAÑA: QUIZ EVALUATIVO -->
        <section id="content-quiz" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm max-w-3xl mx-auto">
                <div class="flex items-center gap-3 mb-6">
                    <div class="bg-cyan-100 text-cyan-600 p-3 rounded-xl">
                        <i class="fa-solid fa-graduation-cap text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-800">Examen Diagnóstico de Computación</h2>
                        <p class="text-sm text-slate-500">Ponte a prueba con 10 preguntas fundamentales de opción múltiple</p>
                    </div>
                </div>

                <form id="quiz-form" onsubmit="evaluarQuiz(event)" class="space-y-6">
                    <div id="quiz-container" class="space-y-6">
                        <!-- Preguntas cargadas dinámicamente -->
                    </div>

                    <div class="pt-4 border-t border-slate-200 flex flex-wrap items-center justify-between gap-4">
                        <button type="submit" class="w-full sm:w-auto px-6 py-3 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded-xl shadow-sm transition-all">
                            Enviar y Calificar Examen
                        </button>
                        <div id="quiz-result" class="text-base font-bold text-slate-800"></div>
                    </div>
                </form>
            </div>
        </section>

        <!-- PESTAÑA: ASISTENTE IA AUTÓNOMO -->
        <section id="content-ia" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <div class="flex items-center justify-between gap-4 mb-4 pb-4 border-b border-slate-100 flex-wrap">
                    <div class="flex items-center gap-3">
                        <div class="bg-indigo-600 text-white p-3 rounded-xl shadow-sm">
                            <i class="fa-solid fa-robot text-2xl"></i>
                        </div>
                        <div>
                            <h2 class="text-xl font-bold text-slate-800">Tutor e Inteligencia Artificial Educativa</h2>
                            <p class="text-sm text-slate-500">Responde cualquier duda sobre Informática, Programación, Word, Excel, Redes y Tecnología sin límites</p>
                        </div>
                    </div>
                    <span class="text-xs bg-emerald-50 text-emerald-700 font-bold px-3 py-1.5 rounded-full border border-emerald-200 flex items-center gap-1">
                        <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
                        Gemini 3 Flash Activo
                    </span>
                </div>

                <!-- Sugerencias de consulta rápida -->
                <div class="mb-4">
                    <p class="text-xs font-semibold text-slate-500 mb-2">Ejemplos de preguntas avanzadas:</p>
                    <div class="flex flex-wrap gap-2">
                        <button onclick="usarSugerencia('Explícame con ejemplos la diferencia entre RAM, ROM y Disco Duro')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            💾 RAM vs ROM vs Disco Duro
                        </button>
                        <button onclick="usarSugerencia('Dame un ejemplo completo paso a paso de la función =BUSCARV en Excel con una tabla ficticia')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            📊 Función =BUSCARV en Excel
                        </button>
                        <button onclick="usarSugerencia('¿Qué es un algoritmo y cómo se representa en un diagrama de flujo con un ejemplo?')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            📐 Algoritmos y Diagramas
                        </button>
                        <button onclick="usarSugerencia('Escribe un programa sencillo en Python que pida dos números y muestre su suma')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            🐍 Código en Python
                        </button>
                        <button onclick="usarSugerencia('Explícame de manera sencilla cómo funciona la ciberseguridad y Phishing')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            🛡️ Phishing y Seguridad
                        </button>
                    </div>
                </div>

                <!-- Ventana del Chat -->
                <div id="ai-chat-history" class="h-96 overflow-y-auto bg-slate-50 border border-slate-200 rounded-2xl p-4 space-y-4 mb-4">
                    <div class="flex gap-3 items-start">
                        <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold">
                            <i class="fa-solid fa-graduation-cap text-xs"></i>
                        </div>
                        <div class="bg-white border border-slate-200 rounded-2xl p-3 shadow-sm max-w-[85%] text-slate-700 leading-relaxed text-sm">
                            ¡Hola! Ahora cuento con el modelo <b>Gemini 3 Flash</b> integrado. Puedes hacerme cualquier pregunta abierta sobre informática, pedirme explicaciones detalladas, ejemplos prácticos, fórmulas avanzadas de Excel o código de programación.
                        </div>
                    </div>
                </div>

                <!-- Campo de Entrada -->
                <form onsubmit="enviarPreguntaIA(event)" class="flex gap-2">
                    <input type="text" id="ai-input" placeholder="Pregunta lo que quieras sin límites (ej. Explícame cómo funciona una red Wi-Fi)..." class="flex-grow p-3 bg-slate-50 border border-slate-300 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500">
                    <button type="submit" id="ai-send-btn" class="px-5 py-3 bg-indigo-600 hover:bg-indigo-700 text-white font-bold rounded-xl shadow-sm transition-all flex items-center gap-2 text-sm shrink-0">
                        <span>Preguntar</span>
                        <i class="fa-solid fa-paper-plane"></i>
                    </button>
                </form>
            </div>
        </section>

        <!-- PESTAÑA: CÓDIGO QR -->
        <section id="content-qr" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm text-center max-w-lg mx-auto">
                <div class="inline-flex bg-rose-100 text-rose-600 p-4 rounded-2xl mb-3">
                    <i class="fa-solid fa-qrcode text-3xl"></i>
                </div>
                <h2 class="text-xl font-bold text-slate-800 mb-1">Código QR del Sitio Web</h2>
                <p class="text-sm text-slate-500 mb-6">Escanea este código con la cámara de tu teléfono móvil para acceder directamente a la plataforma.</p>

                <div class="bg-slate-50 p-6 rounded-2xl border border-slate-200 inline-block mb-4">
                    <div id="qrcode-container" class="flex justify-center items-center min-h-[200px]"></div>
                </div>

                <p id="qr-url-text" class="text-xs font-mono text-slate-500 break-all bg-slate-100 p-2 rounded-lg"></p>
            </div>
        </section>

    </main>

    <!-- Pie de página -->
    <footer class="bg-slate-900 text-slate-400 py-6 border-t border-slate-800 text-center text-xs">
        <div class="max-w-7xl mx-auto px-4">
            <p class="font-medium">CompuPrep 181 - Material Educativo para Bachillerato General</p>
            <p class="mt-1 text-slate-500">Diseñado para aprendizaje autónomo de informática y herramientas digitales.</p>
        </div>
    </footer>

    <!-- LÓGICA EN JAVASCRIPT -->
    <script>
        // 1. Navegación por Pestañas
        function changeTab(tabName) {
            document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(content => {
                content.classList.add('hidden');
                content.classList.remove('block');
            });

            const selectedBtn = document.getElementById(`tab-${tabName}`);
            const selectedContent = document.getElementById(`content-${tabName}`);

            if (selectedBtn && selectedContent) {
                selectedBtn.classList.add('active');
                selectedContent.classList.remove('hidden');
                selectedContent.classList.add('block');
            }

            if (tabName === 'qr') {
                generarCodigoQR();
            }
        }

        // 2. Generador Dinámico de Código QR
        let qrInstancia = null;
        function generarCodigoQR() {
            const container = document.getElementById('qrcode-container');
            const urlText = document.getElementById('qr-url-text');
            const targetURL = window.location.href.includes('github.io') 
                ? window.location.href 
                : 'https://danigomezruiz1205-web.github.io/aprendecompuc181/';

            if (urlText) urlText.textContent = targetURL;

            if (container) {
                container.innerHTML = '';
                qrInstancia = new QRCode(container, {
                    text: targetURL,
                    width: 200,
                    height: 200,
                    colorDark: "#0f172a",
                    colorLight: "#ffffff",
                    correctLevel: QRCode.CorrectLevel.H
                });
            }
        }

        // 3. Simulador de Excel
        function calcularPromedio() {
            const p1 = parseFloat(document.getElementById('calif1').value) || 0;
            const p2 = parseFloat(document.getElementById('calif2').value) || 0;
            const p3 = parseFloat(document.getElementById('calif3').value) || 0;

            const promedio = (p1 + p2 + p3) / 3;
            document.getElementById('res-promedio').textContent = promedio.toFixed(2);

            const estatus = document.getElementById('res-estatus');
            if (promedio >= 6.0) {
                estatus.textContent = "APROBADO";
                estatus.className = "px-3 py-1 rounded-full text-xs font-bold bg-emerald-100 text-emerald-700";
            } else {
                estatus.textContent = "REPROBADO";
                estatus.className = "px-3 py-1 rounded-full text-xs font-bold bg-rose-100 text-rose-700";
            }
        }

        // 4. Atajos de Teclado con Búsqueda
        const listaAtajos = [
            { tecla: 'Ctrl + C', funcion: 'Copiar el texto o elemento seleccionado', programa: 'Universal' },
            { tecla: 'Ctrl + V', funcion: 'Pegar el contenido del portapapeles', programa: 'Universal' },
            { tecla: 'Ctrl + X', funcion: 'Cortar el elemento seleccionado', programa: 'Universal' },
            { tecla: 'Ctrl + Z', funcion: 'Deshacer la última acción realizada', programa: 'Universal' },
            { tecla: 'Ctrl + G / Ctrl + S', funcion: 'Guardar el archivo o documento actual', programa: 'Word / Excel / PPT' },
            { tecla: 'Ctrl + E', funcion: 'Seleccionar todo el texto o contenido', programa: 'Word / Windows' },
            { tecla: 'Ctrl + J', funcion: 'Justificar alineación de párrafo', programa: 'Microsoft Word' },
            { tecla: 'Ctrl + N', funcion: 'Aplicar formato de Negrita', programa: 'Word / Excel' },
            { tecla: 'Ctrl + K', funcion: 'Aplicar formato de Cursiva', programa: 'Word / Excel' },
            { tecla: 'F5', funcion: 'Iniciar la presentación desde el principio', programa: 'PowerPoint' },
            { tecla: 'Alt + Tab', funcion: 'Cambiar rápidamente entre aplicaciones abiertas', programa: 'Windows' },
            { tecla: 'Tecla Windows + D', funcion: 'Mostrar o ocultar el escritorio inmediatamente', programa: 'Windows' }
        ];

        function renderizarAtajos(items) {
            const tbody = document.getElementById('shortcuts-table-body');
            if (!tbody) return;
            tbody.innerHTML = '';

            items.forEach(item => {
                const tr = document.createElement('tr');
                tr.className = 'hover:bg-slate-50/80 transition-colors';
                tr.innerHTML = `
                    <td class="p-3"><kbd class="px-2 py-1 bg-slate-200 border border-slate-300 rounded text-xs font-mono font-semibold text-slate-800">${item.tecla}</kbd></td>
                    <td class="p-3 text-slate-700">${item.funcion}</td>
                    <td class="p-3"><span class="text-xs bg-slate-100 text-slate-600 px-2 py-1 rounded font-medium">${item.programa}</span></td>
                `;
                tbody.appendChild(tr);
            });
        }

        function filtrarAtajos() {
            const query = document.getElementById('shortcut-search').value.toLowerCase();
            const filtrados = listaAtajos.filter(a => 
                a.tecla.toLowerCase().includes(query) || 
                a.funcion.toLowerCase().includes(query) || 
                a.programa.toLowerCase().includes(query)
            );
            renderizarAtajos(filtrados);
        }

        // 5. Minijuego de Atajos con Detección de Errores
        const preguntasJuego = [
            { q: '¿Qué atajo de teclado te permite deshacer una equivocación?', opts: ['Ctrl + Z', 'Ctrl + Y', 'Ctrl + X', 'Ctrl + D'], correct: 0 },
            { q: '¿Qué tecla presionas para iniciar una presentación en PowerPoint?', opts: ['F1', 'F5', 'F11', 'Ctrl + P'], correct: 1 },
            { q: '¿Cuál es el atajo para guardar un archivo en Office en español?', opts: ['Ctrl + G', 'Ctrl + S', 'Ctrl + P', 'Ctrl + A'], correct: 0 },
            { q: '¿Cómo seleccionas todo el contenido de un documento en Word?', opts: ['Ctrl + A', 'Ctrl + E', 'Ctrl + T', 'Ctrl + S'], correct: 1 },
            { q: '¿Cuál es la combinación para cortar un texto seleccionado?', opts: ['Ctrl + C', 'Ctrl + V', 'Ctrl + X', 'Ctrl + Z'], correct: 2 }
        ];

        let indexJuego = 0;
        let timerJuego = null;
        let tiempoRestante = 10;
        let juegoBloqueado = false;

        function iniciarMinijuego() {
            indexJuego = 0;
            juegoBloqueado = false;
            cargarPreguntaJuego();
        }

        function cargarPreguntaJuego() {
            clearInterval(timerJuego);
            juegoBloqueado = false;
            tiempoRestante = 10;

            if (indexJuego >= preguntasJuego.length) {
                document.getElementById('game-card').innerHTML = `
                    <div class="text-center py-6">
                        <i class="fa-solid fa-trophy text-4xl text-amber-500 mb-2"></i>
                        <h3 class="text-xl font-bold text-slate-800">¡Desafío Completado!</h3>
                        <p class="text-sm text-slate-600 my-2">Has dominado los atajos esenciales de computación.</p>
                        <button onclick="iniciarMinijuego()" class="mt-4 px-5 py-2.5 bg-blue-600 text-white font-bold text-sm rounded-xl hover:bg-blue-700">Jugar de Nuevo</button>
                    </div>
                `;
                return;
            }

            const p = preguntasJuego[indexJuego];
            document.getElementById('game-progress').textContent = `Pregunta ${indexJuego + 1} de ${preguntasJuego.length}`;
            document.getElementById('game-question').textContent = p.q;
            document.getElementById('game-timer').innerHTML = `<i class="fa-regular fa-clock mr-1"></i>${tiempoRestante}s`;
            document.getElementById('game-feedback').textContent = '';

            const optsContainer = document.getElementById('game-options');
            optsContainer.innerHTML = '';

            p.opts.forEach((opt, idx) => {
                const btn = document.createElement('button');
                btn.className = 'opt-btn p-3 bg-white border border-slate-300 rounded-xl text-sm font-semibold text-slate-700 hover:border-blue-500 hover:bg-blue-50/50 transition-all text-left';
                btn.textContent = opt;
                btn.onclick = () => responderJuego(idx, btn);
                optsContainer.appendChild(btn);
            });

            timerJuego = setInterval(() => {
                tiempoRestante--;
                document.getElementById('game-timer').innerHTML = `<i class="fa-regular fa-clock mr-1"></i>${tiempoRestante}s`;
                if (tiempoRestante <= 0) {
                    clearInterval(timerJuego);
                    manejarTiempoAgotado();
                }
            }, 1000);
        }

        function responderJuego(indexSeleccionado, btnElement) {
            if (juegoBloqueado) return;
            juegoBloqueado = true;
            clearInterval(timerJuego);

            const p = preguntasJuego[indexJuego];
            const feedback = document.getElementById('game-feedback');
            const gameCard = document.getElementById('game-card');

            if (indexSeleccionado === p.correct) {
                btnElement.classList.remove('bg-white', 'border-slate-300');
                btnElement.classList.add('bg-emerald-500', 'text-white', 'border-emerald-600');
                feedback.innerHTML = `<span class="text-emerald-600"><i class="fa-solid fa-circle-check mr-1"></i>¡Correcto! Excelente reflejo.</span>`;
            } else {
                gameCard.classList.add('animate-shake');
                btnElement.classList.remove('bg-white', 'border-slate-300');
                btnElement.classList.add('bg-rose-500', 'text-white', 'border-rose-600');

                const btns = document.querySelectorAll('.opt-btn');
                if (btns[p.correct]) {
                    btns[p.correct].classList.remove('bg-white', 'border-slate-300');
                    btns[p.correct].classList.add('bg-emerald-100', 'text-emerald-800', 'border-emerald-400');
                }

                feedback.innerHTML = `<span class="text-rose-600"><i class="fa-solid fa-circle-xmark mr-1"></i>Incorrecto. La respuesta correcta era: <b>${p.opts[p.correct]}</b></span>`;

                setTimeout(() => gameCard.classList.remove('animate-shake'), 400);
            }

            setTimeout(() => {
                indexJuego++;
                cargarPreguntaJuego();
            }, 1600);
        }

        function manejarTiempoAgotado() {
            if (juegoBloqueado) return;
            juegoBloqueado = true;

            const p = preguntasJuego[indexJuego];
            const feedback = document.getElementById('game-feedback');
            const btns = document.querySelectorAll('.opt-btn');

            if (btns[p.correct]) {
                btns[p.correct].classList.add('bg-emerald-100', 'text-emerald-800', 'border-emerald-400');
            }

            feedback.innerHTML = `<span class="text-rose-600"><i class="fa-solid fa-hourglass-end mr-1"></i>¡Tiempo agotado! La opción correcta era: <b>${p.opts[p.correct]}</b></span>`;

            setTimeout(() => {
                indexJuego++;
                cargarPreguntaJuego();
            }, 1600);
        }

        // 6. Quiz Evaluativo Estructurado
        const quizPreguntas = [
            { q: '1. ¿Cuál es el formato estándar recomendado para márgenes en un trabajo con formato APA?', opts: ['1 cm por lado', '2.54 cm por lado', '3.5 cm superior e inferior', 'Sin márgenes'], correct: 1 },
            { q: '2. En Microsoft Excel, ¿cuál es el símbolo obligatorio para iniciar cualquier fórmula?', opts: ['#', '=', '$', '&'], correct: 1 },
            { q: '3. ¿Qué establece la Regla del 6x6 en PowerPoint?', opts: ['6 diapositivas por minuto', 'Máximo 6 líneas por diapositiva y 6 palabras por línea', 'Usar solo 6 colores', 'Presentar en 6 minutos'], correct: 1 },
            { q: '4. ¿Qué atajo de teclado permite deshacer una acción en Windows?', opts: ['Ctrl + X', 'Ctrl + C', 'Ctrl + Z', 'Ctrl + V'], correct: 2 },
            { q: '5. ¿Cuál es la función principal del Procesador de Textos?', opts: ['Calcular presupuestos', 'Crear y editar documentos de texto', 'Diseñar bases de datos', 'Editar video'], correct: 1 },
            { q: '6. ¿Qué función de Excel evalúa una condición lógica y entrega un resultado verdadero o falso?', opts: ['=SUMA', '=PROMEDIO', '=SI', '=MAX'], correct: 2 },
            { q: '7. Para actualizar automáticamente la tabla de contenido en Word debemos usar:', opts: ['Estilos de Título (Título 1, Título 2)', 'Negrita manual', 'Subrayado simple', 'Cambio de fuente'], correct: 0 },
            { q: '8. ¿Cuál es una buena práctica de seguridad digital en contraseñas?', opts: ['Usar "123456"', 'Compartirla con amigos', 'Combinar letras, números y símbolos', 'Usar tu fecha de nacimiento'], correct: 2 },
            { q: '9. ¿Qué tecla se utiliza para iniciar una presentación a pantalla completa en PowerPoint?', opts: ['F1', 'F5', 'Esc', 'Enter'], correct: 1 },
            { q: '10. ¿Qué servicio permite almacenar archivos en Internet de forma remota?', opts: ['Procesador local', 'Almacenamiento en la Nube', 'Disco flexible', 'Memoria ROM'], correct: 1 }
        ];

        function cargarQuiz() {
            const container = document.getElementById('quiz-container');
            if (!container) return;
            container.innerHTML = '';

            quizPreguntas.forEach((item, qIndex) => {
                const qDiv = document.createElement('div');
                qDiv.className = 'p-4 bg-slate-50 border border-slate-200 rounded-xl';
                
                let optsHTML = '';
                item.opts.forEach((opt, oIndex) => {
                    optsHTML += `
                        <label class="flex items-center gap-2 p-2 rounded-lg hover:bg-white border border-transparent hover:border-slate-200 cursor-pointer text-sm text-slate-700">
                            <input type="radio" name="quiz-q-${qIndex}" value="${oIndex}" class="text-blue-600 focus:ring-blue-500">
                            <span>${opt}</span>
                        </label>
                    `;
                });

                qDiv.innerHTML = `
                    <p class="font-semibold text-slate-800 text-sm mb-3">${item.q}</p>
                    <div class="space-y-1">${optsHTML}</div>
                `;
                container.appendChild(qDiv);
            });
        }

        function evaluarQuiz(e) {
            e.preventDefault();
            let aciertos = 0;

            quizPreguntas.forEach((item, qIndex) => {
                const selected = document.querySelector(`input[name="quiz-q-${qIndex}"]:checked`);
                if (selected && parseInt(selected.value) === item.correct) {
                    aciertos++;
                }
            });

            const calificacion = ((aciertos / quizPreguntas.length) * 10).toFixed(1);
            const resDiv = document.getElementById('quiz-result');

            if (calificacion >= 6.0) {
                resDiv.innerHTML = `<span class="text-emerald-600"><i class="fa-solid fa-circle-check mr-1"></i>Puntaje: ${calificacion} / 10 (${aciertos} aciertos) - ¡Aprobado!</span>`;
            } else {
                resDiv.innerHTML = `<span class="text-rose-600"><i class="fa-solid fa-circle-xmark mr-1"></i>Puntaje: ${calificacion} / 10 (${aciertos} aciertos) - Repasa los temas e intenta de nuevo.</span>`;
            }
        }

        // 7. Base de Conocimiento Local Integrada (Soporte Offline Completo de IA)
        const baseConocimiento = [
            {
                claves: ['indice', 'índice', 'tabla de contenido', 'word'],
                respuesta: "<b>Crear un índice automático en Microsoft Word:</b><br>1. Selecciona los títulos de tu documento.<br>2. En la pestaña <b>Inicio</b>, asigna <i>Título 1</i> para temas principales y <i>Título 2</i> para subtemas.<br>3. Ve a la pestaña <b>Referencias</b> &gt; <b>Tabla de contenido</b> &gt; elige un estilo automático.<br>4. Si modificas el documento, haz clic secundario sobre la tabla y presiona <i>'Actualizar campo'</i>."
            },
            {
                claves: ['si', '=si', 'funcion si', 'función si', 'condicional', 'excel'],
                respuesta: "<b>La función =SI en Microsoft Excel:</b><br>Evalúa si una condición se cumple (VERDADERO) o no (FALSO).<br><br><b>Sintaxis oficial:</b><br><code>=SI(prueba_logica, valor_si_verdadero, valor_si_falso)</code><br><br><b>Ejemplo escolar:</b><br><code>=SI(A1&gt;=6, \"Aprobado\", \"Reprobado\")</code><br>Devuelve 'Aprobado' si la nota es igual o mayor a 6."
            },
            {
                claves: ['6x6', 'regla 6x6', 'powerpoint', 'diapositiva', 'presentacion'],
                respuesta: "<b>La Regla del 6x6 en PowerPoint:</b><br>Es una guía para evitar diapositivas sobrecargadas:<br>• Usar máximo <b>6 líneas de texto</b> por diapositiva.<br>• Usar un promedio de <b>6 palabras por línea</b>.<br><i>Tip:</i> La diapositiva debe ser una guía visual complementaria, no un guion para leer completo."
            },
            {
                claves: ['ip', 'direccion ip', 'redes', 'internet'],
                respuesta: "<b>Dirección IP (Internet Protocol):</b><br>Es la etiqueta numérica única que identifica a un dispositivo (computadora, teléfono, impresora) conectado a una red local o a Internet. Permite el envío y recepción de paquetes de datos entre equipos."
            },
            {
                claves: ['binario', 'sistema binario', 'bits', 'byte'],
                respuesta: "<b>Sistema Binario en Informática:</b><br>Es el sistema de numeración base 2 utilizado por las computadoras digitalmente. Solo emplea los dígitos <b>0</b> (apagado/sin voltaje) y <b>1</b> (encendido/con voltaje).<br>• 1 Bit = La unidad mínima (0 o 1).<br>• 1 Byte = 8 Bits de información."
            },
            {
                claves: ['ram', 'memoria ram', 'hardware'],
                respuesta: "<b>Memoria RAM (Random Access Memory):</b><br>Es la memoria de acceso aleatorio y almacenamiento temporal de la computadora. Guarda las instrucciones y programas ejecutados en el instante. Al apagar el equipo, su contenido se borra completamente (memoria volátil)."
            },
            {
                claves: ['cpu', 'procesador'],
                respuesta: "<b>CPU (Unidad Central de Procesamiento):</b><br>Conocido como el 'cerebro' de la computadora. Se encarga de interpretar instrucciones, ejecutar el sistema operativo y procesar todos los cálculos matemáticos y lógicos de los programas."
            }
        ];

        function usarSugerencia(texto) {
            document.getElementById('ai-input').value = texto;
            enviarPreguntaIA(new Event('submit'));
        }

        // 7. Integración con API de IA Inteligente (Gemini API + Respaldo Local)
        async function enviarPreguntaIA(event) {
            event.preventDefault();
            const inputElem = document.getElementById('ai-input');
            const userText = inputElem.value.trim();
            if (!userText) return;

            const chatHistory = document.getElementById('ai-chat-history');
            const sendBtn = document.getElementById('ai-send-btn');

            const userMsgHTML = `
                <div class="flex gap-3 items-start justify-end">
                    <div class="bg-indigo-600 text-white rounded-2xl p-3 shadow-sm max-w-[85%] text-sm leading-relaxed">
                        ${escapeHTML(userText)}
                    </div>
                    <div class="w-8 h-8 rounded-lg bg-slate-800 text-white flex items-center justify-center shrink-0 font-bold text-xs">
                        <i class="fa-solid fa-user"></i>
                    </div>
                </div>
            `;
            chatHistory.insertAdjacentHTML('beforeend', userMsgHTML);
            inputElem.value = '';
            chatHistory.scrollTop = chatHistory.scrollHeight;

            // Indicador de carga
            const loadingId = 'ai-loading-' + Date.now();
            const loadingHTML = `
                <div id="${loadingId}" class="flex gap-3 items-start">
                    <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold text-xs">
                        <i class="fa-solid fa-graduation-cap"></i>
                    </div>
                    <div class="bg-white border border-slate-200 rounded-2xl p-3 shadow-sm text-slate-500 text-sm flex items-center gap-2">
                        <i class="fa-solid fa-circle-notch animate-spin text-indigo-600"></i>
                        <span>Generando respuesta detallada...</span>
                    </div>
                </div>
            `;
            chatHistory.insertAdjacentHTML('beforeend', loadingHTML);
            chatHistory.scrollTop = chatHistory.scrollHeight;

            sendBtn.disabled = true;

            try {
                // Llamada directa a Gemini 3 Flash API
                const apiKey = ""; // Runtime inyectado automáticamente
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;

                const systemPrompt = "Eres un profesor interactivo y amable de Computación Básica e Informática para estudiantes de preparatoria/bachillerato. Tu trabajo es dar explicaciones claras, pedagógicas, con ejemplos sencillos y estructuradas con formato HTML (usa <b>, <i>, <code>, <pre>, listas <ul> o <ol>) para facilitar la lectura.";

                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({
                        contents: [{ parts: [{ text: userText }] }],
                        systemInstruction: { parts: [{ text: systemPrompt }] }
                    })
                });

                const data = await response.json();
                let respuesta = data?.candidates?.[0]?.content?.parts?.[0]?.text;

                if (respuesta) {
                    // Formatear respuestas de markdown a html básico para mejor presentación
                    respuesta = respuesta
                        .replace(/```([\s\S]*?)```/g, '<pre class="bg-slate-900 text-emerald-400 p-3 rounded-xl my-2 text-xs font-mono overflow-x-auto">$1</pre>')
                        .replace(/`([^`]+)`/g, '<code class="bg-slate-100 text-pink-600 px-1.5 py-0.5 rounded text-xs font-mono">$1</code>')
                        .replace(/\*\*(.*?)\*\*/g, '<b>$1</b>')
                        .replace(/\n\n/g, '<br><br>')
                        .replace(/\n/g, '<br>');
                } else {
                    respuesta = obtenerRespuestaLocal(userText);
                }

                renderizarRespuestaIA(loadingId, respuesta);

            } catch (err) {
                // Si la red falla o está offline, usa la base de conocimiento local estructurada
                const respuestaLocal = obtenerRespuestaLocal(userText);
                renderizarRespuestaIA(loadingId, respuestaLocal);
            } finally {
                sendBtn.disabled = false;
                chatHistory.scrollTop = chatHistory.scrollHeight;
            }
        }

        function renderizarRespuestaIA(loadingId, respuestaText) {
            const loadingElem = document.getElementById(loadingId);
            if (loadingElem) {
                loadingElem.outerHTML = `
                    <div class="flex gap-3 items-start">
                        <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold text-xs">
                            <i class="fa-solid fa-graduation-cap"></i>
                        </div>
                        <div class="bg-white border border-slate-200 rounded-2xl p-3 shadow-sm max-w-[85%] text-slate-700 leading-relaxed text-sm">
                            ${respuestaText}
                        </div>
                    </div>
                `;
            }
        }

        function obtenerRespuestaLocal(userText) {
            const textLower = userText.toLowerCase();
            for (const item of baseConocimiento) {
                if (item.claves.some(k => textLower.includes(k))) {
                    return item.respuesta;
                }
            }
            return `Entendido tu consulta sobre <b>"${escapeHTML(userText)}"</b>.<br><br><b>Resumen temático general:</b><br>• <b>Word:</b> Formato APA, márgenes 2.54cm, estilos de título e índices.<br>• <b>Excel:</b> Funciones =SUMA, =PROMEDIO, =SI, =BUSCARV.<br>• <b>PowerPoint:</b> Regla 6x6 y contraste visual.<br>• <b>Ciberseguridad:</b> Contraseñas seguras y prevención de fraude.`;
        }

        function escapeHTML(str) {
            return str.replace(/[&<>'"]/g, 
                tag => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', "'": '&#39;', '"': '&quot;' }[tag] || tag)
            );
        }

        // Inicializaciones al cargar la página
        window.onload = function() {
            calcularPromedio();
            renderizarAtajos(listaAtajos);
            iniciarMinijuego();
            cargarQuiz();
        };
    </script>
</body>
</html>
