<!DOCTYPE html>
<html lang="sq">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Auto Çelësa & Diagnostikë - 25 Vite Përvojë</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    
    <style>
        :root {
            --primary-color: #ffcc00; /* Ngjyra e arit/çelësit */
            --dark-bg: #0f1113;
            --card-bg: #1a1d21;
            --text-light: #ffffff;
        }

        body {
            margin: 0;
            font-family: 'Poppins', sans-serif;
            background-color: var(--dark-bg);
            color: var(--text-light);
            scroll-behavior: smooth;
        }

        /* Navigimi */
        nav {
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(15, 17, 19, 0.95);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid #333;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
            text-transform: uppercase;
        }

        /* Hero Section me Animacion */
        .hero {
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://images.unsplash.com/photo-1549027226-e17621980892?q=80&w=2070&auto=format&fit=crop'); /* Foto ilustruese */
            background-size: cover;
            background-position: center;
            animation: fadeIn 2s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            color: var(--primary-color);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
        }

        /* Butoni i Kontaktit Mjeshtrit */
        .btn-contact {
            background-color: var(--primary-color);
            color: #000;
            padding: 15px 35px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            transition: transform 0.3s, box-shadow 0.3s;
            margin-top: 25px;
            display: inline-block;
            box-shadow: 0 0 20px rgba(255, 204, 0, 0.4);
        }

        .btn-contact:hover {
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(255, 204, 0, 0.6);
        }

        /* Grid i Shërbimeve */
        .services {
            padding: 80px 10%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .card {
            background: var(--card-bg);
            padding: 40px;
            border-radius: 15px;
            text-align: center;
            transition: 0.4s;
            border: 1px solid #222;
        }

        .card:hover {
            border-color: var(--primary-color);
            transform: translateY(-10px);
        }

        .card i {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 20px;
        }

        /* Seksioni 25 Vite Besim */
        .experience {
            background: var(--primary-color);
            color: #000;
            padding: 60px 0;
            text-align: center;
            font-weight: 700;
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.2rem; }
        }
    </style>
</head>
<body>

    <nav>
        <div class="logo">Ekspert Çelësash</div>
        <div>25 Vite Përvojë</div>
    </nav>

    <section class="hero">
        <h1>SIGURI DHE PRECIZION</h1>
        <p>Specialistë për çelësa makinash, diagnostikim dhe riparim dritaresh e bravash me teknologjinë më moderne.</p>
        <a href="tel:+389070229348" class="btn-contact">
            <i class="fas fa-phone-alt"></i> KONTAKTO MJESHTRIN
        </a>
    </section>

    <div class="experience">
        <h2>MBI 25 VITE EKSPERIENCË NË TREG - BESIM DHE CILËSI</h2>
    </div>

    <section class="services">
        <div class="card">
            <i class="fas fa-key"></i>
            <h3>Çelësa Duplikat</h3>
            <p>Duplikim dhe kodim për të gjitha llojet e makinave moderne.</p>
        </div>
        <div class="card">
            <i class="fas fa-car-crash"></i>
            <h3>Diagnostikë</h3>
            <p>Identifikimi i gabimeve elektronike me pajisje profesionale.</p>
        </div>
        <div class="card">
            <i class="fas fa-door-open"></i>
            <h3>Brava & Dritare</h3>
            <p>Riparim i mekanizmave të dritareve dhe bravave të makinës.</p>
        </div>
    </section>

    <footer style="text-align: center; padding: 40px; border-top: 1px solid #333; opacity: 0.6;">
        <p>&copy; 2026 Shërbimi i Çelësave. Të gjitha të drejtat e rezervuara.</p>
        <p>Telefon: +389 070 229 348</p>
    </footer>

</body>
</html>
