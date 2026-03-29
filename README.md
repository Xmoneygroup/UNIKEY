
<html lang="sq">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UNIKEY - Specialist për Çelësa makinash</title>
    <style>
        :root {
            --bg-dark: #06090f; 
            --bg-panel: #0d1117; 
            --accent-blue: #007bff; 
            --accent-electric: #00f2fe; 
            --text-main: #ffffff;
            --text-muted: #8b949e;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-main);
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }

        a { text-decoration: none; color: inherit; }
        ul { list-style: none; padding: 0; margin: 0; }

        /* HEADER RREGULLUAR - Tekstet drejt dhe bukur */
        header {
            background-color: rgba(13, 17, 23, 0.98);
            padding: 25px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-sizing: border-box;
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }

        .logo {
            font-size: 26px;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        .logo span { color: var(--accent-electric); }

        nav ul { 
            display: flex; 
            gap: 35px; 
            align-items: center; /* I mban tekstet baras dhe drejt */
        }
        nav a { 
            font-size: 14px; 
            text-transform: uppercase; 
            color: var(--text-muted); 
            font-weight: 700; 
            letter-spacing: 1.5px;
            transition: 0.3s;
        }
        nav a:hover { color: var(--accent-electric); }

        /* HERO SECTION - Pa vijën e bardhë poshtë titullit */
        .hero {
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding-top: 100px;
            background: radial-gradient(circle at center, #111b2d 0%, var(--bg-dark) 80%);
        }

        .hero h1 {
            font-size: 80px;
            margin: 0; /* Hoqa marginat që të mos ketë hapësira të tepërta */
            text-transform: uppercase;
            letter-spacing: 8px;
            font-weight: 900;
        }
        .hero h1 span { color: var(--accent-electric); }

        /* Hoqa stilin që krijonte vijën e bardhë këtu */

        .hero p { 
            font-size: 18px; 
            color: var(--text-muted); 
            max-width: 600px; 
            margin-top: 20px;
            margin-bottom: 40px;
        }

        .contact-btn {
            background-color: var(--accent-blue);
            color: white;
            padding: 12px 30px;
            border-radius: 4px;
            font-weight: bold;
            text-transform: uppercase;
            transition: 0.3s;
        }
        .contact-btn:hover { background-color: #0056b3; transform: scale(1.05); }

        /* DIAGNOSTIKA - Pamje më e pastër */
        .diagnostike-section {
            padding: 100px 50px;
            background-color: var(--bg-panel);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 50px;
        }

        .radar-box {
            width: 300px;
            height: 200px;
            background: #05070a;
            border-radius: 10px;
            border: 1px solid rgba(0, 242, 254, 0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .line {
            width: 100%;
            height: 2px;
            background: var(--accent-electric);
            box-shadow: 0 0 15px var(--accent-electric);
            position: absolute;
            animation: scan 3s infinite linear;
        }

        @keyframes scan {
            0% { top: 0; }
            100% { top: 100%; }
        }

        .diag-text h2 { font-size: 35px; text-transform: uppercase; }
        .diag-text span { color: var(--accent-electric); }

        /* FOOTER KORRIGJUAR */
        footer {
            padding: 80px 20px;
            text-align: center;
            background-color: var(--bg-dark);
        }

        .contact-card {
            background-color: var(--bg-panel);
            padding: 30px;
            border-radius: 15px;
            display: inline-block;
            border: 1px solid rgba(255,255,255,0.05);
        }

        .c-name { font-size: 24px; font-weight: 800; margin-bottom: 10px; }
        .c-phone { font-size: 30px; color: var(--accent-electric); font-weight: bold; }

        @media (max-width: 768px) {
            header { padding: 20px; flex-direction: column; gap: 15px; }
            nav ul { gap: 15px; }
            .hero h1 { font-size: 45px; }
            .diagnostike-section { flex-direction: column; text-align: center; }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">UNI<span>KEY</span></div>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#sherbimet">Shërbimet</a></li>
                <li><a href="#diagnostike">Diagnostikë</a></li>
                <li><a href="#kontakt">Kontakt</a></li>
            </ul>
        </nav>
        <a href="tel:+389070229348" class="contact-btn" style="padding: 10px 20px; font-size: 12px;">TELEFONO</a>
    </header>

    <section id="home" class="hero">
        <h1>UNI<span>KEY</span></h1>
        <p>Specialistë të çertifikuar për kodimin e çelësave inteligjentë dhe diagnostikë kompjuterike për makina moderne.</p>
        <a href="#sherbimet" class="contact-btn">SHIKO SHËRBIMET</a>
    </section>

    <section id="diagnostike" class="diagnostike-section">
        <div class="radar-box">
            <div class="line"></div>
            <span style="color: var(--accent-electric); font-weight: bold; letter-spacing: 2px;">DIAGNOSING...</span>
        </div>
        <div class="diag-text">
            <h2>Diagnostikë <span>Kompjuterike</span></h2>
            <p style="color: var(--text-muted); max-width: 400px;">Zbulim i gabimeve elektronike me pajisjet më të fundit në treg.</p>
        </div>
    </section>

    <footer id="kontakt">
        <div class="contact-card">
            <div class="c-name">Muhamed Musli</div>
            <div class="c-phone"><a href="tel:+389070229348">+389 070 229 348</a></div>
        </div>
        <p style="margin-top: 40px; color: #333; font-size: 12px;">&copy; 2026 UNIKEY. ALL RIGHTS RESERVED.</p>
    </footer>

</body>
</html>
