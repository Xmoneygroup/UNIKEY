<!DOCTYPE html>
<html lang="sq">
<head>
    <meta charset="UTF-8">
    <title>X-TREME VELOCITY | Ultra Quality</title>
    <style>
        body { margin: 0; background: #000; overflow: hidden; font-family: 'Inter', sans-serif; }
        #ui { position: absolute; top: 30px; left: 30px; color: white; z-index: 100; pointer-events: none; }
        #score { font-size: 48px; font-weight: 900; color: #00ffcc; text-shadow: 0 0 20px #00ffcc; }
        canvas { display: block; filter: contrast(1.2) brightness(1.1); }
    </style>
</head>
<body>

<div id="ui">
    <div style="font-size: 12px; letter-spacing: 5px; opacity: 0.5;">X-MESAGE SYSTEM</div>
    <div id="score">0</div>
</div>

<canvas id="c"></canvas>

<script>
    const canvas = document.getElementById('c');
    const ctx = canvas.getContext('2d');
    let w = canvas.width = window.innerWidth;
    let h = canvas.height = window.innerHeight;

    let score = 0;
    let particles = [];
    let obstacles = [];
    let speed = 15;
    let mouse = { x: w / 2, y: h / 2 };

    // Grimcat e sfondit (Stars/Dust)
    class Particle {
        constructor() {
            this.reset();
        }
        reset() {
            this.x = Math.random() * w;
            this.y = Math.random() * h;
            this.z = Math.random() * w;
            this.pz = this.z;
        }
        update() {
            this.z -= speed;
            if (this.z <= 1) this.reset();
        }
        show() {
            let sx = (this.x - w / 2) * (w / this.z) + w / 2;
            let sy = (this.y - h / 2) * (w / this.z) + h / 2;
            let px = (this.x - w / 2) * (w / this.pz) + w / 2;
            let py = (this.y - h / 2) * (w / this.pz) + h / 2;
            this.pz = this.z;

            ctx.strokeStyle = 'rgba(0, 255, 204, 0.4)';
            ctx.lineWidth = 2;
            ctx.beginPath();
            ctx.moveTo(sx, sy);
            ctx.lineTo(px, py);
            ctx.stroke();
        }
    }

    // Pengesat (Neon Rings)
    class Obstacle {
        constructor() {
            this.z = w;
            this.x = Math.random() * w;
            this.y = Math.random() * h;
            this.size = 150;
        }
        update() {
            this.z -= speed;
            if (this.z <= 0) {
                this.z = w;
                this.x = Math.random() * w;
                this.y = Math.random() * h;
                score += 10;
                document.getElementById('score').innerText = score;
            }
        }
        show() {
            let scale = w / this.z;
            let sx = (this.x - w / 2) * scale + w / 2;
            let sy = (this.y - h / 2) * scale + h / 2;
            let s = this.size * scale;

            ctx.strokeStyle = '#ff0055';
            ctx.lineWidth = 5 * scale;
            ctx.shadowBlur = 15;
            ctx.shadowColor = '#ff0055';
            ctx.strokeRect(sx - s/2, sy - s/2, s, s);

            // Kontrolli i përplasjes
            if (this.z < 50 && Math.abs(sx - mouse.x) < s/2 && Math.abs(sy - mouse.y) < s/2) {
                speed = 0;
                ctx.fillStyle = "white";
                ctx.font = "bold 60px Inter";
                ctx.fillText("CRITICAL ERROR", w/2 - 200, h/2);
                setTimeout(() => location.reload(), 2000);
            }
        }
    }

    for (let i = 0; i < 400; i++) particles.push(new Particle());
    for (let i = 0; i < 3; i++) obstacles.push(new Obstacle());

    function drawX(x, y) {
        ctx.save();
        ctx.translate(x, y);
        ctx.strokeStyle = "white";
        ctx.lineWidth = 6;
        ctx.shadowBlur = 25;
        ctx.shadowColor = "white";
        
        ctx.beginPath();
        ctx.moveTo(-30, -30); ctx.lineTo(30, 30);
        ctx.moveTo(30, -30); ctx.lineTo(-30, 30);
        ctx.stroke();
        ctx.restore();
    }

    function loop() {
        ctx.fillStyle = 'rgba(0, 0, 0, 0.2)'; // Motion Blur efekt
        ctx.fillRect(0, 0, w, h);

        particles.forEach(p => { p.update(); p.show(); });
        obstacles.forEach(o => { o.update(); o.show(); });
        
        drawX(mouse.x, mouse.y);
        
        if (speed > 0) {
            speed += 0.005;
            requestAnimationFrame(loop);
        }
    }

    window.addEventListener('mousemove', e => {
        mouse.x = e.clientX;
        mouse.y = e.clientY;
    });

    loop();
</script>

</body>
</html>
