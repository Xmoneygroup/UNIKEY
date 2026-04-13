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
            z-index: 20; /* Tani njerëzit janë PËRPARA pllakatës */
            pointer-events: none;
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
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.05); 
            backdrop-filter: blur(12px); 
            -webkit-backdrop-filter: blur(12px);
            width: 570px; 
            padding: 60px; 
            border-radius: 40px;
            text-align: left;
            box-shadow: 0 30px 60px rgba(0,0,0,0.5);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .badge-container { display: flex; gap: 12px; margin-bottom: 20px; }
        .badge { display: flex; align-items: center; gap: 6px; padding: 6px 14px; border-radius: 100px; font-size: 0.75rem; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; }
        .verified-badge { background: rgba(0, 242, 255, 0.15); color: #00f2ff; border: 1px solid rgba(0, 242, 255, 0.3); }
        .premium-badge { background: rgba(255, 215, 0, 0.15); color: #ffd700; border: 1px solid rgba(255, 215, 0, 0.3); }

        .glass-card h2 { color: #fff; font-size: 2rem; margin: 0 0 15px 0; font-weight: 600; }
        .domain-name { color: rgba(255,255,255,0.8); font-size: 1.1rem; margin-bottom: 8px; }
        .price { font-size: 1.8rem; font-weight: 700; color: #fff; }

        .next-btn {
            display: block;
            width: 100%;
            padding: 20px;
            background: #fff;
            color: #000;
            text-decoration: none;
            font-weight: 600;
            border-radius: 20px;
            text-align: center;
            font-size: 1.1rem;
            margin: 25px 0;
        }

        .contact-info { color: rgba(255,255,255,0.5); font-size: 0.9rem; text-align: center; }
        .phone-link { color: #fff; text-decoration: none; font-size: 1.4rem; font-weight: 600; display: block; margin-top: 10px; }

        .info-panel { text-align: left; color: #fff; }
        .info-domain { font-family: 'Syncopate', sans-serif; font-size: 3.5rem; letter-spacing: 2px; }
        .info-status { font-size: 1.6rem; font-weight: 300; opacity: 0.8; margin-bottom: 40px; letter-spacing: 3px; }

        @media (max-width: 1000px) {
            .main-wrapper { flex-direction: column; padding-bottom: 40px; }
            .glass-card { width: 90%; }
        }
    </style>
</head>
<body>

    <canvas id="canvas"></canvas>

    <div class="main-wrapper">
        <div class="glass-card" id="target-card">
            <div class="badge-container">
                <div class="badge verified-badge"><span class="material-icons">verified</span> verified</div>
                <div class="badge premium-badge"><span class="material-icons">stars</span> premium</div>
            </div>

            <h2>Buy Now</h2>
            <div class="domain-line">
                <p class="domain-name">dubinv.com is for sale now</p>
                <p class="price">20,000 USD</p>
            </div>
            
            <a href="#" class="next-btn" id="btn-next">Next</a>
            
            <div class="contact-info" id="contact-text">
                Need help? <span id="letter-c" style="color:#fff">C</span>ontact us<br>
                <a href="tel:+389XXXXXXXXX" class="phone-link">+389 XX XXX XXX</a> 
            </div>
        </div>

        <div class="info-panel">
            <div class="info-domain">dubinv.com</div>
            <div class="info-status">is for sale!</div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');
        const nextBtn = document.getElementById('btn-next');
        const letterC = document.getElementById('letter-c');
        
        let width, height;
        function setCanvasSize() {
            width = canvas.width = window.innerWidth;
            height = canvas.height = window.innerHeight;
        }
        setCanvasSize();
        window.addEventListener('resize', setCanvasSize);

        class Person {
            constructor() {
                this.init();
            }

            init() {
                this.type = Math.random() > 0.5 ? 'button' : 'letter';
                this.x = Math.random() < 0.5 ? -100 : width + 100;
                this.y = height * 0.7;
                this.color = `hsl(${Math.random() * 360}, 80%, 70%)`;
                this.state = 'walking'; // walking, climbing, sitting, falling
                this.waitStart = 0;
                this.legAngle = 0;
                this.armAngle = 0;
                this.fallSpeed = 0;
                this.rotation = 0;
            }

            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate(this.rotation);
                ctx.strokeStyle = this.color;
                ctx.lineWidth = 3;
                ctx.lineCap = 'round';

                // Kokë
                ctx.beginPath();
                ctx.arc(0, -25, 6, 0, Math.PI * 2);
                ctx.stroke();

                // Trup
                ctx.beginPath();
                ctx.moveTo(0, -19);
                ctx.lineTo(0, 0);
                ctx.stroke();

                // Duart (për tu nxhur)
                let aAnim = Math.sin(this.armAngle) * 15;
                ctx.beginPath();
                ctx.moveTo(0, -15);
                ctx.lineTo(-12, -10 + (this.state === 'climbing' ? aAnim : 0));
                ctx.moveTo(0, -15);
                ctx.lineTo(12, -10 - (this.state === 'climbing' ? aAnim : 0));
                ctx.stroke();

                // Këmbët
                if (this.state === 'sitting') {
                    ctx.beginPath();
                    ctx.moveTo(0, 0); ctx.lineTo(10, 8);
                    ctx.moveTo(0, 0); ctx.lineTo(-10, 8);
                    ctx.stroke();
                } else {
                    let lAnim = Math.sin(this.legAngle) * 12;
                    ctx.beginPath();
                    ctx.moveTo(0, 0); ctx.lineTo(-lAnim, 15);
                    ctx.moveTo(0, 0); ctx.lineTo(lAnim, 15);
                    ctx.stroke();
                }
                ctx.restore();
            }

            update() {
                const targetEl = this.type === 'button' ? nextBtn : letterC;
                const rect = targetEl.getBoundingClientRect();
                const tx = rect.left + rect.width / 2;
                const ty = rect.top;

                if (this.state === 'walking') {
                    this.legAngle += 0.1;
                    this.armAngle += 0.1;
                    this.x += (tx - this.x) * 0.01;
                    if (Math.abs(this.x - tx) < 50) this.state = 'climbing';
                } 
                else if (this.state === 'climbing') {
                    this.legAngle += 0.15;
                    this.armAngle += 0.3;
                    this.x += (tx - this.x) * 0.05;
                    this.y += (ty - this.y) * 0.05;
                    if (Math.abs(this.y - ty) < 5) {
                        this.state = 'sitting';
                        this.waitStart = Date.now();
                    }
                } 
                else if (this.state === 'sitting') {
                    if (Date.now() - this.waitStart > 2500) this.state = 'falling';
                } 
                else if (this.state === 'falling') {
                    this.fallSpeed += 0.5;
                    this.y += this.fallSpeed;
                    this.rotation += 0.1;
                    if (this.y > height + 100) this.init();
                }
            }
        }

        class Firework {
            constructor() {
                this.x = Math.random() * width;
                this.y = height;
                this.targetY = Math.random() * (height * 0.5);
                this.velY = -Math.random() * 4 - 6;
                this.dead = false;
            }
            update() {
                this.y += this.velY;
                if (this.y <= this.targetY) { this.explode(); this.dead = true; }
            }
            draw() {
                ctx.fillStyle = "#fff";
                ctx.beginPath(); ctx.arc(this.x, this.y, 3, 0, Math.PI*2); ctx.fill();
            }
            explode() {
                for (let i = 0; i < 50; i++) {
                    particles.push(new Particle(this.x, this.y));
                }
            }
        }

        class Particle {
            constructor(x, y) {
                this.x = x; this.y = y;
                this.color = `hsl(${Math.random() * 360}, 100%, 60%)`;
                this.vel = { x: (Math.random()-0.5)*12, y: (Math.random()-0.5)*12 };
                this.alpha = 1;
            }
            update() { this.x += this.vel.x; this.y += this.vel.y; this.alpha -= 0.015; }
            draw() {
                ctx.globalAlpha = this.alpha;
                ctx.fillStyle = this.color;
                ctx.shadowBlur = 10;
                ctx.shadowColor = this.color;
                ctx.beginPath(); ctx.arc(this.x, this.y, 2.5, 0, Math.PI*2); ctx.fill();
                ctx.shadowBlur = 0;
            }
        }

        let people = Array.from({ length: 4 }, () => new Person());
        let fireworks = [];
        let particles = [];

        // Cikli i raketave çdo 3 sekonda
        setInterval(() => {
            for(let i=0; i<4; i++) {
                setTimeout(() => fireworks.push(new Firework()), i * 400);
            }
        }, 3000);

        function animate() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.15)';
            ctx.fillRect(0, 0, width, height);
            
            fireworks.forEach((f, i) => { f.update(); f.draw(); if (f.dead) fireworks.splice(i, 1); });
            particles.forEach((p, i) => { p.update(); p.draw(); if (p.alpha <= 0) particles.splice(i, 1); });
            people.forEach(p => { p.update(); p.draw(); });

            requestAnimationFrame(animate);
        }
        animate();
    </script>
</body>
</html>
