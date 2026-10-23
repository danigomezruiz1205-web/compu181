[xd.html](https://github.com/user-attachments/files/33894800/xd.html)
<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <!-- 
      CompuPrep 181 - Apuntes y Guías
      Creado por Dani y Edwin (Grupo 3°B - Prepa 181)
      "Para que nadie se vaya a extraordinario de Informática"
    -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CompuPrep 181 | Hecho por Dani y Edwin</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Permanent Marker, Caveat & Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Permanent+Marker&family=Inter:ital,wght@0,400;0,600;0,700;0,800;1,400&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f4f3ef;
            background-image: radial-gradient(#d1d5db 1px, transparent 1px);
            background-size: 20px 20px;
            color: #1e293b;
        }
        .font-handwriting {
            font-family: 'Caveat', cursive;
        }
        .font-marker {
            font-family: 'Permanent Marker', cursive;
        }
        .font-mono-code {
            font-family: 'JetBrains Mono', monospace;
        }
        .tab-btn.active {
            background-color: #0f172a;
            color: #ffffff;
            border-bottom: 4px solid #f59e0b;
        }
        .tape-effect {
            background: rgba(254, 240, 138, 0.7);
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
        }
        kbd {
            box-shadow: 0 3px 0 #94a3b8;
        }
        .notebook-line {
            background-image: linear-gradient(transparent 95%, #e2e8f0 95%);
            background-size: 100% 2rem;
            line-height: 2rem;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col selection:bg-amber-200 selection:text-amber-900" oncontextmenu="return false;">

    <!-- BARRA SUPERIOR Y CRÉDITOS DANI Y EDWIN -->
    <header class="bg-slate-900 text-white sticky top-0 z-50 border-b-4 border-amber-500 shadow-lg">
        <div class="max-w-6xl mx-auto px-4 sm:px-6">
            <div class="flex items-center justify-between h-16 sm:h-20">
                <div class="flex items-center gap-3">
                    <div class="bg-amber-500 text-slate-950 p-2.5 rounded-2xl transform -rotate-3 font-marker text-xl shadow-md">
                        181
                    </div>
                    <div>
                        <div class="flex items-center gap-2">
                            <h1 class="font-extrabold text-xl sm:text-2xl tracking-tight text-white">CompuPrep 181</h1>
                            <span class="bg-amber-400 text-slate-950 text-[10px] font-black px-2 py-0.5 rounded-full uppercase tracking-widest hidden sm:inline-block">2026</span>
                        </div>
                        <p class="text-xs text-amber-300/90 font-medium flex items-center gap-1">
                            <i class="fa-solid fa-code text-amber-400"></i> Creado por Dani y Edwin
                        </p>
                    </div>
                </div>

                <!-- Badge de autoría visible -->
                <div class="flex items-center gap-2">
                    <div class="bg-slate-800 border border-slate-700 rounded-xl px-3 py-1.5 flex items-center gap-2 shadow-inner">
                        <span class="flex h-2.5 w-2.5 relative">
                            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                            <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-emerald-500"></span>
                        </span>
                        <span class="text-xs font-semibold text-slate-300">
                            Hecho por <strong class="text-amber-400">Dani y Edwin</strong>
                        </span>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Pestañas estilo cuaderno escolar -->
        <nav class="bg-slate-950 border-t border-slate-800 overflow-x-auto scrollbar-none">
            <div class="max-w-6xl mx-auto px-2 flex gap-1 sm:gap-2 py-1 min-w-max">
                <button onclick="changeTab('home')" id="tab-home" class="tab-btn active px-4 py-2.5 rounded-t-xl text-xs sm:text-sm font-bold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-800">
                    <i class="fa-solid fa-house text-amber-400"></i> Inicio
                </button>
                <button onclick="changeTab('word')" id="tab-word" class="tab-btn px-4 py-2.5 rounded-t-xl text-xs sm:text-sm font-bold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-800">
                    <i class="fa-solid fa-file-word text-blue-400"></i> Word
                </button>
                <button onclick="changeTab('excel')" id="tab-excel" class="tab-btn px-4 py-2.5 rounded-t-xl text-xs sm:text-sm font-bold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-800">
                    <i class="fa-solid fa-file-excel text-emerald-400"></i> Excel
                </button>
                <button onclick="changeTab('powerpoint')" id="tab-powerpoint" class="tab-btn px-4 py-2.5 rounded-t-xl text-xs sm:text-sm font-bold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-800">
                    <i class="fa-solid fa-file-powerpoint text-orange-400"></i> PowerPoint
                </button>
                <button onclick="changeTab('pdf')" id="tab-pdf" class="tab-btn px-4 py-2.5 rounded-t-xl text-xs sm:text-sm font-bold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-800">
                    <i class="fa-solid fa-file-pdf text-rose-400"></i> Biblioteca y PDFs
                </button>
                <button onclick="changeTab('atajos')" id="tab-atajos" class="tab-btn px-4 py-2.5 rounded-t-xl text-xs sm:text-sm font-bold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-800">
                    <i class="fa-solid fa-keyboard text-purple-400"></i> Atajos de Teclado
                </button>
                <button onclick="changeTab('examen')" id="tab-examen" class="tab-btn px-4 py-2.5 rounded-t-xl text-xs sm:text-sm font-bold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-800">
                    <i class="fa-solid fa-clipboard-question text-cyan-400"></i> Mini Examen
                </button>
                <button onclick="changeTab('tips')" id="tab-tips" class="tab-btn px-4 py-2.5 rounded-t-xl text-xs sm:text-sm font-bold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-800">
                    <i class="fa-solid fa-graduation-cap text-rose-400"></i> Tips Examen
                </button>
                <button onclick="changeTab('creditos')" id="tab-creditos" class="tab-btn px-4 py-2.5 rounded-t-xl text-xs sm:text-sm font-bold transition-all flex items-center gap-2 text-slate-300 hover:bg-slate-800">
                    <i class="fa-solid fa-users text-amber-400"></i> Dani y Edwin
                </button>
            </div>
        </nav>
    </header>

    <!-- BANNER DE BIENVENIDA / HERO -->
    <div class="bg-gradient-to-r from-slate-900 via-slate-800 to-blue-950 text-white py-8 px-4 border-b border-slate-700 relative overflow-hidden">
        <div class="max-w-6xl mx-auto flex flex-col md:flex-row items-center justify-between gap-6 relative z-10">
            <div class="space-y-2 text-center md:text-left">
                <div class="inline-flex items-center gap-2 bg-amber-400/10 border border-amber-400/30 px-3 py-1 rounded-full text-amber-300 text-xs font-semibold">
                    <i class="fa-solid fa-star"></i> Apuntes de alumnos para alumnos • Prepa 181
                </div>
                <h2 class="text-2xl sm:text-4xl font-extrabold tracking-tight">
                    El portal de compu que sí le entiendes.
                </h2>
                <p class="text-sm sm:text-base text-slate-300 max-w-2xl">
                    Armamos este sitio entre los dos para subir resúmenes, las fórmulas de Excel que siempre se nos olvidan en los exámenes y un simulador de examen para practicar sin nervios.
                </p>
            </div>
            
            <!-- Etiqueta estilo sticker -->
            <div class="bg-amber-100 text-slate-900 p-4 rounded-2xl transform rotate-2 border-2 border-slate-900 shadow-xl max-w-xs text-center relative shrink-0">
                <div class="absolute -top-3 left-1/2 -translate-x-1/2 px-4 py-0.5 tape-effect text-[11px] font-bold tracking-widest text-slate-700 uppercase">
                    IMPORTANTE
                </div>
                <p class="font-handwriting text-2xl font-bold leading-tight text-amber-900">
                    "Creado por Dani y Edwin"
                </p>
                <p class="text-xs text-slate-600 mt-1">
                    Preparatoria N° 181 • Informática I y II
                </p>
            </div>
        </div>
    </div>

    <!-- CONTENIDO PRINCIPAL -->
    <main class="flex-grow max-w-6xl w-full mx-auto p-4 sm:p-6 lg:p-8">

        <!-- ==================== PESTAÑA: INICIO ==================== -->
        <section id="content-home" class="tab-content block space-y-6">
            <div class="grid md:grid-cols-3 gap-6">
                <!-- Columna Principal -->
                <div class="md:col-span-2 space-y-6">
                    
                    <div class="bg-white p-6 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)] relative">
                        <span class="absolute -top-3 right-4 bg-rose-500 text-white font-bold text-xs px-3 py-1 rounded-full">
                            ¡Nuevo Mini Examen!
                        </span>
                        <h3 class="text-xl font-bold text-slate-900 mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-bullhorn text-amber-500"></i> ¿Por qué hicimos esta página?
                        </h3>
                        <p class="text-sm text-slate-700 leading-relaxed mb-4">
                            En la sala de cómputo siempre pasa lo mismo: a la mitad de la práctica a alguien se le desacomoda la tabla en Word, a otro le sale el error <code class="bg-slate-100 text-rose-600 font-mono px-1 border border-slate-300">#¡VALOR!</code> en Excel, o nadie se acuerda de la fórmula del promedio. 
                        </p>
                        <p class="text-sm text-slate-700 leading-relaxed">
                            Por eso resumimos aquí todo lo que pide el profe en el temario, explicado directo, con simuladores y ahora con un <b>Mini Examen interactivo</b> para que pongas a prueba tus conocimientos antes de la evaluación oficial.
                        </p>
                    </div>

                    <!-- Cuadrícula de acceso rápido -->
                    <div class="grid sm:grid-cols-2 gap-4">
                        <div onclick="changeTab('word')" class="cursor-pointer bg-blue-50 hover:bg-blue-100/80 p-5 rounded-2xl border-2 border-blue-900 shadow-md transition-all transform hover:-translate-y-1">
                            <div class="bg-blue-600 text-white w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3 shadow">
                                <i class="fa-solid fa-file-word text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base">Guía Extendida de Word</h4>
                            <p class="text-xs text-slate-600 mt-1">Márgenes APA, sangría francesa, portadas, tablas automáticas y cómo evitar que se mueva el formato.</p>
                        </div>

                        <div onclick="changeTab('excel')" class="cursor-pointer bg-emerald-50 hover:bg-emerald-100/80 p-5 rounded-2xl border-2 border-emerald-900 shadow-md transition-all transform hover:-translate-y-1">
                            <div class="bg-emerald-600 text-white w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3 shadow">
                                <i class="fa-solid fa-file-excel text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base">Fórmulas Avanzadas & Excel</h4>
                            <p class="text-xs text-slate-600 mt-1">Simulador de promedio de calificaciones, referencias absolutas ($A$1) y funciones lógicas.</p>
                        </div>

                        <div onclick="changeTab('powerpoint')" class="cursor-pointer bg-orange-50 hover:bg-orange-100/80 p-5 rounded-2xl border-2 border-orange-900 shadow-md transition-all transform hover:-translate-y-1">
                            <div class="bg-orange-600 text-white w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3 shadow">
                                <i class="fa-solid fa-file-powerpoint text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base">PowerPoint Pro</h4>
                            <p class="text-xs text-slate-600 mt-1">Regla 6x6, transiciones profesionales, diseño de diapositivas y modo presentador.</p>
                        </div>

                        <div onclick="changeTab('examen')" class="cursor-pointer bg-cyan-50 hover:bg-cyan-100/80 p-5 rounded-2xl border-2 border-cyan-900 shadow-md transition-all transform hover:-translate-y-1">
                            <div class="bg-cyan-600 text-white w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3 shadow">
                                <i class="fa-solid fa-clipboard-question text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base">Nuevo Mini Examen</h4>
                            <p class="text-xs text-slate-600 mt-1">Pon a prueba lo que sabes con preguntas de opción múltiple y calificación inmediata.</p>
                        </div>
                    </div>

                </div>

                <!-- Barra Lateral Estilo Libreta -->
                <div class="space-y-6">
                    <div class="bg-amber-100/90 p-5 rounded-2xl border-2 border-amber-800 shadow-[4px_4px_0px_0px_rgba(146,64,14,1)] relative transform rotate-1">
                        <div class="w-12 h-3 bg-amber-300/80 mx-auto -mt-7 mb-3 tape-effect rounded"></div>
                        <h4 class="font-marker text-slate-900 text-lg mb-2 border-b border-amber-300 pb-1">
                            📌 AVISOS DE LA PREPA 181
                        </h4>
                        <ul class="text-xs text-slate-800 space-y-3 font-medium">
                            <li class="flex items-start gap-2">
                                <span class="text-rose-600 font-bold">•</span>
                                <span><b>Examen del Parcial:</b> Practica en la pestaña "Mini Examen" antes de pasar al laboratorio.</span>
                            </li>
                            <li class="flex items-start gap-2">
                                <span class="text-rose-600 font-bold">•</span>
                                <span><b>Memoria USB:</b> Guarden todo siempre en la nube o envíenselo por correo, la compu 12 del lab borra archivos al reiniciar.</span>
                            </li>
                            <li class="flex items-start gap-2">
                                <span class="text-rose-600 font-bold">•</span>
                                <span><b>Créditos:</b> Esta página fue programada y redactada por <b>Dani y Edwin</b> para ayudar a la comunidad del plantel.</span>
                            </li>
                        </ul>
                    </div>

                    <div class="bg-slate-900 text-white p-5 rounded-2xl border-2 border-slate-800 shadow-md">
                        <h4 class="font-bold text-amber-400 text-sm mb-3 flex items-center gap-2">
                            <i class="fa-solid fa-circle-question"></i> ¿Dudas sobre una práctica?
                        </h4>
                        <p class="text-xs text-slate-300 leading-relaxed mb-3">
                            Si tienes algún problema con una fórmula o un documento de la materia, acércate con Dani o Edwin durante el receso o la hora libre en la sala de computación.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- ==================== PESTAÑA: WORD (INFORMACIÓN AMPLIADA) ==================== -->
        <section id="content-word" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-blue-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-file-word text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Microsoft Word: Guía Extendida y Formato APA</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Aprende a estructurar tus reportes académicos de nivel superior sin errores de formato.</p>
                    </div>
                </div>

                <!-- Anotación rápida -->
                <div class="bg-amber-50 border-l-4 border-amber-500 p-4 rounded-r-xl text-xs sm:text-sm text-slate-700 mb-6">
                    <p class="font-bold text-amber-900 mb-1">
                        <i class="fa-solid fa-pen-to-square"></i> Nota de Edwin:
                    </p>
                    <p>"Si vas a meter imágenes en Word, haz clic derecho sobre la imagen, selecciona <b>Ajustar texto > Cuadrado</b> o <b>Estrecho</b>. Así la puedes mover por donde quieras sin que se desacomode todo el párrafo."</p>
                </div>

                <!-- Taller interactivo de texto -->
                <div class="bg-slate-50 p-5 sm:p-6 rounded-2xl border-2 border-slate-300 mb-8">
                    <div class="flex items-center justify-between flex-wrap gap-2 mb-4">
                        <h3 class="font-bold text-slate-900 text-sm sm:text-base flex items-center gap-2">
                            <i class="fa-solid fa-sliders text-blue-600"></i> Probador Interactivo de Estilos para Trabajos
                        </h3>
                        <span class="text-[11px] font-semibold text-slate-500 bg-slate-200 px-2 py-0.5 rounded">Prueba en vivo</span>
                    </div>

                    <div class="grid sm:grid-cols-3 gap-3 mb-4">
                        <div>
                            <label class="block text-xs font-bold text-slate-700 mb-1">Tipo de letra:</label>
                            <select id="word-font" onchange="updateWordPreview()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium focus:ring-2 focus:ring-blue-500">
                                <option value="Arial, sans-serif">Arial (Limpia y estándar)</option>
                                <option value="'Times New Roman', serif">Times New Roman (Estilo APA tradicional)</option>
                                <option value="'Calibri', sans-serif">Calibri (Por defecto en Word)</option>
                            </select>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-slate-700 mb-1">Alineación:</label>
                            <select id="word-align" onchange="updateWordPreview()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium focus:ring-2 focus:ring-blue-500">
                                <option value="justify">Justificado (El preferido de los profes)</option>
                                <option value="left">Izquierda</option>
                                <option value="center">Centrado (Para portadas)</option>
                            </select>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-slate-700 mb-1">Interlineado:</label>
                            <select id="word-line" onchange="updateWordPreview()" class="w-full p-2 bg-white border border-slate-300 rounded-lg text-xs font-medium focus:ring-2 focus:ring-blue-500">
                                <option value="1.5">1.5 líneas (Limpio y legible)</option>
                                <option value="2.0">Doble - 2.0 (Norma APA estricta)</option>
                                <option value="1.0">Sencillo - 1.0 (Muy apretado)</option>
                            </select>
                        </div>
                    </div>

                    <div class="p-6 bg-white border-2 border-slate-300 rounded-xl shadow-inner min-h-[160px]">
                        <h4 id="word-preview-title" class="font-bold text-slate-900 text-base mb-2">
                            Materia: Informática • Preparatoria N° 181
                        </h4>
                        <p id="word-preview-text" class="text-sm text-slate-800 leading-relaxed" style="text-align: justify; font-family: Arial, sans-serif; line-height: 1.5;">
                            Esta es una demostración en tiempo real de cómo luce el texto al cambiar el formato. Recuerda que para los reportes finales es recomendable usar títulos en negrita con un tamaño ligeramente mayor (14pt) y texto general en 12pt con alineación justificada.
                        </p>
                    </div>
                </div>

                <!-- Más información detallada añadida -->
                <h3 class="font-bold text-slate-900 text-lg mb-4 flex items-center gap-2">
                    <i class="fa-solid fa-book-open text-blue-600"></i> Conceptos Clave evaluados en Word
                </h3>

                <div class="grid sm:grid-cols-3 gap-4 mb-6">
                    <div class="p-4 bg-blue-50/70 rounded-xl border border-blue-200">
                        <h4 class="font-bold text-blue-900 text-sm mb-1">1. Sangría Francesa</h4>
                        <p class="text-xs text-slate-700">Utilizada obligatoriamente en la bibliografía o lista de referencias APA, donde la primera línea va al margen y las siguientes están sangradas.</p>
                    </div>
                    <div class="p-4 bg-blue-50/70 rounded-xl border border-blue-200">
                        <h4 class="font-bold text-blue-900 text-sm mb-1">2. Encabezado y Pie</h4>
                        <p class="text-xs text-slate-700">Permite insertar números de página automáticos, nombre del trabajo institucional y fecha sin alterar el contenido central.</p>
                    </div>
                    <div class="p-4 bg-blue-50/70 rounded-xl border border-blue-200">
                        <h4 class="font-bold text-blue-900 text-sm mb-1">3. Saltos de Sección</h4>
                        <p class="text-xs text-slate-700">Esenciales para separar la portada (sin número de página) del resto del documento que sí lleva numeración romana o arábiga.</p>
                    </div>
                </div>

                <!-- Cuadros explicativos -->
                <div class="grid sm:grid-cols-2 gap-4">
                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
                        <h4 class="font-bold text-slate-900 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-list-ol text-blue-600"></i> Cómo hacer índice automático
                        </h4>
                        <ol class="text-xs text-slate-700 space-y-1.5 list-decimal list-inside">
                            <li>Selecciona el título de cada tema y aplícale el estilo <b>Título 1</b>.</li>
                            <li>A los subtítulos aplícales el estilo <b>Título 2</b>.</li>
                            <li>Ve a la pestaña <b>Referencias > Tabla de contenido</b> y elige la primera opción.</li>
                        </ol>
                    </div>

                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
                        <h4 class="font-bold text-slate-900 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-file-export text-blue-600"></i> Para guardar en PDF
                        </h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            No le saques fotos a la pantalla. Ve a <b>Archivo > Guardar como</b>, cambia el tipo de documento a <b>PDF (*.pdf)</b> y listo. Así el formato no se mueve cuando el profe lo abra en su compu.
                        </p>
                    </div>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: EXCEL (INFORMACIÓN AMPLIADA) ==================== -->
        <section id="content-excel" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-emerald-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-file-excel text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Microsoft Excel: Fórmulas y Guía Extendida</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Domina el uso de celdas, rangos, funciones matemáticas y lógicas para la prepa.</p>
                    </div>
                </div>

                <!-- SIMULADOR INTERACTIVO DE PROMEDIO -->
                <div class="bg-slate-900 text-white p-5 sm:p-6 rounded-2xl border-2 border-slate-800 mb-8 shadow-lg">
                    <div class="flex items-center justify-between flex-wrap gap-2 mb-4">
                        <h3 class="font-bold text-amber-400 text-base flex items-center gap-2">
                            <i class="fa-solid fa-calculator"></i> Simulador Interactivo de Promedio de Calificaciones
                        </h3>
                        <span class="text-[11px] bg-emerald-500/20 text-emerald-300 font-semibold px-2.5 py-0.5 rounded border border-emerald-500/30">
                            Práctica estilo examen
                        </span>
                    </div>

                    <p class="text-xs text-slate-300 mb-4">
                        Ingresa tus tres calificaciones parciales para probar cómo funcionan las fórmulas <code class="text-emerald-400 font-mono">=PROMEDIO()</code> y <code class="text-emerald-400 font-mono">=SI()</code> en Excel:
                    </p>

                    <div class="grid sm:grid-cols-3 gap-4 mb-6">
                        <div>
                            <label class="block text-xs font-semibold text-slate-300 mb-1">Parcial 1:</label>
                            <input type="number" id="calc-p1" min="0" max="10" value="8" oninput="calcularPromedioSimulado()" class="w-full p-2.5 bg-slate-800 border border-slate-700 rounded-lg text-sm text-white font-bold focus:ring-2 focus:ring-emerald-400 focus:outline-none">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-300 mb-1">Parcial 2:</label>
                            <input type="number" id="calc-p2" min="0" max="10" value="7" oninput="calcularPromedioSimulado()" class="w-full p-2.5 bg-slate-800 border border-slate-700 rounded-lg text-sm text-white font-bold focus:ring-2 focus:ring-emerald-400 focus:outline-none">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-300 mb-1">Parcial 3:</label>
                            <input type="number" id="calc-p3" min="0" max="10" value="9" oninput="calcularPromedioSimulado()" class="w-full p-2.5 bg-slate-800 border border-slate-700 rounded-lg text-sm text-white font-bold focus:ring-2 focus:ring-emerald-400 focus:outline-none">
                        </div>
                    </div>

                    <div class="bg-slate-950 p-4 rounded-xl border border-slate-800 grid sm:grid-cols-2 gap-4 items-center">
                        <div>
                            <span class="text-[11px] text-slate-400 block mb-0.5">Fórmula empleada:</span>
                            <div class="font-mono text-xs text-emerald-400 bg-slate-900 p-2 rounded border border-slate-800">
                                =PROMEDIO(B2:D2)
                            </div>
                        </div>

                        <div class="text-right sm:border-l sm:border-slate-800 sm:pl-4">
                            <span class="text-xs text-slate-400 block">Resultado obtenido:</span>
                            <div id="sim-resultado" class="text-2xl font-black text-amber-400">8.0</div>
                            <div id="sim-estatus" class="text-xs font-bold text-emerald-400">¡Aprobado!</div>
                        </div>
                    </div>
                </div>

                <!-- Lista de Fórmulas Clave -->
                <h3 class="font-bold text-slate-900 text-lg mb-4 flex items-center gap-2">
                    <i class="fa-solid fa-code text-emerald-600"></i> Fórmulas indispensables para el examen
                </h3>

                <div class="grid sm:grid-cols-2 gap-4 mb-6">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <div class="font-mono text-xs text-emerald-700 font-bold bg-emerald-100/80 px-2 py-1 rounded inline-block mb-2">
                            =SUMA(A1:A10)
                        </div>
                        <p class="text-xs text-slate-700">Suma todos los números contenidos en ese rango de celdas sin tener que poner A1+A2+A3...</p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <div class="font-mono text-xs text-emerald-700 font-bold bg-emerald-100/80 px-2 py-1 rounded inline-block mb-2">
                            =PROMEDIO(B1:B5)
                        </div>
                        <p class="text-xs text-slate-700">Calcula la media aritmética del grupo de celdas seleccionado.</p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <div class="font-mono text-xs text-emerald-700 font-bold bg-emerald-100/80 px-2 py-1 rounded inline-block mb-2">
                            =MAX(C1:C20) y =MIN(C1:C20)
                        </div>
                        <p class="text-xs text-slate-700">Obtiene la calificación más alta o más baja automáticamente dentro de una lista.</p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <div class="font-mono text-xs text-emerald-700 font-bold bg-emerald-100/80 px-2 py-1 rounded inline-block mb-2">
                            =SI(A1&gt;=6, "Aprobado", "Reprobado")
                        </div>
                        <p class="text-xs text-slate-700">Comprueba una condición lógica y coloca un texto según el resultado.</p>
                    </div>
                </div>

                <!-- Sección extra agregada -->
                <div class="bg-emerald-50/70 p-5 rounded-2xl border border-emerald-200">
                    <h4 class="font-bold text-emerald-900 text-sm mb-2 flex items-center gap-2">
                        <i class="fa-solid fa-circle-info text-emerald-700"></i> ¿Qué son las Referencias Absolutas en Excel?
                    </h4>
                    <p class="text-xs text-slate-700 leading-relaxed mb-2">
                        Cuando arrastras una fórmula hacia abajo, las celdas cambian automáticamente (ej. de A1 pasa a A2). Sin embargo, si necesitas que una celda fija (como el porcentaje de IVA en la celda <code class="font-mono text-emerald-800 font-bold">F1</code>) no se mueva al copiar la fórmula, debes usar el signo de pesos: <code class="font-mono text-emerald-800 font-bold">$F$1</code>. ¡Esta pregunta siempre viene en los exámenes parciales!
                    </p>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: POWERPOINT (INFORMACIÓN AMPLIADA) ==================== -->
        <section id="content-powerpoint" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-orange-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-file-powerpoint text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">PowerPoint: Exposiciones de 10 y Guía Extendida</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Estrategias de diseño visual y estructuración para presentaciones escolares exitosas.</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-3 gap-6 mb-6">
                    <div class="p-5 bg-orange-50/70 rounded-2xl border-2 border-orange-200">
                        <div class="text-orange-600 font-marker text-2xl mb-1">Regla 6 x 6</div>
                        <h4 class="font-bold text-slate-900 text-sm mb-2">Para no saturar de texto</h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            Máximo <b>6 líneas</b> por diapositiva y máximo <b>6 palabras</b> por línea. Si pones párrafos eternos, la gente deja de poner atención y el profe te baja puntos por leer.
                        </p>
                    </div>

                    <div class="p-5 bg-orange-50/70 rounded-2xl border-2 border-orange-200">
                        <div class="text-orange-600 font-marker text-2xl mb-1">F5 / Shift + F5</div>
                        <h4 class="font-bold text-slate-900 text-sm mb-2">Presentar al instante</h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            Presiona <kbd class="px-1.5 py-0.5 bg-white border border-slate-300 rounded text-[11px]">F5</kbd> para iniciar desde la primera diapositiva o <kbd class="px-1.5 py-0.5 bg-white border border-slate-300 rounded text-[11px]">Shift + F5</kbd> para empezar desde la diapositiva actual en la que estés trabajando.
                        </p>
                    </div>

                    <div class="p-5 bg-orange-50/70 rounded-2xl border-2 border-orange-200">
                        <div class="text-orange-600 font-marker text-2xl mb-1">Imágenes PNG</div>
                        <h4 class="font-bold text-slate-900 text-sm mb-2">Sin fondos blancos</h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            Busca siempre imágenes con fondo transparente (PNG) o quítale el fondo en las herramientas de PowerPoint. Le da un toque mucho más profesional a tu trabajo escolar.
                        </p>
                    </div>
                </div>

                <!-- Bloque adicional añadido -->
                <div class="grid sm:grid-cols-2 gap-4 mb-6">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h4 class="font-bold text-slate-900 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-masks-theater text-orange-600"></i> Vistas de Presentación
                        </h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            Distingue entre la vista <b>Normal</b> (para editar), el <b>Clasificador de diapositivas</b> (para reordenar la secuencia completa en miniatura) y la vista <b>Vista de lectura</b>.
                        </p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h4 class="font-bold text-slate-900 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-bullseye text-orange-600"></i> Uso del Patrón de Diapositivas
                        </h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            Sirve para aplicar un logotipo institucional (como el escudo de la Prepa 181) o un tipo de fuente en todas las diapositivas de manera automática sin modificar una por una.
                        </p>
                    </div>
                </div>

                <div class="bg-slate-900 text-white p-6 rounded-2xl border-2 border-slate-800">
                    <h3 class="font-bold text-amber-400 text-base mb-2 flex items-center gap-2">
                        <i class="fa-solid fa-lightbulb"></i> Tip extra de Dani y Edwin para pasar con 10
                    </h3>
                    <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
                        Usa transiciones sutiles como <b>Desvanecer</b> o <b>Desplazar</b>. Evita los efectos de texto con sonidos de máquina de escribir o láser, ya que suelen verse poco formales en las exposiciones de la prepa.
                    </p>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: BIBLIOTECA Y PDFS (INFORMACIÓN AMPLIADA) ==================== -->
        <section id="content-pdf" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-rose-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-file-pdf text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Biblioteca Digital y Guías en PDF (Ampliada)</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Material de apoyo bibliográfico y resúmenes oficiales para las prácticas de cómputo.</p>
                    </div>
                </div>

                <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4 mb-6">
                    <div class="bg-slate-50 border-2 border-slate-300 p-5 rounded-2xl flex flex-col justify-between">
                        <div>
                            <div class="bg-rose-100 text-rose-700 w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3">
                                <i class="fa-solid fa-file-pdf text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-sm mb-1">Guía Oficial de Word Básico</h4>
                            <p class="text-xs text-slate-600 mb-4">Ejercicios de formato, sangría francesa, portadas e inserción de tablas.</p>
                        </div>
                        <button onclick="mostrarAvisoDescarga('Guía Oficial de Word Básico')" class="w-full bg-slate-900 hover:bg-slate-800 text-white font-bold text-xs py-2.5 rounded-xl transition-all flex items-center justify-center gap-2">
                            <i class="fa-solid fa-download"></i> Descargar PDF
                        </button>
                    </div>

                    <div class="bg-slate-50 border-2 border-slate-300 p-5 rounded-2xl flex flex-col justify-between">
                        <div>
                            <div class="bg-emerald-100 text-emerald-700 w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3">
                                <i class="fa-solid fa-file-pdf text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-sm mb-1">Manual de Fórmulas Excel</h4>
                            <p class="text-xs text-slate-600 mb-4">Formulario completo con SUMA, PROMEDIO, SI condicional y gráficas de barras.</p>
                        </div>
                        <button onclick="mostrarAvisoDescarga('Manual de Fórmulas Excel')" class="w-full bg-slate-900 hover:bg-slate-800 text-white font-bold text-xs py-2.5 rounded-xl transition-all flex items-center justify-center gap-2">
                            <i class="fa-solid fa-download"></i> Descargar PDF
                        </button>
                    </div>

                    <div class="bg-slate-50 border-2 border-slate-300 p-5 rounded-2xl flex flex-col justify-between">
                        <div>
                            <div class="bg-orange-100 text-orange-700 w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3">
                                <i class="fa-solid fa-file-pdf text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-sm mb-1">Plantilla de Exposición Pro</h4>
                            <p class="text-xs text-slate-600 mb-4">Estructura recomendada diapositiva por diapositiva para el proyecto final.</p>
                        </div>
                        <button onclick="mostrarAvisoDescarga('Plantilla de Exposición Pro')" class="w-full bg-slate-900 hover:bg-slate-800 text-white font-bold text-xs py-2.5 rounded-xl transition-all flex items-center justify-center gap-2">
                            <i class="fa-solid fa-download"></i> Descargar PDF
                        </button>
                    </div>
                </div>

                <!-- Nuevos documentos añadidos -->
                <div class="grid sm:grid-cols-2 gap-4">
                    <div class="bg-rose-50/70 p-4 rounded-xl border border-rose-200 flex items-center justify-between">
                        <div>
                            <h4 class="font-bold text-rose-900 text-sm">Glosario de Términos Informáticos</h4>
                            <p class="text-xs text-slate-600">Definiciones de Hardware, Software, RAM, ROM y Redes.</p>
                        </div>
                        <button onclick="mostrarAvisoDescarga('Glosario de Términos Informáticos')" class="bg-rose-600 hover:bg-rose-700 text-white text-xs font-bold px-3 py-2 rounded-lg shrink-0">
                            Descargar
                        </button>
                    </div>

                    <div class="bg-rose-50/70 p-4 rounded-xl border border-rose-200 flex items-center justify-between">
                        <div>
                            <h4 class="font-bold text-rose-900 text-sm">Guía de Seguridad en la Nube</h4>
                            <p class="text-xs text-slate-600">Buenas prácticas para respaldar archivos escolares.</p>
                        </div>
                        <button onclick="mostrarAvisoDescarga('Guía de Seguridad en la Nube')" class="bg-rose-600 hover:bg-rose-700 text-white text-xs font-bold px-3 py-2 rounded-lg shrink-0">
                            Descargar
                        </button>
                    </div>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: ATAJOS DE TECLADO (DISEÑO MEJORADO NEÓN / TERMINAL) ==================== -->
        <section id="content-atajos" class="tab-content hidden space-y-6">
            <div class="bg-slate-950 p-6 sm:p-10 rounded-3xl border-2 border-purple-500/40 shadow-[0_0_30px_rgba(168,85,247,0.15)] relative overflow-hidden text-white">
                
                <div class="absolute -right-20 -top-20 w-72 h-72 bg-purple-600/10 rounded-full blur-3xl pointer-events-none"></div>
                <div class="absolute -left-20 -bottom-20 w-72 h-72 bg-cyan-600/10 rounded-full blur-3xl pointer-events-none"></div>

                <div class="flex items-center gap-4 mb-8 pb-6 border-b border-purple-500/30 relative z-10">
                    <div class="bg-gradient-to-br from-purple-600 to-indigo-600 text-white p-4 rounded-2xl shadow-lg shadow-purple-500/30 border border-purple-400/30">
                        <i class="fa-solid fa-terminal text-3xl text-cyan-300"></i>
                    </div>
                    <div>
                        <div class="inline-flex items-center gap-2 bg-purple-500/20 border border-purple-500/40 px-3 py-1 rounded-full text-purple-300 text-xs font-mono font-bold mb-1">
                            <i class="fa-solid fa-bolt text-amber-400"></i> MODO TERMINAL PRO
                        </div>
                        <h2 class="text-2xl sm:text-3xl font-extrabold tracking-tight text-white font-mono-code">Atajos de Teclado Esenciales</h2>
                        <p class="text-xs sm:text-sm text-slate-400">Domina estas combinaciones clave para trabajar a máxima velocidad en Windows, Word, Excel y PowerPoint.</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-2 gap-6 relative z-10">
                    
                    <!-- Tarjeta 1: Sistema Windows -->
                    <div class="bg-slate-900/90 border border-purple-500/30 p-6 rounded-2xl shadow-xl hover:border-purple-500/60 transition-all group">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="w-10 h-10 rounded-xl bg-blue-500/20 text-blue-400 flex items-center justify-center font-bold border border-blue-500/30">
                                <i class="fa-brands fa-windows"></i>
                            </div>
                            <h3 class="font-bold text-slate-100 text-base font-mono-code">Sistema Windows</h3>
                        </div>
                        <ul class="space-y-3 text-xs sm:text-sm">
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Copiar / Pegar</span>
                                <div class="space-x-1">
                                    <kbd class="px-2 py-1 bg-slate-800 text-cyan-300 font-mono text-xs rounded border border-slate-700 shadow">Ctrl + C</kbd>
                                    <kbd class="px-2 py-1 bg-slate-800 text-cyan-300 font-mono text-xs rounded border border-slate-700 shadow">Ctrl + V</kbd>
                                </div>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Deshacer / Rehacer</span>
                                <div class="space-x-1">
                                    <kbd class="px-2 py-1 bg-slate-800 text-cyan-300 font-mono text-xs rounded border border-slate-700 shadow">Ctrl + Z</kbd>
                                    <kbd class="px-2 py-1 bg-slate-800 text-cyan-300 font-mono text-xs rounded border border-slate-700 shadow">Ctrl + Y</kbd>
                                </div>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Guardar documento</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-cyan-300 font-mono text-xs rounded border border-slate-700 shadow">Ctrl + G / S</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Seleccionar todo</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-cyan-300 font-mono text-xs rounded border border-slate-700 shadow">Ctrl + E</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Abrir Explorador de Archivos</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-cyan-300 font-mono text-xs rounded border border-slate-700 shadow">Win + E</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Minimizar todas las ventanas</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-cyan-300 font-mono text-xs rounded border border-slate-700 shadow">Win + D</kbd>
                            </li>
                        </ul>
                    </div>

                    <!-- Tarjeta 2: Microsoft Word -->
                    <div class="bg-slate-900/90 border border-purple-500/30 p-6 rounded-2xl shadow-xl hover:border-purple-500/60 transition-all group">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="w-10 h-10 rounded-xl bg-blue-600/20 text-blue-400 flex items-center justify-center font-bold border border-blue-500/30">
                                <i class="fa-solid fa-file-word"></i>
                            </div>
                            <h3 class="font-bold text-slate-100 text-base font-mono-code">Microsoft Word</h3>
                        </div>
                        <ul class="space-y-3 text-xs sm:text-sm">
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Negrita / Cursiva / Subrayado</span>
                                <div class="space-x-1">
                                    <kbd class="px-1.5 py-1 bg-slate-800 text-blue-300 font-mono text-[11px] rounded border border-slate-700">Ctrl+N</kbd>
                                    <kbd class="px-1.5 py-1 bg-slate-800 text-blue-300 font-mono text-[11px] rounded border border-slate-700">Ctrl+K</kbd>
                                    <kbd class="px-1.5 py-1 bg-slate-800 text-blue-300 font-mono text-[11px] rounded border border-slate-700">Ctrl+S</kbd>
                                </div>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Alinear Justificado</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-blue-300 font-mono text-xs rounded border border-slate-700">Ctrl + J</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Buscar palabra</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-blue-300 font-mono text-xs rounded border border-slate-700">Ctrl + B / L</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Insertar salto de página</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-blue-300 font-mono text-xs rounded border border-slate-700">Ctrl + Enter</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Aumentar tamaño de fuente</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-blue-300 font-mono text-xs rounded border border-slate-700">Ctrl + &gt;</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Ortografía y Gramática</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-blue-300 font-mono text-xs rounded border border-slate-700">F7</kbd>
                            </li>
                        </ul>
                    </div>

                    <!-- Tarjeta 3: Microsoft Excel -->
                    <div class="bg-slate-900/90 border border-purple-500/30 p-6 rounded-2xl shadow-xl hover:border-purple-500/60 transition-all group">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="w-10 h-10 rounded-xl bg-emerald-600/20 text-emerald-400 flex items-center justify-center font-bold border border-emerald-500/30">
                                <i class="fa-solid fa-file-excel"></i>
                            </div>
                            <h3 class="font-bold text-slate-100 text-base font-mono-code">Microsoft Excel</h3>
                        </div>
                        <ul class="space-y-3 text-xs sm:text-sm">
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Editar celda seleccionada</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-emerald-300 font-mono text-xs rounded border border-slate-700">F2</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Suma automática rápida</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-emerald-300 font-mono text-xs rounded border border-slate-700">Alt + Shift + =</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Insertar fecha actual</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-emerald-300 font-mono text-xs rounded border border-slate-700">Ctrl + ; (punto y coma)</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Insertar hora actual</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-emerald-300 font-mono text-xs rounded border border-slate-700">Ctrl + Shift + :</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Crear gráfico rápido</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-emerald-300 font-mono text-xs rounded border border-slate-700">Alt + F1</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Ir a la celda A1</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-emerald-300 font-mono text-xs rounded border border-slate-700">Ctrl + Inicio</kbd>
                            </li>
                        </ul>
                    </div>

                    <!-- Tarjeta 4: Microsoft PowerPoint -->
                    <div class="bg-slate-900/90 border border-purple-500/30 p-6 rounded-2xl shadow-xl hover:border-purple-500/60 transition-all group">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="w-10 h-10 rounded-xl bg-orange-600/20 text-orange-400 flex items-center justify-center font-bold border border-orange-500/30">
                                <i class="fa-solid fa-file-powerpoint"></i>
                            </div>
                            <h3 class="font-bold text-slate-100 text-base font-mono-code">Microsoft PowerPoint</h3>
                        </div>
                        <ul class="space-y-3 text-xs sm:text-sm">
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Iniciar presentación (desde inicio)</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-amber-300 font-mono text-xs rounded border border-slate-700">F5</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Iniciar desde diapositiva actual</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-amber-300 font-mono text-xs rounded border border-slate-700">Shift + F5</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Nueva diapositiva</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-amber-300 font-mono text-xs rounded border border-slate-700">Ctrl + M</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Agrupar objetos seleccionados</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-amber-300 font-mono text-xs rounded border border-slate-700">Ctrl + G</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Duplicar diapositiva actual</span>
                                <kbd class="px-2 py-1 bg-slate-800 text-amber-300 font-mono text-xs rounded border border-slate-700">Ctrl + D</kbd>
                            </li>
                            <li class="flex items-center justify-between p-2 rounded-lg bg-slate-950/60 border border-slate-800">
                                <span class="text-slate-300">Pantalla en negro / blanca en modo presentación</span>
                                <div class="space-x-1">
                                    <kbd class="px-1.5 py-1 bg-slate-800 text-amber-300 font-mono text-[11px] rounded border border-slate-700">B</kbd>
                                    <kbd class="px-1.5 py-1 bg-slate-800 text-amber-300 font-mono text-[11px] rounded border border-slate-700">W</kbd>
                                </div>
                            </li>
                        </ul>
                    </div>

                </div>

                <div class="mt-8 p-4 bg-purple-950/40 border border-purple-500/30 rounded-xl text-center relative z-10">
                    <p class="text-xs text-purple-300 font-mono">
                        <i class="fa-solid fa-terminal text-amber-400"></i> Tip de Dani y Edwin: Memoriza al menos 3 atajos de cada programa y terminarás tus prácticas de laboratorio con 15 minutos de sobra.
                    </p>
                </div>

            </div>
        </section>

        <!-- ==================== NUEVA PESTAÑA: MINI EXAMEN INTERACTIVO ==================== -->
        <section id="content-examen" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center justify-between gap-3 mb-6 pb-4 border-b border-slate-200 flex-wrap">
                    <div class="flex items-center gap-3">
                        <div class="bg-cyan-600 text-white p-3 rounded-xl shadow">
                            <i class="fa-solid fa-clipboard-question text-2xl"></i>
                        </div>
                        <div>
                            <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Mini Examen Interactivo de Informática</h2>
                            <p class="text-xs sm:text-sm text-slate-600">Pon a prueba tus conocimientos para la Prepa 181 con retroalimentación instantánea.</p>
                        </div>
                    </div>
                    <div id="quiz-score-badge" class="bg-slate-900 text-white px-4 py-2 rounded-xl text-xs font-bold shadow">
                        Aciertos: <span id="current-score" class="text-amber-400 text-sm">0</span> / <span id="total-questions">5</span>
                    </div>
                </div>

                <!-- Contenedor del Quiz -->
                <div id="quiz-container" class="space-y-6">
                    
                    <!-- Pregunta 1 -->
                    <div class="p-5 bg-slate-50 border-2 border-slate-300 rounded-2xl question-card" data-question="1">
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-xs font-bold text-cyan-700 bg-cyan-100 px-2.5 py-1 rounded-full">Pregunta 1 de 5</span>
                            <span class="text-xs text-slate-500 font-medium">Microsoft Word</span>
                        </div>
                        <h3 class="font-bold text-slate-900 text-sm sm:text-base mb-3">
                            ¿Cuál es la combinación de teclas estándar en Windows para copiar un texto seleccionado?
                        </h3>
                        <div class="grid sm:grid-cols-2 gap-2.5 options-group">
                            <button onclick="checkAnswer(1, 'A', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                A) Ctrl + X
                            </button>
                            <button onclick="checkAnswer(1, 'B', true)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                B) Ctrl + C
                            </button>
                            <button onclick="checkAnswer(1, 'C', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                C) Ctrl + V
                            </button>
                            <button onclick="checkAnswer(1, 'D', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                D) Ctrl + Z
                            </button>
                        </div>
                        <div class="feedback-msg mt-3 text-xs font-bold hidden"></div>
                    </div>

                    <!-- Pregunta 2 -->
                    <div class="p-5 bg-slate-50 border-2 border-slate-300 rounded-2xl question-card" data-question="2">
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-xs font-bold text-cyan-700 bg-cyan-100 px-2.5 py-1 rounded-full">Pregunta 2 de 5</span>
                            <span class="text-xs text-slate-500 font-medium">Microsoft Excel</span>
                        </div>
                        <h3 class="font-bold text-slate-900 text-sm sm:text-base mb-3">
                            ¿Con qué carácter obligatorio debe iniciar cualquier fórmula matemática o función en Excel?
                        </h3>
                        <div class="grid sm:grid-cols-2 gap-2.5 options-group">
                            <button onclick="checkAnswer(2, 'A', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                A) El signo de número (#)
                            </button>
                            <button onclick="checkAnswer(2, 'B', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                B) El signo de pesos ($)
                            </button>
                            <button onclick="checkAnswer(2, 'C', true)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                C) El signo igual (=)
                            </button>
                            <button onclick="checkAnswer(2, 'D', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                D) Los dos puntos (:)
                            </button>
                        </div>
                        <div class="feedback-msg mt-3 text-xs font-bold hidden"></div>
                    </div>

                    <!-- Pregunta 3 -->
                    <div class="p-5 bg-slate-50 border-2 border-slate-300 rounded-2xl question-card" data-question="3">
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-xs font-bold text-cyan-700 bg-cyan-100 px-2.5 py-1 rounded-full">Pregunta 3 de 5</span>
                            <span class="text-xs text-slate-500 font-medium">PowerPoint</span>
                        </div>
                        <h3 class="font-bold text-slate-900 text-sm sm:text-base mb-3">
                            ¿Qué tecla de función se utiliza para iniciar una presentación de diapositivas desde el principio (primera diapositiva)?
                        </h3>
                        <div class="grid sm:grid-cols-2 gap-2.5 options-group">
                            <button onclick="checkAnswer(3, 'A', true)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                A) F5
                            </button>
                            <button onclick="checkAnswer(3, 'B', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                B) F7
                            </button>
                            <button onclick="checkAnswer(3, 'C', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                C) F12
                            </button>
                            <button onclick="checkAnswer(3, 'D', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                D) F1
                            </button>
                        </div>
                        <div class="feedback-msg mt-3 text-xs font-bold hidden"></div>
                    </div>

                    <!-- Pregunta 4 -->
                    <div class="p-5 bg-slate-50 border-2 border-slate-300 rounded-2xl question-card" data-question="4">
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-xs font-bold text-cyan-700 bg-cyan-100 px-2.5 py-1 rounded-full">Pregunta 4 de 5</span>
                            <span class="text-xs text-slate-500 font-medium">Excel Avanzado</span>
                        </div>
                        <h3 class="font-bold text-slate-900 text-sm sm:text-base mb-3">
                            ¿Qué función de Excel se utiliza para calcular la media aritmética de un grupo de celdas numéricas?
                        </h3>
                        <div class="grid sm:grid-cols-2 gap-2.5 options-group">
                            <button onclick="checkAnswer(4, 'A', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                A) =SUMA()
                            </button>
                            <button onclick="checkAnswer(4, 'B', true)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                B) =PROMEDIO()
                            </button>
                            <button onclick="checkAnswer(4, 'C', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                C) =MAX()
                            </button>
                            <button onclick="checkAnswer(4, 'D', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                D) =CONTAR()
                            </button>
                        </div>
                        <div class="feedback-msg mt-3 text-xs font-bold hidden"></div>
                    </div>

                    <!-- Pregunta 5 -->
                    <div class="p-5 bg-slate-50 border-2 border-slate-300 rounded-2xl question-card" data-question="5">
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-xs font-bold text-cyan-700 bg-cyan-100 px-2.5 py-1 rounded-full">Pregunta 5 de 5</span>
                            <span class="text-xs text-slate-500 font-medium">Conceptos Generales</span>
                        </div>
                        <h3 class="font-bold text-slate-900 text-sm sm:text-base mb-3">
                            ¿Qué tipo de referencia en Excel evita que una celda fija cambie al arrastrar la fórmula (ej. <code class="font-mono text-cyan-750">$A$1</code>)?
                        </h3>
                        <div class="grid sm:grid-cols-2 gap-2.5 options-group">
                            <button onclick="checkAnswer(5, 'A', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                A) Referencia relativa
                            </button>
                            <button onclick="checkAnswer(5, 'B', true)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                B) Referencia absoluta
                            </button>
                            <button onclick="checkAnswer(5, 'C', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                C) Referencia circular
                            </button>
                            <button onclick="checkAnswer(5, 'D', false)" class="option-btn text-left p-3 rounded-xl border border-slate-300 bg-white hover:bg-cyan-50 text-xs sm:text-sm font-medium transition-all">
                                D) Referencia en bloque
                            </button>
                        </div>
                        <div class="feedback-msg mt-3 text-xs font-bold hidden"></div>
                    </div>

                </div>

                <!-- Botón de Reiniciar Examen -->
                <div class="mt-8 text-center">
                    <button onclick="resetQuiz()" class="bg-slate-900 hover:bg-slate-800 text-white font-bold text-xs sm:text-sm px-6 py-3 rounded-xl transition-all shadow flex items-center justify-center gap-2 mx-auto">
                        <i class="fa-solid fa-rotate-right"></i> Reiniciar Mini Examen
                    </button>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: TIPS EXAMEN ==================== -->
        <section id="content-tips" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-rose-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-graduation-cap text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Tips para Pasar el Examen de Informática</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Recomendaciones clave recopiladas por los creadores para asegurar el 10 en la libreta y en la compu.</p>
                    </div>
                </div>

                <div class="space-y-4">
                    <div class="p-5 bg-rose-50/70 rounded-2xl border-2 border-rose-200">
                        <h3 class="font-bold text-rose-900 text-sm mb-1 flex items-center gap-2">
                            <i class="fa-solid fa-circle-check"></i> 1. Lee bien las instrucciones de la práctica
                        </h3>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            Muchas veces bajamos puntos no por no saber usar Excel o Word, sino porque no pusimos el nombre exacto al archivo, el interlineado que pidió el profesor o la alineación correcta.
                        </p>
                    </div>

                    <div class="p-5 bg-rose-50/70 rounded-2xl border-2 border-rose-200">
                        <h3 class="font-bold text-rose-900 text-sm mb-1 flex items-center gap-2">
                            <i class="fa-solid fa-circle-check"></i> 2. Repasa la sintaxis de las fórmulas
                        </h3>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            En Excel recuerda que toda fórmula inicia con el signo igual (<code class="font-mono text-rose-600 font-bold">=</code>). Si olvidas poner los dos puntos (<code class="font-mono text-rose-600 font-bold">:</code>) en los rangos, te marcará error de sintaxis.
                        </p>
                    </div>

                    <div class="p-5 bg-rose-50/70 rounded-2xl border-2 border-rose-200">
                        <h3 class="font-bold text-rose-900 text-sm mb-1 flex items-center gap-2">
                            <i class="fa-solid fa-circle-check"></i> 3. Guarda respaldos en la nube
                        </h3>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            Evita el coraje de perder tu avance. Sube tu archivo a Google Drive o mándatelo por correo electrónico cada 10 minutos de trabajo en el laboratorio escolar.
                        </p>
                    </div>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: DANI Y EDWIN ==================== -->
        <section id="content-creditos" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-amber-500 text-slate-950 p-3 rounded-xl font-marker text-xl shadow">
                        181
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Sobre los Creadores</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Conoce al equipo detrás de CompuPrep 181.</p>
                    </div>
                </div>

                <div class="grid sm:grid-cols-2 gap-6 mb-8">
                    <!-- Dani -->
                    <div class="bg-slate-50 p-6 rounded-2xl border-2 border-slate-300 text-center space-y-3">
                        <div class="w-16 h-16 bg-blue-600 text-white rounded-full flex items-center justify-center font-bold text-2xl mx-auto shadow">
                            D
                        </div>
                        <h3 class="font-bold text-slate-900 text-lg">Daniela (Dani)</h3>
                        <p class="text-xs text-amber-700 font-bold uppercase tracking-wider">Grupo 3°B • Prepa 181</p>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            Encargada de la redacción de apuntes, diseño de contenidos escolares y recopilación de guías oficiales para el examen.
                        </p>
                    </div>

                    <!-- Edwin -->
                    <div class="bg-slate-50 p-6 rounded-2xl border-2 border-slate-300 text-center space-y-3">
                        <div class="w-16 h-16 bg-emerald-600 text-white rounded-full flex items-center justify-center font-bold text-2xl mx-auto shadow">
                            E
                        </div>
                        <h3 class="font-bold text-slate-900 text-lg">Edwin</h3>
                        <p class="text-xs text-amber-700 font-bold uppercase tracking-wider">Grupo 3°B • Prepa 181</p>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            Programador del portal web, simuladores interactivos y sistemas de optimización y seguridad de la plataforma.
                        </p>
                    </div>
                </div>

                <div class="bg-slate-900 text-white p-6 rounded-2xl border-2 border-slate-800 text-center space-y-3">
                    <h3 class="font-marker text-amber-400 text-xl">"Para que nadie se vaya a extraordinario de Informática"</h3>
                    <p class="text-xs text-slate-300 max-w-xl mx-auto">
                        Este portal es un proyecto estudiantil sin fines de lucro creado con dedicación para todos nuestros compañeros de la Preparatoria Oficial N° 181. ¡Mucho éxito en sus prácticas!
                    </p>
                </div>

            </div>
        </section>

    </main>

    <!-- PIE DE PÁGINA -->
    <footer class="bg-slate-950 text-white border-t border-slate-800 py-8 px-4 mt-12">
        <div class="max-w-6xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-4 text-center sm:text-left">
            <div class="flex items-center gap-3">
                <div class="bg-amber-500 text-slate-950 font-marker px-2.5 py-1 rounded-lg text-sm">
                    181
                </div>
                <div>
                    <p class="text-sm font-bold">CompuPrep 181</p>
                    <p class="text-xs text-slate-400">Creado con orgullo por Dani y Edwin (3°B)</p>
                </div>
            </div>
            <div class="text-xs text-slate-500">
                © 2026 Preparatoria Oficial N° 181 • Todos los derechos reservados.
            </div>
        </div>
    </footer>

    <!-- MODAL DE MENSAJE PERSONALIZADO (CUMPLE CON REGLA DE NO USAR ALERT) -->
    <div id="custom-modal" class="fixed inset-0 bg-slate-950/80 backdrop-blur-sm z-50 hidden items-center justify-center p-4">
        <div class="bg-white text-slate-900 p-6 rounded-2xl border-4 border-slate-900 max-w-sm w-full shadow-2xl text-center space-y-4 transform scale-95 transition-transform" id="modal-content-box">
            <div id="modal-icon" class="w-12 h-12 bg-amber-100 text-amber-600 rounded-2xl flex items-center justify-center font-bold text-xl mx-auto shadow">
                <i class="fa-solid fa-download"></i>
            </div>
            <h3 id="modal-title" class="font-bold text-lg text-slate-900">Aviso de Biblioteca</h3>
            <p id="modal-message" class="text-xs sm:text-sm text-slate-600 leading-relaxed">Mensaje del sistema...</p>
            <button onclick="cerrarModal()" class="w-full bg-slate-900 hover:bg-slate-800 text-white font-bold text-xs py-3 rounded-xl transition-all shadow">
                Entendido
            </button>
        </div>
    </div>

    <!-- SCRIPT DE LÓGICA Y PROTECCIÓN DE CÓDIGO -->
    <script>
        // ==========================================
        // 1. SISTEMA DE PESTAÑAS
        // ==========================================
        function changeTab(tabName) {
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(el => el.classList.add('hidden'));

            const buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(el => el.classList.remove('active'));

            const activeContent = document.getElementById('content-' + tabName);
            if (activeContent) {
                activeContent.classList.remove('hidden');
            }

            const activeBtn = document.getElementById('tab-' + tabName);
            if (activeBtn) {
                activeBtn.classList.add('active');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // ==========================================
        // 2. PROBADOR INTERACTIVO DE WORD
        // ==========================================
        function updateWordPreview() {
            const font = document.getElementById('word-font').value;
            const align = document.getElementById('word-align').value;
            const line = document.getElementById('word-line').value;

            const previewText = document.getElementById('word-preview-text');
            previewText.style.fontFamily = font;
            previewText.style.textAlign = align;
            previewText.style.lineHeight = line;
        }

        // ==========================================
        // 3. SIMULADOR INTERACTIVO DE EXCEL
        // ==========================================
        function calcularPromedioSimulado() {
            const p1 = parseFloat(document.getElementById('calc-p1').value) || 0;
            const p2 = parseFloat(document.getElementById('calc-p2').value) || 0;
            const p3 = parseFloat(document.getElementById('calc-p3').value) || 0;

            const promedio = (p1 + p2 + p3) / 3;
            const resultadoEl = document.getElementById('sim-resultado');
            const estatusEl = document.getElementById('sim-estatus');

            resultadoEl.textContent = promedio.toFixed(1);

            if (promedio >= 6.0) {
                estatusEl.textContent = "¡Aprobado!";
                estatusEl.className = "text-xs font-bold text-emerald-400";
            } else {
                estatusEl.textContent = "Reprobado (Requiere regularización)";
                estatusEl.className = "text-xs font-bold text-rose-400";
            }
        }

        // ==========================================
        // 4. LÓGICA DEL MINI EXAMEN INTERACTIVO
        // ==========================================
        let answeredQuestions = {};
        let score = 0;

        function checkAnswer(questionNum, selectedOption, isCorrect) {
            const card = document.querySelector(`.question-card[data-question="${questionNum}"]`);
            if (answeredQuestions[questionNum]) return; // Ya respondida

            answeredQuestions[questionNum] = true;
            const buttons = card.querySelectorAll('.option-btn');
            const feedback = card.querySelector('.feedback-msg');

            // Deshabilitar botones de esta pregunta
            buttons.forEach(btn => {
                btn.disabled = true;
                btn.classList.add('opacity-70', 'cursor-not-allowed');
            });

            feedback.classList.remove('hidden');

            if (isCorrect) {
                score++;
                feedback.textContent = "¡Correcto! Muy bien respondido.";
                feedback.className = "feedback-msg mt-3 text-xs font-bold text-emerald-600 bg-emerald-50 p-2.5 rounded-lg border border-emerald-200";
                
                // Resaltar botón correcto
                buttons.forEach(btn => {
                    if (btn.textContent.trim().startsWith(selectedOption)) {
                        btn.classList.remove('bg-white', 'hover:bg-cyan-50');
                        btn.classList.add('bg-emerald-600', 'text-white', 'border-emerald-700');
                    }
                });
            } else {
                feedback.textContent = "Incorrecto. Revisa los apuntes de la materia para repasar este tema.";
                feedback.className = "feedback-msg mt-3 text-xs font-bold text-rose-600 bg-rose-50 p-2.5 rounded-lg border border-rose-200";
                
                // Resaltar botón elegido incorrecto
                buttons.forEach(btn => {
                    if (btn.textContent.trim().startsWith(selectedOption)) {
                        btn.classList.remove('bg-white', 'hover:bg-cyan-50');
                        btn.classList.add('bg-rose-600', 'text-white', 'border-rose-700');
                    }
                });
            }

            // Actualizar marcador
            document.getElementById('current-score').textContent = score;
        }

        function resetQuiz() {
            answeredQuestions = {};
            score = 0;
            document.getElementById('current-score').textContent = score;

            const cards = document.querySelectorAll('.question-card');
            cards.forEach(card => {
                const buttons = card.querySelectorAll('.option-btn');
                buttons.forEach(btn => {
                    btn.disabled = false;
                    btn.classList.remove('opacity-70', 'cursor-not-allowed', 'bg-emerald-600', 'text-white', 'border-emerald-700', 'bg-rose-600', 'border-rose-700');
                    btn.classList.add('bg-white', 'hover:bg-cyan-50');
                });

                const feedback = card.querySelector('.feedback-msg');
                feedback.classList.add('hidden');
                feedback.textContent = "";
            });
        }

        // ==========================================
        // 5. MODAL PERSONALIZADO (SIN ALERT)
        // ==========================================
        function mostrarAvisoDescarga(nombreGuia) {
            const modal = document.getElementById('custom-modal');
            const modalTitle = document.getElementById('modal-title');
            const modalMessage = document.getElementById('modal-message');

            modalTitle.textContent = "Descarga de Biblioteca 181";
            modalMessage.innerHTML = `Estás descargando el archivo <b>"${nombreGuia}"</b> en formato PDF. Recuerda guardarlo en tu memoria USB o carpeta de la Prepa 181.`;

            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function cerrarModal() {
            const modal = document.getElementById('custom-modal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        // ==========================================
        // 6. MEDIDA DE PROTECCIÓN DE CÓDIGO AVANZADA
        // ==========================================
        document.addEventListener('contextmenu', function (e) {
            e.preventDefault();
            return false;
        });

        document.addEventListener('keydown', function (e) {
            if (e.keyCode === 123) { // F12
                e.preventDefault();
                return false;
            }
            if (e.ctrlKey && e.shiftKey && (e.keyCode === 73 || e.keyCode === 74 || e.keyCode === 67)) {
                e.preventDefault();
                return false;
            }
            if (e.ctrlKey && e.keyCode === 85) { // Ctrl + U
                e.preventDefault();
                return false;
            }
            if (e.ctrlKey && e.keyCode === 83) { // Ctrl + S
                e.preventDefault();
                return false;
            }
        });
    </script>
</body>
</html>
```
eof
