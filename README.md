 Chaudhary-s-Business
website for homemade products
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>RasoiRoots – Pure Homemade Spices</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
  <style>
    /* Reset & Fonts */
    * { margin: 0; padding: 0; box-sizing: border-box; scroll-behavior: smooth; }
    body { font-family: 'Segoe UI', sans-serif; background: #fcf9f4; color: #333; }

    /* Header */
    header {
      background: linear-gradient(90deg, #7b1f1f, #a83232);
      color: #fff;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      position: fixed;
      top: 0; left: 0;
      width: 100%;
      z-index: 1000;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
    .logo { font-size: 1.8rem; font-weight: bold; }
    nav ul { display: flex; list-style: none; gap: 1.5rem; }
    nav a {
      color: #fff;
      font-weight: 500;
      cursor: pointer;
      text-decoration: none;
    }

    /* Sections */
    section {
      padding: 6rem 2rem 4rem;
      max-width: 1200px;
      margin: auto;
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
    }
    .product, .review {
      background: #fff;
      padding: 1.5rem;
      border-radius: 10px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.05);
    }
    .price {
      color: #a83232;
      font-weight: bold;
    }
    .btn-primary {
      background: #a83232;
      color: #fff;
      border: none;
      padding: 0.7rem 1.2rem;
      border-radius: 5px;
      cursor: pointer;
    }
    .btn-primary:hover { background: #7b1f1f; }

    /* Newsletter */
    .newsletter input {
      padding: 0.7rem;
      width: 60%;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    .newsletter button {
      padding: 0.7rem 1rem;
      background: #a83232;
      color: #fff;
      border: none;
      border-radius: 5px;
    }

    /* Modal */
    .modal, .overlay { position: fixed; display: none; }
    .overlay {
      top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.5); z-index: 1000;
    }
    .modal {
      top: 50%; left: 50%;
      transform: translate(-50%, -50%);
      background: #fff;
      padding: 2rem;
      border-radius: 10px;
      z-index: 1001;
      width: 320px;
      box-shadow: 0 0 15px rgba(0,0,0,0.3);
    }
    .modal input {
      width: 100%;
      margin: 0.5rem 0;
      padding: 0.6rem;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    /* Footer */
    footer {
      background: #7b1f1f;
      color: #fff;
      text-align: center;
      padding: 2rem;
    }
    .icons { margin-right: 8px; color: #a83232; }
  </style>
</head>
<body>

  <!-- Header -->
  <header>
    <div class="logo">RasoiRoots</div>
    <nav>
      <ul>
        <li><a href="#home"><i class="fas fa-home icons"></i>Home</a></li>
        <li><a href="#products">Products</a></li>
        <li><a href="#reviews">Reviews</a></li>
        <li><a href="#newsletter">Subscribe</a></li>
        <li><a href="#contact"><i class="fas fa-phone icons"></i>Contact</a></li>
        <li><a href="#login" onclick="openLogin()">Login</a></li>
      </ul>
    </nav>
  </header>

  <!-- Home Section -->
  <section id="home">
    <h1 style="text-align:center;">Welcome to RasoiRoots</h1>
    <p style="text-align:center;">Pure & Homemade Spices with Authentic Flavour</p>
  </section>

  <!-- Products Section -->
  <section id="products">
    <h2>Our Products</h2>
    <div class="grid">
      <div class="product">
        <h3>Red Chilly Powder</h3>
        <p>200g — <span class="price">₹70</span></p>
        <button class="btn-primary">Add to Cart</button>
      </div>
      <div class="product">
        <h3>Coriander Powder</h3>
        <p>200g — <span class="price">₹60</span></p>
        <button class="btn-primary">Add to Cart</button>
      </div>
      <div class="product">
        <h3>Turmeric Powder</h3>
        <p>200g — <span class="price">₹70</span></p>
        <button class="btn-primary">Add to Cart</button>
      </div>
    </div>
  </section>

  <!-- Reviews Section -->
  <section id="reviews">
    <h2>Customer Reviews</h2>
    <div class="grid">
      <div class="review">“Absolutely fresh and aromatic! RasoiRoots never disappoints.”<br><strong>— Priya</strong></div>
      <div class="review">“The best homemade spices I’ve ever used.”<br><strong>— Akshay</strong></div>
    </div>
  </section>

  <!-- Newsletter Section -->
  <section id="newsletter">
    <h2>Subscribe to Our Newsletter</h2>
    <div class="newsletter">
      <input type="email" placeholder="Enter your email" />
      <button>Subscribe</button>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact">
    <h2>Contact Us</h2>
    <p><i class="fas fa-phone icons"></i><strong>Phone:</strong> 8954152963, 9411911398</p>
    <p><i class="fas fa-envelope icons"></i><strong>Email:</strong> rasoiroots@gmail.com</p>
    <p><i class="fas fa-map-marker-alt icons"></i><strong>Address:</strong> Village - Atmadsarai, 203408, Bulandshahr</p>
    <iframe
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d14014.885514059218!2d77.9489032!3d28.4090125!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x390c7bbd641a5eb7%3A0xe06f6ecff404178f!2sAtmadsarai%2C%20Uttar%20Pradesh%20203408!5e0!3m2!1sen!2sin!4v1716570541051!5m2!1sen!2sin"
      width="100%" height="300" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
  </section>

  <!-- Overlay + Modal -->
  <div class="overlay" id="overlay" onclick="closeModals()"></div>
  <div class="modal" id="loginModal">
    <h3>Login</h3>
    <input type="email" id="email" placeholder="Email">
    <input type="password" id="password" placeholder="Password">
    <button class="btn-primary" onclick="loginUser()">Login</button>
  </div>

  <!-- Footer -->
  <footer>
    &copy; 2025 RasoiRoots | Pure Homemade Spices | Designed with ❤️
  </footer>

  <!-- JS Script -->
  <script>
    function openLogin() {
      document.getElementById('overlay').style.display = 'block';
      document.getElementById('loginModal').style.display = 'block';
    }
    function closeModals() {
      document.getElementById('overlay').style.display = 'none';
      document.getElementById('loginModal').style.display = 'none';
    }
    function loginUser() {
      const email = document.getElementById('email').value;
      const pass = document.getElementById('password').value;
      if (email === "user@example.com" && pass === "password123") {
        alert("Login successful!");
        closeModals();
      } else {
        alert("Invalid email or password");
      }
    }
  </script>

</body>
</html>
