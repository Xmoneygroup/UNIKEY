<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elite Domain Sales | dubinv.com</title>
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Syncopate:wght@700&family=Space+Grotesk:wght@300;400;600;700&display=swap');

        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            background-color: #000;
            font-family: 'Space Grotesk', sans-serif;
        }

        #canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }

        .main-wrapper {
            position: relative;
            z-index: 10;
            width: 100%;
            height: 100vh;
            display: flex;
            flex-direction: row;
            justify-content: center; 
            align-items: center;     
            gap: 60px;                
            padding: 20px;
            padding-bottom: 180px;
            box-sizing: border-box;
            pointer-events: none;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.05); 
            backdrop-filter: blur(8px); 
            -webkit-backdrop-filter: blur(8px);
            width: 570px; 
            padding: 60px; 
            border-radius: 40px;
            text-align: left;
            box-shadow: 0 30px 60px rgba(0,0,0,0.3);
            pointer-events: auto;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .badge-container {
            display: flex;
            gap: 12px;
            margin-bottom: 20px;
        }

        .badge {
            display: flex;
            align-items: center;
            gap: 6px;
            padding: 6px 14px;
            border-radius: 100px;
            font-size: 0.75rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .verified-badge {
            background: rgba(0, 242, 255, 0.15);
            color: #00f2ff;
            border: 1px solid rgba(0, 242, 255, 0.3);
        }

        .premium-badge {
            background: rgba(255, 215, 0, 0.15);
            color: #ffd700;
            border: 1px solid rgba(255, 215, 0, 0.3);
        }

        .badge span {
            font-size: 14px;
        }

        .glass-card h2 {
            color: #fff;
            font-size: 2rem; 
            margin: 0 0 15px 0;
            font-weight: 600;
            letter-spacing: -0.5px;
        }

        .glass-card .domain-line {
            display: block;
            margin-bottom: 35px;
        }

        .glass-card .domain-name {
            color: rgba(255,255,255,0.8);
            font-weight: 300;
            font-size: 1.1rem;
            margin: 0 0 8px 0;
        }

        .glass-card .price {
            font-size: 1.8rem;
            font-weight: 700;
            color: #fff;
            margin: 0;
            letter-spacing: 0.5px;
        }

        .next-btn {
            display: block;
            width: 100%;
            padding: 20px;
            background: #fff;
            color: #000;
            text-decoration: none;
            font-weight: 600;
            border-radius: 20px;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            text-align: center;
            font-size: 1.1rem;
        }

        .next-btn:hover {
            background: rgba(255,255,255,0.9);
            transform: scale(0.98);
        }

        .contact-info {
            color: rgba(255,255,255,0.5);
            font-size: 0.9rem;
            margin-top: 40px;
            text-align: center;
        }

        .phone-link {
            color: #fff;
            text-decoration: none;
            font-size: 1.4rem;
            font-weight: 600;
            display: block;
            margin-top: 10px;
        }

        .info-panel {
            text-align: left;
            color: #fff;
        }

        .info-domain {
            font-family: 'Syncopate', sans-serif;
            font-size: 3.5rem;
            margin: 0;
            letter-spacing: 2px;
            text-transform: lowercase;
            text-shadow: 0 0 30px rgba(255,255,255,0.2);
        }

        .info-status {
            font-size: 1.6rem;
            font-weight: 300;
            opacity: 0.8;
            margin-top: 5px;
            margin-bottom: 40px;
            text-transform: uppercase;
            letter-spacing: 3px;
        }

        .trust-list {
            display: flex;
            flex-direction: column;
            gap: 20px;
            align-items: flex-start;
        }

        .trust-item {
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 1rem;
            color: rgba(255,255,255,0.8);
            font-weight: 300;
        }

        .trust-item span {
            font-size: 1.4rem;
            color: #00f2ff;
        }

        @media (max-width: 1000px) {
            .main-wrapper { flex-direction: column; gap: 40px; padding-bottom: 40px; }
            .info-panel { text-align: center; }
            .trust-list { align-items: center; }
            .glass-card { width: 90%; max-width: 570px; padding: 40px; }
            .info-domain { font-size: 2.5rem; }
        }
    </style>
</head>
<body>

    <canvas id="canvas"></canvas>

    <div class="main-wrapper">
        <div class="glass-card">
            <div class="badge-container">
                <div class="badge verified-badge">
                    <span class="material-icons">verified</span> verified
                </div>
                <div class="badge premium-badge">
                    <span class="material-icons">stars</span> premium domain
                </div>
            </div>

            <h2>Buy Now</h2>
            <div class="domain-line">
                <p class="domain-name">dubinv.com is for sale now</p>
                <p class="price">20,000 USD</p>
            </div>
            
            <a href="VENDO_LINKUN_TËND" class="next-btn">Next</a>
            
            <div class="contact-info">
                Need help? Give us a call<br>
                <a href="tel:+389XXXXXXXXX" class="phone-link">+389 XX XXX XXX</a> 
            </div>
        </div>

        <div class="info-panel">
            <div class="info-domain">dubinv.com</div>
            <div class="info-status">is for sale!</div>
            
            <div class="trust-list">
                <div class="trust-item">
                    <span class="material-icons">verified_user</span>
                    Simple, secure purchase & transfer
                </div>
                <div class="trust-item">
                    <span class="material-icons">public</span>
                    Trusted by customers globally
                </div>
                <div class="trust-item">
                    <span class="material-icons">support_agent</span>
                    24/7 dedicated support
                </div>
            </div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');
        let width, height;

        function setCanvasSize() {
            width = canvas.width = window.innerWidth;
            height = canvas.height = window.innerHeight;
        }
        setCanvasSize();
        window.addEventListener('resize', setCanvasSize);

        // --- Konfigurimi i Animacionit të Ndërtimit ---
        const constructionColor = '#00f2ff'; // Neon Cyan
        const constructionGlow = '#00c3ff';
        const finishedBuildingColor = '#1a1a1a'; // Dark grey silhouette
        const buildingSpeed = 2; // Sa pikselë ngrihet në çdo frame
        
        let buildings = [];
        let fireworks = [];
        let particles = [];

        // Krijo strukturat e ndërtesave (siluetat ikonike të Dubait)
        function initBuildings() {
            buildings = [];
            const numBuildings = Math.floor(width / 100); // Një ndërtesë çdo 100px
            
            for (let i = 0; i < numBuildings; i++) {
                // Përcakto llojin e ndërtesës (Burj Khalifa, Cayan Tower, etj.)
                const typeRand = Math.random();
                let bWidth, bHeight, complexity;
                
                if (typeRand > 0.8) { // Burj Khalifa style
                    bWidth = 30 + Math.random() * 20;
                    bHeight = height * 0.6 + Math.random() * (height * 0.3);
                    complexity = 'spire';
                } else if (typeRand > 0.5) { // Twisting tower style
                    bWidth = 40 + Math.random() * 20;
                    bHeight = height * 0.4 + Math.random() * (height * 0.3);
                    complexity = 'twist';
                } else { // Standard block
                    bWidth = 50 + Math.random() * 30;
                    bHeight = height * 0.3 + Math.random() * (height * 0.3);
                    complexity = 'block';
                }

                buildings.push({
                    x: i * 100 + (Math.random() * 20 - 10) + 50, // Pozicioni X
                    y: height, // Fillon nga fundi
                    targetHeight: bHeight,
                    width: bWidth,
                    currentHeight: 0, // Sa është ndërtuar aktualisht
                    status: 'constructing', // constructing, finished
                    complexity: complexity,
                    color: finishedBuildingColor
                });
            }
        }
        initBuildings();
        window.addEventListener('resize', initBuildings); // Rikrijo kur ndryshon ekrani

        // --- Klasat e Fishekzjarreve (Ndryshuar për të shpërthyer pas ndërtesave) ---
        class Firework {
            constructor(x, targetY) {
                this.x = x;
                this.y = height;
                this.targetY = targetY;
                this.speed = 4 + Math.random() * 2;
                this.angle = -Math.PI / 2 + (Math.random() * 0.1 - 0.05);
                this.velocity = { x: Math.cos(this.angle) * this.speed, y: Math.sin(this.angle) * this.speed };
                this.dead = false;
                this.trail = [];
            }
            update() {
                this.trail.push({x: this.x, y: this.y});
                if (this.trail.length > 10) this.trail.shift();
                this.x += this.velocity.x;
                this.y += this.velocity.y;
                if (this.y <= this.targetY) { this.explode(); this.dead = true; }
            }
            draw() {
                ctx.beginPath(); ctx.strokeStyle = "rgba(255, 255, 255, 0.2)"; ctx.lineWidth = 1;
                if(this.trail.length > 0) { ctx.moveTo(this.trail[0].x, this.trail[0].y); ctx.lineTo(this.x, this.y); ctx.stroke(); }
            }
            explode() {
                // Ngjyra luksoze dhe neon (ari, argjend, cyan, vjollcë)
                const colors = ['#FFD700', '#FFFFFF', '#00f2ff', '#ff00ee', '#ffd700', '#ffffff'];
                const color = colors[Math.floor(Math.random() * colors.length)];
                const explosionSize = 50 + Math.random() * 100;
                for (let i = 0; i < explosionSize; i++) { particles.push(new Particle(this.x, this.y, color)); }
            }
        }

        class Particle {
            constructor(x, y, color) {
                this.x = x; this.y = y; this.color = color;
                const angle = Math.random() * Math.PI * 2;
                const force = Math.random() * 9;
                this.velocity = { x: Math.cos(angle) * force, y: Math.sin(angle) * force };
                this.alpha = 1; this.friction = 0.95; this.gravity = 0.12; this.size = Math.random() * 2 + 0.5;
            }
            draw() {
                ctx.save(); ctx.globalAlpha = this.alpha; ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2); ctx.fillStyle = this.color;
                ctx.shadowBlur = 10; ctx.shadowColor = this.color; ctx.fill(); ctx.restore();
            }
            update() {
                this.velocity.x *= this.friction; this.velocity.y *= this.friction; this.velocity.y += this.gravity;
                this.x += this.velocity.x; this.y += this.velocity.y; this.alpha -= 0.01;
            }
        }

        // --- Loop-i Kryesor i Animacionit ---
        function animate() {
            // Pastro canvasin me një fade të lehtë për trail-et
            ctx.fillStyle = 'rgba(0, 0, 0, 0.2)'; 
            ctx.fillRect(0, 0, width, height);

            // --- 1. Vizato Fishekzjarret (SHTRESA E PASME) ---
            // Ata vizatohen para ndërtesave që të duken "mbrapa" tyre
            fireworks.forEach((fw, index) => { fw.update(); fw.draw(); if (fw.dead) fireworks.splice(index, 1); });
            particles.forEach((p, index) => { p.update(); p.draw(); if (p.alpha <= 0) particles.splice(index, 1); });

            // --- 2. Vizato dhe Përditëso Ndërtesat (SHTRESA E MESME) ---
            let allFinished = true;
            buildings.forEach(b => {
                ctx.save();
                
                // Efekti Glow kur ndërtohet
                if (b.status === 'constructing') {
                    ctx.shadowBlur = 15;
                    ctx.shadowColor = constructionGlow;
                    ctx.strokeStyle = constructionColor;
                    ctx.lineWidth = 2;
                    allFinished = false;
                } else {
                    ctx.shadowBlur = 5;
                    ctx.shadowColor = 'rgba(26, 26, 26, 0.5)';
                    ctx.strokeStyle = 'rgba(255, 255, 255, 0.1)'; // Kufiri i hollë i xhamit kur mbaron
                    ctx.lineWidth = 1;
                }

                // Vizato siluetën e ndërtesës
                ctx.beginPath();
                
                if (b.complexity === 'spire') { // Burj Style
                    ctx.moveTo(b.x - b.width/2, height);
                    ctx.lineTo(b.x - b.width/2, height - b.currentHeight * 0.7);
                    ctx.lineTo(b.x - b.width/4, height - b.currentHeight * 0.9);
                    ctx.lineTo(b.x, height - b.currentHeight); // Maja
                    ctx.lineTo(b.x + b.width/4, height - b.currentHeight * 0.9);
                    ctx.lineTo(b.x + b.width/2, height - b.currentHeight * 0.7);
                    ctx.lineTo(b.x + b.width/2, height);
                } else if (b.complexity === 'twist') { // Twisted style
                    const sections = 10;
                    ctx.moveTo(b.x - b.width/2, height);
                    for(let i=1; i<=sections; i++) {
                        const h = (b.currentHeight / sections) * i;
                        const twist = Math.sin(i * 0.5) * 10;
                        ctx.lineTo(b.x - b.width/2 + twist, height - h);
                    }
                    ctx.lineTo(b.x + b.width/2, height - b.currentHeight);
                    for(let i=sections; i>=0; i--) {
                        const h = (b.currentHeight / sections) * i;
                        const twist = Math.sin(i * 0.5) * 10;
                        ctx.lineTo(b.x + b.width/2 + twist, height - h);
                    }
                } else { // Block style
                    ctx.rect(b.x - b.width/2, height - b.currentHeight, b.width, b.currentHeight);
                }

                // Mbush ndërtesën (siluetë e errët)
                ctx.fillStyle = b.color;
                ctx.fill();
                ctx.stroke(); // Vizato vijat neon

                // Shto dritare të vogla kur mbaron
                if (b.status === 'finished') {
                    ctx.fillStyle = Math.random() > 0.98 ? finishedBuildingColor : 'rgba(255, 255, 255, 0.3)'; // Dritare që nisin e fiken
                    for (let wy = height - b.currentHeight + 20; wy < height - 20; wy += 20) {
                        for (let wx = b.x - b.width/2 + 10; wx < b.x + b.width/2 - 10; wx += 15) {
                            if (Math.random() > 0.3) ctx.fillRect(wx, wy, 3, 3);
                        }
                    }
                }
                
                ctx.restore();

                // Përditëso lartësinë (procesi i ndërtimit)
                if (b.status === 'constructing') {
                    b.currentHeight += buildingSpeed;
                    if (b.currentHeight >= b.targetHeight) {
                        b.currentHeight = b.targetHeight;
                        b.status = 'finished';
                        b.color = finishedBuildingColor; // Ngjyra përfundimtare e errët
                        // Shpërthe një fishekzjarr MBRAK ndërtesës kur mbaron
                        fireworks.push(new Firework(b.x, height - b.targetHeight - Math.random() * 50));
                    }
                }
            });

            // Nëse të gjitha mbaruan, rifillo ndërtimin pas një kohe
            if (allFinished && Math.random() < 0.005) { // 0.5% shans në çdo frame pas mbarimit
                 initBuildings();
            }

            requestAnimationFrame(animate);
        }
        animate();
    </script>
</body>
</html>
