
<!DOCTYPE html>
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
        
        /* --- LOADING SCREEN --- */
        #loader-wrapper {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: #0f172a; display: flex; flex-direction: column;
            justify-content: center; align-items: center; z-index: 9999;
            transition: opacity 0.8s ease, visibility 0.8s;
        }
        .loader-orbit {
            width: 60px; height: 60px; border: 3px solid transparent;
            border-top-color: #00f2ff; border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        @keyframes spin { 100% { transform: rotate(360deg); } }

        /* --- DESIGN UNCHANGED --- */
        .hero-section {
            background: linear-gradient(rgba(15, 23, 42, 0.6), rgba(15, 23, 42, 0.9)), 
                        url('nowaf-vision.jpg');
            background-size: cover; background-position: center; background-attachment: fixed;
        }

        .glass-overlay {
            background: rgba(255, 255, 255, 0.02); backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px); border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3); position: relative; overflow: hidden;
        }

        .bounce-card { transition: all 0.6s cubic-bezier(0.34, 1.56, 0.64, 1); cursor: pointer; will-change: transform; }
        .bounce-card:hover { transform: translateY(-15px) scale(1.04); }
        .bounce-card:active { transform: scale(0.88) translateY(10px); }

        .neon-text { text-shadow: 0 0 15px rgba(0, 242, 255, 0.7); }
        html { scroll-behavior: smooth; }

        /* --- NEW SCROLL ANIMATIONS --- */
        .reveal { opacity: 0; transform: translateY(40px); transition: 1.2s all ease; }
        .reveal.active { opacity: 1; transform: translateY(0); }
    </style>
</head>
<body>

    <div id="loader-wrapper">
        <div class="loader-orbit"></div>
        <p class="mt-4 hero-font text-cyan-400 tracking-widest animate-pulse">INITIALIZING VISION</p>
    </div>

    <audio id="bgMusic" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-15.mp3" type="audio/mpeg">
    </audio>
    <audio id="clickSound">
        <source src="https://www.soundjay.com/buttons/sounds/button-16.mp3" type="audio/mpeg">
    </audio>

    <nav class="fixed w-full z-50 bg-slate-950/60 backdrop-blur-xl border-b border-slate-800/50">
        <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-2xl font-bold tracking-widest hero-font text-cyan-400">NOWAF VISION</div>
            <div class="hidden md:flex space-x-8 font-medium">
                <a href="#about" class="hover:text-cyan-400 transition-colors duration-300">About</a>
                <a href="#socials" class="hover:text-cyan-400 transition-colors duration-300">Connect</a>
            </div>
            <a href="https://www.youtube.com/@nowafvision" target="_blank" onclick="playClick()" class="haptic-trigger bg-cyan-500 hover:bg-cyan-400 text-slate-950 px-6 py-2 rounded-full font-bold transition-all duration-300 active:scale-90">
                Subscribe
            </a>
        </div>
    </nav>

    <header class="hero-section min-h-screen flex items-center justify-center px-6 text-center">
        <div class="max-w-4xl glass-overlay p-10 md:p-20 rounded-[50px] bounce-card haptic-trigger reveal">
            <h1 class="text-6xl md:text-8xl font-bold mb-4 hero-font tracking-tighter neon-text">
                NOWAF <span class="text-cyan-400">VISION</span>
            </h1>
            <p class="text-xl md:text-2xl text-slate-300 mb-10 tracking-wide uppercase opacity-80">
                Digital Creator • Visual Artist • Tech Enthusiast
            </p>
            <div class="flex flex-wrap justify-center gap-6">
                <a href="#socials" onclick="playClick()" class="haptic-trigger border-2 border-cyan-400/50 px-10 py-4 rounded-xl font-bold hover:bg-cyan-500 hover:text-slate-950 transition-all duration-500 active:scale-95">
                    My Work
                </a>
            </div>
        </div>
    </header>

    <section id="socials" class="py-24 bg-slate-950">
        <div class="max-w-7xl mx-auto px-6">
            <h2 class="text-4xl font-bold hero-font text-center mb-16 text-cyan-400 tracking-widest reveal">CONNECT WITH ME</h2>
            
            <div class="grid md:grid-cols-3 gap-10">
                <a href="https://www.youtube.com/@nowafvision" onclick="playClick()" target="_blank" class="p-8 glass-overlay rounded-3xl bounce-card group haptic-trigger reveal">
                    <h3 class="text-2xl font-bold mb-2 group-hover:text-red-500 transition-colors duration-300">YouTube</h3>
                    <p class="text-slate-400 mb-4">Watch my latest visual content and tech reviews.</p>
                    <span class="text-red-500 font-semibold underline underline-offset-8">Visit Channel →</span>
                </a>

                <a href="https://www.facebook.com/share/1PfieLvfCx/" onclick="playClick()" target="_blank" class="p-8 glass-overlay rounded-3xl bounce-card group haptic-trigger reveal">
                    <h3 class="text-2xl font-bold mb-2 group-hover:text-blue-500 transition-colors duration-300">Facebook</h3>
                    <p class="text-slate-400 mb-4">Join my community and stay updated on daily life.</p>
                    <span class="text-blue-500 font-semibold underline underline-offset-8">Join Community →</span>
                </a>

                <a href="https://www.instagram.com/nowaf.khan" onclick="playClick()" target="_blank" class="p-8 glass-overlay rounded-3xl bounce-card group haptic-trigger reveal">
                    <h3 class="text-2xl font-bold mb-2 group-hover:text-pink-500 transition-colors duration-300">Instagram</h3>
                    <p class="text-slate-400 mb-4">Follow for behind-the-scenes and photography.</p>
                    <span class="text-pink-500 font-semibold underline underline-offset-8">Follow Me →</span>
                </a>
            </div>
        </div>
    </section>

    <footer class="bg-black py-16 border-t border-slate-900">
        <div class="max-w-7xl mx-auto px-6 text-center">
            <p class="hero-font text-slate-600 text-sm tracking-widest">© 2026 NOWAF VISION | CREATING THE FUTURE</p>
        </div>
    </footer>

    <script>
        // --- LOADER & MUSIC START ---
        window.addEventListener('load', () => {
            const loader = document.getElementById('loader-wrapper');
            setTimeout(() => {
                loader.style.opacity = '0';
                loader.style.visibility = 'hidden';
                // Try playing music (Browsers require interaction)
                document.body.addEventListener('click', () => {
                    document.getElementById('bgMusic').play();
                }, { once: true });
            }, 1500);
        });

        // --- SOUND & HAPTIC LOGIC ---
        function playClick() {
            const clickSnd = document.getElementById('clickSound');
            clickSnd.currentTime = 0;
            clickSnd.play();
            if (navigator.vibrate) navigator.vibrate(12);
        }

        // --- SCROLL REVEAL ---
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) entry.target.classList.add('active');
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

        // --- MOBILE HAPTICS ---
        const hapticElements = document.querySelectorAll('.haptic-trigger, .bounce-card');
        hapticElements.forEach(element => {
            element.addEventListener('touchstart', () => {
                if (navigator.vibrate) navigator.vibrate(10); 
            });
        });
    </script>

</body>
</html>
