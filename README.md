<!DOCTYPE html>
<html lang="id" class="dark scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Behind The Show | Event Industry Hub Indonesia</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            black: '#080808',
                            dark: '#121214',
                            card: '#18181b',
                            border: '#27272a',
                            lightBg: '#f4f4f5',
                            lightCard: '#ffffff',
                            lightBorder: '#e4e4e7',
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['JetBrains Mono', 'monospace'],
                    }
                }
            }
        }
    </script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <style>
        body {
            font-family: 'Inter', sans-serif;
            transition: background-color 0.3s ease, color 0.3s ease;
        }
        
        .mono-grid-bg {
            background-image: radial-gradient(rgba(255, 255, 255, 0.07) 1px, transparent 0);
            background-size: 24px 24px;
        }
        .light .mono-grid-bg {
            background-image: radial-gradient(rgba(0, 0, 0, 0.06) 1px, transparent 0);
            background-size: 24px 24px;
        }

        .industrial-border {
            border: 1px solid rgba(255, 255, 255, 0.12);
        }
        .light .industrial-border {
            border: 1px solid rgba(0, 0, 0, 0.1);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #09090b;
        }
        .light ::-webkit-scrollbar-track {
            background: #f4f4f5;
        }
        ::-webkit-scrollbar-thumb {
            background: #3f3f46;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #71717a;
        }

        .tab-active {
            border-bottom: 2px solid currentColor;
            font-weight: 700;
        }
    </style>
</head>
<body class="bg-brand-black text-zinc-100 dark:bg-brand-black dark:text-zinc-100 transition-colors duration-200">

    <!-- TOP ANNOUNCEMENT BANNER -->
    <div id="top-announcement" class="bg-zinc-900 border-b border-zinc-800 text-zinc-300 text-xs py-2 px-4 text-center flex items-center justify-between dark:bg-zinc-900 dark:text-zinc-300 light:bg-zinc-200 light:text-zinc-800">
        <div class="flex items-center gap-2 mx-auto">
            <span class="inline-block w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
            <span class="font-mono uppercase tracking-wider text-[11px]">BehindTheShow.id v2.0 Live — Platform Infrastruktur & Matchmaking Event No. 1 Indonesia</span>
        </div>
        <button onclick="document.getElementById('top-announcement').style.display='none'" class="hover:text-white transition"><i data-lucide="x" class="w-3.5 h-3.5"></i></button>
    </div>

    <!-- NAVBAR -->
    <header class="sticky top-0 z-40 backdrop-blur-md bg-zinc-950/90 dark:bg-zinc-950/90 light:bg-white/90 border-b border-zinc-800/80 dark:border-zinc-800 light:border-zinc-200 transition-colors">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            
            <!-- LOGO BRAND (Recreated SVG based on prompt design specs) -->
            <a href="#" class="flex items-center gap-4 group">
                <div class="flex items-center gap-3">
                    <!-- SVG LOGO FULL -->
                    <svg class="h-10 w-auto" viewBox="0 0 160 65" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <!-- Bars -->
                        <rect x="0" y="0" width="8" height="60" fill="currentColor" class="text-zinc-100 dark:text-white light:text-zinc-900" />
                        <rect x="13" y="0" width="8" height="46" fill="currentColor" class="text-zinc-400 dark:text-zinc-300 light:text-zinc-700" />
                        <rect x="26" y="0" width="8" height="32" fill="currentColor" class="text-zinc-500 dark:text-zinc-400 light:text-zinc-500" />
                        <rect x="39" y="0" width="8" height="18" fill="currentColor" class="text-zinc-600 dark:text-zinc-500 light:text-zinc-400" />
                        <!-- Text stacked -->
                        <text x="56" y="16" fill="currentColor" class="text-zinc-100 dark:text-white light:text-zinc-900" font-family="Inter, sans-serif" font-weight="800" font-size="16" letter-spacing="1">BEHIND</text>
                        <text x="56" y="35" fill="currentColor" class="text-zinc-100 dark:text-white light:text-zinc-900" font-family="Inter, sans-serif" font-weight="800" font-size="16" letter-spacing="1">THE</text>
                        <text x="56" y="54" fill="currentColor" class="text-zinc-100 dark:text-white light:text-zinc-900" font-family="Inter, sans-serif" font-weight="800" font-size="16" letter-spacing="1">SHOW</text>
                    </svg>
                </div>
            </a>

            <!-- DESKTOP NAV MENU -->
            <nav class="hidden lg:flex items-center space-x-1 text-xs font-semibold uppercase tracking-wider text-zinc-300 dark:text-zinc-300 light:text-zinc-700">
                <a href="#autofind" class="px-3 py-2 hover:text-white dark:hover:text-white light:hover:text-black transition flex items-center gap-1.5">
                    <i data-lucide="calculator" class="w-3.5 h-3.5"></i> Smart Autofind
                </a>
                <a href="#directory" class="px-3 py-2 hover:text-white dark:hover:text-white light:hover:text-black transition flex items-center gap-1.5">
                    <i data-lucide="grid" class="w-3.5 h-3.5"></i> Directory Vendor
                </a>
                <a href="#tenders" class="px-3 py-2 hover:text-white dark:hover:text-white light:hover:text-black transition flex items-center gap-1.5">
                    <i data-lucide="file-text" class="w-3.5 h-3.5"></i> Tender Event (RFP)
                </a>
                <a href="#sponsors" class="px-3 py-2 hover:text-white dark:hover:text-white light:hover:text-black transition flex items-center gap-1.5">
                    <i data-lucide="award" class="w-3.5 h-3.5"></i> Sponsor Hub
                </a>
                <a href="#crew" class="px-3 py-2 hover:text-white dark:hover:text-white light:hover:text-black transition flex items-center gap-1.5">
                    <i data-lucide="users" class="w-3.5 h-3.5"></i> Crew & Talent
                </a>
            </nav>

            <!-- CONTROLS & CTA -->
            <div class="flex items-center gap-3">
                <!-- Theme Toggle Button -->
                <button id="theme-toggle" title="Toggle Light/Dark Theme" class="p-2.5 rounded-none border border-zinc-700 dark:border-zinc-800 light:border-zinc-300 bg-zinc-900 dark:bg-zinc-900 light:bg-zinc-100 text-zinc-200 dark:text-zinc-200 light:text-zinc-800 hover:bg-zinc-800 dark:hover:bg-zinc-800 light:hover:bg-zinc-200 transition flex items-center gap-2 text-xs font-mono">
                    <i data-lucide="sun" class="w-4 h-4 hidden dark:block"></i>
                    <i data-lucide="moon" class="w-4 h-4 block dark:hidden"></i>
                    <span class="hidden sm:inline font-bold uppercase text-[10px] tracking-widest">Theme</span>
                </button>

                <!-- Ad Promotion Button -->
                <button onclick="openAdModal()" class="hidden md:flex items-center gap-2 border border-zinc-700 dark:border-zinc-700 light:border-zinc-400 px-3 py-2 text-xs font-semibold uppercase tracking-wider hover:bg-zinc-800 dark:hover:bg-zinc-800 light:hover:bg-zinc-200 transition">
                    <i data-lucide="megaphone" class="w-3.5 h-3.5"></i> Pasang Iklan
                </button>

                <!-- Main CTA -->
                <a href="#autofind" class="bg-zinc-100 text-zinc-950 dark:bg-white dark:text-black light:bg-black light:text-white px-4 py-2.5 text-xs font-extrabold uppercase tracking-widest hover:bg-zinc-300 dark:hover:bg-zinc-200 light:hover:bg-zinc-800 transition flex items-center gap-2">
                    <span>Hitung Estimasi</span>
                    <i data-lucide="arrow-right" class="w-4 h-4"></i>
                </a>

                <!-- Mobile Menu Button -->
                <button onclick="toggleMobileMenu()" class="lg:hidden p-2 text-zinc-400 hover:text-white">
                    <i data-lucide="menu" class="w-6 h-6"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Nav Menu Drawer -->
        <div id="mobile-menu" class="hidden lg:hidden border-b border-zinc-800 bg-zinc-950 px-4 py-4 space-y-3 font-semibold uppercase text-xs">
            <a href="#autofind" onclick="toggleMobileMenu()" class="block py-2 text-zinc-300 hover:text-white">Smart Autofind Engine</a>
            <a href="#directory" onclick="toggleMobileMenu()" class="block py-2 text-zinc-300 hover:text-white">Directory Vendor Produksi</a>
            <a href="#tenders" onclick="toggleMobileMenu()" class="block py-2 text-zinc-300 hover:text-white">Tender Event Open RFP</a>
            <a href="#sponsors" onclick="toggleMobileMenu()" class="block py-2 text-zinc-300 hover:text-white">Sponsorship Matchmaking</a>
            <a href="#crew" onclick="toggleMobileMenu()" class="block py-2 text-zinc-300 hover:text-white">Crew & Technical Talent</a>
            <button onclick="openAdModal(); toggleMobileMenu();" class="w-full text-left py-2 text-zinc-300 hover:text-white border-t border-zinc-800 pt-3">
                <i data-lucide="megaphone" class="w-3.5 h-3.5 inline mr-2"></i> Pasang Iklan / Priority Listing
            </button>
        </div>
    </header>

    <!-- HERO SECTION -->
    <section class="relative pt-16 pb-20 border-b border-zinc-800 dark:border-zinc-800 light:border-zinc-200 mono-grid-bg overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
                
                <div class="lg:col-span-7 space-y-6">
                    <div class="inline-flex items-center gap-2 border border-zinc-700 bg-zinc-900/80 px-3 py-1.5 text-xs font-mono text-zinc-300">
                        <span class="w-2 h-2 rounded-full bg-white dark:bg-white light:bg-black"></span>
                        <span class="uppercase tracking-wider">The All-In-One Event Ecosystem</span>
                    </div>

                    <h1 class="text-4xl sm:text-5xl md:text-6xl font-black uppercase tracking-tight leading-none text-zinc-100 dark:text-white light:text-zinc-900">
                        Behind The Show <br>
                        <span class="text-zinc-500 dark:text-zinc-500 light:text-zinc-400 font-extrabold">Infrastructure Engine</span>
                    </h1>

                    <p class="text-base sm:text-lg text-zinc-400 dark:text-zinc-400 light:text-zinc-600 max-w-2xl leading-relaxed">
                        Hub ekosistem industri pertunjukan terpadu Indonesia. Temukan vendor sound system, lighting, LED wall, panggung rigging terverifikasi, ajukan Tender RFP, serta kalkulasi RAB otomatis dalam hitungan detik.
                    </p>

                    <div class="pt-2 flex flex-wrap items-center gap-4">
                        <a href="#autofind" class="bg-white text-black dark:bg-white dark:text-black light:bg-black light:text-white px-6 py-3.5 text-xs font-black uppercase tracking-widest hover:bg-zinc-200 transition flex items-center gap-2 shadow-lg">
                            <i data-lucide="cpu" class="w-4 h-4"></i>
                            <span>Buka Smart Autofind</span>
                        </a>
                        <a href="#tenders" class="border border-zinc-700 dark:border-zinc-700 light:border-zinc-300 text-zinc-200 dark:text-zinc-200 light:text-zinc-800 px-6 py-3.5 text-xs font-bold uppercase tracking-wider hover:bg-zinc-800/60 dark:hover:bg-zinc-800 light:hover:bg-zinc-200 transition flex items-center gap-2">
                            <i data-lucide="search" class="w-4 h-4"></i>
                            <span>Cari Tender Event</span>
                        </a>
                    </div>

                    <!-- Verified Metrics Bar -->
                    <div class="pt-8 border-t border-zinc-800/80 grid grid-cols-2 sm:grid-cols-4 gap-4 font-mono">
                        <div>
                            <div class="text-2xl font-black text-white dark:text-white light:text-zinc-900">1,480+</div>
                            <div class="text-[11px] text-zinc-500 uppercase tracking-wider">Vendor Terverifikasi</div>
                        </div>
                        <div>
                            <div class="text-2xl font-black text-white dark:text-white light:text-zinc-900">380+</div>
                            <div class="text-[11px] text-zinc-500 uppercase tracking-wider">Project Active RFP</div>
                        </div>
                        <div>
                            <div class="text-2xl font-black text-white dark:text-white light:text-zinc-900">Rp 14.2B</div>
                            <div class="text-[11px] text-zinc-500 uppercase tracking-wider">Nilai Transaksi Kontrak</div>
                        </div>
                        <div>
                            <div class="text-2xl font-black text-white dark:text-white light:text-zinc-900">99.4%</div>
                            <div class="text-[11px] text-zinc-500 uppercase tracking-wider">SLA Match Accuracy</div>
                        </div>
                    </div>
                </div>

                <!-- HERO ICON DISPLAY & QUICK ACCESS CARDS -->
                <div class="lg:col-span-5 relative">
                    <div class="bg-zinc-900/90 dark:bg-zinc-900/90 light:bg-white border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-6 relative">
                        <!-- Icon Variant Display (From spec sheet) -->
                        <div class="flex items-center justify-between border-b border-zinc-800 dark:border-zinc-800 light:border-zinc-200 pb-4 mb-6">
                            <span class="text-xs font-mono uppercase tracking-widest text-zinc-400">Brand Spec Variant</span>
                            <span class="text-[10px] font-mono bg-zinc-800 px-2 py-0.5 text-zinc-300 uppercase">Ver. BTS-01</span>
                        </div>

                        <div class="flex items-center justify-center py-6 bg-black/40 dark:bg-black/60 light:bg-zinc-100 border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 mb-6">
                            <!-- BTS SVG ICON VARIANT (Exact match with prompt uploaded icon variant) -->
                            <svg class="h-28 w-auto" viewBox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <rect x="20" y="10" width="12" height="75" fill="currentColor" class="text-zinc-100 dark:text-white light:text-zinc-900" />
                                <rect x="40" y="10" width="12" height="60" fill="currentColor" class="text-zinc-400 dark:text-zinc-300 light:text-zinc-700" />
                                <rect x="60" y="10" width="12" height="45" fill="currentColor" class="text-zinc-500 dark:text-zinc-400 light:text-zinc-500" />
                                <rect x="80" y="10" width="12" height="30" fill="currentColor" class="text-zinc-600 dark:text-zinc-500 light:text-zinc-400" />
                                <text x="22" y="100" fill="currentColor" class="text-zinc-100 dark:text-white light:text-zinc-900" font-family="Inter, sans-serif" font-weight="900" font-size="20">B</text>
                                <text x="62" y="70" fill="currentColor" class="text-zinc-100 dark:text-white light:text-zinc-900" font-family="Inter, sans-serif" font-weight="900" font-size="20">T</text>
                                <text x="82" y="55" fill="currentColor" class="text-zinc-100 dark:text-white light:text-zinc-900" font-family="Inter, sans-serif" font-weight="900" font-size="20">S</text>
                            </svg>
                        </div>

                        <div class="space-y-3">
                            <div class="p-3 bg-zinc-950 dark:bg-zinc-950 light:bg-zinc-50 border border-zinc-800 dark:border-zinc-800 light:border-zinc-200 flex items-center justify-between">
                                <div>
                                    <div class="text-xs font-bold uppercase text-white dark:text-white light:text-black">Rigging & Lighting System</div>
                                    <div class="text-[11px] text-zinc-400">L-Acoustics K2, GrandMA3, P2.5 Outdoor</div>
                                </div>
                                <span class="text-xs font-mono text-emerald-400">VERIFIED</span>
                            </div>
                            <div class="p-3 bg-zinc-950 dark:bg-zinc-950 light:bg-zinc-50 border border-zinc-800 dark:border-zinc-800 light:border-zinc-200 flex items-center justify-between">
                                <div>
                                    <div class="text-xs font-bold uppercase text-white dark:text-white light:text-black">Production Crew Standby</div>
                                    <div class="text-[11px] text-zinc-400">Sound Engineers, Stagehand, LO Crew</div>
                                </div>
                                <span class="text-xs font-mono text-zinc-400">READY</span>
                            </div>
                        </div>

                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- SMART AUTOFIND ENGINE SECTION -->
    <section id="autofind" class="py-20 border-b border-zinc-800 dark:border-zinc-800 light:border-zinc-200 bg-zinc-950 dark:bg-zinc-950 light:bg-zinc-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <div class="text-center max-w-3xl mx-auto mb-12">
                <span class="text-xs font-mono uppercase tracking-widest text-zinc-400 block mb-2">// AUTOMATED MATCHMAKING & ESTIMATOR ENGINE</span>
                <h2 class="text-3xl sm:text-4xl font-black uppercase tracking-tight text-white dark:text-white light:text-black">
                    Smart Autofind & Kalkulator RAB Event
                </h2>
                <p class="text-zinc-400 text-sm mt-2">
                    Masukkan spesifikasi dan lokasi acara Anda. Sistem AI BehindTheShow akan menghitung estimasi alokasi anggaran serta menampilkan rekomendasi vendor produksi terbaik.
                </p>
            </div>

            <div class="bg-zinc-900 dark:bg-zinc-900 light:bg-white border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-6 sm:p-8 shadow-2xl">
                <form id="autofind-form" onsubmit="calculateRAB(event)">
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
                        
                        <!-- Event Scale -->
                        <div>
                            <label class="block text-xs font-mono uppercase tracking-wider text-zinc-300 dark:text-zinc-300 light:text-zinc-700 mb-2">
                                1. Skala / Kapasitas Event
                            </label>
                            <select id="event-scale" class="w-full bg-zinc-950 dark:bg-zinc-950 light:bg-zinc-100 border border-zinc-700 dark:border-zinc-700 light:border-zinc-300 text-sm text-white dark:text-white light:text-black p-3 focus:outline-none focus:border-white">
                                <option value="intimate">Intimate / Mini Event (100 - 500 Pax)</option>
                                <option value="medium" selected>Mid-Scale Concert / Expo (1.000 - 3.000 Pax)</option>
                                <option value="large">Festival Outdoor (5.000 - 10.000 Pax)</option>
                                <option value="mega">Stadium / Mega Event (20.000+ Pax)</option>
                            </select>
                        </div>

                        <!-- Location -->
                        <div>
                            <label class="block text-xs font-mono uppercase tracking-wider text-zinc-300 dark:text-zinc-300 light:text-zinc-700 mb-2">
                                2. Wilayah / Kota Pelaksanaan
                            </label>
                            <select id="event-location" class="w-full bg-zinc-950 dark:bg-zinc-950 light:bg-zinc-100 border border-zinc-700 dark:border-zinc-700 light:border-zinc-300 text-sm text-white dark:text-white light:text-black p-3 focus:outline-none focus:border-white">
                                <option value="jakarta">DKI Jakarta & Bodetabek</option>
                                <option value="bandung">Bandung & Jawa Barat</option>
                                <option value="yogyakarta">Yogyakarta & Jateng</option>
                                <option value="surabaya">Surabaya & Jatim</option>
                                <option value="bali">Bali & Nusa Tenggara</option>
                                <option value="sumatra">Medan & Sumatra</option>
                            </select>
                        </div>

                        <!-- Budget Tier -->
                        <div>
                            <label class="block text-xs font-mono uppercase tracking-wider text-zinc-300 dark:text-zinc-300 light:text-zinc-700 mb-2">
                                3. Pagu Anggaran (Budget Target)
                            </label>
                            <select id="event-budget" class="w-full bg-zinc-950 dark:bg-zinc-950 light:bg-zinc-100 border border-zinc-700 dark:border-zinc-700 light:border-zinc-300 text-sm text-white dark:text-white light:text-black p-3 focus:outline-none focus:border-white">
                                <option value="budget_low">Rp 25.000.000 - Rp 75.000.000</option>
                                <option value="budget_mid" selected>Rp 75.000.000 - Rp 250.000.000</option>
                                <option value="budget_high">Rp 250.000.000 - Rp 600.000.000</option>
                                <option value="budget_pro">Rp 600.000.000 +</option>
                            </select>
                        </div>

                    </div>

                    <!-- Kebutuhan Equipment Checkboxes -->
                    <div class="mb-8">
                        <label class="block text-xs font-mono uppercase tracking-wider text-zinc-300 dark:text-zinc-300 light:text-zinc-700 mb-3">
                            4. Pilih Item Infrastruktur & Vendor yang Dibutuhkan:
                        </label>
                        <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-6 gap-3">
                            <label class="border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-3 flex items-center gap-2 cursor-pointer bg-zinc-950/50 hover:border-zinc-500 transition">
                                <input type="checkbox" id="need-sound" checked class="accent-white">
                                <span class="text-xs font-semibold uppercase">Sound System</span>
                            </label>
                            <label class="border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-3 flex items-center gap-2 cursor-pointer bg-zinc-950/50 hover:border-zinc-500 transition">
                                <input type="checkbox" id="need-lighting" checked class="accent-white">
                                <span class="text-xs font-semibold uppercase">Lighting Rig</span>
                            </label>
                            <label class="border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-3 flex items-center gap-2 cursor-pointer bg-zinc-950/50 hover:border-zinc-500 transition">
                                <input type="checkbox" id="need-led" checked class="accent-white">
                                <span class="text-xs font-semibold uppercase">LED Screen P2.5</span>
                            </label>
                            <label class="border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-3 flex items-center gap-2 cursor-pointer bg-zinc-950/50 hover:border-zinc-500 transition">
                                <input type="checkbox" id="need-stage" checked class="accent-white">
                                <span class="text-xs font-semibold uppercase">Stage & Rigging</span>
                            </label>
                            <label class="border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-3 flex items-center gap-2 cursor-pointer bg-zinc-950/50 hover:border-zinc-500 transition">
                                <input type="checkbox" id="need-crew" checked class="accent-white">
                                <span class="text-xs font-semibold uppercase">Technical Crew</span>
                            </label>
                            <label class="border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-3 flex items-center gap-2 cursor-pointer bg-zinc-950/50 hover:border-zinc-500 transition">
                                <input type="checkbox" id="need-security" class="accent-white">
                                <span class="text-xs font-semibold uppercase">Security & Crowd</span>
                            </label>
                        </div>
                    </div>

                    <div class="flex justify-end">
                        <button type="submit" class="w-full sm:w-auto bg-white text-black dark:bg-white dark:text-black light:bg-black light:text-white px-8 py-4 text-xs font-black uppercase tracking-widest hover:bg-zinc-200 transition flex items-center justify-center gap-2">
                            <i data-lucide="calculator" class="w-4 h-4"></i>
                            <span>Proses Autofind & Kalkulasi RAB</span>
                        </button>
                    </div>
                </form>

                <!-- AUTOFIND RESULTS SECTION (Hidden initially, toggled via JS) -->
                <div id="autofind-results" class="hidden mt-10 pt-8 border-t border-zinc-800">
                    <div class="flex items-center justify-between mb-6">
                        <div>
                            <span class="text-xs font-mono text-emerald-400 uppercase">// ESTIMATION OUTPUT GENERATED</span>
                            <h3 class="text-xl font-bold uppercase text-white dark:text-white light:text-black">Rincian Estimasi RAB & Matched Vendor</h3>
                        </div>
                        <span id="result-total-rab" class="text-2xl font-mono font-black text-white dark:text-white light:text-black bg-zinc-800 px-4 py-2 border border-zinc-700">
                            Rp 135.000.000
                        </span>
                    </div>

                    <!-- Breakdown & Matched Vendors Grid -->
                    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                        <!-- RAB Breakdown -->
                        <div class="lg:col-span-5 bg-zinc-950 p-5 border border-zinc-800">
                            <h4 class="text-xs font-mono uppercase text-zinc-400 mb-4 border-b border-zinc-800 pb-2">ESTIMATED COST ALLOCATION (RAB)</h4>
                            <div id="rab-breakdown-list" class="space-y-3 text-xs font-mono">
                                <!-- Dynamic JS Output -->
                            </div>
                        </div>

                        <!-- Top Matching Vendors -->
                        <div class="lg:col-span-7 space-y-3">
                            <h4 class="text-xs font-mono uppercase text-zinc-400 mb-2">3 RECOMMENDATION VENDOR TERVERIFIKASI BTS</h4>
                            <div id="matched-vendor-list" class="space-y-3">
                                <!-- Dynamic JS Output -->
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- DIRECTORY VENDOR SECTION -->
    <section id="directory" class="py-20 border-b border-zinc-800 dark:border-zinc-800 light:border-zinc-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-10 gap-4">
                <div>
                    <span class="text-xs font-mono uppercase tracking-widest text-zinc-400 block mb-2">// VERIFIED INFRASTRUCTURE PROVIDERS</span>
                    <h2 class="text-3xl font-black uppercase text-white dark:text-white light:text-black">
                        Directory Vendor Produksi
                    </h2>
                </div>
                <div class="flex items-center gap-2">
                    <input type="text" id="vendor-search" oninput="filterVendors()" placeholder="Cari nama vendor atau spek alat..." class="bg-zinc-900 border border-zinc-700 text-xs text-white p-2.5 w-64 focus:outline-none focus:border-white">
                </div>
            </div>

            <!-- Category Filter Pills -->
            <div class="flex flex-wrap items-center gap-2 mb-8 font-mono text-xs">
                <button onclick="setVendorCategory('all')" class="vendor-cat-btn tab-active px-4 py-2 border border-zinc-700 uppercase">Semua Category</button>
                <button onclick="setVendorCategory('sound')" class="vendor-cat-btn px-4 py-2 border border-zinc-800 text-zinc-400 hover:text-white uppercase">Sound System</button>
                <button onclick="setVendorCategory('lighting')" class="vendor-cat-btn px-4 py-2 border border-zinc-800 text-zinc-400 hover:text-white uppercase">Lighting Rig</button>
                <button onclick="setVendorCategory('led')" class="vendor-cat-btn px-4 py-2 border border-zinc-800 text-zinc-400 hover:text-white uppercase">LED Screen & Video</button>
                <button onclick="setVendorCategory('stage')" class="vendor-cat-btn px-4 py-2 border border-zinc-800 text-zinc-400 hover:text-white uppercase">Stage & Rigging</button>
                <button onclick="setVendorCategory('eo')" class="vendor-cat-btn px-4 py-2 border border-zinc-800 text-zinc-400 hover:text-white uppercase">Event Management</button>
            </div>

            <!-- VENDORS GRID -->
            <div id="vendor-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Vendor Card 1 -->
                <div class="vendor-card bg-zinc-900 dark:bg-zinc-900 light:bg-white border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-5 flex flex-col justify-between hover:border-zinc-600 transition" data-category="sound">
                    <div>
                        <div class="flex items-start justify-between mb-4">
                            <div>
                                <span class="text-[10px] font-mono uppercase bg-zinc-800 text-zinc-300 px-2 py-0.5 border border-zinc-700">Sound System Pro</span>
                                <h3 class="text-lg font-bold text-white dark:text-white light:text-black uppercase mt-2">Thunder Audio Pro</h3>
                                <p class="text-xs text-zinc-400 flex items-center gap-1 mt-1"><i data-lucide="map-pin" class="w-3 h-3"></i> Jakarta Selatan & BSD</p>
                            </div>
                            <span class="text-xs font-mono bg-emerald-950 text-emerald-400 border border-emerald-800 px-2 py-1 flex items-center gap-1">
                                <i data-lucide="check-circle" class="w-3 h-3"></i> BTS VERIFIED
                            </span>
                        </div>
                        <p class="text-xs text-zinc-300 mb-4 line-clamp-2">
                            Spesialis Line Array L-Acoustics K2 & DiGiCo Quantum SD7. Berpengalaman di festival musik outdoor >20,000 penonton.
                        </p>
                        <div class="space-y-1.5 mb-6 text-[11px] font-mono text-zinc-400 border-t border-b border-zinc-800 py-3">
                            <div class="flex justify-between"><span>Kapasitas Max:</span> <span class="text-white">50.000 Watt RMS</span></div>
                            <div class="flex justify-between"><span>Utama Mixer:</span> <span class="text-white">DiGiCo SD12 / Midas PRO6</span></div>
                            <div class="flex justify-between"><span>Rating Client:</span> <span class="text-amber-400">★ 4.9 (48 Review)</span></div>
                        </div>
                    </div>
                    <div class="flex items-center justify-between gap-2 pt-2">
                        <div>
                            <span class="text-[10px] font-mono text-zinc-500 uppercase block">Start From</span>
                            <span class="text-sm font-mono font-bold text-white">Rp 25.000.000 / Day</span>
                        </div>
                        <button onclick="openVendorDetail('Thunder Audio Pro', 'Sound System', 'Jakarta', 'L-Acoustics K2, DiGiCo SD12', 'Rp 25.000.000')" class="bg-zinc-800 hover:bg-zinc-700 text-white px-3 py-2 text-xs font-mono uppercase tracking-wider transition">
                            Minta Quotation
                        </button>
                    </div>
                </div>

                <!-- Vendor Card 2 -->
                <div class="vendor-card bg-zinc-900 dark:bg-zinc-900 light:bg-white border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-5 flex flex-col justify-between hover:border-zinc-600 transition" data-category="lighting">
                    <div>
                        <div class="flex items-start justify-between mb-4">
                            <div>
                                <span class="text-[10px] font-mono uppercase bg-zinc-800 text-zinc-300 px-2 py-0.5 border border-zinc-700">Lighting System</span>
                                <h3 class="text-lg font-bold text-white dark:text-white light:text-black uppercase mt-2">Lumina Stage Craft</h3>
                                <p class="text-xs text-zinc-400 flex items-center gap-1 mt-1"><i data-lucide="map-pin" class="w-3 h-3"></i> Bandung & Jabodetabek</p>
                            </div>
                            <span class="text-xs font-mono bg-emerald-950 text-emerald-400 border border-emerald-800 px-2 py-1 flex items-center gap-1">
                                <i data-lucide="check-circle" class="w-3 h-3"></i> BTS VERIFIED
                            </span>
                        </div>
                        <p class="text-xs text-zinc-300 mb-4 line-clamp-2">
                            Penyedia Moving Light Beam 380W, Wash LED 19x40, Laser Kinetic FX, & GrandMA3 Light console resmi.
                        </p>
                        <div class="space-y-1.5 mb-6 text-[11px] font-mono text-zinc-400 border-t border-b border-zinc-800 py-3">
                            <div class="flex justify-between"><span>Lighting Fixtures:</span> <span class="text-white">120+ Units Standby</span></div>
                            <div class="flex justify-between"><span>Control Desk:</span> <span class="text-white">GrandMA3 Full Size</span></div>
                            <div class="flex justify-between"><span>Rating Client:</span> <span class="text-amber-400">★ 4.85 (32 Review)</span></div>
                        </div>
                    </div>
                    <div class="flex items-center justify-between gap-2 pt-2">
                        <div>
                            <span class="text-[10px] font-mono text-zinc-500 uppercase block">Start From</span>
                            <span class="text-sm font-mono font-bold text-white">Rp 18.000.000 / Day</span>
                        </div>
                        <button onclick="openVendorDetail('Lumina Stage Craft', 'Lighting System', 'Bandung', 'GrandMA3, Beam 380W, Kinetic Laser', 'Rp 18.000.000')" class="bg-zinc-800 hover:bg-zinc-700 text-white px-3 py-2 text-xs font-mono uppercase tracking-wider transition">
                            Minta Quotation
                        </button>
                    </div>
                </div>

                <!-- Vendor Card 3 -->
                <div class="vendor-card bg-zinc-900 dark:bg-zinc-900 light:bg-white border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-5 flex flex-col justify-between hover:border-zinc-600 transition" data-category="led">
                    <div>
                        <div class="flex items-start justify-between mb-4">
                            <div>
                                <span class="text-[10px] font-mono uppercase bg-zinc-800 text-zinc-300 px-2 py-0.5 border border-zinc-700">LED & Visual Visualiser</span>
                                <h3 class="text-lg font-bold text-white dark:text-white light:text-black uppercase mt-2">PixelMatrix LED Visual</h3>
                                <p class="text-xs text-zinc-400 flex items-center gap-1 mt-1"><i data-lucide="map-pin" class="w-3 h-3"></i> Surabaya & Bali</p>
                            </div>
                            <span class="text-xs font-mono bg-emerald-950 text-emerald-400 border border-emerald-800 px-2 py-1 flex items-center gap-1">
                                <i data-lucide="check-circle" class="w-3 h-3"></i> BTS VERIFIED
                            </span>
                        </div>
                        <p class="text-xs text-zinc-300 mb-4 line-clamp-2">
                            LED Screen High Refresh Rate P2.5 Indoor & P3.9 Outdoor Curve Wall. Lengkap dengan Video Processor NovaStar VX1000.
                        </p>
                        <div class="space-y-1.5 mb-6 text-[11px] font-mono text-zinc-400 border-t border-b border-zinc-800 py-3">
                            <div class="flex justify-between"><span>Screen Pixel Pitch:</span> <span class="text-white">P2.5 & P3.9 Outdoor</span></div>
                            <div class="flex justify-between"><span>Max Modular Size:</span> <span class="text-white">120 M2 Stock Available</span></div>
                            <div class="flex justify-between"><span>Rating Client:</span> <span class="text-amber-400">★ 4.92 (64 Review)</span></div>
                        </div>
                    </div>
                    <div class="flex items-center justify-between gap-2 pt-2">
                        <div>
                            <span class="text-[10px] font-mono text-zinc-500 uppercase block">Start From</span>
                            <span class="text-sm font-mono font-bold text-white">Rp 220.000 / M2</span>
                        </div>
                        <button onclick="openVendorDetail('PixelMatrix LED Visual', 'LED Screen', 'Surabaya', 'LED P2.5, NovaStar VX1000', 'Rp 220.000/M2')" class="bg-zinc-800 hover:bg-zinc-700 text-white px-3 py-2 text-xs font-mono uppercase tracking-wider transition">
                            Minta Quotation
                        </button>
                    </div>
                </div>

                <!-- Vendor Card 4 -->
                <div class="vendor-card bg-zinc-900 dark:bg-zinc-900 light:bg-white border border-zinc-800 dark:border-zinc-800 light:border-zinc-300 p-5 flex flex-col justify-between hover:border-zinc-600 transition" data-category="stage">
                    <div>
                        <div class="flex items-start justify-between mb-4">
                            <div>
                                <span class="text-[10px] font-mono uppercase bg-zinc-800 text-zinc-300 px-2 py-0.5 border border-zinc-700">Stage & Truss</span>
                                <h3 class="text-lg font-bold text-white dark:text-white light:text-black uppercase mt-2">Titan Truss Rigging</h3>
                                <p class="text-xs text-zinc-400 flex items-center gap-1 mt-1"><i data-lucide="map-pin" class="w-3 h-3"></i> Yogyakarta & Semarang</p>
                            </div>
                            <span class="text-xs font-mono bg-zinc-800 text-zinc-400 border border-zinc-700 px-2 py-1">PRO SUPPLIER</span>
                        </div>
                        <p class="text-xs text-zinc-300 mb-4 line-clamp-2">
                            Panggung Rigging Aluminium heavy duty 12x10m, 16x12m roof structure, barricade mojo, dan flooring panggung hidrolik.
                        </p>
                        <div class="space-y-1.5 mb-6 text-[11px] font-mono text-zinc-400 border-t border-b border-zinc-800 py-3">
                            <div class="flex justify-between"><span>Struktur Rigging:</span> <span class="text-white">Aluminium Heavy Truss</span></div>
                            <div class="flex justify-between"><span>Sertifikat Safety:</span> <span class="text-emerald-400">Pass Load Test</span></div>
                            <div class="flex justify-between"><span>Rating Client:</span> <span class="text-amber-400">★ 4.80 (21 Review)</span></div>
                        </div>
                    </div>
                    <div class="flex items-center justify-between gap-2 pt-2">
                        <div>
                            <span class="text-[10px] font-mono text-zinc-500 uppercase block">Start From</span>
                            <span class="text-sm font-mono font-bold text-white">Rp 20.000.000 / Set</span>
                        </div>
                        <button onclick="openVendorDetail('Titan Truss Rigging', 'Stage & Rigging', 'Yogyakarta', 'Aluminium Truss 16x12m, Mojo Barricade', 'Rp 20.000.000')" class="bg-zinc-800 hover:bg-zinc-700 text-white px-3 py-2 text-xs font-mono uppercase tracking-wider transition">
                            Minta Quotation
                        </button>
                    </div>
                </div>

            </div>

        </div>
    </section>

    <!-- TENDER OPEN RFP HUB SECTION -->
    <section id="tenders" class="py-20 border-b border-zinc-800 dark:border-zinc-800 light:border-zinc-200 bg-zinc-950 dark:bg-zinc-950 light:bg-zinc-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-10 gap-4">
                <div>
                    <span class="text-xs font-mono uppercase tracking-widest text-zinc-400 block mb-2">// OPEN BIDDING & PROJECT TENDERS</span>
                    <h2 class="text-3xl font-black uppercase text-white dark:text-white light:text-black">
                        Tender Event Open RFP
                    </h2>
                    <p class="text-xs text-zinc-400 mt-1">Daftar tender infrastruktur acara aktif dari EO dan Promotor nasional. Submit penawaran RAB Anda secara langsung.</p>
                </div>
                <button onclick="openAdModal()" class="bg-zinc-100 text-zinc-900 hover:bg-zinc-300 text-xs font-black uppercase tracking-wider px-4 py-2.5 flex items-center gap-2">
                    <i data-lucide="plus-circle" class="w-4 h-4"></i> Buat Tender Baru
                </button>
            </div>

            <!-- Tenders Grid -->
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                
                <!-- Tender Card 1 -->
                <div class="bg-zinc-900 border border-zinc-800 p-6 flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-3 font-mono text-xs">
                            <span class="bg-amber-950 text-amber-400 border border-amber-800 px-2 py-0.5">TENDER OPEN</span>
                            <span class="text-zinc-400 flex items-center gap-1"><i data-lucide="clock" class="w-3.5 h-3.5"></i> Sisa Waktu: 2 Hari 14 Jam</span>
                        </div>
                        <h3 class="text-xl font-bold uppercase text-white mb-2">Sound & Lighting Tender — Java Soundwave Fest 2026</h3>
                        <p class="text-xs text-zinc-400 mb-4">
                            Dibutuhkan paket Sound System Line Array 40k Watt & Full Lighting Rig untuk Festival Outdoor 2 Stage di Lapangan Puspiptek Serpong.
                        </p>
                        
                        <div class="grid grid-cols-2 gap-3 text-xs font-mono bg-zinc-950 p-3 border border-zinc-800 mb-6">
                            <div>
                                <span class="text-zinc-500 block text-[10px]">PAGU ANGGARAN:</span>
                                <span class="font-bold text-white">Rp 180.000.000 - Rp 220.000.000</span>
                            </div>
                            <div>
                                <span class="text-zinc-500 block text-[10px]">TANGGAL ACARA:</span>
                                <span class="font-bold text-white">18 - 20 November 2026</span>
                            </div>
                            <div>
                                <span class="text-zinc-500 block text-[10px]">LOKASI:</span>
                                <span class="text-white">Tangerang Selatan</span>
                            </div>
                            <div>
                                <span class="text-zinc-500 block text-[10px]">PROMOSI / PROMOTOR:</span>
                                <span class="text-white">Nada Live Entertainment</span>
                            </div>
                        </div>
                    </div>

                    <div class="flex items-center justify-between pt-2 border-t border-zinc-800">
                        <span class="text-xs font-mono text-zinc-400">14 Vendor Sudah Submit Proposal</span>
                        <button onclick="openPitchModal('Java Soundwave Fest 2026 - Sound & Lighting', 'Rp 180 - 220 Juta')" class="bg-white text-black hover:bg-zinc-200 px-4 py-2 text-xs font-extrabold uppercase tracking-wider transition flex items-center gap-2">
                            <span>Submit Proposal / Pitch</span>
                            <i data-lucide="arrow-up-right" class="w-4 h-4"></i>
                        </button>
                    </div>
                </div>

                <!-- Tender Card 2 -->
                <div class="bg-zinc-900 border border-zinc-800 p-6 flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-3 font-mono text-xs">
                            <span class="bg-amber-950 text-amber-400 border border-amber-800 px-2 py-0.5">TENDER OPEN</span>
                            <span class="text-zinc-400 flex items-center gap-1"><i data-lucide="clock" class="w-3.5 h-3.5"></i> Sisa Waktu: 4 Hari</span>
                        </div>
                        <h3 class="text-xl font-bold uppercase text-white mb-2">LED Screen Curved & Stage Rigging — Tech Summit Expo</h3>
                        <p class="text-xs text-zinc-400 mb-4">
                            Pengadaan LED Screen Seamless P2.5 Indoor luas total 85 M2 + Multilevel Hydraulic Stage & Rigging Backdrop Grand Ballroom Ritz Carlton.
                        </p>
                        
                        <div class="grid grid-cols-2 gap-3 text-xs font-mono bg-zinc-950 p-3 border border-zinc-800 mb-6">
                            <div>
                                <span class="text-zinc-500 block text-[10px]">PAGU ANGGARAN:</span>
                                <span class="font-bold text-white">Rp 120.000.000 - Rp 150.000.000</span>
                            </div>
                            <div>
                                <span class="text-zinc-500 block text-[10px]">TANGGAL ACARA:</span>
                                <span class="font-bold text-white">05 - 06 Desember 2026</span>
                            </div>
                            <div>
                                <span class="text-zinc-500 block text-[10px]">LOKASI:</span>
                                <span class="text-white">SCBD, Jakarta</span>
                            </div>
                            <div>
                                <span class="text-zinc-500 block text-[10px]">PROMOSI / PROMOTOR:</span>
                                <span class="text-white">Nusantara Expo Network</span>
                            </div>
                        </div>
                    </div>

                    <div class="flex items-center justify-between pt-2 border-t border-zinc-800">
                        <span class="text-xs font-mono text-zinc-400">8 Vendor Sudah Submit Proposal</span>
                        <button onclick="openPitchModal('Tech Summit Expo - LED Screen & Stage', 'Rp 120 - 150 Juta')" class="bg-white text-black hover:bg-zinc-200 px-4 py-2 text-xs font-extrabold uppercase tracking-wider transition flex items-center gap-2">
                            <span>Submit Proposal / Pitch</span>
                            <i data-lucide="arrow-up-right" class="w-4 h-4"></i>
                        </button>
                    </div>
                </div>

            </div>

        </div>
    </section>

    <!-- SPONSOR MATCHMAKING HUB -->
    <section id="sponsors" class="py-20 border-b border-zinc-800 dark:border-zinc-800 light:border-zinc-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <div class="text-center max-w-3xl mx-auto mb-12">
                <span class="text-xs font-mono uppercase tracking-widest text-zinc-400 block mb-2">// BRAND & SPONSORSHIP BRIDGING HUB</span>
                <h2 class="text-3xl font-black uppercase text-white dark:text-white light:text-black">
                    Sponsor Matching Hub
                </h2>
                <p class="text-xs text-zinc-400 mt-2">Menghubungkan Brand Corporate dan Produk FMCG secara presisi dengan Event Organisers berprospek audiens tinggi.</p>
            </div>

            <!-- Sponsor Cards Grid -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                
                <div class="bg-zinc-900 border border-zinc-800 p-6 flex flex-col justify-between">
                    <div>
                        <div class="flex justify-between items-center mb-3">
                            <span class="text-[10px] font-mono bg-zinc-800 text-zinc-300 px-2 py-0.5">TARGET: GEN Z & GAMERS</span>
                            <span class="text-xs font-mono text-emerald-400">OPEN SPONSOR</span>
                        </div>
                        <h3 class="text-lg font-bold text-white uppercase mb-2">Indie Music & eSports Championship 2026</h3>
                        <p class="text-xs text-zinc-400 mb-4">Estimasi 12,000 pengunjung fisik + 150k Live Stream Viewers. Membuka Title & Main Sponsor Slot.</p>
                        <div class="space-y-2 text-xs font-mono text-zinc-300 mb-6 bg-zinc-950 p-3 border border-zinc-800">
                            <div class="flex justify-between"><span>Paket Main Sponsor:</span> <span>Rp 150.000.000</span></div>
                            <div class="flex justify-between"><span>Paket Co-Sponsor:</span> <span>Rp 50.000.000</span></div>
                            <div class="flex justify-between"><span>Lokasi Event:</span> <span>Sabuga, Bandung</span></div>
                        </div>
                    </div>
                    <button onclick="triggerToast('Permohonan proposal sponsorship telah dikirimkan ke panitia acara!')" class="w-full bg-zinc-800 hover:bg-zinc-700 text-white py-2.5 text-xs font-mono uppercase tracking-wider transition">
                        Ajukan Sponsorship
                    </button>
                </div>

                <div class="bg-zinc-900 border border-zinc-800 p-6 flex flex-col justify-between">
                    <div>
                        <div class="flex justify-between items-center mb-3">
                            <span class="text-[10px] font-mono bg-zinc-800 text-zinc-300 px-2 py-0.5">TARGET: EXECUTIVE & CORPORATE</span>
                            <span class="text-xs font-mono text-emerald-400">OPEN SPONSOR</span>
                        </div>
                        <h3 class="text-lg font-bold text-white uppercase mb-2">Indonesia Green Energy & Tech Forum</h3>
                        <p class="text-xs text-zinc-400 mb-4">Konferensi 2 hari menghadirkan 800+ CEO, Founder, & Delegasi Pemerintah. Booth & Platinum Sponsor.</p>
                        <div class="space-y-2 text-xs font-mono text-zinc-300 mb-6 bg-zinc-950 p-3 border border-zinc-800">
                            <div class="flex justify-between"><span>Platinum Sponsor:</span> <span>Rp 250.000.000</span></div>
                            <div class="flex justify-between"><span>Gold Sponsor:</span> <span>Rp 100.000.000</span></div>
                            <div class="flex justify-between"><span>Lokasi Event:</span> <span>JCC Senayan, Jakarta</span></div>
                        </div>
                    </div>
                    <button onclick="triggerToast('Permohonan proposal sponsorship telah dikirimkan ke panitia acara!')" class="w-full bg-zinc-800 hover:bg-zinc-700 text-white py-2.5 text-xs font-mono uppercase tracking-wider transition">
                        Ajukan Sponsorship
                    </button>
                </div>

                <div class="bg-zinc-900 border border-zinc-800 p-6 flex flex-col justify-between">
                    <div>
                        <div class="flex justify-between items-center mb-3">
                            <span class="text-[10px] font-mono bg-zinc-800 text-zinc-300 px-2 py-0.5">TARGET: COMMUTERS & RUNNERS</span>
                            <span class="text-xs font-mono text-emerald-400">OPEN SPONSOR</span>
                        </div>
                        <h3 class="text-lg font-bold text-white uppercase mb-2">Nusantara Night Half Marathon 2026</h3>
                        <p class="text-xs text-zinc-400 mb-4">Event Lari Malam Terbesar dengan 8.000 peserta terdaftar. Kategori Beverage, Apparel, & Bank Partner.</p>
                        <div class="space-y-2 text-xs font-mono text-zinc-300 mb-6 bg-zinc-950 p-3 border border-zinc-800">
                            <div class="flex justify-between"><span>Official Hydration:</span> <span>Rp 80.000.000</span></div>
                            <div class="flex justify-between"><span>Jersey Sponsor:</span> <span>Rp 120.000.000</span></div>
                            <div class="flex justify-between"><span>Lokasi Event:</span> <span>Batu Tulis, Bali</span></div>
                        </div>
                    </div>
                    <button onclick="triggerToast('Permohonan proposal sponsorship telah dikirimkan ke panitia acara!')" class="w-full bg-zinc-800 hover:bg-zinc-700 text-white py-2.5 text-xs font-mono uppercase tracking-wider transition">
                        Ajukan Sponsorship
                    </button>
                </div>

            </div>

        </div>
    </section>

    <!-- CREW & TALENT JOB BOARD SECTION -->
    <section id="crew" class="py-20 border-b border-zinc-800 dark:border-zinc-800 light:border-zinc-200 bg-zinc-950 dark:bg-zinc-950 light:bg-zinc-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-10 gap-4">
                <div>
                    <span class="text-xs font-mono uppercase tracking-widest text-zinc-400 block mb-2">// TECHNICAL CREW & FREELANCE TALENT DIRECTORY</span>
                    <h2 class="text-3xl font-black uppercase text-white dark:text-white light:text-black">
                        Crew & Technical Talent Hub
                    </h2>
                    <p class="text-xs text-zinc-400 mt-1">Lowongan harian & direktori crew panggung profesional: FOH Sound Engineer, Stagehand, LO, Runner, hingga Rigging Specialist.</p>
                </div>
            </div>

            <div class="bg-zinc-900 border border-zinc-800 overflow-x-auto">
                <table class="w-full text-left font-mono text-xs">
                    <thead class="bg-zinc-950 border-b border-zinc-800 text-zinc-400">
                        <tr>
                            <th class="p-4">POSISI CREW</th>
                            <th class="p-4">PROJECT / EVENT</th>
                            <th class="p-4">LOKASI</th>
                            <th class="p-4">HONOR HARIAN (DAILY RATE)</th>
                            <th class="p-4">STATUS</th>
                            <th class="p-4 text-right">ACTION</th>
                        </tr>
                    </thead>
                    <tbody class="divide-y divide-zinc-800 text-zinc-200">
                        <tr class="hover:bg-zinc-800/50">
                            <td class="p-4 font-bold text-white uppercase">FOH Sound Engineer (DiGiCo Spec)</td>
                            <td class="p-4">Concert World Tour Artist</td>
                            <td class="p-4">Istora Senayan, Jakarta</td>
                            <td class="p-4 text-emerald-400">Rp 2.500.000 / Day</td>
                            <td class="p-4"><span class="bg-zinc-800 text-zinc-300 px-2 py-0.5 text-[10px]">2 CREW NEEDED</span></td>
                            <td class="p-4 text-right">
                                <button onclick="triggerToast('Lamaran posisi FOH Sound Engineer berhasil dikirim!')" class="bg-white text-black font-bold px-3 py-1.5 hover:bg-zinc-200 transition">Lamar Now</button>
                            </td>
                        </tr>
                        <tr class="hover:bg-zinc-800/50">
                            <td class="p-4 font-bold text-white uppercase">Lighting Programmer GrandMA3</td>
                            <td class="p-4">Festival Musik Electronic</td>
                            <td class="p-4">GWK Park, Bali</td>
                            <td class="p-4 text-emerald-400">Rp 3.000.000 / Day</td>
                            <td class="p-4"><span class="bg-zinc-800 text-zinc-300 px-2 py-0.5 text-[10px]">1 CREW NEEDED</span></td>
                            <td class="p-4 text-right">
                                <button onclick="triggerToast('Lamaran posisi Lighting Programmer berhasil dikirim!')" class="bg-white text-black font-bold px-3 py-1.5 hover:bg-zinc-200 transition">Lamar Now</button>
                            </td>
                        </tr>
                        <tr class="hover:bg-zinc-800/50">
                            <td class="p-4 font-bold text-white uppercase">Senior Liaison Officer (LO VIP Artist)</td>
                            <td class="p-4">International Film Festival</td>
                            <td class="p-4">Yogyakarta</td>
                            <td class="p-4 text-emerald-400">Rp 850.000 / Day</td>
                            <td class="p-4"><span class="bg-zinc-800 text-zinc-300 px-2 py-0.5 text-[10px]">6 CREW NEEDED</span></td>
                            <td class="p-4 text-right">
                                <button onclick="triggerToast('Lamaran posisi Senior LO berhasil dikirim!')" class="bg-white text-black font-bold px-3 py-1.5 hover:bg-zinc-200 transition">Lamar Now</button>
                            </td>
                        </tr>
                        <tr class="hover:bg-zinc-800/50">
                            <td class="p-4 font-bold text-white uppercase">Stagehand & Cable Runner</td>
                            <td class="p-4">Corporate Annual Gala</td>
                            <td class="p-4">Surabaya</td>
                            <td class="p-4 text-emerald-400">Rp 500.000 / Day</td>
                            <td class="p-4"><span class="bg-zinc-800 text-zinc-300 px-2 py-0.5 text-[10px]">10 CREW NEEDED</span></td>
                            <td class="p-4 text-right">
                                <button onclick="triggerToast('Lamaran posisi Stagehand berhasil dikirim!')" class="bg-white text-black font-bold px-3 py-1.5 hover:bg-zinc-200 transition">Lamar Now</button>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>

        </div>
    </section>

    <!-- MODAL 1: SUBMIT PITCH / PROPOSAL MODAL -->
    <div id="modal-pitch" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 hidden items-center justify-center p-4">
        <div class="bg-zinc-900 border border-zinc-700 max-w-xl w-full p-6 sm:p-8 relative">
            <button onclick="closeModal('modal-pitch')" class="absolute top-4 right-4 text-zinc-400 hover:text-white">
                <i data-lucide="x" class="w-6 h-6"></i>
            </button>
            
            <div class="mb-6">
                <span class="text-xs font-mono text-emerald-400 uppercase">// SUBMIT PROJECT PITCH & RAB</span>
                <h3 id="modal-pitch-title" class="text-xl font-black uppercase text-white mt-1">Submit Proposal Tender</h3>
                <p id="modal-pitch-subtitle" class="text-xs text-zinc-400 mt-1">Pagu Anggaran: Rp 180 - 220 Juta</p>
            </div>

            <form onsubmit="handlePitchSubmit(event)" class="space-y-4 text-xs font-mono">
                <div>
                    <label class="block text-zinc-300 uppercase mb-1">Nama Vendor / Perusahaan</label>
                    <input type="text" required placeholder="Contoh: PT Sound Pro Indonesia" class="w-full bg-zinc-950 border border-zinc-700 text-white p-3 focus:outline-none focus:border-white">
                </div>
                <div>
                    <label class="block text-zinc-300 uppercase mb-1">Total Nilai Penawaran RAB (Rp)</label>
                    <input type="number" required placeholder="195000000" class="w-full bg-zinc-950 border border-zinc-700 text-white p-3 focus:outline-none focus:border-white">
                </div>
                <div>
                    <label class="block text-zinc-300 uppercase mb-1">Catatan Ringkas / Spesifikasi Utama</label>
                    <textarea rows="3" placeholder="Sebutkan spesifikasi alat utama yang Anda tawarkan..." class="w-full bg-zinc-950 border border-zinc-700 text-white p-3 focus:outline-none focus:border-white"></textarea>
                </div>
                <div class="border border-dashed border-zinc-700 p-4 text-center">
                    <i data-lucide="upload-cloud" class="w-6 h-6 mx-auto mb-2 text-zinc-400"></i>
                    <p class="text-zinc-400 text-[11px]">Upload File Proposal / Deck Spec (PDF Max 15MB)</p>
                    <span class="text-[10px] text-zinc-500">File Simulasi Otomatis Diterima</span>
                </div>
                <button type="submit" class="w-full bg-white text-black py-3.5 text-xs font-black uppercase tracking-widest hover:bg-zinc-200 transition">
                    Kirim Penawaran Sekarang
                </button>
            </form>
        </div>
    </div>

    <!-- MODAL 2: VENDOR QUOTATION REQUEST MODAL -->
    <div id="modal-vendor" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 hidden items-center justify-center p-4">
        <div class="bg-zinc-900 border border-zinc-700 max-w-lg w-full p-6 sm:p-8 relative">
            <button onclick="closeModal('modal-vendor')" class="absolute top-4 right-4 text-zinc-400 hover:text-white">
                <i data-lucide="x" class="w-6 h-6"></i>
            </button>
            
            <div class="mb-6">
                <span class="text-xs font-mono text-zinc-400 uppercase">// DIRECT QUOTATION REQUEST</span>
                <h3 id="modal-vendor-name" class="text-xl font-black uppercase text-white mt-1">Thunder Audio Pro</h3>
                <p id="modal-vendor-meta" class="text-xs text-zinc-400 mt-1">Sound System | Jakarta</p>
            </div>

            <form onsubmit="handleVendorQuoteSubmit(event)" class="space-y-4 text-xs font-mono">
                <div>
                    <label class="block text-zinc-300 uppercase mb-1">Nama Pemesan / Event Organizer</label>
                    <input type="text" required placeholder="Nama Anda atau PT Organiser" class="w-full bg-zinc-950 border border-zinc-700 text-white p-3 focus:outline-none focus:border-white">
                </div>
                <div>
                    <label class="block text-zinc-300 uppercase mb-1">Nomor WhatsApp & Email</label>
                    <input type="text" required placeholder="0812-xxxx-xxxx" class="w-full bg-zinc-950 border border-zinc-700 text-white p-3 focus:outline-none focus:border-white">
                </div>
                <div>
                    <label class="block text-zinc-300 uppercase mb-1">Tanggal Acara & Lokasi Venue</label>
                    <input type="text" required placeholder="Contoh: 25 Des 2026 @ BICC Bali" class="w-full bg-zinc-950 border border-zinc-700 text-white p-3 focus:outline-none focus:border-white">
                </div>
                <button type="submit" class="w-full bg-white text-black py-3.5 text-xs font-black uppercase tracking-widest hover:bg-zinc-200 transition">
                    Kirim Permintaan Quotation
                </button>
            </form>
        </div>
    </div>

    <!-- MODAL 3: PAID PROMOTION & ADVERTISING MODAL -->
    <div id="modal-ad" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 hidden items-center justify-center p-4">
        <div class="bg-zinc-900 border border-zinc-700 max-w-2xl w-full p-6 sm:p-8 relative">
            <button onclick="closeModal('modal-ad')" class="absolute top-4 right-4 text-zinc-400 hover:text-white">
                <i data-lucide="x" class="w-6 h-6"></i>
            </button>
            
            <div class="mb-6">
                <span class="text-xs font-mono text-emerald-400 uppercase">// BTS ADVERTISING & PROMOTION</span>
                <h3 class="text-2xl font-black uppercase text-white mt-1">Pasang Iklan & Priority Listing</h3>
                <p class="text-xs text-zinc-400 mt-1">Tingkatkan visibilitas vendor dan tender acara Anda di depan 50.000+ stakeholder event pertunjukan Indonesia.</p>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-6 font-mono text-xs">
                <div class="border border-zinc-700 p-4 bg-zinc-950 hover:border-white transition cursor-pointer" onclick="selectAdPackage('Featured Vendor Badge')">
                    <div class="text-amber-400 font-bold mb-1">FEATURED VENDOR</div>
                    <div class="text-lg font-extrabold text-white mb-2">Rp 1.5M <span class="text-[10px] text-zinc-500">/ Bln</span></div>
                    <ul class="text-[10px] text-zinc-400 space-y-1">
                        <li>✓ Top 3 Grid Directory</li>
                        <li>✓ Verified Blue Badge</li>
                        <li>✓ Direct WA Leads</li>
                    </ul>
                </div>
                <div class="border border-zinc-700 p-4 bg-zinc-950 hover:border-white transition cursor-pointer" onclick="selectAdPackage('Banner Ad Hero')">
                    <div class="text-amber-400 font-bold mb-1">HERO BANNER AD</div>
                    <div class="text-lg font-extrabold text-white mb-2">Rp 3.5M <span class="text-[10px] text-zinc-500">/ Bln</span></div>
                    <ul class="text-[10px] text-zinc-400 space-y-1">
                        <li>✓ Placement Halaman Utama</li>
                        <li>✓ Dedicated Click-Through</li>
                        <li>✓ Highlight Email Blast</li>
                    </ul>
                </div>
                <div class="border border-zinc-700 p-4 bg-zinc-950 hover:border-white transition cursor-pointer" onclick="selectAdPackage('Priority Tender RFP')">
                    <div class="text-amber-400 font-bold mb-1">PRIORITY TENDER</div>
                    <div class="text-lg font-extrabold text-white mb-2">Rp 750k <span class="text-[10px] text-zinc-500">/ Tender</span></div>
                    <ul class="text-[10px] text-zinc-400 space-y-1">
                        <li>✓ Push Notification Crew</li>
                        <li>✓ Urgent Bidding Tag</li>
                        <li>✓ Max Proposal Exposure</li>
                    </ul>
                </div>
            </div>

            <form onsubmit="handleAdSubmit(event)" class="space-y-4 text-xs font-mono">
                <input type="hidden" id="selected-ad-type" value="Featured Vendor Badge">
                <div>
                    <label class="block text-zinc-300 uppercase mb-1">Nama Perusahaan / Brand Kontak</label>
                    <input type="text" required placeholder="PT Event Jaya Mandiri" class="w-full bg-zinc-950 border border-zinc-700 text-white p-3 focus:outline-none focus:border-white">
                </div>
                <div>
                    <label class="block text-zinc-300 uppercase mb-1">WhatsApp Official</label>
                    <input type="text" required placeholder="0811-xxxx-xxxx" class="w-full bg-zinc-950 border border-zinc-700 text-white p-3 focus:outline-none focus:border-white">
                </div>
                <button type="submit" class="w-full bg-white text-black py-3.5 text-xs font-black uppercase tracking-widest hover:bg-zinc-200 transition">
                    Lanjutkan ke Pemasangan Iklan
                </button>
            </form>
        </div>
    </div>

    <!-- TOAST NOTIFICATION FLOATER -->
    <div id="toast" class="fixed bottom-6 right-6 z-50 bg-white text-black border border-zinc-400 px-5 py-3 shadow-2xl font-mono text-xs font-bold hidden items-center gap-3 transition-all duration-300 transform translate-y-4">
        <i data-lucide="check-circle-2" class="w-5 h-5 text-emerald-600"></i>
        <span id="toast-message">Notifikasi berhasil!</span>
    </div>

    <!-- FOOTER -->
    <footer class="bg-zinc-950 border-t border-zinc-800 text-zinc-400 py-16 text-xs font-mono">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-10 mb-12">
                
                <div class="space-y-4">
                    <!-- Brand SVG Footer -->
                    <svg class="h-8 w-auto text-white" viewBox="0 0 160 65" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <rect x="0" y="0" width="8" height="60" fill="currentColor" />
                        <rect x="13" y="0" width="8" height="46" fill="#A1A1AA" />
                        <rect x="26" y="0" width="8" height="32" fill="#71717A" />
                        <rect x="39" y="0" width="8" height="18" fill="#3F3F46" />
                        <text x="56" y="16" fill="currentColor" font-family="Inter, sans-serif" font-weight="800" font-size="16">BEHIND</text>
                        <text x="56" y="35" fill="currentColor" font-family="Inter, sans-serif" font-weight="800" font-size="16">THE</text>
                        <text x="56" y="54" fill="currentColor" font-family="Inter, sans-serif" font-weight="800" font-size="16">SHOW</text>
                    </svg>
                    <p class="text-zinc-500 text-[11px] leading-relaxed">
                        BehindTheShow.id adalah platform hub infrastruktur dan matchmaking ekosistem industri pertunjukan Indonesia.
                    </p>
                </div>

                <div>
                    <h4 class="text-white font-bold uppercase mb-4">Fitur Platform</h4>
                    <ul class="space-y-2">
                        <li><a href="#autofind" class="hover:text-white transition">Kalkulator RAB Event</a></li>
                        <li><a href="#directory" class="hover:text-white transition">Directory Vendor Produksi</a></li>
                        <li><a href="#tenders" class="hover:text-white transition">Open Tender RFP</a></li>
                        <li><a href="#sponsors" class="hover:text-white transition">Sponsor Matchmaking</a></li>
                        <li><a href="#crew" class="hover:text-white transition">Crew Job Board</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="text-white font-bold uppercase mb-4">Kategori Infrastructure</h4>
                    <ul class="space-y-2">
                        <li><a href="#directory" class="hover:text-white transition">Sound System Pro Line Array</a></li>
                        <li><a href="#directory" class="hover:text-white transition">Lighting Rig & Kinetic Laser</a></li>
                        <li><a href="#directory" class="hover:text-white transition">LED Screen Curved & Video Wall</a></li>
                        <li><a href="#directory" class="hover:text-white transition">Hydraulic Stage & Rigging Roof</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="text-white font-bold uppercase mb-4">Official Contact</h4>
                    <p class="text-zinc-500 mb-2">HQ: Grand Slipi Tower Lt. 18, Jakarta Barat</p>
                    <p class="text-zinc-300">Email: halo@behindtheshow.id</p>
                    <p class="text-zinc-300">WA Hotline: +62 812-8800-9900</p>
                </div>

            </div>

            <div class="border-t border-zinc-900 pt-8 flex flex-col sm:flex-row justify-between items-center text-zinc-600 text-[11px]">
                <p>&copy; 2026 BEHINDTHESHOW.ID — ALL RIGHTS RESERVED. HIGH CONTRAST INDUSTRIAL EDITION.</p>
                <div class="flex gap-4 mt-4 sm:mt-0">
                    <a href="#" class="hover:text-white">PRIVACY POLICY</a>
                    <a href="#" class="hover:text-white">TERMS OF SERVICE</a>
                    <a href="#" class="hover:text-white">VENDOR STANDARDS</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Initialize Lucide icons
        lucide.createIcons();

        // -------------------------------------------------------------
        // THEME TOGGLE LOGIC (DARK / LIGHT DUAL MODE)
        // -------------------------------------------------------------
        const themeToggleBtn = document.getElementById('theme-toggle');
        
        // Default dark mode
        if (localStorage.getItem('color-theme') === 'light') {
            document.documentElement.classList.remove('dark');
            document.documentElement.classList.add('light');
        } else {
            document.documentElement.classList.add('dark');
        }

        themeToggleBtn.addEventListener('click', function() {
            if (document.documentElement.classList.contains('dark')) {
                document.documentElement.classList.remove('dark');
                document.documentElement.classList.add('light');
                localStorage.setItem('color-theme', 'light');
            } else {
                document.documentElement.classList.remove('light');
                document.documentElement.classList.add('dark');
                localStorage.setItem('color-theme', 'dark');
            }
        });

        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // -------------------------------------------------------------
        // SMART AUTOFIND ENGINE & CALCULATOR LOGIC
        // -------------------------------------------------------------
        function calculateRAB(e) {
            e.preventDefault();

            const scale = document.getElementById('event-scale').value;
            const location = document.getElementById('event-location').value;
            const resultsDiv = document.getElementById('autofind-results');
            const totalRabEl = document.getElementById('result-total-rab');
            const breakdownEl = document.getElementById('rab-breakdown-list');
            const matchedEl = document.getElementById('matched-vendor-list');

            let baseCost = 0;
            let soundCost = 0;
            let lightingCost = 0;
            let ledCost = 0;
            let stageCost = 0;
            let crewCost = 0;

            if (scale === 'intimate') baseCost = 35000000;
            else if (scale === 'medium') baseCost = 120000000;
            else if (scale === 'large') baseCost = 320000000;
            else if (scale === 'mega') baseCost = 750000000;

            if (document.getElementById('need-sound').checked) soundCost = Math.round(baseCost * 0.35);
            if (document.getElementById('need-lighting').checked) lightingCost = Math.round(baseCost * 0.25);
            if (document.getElementById('need-led').checked) ledCost = Math.round(baseCost * 0.20);
            if (document.getElementById('need-stage').checked) stageCost = Math.round(baseCost * 0.15);
            if (document.getElementById('need-crew').checked) crewCost = Math.round(baseCost * 0.05);

            const total = soundCost + lightingCost + ledCost + stageCost + crewCost;

            totalRabEl.innerText = 'Rp ' + total.toLocaleString('id-ID');

            breakdownEl.innerHTML = `
                <div class="flex justify-between py-1 border-b border-zinc-900"><span>1. Sound System Spec:</span> <span class="text-white">Rp ${soundCost.toLocaleString('id-ID')}</span></div>
                <div class="flex justify-between py-1 border-b border-zinc-900"><span>2. Lighting Fixtures:</span> <span class="text-white">Rp ${lightingCost.toLocaleString('id-ID')}</span></div>
                <div class="flex justify-between py-1 border-b border-zinc-900"><span>3. LED Videowall Modular:</span> <span class="text-white">Rp ${ledCost.toLocaleString('id-ID')}</span></div>
                <div class="flex justify-between py-1 border-b border-zinc-900"><span>4. Rigging Stage & Backdrop:</span> <span class="text-white">Rp ${stageCost.toLocaleString('id-ID')}</span></div>
                <div class="flex justify-between py-1 border-b border-zinc-900"><span>5. Standby Technical Crew:</span> <span class="text-white">Rp ${crewCost.toLocaleString('id-ID')}</span></div>
            `;

            matchedEl.innerHTML = `
                <div class="p-3 bg-zinc-950 border border-zinc-800 flex items-center justify-between">
                    <div>
                        <span class="text-[10px] text-emerald-400 font-bold block">98.8% MATCH ACCURACY</span>
                        <h5 class="text-sm font-bold text-white uppercase">Thunder Audio Pro & Lumina</h5>
                        <p class="text-[11px] text-zinc-400">Paket bundling Sound + Lighting untuk lokasi ${location.toUpperCase()}</p>
                    </div>
                    <button onclick="openVendorDetail('Thunder Audio Pro', 'Bundled Package', '${location}', 'All Spec Inbound', 'Rp ${total.toLocaleString('id-ID')}')" class="bg-white text-black px-3 py-1.5 text-xs font-bold hover:bg-zinc-200">
                        Request Pitch
                    </button>
                </div>
                <div class="p-3 bg-zinc-950 border border-zinc-800 flex items-center justify-between">
                    <div>
                        <span class="text-[10px] text-emerald-400 font-bold block">95.4% MATCH ACCURACY</span>
                        <h5 class="text-sm font-bold text-white uppercase">PixelMatrix LED & Titan Rigging</h5>
                        <p class="text-[11px] text-zinc-400">Paket Visual Stage Heavy-Duty</p>
                    </div>
                    <button onclick="openVendorDetail('PixelMatrix LED', 'Stage & Visual', '${location}', 'LED + Truss', 'Rp ${total.toLocaleString('id-ID')}')" class="bg-white text-black px-3 py-1.5 text-xs font-bold hover:bg-zinc-200">
                        Request Pitch
                    </button>
                </div>
            `;

            resultsDiv.classList.remove('hidden');
            resultsDiv.scrollIntoView({ behavior: 'smooth' });
            triggerToast('Kalkulasi RAB & Matching Vendor Berhasil!');
        }

        // -------------------------------------------------------------
        // VENDOR FILTER & SEARCH LOGIC
        // -------------------------------------------------------------
        function setVendorCategory(cat) {
            const btns = document.querySelectorAll('.vendor-cat-btn');
            btns.forEach(b => b.classList.remove('tab-active', 'text-white'));
            
            event.target.classList.add('tab-active');

            const cards = document.querySelectorAll('.vendor-card');
            cards.forEach(card => {
                if (cat === 'all' || card.dataset.category === cat) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        function filterVendors() {
            const query = document.getElementById('vendor-search').value.toLowerCase();
            const cards = document.querySelectorAll('.vendor-card');
            
            cards.forEach(card => {
                const text = card.innerText.toLowerCase();
                if (text.includes(query)) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        // -------------------------------------------------------------
        // MODAL CONTROLS & EVENT HANDLERS
        // -------------------------------------------------------------
        function openPitchModal(title, subtitle) {
            document.getElementById('modal-pitch-title').innerText = title;
            document.getElementById('modal-pitch-subtitle').innerText = 'Pagu Anggaran: ' + subtitle;
            document.getElementById('modal-pitch').style.display = 'flex';
        }

        function openVendorDetail(name, cat, city, specs, price) {
            document.getElementById('modal-vendor-name').innerText = name;
            document.getElementById('modal-vendor-meta').innerText = `${cat} | ${city} | Spek: ${specs}`;
            document.getElementById('modal-vendor').style.display = 'flex';
        }

        function openAdModal() {
            document.getElementById('modal-ad').style.display = 'flex';
        }

        function closeModal(id) {
            document.getElementById(id).style.display = 'none';
        }

        function selectAdPackage(pkg) {
            document.getElementById('selected-ad-type').value = pkg;
            triggerToast('Paket Iklan Dipilih: ' + pkg);
        }

        function handlePitchSubmit(e) {
            e.preventDefault();
            closeModal('modal-pitch');
            triggerToast('Proposal Pitch RAB Anda Berhasil Dikirimkan ke Promotor!');
        }

        function handleVendorQuoteSubmit(e) {
            e.preventDefault();
            closeModal('modal-vendor');
            triggerToast('Permintaan Quotation Langsung Dikirim ke Vendor WhatsApp!');
        }

        function handleAdSubmit(e) {
            e.preventDefault();
            closeModal('modal-ad');
            triggerToast('Permohonan Iklan Diterima! Tim Sales BTS akan menghubungi Anda.');
        }

        // -------------------------------------------------------------
        // TOAST NOTIFICATION UTILITY
        // -------------------------------------------------------------
        function triggerToast(msg) {
            const toast = document.getElementById('toast');
            const toastMsg = document.getElementById('toast-message');
            toastMsg.innerText = msg;
            toast.classList.remove('hidden');
            toast.classList.add('flex');
            toast.style.transform = 'translateY(0)';

            setTimeout(() => {
                toast.style.transform = 'translateY(1rem)';
                setTimeout(() => {
                    toast.classList.add('hidden');
                    toast.classList.remove('flex');
                }, 300);
            }, 3500);
        }
    </script>
</body>
</html>
[Uploading behindtheshow_event_industry_hub.html…]()
