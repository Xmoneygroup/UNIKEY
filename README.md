<!DOCTYPE html>
<html lang="sq">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UNIKEY - Specialist për Celsa Makinash</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Rajdhani:wght@300;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --gold: #FFD700;
            --dark-bg: #050505;
            --glass: rgba(255, 255, 255, 0.05);
            --border-glass: rgba(255, 255, 255, 0.1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Rajdhani', sans-serif;
            background-color: var(--dark-bg);
            color: #fff;
            overflow-x: hidden;
            min-height: 100vh;
        }

        /* BACKGROUND ME LOGO MAKINASH */
        #bg-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle at center, #111 0%, #000 100%);
        }

        .floating-logo {
            position: absolute;
            font-family: 'Orbitron', sans-serif;
            font-weight: bold;
            color: rgba(255, 215, 0, 0.1);
            user-select: none;
            pointer-events: none;
            white-space: nowrap;
        }

        .header-nav {
            display: flex;
            justify-content: flex-end;
            padding: 25px 5%;
        }

        .btn-translate {
            background: transparent;
            color: var(--gold);
            border: 1px solid var(--gold);
            padding: 8px 20px;
            font-family: 'Orbitron', sans-serif;
            cursor: pointer;
            transition: 0.3s;
        }

        .btn-translate:hover {
            background: var(--gold);
            color: #000;
        }

        .main-wrapper {
            max-width: 1100px;
            margin: 0 auto;
            padding: 20px;
            text-align: center;
        }

        .luxury-title {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(3rem, 10vw, 5rem);
            color: var(--gold);
            letter-spacing: 10px;
            margin-bottom: 40px;
            text-shadow: 0 0 20px rgba(255, 215, 0, 0.4);
        }

        .info-card {
            background: var(--glass);
            border-left: 5px solid var(--gold);
            backdrop-filter: blur(15px);
            padding: 30px;
            text-align: left;
            margin-bottom: 50px;
        }

        .info-list { list-style: none; }
        .info-list li {
            font-size: 1.2rem;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }

        /* RREGULLIMI I FOTOOVE */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .img-box {
            background: #111;
            border: 1px solid var(--border-glass);
            height: 400px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }

        .img-box img {
            width: 100%;
            height: 100%;
            object-fit: cover; /* Kjo ben qe foto te mos shtremberohet */
            display: block;
            transition: 0.5s;
        }

        .img-box:hover img {
            transform: scale(1.08);
        }

        /* Teksti nese foto nuk hapet */
        .img-box::after {
            content: 'Duke ngarkuar foton e punës...';
            position: absolute;
            font-size: 0.8rem;
            color: #444;
            z-index: -1;
        }

        .rating-container {
            background: rgba(255,255,255,0.02);
            border: 1px solid var(--gold);
            padding: 40px;
            margin-top: 50px;
        }

        .star { cursor: pointer; font-size: 2rem; color: #222; }
        .star.active { color: var(--gold); }

        textarea {
            width: 100%;
            height: 100px;
            background: #000;
            border: 1px solid var(--border-glass);
            color: white;
            padding: 15px;
            margin-top: 20px;
        }

        .btn-submit {
            background: var(--gold);
            border: none;
            padding: 15px 30px;
            margin-top: 15px;
            font-weight: bold;
            cursor: pointer;
        }
    </style>
</head>
<body>

<div id="bg-canvas"></div>

<nav class="header-nav">
    <button class="btn-translate" onclick="toggleLanguage()">Përkthe në Anglisht</button>
</nav>

<div class="main-wrapper">
    <h1 class="luxury-title">UNIKEY</h1>

    <div class="info-card">
        <ul class="info-list" id="content-list">
            <li data-sq="Kemi 17 vite qe meremi me kete profesion." data-en="17 years of professional experience.">Kemi 17 vite qe meremi me kete profesion.</li>
            <li data-sq="Punojm 6 ditet e javes (Hënë - Shtunë), 09:30 - 19:00." data-en="Working 6 days (Mon - Sat), 09:30 - 19:00.">Punojm 6 ditet e javes (Hënë - Shtunë), 09:30 - 19:00.</li>
            <li data-sq="Riparojm Brava, Mekanizma dritaresh, Qelsa duplikat, Kodime, Diagnostikë." data-en="Repairs: Locks, Window mechanisms, Duplicate keys, Coding, Diagnostics.">Riparojm Brava, Mekanizma dritaresh, Qelsa duplikat, Kodime, Diagnostikë.</li>
            <li data-sq="Lokacioni: Gjorce Petrov, Maqedoni (UNIKKEY - Gjorce Petrov)." data-en="Location: Gjorce Petrov, Macedonia (UNIKKEY - Gjorce Petrov).">Lokacioni: Gjorce Petrov, Maqedoni (UNIKKEY - Gjorce Petrov).</li>
            <li data-sq="Kontakt: Muhamet Musliu - +389 070 229 348" data-en="Contact: Muhamet Musliu - +389 070 229 348">Kontakt: Muhamet Musliu - +389 070 229 348</li>
        </ul>
    </div>

    <div class="gallery-grid">
        <!-- Sigurohu qe fotot t'i kesh ne GitHub me keto emra saktesisht -->
        <div class="img-box"><img src="foto1.jpg" onerror="this.style.display='none'"></div>
        <div class="img-box"><img src="foto2.jpg" onerror="this.style.display='none'"></div>
        <div class="img-box"><img src="foto3.jpg" onerror="this.style.display='none'"></div>
        <div class="img-box"><img src="foto4.jpg" onerror="this.style.display='none'"></div>
        <div class="img-box"><img src="foto5.jpg" onerror="this.style.display='none'"></div>
        <div class="img-box"><img src="foto6.jpg" onerror="this.style.display='none'"></div>
        <div class="img-box"><img src="foto7.jpg" onerror="this.style.display='none'"></div>
    </div>

    <div class="rating-container">
        <h2 id="rate-title">VLERSONI PUNEN TONE</h2>
        <div id="stars">
            <span class="star" onclick="rate(1)">★</span>
            <span class="star" onclick="rate(2)">★</span>
            <span class="star" onclick="rate(3)">★</span>
            <span class="star" onclick="rate(4)">★</span>
            <span class="star" onclick="rate(5)">★</span>
        </div>
        <textarea id="comment" placeholder="Shkruani mendimin tuaj..."></textarea>
        <button class="btn-submit" onclick="submit()">DËRGO</button>
    </div>
</div>

<script>
    const brands = ['LAMBORGHINI', 'FERRARI', 'PORSCHE', 'BMW', 'AUDI', 'MERCEDES', 'TOYOTA', 'VW', 'CADILLAC'];
    const bg = document.getElementById('bg-canvas');

    function createLogo() {
        const logo = document.createElement('div');
        logo.className = 'floating-logo';
        logo.innerText = brands[Math.floor(Math.random() * brands.length)];
        logo.style.left = Math.random() * 100 + 'vw';
        logo.style.top = '110vh';
        const dur = 10 + Math.random() * 15;
        logo.style.transition = `transform ${dur}s linear`;
        bg.appendChild(logo);
        setTimeout(() => { logo.style.transform = `translateY(-120vh) rotate(360deg)`; }, 100);
        setTimeout(() => { logo.remove(); }, dur * 1000);
    }
    setInterval(createLogo, 2000);

    let en = false;
    function toggleLanguage() {
        en = !en;
        document.querySelectorAll('#content-list li').forEach(li => {
            li.innerText = en ? li.getAttribute('data-en') : li.getAttribute('data-sq');
        });
        document.querySelector('.btn-translate').innerText = en ? "Back to Albanian" : "Përkthe në Anglisht";
    }

    function rate(n) {
        document.querySelectorAll('.star').forEach((s, i) => {
            s.classList.toggle('active', i < n);
        });
    }

    function submit() {
        alert("Faleminderit!");
        document.getElementById('comment').value = "";
    }
</script>

</body>
</html>
