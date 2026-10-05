<!DOCTYPE html>
<html lang="en" class="dark scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Behind The Show - The All-In-One Event Ecosystem</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Syne:wght@700;800&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            orange: '#FF3B00',
                            orangeDark: '#D63200',
                            cyan: '#00F0FF',
                            cyanDark: '#00B8C4',
                            dark: '#09090B',
                            card: '#121217',
                            cardHover: '#1A1A22',
                            border: '#27272A'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Syne', 'Impact', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <style>
        /* Custom Glowing & Outline Text Effects from Design Prototype */
        .text-stroke-cyan {
            -webkit-text-stroke: 1.5px #00F0FF;
            color: transparent;
        }
        .text-stroke-orange {
            -webkit-text-stroke: 1.5px #FF3B00;
            color: transparent;
        }
        .glow-orange {
            box-shadow: 0 0 30px rgba(255, 59, 0, 0.35);
        }
        .glow-cyan {
            box-shadow: 0 0 25px rgba(0, 240, 255, 0.25);
        }
        /* Custom Bar Equalizer Icon Animation */
        .eq-bar {
            animation: eqPulse 1.2s infinite ease-in-out alternate;
        }
        .eq-bar:nth-child(1) { animation-delay: 0.1s; }
        .eq-bar:nth-child(2) { animation-delay: 0.3s; }
        .eq-bar:nth-child(3) { animation-delay: 0.2s; }
        .eq-bar:nth-child(4) { animation-delay: 0.4s; }

        @keyframes eqPulse {
            0% { height: 25%; }
            100% { height: 100%; }
        }

        /* Glassmorphism */
        .glass-panel {
            background: rgba(18, 18, 23, 0.85);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }
    </style>
</head>
<body class="bg-brand-dark text-zinc-100 font-sans selection:bg-brand-orange selection:text-white min-h-screen flex flex-col justify-between overflow-x-hidden">

    <!-- NAVIGATION BAR -->
    <header class="sticky top-0 z-50 glass-panel border-b border-brand-border/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                
                <!-- Logo with 4-Bar Stepped Equalizer / Truss Icon -->
                <a href="#" class="flex items-center gap-3 group">
                    <div class="w-10 h-10 bg-brand-orange rounded-lg flex items-end justify-center p-2 gap-1 group-hover:scale-105 transition-transform shadow-lg shadow-brand-orange/30">
                        <span class="w-1.5 bg-white rounded-full eq-bar h-2"></span>
                        <span class="w-1.5 bg-white rounded-full eq-bar h-4"></span>
                        <span class="w-1.5 bg-white rounded-full eq-bar h-6"></span>
                        <span class="w-1.5 bg-white rounded-full eq-bar h-3"></span>
                    </div>
                    <div class="flex flex-col">
                        <span class="font-display text-xl font-extrabold tracking-wider text-white leading-none">BEHIND<span class="text-brand-orange">THE</span>SHOW</span>
                        <span class="text-[10px] text-brand-cyan tracking-widest font-semibold uppercase">Event Ecosystem .id</span>
                    </div>
                </a>

                <!-- Nav Links -->
                <nav class="hidden md:flex items-center gap-8 text-sm font-medium text-zinc-300">
                    <a href="#hero" class="hover:text-brand-orange transition-colors">Featured Event</a>
                    <a href="#ecosystem" class="hover:text-brand-orange transition-colors">Ecosystem</a>
                    <a href="#directory" class="hover:text-brand-orange transition-colors">Vendor Directory</a>
                    <a href="#rab-calculator" class="hover:text-brand-cyan transition-colors flex items-center gap-1.5">
                        <i class="fa-solid fa-calculator text-brand-cyan"></i> Smart RAB
                    </a>
                    <a href="#open-tender" class="hover:text-brand-orange transition-colors">Open Tender (RFP)</a>
                    <a href="#recruitment" class="hover:text-brand-orange transition-colors">Sponsor & Crew</a>
                </nav>

                <!-- Action Buttons -->
                <div class="flex items-center gap-3">
                    <button onclick="openRFPModal()" class="hidden sm:inline-flex items-center gap-2 bg-gradient-to-r from-brand-orange to-red-600 hover:from-brand-orangeDark hover:to-red-700 text-white font-semibold text-xs uppercase tracking-wider px-4 py-2.5 rounded-lg shadow-lg shadow-brand-orange/20 transition-all hover:scale-105 active:scale-95">
                        <i class="fa-solid fa-plus-circle"></i> Post RFP
                    </button>
                    <button id="themeToggle" onclick="toggleTheme()" class="w-10 h-10 rounded-lg bg-zinc-800 border border-zinc-700 flex items-center justify-center text-zinc-300 hover:text-white hover:bg-zinc-700 transition">
                        <i class="fa-solid fa-sun" id="themeIcon"></i>
                    </button>
                    <!-- Mobile Menu Toggle -->
                    <button onclick="toggleMobileMenu()" class="md:hidden w-10 h-10 rounded-lg bg-zinc-800 flex items-center justify-center text-zinc-300">
                        <i class="fa-solid fa-bars text-lg"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu Container -->
        <div id="mobileMenu" class="hidden md:hidden bg-brand-card border-b border-brand-border px-4 py-4 space-y-3">
            <a href="#hero" onclick="toggleMobileMenu()" class="block text-zinc-300 hover:text-brand-orange py-1">Featured Event</a>
            <a href="#ecosystem" onclick="toggleMobileMenu()" class="block text-zinc-300 hover:text-brand-orange py-1">Ecosystem Vision</a>
            <a href="#directory" onclick="toggleMobileMenu()" class="block text-zinc-300 hover:text-brand-orange py-1">Vendor Directory</a>
            <a href="#rab-calculator" onclick="toggleMobileMenu()" class="block text-brand-cyan hover:text-white py-1">Smart RAB Estimator</a>
            <a href="#open-tender" onclick="toggleMobileMenu()" class="block text-zinc-300 hover:text-brand-orange py-1">Open Tender (RFP)</a>
            <a href="#recruitment" onclick="toggleMobileMenu()" class="block text-zinc-300 hover:text-brand-orange py-1">Sponsor & Crew</a>
            <button onclick="toggleMobileMenu(); openRFPModal();" class="w-full bg-brand-orange text-white py-2.5 rounded-lg font-semibold text-sm uppercase tracking-wider">
                Post RFP Proposal
            </button>
        </div>
    </header>

    <main class="flex-grow">
        <!-- HERO SECTION (RECREATED FROM PROTOTYPE 1.pdf) -->
        <section id="hero" class="relative py-8 md:py-12 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 items-stretch">
                
                <!-- Main Event Poster Banner (The Weeknd Asia Tour) -->
                <div class="lg:col-span-8 bg-brand-orange rounded-2xl overflow-hidden shadow-2xl relative flex flex-col md:flex-row group min-h-[380px] border border-brand-orange/40">
                    
                    <!-- Left Section: Fiery Orange Graphic & Bold Headline -->
                    <div class="p-6 md:p-10 flex-1 flex flex-col justify-between z-10 text-black">
                        <div>
                            <!-- Tagline -->
                            <div class="inline-flex items-center gap-2 bg-black text-brand-cyan text-xs font-bold uppercase tracking-widest px-3 py-1 rounded-full mb-4">
                                <span class="w-2 h-2 rounded-full bg-brand-cyan animate-pulse"></span>
                                Coming Up Event
                            </div>
                            
                            <!-- Stylized Vertical Outline Text "A S I A" & Headline -->
                            <div class="relative my-2">
                                <div class="font-display text-5xl md:text-7xl font-black tracking-widest text-stroke-cyan leading-none select-none opacity-90">
                                    A &nbsp; S &nbsp; I &nbsp; A
                                </div>
                                <h1 class="font-display text-4xl md:text-6xl font-black tracking-tight text-black uppercase leading-none mt-2">
                                    THE WEEKND
                                </h1>
                            </div>
                        </div>

                        <!-- Sub-heading & Action -->
                        <div class="mt-6 border-t border-black/20 pt-4">
                            <p class="font-black text-sm md:text-base tracking-widest text-black uppercase">
                                THE FINAL LEG BEFORE SHUTDOWN...
                            </p>
                            <div class="mt-4 flex flex-wrap items-center gap-3">
                                <button onclick="triggerTicketModal('The Weeknd Asia Tour 2026')" class="bg-black hover:bg-zinc-900 text-white font-bold text-xs uppercase tracking-wider px-5 py-3 rounded-xl flex items-center gap-2 transition-transform transform group-hover:translate-x-1 shadow-xl">
                                    <i class="fa-solid fa-ticket text-brand-cyan"></i> Get Tickets / Info
                                </button>
                                <span class="text-xs font-bold text-black/80 bg-white/20 px-3 py-2 rounded-lg backdrop-blur-sm">
                                    <i class="fa-solid fa-location-dot"></i> GBK Main Stadium, Jakarta
                                </span>
                            </div>
                        </div>
                    </div>

                    <!-- Right Section: Visual Artist Portrait / Image Overlay -->
                    <div class="w-full md:w-1/2 relative min-h-[260px] md:min-h-full bg-zinc-900 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1514525253161-7a46d19cd819?q=80&w=1000&auto=format&fit=crop" 
                             alt="The Weeknd Stage Performance" 
                             class="w-full h-full object-cover object-center mix-blend-luminosity opacity-90 group-hover:scale-105 transition-transform duration-700">
                        <!-- Warm Red/Orange Gradient Overlays to match prototype atmosphere -->
                        <div class="absolute inset-0 bg-gradient-to-t md:bg-gradient-to-r from-brand-orange via-transparent to-transparent opacity-90"></div>
                        <div class="absolute inset-0 bg-gradient-to-b from-transparent via-black/30 to-black/80"></div>
                        
                        <!-- Floating Artist Status Pill -->
                        <div class="absolute bottom-4 right-4 bg-black/80 backdrop-blur-md px-3 py-1.5 rounded-lg border border-white/10 text-right">
                            <div class="text-[10px] text-zinc-400 font-medium">Stage AVL by</div>
                            <div class="text-xs font-bold text-brand-cyan flex items-center gap-1">
                                <i class="fa-solid fa-circle-check"></i> BehindTheShow Partner
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Catalogue Recommendation Box (Matching Prototype Right Side) -->
                <div class="lg:col-span-4 bg-brand-card rounded-2xl p-6 border border-brand-border flex flex-col justify-between relative overflow-hidden group hover:border-brand-cyan/50 transition-colors">
                    <div class="absolute -top-12 -right-12 w-36 h-36 bg-brand-cyan/10 rounded-full blur-2xl group-hover:bg-brand-cyan/20 transition-all"></div>
                    
                    <div>
                        <!-- Header badge -->
                        <div class="flex items-center justify-between mb-4">
                            <span class="text-xs font-bold text-zinc-400 uppercase tracking-widest flex items-center gap-2">
                                <i class="fa-solid fa-star text-brand-orange"></i> Catalogue Recommendation
                            </span>
                            <span class="bg-brand-cyan/10 text-brand-cyan border border-brand-cyan/30 text-[10px] font-bold uppercase px-2.5 py-0.5 rounded-full">
                                Verified Partner
                            </span>
                        </div>

                        <!-- Brand Showcase: LOKET -->
                        <div class="bg-zinc-900/90 rounded-xl p-5 border border-zinc-800 my-2">
                            <div class="flex items-center justify-between mb-2">
                                <h3 class="font-display text-2xl font-black tracking-wider text-white">
                                    LOK<span class="text-brand-cyan">É</span>T
                                </h3>
                                <span class="text-xs text-zinc-400 font-mono">@loketcom</span>
                            </div>
                            <p class="text-xs text-zinc-400 leading-relaxed">
                                Official ticketing & access control partner for mega concerts, sports, and international expos across Southeast Asia.
                            </p>
                        </div>

                        <!-- Feature Badges -->
                        <div class="grid grid-cols-2 gap-2 mt-4 text-xs font-medium text-zinc-300">
                            <div class="bg-zinc-800/60 p-2.5 rounded-lg border border-zinc-700/50 flex items-center gap-2">
                                <i class="fa-solid fa-qrcode text-brand-cyan"></i>
                                <span>RFID Gate Access</span>
                            </div>
                            <div class="bg-zinc-800/60 p-2.5 rounded-lg border border-zinc-700/50 flex items-center gap-2">
                                <i class="fa-solid fa-bolt text-brand-orange"></i>
                                <span>Instant Cashout</span>
                            </div>
                        </div>
                    </div>

                    <!-- Bottom CTA button -->
                    <div class="mt-6 pt-4 border-t border-zinc-800">
                        <a href="https://loket.com" target="_blank" rel="noopener" class="w-full bg-zinc-800 hover:bg-brand-cyan hover:text-black text-white font-bold text-xs uppercase tracking-wider py-3 rounded-xl flex items-center justify-center gap-2 transition-all">
                            Visit loket.com <i class="fa-solid fa-arrow-up-right-from-square text-xs"></i>
                        </a>
                    </div>
                </div>

            </div>
        </section>

        <!-- ECOSYSTEM VISION STATEMENT (EXACT TEXT FROM PROTOTYPE) -->
        <section id="ecosystem" class="py-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="bg-gradient-to-r from-brand-card via-zinc-900 to-brand-card rounded-2xl p-6 sm:p-10 border border-brand-border relative overflow-hidden shadow-2xl">
                <!-- Decorative Graphic Lines -->
                <div class="absolute top-0 right-0 w-64 h-64 bg-brand-orange/5 rounded-full blur-3xl pointer-events-none"></div>
                
                <div class="max-w-4xl mx-auto text-center space-y-4">
                    <!-- Title Badge -->
                    <div class="inline-block">
                        <span class="text-xs font-extrabold text-brand-cyan uppercase tracking-widest bg-brand-cyan/10 px-4 py-1.5 rounded-full border border-brand-cyan/30">
                            THE ALL-IN-ONE EVENT ECOSYSTEM
                        </span>
                    </div>

                    <h2 class="font-display text-3xl sm:text-4xl font-extrabold tracking-tight text-white uppercase">
                        BEHIND THE SHOW
                    </h2>

                    <!-- Exact English text from prototype PDF -->
                    <p class="text-zinc-300 text-sm sm:text-base leading-relaxed sm:leading-loose text-justify sm:text-center font-normal pt-2">
                        <strong class="text-white font-semibold">Behindtheshow.id</strong> is the premier digital ecosystem built to connect, empower, and streamline the entire creative and event industry. We serve as a centralized hub where event organizers, vendors, contractors, agencies, brands, and technical crew seamlessly collaborate. By leveraging smart geolocation, custom budget estimators, and verified ratings, We help you instantly discover and compare the exact equipment, services, and partners required for your event based on location and cost. Beyond directory searches, we simplify your entire event production workflow by enabling open tender (RFP) bidding for competitive proposals, direct sponsorship matching for brand activations, and rapid freelance workforce recruitment—providing the all-in-one infrastructure you need to turn any event vision into a seamless reality.
                    </p>

                    <!-- Ecosystem Pillars -->
                    <div class="grid grid-cols-2 md:grid-cols-4 gap-4 pt-6 text-left">
                        <div class="bg-zinc-950/60 p-4 rounded-xl border border-zinc-800 hover:border-brand-orange/40 transition-colors">
                            <i class="fa-solid fa-map-location-dot text-brand-orange text-xl mb-2"></i>
                            <h4 class="text-xs font-bold text-white uppercase">Smart Geolocation</h4>
                            <p class="text-[11px] text-zinc-400 mt-1">Locate closest AVL, stage & merch vendors.</p>
                        </div>
                        <div class="bg-zinc-950/60 p-4 rounded-xl border border-zinc-800 hover:border-brand-cyan/40 transition-colors">
                            <i class="fa-solid fa-calculator text-brand-cyan text-xl mb-2"></i>
                            <h4 class="text-xs font-bold text-white uppercase">RAB Estimator</h4>
                            <p class="text-[11px] text-zinc-400 mt-1">Auto-calculate event budgets & allocations.</p>
                        </div>
                        <div class="bg-zinc-950/60 p-4 rounded-xl border border-zinc-800 hover:border-brand-orange/40 transition-colors">
                            <i class="fa-solid fa-file-signature text-brand-orange text-xl mb-2"></i>
                            <h4 class="text-xs font-bold text-white uppercase">Open Tender (RFP)</h4>
                            <p class="text-[11px] text-zinc-400 mt-1">Submit bids & transparent proposals.</p>
                        </div>
                        <div class="bg-zinc-950/60 p-4 rounded-xl border border-zinc-800 hover:border-brand-cyan/40 transition-colors">
                            <i class="fa-solid fa-users-gear text-brand-cyan text-xl mb-2"></i>
                            <h4 class="text-xs font-bold text-white uppercase">Crew Recruitment</h4>
                            <p class="text-[11px] text-zinc-400 mt-1">Hire verified sound, stage & SIS technicians.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- FEATURE 1: VENDOR SEARCH ENGINE & DIRECTORY (WITH GEOLOCATION & PRICE FILTERS) -->
        <section id="directory" class="py-12 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-8 gap-4">
                <div>
                    <span class="text-xs font-bold text-brand-orange uppercase tracking-widest">Ecosystem Partners</span>
                    <h2 class="font-display text-3xl font-black text-white uppercase mt-1">Vendor & Equipment Directory</h2>
                    <p class="text-xs text-zinc-400 mt-1">Filter verified AVL, Stage, Konveksi Merch, SIS Translation, and Talent by proximity to venue.</p>
                </div>
                <div class="flex items-center gap-2">
                    <span class="text-xs text-zinc-400">Target Venue:</span>
                    <span class="bg-zinc-800 text-brand-cyan text-xs font-semibold px-3 py-1.5 rounded-lg border border-zinc-700 flex items-center gap-1.5">
                        <i class="fa-solid fa-location-dot"></i> GBK Senayan, Jakarta
                    </span>
                </div>
            </div>

            <!-- Directory Controls Bar -->
            <div class="bg-brand-card p-4 rounded-2xl border border-brand-border mb-8 space-y-4">
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
                    <!-- Search Input -->
                    <div class="relative">
                        <i class="fa-solid fa-search absolute left-3.5 top-3.5 text-zinc-500 text-sm"></i>
                        <input type="text" id="vendorSearch" onkeyup="filterVendors()" placeholder="Search sound, lighting, konveksi..." class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl pl-10 pr-4 py-3 focus:outline-none focus:border-brand-orange transition">
                    </div>

                    <!-- Category Select -->
                    <div>
                        <select id="categoryFilter" onchange="filterVendors()" class="w-full bg-zinc-900 border border-zinc-800 text-zinc-300 text-xs rounded-xl px-3 py-3 focus:outline-none focus:border-brand-orange transition">
                            <option value="ALL">All Categories</option>
                            <option value="AVL">Audio Visual Lighting (AVL)</option>
                            <option value="STAGE">Stage & Rigging Contractor</option>
                            <option value="KONVEKSI">Garment & Merch Konveksi</option>
                            <option value="TRANSLATOR">SIS Translator & Seminar Tech</option>
                            <option value="CREW">Technical Crew & Production</option>
                        </select>
                    </div>

                    <!-- Distance Filter Slider -->
                    <div class="bg-zinc-900 border border-zinc-800 px-4 py-2 rounded-xl flex flex-col justify-center">
                        <div class="flex justify-between items-center text-[11px] text-zinc-400 mb-1">
                            <span>Max Distance:</span>
                            <span id="distanceValue" class="text-brand-cyan font-bold">15 km</span>
                        </div>
                        <input type="range" id="distanceRange" min="1" max="50" value="15" oninput="updateDistanceLabel(this.value); filterVendors();" class="w-full accent-brand-cyan h-1 bg-zinc-800 rounded-lg cursor-pointer">
                    </div>

                    <!-- Sort By -->
                    <div>
                        <select id="sortFilter" onchange="filterVendors()" class="w-full bg-zinc-900 border border-zinc-800 text-zinc-300 text-xs rounded-xl px-3 py-3 focus:outline-none focus:border-brand-orange transition">
                            <option value="PROXIMITY">Sort by: Nearest Distance</option>
                            <option value="RATING">Sort by: Highest Rating</option>
                            <option value="PRICE_LOW">Sort by: Price (Low to High)</option>
                        </select>
                    </div>
                </div>
            </div>

            <!-- Dynamic Vendor Cards Grid -->
            <div id="vendorGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Dynamic Content Injected via JS -->
            </div>
        </section>

        <!-- FEATURE 2: SMART AUTOFIND ENGINE (RAB BUDGET ESTIMATOR & GENERATOR) -->
        <section id="rab-calculator" class="py-12 bg-zinc-950/80 border-y border-brand-border">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-3xl mx-auto mb-10">
                    <span class="text-xs font-bold text-brand-cyan uppercase tracking-widest bg-brand-cyan/10 px-3 py-1 rounded-full border border-brand-cyan/20">
                        AI-Powered Smart Autofind
                    </span>
                    <h2 class="font-display text-3xl sm:text-4xl font-extrabold text-white uppercase mt-3">
                        Event RAB Budget Estimator
                    </h2>
                    <p class="text-xs sm:text-sm text-zinc-400 mt-2">
                        Input your event parameters to auto-generate standard itemized budget allocations (RAB) and instantly match required vendors.
                    </p>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-start">
                    <!-- RAB Form Controls -->
                    <div class="lg:col-span-5 bg-brand-card p-6 rounded-2xl border border-brand-border space-y-5">
                        <h3 class="text-sm font-bold text-white uppercase flex items-center gap-2">
                            <i class="fa-solid fa-sliders text-brand-orange"></i> Configure Event Scope
                        </h3>

                        <!-- Event Type -->
                        <div>
                            <label class="block text-xs text-zinc-400 mb-2 font-medium">Event Format</label>
                            <select id="rabEventType" class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl px-3 py-3">
                                <option value="CONCERT">Outdoor Music Concert / Festival</option>
                                <option value="SEMINAR">International Seminar & MICE (with SIS Translator)</option>
                                <option value="BRAND">Brand Activation & Exhibition</option>
                            </select>
                        </div>

                        <!-- Target Audience -->
                        <div>
                            <label class="block text-xs text-zinc-400 mb-2 font-medium">Expected Capacity (Audience)</label>
                            <select id="rabAudience" class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl px-3 py-3">
                                <option value="500">Up to 500 Pax</option>
                                <option value="2000">1,000 - 3,000 Pax</option>
                                <option value="10000">5,000 - 15,000+ Pax (Stadium Scale)</option>
                            </select>
                        </div>

                        <!-- Total Budget Slider -->
                        <div>
                            <div class="flex justify-between text-xs mb-2">
                                <span class="text-zinc-400">Total Production Budget (IDR):</span>
                                <span id="rabBudgetValue" class="text-brand-orange font-bold font-mono">Rp 150,000,000</span>
                            </div>
                            <input type="range" id="rabBudgetInput" min="20000000" max="500000000" step="10000000" value="150000000" oninput="updateRABValue(this.value)" class="w-full accent-brand-orange h-2 bg-zinc-800 rounded-lg cursor-pointer">
                        </div>

                        <button onclick="calculateRAB()" class="w-full bg-gradient-to-r from-brand-orange to-red-600 hover:from-brand-orangeDark hover:to-red-700 text-white font-bold text-xs uppercase tracking-wider py-3.5 rounded-xl shadow-lg shadow-brand-orange/20 transition">
                            <i class="fa-solid fa-wand-magic-sparkles"></i> Generate RAB & Match Vendors
                        </button>
                    </div>

                    <!-- RAB Results & Allocation Breakdown -->
                    <div class="lg:col-span-7 bg-brand-card p-6 rounded-2xl border border-brand-border min-h-[380px] flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between pb-4 border-b border-zinc-800">
                                <h3 class="text-sm font-bold text-white uppercase">Itemized RAB Allocation</h3>
                                <span class="text-[10px] text-brand-cyan bg-brand-cyan/10 px-2.5 py-1 rounded-full font-mono">
                                    Standard Production Ratio
                                </span>
                            </div>

                            <div id="rabBreakdownList" class="mt-6 space-y-4">
                                <!-- Dynamic Breakdown Bars Injected via JS -->
                            </div>
                        </div>

                        <!-- Match Summary CTA -->
                        <div class="mt-6 pt-4 border-t border-zinc-800 flex flex-wrap items-center justify-between gap-3">
                            <div class="text-xs text-zinc-400">
                                Auto-matched <span id="matchedCount" class="text-white font-bold">4</span> top-rated vendors in Jakarta.
                            </div>
                            <button onclick="exportRAB()" class="bg-zinc-800 hover:bg-zinc-700 text-white text-xs font-bold px-4 py-2 rounded-lg transition flex items-center gap-2">
                                <i class="fa-solid fa-download text-brand-cyan"></i> Export Copy RAB
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- FEATURE 3: OPEN TENDER (RFP) BIDDING PORTAL -->
        <section id="open-tender" class="py-12 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-8 gap-4">
                <div>
                    <span class="text-xs font-bold text-brand-cyan uppercase tracking-widest">Transparent Bidding</span>
                    <h2 class="font-display text-3xl font-black text-white uppercase mt-1">Open Tender (RFP) Portal</h2>
                    <p class="text-xs text-zinc-400 mt-1">Submit competitive pitch proposals or publish requirements for vendor bidding.</p>
                </div>
                <button onclick="openRFPModal()" class="bg-brand-orange hover:bg-brand-orangeDark text-white font-bold text-xs uppercase tracking-wider px-5 py-3 rounded-xl transition flex items-center gap-2">
                    <i class="fa-solid fa-plus"></i> Submit New RFP Request
                </button>
            </div>

            <!-- RFP Active List -->
            <div id="rfpContainer" class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- RFP Card 1 -->
                <div class="bg-brand-card p-6 rounded-2xl border border-brand-border flex flex-col justify-between hover:border-brand-orange/40 transition">
                    <div>
                        <div class="flex justify-between items-start mb-3">
                            <span class="bg-brand-orange/10 text-brand-orange border border-brand-orange/30 text-[10px] font-bold uppercase px-2.5 py-0.5 rounded-full">
                                Sound & Stage Tender
                            </span>
                            <span class="text-[11px] text-zinc-500"><i class="fa-regular fa-clock"></i> 3 Days Left</span>
                        </div>
                        <h3 class="font-bold text-base text-white">Java Jazz Festival Mainstage Audio & Trussing</h3>
                        <p class="text-xs text-zinc-400 mt-2 line-clamp-2">
                            Requires Line Array 40kW L-Acoustics K2 or equivalent, 12x10m Aluminum Roof Truss, & GrandMA3 console.
                        </p>
                    </div>

                    <div class="mt-6 pt-4 border-t border-zinc-800 space-y-3">
                        <div class="flex justify-between text-xs">
                            <span class="text-zinc-500">Target Budget:</span>
                            <span class="text-brand-cyan font-bold font-mono">Rp 120,000,000</span>
                        </div>
                        <button onclick="openProposalModal('Java Jazz Festival Mainstage Audio & Trussing')" class="w-full bg-zinc-800 hover:bg-brand-orange hover:text-white text-zinc-200 text-xs font-bold py-2.5 rounded-xl transition">
                            Submit Proposal / Bid
                        </button>
                    </div>
                </div>

                <!-- RFP Card 2 -->
                <div class="bg-brand-card p-6 rounded-2xl border border-brand-border flex flex-col justify-between hover:border-brand-cyan/40 transition">
                    <div>
                        <div class="flex justify-between items-start mb-3">
                            <span class="bg-brand-cyan/10 text-brand-cyan border border-brand-cyan/30 text-[10px] font-bold uppercase px-2.5 py-0.5 rounded-full">
                                Konveksi Merch
                            </span>
                            <span class="text-[11px] text-zinc-500"><i class="fa-regular fa-clock"></i> 5 Days Left</span>
                        </div>
                        <h3 class="font-bold text-base text-white">2,000 Pcs Tech Summit Official Hoodie & Polo</h3>
                        <p class="text-xs text-zinc-400 mt-2 line-clamp-2">
                            High quality Heavy Cotton 280gsm, Plastisol High-density print, deadline 10 days production lead time.
                        </p>
                    </div>

                    <div class="mt-6 pt-4 border-t border-zinc-800 space-y-3">
                        <div class="flex justify-between text-xs">
                            <span class="text-zinc-500">Target Budget:</span>
                            <span class="text-brand-cyan font-bold font-mono">Rp 75,000,000</span>
                        </div>
                        <button onclick="openProposalModal('2,000 Pcs Tech Summit Official Hoodie & Polo')" class="w-full bg-zinc-800 hover:bg-brand-cyan hover:text-black text-zinc-200 text-xs font-bold py-2.5 rounded-xl transition">
                            Submit Proposal / Bid
                        </button>
                    </div>
                </div>

                <!-- RFP Card 3 -->
                <div class="bg-brand-card p-6 rounded-2xl border border-brand-border flex flex-col justify-between hover:border-brand-orange/40 transition">
                    <div>
                        <div class="flex justify-between items-start mb-3">
                            <span class="bg-purple-500/10 text-purple-400 border border-purple-500/30 text-[10px] font-bold uppercase px-2.5 py-0.5 rounded-full">
                                SIS Translation
                            </span>
                            <span class="text-[11px] text-zinc-500"><i class="fa-regular fa-clock"></i> 1 Day Left</span>
                        </div>
                        <h3 class="font-bold text-base text-white">Simultaneous Interpreter System (3 Languages)</h3>
                        <p class="text-xs text-zinc-400 mt-2 line-clamp-2">
                            Asean Energy Conference at Ritz Carlton. Needs 200 Wireless Receiver headsets, 3 Booths, and certified Japanese/Mandarin interpreters.
                        </p>
                    </div>

                    <div class="mt-6 pt-4 border-t border-zinc-800 space-y-3">
                        <div class="flex justify-between text-xs">
                            <span class="text-zinc-500">Target Budget:</span>
                            <span class="text-brand-cyan font-bold font-mono">Rp 35,000,000</span>
                        </div>
                        <button onclick="openProposalModal('Simultaneous Interpreter System (3 Languages)')" class="w-full bg-zinc-800 hover:bg-brand-orange hover:text-white text-zinc-200 text-xs font-bold py-2.5 rounded-xl transition">
                            Submit Proposal / Bid
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- FEATURE 4: SPONSORSHIP MATCHING & FREELANCE CREW RECRUITMENT -->
        <section id="recruitment" class="py-12 bg-zinc-950/80 border-t border-brand-border">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                    
                    <!-- Sponsorship Matching Sub-section -->
                    <div class="bg-brand-card p-6 rounded-2xl border border-brand-border">
                        <div class="flex items-center justify-between mb-6">
                            <div>
                                <span class="text-xs font-bold text-brand-orange uppercase tracking-widest">Brand Activations</span>
                                <h3 class="font-display text-xl font-black text-white uppercase">Sponsorship Opportunities</h3>
                            </div>
                            <span class="text-xs text-brand-cyan font-semibold cursor-pointer hover:underline" onclick="showToast('Sponsorship matching portal active!')">View All</span>
                        </div>

                        <div class="space-y-4">
                            <!-- Sponsor item 1 -->
                            <div class="bg-zinc-900/80 p-4 rounded-xl border border-zinc-800 flex items-center justify-between">
                                <div class="flex items-center gap-3">
                                    <div class="w-10 h-10 rounded-lg bg-zinc-800 flex items-center justify-center text-brand-cyan font-bold text-lg">
                                        F
                                    </div>
                                    <div>
                                        <h4 class="text-xs font-bold text-white">FintechX App Launch</h4>
                                        <p class="text-[11px] text-zinc-400">Looking for Gen-Z Music Festivals (5k+ audience)</p>
                                    </div>
                                </div>
                                <span class="text-xs font-bold text-brand-orange bg-brand-orange/10 px-2.5 py-1 rounded-lg">Up to Rp 50M</span>
                            </div>

                            <!-- Sponsor item 2 -->
                            <div class="bg-zinc-900/80 p-4 rounded-xl border border-zinc-800 flex items-center justify-between">
                                <div class="flex items-center gap-3">
                                    <div class="w-10 h-10 rounded-lg bg-zinc-800 flex items-center justify-center text-brand-orange font-bold text-lg">
                                        E
                                    </div>
                                    <div>
                                        <h4 class="text-xs font-bold text-white">EnergyDrink Official Sponsor</h4>
                                        <p class="text-[11px] text-zinc-400">Exclusive beverage partner for outdoor sports & EDM events</p>
                                    </div>
                                </div>
                                <span class="text-xs font-bold text-brand-orange bg-brand-orange/10 px-2.5 py-1 rounded-lg">Product + Cash</span>
                            </div>
                        </div>
                    </div>

                    <!-- Freelance Technical Crew Recruitment Sub-section -->
                    <div class="bg-brand-card p-6 rounded-2xl border border-brand-border">
                        <div class="flex items-center justify-between mb-6">
                            <div>
                                <span class="text-xs font-bold text-brand-cyan uppercase tracking-widest">Rapid Workforce</span>
                                <h3 class="font-display text-xl font-black text-white uppercase">Freelance Crew Board</h3>
                            </div>
                            <span class="text-xs text-brand-orange font-semibold cursor-pointer hover:underline" onclick="showToast('Hire verified crew members!')">Hire Now</span>
                        </div>

                        <div class="space-y-4">
                            <!-- Crew item 1 -->
                            <div class="bg-zinc-900/80 p-4 rounded-xl border border-zinc-800 flex items-center justify-between">
                                <div class="flex items-center gap-3">
                                    <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?q=80&w=200&auto=format&fit=crop" class="w-10 h-10 rounded-full object-cover border border-brand-cyan">
                                    <div>
                                        <h4 class="text-xs font-bold text-white flex items-center gap-1.5">
                                            Rian Hidayat <i class="fa-solid fa-circle-check text-brand-cyan text-[10px]"></i>
                                        </h4>
                                        <p class="text-[11px] text-zinc-400">Senior Sound Systems Engineer (FOH Operator)</p>
                                    </div>
                                </div>
                                <button onclick="hireCrew('Rian Hidayat')" class="text-xs bg-zinc-800 hover:bg-brand-cyan hover:text-black font-bold px-3 py-1.5 rounded-lg transition">
                                    Book Crew
                                </button>
                            </div>

                            <!-- Crew item 2 -->
                            <div class="bg-zinc-900/80 p-4 rounded-xl border border-zinc-800 flex items-center justify-between">
                                <div class="flex items-center gap-3">
                                    <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w=200&auto=format&fit=crop" class="w-10 h-10 rounded-full object-cover border border-brand-orange">
                                    <div>
                                        <h4 class="text-xs font-bold text-white flex items-center gap-1.5">
                                            Siti Nurhaliza <i class="fa-solid fa-circle-check text-brand-cyan text-[10px]"></i>
                                        </h4>
                                        <p class="text-[11px] text-zinc-400">Certified English-Mandarin SIS Translator</p>
                                    </div>
                                </div>
                                <button onclick="hireCrew('Siti Nurhaliza')" class="text-xs bg-zinc-800 hover:bg-brand-orange hover:text-white font-bold px-3 py-1.5 rounded-lg transition">
                                    Book Crew
                                </button>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </section>
    </main>

    <!-- FOOTER -->
    <footer class="bg-zinc-950 border-t border-brand-border py-12 text-zinc-400 text-xs">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-8">
                <div>
                    <div class="flex items-center gap-2 mb-3">
                        <div class="w-6 h-6 bg-brand-orange rounded flex items-center justify-center text-white text-xs font-black">
                            B
                        </div>
                        <span class="font-display font-bold text-white text-base">BEHIND THE SHOW</span>
                    </div>
                    <p class="text-zinc-500 leading-relaxed text-[11px]">
                        The premier digital ecosystem connecting event organizers, vendors, contractors, and crew across Indonesia.
                    </p>
                </div>

                <div>
                    <h4 class="text-white font-bold mb-3 uppercase tracking-wider text-[11px]">Core Features</h4>
                    <ul class="space-y-2">
                        <li><a href="#directory" class="hover:text-white transition">Smart Geolocation Directory</a></li>
                        <li><a href="#rab-calculator" class="hover:text-white transition">Custom RAB Budget Calculator</a></li>
                        <li><a href="#open-tender" class="hover:text-white transition">Open Tender (RFP) Bidding</a></li>
                        <li><a href="#recruitment" class="hover:text-white transition">Crew & Sponsorship Hub</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="text-white font-bold mb-3 uppercase tracking-wider text-[11px]">Ecosystem Partners</h4>
                    <ul class="space-y-2">
                        <li><a href="https://loket.com" class="hover:text-brand-cyan transition">LOKET (loket.com)</a></li>
                        <li><a href="#" class="hover:text-white transition">Audio Visual Lighting Guild</a></li>
                        <li><a href="#" class="hover:text-white transition">Indonesian Event Contractor Assoc.</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="text-white font-bold mb-3 uppercase tracking-wider text-[11px]">Contact & Support</h4>
                    <p class="text-zinc-500">Jakarta, Indonesia</p>
                    <p class="text-zinc-500 mt-1">support@behindtheshow.id</p>
                    <div class="flex items-center gap-3 mt-3 text-sm">
                        <a href="#" class="w-8 h-8 rounded-lg bg-zinc-900 flex items-center justify-center hover:text-brand-cyan"><i class="fa-brands fa-instagram"></i></a>
                        <a href="#" class="w-8 h-8 rounded-lg bg-zinc-900 flex items-center justify-center hover:text-brand-orange"><i class="fa-brands fa-linkedin"></i></a>
                        <a href="#" class="w-8 h-8 rounded-lg bg-zinc-900 flex items-center justify-center hover:text-brand-cyan"><i class="fa-brands fa-whatsapp"></i></a>
                    </div>
                </div>
            </div>

            <div class="pt-8 border-t border-zinc-900 flex flex-col sm:flex-row justify-between items-center text-[11px] text-zinc-600 gap-2">
                <p>&copy; 2026 behindtheshow.id. All rights reserved.</p>
                <div class="flex gap-4">
                    <a href="#" class="hover:underline">Privacy Policy</a>
                    <a href="#" class="hover:underline">Terms of Ecosystem Service</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- INTERACTIVE MODALS -->

    <!-- Modal 1: Vendor Quotation Modal -->
    <div id="vendorModal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-md flex items-center justify-center p-4">
        <div class="bg-brand-card border border-brand-border rounded-2xl max-w-lg w-full p-6 relative">
            <button onclick="closeModal('vendorModal')" class="absolute top-4 right-4 text-zinc-400 hover:text-white">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            <div id="vendorModalContent">
                <!-- Injected via JS -->
            </div>
        </div>
    </div>

    <!-- Modal 2: Submit RFP Pitch Modal -->
    <div id="rfpModal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-md flex items-center justify-center p-4">
        <div class="bg-brand-card border border-brand-border rounded-2xl max-w-lg w-full p-6 relative">
            <button onclick="closeModal('rfpModal')" class="absolute top-4 right-4 text-zinc-400 hover:text-white">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            <h3 id="rfpModalTitle" class="font-display text-lg font-bold text-white uppercase mb-4">Post New Event RFP</h3>
            
            <form onsubmit="handleRFPSubmit(event)" class="space-y-4">
                <div>
                    <label class="block text-xs text-zinc-400 mb-1">Project / Event Title</label>
                    <input type="text" id="rfpTitleInput" required placeholder="e.g. Stage Sound System 20,000 W" class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl p-3 focus:outline-none focus:border-brand-orange">
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs text-zinc-400 mb-1">Target Budget (IDR)</label>
                        <input type="number" required placeholder="50000000" class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl p-3 focus:outline-none focus:border-brand-orange">
                    </div>
                    <div>
                        <label class="block text-xs text-zinc-400 mb-1">Category</label>
                        <select class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl p-3">
                            <option>Audio Visual Lighting (AVL)</option>
                            <option>Stage & Rigging</option>
                            <option>Konveksi / Apparel Merch</option>
                            <option>SIS Translator</option>
                        </select>
                    </div>
                </div>
                <div>
                    <label class="block text-xs text-zinc-400 mb-1">Technical Requirements & Rider</label>
                    <textarea rows="3" required placeholder="Describe technical specifications required..." class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl p-3 focus:outline-none focus:border-brand-orange"></textarea>
                </div>
                <button type="submit" class="w-full bg-brand-orange hover:bg-brand-orangeDark text-white font-bold text-xs uppercase tracking-wider py-3 rounded-xl transition">
                    Publish RFP Tender To Ecosystem
                </button>
            </form>
        </div>
    </div>

    <!-- Toast Notification Container -->
    <div id="toast" class="fixed bottom-6 right-6 z-50 transform translate-y-20 opacity-0 transition-all duration-300 bg-brand-card border border-brand-cyan text-white px-5 py-3 rounded-xl shadow-2xl flex items-center gap-3">
        <i class="fa-solid fa-circle-check text-brand-cyan text-lg"></i>
        <span id="toastMsg" class="text-xs font-semibold">Notification message</span>
    </div>

    <!-- JAVASCRIPT APP LOGIC -->
    <script>
        // MOCK DATA: VENDORS
        const vendorsData = [
            {
                id: 1,
                name: "SoundNation Pro Audio & Lighting",
                category: "AVL",
                distanceKm: 2.4,
                rating: 4.9,
                reviews: 128,
                pricePerDay: "Rp 15,000,000",
                verified: true,
                image: "https://images.unsplash.com/photo-1470225620780-dba8ba36b745?q=80&w=600&auto=format&fit=crop",
                specs: ["L-Acoustics K2 Line Array", "GrandMA3 Lighting Console", "P2.9 Indoor LED Wall"],
                address: "Kebayoran Baru, Jakarta (2.4 km from GBK)"
            },
            {
                id: 2,
                name: "Lintas Stage & Truss Construction",
                category: "STAGE",
                distanceKm: 4.1,
                rating: 4.8,
                reviews: 95,
                pricePerDay: "Rp 25,000,000",
                verified: true,
                image: "https://images.unsplash.com/photo-1501386761578-eac5c94b800a?q=80&w=600&auto=format&fit=crop",
                specs: ["Aluminum Roof Truss 12x10m", "Hydraulic Stage Height 1.5m", "Safety Load Certified"],
                address: "Palmerah, Jakarta Barat (4.1 km from GBK)"
            },
            {
                id: 3,
                name: "Nusantara Garment & Konveksi",
                category: "KONVEKSI",
                distanceKm: 1.2,
                rating: 4.9,
                reviews: 210,
                pricePerDay: "Rp 45,000 / pcs",
                verified: true,
                image: "https://images.unsplash.com/photo-1556905055-8f358a7a47b2?q=80&w=600&auto=format&fit=crop",
                specs: ["Capacity: 5,000 Pcs/Week", "Heavy Cotton 24s / 30s", "High Density Plastisol Print"],
                address: "Tanah Abang, Jakarta Pusat (1.2 km from GBK)"
            },
            {
                id: 4,
                name: "Global Voice SIS Translator Tech",
                category: "TRANSLATOR",
                distanceKm: 3.5,
                rating: 5.0,
                reviews: 82,
                pricePerDay: "Rp 8,500,000",
                verified: true,
                image: "https://images.unsplash.com/photo-1590650046871-92c887180603?q=80&w=600&auto=format&fit=crop",
                specs: ["Bosch DCN Wireless SIS System", "Audience Receivers (up to 500)", "ISO Soundproof Interpreter Booth"],
                address: "Sudirman, Jakarta Pusat (3.5 km from GBK)"
            },
            {
                id: 5,
                name: "VividFX Laser & LED Display",
                category: "AVL",
                distanceKm: 6.8,
                rating: 4.7,
                reviews: 64,
                pricePerDay: "Rp 12,000,000",
                verified: true,
                image: "https://images.unsplash.com/photo-1516450360452-9312f5e86fc7?q=80&w=600&auto=format&fit=crop",
                specs: ["Outdoor P3.9 Waterproof LED", "30W Full Color RGB Laser", "CO2 Confetti Cannons"],
                address: "Cilandak, Jakarta Selatan (6.8 km from GBK)"
            },
            {
                id: 6,
                name: "CrewX Technical Production Workforce",
                category: "CREW",
                distanceKm: 0.8,
                rating: 4.9,
                reviews: 156,
                pricePerDay: "Rp 500,000 / crew / shift",
                verified: true,
                image: "https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?q=80&w=600&auto=format&fit=crop",
                specs: ["Certified Riggers & Sound Crew", "Stage Hands & Loaders", "Event Operations Management"],
                address: "Senayan, Jakarta Pusat (0.8 km from GBK)"
            }
        ];

        // RENDER VENDOR DIRECTORY
        function renderVendors(data) {
            const grid = document.getElementById('vendorGrid');
            grid.innerHTML = '';

            if(data.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full py-12 text-center text-zinc-500">
                        <i class="fa-solid fa-filter-circle-xmark text-3xl mb-2"></i>
                        <p class="text-xs">No vendors matched your geolocation or category criteria.</p>
                    </div>
                `;
                return;
            }

            data.forEach(v => {
                grid.innerHTML += `
                    <div class="bg-brand-card rounded-2xl overflow-hidden border border-brand-border hover:border-brand-orange/50 transition duration-300 flex flex-col justify-between group">
                        <div>
                            <!-- Vendor Image & Distance Badge -->
                            <div class="relative h-44 overflow-hidden">
                                <img src="${v.image}" alt="${v.name}" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                                <div class="absolute inset-0 bg-gradient-to-t from-brand-card via-transparent to-transparent"></div>
                                <span class="absolute top-3 right-3 bg-black/80 backdrop-blur-md text-brand-cyan text-[10px] font-bold px-2.5 py-1 rounded-full border border-brand-cyan/30 flex items-center gap-1">
                                    <i class="fa-solid fa-location-arrow"></i> ${v.distanceKm} km
                                </span>
                                <span class="absolute bottom-3 left-3 bg-brand-orange text-white text-[10px] font-bold px-2.5 py-0.5 rounded-md uppercase">
                                    ${v.category}
                                </span>
                            </div>

                            <!-- Content -->
                            <div class="p-5">
                                <div class="flex items-center justify-between mb-1">
                                    <h3 class="font-bold text-base text-white group-hover:text-brand-orange transition-colors">${v.name}</h3>
                                    ${v.verified ? '<i class="fa-solid fa-circle-check text-brand-cyan text-sm" title="Verified Ecosystem Vendor"></i>' : ''}
                                </div>
                                <p class="text-[11px] text-zinc-400 mb-3"><i class="fa-solid fa-map-marker-alt text-brand-orange mr-1"></i>${v.address}</p>

                                <!-- Specs list -->
                                <div class="bg-zinc-900/90 rounded-xl p-3 space-y-1.5 border border-zinc-800/80 mb-4">
                                    ${v.specs.map(s => `<div class="text-[11px] text-zinc-300 flex items-center gap-2"><i class="fa-solid fa-check text-brand-cyan text-[9px]"></i> ${s}</div>`).join('')}
                                </div>
                            </div>
                        </div>

                        <!-- Footer Pricing & Action -->
                        <div class="px-5 pb-5 pt-0 flex items-center justify-between border-t border-zinc-800/50 mt-2">
                            <div>
                                <span class="text-[10px] text-zinc-500 block">Rate Est.</span>
                                <span class="text-xs font-bold text-white font-mono">${v.pricePerDay}</span>
                            </div>
                            <button onclick="openVendorDetail(${v.id})" class="bg-zinc-800 hover:bg-brand-orange hover:text-white text-zinc-200 text-xs font-bold px-4 py-2 rounded-xl transition">
                                Request Quote
                            </button>
                        </div>
                    </div>
                `;
            });
        }

        // FILTER VENDORS
        function filterVendors() {
            const search = document.getElementById('vendorSearch').value.toLowerCase();
            const cat = document.getElementById('categoryFilter').value;
            const maxDist = parseFloat(document.getElementById('distanceRange').value);
            const sort = document.getElementById('sortFilter').value;

            let filtered = vendorsData.filter(v => {
                const matchSearch = v.name.toLowerCase().includes(search) || v.specs.some(s => s.toLowerCase().includes(search));
                const matchCat = (cat === 'ALL' || v.category === cat);
                const matchDist = (v.distanceKm <= maxDist);
                return matchSearch && matchCat && matchDist;
            });

            // Sorting
            if(sort === 'PROXIMITY') {
                filtered.sort((a,b) => a.distanceKm - b.distanceKm);
            } else if(sort === 'RATING') {
                filtered.sort((a,b) => b.rating - a.rating);
            }

            renderVendors(filtered);
        }

        function updateDistanceLabel(val) {
            document.getElementById('distanceValue').innerText = val + ' km';
        }

        // SMART RAB CALCULATOR ENGINE
        function calculateRAB() {
            const budget = parseInt(document.getElementById('rabBudgetInput').value);
            const eventType = document.getElementById('rabEventType').value;
            const list = document.getElementById('rabBreakdownList');

            let ratios = {
                avl: 0.35,
                stage: 0.25,
                crew: 0.15,
                merch: 0.15,
                ops: 0.10
            };

            if(eventType === 'SEMINAR') {
                ratios = { avl: 0.25, stage: 0.15, crew: 0.20, merch: 0.10, ops: 0.30 }; // Higher for SIS & Venue
            } else if(eventType === 'BRAND') {
                ratios = { avl: 0.20, stage: 0.35, crew: 0.15, merch: 0.20, ops: 0.10 };
            }

            const items = [
                { name: "Audio Visual & Lighting (AVL)", ratio: ratios.avl, color: "bg-brand-orange" },
                { name: "Stage Construction & Rigging", ratio: ratios.stage, color: "bg-brand-cyan" },
                { name: "Technical Crew & SIS Operators", ratio: ratios.crew, color: "bg-purple-500" },
                { name: "Event Apparel & Merch (Konveksi)", ratio: ratios.merch, color: "bg-emerald-500" },
                { name: "Operational & Contingency", ratio: ratios.ops, color: "bg-zinc-500" }
            ];

            list.innerHTML = '';
            items.forEach(item => {
                const itemCost = Math.round(budget * item.ratio);
                const percentage = Math.round(item.ratio * 100);

                list.innerHTML += `
                    <div>
                        <div class="flex justify-between text-xs mb-1">
                            <span class="text-zinc-300 font-semibold">${item.name} (${percentage}%)</span>
                            <span class="text-white font-mono font-bold">Rp ${itemCost.toLocaleString('id-ID')}</span>
                        </div>
                        <div class="w-full h-2 bg-zinc-900 rounded-full overflow-hidden">
                            <div class="h-full ${item.color}" style="width: ${percentage}%"></div>
                        </div>
                    </div>
                `;
            });

            showToast("RAB Breakdown successfully calculated!");
        }

        function updateRABValue(val) {
            document.getElementById('rabBudgetValue').innerText = 'Rp ' + parseInt(val).toLocaleString('id-ID');
        }

        // MODAL HANDLERS
        function openVendorDetail(id) {
            const vendor = vendorsData.find(v => v.id === id);
            const content = document.getElementById('vendorModalContent');
            
            content.innerHTML = `
                <div class="text-center mb-4">
                    <span class="text-[10px] font-bold text-brand-cyan bg-brand-cyan/10 border border-brand-cyan/30 px-3 py-1 rounded-full uppercase">Direct Inquiry</span>
                    <h3 class="font-display text-xl font-bold text-white uppercase mt-2">${vendor.name}</h3>
                    <p class="text-xs text-zinc-400"><i class="fa-solid fa-map-marker-alt text-brand-orange mr-1"></i>${vendor.address}</p>
                </div>
                <div class="bg-zinc-900 p-4 rounded-xl border border-zinc-800 space-y-2 mb-4 text-xs">
                    <div class="flex justify-between text-zinc-300">
                        <span>Standard Rate:</span>
                        <span class="font-bold text-white font-mono">${vendor.pricePerDay}</span>
                    </div>
                    <div class="flex justify-between text-zinc-300">
                        <span>Distance to GBK Venue:</span>
                        <span class="font-bold text-brand-cyan">${vendor.distanceKm} km</span>
                    </div>
                </div>
                <form onsubmit="submitQuotation(event)" class="space-y-3">
                    <input type="text" required placeholder="Your Event Name / Company" class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl p-3 focus:outline-none focus:border-brand-orange">
                    <input type="date" required class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl p-3 text-zinc-400">
                    <textarea rows="3" required placeholder="Specific technical requirements or questions..." class="w-full bg-zinc-900 border border-zinc-800 text-white text-xs rounded-xl p-3 focus:outline-none focus:border-brand-orange"></textarea>
                    <button type="submit" class="w-full bg-brand-orange hover:bg-brand-orangeDark text-white font-bold text-xs uppercase tracking-wider py-3 rounded-xl transition">
                        Send Quotation Request
                    </button>
                </form>
            `;
            document.getElementById('vendorModal').classList.remove('hidden');
        }

        function openRFPModal() {
            document.getElementById('rfpModal').classList.remove('hidden');
        }

        function openProposalModal(title) {
            document.getElementById('rfpModalTitle').innerText = 'Submit Pitch for: ' + title;
            document.getElementById('rfpModal').classList.remove('hidden');
        }

        function closeModal(id) {
            document.getElementById(id).classList.add('hidden');
        }

        function submitQuotation(e) {
            e.preventDefault();
            closeModal('vendorModal');
            showToast("Quotation request sent to vendor!");
        }

        function handleRFPSubmit(e) {
            e.preventDefault();
            closeModal('rfpModal');
            showToast("RFP Proposal successfully submitted to Ecosystem!");
        }

        function triggerTicketModal(title) {
            showToast("Redirecting to LOKET ticketing for " + title + "...");
        }

        function exportRAB() {
            showToast("RAB details copied to clipboard!");
        }

        function hireCrew(name) {
            showToast("Booking request initiated for " + name);
        }

        // TOAST SYSTEM
        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toastMsg').innerText = msg;
            toast.classList.remove('translate-y-20', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3500);
        }

        // MOBILE MENU
        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        }

        // THEME TOGGLE (LIGHT / DARK HIGH CONTRAST)
        let isDark = true;
        function toggleTheme() {
            isDark = !isDark;
            const icon = document.getElementById('themeIcon');
            if(isDark) {
                document.documentElement.classList.add('dark');
                icon.className = 'fa-solid fa-sun';
            } else {
                document.documentElement.classList.remove('dark');
                icon.className = 'fa-solid fa-moon';
            }
        }

        // INITIALIZE ON LOAD
        window.onload = function() {
            renderVendors(vendorsData);
            calculateRAB();
        };
    </script>
</body>
</html>
