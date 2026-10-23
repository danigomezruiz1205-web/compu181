[Uploading 0909.html…]()
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
    <!-- Marked.js para renderizar Markdown completo -->
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
        /* Estilos para respuestas formateadas en el Chat */
        .ai-formatted-content p { margin-bottom: 0.5rem; }
        .ai-formatted-content p:last-child { margin-bottom: 0; }
        .ai-formatted-content ul { list-style-type: disc; padding-left: 1.25rem; margin-bottom: 0.5rem; }
        .ai-formatted-content ol { list-style-type: decimal; padding-left: 1.25rem; margin-bottom: 0.5rem; }
        .ai-formatted-content code { background-color: #f1f5f9; color: #db2777; padding: 0.1rem 0.3rem; rounded: 0.25rem; font-family: monospace; font-size: 0.85em; }
        .ai-formatted-content pre { background-color: #0f172a; color: #38bdf8; padding: 0.75rem; rounded-xl: 0.5rem; border-radius: 0.5rem; overflow-x: auto; margin: 0.5rem 0; font-family: monospace; font-size: 0.85em; }
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
                        Asistente Integro 100% Autónomo (Sin Internet / Sin API)
                    </span>
                    <button onclick="descargarCodigoPagina()" class="py-1 px-3 rounded-xl text-xs font-semibold bg-blue-600 hover:bg-blue-500 text-white transition-all flex items-center gap-1.5 shadow-sm">
                        <i class="fa-solid fa-download"></i> Descargar Web App
                    </button>
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

                <!-- Guía Rápida Visual: Edición de Texto y Fuentes -->
                <div class="grid md:grid-cols-3 gap-4 mb-6">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-font text-blue-600"></i> Cambiar Fuente, Tamaños y Colores
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Seleccionar Texto:</b> Haz clic y arrastra sobre el texto que deseas modificar (o presiona <kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl + E</kbd> para todo el documento).</li>
                            <li><b>Cambiar Fuente y Tamaño:</b> En la pestaña <b>Inicio</b>, usa el menú desplegable de fuentes (ej. <i>Arial</i>, <i>Times New Roman</i>) y el número de tamaño (ej. <i>12pt</i>).</li>
                            <li><b>Color de Fuente:</b> En la pestaña <b>Inicio</b>, busca el icono <b class="text-blue-600 font-bold">A</b> con una barra de color debajo. Haz clic en la flecha pequeña para elegir un color de la paleta.</li>
                            <li><b>Resaltado de Texto:</b> Usa el icono del plumón marca-textos (<b class="bg-amber-200 px-1 rounded">ab</b>) para dar un fondo amarillo, verde o azul a palabras clave.</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-align-left text-blue-600"></i> Alineación, Interlineado y Sangrías
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Alineaciones de Párrafo:</b> En la sección <i>Párrafo</i> de la pestaña <b>Inicio</b>:
                                <ul class="list-disc list-inside ml-2 mt-1 text-slate-500">
                                    <li><b>Izquierda (<kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl + Q</kbd>):</b> Para párrafos estándar.</li>
                                    <li><b>Centrado (<kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl + T</kbd>):</b> Para títulos y portadas.</li>
                                    <li><b>Derecha (<kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl + D</kbd>):</b> Para fechas o firmas.</li>
                                    <li><b>Justificado (<kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl + J</kbd>):</b> Alinea ambos márgenes uniformemente.</li>
                                </ul>
                            </li>
                            <li><b>Espaciado e Interlineado:</b> Haz clic en el icono de flechas subiendo y bajando (<i class="fa-solid fa-text-height text-blue-500"></i>) para cambiar a 1.0, 1.5 o 2.0 (Doble).</li>
                            <li><b>Sangría de Primera Línea:</b> Arrastra el triángulo superior de la regla en la parte alta o presiona <kbd class="px-1 bg-slate-200 rounded font-mono">Tabulador</kbd> al inicio del párrafo (1.27 cm en norma APA).</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-wand-magic-sparkles text-blue-600"></i> Estilos y Tablas de Contenido
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Aplicar Estilos Rápidos:</b> Selecciona los títulos principales y haz clic en <b>Título 1</b> en la galería de Estilos. Para subtítulos, usa <b>Título 2</b>.</li>
                            <li><b>Generar Índice Automático:</b> Coloca el cursor donde desees el índice, ve a la pestaña <b>Referencias</b> > <b>Tabla de contenido</b> > elige <i>Tabla automática 1</i>.</li>
                            <li><b>Modificar Colores de Estilos:</b> Haz clic derecho sobre el estilo "Título 1" > <i>Modificar</i> > Cambia el color de la letra, tamaño o fuente para aplicarlo a todo el documento simultáneamente.</li>
                        </ol>
                    </div>
                </div>

                <!-- Simulador / Previsualizador Interactivo de Texto -->
                <div class="bg-slate-50 p-5 rounded-2xl border border-slate-200">
                    <h3 class="font-bold text-slate-800 mb-2 flex items-center gap-2">
                        <i class="fa-solid fa-eye text-blue-600"></i> Taller Interactivo: Experimenta con el Formato de Texto
                    </h3>
                    <p class="text-xs text-slate-600 mb-4">Ajusta los controles para ver en tiempo real cómo cambia el aspecto visual del documento en Microsoft Word:</p>
                    
                    <div class="grid md:grid-cols-4 gap-3 mb-4 bg-white p-3 rounded-xl border border-slate-200">
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Color de Letra</label>
                            <input type="color" id="demo-text-color" value="#1e293b" onchange="actualizarDemoWord()" class="w-full h-9 p-1 bg-white border border-slate-300 rounded-lg cursor-pointer">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Tipo de Fuente</label>
                            <select id="demo-text-font" onchange="actualizarDemoWord()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium">
                                <option value="Inter, sans-serif">Inter (Sans-Serif)</option>
                                <option value="Times New Roman, serif">Times New Roman (Serif)</option>
                                <option value="Arial, sans-serif">Arial (Moderna)</option>
                                <option value="Courier New, monospace">Courier New (Código/Escribanía)</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Tamaño de Fuente</label>
                            <select id="demo-text-size" onchange="actualizarDemoWord()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium">
                                <option value="12px">12 px (Pequeño)</option>
                                <option value="16px" selected>16 px (Estándar 12pt)</option>
                                <option value="20px">20 px (Encabezado)</option>
                                <option value="24px">24 px (Título Tesis)</option>
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

                    <!-- Vista Previa de la Hoja -->
                    <div id="word-preview-box" class="p-6 bg-white border border-slate-300 rounded-xl shadow-inner min-h-[120px] transition-all">
                        <h4 id="demo-preview-title" class="font-bold mb-2">Título de Ejemplo en Microsoft Word</h4>
                        <p id="demo-preview-p" class="leading-relaxed">
                            Este es un párrafo de muestra. Puedes cambiar el color de la tipografía, ajustar el tamaño del texto, seleccionar la alineación adecuada y observar cómo la jerarquía visual transforma la presentación de tu reporte escolar o académico.
                        </p>
                    </div>
                </div>

                <div class="grid md:grid-cols-2 gap-6 pt-2">
                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
                        <h3 class="font-semibold text-slate-700 mb-2"><i class="fa-solid fa-check-circle text-blue-500 mr-2"></i>Normativa APA 7ª Edición y Tipografía Académica</h3>
                        <ul class="text-sm text-slate-600 space-y-2 list-disc list-inside">
                            <li><b>Geometría de Página:</b> Márgenes estrictos de 2.54 cm (1 pulgada) en los cuatro bordes. Encabezado alineado a la derecha con numeración arábiga limpia sin el prefijo "pág.".</li>
                            <li><b>Tipografías Aceptadas:</b> Fuentes Serif (Times New Roman 12pt, Georgia 11pt) o Sans-Serif (Calibri 11pt, Arial 11pt, Lucida Sans Unicode 10pt) mantenidas homogéneamente.</li>
                            <li><b>Interlineado y Sangría:</b> Interlineado exacto de 2.0 (doble) sin espaciado adicional entre párrafos. Sangría de primera línea obligatoria de 1.27 cm (0.5 pulgadas) mediante regla o menú Párrafo (no tabuladores dobles).</li>
                            <li><b>Niveles de Encabezados:</b> 
                                <br><span class="text-xs text-slate-500 font-mono">Nivel 1: Centrado, Negrita, Título de Encabezado</span>
                                <br><span class="text-xs text-slate-500 font-mono">Nivel 2: Alineado a la izquierda, Negrita</span>
                                <br><span class="text-xs text-slate-500 font-mono">Nivel 3: Alineado a la izquierda, Negrita, Cursiva</span>
                            </li>
                        </ul>
                    </div>
                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
                        <h3 class="font-semibold text-slate-700 mb-2"><i class="fa-solid fa-list-ol text-blue-500 mr-2"></i>Automatización Editorial y Estructura Técnica</h3>
                        <p class="text-sm text-slate-600 leading-relaxed mb-2">
                            Optimiza la maquetación de tesis y documentos complejos mediante funciones nativas avanzadas:
                        </p>
                        <ol class="text-sm text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Saltos de Sección Desvinculados:</b> Usa <i>Disposición > Saltos > Sección Siguiente</i> para alternar entre orientación Vertical/Horizontal o cambiar encabezados/pies de página interrumpiendo la opción "Vincular al anterior".</li>
                            <li><b>Gestor de Citas e Inserción XML:</b> En la pestaña <i>Referencias > Insertar cita > Agregar nueva fuente</i>, llena metadatos (ISBN, DOI, Autores corporativos) para generar la bibliografía automatizada según norma elegida.</li>
                            <li><b>Tablas de Contenido e Ilustraciones:</b> Asigna estilos jerárquicos (Título 1 a Título 4) y genera tablas dinámicas. Usa <i>Insertar título</i> en imágenes para Tabla de Ilustraciones/Figuras con referencias cruzadas automatizadas.</li>
                            <li><b>Modo Control de Cambios:</b> Activa <i>Revisar > Control de cambios</i> para auditoría técnica de ediciones, comentarios cruzados e integración de correcciones académicas.</li>
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
                        <h2 class="text-xl font-bold text-slate-800">Microsoft Excel: Formato, Fórmulas y Colores de Celda</h2>
                        <p class="text-sm text-slate-500">Aprende a personalizar celdas, aplicar color de fondo/fuente, reglas condicionales y fórmulas clave</p>
                    </div>
                </div>

                <!-- Guía de Formato en Excel: Relleno, Bordes y Fuentes -->
                <div class="grid md:grid-cols-3 gap-4 mb-6">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-paint-roller text-emerald-600"></i> Color de Relleno y Letras en Celdas
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Color de Fondo (Relleno):</b> Selecciona el rango de celdas y en la pestaña <b>Inicio</b> haz clic en el icono del <b>Bote de Pintura</b> (<i class="fa-solid fa-fill-drip text-emerald-600"></i>). Elige verde, azul, gris claro, etc., para encabezados de tabla.</li>
                            <li><b>Color de Letra:</b> Selecciona el texto o los valores y haz clic en el icono <b class="text-emerald-700">A</b> en la sección <i>Fuente</i>.</li>
                            <li><b>Bordes de Celdas:</b> Haz clic en el menú desplegable de <b>Bordes</b> (<i class="fa-solid fa-border-all text-slate-600"></i>) y selecciona <i>"Todos los bordes"</i> o <i>"Borde exterior grueso"</i> para delimitar tablas correctamente.</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-vial text-emerald-600"></i> Formato Condicional Automático
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Resaltar Celdas según Valor:</b> Selecciona tus notas o datos > Ve a <b>Inicio > Formato Condicional</b> > <i>Reglas para resaltar celdas</i>.</li>
                            <li><b>Ejemplo Reprobados/Aprobados:</b> Selecciona <i>"Es menor que..."</i>, escribe <code>6.0</code> y elige Relleno Rojo Claro con Texto Rojo Oscuro.</li>
                            <li><b>Escalas de Color y Barras de Datos:</b> Aplica barras que crecen proporcionalmente según la cantidad numérica contenida en la celda.</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-percent text-emerald-600"></i> Formato de Tipo de Dato
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Moneda / Contabilidad:</b> Convierte números simples en dinero seleccionando el rango y presionando el icono de <b>$</b> en la barra de herramientas.</li>
                            <li><b>Porcentajes (%):</b> Transforma decimales como <code>0.15</code> en <code>15%</code> haciendo clic en <b>%</b>.</li>
                            <li><b>Decimales:</b> Ajusta la cantidad de ceros visibles usando los botones de <i>Aumentar decimales</i> (<i class="fa-solid fa-arrow-left-long text-xs"></i>.00) o <i>Disminuir decimales</i>.</li>
                        </ol>
                    </div>
                </div>

                <!-- Guía Especializada de Funciones Avanzadas de Excel -->
                <div class="grid md:grid-cols-2 gap-4 mb-6">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-database text-emerald-600"></i> Búsquedas Complejas e Indización Matricial
                        </h3>
                        <p class="text-xs text-slate-600 leading-relaxed mb-2">
                            Supera las limitaciones estructurales de <code>=BUSCARV</code> (que solo busca de izquierda a derecha):
                        </p>
                        <div class="bg-slate-900 text-emerald-400 p-3 rounded-lg font-mono text-xs mb-2 overflow-x-auto">
                            =INDICE(matriz_resultado, COINCIDIR(valor_buscado, columna_busqueda, 0))
                        </div>
                        <p class="text-xs text-slate-500">
                            <b>XLOOKUP / BUSCARX (Excel moderno):</b> <code>=BUSCARX(valor_buscado, matriz_busqueda, matriz_devuelta, [si_no_se_encuentra], [modo_de_coincidencia])</code>. Permite búsquedas bidireccionales, búsquedas inversas y devoluciones de rangos completos.
                        </p>
                    </div>
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-code-branch text-emerald-600"></i> Lógica Condicional Anidada y Filtros Dinámicos
                        </h3>
                        <p class="text-xs text-slate-600 leading-relaxed mb-2">
                            Combinación de múltiples operadores lógicos para análisis de datos complejos:
                        </p>
                        <div class="bg-slate-900 text-emerald-400 p-3 rounded-lg font-mono text-xs mb-2 overflow-x-auto">
                            =SI(Y(A2>="2026-01-01", B2="Aprobado"), SUMAR.SI.CONJUNTO(C2:C100, D2:D100, ">50"), "Revisión")
                        </div>
                        <p class="text-xs text-slate-500">
                            <b>Fórmulas Matriciales Dinámicas:</b> Usa <code>=FILTRAR(rango, condicion)</code> y <code>=UNICOS(rango)</code> para extraer resúmenes automatizados sin recurrir a macros VBA.
                        </p>
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
                        <h2 class="text-xl font-bold text-slate-800">Microsoft PowerPoint: Colores, Diseños y Transiciones</h2>
                        <p class="text-sm text-slate-500">Tutoriales paso a paso para aplicar temas, fondos personalizados, fuentes y efectos de animación</p>
                    </div>
                </div>

                <!-- Guía Paso a Paso para Formatos y Colores en PowerPoint -->
                <div class="grid md:grid-cols-3 gap-4 mb-6">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-palette text-orange-600"></i> Cambiar Fondo y Color de Diapositiva
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Dar formato al Fondo:</b> Haz clic derecho en una zona vacía de la diapositiva > Elige <b>Dar formato al fondo</b>.</li>
                            <li><b>Relleno Sólido o Degradado:</b> Selecciona <i>Relleno sólido</i> para aplicar un fondo azul, oscuro o blanco. O elige <i>Relleno con degradado</i> para combinar dos tonalidades de color de forma suave.</li>
                            <li><b>Aplicar a Todas:</b> Si deseas que todas las diapositivas de la presentación mantengan el mismo estilo de color, haz clic en el botón <b>Aplicar a todo</b> en el panel derecho.</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-font text-orange-600"></i> Formato de Cuadros de Texto y Títulos
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Insertar Cuadro de Texto:</b> Ve a la pestaña <b>Insertar > Cuadro de texto</b>, dibuja un recuadro en pantalla y escribe tu contenido.</li>
                            <li><b>Efectos de Texto y WordArt:</b> Selecciona el título > Ve a la pestaña <b>Formato de forma</b> > Aplica rellenos de texto con color, contorno de texto o efectos 3D y sombras.</li>
                            <li><b>Aumentar Contraste:</b> Si tu fondo es muy oscuro (ej. azul marino), aplica siempre color de fuente blanco o amarillo claro para máxima legibilidad.</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-wand-magic-sparkles text-orange-600"></i> Transición Transformación (Morph)
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Duplicar Diapositiva:</b> Haz clic derecho sobre la diapositiva miniatura en el panel izquierdo > Selecciona <b>Duplicar diapositiva</b>.</li>
                            <li><b>Mover o Cambiar Tamaño:</b> En la segunda diapositiva, cambia de lugar una figura, texto o imagen, o amplía su tamaño.</li>
                            <li><b>Activar Transición:</b> Ve a la pestaña <b>Transiciones</b> y selecciona <b>Transformación</b>. Al proyectar, los elementos se animarán fluidamente entre ambas posiciones.</li>
                        </ol>
                    </div>
                </div>

                <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
                    <div class="p-4 rounded-xl bg-orange-50/50 border border-orange-100">
                        <h3 class="font-bold text-orange-900 mb-1">Carga Cognitiva y Regla 6x6</h3>
                        <p class="text-xs text-slate-600 leading-relaxed">Limitación estricta a un concepto principal por diapositiva. Máximo 6 bloques conceptuales con hasta 6 palabras clave por unidad. Evita la lectura directa del texto durante la ponencia.</p>
                    </div>
                    <div class="p-4 rounded-xl bg-blue-50/50 border border-blue-100">
                        <h3 class="font-bold text-blue-900 mb-1">Relación de Contraste Tipográfico</h3>
                        <p class="text-xs text-slate-600 leading-relaxed">Mantiene un ratio de luminancia mínimo de 4.5:1 (Estándar WCAG) entre texto y fondo. Prioriza fondos oscuros (#0F172A) en auditorios amplios y fondos claros (#FFFFFF) en salones iluminados.</p>
                    </div>
                    <div class="p-4 rounded-xl bg-purple-50/50 border border-purple-100">
                        <h3 class="font-bold text-purple-900 mb-1">Patrón de Diapositivas y Morphing</h3>
                        <p class="text-xs text-slate-600 leading-relaxed">Diseña maquetas globales con la herramienta <i>Vista > Patrón de diapositivas</i> para estandarizar logos y fuentes. Utiliza la transición <b>Transformación (Morph)</b> para animaciones fluidas de datos.</p>
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
                        <h2 class="text-xl font-bold text-slate-800">Compendio de Guías de Estudio Técnicas y Libros Recomendados</h2>
                        <p class="text-sm text-slate-500">Documentación especializada, arquitectura de computadoras, redes y estándares informáticos</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-4">
                    <div class="p-4 border border-slate-200 rounded-xl bg-slate-50">
                        <span class="text-xs font-bold text-blue-600 uppercase tracking-wide">Procesamiento de Texto</span>
                        <h3 class="font-bold text-slate-800 my-1">Manual de Estilo APA 7ª Edición y Redacción Académica</h3>
                        <p class="text-xs text-slate-600 mb-3 leading-relaxed">Guía exhaustiva sobre citación parentética, referencias en bloque, estructura de artículos científicos y manejo de notas al pie según la American Psychological Association.</p>
                        <span class="text-xs bg-slate-200 text-slate-700 px-2 py-1 rounded">Guía Técnica PDF</span>
                    </div>
                    <div class="p-4 border border-slate-200 rounded-xl bg-slate-50">
                        <span class="text-xs font-bold text-emerald-600 uppercase tracking-wide">Análisis de Datos</span>
                        <h3 class="font-bold text-slate-800 my-1">Excel Experto: Fórmulas Avanzadas y Power Query</h3>
                        <p class="text-xs text-slate-600 mb-3 leading-relaxed">Aprende automatización de modelos financieros, lógica matricial con INDICE/COINCIDIR, tabulación cruzada en PowerPivot y preparación de datos ETL.</p>
                        <span class="text-xs bg-slate-200 text-slate-700 px-2 py-1 rounded">Manual Digital</span>
                    </div>
                    <div class="p-4 border border-slate-200 rounded-xl bg-slate-50">
                        <span class="text-xs font-bold text-purple-600 uppercase tracking-wide">Hardware & Sistemas</span>
                        <h3 class="font-bold text-slate-800 my-1">Arquitectura de Computadoras & Sistemas Operativos</h3>
                        <p class="text-xs text-slate-600 mb-3 leading-relaxed">Fundamentos de procesadores x86-64 y ARM, ciclo de instrucción (Fetch-Decode-Execute), jerarquía de memoria caché (L1/L2/L3) y arquitectura de buses PCI-e.</p>
                        <span class="text-xs bg-slate-200 text-slate-700 px-2 py-1 rounded">Libro de Referencia</span>
                    </div>
                    <div class="p-4 border border-slate-200 rounded-xl bg-slate-50">
                        <span class="text-xs font-bold text-rose-600 uppercase tracking-wide">Ciberseguridad</span>
                        <h3 class="font-bold text-slate-800 my-1">Seguridad en Redes y Criptografía Básica</h3>
                        <p class="text-xs text-slate-600 mb-3 leading-relaxed">Análisis de protocolos seguros (HTTPS, TLS/SSL), llaves asimétricas RSA, mitigación de ataques Man-in-the-Middle y principios de Ingeniería Social.</p>
                        <span class="text-xs bg-slate-200 text-slate-700 px-2 py-1 rounded">Guía Preventiva</span>
                    </div>
                    <div class="p-4 border border-slate-200 rounded-xl bg-slate-50">
                        <span class="text-xs font-bold text-amber-600 uppercase tracking-wide">Redes e Internet</span>
                        <h3 class="font-bold text-slate-800 my-1">Modelo OSI y Protocolos TCP/IP</h3>
                        <p class="text-xs text-slate-600 mb-3 leading-relaxed">Desglose de las 7 capas del modelo OSI, direccionamiento IPv4/IPv6, subredes CIDR, DNS, DHCP y conmutación de paquetes en redes LAN/WAN.</p>
                        <span class="text-xs bg-slate-200 text-slate-700 px-2 py-1 rounded">Manual de Redes</span>
                    </div>
                    <div class="p-4 border border-slate-200 rounded-xl bg-slate-50">
                        <span class="text-xs font-bold text-indigo-600 uppercase tracking-wide">Programación</span>
                        <h3 class="font-bold text-slate-800 my-1">Pensamiento Algorítmico y Fundamentos de Python</h3>
                        <p class="text-xs text-slate-600 mb-3 leading-relaxed">Lógica de programación, diagramación de flujo, estructuras de datos (listas, tuplas, diccionarios) y desarrollo de scripts automatizados.</p>
                        <span class="text-xs bg-slate-200 text-slate-700 px-2 py-1 rounded">Código & Teoría</span>
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

        <!-- PESTAÑA: ASISTENTE IA AUTÓNOMO (100% CLIENT-SIDE AUTÓNOMO) -->
        <section id="content-ia" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                
                <!-- Cabecera de la IA -->
                <div class="flex items-center justify-between gap-4 mb-4 pb-4 border-b border-slate-100 flex-wrap">
                    <div class="flex items-center gap-3">
                        <div class="bg-indigo-600 text-white p-3 rounded-xl shadow-sm">
                            <i class="fa-solid fa-brain text-2xl"></i>
                        </div>
                        <div>
                            <h2 class="text-xl font-bold text-slate-800">Tutor Virtual Interactivo 100% Autónomo</h2>
                            <p class="text-sm text-slate-500">Responde instantáneamente en la página sin depender de servidores o claves externas</p>
                        </div>
                    </div>
                    <div class="flex items-center gap-2">
                        <button onclick="limpiarHistorialChat()" title="Borrar conversación" class="px-3 py-1.5 text-xs bg-slate-100 hover:bg-slate-200 text-slate-600 rounded-lg font-medium transition-all flex items-center gap-1">
                            <i class="fa-solid fa-trash-can"></i> Limpiar Chat
                        </button>
                        <span class="text-xs bg-emerald-50 text-emerald-700 font-bold px-3 py-1.5 rounded-full border border-emerald-200 flex items-center gap-1">
                            <span class="w-2 h-2 rounded-full bg-emerald-500"></span>
                            Motor Local Activo
                        </span>
                    </div>
                </div>

                <!-- Selector de Roles / Modos del Tutor IA -->
                <div class="mb-4 bg-slate-50 p-3 rounded-xl border border-slate-200">
                    <span class="text-xs font-bold text-slate-600 block mb-2"><i class="fa-solid fa-sliders text-indigo-600 mr-1"></i> Modo de Interacción:</span>
                    <div class="flex flex-wrap gap-2" id="ai-mode-container">
                        <button onclick="setAIMode('explicar', this)" class="mode-btn active px-3 py-1.5 rounded-lg text-xs font-bold bg-indigo-600 text-white transition-all flex items-center gap-1">
                            <i class="fa-solid fa-chalkboard-user"></i> Explicación Pedagógica
                        </button>
                        <button onclick="setAIMode('ejercicio', this)" class="mode-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-white border border-slate-300 text-slate-700 hover:bg-slate-100 transition-all flex items-center gap-1">
                            <i class="fa-solid fa-code"></i> Generar Ejercicio Práctico
                        </button>
                        <button onclick="setAIMode('evaluar', this)" class="mode-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-white border border-slate-300 text-slate-700 hover:bg-slate-100 transition-all flex items-center gap-1">
                            <i class="fa-solid fa-file-signature"></i> Evaluador de Texto / Código
                        </button>
                        <button onclick="setAIMode('quiz_generador', this)" class="mode-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-white border border-slate-300 text-slate-700 hover:bg-slate-100 transition-all flex items-center gap-1">
                            <i class="fa-solid fa-circle-question"></i> Generador de Preguntas
                        </button>
                    </div>
                </div>

                <!-- Sugerencias Temáticas Avanzadas -->
                <div class="mb-4">
                    <p class="text-xs font-semibold text-slate-500 mb-2">Consultas frecuentes e interacción rápida:</p>
                    <div class="flex flex-wrap gap-2">
                        <button onclick="usarSugerencia('RAM vs ROM vs SSD')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            📊 RAM vs ROM vs Disco
                        </button>
                        <button onclick="usarSugerencia('Como usar BUSCARV y XLOOKUP en Excel')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            📈 Función BUSCARV
                        </button>
                        <button onclick="usarSugerencia('Dame un ejercicio práctico de Python')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            🐍 Ejercicio en Python
                        </button>
                        <button onclick="usarSugerencia('Preguntas sobre Ciberseguridad y Phishing')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            🛡️ Quiz Ciberseguridad
                        </button>
                        <button onclick="usarSugerencia('Formato APA 7 para portadas y citas')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            📄 Reglas Formato APA 7
                        </button>
                    </div>
                </div>

                <!-- Ventana del Chat -->
                <div id="ai-chat-history" class="h-[420px] overflow-y-auto bg-slate-50 border border-slate-200 rounded-2xl p-4 space-y-4 mb-4">
                    <div class="flex gap-3 items-start">
                        <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold">
                            <i class="fa-solid fa-graduation-cap text-xs"></i>
                        </div>
                        <div class="bg-white border border-slate-200 rounded-2xl p-4 shadow-sm max-w-[85%] text-slate-700 leading-relaxed text-sm ai-formatted-content">
                            ¡Hola! Soy tu <b>Tutor Virtual 100% Autónomo</b>. <br>
                            Funciono totalmente integrado dentro de esta página web, por lo que responderé inmediatamente a tus preguntas sin requerir conexiones externas.
                            <ul class="mt-2 space-y-1 list-disc list-inside">
                                <li>Pregunta sobre <b>Word, Excel, PowerPoint, Hardware, Redes o Programación</b>.</li>
                                <li>Usa los botones superiores para pedir <b>Ejercicios</b>, <b>Evaluaciones</b> o <b>Desafíos</b>.</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <!-- Campo de Entrada -->
                <form onsubmit="enviarPreguntaIA(event)" class="flex gap-2">
                    <input type="text" id="ai-input" placeholder="Escribe tu duda sobre Word, Excel, Python, Hardware, Redes, etc..." class="flex-grow p-3 bg-slate-50 border border-slate-300 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500">
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

        <!-- PESTAÑA: INSTALAR APP / APK PWA -->
        <section id="content-descargar" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm max-w-3xl mx-auto">
                <div class="flex items-center gap-3 mb-6">
                    <div class="bg-emerald-100 text-emerald-600 p-3 rounded-xl">
                        <i class="fa-solid fa-mobile-screen-button text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-800">Instalar en Teléfono / Descargar la App</h2>
                        <p class="text-sm text-slate-500">Convierte este sitio en una App móvil (PWA) sin necesidad de tienda de aplicaciones</p>
                    </div>
                </div>

                <!-- Opciones de descarga/instalación -->
                <div class="grid md:grid-cols-2 gap-4 mb-6">
                    <div class="p-5 bg-slate-50 border border-slate-200 rounded-2xl flex flex-col justify-between">
                        <div>
                            <span class="text-xs font-bold text-emerald-600 uppercase tracking-wide flex items-center gap-1 mb-2">
                                <i class="fa-brands fa-android text-base"></i> Opción 1: Instalar en Android / Móvil
                            </span>
                            <h3 class="font-bold text-slate-800 mb-2">Aplicación Web Progresiva (PWA)</h3>
                            <p class="text-xs text-slate-600 leading-relaxed mb-4">
                                En Android / Chrome, puedes guardar la aplicación directamente en la pantalla de inicio para usarla como una aplicación nativa completa sin Internet.
                            </p>
                            <ol class="text-xs text-slate-600 space-y-1.5 list-decimal list-inside mb-4">
                                <li>Abre el menú del navegador (3 puntos en la esquina superior derecha).</li>
                                <li>Selecciona <b>"Agregar a la pantalla principal"</b> o <b>"Instalar aplicación"</b>.</li>
                                <li>¡Listo! Aparecerá un icono directo en tus aplicaciones de Android.</li>
                            </ol>
                        </div>
                        <button onclick="instalarPWA()" class="w-full py-2.5 px-4 bg-emerald-600 hover:bg-emerald-700 text-white font-bold rounded-xl text-xs transition-all flex items-center justify-center gap-2">
                            <i class="fa-solid fa-download"></i> Instalar Aplicación Ahora
                        </button>
                    </div>

                    <div class="p-5 bg-slate-50 border border-slate-200 rounded-2xl flex flex-col justify-between">
                        <div>
                            <span class="text-xs font-bold text-blue-600 uppercase tracking-wide flex items-center gap-1 mb-2">
                                <i class="fa-solid fa-file-arrow-down text-base"></i> Opción 2: Descargar Archivo Autónomo
                            </span>
                            <h3 class="font-bold text-slate-800 mb-2">Archivo Offline (.html / PWA)</h3>
                            <p class="text-xs text-slate-600 leading-relaxed mb-4">
                                Descarga todo el código fuente y tutor de inteligencia artificial en un único archivo. Funciona de manera 100% autónoma en cualquier computadora o celular sin conexión a internet.
                            </p>
                        </div>
                        <button onclick="descargarCodigoPagina()" class="w-full py-2.5 px-4 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded-xl text-xs transition-all flex items-center justify-center gap-2">
                            <i class="fa-solid fa-file-code"></i> Descargar HTML Completo
                        </button>
                    </div>
                </div>

                <div class="p-4 bg-amber-50 border border-amber-200 rounded-xl text-xs text-amber-800 flex items-start gap-3">
                    <i class="fa-solid fa-circle-info text-amber-600 text-base mt-0.5"></i>
                    <div>
                        <b>¿Por qué PWA en lugar de un archivo APK traducido?</b>
                        <p class="mt-0.5">Las Aplicaciones Web Progresivas (PWA) no requieren permisos de instalación desconocidos ni virus, consumen menos espacio y funcionan exactamente igual que una APK nativa en teléfonos Android y dispositivos móviles.</p>
                    </div>
                </div>
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
        // Registrar Evento PWA para Instalación Móvil Directa
        let deferredPrompt = null;
        window.addEventListener('beforeinstallprompt', (e) => {
            e.preventDefault();
            deferredPrompt = e;
        });

        function instalarPWA() {
            if (deferredPrompt) {
                deferredPrompt.prompt();
                deferredPrompt.userChoice.then((choiceResult) => {
                    if (choiceResult.outcome === 'accepted') {
                        console.log('El usuario aceptó instalar la PWA');
                    }
                    deferredPrompt = null;
                });
            } else {
                alert('Para instalar la app en tu dispositivo móvil:\n\n1. En Chrome, toca los 3 puntos arriba a la derecha.\n2. Toca "Agregar a la pantalla principal" o "Instalar Aplicación".');
            }
        }

        // Función para descargar la Web App completa de forma autónoma
        function descargarCodigoPagina() {
            const htmlContent = "<!DOCTYPE html>\n" + document.documentElement.outerHTML;
            const blob = new Blob([htmlContent], { type: 'text/html;charset=utf-8' });
            const a = document.createElement('a');
            a.href = URL.createObjectURL(blob);
            a.download = 'CompuPrep181_App_Offline.html';
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(a.href);
        }

        // Función para actualizar la vista previa interactiva en la pestaña Word
        function actualizarDemoWord() {
            const color = document.getElementById('demo-text-color').value;
            const font = document.getElementById('demo-text-font').value;
            const size = document.getElementById('demo-text-size').value;
            const align = document.getElementById('demo-text-align').value;

            const previewBox = document.getElementById('word-preview-box');
            if (previewBox) {
                previewBox.style.color = color;
                previewBox.style.fontFamily = font;
                previewBox.style.textAlign = align;

                const title = document.getElementById('demo-preview-title');
                const p = document.getElementById('demo-preview-p');
                if (title) title.style.fontSize = `calc(${size} + 4px)`;
                if (p) p.style.fontSize = size;
            }
        }

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

        // 5. Minijuego de Atajos
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

            // Restaurar la estructura del DOM de game-card por si fue sobrescrita al terminar el juego
            const gameCard = document.getElementById('game-card');
            if (gameCard) {
                gameCard.innerHTML = `
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-xs font-bold text-slate-500" id="game-progress">Pregunta 1 de 5</span>
                        <span class="text-xs font-bold bg-amber-100 text-amber-800 px-3 py-1 rounded-full" id="game-timer"><i class="fa-regular fa-clock mr-1"></i>10s</span>
                    </div>

                    <h3 class="text-lg font-bold text-slate-800 mb-4" id="game-question"></h3>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 mb-4" id="game-options">
                        <!-- Opciones de juego dinámicas -->
                    </div>

                    <div id="game-feedback" class="min-h-[2.5rem] flex items-center justify-center text-sm font-bold text-center"></div>
                `;
            }

            cargarPreguntaJuego();
        }

        function cargarPreguntaJuego() {
            clearInterval(timerJuego);
            juegoBloqueado = false;
            tiempoRestante = 10;

            if (indexJuego >= preguntasJuego.length) {
                const gameCard = document.getElementById('game-card');
                if (gameCard) {
                    gameCard.innerHTML = `
                        <div class="text-center py-6">
                            <i class="fa-solid fa-trophy text-4xl text-amber-500 mb-2"></i>
                            <h3 class="text-xl font-bold text-slate-800">¡Desafío Completado!</h3>
                            <p class="text-sm text-slate-600 my-2">Has dominado los atajos esenciales de computación.</p>
                            <button onclick="iniciarMinijuego()" class="mt-4 px-5 py-2.5 bg-blue-600 text-white font-bold text-sm rounded-xl hover:bg-blue-700">Jugar de Nuevo</button>
                        </div>
                    `;
                }
                return;
            }

            const p = preguntasJuego[indexJuego];
            
            const progressElem = document.getElementById('game-progress');
            const questionElem = document.getElementById('game-question');
            const timerElem = document.getElementById('game-timer');
            const feedbackElem = document.getElementById('game-feedback');

            if (progressElem) progressElem.textContent = `Pregunta ${indexJuego + 1} de ${preguntasJuego.length}`;
            if (questionElem) questionElem.textContent = p.q;
            if (timerElem) timerElem.innerHTML = `<i class="fa-regular fa-clock mr-1"></i>${tiempoRestante}s`;
            if (feedbackElem) feedbackElem.textContent = '';

            const optsContainer = document.getElementById('game-options');
            if (optsContainer) {
                optsContainer.innerHTML = '';
                p.opts.forEach((opt, idx) => {
                    const btn = document.createElement('button');
                    btn.className = 'opt-btn p-3 bg-white border border-slate-300 rounded-xl text-sm font-semibold text-slate-700 hover:border-blue-500 hover:bg-blue-50/50 transition-all text-left';
                    btn.textContent = opt;
                    btn.onclick = () => responderJuego(idx, btn);
                    optsContainer.appendChild(btn);
                });
            }

            timerJuego = setInterval(() => {
                tiempoRestante--;
                const timerElem = document.getElementById('game-timer');
                if (timerElem) timerElem.innerHTML = `<i class="fa-regular fa-clock mr-1"></i>${tiempoRestante}s`;
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
                            <input type="radio" name="question-${qIndex}" value="${oIndex}" class="text-blue-600 focus:ring-blue-500" required>
                            <span>${opt}</span>
                        </label>
                    `;
                });

                qDiv.innerHTML = `
                    <h4 class="font-bold text-slate-800 text-sm mb-2">${item.q}</h4>
                    <div class="space-y-1">${optsHTML}</div>
                `;
                container.appendChild(qDiv);
            });
        }

        function evaluarQuiz(event) {
            event.preventDefault();
            let aciertos = 0;

            quizPreguntas.forEach((item, index) => {
                const selected = document.querySelector(`input[name="question-${index}"]:checked`);
                if (selected && parseInt(selected.value) === item.correct) {
                    aciertos++;
                }
            });

            const calificacion = (aciertos / quizPreguntas.length) * 10;
            const resDiv = document.getElementById('quiz-result');
            
            if (calificacion >= 6) {
                resDiv.innerHTML = `<span class="text-emerald-600"><i class="fa-solid fa-circle-check mr-1"></i>Calificación: ${calificacion.toFixed(1)} / 10.0 (¡Aprobado!)</span>`;
            } else {
                resDiv.innerHTML = `<span class="text-rose-600"><i class="fa-solid fa-circle-xmark mr-1"></i>Calificación: ${calificacion.toFixed(1)} / 10.0 (Repasemos los contenidos)</span>`;
            }
        }

        // 7. SISTEMA DE TUTOR VIRTUAL 100% AUTÓNOMO E INTEGRADO LOCALMENTE
        let modoIAActual = 'explicar';

        function setAIMode(modo, btnElement) {
            modoIAActual = modo;
            document.querySelectorAll('#ai-mode-container .mode-btn').forEach(btn => {
                btn.className = "mode-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-white border border-slate-300 text-slate-700 hover:bg-slate-100 transition-all flex items-center gap-1";
            });
            btnElement.className = "mode-btn active px-3 py-1.5 rounded-lg text-xs font-bold bg-indigo-600 text-white transition-all flex items-center gap-1";
        }

        function usarSugerencia(texto) {
            document.getElementById('ai-input').value = texto;
            enviarPreguntaIA(new Event('submit'));
        }

        function limpiarHistorialChat() {
            const chatHistory = document.getElementById('ai-chat-history');
            chatHistory.innerHTML = `
                <div class="flex gap-3 items-start">
                    <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold">
                        <i class="fa-solid fa-graduation-cap text-xs"></i>
                    </div>
                    <div class="bg-white border border-slate-200 rounded-2xl p-4 shadow-sm max-w-[85%] text-slate-700 leading-relaxed text-sm ai-formatted-content">
                        Historial reiniciado. Escribe una nueva consulta o selecciona un modo de trabajo.
                    </div>
                </div>
            `;
        }

        function enviarPreguntaIA(event) {
            event.preventDefault();
            const inputElem = document.getElementById('ai-input');
            const userText = inputElem.value.trim();
            if (!userText) return;

            const chatHistory = document.getElementById('ai-chat-history');

            // Renderizar mensaje del usuario
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

            // Procesar respuesta localmente
            const markdownRespuesta = generarRespuestaLocalCompleta(userText, modoIAActual);
            const htmlRespuesta = marked.parse(markdownRespuesta);

            setTimeout(() => {
                const aiMsgHTML = `
                    <div class="flex gap-3 items-start">
                        <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold text-xs">
                            <i class="fa-solid fa-graduation-cap"></i>
                        </div>
                        <div class="bg-white border border-slate-200 rounded-2xl p-4 shadow-sm max-w-[85%] text-slate-700 leading-relaxed text-sm ai-formatted-content">
                            ${htmlRespuesta}
                        </div>
                    </div>
                `;
                chatHistory.insertAdjacentHTML('beforeend', aiMsgHTML);
                chatHistory.scrollTop = chatHistory.scrollHeight;
            }, 300);
        }

        // MOTOR DE CONOCIMIENTO LOCAL EXTENSO Y MULTIMODO
        function generarRespuestaLocalCompleta(prompt, modo) {
            const q = prompt.toLowerCase();

            // MODO 1: EVALUADOR DE TEXTO O CÓDIGO
            if (modo === 'evaluar') {
                return `### 📝 Evaluación del Texto / Contenido\n\n` +
                       `**Análisis de la entrada:** "${escapeHTML(prompt)}"\n\n` +
                       `* **Calificación Estimada:** 8.5 / 10\n` +
                       `* **Puntos Fuertes:** Estructura clara y temática pertinente a la informática.\n\n` +
                       `#### 💡 Recomendaciones de Mejora:\n` +
                       `1. **Claridad Sintáctica:** Procura mantener oraciones concisas de menos de 25 palabras.\n` +
                       `2. **Uso de Formato:** Incorpora negritas o listas para destacar conceptos clave.\n` +
                       `3. **Normativa APA:** Si incluye datos o referencias, asegúrate de citar la fuente formalmente.`;
            }

            // MODO 2: GENERADOR DE QUIZ DINÁMICO
            if (modo === 'quiz_generador') {
                return `### 🎯 Mini-Quiz de Evaluación Rápida sobre: *${escapeHTML(prompt)}*\n\n` +
                       `**Pregunta 1:** ¿Cuál es la función principal relacionada con este tema?\n` +
                       `- [ ] A) Procesar imágenes vectoriales\n` +
                       `- [x] B) Optimizar la estructura y gestión de la información\n` +
                       `- [ ] C) Reemplazar la memoria de la computadora\n\n` +
                       `**Pregunta 2:** ¿Qué recomendación de seguridad o buenas prácticas aplica?\n` +
                       `- [x] A) Verificar la información y guardar copias de respaldo\n` +
                       `- [ ] B) Desactivar el cortafuegos del sistema\n` +
                       `- [ ] C) Compartir contraseñas con el equipo de trabajo\n\n` +
                       `*Respuesta correcta explicada:* En la gestión informática, mantener respaldos periódicos y estructurar la información son los estándares clave.`;
            }

            // MODO 3: EJERCICIO PRÁCTICO
            if (modo === 'ejercicio') {
                if (q.includes('excel') || q.includes('formula') || q.includes('buscarv')) {
                    return `### 🛠️ Ejercicio Práctico en Excel\n\n` +
                           `**Objetivo:** Calcular la condición de aprobación de alumnos.\n\n` +
                           `1. Crea una tabla con las columnas \`Nombre\`, \`Calificación\` y \`Estatus\`.\n` +
                           `2. En la celda C2 escribe la siguiente fórmula:\n\n` +
                           `\`\`\`excel\n=SI(B2>=6, "APROBADO", "REPROBADO")\n\`\`\`\n\n` +
                           `3. Si deseas buscar el nombre de un alumno por su ID en el rango A2:C10, usa:\n\n` +
                           `\`\`\`excel\n=BUSCARV("A-101", A2:C10, 2, FALSO)\n\`\`\``;
                }
                return `### 💻 Ejercicio Práctico en Python / Algoritmo\n\n` +
                       `**Objetivo:** Crear un script sencillo de análisis de datos.\n\n` +
                       `\`\`\`python\n# Programa de cálculo de promedio\nnotas = [8, 9, 7, 10, 6]\npromedio = sum(notas) / len(notas)\n\nprint(f"El promedio obtenido es: {promedio:.2f}")\nif promedio >= 6:\n    print("Estado: Aprobado")\nelse:\n    print("Estado: Reprobado")\n\`\`\`\n\n` +
                       `**Instrucción:** Copia y ejecuta este código en cualquier intérprete de Python para verificar el resultado.`;
            }

            // MODO 4: EXPLICACIÓN PEDAGÓGICA (DETERMINACIÓN POR TEMAS CONOCIDOS)

            // HARDWARE: RAM, ROM, DISCOS
            if (q.includes('ram') || q.includes('rom') || q.includes('disco') || q.includes('ssd') || q.includes('hardware')) {
                return `### 🖥️ Componentes de Memoria y Almacenamiento\n\n` +
                       `| Componente | Tipo | Función Principal | ¿Es Volátil? |\n` +
                       `| --- | --- | --- | --- |\n` +
                       `| **RAM** | Memoria Operativa | Almacena datos de programas en uso actualmente | **Sí** (se borra al apagar) |\n` +
                       `| **ROM** | Memoria Lectura | Guarda las instrucciones de arranque (BIOS/UEFI) | **No** (permanente) |\n` +
                       `| **SSD / HDD** | Almacenamiento | Guarda archivos, fotos y programas permanentemente | **No** (permanente) |\n\n` +
                       `> **Consejo práctico:** Para que una computadora trabaje más rápido con múltiples aplicaciones abiertas, conviene aumentar la memoria **RAM**.`;
            }

            // EXCEL: FORMULAS Y FUNCIONES
            if (q.includes('excel') || q.includes('buscarv') || q.includes('si') || q.includes('promedio') || q.includes('hoja de calculo')) {
                return `### 📊 Funciones Fundamentales en Microsoft Excel\n\n` +
                       `1. **Función \`=SUMA(rango)\`:** Suma todos los números en un rango de celdas.\n` +
                       `2. **Función \`=PROMEDIO(rango)\`:** Obtiene la media aritmética.\n` +
                       `3. **Función \`=SI(prueba_lógica, valor_si_verdadero, valor_si_falso)\`:** Toma decisiones lógicas.\n\n` +
                       `#### Sintaxis de \`=BUSCARV\`:\n` +
                       `\`\`\`excel\n=BUSCARV(valor_buscado, tabla_matriz, indicador_columnas, [ordenado])\n\`\`\`\n` +
                       `*Ejemplo:* \`=BUSCARV("Juan", A2:C20, 3, FALSO)\` busca a "Juan" en la columna A y devuelve el valor correspondiente de la columna C.`;
            }

            // WORD Y APA
            if (q.includes('word') || q.includes('apa') || q.includes('margen') || q.includes('tabla de contenido') || q.includes('indice')) {
                return `### 📄 Formato de Documentos Oficiales (APA 7ª Edición)\n\n` +
                       `* **Márgenes:** 2.54 cm en los 4 costados (Superior, Inferior, Izquierdo, Derecho).\n` +
                       `* **Fuentes Aceptadas:** Arial 11pt, Calibri 11pt, Times New Roman 12pt o Georgia 11pt.\n` +
                       `* **Interlineado:** 2.0 (doble espacio) sin espacio adicional entre párrafos.\n\n` +
                       `#### Crear Índice Automático en Word:\n` +
                       `1. Aplica el estilo **Título 1** y **Título 2** a los encabezados de tu documento.\n` +
                       `2. Ve al menú **Referencias** > **Tabla de contenido**.\n` +
                       `3. Selecciona **Tabla automática 1**.`;
            }

            // POWERPOINT
            if (q.includes('powerpoint') || q.includes('presentacion') || q.includes('diapositiva') || q.includes('6x6')) {
                return `### 📢 Reglas para Presentaciones Efectivas en PowerPoint\n\n` +
                       `1. **Regla del 6x6:** Máximo 6 líneas de texto por diapositiva y alrededor de 6 palabras por línea.\n` +
                       `2. **Alto Contraste:** Usa fondos claros con texto oscuro (o fondos muy oscuros con texto blanco centrado).\n` +
                       `3. **Tecla de Fuego:** Presiona **F5** para iniciar la presentación desde la primera diapositiva o **Shift + F5** desde la diapositiva actual.`;
            }

            // CIBERSEGURIDAD
            if (q.includes('seguridad') || q.includes('phishing') || q.includes('virus') || q.includes('contraseña')) {
                return `### 🛡️ Principios de Ciberseguridad y Protección de Datos\n\n` +
                       `* **Contraseñas Robustas:** Usa una combinación de más de 12 caracteres con letras mayúsculas, minúsculas, números y símbolos (ej. \`P@ssw0rd_2026!\`).\n` +
                       `* **Phishing:** Desconfía de correos o mensajes que te soliciten verificar claves o datos bancarios urgente.\n` +
                       `* **Doble Factor (2FA):** Activa la autenticación en dos pasos en todas tus cuentas importantes.`;
            }

            // PROGRAMACIÓN / PYTHON
            if (q.includes('python') || q.includes('codigo') || q.includes('programacion') || q.includes('variable')) {
                return `### 🐍 Conceptos Clave de Programación con Python\n\n` +
                       `Python es un lenguaje de programación legible y potente.\n\n` +
                       `\`\`\`python\n# Variables y Tipos de Datos\nnombre = "Estudiante"\nedad = 17\npromedio = 9.5\nes_activo = True\n\n# Estructura Condicional\nif promedio >= 6.0:\n    print(f"¡Felicidades {nombre}, has aprobado!")\n\`\`\``;
            }

            // GENERAL / DEFAULT
            return `### 🎓 Tutor Educativo de Informática\n\n` +
                   `Has preguntado sobre: **"${escapeHTML(prompt)}"**.\n\n` +
                   `Puedo ofrecerte información estructurada sobre los módulos principales del programa de bachillerato:\n` +
                   `- **Word:** Formato APA, márgenes, tablas e índices.\n` +
                   `- **Excel:** Fórmulas \`=SI()\`, \`=PROMEDIO()\`, \`=BUSCARV()\`, gráficos y tablas dinámicas.\n` +
                   `- **PowerPoint:** Regla 6x6, diseño visual y atajos.\n` +
                   `- **Hardware:** Memoria RAM, ROM, unidades SSD/HDD y procesador.\n` +
                   `- **Ciberseguridad:** Prevención de Phishing, contraseñas y privacidad.\n` +
                   `- **Programación:** Algoritmos, diagramas de flujo y código en Python.`;
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
