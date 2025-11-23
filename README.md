<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LookAfter | Automation Systems for Business</title>
    <meta name="description" content="I build revenue-generating automation systems. Stop doing robot work.">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">

    <!-- Custom Configuration for Tailwind -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            dark: '#0f172a',
                            primary: '#3b82f6', // Blue
                            accent: '#8b5cf6',  // Purple
                            light: '#f8fafc'
                        }
                    },
                    animation: {
                        'float': 'float 6s ease-in-out infinite',
                        'blob': 'blob 10s infinite',
                    },
                    keyframes: {
                        float: {
                            '0%, 100%': { transform: 'translateY(0)' },
                            '50%': { transform: 'translateY(-10px)' },
                        },
                        blob: {
                            '0%': { transform: 'translate(0px, 0px) scale(1)' },
                            '33%': { transform: 'translate(30px, -50px) scale(1.1)' },
                            '66%': { transform: 'translate(-20px, 20px) scale(0.9)' },
                            '100%': { transform: 'translate(0px, 0px) scale(1)' },
                        }
                    }
                }
            }
        }
    </script>

    <style>
        /* Custom Utilities */
        .glass-card {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .gradient-text {
            background: linear-gradient(to right, #3b82f6, #8b5cf6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Reveal Animation Class */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease-out;
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Noise Texture Overlay */
        .bg-noise {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            opacity: 0.06; 
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
        }
        
        /* Pricing Card Hover Effect */
        .pricing-card:hover {
            transform: translateY(-8px);
            border-color: rgba(59, 130, 246, 0.5);
            box-shadow: 0 20px 40px -15px rgba(59, 130, 246, 0.2);
        }

        /* Animation Delays for Blobs */
        .animation-delay-2000 { animation-delay: 2s; }
        .animation-delay-4000 { animation-delay: 4s; }
        .animation-delay-6000 { animation-delay: 6s; }
        
        /* Will change for performance */
        .will-change-transform { will-change: transform; }
    </style>
</head>
<body class="text-slate-300 font-sans overflow-x-hidden relative">

    <!-- Background Effects (Heatmap Optimized) -->
    <div class="fixed inset-0 -z-50 bg-[#0f172a]"></div> <!-- Solid dark base -->
    
    <!-- Moving Heatmap Blobs (Optimized with will-change-transform) -->
    <div class="fixed inset-0 -z-40 overflow-hidden pointer-events-none">
        <div class="absolute top-[-10%] left-[-10%] w-[600px] h-[600px] bg-indigo-600/20 rounded-full mix-blend-screen filter blur-[100px] opacity-30 animate-blob will-change-transform"></div>
        <div class="absolute top-[10%] right-[-10%] w-[500px] h-[500px] bg-blue-700/20 rounded-full mix-blend-screen filter blur-[80px] opacity-30 animate-blob animation-delay-2000 will-change-transform"></div>
        <div class="absolute bottom-[-10%] left-[10%] w-[600px] h-[600px] bg-violet-600/20 rounded-full mix-blend-screen filter blur-[90px] opacity-30 animate-blob animation-delay-4000 will-change-transform"></div>
        <div class="absolute bottom-[20%] right-[-5%] w-[400px] h-[400px] bg-blue-500/20 rounded-full mix-blend-screen filter blur-[80px] opacity-30 animate-blob animation-delay-2000 will-change-transform"></div>
        <div class="absolute top-[40%] left-[30%] w-[500px] h-[500px] bg-purple-800/20 rounded-full mix-blend-screen filter blur-[100px] opacity-20 animate-blob animation-delay-6000 will-change-transform"></div>
        <div class="absolute top-[60%] left-[-5%] w-[300px] h-[300px] bg-sky-600/10 rounded-full mix-blend-screen filter blur-[60px] opacity-30 animate-blob animation-delay-4000 will-change-transform"></div>
    </div>
    
    <div class="bg-noise"></div>

    <!-- Navigation -->
    <nav class="fixed w-full z-50 top-0 pt-6 transition-transform duration-300 pointer-events-none" id="navbar">
        <div class="container mx-auto px-4">
            <div class="pointer-events-auto max-w-5xl mx-auto bg-slate-900/90 backdrop-blur-md border border-slate-800 rounded-full shadow-2xl px-6 py-3 flex justify-between items-center transform transition-all duration-300 hover:scale-[1.01]">
                <a href="#" class="text-2xl font-bold text-white tracking-tighter">
                    Look<span class="text-brand-primary">After</span>.
                </a>
                
                <!-- Desktop Menu -->
                <div class="hidden md:flex space-x-6 items-center text-sm font-medium">
                    <a href="#process" class="hover:text-white transition-colors">Process</a>
                    <a href="#pricing" class="hover:text-white transition-colors">Pricing</a>
                    <a href="#case-studies" class="hover:text-white transition-colors">Case Studies</a>
                    <a href="#faq" class="hover:text-white transition-colors">FAQ</a>
                    <a href="#audit" class="px-5 py-2 bg-brand-primary hover:bg-blue-600 text-white rounded-full font-medium transition-all transform hover:scale-105 ml-2 shadow-lg shadow-brand-primary/20">
                        Book Audit
                    </a>
                </div>

                <!-- Mobile Button -->
                <button id="mobile-menu-btn" class="md:hidden text-white text-xl focus:outline-none px-2">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Menu (Floating below) -->
        <div id="mobile-menu" class="hidden md:hidden pointer-events-auto max-w-5xl mx-auto px-4 mt-2">
            <div class="bg-slate-900/95 backdrop-blur-xl border border-slate-800 rounded-2xl shadow-2xl overflow-hidden">
                <div class="flex flex-col px-6 py-6 space-y-4 text-center">
                    <a href="#process" class="mobile-link text-slate-300 hover:text-white font-medium py-2">Process</a>
                    <a href="#pricing" class="mobile-link text-slate-300 hover:text-white font-medium py-2">Pricing</a>
                    <a href="#case-studies" class="mobile-link text-slate-300 hover:text-white font-medium py-2">Case Studies</a>
                    <a href="#faq" class="mobile-link text-slate-300 hover:text-white font-medium py-2">FAQ</a>
                    <a href="#audit" class="mobile-link text-brand-primary font-bold py-2">Book Audit</a>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section with INTERACTIVE DEMO -->
    <section id="home" class="min-h-screen flex items-center justify-center pt-20 relative overflow-hidden">
        <!-- Changed: Added max-w-7xl to constrain width and create better centering -->
        <div class="container max-w-7xl mx-auto px-6 grid md:grid-cols-2 gap-12 items-center">
            
            <!-- Text Content -->
            <!-- Changed: Added text-center to align text in the middle -->
            <div class="space-y-6 z-10 reveal active text-center">
                <div class="inline-block px-4 py-1 rounded-full bg-slate-800/50 border border-slate-700 text-sm font-medium text-brand-primary mb-2 backdrop-blur-sm">
                    Taking New Clients for Oct/Nov
                </div>
                <h1 class="text-5xl md:text-7xl font-extrabold text-white leading-tight">
                    I Build Systems That <br>
                    <span class="gradient-text">Generate Revenue</span> <br>
                    While You Sleep.
                </h1>
                <p class="text-lg text-slate-400 max-w-lg mx-auto">
                    Stop doing robot work. I analyze your manual workflows and build custom AI-powered automation systems to handle them for you.
                </p>
                <!-- Changed: Added justify-center to align buttons in the middle -->
                <div class="flex flex-col sm:flex-row gap-4 pt-4 justify-center">
                    <a href="#case-studies" class="px-8 py-4 bg-white text-brand-dark font-bold rounded-lg hover:bg-slate-200 transition-colors text-center shadow-lg shadow-white/10">
                        See How It Works
                    </a>
                    <a href="#audit" class="px-8 py-4 border border-slate-600 text-white font-medium rounded-lg hover:border-brand-primary hover:text-brand-primary transition-colors text-center bg-slate-900/30 backdrop-blur-sm">
                        Book 15-Min Audit
                    </a>
                </div>
            </div>

            <!-- INTERACTIVE DEMO WIDGET (Gemini Powered) -->
            <div class="relative z-10 w-full">
                <div class="w-full max-w-xl mx-auto glass-card rounded-xl overflow-hidden shadow-2xl shadow-brand-primary/10 border border-slate-700">
                    <!-- Window Header -->
                    <div class="flex items-center justify-between px-4 py-3 border-b border-slate-700 bg-slate-800/50">
                        <div class="flex space-x-2">
                            <div class="w-3 h-3 rounded-full bg-red-500/80"></div>
                            <div class="w-3 h-3 rounded-full bg-yellow-500/80"></div>
                            <div class="w-3 h-3 rounded-full bg-green-500/80"></div>
                        </div>
                        <div class="text-xs font-mono text-slate-400">gemini_agent.py</div>
                    </div>
                    
                    <!-- Demo Body -->
                    <div class="p-6 space-y-4">
                        <div class="space-y-2">
                            <label class="text-xs font-bold text-slate-400 uppercase tracking-wider">Select Task</label>
                            <div class="relative">
                                <select id="demo-select" class="w-full bg-slate-900 border border-slate-700 text-slate-300 text-sm rounded-lg p-3 appearance-none focus:border-brand-primary focus:ring-1 focus:ring-brand-primary outline-none transition-all cursor-pointer">
                                    <option value="sales">Generate Sales Script</option>
                                    <option value="invoice">Extract Invoice Data</option>
                                    <option value="sitemap">Create Website Sitemap</option>
                                </select>
                                <div class="absolute right-3 top-1/2 -translate-y-1/2 pointer-events-none text-slate-500">
                                    <i class="fas fa-chevron-down text-xs"></i>
                                </div>
                            </div>
                        </div>

                        <button id="run-demo-btn" class="w-full py-3 bg-gradient-to-r from-brand-primary to-brand-accent hover:opacity-90 text-white font-bold rounded-lg transition-all flex items-center justify-center gap-2 shadow-lg shadow-brand-primary/20">
                            <i class="fas fa-play text-xs"></i> <span id="demo-btn-text">Run Automation</span>
                        </button>

                        <div class="relative mt-4 group">
                            <div class="absolute -inset-0.5 bg-gradient-to-r from-brand-primary/20 to-brand-accent/20 rounded-lg blur opacity-75 transition duration-1000"></div>
                            <div class="relative h-48 bg-slate-900 rounded-lg p-4 font-mono text-xs md:text-sm text-brand-primary overflow-auto border border-slate-700" id="demo-output">
                                <p class="text-slate-600">Waiting for input... Select a task above.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Tech Stack / Tools Section -->
    <section class="py-12 border-y border-slate-800 bg-slate-900/50">
        <div class="container mx-auto px-6 text-center">
            <p class="text-xs uppercase tracking-widest text-slate-500 mb-8">I connect to the tools you already use</p>
            <!-- Removed grayscale, added permanent colors and float animation -->
            <div class="flex flex-wrap justify-center gap-8 md:gap-12 transition-all duration-500">
                <div class="flex flex-col items-center gap-2 text-orange-500 animate-float" style="animation-delay: 0s;"><i class="fab fa-hubspot text-3xl drop-shadow-[0_0_10px_rgba(249,115,22,0.3)]"></i><span class="text-xs font-bold text-slate-400">HubSpot</span></div>
                <div class="flex flex-col items-center gap-2 text-blue-500 animate-float" style="animation-delay: 0.5s;"><i class="fab fa-salesforce text-3xl drop-shadow-[0_0_10px_rgba(59,130,246,0.3)]"></i><span class="text-xs font-bold text-slate-400">Salesforce</span></div>
                <div class="flex flex-col items-center gap-2 text-purple-500 animate-float" style="animation-delay: 1s;"><i class="fab fa-slack text-3xl drop-shadow-[0_0_10px_rgba(168,85,247,0.3)]"></i><span class="text-xs font-bold text-slate-400">Slack</span></div>
                <div class="flex flex-col items-center gap-2 text-indigo-400 animate-float" style="animation-delay: 1.5s;"><i class="fab fa-stripe text-3xl drop-shadow-[0_0_10px_rgba(129,140,248,0.3)]"></i><span class="text-xs font-bold text-slate-400">Stripe</span></div>
                <div class="flex flex-col items-center gap-2 text-green-500 animate-float" style="animation-delay: 2s;"><i class="fab fa-google text-3xl drop-shadow-[0_0_10px_rgba(34,197,94,0.3)]"></i><span class="text-xs font-bold text-slate-400">Gmail</span></div>
                <div class="flex flex-col items-center gap-2 text-blue-600 animate-float" style="animation-delay: 2.5s;"><i class="fab fa-microsoft text-3xl drop-shadow-[0_0_10px_rgba(37,99,235,0.3)]"></i><span class="text-xs font-bold text-slate-400">Outlook</span></div>
                <div class="flex flex-col items-center gap-2 text-teal-400 animate-float" style="animation-delay: 3s;"><i class="fas fa-robot text-3xl drop-shadow-[0_0_10px_rgba(45,212,191,0.3)]"></i><span class="text-xs font-bold text-slate-400">OpenAI</span></div>
                <div class="flex flex-col items-center gap-2 text-yellow-400 animate-float" style="animation-delay: 3.5s;"><i class="fas fa-database text-3xl drop-shadow-[0_0_10px_rgba(250,204,21,0.3)]"></i><span class="text-xs font-bold text-slate-400">Airtable</span></div>
                <div class="flex flex-col items-center gap-2 text-white animate-float" style="animation-delay: 4s;"><i class="fas fa-cube text-3xl drop-shadow-[0_0_10px_rgba(255,255,255,0.3)]"></i><span class="text-xs font-bold text-slate-400">Notion</span></div>
            </div>
        </div>
    </section>

    <!-- Process Section -->
    <section id="process" class="py-24 relative">
        <div class="container mx-auto px-6">
            <div class="mb-16 text-center reveal">
                <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">How We Work</h2>
                <p class="text-slate-400">Automation isn't magic. It's a proven engineering process.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-4 gap-8 relative">
                <div class="hidden md:block absolute top-1/3 left-0 w-full h-0.5 bg-slate-800 -z-10"></div>

                <div class="reveal bg-slate-900/80 p-6 rounded-xl border border-slate-800 hover:border-brand-primary transition-colors text-center">
                    <div class="w-16 h-16 mx-auto bg-slate-800 rounded-full flex items-center justify-center text-brand-primary font-bold text-xl border border-slate-700 mb-4 shadow-lg">1</div>
                    <h4 class="text-lg font-bold text-white mb-2">Audit</h4>
                    <p class="text-sm text-slate-400">I analyze your current manual workflow to find the bottlenecks and wasted hours.</p>
                </div>
                
                <div class="reveal bg-slate-900/80 p-6 rounded-xl border border-slate-800 hover:border-brand-primary transition-colors text-center" style="transition-delay: 100ms;">
                    <div class="w-16 h-16 mx-auto bg-slate-800 rounded-full flex items-center justify-center text-brand-primary font-bold text-xl border border-slate-700 mb-4 shadow-lg">2</div>
                    <h4 class="text-lg font-bold text-white mb-2">Map</h4>
                    <p class="text-sm text-slate-400">I design the logic diagram (The Blueprint) for your approval before writing a single line of code.</p>
                </div>
                
                <div class="reveal bg-slate-900/80 p-6 rounded-xl border border-slate-800 hover:border-brand-primary transition-colors text-center" style="transition-delay: 200ms;">
                    <div class="w-16 h-16 mx-auto bg-slate-800 rounded-full flex items-center justify-center text-brand-primary font-bold text-xl border border-slate-700 mb-4 shadow-lg">3</div>
                    <h4 class="text-lg font-bold text-white mb-2">Build</h4>
                    <p class="text-sm text-slate-400">I build the automation in n8n/Python and rigorously test it with dummy data to ensure stability.</p>
                </div>
                
                <div class="reveal bg-slate-900/80 p-6 rounded-xl border border-slate-800 hover:border-brand-primary transition-colors text-center" style="transition-delay: 300ms;">
                    <div class="w-16 h-16 mx-auto bg-brand-primary rounded-full flex items-center justify-center text-white font-bold text-xl shadow-lg shadow-blue-500/50 mb-4">4</div>
                    <h4 class="text-lg font-bold text-white mb-2">Handover</h4>
                    <p class="text-sm text-slate-400">I give you the keys, a training video, and 30 days of support. You own the system.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section id="pricing" class="py-24 bg-slate-900/30">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16 reveal">
                <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">Transparent Packages</h2>
                <p class="text-slate-400">Productized services with clear deliverables. No surprises.</p>
            </div>

            <div class="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">
                <!-- Starter -->
                <div class="glass-card p-8 rounded-2xl pricing-card transition-all duration-300 reveal flex flex-col">
                    <div class="text-cyan-400 font-bold tracking-wider text-sm uppercase mb-2">Starter</div>
                    <h3 class="text-2xl font-bold text-white mb-4">The Quick Fix</h3>
                    <div class="text-4xl font-bold text-white mb-6">$500 <span class="text-lg text-slate-400 font-normal">/ one-time</span></div>
                    <p class="text-slate-300 text-sm mb-8 flex-grow">Perfect for fixing one specific broken process or connecting two apps.</p>
                    <ul class="space-y-4 mb-8 text-sm text-slate-300">
                        <li class="flex items-start gap-3"><i class="fas fa-check text-cyan-400 mt-1"></i> One simple Zapier/n8n workflow</li>
                        <li class="flex items-start gap-3"><i class="fas fa-check text-cyan-400 mt-1"></i> Up to 3 steps</li>
                        <li class="flex items-start gap-3"><i class="fas fa-check text-cyan-400 mt-1"></i> 48-hour turnaround</li>
                    </ul>
                    <a href="#audit" class="block w-full py-3 text-center bg-gradient-to-r from-cyan-500 to-blue-500 rounded-lg hover:opacity-90 text-white font-bold transition-all shadow-lg shadow-cyan-500/20">Book This</a>
                </div>

                <!-- Growth -->
                <div class="glass-card p-8 rounded-2xl pricing-card transition-all duration-300 reveal border-brand-primary bg-slate-800/40 relative transform md:-translate-y-4 flex flex-col">
                    <div class="absolute top-0 left-1/2 -translate-x-1/2 bg-brand-primary text-white text-xs font-bold px-3 py-1 rounded-b-lg">MOST POPULAR</div>
                    <div class="text-brand-accent font-bold tracking-wider text-sm uppercase mb-2">Growth</div>
                    <h3 class="text-2xl font-bold text-white mb-4">The Lead Machine</h3>
                    <div class="text-4xl font-bold text-white mb-6">$1,500 <span class="text-lg text-slate-400 font-normal">/ project</span></div>
                    <p class="text-slate-300 text-sm mb-8 flex-grow">The exact Google Maps -> AI -> CRM system shown in my case studies.</p>
                    <ul class="space-y-4 mb-8 text-sm text-slate-300">
                        <li class="flex items-start gap-3"><i class="fas fa-check text-brand-accent mt-1"></i> Full Lead Gen System</li>
                        <li class="flex items-start gap-3"><i class="fas fa-check text-brand-accent mt-1"></i> Data Scraping & Enrichment</li>
                        <li class="flex items-start gap-3"><i class="fas fa-check text-brand-accent mt-1"></i> AI Email Personalization</li>
                        <li class="flex items-start gap-3"><i class="fas fa-check text-brand-accent mt-1"></i> CRM Integration</li>
                    </ul>
                    <a href="#audit" class="block w-full py-3 text-center bg-gradient-to-r from-brand-primary to-brand-accent rounded-lg hover:opacity-90 text-white font-bold transition-all shadow-lg shadow-brand-primary/20">Get The Machine</a>
                </div>

                <!-- Custom -->
                <div class="glass-card p-8 rounded-2xl pricing-card transition-all duration-300 reveal flex flex-col">
                    <div class="text-pink-400 font-bold tracking-wider text-sm uppercase mb-2">Enterprise</div>
                    <h3 class="text-2xl font-bold text-white mb-4">Custom Build</h3>
                    <div class="text-4xl font-bold text-white mb-6">$3k+ <span class="text-lg text-slate-400 font-normal">/ starts at</span></div>
                    <p class="text-slate-300 text-sm mb-8 flex-grow">Full operations audit and complex multi-step automation architecture.</p>
                    <ul class="space-y-4 mb-8 text-sm text-slate-300">
                        <li class="flex items-start gap-3"><i class="fas fa-check text-pink-400 mt-1"></i> Full Business Workflow Audit</li>
                        <li class="flex items-start gap-3"><i class="fas fa-check text-pink-400 mt-1"></i> Custom API Integrations</li>
                        <li class="flex items-start gap-3"><i class="fas fa-check text-pink-400 mt-1"></i> Dedicated Support Channel</li>
                    </ul>
                    <a href="#audit" class="block w-full py-3 text-center bg-gradient-to-r from-purple-500 to-pink-500 rounded-lg hover:opacity-90 text-white font-bold transition-all shadow-lg shadow-pink-500/20">Talk to Me</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Case Studies Section -->
    <section id="case-studies" class="py-24 relative">
        <div class="container mx-auto px-6">
            <div class="mb-16 reveal">
                <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">The Evidence</h2>
                <p class="text-slate-400">I don't just use tools. I build revenue-generating systems.</p>
            </div>

            <!-- Featured Case Study: Lead Gen -->
            <div class="glass-card rounded-2xl border border-slate-700 overflow-hidden mb-16 reveal">
                <div class="grid lg:grid-cols-2">
                    <!-- Content Side -->
                    <div class="p-8 md:p-12 flex flex-col justify-center">
                        <div class="inline-block px-3 py-1 rounded bg-brand-accent/20 text-brand-accent text-xs font-bold tracking-widest mb-4 w-max">AUTOMATION SYSTEM</div>
                        <h3 class="text-3xl font-bold text-white mb-2">AI-Powered Lead Generation Engine</h3>
                        <p class="text-slate-400 mb-8">Automating the extraction, enrichment, and personalization of cold leads using n8n & OpenAI.</p>
                        
                        <div class="space-y-8">
                            <div>
                                <h4 class="text-white font-bold mb-2 flex items-center gap-2"><i class="fas fa-exclamation-circle text-red-400"></i> The Challenge (Before)</h4>
                                <p class="text-slate-400 text-sm leading-relaxed">
                                    The client was spending 15+ hours a week manually searching Google Maps for prospects, copying emails into spreadsheets, and writing generic emails that got low response rates.
                                </p>
                            </div>
                            
                            <div>
                                <h4 class="text-white font-bold mb-2 flex items-center gap-2"><i class="fas fa-check-circle text-green-400"></i> The Solution (The Build)</h4>
                                <p class="text-slate-400 text-sm leading-relaxed mb-4">
                                    I architected a fully automated workflow using n8n as the central orchestrator to Scrape, Enrich, and Personalize every lead.
                                </p>
                            </div>

                            <div>
                                <h4 class="text-white font-bold mb-2 flex items-center gap-2"><i class="fas fa-chart-line text-brand-primary"></i> The Results</h4>
                                <div class="grid grid-cols-3 gap-4 text-center">
                                    <div class="bg-slate-800/50 p-3 rounded-lg">
                                        <div class="text-xl font-bold text-white">95%</div>
                                        <div class="text-[10px] text-slate-400 uppercase">Time Saved</div>
                                    </div>
                                    <div class="bg-slate-800/50 p-3 rounded-lg">
                                        <div class="text-xl font-bold text-white">10x</div>
                                        <div class="text-[10px] text-slate-400 uppercase">Lead Volume</div>
                                    </div>
                                    <div class="bg-slate-800/50 p-3 rounded-lg">
                                        <div class="text-xl font-bold text-white">100%</div>
                                        <div class="text-[10px] text-slate-400 uppercase">Clean Data</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Visual Side -->
                    <div class="bg-slate-900/80 border-t lg:border-t-0 lg:border-l border-slate-700 p-8 md:p-12 flex flex-col justify-center relative overflow-hidden">
                        <div class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/cubes.png')] opacity-5"></div>
                        <!-- Abstract Logic Visual -->
                        <div class="relative z-10 bg-slate-800 rounded-xl border border-slate-700 p-6 shadow-2xl">
                            <div class="flex items-center gap-4 mb-6">
                                <div class="w-8 h-8 bg-yellow-500/20 text-yellow-500 rounded flex items-center justify-center"><i class="fas fa-bolt"></i></div>
                                <div class="flex-1 h-1 bg-slate-700 rounded overflow-hidden"><div class="w-full h-full bg-green-500/50 animate-pulse"></div></div>
                                <div class="w-8 h-8 bg-brand-accent/20 text-brand-accent rounded flex items-center justify-center"><i class="fas fa-robot"></i></div>
                                <div class="flex-1 h-1 bg-slate-700 rounded overflow-hidden"><div class="w-full h-full bg-green-500/50 animate-pulse"></div></div>
                                <div class="w-8 h-8 bg-green-500/20 text-green-500 rounded flex items-center justify-center"><i class="fas fa-check"></i></div>
                            </div>
                            <div class="text-xs font-mono text-green-400 space-y-2">
                                <p>> Scraping Google Maps...</p>
                                <p>> Found 50 leads.</p>
                                <p>> Enriching via Apollo API...</p>
                                <p>> Generating AI Icebreakers...</p>
                                <p>> Leads pushed to CRM successfully.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- FAQ Section -->
    <section id="faq" class="py-24 bg-slate-900/30">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16 reveal">
                <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">Frequently Asked Questions</h2>
                <p class="text-slate-400">Addressing your concerns about automation.</p>
            </div>
            
            <div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
                <div class="glass-card p-6 rounded-xl reveal">
                    <h4 class="text-lg font-bold text-white mb-2"><i class="fas fa-question-circle text-brand-primary mr-2"></i> What happens if it breaks?</h4>
                    <p class="text-sm text-slate-400">I build robust error-handlers that alert me instantly if something goes wrong. I also offer a monthly maintenance package to ensure 99.9% uptime.</p>
                </div>
                <div class="glass-card p-6 rounded-xl reveal">
                    <h4 class="text-lg font-bold text-white mb-2"><i class="fas fa-lock text-brand-primary mr-2"></i> Is my data safe?</h4>
                    <p class="text-sm text-slate-400">Yes. I use industry-standard encryption. I never store your customer data on my own servers—it stays securely within your own accounts (HubSpot, Sheets, etc).</p>
                </div>
                <div class="glass-card p-6 rounded-xl reveal">
                    <h4 class="text-lg font-bold text-white mb-2"><i class="fas fa-wallet text-brand-primary mr-2"></i> Do I need to pay for n8n?</h4>
                    <p class="text-sm text-slate-400">Yes, you will own the account so you have full control. It costs roughly $20/month for the cloud version, which is significantly cheaper than one hour of human labor.</p>
                </div>
                <div class="glass-card p-6 rounded-xl reveal">
                    <h4 class="text-lg font-bold text-white mb-2"><i class="fas fa-code text-brand-primary mr-2"></i> Do you offer support?</h4>
                    <p class="text-sm text-slate-400">Every build comes with a 30-day warranty where I fix any bugs for free. After that, you can subscribe to a support retainer or pay hourly for updates.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Audit / Booking Section -->
    <section id="audit" class="py-24 relative">
        <div class="container mx-auto px-6">
            <div class="max-w-4xl mx-auto glass-card p-1 rounded-2xl border border-brand-primary/30 shadow-[0_0_40px_rgba(59,130,246,0.15)] reveal">
                <div class="bg-slate-900 rounded-xl p-6 md:p-12 overflow-hidden">
                    
                    <!-- Booking Header -->
                    <div class="text-center mb-10">
                        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-green-500/10 text-green-400 text-xs font-bold mb-4">
                            <span class="w-2 h-2 rounded-full bg-green-500 animate-pulse"></span> Available for New Projects
                        </div>
                        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">Book a 15-Minute Audit</h2>
                        <p class="text-slate-400">Let's find one manual process we can automate this week.</p>
                    </div>

                    <!-- Simulated Booking Interface -->
                    <div id="booking-ui" class="max-w-2xl mx-auto">
                        <!-- Step 1: Questions -->
                        <form id="audit-form" class="space-y-6">
                            <div class="space-y-2">
                                <label class="text-sm font-bold text-slate-300">1. What is your website?</label>
                                <input type="text" name="website" required placeholder="e.g. www.mybusiness.com" class="w-full bg-slate-800 border border-slate-700 rounded-lg p-3 text-white focus:border-brand-primary focus:outline-none transition-colors">
                            </div>
                            
                            <div class="space-y-2">
                                <label class="text-sm font-bold text-slate-300">2. What manual task do you hate the most?</label>
                                <textarea name="task" required rows="2" placeholder="e.g. Copying leads from email to Excel..." class="w-full bg-slate-800 border border-slate-700 rounded-lg p-3 text-white focus:border-brand-primary focus:outline-none transition-colors"></textarea>
                            </div>

                            <div class="space-y-2">
                                <label class="text-sm font-bold text-slate-300">3. What is your estimated budget?</label>
                                <div class="relative">
                                    <select name="budget" class="w-full bg-slate-800 border border-slate-700 rounded-lg p-3 text-white appearance-none focus:border-brand-primary focus:outline-none transition-colors">
                                        <option value="Less than $500">Less than $500 (Quick Fix)</option>
                                        <option value="$1k - $5k">$1,000 - $5,000 (Standard Project)</option>
                                        <option value="$5k+">$5,000+ (Custom System)</option>
                                    </select>
                                    <div class="absolute right-4 top-1/2 -translate-y-1/2 pointer-events-none text-slate-500"><i class="fas fa-chevron-down"></i></div>
                                </div>
                            </div>
                            
                            <div class="space-y-2">
                                <label class="text-sm font-bold text-slate-300">4. Your Email Address</label>
                                <input type="email" name="email" required placeholder="you@company.com" class="w-full bg-slate-800 border border-slate-700 rounded-lg p-3 text-white focus:border-brand-primary focus:outline-none transition-colors">
                            </div>

                            <button type="submit" class="w-full py-4 bg-brand-primary hover:bg-blue-600 text-white font-bold rounded-lg shadow-lg shadow-brand-primary/25 transition-all transform active:scale-[0.98] flex items-center justify-center gap-3">
                                <i class="fas fa-calendar-alt"></i> Continue to Calendar
                            </button>
                        </form>

                        <!-- Step 2: Fake Calendar (Hidden by default) -->
                        <div id="calendar-view" class="hidden text-center py-8">
                            <div class="w-16 h-16 bg-brand-primary/20 text-brand-primary rounded-full flex items-center justify-center text-3xl mx-auto mb-6">
                                <i class="fas fa-check"></i>
                            </div>
                            <h3 class="text-xl font-bold text-white mb-2">Pre-Qualification Complete</h3>
                            <p class="text-slate-400 text-sm mb-6">Your audit request is ready. Click below to send your details to my system.</p>
                            <button id="final-submit" class="w-full md:w-auto px-8 py-3 bg-white text-slate-900 font-bold rounded-lg hover:bg-slate-200 transition-colors flex items-center justify-center gap-2 mx-auto">
                                <span>Finish Booking</span>
                            </button>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-slate-950 py-12 border-t border-slate-800 text-sm">
        <div class="container mx-auto px-6">
            <!-- Changed: Replaced justify-between with justify-center and added gap-12 to bring elements closer -->
            <div class="flex flex-col md:flex-row justify-center items-center gap-12 mb-8">
                <div class="text-white font-bold text-lg">Look<span class="text-brand-primary">After</span>.</div>
                <div class="flex gap-6">
                    <a href="#" class="text-slate-400 hover:text-white transition-colors"><i class="fab fa-github text-xl"></i></a>
                    <a href="https://www.linkedin.com/in/ravi-chaurasiya-10325b31b/" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-white transition-colors"><i class="fab fa-linkedin text-xl"></i></a>
                    <a href="https://x.com/lookkafter" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-white transition-colors"><i class="fab fa-twitter text-xl"></i></a>
                    <a href="mailto:your-email@gmail.com" class="text-slate-400 hover:text-white transition-colors"><i class="fas fa-envelope text-xl"></i></a>
                </div>
            </div>
            
            <!-- Copyright Section -->
            <div class="flex flex-col md:flex-row justify-center items-center gap-6 border-t border-slate-800 pt-8 text-slate-500 text-xs">
                <div>© 2024 LookAfter. All rights reserved.</div>
                <div class="flex gap-6">
                    <a href="#" class="hover:text-white transition-colors">Privacy Policy</a>
                    <a href="#" class="hover:text-white transition-colors">Terms of Service</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Back to Top Button -->
    <a href="#home" id="back-to-top" class="fixed bottom-8 right-8 bg-brand-primary text-white p-4 rounded-full shadow-lg z-50 transition-all duration-300 opacity-0 translate-y-10 pointer-events-none hover:bg-blue-600">
        <i class="fas fa-arrow-up"></i>
    </a>

    <!-- Interactive Scripts -->
    <script>
        // Mobile Menu Toggle
        const mobileBtn = document.getElementById('mobile-menu-btn');
        const mobileMenu = document.getElementById('mobile-menu');
        const mobileLinks = document.querySelectorAll('.mobile-link');

        mobileBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
            });
        });

        // INTERACTIVE DEMO LOGIC (GEMINI POWERED)
        const runDemoBtn = document.getElementById('run-demo-btn');
        const demoSelect = document.getElementById('demo-select');
        const demoOutput = document.getElementById('demo-output');
        const demoBtnText = document.getElementById('demo-btn-text');
        
        const apiKey = ""; // Provided by environment

        if (runDemoBtn) {
            const scenarios = {
                'sales': `Subject: Quick question about {company}\n\nHi {First_Name},\n\nI noticed you're using HubSpot but haven't automated your lead scoring yet.\n\nI built a workflow that does this automatically. Want to see it?\n\nBest,\nRavi`,
                'invoice': `{\n  "invoice_id": "INV-2024-001",\n  "total": 4500.00,\n  "currency": "USD",\n  "vendor": "AWS Services",\n  "status": "PAID"\n}`,
                'sitemap': `- /home (Priority: 1.0)\n- /services/automation (Priority: 0.9)\n- /case-studies/lead-gen (Priority: 0.8)\n- /contact (Priority: 0.5)`
            };

            const prompts = {
                'sales': "Write a short, high-conversion cold email sales script for a lead named Alex about automating manual data entry. Keep it under 50 words.",
                'invoice': "Extract key data (Invoice ID, Total Amount, Date) from this text into JSON: 'Invoice #9921 from AWS Web Services dated Oct 24, 2024 for $4,500.00 USD paid via credit card.'",
                'sitemap': "Generate a simple 4-page website sitemap (Home, Services, About, Contact) in a tree text structure."
            };

            runDemoBtn.addEventListener('click', async () => {
                const selectedTask = demoSelect.value;
                
                // Loading State
                runDemoBtn.disabled = true;
                runDemoBtn.classList.add('opacity-75', 'cursor-not-allowed');
                demoBtnText.innerText = "AI Processing...";
                demoOutput.innerHTML = `
                    <div class="space-y-1">
                        <p class="animate-pulse text-xs text-brand-primary">> Connecting to Gemini API...</p>
                        <p class="animate-pulse delay-75 text-xs text-brand-primary">> Analyzing Request...</p>
                    </div>
                `;

                try {
                    // Try calling real Gemini API
                    if (apiKey) {
                        const response = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`, {
                            method: 'POST',
                            headers: {
                                'Content-Type': 'application/json'
                            },
                            body: JSON.stringify({
                                contents: [{
                                    parts: [{
                                        text: prompts[selectedTask]
                                    }]
                                }]
                            })
                        });

                        const data = await response.json();
                        const aiText = data.candidates?.[0]?.content?.parts?.[0]?.text || scenarios[selectedTask]; // Fallback if structure differs

                        demoOutput.innerHTML = `
                            <span class="text-slate-500 select-none block mb-2 text-xs">Gemini Output:</span>
                            <pre class="whitespace-pre-wrap font-mono text-brand-primary text-xs md:text-sm">${aiText}</pre>
                        `;
                    } else {
                        // Fallback to mocked data if no API key
                        // Simulated Delay
                        await new Promise(r => setTimeout(r, 1500));
                        demoOutput.innerHTML = `
                            <span class="text-slate-500 select-none block mb-2 text-xs">Simulated Output:</span>
                            <pre class="whitespace-pre-wrap font-mono text-brand-primary text-xs md:text-sm">${scenarios[selectedTask]}</pre>
                        `;
                    }
                } catch (error) {
                    console.error("AI Error", error);
                    demoOutput.innerHTML = `<p class="text-red-400 text-xs">Error connecting to AI agent. Showing cached result:</p><pre class="mt-2 text-brand-primary text-xs">${scenarios[selectedTask]}</pre>`;
                } finally {
                    // Reset Button
                    runDemoBtn.disabled = false;
                    runDemoBtn.classList.remove('opacity-75', 'cursor-not-allowed');
                    demoBtnText.innerText = "Run Automation";
                }
            });
        }

        // Booking UI Logic
        const auditForm = document.getElementById('audit-form');
        const calendarView = document.getElementById('calendar-view');
        const finalSubmit = document.getElementById('final-submit');
        let collectedAuditData = {}; // Store data between steps

        if(auditForm) {
            auditForm.addEventListener('submit', (e) => {
                e.preventDefault();
                
                // 1. Capture Data from Form
                const formData = new FormData(auditForm);
                collectedAuditData = Object.fromEntries(formData.entries());
                
                // 2. Switch UI
                auditForm.classList.add('hidden');
                calendarView.classList.remove('hidden');
            });

            finalSubmit.addEventListener('click', async () => {
                // UI Loading State
                const originalBtnContent = finalSubmit.innerHTML;
                finalSubmit.innerHTML = '<i class="fas fa-circle-notch fa-spin"></i> Sending Request...';
                finalSubmit.disabled = true;
                finalSubmit.classList.add('opacity-75', 'cursor-not-allowed');

                try {
                    // 3. Send to Formspree Webhook
                    await fetch('https://formspree.io/f/xzzwqjpj', {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json',
                            'Accept': 'application/json'
                        },
                        body: JSON.stringify({
                            type: 'Audit Booking Request',
                            ...collectedAuditData,
                            timestamp: new Date().toISOString()
                        })
                    });

                    // 4. Success UI
                    finalSubmit.innerHTML = '<i class="fas fa-check"></i> Request Sent!';
                    finalSubmit.classList.remove('bg-white', 'text-slate-900');
                    finalSubmit.classList.add('bg-green-500', 'text-white');
                    
                    // Reset form after delay
                    setTimeout(() => {
                        calendarView.classList.add('hidden');
                        auditForm.classList.remove('hidden');
                        auditForm.reset();
                        finalSubmit.innerHTML = originalBtnContent;
                        finalSubmit.classList.add('bg-white', 'text-slate-900');
                        finalSubmit.classList.remove('bg-green-500', 'text-white');
                        finalSubmit.disabled = false;
                        finalSubmit.classList.remove('opacity-75', 'cursor-not-allowed');
                    }, 4000);

                } catch (error) {
                    console.error('Error sending booking:', error);
                    finalSubmit.innerHTML = 'Error. Please try again.';
                    setTimeout(() => {
                        finalSubmit.innerHTML = originalBtnContent;
                        finalSubmit.disabled = false;
                        finalSubmit.classList.remove('opacity-75', 'cursor-not-allowed');
                    }, 3000);
                }
            });
        }

        // Scroll Reveal Animation
        const revealElements = document.querySelectorAll('.reveal');

        const revealOnScroll = () => {
            const windowHeight = window.innerHeight;
            const elementVisible = 100;

            revealElements.forEach((reveal) => {
                const elementTop = reveal.getBoundingClientRect().top;
                if (elementTop < windowHeight - elementVisible) {
                    reveal.classList.add('active');
                }
            });
        };

        window.addEventListener('scroll', revealOnScroll);
        revealOnScroll();

        // Smart Navbar & Back-to-Top Logic
        let lastScrollTop = 0;
        const navbar = document.getElementById('navbar');
        const backToTop = document.getElementById('back-to-top');

        window.addEventListener('scroll', () => {
            const scrollTop = window.pageYOffset || document.documentElement.scrollTop;

            // Navbar Logic
            if (scrollTop > lastScrollTop && scrollTop > 100) {
                // Scrolling Down AND past header -> Hide
                navbar.classList.add('-translate-y-full');
            } else {
                // Scrolling Up -> Show
                navbar.classList.remove('-translate-y-full');
            }

            // Back to Top Logic
            if (scrollTop > 500) {
                backToTop.classList.remove('opacity-0', 'translate-y-10', 'pointer-events-none');
                backToTop.classList.add('opacity-100', 'translate-y-0', 'pointer-events-auto');
            } else {
                backToTop.classList.add('opacity-0', 'translate-y-10', 'pointer-events-none');
                backToTop.classList.remove('opacity-100', 'translate-y-0', 'pointer-events-auto');
            }

            lastScrollTop = scrollTop <= 0 ? 0 : scrollTop; // For Mobile or negative scrolling
        });
    </script>
</body>
</html>
