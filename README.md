<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>XStore</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    * {margin:0; padding:0; box-sizing:border-box; font-family:'Poppins', sans-serif;}
    body {background:#0d0d0d; color:#fff;}

    header {
      display:flex; justify-content:space-between; align-items:center;
      padding:20px 50px; position:absolute; width:100%; z-index:10;
    }

    .logo {font-size:28px; font-weight:700;}
    .logo span {color:#ff3c00;}

    nav a {
      margin:0 15px; text-decoration:none; color:#ccc; font-size:14px;
      transition:0.3s;
    }
    nav a:hover {color:#fff;}

    .btn {
      border:1px solid #ff3c00; padding:8px 18px; border-radius:8px;
      color:#fff; text-decoration:none; transition:0.3s;
    }
    .btn:hover {background:#ff3c00;}

    .hero {
      height:100vh;
      background:url('https://images.unsplash.com/photo-1503376780353-7e6692767b70') no-repeat center/cover;
      display:flex; align-items:center; justify-content:center;
      text-align:center; position:relative;
    }

    .overlay {
      position:absolute; width:100%; height:100%; background:rgba(0,0,0,0.7);
      top:0; left:0;
    }

    .hero-content {position:relative; z-index:2;}

    .hero h1 {
      font-size:60px; letter-spacing:2px;
    }
    .hero h1 span {color:#ff3c00;}

    .hero p {margin:20px 0; color:#aaa;}

    .cta {
      padding:15px 35px; border:none; background:#ff3c00;
      color:#fff; border-radius:30px; font-size:16px;
      cursor:pointer; transition:0.3s;
    }
    .cta:hover {background:#ff1e00;}

    .stats {
      position:absolute; left:30px; top:150px;
      background:rgba(0,0,0,0.6);
      padding:20px; border-radius:10px;
    }
    .stats div {margin:10px 0;}

    .section {
      padding:80px 50px; text-align:center;
    }

    .cards {
      display:grid; grid-template-columns:repeat(auto-fit, minmax(250px,1fr)); gap:20px;
      margin-top:40px;
    }

    .card {
      background:#1a1a1a; padding:20px; border-radius:15px;
      transition:0.3s;
    }
    .card:hover {transform:translateY(-10px);}

    footer {
      text-align:center; padding:30px; background:#111;
      color:#777;
    }
  </style>
</head>
<body>

<header>
  <div class="logo"><span>X</span>STORE</div>
  <nav>
    <a href="#">Car Parts</a>
    <a href="#">Accessories</a>
    <a href="#">Performance</a>
    <a href="#">Services</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </nav>
  <a href="#" class="btn">Login</a>
</header>

<section class="hero">
  <div class="overlay"></div>
  <div class="stats">
    <div>10,000+ Sales</div>
    <div>25,000+ Customers</div>
    <div>20 Years Experience</div>
  </div>
  <div class="hero-content">
    <h1><span>X</span>STORE</h1>
    <p>Elevate Your Drive</p>
    <button class="cta">JOIN IN STORE</button>
  </div>
</section>

<section class="section">
  <h2>Our Products</h2>
  <div class="cards">
    <div class="card">Car Parts</div>
    <div class="card">Accessories</div>
    <div class="card">Performance</div>
  </div>
</section>

<footer>
  <p>© 2026 XStore. All rights reserved.</p>
</footer>

</body>
</html>
