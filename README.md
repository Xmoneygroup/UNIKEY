<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>XStore Neon</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;800&display=swap" rel="stylesheet">

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Orbitron',sans-serif;}

body{
  background:#050505;
  color:#fff;
  overflow-x:hidden;
}

/* Neon background */
body::before{
  content:"";
  position:fixed;
  width:100%;height:100%;
  background:radial-gradient(circle at 20% 30%, #ff3c0033, transparent 40%),
             radial-gradient(circle at 80% 70%, #ff000033, transparent 40%),
             radial-gradient(circle at 50% 50%, #ff3c0011, transparent 60%);
  z-index:-1;
}

header{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:20px 50px;
}

.logo{
  font-size:30px;
  font-weight:800;
  color:#fff;
}
.logo span{
  color:#ff3c00;
  text-shadow:0 0 10px #ff3c00, 0 0 20px #ff3c00;
}

nav a{
  margin:0 15px;
  text-decoration:none;
  color:#aaa;
  transition:.3s;
}

nav a:hover{
  color:#fff;
  text-shadow:0 0 10px #ff3c00;
}

.btn{
  border:1px solid #ff3c00;
  padding:10px 20px;
  border-radius:10px;
  text-decoration:none;
  color:#fff;
  transition:.3s;
}

.btn:hover{
  background:#ff3c00;
  box-shadow:0 0 15px #ff3c00;
}

.hero{
  height:90vh;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  text-align:center;
}

.hero h1{
  font-size:80px;
}

.hero h1 span{
  color:#ff3c00;
  text-shadow:0 0 20px #ff3c00,0 0 40px #ff0000;
}

.hero p{
  margin-top:20px;
  color:#bbb;
}

.cta{
  margin-top:40px;
  padding:15px 40px;
  border:none;
  background:transparent;
  color:#fff;
  border:2px solid #ff3c00;
  border-radius:30px;
  cursor:pointer;
  font-size:16px;
  transition:.3s;
}

.cta:hover{
  background:#ff3c00;
  box-shadow:0 0 20px #ff3c00,0 0 40px #ff0000;
}

.stats{
  position:absolute;
  left:40px;
  top:150px;
  border:1px solid #ff3c00;
  padding:20px;
  border-radius:15px;
  box-shadow:0 0 15px #ff3c00;
}

.stats div{
  margin:10px 0;
}

.section{
  padding:80px 50px;
  text-align:center;
}

.cards{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
  gap:20px;
  margin-top:40px;
}

.card{
  background:#0d0d0d;
  border:1px solid #ff3c00;
  padding:30px;
  border-radius:15px;
  transition:.3s;
}

.card:hover{
  transform:translateY(-10px);
  box-shadow:0 0 20px #ff3c00;
}

footer{
  text-align:center;
  padding:30px;
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
  <div class="stats">
    <div>10,000+ Sales</div>
    <div>25,000+ Customers</div>
    <div>20 Years Experience</div>
  </div>

  <h1><span>X</span>STORE</h1>
  <p>Elevate Your Drive</p>
  <button class="cta">JOIN IN STORE</button>
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
  <p>© 2026 XStore Neon Edition</p>
</footer>

</body>
</html>
