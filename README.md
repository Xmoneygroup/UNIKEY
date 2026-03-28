<!DOCTYPE html>
<html lang="sq">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UNIKEY - Specialist për Celsa Makinash</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --gold: #d4af37;
            --dark: #0a0a0a;
            --glass: rgba(255, 255, 255, 0.1);
        }

        body, html {
            margin: 0;
            padding: 0;
            font-family: 'Poppins', sans-serif;
            background-color: var(--dark);
            color: white;
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* Background Animacion 3D me Logo Makinash */
        #bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle, #1a1a1a 0%, #000 100%);
            overflow: hidden;
        }

        .car-logo {
            position: absolute;
            font-size: 1.5rem;
            color: rgba(212, 175, 55, 0.2);
            font-weight: bold;
            white-space: nowrap;
            text-transform: uppercase;
            letter-spacing: 5px;
            pointer-events: none;
        }

        /* Header & Translate */
        .top-bar {
            display: flex;
            justify-content: flex-end;
            padding: 20px;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .btn-translate {
            background: var(--gold);
            color: black;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            font-weight: bold;
            border-radius: 5px;
            transition: 0.3s;
            box-shadow: 0 0 10px rgba(212, 175, 55, 0.5);
        }

        .btn-translate:hover { transform: scale(1.05); }

        /* Titulli Luxury */
        .container {
            max-width: 1000px;
            margin: auto;
            text-align: center;
            padding: 50px 20px;
        }

        h1.luxury-title {
            font-family: 'Cinzel', serif;
            font-size: clamp(3rem, 10vw, 6rem);
            color: var(--gold);
            text-shadow: 0 0 30px rgba(212, 175, 55, 0.6);
            margin-bottom: 20px;
            letter-spacing: 10px;
        }

        /* Nentitujt */
        .info-list {
            list-style: none;
            padding: 40px;
            text-align: left;
            display: inline-block;
            background: var(--glass);
            border-radius: 20px;
            backdrop-filter: blur(15px);
            border: 1px solid rgba(212, 175, 55, 0.3);
            margin-bottom: 50px;
        }

        .info-list li {
            font-size: 1.2rem;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            line-height: 1.5;
        }

        .info-list li::before {
            content: '🔑';
            margin-right: 15px;
            filter: drop-shadow(0 0 5px var(--gold));
        }

        /* Galeria e Fotove - RREGULLIMI I RI */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 50px;
        }

        .img-box {
            width: 100%;
            height: 400px;
            border-radius: 15px;
            overflow: hidden;
            border: 2px solid rgba(212, 175, 55, 0.2);
            background: #1a1a1a; /* Ngjyra nese foto nuk kthehet */
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .img-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: 0.5s ease;
        }

        .img-box:hover img {
            transform: scale(1.1);
            filter: brightness(1.2);
        }

        /* Vleresimi me Yje */
        .rating-section {
            margin-top: 80px;
            background: var(--glass);
            padding: 40px;
            border-radius: 20px;
            border: 1px solid rgba(212, 175, 55, 0.2);
        }

        .stars {
            font-size: 2.5rem;
            color: #333;
            cursor: pointer;
            margin-bottom: 20px;
        }

        .star.active { color: var(--gold); text-shadow: 0 0 10px var(--gold); }

        textarea {
            width: 100%;
            height: 120px;
            background: rgba(0,0,0,0.7);
            color: white;
            border: 1px solid var(--gold);
            padding: 15px;
            border-radius: 10px;
            font-family: inherit;
        }

        .btn-submit {
            margin-top: 20px;
            background: var(--gold);
            border: none;
            padding: 12px 40px;
            font-weight: bold;
            cursor: pointer;
            border-radius: 5px;
            text-transform: uppercase;
        }
    </style>
</head>
<body>

    <div id="bg-animation"></div>

    <div class="top-bar">
        <button class="btn-translate" onclick="toggleLanguage()">Translate to English</button>
    </div>

    <div class="container">
        <h1 class="luxury-title">UNIKEY</h1>
        
        <ul class="info-list" id="content-list">
            <li data-sq="Kemi 17 vite qe meremi me kete profesion." data-en="We have 17 years of experience in this profession.">Kemi 17 vite qe meremi me kete profesion.</li>
            <li data-sq="Punojm 6 ditet e javes nga e Hena deri ne dIten e Shtune , nga ora 9:30 deri ne ora 19:00." data-en="Working 6 days a week, Monday to Saturday, 9:30 AM to 7:00 PM.">Punojm 6 ditet e javes nga e Hena deri ne dIten e Shtune , nga ora 9:30 deri ne ora 19:00.</li>
            <li data-sq="Riparojm Dyer te makinave ( Brava ), Mehanizma te dritareve te Makinave, Qelsa duplikat te makinave kodime , celsa te shtepive, Diagnostik dhe shum gjera te tjera." data-en="We repair car door locks, window mechanisms, duplicate keys, coding, house keys, and diagnostics.">Riparojm Dyer te makinave ( Brava ), Mehanizma te dritareve te Makinave, Qelsa duplikat te makinave kodime , celsa te shtepive, Diagnostik dhe shum gjera te tjera.</li>
            <li data-sq="Me lokacion ndodhemi ne Maqedoni, Komuna Gjorce Petrov, Me lokacion mundeni te na gjeni duke kerkuar vetem ( UNIKKEY - Gjorce Petrov )." data-en="Location: Gjorce Petrov, Macedonia. Search for 'UNIKKEY - Gjorce Petrov' to find us.">Me lokacion ndodhemi ne Maqedoni, Komuna Gjorce Petrov, Me lokacion mundeni te na gjeni duke kerkuar vetem ( UNIKKEY - Gjorce Petrov ).</li>
            <li data-sq="Kontaktoni ne kete numer: Muhamet Musliu - + 389 070 229 348" data-en="Contact us: Muhamet Musliu - + 389 070 229 348">Kontaktoni ne kete numer: Muhamet Musliu - + 389 070 229 348</li>
        </ul>

        <div class="gallery">
            <!-- KETU JANE FOTOT: Ndrysho vetem emrin nese i ke ndryshe ne GitHub -->
            <div class="img-box"><img src="foto1.jpg" alt="Unikey Service" onerror="this.src='https://via.placeholder.com/400x600/1a1a1a/d4af37?text=Foto+1'"></div>
            <div class="img-box"><img src="foto2.jpg" alt="Unikey Service" onerror="this.src='https://via.placeholder.com/400x600/1a1a1a/d4af37?text=Foto+2'"></div>
            <div class="img-box"><img src="foto3.jpg" alt="Unikey Service" onerror="this.src='https://via.placeholder.com/400x600/1a1a1a/d4af37?text=Foto+3'"></div>
            <div class="img-box"><img src="foto4.jpg" alt="Unikey Service" onerror="this.src='https://via.placeholder.com/400x600/1a1a1a/d4af37?text=Foto+4'"></div>
            <div class="img-box"><img src="foto5.jpg" alt="Unikey Service" onerror="this.src='https://via.placeholder.com/400x600/1a1a1a/d4af37?text=Foto+5'"></div>
            <div class="img-box"><img src="foto6.jpg" alt="Unikey Service" onerror="this.src='https://via.placeholder.com/400x600/1a1a1a/d4af37?text=Foto+6'"></div>
        </div>

        <div class="rating-section">
            <h2 id="rate-title" style="color:var(--gold); margin-bottom:10px;">VLERËSONI PUNËN TONË</h2>
            <div class="stars">
                <span class="star" onclick="setRate(1)">★</span>
                <span class="star" onclick="setRate(2)">★</span>
                <span class="star" onclick="setRate(3)">★</span>
                <span class="star" onclick="setRate(4)">★</span>
                <span class="star" onclick="setRate(5)">★</span>
            </div>
            <textarea id="comment-box" placeholder="Shkruani mendimin tuaj këtu..."></textarea>
            <br>
            <button class="btn-submit" onclick="submitReview()">Dërgo Vlerësimin</button>
        </div>
    </div>

    <script>
        // Animacioni i Backgroundit me shpejtesi te ndryshueshme
        const bg = document.getElementById('bg-animation');
        const logos = ['LAMBORGHINI', 'FERRARI', 'PORSCHE', 'BMW', 'AUDI', 'MERCEDES', 'TOYOTA', 'VW', 'CADILLAC'];
        
        function createLogo() {
            const el = document.createElement('div');
            el.className = 'car-logo';
            el.innerText = logos[Math.floor(Math.random() * logos.length)];
            el.style.left = Math.random() * 100 + 'vw';
            el.style.top = '110vh';
            
            // Shpejtesia: 3 sekonda ne fillim, pastaj ngadalësohet
            const duration = 15 + Math.random() * 10;
            el.style.transition = `transform ${duration}s linear, opacity 2s`;
            
            bg.appendChild(el);

            setTimeout(() => {
                el.style.transform = `translateY(-120vh) rotate(${Math.random() * 360}deg)`;
            }, 100);

            setTimeout(() => { el.remove(); }, duration * 1000);
        }

        setInterval(createLogo, 1500);

        // Funksioni Translate
        let isEn = false;
        function toggleLanguage() {
            isEn = !isEn;
            const list = document.querySelectorAll('#content-list li');
            const btn = document.querySelector('.btn-translate');
            const rTitle = document.getElementById('rate-title');

            list.forEach(li => {
                li.innerText = isEn ? li.getAttribute('data-en') : li.getAttribute('data-sq');
            });
            btn.innerText = isEn ? "Kthe ne Shqip" : "Translate to English";
            rTitle.innerText = isEn ? "RATE OUR WORK" : "VLERËSONI PUNËN TONË";
        }

        // Sistemi i yjeve
        function setRate(n) {
            const stars = document.querySelectorAll('.star');
            stars.forEach((s, i) => {
                s.classList.toggle('active', i < n);
            });
        }

        function submitReview() {
            alert("Faleminderit Muhamet! Vlerësimi u dërgua me sukses.");
            document.getElementById('comment-box').value = "";
        }
    </script>
</body>
</html>
