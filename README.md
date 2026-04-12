<!DOCTYPE html>
<html lang="sq">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elite Domain Portfolio</title>
    <style>
        /* STILI LUXURY */
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            background-color: #050505; /* E zezë e thellë */
            font-family: 'Montserrat', sans-serif;
        }

        #canvas {
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
        }

        /* KONTEJNERI KRYESOR */
        .content-wrapper {
            position: relative;
            z-index: 10;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            pointer-events: none; /* Lejon mausin të ndërveprojë me background-in */
        }

        .luxury-card {
            text-align: center;
            padding: 40px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            backdrop-filter: blur(10px); /* Efekti xham (Glassmorphism) */
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
        }

        .title {
            font-size: 4rem;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 10px;
            margin: 0;
            background: linear-gradient(45deg, #fff, #d4af37, #fff);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shine 3s linear infinite;
        }

        .subtitle {
            color: rgba(255, 255, 255, 0.6);
            font-size: 1rem;
            margin-top: 10px;
            letter-spacing: 5px;
            text-transform: uppercase;
        }

        @keyframes shine {
            to { background-position: 200% center; }
        }

        /* Mobile Optimization */
        @media (max-width: 768px) {
            .title { font-size: 2rem; letter-spacing: 5px; }
        }
    </style>
</head>
<body>

    <canvas id="canvas"></canvas>

    <div class="content-wrapper">
        <div class="luxury-card">
            <h1 class="title">This Domain is for Sale</h1>
            <div class="subtitle">Premium Asset • Digital Real Estate</div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');
        let particlesArray;

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        let mouse = {
            x: null,
            y: null,
            radius: (canvas.height/80) * (canvas.width/80)
        }

        window.addEventListener('mousemove', function(event) {
            mouse.x = event.x;
            mouse.y = event.y;
        });

        class Particle {
            constructor(x, y, directionX, directionY, size, color) {
                this.x = x;
                this.y = y;
                this.directionX = directionX;
                this.directionY = directionY;
                this.size = size;
                this.color = color;
            }
            draw() {
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2, false);
                ctx.fillStyle = '#fff';
                ctx.fill();
            }
            update() {
                if (this.x > canvas.width || this.x < 0) this.directionX = -this.directionX;
                if (this.y > canvas.height || this.y < 0) this.directionY = -this.directionY;
                this.x += this.directionX;
                this.y += this.directionY;
                this.draw();
            }
        }

        function init() {
            particlesArray = [];
            let numberOfParticles = (canvas.height * canvas.width) / 9000;
            for (let i = 0; i < numberOfParticles; i++) {
                let size = (Math.random() * 2) + 1;
                let x = (Math.random() * ((innerWidth - size * 2) - (size * 2)) + size * 2);
                let y = (Math.random() * ((innerHeight - size * 2) - (size * 2)) + size * 2);
                let directionX = (Math.random() * 2) - 1;
                let directionY = (Math.random() * 2) - 1;
                let color = '#ffffff';
                particlesArray.push(new Particle(x, y, directionX, directionY, size, color));
            }
        }

        function connect() {
            let opacityValue = 1;
            for (let a = 0; a < particlesArray.length; a++) {
                for (let b = a; b < particlesArray.length; b++) {
                    let distance = ((particlesArray[a].x - particlesArray[b].x) * (particlesArray[a].x - particlesArray[b].x))
                    + ((particlesArray[a].y - particlesArray[b].y) * (particlesArray[a].y - particlesArray[b].y));
                    if (distance < (canvas.width/7) * (canvas.height/7)) {
                        opacityValue = 1 - (distance/20000);
                        ctx.strokeStyle = 'rgba(212, 175, 55,' + opacityValue + ')'; // Ngjyra Gold për lidhjet
                        ctx.lineWidth = 1;
                        ctx.beginPath();
                        ctx.moveTo(particlesArray[a].x, particlesArray[a].y);
                        ctx.lineTo(particlesArray[b].x, particlesArray[b].y);
                        ctx.stroke();
                    }
                }
            }
        }

        function animate() {
            requestAnimationFrame(animate);
            ctx.clearRect(0,0, innerWidth, innerHeight);
            for (let i = 0; i < particlesArray.length; i++) {
                particlesArray[i].update();
            }
            connect();
        }

        init();
        animate();

        window.addEventListener('resize', function(){
            canvas.width = innerWidth;
            canvas.height = innerHeight;
            init();
        });
    </script>
</body>
</html>
