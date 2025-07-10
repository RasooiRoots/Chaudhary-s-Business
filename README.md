 Chaudhary-s-Business
website for homemade products
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RasoiRoots | Pure Homemade Spices</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"/>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #fcf9f4;
      color: #333;
    }
    header {
      background: #a83232;
      color: white;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
    }
    .logo {
      font-size: 1.8rem;
      font-weight: bold;
    }
    nav a {
      color: white;
      margin-left: 1.2rem;
      text-decoration: none;
      font-weight: 500;
    }
    nav a i {
      margin-right: 5px;
    }
    main {
      padding-top: 100px;
      max-width: 1200px;
      margin: auto;
    }
    section {
      padding: 4rem 2rem;
      border-bottom: 1px solid #ddd;
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.5rem;
    }
    .product, .review {
      background-color: white;
      padding: 1.2rem;
      border-radius: 10px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }
    .btn {
      background-color: #a83232;
      color: white;
      padding: 10px 15px;
      border: none;
      border-radius: 5px;
      margin-top: 10px;
      cursor: pointer;
    }
    form input {
      padding: 0.8rem;
      width: 100%;
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
      background-color: #a83232;
      color: white;
      text-align: center;
      padding: 2rem 1rem;
    }
    .icons {
      margin-right: 8px;
    }
    h1, h2 {
      color: #a83232;
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
        <div class="product"><h3>Red Chilly Powder</h3><p>200g — ₹70</p><button class="btn">Add to Cart</button></div>
        <div class="product"><h3>Coriander Powder</h3><p>200g — ₹60</p><button class="btn">Add to Cart</button></div>
        <div class="product"><h3>Turmeric Powder</h3><p>200g — ₹70</p><button class="btn">Add to Cart</button></div>
        <div class="product"><h3>Garam Masala</h3><p>200g — ₹200</p><button class="btn">Add to Cart</button></div>
        <div class="product"><h3>Cumin Seeds (Jeera)</h3><p>200g — ₹90</p><button class="btn">Add to Cart</button></div>
        <div class="product"><h3>Besan (Gram Flour)</h3><p>1kg — ₹100</p><button class="btn">Add to Cart</button></div>
        <div class="product"><h3>Mustard Oil</h3><p>1kg — ₹160</p><button class="btn">Add to Cart</button></div>
      </div>
    </section>

    <section id="reviews">
      <h2>Customer Reviews</h2>
      <div class="grid">
        <div class="review">"Absolutely fresh and aromatic! RasoiRoots never disappoints." – Priya</div>
        <div class="review">"The best homemade spices I’ve ever used." – Akshay</div>
        <div class="review">"Good packaging, on-time delivery and real flavor." – Kavita</div>
      </div>
    </section>

    <section id="contact">
      <h2>Contact Us</h2>
      <p><i class="fas fa-phone icons"></i><strong>Phone:</strong> 8954152963, 9411911398</p>
      <p><i class="fas fa-envelope icons"></i><strong>Email:</strong> rasoiroots@gmail.com</p>
      <p><i class="fas fa-map-marker-alt icons"></i><strong>Address:</strong> Village - Atmadsarai, 203408, Bulandshahr</p>
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d14014.885514059218!2d77.9489032!3d28.4090125"
        allowfullscreen=""
        loading="lazy">
      </iframe>
    </section>

    <section id="login">
      <h2>Login</h2>
      <form onsubmit="login(event)">
        <input type="email" id="loginEmail" placeholder="Email" required />
        <input type="password" id="loginPass" placeholder="Password" required />
        <button class="btn">Login</button>
      </form>
    </section>

    <section id="signup">
      <h2>Sign Up</h2>
      <form onsubmit="signup(event)">
        <input type="text" placeholder="Full Name" required />
        <input type="email" placeholder="Email" required />
        <input type="password" placeholder="Password" required />
        <button class="btn">Create Account</button>
      </form>
    </section>
  </main>

  <footer>
    &copy; 2025 RasoiRoots | Pure Homemade Spices | Built with ❤️
  </footer>

  <script>
    function login(e) {
      e.preventDefault();
      const email = document.getElementById('loginEmail').value;
      const pass = document.getElementById('loginPass').value;
      if (email === "user@example.com" && pass === "password123") {
        alert("Login successful!");
      } else {
        alert("Invalid email or password.");
      }
    }

    function signup(e) {
      e.preventDefault();
      alert("Account created! (This is a demo. No backend connected.)");
    }
  </script>

</body>
</html>
