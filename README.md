[index.html.txt](https://github.com/user-attachments/files/32673434/index.html.txt)
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PathTeacher PGSD | Media Informasi Karier Guru SD Masa Kini</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts: Audiowide (Y2K) & Plus Jakarta Sans (Heading & Body) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Audiowide&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Marked.js untuk memformat output Markdown dari AI -->
    <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>

    <!-- Tailwind Configuration -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['"Plus Jakarta Sans"', 'sans-serif'],
                        display: ['"Plus Jakarta Sans"', 'sans-serif'],
                    },
                    colors: {
                        // Soft Pink and Blue Palette
                        primary: {
                            50: '#fdf2f8',
                            100: '#fce7f3',
                            500: '#ec4899',
                            600: '#db2777',
                            700: '#be185d',
                            900: '#831843',
                        }
                    }
                }
            }
        }
    </script>

    <style>
        /* Custom Styles for Timeline */
        .timeline-container {
            position: relative;
        }
        .timeline-container::after {
            content: '';
            position: absolute;
            width: 4px;
            background-color: #fce7f3; /* pink-100 */
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -2px;
            border-radius: 4px;
        }
        .timeline-item {
            position: relative;
            background-color: inherit;
            width: 50%;
        }
        .timeline-item.left {
            left: 0;
        }
        .timeline-item.right {
            left: 50%;
        }
        .timeline-item::after {
            content: '';
            position: absolute;
            width: 24px;
            height: 24px;
            right: -12px;
            background-color: white;
            border: 4px solid #db2777; /* pink-600 */
            top: 15px;
            border-radius: 50%;
            z-index: 1;
        }
        .timeline-item.right::after {
            left: -12px;
        }
        
        @media screen and (max-width: 768px) {
            .timeline-container::after {
                left: 31px;
            }
            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }
            .timeline-item.left, .timeline-item.right {
                left: 0;
            }
            .timeline-item.left::after, .timeline-item.right::after {
                left: 19px;
            }
        }

        html { scroll-behavior: smooth; }
        
        .fade-in { opacity: 0; transform: translateY(20px); transition: opacity 0.6s ease-out, transform 0.6s ease-out; }
        .fade-in.appear { opacity: 1; transform: translateY(0); }

        .custom-scrollbar::-webkit-scrollbar {
            height: 8px;
            width: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: #f8fafc;
            border-radius: 8px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 8px;
        }
        
        .tab-btn {
            border-color: transparent;
            background-color: #f8fafc;
            color: #475569;
            transition: all 0.3s ease;
        }
        .tab-btn:hover {
            background-color: #f1f5f9;
        }
        .tab-btn.active {
            border-color: #db2777;
            background-color: #ffffff;
            color: #be185d;
            box-shadow: 0 10px 25px -5px rgba(236, 72, 153, 0.15);
        }
        .tab-content {
            display: none;
            animation: fadeInTab 0.5s ease-out forwards;
        }
        .tab-content.active {
            display: block;
        }
        @keyframes fadeInTab {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .accordion-content {
            transition: max-height 0.3s ease-in-out, opacity 0.3s ease-in-out;
            max-height: 0;
            opacity: 0;
            overflow: hidden;
        }
        .accordion-content.open {
            max-height: 1000px;
            opacity: 1;
        }

        /* Cozy Y2K Curtain Intro Animation Styles */
        #intro-curtains {
            transition: opacity 0.8s ease;
        }
        #curtain-left {
            transition: transform 1.2s cubic-bezier(0.77, 0, 0.175, 1);
        }
        #curtain-right {
            transition: transform 1.2s cubic-bezier(0.77, 0, 0.175, 1);
        }
        .curtain-open #curtain-left {
            transform: translateX(-100%);
        }
        .curtain-open #curtain-right {
            transform: translateX(100%);
        }
        
        /* Glassmorphism utility */
        .glass-panel {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.5);
        }

        /* Hanging Sign Y2K Cyber Style */
        .y2k-cyber-text {
            font-family: 'Audiowide', sans-serif;
            color: #ec4899; /* pink-500 */
            -webkit-text-stroke: 3px #ffffff;
            text-shadow: 6px 6px 0px #3b82f6; /* blue-500 */
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        @media screen and (max-width: 768px) {
            .y2k-cyber-text {
                -webkit-text-stroke: 2px #ffffff;
                text-shadow: 4px 4px 0px #3b82f6;
            }
        }

        /* Smaller Y2K Cyber Style for Navbar and Footer Logo */
        .y2k-cyber-text-sm {
            font-family: 'Audiowide', sans-serif;
            color: #ec4899;
            -webkit-text-stroke: 1px #ffffff;
            text-shadow: 2px 2px 0px #3b82f6;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        .hanging-sign {
            position: relative;
            display: inline-block;
            transform-origin: top center;
            animation: swing-sign 3s ease-in-out infinite alternate;
            padding-top: 40px;
            margin-bottom: 2rem;
            z-index: 40;
        }
        
        .rope {
            position: absolute;
            top: -150px; /* Connects out of screen */
            width: 4px;
            height: 190px;
            background: repeating-linear-gradient(
                45deg,
                #cbd5e1,
                #cbd5e1 5px,
                #94a3b8 5px,
                #94a3b8 10px
            );
            z-index: -1;
            box-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }
        .rope.left { left: 15%; }
        .rope.right { right: 15%; }

        .rope::after {
            content: '';
            position: absolute;
            bottom: -6px;
            left: -4px;
            width: 12px;
            height: 12px;
            background: #94a3b8;
            border: 2px solid white;
            border-radius: 50%;
            box-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }

        @keyframes swing-sign {
            0% { transform: rotate(4deg); }
            100% { transform: rotate(-4deg); }
        }

        /* Single Tarot Card Back Design Style */
        .single-tarot-card {
            perspective: 1000px;
            cursor: pointer;
            width: 280px;
            height: 400px;
            margin: 0 auto;
        }
        .single-tarot-inner {
            position: relative;
            width: 100%;
            height: 100%;
            text-align: center;
            transition: transform 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            transform-style: preserve-3d;
        }
        .single-tarot-card.flipped .single-tarot-inner {
            transform: rotateY(180deg);
        }
        .single-tarot-front, .single-tarot-back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 1.5rem;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            box-shadow: 0 20px 40px rgba(131, 24, 67, 0.15);
            padding: 24px;
        }
        /* Tampilan Sisi Depan: Desain Belakang Kartu Tarot Klasik Estetik */
        .single-tarot-front {
            background: #1e1b4b; /* Deep Indigo / Navy Mystical */
            color: #fce7f3;
            border: 5px solid #d946ef;
            background-image: 
                radial-gradient(#d946ef 1px, transparent 1px),
                radial-gradient(#3b82f6 1px, #1e1b4b 1px);
            background-size: 20px 20px;
            background-position: 0 0, 10px 10px;
        }
        .tarot-back-pattern {
            border: 2px dashed rgba(255, 255, 255, 0.3);
            border-radius: 1rem;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 16px;
        }
        /* Tampilan Sisi Belakang Kartu (Hasil Tarot) */
        .single-tarot-back {
            background: white;
            color: #1e293b;
            transform: rotateY(180deg);
            border: 4px solid #fce7f3;
        }
        @keyframes shuffle-anim {
            0% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(8deg) scale(0.95); }
            100% { transform: translateY(0) rotate(0deg); }
        }
        .shuffling {
            animation: shuffle-anim 0.4s ease infinite;
        }
    </style>
</head>
<body class="font-sans bg-slate-50 text-slate-800 antialiased overflow-x-hidden" style="overflow: hidden;">

    <!-- Intro Curtain Animation (Cozy Pastel Y2K Style) -->
    <div id="intro-curtains" class="fixed inset-0 z-[9999] flex overflow-hidden bg-white">
        <!-- Left Curtain -->
        <div id="curtain-left" class="w-1/2 h-full bg-gradient-to-r from-pink-200 via-pink-100 to-white border-r-4 border-white relative shadow-[10px_0_30px_rgba(236,72,153,0.15)] flex items-center justify-end">
            <div class="absolute inset-0 bg-[radial-gradient(#ec4899_1px,transparent_1px)] [background-size:24px_24px] opacity-5"></div>
        </div>

        <!-- Right Curtain -->
        <div id="curtain-right" class="w-1/2 h-full bg-gradient-to-l from-blue-200 via-blue-100 to-white border-l-4 border-white relative shadow-[-10px_0_30px_rgba(59,130,246,0.15)] flex items-center justify-start">
            <div class="absolute inset-0 bg-[radial-gradient(#3b82f6_1px,transparent_1px)] [background-size:24px_24px] opacity-5"></div>
        </div>

        <!-- Center Interactive Welcome Content -->
        <div id="curtain-center-content" class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-center z-30 w-full px-6 transition-opacity duration-500">
            
            <!-- Hanging Sign -->
            <div class="hanging-sign">
                <div class="rope left"></div>
                <div class="rope right"></div>
                <h1 class="y2k-cyber-text text-4xl md:text-6xl lg:text-7xl">PathTeacher</h1>
            </div>

            <br>
          <span class="px-4 py-1.5 rounded-md bg-blue-50 text-blue-700 text-sm font-medium mb-4 inline-block font-sans">
    Portal Informasi Karier
</span>
            
            <p class="text-slate-600 text-sm md:text-lg max-w-xl mx-auto mb-8 font-medium leading-relaxed bg-white/50 backdrop-blur-sm p-4 rounded-3xl border border-white">
                "Panduan karier untuk calon guru SD dari persiapan CPNS, PPPK, sampai peluang mengajar di sekolah internasional"
            </p>
            <button onclick="openCurtains()" class="bg-gradient-to-r from-pink-500 to-blue-500 hover:from-pink-400 hover:to-blue-400 text-white font-bold px-8 py-4 rounded-full shadow-[0_10px_30px_rgba(236,72,153,0.3)] transition-all transform hover:scale-105 active:scale-95 text-base flex items-center gap-3 mx-auto font-display tracking-wide">
                <span>Buka Tirai & Mulai Eksplorasi</span>
                <i class="fa-solid fa-sparkles"></i>
            </button>
         </div>   
    </div>

    <!-- Navbar -->
    <header class="fixed w-full top-0 z-50 glass-panel shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex-shrink-0 flex items-center gap-2 cursor-pointer" onclick="window.scrollTo(0,0)">
                    <div class="w-10 h-10 bg-gradient-to-br from-pink-500 to-blue-500 rounded-2xl flex items-center justify-center text-white font-bold text-xl shadow-md transform rotate-3">
                        <i class="fa-solid fa-graduation-cap -rotate-3"></i>
                    </div>
                    <span class="y2k-cyber-text-sm text-xl md:text-2xl">PathTeacher</span>
                </div>
                
                <nav class="hidden md:flex space-x-8">
                    <a href="#beranda" class="text-slate-600 hover:text-pink-500 font-bold transition-colors">Beranda</a>
                    <a href="#minat-bakat" class="text-pink-500 font-bold transition-colors flex items-center gap-1"><i class="fa-solid fa-gamepad text-pink-400"></i> Tes Minat</a>
                    <a href="#tarot-motivasi" class="text-slate-600 hover:text-pink-500 font-bold transition-colors flex items-center gap-1"><i class="fa-solid fa-wand-magic-sparkles text-pink-400"></i> Tarot Motivasi</a>
                    <a href="#jalur-karier" class="text-slate-600 hover:text-pink-500 font-bold transition-colors">Jalur Karier</a>
                    <a href="#peta-tahapan" class="text-slate-600 hover:text-pink-500 font-bold transition-colors">Roadmap</a>
                    <a href="#persiapan" class="text-slate-600 hover:text-pink-500 font-bold transition-colors">Tips</a>
                </nav>

                <div class="hidden md:block">
                    <a href="#tanya-ai" class="bg-gradient-to-r from-pink-500 to-blue-500 hover:opacity-90 text-white px-6 py-2.5 rounded-full font-bold transition-all shadow-lg shadow-pink-500/30 flex items-center gap-2 font-display">
                        <i class="fa-solid fa-sparkles"></i> Tanya AI
                    </a>
                </div>

                <div class="md:hidden flex items-center">
                    <button id="mobile-menu-btn" class="text-slate-600 hover:text-pink-500 focus:outline-none">
                        <i class="fa-solid fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <div id="mobile-menu" class="hidden md:hidden bg-white/95 backdrop-blur-md border-t border-pink-50 shadow-xl">
            <div class="px-4 pt-3 pb-4 space-y-2">
                <a href="#beranda" class="block px-4 py-3 text-slate-700 hover:text-pink-500 font-bold rounded-2xl">Beranda</a>
                <a href="#minat-bakat" class="block px-4 py-3 text-pink-600 font-bold bg-pink-50 rounded-2xl"><i class="fa-solid fa-gamepad mr-2"></i> Tes Minat & Bakat</a>
                <a href="#tarot-motivasi" class="block px-4 py-3 text-slate-700 hover:text-pink-500 font-bold rounded-2xl"><i class="fa-solid fa-wand-magic-sparkles mr-2 text-pink-500"></i> Tarot Motivasi</a>
                <a href="#jalur-karier" class="block px-4 py-3 text-slate-700 hover:text-pink-500 font-bold rounded-2xl">Jalur Karier</a>
                <a href="#peta-tahapan" class="block px-4 py-3 text-slate-700 hover:text-pink-500 font-bold rounded-2xl">Roadmap</a>
                <a href="#persiapan" class="block px-4 py-3 text-slate-700 hover:text-pink-500 font-bold rounded-2xl">Tips</a>
                <a href="#tanya-ai" class="block px-4 py-3 text-white font-bold bg-gradient-to-r from-pink-500 to-blue-500 rounded-2xl mt-4 text-center"><i class="fa-solid fa-robot mr-2"></i> Tanya AI PathTeacher</a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="beranda" class="pt-28 pb-20 lg:pt-36 lg:pb-28 bg-gradient-to-br from-pink-50 via-white to-blue-50 relative overflow-hidden">
        <!-- Soft Blob Backgrounds -->
        <div class="absolute top-0 right-0 -mr-20 -mt-20 w-96 h-96 rounded-full bg-pink-200/40 blur-3xl pointer-events-none"></div>
        <div class="absolute bottom-0 left-0 -ml-20 -mb-20 w-80 h-80 rounded-full bg-blue-200/40 blur-3xl pointer-events-none"></div>
        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-full h-full bg-[radial-gradient(#cbd5e1_1px,transparent_1px)] [background-size:24px_24px] opacity-20 pointer-events-none"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="fade-in">
                    <div class="inline-block px-5 py-2 rounded-full bg-white text-pink-600 font-bold text-sm mb-6 border border-pink-100 shadow-sm font-display tracking-wide">
                        <i class="fa-solid fa-compass mr-2 text-pink-400"></i> Media Karier Mahasiswa PGSD
                    </div>
                    <h1 class="text-4xl md:text-5xl lg:text-6xl font-extrabold text-slate-800 leading-tight mb-6 font-display">
                        Level Up Kariermu Jadi <span class="text-transparent bg-clip-text bg-gradient-to-r from-pink-500 to-blue-500">Guru SD Idaman</span>
                    </h1>
                    <p class="text-lg text-slate-600 mb-8 leading-relaxed font-medium">
                        "Bingung menyiapkan karier setelah lulus PGSD? Semua yang perlu kamu tahu tentang CPNS, PPPK, dan sekolah internasional ada di sini."
                    </p>
                    <div class="flex flex-col sm:flex-row gap-4">
                        <a href="#minat-bakat" class="bg-gradient-to-r from-pink-500 to-pink-600 hover:from-pink-400 hover:to-pink-500 text-white px-8 py-4 rounded-full font-bold text-lg text-center transition-all shadow-lg shadow-pink-500/25 flex items-center justify-center gap-2 font-display tracking-wide">
                            Main Tes Minat <i class="fa-solid fa-gamepad"></i>
                        </a>
                        <a href="#tarot-motivasi" class="bg-white hover:bg-slate-50 text-slate-700 border-2 border-pink-100 px-8 py-4 rounded-full font-bold text-lg text-center transition-all flex items-center justify-center gap-2 shadow-sm font-display tracking-wide text-pink-600">
                            <i class="fa-solid fa-wand-magic-sparkles text-pink-400"></i> Tarot Motivasi
                        </a>
                    </div>
                </div>
                
                <div class="relative fade-in hidden lg:block">
                    <!-- Glassmorphism Image Container -->
                    <div class="relative rounded-[2rem] bg-white/40 backdrop-blur-xl shadow-2xl p-3 border border-white transform rotate-2 hover:rotate-0 transition-transform duration-500">
                        <img src="https://images.unsplash.com/photo-1577896851231-70ef18881754?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Guru mengajar di kelas" class="rounded-3xl w-full h-[450px] object-cover">
                        <!-- Floating Badge -->
                        <div class="absolute -bottom-6 -left-6 bg-white p-4 rounded-2xl shadow-xl flex items-center gap-4 border border-pink-50 animate-bounce">
                            <div class="w-12 h-12 bg-blue-100 rounded-xl flex items-center justify-center text-blue-500 text-xl font-bold transform -rotate-6">
                                <i class="fa-solid fa-bolt"></i>
                            </div>
                            <div>
                                <p class="text-xs text-slate-500 font-bold uppercase tracking-wider">Update Info</p>
                                <p class="font-bold text-slate-800 font-display text-lg">Formasi Guru 2026</p>
                            </div>
                        </div>
                        
                        <!-- Secondary Floating Badge -->
                        <div class="absolute top-10 -right-6 bg-white p-3 rounded-2xl shadow-lg flex items-center gap-3 border border-pink-50">
                            <div class="w-10 h-10 bg-pink-100 rounded-full flex items-center justify-center text-pink-500">
                                <i class="fa-solid fa-heart"></i>
                            </div>
                            <p class="font-bold text-slate-700 text-sm pr-2">Love Teaching</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Minat & Bakat Section (10 Pertanyaan Quiz) -->
    <section id="minat-bakat" class="py-24 bg-white border-t border-pink-50">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12 fade-in">
                <span class="px-5 py-2 rounded-full bg-pink-50 border border-pink-100 text-pink-600 font-bold text-xs uppercase tracking-widest mb-4 inline-block font-display">Interactive Quiz 🎮</span>
                <h3 class="text-3xl md:text-4xl font-extrabold text-slate-800 mb-4 font-display">Tes Minat & Jalur Karier Guru SD</h3>
                <p class="text-slate-600 text-base md:text-lg max-w-2xl mx-auto font-medium">
                    Bingung mau pilih jalur CPNS, PPPK, atau Sekolah Internasional? Jawab 10 pertanyaan santai ini buat nemuin jalur yang paling <em>match</em> sama kepribadian dan mimpimu!
                </p>
            </div>

            <div id="quiz-container" class="glass-panel bg-white/60 rounded-[2.5rem] shadow-[0_20px_50px_rgba(236,72,153,0.08)] border border-pink-100 p-6 md:p-10 fade-in">
                
                <!-- Intro Quiz -->
                <div id="quiz-intro" class="text-center py-8">
                    <div class="w-24 h-24 bg-gradient-to-br from-pink-100 to-blue-100 rounded-[2rem] flex items-center justify-center text-pink-500 text-4xl mx-auto mb-6 shadow-sm border border-white">
                        <i class="fa-solid fa-gamepad"></i>
                    </div>
                    <h4 class="text-2xl font-bold text-slate-800 mb-3 font-display">Siap Cari Tahu Vibes Kariermu?</h4>
                    <p class="text-slate-600 max-w-md mx-auto mb-8 text-sm md:text-base font-medium">
                        Kuis seru ini cuma butuh waktu 2 menit. Tinggal pilih jawaban yang paling "kamu banget"!
                    </p>
                    <button onclick="startQuiz()" class="bg-slate-800 hover:bg-slate-700 text-white font-bold px-8 py-4 rounded-full shadow-lg shadow-slate-200 transition-all transform hover:scale-105 active:scale-95 text-base inline-flex items-center gap-3 font-display tracking-wide">
                        <span>Mulai Kuis Sekarang</span>
                        <i class="fa-solid fa-play"></i>
                    </button>
                </div>

                <!-- Soal Quiz -->
                <div id="quiz-questions-screen" class="hidden">
                    <div class="flex justify-between items-center mb-6 pb-4 border-b border-slate-100">
                        <span id="quiz-counter" class="text-xs font-bold text-pink-600 bg-pink-50 border border-pink-100 px-4 py-1.5 rounded-full font-display">Pertanyaan 1/10</span>
                        <span id="quiz-progress-text" class="text-xs font-bold text-slate-400">10%</span>
                    </div>

                    <div class="w-full bg-slate-100 h-3 rounded-full mb-8 overflow-hidden border border-slate-200/50">
                        <div id="quiz-progress-bar" class="bg-gradient-to-r from-pink-400 to-blue-400 h-full rounded-full transition-all duration-300" style="width: 10%"></div>
                    </div>

                    <h4 id="quiz-question-title" class="text-xl md:text-2xl font-bold text-slate-800 mb-6 leading-snug font-display">Pertanyaan akan muncul di sini...</h4>

                    <div id="quiz-options-list" class="space-y-3 font-medium"></div>
                </div>

                <!-- Hasil Quiz -->
                <div id="quiz-result-screen" class="hidden text-center py-6">
                    <div class="w-24 h-24 bg-gradient-to-br from-blue-100 to-pink-100 text-blue-600 rounded-[2rem] flex items-center justify-center text-4xl mx-auto mb-6 shadow-sm border border-white">
                        <i class="fa-solid fa-award"></i>
                    </div>
                    <span class="text-xs font-bold px-4 py-1.5 rounded-full bg-blue-50 text-blue-600 mb-3 inline-block font-display border border-blue-100">Hasil Analisis KarierGen</span>
                    <h4 id="result-title" class="text-3xl font-extrabold text-slate-800 mb-3 font-display">Jalur Karier Anda</h4>
                    <p id="result-description" class="text-slate-600 text-base max-w-lg mx-auto mb-8 leading-relaxed font-medium">
                        Deskripsi hasil akan muncul di sini...
                    </p>

                    <div class="bg-white/80 border border-pink-100 p-6 rounded-3xl mb-8 text-left relative overflow-hidden shadow-sm">
                        <div class="absolute -right-4 -bottom-8 text-pink-100 text-8xl font-display pointer-events-none">“</div>
                        <h5 class="font-bold text-pink-500 text-sm uppercase tracking-wider mb-2 flex items-center gap-2 font-display"><i class="fa-solid fa-sparkles text-amber-400"></i> Quote Buat Kamu</h5>
                        <p id="result-quote" class="text-slate-700 italic text-sm md:text-base leading-relaxed font-medium">"Pesan motivasi..."</p>
                    </div>

                    <div class="flex flex-col sm:flex-row justify-center gap-4">
                        <a id="result-action-btn" href="#jalur-karier" class="bg-gradient-to-r from-pink-500 to-blue-500 text-white font-bold px-8 py-4 rounded-full shadow-md transition-all flex items-center justify-center gap-2 font-display tracking-wide transform hover:scale-105">
                            <span>Lihat Detail Jalurnya</span>
                            <i class="fa-solid fa-arrow-right"></i>
                        </a>
                        <button onclick="resetQuiz()" class="bg-slate-100 hover:bg-slate-200 text-slate-700 font-bold px-6 py-4 rounded-full transition-all flex items-center justify-center gap-2 font-display">
                            <i class="fa-solid fa-rotate-right"></i> Main Lagi
                        </button>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- FITUR BARU: Tarot Motivasi Estetik (Tampilan Belakang Kartu Klasik & Kumpulan Kata Banyak) -->
    <section id="tarot-motivasi" class="py-24 bg-gradient-to-br from-pink-50/50 via-indigo-50/30 to-blue-50/50 border-t border-pink-50">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <div class="mb-12 fade-in">
                <span class="px-5 py-2 rounded-full bg-white border border-pink-100 text-pink-600 font-bold text-xs uppercase tracking-widest mb-4 inline-block font-display shadow-sm">Tarot Motivasi 22 Lembar 🔮✨</span>
                <h3 class="text-3xl md:text-4xl font-extrabold text-slate-800 mb-4 font-display">Kocok & Ambil 1 Kartu Inspirasimu Hari Ini!</h3>
                <p class="text-slate-600 text-base md:text-lg max-w-2xl mx-auto font-medium">
                    Pilih atau kocok tumpukan kartu mistis estetik ini untuk memunculkan satu kata motivasi pengembangan diri atau semangat menjadi guru terbaik.
                </p>
            </div>

            <!-- Single Tarot Card with Classic Back Pattern -->
            <div class="fade-in mb-8">
                <div id="single-tarot-card" class="single-tarot-card" onclick="flipSingleCard()">
                    <div id="single-tarot-inner" class="single-tarot-inner">
                        <!-- Sisi Depan: Desain Belakang Kartu Tarot Klasik -->
                        <div class="single-tarot-front">
                            <div class="tarot-back-pattern">
                                <div class="w-14 h-14 rounded-full bg-pink-500/25 flex items-center justify-center text-pink-200 text-2xl mb-3 border border-pink-400/40">
                                    <i class="fa-solid fa-eye"></i>
                                </div>
                                <h4 class="text-lg font-bold font-display uppercase tracking-widest text-pink-200 mb-1">PathTeacher</h4>
                                <p class="text-[10px] text-pink-300 font-medium tracking-wide">Tarot Pengembang Diri & Guru</p>
                                <div class="mt-4 text-xs bg-white/10 px-4 py-1.5 rounded-full border border-white/20 text-white font-bold">Ketuk untuk Buka ✨</div>
                            </div>
                        </div>
                        <!-- Sisi Belakang: Hasil Kata Motivasi -->
                        <div class="single-tarot-back">
                            <span id="tarot-badge" class="text-[10px] font-bold px-3 py-1 rounded-full bg-pink-50 text-pink-600 uppercase tracking-widest mb-3 border border-pink-100 font-display">Inspirasi Pendidik</span>
                            <h4 id="tarot-word" class="text-xl md:text-2xl font-extrabold text-slate-800 mb-3 font-display">Klik Kocok Kartu!</h4>
                            <p id="tarot-desc" class="text-sm md:text-sm text-slate-600 font-medium leading-relaxed px-2">Temukan kata-kata berharga untuk perjalanan menakjubkanmu sebagai seorang pendidik unggul.</p>
                            <span class="text-[11px] text-pink-500 font-bold mt-6 italic">Tekan tombol di bawah untuk kocok kartu</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Tombol Kocok Kartu -->
            <div class="fade-in">
                <button onclick="shuffleSingleTarot()" class="bg-gradient-to-r from-pink-500 to-blue-500 hover:opacity-90 text-white font-bold px-8 py-4 rounded-full shadow-lg shadow-pink-500/20 transition-all transform hover:scale-105 active:scale-95 text-base inline-flex items-center gap-3 font-display tracking-wide">
                    <i class="fa-solid fa-shuffle" id="shuffle-icon"></i>
                    <span>Kocok & Ambil 1 Kartu Baru</span>
                </button>
            </div>
        </div>
    </section>

    <!-- Jalur Karier Section (Dengan Kiat per tab lebih dari satu) -->
    <section id="jalur-karier" class="py-24 bg-pink-50/30 border-y border-pink-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-14 fade-in">
                <h2 class="text-sm font-bold text-pink-500 uppercase tracking-wide mb-2 font-display">Pilihan Masa Depan</h2>
                <h3 class="text-3xl md:text-4xl font-bold text-slate-800 mb-4 font-display">Eksplorasi Jalur Karier Utama</h3>
                <p class="text-slate-600 text-lg font-medium">Pilih jalur yang paling <em>match</em> dengan hasil kuis atau passion kamu.</p>
            </div>

            <div class="flex flex-col lg:flex-row gap-8 items-start">
                
                <!-- Sidebar Tabs -->
                <div class="lg:w-1/4 w-full flex flex-col gap-3 fade-in sticky top-28 z-10">
                    <button onclick="openTab('cpns')" id="btn-cpns" class="tab-btn active w-full text-left px-6 py-5 rounded-3xl border-l-4 font-bold relative overflow-hidden group shadow-sm">
                        <span class="relative z-10 flex items-center gap-4"><i class="fa-solid fa-building-columns text-2xl w-8 text-center text-pink-500"></i> <span class="text-lg font-display">Guru CPNS</span></span>
                    </button>
                    
                    <button onclick="openTab('pppk')" id="btn-pppk" class="tab-btn font-medium w-full text-left px-6 py-5 rounded-3xl border-l-4 relative overflow-hidden group shadow-sm">
                        <span class="relative z-10 flex items-center gap-4"><i class="fa-solid fa-file-signature text-2xl w-8 text-center text-blue-500"></i> <span class="text-lg font-display">Guru PPPK</span></span>
                    </button>
                    
                    <button onclick="openTab('swasta')" id="btn-swasta" class="tab-btn font-medium w-full text-left px-6 py-5 rounded-3xl border-l-4 relative overflow-hidden group shadow-sm">
                        <span class="relative z-10 flex items-center gap-4"><i class="fa-solid fa-globe text-2xl w-8 text-center text-violet-500"></i> <span class="text-lg font-display">Sekolah Internasional</span></span>
                    </button>
                </div>

                <!-- Content Area -->
                <div class="lg:w-3/4 w-full fade-in" style="transition-delay: 100ms;">
                    
                    <!-- TAB 1: CPNS -->
                    <div id="content-cpns" class="tab-content active glass-panel rounded-[2.5rem] shadow-xl p-8 md:p-10 border border-white">
                        <div class="inline-flex items-center justify-center w-16 h-16 rounded-2xl bg-pink-100 text-pink-600 text-3xl mb-6 shadow-sm border border-white">
                            <i class="fa-solid fa-building-columns"></i>
                        </div>
                        <h3 class="text-3xl font-extrabold text-slate-800 mb-4 font-display">Guru CPNS (Pegawai Negeri Sipil)</h3>
                        
                        <!-- Waktu Pelaksanaan -->
                        <div class="mb-8 bg-white/70 p-6 rounded-3xl border border-pink-100 shadow-sm">
                            <h4 class="text-lg font-bold text-pink-600 mb-3 flex items-center gap-2 font-display">
                                <i class="fa-solid fa-calendar-days"></i> Kapan Seleksi Dibuka?
                            </h4>
                            <p class="text-sm text-slate-700 leading-relaxed mb-4 font-medium">
                                Berdasarkan tren historis, BKN biasanya membuka pendaftaran pada <strong>pertengahan tahun (Juli-Agustus)</strong>, dengan tes SKD dan SKB di akhir tahun. *Ini pola historis ya, untuk jadwal resminya tetap tunggu pengumuman KemenpanRB!*
                            </p>
                        </div>

                        <!-- Konteks Gambar / Visual -->
                        <div class="mb-10">
                            <h4 class="text-lg font-bold text-slate-800 mb-4 flex items-center gap-2 font-display"><i class="fa-solid fa-image text-pink-400"></i> Visualisasi Seleksi CPNS</h4>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                <div class="bg-white rounded-3xl overflow-hidden shadow-sm border border-slate-100 p-2">
                                    <img src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Ujian CAT BKN" class="w-full h-40 object-cover rounded-2xl">
                                    <div class="p-4">
                                        <span class="text-[10px] font-bold text-pink-600 bg-pink-50 border border-pink-100 px-3 py-1 rounded-full uppercase tracking-wide">Tahap SKD (CAT BKN)</span>
                                        <p class="text-xs text-slate-600 mt-3 leading-relaxed font-medium">
                                            Peserta ngerjain soal pakai komputer (Computer Assisted Test). Skor langsung keluar *real-time* pas waktu habis! Deg-degan tapi transparan.
                                        </p>
                                    </div>
                                </div>
                                <div class="bg-white rounded-3xl overflow-hidden shadow-sm border border-slate-100 p-2">
                                    <img src="https://images.unsplash.com/photo-1531482615713-2afd69097998?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Wawancara" class="w-full h-40 object-cover rounded-2xl">
                                    <div class="p-4">
                                        <span class="text-[10px] font-bold text-pink-600 bg-pink-50 border border-pink-100 px-3 py-1 rounded-full uppercase tracking-wide">Tahap SKB</span>
                                        <p class="text-xs text-slate-600 mt-3 leading-relaxed font-medium">
                                            Kalo lolos SKD, kamu bakal diuji sesuai bidang. Kadang ada tes praktik mengajar (Microteaching) atau wawancara langsung sama pejabat daerah.
                                        </p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Map Horizontal -->
                        <div class="mb-10 bg-white/50 rounded-3xl p-6 border border-white shadow-sm">
                            <h4 class="text-lg font-bold text-slate-800 mb-6 flex items-center gap-2 font-display"><i class="fa-solid fa-route text-pink-400"></i> Alur Tahapan Resmi</h4>
                            <div class="relative w-full overflow-x-auto pb-6 custom-scrollbar">
                                <div class="min-w-[800px] flex justify-between relative px-4">
                                    <div class="absolute top-6 left-12 right-12 h-1.5 bg-pink-100 rounded-full z-0"></div>
                                    
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-pink-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-pink-50 font-display">1</div>
                                        <h5 class="font-bold text-sm text-slate-800">Daftar Akun</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">SSCASN BKN</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-pink-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-pink-50 font-display">2</div>
                                        <h5 class="font-bold text-sm text-slate-800">Tes SKD</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">TWK, TIU, TKP</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-pink-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-pink-50 font-display">3</div>
                                        <h5 class="font-bold text-sm text-slate-800">Tes SKB</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Ujian Bidang</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-pink-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-pink-50 font-display">4</div>
                                        <h5 class="font-bold text-sm text-slate-800">Integrasi</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Skor SKD + SKB</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-pink-500 text-white flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-pink-100"><i class="fa-solid fa-flag-checkered"></i></div>
                                        <h5 class="font-bold text-sm text-slate-800">Pemberkasan</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Dapat NIP PNS!</p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Kiat Lolos (Multiple) -->
                        <div>
                            <h4 class="text-lg font-bold text-slate-800 mb-4 flex items-center gap-2 font-display"><i class="fa-solid fa-lightbulb text-amber-400"></i> Tips & Trik Tembus CPNS</h4>
                            <div class="flex flex-col gap-3">
                                <div class="bg-white rounded-2xl border border-pink-100 overflow-hidden shadow-sm">
                                    <button onclick="toggleAccordion('cpns-acc-1')" class="w-full flex justify-between items-center px-6 py-4 text-left hover:bg-pink-50/50 transition-colors focus:outline-none group">
                                        <span class="font-bold text-slate-700 group-hover:text-pink-600 transition-colors">1. Formasi Linier Selain Guru Kelas</span>
                                        <i id="icon-cpns-acc-1" class="fa-solid fa-chevron-down text-pink-400 transition-transform duration-300"></i>
                                    </button>
                                    <div id="cpns-acc-1" class="accordion-content px-6 bg-pink-50/30">
                                        <div class="py-4 border-t border-pink-100 text-sm text-slate-600 font-medium leading-relaxed">
                                            <p>Ijazah PGSD gak melulu harus ngajar di kelas! Kamu juga bisa lamar formasi pendukung seperti Analis Kurikulum, Pengembang Penilaian Pendidikan, atau Penyuluh Bahasa di berbagai Kementerian.</p>
                                        </div>
                                    </div>
                                </div>
                                
                                <div class="bg-white rounded-2xl border border-pink-100 overflow-hidden shadow-sm">
                                    <button onclick="toggleAccordion('cpns-acc-2')" class="w-full flex justify-between items-center px-6 py-4 text-left hover:bg-pink-50/50 transition-colors focus:outline-none group">
                                        <span class="font-bold text-slate-700 group-hover:text-pink-600 transition-colors">2. Cheat Code: Sertifikat Pendidik (Serdik)</span>
                                        <i id="icon-cpns-acc-2" class="fa-solid fa-chevron-down text-pink-400 transition-transform duration-300"></i>
                                    </button>
                                    <div id="cpns-acc-2" class="accordion-content px-6 bg-pink-50/30">
                                        <div class="py-4 border-t border-pink-100 text-sm text-slate-600 font-medium leading-relaxed">
                                            <p>Lulusan PPG Prajabatan yang punya Serdik linier otomatis dapat nilai SKB maksimal (poin 100). Ini beneran <em>game changer</em> buat numbangin sainganmu!</p>
                                        </div>
                                    </div>
                                </div>

                                <div class="bg-white rounded-2xl border border-pink-100 overflow-hidden shadow-sm">
                                    <button onclick="toggleAccordion('cpns-acc-3')" class="w-full flex justify-between items-center px-6 py-4 text-left hover:bg-pink-50/50 transition-colors focus:outline-none group">
                                        <span class="font-bold text-slate-700 group-hover:text-pink-600 transition-colors">3. Hack Mengerjakan Soal SKD</span>
                                        <i id="icon-cpns-acc-3" class="fa-solid fa-chevron-down text-pink-400 transition-transform duration-300"></i>
                                    </button>
                                    <div id="cpns-acc-3" class="accordion-content px-6 bg-pink-50/30">
                                        <div class="py-4 border-t border-pink-100 text-sm text-slate-600 font-medium leading-relaxed">
                                            <p>Selalu kerjain bagian TKP (Tes Karakteristik Pribadi) duluan. Soalnya panjang-panjang, butuh konsentrasi, tapi asyiknya gak ada jawaban yang nilainya 0 (rentang 1-5 poin).</p>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- TAB 2: PPPK -->
                    <div id="content-pppk" class="tab-content glass-panel rounded-[2.5rem] shadow-xl p-8 md:p-10 border border-white">
                        <div class="inline-flex items-center justify-center w-16 h-16 rounded-2xl bg-blue-100 text-blue-500 text-3xl mb-6 shadow-sm border border-white">
                            <i class="fa-solid fa-file-signature"></i>
                        </div>
                        <h3 class="text-3xl font-extrabold text-slate-800 mb-4 font-display">Guru PPPK (Pegawai Pemerintah)</h3>
                        
                        <!-- Waktu Pelaksanaan -->
                        <div class="mb-8 bg-white/70 p-6 rounded-3xl border border-blue-100 shadow-sm">
                            <h4 class="text-lg font-bold text-blue-600 mb-3 flex items-center gap-2 font-display">
                                <i class="fa-solid fa-calendar-days"></i> Kapan Seleksi Dibuka?
                            </h4>
                            <p class="text-sm text-slate-700 leading-relaxed mb-4 font-medium">
                                Biasanya dibuka beriringan atau tak lama setelah pendaftaran CPNS <strong>(sekitar Agustus - Oktober)</strong>. PPPK sangat difokuskan untuk memenuhi kebutuhan guru yang siap kerja (banyak formasi buat honorer dan lulusan PPG).
                            </p>
                        </div>

                        <!-- Konteks Gambar / Visual -->
                        <div class="mb-10">
                            <h4 class="text-lg font-bold text-slate-800 mb-4 flex items-center gap-2 font-display"><i class="fa-solid fa-image text-blue-400"></i> Visualisasi Seleksi PPPK</h4>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                <div class="bg-white rounded-3xl overflow-hidden shadow-sm border border-slate-100 p-2">
                                    <img src="https://images.unsplash.com/photo-1554415707-6e8cfc93fe23?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Verval Ijazah" class="w-full h-40 object-cover rounded-2xl">
                                    <div class="p-4">
                                        <span class="text-[10px] font-bold text-blue-600 bg-blue-50 border border-blue-100 px-3 py-1 rounded-full uppercase tracking-wide">Tahap Verval Dapodik</span>
                                        <p class="text-xs text-slate-600 mt-3 leading-relaxed font-medium">
                                            Tahap krusial! Buat honorer, data kamu di Info GTK harus valid hijau dan sinkron sama ijazah kampus. Kalau error, auto gagal daftar admin.
                                        </p>
                                    </div>
                                </div>
                                <div class="bg-white rounded-3xl overflow-hidden shadow-sm border border-slate-100 p-2">
                                    <img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Ujian Kompetensi Teknis" class="w-full h-40 object-cover rounded-2xl">
                                    <div class="p-4">
                                        <span class="text-[10px] font-bold text-blue-600 bg-blue-50 border border-blue-100 px-3 py-1 rounded-full uppercase tracking-wide">Ujian Kompetensi</span>
                                        <p class="text-xs text-slate-600 mt-3 leading-relaxed font-medium">
                                            Berbeda dengan CPNS yang nguji sejarah, PPPK lebih banyak nguji studi kasus ngajar (pedagogik) dan cara kamu ngadepin masalah kelas.
                                        </p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="mb-10 bg-white/50 rounded-3xl p-6 border border-white shadow-sm">
                            <h4 class="text-lg font-bold text-slate-800 mb-6 flex items-center gap-2 font-display"><i class="fa-solid fa-route text-blue-400"></i> Alur Tahapan PPPK</h4>
                            <div class="relative w-full overflow-x-auto pb-6 custom-scrollbar">
                                <div class="min-w-[800px] flex justify-between relative px-4">
                                    <div class="absolute top-6 left-12 right-12 h-1.5 bg-blue-100 rounded-full z-0"></div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-blue-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-blue-50 font-display">1</div>
                                        <h5 class="font-bold text-sm text-slate-800">Cek Dapodik</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Validasi Info GTK</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-blue-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-blue-50 font-display">2</div>
                                        <h5 class="font-bold text-sm text-slate-800">Daftar SSCASN</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Pilih Formasi</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-blue-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-blue-50 font-display">3</div>
                                        <h5 class="font-bold text-sm text-slate-800">Komp. Teknis</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Soal Pedagogik</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-blue-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-blue-50 font-display">4</div>
                                        <h5 class="font-bold text-sm text-slate-800">Manajerial</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Wawancara Sistem</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-blue-500 text-white flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-blue-100"><i class="fa-solid fa-handshake"></i></div>
                                        <h5 class="font-bold text-sm text-slate-800">Penetapan SK</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Resmi ASN PPPK</p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div>
                            <h4 class="text-lg font-bold text-slate-800 mb-4 flex items-center gap-2 font-display"><i class="fa-solid fa-lightbulb text-amber-400"></i> Tips & Trik Tembus PPPK</h4>
                            <div class="flex flex-col gap-3">
                                <div class="bg-white rounded-2xl border border-blue-100 overflow-hidden shadow-sm">
                                    <button onclick="toggleAccordion('pppk-acc-1')" class="w-full flex justify-between items-center px-6 py-4 text-left hover:bg-blue-50/50 transition-colors focus:outline-none group">
                                        <span class="font-bold text-slate-700 group-hover:text-blue-600 transition-colors">1. Rajin Cek Verval Ijazah</span>
                                        <i id="icon-pppk-acc-1" class="fa-solid fa-chevron-down text-blue-400 transition-transform duration-300"></i>
                                    </button>
                                    <div id="pppk-acc-1" class="accordion-content px-6 bg-blue-50/30">
                                        <div class="py-4 border-t border-blue-100 text-sm text-slate-600 font-medium leading-relaxed">
                                            <p>Buat kamu yang udah honorer, pastiin sering-sering cek web <em>info.gtk.kemdikbud.go.id</em>. Pastiin status ijazah S1 PGSD kamu sinkron sama PDDikti. Banyak yang gagal daftar cuma karena masalah administrasi ini!</p>
                                        </div>
                                    </div>
                                </div>

                                <div class="bg-white rounded-2xl border border-blue-100 overflow-hidden shadow-sm">
                                    <button onclick="toggleAccordion('pppk-acc-2')" class="w-full flex justify-between items-center px-6 py-4 text-left hover:bg-blue-50/50 transition-colors focus:outline-none group">
                                        <span class="font-bold text-slate-700 group-hover:text-blue-600 transition-colors">2. Pola Pikir Jawaban Pedagogik</span>
                                        <i id="icon-pppk-acc-2" class="fa-solid fa-chevron-down text-blue-400 transition-transform duration-300"></i>
                                    </button>
                                    <div id="pppk-acc-2" class="accordion-content px-6 bg-blue-50/30">
                                        <div class="py-4 border-t border-blue-100 text-sm text-slate-600 font-medium leading-relaxed">
                                            <p>Saat tes teknis PPPK, soalnya bakal nanya solusi masalah kelas. Ingat kuncinya: Selalu pilih jawaban yang **"Student Centered"** (berpusat pada kebutuhan murid) dan komunikatif, hindari opsi hukuman fisik atau otoriter.</p>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- TAB 3: Swasta Internasional -->
                    <div id="content-swasta" class="tab-content glass-panel rounded-[2.5rem] shadow-xl p-8 md:p-10 border border-white">
                        <div class="inline-flex items-center justify-center w-16 h-16 rounded-2xl bg-violet-100 text-violet-500 text-3xl mb-6 shadow-sm border border-white">
                            <i class="fa-solid fa-globe"></i>
                        </div>
                        <h3 class="text-3xl font-extrabold text-slate-800 mb-4 font-display">Sekolah Swasta Internasional</h3>
                        
                        <!-- Waktu Pelaksanaan -->
                        <div class="mb-8 bg-white/70 p-6 rounded-3xl border border-violet-100 shadow-sm">
                            <h4 class="text-lg font-bold text-violet-600 mb-3 flex items-center gap-2 font-display">
                                <i class="fa-solid fa-calendar-days"></i> Kapan Seleksi Dibuka?
                            </h4>
                            <p class="text-sm text-slate-700 leading-relaxed mb-4 font-medium">
                                Gak ada jadwal terpusat! Biasanya sekolah elit membuka rekrutmen sekitar <strong>3-5 bulan sebelum tahun ajaran baru (Januari - April)</strong>. Kamu harus proaktif pantau *LinkedIn* atau *Career Page* website sekolahnya langsung.
                            </p>
                        </div>

                        <!-- Konteks Gambar / Visual -->
                        <div class="mb-10">
                            <h4 class="text-lg font-bold text-slate-800 mb-4 flex items-center gap-2 font-display"><i class="fa-solid fa-image text-violet-400"></i> Visualisasi Rekrutmen Global</h4>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                <div class="bg-white rounded-3xl overflow-hidden shadow-sm border border-slate-100 p-2">
                                    <img src="https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Panel Interview" class="w-full h-40 object-cover rounded-2xl">
                                    <div class="p-4">
                                        <span class="text-[10px] font-bold text-violet-600 bg-violet-50 border border-violet-100 px-3 py-1 rounded-full uppercase tracking-wide">User Interview</span>
                                        <p class="text-xs text-slate-600 mt-3 leading-relaxed font-medium">
                                            Interviewnya santai tapi dalem. Biasanya ngobrol bareng Principal (Kepsek ekspatriat) full bahasa Inggris, ngebahas gimana cara kamu ngadepin anak beda budaya.
                                        </p>
                                    </div>
                                </div>
                                <div class="bg-white rounded-3xl overflow-hidden shadow-sm border border-slate-100 p-2">
                                    <img src="https://images.unsplash.com/photo-1524178232363-1fb2b075b655?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Microteaching" class="w-full h-40 object-cover rounded-2xl">
                                    <div class="p-4">
                                        <span class="text-[10px] font-bold text-violet-600 bg-violet-50 border border-violet-100 px-3 py-1 rounded-full uppercase tracking-wide">Demo Mengajar (Microteaching)</span>
                                        <p class="text-xs text-slate-600 mt-3 leading-relaxed font-medium">
                                            Tahap paling *makes or breaks*. Kamu harus tunjukin cara ngajar yang seru pakai metode IB atau Cambridge, gak cuma nulis di papan tulis!
                                        </p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="mb-10 bg-white/50 rounded-3xl p-6 border border-white shadow-sm">
                            <h4 class="text-lg font-bold text-slate-800 mb-6 flex items-center gap-2 font-display"><i class="fa-solid fa-route text-violet-400"></i> Alur Rekrutmen Internasional</h4>
                            <div class="relative w-full overflow-x-auto pb-6 custom-scrollbar">
                                <div class="min-w-[800px] flex justify-between relative px-4">
                                    <div class="absolute top-6 left-12 right-12 h-1.5 bg-violet-100 rounded-full z-0"></div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-violet-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-violet-50 font-display">1</div>
                                        <h5 class="font-bold text-sm text-slate-800">Kirim CV</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">CV ATS (English)</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-violet-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-violet-50 font-display">2</div>
                                        <h5 class="font-bold text-sm text-slate-800">HR Screen</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Cek Background & TOEFL</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-violet-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-violet-50 font-display">3</div>
                                        <h5 class="font-bold text-sm text-slate-800">Interview</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Sesi bareng Principal</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-white text-violet-500 flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-violet-50 font-display">4</div>
                                        <h5 class="font-bold text-sm text-slate-800">Demo Ajar</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Microteaching Live</p>
                                    </div>
                                    <div class="relative z-10 flex flex-col items-center text-center w-32">
                                        <div class="w-12 h-12 rounded-full bg-violet-500 text-white flex items-center justify-center text-xl font-bold shadow-sm mb-3 border-4 border-violet-100"><i class="fa-solid fa-file-contract"></i></div>
                                        <h5 class="font-bold text-sm text-slate-800">Kontrak</h5>
                                        <p class="text-xs text-slate-500 mt-1 font-medium">Negosiasi Gaji (Offering)</p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div>
                            <h4 class="text-lg font-bold text-slate-800 mb-4 flex items-center gap-2 font-display"><i class="fa-solid fa-lightbulb text-amber-400"></i> Tips Sekolah Internasional</h4>
                            <div class="flex flex-col gap-3">
                                <div class="bg-white rounded-2xl border border-violet-100 overflow-hidden shadow-sm">
                                    <button onclick="toggleAccordion('swasta-acc-1')" class="w-full flex justify-between items-center px-6 py-4 text-left hover:bg-violet-50/50 transition-colors focus:outline-none group">
                                        <span class="font-bold text-slate-700 group-hover:text-violet-600 transition-colors">1. Wajib Punya Sertifikat TOEFL/IELTS</span>
                                        <i id="icon-swasta-acc-1" class="fa-solid fa-chevron-down text-violet-400 transition-transform duration-300"></i>
                                    </button>
                                    <div id="swasta-acc-1" class="accordion-content px-6 bg-violet-50/30">
                                        <div class="py-4 border-t border-violet-100 text-sm text-slate-600 font-medium leading-relaxed">
                                            <p>Jangan pakai TOEFL abal-abal! Sekolah internasional biasanya minta hasil tes resmi (ETS TOEFL iBT minimal skor 80 atau IDP IELTS minimal Band 6.5). Ini bukti kuat kamu siap ngajar 100% pakai bahasa Inggris.</p>
                                        </div>
                                    </div>
                                </div>
                                <div class="bg-white rounded-2xl border border-violet-100 overflow-hidden shadow-sm">
                                    <button onclick="toggleAccordion('swasta-acc-2')" class="w-full flex justify-between items-center px-6 py-4 text-left hover:bg-violet-50/50 transition-colors focus:outline-none group">
                                        <span class="font-bold text-slate-700 group-hover:text-violet-600 transition-colors">2. Bikin CV ATS Friendly Berbahasa Inggris</span>
                                        <i id="icon-swasta-acc-2" class="fa-solid fa-chevron-down text-violet-400 transition-transform duration-300"></i>
                                    </button>
                                    <div id="swasta-acc-2" class="accordion-content px-6 bg-violet-50/30">
                                        <div class="py-4 border-t border-violet-100 text-sm text-slate-600 font-medium leading-relaxed">
                                            <p>HRD sekolah swasta sering pakai software ATS. Jangan bikin CV yang terlalu heboh desainnya, mending pakai layout minimalis (ATS Friendly), full English, dan sertakan link portofolio digital / video ngajar kamu.</p>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Roadmap Karier Section (Expanded dengan info detail per tahapan) -->
    <section id="peta-tahapan" class="py-24 bg-white relative overflow-hidden">
        <!-- Deco elements -->
        <div class="absolute right-0 top-20 w-64 h-64 bg-pink-100/40 rounded-full blur-3xl"></div>
        <div class="absolute left-0 bottom-20 w-80 h-80 bg-blue-100/40 rounded-full blur-3xl"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="text-center max-w-3xl mx-auto mb-16 fade-in">
                <span class="px-5 py-2 rounded-full bg-pink-50 border border-pink-100 text-pink-600 font-bold text-xs uppercase tracking-widest mb-4 inline-block font-display">Roadmap Karier 🗺️</span>
                <h3 class="text-3xl md:text-5xl font-extrabold text-slate-800 mb-4 font-display">Peta Tahapan Jadi Guru Hebat</h3>
                <p class="text-slate-600 text-lg font-medium">Langkah demi langkah detail yang mesti kamu cicil mulai dari masih di bangku kuliah sampai resmi jadi guru berdampak.</p>
            </div>

            <div class="timeline-container max-w-5xl mx-auto py-8">
                <!-- Step 1 -->
                <div class="timeline-item left md:pr-12 md:text-right mb-12 fade-in">
                    <div class="bg-white p-8 rounded-[2rem] shadow-sm hover:shadow-xl transition-shadow border border-pink-100 relative z-10 timeline-content group">
                        <span class="text-pink-600 font-bold text-xs bg-pink-50 px-3 py-1.5 rounded-full mb-4 inline-block uppercase tracking-wider font-display border border-pink-100 group-hover:bg-pink-100 transition-colors">Semester 5-8 Kuliah</span>
                        <h4 class="text-2xl font-bold text-slate-800 mb-3 font-display">Upgrade Portofolio & Skill Mengajar</h4>
                        <p class="text-slate-600 text-sm leading-relaxed mb-4 font-medium">
                            Jangan cuma nunggu ijazah! IPK di atas 3.00 itu penting, tapi pengalaman lebih dilirik. Aktiflah di program <strong>Kampus Mengajar</strong> buat ngerasain realitas kelas. Mulai kumpulkan karya-karyamu (video ngajar, RPP kreatif, PPT interaktif) di dalam satu <em>link Google Sites</em>/Notion biar gampang dikasih ke HRD nanti.
                        </p>
                        <div class="text-xs bg-slate-50 p-3 rounded-xl border border-slate-100 text-slate-600 inline-block text-left">
                            <strong>Action Item:</strong> Bikin web portofolio gratisan pakai Canva / Notion.
                        </div>
                    </div>
                </div>

                <!-- Step 2 -->
                <div class="timeline-item right md:pl-12 mb-12 fade-in">
                    <div class="bg-white p-8 rounded-[2rem] shadow-sm hover:shadow-xl transition-shadow border border-pink-100 relative z-10 timeline-content group">
                        <span class="text-blue-600 font-bold text-xs bg-blue-50 px-3 py-1.5 rounded-full mb-4 inline-block uppercase tracking-wider font-display border border-blue-100 group-hover:bg-blue-100 transition-colors">Setelah Lulus (Opsional tapi Sangat Disarankan)</span>
                        <h4 class="text-2xl font-bold text-slate-800 mb-3 font-display">Berburu Sertifikat Pendidik (PPG)</h4>
                        <p class="text-slate-600 text-sm leading-relaxed mb-4 font-medium">
                            Dapat ijazah S.Pd itu baru awal. Daftar <strong>PPG Prajabatan</strong> (Pendidikan Profesi Guru) yang disubsidi pemerintah selama setahun. Lulusan PPG bakal dapet Serdik (Sertifikat Pendidik). Serdik ini ibarat <em>"Black Card"</em> yang ngasih nilai SKB mentok (100) pas daftar CASN dan tiket cairnya Tunjangan Profesi Guru (TPG) bulanan.
                        </p>
                    </div>
                </div>

                <!-- Step 3 -->
                <div class="timeline-item left md:pr-12 md:text-right mb-12 fade-in">
                    <div class="bg-white p-8 rounded-[2rem] shadow-sm hover:shadow-xl transition-shadow border border-pink-100 relative z-10 timeline-content group">
                        <span class="text-pink-600 font-bold text-xs bg-pink-50 px-3 py-1.5 rounded-full mb-4 inline-block uppercase tracking-wider font-display border border-pink-100 group-hover:bg-pink-100 transition-colors">Fase Menunggu Bukaan</span>
                        <h4 class="text-2xl font-bold text-slate-800 mb-3 font-display">Persiapan Berkas & Tryout</h4>
                        <p class="text-slate-600 text-sm leading-relaxed mb-4 font-medium">
                            Jangan leyeh-leyeh. Urus KTP, legalisir SKCK, pastiin NIK sinkron sama ijazah. Kalau ngejar CASN: mulai cicil ikut <strong>Tryout SKD online</strong> seminggu sekali (fokus di TIU dan TKP). Kalau ngejar swasta internasional: ambil tes resmi <strong>TOEFL iBT / IELTS</strong> dari sekarang mumpung materi bahasa Inggrismu masih <em>fresh</em>.
                        </p>
                    </div>
                </div>

                <!-- Step 4 -->
                <div class="timeline-item right md:pl-12 mb-12 fade-in">
                    <div class="bg-white p-8 rounded-[2rem] shadow-sm hover:shadow-xl transition-shadow border border-pink-100 relative z-10 timeline-content group">
                        <span class="text-pink-600 font-bold text-xs bg-pink-50 px-3 py-1.5 rounded-full mb-4 inline-block uppercase tracking-wider font-display border border-pink-100 group-hover:bg-pink-100 transition-colors">Fase Eksekusi</span>
                        <h4 class="text-2xl font-bold text-slate-800 mb-3 font-display">Pendaftaran & Masa Tes</h4>
                        <p class="text-slate-600 text-sm leading-relaxed mb-4 font-medium">
                            Pantengin info di medsos BKN / Kemdikbud (buat CASN) atau website karier sekolah favorit. Bikin akun sscasn dengan teliti. Saat tes SKD / Wawancara, jaga kesehatan dan atur manajemen waktu. Jawab soal pakai *mindset* abdi negara atau <em>modern educator</em>.
                        </p>
                    </div>
                </div>

                <!-- Step 5 -->
                <div class="timeline-item left md:pr-12 md:text-right fade-in">
                    <div class="bg-gradient-to-br from-pink-500 to-blue-600 p-8 rounded-[2rem] shadow-xl border border-white/20 relative z-10 timeline-content text-white">
                        <div class="w-14 h-14 bg-white/20 backdrop-blur-sm rounded-2xl flex items-center justify-center text-3xl mb-4 md:ml-auto border border-white/30">
                            <i class="fa-solid fa-star"></i>
                        </div>
                        <h4 class="text-2xl font-bold mb-3 font-display">Pengabdian & Realitas Karier</h4>
                        <p class="text-white/90 text-sm leading-relaxed mb-4 font-medium">
                            Lolos seleksi? <em>Congrats!</em> Tapi kerjaan aslinya baru mulai. Kamu bakal ngadepin kurikulum yang terus <em>update</em>, siswa beda karakter, sampe ngadepin wali murid. Tetep <em>humble</em>, mau belajar hal baru, dan jadilah guru SD yang nyenengin buat anak-anak bangsa!
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Persiapan/Tips Section (Expanded with Modals & Real Contexts) -->
    <section id="persiapan" class="py-24 bg-slate-50 border-t border-slate-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16 fade-in">
                <span class="px-5 py-2 rounded-full bg-blue-50 border border-blue-100 text-blue-600 font-bold text-xs uppercase tracking-widest mb-4 inline-block font-display">Preparation Hacks 💡</span>
                <h3 class="text-3xl md:text-5xl font-extrabold text-slate-800 mb-4 font-display">Bekal Persiapan & Referensi Resmi</h3>
                <p class="text-slate-600 text-lg font-medium">Siapin dokumen penting dari jauh hari dan cek sumber belajar resmi yang kredibel. Klik tombol "Detail" buat lihat panduan lengkapnya.</p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-10 items-start mb-16">
                <!-- Kolom Dokumen Umum -->
                <div class="glass-panel p-8 rounded-[2rem] shadow-sm border border-white fade-in relative overflow-hidden">
                    <div class="absolute top-0 right-0 w-32 h-32 bg-pink-200/20 rounded-full blur-2xl"></div>
                    <h4 class="text-2xl font-bold text-slate-800 mb-4 flex items-center gap-3 font-display relative z-10">
                        <div class="w-12 h-12 rounded-xl bg-pink-100 text-pink-500 flex items-center justify-center text-xl shadow-sm"><i class="fa-solid fa-folder-open"></i></div>
                        <span>Dokumen Umum Pendaftaran</span>
                    </h4>
                    <p class="text-sm text-slate-600 mb-6 leading-relaxed font-medium relative z-10">
                        Jangan nunggu portal daftar buka baru nyari dokumen. Siapin scan aslinya dari sekarang:
                    </p>
                    <div class="space-y-4 relative z-10">
                        <!-- Doc Item -->
                        <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 hover:border-pink-300 transition-colors">
                            <h5 class="font-bold text-slate-800 text-sm flex items-center justify-between font-display tracking-wide">
                                <span class="flex items-center gap-2"><i class="fa-solid fa-id-card text-pink-400"></i> KTP Asli / Keterangan Dukcapil</span>
                                <button onclick="openResourceModal('ktp')" class="text-xs text-pink-500 hover:bg-pink-50 px-3 py-1 rounded-full font-bold transition-colors">Detail <i class="fa-solid fa-arrow-right"></i></button>
                            </h5>
                            <p class="text-xs text-slate-500 mt-2 font-medium">Untuk verifikasi NIK dan data kependudukan secara nasional.</p>
                        </div>
                        <!-- Doc Item -->
                        <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 hover:border-pink-300 transition-colors">
                            <h5 class="font-bold text-slate-800 text-sm flex items-center justify-between font-display tracking-wide">
                                <span class="flex items-center gap-2"><i class="fa-solid fa-graduation-cap text-pink-400"></i> Ijazah & Transkrip S1 PGSD Asli</span>
                                <button onclick="openResourceModal('ijazah')" class="text-xs text-pink-500 hover:bg-pink-50 px-3 py-1 rounded-full font-bold transition-colors">Detail <i class="fa-solid fa-arrow-right"></i></button>
                            </h5>
                            <p class="text-xs text-slate-500 mt-2 font-medium">Syarat mutlak cek linieritas jurusan dengan formasi yang dilamar.</p>
                        </div>
                        <!-- Doc Item -->
                        <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 hover:border-pink-300 transition-colors">
                            <h5 class="font-bold text-slate-800 text-sm flex items-center justify-between font-display tracking-wide">
                                <span class="flex items-center gap-2"><i class="fa-solid fa-file-contract text-pink-400"></i> Pasfoto & Surat Ber-meterai</span>
                                <button onclick="openResourceModal('surat')" class="text-xs text-pink-500 hover:bg-pink-50 px-3 py-1 rounded-full font-bold transition-colors">Detail <i class="fa-solid fa-arrow-right"></i></button>
                            </h5>
                            <p class="text-xs text-slate-500 mt-2 font-medium">Pasfoto background merah dan surat pernyataan resmi (pakai e-meterai).</p>
                        </div>
                    </div>
                </div>

                <!-- Kolom Sumber Belajar Resmi -->
                <div class="glass-panel p-8 rounded-[2rem] shadow-sm border border-white fade-in relative overflow-hidden">
                    <div class="absolute top-0 right-0 w-32 h-32 bg-blue-200/20 rounded-full blur-2xl"></div>
                    <h4 class="text-2xl font-bold text-slate-800 mb-4 flex items-center gap-3 font-display relative z-10">
                        <div class="w-12 h-12 rounded-xl bg-blue-100 text-blue-500 flex items-center justify-center text-xl shadow-sm"><i class="fa-solid fa-book-bookmark"></i></div>
                        <span>Rekomendasi Sumber Belajar</span>
                    </h4>
                    <p class="text-sm text-slate-600 mb-6 leading-relaxed font-medium relative z-10">
                        Banyak yang jualan buku/kursus mahal. Padahal kamu bisa latihan secara kredibel lewat jalur ini:
                    </p>
                    <div class="space-y-4 relative z-10">
                        <!-- Resource Item -->
                        <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 hover:border-blue-300 transition-colors">
                            <h5 class="font-bold text-slate-800 text-sm flex items-center justify-between font-display tracking-wide">
                                <span class="flex items-center gap-2"><i class="fa-solid fa-desktop text-blue-400"></i> Simulasi CAT BKN Resmi</span>
                                <a href="https://cat.bkn.go.id" target="_blank" rel="noopener noreferrer" class="text-xs text-blue-500 hover:bg-blue-50 px-3 py-1 rounded-full font-bold transition-colors">Kunjungi <i class="fa-solid fa-external-link-alt"></i></a>
                            </h5>
                            <p class="text-xs text-slate-500 mt-2 font-medium">BKN nyediain portal simulasi CAT gratis biar kamu gak kagok pas tes pakai komputer betulan.</p>
                        </div>
                        <!-- Resource Item -->
                        <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 hover:border-blue-300 transition-colors">
                            <h5 class="font-bold text-slate-800 text-sm flex items-center justify-between font-display tracking-wide">
                                <span class="flex items-center gap-2"><i class="fa-brands fa-youtube text-blue-400"></i> Tryout & Pembahasan SKD</span>
                            </h5>
                            <p class="text-xs text-slate-500 mt-2 font-medium">Banyak channel Edukasi gratis bahas kupas tuntas soal-soal TWK/TIU. Gak usah ikut bimbel jutaan kalau kamu disiplin belajar mandiri!</p>
                        </div>
                        <!-- Resource Item -->
                        <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 hover:border-blue-300 transition-colors">
                            <h5 class="font-bold text-slate-800 text-sm flex items-center justify-between font-display tracking-wide">
                                <span class="flex items-center gap-2"><i class="fa-solid fa-language text-blue-400"></i> Lembaga Resmi TOEFL / IELTS</span>
                                <button onclick="openResourceModal('toefl')" class="text-xs text-blue-500 hover:bg-blue-50 px-3 py-1 rounded-full font-bold transition-colors">Panduan <i class="fa-solid fa-arrow-right"></i></button>
                            </h5>
                            <p class="text-xs text-slate-500 mt-2 font-medium">Buat incer sekolah internasional, ambil tes <strong>Academic</strong> dari ETS (TOEFL iBT) atau IDP/British Council (IELTS).</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Mini Tips Cards -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Tip 1 -->
                <div class="bg-white border border-slate-100 rounded-3xl overflow-hidden hover:shadow-xl hover:shadow-pink-500/10 transition-all transform hover:-translate-y-1 fade-in cursor-pointer group" onclick="openModal('tip1')">
                    <div class="h-40 bg-slate-100 relative overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1434030216411-0b793f4b4173?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Belajar" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                    </div>
                    <div class="p-5">
                        <span class="text-[10px] font-bold text-pink-600 bg-pink-50 border border-pink-100 px-3 py-1 rounded-full uppercase tracking-wider">CASN</span>
                        <h4 class="font-bold text-slate-800 mt-3 mb-2 leading-tight font-display text-lg">Hack Lolos SKD CPNS</h4>
                        <p class="text-slate-500 text-sm line-clamp-2 font-medium">Trik pembagian menit saat jawab soal TWK, TIU, TKP biar gak kehabisan waktu.</p>
                    </div>
                </div>
                <!-- Tip 2 -->
                <div class="bg-white border border-slate-100 rounded-3xl overflow-hidden hover:shadow-xl hover:shadow-blue-500/10 transition-all transform hover:-translate-y-1 fade-in cursor-pointer group" style="transition-delay: 100ms;" onclick="openModal('tip2')">
                    <div class="h-40 bg-slate-100 relative overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Interview" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                    </div>
                    <div class="p-5">
                        <span class="text-[10px] font-bold text-blue-600 bg-blue-50 border border-blue-100 px-3 py-1 rounded-full uppercase tracking-wider">Swasta</span>
                        <h4 class="font-bold text-slate-800 mt-3 mb-2 leading-tight font-display text-lg">Microteaching in English</h4>
                        <p class="text-slate-500 text-sm line-clamp-2 font-medium">Jangan ceramah! Cara bikin kepsek internasional terpukau pas kamu demo ngajar.</p>
                    </div>
                </div>
                <!-- Tip 3 -->
                <div class="bg-white border border-slate-100 rounded-3xl overflow-hidden hover:shadow-xl hover:shadow-pink-500/10 transition-all transform hover:-translate-y-1 fade-in cursor-pointer group" style="transition-delay: 200ms;" onclick="openModal('tip3')">
                    <div class="h-40 bg-slate-100 relative overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Portofolio" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                    </div>
                    <div class="p-5">
                        <span class="text-[10px] font-bold text-violet-600 bg-violet-50 border border-violet-100 px-3 py-1 rounded-full uppercase tracking-wider">Skill</span>
                        <h4 class="font-bold text-slate-800 mt-3 mb-2 leading-tight font-display text-lg">Bikin Portofolio Estetik</h4>
                        <p class="text-slate-500 text-sm line-clamp-2 font-medium">Bikin HRD kagum cuma dengan link Google Sites isinya video ngajar & karya RPP kamu.</p>
                    </div>
                </div>
                <!-- Tip 4 -->
                <div class="bg-white border border-slate-100 rounded-3xl overflow-hidden hover:shadow-xl hover:shadow-blue-500/10 transition-all transform hover:-translate-y-1 fade-in cursor-pointer group" style="transition-delay: 300ms;" onclick="openModal('tip4')">
                    <div class="h-40 bg-slate-100 relative overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1523240795612-9a054b0db644?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Sertifikasi" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                    </div>
                    <div class="p-5">
                        <span class="text-[10px] font-bold text-pink-600 bg-pink-50 border border-pink-100 px-3 py-1 rounded-full uppercase tracking-wider">Wajib Tahu</span>
                        <h4 class="font-bold text-slate-800 mt-3 mb-2 leading-tight font-display text-lg">Keajaiban Sertifikat Pendidik</h4>
                        <p class="text-slate-500 text-sm line-clamp-2 font-medium">Punya Serdik itu privilege. Ini alasan kenapa freshgrad harus ngejar PPG!</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Asisten AI Section (Gaya Y2K Modern) -->
    <section id="tanya-ai" class="py-24 bg-white border-t border-slate-100 relative overflow-hidden">
        <!-- Floating Pastel Blobs -->
        <div class="absolute top-10 left-10 w-72 h-72 bg-pink-300/15 rounded-full blur-[80px] pointer-events-none"></div>
        <div class="absolute bottom-10 right-10 w-96 h-96 bg-blue-300/15 rounded-full blur-[80px] pointer-events-none"></div>

        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="text-center mb-10 fade-in">
                <div class="inline-flex items-center gap-2 px-5 py-2 rounded-full bg-white border border-slate-100 text-slate-700 font-bold text-sm mb-4 shadow-sm font-display">
                    <i class="fa-solid fa-wand-magic-sparkles text-pink-400"></i> Smart AI Fallback Enabled
                </div>
                <h3 class="text-3xl md:text-5xl font-extrabold text-slate-800 mb-4 font-display">Tanya Asisten AI PathTeacher</h3>
                <p class="text-slate-600 text-lg font-medium">Bebas nanya jadwal, syarat dokumen, info GTK, atau rahasia tembus PPPK/CPNS ke AI kece kita 24/7!</p>
            </div>

            <!-- Chat Container -->
            <div class="glass-panel bg-white/60 rounded-[2.5rem] shadow-[0_20px_50px_rgba(236,72,153,0.08)] border border-white overflow-hidden fade-in flex flex-col" style="height: 550px;">
                <!-- Header Chat -->
                <div class="bg-white/80 border-b border-pink-50 p-5 flex items-center gap-4 text-slate-800 relative z-10">
                    <div class="w-12 h-12 bg-gradient-to-br from-pink-400 to-blue-400 rounded-[1rem] flex items-center justify-center text-white text-xl shadow-md border border-white">
                        <i class="fa-solid fa-robot"></i>
                    </div>
                    <div>
                        <h4 class="font-bold text-lg leading-tight font-display">Asisten PathTeacher</h4>
                        <p class="text-xs text-slate-500 font-bold flex items-center gap-1.5"><span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span> Online & Siap Bantu!</p>
                    </div>
                </div>

                <!-- Chat History -->
                <div id="ai-chat-history" class="flex-1 overflow-y-auto p-6 space-y-6 bg-slate-50/50 custom-scrollbar scroll-smooth">
                    <div class="flex gap-4">
                        <div class="w-10 h-10 rounded-full bg-gradient-to-br from-pink-400 to-blue-400 flex items-center justify-center flex-shrink-0 text-white shadow-sm mt-1 border border-white">
                            <i class="fa-solid fa-robot text-sm"></i>
                        </div>
                        <div class="bg-white p-5 rounded-3xl rounded-tl-none border border-white shadow-sm text-slate-700 text-sm md:text-base max-w-[85%] font-medium leading-relaxed">
                            Hai calon pendidik keren! 👋✨<br><br>
                            Udah gak jaman pusing baca panduan kaku. Aku di sini siap jawab pertanyaan kamu seputar:
                            <ul class="list-disc ml-5 mt-2 space-y-1 text-slate-600">
                                <li>Bocoran jadwal & tips lolos CPNS/PPPK</li>
                                <li>Solusi verifikasi Info GTK</li>
                                <li>Rahasia tembus Sekolah Internasional</li>
                            </ul>
                            <br>
                            <em>Ketik aja bebas di bawah ya, ntar aku bantuin jawab!</em>
                        </div>
                    </div>
                </div>

                <!-- Input Chat -->
                <div class="p-5 bg-white border-t border-slate-100 relative z-10">
                    <div class="relative flex items-end gap-3">
                        <textarea id="ai-user-input" rows="1" class="w-full bg-slate-100/80 border border-slate-200 rounded-[1.5rem] pl-5 pr-14 py-4 text-sm md:text-base focus:outline-none focus:ring-2 focus:ring-pink-300 resize-none max-h-32 transition-all custom-scrollbar font-medium" placeholder="Ketik pertanyaan kamu di sini..." oninput="this.style.height = '';this.style.height = Math.min(this.scrollHeight, 128) + 'px'"></textarea>
                        
                        <button id="ai-send-btn" onclick="sendToGemini()" class="absolute right-3 bottom-2.5 bg-gradient-to-r from-pink-500 to-blue-500 hover:opacity-90 text-white w-11 h-11 rounded-[1.2rem] flex items-center justify-center transition-all shadow-md transform hover:scale-105 active:scale-95 disabled:opacity-50">
                            <i class="fa-solid fa-paper-plane"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Modal Layout untuk Tips & Artikel -->
    <div id="article-modal" class="fixed inset-0 z-[10000] hidden items-center justify-center px-4 sm:px-6">
        <div class="absolute inset-0 bg-slate-900/40 backdrop-blur-sm transition-opacity opacity-0" id="modal-backdrop" onclick="closeModal()"></div>
        <div class="relative bg-white rounded-[2rem] shadow-2xl w-full max-w-3xl max-h-[85vh] flex flex-col transform scale-95 opacity-0 transition-all duration-300 z-10 border border-white" id="modal-panel">
            
            <div class="flex items-center justify-between p-6 border-b border-slate-100">
                <div class="flex items-center gap-3">
                    <span id="modal-tag" class="text-xs font-bold px-4 py-1.5 rounded-full font-display uppercase tracking-wider">Tag</span>
                </div>
                <button onclick="closeModal()" class="text-slate-400 hover:text-pink-500 focus:outline-none bg-slate-50 hover:bg-pink-50 rounded-full w-10 h-10 flex items-center justify-center transition-colors">
                    <i class="fa-solid fa-xmark text-lg"></i>
                </button>
            </div>
            
            <div class="p-8 overflow-y-auto custom-scrollbar" id="modal-content">
                <h3 id="modal-title" class="text-2xl md:text-4xl font-extrabold text-slate-800 mb-6 leading-tight font-display">Judul Artikel</h3>
                <div id="modal-body" class="text-slate-600 space-y-4 text-base leading-relaxed font-medium"></div>
            </div>
            
            <div class="p-6 border-t border-slate-100 bg-slate-50/50 rounded-b-[2rem] flex justify-end">
                <button onclick="closeModal()" class="bg-gradient-to-r from-pink-500 to-blue-500 text-white px-8 py-3 rounded-full font-bold transition-transform transform hover:scale-105 font-display tracking-wide shadow-md">Tutup Artikel</button>
            </div>
        </div>
    </div>

    <!-- Modal untuk Detail Dokumen & Sumber Belajar -->
    <div id="resource-modal" class="fixed inset-0 z-[10000] hidden items-center justify-center px-4 sm:px-6">
        <div class="absolute inset-0 bg-slate-900/40 backdrop-blur-sm transition-opacity opacity-0" id="resource-backdrop" onclick="closeResourceModal()"></div>
        <div class="relative bg-white rounded-[2rem] shadow-2xl w-full max-w-2xl max-h-[85vh] flex flex-col transform scale-95 opacity-0 transition-all duration-300 z-10 border border-white" id="resource-panel">
            
            <div class="flex items-center justify-between p-6 border-b border-slate-100">
                <h3 id="resource-modal-title" class="text-xl font-extrabold text-slate-800 font-display">Judul Detail</h3>
                <button onclick="closeResourceModal()" class="text-slate-400 hover:text-pink-500 focus:outline-none bg-slate-50 hover:bg-pink-50 rounded-full w-10 h-10 flex items-center justify-center transition-colors">
                    <i class="fa-solid fa-xmark text-lg"></i>
                </button>
            </div>
            
            <div class="p-8 overflow-y-auto custom-scrollbar text-slate-600 text-sm md:text-base leading-relaxed space-y-4 font-medium" id="resource-modal-body">
                <!-- Konten dinamis dari JS -->
            </div>
            
            <div class="p-6 border-t border-slate-100 bg-slate-50/50 rounded-b-[2rem] flex justify-end">
                <button onclick="closeResourceModal()" class="bg-gradient-to-r from-pink-500 to-blue-500 text-white px-8 py-3 rounded-full font-bold transition-transform transform hover:scale-105 font-display tracking-wide shadow-md">Paham!</button>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-slate-900 text-white pt-16 pb-8 border-t-4 border-pink-500">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-12 mb-12">
                <div class="col-span-1 md:col-span-2">
                    <div class="flex items-center gap-2 mb-4">
                        <div class="w-10 h-10 bg-gradient-to-br from-pink-500 to-blue-500 rounded-xl flex items-center justify-center text-white font-bold text-xl">
                            <i class="fa-solid fa-graduation-cap"></i>
                        </div>
                        <span class="y2k-cyber-text-sm text-2xl">PathTeacher</span>
                    </div>
                    <p class="text-slate-400 mb-6 max-w-sm font-medium leading-relaxed">
                        Portal panduan karier ter-cozy buat mahasiswa dan alumni PGSD Indonesia. Bye-bye panduan kaku, <em>hello future teacher!</em>
                    </p>
                </div>
                
                <div>
                    <h4 class="text-lg font-bold mb-4 font-display text-white">Menu Utama</h4>
                    <ul class="space-y-3 text-slate-400 font-medium">
                        <li><a href="#beranda" class="hover:text-pink-400 transition-colors">Beranda</a></li>
                        <li><a href="#jalur-karier" class="hover:text-pink-400 transition-colors">Jalur CPNS & PPPK</a></li>
                        <li><a href="#peta-tahapan" class="hover:text-pink-400 transition-colors">Roadmap Karier</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="text-lg font-bold mb-4 font-display text-white">Dukungan</h4>
                    <ul class="space-y-3 text-slate-400 font-medium">
                        <li><a href="#tanya-ai" class="hover:text-pink-400 transition-colors">Tanya AI PathTeacher</a></li>
                        <li><a href="#" class="hover:text-pink-400 transition-colors">Hubungi Kami</a></li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-slate-800 pt-8 text-center text-slate-500 text-sm font-bold font-display tracking-wide">
                <p>&copy; 2026 PathTeacher PGSD. Dibuat dengan 💖 untuk Guru SD masa depan.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript (All Logic Maintained + Expanded Tarot Motivations & Classic Back Styling) -->
    <script>
        // Intro Curtain Logic
        function openCurtains() {
            const container = document.getElementById('intro-curtains');
            container.classList.add('curtain-open');
            document.body.style.overflow = 'auto';

            setTimeout(() => {
                container.style.display = 'none';
            }, 1200);
        }

        // Mobile Menu
        const btn = document.getElementById('mobile-menu-btn');
        const menu = document.getElementById('mobile-menu');

        btn.addEventListener('click', () => {
            menu.classList.toggle('hidden');
        });

        const mobileLinks = menu.querySelectorAll('a');
        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                menu.classList.add('hidden');
            });
        });

        // Observer Animations
        const observerOptions = { root: null, rootMargin: '0px', threshold: 0.15 };
        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('appear');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach((element) => observer.observe(element));

        // Tab Navigation
        function openTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.remove('active'));
            document.querySelectorAll('.tab-btn').forEach(el => el.classList.remove('active'));

            document.getElementById('content-' + tabId).classList.add('active');
            const activeBtn = document.getElementById('btn-' + tabId);
            activeBtn.classList.add('active');
            
            // Adjusting Active Tab Colors (Y2K Palette)
            if (tabId === 'cpns') {
                activeBtn.style.color = '#be185d'; // pink-700
                activeBtn.style.borderColor = '#db2777'; // pink-600
            } else if (tabId === 'pppk') {
                activeBtn.style.color = '#1d4ed8'; // blue-700
                activeBtn.style.borderColor = '#2563eb'; // blue-600
            } else if (tabId === 'swasta') {
                activeBtn.style.color = '#6d28d9'; // violet-700
                activeBtn.style.borderColor = '#7c3aed'; // violet-600
            }
        }

        // Accordions
        function toggleAccordion(id) {
            const content = document.getElementById(id);
            const icon = document.getElementById('icon-' + id);
            
            if (!content.classList.contains('open')) {
                const parentTab = content.closest('.tab-content');
                parentTab.querySelectorAll('.accordion-content').forEach(el => el.classList.remove('open'));
                parentTab.querySelectorAll('.fa-chevron-down').forEach(el => el.style.transform = 'rotate(0deg)');

                content.classList.add('open');
                icon.style.transform = 'rotate(180deg)';
            } else {
                content.classList.remove('open');
                icon.style.transform = 'rotate(0deg)';
            }
        }

        // --- EXPANDED TAROT MOTIVATIONS (Bahasa Indonesia & English - 24 Pilihan Kata Estetik) ---
        // Penulisan menggunakan elemen span untuk format terjemahan agar rapi dan tidak merusak layout HTML utama.
        const tarotMotivations = [
            { word: "Resilience", desc: "Hadapi setiap perubahan kurikulum dan dinamika kelas dengan hati yang tangguh. Kesulitan hari ini adalah kekuatanmu esok hari.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Face every curriculum change and classroom dynamic with a resilient heart. Today's difficulty is tomorrow's strength.</span>" },
            { word: "Inspiration", desc: "Jadilah percikan cahaya yang menyalakan rasa ingin tahu dan keberanian siswa untuk bermimpi besar.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Be the spark of light that ignites your students' curiosity and courage to dream big.</span>" },
            { word: "Patience", desc: "Kesabaranmu dalam membimbing anak yang tertinggal adalah bukti cinta sejati seorang pendidik. Jangan menyerah pada mereka.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Your patience in guiding lagging students is proof of an educator's true love. Never give up on them.</span>" },
            { word: "Empathy", desc: "Pahami bahwa setiap kenakalan anak seringkali adalah permintaan tolong yang tak terucapkan. Dengarkan dengan hati.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Understand that a child's misbehavior is often an unspoken plea for help. Listen with your heart.</span>" },
            { word: "Consistency", desc: "Kehebatan seorang guru dibangun dari dedikasi kecil yang dilakukan secara konsisten setiap hari, bukan dalam semalam.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>A teacher's greatness is built through small, consistent dedication every single day, not overnight.</span>" },
            { word: "Innovation", desc: "Jangan takut mencoba metode mengajar baru. Kreativitasmu adalah kunci membuka potensi tersembunyi setiap siswa.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Don't be afraid to try new teaching methods. Your creativity is the key to unlocking every student's hidden potential.</span>" },
            { word: "Adaptability", desc: "Guru yang sukses adalah ia yang mau terus belajar dan beradaptasi dengan zaman, bukan yang terjebak di masa lalu.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>A successful teacher is one who continues to learn and adapt to the times, not one stuck in the past.</span>" },
            { word: "Dedication", desc: "Waktu dan tenaga yang kamu curahkan mungkin tak selalu diapresiasi sekarang, tapi kelak akan melahirkan pemimpin hebat.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>The time and energy you pour in may not always be appreciated now, but they will birth great leaders.</span>" },
            { word: "Growth Mindset", desc: "Percayalah bahwa kecerdasan bisa dilatih. Tanamkan pola pikir berkembang ini pada dirimu sendiri dan murid-muridmu.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Believe that intelligence can be developed. Instill this growth mindset in yourself and your students.</span>" },
            { word: "Passion", desc: "Mengajar tanpa gairah hanyalah transfer informasi. Mengajar dengan hati akan menyentuh jiwa dan mengubah hidup seseorang.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Teaching without passion is merely information transfer. Teaching with heart touches souls and changes lives.</span>" },
            { word: "Courage", desc: "Beranikan dirimu mengambil tantangan baru, ikut seleksi yang sulit, dan mengajar di lingkungan yang belum pernah kamu coba.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Have the courage to take new challenges, join difficult selections, and teach in environments you've never tried.</span>" },
            { word: "Focus", desc: "Abaikan kebisingan birokrasi dan keluhan. Tetaplah fokus pada tujuan utamamu: mencerdaskan dan membentuk karakter anak bangsa.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Ignore the noise of bureaucracy and complaints. Stay focused on your main goal: educating and shaping the nation's children.</span>" },
            { word: "Optimism", desc: "Selalu bawa energi positif ke kelas. Optimismemu menular dan bisa mengubah hari buruk seorang anak menjadi sangat luar biasa.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Always bring positive energy to class. Your optimism is contagious and can turn a child's bad day into an amazing one.</span>" },
            { word: "Creativity", desc: "Jadikan kelasmu sebagai kanvas. Warnai dengan metode interaktif yang membuat siswa selalu rindu untuk kembali belajar padamu.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Make your class a canvas. Paint it with interactive methods that make students always yearn to come back and learn from you.</span>" },
            { word: "Leadership", desc: "Guru adalah pemimpin di kelasnya. Bimbing mereka bukan dengan rasa takut, melainkan dengan teladan nyata dan rasa hormat.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>A teacher is the leader of their class. Guide them not with fear, but with real examples and respect.</span>" },
            { word: "Energy", desc: "Kelelahan itu pasti ada, tapi ingatlah bahwa antusiasmemu adalah bahan bakar utama bagi motivasi belajar siswa di ruang kelas.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Exhaustion is certain, but remember that your enthusiasm is the main fuel for your students' learning motivation in the classroom.</span>" },
            { word: "Mindfulness", desc: "Hadirkan dirimu seutuhnya di kelas. Tinggalkan sejenak beban pribadimu dan nikmati momen berharga bersama anak didikmu.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Be fully present in class. Leave your personal burdens behind for a moment and enjoy the precious moments with your students.</span>" },
            { word: "Lifelong Learner", desc: "Untuk bisa mendidik dengan baik, rela lah menjadi murid abadi. Teruslah membaca, belajar, dan mengasah kompetensimu.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>To educate well, be willing to be an eternal student. Keep reading, learning, and honing your competencies.</span>" },
            { word: "Appreciation", desc: "Beri pujian pada prosesnya, bukan hanya hasil akhir. Apresiasi kecilmu bisa menjadi memori terindah yang diingat siswa seumur hidup.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Praise the process, not just the final result. Your small appreciation can be the most beautiful memory a student remembers for a lifetime.</span>" },
            { word: "Sincerity", desc: "Ketulusan hati seorang pendidik tidak akan pernah bisa digantikan oleh kecerdasan buatan secanggih apapun di dunia ini.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>The sincerity of an educator's heart can never be replaced by artificial intelligence, no matter how advanced it is in this world.</span>" },
            { word: "Impact", desc: "Sadari bahwa setiap kata yang kamu ucapkan di kelas sedang membentuk masa depan peradaban. Mulailah berdampak hari ini.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Realize that every word you say in class is shaping the future of civilization. Start making an impact today.</span>" },
            { word: "Compassion", desc: "Rangkul siswa yang paling sulit diatur, karena seringkali merekalah yang paling membutuhkan kasih sayang dan bimbingan gurunya.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Embrace the most difficult students to manage, because they are often the ones who most need their teacher's love and guidance.</span>" },
            { word: "Perseverance", desc: "Jalan menjadi pendidik profesional mungkin berliku, tapi ketekunanmu akan membuahkan hasil yang manis. Jangan pernah berhenti.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>The path to becoming a professional educator may be winding, but your perseverance will yield sweet results. Never stop.</span>" },
            { word: "Blessing", desc: "Setiap ilmu yang kamu bagikan dengan ikhlas akan menjadi ladang pahala yang tak terputus. Mengajar adalah berkah yang tiada tara.<br><span class='text-[10px] md:text-xs text-slate-400 italic mt-3 block font-sans'>Every knowledge you share sincerely will become an unbroken field of reward. Teaching is an incomparable blessing.</span>" }
        ];

        function flipSingleCard() {
            const card = document.getElementById('single-tarot-card');
            card.classList.toggle('flipped');
        }

        function shuffleSingleTarot() {
            const card = document.getElementById('single-tarot-card');
            const icon = document.getElementById('shuffle-icon');
            
            // Animasi putar ikon & kocok kartu
            icon.classList.add('fa-spin');
            card.classList.add('shuffling');

            setTimeout(() => {
                // Pilih acak 1 kartu dari daftar motivasi yang melimpah
                const randomCard = tarotMotivations[Math.floor(Math.random() * tarotMotivations.length)];
                
                document.getElementById('tarot-word').innerText = randomCard.word;
                
                // MENGGUNAKAN innerHTML AGAR TAG HTML (seperti <span>, <br>) DI DALAM ARRAY BISA TER-RENDER DENGAN BAIK
                document.getElementById('tarot-desc').innerHTML = randomCard.desc;

                // Tutup kembali kartu lalu buka otomatis setelah diacak
                card.classList.remove('flipped');
                card.classList.remove('shuffling');
                icon.classList.remove('fa-spin');

                setTimeout(() => {
                    card.classList.add('flipped');
                }, 200);
            }, 600);
        }

        // --- DATA MINAT & BAKAT KUIS (10 Pertanyaan) ---
        const quizData = [
            {
                question: "1. Kalo disuruh milih vibes tempat kerja impian kamu, mana yang paling pas?",
                options: [
                    { text: "Aman, stabil, ada jaminan hari tua sampai pensiun (PNS).", type: "cpns" },
                    { text: "Yang penting cepet kerja ngabdi, digaji setara PNS, fleksibel sistem kontrak.", type: "pppk" },
                    { text: "Dinamo, *fast-paced*, fasilitas elite, dan bayaran tinggi.", type: "swasta" }
                ]
            },
            {
                question: "2. Gimana tingkat Pe-De kamu pake Bahasa Inggris pas ngomong di depan umum?",
                options: [
                    { text: "Lebih nyaman full Bahasa Indonesia aja deh.", type: "cpns" },
                    { text: "Lumayan buat percakapan dasar sehari-hari.", type: "pppk" },
                    { text: "Lancar jaya! Siap kalau disuruh ngajar *full English* tiap hari.", type: "swasta" }
                ]
            },
            {
                question: "3. Menurut kamu, ujian seleksi masuk kerja yang ideal tuh kaya apa?",
                options: [
                    { text: "Ujian tertulis di depan komputer (CAT), nguji logika & wawasan bangsa.", type: "cpns" },
                    { text: "Ujian studi kasus tentang cara ngajar dan selesain masalah anak di kelas.", type: "pppk" },
                    { text: "Mending langsung disuruh praktek *Microteaching* diliat bule/kepsek.", type: "swasta" }
                ]
            },
            {
                question: "4. Kurikulum apa yang paling pengen kamu *explore* buat diajarin?",
                options: [
                    { text: "Kurikulum Nasional/Merdeka yang diterapin di sekolah negeri pada umumnya.", type: "cpns" },
                    { text: "Kurikulum Merdeka dengan modifikasi kebutuhan sekolah daerah.", type: "pppk" },
                    { text: "Kurikulum global kaya Cambridge Primary atau IB (International Baccalaureate).", type: "swasta" }
                ]
            },
            {
                question: "5. Pendapat kamu tentang birokrasi & seragam dinas (kaya Khaki/Batik Korpri)?",
                options: [
                    { text: "Bangga banget! Emang cita-cita dari kecil pengen pake seragam itu.", type: "cpns" },
                    { text: "Biasa aja, yang penting ngajar resmi dapet SK dari pemerintah.", type: "pppk" },
                    { text: "Kurang suka birokrasi kaku, mending pake *smart casual* aja tiap hari.", type: "swasta" }
                ]
            },
            {
                question: "6. Kalo ditanya soal target waktu, kamu maunya kapan dapet kerjaan?",
                options: [
                    { text: "Rela nunggu bukaan setahun sekali, yang penting status PNS seumur hidup.", type: "cpns" },
                    { text: "Pengen cepet diangkat, peluang formasinya gede, bisa mulai secepatnya.", type: "pppk" },
                    { text: "Gak masalah kapan aja nyari lowongan sendiri di LinkedIn/portal *career*.", type: "swasta" }
                ]
            },
            {
                question: "7. Kalo disuruh milih murid, kamu lebih siap ngadepin lingkungan kaya apa?",
                options: [
                    { text: "Murid di lingkungan sekolah negeri biasa, dari berbagai latar belakang ekonomi.", type: "cpns" },
                    { text: "Siswa sekolah daerah yang butuh guru dengan jiwa pengabdian dan kesabaran tinggi.", type: "pppk" },
                    { text: "Murid ekspatriat atau dari keluarga *high-profile* dengan budaya beda-beda.", type: "swasta" }
                ]
            },
            {
                question: "8. Gimana pandangan kamu tentang Sertifikat Pendidik (Serdik)?",
                options: [
                    { text: "Wajib punya biar dapet nilai 100 gratis pas daftar CASN nanti.", type: "cpns" },
                    { text: "Penting buat narik TPG, tapi kalo bisa keterima PPPK duluan gpp.", type: "pppk" },
                    { text: "Penting, tapi skor TOEFL iBT dan skill *speaking* lebih krusial.", type: "swasta" }
                ]
            },
            {
                question: "9. Modal utama kamu buat naklukin hati *interviewer* itu apa?",
                options: [
                    { text: "Paham ideologi Pancasila dan punya jiwa melayani negara.", type: "cpns" },
                    { text: "Punya pengalaman lapangan nanganin anak nakal / pas Kampus Mengajar.", type: "pppk" },
                    { text: "Portofolio digital estetik dan kemampuan adaptasi kurikulum luar negeri.", type: "swasta" }
                ]
            },
            {
                question: "10. Dalam 5 tahun ke depan, kamu ngebayangin posisi kariermu ada di tahap apa?",
                options: [
                    { text: "Jadi Guru PNS golongan III yang lagi antre naik pangkat struktural.", type: "cpns" },
                    { text: "Guru PPPK yang mapan dan dihormati masyarakat, nunggu perpanjangan kontrak.", type: "pppk" },
                    { text: "Menjadi *Homeroom Teacher* elit atau promosi ngajar di luar negeri.", type: "swasta" }
                ]
            }
        ];

        let currentQuizIndex = 0;
        let quizScores = { cpns: 0, pppk: 0, swasta: 0 };

        function startQuiz() {
            document.getElementById('quiz-intro').classList.add('hidden');
            document.getElementById('quiz-questions-screen').classList.remove('hidden');
            currentQuizIndex = 0;
            quizScores = { cpns: 0, pppk: 0, swasta: 0 };
            loadQuizQuestion();
        }

        function loadQuizQuestion() {
            const q = quizData[currentQuizIndex];
            const total = quizData.length;
            const progress = ((currentQuizIndex + 1) / total) * 100;

            document.getElementById('quiz-counter').innerText = `Pertanyaan ${currentQuizIndex + 1}/${total}`;
            document.getElementById('quiz-progress-text').innerText = `${Math.round(progress)}%`;
            document.getElementById('quiz-progress-bar').style.width = `${progress}%`;
            document.getElementById('quiz-question-title').innerText = q.question;

            const optionsList = document.getElementById('quiz-options-list');
            optionsList.innerHTML = '';

            q.options.forEach((opt) => {
                const btn = document.createElement('button');
                btn.className = "w-full text-left p-4 rounded-2xl border border-slate-200 hover:border-pink-400 hover:bg-pink-50 transition-all font-medium text-slate-700 text-sm md:text-base flex items-center justify-between group shadow-sm bg-white";
                btn.innerHTML = `
                    <span>${opt.text}</span>
                    <i class="fa-solid fa-check text-slate-200 group-hover:text-pink-500 transition-colors"></i>
                `;
                btn.onclick = () => selectQuizAnswer(opt.type);
                optionsList.appendChild(btn);
            });
        }

        function selectQuizAnswer(type) {
            quizScores[type]++;
            currentQuizIndex++;

            if (currentQuizIndex < quizData.length) {
                loadQuizQuestion();
            } else {
                showQuizResult();
            }
        }

        function showQuizResult() {
            document.getElementById('quiz-questions-screen').classList.add('hidden');
            document.getElementById('quiz-result-screen').classList.remove('hidden');

            let highestType = 'cpns';
            if (quizScores.pppk > quizScores.cpns && quizScores.pppk >= quizScores.swasta) highestType = 'pppk';
            else if (quizScores.swasta > quizScores.cpns && quizScores.swasta > quizScores.pppk) highestType = 'swasta';

            const resultTitle = document.getElementById('result-title');
            const resultDesc = document.getElementById('result-description');
            const resultQuote = document.getElementById('result-quote');
            const actionBtn = document.getElementById('result-action-btn');

            if (highestType === 'cpns') {
                resultTitle.innerText = "Target Kamu: Guru CPNS (PNS) 🏛️";
                resultDesc.innerHTML = "Vibes kamu cocok banget jadi abdi negara! Kamu suka kepastian, jaminan pensiun, dan bangga bisa melayani negeri dari dalam sistem resmi. Mulai sekarang <em>push</em> hafalan TWK dan logika TIU ya!";
                resultQuote.innerText = `"Stabilitas adalah kemewahan yang diraih lewat ketekunan belajar dari sekarang."`;
                actionBtn.onclick = () => openTab('cpns');
            } else if (highestType === 'pppk') {
                resultTitle.innerText = "Target Kamu: Guru PPPK 📝";
                resultDesc.innerHTML = "Kamu tipe orang yang sat-set, solutif, dan *ready to work*! Jalur PPPK cocok buat kamu yang pengen cepet punya SK ngajar dengan penghasilan stabil, fokus asah skill pedagogik kelas aja.";
                resultQuote.innerText = `"Bukan tentang seragamnya, tapi seberapa cepat kamu turun tangan buat cerdasin anak bangsa."`;
                actionBtn.onclick = () => openTab('pppk');
            } else {
                resultTitle.innerText = "Target Kamu: Sekolah Internasional 🌍";
                resultDesc.innerHTML = "Anak skena global banget! Kamu cocok di lingkungan multikultural yang bebas birokrasi, gaji elit, dan pakai *full English*. Mulai sekarang kejar skor TOEFL dan pelajarin kurikulum IB!";
                resultQuote.innerText = `"Dream big, teach globally. Kesempatanmu gak cuma di dalam negeri."`;
                actionBtn.onclick = () => openTab('swasta');
            }
        }

        function resetQuiz() {
            document.getElementById('quiz-result-screen').classList.add('hidden');
            document.getElementById('quiz-intro').classList.remove('hidden');
        }

        // --- DATA MODAL TIPS & RESOURCE ---
        const tipsData = {
            tip1: {
                title: "Hack Lolos Passing Grade SKD CPNS",
                tag: "CASN",
                tagColor: "bg-pink-100 text-pink-700 border border-pink-200",
                content: `
                    <p class="font-medium text-slate-800">SKD (Seleksi Kompetensi Dasar) sering bikin peserta nangis di ujung waktu. Ini trik atur waktunya:</p>
                    <ul class="list-disc ml-5 space-y-2 mt-3 text-slate-600">
                        <li><strong>TKP (± 35 menit):</strong> Kerjain duluan. Gak ada nilai nol, jadi pasti nyumbang poin. Jawabannya harus idealis: pilih opsi yang paling profesional, inovatif, dan kolaboratif.</li>
                        <li><strong>TIU (± 40 menit):</strong> Habis TKP, masuk ke logika TIU. Sikat deret angka dan silogisme. Kalo nemu hitungan aljabar panjang yang bikin mumet, <em>SKIP</em> dulu! Jangan buang 5 menit buat 1 soal.</li>
                        <li><strong>TWK (± 25 menit):</strong> Sejarah & UUD. Ini pure ingatan. Jawab pakai insting pertama karena kalau dipikir kelamaan malah makin bingung.</li>
                    </ul>
                `
            },
            tip2: {
                title: "Mastering Microteaching English",
                tag: "Sekolah Swasta Internasional",
                tagColor: "bg-blue-100 text-blue-700 border border-blue-200",
                content: `
                    <p class="font-medium text-slate-800">Sekolah SPK (Satuan Pendidikan Kerjasama) benci banget sama guru yang ngajar pake metode "ceramah doang".</p>
                    <ul class="list-disc ml-5 space-y-2 mt-3 text-slate-600">
                        <li><strong>Inquiry-Based:</strong> Jangan kasih tahu jawabannya langsung. Kasih murid <em>clue</em> atau barang (realia) biar mereka nebak sendiri materinya.</li>
                        <li><strong>Positive Reinforcement:</strong> Kasih pujian spesifik (misal: "I love how you solved that puzzle, Emma!") jangan cuma bilang "Good job!".</li>
                        <li><strong>Gak perlu aksen fakes:</strong> Gak usah maksa aksen British/American kalo gak natural. Yang penting <em>pronunciation</em> jelas dan <em>grammar</em> gak berantakan.</li>
                    </ul>
                `
            },
            tip3: {
                title: "Bikin Portofolio Guru Estetik",
                tag: "Umum / Skill",
                tagColor: "bg-violet-100 text-violet-700 border border-violet-200",
                content: `
                    <p class="font-medium text-slate-800">CV PDF udah biasa, kamu harus punya <em>Digital Portfolio</em>!</p>
                    <ul class="list-disc ml-5 space-y-2 mt-3 text-slate-600">
                        <li>Bikin pakai <strong>Google Sites</strong> atau <strong>Notion</strong> (gratis dan tampilannya modern).</li>
                        <li>Isi dengan: rekaman 3-5 menit kamu lagi asik ngajar (Microteaching), foto-foto pas Kampus Mengajar, desain PPT keren yang pernah kamu bikin, dan *Lesson Plan* (RPP) yang formatnya estetik (pakai Canva).</li>
                        <li>Taruh link portofolio (atau QR Code) itu di CV utama kamu. Dijamin HRD auto ngelirik!</li>
                    </ul>
                `
            },
            tip4: {
                title: "Keajaiban Sertifikat Pendidik (Serdik)",
                tag: "Sertifikasi",
                tagColor: "bg-pink-100 text-pink-700 border border-pink-200",
                content: `
                    <p class="font-medium text-slate-800">Abis lulus jangan cuma rebahan nunggu bukaan CPNS. Langsung gas daftar PPG Prajabatan!</p>
                    <ul class="list-disc ml-5 space-y-2 mt-3 text-slate-600">
                        <li><strong>The Golden Ticket:</strong> Punya Serdik linier artinya kamu dapet <strong>afirmasi poin 100 maksimal</strong> buat tes SKB CASN. Kamu nyaris gak bisa dikalahin peserta lain yang gak punya Serdik.</li>
                        <li><strong>Tunjangan Cair:</strong> Syarat utama dapet Tunjangan Profesi Guru (gaji dobel) dari negara itu ya punya Serdik ini.</li>
                        <li><strong>Subsidi Penuh:</strong> Program Prajabatan dari Kemdikbud biasanya disubsidi. Kamu kuliah gratis setahun buat masa depan yang terjamin!</li>
                    </ul>
                `
            }
        };

        const resourceDetails = {
            ktp: {
                title: "Panduan Dokumen: KTP & NIK",
                content: `
                    <p class="mb-3">KTP bukan sekadar kartu, NIK di dalemnya adalah nyawa pendaftaran SSCASN kamu.</p>
                    <ul class="list-disc ml-5 space-y-2">
                        <li>Pastiin nama, tempat, dan tanggal lahir di KTP sama persis dengan yang ada di <strong>Ijazah S1 PGSD</strong>.</li>
                        <li>Kalo beda sehuruf aja, mending cepet urus surat perbaikan ke Dukcapil sekarang sebelum portal pendaftaran BKN buka.</li>
                        <li>Siapin scan KTP asli bentuk JPEG/JPG (ukuran max biasanya 200-300kb). Jangan nge-scan KTP hasil fotokopian!</li>
                    </ul>
                `
            },
            ijazah: {
                title: "Panduan Dokumen: Ijazah & Transkrip S1 PGSD",
                content: `
                    <p class="mb-3">Ini dokumen penentu kamu bisa ngelamar formasi yang kamu mau.</p>
                    <ul class="list-disc ml-5 space-y-2">
                        <li>Sistem BKN bakal ngecek apakah jurusan di Ijazah kamu <strong>linier</strong> sama formasi yang dipilih (misal: S1 PGSD wajib linier ke formasi Guru Kelas Ahli Pertama).</li>
                        <li>Cek dari sekarang nama dan ijazah kamu udah kedaftar dan aktif di <strong>PDDIKTI (pddikti.kemdikbud.go.id)</strong>. Kalo belum, buruan lapor admin kampus!</li>
                        <li>Scan dari Ijazah & Transkrip Asli berwarna, bukan yang legalisir hitam putih (tergantung syarat instansi).</li>
                    </ul>
                `
            },
            surat: {
                title: "Panduan Dokumen: Pasfoto & E-Meterai",
                content: `
                    <p class="mb-3">Dokumen teknis yang sering bikin peserta gagal di tahap Administrasi.</p>
                    <ul class="list-disc ml-5 space-y-2">
                        <li><strong>Pasfoto:</strong> Pakai kemeja putih rapi, background merah terang (buat CPNS/PPPK). Jangan pakai editan wajah berlebihan (filter beauty) karena bisa nyusahin <em>Face Recognition</em> pas hari H ujian!</li>
                        <li><strong>E-Meterai:</strong> Beli di agen resmi Peruri. Jangan tanda tangan nutupin barcode meterai elektroniknya. Tempel meterai di sebelah kiri/kanan tanda tangan.</li>
                    </ul>
                `
            },
            toefl: {
                title: "Panduan Resmi Sertifikasi TOEFL & IELTS",
                content: `
                    <p class="mb-3">Buat kamu yang ngincer sekolah elit / SPK, lupain sertifikat TOEFL EPT kampus yang cuma 50 ribu itu.</p>
                    <ul class="list-disc ml-5 space-y-2">
                        <li><strong>TOEFL iBT (Internet-based Test):</strong> Resmi dari ETS. Skor yang aman buat lamar guru kelas biasanya minimal 80-90+. Biayanya emang mahal (sekitar 3 jutaan), tapi <em>worth it</em> banget buat gaji belasan juta nantinya.</li>
                        <li><strong>IELTS (Academic):</strong> Dari IDP/British Council. Rata-rata sekolah elit minta band skor 6.5 atau 7.0. Fokus latihan di bagian <em>Speaking</em> dan <em>Writing</em>.</li>
                    </ul>
                `
            }
        };

        // Open Tips Modal
        function openModal(tipId) {
            const modal = document.getElementById('article-modal');
            const backdrop = document.getElementById('modal-backdrop');
            const panel = document.getElementById('modal-panel');
            const data = tipsData[tipId];

            if(!data) return;

            document.getElementById('modal-title').innerText = data.title;
            document.getElementById('modal-body').innerHTML = data.content;
            
            const tagEl = document.getElementById('modal-tag');
            tagEl.innerText = data.tag;
            tagEl.className = "text-[10px] font-extrabold px-4 py-1.5 rounded-full uppercase tracking-widest " + data.tagColor;

            modal.classList.remove('hidden');
            modal.classList.add('flex');
            setTimeout(() => {
                backdrop.classList.remove('opacity-0');
                backdrop.classList.add('opacity-100');
                panel.classList.remove('opacity-0', 'scale-95');
                panel.classList.add('opacity-100', 'scale-100');
            }, 10);
            document.body.style.overflow = 'hidden';
        }

        // Close Tips Modal
        function closeModal() {
            const modal = document.getElementById('article-modal');
            const backdrop = document.getElementById('modal-backdrop');
            const panel = document.getElementById('modal-panel');

            backdrop.classList.remove('opacity-100');
            backdrop.classList.add('opacity-0');
            panel.classList.remove('opacity-100', 'scale-100');
            panel.classList.add('opacity-0', 'scale-95');

            setTimeout(() => {
                modal.classList.add('hidden');
                modal.classList.remove('flex');
                if (document.getElementById('intro-curtains').style.display === 'none') {
                    document.body.style.overflow = 'auto';
                }
            }, 300);
        }

        // Open Resource Modal
        function openResourceModal(resId) {
            const modal = document.getElementById('resource-modal');
            const backdrop = document.getElementById('resource-backdrop');
            const panel = document.getElementById('resource-panel');
            const data = resourceDetails[resId];

            if(!data) return;

            document.getElementById('resource-modal-title').innerText = data.title;
            document.getElementById('resource-modal-body').innerHTML = data.content;

            modal.classList.remove('hidden');
            modal.classList.add('flex');

            setTimeout(() => {
                backdrop.classList.remove('opacity-0');
                backdrop.classList.add('opacity-100');
                panel.classList.remove('opacity-0', 'scale-95');
                panel.classList.add('opacity-100', 'scale-100');
            }, 10);
            document.body.style.overflow = 'hidden';
        }

        // Close Resource Modal
        function closeResourceModal() {
            const modal = document.getElementById('resource-modal');
            const backdrop = document.getElementById('resource-backdrop');
            const panel = document.getElementById('resource-panel');

            backdrop.classList.remove('opacity-100');
            backdrop.classList.add('opacity-0');
            panel.classList.remove('opacity-100', 'scale-100');
            panel.classList.add('opacity-0', 'scale-95');

            setTimeout(() => {
                modal.classList.add('hidden');
                modal.classList.remove('flex');
                if (document.getElementById('intro-curtains').style.display === 'none') {
                    document.body.style.overflow = 'auto';
                }
            }, 300);
        }

        // --- AI CHATBOT LOGIC (Robust Fallback) ---
        marked.setOptions({ breaks: true, gfm: true });

        async function sendToGemini() {
            const inputEl = document.getElementById('ai-user-input');
            const sendBtn = document.getElementById('ai-send-btn');
            const userText = inputEl.value.trim();

            if (!userText) return;

            appendMessage('user', userText);
            inputEl.value = '';
            inputEl.style.height = ''; 
            inputEl.disabled = true;
            sendBtn.disabled = true;

            const loadingId = appendLoading();

            try {
                // System Prompt untuk AI
                const systemPrompt = "Kamu adalah 'Asisten PathTeacher', konsultan karier AI yang santai, gaul, dan profesional khusus ngebantu mahasiswa & lulusan S1 PGSD di Indonesia. Jawabanmu informatif tentang CPNS, PPPK, Info GTK, PPG, dan sekolah internasional. Gunakan bahasa Indonesia gaya Gen-Z yang asyik tapi tetap sopan.";
                
                let success = false;
                let aiResponseText = "";
                const lower = userText.toLowerCase();

                // 1. SMART LOCAL FALLBACK: Deteksi keyword spesifik untuk respon instan dan akurat
                if (lower.includes('gtk') || lower.includes('info gtk') || lower.includes('validasi ijazah')) {
                    aiResponseText = "Santai, buat ngecek validitas ijazah PGSD kamu supaya aman daftar CASN:\n\n1. Langsung gas buka web resminya di **info.gtk.kemdikbud.go.id**\n2. Login pakai akun PTK yang udah didaftarin operator Dapodik sekolah kamu.\n3. Masuk ke menu **Verval Ijazah**.\n4. Pastiin statusnya udah *Selesai* dan nyambung ke data PDDikti kampusmu. Kalo ada kendala, langsung colek operator sekolah ya!";
                    success = true;
                } else if (lower.includes('pppk') || lower.includes('cpns') || lower.includes('jadwal')) {
                    aiResponseText = "Biasanya nih, bukaan pendaftaran seleksi CASN (CPNS/PPPK) Guru itu ada di pertengahan tahun (sekitar **Juli-Oktober**). Tapi buat info pastinya, kamu wajib pantengin terus IG resminya **@bkngoidofficial** atau web **sscasn.bkn.go.id**. Jangan lupa siapin hafalan buat SKD sama latihan soal pedagogik dari sekarang!";
                    success = true;
                } else if (lower.includes('internasional') || lower.includes('swasta') || lower.includes('cambridge')) {
                    aiResponseText = "Wah, ngincer sekolah internasional (SPK) ya? Mantap! Ini bekal yang wajib kamu punya:\n- Skor **TOEFL iBT** (min. 80) atau **IELTS** (min. 6.5).\n- Paham kurikulum luar kaya **Cambridge** atau **IB (International Baccalaureate)**.\n- Skill *Microteaching* yang komunikatif pakai metode *Inquiry-Based Learning* (anak-anak yang aktif, bukan gurunya nyeramah).";
                    success = true;
                } else if (lower.includes('serdik') || lower.includes('ppg') || lower.includes('sertifikat pendidik')) {
                    aiResponseText = "Punya **Sertifikat Pendidik (Serdik)** dari program **PPG Prajabatan** tuh kaya dapet 100 nyawa tambahan! Pas kamu daftar CPNS nanti, otomatis nilai tes SKB kamu langsung **skor maksimal 100**. Udah gitu, Serdik ini syarat mutlak biar kamu dapet Tunjangan Profesi Guru (TPG). So, lulus S1 mending langsung <em>apply</em> PPG ya!";
                    success = true;
                }

                // 2. FETCH GEMINI API: Kalau gak masuk local fallback, baru request ke Google AI
                if (!success) {
                    const apiKey = ""; 
                    const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;

                    const payload = {
                        contents: [{ role: 'user', parts: [{ text: userText }] }],
                        systemInstruction: { parts: [{ text: systemPrompt }] }
                    };

                    const response = await fetch(apiUrl, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });

                    if (response.ok) {
                        const result = await response.json();
                        const candidate = result.candidates?.[0];
                        if (candidate && candidate.content?.parts?.[0]?.text) {
                            aiResponseText = candidate.content.parts[0].text;
                            success = true;
                        }
                    }
                }

                // 3. FAIL-SAFE FALLBACK: Kalau API error/sibuk dan local fallback gagal
                if (!success) {
                    aiResponseText = `Thanks udah nanya tentang **"${userText}"**! ✨\n\nTips paling ampuh buat ngejar karier guru SD impian kamu:\n1. Update terus berkas di Dapodik/Info GTK.\n2. Tingkatin <em>skill</em> pakai bikin *digital portfolio*.\n3. Kalau ada peluang, langsung ambil PPG Prajabatan.\n\n*(Info: Sistem AI lagi lumayan antre nih, tapi panduan di atas udah pasti valid buat siapin masa depanmu!)*`;
                }

                removeLoading(loadingId);
                appendMessage('ai', marked.parse(aiResponseText));

            } catch (error) {
                console.error(error);
                removeLoading(loadingId);
                // Graceful error UI
                appendMessage('ai', `<p class="text-slate-700 font-medium">Wah, kayaknya server AI kita lagi nge-lag dikit nih! Tapi tenang, kamu tetep bisa scroll web PathTeacher di atas buat baca-baca info lengkap tentang syarat, jadwal, dan hacks tembus seleksi. Semangat ya! 🚀</p>`);
            } finally {
                inputEl.disabled = false;
                sendBtn.disabled = false;
                inputEl.focus();
            }
        }

        function appendMessage(role, htmlContent) {
            const chatHistory = document.getElementById('ai-chat-history');
            const msgDiv = document.createElement('div');
            msgDiv.className = 'flex gap-3 md:gap-4 fade-in appear w-full';
            
            if (role === 'user') {
                msgDiv.classList.add('flex-row-reverse');
                msgDiv.innerHTML = `
                    <div class="w-10 h-10 rounded-full bg-white border border-slate-200 flex items-center justify-center flex-shrink-0 mt-1 shadow-sm">
                        <i class="fa-solid fa-user text-slate-400 text-sm"></i>
                    </div>
                    <div class="bg-gradient-to-r from-pink-500 to-pink-600 text-white p-4 rounded-[1.5rem] rounded-tr-none shadow-sm text-sm md:text-base max-w-[85%] md:max-w-[75%] break-words font-medium">
                        ${htmlContent.replace(/</g, "&lt;").replace(/>/g, "&gt;")}
                    </div>
                `;
            } else {
                msgDiv.innerHTML = `
                    <div class="w-10 h-10 rounded-full bg-gradient-to-br from-pink-400 to-blue-400 flex items-center justify-center flex-shrink-0 text-white shadow-sm mt-1 border border-white">
                        <i class="fa-solid fa-robot text-sm"></i>
                    </div>
                    <div class="bg-white p-5 rounded-[1.5rem] rounded-tl-none border border-slate-100 shadow-sm text-slate-700 text-sm md:text-base max-w-[90%] md:max-w-[80%] leading-relaxed prose prose-sm md:prose-base prose-pink max-w-none font-medium">
                        ${htmlContent}
                    </div>
                `;
            }
            chatHistory.appendChild(msgDiv);
            
            setTimeout(() => {
                chatHistory.scrollTo({ top: chatHistory.scrollHeight, behavior: 'smooth' });
            }, 50);
        }

        function appendLoading() {
            const chatHistory = document.getElementById('ai-chat-history');
            const id = 'loading-' + Date.now();
            const msgDiv = document.createElement('div');
            msgDiv.id = id;
            msgDiv.className = 'flex gap-3 md:gap-4 w-full';
            msgDiv.innerHTML = `
                <div class="w-10 h-10 rounded-full bg-slate-200 flex items-center justify-center flex-shrink-0 text-slate-400 shadow-sm mt-1 border border-white">
                    <i class="fa-solid fa-robot text-sm"></i>
                </div>
                <div class="bg-white p-4 rounded-[1.5rem] rounded-tl-none border border-slate-100 shadow-sm flex items-center gap-2 max-w-max">
                    <div class="flex items-center gap-1.5 px-2 py-1">
                        <span class="w-2.5 h-2.5 bg-pink-400 rounded-full animate-bounce"></span>
                        <span class="w-2.5 h-2.5 bg-pink-400 rounded-full animate-bounce" style="animation-delay: 0.15s"></span>
                        <span class="w-2.5 h-2.5 bg-blue-400 rounded-full animate-bounce" style="animation-delay: 0.3s"></span>
                    </div>
                    <span class="text-xs text-slate-400 font-bold ml-1 font-display tracking-wide">Ngetik jawaban...</span>
                </div>
            `;
            chatHistory.appendChild(msgDiv);
            chatHistory.scrollTo({ top: chatHistory.scrollHeight, behavior: 'smooth' });
            return id;
        }

        function removeLoading(id) {
            const el = document.getElementById(id);
            if (el) el.remove();
        }
    </script>
</body>
</html>
