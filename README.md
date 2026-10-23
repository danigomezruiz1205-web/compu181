[compuprep_181_portal_educativo.html](https://github.com/user-attachments/files/33893123/compuprep_181_portal_educativo.html)
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
    <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Permanent+Marker&family=Inter:ital,wght@0,400;0,600;0,700;0,800;1,400&display=swap" rel="stylesheet">
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
<body class="min-h-screen flex flex-col selection:bg-amber-200 selection:text-amber-900">

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
                    Armamos este sitio entre los dos para subir resúmenes, las fórmulas de Excel que siempre se nos olvidan en los exámenees y los trucos para que el profe no te rebaje puntos por el formato.
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
                            ¡Novedad!
                        </span>
                        <h3 class="text-xl font-bold text-slate-900 mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-bullhorn text-amber-500"></i> ¿Por qué hicimos esta página?
                        </h3>
                        <p class="text-sm text-slate-700 leading-relaxed mb-4">
                            En la sala de cómputo siempre pasa lo mismo: a la mitad de la práctica a alguien se le desacomoda la tabla en Word, a otro le sale el error <code class="bg-slate-100 text-rose-600 font-mono px-1 border border-slate-300">#¡VALOR!</code> en Excel, o nadie se acuerda de la fórmula del promedio. 
                        </p>
                        <p class="text-sm text-slate-700 leading-relaxed">
                            Por eso resumimos aquí todo lo que pide el profe en el temario, explicado directo, sin rodeos y con probadores interactivos para practicar antes de entregar el trabajo.
                        </p>
                    </div>

                    <!-- Cuadrícula de acceso rápido -->
                    <div class="grid sm:grid-cols-2 gap-4">
                        <div onclick="changeTab('word')" class="cursor-pointer bg-blue-50 hover:bg-blue-100/80 p-5 rounded-2xl border-2 border-blue-900 shadow-md transition-all transform hover:-translate-y-1">
                            <div class="bg-blue-600 text-white w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3 shadow">
                                <i class="fa-solid fa-file-word text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base">Guía de Microsoft Word</h4>
                            <p class="text-xs text-slate-600 mt-1">Probador de fuentes APA, márgenes, sangría y cómo acomodar imágenes sin que se mueva todo.</p>
                        </div>

                        <div onclick="changeTab('excel')" class="cursor-pointer bg-emerald-50 hover:bg-emerald-100/80 p-5 rounded-2xl border-2 border-emerald-900 shadow-md transition-all transform hover:-translate-y-1">
                            <div class="bg-emerald-600 text-white w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3 shadow">
                                <i class="fa-solid fa-file-excel text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base">Calculadora & Excel</h4>
                            <p class="text-xs text-slate-600 mt-1">Calcula tu promedio de la prepa con el simulador e imita las fórmulas exactas para tus prácticas.</p>
                        </div>

                        <div onclick="changeTab('powerpoint')" class="cursor-pointer bg-orange-50 hover:bg-orange-100/80 p-5 rounded-2xl border-2 border-orange-900 shadow-md transition-all transform hover:-translate-y-1">
                            <div class="bg-orange-600 text-white w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3 shadow">
                                <i class="fa-solid fa-file-powerpoint text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base">PowerPoint sin Aburrir</h4>
                            <p class="text-xs text-slate-600 mt-1">Regla 6x6 para diapositivas, animaciones discretas y cómo proyectar sin perder tus notas.</p>
                        </div>

                        <div onclick="changeTab('atajos')" class="cursor-pointer bg-purple-50 hover:bg-purple-100/80 p-5 rounded-2xl border-2 border-purple-900 shadow-md transition-all transform hover:-translate-y-1">
                            <div class="bg-purple-600 text-white w-10 h-10 rounded-xl flex items-center justify-center font-bold mb-3 shadow">
                                <i class="fa-solid fa-keyboard text-lg"></i>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base">Atajos de Teclado Rápidos</h4>
                            <p class="text-xs text-slate-600 mt-1">Aprende combinaciones de teclas para terminar tus prácticas en la mitad de tiempo.</p>
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
                                <span><b>Examen del Parcial:</b> No olviden repasar la sección de fórmulas de Excel y formatos de texto.</span>
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

        <!-- ==================== PESTAÑA: WORD ==================== -->
        <section id="content-word" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-blue-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-file-word text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Microsoft Word: Trucos y Formato APA</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Aprende a estructurar tus reportes sin pelearte con las imágenes ni los márgenes.</p>
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

                <!-- Cuadros explicativos -->
                <div class="grid sm:grid-cols-2 gap-4">
                    <div class="bg-blue-50/60 p-4 rounded-xl border border-blue-200">
                        <h4 class="font-bold text-blue-900 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-list-ol"></i> Cómo hacer índice automático
                        </h4>
                        <ol class="text-xs text-slate-700 space-y-1.5 list-decimal list-inside">
                            <li>Selecciona el título de cada tema y aplícale el estilo <b>Título 1</b>.</li>
                            <li>A los subtítulos aplícales el estilo <b>Título 2</b>.</li>
                            <li>Ve a la pestaña <b>Referencias > Tabla de contenido</b> y elige la primera opción.</li>
                        </ol>
                    </div>

                    <div class="bg-blue-50/60 p-4 rounded-xl border border-blue-200">
                        <h4 class="font-bold text-blue-900 text-sm mb-2 flex items-center gap-2">
                            <i class="fa-solid fa-file-export"></i> Para guardar en PDF
                        </h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            No le saques fotos a la pantalla. Ve a <b>Archivo > Guardar como</b>, cambia el tipo de documento a <b>PDF (*.pdf)</b> y listo. Así el formato no se mueve cuando el profe lo abra en su compu.
                        </p>
                    </div>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: EXCEL ==================== -->
        <section id="content-excel" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-emerald-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-file-excel text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Microsoft Excel: Fórmulas que sí sirven</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Aprende a usar las celdas sin miedo a que te marque error.</p>
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
                    <i class="fa-solid fa-code text-emerald-600"></i> Las 4 fórmulas que vienen en el examen
                </h3>

                <div class="grid sm:grid-cols-2 gap-4">
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

            </div>
        </section>

        <!-- ==================== PESTAÑA: POWERPOINT ==================== -->
        <section id="content-powerpoint" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-orange-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-file-powerpoint text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">PowerPoint: Exposiciones de 10</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Presentaciones limpias para exponer frente al grupo sin leer diapositivas.</p>
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
                            Presiona <kbd class="px-1.5 py-0.5 bg-white border border-slate-300 rounded text-[11px]">F5</kbd> para iniciar desde la primera diapositiva, o <kbd class="px-1.5 py-0.5 bg-white border border-slate-300 rounded text-[11px]">Shift + F5</kbd> para iniciar justo en la que estás editando.
                        </p>
                    </div>

                    <div class="p-5 bg-orange-50/70 rounded-2xl border-2 border-orange-200">
                        <div class="text-orange-600 font-marker text-2xl mb-1">Tecla B y W</div>
                        <h4 class="font-bold text-slate-900 text-sm mb-2">Modo pausa en vivo</h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            Durante la exposición presiona la tecla <kbd class="px-1.5 py-0.5 bg-white border border-slate-300 rounded text-[11px]">B</kbd> para poner la pantalla en negro (Black) o <kbd class="px-1.5 py-0.5 bg-white border border-slate-300 rounded text-[11px]">W</kbd> para ponerla en blanco (White) y recuperar la atención.
                        </p>
                    </div>
                </div>

                <div class="bg-amber-100/80 p-5 rounded-2xl border border-amber-300 text-slate-800 text-xs sm:text-sm">
                    <p class="font-bold text-amber-950 mb-1 flex items-center gap-2">
                        <i class="fa-solid fa-lightbulb text-amber-700"></i> Consejo de Dani para exponer:
                    </p>
                    <p>Usa colores con buen contraste: fondo claro con texto oscuro (o viceversa). Si usas fondo azul rey con letras rojas, no se va a ver nada en el proyector del salón.</p>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: BIBLIOTECA Y PDFS ==================== -->
        <section id="content-pdf" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-rose-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-folder-open text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Biblioteca Digital de PDFs y Guías</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Material de lectura oficial descargable recopilado por Dani y Edwin.</p>
                    </div>
                </div>

                <!-- Nota informativa -->
                <div class="bg-amber-50 border-l-4 border-amber-500 p-4 rounded-r-xl text-xs sm:text-sm text-slate-700 mb-6 flex items-start gap-3">
                    <i class="fa-solid fa-circle-info text-amber-600 text-lg mt-0.5"></i>
                    <div>
                        <p class="font-bold text-amber-900 mb-0.5">Nota de Dani y Edwin:</p>
                        <p>Recopilamos estos manuales de fuentes oficiales e instituciones (UNAM, IPN, Microsoft) para que puedas estudiar con archivos descargables en tu cel o compu sin gastar datos en el laboratorio.</p>
                    </div>
                </div>

                <!-- Tarjetas de PDFs Descargables -->
                <h3 class="font-bold text-slate-900 text-lg mb-4 flex items-center gap-2">
                    <i class="fa-solid fa-file-pdf text-rose-600"></i> Guías Descargables y Manuales
                </h3>

                <div class="grid sm:grid-cols-2 gap-4 mb-8">
                    
                    <!-- PDF Card 1 -->
                    <div class="p-5 bg-slate-50 rounded-2xl border-2 border-slate-200 hover:border-slate-800 transition-all flex flex-col justify-between shadow-sm">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="bg-rose-100 text-rose-700 font-bold text-[10px] uppercase px-2.5 py-0.5 rounded-full border border-rose-200">PDF Oficial</span>
                                <span class="text-xs text-slate-400 font-mono">1.2 MB</span>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base mb-1">Guía Rápida de Formato APA (7ma Edición)</h4>
                            <p class="text-xs text-slate-600 mb-4 leading-relaxed">
                                Documento con la estructura requerida para citar fuentes, márgenes, sangrías y portada estandarizada para tareas escolares.
                            </p>
                        </div>
                        <div class="flex items-center gap-2 pt-3 border-t border-slate-200">
                            <a href="https://www.cch.unam.mx/comunicacion/sites/www.cch.unam.mx.comunicacion/files/guia_apa_7ma_edicion.pdf" target="_blank" rel="noopener noreferrer" class="flex-1 text-center bg-rose-600 hover:bg-rose-700 text-white font-bold text-xs py-2 px-3 rounded-lg transition-colors flex items-center justify-center gap-2">
                                <i class="fa-solid fa-file-arrow-down"></i> Descargar PDF
                            </a>
                            <a href="https://www.cch.unam.mx/comunicacion/sites/www.cch.unam.mx.comunicacion/files/guia_apa_7ma_edicion.pdf" target="_blank" rel="noopener noreferrer" class="bg-slate-200 hover:bg-slate-300 text-slate-800 font-bold text-xs py-2 px-3 rounded-lg transition-colors">
                                <i class="fa-solid fa-arrow-up-right-from-square"></i>
                            </a>
                        </div>
                    </div>

                    <!-- PDF Card 2 -->
                    <div class="p-5 bg-slate-50 rounded-2xl border-2 border-slate-200 hover:border-slate-800 transition-all flex flex-col justify-between shadow-sm">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="bg-emerald-100 text-emerald-700 font-bold text-[10px] uppercase px-2.5 py-0.5 rounded-full border border-emerald-200">Manual Excel</span>
                                <span class="text-xs text-slate-400 font-mono">2.4 MB</span>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base mb-1">Compendio de Fórmulas y Funciones de Excel</h4>
                            <p class="text-xs text-slate-600 mb-4 leading-relaxed">
                                Guía con ejemplos visuales de sintaxis para las funciones <code>PROMEDIO</code>, <code>SUMA</code>, <code>SI</code>, <code>BUSCARV</code> y gráficos básicos.
                            </p>
                        </div>
                        <div class="flex items-center gap-2 pt-3 border-t border-slate-200">
                            <a href="https://support.microsoft.com/es-es/office/funciones-de-excel-por-categor%C3%ADa-5f0d062b-1031-4b13-89f5-4771136e32a1" target="_blank" rel="noopener noreferrer" class="flex-1 text-center bg-emerald-600 hover:bg-emerald-700 text-white font-bold text-xs py-2 px-3 rounded-lg transition-colors flex items-center justify-center gap-2">
                                <i class="fa-solid fa-book-open"></i> Ver en Microsoft
                            </a>
                        </div>
                    </div>

                    <!-- PDF Card 3 -->
                    <div class="p-5 bg-slate-50 rounded-2xl border-2 border-slate-200 hover:border-slate-800 transition-all flex flex-col justify-between shadow-sm">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="bg-blue-100 text-blue-700 font-bold text-[10px] uppercase px-2.5 py-0.5 rounded-full border border-blue-200">Manual Word</span>
                                <span class="text-xs text-slate-400 font-mono">1.8 MB</span>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base mb-1">Manual de Procesador de Textos Básicos</h4>
                            <p class="text-xs text-slate-600 mb-4 leading-relaxed">
                                Tutorial ilustrado paso a paso sobre tabuladores, índices automáticos, encabezados y pie de página en Microsoft Word.
                            </p>
                        </div>
                        <div class="flex items-center gap-2 pt-3 border-t border-slate-200">
                            <a href="https://www.ipn.mx" target="_blank" rel="noopener noreferrer" class="flex-1 text-center bg-blue-600 hover:bg-blue-700 text-white font-bold text-xs py-2 px-3 rounded-lg transition-colors flex items-center justify-center gap-2">
                                <i class="fa-solid fa-graduation-cap"></i> Portal IPN
                            </a>
                        </div>
                    </div>

                    <!-- PDF Card 4 -->
                    <div class="p-5 bg-slate-50 rounded-2xl border-2 border-slate-200 hover:border-slate-800 transition-all flex flex-col justify-between shadow-sm">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="bg-orange-100 text-orange-700 font-bold text-[10px] uppercase px-2.5 py-0.5 rounded-full border border-orange-200">Exposición</span>
                                <span class="text-xs text-slate-400 font-mono">950 KB</span>
                            </div>
                            <h4 class="font-bold text-slate-900 text-base mb-1">Guía para Presentaciones Efectivas</h4>
                            <p class="text-xs text-slate-600 mb-4 leading-relaxed">
                                Consejos para diseño visual, contraste de color, estructura narrativa y cómo exponer sin leer las diapositivas.
                            </p>
                        </div>
                        <div class="flex items-center gap-2 pt-3 border-t border-slate-200">
                            <a href="https://www.unam.mx" target="_blank" rel="noopener noreferrer" class="flex-1 text-center bg-orange-600 hover:bg-orange-700 text-white font-bold text-xs py-2 px-3 rounded-lg transition-colors flex items-center justify-center gap-2">
                                <i class="fa-solid fa-building-columns"></i> Portal UNAM
                            </a>
                        </div>
                    </div>

                </div>

                <!-- CRÉDITOS Y RECURSOS ACADÉMICOS -->
                <h3 class="font-bold text-slate-900 text-lg mb-4 flex items-center gap-2">
                    <i class="fa-solid fa-award text-amber-500"></i> Créditos e Instituciones Colaboradoras
                </h3>

                <div class="grid sm:grid-cols-3 gap-4">
                    <div class="p-4 bg-amber-50/80 rounded-xl border-2 border-amber-200 text-center">
                        <div class="w-10 h-10 bg-amber-500 text-slate-950 font-bold rounded-full flex items-center justify-center mx-auto mb-2 text-sm shadow">
                            UNAM
                        </div>
                        <h4 class="font-bold text-slate-900 text-xs">CCH / DGEP UNAM</h4>
                        <p class="text-[11px] text-slate-600 mt-1">Fuente oficial de los lineamientos del formato APA 7ma edición.</p>
                    </div>

                    <div class="p-4 bg-amber-50/80 rounded-xl border-2 border-amber-200 text-center">
                        <div class="w-10 h-10 bg-slate-900 text-amber-400 font-bold rounded-full flex items-center justify-center mx-auto mb-2 text-sm shadow">
                            IPN
                        </div>
                        <h4 class="font-bold text-slate-900 text-xs">Instituto Politécnico Nacional</h4>
                        <p class="text-[11px] text-slate-600 mt-1">Recursos de nivel medio superior para laboratorios de informática.</p>
                    </div>

                    <div class="p-4 bg-amber-50/80 rounded-xl border-2 border-amber-200 text-center">
                        <div class="w-10 h-10 bg-blue-600 text-white font-bold rounded-full flex items-center justify-center mx-auto mb-2 text-sm shadow">
                            MS
                        </div>
                        <h4 class="font-bold text-slate-900 text-xs">Microsoft Learn</h4>
                        <p class="text-[11px] text-slate-600 mt-1">Documentación oficial de ayuda para Word, Excel y PowerPoint.</p>
                    </div>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: ATAJOS ==================== -->
        <section id="content-atajos" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-purple-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-keyboard text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Atajos de Teclado Indispensables</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Para terminar rápido tus trabajos e irte temprano al receso.</p>
                    </div>
                </div>

                <div class="grid sm:grid-cols-2 md:grid-cols-3 gap-4">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-300 flex items-center gap-3">
                        <kbd class="px-2.5 py-1.5 bg-slate-800 text-white rounded font-mono text-xs font-bold shrink-0">Ctrl + C</kbd>
                        <span class="text-xs text-slate-700 font-semibold">Copiar lo seleccionado</span>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-300 flex items-center gap-3">
                        <kbd class="px-2.5 py-1.5 bg-slate-800 text-white rounded font-mono text-xs font-bold shrink-0">Ctrl + V</kbd>
                        <span class="text-xs text-slate-700 font-semibold">Pegar lo copiado</span>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-300 flex items-center gap-3">
                        <kbd class="px-2.5 py-1.5 bg-slate-800 text-white rounded font-mono text-xs font-bold shrink-0">Ctrl + Z</kbd>
                        <span class="text-xs text-slate-700 font-semibold">Deshacer el último error</span>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-300 flex items-center gap-3">
                        <kbd class="px-2.5 py-1.5 bg-slate-800 text-white rounded font-mono text-xs font-bold shrink-0">Ctrl + E</kbd>
                        <span class="text-xs text-slate-700 font-semibold">Seleccionar todo el documento</span>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-300 flex items-center gap-3">
                        <kbd class="px-2.5 py-1.5 bg-slate-800 text-white rounded font-mono text-xs font-bold shrink-0">Ctrl + G</kbd>
                        <span class="text-xs text-slate-700 font-semibold">Guardar cambios rápidos</span>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-300 flex items-center gap-3">
                        <kbd class="px-2.5 py-1.5 bg-slate-800 text-white rounded font-mono text-xs font-bold shrink-0">Ctrl + N</kbd>
                        <span class="text-xs text-slate-700 font-semibold">Poner texto en Negrita</span>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-300 flex items-center gap-3">
                        <kbd class="px-2.5 py-1.5 bg-slate-800 text-white rounded font-mono text-xs font-bold shrink-0">Alt + Tab</kbd>
                        <span class="text-xs text-slate-700 font-semibold">Cambiar de ventana rápidamente</span>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-300 flex items-center gap-3">
                        <kbd class="px-2.5 py-1.5 bg-slate-800 text-white rounded font-mono text-xs font-bold shrink-0">Windows + L</kbd>
                        <span class="text-xs text-slate-700 font-semibold">Bloquear la pantalla si te paras</span>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-300 flex items-center gap-3">
                        <kbd class="px-2.5 py-1.5 bg-slate-800 text-white rounded font-mono text-xs font-bold shrink-0">Ctrl + Shift + Esc</kbd>
                        <span class="text-xs text-slate-700 font-semibold">Abrir Administrador de tareas</span>
                    </div>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: TIPS EXAMEN ==================== -->
        <section id="content-examen" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)]">
                
                <div class="flex items-center gap-3 mb-6 pb-4 border-b border-slate-200">
                    <div class="bg-rose-600 text-white p-3 rounded-xl shadow">
                        <i class="fa-solid fa-graduation-cap text-2xl"></i>
                    </div>
                    <div>
                        <h2 class="text-xl sm:text-2xl font-bold text-slate-900">Guía Práctica para el Examen</h2>
                        <p class="text-xs sm:text-sm text-slate-600">Conceptos teóricos que siempre vienen en la prueba escrita.</p>
                    </div>
                </div>

                <div class="space-y-4">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h4 class="font-bold text-slate-900 text-sm mb-1 flex items-center gap-2">
                            <span class="bg-rose-500 text-white text-xs px-2 py-0.5 rounded font-bold">1</span> Hardware vs Software
                        </h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            <b>Hardware:</b> Lo que puedes tocar físicamente (Teclado, Mouse, Monitor, Disco Duro, RAM).<br>
                            <b>Software:</b> Los programas e instrucciones que no puedes tocar físicamente (Windows, Word, Navegador, Excel).
                        </p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h4 class="font-bold text-slate-900 text-sm mb-1 flex items-center gap-2">
                            <span class="bg-rose-500 text-white text-xs px-2 py-0.5 rounded font-bold">2</span> Dispositivos de Entrada y Salida
                        </h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            <b>Entrada (meten datos):</b> Teclado, Mouse, Micrófono, Escáner, Cámara.<br>
                            <b>Salida (muestran datos):</b> Monitor, Impresora, Bocinas, Proyector.
                        </p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <h4 class="font-bold text-slate-900 text-sm mb-1 flex items-center gap-2">
                            <span class="bg-rose-500 text-white text-xs px-2 py-0.5 rounded font-bold">3</span> Memoria RAM vs Disco Duro
                        </h4>
                        <p class="text-xs text-slate-700 leading-relaxed">
                            La <b>RAM</b> es la memoria temporal de trabajo (se borra si apagas la compu). El <b>Disco Duro</b> guarda tus archivos permanentemente.
                        </p>
                    </div>
                </div>

            </div>
        </section>

        <!-- ==================== PESTAÑA: CRÉDITOS DANI Y EDWIN ==================== -->
        <section id="content-creditos" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 sm:p-8 rounded-2xl border-2 border-slate-800 shadow-[4px_4px_0px_0px_rgba(15,23,42,1)] text-center max-w-2xl mx-auto">
                
                <div class="bg-amber-400 text-slate-950 w-20 h-20 rounded-3xl flex items-center justify-center mx-auto mb-4 font-marker text-3xl shadow-md transform -rotate-3">
                    D&E
                </div>

                <h2 class="text-2xl sm:text-3xl font-extrabold text-slate-900 mb-2">
                    Creado por Dani y Edwin
                </h2>
                
                <p class="text-xs sm:text-sm text-slate-600 leading-relaxed mb-6">
                    Somos estudiantes de la Preparatoria N° 181. Desarrollamos este portal educativo para reunir los temas del programa de Informática, atajos útiles y herramientas interactivas que nos sirvan a todos durante el ciclo escolar.
                </p>

                <div class="grid sm:grid-cols-2 gap-4 mb-6 text-left">
                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <div class="font-bold text-slate-900 text-sm mb-1 flex items-center gap-2">
                            <i class="fa-solid fa-code text-blue-600"></i> Dani
                        </div>
                        <p class="text-xs text-slate-600">Encargado de la estructura web, diseño visual y probadores interactivos en JavaScript.</p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-xl border border-slate-200">
                        <div class="font-bold text-slate-900 text-sm mb-1 flex items-center gap-2">
                            <i class="fa-solid fa-pen-nib text-amber-600"></i> Edwin
                        </div>
                        <p class="text-xs text-slate-600">Encargado de los resúmenes de temas, recopilación de fórmulas de Excel y tips de examen.</p>
                    </div>
                </div>

                <div class="inline-flex items-center gap-2 px-4 py-2 bg-slate-900 text-amber-400 rounded-xl text-xs font-bold">
                    <i class="fa-solid fa-school"></i> Preparatoria N° 181 • Proyecto de Informática
                </div>

            </div>
        </section>

    </main>

    <!-- PIE DE PÁGINA PÚBLICO DESTACADO -->
    <footer class="bg-slate-950 text-slate-400 py-8 border-t-4 border-amber-500 mt-auto">
        <div class="max-w-6xl mx-auto px-4 text-center space-y-3">
            <div class="flex items-center justify-center gap-2 text-white font-bold text-base">
                <i class="fa-solid fa-laptop-code text-amber-400"></i> CompuPrep 181
            </div>
            <p class="text-xs sm:text-sm text-slate-300 font-medium">
                Página web educativa creada por <strong class="text-amber-400">Dani y Edwin</strong> • Preparatoria N° 181
            </p>
            <p class="text-[11px] text-slate-500">
                Diseñado para la materia de Informática. Libre de contenidos genéricos.
            </p>
        </div>
    </footer>

    <!-- LÓGICA DE INTERACCIÓN -->
    <script>
        // Navegación entre pestañas
        function changeTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(el => {
                el.classList.add('hidden');
                el.classList.remove('block');
            });
            
            document.querySelectorAll('.tab-btn').forEach(el => {
                el.classList.remove('active');
            });
            
            const targetContent = document.getElementById('content-' + tabId);
            if (targetContent) {
                targetContent.classList.remove('hidden');
                targetContent.classList.add('block');
            }
            
            const targetTab = document.getElementById('tab-' + tabId);
            if (targetTab) {
                targetTab.classList.add('active');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Actualizador del taller de Word
        function updateWordPreview() {
            const font = document.getElementById('word-font').value;
            const align = document.getElementById('word-align').value;
            const line = document.getElementById('word-line').value;
            
            const textElem = document.getElementById('word-preview-text');
            if (textElem) {
                textElem.style.fontFamily = font;
                textElem.style.textAlign = align;
                textElem.style.lineHeight = line;
            }
        }

        // Simulador de promedio de calificaciones para Excel
        function calcularPromedioSimulado() {
            const p1 = parseFloat(document.getElementById('calc-p1').value) || 0;
            const p2 = parseFloat(document.getElementById('calc-p2').value) || 0;
            const p3 = parseFloat(document.getElementById('calc-p3').value) || 0;
            
            const promedio = (p1 + p2 + p3) / 3;
            const resElem = document.getElementById('sim-resultado');
            const estatusElem = document.getElementById('sim-estatus');
            
            if (resElem) {
                resElem.innerText = promedio.toFixed(1);
            }
            
            if (estatusElem) {
                if (promedio >= 6) {
                    estatusElem.innerText = "¡Aprobado! (=SI(PROMEDIO>=6))";
                    estatusElem.className = "text-xs font-bold text-emerald-400";
                } else {
                    estatusElem.innerText = "Reprobado (=SI(PROMEDIO<6))";
                    estatusElem.className = "text-xs font-bold text-rose-400";
                }
            }
        }
    </script>
</body>
</html>
