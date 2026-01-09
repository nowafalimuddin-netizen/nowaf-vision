<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nowaf Vision | Ultra Pro Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Inter:wght@300;500;700&display=swap" rel="stylesheet">
    <style>
        :root { --neon: #00f2ff; --purple: #ba01ff; --bg: #020617; }
        body { font-family: 'Inter', sans-serif; background-color: var(--bg); color: white; overflow-x: hidden; scroll-behavior: smooth; }
        .hero-font { font-family: 'Orbitron', sans-serif; }

        /* --- LIQUID GLASS MIXTURE EFFECT --- */
        .liquid-glass-mix {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.03) 0%, rgba(255, 255, 255, 0.01) 100%);
            backdrop-filter: blur(15px) saturate(150%);
            border-left: 4px solid var(--neon);
            position: relative;
            overflow: hidden;
        }
        .liquid-glass-mix::after {
            content: '';
            position: absolute;
            top: -50%; left: -50%; width: 200%; height: 200%;
            background: radial-gradient(circle, rgba(186, 1, 255, 0.08) 0%, transparent 60%);
            animation: liquid-flow 10s infinite alternate;
            z-index: -1;
        }
        @keyframes liquid-flow {
            0% { transform: translate(-10%, -10%); }
            100% { transform: translate(10%, 10%); }
        }

        /* --- ADVANCED LOADING SCREEN --- */
        #loader {
            position: fixed; inset: 0; background: var(--bg); z-index: 9999;
            display: flex; flex-direction: column; justify-content: center; align-items: center;
            transition: transform 1s cubic-bezier(1, 0, 0, 1);
        }
        .orbit-box { width: 100px; height: 100px; position: relative; }
        .orbit { border: 2px solid var(--neon); border-radius: 50%; position: absolute; inset: 0; animation: spin 2s linear infinite; }
        .orbit-inner { border: 2px solid var(--purple); border-radius: 50%; position: absolute; inset: 15px; animation: spin 1s linear reverse infinite; }
        @keyframes spin { 100% { transform: rotate(360deg); } }

        /* --- PRO SMOOTHNESS --- */
        .reveal { opacity: 0; transform: translateY(30px); transition: 1.2s cubic-bezier(0.2, 1, 0.2, 1); will-change: transform, opacity; }
        .reveal.active { opacity: 1; transform: translateY(0); }

        /* --- GAME STYLES --- */
        #game-canvas {
            background: rgba(0, 0, 0, 0.4);
            border-radius: 1.5rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            cursor: crosshair;
        }
        
        .hero-section {
            background: radial-gradient(circle at center, rgba(186, 1, 255, 0.05) 0%, transparent 70%), 
                        linear-gradient(rgba(2, 6, 23, 0.8), rgba(2, 6, 23, 0.95)), 
                        url('nowaf-vision.jpg');
            background-size: cover; background-position: center; min-height: 100vh;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.01); backdrop-filter: blur(25px);
            border: 1px solid rgba(255, 255, 255, 0.05); transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .glass-card:hover { border-color: var(--neon); box-shadow: 0 0 30px rgba(0, 242, 255, 0.1); transform: translateY(-10px) scale(1.02); }

        .neon-text { color: white; text-shadow: 0 0 20px rgba(186, 1, 255, 0.8); }
        .post-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 2rem; }
        iframe { width: 100%; aspect-ratio: 16/9; border-radius: 1.5rem; }
    </style>
</head>
<body class="haptic-area">

    <div id="loader">
        <div class="orbit-box">
            <div class="orbit"></div>
            <div class="orbit-inner"></div>
        </div>
        <p class="mt-8 hero-font tracking-[0.5em] text-cyan-400 animate-pulse">SYSTEM STARTING</p>
    </div>

    <audio id="bgMusic" loop>
        <source src="https://assets.mixkit.co/music/preview/mixkit-dreaming-big-31.mp3" type="audio/mpeg">
    </audio>
    <audio id="clickSound">
        <source src="https://www.soundjay.com/buttons/sounds/button-16.mp3" type="audio/mpeg">
    </audio>

    <nav class="fixed w-full z-50 border-b border-white/5 bg-slate-950/20 backdrop-blur-xl">
        <div class="max-w-7xl mx-auto px-8 py-5 flex justify-between items-center">
            <div class="hero-font text-xl font-bold tracking-tighter">NOWAF <span class="text-cyan-400">VISION</span></div>
            <div class="flex gap-8 text-xs font-bold tracking-widest uppercase opacity-60">
                <a href="#vault" class="hover:text-cyan-400 transition">Vault</a>
                <a href="#game-section" class="hover:text-cyan-400 transition">Arcade</a>
                <a href="#connect" class="hover:text-cyan-400 transition">Connect</a>
            </div>
        </div>
    </nav>

    <header class="hero-section flex items-center justify-center px-6">
        <div class="max-w-5xl text-center reveal" id="hero-reveal">
            <h1 class="text-7xl md:text-[10rem] font-bold hero-font tracking-tighter neon-text leading-none mb-4">
                NOWAF
            </h1>
            <p class="text-cyan-400 hero-font tracking-[1em] uppercase text-sm md:text-xl mb-12">Visual Architect</p>
            <div class="flex justify-center gap-6">
                <button onclick="playTap()" class="glass-card px-12 py-4 rounded-full font-bold uppercase tracking-widest text-xs border border-white/10 hover:bg-white hover:text-black transition">Explore Vault</button>
            </div>
        </div>
    </header>

    <section id="game-section" class="py-32 px-8 bg-slate-950/40">
        <div class="max-w-4xl mx-auto text-center">
            <h2 class="hero-font text-3xl mb-12 tracking-tighter liquid-glass-mix py-4 px-6 inline-block rounded-r-xl">NEON SNAKE ARCADE</h2>
            <div class="glass-card p-6 rounded-[2.5rem] relative overflow-hidden">
                <canvas id="game-canvas" width="400" height="400" class="w-full max-w-[400px] mx-auto"></canvas>
                <div class="mt-6 flex justify-between items-center hero-font text-[10px] tracking-widest text-slate-500">
                    <span>SCORE: <span id="score" class="text-cyan-400">0</span></span>
                    <span class="animate-pulse">USE ARROWS OR SWIPE TO PLAY</span>
                </div>
            </div>
        </div>
    </section>

    <section id="vault" class="py-32 px-8">
        <div class="max-w-7xl mx-auto">
            <h2 class="hero-font text-3xl mb-20 tracking-tighter border-l-4 border-cyan-400 pl-6 liquid-glass-mix py-2">DATA VAULT</h2>
            
            <div class="post-container">
                <div class="glass-card p-4 rounded-[2rem] reveal">
                    <iframe src="https://www.youtube.com/embed?listType=user_uploads&list=nowafvision" frameborder="0" allowfullscreen></iframe>
                    <div class="mt-6 flex justify-between px-2">
                        <span class="text-xs hero-font opacity-40 uppercase">YouTube Broadcast</span>
                        <button onclick="handleLike(this)" class="text-pink-500">❤️ <span class="like-count text-white ml-2">10k</span></button>
                    </div>
                </div>

                <div class="glass-card p-4 rounded-[2rem] reveal">
                    <div class="aspect-video bg-slate-900 rounded-[1.5rem] flex items-center justify-center overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1550745165-9bc0b252726f" class="w-full h-full object-cover opacity-40" alt="">
                        <div class="absolute hero-font text-xs tracking-widest bg-black/60 px-4 py-2 rounded-full">LIVE FEED</div>
                    </div>
                    <div class="mt-6 flex justify-between px-2">
                        <span class="text-xs hero-font opacity-40 uppercase">Instagram Capture</span>
                        <button onclick="handleLike(this)" class="text-pink-500">❤️ <span class="like-count text-white ml-2">4.2k</span></button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="connect" class="py-32 bg-slate-900/20 haptic-area">
        <div class="max-w-7xl mx-auto px-8 grid md:grid-cols-3 gap-8">
            <a href="https://youtube.com/@nowafvision" target="_blank" onclick="playTap()" class="glass-card p-12 rounded-[3rem] text-center reveal">
                <div class="text-4xl mb-4">📺</div>
                <div class="hero-font text-sm tracking-widest">YOUTUBE</div>
            </a>
            <a href="https://instagram.com/nowaf.khan" target="_blank" onclick="playTap()" class="glass-card p-12 rounded-[3rem] text-center reveal">
                <div class="text-4xl mb-4">📸</div>
                <div class="hero-font text-sm tracking-widest">INSTAGRAM</div>
            </a>
            <a href="#" target="_blank" onclick="playTap()" class="glass-card p-12 rounded-[3rem] text-center reveal">
                <div class="text-4xl mb-4">🌀</div>
                <div class="hero-font text-sm tracking-widest">FACEBOOK</div>
            </a>
        </div>
    </section>

    <footer class="py-20 text-center border-t border-white/5 opacity-20">
        <p class="hero-font text-xs tracking-[0.5em]">© 2026 NOWAF VISION // ACCESS GRANTED</p>
    </footer>

    <script>
        // --- PRO LOADER LOGIC ---
        window.addEventListener('load', () => {
            const loader = document.getElementById('loader');
            setTimeout(() => {
                loader.style.transform = 'translateY(-100%)';
                document.getElementById('hero-reveal').classList.add('active');
            }, 2000);
        });

        // --- HAPTIC ENGINE (Touch any section) ---
        function triggerHaptic(duration = 10) {
            if (navigator.vibrate) navigator.vibrate(duration);
        }

        document.querySelectorAll('section, nav, footer, .glass-card').forEach(el => {
            el.addEventListener('touchstart', () => triggerHaptic(5));
        });

        // --- AUDIO ENGINE ---
        const bgMusic = document.getElementById('bgMusic');
        const clickSound = document.getElementById('clickSound');

        function playTap() {
            clickSound.currentTime = 0;
            clickSound.play().catch(()=>{}); 
            triggerHaptic(20);
        }

        // Start background music on the first user interaction
        document.body.addEventListener('click', () => {
            if (bgMusic.paused) {
                bgMusic.volume = 0;
                bgMusic.play().then(() => {
                    // Smoothly fade in volume
                    let vol = 0;
                    let fade = setInterval(() => {
                        if (vol < 0.4) {
                            vol += 0.05;
                            bgMusic.volume = vol;
                        } else {
                            clearInterval(fade);
                        }
                    }, 200);
                }).catch(()=>{});
            }
        }, { once: true });

        function handleLike(btn) {
            playTap();
            const countTag = btn.querySelector('.like-count');
            countTag.innerText = (parseFloat(countTag.innerText) + 0.1).toFixed(1) + 'k';
            btn.style.transform = "scale(1.5)";
            setTimeout(() => btn.style.transform = "scale(1)", 200);
        }

        // --- CYBER SNAKE GAME LOGIC ---
        const canvas = document.getElementById('game-canvas');
        const ctx = canvas.getContext('2d');
        const scoreEl = document.getElementById('score');
        let box = 20, score = 0, snake = [{x: 9 * box, y: 10 * box}], food = {x: 5*box, y: 5*box}, d;

        document.addEventListener("keydown", e => {
            if(e.keyCode == 37 && d != "RIGHT") d = "LEFT";
            if(e.keyCode == 38 && d != "DOWN") d = "UP";
            if(e.keyCode == 39 && d != "LEFT") d = "RIGHT";
            if(e.keyCode == 40 && d != "UP") d = "DOWN";
            triggerHaptic(5);
        });

        function drawGame() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for(let i=0; i<snake.length; i++) {
                ctx.fillStyle = (i==0) ? "#00f2ff" : "rgba(0, 242, 255, 0.3)";
                ctx.shadowBlur = 10; ctx.shadowColor = "#00f2ff";
                ctx.fillRect(snake[i].x, snake[i].y, box, box);
            }
            ctx.fillStyle = "#ba01ff"; ctx.shadowColor = "#ba01ff";
            ctx.fillRect(food.x, food.y, box, box);

            let sX = snake[0].x, sY = snake[0].y;
            if(d == "LEFT") sX -= box; if(d == "UP") sY -= box;
            if(d == "RIGHT") sX += box; if(d == "DOWN") sY += box;

            if(sX == food.x && sY == food.y) {
                score++; scoreEl.innerHTML = score;
                food = { x: Math.floor(Math.random()*19+1)*box, y: Math.floor(Math.random()*19+1)*box };
                triggerHaptic(30);
            } else { snake.pop(); }

            let newH = {x: sX, y: sY};
            if(sX < 0 || sX >= canvas.width || sY < 0 || sY >= canvas.height || snake.some(t => t.x == newH.x && t.y == newH.y)) {
                clearInterval(game); triggerHaptic([50, 50, 50]);
            }
            snake.unshift(newH);
        }
        let game = setInterval(drawGame, 120);

        // --- SCROLL ENGINE ---
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('active'); });
        }, { threshold: 0.1 });
        document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
    </script>
</body>
</html>
