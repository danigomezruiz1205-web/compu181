<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aprende Computación Básica - Preparatoria</title>
    <!-- Tailwind CSS desde CDN oficial -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Iconografía Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Utilidad para códigos QR -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <!-- Motor Marked para Markdown -->
    <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
    <!-- Tipografía Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        /* Estilos base escritos a mano */
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
        /* Ajustes tipográficos para el chat markdown */
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

    <!-- Barra de navegación principal -->
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
        
        <!-- Pestañas de navegación -->
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

    <!-- Contenedor general -->
    <main class="flex-grow max-w-7xl w-full mx-auto p-4 sm:p-6 lg:p-8">

        <!-- SECCIÓN: WORD -->
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

                <!-- Taller / Simulador en vivo -->
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

        <!-- SECCIÓN: EXCEL -->
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

        <!-- SECCIÓN: POWERPOINT -->
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

                <div class="grid md:grid-cols-3 gap-4 mb-6">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-palette text-orange-600"></i> Cambiar Fondo y Color de Diapositiva
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Dar formato al Fondo:</b> Haz clic derecho en una zona vacía de la diapositiva > Elige <b>Dar formato al fondo</b>.</li>
                            <li><b>Relleno Sólido o Degradado:</b> Selecciona <i>Relleno sólido</i> para aplicar un fondo azul, oscuro o blanco. O elige <i>Relleno con degradado</i> para combinar dos tonalidades de color de forma suave.</li>
                            <li><b>Aplicar a Todas:</b> Si te gusta un diseño, haz clic en <b>"Aplicar a todo"</b> para que se refleje de manera uniforme en toda la presentación escolar.</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-wand-magic text-orange-600"></i> Transiciones y Animaciones
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Efectos de Transición:</b> Ve a la pestaña <b>Transiciones</b> y selecciona efectos como <i>Desvanecer</i>, <i>Empuje</i> o <i>Cortinas</i> para el paso entre diapositivas.</li>
                            <li><b>Animar Elementos:</b> Selecciona un cuadro de texto o imagen, ve a la pestaña <b>Animaciones</b> y elige <i>Aparecer</i> o <i>Rebotar</i>.</li>
                            <li><b>Panel de Animación:</b> Controla el orden de aparición y la duración de cada elemento de forma profesional.</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-image text-orange-600"></i> Inserción Multimedia y Diseño
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Insertar Imágenes y Formas:</b> Usa la pestaña <b>Insertar</b> para agregar iconos vectoriais, formas geométricas y fotografías de alta calidad.</li>
                            <li><b>Diseño Inteligente (SmartArt):</b> Convierte listas de texto aburridas en diagramas de flujo y mapas conceptuales profesionales con un solo clic.</li>
                            <li><b>Diseñador de PowerPoint:</b> Activa la herramienta inteligente lateral para sugerencias automáticas de diseño moderno.</li>
                        </ol>
                    </div>
                </div>
            </div>
        </section>

        <!-- SECCIÓN: LIBROS Y GUÍAS -->
        <section id="content-libros" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <h2 class="text-xl font-bold text-slate-800 mb-2">Guías, Manuales y Libros de Consulta</h2>
                <p class="text-sm text-slate-500 mb-6">Recursos y documentación oficial recomendada para estudiantes de preparatoria.</p>
                <div class="grid md:grid-cols-2 gap-4">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200 flex items-start gap-3">
                        <div class="bg-amber-100 text-amber-600 p-3 rounded-xl"><i class="fa-solid fa-book text-xl"></i></div>
                        <div>
                            <h3 class="font-bold text-slate-800 text-sm">Manual Oficial de Microsoft Word 365</h3>
                            <p class="text-xs text-slate-500 mt-1">Guía completa de procesamiento de textos, maquetación avanzada y formatos de impresión académica.</p>
                        </div>
                    </div>
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200 flex items-start gap-3">
                        <div class="bg-emerald-100 text-emerald-600 p-3 rounded-xl"><i class="fa-solid fa-book text-xl"></i></div>
                        <div>
                            <h3 class="font-bold text-slate-800 text-sm">Fundamentos de Excel y Analítica de Datos</h3>
                            <p class="text-xs text-slate-500 mt-1">Aprende hojas de cálculo desde cero hasta funciones lógicas condicionales y tablas dinámicas.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- SECCIÓN: ATAJOS DE TECLADO -->
        <section id="content-atajos" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <h2 class="text-xl font-bold text-slate-800 mb-2">Atajos de Teclado Esenciales</h2>
                <p class="text-sm text-slate-500 mb-6">Acelera tu productividad diaria usando combinaciones directas del teclado.</p>
                <div class="grid sm:grid-cols-2 md:grid-cols-3 gap-3">
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200 flex justify-between items-center">
                        <span class="text-xs font-medium text-slate-700">Copiar</span>
                        <code class="px-2 py-1 bg-white border border-slate-300 rounded text-xs font-mono font-bold">Ctrl + C</code>
                    </div>
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200 flex justify-between items-center">
                        <span class="text-xs font-medium text-slate-700">Pegar</span>
                        <code class="px-2 py-1 bg-white border border-slate-300 rounded text-xs font-mono font-bold">Ctrl + V</code>
                    </div>
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200 flex justify-between items-center">
                        <span class="text-xs font-medium text-slate-700">Deshacer</span>
                        <code class="px-2 py-1 bg-white border border-slate-300 rounded text-xs font-mono font-bold">Ctrl + Z</code>
                    </div>
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200 flex justify-between items-center">
                        <span class="text-xs font-medium text-slate-700">Guardar</span>
                        <code class="px-2 py-1 bg-white border border-slate-300 rounded text-xs font-mono font-bold">Ctrl + G / S</code>
                    </div>
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200 flex justify-between items-center">
                        <span class="text-xs font-medium text-slate-700">Seleccionar Todo</span>
                        <code class="px-2 py-1 bg-white border border-slate-300 rounded text-xs font-mono font-bold">Ctrl + E</code>
                    </div>
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200 flex justify-between items-center">
                        <span class="text-xs font-medium text-slate-700">Buscar</span>
                        <code class="px-2 py-1 bg-white border border-slate-300 rounded text-xs font-mono font-bold">Ctrl + B / F</code>
                    </div>
                </div>
            </div>
        </section>

        <!-- SECCIÓN: DESAFÍO ATAJOS (JUEGO) -->
        <section id="content-juego" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm text-center">
                <h2 class="text-xl font-bold text-slate-800 mb-2">Desafío de Atajos de Teclado</h2>
                <p class="text-sm text-slate-500 mb-6">Pon a prueba tu agilidad mental emparejando funciones con sus comandos rápidos.</p>
                <div class="p-6 bg-slate-50 rounded-2xl border border-slate-200 max-w-xl mx-auto">
                    <p class="text-sm font-bold text-slate-700 mb-3" id="juego-pregunta">¿Cuál es el atajo de teclado para COPIAR texto?</p>
                    <div class="grid grid-cols-2 gap-3" id="juego-opciones">
                        <button onclick="verificarJuego(true)" class="p-3 bg-white border border-slate-300 rounded-xl font-mono text-sm font-bold hover:bg-slate-100">Ctrl + C</button>
                        <button onclick="verificarJuego(false)" class="p-3 bg-white border border-slate-300 rounded-xl font-mono text-sm font-bold hover:bg-slate-100">Ctrl + V</button>
                    </div>
                    <p id="juego-resultado" class="text-xs font-bold mt-4"></p>
                </div>
            </div>
        </section>

        <!-- SECCIÓN: QUIZ EVALUATIVO -->
        <section id="content-quiz" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <h2 class="text-xl font-bold text-slate-800 mb-2">Quiz Evaluativo de Computación Básica</h2>
                <p class="text-sm text-slate-500 mb-6">Responde las preguntas para comprobar tus conocimientos adquiridos en el curso.</p>
                <div id="quiz-container" class="space-y-4 max-w-2xl">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <p class="font-bold text-sm text-slate-800 mb-3">1. ¿Qué función de Excel se utiliza para calcular la media aritmética de un rango de celdas?</p>
                        <div class="space-y-2 text-xs">
                            <label class="flex items-center gap-2 cursor-pointer"><input type="radio" name="q1" value="a"> =SUMA(rango)</label>
                            <label class="flex items-center gap-2 cursor-pointer"><input type="radio" name="q1" value="b"> =PROMEDIO(rango)</label>
                            <label class="flex items-center gap-2 cursor-pointer"><input type="radio" name="q1" value="c"> =CONTAR(rango)</label>
                        </div>
                    </div>
                    <button onclick="calificarQuiz()" class="py-2 px-4 bg-cyan-600 hover:bg-cyan-500 text-white rounded-xl text-xs font-semibold shadow-sm transition-all">Calificar Examen</button>
                    <p id="quiz-calificacion" class="text-sm font-bold text-slate-700"></p>
                </div>
            </div>
        </section>

        <!-- SECCIÓN: TUTOR IA PRO -->
        <section id="content-ia" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col h-[500px]">
                <div class="flex items-center justify-between pb-3 border-b border-slate-200 mb-3">
                    <div class="flex items-center gap-2">
                        <div class="bg-indigo-100 text-indigo-600 p-2 rounded-lg"><i class="fa-solid fa-robot"></i></div>
                        <div>
                            <h3 class="font-bold text-sm text-slate-800">Tutor Virtual Interactivo</h3>
                            <p class="text-xs text-slate-400">Pregúntame cualquier duda sobre Word, Excel o PowerPoint</p>
                        </div>
                    </div>
                </div>
                <div id="chat-messages" class="flex-grow overflow-y-auto space-y-3 p-2 text-xs text-slate-700 bg-slate-50 rounded-xl border border-slate-200">
                    <div class="p-3 bg-white rounded-xl border border-slate-200 max-w-[80%] shadow-sm">
                        ¡Hola! Soy tu asistente de computación. ¿En qué puedo ayudarte a repasar hoy?
                    </div>
                </div>
                <div class="pt-3 flex gap-2">
                    <input type="text" id="chat-input" placeholder="Escribe tu duda aquí..." class="flex-grow p-2.5 bg-slate-50 border border-slate-300 rounded-xl text-xs focus:outline-none focus:ring-2 focus:ring-indigo-500">
                    <button onclick="enviarMensajeIA()" class="py-2.5 px-4 bg-indigo-600 hover:bg-indigo-500 text-white rounded-xl text-xs font-semibold shadow-sm transition-all">Enviar</button>
                </div>
            </div>
        </section>

        <!-- SECCIÓN: INSTALAR / APK -->
        <section id="content-descargar" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm text-center max-w-xl mx-auto">
                <div class="bg-emerald-100 text-emerald-600 w-16 h-16 rounded-2xl flex items-center justify-center mx-auto mb-4 text-2xl">
                    <i class="fa-solid fa-mobile-screen-button"></i>
                </div>
                <h2 class="text-xl font-bold text-slate-800 mb-2">Instala CompuPrep en tu Dispositivo</h2>
                <p class="text-sm text-slate-500 mb-6">Lleva esta aplicación web contigo sin necesidad de conexión permanente a internet.</p>
                <button onclick="descargarCodigoPagina()" class="py-2.5 px-6 bg-emerald-600 hover:bg-emerald-500 text-white rounded-xl text-xs font-semibold shadow-sm transition-all">
                    <i class="fa-solid fa-download mr-1"></i> Descargar Archivo HTML
                </button>
            </div>
        </section>

        <!-- SECCIÓN: CÓDIGO QR -->
        <section id="content-qr" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm text-center max-w-xl mx-auto">
                <h2 class="text-xl font-bold text-slate-800 mb-2">Comparte
