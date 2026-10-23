[656.html](https://github.com/user-attachments/files/33849530/656.html)
<!DOCTYPE html>
<html lang="es-MX" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aprende Computación Básica - Preparatoria 181</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome para Iconos -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- QRCode.js para generación de QR en tiempo real -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <!-- Tipografía Inter & Plus Jakarta Sans -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,400;0,500;0,600;0,700;0,800;1,400&family=Outfit:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        body { 
            font-family: 'Plus Jakarta Sans', sans-serif; 
            background-color: #f8fafc;
            color: #0f172a;
        }
        h1, h2, h3, .font-heading {
            font-family: 'Outfit', sans-serif;
        }
        .tab-content { display: none; }
        .tab-content.active { display: block; }

        /* Animaciones artesanales para interacciones fluidas */
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            20%, 60% { transform: translateX(-6px); }
            40%, 80% { transform: translateX(6px); }
        }
        .animate-shake { animation: shake 0.35s cubic-bezier(.36,.07,.19,.97); }

        .btn-correct {
            background-color: #10b981 !important;
            color: #ffffff !important;
            border-color: #059669 !important;
        }
        .btn-wrong {
            background-color: #ef4444 !important;
            color: #ffffff !important;
            border-color: #dc2626 !important;
        }

        /* Ocultar barra de desplazamiento sin perder funcionalidad */
        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col selection:bg-indigo-500 selection:text-white">

    <!-- Encabezado con estética limpia y humana -->
    <header class="bg-white/80 backdrop-blur-md border-b border-slate-200/80 sticky top-0 z-50 transition-all">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-3 flex items-center justify-between gap-4">
            <div class="flex items-center space-x-3 cursor-pointer group" onclick="switchTab('inicio')">
                <div class="w-10 h-10 bg-gradient-to-tr from-indigo-600 to-violet-500 rounded-2xl flex items-center justify-center text-white shadow-md shadow-indigo-200 group-hover:scale-105 transition duration-200">
                    <i class="fa-solid fa-laptop-code text-base"></i>
                </div>
                <div>
                    <div class="flex items-center gap-2">
                        <h1 class="text-base font-bold text-slate-900 leading-tight">Computación I</h1>
                        <span class="px-2 py-0.5 text-[10px] font-bold uppercase tracking-wider bg-indigo-50 text-indigo-600 rounded-full border border-indigo-100">Prep. 181</span>
                    </div>
                    <p class="text-xs text-slate-500">Material de consulta rápida y ejercicios</p>
                </div>
            </div>

            <!-- Acciones directas -->
            <div class="flex items-center space-x-2">
                <button onclick="toggleQRModal()" class="inline-flex items-center space-x-2 bg-slate-100 hover:bg-slate-200/80 text-slate-700 text-xs font-semibold px-3.5 py-2 rounded-xl transition border border-slate-200/70">
                    <i class="fa-solid fa-mobile-screen-button text-slate-500"></i>
                    <span class="hidden sm:inline">Ver en celular</span>
                </button>
            </div>
        </div>

        <!-- Menú de Navegación Tipo Tabs Orgánico -->
        <nav class="bg-slate-50/60 border-t border-slate-200/60 overflow-x-auto no-scrollbar">
            <div class="max-w-7xl mx-auto px-3 flex space-x-1 min-w-max py-1.5 text-xs font-medium text-slate-600">
                <button onclick="switchTab('inicio')" id="nav-inicio" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2 active shadow-sm bg-white text-slate-900">
                    <i class="fa-solid fa-compass text-indigo-500"></i> Inicio
                </button>
                <button onclick="switchTab('word')" id="nav-word" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2">
                    <i class="fa-solid fa-file-word text-blue-600"></i> Word
                </button>
                <button onclick="switchTab('excel')" id="nav-excel" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2">
                    <i class="fa-solid fa-file-excel text-emerald-600"></i> Excel
                </button>
                <button onclick="switchTab('powerpoint')" id="nav-powerpoint" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2">
                    <i class="fa-solid fa-file-powerpoint text-orange-600"></i> PowerPoint
                </button>
                <button onclick="switchTab('seguridad')" id="nav-seguridad" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2">
                    <i class="fa-solid fa-cloud-lock text-sky-600"></i> Nube y Redes
                </button>
                <button onclick="switchTab('libros')" id="nav-libros" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2">
                    <i class="fa-solid fa-bookmark text-amber-600"></i> Guías
                </button>
                <button onclick="switchTab('atajos')" id="nav-atajos" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2">
                    <i class="fa-solid fa-keyboard text-slate-500"></i> Atajos
                </button>
                <button onclick="switchTab('juego')" id="nav-juego" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2">
                    <i class="fa-solid fa-gamepad text-purple-600"></i> Minijuego
                </button>
                <button onclick="switchTab('ia-chat')" id="nav-ia-chat" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2 font-semibold text-indigo-700 bg-indigo-50/70 border border-indigo-100">
                    <i class="fa-solid fa-sparkles text-indigo-600"></i> Asistente Escolar
                </button>
                <button onclick="switchTab('quiz')" id="nav-quiz" class="tab-btn px-3.5 py-2 rounded-xl hover:bg-white hover:text-slate-900 transition flex items-center gap-2">
                    <i class="fa-solid fa-circle-check text-teal-600"></i> Repaso
                </button>
            </div>
        </nav>
    </header>

    <!-- ÁREA DE CONTENIDO PRINCIPAL -->
    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 flex-grow w-full">

        <!-- 1. PESTAÑA: INICIO -->
        <section id="tab-inicio" class="tab-content active space-y-8">
            <!-- Hero Banner con diseño editorial -->
            <div class="bg-gradient-to-br from-slate-900 via-indigo-950 to-slate-900 rounded-3xl p-6 sm:p-10 text-white relative overflow-hidden shadow-xl">
                <div class="absolute -right-10 -bottom-10 w-72 h-72 bg-indigo-500/10 rounded-full blur-3xl pointer-events-none"></div>
                
                <div class="max-w-2xl space-y-4 relative z-10">
                    <span class="inline-flex items-center gap-2 px-3 py-1 rounded-full text-xs font-semibold bg-indigo-500/20 text-indigo-300 border border-indigo-400/20 backdrop-blur-sm">
                        <i class="fa-solid fa-graduation-cap"></i> Preparatoria 181 • Semestre Actual
                    </span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold tracking-tight leading-tight">
                        Aprende computación de forma clara, práctica y sin rodeos.
                    </h2>
                    <p class="text-slate-300 text-sm sm:text-base leading-relaxed">
                        Un espacio diseñado por y para estudiantes. Encuentra trucos rápidos, ejemplos listos para aplicar en tus proyectos y herramientas para entregar mejores trabajos en clase.
                    </p>
                    <div class="flex flex-wrap gap-3 pt-3">
                        <button onclick="switchTab('word')" class="bg-indigo-600 hover:bg-indigo-500 text-white text-xs sm:text-sm font-semibold px-5 py-3 rounded-2xl transition shadow-lg shadow-indigo-600/30 flex items-center gap-2">
                            <span>Explorar Guías de Word</span>
                            <i class="fa-solid fa-arrow-right text-xs"></i>
                        </button>
                        <button onclick="switchTab('juego')" class="bg-white/10 hover:bg-white/20 text-white text-xs sm:text-sm font-semibold px-5 py-3 rounded-2xl transition border border-white/10 backdrop-blur-sm flex items-center gap-2">
                            <i class="fa-solid fa-gamepad text-purple-400"></i>
                            <span>Practicar Atajos</span>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Accesos Rápidos por Módulo -->
            <div>
                <h3 class="text-xs font-bold uppercase tracking-wider text-slate-400 mb-4 px-1">Módulos principales de estudio</h3>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-5">
                    <div onclick="switchTab('word')" class="bg-white p-6 rounded-2xl border border-slate-200/80 hover:border-blue-300 hover:shadow-xl hover:shadow-blue-500/5 transition duration-200 cursor-pointer space-y-3 group">
                        <div class="w-12 h-12 rounded-2xl bg-blue-50 text-blue-600 flex items-center justify-center font-bold group-hover:bg-blue-600 group-hover:text-white transition duration-200 shadow-sm">
                            <i class="fa-solid fa-file-word text-xl"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-slate-900 group-hover:text-blue-600 transition">Word Profesional</h3>
                            <p class="text-xs text-slate-500 leading-relaxed mt-1">Formato APA, índices automáticos, saltos de sección y márgenes correctos.</p>
                        </div>
                    </div>

                    <div onclick="switchTab('excel')" class="bg-white p-6 rounded-2xl border border-slate-200/80 hover:border-emerald-300 hover:shadow-xl hover:shadow-emerald-500/5 transition duration-200 cursor-pointer space-y-3 group">
                        <div class="w-12 h-12 rounded-2xl bg-emerald-50 text-emerald-600 flex items-center justify-center font-bold group-hover:bg-emerald-600 group-hover:text-white transition duration-200 shadow-sm">
                            <i class="fa-solid fa-file-excel text-xl"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-slate-900 group-hover:text-emerald-600 transition">Excel Práctico</h3>
                            <p class="text-xs text-slate-500 leading-relaxed mt-1">Suma, promedios, función =SI y simulador dinámico de calificaciones.</p>
                        </div>
                    </div>

                    <div onclick="switchTab('powerpoint')" class="bg-white p-6 rounded-2xl border border-slate-200/80 hover:border-orange-300 hover:shadow-xl hover:shadow-orange-500/5 transition duration-200 cursor-pointer space-y-3 group">
                        <div class="w-12 h-12 rounded-2xl bg-orange-50 text-orange-600 flex items-center justify-center font-bold group-hover:bg-orange-600 group-hover:text-white transition duration-200 shadow-sm">
                            <i class="fa-solid fa-file-powerpoint text-xl"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-slate-900 group-hover:text-orange-600 transition">PowerPoint Limpio</h3>
                            <p class="text-xs text-slate-500 leading-relaxed mt-1">La regla 6x6, paletas de color con buen contraste e impacto en clase.</p>
                        </div>
                    </div>

                    <div onclick="switchTab('seguridad')" class="bg-white p-6 rounded-2xl border border-slate-200/80 hover:border-sky-300 hover:shadow-xl hover:shadow-sky-500/5 transition duration-200 cursor-pointer space-y-3 group">
                        <div class="w-12 h-12 rounded-2xl bg-sky-50 text-sky-600 flex items-center justify-center font-bold group-hover:bg-sky-600 group-hover:text-white transition duration-200 shadow-sm">
                            <i class="fa-solid fa-shield-halved text-xl"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-slate-900 group-hover:text-sky-600 transition">Nube y Seguridad</h3>
                            <p class="text-xs text-slate-500 leading-relaxed mt-1">Búsquedas avanzadas en Google, organización en Drive y prevención de fraudes.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 4. PESTAÑA: POWERPOINT -->
        <section id="tab-powerpoint" class="tab-content space-y-6">
            <div class="bg-white border border-slate-200 rounded-2xl p-6 shadow-sm space-y-6">
                <div class="flex items-center gap-3 border-b border-slate-100 pb-4">
                    <div class="w-10 h-10 rounded-xl bg-orange-100 text-orange-700 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-file-powerpoint"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-900">Microsoft PowerPoint: Exposición y Diapositivas</h2>
                        <p class="text-xs text-slate-500">Reglas clave para crear presentaciones claras que no aburran al grupo.</p>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-5">
                    <div class="border border-slate-200 rounded-xl p-4 bg-orange-50/30 space-y-2">
                        <h3 class="font-bold text-slate-800 text-sm flex items-center gap-2">
                            <i class="fa-solid fa-check text-orange-600"></i> Regla del 6x6
                        </h3>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            Procura no colocar más de <strong>6 líneas de texto</strong> por diapositiva y un máximo aproximado de <strong>6 palabras por línea</strong>. Las diapositivas son un apoyo visual para el expositor, no fichas para leer todo el tema.
                        </p>
                    </div>

                    <div class="border border-slate-200 rounded-xl p-4 bg-orange-50/30 space-y-2">
                        <h3 class="font-bold text-slate-800 text-sm flex items-center gap-2">
                            <i class="fa-solid fa-palette text-orange-600"></i> Contraste y Tipografía
                        </h3>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            Utiliza fondos claros con letras oscuras (o fondo muy oscuro con letras blancas). Evita combinar colores chillantes como texto amarillo sobre fondo blanco. El tamaño de letra sugerido para títulos es de 32 pt y cuerpo de 20 pt.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 5. PESTAÑA: SEGURIDAD E INTERNET -->
        <section id="tab-seguridad" class="tab-content space-y-6">
            <div class="bg-white border border-slate-200 rounded-2xl p-6 shadow-sm space-y-6">
                <div class="flex items-center gap-3 border-b border-slate-100 pb-4">
                    <div class="w-10 h-10 rounded-xl bg-indigo-100 text-indigo-700 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-shield-halved"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-900">Búsquedas Confiables y Seguridad en la Nube</h2>
                        <p class="text-xs text-slate-500">Criterios para evaluar la información web y organizar tus archivos digitales.</p>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                    <div class="border border-slate-200 rounded-xl p-4 bg-slate-50 space-y-2">
                        <h3 class="font-bold text-slate-800 text-sm flex items-center gap-2">
                            <i class="fa-solid fa-magnifying-glass text-indigo-600"></i> Filtros en Google
                        </h3>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            Utiliza comillas <code>"texto exacto"</code> para buscar una frase precisa, o el comando <code>filetype:pdf</code> al final de tu búsqueda para encontrar documentos académicos en PDF.
                        </p>
                    </div>

                    <div class="border border-slate-200 rounded-xl p-4 bg-slate-50 space-y-2">
                        <h3 class="font-bold text-slate-800 text-sm flex items-center gap-2">
                            <i class="fa-solid fa-cloud text-indigo-600"></i> Nube Escolar
                        </h3>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            Guarda tus tareas en Google Drive o OneDrive organizadas por carpetas de cada materia. Evita tener todos los archivos sueltos en el escritorio de la computadora.
                        </p>
                    </div>

                    <div class="border border-slate-200 rounded-xl p-4 bg-slate-50 space-y-2">
                        <h3 class="font-bold text-slate-800 text-sm flex items-center gap-2">
                            <i class="fa-solid fa-lock text-indigo-600"></i> Cuidado con Correos Sospechosos
                        </h3>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            Si recibes un correo pidiendo contraseñas o ofreciendo regalos extraños, revisa el remitente. Las instituciones escolares nunca te pedirán tu clave secreta por mensaje.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 6. PESTAÑA: LIBROS Y GUÍAS -->
        <section id="tab-libros" class="tab-content space-y-6">
            <div class="bg-white border border-slate-200 rounded-2xl p-6 shadow-sm space-y-6">
                <div class="flex items-center gap-3 border-b border-slate-100 pb-4">
                    <div class="w-10 h-10 rounded-xl bg-amber-100 text-amber-700 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-book-bookmark"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-900">Guías de Estudio y Libros Recomendados</h2>
                        <p class="text-xs text-slate-500">Material de referencia y documentos para profundizar en la materia.</p>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-5">
                    <div class="border border-slate-200 rounded-xl p-4 bg-slate-50 flex items-start gap-3">
                        <div class="text-amber-600 text-2xl pt-1"><i class="fa-solid fa-file-pdf"></i></div>
                        <div>
                            <h3 class="font-bold text-slate-800 text-sm">Guía Básica de Informática para Bachillerato</h3>
                            <p class="text-xs text-slate-500 mt-1">Sintesis con los conceptos teóricos del programa escolar: hardware, software, sistemas operativos y redes.</p>
                            <span class="inline-block mt-2 text-xs font-semibold text-blue-700">Consulta en Biblioteca Escolar</span>
                        </div>
                    </div>

                    <div class="border border-slate-200 rounded-xl p-4 bg-slate-50 flex items-start gap-3">
                        <div class="text-amber-600 text-2xl pt-1"><i class="fa-solid fa-book"></i></div>
                        <div>
                            <h3 class="font-bold text-slate-800 text-sm">Manual de Usuario de la Suite de Oficina</h3>
                            <p class="text-xs text-slate-500 mt-1">Manual de referencia con todas las herramientas de la barra de cinta de Word y Excel explicadas con ejemplos.</p>
                            <span class="inline-block mt-2 text-xs font-semibold text-blue-700">Material de Apoyo Digital</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 7. PESTAÑA: ATAJOS DE TECLADO -->
        <section id="tab-atajos" class="tab-content space-y-6">
            <div class="bg-white border border-slate-200 rounded-2xl p-6 shadow-sm space-y-6">
                <div class="flex items-center justify-between border-b border-slate-100 pb-4 flex-wrap gap-3">
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 rounded-xl bg-slate-100 text-slate-700 flex items-center justify-center text-xl font-bold">
                            <i class="fa-solid fa-keyboard"></i>
                        </div>
                        <div>
                            <h2 class="text-xl font-bold text-slate-900">Buscador de Atajos de Teclado</h2>
                            <p class="text-xs text-slate-500">Gana agilidad al trabajar en la computadora utilizando el teclado.</p>
                        </div>
                    </div>

                    <!-- Buscador -->
                    <div class="w-full sm:w-64">
                        <input type="text" id="shortcut-search" onkeyup="filtrarAtajos()" placeholder="Buscar atajo (ej. Copiar, Guardar)..." class="w-full border border-slate-300 rounded-xl px-3 py-2 text-xs focus:ring-2 focus:ring-blue-500 outline-none">
                    </div>
                </div>

                <!-- Tabla de Atajos -->
                <div class="overflow-x-auto">
                    <table class="w-full text-left text-xs border-collapse">
                        <thead>
                            <tr class="bg-slate-100 text-slate-700 uppercase font-semibold">
                                <th class="p-3 rounded-l-lg">Atajo</th>
                                <th class="p-3">Acción</th>
                                <th class="p-3 rounded-r-lg">Programa</th>
                            </tr>
                        </thead>
                        <tbody id="shortcut-tbody" class="divide-y divide-slate-100 text-slate-600">
                            <tr><td class="p-3 font-mono font-bold text-slate-900">Ctrl + C</td><td class="p-3">Copiar texto o elemento seleccionado</td><td class="p-3"><span class="bg-slate-100 px-2 py-0.5 rounded text-slate-600">General</span></td></tr>
                            <tr><td class="p-3 font-mono font-bold text-slate-900">Ctrl + V</td><td class="p-3">Pegar contenido del portapapeles</td><td class="p-3"><span class="bg-slate-100 px-2 py-0.5 rounded text-slate-600">General</span></td></tr>
                            <tr><td class="p-3 font-mono font-bold text-slate-900">Ctrl + X</td><td class="p-3">Cortar elemento seleccionado</td><td class="p-3"><span class="bg-slate-100 px-2 py-0.5 rounded text-slate-600">General</span></td></tr>
                            <tr><td class="p-3 font-mono font-bold text-slate-900">Ctrl + Z</td><td class="p-3">Deshacer última acción realizada</td><td class="p-3"><span class="bg-slate-100 px-2 py-0.5 rounded text-slate-600">General</span></td></tr>
                            <tr><td class="p-3 font-mono font-bold text-slate-900">Ctrl + G</td><td class="p-3">Guardar el documento actual</td><td class="p-3"><span class="bg-blue-50 text-blue-700 px-2 py-0.5 rounded font-semibold">Word / Excel</span></td></tr>
                            <tr><td class="p-3 font-mono font-bold text-slate-900">Ctrl + J</td><td class="p-3">Justificar el texto formateado</td><td class="p-3"><span class="bg-blue-50 text-blue-700 px-2 py-0.5 rounded font-semibold">Word</span></td></tr>
                            <tr><td class="p-3 font-mono font-bold text-slate-900">F5</td><td class="p-3">Iniciar presentación con diapositivas desde el principio</td><td class="p-3"><span class="bg-orange-50 text-orange-700 px-2 py-0.5 rounded font-semibold">PowerPoint</span></td></tr>
                            <tr><td class="p-3 font-mono font-bold text-slate-900">Ctrl + T</td><td class="p-3">Abrir una nueva pestaña en el navegador web</td><td class="p-3"><span class="bg-indigo-50 text-indigo-700 px-2 py-0.5 rounded font-semibold">Navegadores</span></td></tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </section>

        <!-- 8. PESTAÑA: MINIJUEGO INTERACTIVO -->
        <section id="tab-juego" class="tab-content space-y-6">
            <div class="bg-white border border-slate-200 rounded-2xl p-6 shadow-sm space-y-6">
                <div class="flex items-center justify-between border-b border-slate-100 pb-4 flex-wrap gap-3">
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 rounded-xl bg-purple-100 text-purple-700 flex items-center justify-center text-xl font-bold">
                            <i class="fa-solid fa-gamepad"></i>
                        </div>
                        <div>
                            <h2 class="text-xl font-bold text-slate-900">Desafío de Atajos: "Atrapa la Tecla"</h2>
                            <p class="text-xs text-slate-500">Demuestra tu velocidad seleccionando la combinación correcta de teclas.</p>
                        </div>
                    </div>

                    <div class="flex items-center gap-4 text-xs font-bold">
                        <div class="bg-slate-100 px-3 py-1.5 rounded-lg border border-slate-200">
                            Puntuación: <span id="game-score" class="text-purple-700 font-extrabold">0</span> pts
                        </div>
                        <div class="bg-slate-100 px-3 py-1.5 rounded-lg border border-slate-200">
                            Tiempo: <span id="game-timer" class="text-red-600 font-extrabold">10</span>s
                        </div>
                    </div>
                </div>

                <!-- Área de Juego -->
                <div id="game-container" class="border-2 border-dashed border-slate-200 rounded-2xl p-6 text-center space-y-6 bg-slate-50 transition-all">
                    <!-- Pantalla Inicial -->
                    <div id="game-start-screen" class="space-y-4 py-6">
                        <div class="w-16 h-16 bg-purple-100 text-purple-700 rounded-full flex items-center justify-center mx-auto text-2xl">
                            <i class="fa-solid fa-bolt"></i>
                        </div>
                        <h3 class="text-lg font-bold text-slate-900">¿Qué tan rápido identificas los atajos de teclado?</h3>
                        <p class="text-xs text-slate-500 max-w-md mx-auto">Tendrás 10 segundos por pregunta. Si eliges mal, la caja temblará y te mostrará en rojo tu error y en verde la opción correcta.</p>
                        <button onclick="iniciarJuego()" class="bg-purple-700 hover:bg-purple-800 text-white font-bold text-xs px-6 py-3 rounded-xl transition shadow-md">
                            ¡Comenzar Desafío!
                        </button>
                    </div>

                    <!-- Pantalla de Pregunta -->
                    <div id="game-play-screen" class="hidden space-y-5">
                        <span id="game-question-num" class="text-xs font-bold uppercase tracking-wider text-purple-700 bg-purple-50 px-2.5 py-1 rounded-full">Pregunta 1 de 5</span>
                        <h3 id="game-target-action" class="text-lg sm:text-xl font-extrabold text-slate-900">¿Cuál es el atajo para copiar texto?</h3>
                        
                        <!-- Retroalimentación de Error/Acierto -->
                        <div id="game-feedback" class="hidden text-xs font-bold py-2 px-3 rounded-lg max-w-md mx-auto transition"></div>

                        <!-- Opciones de Respuesta -->
                        <div id="game-options" class="grid grid-cols-1 sm:grid-cols-2 gap-3 max-w-lg mx-auto">
                            <!-- Se generan con JS -->
                        </div>
                    </div>

                    <!-- Pantalla Fin de Juego -->
                    <div id="game-end-screen" class="hidden space-y-4 py-6">
                        <div class="w-16 h-16 bg-emerald-100 text-emerald-700 rounded-full flex items-center justify-center mx-auto text-2xl">
                            <i class="fa-solid fa-trophy"></i>
                        </div>
                        <h3 class="text-lg font-bold text-slate-900">¡Reto Completado!</h3>
                        <p class="text-xs text-slate-600">Puntuación total obtenida: <span id="final-game-score" class="font-bold text-purple-700 text-sm">0</span> puntos.</p>
                        <button onclick="iniciarJuego()" class="bg-purple-700 hover:bg-purple-800 text-white font-bold text-xs px-6 py-3 rounded-xl transition shadow-md">
                            Volver a Intentar
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- 8.5. PESTAÑA: ASISTENTE DE IA (PREGUNTAS) -->
        <section id="tab-ia-chat" class="tab-content space-y-6">
            <div class="bg-white border border-slate-200 rounded-2xl p-6 shadow-sm space-y-6">
                <div class="flex items-center gap-3 border-b border-slate-100 pb-4">
                    <div class="w-10 h-10 rounded-xl bg-indigo-100 text-indigo-700 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-sparkles"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-900">Tutor Escolar de Computación</h2>
                        <p class="text-xs text-slate-500">Haz una pregunta sobre tus tareas o temas del temario.</p>
                    </div>
                </div>

                <!-- Sugerencias de Preguntas -->
                <div class="space-y-2">
                    <p class="text-xs font-semibold text-slate-500">Preguntas comunes:</p>
                    <div class="flex flex-wrap gap-2 text-xs">
                        <button onclick="usarSugerencia('¿Cómo hago un índice automático en Word?')" class="bg-slate-100 hover:bg-slate-200 text-slate-700 px-3 py-1.5 rounded-lg border border-slate-200 transition">
                            ¿Cómo hago un índice en Word?
                        </button>
                        <button onclick="usarSugerencia('¿Cómo funciona la función =SI en Excel? Explica con un ejemplo fácil.')" class="bg-slate-100 hover:bg-slate-200 text-slate-700 px-3 py-1.5 rounded-lg border border-slate-200 transition">
                            ¿Cómo funciona la función =SI en Excel?
                        </button>
                        <button onclick="usarSugerencia('¿Qué es la regla 6x6 en PowerPoint?')" class="bg-slate-100 hover:bg-slate-200 text-slate-700 px-3 py-1.5 rounded-lg border border-slate-200 transition">
                            ¿Qué es la regla 6x6 en PPT?
                        </button>
                        <button onclick="usarSugerencia('¿Cuáles son los atajos más importantes para trabajar rápido en la computadora?')" class="bg-slate-100 hover:bg-slate-200 text-slate-700 px-3 py-1.5 rounded-lg border border-slate-200 transition">
                            Atajos clave de teclado
                        </button>
                    </div>
                </div>

                <!-- Caja del Chat -->
                <div class="border border-slate-200 rounded-xl bg-slate-50 overflow-hidden flex flex-col h-[400px]">
                    <!-- Contenedor de Mensajes -->
                    <div id="ai-chat-history" class="flex-grow p-4 overflow-y-auto space-y-4 text-xs">
                        <!-- Mensaje de bienvenida del bot -->
                        <div class="flex gap-3 items-start">
                            <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold shadow-sm">
                                <i class="fa-solid fa-graduation-cap text-xs"></i>
                            </div>
                            <div class="bg-white border border-slate-200/80 rounded-2xl p-3.5 shadow-sm max-w-[85%] text-slate-700 leading-relaxed">
                                ¡Hola! 👋 Soy el asistente de Computación I de la prepa.<br><br>¿Tienes dudas con alguna fórmula de Excel, formato de Word o cómo estructurar una presentación? Escribe tu duda y te ayudo paso a paso.
                            </div>
                        </div>
                    </div>

                    <!-- Input y Botón de Envío -->
                    <form onsubmit="enviarPreguntaIA(event)" class="p-3 bg-white border-t border-slate-200 flex gap-2 items-center">
                        <input type="text" id="ai-input" placeholder="Escribe tu duda sobre computación básica aquí..." class="flex-grow border border-slate-300 rounded-xl px-3 py-2 text-xs focus:ring-2 focus:ring-indigo-500 outline-none" required>
                        <button type="submit" id="ai-send-btn" class="bg-indigo-600 hover:bg-indigo-700 text-white px-4 py-2 rounded-xl text-xs font-semibold transition flex items-center gap-1.5 shrink-0 shadow-sm">
                            <span>Preguntar</span>
                            <i class="fa-solid fa-paper-plane text-[10px]"></i>
                        </button>
                    </form>
                </div>
            </div>
        </section>

        <!-- 9. PESTAÑA: QUIZ DE EVALUACIÓN -->
        <section id="tab-quiz" class="tab-content space-y-6">
            <div class="bg-white border border-slate-200 rounded-2xl p-6 shadow-sm space-y-6">
                <div class="flex items-center gap-3 border-b border-slate-100 pb-4">
                    <div class="w-10 h-10 rounded-xl bg-teal-100 text-teal-700 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-check-double"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-900">Cuestionario de Autoevaluación</h2>
                        <p class="text-xs text-slate-500">Pone a prueba tus conocimientos antes de los exámenes parciales.</p>
                    </div>
                </div>

                <div id="quiz-container" class="space-y-6">
                    <!-- Preguntas estructuradas -->
                    <div class="space-y-4">
                        <!-- Pregunta 1 -->
                        <div class="p-4 border border-slate-200 rounded-xl bg-slate-50 space-y-2">
                            <p class="font-bold text-xs text-slate-800">1. ¿Qué combinación de teclas se utiliza para justificar un párrafo en Microsoft Word?</p>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2 text-xs">
                                <button onclick="evaluarQuiz(this, false)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">a) Ctrl + E</button>
                                <button onclick="evaluarQuiz(this, true)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">b) Ctrl + J</button>
                                <button onclick="evaluarQuiz(this, false)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">c) Ctrl + N</button>
                                <button onclick="evaluarQuiz(this, false)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">d) Alt + F4</button>
                            </div>
                        </div>

                        <!-- Pregunta 2 -->
                        <div class="p-4 border border-slate-200 rounded-xl bg-slate-50 space-y-2">
                            <p class="font-bold text-xs text-slate-800">2. En Excel, ¿qué signo debe escribirse obligatoriamente al inicio de toda fórmula o función?</p>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2 text-xs">
                                <button onclick="evaluarQuiz(this, false)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">a) El signo de gato (#)</button>
                                <button onclick="evaluarQuiz(this, true)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">b) El signo de igual (=)</button>
                                <button onclick="evaluarQuiz(this, false)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">c) El signo de dinero ($)</button>
                                <button onclick="evaluarQuiz(this, false)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">d) El signo de suma (+)</button>
                            </div>
                        </div>

                        <!-- Pregunta 3 -->
                        <div class="p-4 border border-slate-200 rounded-xl bg-slate-50 space-y-2">
                            <p class="font-bold text-xs text-slate-800">3. ¿En qué consiste la regla del 6x6 para diseñar presentaciones en PowerPoint?</p>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2 text-xs">
                                <button onclick="evaluarQuiz(this, false)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">a) Usar máximo 6 diapositivas de 6 colores distintos</button>
                                <button onclick="evaluarQuiz(this, true)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">b) Máximo 6 líneas por diapositiva y aprox. 6 palabras por línea</button>
                                <button onclick="evaluarQuiz(this, false)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">c) Exponer en un tiempo exacto de 6 minutos con 6 segundos</button>
                                <button onclick="evaluarQuiz(this, false)" class="p-2 bg-white border rounded-lg text-left hover:bg-slate-100">d) Insertar 6 imágenes por cada 6 párrafos impresos</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- PIE DE PÁGINA -->
    <footer class="bg-slate-900 text-slate-400 text-xs py-8 border-t border-slate-800 mt-auto">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row items-center justify-between gap-4">
            <div>
                <p class="font-bold text-slate-200">Materia de Computación I • Preparatoria No. 181</p>
                <p class="text-slate-500 mt-0.5">Recursos de estudio para el ciclo escolar 2026.</p>
            </div>
            <div class="flex items-center space-x-4">
                <button onclick="switchTab('inicio')" class="hover:text-white transition">Inicio</button>
                <button onclick="toggleQRModal()" class="hover:text-white transition">Generar QR Escolar</button>
            </div>
        </div>
    </footer>

    <!-- MODAL DE CÓDIGO QR -->
    <div id="qr-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-2xl max-w-sm w-full p-6 text-center space-y-4 shadow-2xl relative">
            <button onclick="toggleQRModal()" class="absolute top-3 right-3 text-slate-400 hover:text-slate-600 w-8 h-8 rounded-full bg-slate-100 flex items-center justify-center text-sm">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <div class="w-12 h-12 bg-blue-100 text-blue-700 rounded-xl flex items-center justify-center mx-auto text-xl">
                <i class="fa-solid fa-qrcode"></i>
            </div>
            <h3 class="text-base font-bold text-slate-900">Escanea para abrir en celular</h3>
            <p class="text-xs text-slate-500">Apunta con la cámara de tu teléfono móvil para acceder directamente a la página web sin escribir el enlace.</p>
            
            <!-- Contenedor del QR generado dinámicamente -->
            <div id="qrcode-target" class="flex justify-center p-3 bg-white border border-slate-200 rounded-xl"></div>

            <p class="text-[11px] font-mono text-slate-400 break-all">https://danigomezruiz1205-web.github.io/aprendecompuc181/</p>
        </div>
    </div>

    <!-- SCRIPT PRINCIPAL DE LÓGICA E INTERACCIÓN -->
    <script>
        // 1. Cambio de pestañas
        function switchTab(tabId) {
            // Ocultar todas las secciones
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(content => content.classList.remove('active'));

            // Quitar clase activa a los botones del menú
            const buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => {
                btn.classList.remove('bg-white', 'text-slate-900', 'shadow-sm');
            });

            // Mostrar la pestaña seleccionada
            const targetContent = document.getElementById('tab-' + tabId);
            if (targetContent) {
                targetContent.classList.add('active');
            }

            // Activar botón del menú
            const targetBtn = document.getElementById('nav-' + tabId);
            if (targetBtn) {
                targetBtn.classList.add('bg-white', 'text-slate-900', 'shadow-sm');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // 2. Simulador numérico de Excel
        function calcularSimuladorExcel() {
            const p1 = parseFloat(document.getElementById('calc-p1').value) || 0;
            const p2 = parseFloat(document.getElementById('calc-p2').value) || 0;
            const p3 = parseFloat(document.getElementById('calc-p3').value) || 0;

            const promedio = ((p1 + p2 + p3) / 3).toFixed(1);
            document.getElementById('res-promedio').innerText = promedio;

            const estatusElem = document.getElementById('res-estatus');
            if (promedio >= 6.0) {
                estatusElem.innerText = "Aprobado";
                estatusElem.className = "px-2 py-0.5 rounded text-xs font-bold bg-emerald-900 text-emerald-300";
            } else {
                estatusElem.innerText = "Reprobado";
                estatusElem.className = "px-2 py-0.5 rounded text-xs font-bold bg-red-900 text-red-300";
            }
        }

        // 3. Filtrar atajos de teclado
        function filtrarAtajos() {
            const query = document.getElementById('shortcut-search').value.toLowerCase();
            const rows = document.querySelectorAll('#shortcut-tbody tr');

            rows.forEach(row => {
                const text = row.innerText.toLowerCase();
                if (text.includes(query)) {
                    row.style.display = '';
                } else {
                    row.style.display = 'none';
                }
            });
        }

        // 4. Modal y Generador Dinámico de Código QR
        let qrGenerated = false;
        function toggleQRModal() {
            const modal = document.getElementById('qr-modal');
            modal.classList.toggle('hidden');

            if (!qrGenerated && !modal.classList.contains('hidden')) {
                const url = "https://danigomezruiz1205-web.github.io/aprendecompuc181/";
                new QRCode(document.getElementById("qrcode-target"), {
                    text: url,
                    width: 160,
                    height: 160,
                    colorDark : "#0f172a",
                    colorLight : "#ffffff",
                    correctLevel : QRCode.CorrectLevel.H
                });
                qrGenerated = true;
            }
        }

        // 5. Minijuego con detección visual de errores
        const preguntasJuego = [
            { accion: "Copiar texto o elemento", correcta: "Ctrl + C", opciones: ["Ctrl + C", "Ctrl + V", "Ctrl + X", "Ctrl + Z"] },
            { accion: "Pegar contenido del portapapeles", correcta: "Ctrl + V", opciones: ["Ctrl + C", "Ctrl + V", "Ctrl + P", "Ctrl + G"] },
            { accion: "Deshacer la última acción", correcta: "Ctrl + Z", opciones: ["Ctrl + Y", "Ctrl + Z", "Ctrl + D", "Alt + F4"] },
            { accion: "Guardar documento actual", correcta: "Ctrl + G", opciones: ["Ctrl + S", "Ctrl + G", "Ctrl + A", "Ctrl + P"] },
            { accion: "Justificar texto en Word", correcta: "Ctrl + J", opciones: ["Ctrl + T", "Ctrl + E", "Ctrl + J", "Ctrl + D"] }
        ];

        let juegoIndice = 0;
        let juegoPuntos = 0;
        let juegoTimer = null;
        let tiempoRestante = 10;

        function iniciarJuego() {
            juegoIndice = 0;
            juegoPuntos = 0;
            document.getElementById('game-score').innerText = "0";
            document.getElementById('game-start-screen').classList.add('hidden');
            document.getElementById('game-end-screen').classList.add('hidden');
            document.getElementById('game-play-screen').classList.remove('hidden');
            mostrarPreguntaJuego();
        }

        function mostrarPreguntaJuego() {
            if (juegoIndice >= preguntasJuego.length) {
                finalizarJuego();
                return;
            }

            const q = preguntasJuego[juegoIndice];
            document.getElementById('game-question-num').innerText = `Pregunta ${juegoIndice + 1} de ${preguntasJuego.length}`;
            document.getElementById('game-target-action').innerText = `¿Cuál es el atajo para: "${q.accion}"?`;

            // Resetear retroalimentación
            const feedback = document.getElementById('game-feedback');
            feedback.classList.add('hidden');
            feedback.className = "hidden text-xs font-bold py-2 px-3 rounded-lg max-w-md mx-auto transition";

            // Opciones
            const container = document.getElementById('game-options');
            container.innerHTML = '';

            q.opciones.forEach(opt => {
                const btn = document.createElement('button');
                btn.className = "p-3 bg-white border border-slate-200 rounded-xl font-mono text-sm font-bold text-slate-800 hover:border-purple-300 hover:bg-purple-50/50 transition outline-none";
                btn.innerText = opt;
                btn.onclick = () => verificarRespuestaJuego(opt, q.correcta, btn);
                container.appendChild(btn);
            });

            // Reiniciar Reloj
            clearInterval(juegoTimer);
            tiempoRestante = 10;
            document.getElementById('game-timer').innerText = tiempoRestante;

            juegoTimer = setInterval(() => {
                tiempoRestante--;
                document.getElementById('game-timer').innerText = tiempoRestante;
                if (tiempoRestante <= 0) {
                    clearInterval(juegoTimer);
                    marcarErrorTiempo(q.correcta);
                }
            }, 1000);
        }

        function verificarRespuestaJuego(seleccion, correcta, botonPresionado) {
            clearInterval(juegoTimer);
            const container = document.getElementById('game-container');
            const feedback = document.getElementById('game-feedback');
            const botones = document.querySelectorAll('#game-options button');

            // Deshabilitar botones para evitar múltiples clics
            botones.forEach(b => b.disabled = true);

            if (seleccion === correcta) {
                botonPresionado.classList.add('btn-correct');
                juegoPuntos += 20;
                document.getElementById('game-score').innerText = juegoPuntos;
                
                feedback.innerText = "¡Correcto! +20 Puntos";
                feedback.classList.remove('hidden');
                feedback.classList.add('bg-emerald-100', 'text-emerald-800');

                setTimeout(() => {
                    juegoIndice++;
                    mostrarPreguntaJuego();
                }, 1200);
            } else {
                // EFECTO DE ERROR VISUAL
                botonPresionado.classList.add('btn-wrong');
                container.classList.add('animate-shake');

                // Resaltar la opción correcta
                botones.forEach(b => {
                    if (b.innerText === correcta) {
                        b.classList.add('btn-correct');
                    }
                });

                feedback.innerText = `¡Incorrecto! La combinación correcta era: ${correcta}`;
                feedback.classList.remove('hidden');
                feedback.classList.add('bg-red-100', 'text-red-800');

                setTimeout(() => {
                    container.classList.remove('animate-shake');
                    juegoIndice++;
                    mostrarPreguntaJuego();
                }, 1800);
            }
        }

        function marcarErrorTiempo(correcta) {
            const container = document.getElementById('game-container');
            const feedback = document.getElementById('game-feedback');
            const botones = document.querySelectorAll('#game-options button');

            botones.forEach(b => {
                b.disabled = true;
                if (b.innerText === correcta) {
                    b.classList.add('btn-correct');
                }
            });

            container.classList.add('animate-shake');
            feedback.innerText = `¡Se agotó el tiempo! La opción correcta era: ${correcta}`;
            feedback.classList.remove('hidden');
            feedback.classList.add('bg-red-100', 'text-red-800');

            setTimeout(() => {
                container.classList.remove('animate-shake');
                juegoIndice++;
                mostrarPreguntaJuego();
            }, 1800);
        }

        function finalizarJuego() {
            document.getElementById('game-play-screen').classList.add('hidden');
            document.getElementById('game-end-screen').classList.remove('hidden');
            document.getElementById('final-game-score').innerText = juegoPuntos;
        }

        // 6. Evaluación sencilla para el Cuestionario
        function evaluarQuiz(button, esCorrecta) {
            const parent = button.parentElement;
            const buttons = parent.querySelectorAll('button');

            buttons.forEach(b => {
                b.disabled = true;
                b.classList.remove('hover:bg-slate-100');
            });

            if (esCorrecta) {
                button.classList.add('btn-correct');
            } else {
                button.classList.add('btn-wrong');
            }
        }

        // 7. Integración con la API de IA (Gemini)
        function usarSugerencia(texto) {
            document.getElementById('ai-input').value = texto;
            enviarPreguntaIA(new Event('submit'));
        }

        async function enviarPreguntaIA(event) {
            event.preventDefault();
            const inputElem = document.getElementById('ai-input');
            const userText = inputElem.value.trim();
            if (!userText) return;

            const chatHistory = document.getElementById('ai-chat-history');
            const sendBtn = document.getElementById('ai-send-btn');

            // 1. Mostrar mensaje del usuario
            const userMsgHTML = `
                <div class="flex gap-3 items-start justify-end">
                    <div class="bg-blue-600 text-white rounded-2xl p-3 shadow-sm max-w-[85%] leading-relaxed">
                        ${escapeHTML(userText)}
                    </div>
                    <div class="w-8 h-8 rounded-lg bg-slate-800 text-white flex items-center justify-center shrink-0 font-bold">
                        <i class="fa-solid fa-user text-xs"></i>
                    </div>
                </div>
            `;
            chatHistory.insertAdjacentHTML('beforeend', userMsgHTML);
            inputElem.value = '';
            chatHistory.scrollTop = chatHistory.scrollHeight;

            // 2. Mostrar indicador de "Pensando..."
            const loadingId = 'loading-' + Date.now();
            const loadingHTML = `
                <div id="${loadingId}" class="flex gap-3 items-start">
                    <div class="w-8 h-8 rounded-lg bg-blue-600 text-white flex items-center justify-center shrink-0 font-bold">
                        <i class="fa-solid fa-robot text-xs animate-spin"></i>
                    </div>
                    <div class="bg-white border border-slate-200 rounded-2xl p-3 shadow-sm text-slate-500 italic">
                        Escribiendo respuesta...
                    </div>
                </div>
            `;
            chatHistory.insertAdjacentHTML('beforeend', loadingHTML);
            chatHistory.scrollTop = chatHistory.scrollHeight;

            // Deshabilitar botón temporalmente
            sendBtn.disabled = true;

            try {
                // Prompt del sistema para limitar las respuestas al ámbito de Computación Básica de Preparatoria
                const systemPrompt = `Eres un profesor/tutor amable y didáctico de la materia 'Computación I' para alumnos de Preparatoria (Bachillerato).
Tu trabajo es responder dudas de manera clara, concisa y con un lenguaje accesible para estudiantes jóvenes.
Tus temas principales son:
1. Procesador de Textos (Microsoft Word): Índices automáticos, formato APA, sangrías, márgenes, interlineado.
2. Hojas de Cálculo (Microsoft Excel): Fórmulas básicas (=SUMA, =PROMEDIO, =SI, =CONTAR), celdas, rangos, gráficos.
3. Presentaciones (Microsoft PowerPoint): Regla 6x6, diseño, contraste, animaciones básicas.
4. Internet, Nube y Seguridad: Búsquedas con comillas y filetype:pdf, Google Drive, OneDrive, prevención de phishing.
5. Atajos de Teclado (Ctrl+C, Ctrl+V, Ctrl+Z, Ctrl+G, etc.).

REGLA STRICTA DE SEGURIDAD:
Si el usuario pregunta algo que NO esté relacionado con informática, computación básica, software de oficina, tecnología o estudio escolar, responde cortésmente diciendo: "Lo siento, como tutor de Computación I solo puedo ayudarte con temas relacionados a informática básica, procesadores de texto, hojas de cálculo, presentaciones, internet y herramientas digitales para tus estudios. ¿Tienes alguna pregunta sobre estos temas?"
Mantén respuestas breves (1 a 3 párrafos cortos) y organizadas.`;

                const apiKey = "";
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;

                const payload = {
                    contents: [{ parts: [{ text: userText }] }],
                    systemInstruction: { parts: [{ text: systemPrompt }] }
                };

                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                const data = await response.json();
                const aiReply = data?.candidates?.[0]?.content?.parts?.[0]?.text || "Lo siento, no pude procesar tu respuesta en este momento. Intenta preguntar de nuevo.";

                // Remover loader
                const loader = document.getElementById(loadingId);
                if (loader) loader.remove();

                // Formatear saltos de línea e incrustar la respuesta de la IA
                const formattedReply = escapeHTML(aiReply).replace(/\n/g, '<br>');

                const aiMsgHTML = `
                    <div class="flex gap-3 items-start">
                        <div class="w-8 h-8 rounded-lg bg-blue-600 text-white flex items-center justify-center shrink-0 font-bold">
                            <i class="fa-solid fa-robot text-xs"></i>
                        </div>
                        <div class="bg-white border border-slate-200 rounded-2xl p-3 shadow-sm max-w-[85%] text-slate-700 leading-relaxed">
                            ${formattedReply}
                        </div>
                    </div>
                `;
                chatHistory.insertAdjacentHTML('beforeend', aiMsgHTML);

            } catch (err) {
                const loader = document.getElementById(loadingId);
                if (loader) loader.remove();

                const errorHTML = `
                    <div class="flex gap-3 items-start">
                        <div class="w-8 h-8 rounded-lg bg-red-600 text-white flex items-center justify-center shrink-0 font-bold">
                            <i class="fa-solid fa-triangle-exclamation text-xs"></i>
                        </div>
                        <div class="bg-red-50 border border-red-200 rounded-2xl p-3 shadow-sm max-w-[85%] text-red-700">
                            Hubo un problema al conectar con el servidor de IA. Por favor verifica tu conexión e inténtalo de nuevo.
                        </div>
                    </div>
                `;
                chatHistory.insertAdjacentHTML('beforeend', errorHTML);
            } finally {
                sendBtn.disabled = false;
                chatHistory.scrollTop = chatHistory.scrollHeight;
            }
        }

        function escapeHTML(str) {
            return str.replace(/[&<>'"]/g, 
                tag => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', "'": '&#39;', '"': '&quot;' }[tag] || tag)
            );
        }
    </script>
</body>
</html>
