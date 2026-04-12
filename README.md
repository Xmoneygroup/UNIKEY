<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elite Domain | Particles</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Syncopate:wght@700&display=swap');

        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            background-color: #000;
        }

        canvas {
            display: block;
        }
    </style>
</head>
<body>

    <canvas id="canvas"></canvas>

    <script>
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        let particles = [];
        let mouse = { x: 0, y: 0, radius: 100 };
        let text = "DOMAIN FOR SALE";
        let particleSize = 2;
        let gap = 4;
        let state = "forming"; // forming, exploding, falling
        let timer = 0;

        // Krijimi i koordinatave nga teksti
        function initText() {
            ctx.fillStyle = 'white';
            ctx.font = 'bold 80px Syncopate';
            if(window.innerWidth < 768) ctx.font = 'bold 30px Syncopate';
            
            ctx.textAlign = 'center';
            ctx.fillText(text, canvas.width / 2, canvas.height / 2);
            
            const imageData = ctx.getImageData(0, 0, canvas.width, canvas.height);
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            particles = [];
            for (let y = 0; y < imageData.height; y += gap) {
                for (let x = 0; x < imageData.width; x += gap) {
                    if (imageData.data[(y * imageData.width + x) * 4 + 3] > 128) {
                        particles.push(new Particle(x, y));
                    }
                }
            }
        }

        class Particle {
            constructor(x, y) {
                this.originX = x;
                this.originY = y;
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.vx = 0;
                this.vy = 0;
                this.acc = 0.1;
                this.friction = 0.95;
                this.color = '#00f2ff';
                this.gravity = 0.2;
            }

            draw() {
                ctx.fillStyle = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, particleSize, 0, Math.PI * 2);
                ctx.fill();
            }

            update() {
                if (state === "forming") {
                    let dx = this.originX - this.x;
                    let dy = this.originY - this.y;
                    this.vx += dx * this.acc;
                    this.vy += dy * this.acc;
                    this.vx *= this.friction;
                    this.vy *= this.friction;
                } 
                else if (state === "shattering") {
                    // Shpërthim i shpejtë
                    this.vx += (Math.random() - 0.5) * 10;
                    this.vy += (Math.random() - 0.5) * 10;
                    this.vx *= 0.99;
                    this.vy *= 0.99;
                }
                else if (state === "falling") {
                    this.vy += this.gravity;
                    this.vx *= 0.99;
                }

                this.x += this.vx;
                this.y += this.vy;
            }
        }

        function animate() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.2)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            timer++;

            // LOGJIKA E CIKLIT 5 SEKONDASH
            if (timer < 180) { // Sekonda 0-3: Formohet
                state = "forming";
            } else if (timer < 210) { // Sekonda 3-3.5: Shpërthejnë
                state = "shattering";
            } else if (timer < 300) { // Sekonda 3.5-5: Bien poshtë
                state = "falling";
            } else {
                timer = 0;
                // I nisim grimcat nga pozicione të reja random që të mblidhen prapë
                particles.forEach(p => {
                    p.y = -10;
                    p.x = Math.random() * canvas.width;
                });
            }

            particles.forEach(p => {
                p.update();
                p.draw();
            });

            // SHTOJMË EDHE NJË PAK FISHEKZJARRË NË SFOND
            if (Math.random() < 0.03) drawMiniFirework();

            requestAnimationFrame(animate);
        }

        function drawMiniFirework() {
            let x = Math.random() * canvas.width;
            let y = Math.random() * canvas.height;
            ctx.fillStyle = '#ff00ee';
            ctx.beginPath();
            ctx.arc(x, y, 1, 0, Math.PI * 2);
            ctx.fill();
        }

        initText();
        animate();

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            initText();
        });
    </script>
</body>
</html>
