[HUHI.html](https://github.com/user-attachments/files/33892805/HUHI.html)
<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <!-- 
      CompuPrep 181 - Portal Educativo de Apoyo
      Desarrollado para la materia de Informática I y II
      Plantel Preparatoria N° 181
      Año: 2026
    -->
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
        
        /* Ajustes tipográficos manuales */
        .custom-scrollbar::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 4px;
        }
        kbd {
            border-bottom: 2px solid #94a3b8;
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
                        <p class="text-xs text-slate-400">Portal Educativo de Informática I y II</p>
                    </div>
                </div>
                <div class="hidden md:flex items-center gap-2">
                    <span class="inline-flex items-center gap-1.5 py-1 px-3 rounded-full text-xs font-medium bg-blue-500/10 text-blue-300 border border-blue-500/20">
                        <span class="w-2 h-2 rounded-full bg-blue-400"></span>
                        Ciclo Escolar 2026 - Material de Apoyo
                    </span>
                    <button onclick="descargarCodigoPagina()" class="py-1 px-3 rounded-xl text-xs font-semibold bg-blue-600 hover:bg-blue-500 text-white transition-all flex items-center gap-1.5 shadow-sm">
                        <i class="fa-solid fa-download"></i> Guardar Copia Offline
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
                    <i class="fa-solid fa-book-bookmark text-amber-400"></i> Lecturas y Enlaces
                </button>
                <button onclick="changeTab('atajos')" id="tab-atajos" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-keyboard text-purple-400"></i> Atajos
                </button>
                <button onclick="changeTab('juego')" id="tab-juego" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-gamepad text-pink-400"></i> Práctica Visual
                </button>
                <button onclick="changeTab('quiz')" id="tab-quiz" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-graduation-cap text-cyan-400"></i> Autoevaluación
                </button>
                <button onclick="changeTab('ia')" id="tab-ia" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-comments text-indigo-400"></i> Consultas al Prof. Juan
                </button>
                <button onclick="changeTab('descargar')" id="tab-descargar" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-mobile-screen-button text-emerald-400"></i> Guardar App
                </button>
                <button onclick="changeTab('qr')" id="tab-qr" class="tab-btn px-4 py-2 rounded-lg text-sm font-semibold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-700">
                    <i class="fa-solid fa-qrcode text-rose-400"></i> Compartir QR
                </button>
            </div>
        </nav>
    </header>

    <!-- Contenido Principal -->
    <main class="flex-grow max-w-7xl w-full mx-auto p-4 sm:p-6 lg:p-8">

        <!-- PESTAÑA: WORD -->
        <section id="content-word" class="tab-content block space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <!-- Nota estilo aviso del docente -->
                <div class="mb-6 p-4 rounded-xl bg-amber-50 border-l-4 border-amber-400 text-slate-700 text-xs">
                    <p class="font-bold mb-1 text-amber-900"><i class="fa-solid fa-circle-info mr-1"></i> Indicaciones del Laboratorio (Prof. Juan):</p>
                    <p>Jóvenes: para la entrega del reporte final de este parcial, la carátula y el formato de bibliografía deben seguir obligatoriamente las especificaciones de la norma APA mostradas abajo. Eviten entregar archivos con formato libre o fuentes no autorizadas.</p>
                </div>

                <div class="flex items-center gap-3 mb-4">
                    <div class="bg-blue-100 text-blue-600 p-3 rounded-xl">
                        <i class="fa-solid fa-file-word text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl font-bold text-slate-800">Microsoft Word: Guía Práctica de Elaboración de Documentos</h2>
                        <p class="text-sm text-slate-500">Pasos recomendados para la edición y entrega de trabajos escolares en el plantel</p>
                    </div>
                </div>

                <!-- Guía Rápida Visual: Edición de Texto y Fuentes -->
                <div class="grid md:grid-cols-3 gap-4 mb-6">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-font text-blue-600"></i> Edición de Letra y Estilo
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Seleccionar Texto:</b> Haz clic e ilumina el párrafo con el ratón (o usa <kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl + E</kbd> para marcar todo el texto).</li>
                            <li><b>Selección de Fuente:</b> En la pestaña <b>Inicio</b>, ajusta el tipo de letra a <i>Arial</i> o <i>Times New Roman</i> según las indicaciones del docente.</li>
                            <li><b>Colores de Resaltado:</b> Utiliza el icono <b class="text-blue-600 font-bold">A</b> con la barra inferior para títulos principales y la herramienta de resaltado para referencias clave.</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-align-left text-blue-600"></i> Formato de Párrafo e Interlineado
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Alineación:</b> Utiliza <b>Justificado (<kbd class="px-1 bg-slate-200 rounded font-mono">Ctrl + J</kbd>)</b> en el cuerpo de tus ensayos para mantener los márgenes rectos.</li>
                            <li><b>Interlineado:</b> Ajusta el espacio a 1.5 o 2.0 (Doble) desde el menú <i>Párrafo</i> en la cinta superior.</li>
                            <li><b>Sangría:</b> Presiona la tecla <kbd class="px-1 bg-slate-200 rounded font-mono">Tab</kbd> al inicio de cada nuevo párrafo para aplicar la sangría estándar.</li>
                        </ol>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-wand-magic-sparkles text-blue-600"></i> Índice Automático
                        </h3>
                        <ol class="text-xs text-slate-600 space-y-2 list-decimal list-inside">
                            <li><b>Marcar Encabezados:</b> Asigna el estilo <b>Título 1</b> a los temas principales y <b>Título 2</b> a los subtítulos.</li>
                            <li><b>Insertar Tabla:</b> Colócate en una página en blanco al principio y dirígete a <b>Referencias > Tabla de contenido</b>.</li>
                            <li><b>Actualización:</b> Haz clic derecho sobre el índice generado y selecciona "Actualizar campos" si modificas la cantidad de páginas.</li>
                        </ol>
                    </div>
                </div>

                <!-- Simulador / Previsualizador Interactivo de Texto -->
                <div class="bg-slate-50 p-5 rounded-2xl border border-slate-200">
                    <h3 class="font-bold text-slate-800 mb-2 flex items-center gap-2">
                        <i class="fa-solid fa-eye text-blue-600"></i> Taller de Prueba: Vista Previa de Formato
                    </h3>
                    <p class="text-xs text-slate-600 mb-4">Utiliza los siguientes controles para verificar visualmente los cambios antes de imprimir o enviar tus tareas:</p>
                    
                    <div class="grid md:grid-cols-4 gap-3 mb-4 bg-white p-3 rounded-xl border border-slate-200">
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Color de Fuente</label>
                            <input type="color" id="demo-text-color" value="#1e293b" onchange="actualizarDemoWord()" class="w-full h-9 p-1 bg-white border border-slate-300 rounded-lg cursor-pointer">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Tipografía</label>
                            <select id="demo-text-font" onchange="actualizarDemoWord()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium">
                                <option value="Arial, sans-serif">Arial</option>
                                <option value="Times New Roman, serif">Times New Roman</option>
                                <option value="Inter, sans-serif">Inter</option>
                                <option value="Courier New, monospace">Courier New</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Tamaño</label>
                            <select id="demo-text-size" onchange="actualizarDemoWord()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium">
                                <option value="14px">14 px (Notas / Pie de página)</option>
                                <option value="16px" selected>16 px (Texto base / Parrafos)</option>
                                <option value="20px">20 px (Subtítulos)</option>
                                <option value="24px">24 px (Título principal)</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-600 mb-1">Alineación</label>
                            <select id="demo-text-align" onchange="actualizarDemoWord()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium">
                                <option value="left">Izquierda</option>
                                <option value="justify" selected>Justificado</option>
                                <option value="center">Centrado</option>
                                <option value="right">Derecha</option>
                            </select>
                        </div>
                    </div>

                    <!-- Vista Previa de la Hoja -->
                    <div id="word-preview-box" class="p-6 bg-white border border-slate-300 rounded-xl shadow-inner min-h-[120px] transition-all">
                        <h4 id="demo-preview-title" class="font-bold mb-2">Introducción a la Informática Educativa</h4>
                        <p id="demo-preview-p" class="leading-relaxed">
                            Este espacio sirve para revisar la legibilidad de tus redacciones. Asegúrate de mantener una jerarquía clara en los títulos y un tamaño adecuado en la tipografía para facilitar la revisión del examen o proyecto.
                        </p>
                    </div>
                </div>

                <div class="grid md:grid-cols-2 gap-6 pt-2">
                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
                        <h3 class="font-semibold text-slate-700 mb-2"><i class="fa-solid fa-check-circle text-blue-500 mr-2"></i>Criterios de Formato APA (Entregables)</h3>
                        <ul class="text-sm text-slate-600 space-y-2 list-disc list-inside">
                            <li><b>Márgenes:</b> Establecer 2.54 cm en los cuatro bordes (Izquierdo, Derecho, Superior, Inferior).</li>
                            <li><b>Numeración:</b> Esquina superior derecha de cada hoja en números arábigos.</li>
                            <li><b>Interlineado:</b> 2.0 (Doble espacio) sin agregar renglones extra entre párrafos.</li>
                            <li><b>Encabezados:</b> Nivel 1 en negrita y centrado; Nivel 2 alineado a la izquierda.</li>
                        </ul>
                    </div>
                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
                        <h3 class="font-semibold text-slate-700 mb-2"><i class="fa-solid fa-list-ol text-blue-500 mr-2"></i>Recomendaciones del Docente</h3>
                        <ol class="text-sm text-slate-600 space-y-2 list-decimal list-inside">
                            <li>Guarda tu archivo con tu nombre y grupo (ejemplo: <i>Perez_Juan_3B_Practica1.docx</i>).</li>
                            <li>Utiliza el corrector ortográfico antes de imprimir (<kbd class="px-1 bg-slate-200 rounded font-mono">F7</kbd> en Word).</li>
                            <li>Exporta a formato PDF si vas a subir tu trabajo a la plataforma escolar para evitar que se desacomoden las imágenes.</li>
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

        <!-- PESTAÑA: ASISTENTE EDUCATIVO E INTERACTIVO -->
        <section id="content-ia" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                
                <!-- Cabecera del Asesor -->
                <div class="flex items-center justify-between gap-4 mb-4 pb-4 border-b border-slate-100 flex-wrap">
                    <div class="flex items-center gap-3">
                        <div class="bg-indigo-600 text-white p-3 rounded-xl shadow-sm">
                            <i class="fa-solid fa-chalkboard-user text-2xl"></i>
                        </div>
                        <div>
                            <h2 class="text-xl font-bold text-slate-800">Dudas de Clase y Asesoría con el Prof. Juan</h2>
                            <p class="text-sm text-slate-500">Haz tus preguntas sobre los temas vistos en el laboratorio o pide ejemplos resueltos</p>
                        </div>
                    </div>
                    <div class="flex items-center gap-2">
                        <button onclick="limpiarHistorialChat()" title="Borrar conversación" class="px-3 py-1.5 text-xs bg-slate-100 hover:bg-slate-200 text-slate-600 rounded-lg font-medium transition-all flex items-center gap-1">
                            <i class="fa-solid fa-trash-can"></i> Reiniciar Chat
                        </button>
                        <span class="text-xs bg-emerald-50 text-emerald-700 font-bold px-3 py-1.5 rounded-full border border-emerald-200 flex items-center gap-1">
                            <span class="w-2 h-2 rounded-full bg-emerald-500"></span>
                            Asesoría Disponible
                        </span>
                    </div>
                </div>

                <!-- Selector de Roles / Modos de Trabajo -->
                <div class="mb-4 bg-slate-50 p-3 rounded-xl border border-slate-200">
                    <span class="text-xs font-bold text-slate-600 block mb-2"><i class="fa-solid fa-sliders text-indigo-600 mr-1"></i> ¿Qué necesitas realizar?</span>
                    <div class="flex flex-wrap gap-2" id="ai-mode-container">
                        <button onclick="setAIMode('explicar', this)" class="mode-btn active px-3 py-1.5 rounded-lg text-xs font-bold bg-indigo-600 text-white transition-all flex items-center gap-1">
                            <i class="fa-solid fa-chalkboard-user"></i> Explicación Sencilla
                        </button>
                        <button onclick="setAIMode('ejercicio', this)" class="mode-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-white border border-slate-300 text-slate-700 hover:bg-slate-100 transition-all flex items-center gap-1">
                            <i class="fa-solid fa-code"></i> Ejemplo de Ejercicio
                        </button>
                        <button onclick="setAIMode('evaluar', this)" class="mode-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-white border border-slate-300 text-slate-700 hover:bg-slate-100 transition-all flex items-center gap-1">
                            <i class="fa-solid fa-file-signature"></i> Revisión de Párrafo / Texto
                        </button>
                        <button onclick="setAIMode('quiz_generador', this)" class="mode-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-white border border-slate-300 text-slate-700 hover:bg-slate-100 transition-all flex items-center gap-1">
                            <i class="fa-solid fa-circle-question"></i> Preguntas para Estudiar
                        </button>
                    </div>
                </div>

                <!-- Sugerencias Temáticas Avanzadas -->
                <div class="mb-4">
                    <p class="text-xs font-semibold text-slate-500 mb-2">Consultas habituales de los alumnos:</p>
                    <div class="flex flex-wrap gap-2">
                        <button onclick="usarSugerencia('¿Cuál es la diferencia entre memoria RAM y el Disco Duro?')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            📊 RAM vs Disco Duro
                        </button>
                        <button onclick="usarSugerencia('¿Cómo aplico la fórmula PROMEDIO y la función SI en mi lista de calificaciones?')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            📈 Promedios en Excel
                        </button>
                        <button onclick="usarSugerencia('Dame un ejemplo básico de condicionales en Python')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            🐍 Ejercicio en Python
                        </button>
                        <button onclick="usarSugerencia('¿Cómo identificar correos falsos o de Phishing?')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            🛡️ Identificar Phishing
                        </button>
                        <button onclick="usarSugerencia('¿Cuáles son las reglas básicas de formato APA 7 para mi entrega?')" class="px-3 py-1.5 bg-slate-100 hover:bg-indigo-50 hover:text-indigo-600 text-slate-600 rounded-lg text-xs font-medium transition-all">
                            📄 Reglas Formato APA 7
                        </button>
                    </div>
                </div>

                <!-- Ventana del Chat -->
                <div id="ai-chat-history" class="h-[420px] overflow-y-auto custom-scrollbar bg-slate-50 border border-slate-200 rounded-2xl p-4 space-y-4 mb-4">
                    <div class="flex gap-3 items-start">
                        <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold">
                            <i class="fa-solid fa-user-tie text-xs"></i>
                        </div>
                        <div class="bg-white border border-slate-200 rounded-2xl p-4 shadow-sm max-w-[85%] text-slate-700 leading-relaxed text-sm ai-formatted-content">
                            ¡Qué tal jóvenes! Bienvenidos al espacio de asesoría de Informática. <br>
                            Escriban aquí cualquier duda concreta sobre sus prácticas de laboratorio, problemas con fórmulas de Excel o formato de sus entregas en Word.
                            <ul class="mt-2 space-y-1 list-disc list-inside text-xs text-slate-600">
                                <li>Revisen la pestaña de atajos si tienen dudas sobre teclas rápidas.</li>
                                <li>Pueden pedirme ejemplos sencillos de lógica de programación o aclaraciones sobre el examen.</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <!-- Campo de Entrada -->
                <form onsubmit="enviarPreguntaIA(event)" class="flex gap-2">
                    <input type="text" id="ai-input" placeholder="Escribe aquí tu duda sobre las prácticas..." class="flex-grow p-3 bg-slate-50 border border-slate-300 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500">
                    <button type="submit" id="ai-send-btn" class="px-5 py-3 bg-indigo-600 hover:bg-indigo-700 text-white font-bold rounded-xl shadow-sm transition-all flex items-center gap-2 text-sm shrink-0">
                        <span>Preguntar</span>
                        <i class="fa-solid fa-paper-plane"></i>
                    </button>
                </form>
            </div>
        </section>

        <!-- PESTAÑA: CÓDIGO QR -->
        <section id="content-qr" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm max-w-lg mx-auto text-center">
                <div class="inline-flex bg-rose-100 text-rose-600 p-4 rounded-2xl mb-3">
                    <i class="fa-solid fa-qrcode text-3xl"></i>
                </div>
                <h2 class="text-xl font-bold text-slate-800 mb-1">Compartir este Portal con tus Compañeros</h2>
                <p class="text-xs text-slate-500 mb-6">Escanea el código QR desde la cámara de tu teléfono para acceder rápidamente al material de apoyo y simuladores.</p>

                <div class="flex justify-center mb-4">
                    <div id="qrcode-container" class="p-4 bg-white border-2 border-slate-200 rounded-2xl shadow-sm inline-block"></div>
                </div>

                <p class="text-xs text-slate-400 font-mono break-all px-4" id="qr-url-text"></p>
            </div>
        </section>

        <!-- PESTAÑA: DESCARGAR APP / PWA -->
        <section id="content-descargar" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm max-w-xl mx-auto text-center">
                <div class="inline-flex bg-emerald-100 text-emerald-600 p-4 rounded-2xl mb-3">
                    <i class="fa-solid fa-mobile-screen-button text-3xl"></i>
                </div>
                <h2 class="text-xl font-bold text-slate-800 mb-1">Guarda el Portal en tu Teléfono o Computadora</h2>
                <p class="text-xs text-slate-500 mb-6">Puedes utilizar este material incluso cuando no tengas conexión a internet en la escuela.</p>

                <div class="grid sm:grid-cols-2 gap-4 mb-6 text-left">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-xs mb-2 flex items-center gap-1.5">
                            <i class="fa-brands fa-android text-emerald-600 text-sm"></i> En Android / Chrome
                        </h3>
                        <p class="text-xs text-slate-600 leading-relaxed">Presiona los 3 puntos superiores de tu navegador y elige <b>"Agregar a la pantalla principal"</b>.</p>
                    </div>
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h3 class="font-bold text-slate-800 text-xs mb-2 flex items-center gap-1.5">
                            <i class="fa-brands fa-apple text-slate-800 text-sm"></i> En iPhone / Safari
                        </h3>
                        <p class="text-xs text-slate-600 leading-relaxed">Toca el botón <b>Compartir</b> (el cuadro con una flecha hacia arriba) y selecciona <b>"Agregar a inicio"</b>.</p>
                    </div>
                </div>

                <button onclick="instalarPWA()" class="px-6 py-3 bg-emerald-600 hover:bg-emerald-700 text-white font-bold text-sm rounded-xl shadow-sm transition-all inline-flex items-center gap-2">
                    <i class="fa-solid fa-download"></i> Instrucciones de Instalación
                </button>
            </div>
        </section>

    </main>

    <!-- Pie de página -->
    <footer class="bg-slate-900 text-slate-400 py-6 border-t border-slate-800 mt-auto">
        <div class="max-w-7xl mx-auto px-4 text-center text-xs space-y-2">
            <p class="font-medium text-slate-300">CompuPrep 181 — Material Educativo de Apoyo para Informática I y II</p>
            <p class="text-slate-500">Diseñado para facilitar la práctica en laboratorio y la preparación de evaluaciones escolares.</p>
        </div>
    </footer>

    <!-- Modal personalizado para notificaciones -->
    <div id="custom-modal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-sm z-50 flex items-center justify-center hidden">
        <div class="bg-white rounded-2xl p-6 max-w-sm w-full mx-4 shadow-xl border border-slate-200">
            <div class="text-center">
                <div class="w-12 h-12 rounded-full bg-blue-100 text-blue-600 flex items-center justify-center mx-auto mb-3">
                    <i class="fa-solid fa-circle-info text-xl"></i>
                </div>
                <h3 class="text-lg font-bold text-slate-800 mb-2" id="modal-title">Aviso</h3>
                <p class="text-sm text-slate-600 mb-6" id="modal-message"></p>
                <button onclick="cerrarModalCustom()" class="w-full py-2.5 bg-slate-800 hover:bg-slate-900 text-white font-bold rounded-xl text-sm transition-all">
                    Entendido
                </button>
            </div>
        </div>
    </div>

    <!-- LÓGICA JAVASCRIPT COMPLETA Y REVISADA -->
    <script>
        // MODO ACTUAL DE ASESORÍA
        let aiCurrentMode = 'explicar';

        // FUNCION DE ESCAPE DE HTML
        function escapeHTML(str) {
            if (!str) return '';
            return String(str).replace(/[&<>'"]/g, 
                tag => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', "'": '&#39;', '"': '&quot;' }[tag] || tag)
            );
        }

        // NAVEGACIÓN ENTRE PESTAÑAS
        window.changeTab = function(tabName) {
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(c => c.classList.add('hidden'));

            const selectedContent = document.getElementById('content-' + tabName);
            if (selectedContent) {
                selectedContent.classList.remove('hidden');
            }

            const buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(b => b.classList.remove('active'));

            const activeBtn = document.getElementById('tab-' + tabName);
            if (activeBtn) {
                activeBtn.classList.add('active');
            }

            if (tabName === 'qr') {
                generarCodigoQR();
            }
        };

        // SISTEMA DE MODAL PERSONALIZADO
        window.mostrarModalCustom = function(titulo, mensaje) {
            const modal = document.getElementById('custom-modal');
            const titleElem = document.getElementById('modal-title');
            const msgElem = document.getElementById('modal-message');
            if (modal && titleElem && msgElem) {
                titleElem.textContent = titulo;
                msgElem.textContent = mensaje;
                modal.classList.remove('hidden');
            }
        };

        window.cerrarModalCustom = function() {
            const modal = document.getElementById('custom-modal');
            if (modal) modal.classList.add('hidden');
        };

        window.instalarPWA = function() {
            mostrarModalCustom(
                "Instalación en Teléfonos Móviles",
                "Para guardar el portal en tu pantalla de inicio: Presiona el menú de 3 puntos en la esquina superior derecha de Chrome y selecciona 'Agregar a la pantalla principal'."
            );
        };

        // SIMULADOR DE FORMATO DE WORD
        window.actualizarDemoWord = function() {
            const color = document.getElementById('demo-text-color')?.value || '#1e293b';
            const font = document.getElementById('demo-text-font')?.value || 'Arial, sans-serif';
            const size = document.getElementById('demo-text-size')?.value || '16px';
            const align = document.getElementById('demo-text-align')?.value || 'justify';

            const previewBox = document.getElementById('word-preview-box');
            if (previewBox) {
                previewBox.style.color = color;
                previewBox.style.fontFamily = font;
                previewBox.style.fontSize = size;
                previewBox.style.textAlign = align;
            }
        };

        // SIMULADOR DE PROMEDIO EN EXCEL
        window.calcularPromedio = function() {
            const c1 = parseFloat(document.getElementById('calif1')?.value) || 0;
            const c2 = parseFloat(document.getElementById('calif2')?.value) || 0;
            const c3 = parseFloat(document.getElementById('calif3')?.value) || 0;

            const promedio = (c1 + c2 + c3) / 3;
            const resProm = document.getElementById('res-promedio');
            const resEst = document.getElementById('res-estatus');

            if (resProm) resProm.textContent = promedio.toFixed(2);
            if (resEst) {
                if (promedio >= 6.0) {
                    resEst.textContent = "APROBADO";
                    resEst.className = "px-3 py-1 rounded-full text-xs font-bold bg-emerald-100 text-emerald-700";
                } else {
                    resEst.textContent = "REPROBADO";
                    resEst.className = "px-3 py-1 rounded-full text-xs font-bold bg-rose-100 text-rose-700";
                }
            }
        };

        // ATAJOS DE TECLADO
        const listaAtajos = [
            { tecla: "Ctrl + C", funcion: "Copiar el texto o elemento seleccionado", programa: "Universal" },
            { tecla: "Ctrl + V", funcion: "Pegar el elemento copiado", programa: "Universal" },
            { tecla: "Ctrl + X", funcion: "Cortar el texto o elemento", programa: "Universal" },
            { tecla: "Ctrl + Z", funcion: "Deshacer la última acción", programa: "Universal" },
            { tecla: "Ctrl + Y", funcion: "Rehacer la última acción cancelada", programa: "Universal" },
            { tecla: "Ctrl + G", funcion: "Guardar el documento o libro actual", programa: "Office (Español)" },
            { tecla: "Ctrl + S", funcion: "Guardar rápido", programa: "Programación / Inglés" },
            { tecla: "Ctrl + E", funcion: "Seleccionar todo el texto o celdas", programa: "Windows / Word" },
            { tecla: "Ctrl + P", funcion: "Abrir menú de Impresión", programa: "Universal" },
            { tecla: "Ctrl + F / Ctrl + B", funcion: "Buscar palabras clave", programa: "Navegadores / Word" },
            { tecla: "Ctrl + N", funcion: "Aplicar formato de Negrita a la letra", programa: "Word / Excel" },
            { tecla: "Ctrl + K", funcion: "Aplicar formato Cursiva", programa: "Word / Excel" },
            { tecla: "Ctrl + S", funcion: "Subrayar texto", programa: "Word" },
            { tecla: "F5", funcion: "Iniciar presentación desde el principio", programa: "PowerPoint" },
            { tecla: "Shift + F5", funcion: "Iniciar presentación desde la diapositiva actual", programa: "PowerPoint" },
            { tecla: "Alt + Tab", funcion: "Alternar rápidamente entre ventanas abiertas", programa: "Windows" },
            { tecla: "Tecla Windows + D", funcion: "Mostrar u ocultar el escritorio", programa: "Windows" }
        ];

        window.renderizarAtajos = function(datos) {
            const tbody = document.getElementById('shortcuts-table-body');
            if (!tbody) return;
            tbody.innerHTML = '';

            datos.forEach(item => {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50 transition-colors border-b border-slate-100";
                tr.innerHTML = `
                    <td class="p-3"><kbd class="px-2 py-1 bg-slate-200 text-slate-800 rounded text-xs font-mono font-semibold shadow-sm">${escapeHTML(item.tecla)}</kbd></td>
                    <td class="p-3 text-slate-700">${escapeHTML(item.funcion)}</td>
                    <td class="p-3"><span class="px-2 py-1 bg-purple-50 text-purple-700 text-xs font-medium rounded-full border border-purple-100">${escapeHTML(item.programa)}</span></td>
                `;
                tbody.appendChild(tr);
            });
        };

        window.filtrarAtajos = function() {
            const query = document.getElementById('shortcut-search')?.value.toLowerCase() || '';
            const filtrados = listaAtajos.filter(a => 
                a.tecla.toLowerCase().includes(query) || 
                a.funcion.toLowerCase().includes(query) || 
                a.programa.toLowerCase().includes(query)
            );
            renderizarAtajos(filtrados);
        };

        // MINIJUÉGO DE VELOCIDAD
        const preguntasJuego = [
            { q: "¿Qué atajo usas para copiar un texto seleccionado?", options: ["Ctrl + C", "Ctrl + V", "Ctrl + X", "Ctrl + Z"], correct: 0 },
            { q: "¿Con qué combinación de teclas pegas el contenido del portapapeles?", options: ["Ctrl + P", "Ctrl + V", "Ctrl + G", "Alt + Tab"], correct: 1 },
            { q: "Si cometes un error escribiendo en Word, ¿cómo lo deshaces rápidamente?", options: ["Ctrl + Y", "Ctrl + E", "Ctrl + Z", "Ctrl + N"], correct: 2 },
            { q: "¿Cómo guardas inmediatamente tu trabajo en Office en español?", options: ["Ctrl + G", "Ctrl + S", "Ctrl + P", "Ctrl + A"], correct: 0 },
            { q: "¿Con qué tecla inicias la proyección a pantalla completa en PowerPoint?", options: ["F1", "F5", "Esc", "Enter"], correct: 1 }
        ];

        let juegoIndice = 0;
        let juegoPuntos = 0;
        let juegoTiempo = 10;
        let juegoTimerInterval = null;

        window.iniciarMinijuego = function() {
            juegoIndice = 0;
            juegoPuntos = 0;
            
            const gameCard = document.getElementById('game-card');
            if (gameCard) {
                gameCard.innerHTML = `
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-xs font-bold text-slate-500" id="game-progress">Pregunta 1 de 5</span>
                        <span class="text-xs font-bold bg-amber-100 text-amber-800 px-3 py-1 rounded-full" id="game-timer"><i class="fa-regular fa-clock mr-1"></i>10s</span>
                    </div>
                    <h3 class="text-lg font-bold text-slate-800 mb-4" id="game-question"></h3>
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 mb-4" id="game-options"></div>
                    <div id="game-feedback" class="min-h-[2.5rem] flex items-center justify-center text-sm font-bold text-center"></div>
                `;
            }
            
            cargarPreguntaJuego();
        };

        function cargarPreguntaJuego() {
            if (juegoTimerInterval) clearInterval(juegoTimerInterval);

            if (juegoIndice >= preguntasJuego.length) {
                const card = document.getElementById('game-card');
                if (card) {
                    card.innerHTML = `
                        <div class="text-center py-4">
                            <i class="fa-solid fa-trophy text-4xl text-amber-400 mb-2"></i>
                            <h3 class="text-xl font-bold text-slate-800 mb-1">¡Juego Completado!</h3>
                            <p class="text-sm text-slate-600">Obtuviste <b>${juegoPuntos}</b> de <b>${preguntasJuego.length}</b> respuestas correctas.</p>
                        </div>
                    `;
                }
                return;
            }

            const qActual = preguntasJuego[juegoIndice];
            const progElem = document.getElementById('game-progress');
            const questElem = document.getElementById('game-question');
            const optsElem = document.getElementById('game-options');
            const feedElem = document.getElementById('game-feedback');

            if (progElem) progElem.textContent = `Pregunta ${juegoIndice + 1} de ${preguntasJuego.length}`;
            if (questElem) questElem.textContent = qActual.q;
            if (feedElem) feedElem.textContent = '';

            if (optsElem) {
                optsElem.innerHTML = '';
                qActual.options.forEach((opt, idx) => {
                    const btn = document.createElement('button');
                    btn.className = "p-3 bg-white hover:bg-purple-50 border border-slate-200 rounded-xl font-semibold text-slate-700 text-sm transition-all text-left flex items-center justify-between";
                    btn.innerHTML = `<span>${escapeHTML(opt)}</span> <i class="fa-regular fa-circle text-slate-300"></i>`;
                    btn.onclick = () => responderJuego(idx);
                    optsElem.appendChild(btn);
                });
            }

            juegoTiempo = 10;
            actualizarTimerUI();
            juegoTimerInterval = setInterval(() => {
                juegoTiempo--;
                actualizarTimerUI();
                if (juegoTiempo <= 0) {
                    clearInterval(juegoTimerInterval);
                    responderJuego(-1);
                }
            }, 1000);
        }

        function actualizarTimerUI() {
            const timerElem = document.getElementById('game-timer');
            if (timerElem) {
                timerElem.innerHTML = `<i class="fa-regular fa-clock mr-1"></i>${juegoTiempo}s`;
            }
        }

        function responderJuego(opcionSel) {
            if (juegoTimerInterval) clearInterval(juegoTimerInterval);
            const qActual = preguntasJuego[juegoIndice];
            const feedElem = document.getElementById('game-feedback');

            if (opcionSel === qActual.correct) {
                juegoPuntos++;
                if (feedElem) {
                    feedElem.textContent = "¡Bien hecho! Respuesta correcta.";
                    feedElem.className = "min-h-[2.5rem] flex items-center justify-center text-sm font-bold text-emerald-600";
                }
            } else {
                if (feedElem) {
                    feedElem.textContent = `Opcional no acertada. La respuesta es: ${qActual.options[qActual.correct]}`;
                    feedElem.className = "min-h-[2.5rem] flex items-center justify-center text-sm font-bold text-rose-600";
                }
            }

            setTimeout(() => {
                juegoIndice++;
                cargarPreguntaJuego();
            }, 1400);
        }

        // QUIZ EVALUATIVO
        const preguntasQuiz = [
            { title: "1. En Microsoft Word, ¿cuál es el margen predeterminado exigido en formato APA 7ª Edición?", options: ["1.5 cm en todos los bordes", "2.54 cm (1 pulgada) en los 4 bordes", "3.0 cm lateral y 2.0 cm vertical", "Sin márgenes"], correct: 1 },
            { title: "2. ¿Qué función de Excel se utiliza para calcular la suma de una columna entera?", options: ["=TOTAL()", "=SUMAR.CELDAS()", "=SUMA()", "=CALCULAR.SUMA()"], correct: 2 },
            { title: "3. En Excel, ¿qué devuelve la fórmula =SI(8 >= 6, 'Aprobado', 'Reprobado')?", options: ["8", "6", "Reprobado", "Aprobado"], correct: 3 },
            { title: "4. ¿Qué regla de diseño visual se recomienda para no saturar las diapositivas en PowerPoint?", options: ["Regla del 6x6 (máx. 6 líneas con 6 palabras)", "Poner más de 50 palabras por página", "Usar fondos amarillos con letras blancas", "No poner títulos"], correct: 0 },
            { title: "5. ¿Cuál es la principal característica de la memoria RAM en una computadora?", options: ["Es de solo lectura y no se borra jamás", "Es una memoria volátil donde se ejecutan los programas activos", "Almacena archivos en el disco duro", "Sirve para imprimir documentos"], correct: 1 },
            { title: "6. ¿Cuál de los siguientes es un ejemplo de intento de estafa por correo o mensaje engañoso?", options: ["Phishing", "Hardware", "Hoja de Cálculo", "Formato APA"], correct: 0 },
            { title: "7. Para guardar un trabajo rápidamente en la suite de Office en español se presiona:", options: ["Alt + F4", "Ctrl + G", "Shift + Enter", "Ctrl + Alt + Supr"], correct: 1 },
            { title: "8. ¿Qué tipo de software es Python?", options: ["Un navegador de internet", "Un sistema operativo", "Un lenguaje de programación", "Un editor de video"], correct: 2 },
            { title: "9. ¿Qué extensión suele tener un archivo compilado de documento Web?", options: [".docx", ".xlsx", ".html", ".mp3"], correct: 2 },
            { title: "10. En PowerPoint, la transición que permite mover suavemente objetos duplicados entre diapositivas se llama:", options: ["Transformación (Morph)", "Barrido", "Disolver", "Empuje"], correct: 0 }
        ];

        window.cargarQuiz = function() {
            const container = document.getElementById('quiz-container');
            if (!container) return;
            container.innerHTML = '';

            preguntasQuiz.forEach((q, qIndex) => {
                const div = document.createElement('div');
                div.className = "p-4 bg-slate-50 border border-slate-200 rounded-xl space-y-2";
                
                let optsHTML = '';
                q.options.forEach((opt, optIndex) => {
                    optsHTML += `
                        <label class="flex items-center gap-2 p-2 bg-white rounded-lg border border-slate-200 cursor-pointer hover:bg-blue-50/50 text-sm">
                            <input type="radio" name="quiz_q_${qIndex}" value="${optIndex}" class="text-blue-600 focus:ring-blue-500">
                            <span class="text-slate-700">${escapeHTML(opt)}</span>
                        </label>
                    `;
                });

                div.innerHTML = `
                    <h4 class="font-bold text-slate-800 text-sm">${escapeHTML(q.title)}</h4>
                    <div class="grid sm:grid-cols-2 gap-2 pt-1">${optsHTML}</div>
                `;
                container.appendChild(div);
            });
        };

        window.evaluarQuiz = function(event) {
            event.preventDefault();
            let calificacion = 0;

            preguntasQuiz.forEach((q, qIndex) => {
                const selected = document.querySelector(`input[name="quiz_q_${qIndex}"]:checked`);
                if (selected && parseInt(selected.value) === q.correct) {
                    calificacion++;
                }
            });

            const resDiv = document.getElementById('quiz-result');
            if (resDiv) {
                const porcentaje = (calificacion / preguntasQuiz.length) * 10;
                resDiv.innerHTML = `Resultado: <span class="text-blue-600 font-extrabold">${calificacion} / ${preguntasQuiz.length}</span> (${porcentaje.toFixed(1)} / 10)`;
            }
        };

        // ASESOR DOCENTE - RESPUESTAS HUMANIZADAS Y NATURALES
        window.setAIMode = function(modo, btnElement) {
            aiCurrentMode = modo;
            const buttons = document.querySelectorAll('#ai-mode-container button');
            buttons.forEach(b => {
                b.className = "mode-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-white border border-slate-300 text-slate-700 hover:bg-slate-100 transition-all flex items-center gap-1";
            });
            if (btnElement) {
                btnElement.className = "mode-btn active px-3 py-1.5 rounded-lg text-xs font-bold bg-indigo-600 text-white transition-all flex items-center gap-1";
            }
        };

        window.usarSugerencia = function(texto) {
            const input = document.getElementById('ai-input');
            if (input) {
                input.value = texto;
                document.querySelector('#content-ia form')?.dispatchEvent(new Event('submit', { cancelable: true }));
            }
        };

        window.limpiarHistorialChat = function() {
            const history = document.getElementById('ai-chat-history');
            if (history) {
                history.innerHTML = `
                    <div class="flex gap-3 items-start">
                        <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold">
                            <i class="fa-solid fa-graduation-cap text-xs"></i>
                        </div>
                        <div class="bg-white border border-slate-200 rounded-2xl p-4 shadow-sm max-w-[85%] text-slate-700 leading-relaxed text-sm ai-formatted-content">
                            Listo, he reiniciado la conversación. ¿Qué otra duda tienes sobre las prácticas?
                        </div>
                    </div>
                `;
            }
        };

        function generarRespuestaProfesorHumanizada(prompt, modo) {
            const q = prompt.toLowerCase();

            if (modo === 'evaluar') {
                return `Hola. Estuve revisando lo que escribiste ("${escapeHTML(prompt)}").\n\n` +
                       `En general vas bien encaminado. Tu idea principal se entiende perfectamente, aunque te sugiero organizar el texto en párrafos de no más de 4 o 5 renglones para que no se sienta tan pesado de leer al momento de la entrega.\n\n` +
                       `No olvides verificar la alineación justificada en Word antes de mandar tu archivo y asegurarte de aplicar sangría en la primera línea. Con esos detalles te queda listo.`;
            }

            if (modo === 'quiz_generador') {
                return `Aquí tienes un par de preguntas rápidas sobre **${escapeHTML(prompt)}** para que ensayes antes del examen:\n\n` +
                       `**1.** ¿Para qué sirve principalmente esta función en tus tareas del laboratorio?\n` +
                       `- A) Para que la computadora procese y organice la información de forma ordenada.\n` +
                       `- B) Para acelerar el internet de la máquina.\n` +
                       `- C) Para eliminar archivos temporales.\n\n` +
                       `*(Piénsala bien: la respuesta correcta es la A).*`;
            }

            if (modo === 'ejercicio') {
                if (q.includes('excel') || q.includes('formula') || q.includes('promedio')) {
                    return `Mira, la manera más fácil de practicar esto en Excel es haciendo una tabla rápida:\n\n` +
                           `1. Pon las materias o parciales en las primeras columnas (A y B).\n` +
                           `2. En la columna C pon la fórmula para revisar si pasaste:\n` +
                           `   \`=SI(PROMEDIO(A2:B2)>=6, "Aprobado", "Reprobado")\`\n\n` +
                           `Pruébalo en tu hoja y verás cómo cambia el mensaje de manera automática según la nota que ingreses.`;
                }
                return `Te dejo un ejemplo sencillo de cómo se vería la lógica en código Python:\n\n` +
                       `\`\`\`python\n# Ejemplo sencillo de evaluación\ncalificacion = 7.5\n\nif calificacion >= 6.0:\n    print("Pasa a la siguiente unidad")\nelse:\n    print("Presenta examen extraordinario")\n\`\`\`\n\n` +
                       `Irás viendo cómo la estructura \`if / else\` toma decisiones según el valor numérico.`;
            }

            if (q.includes('ram') || q.includes('rom') || q.includes('disco') || q.includes('hardware')) {
                return `Esa duda surge muy seguido en clase. La forma más clara de distinguirlos es pensar en tu escritorio físico:\n\n` +
                       `- La **memoria RAM** es la parte superior del escritorio donde pones las libretas abiertas mientras trabajas. Si el escritorio es grande, puedes tener varios libros abiertos a la vez. Cuando terminas y apagas la luz (o apagas la PC), la mesa queda vacía.\n` +
                       `- El **disco duro** es la mochila o el cajón. Ahí guardas tus cosas bien guardadas para encontrarlas al día siguiente.\n` +
                       `- La **ROM** son las instrucciones pegadas en la pata del escritorio desde que lo compraste; nadie las borra ni las cambia.`;
            }

            if (q.includes('excel') || q.includes('buscarv') || q.includes('si')) {
                return `Para las prácticas de Excel te sugiero memorizar estas cuatro herramientas básicas:\n\n` +
                       `- \`=SUMA(rango)\`: Para no andar sumando celda por celda.\n` +
                       `- \`=PROMEDIO(rango)\`: Saca la media de tus calificaciones al instante.\n` +
                       `- \`=SI(condicion, si_cumple, si_no)\`: Excelente para poner marcas automáticas de 'Aprobado' o 'Reprobado'.\n` +
                       `- \`=BUSCARV()\`: Para traer datos de otra tabla buscando un código o nombre.`;
            }

            return `Sobre tu duda de **"${escapeHTML(prompt)}"**:\n\n` +
                   `Te recomiendo revisar las pestañas fijas de nuestro portal según el tema de tu práctica:\n` +
                   `- Si es para dar formato a tus textos, en la pestaña **Word** están las reglas de sangría e índices.\n` +
                   `- Para fórmulas o tablas de calificaciones, apóyate en la pestaña **Excel**.\n` +
                   `- Y si tienes dudas con los comandos rápidos, revisa la tabla de **Atajos de Teclado**.`;
        }

        window.enviarPreguntaIA = function(event) {
            event.preventDefault();
            const input = document.getElementById('ai-input');
            const history = document.getElementById('ai-chat-history');
            if (!input || !history) return;

            const pregunta = input.value.trim();
            if (!pregunta) return;

            const userMsgDiv = document.createElement('div');
            userMsgDiv.className = "flex gap-3 items-start justify-end";
            userMsgDiv.innerHTML = `
                <div class="bg-indigo-600 text-white rounded-2xl p-3 shadow-sm max-w-[85%] text-sm leading-relaxed">
                    ${escapeHTML(pregunta)}
                </div>
                <div class="w-8 h-8 rounded-lg bg-slate-200 text-slate-600 flex items-center justify-center shrink-0 font-bold text-xs">
                    Tú
                </div>
            `;
            history.appendChild(userMsgDiv);

            input.value = '';
            history.scrollTop = history.scrollHeight;

            setTimeout(() => {
                const respuestaMD = generarRespuestaProfesorHumanizada(pregunta, aiCurrentMode);
                const respuestaHTML = typeof marked !== 'undefined' ? marked.parse(respuestaMD) : respuestaMD;

                const botMsgDiv = document.createElement('div');
                botMsgDiv.className = "flex gap-3 items-start";
                botMsgDiv.innerHTML = `
                    <div class="w-8 h-8 rounded-lg bg-indigo-600 text-white flex items-center justify-center shrink-0 font-bold">
                        <i class="fa-solid fa-graduation-cap text-xs"></i>
                    </div>
                    <div class="bg-white border border-slate-200 rounded-2xl p-4 shadow-sm max-w-[85%] text-slate-700 leading-relaxed text-sm ai-formatted-content">
                        ${respuestaHTML}
                    </div>
                `;
                history.appendChild(botMsgDiv);
                history.scrollTop = history.scrollHeight;
            }, 300);
        };

        // CÓDIGO QR
        window.generarCodigoQR = function() {
            const qrContainer = document.getElementById('qrcode-container');
            const qrText = document.getElementById('qr-url-text');
            if (!qrContainer) return;

            qrContainer.innerHTML = '';
            const currentURL = window.location.href;
            if (qrText) qrText.textContent = currentURL;

            if (typeof QRCode !== 'undefined') {
                new QRCode(qrContainer, {
                    text: currentURL,
                    width: 180,
                    height: 180,
                    colorDark: "#1e293b",
                    colorLight: "#ffffff",
                    correctLevel: QRCode.CorrectLevel.H
                });
            } else {
                qrContainer.innerHTML = '<p class="text-xs text-slate-500">Librería QR cargando...</p>';
            }
        };

        window.descargarCodigoPagina = function() {
            const htmlContent = document.documentElement.outerHTML;
            const blob = new Blob([htmlContent], { type: 'text/html' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'CompuPrep_181_Offline.html';
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
        };

        // INICIALIZACIÓN
        window.addEventListener('DOMContentLoaded', function() {
            window.calcularPromedio();
            window.renderizarAtajos(listaAtajos);
            window.iniciarMinijuego();
            window.cargarQuiz();
        });
    </script>
</body>
</html>
