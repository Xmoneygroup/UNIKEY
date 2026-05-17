<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MkdMap - Welcome to Macedonia</title>
    <style>
        /* --- STILI PËR EKRANIN HYRËS (SPLASH SCREEN) --- */
        #splash-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            background-color: #0f172a; /* Sfondi i errët që të pëlqeu */
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            opacity: 1;
            transition: opacity 0.5s ease;
        }

        .splash-text {
            color: #ffffff;
            font-family: sans-serif;
            font-size: 2.2rem;
            font-weight: bold;
            letter-spacing: 2px;
            text-transform: uppercase;
            text-align: center;
            padding: 0 20px;
            
            /* --- ANIMACIONI I SHKRONJAVE (IN EFFECT) --- */
            opacity: 0;
            transform: translateY(30px); /* E nis tekstin pak më poshtë */
            animation: textIn 1s cubic-bezier(0.25, 1, 0.5, 1) forwards; /* Lëvizja elegante lart */
        }

        /* Këtu krijojmë lëvizjen e shkronjave */
        @keyframes textIn {
            to {
                opacity: 1;
                transform: translateY(0); /* Teksti vjen në vendin e vet */
            }
        }

        /* --- STILI PËR FAQEN KRYESORE --- */
        body {
            margin: 0;
            padding: 0;
            background-color: #f8fafc;
            font-family: sans-serif;
        }

        header {
            width: 100%;
            padding: 20px 0;
            background-color: #ffffff;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .main-title {
            margin: 0;
            font-size: 1.4rem;
            font-weight: bold;
            letter-spacing: 4px;
            text-transform: uppercase;
            color: #0f172a;
        }

        .content-placeholder {
            text-align: center;
            margin-top: 100px;
            color: #64748b;
        }
    </style>
</head>
<body>

    <!-- 1. SPLASH SCREEN (Me animacion lëvizës) -->
    <div id="splash-screen">
        <div class="splash-text">Welcome to Macedonia</div>
    </div>

    <!-- 2. HOME PAGE -->
    <header>
        <h1 class="main-title">mkdmap</h1>
    </header>

    <main>
        <div class="content-placeholder">
            <p>Animacioni i shkronjave u shtua! Po pres urdhrin e radhës...</p>
        </div>
    </main>

    <!-- 3. SCRIPT-I PËR ZHDUKJEN PAS 2 SEKONDA -->
    <script>
        window.addEventListener("DOMContentLoaded", function() {
            // Presim 2 sekonda (2000ms) që turisti të shohë animacionin e bukur
            setTimeout(function() {
                var splash = document.getElementById("splash-screen");
                splash.style.opacity = "0";
                setTimeout(function() {
                    splash.style.display = "none";
                }, 500); // Kjo e heq plotësisht nga ekrani pasi bëhet transparente
            }, 2000);
        });
    </script>

</body>
</html>
