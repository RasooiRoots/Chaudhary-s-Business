Rasoi Roots
website for homemade products
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1.0" />
  <title>RasoiRoots | Pure Homemade Spices</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"/>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; scroll-behavior: smooth }
    body { font-family: 'Segoe UI', sans-serif; background: #fcf9f4; color: #333 }

    header {
      background: #a83232;
      color: white;
      text-align: center;
      padding: 1.5rem 1rem;
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
    }

    .logo {
      font-size: 2.2rem;
      font-weight: bold;
      margin-bottom: 0.5rem;
    }

    nav {
      margin-top: 0.5rem;
    }

    nav a {
      color: white;
      margin: 0 10px;
      text-decoration: none;
      font-weight: 500;
      font-size: 1rem;
    }

    nav a i {
      margin-right: 5px;
    }

    main {
      padding-top: 150px;
      max-width: 1100px;
      margin: auto;
      text-align: center;
    }

    section {
      padding: 4rem 2rem;
      border-bottom: 1px solid #ddd;
    }

    .grid {
      display: grid;
      gap: 1.5rem;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      justify-content: center;
    }

    .product, .review {
      background: #fff;
      padding: 1.2rem;
      border-radius: 10px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      text-align: left;
    }

    .btn {
      background: #a83232;
      color: #fff;
      padding: 10px 15px;
      border: none;
      border-radius: 5px;
      margin-top: 10px;
      cursor: pointer;
    }

    form input {
      padding: 0.8rem;
      width: 90%;
      max-width: 400px;
      margin: 0.5rem 0;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    iframe {
      width: 100%;
      height: 300px;
      border: none;
      margin-top: 1rem;
    }

    footer {
      background: #a83232;
      color: white;
      text-align: center;
      padding: 2rem 1rem;
    }

    h1, h2 {
      color: #a83232;
      margin-bottom: 1rem;
    }
  </style>
</head>
<body>

  <header>
    <div class="logo">RasoiRoots</div>
    <nav>
      <a href="#home"><i class="fas fa-home"></i>Home</a>
      <a href="#products"><i class="fas fa-box-open"></i>Products</a>
      <a href="#reviews"><i class="fas fa-star"></i>Reviews</a>
      <a href="#contact"><i class="fas fa-phone-alt"></i>Contact</a>
      <a href="#login"><i class="fas fa-sign-in-alt"></i>Login</a>
      <a href="#signup"><i class="fas fa-user-plus"></i>Sign Up</a>
    </nav>
  </header>

  <main>
    <section id="home">
      <h1>Welcome to RasoiRoots</h1>
      <p>Pure & Homemade Spices with Authentic Flavour</p>
    </section>

    <section id="products">
      <h2>Our Products</h2>
      <div class="grid">
        <div class="product"><h3>Red Chilly Powder</h3><p>200g — ₹70</p><button class="btn" onclick="alert('Added to cart')">Add to Cart</button></div>
        <div class="product"><h3>Coriander Powder</h3><p>200g — ₹60</p><button class="btn" onclick="alert('Added to cart')">Add to Cart</button></div>
        <div class="product"><h3>Turmeric Powder</h3><p>200g — ₹70</p><button class="btn" onclick="alert('Added to cart')">Add to Cart</button></div>
        <div class="product"><h3>Garam Masala</h3><p>200g — ₹200</p><button class="btn" onclick="alert('Added to cart')">Add to Cart</button></div>
        <div class="product"><h3>Cumin Seeds (Jeera)</h3><p>200g — ₹90</p><button class="btn" onclick="alert('Added to cart')">Add to Cart</button></div>
        <div class="product"><h3>Besan (Gram Flour)</h3><p>1kg — ₹100</p><button class="btn" onclick="alert('Added to cart')">Add to Cart</button></div>
        <div class="product"><h3>Mustard Oil</h3><p>1kg — ₹160</p><button class="btn" onclick="alert('Added to cart')">Add to Cart</button></div>
      </div>
    </section>

    <section id="reviews">
      <h2>Customer Reviews</h2>
      <div class="grid">
        <div class="review">"Fresh, aromatic, and authentic!" – Priya</div>
        <div class="review">"My cooking changed with this masala." – Akshay</div>
        <div class="review">"Great packaging & taste." – Kavita</div>
      </div>
    </section>

    <section id="contact">
      <h2>Contact Us</h2>
      <p><i class="fas fa-phone-alt"></i> 8954152963, 9411911398</p>
      <p><i class="fas fa-envelope"></i> rasoiroots@gmail.com</p>
      <p><i class="fas fa-map-marker-alt"></i> Village – Atmadsarai, 203408, Bulandshahr</p>
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d28054.647515250086!2d77.82529174999999!3d28.4846376!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x390ca3772100734b%3A0x2b85934592a389b9!2sBrajpal%20Madhyan-%20oil%20mill%20%2C%20flour%20mill%20and%20spices%20point.!5e0!3m2!1sen!2sin!4v1752165381607!5m2!1sen!2sin" allowfullscreen="" loading="lazy"></iframe>
    </section>

    <section id="login">
      <h2>Login</h2>
      <form onsubmit="handleLogin(event)">
        <input type="email" id="loginEmail" placeholder="Email" required>
        <input type="password" id="loginPass" placeholder="Password" required>
        <button class="btn">Login</button>
      </form>
    </section>

    <section id="signup">
      <h2>Sign Up</h2>
      <form onsubmit="handleSignup(event)">
        <input type="text" id="signupName" placeholder="Full Name" required>
        <input type="email" id="signupEmail" placeholder="Email" required>
        <input type="password" id="signupPass" placeholder="Password" required>
        <button class="btn">Create Account</button>
      </form>
    </section>
  </main>

  <footer>
    &copy; 2025 RasoiRoots | Pure Homemade Spices | Built with ❤️
  </footer>

<script>
  function handleLogin(e) {
    e.preventDefault();
    const email = document.getElementById('loginEmail').value.trim();
    const pass = document.getElementById('loginPass').value.trim();
    if (email && pass) {
      alert('Login successful — (Simulated)');
    } else {
      alert('Please enter email and password.');
    }
  }

  function handleSignup(e) {
    e.preventDefault();
    const name = document.getElementById('signupName').value.trim();
    const email = document.getElementById('signupEmail').value.trim();
    const pass = document.getElementById('signupPass').value.trim();
    if (name && email && pass) {
      alert('Account created — (Simulated)');
    } else {
      alert('Please fill all fields.');
    }
  }
</script>

</body>
</html>
