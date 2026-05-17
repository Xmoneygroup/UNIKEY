<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MkdMap - Welcome to Macedonia</title>
    <style>
        /* --- STILI PËR ANIMACIONIN HYRËS (SPLASH SCREEN) --- */
        #splash-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            background-color: #0f172a; /* Ngjyrë e errët elegante slate-900 */
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.5s ease, visibility 0.5s;
        }

        .splash-text {
            color: #ffffff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            font-size: 2.5rem;
            font-weight: 800;
            letter-spacing: 2px;
            text-transform: uppercase;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.8s ease forwards;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Klasa që do të aktivizohet nga JavaScript pas 2 sekondave */
        .fade-out {
            opacity: 0;
            visibility: hidden;
        }

        /* --- STILI PËR FAQEN KRYESORE (HOME PAGE) --- */
        body {
            margin: 0;
            padding: 0;
            background-color: #f8fafc; /* Sfond i hapur dhe i pastër */
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
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
            font-size: 1.5rem; /* Madhësi mesatare/e vogël, shumë elegante */
            font-weight: 700;
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

    <!-- 1. EKRANI HYRËS (SPLASH SCREEN) -->
    <div id="splash-screen">
        <div class="splash-text">Welcome to Macedonia</div>
    </div>

    <!-- 2. FAQJA KRYESORE (HOME PAGE) -->
    <header>
        <h1 class="main-title">mkdmap</h1>
    </header>

    <main>
        <div class="content-placeholder">
            <p>Hapi i parë u krye me sukses. Faqja kryesore po pret pjesën tjetër...</p>
        </div>
    </main>

    <!-- 3. SCRIPT-I PËR ANIMACIONIN 2 SEKONDA -->
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            // Presim saktësisht 2 sekonda (2000 milisekonda) para se të nisë zbehja
            setTimeout(function() {
                const splash = document.getElementById("splash-screen");
                splash.classList.add("fade-out");
            }, 2000);
        });
    </script>

</body>
</html>
