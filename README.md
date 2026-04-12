<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elite Domain | Locarox.com</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Syncopate:wght@700&family=Montserrat:wght@300;400;600&display=swap');

        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            background-color: #000;
            font-family: 'Montserrat', sans-serif;
        }

        #canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }

        /* CONTAINER KRYESOR */
        .main-container {
            position: relative;
            z-index: 10;
            width: 100%;
            height: 100vh;
            display: flex;
            flex-direction: row;
            justify-content: flex-end; /* I shton elementet djathtas */
            align-items: flex-start; /* I ngjit lart */
            padding: 50px;
            box-sizing: border-box;
            pointer-events: none;
        }

        /* PLLAKATA E BARDHË */
        .sales-card {
            background: #ffffff;
            width: 320px;
            padding: 30px;
            border-radius: 4px;
            text-align: center;
            box-shadow: 0 20px 50px rgba(0,0,0,0.5);
            pointer-events: auto; /* Që butoni të punojë */
            margin-right: 20px;
        }

        .sales-card h2 {
            color: #000;
            font-size: 1rem;
            margin: 0;
            letter-spacing: 2px;
            font-weight: 600;
        }

        .sales-card .domain-name {
            color: #000;
            font-weight: 600;
            font-size: 1.2rem;
            margin: 15px 0 5px 0;
        }

        .sales-card .status {
            color: #666;
            font-size: 0.8rem;
            margin-bottom: 20px;
        }

        .sales-card .price {
            font-size: 1.8rem;
            font-weight: 700;
            color: #000;
            margin-bottom: 25px;
        }

        /* BUTONI NEXT */
        .next-btn {
            display: block;
            width: 100%;
            padding: 15px;
            background: #000;
            color: #fff;
            text-decoration: none;
            font-weight: 600;
            border-radius: 4px;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 2px;
            border: none;
            cursor: pointer;
        }

        .next-btn:hover {
            background: #2ecc71; /* E gjelbër e lehtë */
            transform: translateY(-2px);
        }

        .help-text {
            color: #888;
            font-size: 0.75rem;
            margin-top: 20px;
        }

        /* TEKSTI JASHTË PLLAKATËS (DJATHAS POSHTË) */
        .external-info {
            position: absolute;
            right: 50px;
            bottom: 80px;
            text-align: right;
            color: #fff;
        }

        .ext-domain {
            font-family: 'Syncopate', sans-serif;
            font-size: 1.8rem;
            margin-bottom: 5px;
            letter-spacing: 4px;
        }

        .ext-status {
            font-size: 1.1rem;
            font-weight: 300;
            opacity: 0.9;
            margin-bottom: 15px;
        }

        .ext-anim {
            font-size: 0.8rem;
            font-weight: 300;
            color: rgba(255,255,255,0.6);
            border-top: 1px solid rgba(255,255,255,0.2);
            padding-top: 10px;
            animation: fadeInOut 4s infinite ease-in-out;
        }

        @keyframes fadeInOut {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }

        @media (max-width: 768px) {
            .main-container { 
                flex-direction: column; 
                align-items: center; 
                padding: 20px;
                justify-content: center;
            }
            .sales-card { margin: 0 auto; width: 85%; }
            .external-info { position: relative; right: 0; bottom: 0; text-align: center; margin-top: 30px; }
        }
    </style>
</head>
<body>

    <canvas id="canvas"></canvas>

    <div class="main-container">
        <div class="sales-card">
            <h2>BUY NOW</h2>
            <div class="domain-name">locarox.com</div>
            <div class="status">is for sale now</div>
            <div class="price">2,390.00 USD</div>
            
            <a href="KËTU_VENDOS_LINKUN_E_PAGESËS" class="next-btn">Next</a>
            
            <div class="help-text">
                Need help? Give us a call<br>
                <strong>+389 XX XXX XXX</strong> </div>
        </div>

        <div class="external-info">
            <div class="ext-domain">locarox.com</div>
            <div class="ext-status">is for sale!</div>
            <div class="ext-anim">
                Simple, secure purchase & transfer<br>
                Trusted by customers globally
            </div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });

        class Firework {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = canvas.height;
                this.targetY = Math.random() * (canvas.height * 0.7) + 50;
                this.speed = 3 + Math.random() * 3;
                this.angle = -Math.PI / 2 + (Math.random() * 0.4 - 0.2);
                this.velocity = {
                    x: Math.cos(this.angle) * this.speed,
                    y: Math.sin(this.angle) * this.speed
                };
                const rand = Math.random();
                if (rand > 0.85) this.explosionSize = 150;
                else if (rand > 0.4) this.explosionSize = 70;
                else this.explosionSize = 30;
                this.dead = false;
                this.trail = [];
            }

            update() {
                this.trail.push({x: this.x, y: this.y});
                if (this.trail.length > 8) this.trail.shift();
                this.x += this.velocity.x;
                this.y += this.velocity.y;
                if (this.y <= this.targetY) {
                    this.explode();
                    this.dead = true;
                }
            }

            draw() {
                ctx.beginPath();
                ctx.strokeStyle = "rgba(255, 255, 255, 0.3)";
                ctx.lineWidth = 1.5;
                if(this.trail.length > 0) {
                    ctx.moveTo(this.trail[0].x, this.trail[0].y);
                    ctx.lineTo(this.x, this.y);
                    ctx.stroke();
                }
                ctx.beginPath();
                ctx.arc(this.x, this.y, 2, 0, Math.PI * 2);
                ctx.fillStyle = "#fff";
                ctx.fill();
            }

            explode() {
                const neonColors = ['#00f2ff', '#00ffaa', '#ff00ee', '#ffff00', '#ff3300', '#4d4dff', '#ffffff'];
                const color = neonColors[Math.floor(Math.random() * neonColors.length)];
                for (let i = 0; i < this.explosionSize; i++) {
                    particles.push(new Particle(this.x, this.y, color));
                }
            }
        }

        class Particle {
            constructor(x, y, color) {
                this.x = x;
                this.y = y;
                this.color = color;
                const angle = Math.random() * Math.PI * 2;
                const force = Math.random() * 11;
                this.velocity = {
                    x: Math.cos(angle) * force,
                    y: Math.sin(angle) * force
                };
                this.alpha = 1;
                this.friction = 0.94;
                this.gravity = 0.15;
                this.size = Math.random() * 3 + 1;
            }

            draw() {
                ctx.save();
                ctx.globalAlpha = this.alpha;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fillStyle = this.color;
                ctx.shadowBlur = 12;
                ctx.shadowColor = this.color;
                ctx.fill();
                ctx.restore();
            }

            update() {
                this.velocity.x *= this.friction;
                this.velocity.y *= this.friction;
                this.velocity.y += this.gravity;
                this.x += this.velocity.x;
                this.y += this.velocity.y;
                this.alpha -= 0.01;
            }
        }

        let fireworks = [];
        let particles = [];

        function animate() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.18)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            if (Math.random() < 0.07) { 
                fireworks.push(new Firework());
            }
            fireworks.forEach((fw, index) => {
                fw.update();
                fw.draw();
                if (fw.dead) fireworks.splice(index, 1);
            });
            particles.forEach((p, index) => {
                p.update();
                p.draw();
                if (p.alpha <= 0) particles.splice(index, 1);
            });
            requestAnimationFrame(animate);
        }

        animate();
    </script>
</body>
</html>
