
<html lang="sq">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Xmesage | Premium Access</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            background: #050505; /* Black Carbon Base */
            font-family: 'Segoe UI', sans-serif;
            overflow: hidden;
            color: white;
        }

        /* Galaxy Background Animation */
        #galaxy-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            background: radial-gradient(circle at center, #001529 0%, #050505 100%);
        }

        /* Glassmorphism Login Container */
        .login-container {
            position: relative;
            z-index: 10;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            opacity: 0;
            animation: fadeIn 2s ease-in forwards;
            animation-delay: 3s; /* Shfaqet pas intros Galaxy */
        }

        .login-box {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 215, 0, 0.2); /* Gold Border Neon */
            padding: 50px;
            border-radius: 20px;
            box-shadow: 0 0 50px rgba(0, 0, 0, 0.8), 0 0 20px rgba(255, 215, 0, 0.1);
            text-align: center;
            width: 350px;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            letter-spacing: 5px;
            background: linear-gradient(to right, #fff, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 15px rgba(255, 215, 0, 0.5);
        }

        p {
            color: #888;
            margin-bottom: 30px;
            font-size: 0.9rem;
        }

        /* Neon Buttons */
        .btn-login {
            width: 100%;
            padding: 15px;
            margin: 10px 0;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            transition: 0.4s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            font-size: 1rem;
        }

        .google-btn {
            background: white;
            color: #000;
        }

        .apple-btn {
            background: #111;
            color: white;
            border: 1px solid #333;
        }

        .btn-login:hover {
            transform: translateY(-3px);
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.2);
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }

        /* Intro Text Animation */
        #intro-text {
            position: fixed;
            z-index: 100;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 3rem;
            letter-spacing: 15px;
            animation: pulseFade 3s ease-in-out forwards;
        }

        @keyframes pulseFade {
            0% { opacity: 0; letter-spacing: 30px; filter: blur(10px); }
            50% { opacity: 1; filter: blur(0px); }
            100% { opacity: 0; display: none; }
        }
    </style>
</head>
<body>

    <div id="intro-text">XMESAGE</div>

    <canvas id="galaxy-bg"></canvas>

    <div class="login-container">
        <div class="login-box">
            <h1>XMESAGE</h1>
            <p>Ekskluzive për marketing dhe rrjete sociale</p>
            
            <button class="btn-login google-btn">
                Login with Google
            </button>
            
            <button class="btn-login apple-btn">
                Login with Apple
            </button>
        </div>
    </div>

    <script>
        // Simple Starfield Animation (No Stock Photos)
        const canvas = document.getElementById('galaxy-bg');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const stars = [];
        for(let i = 0; i < 200; i++) {
            stars.push({
                x: Math.random() * canvas.width,
                y: Math.random() * canvas.height,
                size: Math.random() * 2,
                speed: Math.random() * 0.5
            });
        }

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = "white";
            stars.forEach(star => {
                ctx.beginPath();
                ctx.arc(star.x, star.y, star.size, 0, Math.PI * 2);
                ctx.fill();
                star.y -= star.speed;
                if(star.y < 0) star.y = canvas.height;
            });
            requestAnimationFrame(animate);
        }
        animate();
    </script>
</body>
</html>
