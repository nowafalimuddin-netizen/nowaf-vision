<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nowaf Vision | Official Website</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #0f172a; color: white; overflow-x: hidden; -webkit-font-smoothing: antialiased; }
        .hero-font { font-family: 'Orbitron', sans-serif; }

        /* --- PRE-LOADER --- */
        #loader-wrapper {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: #020617; display: flex; flex-direction: column;
            justify-content: center; align-items: center; z-index: 9999;
            transition: opacity 0.8s cubic-bezier(0.65, 0, 0.35, 1);
        }
        .loader-ring {
            width: 60px; height: 60px; border: 3px solid rgba(0, 242, 255, 0.1);
            border-top: 3px solid #00f2ff; border-radius: 50%;
            animation: spin 1s infinite linear;
        }
        @keyframes spin { 100% { transform: rotate(360deg); } }

        /* --- DESIGN CORE (UNCHANGED) --- */
        .hero-section {
            background: linear-gradient(rgba(15, 23, 42, 0.6), rgba(15, 23, 42, 0.9)), 
                        url('nowaf-vision.jpg');
            background-size: cover; background-position: center; background-attachment: fixed;
        }
        .glass-overlay {
            background: rgba(255, 255, 255, 0.02); backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px); border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3); position: relative; overflow: hidden;
        }
        .bounce-card { transition: all 0.6s cubic-bezier(0.34, 1.56, 0.64, 1); cursor: pointer; will-change: transform; }
        .bounce-card:hover { transform: translateY(-10px) scale(1.02); border-color: rgba(0, 242, 255, 0.3); }
        .bounce-card:active { transform: scale(0.95); }
        .neon-text { text-shadow: 0 0 15px rgba(0, 242, 255, 0.7); }

        /* --- SMOOTH REVEAL ANIMATION --- */
        .reveal { opacity: 0; transform: translateY(40px); transition: 1.2s cubic-bezier(0.2, 0.8, 0.2, 1); }
        .reveal.active { opacity: 1; transform: translateY(0); }
        
        /* Smooth Scrolling */
        html { scroll-behavior: smooth; }
    </style>
</head>
<body>

    <div id="loader-wrapper">
        <div class="loader-ring"></div>
        <p class="mt-6 hero-font text-cyan-400 tracking-[0.4em] animate-pulse">INITIALIZING VISION</p>
    </div>

    <audio id="bgMusic" loop src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-15.mp3"></audio>
    <audio id="clickSound" src="https://www.soundjay.com/buttons/sounds/button-16.mp3"></audio>

    <nav class="fixed w-full z-50 bg-slate-950/60 backdrop-blur-xl border-b border-slate-800/50">
        <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-2xl font-bold tracking-widest hero-font text-cyan-400">NOWAF VISION</div>
            <button onclick="playAction()" class="bg-cyan-500 text-slate-950 px-6 py-2 rounded-full font-bold active:scale-90 transition">Subscribe</button>
        </div>
    </nav>

    <header class="hero-section min-h-screen flex items-center justify-center px-6 text-center">
        <div class="max-w-4xl glass-overlay p-10 md:p-20 rounded-[50px] bounce-card reveal" id="hero-box">
            <h1 class="text-6xl md:text-8xl font-bold mb-4 hero-font tracking-tighter neon-text">
                NOWAF <span class="text-cyan-400">VISION</span>
            </h1>
            <p class="text-xl md:text-2xl text-slate-300 mb-10 tracking-wide uppercase opacity-80">Digital Creator • Visual Artist</p>
            <a href="#feed" onclick="playAction()" class="haptic-trigger border-2 border-cyan-400/50 px-10 py-4 rounded-xl font-bold hover:bg-cyan-500 hover:text-slate-950 transition-all">Explore Feed</a>
        </div>
    </header>

    <section id="feed" class="py-24 bg-slate-950">
        <div class="max-w-7xl mx-auto px-6">
            <h2 class="text-4xl font-bold hero-font text-center mb-16 text-cyan-400 tracking-widest reveal">LIVE FEED</h2>
            
            <div class="grid md:grid-cols-2 gap-10">
                <div class="glass-overlay rounded-[40px] p-6 bounce-card reveal">
                    <h3 class="hero-font text-sm mb-4 text-slate-400">LATEST FROM YOUTUBE</h3>
                    <div class="aspect-video rounded-2xl overflow-hidden bg-black">
                        <iframe class="w-full h-full" src="https://www.youtube.com/embed?listType=user_uploads&list=nowafvision" frameborder="0" allowfullscreen></iframe>
                    </div>
                    <div class="mt-4 flex justify-between items-center px-2">
                        <button onclick="handleLike(this)" class="group flex items-center space-x-2 text-slate-400 hover:text-pink-500 transition">
                            <span class="text-2xl">❤️</span> <span class="like-count font-bold">1.2k</span>
                        </button>
                        <a href="https://www.youtube.com/@nowafvision" class="text-cyan-400 text-xs font-bold uppercase">Open YouTube →</a>
                    </div>
                </div>

                <div class="glass-overlay rounded-[40px] p-6 bounce-card reveal">
                    <h3 class="hero-font text-sm mb-4 text-slate-400">INSTAGRAM MOMENTS</h3>
                    <div class="aspect-square rounded-2xl overflow-hidden bg-slate-900 flex items-center justify-center">
                        <div class="text-center p-8">
                            <p class="text-slate-500 text-sm mb-4">Linking to @nowaf.khan...</p>
                            <a href="https://www.instagram.com/nowaf.khan" target="_blank" class="bg-gradient-to-tr from-yellow-500 to-purple-600 px-6 py-2 rounded-lg font-bold">View Gallery</a>
                        </div>
                    </div>
                    <div class="mt-4 flex justify-between items-center px-2">
                        <button onclick="handleLike(this)" class="group flex items-center space-x-2 text-slate-400 hover:text-pink-500 transition">
                            <span class="text-2xl">❤️</span> <span class="like-count font-bold">840</span>
                        </button>
                        <span class="text-slate-500 text-xs uppercase tracking-tighter">Synced Live</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="socials" class="py-24 bg-slate-900/50">
        <div class="max-w-7xl mx-auto px-6 text-center">
            <h2 class="text-2xl font-bold hero-font mb-12 text-cyan-400 opacity-60">QUICK LINKS</h2>
            <div class="flex flex-wrap justify-center gap-6">
                <a href="#" class="glass-overlay px-8 py-4 rounded-2xl bounce-card reveal">YouTube</a>
                <a href="#" class="glass-overlay px-8 py-4 rounded-2xl bounce-card reveal">Instagram</a>
                <a href="#" class="glass-overlay px-8 py-4 rounded-2xl bounce-card reveal">Facebook</a>
            </div>
        </div>
    </section>

    <footer class="bg-black py-16 border-t border-slate-900 text-center">
        <p class="hero-font text-slate-600 text-sm tracking-widest">© 2026 NOWAF VISION</p>
    </footer>

    <script>
        // 1. Loader Logic
        window.addEventListener('load', () => {
            const loader = document.getElementById('loader-wrapper');
            setTimeout(() => {
                loader.style.opacity = '0';
                setTimeout(() => { 
                    loader.style.display = 'none';
                    document.getElementById('hero-box').classList.add('active');
                }, 800);
            }, 1500);
        });

        // 2. Music & Sound Logic
        function playAction() {
            const click = document.getElementById('clickSound');
            click.currentTime = 0; click.play();
            if (navigator.vibrate) navigator.vibrate(15);
        }

        // Auto-play Background Music on first interaction
        document.body.addEventListener('click', () => {
            document.getElementById('bgMusic').play();
        }, { once: true });

        // 3. Like Interaction
        function handleLike(btn) {
            playAction();
            const countTag = btn.querySelector('.like-count');
            btn.classList.toggle('text-pink-500');
            btn.style.transform = "scale(1.2)";
            setTimeout(() => btn.style.transform = "scale(1)", 200);
        }

        // 4. Intersection Observer for Smooth Reveals
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('active'); });
        }, { threshold: 0.1 });
        document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

        // 5. Global Mobile Haptics
        document.querySelectorAll('.bounce-card').forEach(card => {
            card.addEventListener('touchstart', () => { if(navigator.vibrate) navigator.vibrate(10); });
        });
    </script>

</body>
</html>
