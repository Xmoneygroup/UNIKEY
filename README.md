<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elite Domain Sales | dubrent.com</title>
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

        .badge span { font-size: 14px; }

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
        <div class="glass-card" id="target-card">
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
        const cardElement = document.getElementById('target-card');
        let width, height;

        function setCanvasSize() {
            width = canvas.width = window.innerWidth;
            height = canvas.height = window.innerHeight;
        }
        setCanvasSize();
        window.addEventListener('resize', setCanvasSize);

        // --- Stick Figure Class ---
        class Person {
            constructor() {
                this.init();
            }

            init() {
                this.x = Math.random() * width;
                this.y = -50;
                this.size = 15 + Math.random() * 10;
                this.color = `hsl(${Math.random() * 360}, 100%, 60%)`;
                this.speedX = (Math.random() - 0.5) * 4;
                this.speedY = 2 + Math.random() * 3;
                this.state = 'falling'; // falling, running, jumping, leaving
                this.legAngle = 0;
            }

            draw() {
                ctx.strokeStyle = this.color;
                ctx.lineWidth = 2;
                ctx.lineCap = 'round';

                const headRadius = this.size / 3;
                const bodyLen = this.size;
                
                // Head
                ctx.beginPath();
                ctx.arc(this.x, this.y, headRadius, 0, Math.PI * 2);
                ctx.stroke();

                // Body
                ctx.beginPath();
                ctx.moveTo(this.x, this.y + headRadius);
                ctx.lineTo(this.x, this.y + headRadius + bodyLen);
                ctx.stroke();

                // Legs
                let angle = Math.sin(this.legAngle) * 0.5;
                ctx.beginPath(); // Left leg
                ctx.moveTo(this.x, this.y + headRadius + bodyLen);
                ctx.lineTo(this.x - 10 * Math.sin(angle + 0.5), this.y + headRadius + bodyLen + 15);
                ctx.stroke();

                ctx.beginPath(); // Right leg
                ctx.moveTo(this.x, this.y + headRadius + bodyLen);
                ctx.lineTo(this.x + 10 * Math.sin(angle + 0.5), this.y + headRadius + bodyLen + 15);
                ctx.stroke();

                // Arms
                ctx.beginPath();
                ctx.moveTo(this.x, this.y + headRadius + 5);
                ctx.lineTo(this.x - 10, this.y + headRadius + 15 + (this.state === 'jumping' ? -20 : 0));
                ctx.stroke();
                ctx.beginPath();
                ctx.moveTo(this.x, this.y + headRadius + 5);
                ctx.lineTo(this.x + 10, this.y + headRadius + 15 + (this.state === 'jumping' ? -20 : 0));
                ctx.stroke();
            }

            update() {
                const rect = cardElement.getBoundingClientRect();
                const cardX = rect.left + rect.width / 2;
                const cardY = rect.top;

                if (this.state === 'falling') {
                    this.y += this.speedY;
                    if (this.y > height - 100) this.state = 'running';
                } 
                else if (this.state === 'running') {
                    this.legAngle += 0.2;
                    let dir = this.x < cardX ? 1 : -1;
                    this.x += 3 * dir;
                    if (Math.abs(this.x - cardX) < 150) this.state = 'jumping';
                } 
                else if (this.state === 'jumping') {
                    this.y -= 5;
                    this.x += (this.x < cardX ? 2 : -2);
                    if (this.y < cardY - 20) this.state = 'leaving';
                } 
                else if (this.state === 'leaving') {
                    this.legAngle += 0.3;
                    this.y += 7;
                    this.x += (this.x < width / 2 ? -4 : 4);
                    if (this.y > height + 50 || this.x < -50 || this.x > width + 50) this.init();
                }
            }
        }

        // --- Raketat (Rralluar) ---
        class Firework {
            constructor() {
                this.x = Math.random() * width;
                this.y = height;
                this.targetY = Math.random() * (height * 0.5);
                this.speed = 4;
                this.dead = false;
            }
            update() {
                this.y -= this.speed;
                if (this.y <= this.targetY) { this.explode(); this.dead = true; }
            }
            draw() {
                ctx.fillStyle = "white";
                ctx.beginPath(); ctx.arc(this.x, this.y, 2, 0, Math.PI*2); ctx.fill();
            }
            explode() {
                for (let i = 0; i < 30; i++) { particles.push(new Particle(this.x, this.y)); }
            }
        }

        class Particle {
            constructor(x, y) {
                this.x = x; this.y = y;
                this.color = `hsl(${Math.random() * 360}, 100%, 50%)`;
                this.vel = { x: (Math.random() - 0.5) * 8, y: (Math.random() - 0.5) * 8 };
                this.alpha = 1;
            }
            update() {
                this.x += this.vel.x; this.y += this.vel.y; this.alpha -= 0.02;
            }
            draw() {
                ctx.globalAlpha = this.alpha;
                ctx.fillStyle = this.color;
                ctx.beginPath(); ctx.arc(this.x, this.y, 2, 0, Math.PI*2); ctx.fill();
                ctx.globalAlpha = 1;
            }
        }

        let people = Array.from({ length: 6 }, () => new Person());
        let fireworks = [];
        let particles = [];

        function animate() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.2)';
            ctx.fillRect(0, 0, width, height);

            // Raketat (Rralluar: 0.01 probabilitet)
            if (Math.random() < 0.01) fireworks.push(new Firework());

            fireworks.forEach((f, i) => { f.update(); f.draw(); if (f.dead) fireworks.splice(i, 1); });
            particles.forEach((p, i) => { p.update(); p.draw(); if (p.alpha <= 0) particles.splice(i, 1); });
            
            people.forEach(p => { p.update(); p.draw(); });

            requestAnimationFrame(animate);
        }
        animate();
    </script>
</body>
</html>
