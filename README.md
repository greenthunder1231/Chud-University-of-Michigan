<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chud University of Michigan • Official Homepage</title>
    <meta name="description" content="Chud University of Michigan — excellence in Gooning, Psychology & Digital Governance. Campuses in Climax, Michigan and Oblong, Illinois. Est. 1969.">

    <!-- Open Graph / social preview -->
    <meta property="og:type" content="website">
    <meta property="og:title" content="Chud University of Michigan">
    <meta property="og:description" content="Excellence in Gooning, Psychology & Digital Governance. Ranked #1 by the Gooning Association of America, 2025.">
    <meta property="og:image" content="/assets/chud-university.svg">
    <meta name="twitter:card" content="summary_large_image">

    <link rel="icon" type="image/svg+xml" href="/assets/chud-university-transparent.svg">

    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <link rel="stylesheet" href="/css/styles.css">
</head>
<body class="bg-[#F8FAFC] text-slate-900">
    <!-- Navigation -->
    <nav class="university-nav sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-8">
            <div class="flex items-center justify-between h-20">
                <div class="flex items-center gap-x-4">
                    <div class="w-11 h-11 bg-[#0A0F1C] rounded-2xl flex items-center justify-center shadow-inner ring-1 ring-inset ring-white/10">
                        <span class="text-white text-[22px] font-bold tracking-[-1.75px] font-serif">CUM</span>
                    </div>
                    <div class="leading-none pt-0.5">
                        <div class="font-bold text-[21px] md:text-[23px] tracking-[-1.3px] text-[#0A0F1C]">Chud University</div>
                        <div class="text-[10px] text-slate-500 tracking-[2.2px] font-medium -mt-px">OF MICHIGAN • EST. 1969</div>
                    </div>
                </div>

                <div class="hidden md:flex items-center gap-x-9 text-[14.5px] font-medium">
                    <a href="#about" class="nav-link px-1">About</a>
                    <a href="#academics" class="nav-link px-1">Academics</a>
                    <a href="#campuses" class="nav-link px-1">Campuses</a>
                    <a href="#admissions" class="nav-link px-1">Admissions</a>
                </div>

                <div class="flex items-center gap-x-3">
                    <button onclick="showApplicationModal()"
                            class="hidden md:block px-7 py-[13px] text-[13.5px] font-semibold formal-button rounded-2xl tracking-[-0.2px]">
                        Apply Now
                    </button>
                    <button onclick="toggleMobileMenu()" aria-label="Toggle navigation menu"
                            class="md:hidden w-11 h-11 flex items-center justify-center text-slate-600 hover:text-slate-900 hover:bg-slate-100 rounded-2xl transition-colors">
                        <i id="mobile-menu-icon" class="fa-solid fa-bars text-[21px]"></i>
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Mobile Menu -->
    <div id="mobile-menu" class="hidden md:hidden border-t bg-white">
        <div class="max-w-7xl mx-auto px-8 py-6 flex flex-col gap-y-1 text-[15px] font-medium">
            <a href="#about" onclick="toggleMobileMenu()" class="nav-link py-3 px-1 border-b border-slate-100">About</a>
            <a href="#academics" onclick="toggleMobileMenu()" class="nav-link py-3 px-1 border-b border-slate-100">Academics</a>
            <a href="#campuses" onclick="toggleMobileMenu()" class="nav-link py-3 px-1 border-b border-slate-100">Campuses</a>
            <a href="#admissions" onclick="toggleMobileMenu()" class="nav-link py-3 px-1 border-b border-slate-100">Admissions</a>
            <button onclick="showApplicationModal(); toggleMobileMenu()"
                    class="mt-5 w-full py-3.5 text-[14px] font-semibold formal-button rounded-2xl">
                Apply Now
            </button>
        </div>
    </div>

    <!-- Hero -->
    <header class="relative h-[660px] flex items-center justify-center overflow-hidden">
        <div class="absolute inset-0 bg-cover bg-center"
             style="background-image: url('https://picsum.photos/id/1015/2000/1200')"></div>
        <div class="hero-overlay absolute inset-0"></div>

        <div class="relative z-10 max-w-5xl mx-auto px-8 text-center">
            <div class="inline-flex items-center gap-x-2.5 bg-white/10 backdrop-blur-2xl px-5 py-1.5 rounded-3xl mb-8 border border-white/25 shadow-sm">
                <div class="w-1.5 h-1.5 bg-emerald-400 rounded-full animate-pulse"></div>
                <span class="text-white text-[12.5px] font-semibold tracking-[1.5px]">RANKED #1 BY THE GOONING ASSOCIATION OF AMERICA • 2025</span>
            </div>

            <h1 class="text-white text-[70px] md:text-[86px] leading-[0.9] font-bold tracking-[-4.4px] heading-serif mb-5">Chud University<br>of Michigan</h1>
            <p class="text-white/95 text-[26px] md:text-[29px] font-light tracking-[-0.65px] mb-10">Excellence in Gooning, Psychology &amp; Digital Governance</p>

            <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                <button onclick="showApplicationModal()"
                        class="group px-9 py-[17px] text-[15.5px] font-semibold accent-button rounded-3xl flex items-center justify-center gap-x-3 shadow-2xl shadow-teal-950/40 active:scale-[0.985] transition-all">
                    <span>Begin Your Application</span>
                    <i class="fa-solid fa-arrow-right transition-transform group-hover:translate-x-0.5"></i>
                </button>
                <button onclick="document.getElementById('about').scrollIntoView({ behavior: 'smooth' })"
                        class="px-8 py-[17px] text-[15.5px] font-medium bg-white/10 hover:bg-white/15 active:bg-white/20 text-white border border-white/35 rounded-3xl backdrop-blur-xl transition-all active:scale-[0.985]">
                    Learn More
                </button>
            </div>

            <div class="mt-14 flex items-center justify-center gap-x-9 text-white/70 text-[13.5px] font-medium tracking-wide">
                <div class="flex items-center gap-x-2.5">
                    <i class="fa-solid fa-map-marker-alt text-white/55"></i>
                    <span>Climax, Michigan</span>
                </div>
                <div class="w-px h-3.5 bg-white/30"></div>
                <div class="flex items-center gap-x-2.5">
                    <i class="fa-solid fa-map-marker-alt text-white/55"></i>
                    <span>Oblong, Illinois</span>
                </div>
            </div>
        </div>
    </header>

    <!-- Quick Stats -->
    <div class="border-b border-slate-200 bg-white" data-stats>
        <div class="max-w-7xl mx-auto px-8 py-9">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-x-8 gap-y-9 text-center">
                <div class="reveal">
                    <div class="text-[44px] font-bold text-[#0A0F1C] tracking-[-1.8px] stat-number">1</div>
                    <div class="text-[12.5px] text-slate-600 mt-1.5 tracking-[1.75px] font-semibold">NATIONAL RANKING IN GOONING</div>
                    <div class="text-xs text-slate-400 mt-0.5">Gooning Association of America, 2025</div>
                </div>
                <div class="reveal reveal-delay-1">
                    <div class="text-[44px] font-bold text-[#0A0F1C] tracking-[-1.8px] stat-number">2,847</div>
                    <div class="text-[12.5px] text-slate-600 mt-1.5 tracking-[1.75px] font-semibold">CURRENTLY ENROLLED</div>
                    <div class="text-xs text-slate-400 mt-0.5">Certified chuds, incels &amp; gooners</div>
                </div>
                <div class="reveal reveal-delay-2">
                    <div class="text-[44px] font-bold text-[#0A0F1C] tracking-[-1.8px] stat-number">94</div>
                    <div class="text-[12.5px] text-slate-600 mt-1.5 tracking-[1.75px] font-semibold">GOON PLACEMENT RATE</div>
                    <div class="text-xs text-slate-400 mt-0.5">Within 6 months of graduation</div>
                </div>
                <div class="reveal reveal-delay-3">
                    <div class="text-[44px] font-bold text-[#0A0F1C] tracking-[-1.8px] stat-number">68</div>
                    <div class="text-[12.5px] text-slate-600 mt-1.5 tracking-[1.75px] font-semibold">DISCORD SERVERS MODERATED</div>
                    <div class="text-xs text-slate-400 mt-0.5">By current student body</div>
                </div>
            </div>
        </div>
    </div>

    <!-- About -->
    <section id="about" class="max-w-5xl mx-auto px-8 pt-20 pb-16 reveal">
        <div class="max-w-[47rem]">
            <div class="uppercase text-xs tracking-[3.75px] text-[#0F766E] font-bold mb-4">ESTABLISHED 1969</div>
            <h2 class="section-header mb-7 leading-none">A distinguished institution<br>dedicated to specialized scholarship.</h2>
            <div class="prose prose-slate text-[15.3px] leading-relaxed text-slate-600">
                <p>Founded in the historic village of Climax, Michigan, Chud University of Michigan has established itself as the premier destination for rigorous training in gooning methodology, psychological inquiry into digital subcultures, and the nuanced art of community moderation.</p>
                <p class="mt-5">We maintain an intentionally selective admissions process. The University extends invitations exclusively to certified chuds, incels, gooners, and the finest basement-dwellers who demonstrate exceptional promise. Our community is built upon a shared commitment to intellectual honesty, digital fluency, and mastery in environments often misunderstood by conventional academia.</p>
            </div>
        </div>
    </section>

    <!-- Academic Programs -->
    <section id="academics" class="bg-white border-y border-slate-200 py-16">
        <div class="max-w-7xl mx-auto px-8">
            <div class="flex items-end justify-between mb-11">
                <div>
                    <div class="uppercase text-xs tracking-[3.75px] text-[#0F766E] font-bold mb-2.5">SIGNATURE PROGRAMS</div>
                    <h2 class="section-header">Academic Offerings</h2>
                </div>
                <a href="#" class="hidden md:flex items-center text-sm font-semibold text-[#0F766E] hover:text-[#115E59] transition-colors group">
                    View full course catalog
                    <i class="fa-solid fa-arrow-right ml-2 transition-transform group-hover:translate-x-0.5"></i>
                </a>
            </div>

            <div class="grid md:grid-cols-3 gap-6">
                <div onclick="showProgramModal('gooning')"
                     class="academic-card interactive-card rounded-3xl p-8 flex flex-col premium-shadow reveal">
                    <div class="flex items-center justify-between mb-7">
                        <div class="w-12 h-12 bg-[#CCFBF1] text-[#0F766E] rounded-2xl flex items-center justify-center">
                            <i class="fa-solid fa-infinity text-[26px]"></i>
                        </div>
                        <span class="program-badge">B.G. • M.G.</span>
                    </div>
                    <h3 class="text-[26px] font-semibold tracking-[-0.6px] mb-3.5">Gooning Studies</h3>
                    <p class="text-[14.8px] text-slate-600 flex-1 leading-relaxed">Our flagship discipline. Students engage in intensive, supervised practice and theoretical analysis of gooning methodology, endurance optimization, and philosophical frameworks.</p>
                    <div class="pt-6 mt-auto border-t border-slate-100 text-sm text-slate-500 flex items-center gap-x-2 font-medium">
                        <i class="fa-solid fa-users text-[#0F766E]"></i>
                        <span>1,142 current majors</span>
                    </div>
                </div>

                <div onclick="showProgramModal('psychology')"
                     class="academic-card interactive-card rounded-3xl p-8 flex flex-col premium-shadow reveal reveal-delay-1">
                    <div class="flex items-center justify-between mb-7">
                        <div class="w-12 h-12 bg-[#E0E7FF] text-[#4338CA] rounded-2xl flex items-center justify-center">
                            <i class="fa-solid fa-brain text-[26px]"></i>
                        </div>
                        <span class="program-badge">B.A. • Ph.D.</span>
                    </div>
                    <h3 class="text-[26px] font-semibold tracking-[-0.6px] mb-3.5">Psychology</h3>
                    <p class="text-[14.8px] text-slate-600 flex-1 leading-relaxed">A specialized curriculum examining the contemporary male experience, online identity formation, and the psychological dimensions of digital subcultures.</p>
                    <div class="pt-6 mt-auto border-t border-slate-100 text-sm text-slate-500 flex items-center gap-x-2 font-medium">
                        <i class="fa-solid fa-users text-[#4338CA]"></i>
                        <span>687 current majors</span>
                    </div>
                </div>

                <div onclick="showProgramModal('discord')"
                     class="academic-card interactive-card rounded-3xl p-8 flex flex-col premium-shadow reveal reveal-delay-2">
                    <div class="flex items-center justify-between mb-7">
                        <div class="w-12 h-12 bg-[#CFFAFE] text-[#0E7490] rounded-2xl flex items-center justify-center">
                            <i class="fa-solid fa-shield-halved text-[26px]"></i>
                        </div>
                        <span class="program-badge">Certificate • B.S.</span>
                    </div>
                    <h3 class="text-[26px] font-semibold tracking-[-0.6px] mb-3.5">Discord Moderation</h3>
                    <p class="text-[14.8px] text-slate-600 flex-1 leading-relaxed">Professional training in rule adjudication, de-escalation techniques, meme governance, and the cultivation of high-signal digital spaces.</p>
                    <div class="pt-6 mt-auto border-t border-slate-100 text-sm text-slate-500 flex items-center gap-x-2 font-medium">
                        <i class="fa-solid fa-users text-[#0E7490]"></i>
                        <span>1,018 current students</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Recognition -->
    <section class="max-w-5xl mx-auto px-8 py-20 text-center reveal">
        <div class="inline-block bg-[#0A0F1C] text-white px-6 py-1.5 rounded-3xl text-xs font-bold tracking-[2.2px] mb-5">INSTITUTIONAL DISTINCTION</div>
        <h2 class="text-[44px] font-bold tracking-[-1.8px] mb-4 leading-none">Ranked #1 Hotspot for Gooning</h2>
        <p class="text-2xl text-slate-600">Gooning Association of America — Annual Rankings, 2025</p>
        <div class="mt-9 inline-flex items-center gap-x-3 bg-white border border-slate-200 px-6 py-4 rounded-3xl text-sm">
            <i class="fa-solid fa-trophy text-amber-500 text-lg"></i>
            <span class="font-medium text-slate-700">Also recognized for excellence in basement scholarship and digital asceticism</span>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="bg-white border-y border-slate-200 py-16">
        <div class="max-w-7xl mx-auto px-8">
            <div class="mb-11">
                <div class="uppercase text-xs tracking-[3.75px] text-[#0F766E] font-bold mb-2.5">FROM OUR ALUMNI</div>
                <h2 class="section-header">Voices from the Community</h2>
            </div>

            <div class="grid md:grid-cols-3 gap-6">
                <div class="testimonial bg-[#F8FAFC] border border-slate-200 rounded-3xl p-8 pt-10 reveal">
                    <p class="text-[15.2px] text-slate-700 italic leading-relaxed relative z-10">"Quite the hole in the wall. I keep coming back."</p>
                    <div class="mt-9 flex items-center gap-x-4">
                        <div class="w-11 h-11 bg-slate-200 rounded-2xl flex-shrink-0 overflow-hidden ring-1 ring-inset ring-slate-300/60">
                            <img src="https://picsum.photos/id/64/44/44" alt="Davi Ferreria" class="object-cover w-full h-full">
                        </div>
                        <div class="leading-tight">
                            <div class="font-semibold tracking-[-0.2px]">Davi Ferreria</div>
                            <div class="text-sm text-slate-500">Class of 2019 • Gooning Studies</div>
                        </div>
                    </div>
                </div>

                <div class="testimonial bg-[#F8FAFC] border border-slate-200 rounded-3xl p-8 pt-10 reveal reveal-delay-1">
                    <p class="text-[15.2px] text-slate-700 italic leading-relaxed relative z-10">"This place is amazing. If only I had a better view of the ocean from my dorm..."</p>
                    <div class="mt-9 flex items-center gap-x-4">
                        <div class="w-11 h-11 bg-slate-200 rounded-2xl flex-shrink-0 overflow-hidden ring-1 ring-inset ring-slate-300/60">
                            <img src="https://picsum.photos/id/1005/44/44" alt="Effrey Jepstein" class="object-cover w-full h-full">
                        </div>
                        <div class="leading-tight">
                            <div class="font-semibold tracking-[-0.2px]">Effrey Jepstein</div>
                            <div class="text-sm text-slate-500">Class of 1997 • Psychology</div>
                        </div>
                    </div>
                </div>

                <div class="testimonial bg-[#F8FAFC] border border-slate-200 rounded-3xl p-8 pt-10 reveal reveal-delay-2">
                    <p class="text-[15.2px] text-slate-700 italic leading-relaxed relative z-10">"Best place to find quality kittens on a budget. This is anonymous, right?"</p>
                    <div class="mt-9 flex items-center gap-x-4">
                        <div class="w-11 h-11 bg-slate-200 rounded-2xl flex-shrink-0 overflow-hidden ring-1 ring-inset ring-slate-300/60">
                            <img src="https://picsum.photos/id/201/44/44" alt="M'Elon M. Usk" class="object-cover w-full h-full">
                        </div>
                        <div class="leading-tight">
                            <div class="font-semibold tracking-[-0.2px]">M'Elon M. Usk</div>
                            <div class="text-sm text-slate-500">Class of 1976 • Discord Moderation</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Campuses -->
    <section id="campuses" class="max-w-7xl mx-auto px-8 py-20">
        <div class="mb-11">
            <div class="uppercase text-xs tracking-[3.75px] text-[#0F766E] font-bold mb-2.5">LOCATIONS</div>
            <h2 class="section-header">Our Campuses</h2>
        </div>

        <div class="grid md:grid-cols-2 gap-8">
            <div class="campus-card bg-white rounded-3xl overflow-hidden border border-slate-200 reveal">
                <div class="h-[230px] bg-cover bg-center relative" style="background-image: url('https://picsum.photos/id/160/900/600')">
                    <div class="absolute top-5 right-5 px-4 py-1 bg-white/90 backdrop-blur-md text-xs font-bold tracking-wider text-emerald-700 rounded-2xl">MAIN CAMPUS</div>
                </div>
                <div class="p-8">
                    <h3 class="text-[29px] font-semibold tracking-[-0.8px]">Climax, Michigan</h3>
                    <p class="mt-4 text-[14.8px] text-slate-600 leading-relaxed">Our historic flagship campus occupies a serene 340-acre site in southwestern Michigan. The grounds feature dedicated gooning pavilions, extensive basement archives, and the university's renowned Center for Digital Asceticism.</p>
                    <div class="mt-6 text-sm flex items-center gap-x-2 text-slate-500 font-medium">
                        <i class="fa-solid fa-users text-emerald-600"></i>
                        <span>1,892 students • 89 faculty residences</span>
                    </div>
                </div>
            </div>

            <div class="campus-card bg-white rounded-3xl overflow-hidden border border-slate-200 reveal reveal-delay-1">
                <div class="h-[230px] bg-cover bg-center relative" style="background-image: url('https://picsum.photos/id/251/900/600')">
                    <div class="absolute top-5 right-5 px-4 py-1 bg-white/90 backdrop-blur-md text-xs font-bold tracking-wider text-sky-700 rounded-2xl">SECONDARY CAMPUS</div>
                </div>
                <div class="p-8">
                    <h3 class="text-[29px] font-semibold tracking-[-0.8px]">Oblong, Illinois</h3>
                    <p class="mt-4 text-[14.8px] text-slate-600 leading-relaxed">Our innovative satellite campus in rural Illinois provides expanded facilities for advanced Discord moderation laboratories and large-scale gooning symposiums. The open landscape offers unique opportunities for off-grid digital practice.</p>
                    <div class="mt-6 text-sm flex items-center gap-x-2 text-slate-500 font-medium">
                        <i class="fa-solid fa-users text-sky-600"></i>
                        <span>955 students • 41 faculty residences</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Admissions -->
    <section id="admissions" class="bg-[#0A0F1C] text-white py-16">
        <div class="max-w-5xl mx-auto px-8">
            <div class="max-w-3xl">
                <div class="uppercase tracking-[3.75px] text-xs text-white/50 font-bold mb-4">SELECTIVE ADMISSIONS</div>
                <h2 class="text-white text-[46px] font-bold tracking-[-1.6px] mb-7 leading-none">Who Belongs at<br>Chud University of Michigan</h2>
                <div class="text-[15.5px] text-white/90 leading-relaxed space-y-5 max-w-[42ch]">
                    <p>Chud University of Michigan maintains one of the most focused admissions policies in higher education. We accept applications exclusively from certified chuds, incels, gooners, and the finest basement-dwellers.</p>
                    <p>Prospective students are expected to demonstrate meaningful engagement with the core disciplines through documented practice, community contributions, and a compelling personal statement.</p>
                </div>
            </div>

            <div class="mt-12 grid md:grid-cols-2 gap-5">
                <div class="bg-white/5 border border-white/10 rounded-3xl p-8 reveal">
                    <div class="font-semibold mb-5 flex items-center gap-x-3 text-lg">
                        <i class="fa-solid fa-check-circle text-emerald-400"></i>
                        <span>Application Requirements</span>
                    </div>
                    <ul class="space-y-3 text-[14.5px] text-white/85">
                        <li class="flex gap-x-3"><span class="font-mono text-xs mt-[3px] opacity-70 w-5">01</span> Completed online application</li>
                        <li class="flex gap-x-3"><span class="font-mono text-xs mt-[3px] opacity-70 w-5">02</span> Certification documentation</li>
                        <li class="flex gap-x-3"><span class="font-mono text-xs mt-[3px] opacity-70 w-5">03</span> Portfolio of relevant work (memes, server logs, manifestos)</li>
                        <li class="flex gap-x-3"><span class="font-mono text-xs mt-[3px] opacity-70 w-5">04</span> Two letters of recommendation from verified online peers</li>
                        <li class="flex gap-x-3"><span class="font-mono text-xs mt-[3px] opacity-70 w-5">05</span> Personal statement (minimum 420 words)</li>
                    </ul>
                </div>

                <div class="bg-white/5 border border-white/10 rounded-3xl p-8 flex flex-col reveal reveal-delay-1">
                    <div>
                        <div class="font-semibold mb-5 text-lg">Application Cycle</div>
                        <div class="text-[14.5px] text-white/85 space-y-1.5">
                            <div><span class="font-medium">Early Action:</span> November 1</div>
                            <div><span class="font-medium">Regular Decision:</span> January 15</div>
                            <div class="pt-1 text-xs text-white/50">Decisions released on a rolling basis</div>
                        </div>
                    </div>
                    <div class="mt-auto pt-9">
                        <button onclick="showApplicationModal()"
                                class="w-full py-4 font-semibold text-[15px] accent-button rounded-3xl flex items-center justify-center gap-x-3 active:scale-[0.985] transition-all">
                            Start Application <i class="fa-solid fa-arrow-right"></i>
                        </button>
                        <p class="text-center text-xs text-white/50 mt-4 tracking-wide">Applications reviewed by the Board of Certified Chuds</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-white border-t border-slate-200 py-14">
        <div class="max-w-7xl mx-auto px-8">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-y-8">
                <div>
                    <div class="flex items-center gap-x-3.5 mb-3.5">
                        <div class="w-9 h-9 bg-[#0A0F1C] rounded-2xl flex items-center justify-center ring-1 ring-inset ring-white/10">
                            <span class="text-white text-[17px] font-bold tracking-[-1.25px] font-serif">CUM</span>
                        </div>
                        <span class="font-semibold tracking-[-0.4px] text-lg">Chud University of Michigan</span>
                    </div>
                    <div class="text-sm text-slate-500">© 1969–2026. All rights reserved. • Climax, Michigan</div>
                </div>
                <div class="text-sm text-slate-500 max-w-[260px] md:text-right leading-snug">
                    Main Campus: 69 Chud Boulevard<br>
                    Climax, Michigan 49034<br>
                    Secondary Campus: Oblong, Illinois
                </div>
            </div>
        </div>
    </footer>

    <!-- Application Modal -->
    <div id="application-modal" class="hidden fixed inset-0 z-[100] flex items-center justify-center bg-black/70 p-4"
         role="dialog" aria-modal="true" aria-label="Application for admission">
        <div onclick="event.target.id === 'application-modal' && hideApplicationModal()" class="absolute inset-0"></div>

        <div class="relative bg-white w-full max-w-lg rounded-3xl shadow-2xl overflow-hidden border border-slate-200 modal">
            <div class="px-9 pt-9 pb-6 border-b">
                <div class="flex items-start justify-between">
                    <div>
                        <div class="font-bold text-[27px] tracking-[-0.6px]">Application for Admission</div>
                        <div class="text-sm text-slate-500 mt-0.5">Chud University of Michigan • Class of 2030</div>
                    </div>
                    <button onclick="hideApplicationModal()" aria-label="Close" class="text-slate-400 hover:text-slate-600 text-4xl leading-none mt-[-6px] transition-colors">×</button>
                </div>
            </div>

            <form id="application-form" onsubmit="submitApplication(event)" class="p-9 space-y-6" novalidate>
                <div class="grid grid-cols-1 gap-5">
                    <div>
                        <label class="block text-xs font-bold tracking-wider text-slate-500 mb-1.5">FULL LEGAL NAME</label>
                        <input type="text" name="full_name" class="w-full border border-slate-300 focus:border-[#0F766E] rounded-2xl px-5 py-[13px] text-[14.5px] focus:outline-none transition-colors" placeholder="Your full legal name">
                    </div>

                    <div>
                        <label class="block text-xs font-bold tracking-wider text-slate-500 mb-1.5">EMAIL ADDRESS</label>
                        <input type="email" name="email" class="w-full border border-slate-300 focus:border-[#0F766E] rounded-2xl px-5 py-[13px] text-[14.5px] focus:outline-none transition-colors" placeholder="you@domain.com">
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
                        <div>
                            <label class="block text-xs font-bold tracking-wider text-slate-500 mb-1.5">INTENDED PROGRAM</label>
                            <select name="intended_program" class="w-full border border-slate-300 focus:border-[#0F766E] rounded-2xl px-5 py-[13px] text-[14.5px] focus:outline-none transition-colors bg-white">
                                <option value="">Select program</option>
                                <option>Gooning Studies</option>
                                <option>Psychology</option>
                                <option>Discord Moderation</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-bold tracking-wider text-slate-500 mb-1.5">CERTIFICATION TYPE</label>
                            <select name="certification_type" class="w-full border border-slate-300 focus:border-[#0F766E] rounded-2xl px-5 py-[13px] text-[14.5px] focus:outline-none transition-colors bg-white">
                                <option value="">Select certification</option>
                                <option>Certified Chud</option>
                                <option>Incel</option>
                                <option>Gooner</option>
                                <option>Basement-Dweller (Elite)</option>
                            </select>
                        </div>
                    </div>

                    <div>
                        <label class="block text-xs font-bold tracking-wider text-slate-500 mb-1.5">PERSONAL STATEMENT</label>
                        <textarea name="personal_statement" rows="4" class="w-full border border-slate-300 focus:border-[#0F766E] rounded-3xl px-5 py-4 text-[14.5px] focus:outline-none transition-colors resize-y" placeholder="Describe your journey and why Chud University of Michigan represents the logical next step..."></textarea>
                        <div class="text-right text-xs text-slate-400 mt-1.5 font-medium">Minimum 420 words recommended</div>
                    </div>

                    <!-- Honeypot: hidden from humans, catches bots. Do not remove. -->
                    <div aria-hidden="true" style="position:absolute;left:-9999px;top:-9999px;">
                        <label>Company<input type="text" name="company" tabindex="-1" autocomplete="off"></label>
                    </div>
                </div>

                <div class="pt-3">
                    <button type="submit" class="w-full py-[17px] font-semibold text-[15px] accent-button rounded-3xl flex items-center justify-center gap-x-3 active:scale-[0.985] transition-all">
                        Submit Application
                    </button>
                    <p class="text-center text-xs text-slate-400 mt-5">Applications reviewed exclusively by the Board of Certified Chuds. Response within 6–8 weeks.</p>
                </div>
            </form>
        </div>
    </div>

    <!-- Program Detail Modal -->
    <div id="program-modal" class="hidden fixed inset-0 z-[110] flex items-center justify-center bg-black/70 p-4"
         role="dialog" aria-modal="true" aria-label="Program details">
        <div onclick="event.target.id === 'program-modal' && hideProgramModal()" class="absolute inset-0"></div>

        <div class="relative bg-white w-full max-w-2xl rounded-3xl shadow-2xl overflow-hidden border border-slate-200 modal">
            <div class="px-9 pt-8 pb-6 border-b flex items-start justify-between">
                <div id="program-modal-header"></div>
                <button onclick="hideProgramModal()" aria-label="Close" class="text-slate-400 hover:text-slate-600 text-4xl leading-none mt-[-4px]">×</button>
            </div>
            <div class="p-9" id="program-modal-body"></div>
            <div class="px-9 py-6 bg-slate-50 border-t flex justify-end gap-3">
                <button onclick="hideProgramModal()" class="px-6 py-2.5 text-sm font-medium border border-slate-300 rounded-2xl hover:bg-white transition-colors">Close</button>
                <button onclick="hideProgramModal(); showApplicationModal()" class="px-6 py-2.5 text-sm font-semibold accent-button rounded-2xl">Apply to this program</button>
            </div>
        </div>
    </div>

    <script src="/js/main.js"></script>
</body>
</html>
