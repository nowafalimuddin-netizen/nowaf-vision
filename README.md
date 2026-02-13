 <head>
    <title>🙏Hello,Sir🙏 </title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
      <h1 class="title">🙏Hello,Sir🙏!</h1>
      <p id="currentTime"></p>
      <script src="script.js"></script>
  </body>
</html<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="google-site-verification" content="UDBMyidqHaPIXk4PPKCqdxjyA-zHEpt5-Ykek4RMfE4" />
    
    <title>Nowaf Vision | Winter Edition</title>
    <meta name="title" content="Nowaf Vision | Visual Architect">
    <meta name="description" content="Access the cinematic vault of Nowaf Vision. Explore visual architecture and neon arcade experiences.">

    <meta property="og:type" content="website">
    <meta property="og:url" content="https://nowafvision.com/">
    <meta property="og:title" content="Nowaf Vision | Visual Architect">
    <meta property="og:description" content="Explore the official portfolio and neon arcade of Nowaf Vision.">
    <meta property="og:image" content="https://img.youtube.com/vi/Xks2aV1YnIo/maxresdefault.jpg">

    <meta property="twitter:card" content="summary_large_image">
    <meta property="twitter:title" content="Nowaf Vision">
    <meta property="twitter:description" content="Visual Architect & Digital Creator.">
    <meta property="twitter:image" content="https://img.youtube.com/vi/Xks2aV1YnIo/maxresdefault.jpg">

    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Inter:wght@300;500;700&display=swap" rel="stylesheet">
    <style>
        /* --- VARIABLES --- */
        :root { --neon: #00f2ff; --purple: #ba01ff; --bg: #0b1121; --text: #ffffff; --glass: rgba(255, 255, 255, 0.05); }
        
        /* LIGHT THEME OVERRIDES */
        body.light-mode { --bg: #f1f5f9; --text: #0f172a; --glass: rgba(255, 255, 255, 0.6); --neon: #0ea5e9; --purple: #6d28d9; }
        body.light-mode .neon-text { color: #0f172a; text-shadow: none; }
        body.light-mode .snowflake { background: #cbd5e1; } 

        body { font-family: 'Inter', sans-serif; background-color: var(--bg); color: var(--text); overflow-x: hidden; scroll-behavior: smooth; transition: background 0.5s ease, color 0.5s ease; }
        .hero-font { font-family: 'Orbitron', sans-serif; } 

        /* --- WINTER SNOW ENGINE --- */
        #snow-container {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none;
            z-index: 1;
            overflow: hidden;
        }
        .snowflake {
            position: absolute;
            top: -10px;
            background: white;
            border-radius: 50%;
            opacity: 0.8;
            filter: blur(1px);
            animation: fall linear infinite;
        }
        @keyframes fall {
            0% { transform: translateY(-10vh) translateX(0); }
            100% { transform: translateY(110vh) translateX(20px); }
        } 

        /* --- SETTINGS MENU STYLES --- */
        #settings-dropdown {
            display: none;
            position: absolute;
            top: 60px; right: 0; width: 200px;
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(20px);
            border: 1px solid var(--neon);
            border-radius: 1rem;
            padding: 1.5rem;
            box-shadow: 0 10px 40px rgba(0,0,0,0.5);
            z-index: 1000;
        }
        body.light-mode #settings-dropdown { background: rgba(255, 255, 255, 0.95); } 

        /* --- LIQUID GLASS MIXTURE EFFECT --- */
        .liquid-glass-mix {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.03) 0%, rgba(255, 255, 255, 0.01) 100%);
            backdrop-filter: blur(15px) saturate(150%);
            border-left: 4px solid var(--neon);
            position: relative; overflow: hidden;
        }
        .liquid-glass-mix::after {
            content: ''; position: absolute; top: -50%; left: -50%; width: 200%; height: 200%;
            background: radial-gradient(circle, rgba(186, 1, 255, 0.08) 0%, transparent 60%);
            animation: liquid-flow 10s infinite alternate; z-index: -1;
        }
        @keyframes liquid-flow { 0% { transform: translate(-10%, -10%); } 100% { transform: translate(10%, 10%); } } 

        /* --- LOADER --- */
        #loader {
            position: fixed; inset: 0; background: var(--bg); z-index: 9999;
            display: flex; flex-direction: column; justify-content: center; align-items: center;
            transition: transform 1s cubic-bezier(1, 0, 0, 1);
        }
        .orbit-box { width: 100px; height: 100px; position: relative; }
        .orbit { border: 2px solid var(--neon); border-radius: 50%; position: absolute; inset: 0; animation: spin 2s linear infinite; }
        .orbit-inner { border: 2px solid var(--purple); border-radius: 50%; position: absolute; inset: 15px; animation: spin 1s linear reverse infinite; }
        @keyframes spin { 100% { transform: rotate(360deg); } } 

        .reveal { opacity: 0; transform: translateY(30px); transition: 1.2s cubic-bezier(0.2, 1, 0.2, 1); will-change: transform, opacity; }
        .reveal.active { opacity: 1; transform: translateY(0); } 

        #game-canvas {
            background: rgba(0, 0, 0, 0.4); border-radius: 1.5rem;
            border: 1px solid rgba(255, 255, 255, 0.1); cursor: crosshair;
        }
        
        .hero-section {
            background: radial-gradient(circle at center, rgba(186, 1, 255, 0.05) 0%, transparent 70%), 
                        linear-gradient(rgba(2, 6, 23, 0.8), rgba(2, 6, 23, 0.95)), 
                        url('nowaf-vision.jpg');
            background-size: cover; background-position: center; min-height: 100vh;
        } 

        .glass-card {
            background: var(--glass); backdrop-filter: blur(25px); color: var(--text);
            border: 1px solid rgba(255, 255, 255, 0.05); transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative; z-index: 10; 
        }
        .glass-card:hover { border-color: var(--neon); box-shadow: 0 0 30px rgba(0, 242, 255, 0.1); transform: translateY(-10px) scale(1.02); } 

        .neon-text { color: white; text-shadow: 0 0 20px rgba(186, 1, 255, 0.8); }
        .post-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 2rem; }
        iframe { width: 100%; aspect-ratio: 16/9; border-radius: 1.5rem; } 

        .d-pad button {
            background: var(--glass); border: 1px solid rgba(0, 242, 255, 0.3);
            border-radius: 12px; color: var(--neon); width: 60px; height: 60px;
            font-size: 1.5rem; display: flex; align-items: center; justify-content: center; transition: all 0.2s;
            z-index: 20;
        }
        .d-pad button:active { background: var(--neon); color: black; transform: scale(0.9); }
        
        /* VIDEO MODAL STYLES */
        #videoModal { transition: opacity 0.4s ease; }
    </style>
</head>
<body class="haptic-area"> 

    <div id="snow-container"></div> 

    <div id="loader">
        <div class="orbit-box">
            <div class="orbit"></div>
            <div class="orbit-inner"></div>
        </div>
        <p class="mt-8 hero-font tracking-[0.5em] text-cyan-400 animate-pulse">SYSTEM STARTING</p>
    </div> 

    <nav class="fixed w-full z-50 border-b border-white/5 bg-slate-950/20 backdrop-blur-xl">
        <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center relative">
            <div class="flex items-center gap-4">
                <div class="hero-font text-xl font-bold tracking-tighter">NOWAF <span class="text-cyan-400">VISION</span></div>
                <button onclick="toggleSettings()" class="text-2xl text-cyan-400 focus:outline-none p-2 animate-pulse">⋮</button>
            </div> 

            <div class="hidden md:flex gap-8 text-xs font-bold tracking-widest uppercase opacity-60">
                <a href="#vault" class="hover:text-cyan-400 transition">Vault</a>
                <a href="#game-section" class="hover:text-cyan-400 transition">Arcade</a>
                <a href="#connect" class="hover:text-cyan-400 transition">Connect</a>
            </div> 

            <div id="settings-dropdown">
                <h3 class="hero-font text-cyan-400 text-xs tracking-widest mb-4 border-b border-white/10 pb-2">SYSTEM CONTROL</h3>
                <div class="mb-5">
                    <label class="text-[10px] uppercase tracking-widest mb-2 block opacity-70">Theme</label>
                    <button onclick="toggleTheme()" class="w-full py-2 border border-cyan-400/50 rounded text-[10px] hero-font hover:bg-cyan-400/20 transition">DARK / BRIGHT</button>
                </div> 
            </div>
        </div>
    </nav> 

    <header class="hero-section flex items-center justify-center px-6">
        <div class="max-w-5xl text-center reveal" id="hero-reveal">
            <h1 class="text-7xl md:text-[10rem] font-bold hero-font tracking-tighter neon-text leading-none mb-4">NOWAF</h1>
            <p class="text-cyan-400 hero-font tracking-[1em] uppercase text-sm md:text-xl mb-12">Visual Architect</p>
            <div class="flex justify-center gap-6">
                <button onclick="openModal('Xks2aV1YnIo')" class="glass-card px-12 py-4 rounded-full font-bold uppercase tracking-widest text-xs border border-white/10 hover:bg-white hover:text-black transition">Explore Vault</button>
            </div>
        </div>
    </header> 

    <section id="game-section" class="py-32 px-8 bg-slate-950/40">
        <div class="max-w-4xl mx-auto text-center">
            <h2 class="hero-font text-3xl mb-12 tracking-tighter liquid-glass-mix py-4 px-6 inline-block rounded-r-xl">NEON SNAKE ARCADE</h2>
            <div class="glass-card p-6 rounded-[2.5rem] relative overflow-hidden">
                <canvas id="game-canvas" width="400" height="400" class="w-full max-w-[400px] mx-auto"></canvas>
                <div class="md:hidden mt-8 grid grid-cols-3 gap-2 w-48 mx-auto d-pad">
                    <div></div>
                    <button onclick="handleMove('UP')" ontouchstart="handleMove('UP')">▲</button>
                    <div></div>
                    <button onclick="handleMove('LEFT')" ontouchstart="handleMove('LEFT')">◀</button>
                    <button onclick="handleMove('DOWN')" ontouchstart="handleMove('DOWN')">▼</button>
                    <button onclick="handleMove('RIGHT')" ontouchstart="handleMove('RIGHT')">▶</button>
                </div> 
                <div class="mt-6 flex justify-between items-center hero-font text-[10px] tracking-widest text-slate-500">
                    <span>SCORE: <span id="score" class="text-cyan-400">0</span></span>
                    <span class="animate-pulse">CONTROLS: ARROWS / D-PAD</span>
                </div>
            </div>
        </div>
    </section> 

    <section id="vault" class="py-32 px-8">
        <div class="max-w-7xl mx-auto">
            <h2 class="hero-font text-3xl mb-20 tracking-tighter border-l-4 border-cyan-400 pl-6 liquid-glass-mix py-2">DATA VAULT</h2>
            <div class="post-container">
                <div class="glass-card p-4 rounded-[2rem] reveal cursor-pointer" onclick="openModal('Xks2aV1YnIo')">
                    <div class="aspect-video bg-slate-900 rounded-[1.5rem] flex items-center justify-center overflow-hidden relative">
                         <img src="https://img.youtube.com/vi/Xks2aV1YnIo/maxresdefault.jpg" class="w-full h-full object-cover opacity-60" alt="Video Thumbnail">
                         <div class="absolute inset-0 flex items-center justify-center">
                            <div class="w-16 h-16 bg-cyan-400 rounded-full flex items-center justify-center text-black pl-1 shadow-2xl">▶</div>
                         </div>
                    </div>
                    <div class="mt-6 flex justify-between px-2">
                        <span class="text-xs hero-font opacity-40 uppercase">YouTube Broadcast</span>
                        <button onclick="handleLike(this); event.stopPropagation();" class="text-pink-500">❤️ <span class="like-count ml-2">10k</span></button>
                    </div>
                </div> 
                <div class="glass-card p-4 rounded-[2rem] reveal">
                    <div class="aspect-video bg-slate-900 rounded-[1.5rem] flex items-center justify-center overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1550745165-9bc0b252726f" class="w-full h-full object-cover opacity-40" alt="Instagram Feed">
                        <div class="absolute hero-font text-xs tracking-widest bg-black/60 px-4 py-2 rounded-full text-white">LIVE FEED</div>
                    </div>
                    <div class="mt-6 flex justify-between px-2">
                        <span class="text-xs hero-font opacity-40 uppercase">Instagram Capture</span>
                        <button onclick="handleLike(this)" class="text-pink-500">❤️ <span class="like-count ml-2">4.2k</span></button>
                    </div>
                </div>
            </div>
        </div>
    </section> 

    <div id="videoModal" class="fixed inset-0 z-[100] hidden flex items-center justify-center p-4 bg-black/90 backdrop-blur-sm">
        <button onclick="closeModal()" class="absolute top-6 right-6 text-white text-5xl hover:text-cyan-400 transition">&times;</button>
        <div class="w-full max-w-5xl aspect-video bg-black rounded-2xl overflow-hidden shadow-2xl border border-white/10">
            <iframe id="modalIframe" class="w-full h-full" src="" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
        </div>
    </div>

    <section id="connect" class="py-32 bg-slate-900/20 haptic-area">
        <div class="max-w-7xl mx-auto px-8 grid md:grid-cols-3 gap-8">
            <a href="https://www.youtube.com/@nowafvision" target="_blank" onclick="playTap()" class="glass-card p-12 rounded-[3rem] text-center reveal">
                <div class="text-4xl mb-4">📺</div>
                <div class="hero-font text-sm tracking-widest">YOUTUBE</div>
            </a>
            <a href="https://www.instagram.com/nowaf.khan" target="_blank" onclick="playTap()" class="glass-card p-12 rounded-[3rem] text-center reveal">
                <div class="text-4xl mb-4">📸</div>
                <div class="hero-font text-sm tracking-widest">INSTAGRAM</div>
            </a>
            <a href="https://www.facebook.com/nowaf.vision" target="_blank" onclick="playTap()" class="glass-card p-12 rounded-[3rem] text-center reveal">
                <div class="text-4xl mb-4">🌀</div>
                <div class="hero-font text-sm tracking-widest">FACEBOOK</div>
            </a>
        </div>
    </section> 

    <footer class="py-20 text-center border-t border-white/5 opacity-20">
        <p class="hero-font text-xs tracking-[0.5em]">© 2026 NOWAF VISION // ACCESS GRANTED</p>
    </footer> 

    <script>
        // --- WINTER ENGINE ---
        function createSnow() {
            const container = document.getElementById('snow-container');
            const particleCount = 60; 
            for(let i=0; i<particleCount; i++) {
                const flake = document.createElement('div');
                flake.classList.add('snowflake');
                const size = Math.random() * 5 + 2 + 'px';
                flake.style.width = size; flake.style.height = size;
                flake.style.left = Math.random() * 100 + 'vw';
                flake.style.animationDuration = Math.random() * 3 + 5 + 's';
                flake.style.animationDelay = Math.random() * 5 + 's';
                flake.style.opacity = Math.random() * 0.7 + 0.3;
                container.appendChild(flake);
            }
        } 

        // --- VIDEO MODAL LOGIC ---
        function openModal(videoId) {
            const modal = document.getElementById('videoModal');
            const iframe = document.getElementById('modalIframe');
            iframe.src = `https://www.youtube.com/embed/${videoId}?autoplay=1`;
            modal.classList.remove('hidden');
            document.body.style.overflow = 'hidden'; 
            playTap();
        }

        function closeModal() {
            const modal = document.getElementById('videoModal');
            const iframe = document.getElementById('modalIframe');
            iframe.src = ""; 
            modal.classList.add('hidden');
            document.body.style.overflow = 'auto'; 
            playTap();
        }

        window.onclick = function(event) {
            const modal = document.getElementById('videoModal');
            if (event.target == modal) { closeModal(); }
        }

        // --- THEME & SETTINGS ---
        function toggleSettings() {
            const menu = document.getElementById('settings-dropdown');
            menu.style.display = menu.style.display === 'block' ? 'none' : 'block';
            playTap();
        } 

        function toggleTheme() {
            document.body.classList.toggle('light-mode');
            playTap();
        } 

        // --- LOADER ---
        window.addEventListener('load', () => {
            createSnow(); 
            const loader = document.getElementById('loader');
            setTimeout(() => {
                loader.style.transform = 'translateY(-100%)';
                document.getElementById('hero-reveal').classList.add('active');
            }, 2000);
        }); 

        // --- HAPTICS ---
        function triggerHaptic(duration = 10) {
            if (navigator.vibrate) navigator.vibrate(duration);
        } 

        function playTap() {
            // Audio elements removed for silent interactions
            triggerHaptic(20);
        } 

        function handleLike(btn) {
            playTap();
            const countTag = btn.querySelector('.like-count');
            countTag.innerText = (parseFloat(countTag.innerText) + 0.1).toFixed(1) + 'k';
            btn.style.transform = "scale(1.5)";
            setTimeout(() => btn.style.transform = "scale(1)", 200);
        } 

        // --- SNAKE ARCADE ---
        const canvas = document.getElementById('game-canvas');
        const ctx = canvas.getContext('2d');
        const scoreEl = document.getElementById('score');
        let box = 20, score = 0, snake = [{x: 9 * box, y: 10 * box}], food = {x: 5*box, y: 5*box}, d; 

        function handleMove(dir) {
            if(dir == "LEFT" && d != "RIGHT") d = "LEFT";
            if(dir == "UP" && d != "DOWN") d = "UP";
            if(dir == "RIGHT" && d != "LEFT") d = "RIGHT";
            if(dir == "DOWN" && d != "UP") d = "DOWN";
            triggerHaptic(10);
        } 

        document.addEventListener("keydown", e => {
            if ([37, 38, 39, 40].includes(e.keyCode)) e.preventDefault();
            
            if(e.keyCode == 37) handleMove("LEFT");
            if(e.keyCode == 38) handleMove("UP");
            if(e.keyCode == 39) handleMove("RIGHT");
            if(e.keyCode == 40) handleMove("DOWN");
        }); 

        function drawGame() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for(let i=0; i<snake.length; i++) {
                ctx.fillStyle = (i==0) ? "#00f2ff" : "rgba(0, 242, 255, 0.3)";
                ctx.fillRect(snake[i].x, snake[i].y, box, box);
            }
            ctx.fillStyle = "#ba01ff"; 
            ctx.fillRect(food.x, food.y, box, box); 

            let sX = snake[0].x, sY = snake[0].y;
            if(d == "LEFT") sX -= box; if(d == "UP") sY -= box;
            if(d == "RIGHT") sX += box; if(d == "DOWN") sY += box; 

            if(sX == food.x && sY == food.y) {
                score++; scoreEl.innerHTML = score;
                food = { x: Math.floor(Math.random()*20)*box, y: Math.floor(Math.random()*20)*box };
            } else { if(d) snake.pop(); } 

            let newH = {x: sX, y: sY};
            if(d && (sX < 0 || sX >= canvas.width || sY < 0 || sY >= canvas.height || snake.some(t => t.x == newH.x && t.y == newH.y))) {
                snake = [{x: 9 * box, y: 10 * box}]; d = null; score = 0; scoreEl.innerHTML = score;
            } else if(d) {
                snake.unshift(newH);
            }
        }
        setInterval(drawGame, 120); 

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('active'); });
        }, { threshold: 0.1 });
        document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
    </script>
</body>
</html>
