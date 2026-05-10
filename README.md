<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>XKAPO | Authority</title>
    <style>
        /* RESET TOTAL */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        /* Sigurohemi që html dhe body të marrin 100% të lartësisë së ekranit */
        body, html { 
            width: 100%; 
            height: 100%; 
            background-color: #000; 
            overflow: hidden; 
            position: fixed; /* Parandalon scroll-in në iOS */
        }

        /* 1. INTRO ANIMATION (LOGO) */
        #intro-splash {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: #000;
            display: flex; justify-content: center; align-items: center;
            z-index: 10000;
        }

        .logo-anim {
            max-width: 80%; /* Nuk lejon logon të preki anët */
            max-height: 80%;
            width: auto; height: auto;
            opacity: 0;
            animation: logoFlash 2s forwards;
        }

        @keyframes logoFlash {
            0% { opacity: 0; transform: scale(0.98); }
            50% { opacity: 1; transform: scale(1); }
            100% { opacity: 0; transform: scale(1.02); }
        }

        /* NAVIGATION STYLE MANSORY */
        nav {
            position: fixed; top: 0; width: 100%; 
            padding: 20px; /* Padding më i vogël për mobile */
            display: flex; justify-content: space-between; align-items: center;
            z-index: 2000;
            background: linear-gradient(to bottom, rgba(0,0,0,0.8), transparent);
            color: white;
            text-transform: uppercase; letter-spacing: 3px;
        }
        
        .nav-logo { font-size: 18px; font-weight: bold; letter-spacing: 5px; }
        
        .contact-btn { 
            border: 1px solid #fff; padding: 8px 15px; 
            text-decoration: none; color: #fff; font-size: 11px;
            transition: 0.3s; 
        }
        .contact-btn:hover { background: #fff; color: #000; }

        /* HOME PAGE & SLIDER */
        #home-content { opacity: 0; width: 100%; height: 100%; position: relative; transition: opacity 0.5s; }
        .slider-container { width: 100%; height: 100%; position: relative; }
        
        .slide {
            position: absolute; width: 100%; height: 100%;
            
            /* KJO ËSHTË ZGJIDHJA PËR KUALITETIN: */
            background-size: cover; /* Mbulon ekranin pa u shtypur */
            background-position: center; /* Mbante qendrën e fotos (makinën) në mes */
            background-repeat: no-repeat;
            
            display: none; /* E bëjmë display none që të mos përzihen (INSTANT) */
        }
        
        /* Kur fotoja është aktive, shfaqet direkt thikë */
        .slide.active { display: block; } 

        /* OVERLAY LEHTË PËR PREMIUM LOOK */
        .overlay { 
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.2); z-index: 5; pointer-events: none; 
        }
    </style>
</head>
<body>

    <div id="intro-splash">
        <img src="9BA7D80D-DB0A-4D39-9C65-6FD915BCF247.jpg" alt="XKAPO" class="logo-anim">
    </div>

    <div id="home-content">
        <nav>
            <div class="nav-logo">XKAPO</div>
            <a href="tel:+389070878227" class="contact-btn">CONTACT US</a>
        </nav>

        <div class="slider-container">
            <div class="overlay"></div>
            
            <div class="slide active" style="background-image: url('IMG_1022.jpg');"></div>
            <div class="slide" style="background-image: url('IMG_1024.jpg');"></div>
            <div class="slide" style="background-image: url('IMG_1025.jpg');"></div>
            <div class="slide" style="background-image: url('IMG_1026.jpg');"></div>
            <div class="slide" style="background-image: url('IMG_1027.jpg');"></div>
        </div>
    </div>

    <script>
        // TRANZICIONI NGA LOGO TE HOME
        window.addEventListener('load', () => {
            // Presim 2 sekonda për animacionin e logos
            setTimeout(() => {
                document.getElementById('intro-splash').style.display = 'none';
                document.getElementById('home-content').style.opacity = '1';
                startInstantSlider();
            }, 2000); 
        });

        // SLIDERI DIREKT PA "FADE" (3.5 SEKONDA)
        function startInstantSlider() {
            const slides = document.querySelectorAll('.slide');
            let current = 0;
            const totalSlides = slides.length;

            if (totalSlides === 0) return; // Siguresa

            setInterval(() => {
                slides[current].classList.remove('active'); // Zhduket direkt
                current = (current + 1) % totalSlides;
                slides[current].classList.add('active'); // Shfaqet direkt tjetra
            }, 3500); // 3.5 sekonda qëndrimi
        }
    </script>
</body>
</html>
