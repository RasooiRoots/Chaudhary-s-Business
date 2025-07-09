# Chaudhary-s-Business
website for homemade products
<!DOCTYPE html><!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RasoiRoots – Authentic Homemade Spices</title>
  <style>
    html { scroll-behavior: smooth; font-size: 16px; }
    body, h1, h2, h3, p, button { margin: 0; padding: 0; }
    body { font-family: 'Segoe UI', sans-serif; background: #fff; color: #333; }
    header { display: flex; align-items: center; justify-content: space-between; padding: 1rem; background: #a83232; color: #fff; position: sticky; top: 0; z-index: 100; }
    .logo { display: flex; align-items: center; }
    .logo img { height: 50px; margin-right: .75rem; border-radius: 5px; }
    nav a { color: #fff; margin: 0 .75rem; text-decoration: none; font-weight: bold; }
    nav a:hover { text-decoration: underline; }
    .login-btn { background: #fff; color: #a83232; padding: .5rem 1rem; border: none; border-radius: 4px; cursor: pointer; }
    .login-btn:hover { background: #822e2e; color: #fff; }
    .hero { text-align: center; padding: 4rem 1rem; background: #fff5ee; }
    .hero h1 { font-size: 2.5rem; margin-bottom: 1rem; }
    .hero p { font-size: 1.125rem; color: #555; max-width: 600px; margin: 0 auto 2rem; }
    .btn-primary { background: #a83232; color: #fff; padding: .75rem 1.5rem; border: none; border-radius: 5px; font-size: 1rem; cursor: pointer; }
    .btn-primary:hover { background: #822e2e; }
    section { padding: 3rem 1rem; max-width: 1200px; margin: 0 auto; }
    .products-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1.5rem; }
    .product { border: 1px solid #eee; border-radius: 8px; overflow: hidden; text-align: center; box-shadow: 0 2px 8px rgba(0,0,0,0.05); }
    .product img { width: 100%; height: auto; }
    .product h3 { margin: .75rem 0 .5rem; font-size: 1.25rem; }
    .product .price { color: #a83232; font-weight: bold; margin-bottom: .75rem; }
    footer { background: #a83232; color: #fff; text-align: center; padding: 1rem; }

    .cart-sidebar { position: fixed; top: 8rem; right: 1rem; width: 280px; background: #fff; border: 1px solid #ddd; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); padding: 1rem; z-index: 100; }
    .cart-sidebar h4 { margin-bottom: .75rem; }
    .cart-item { margin-bottom: .5rem; }
    .checkout-btn { width: 100%; padding: .625rem; background: #822e2e; color: #fff; border: none; border-radius: 5px; cursor: pointer; }
    .checkout-btn:hover { background: #a83232; }

    .login-popup, .overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; }
    .overlay { height: 100%; background: rgba(0,0,0,0.5); z-index: 200; }
    .login-popup { z-index: 300; width: 320px; height: auto; background: #fff; top: 50%; left: 50%; transform: translate(-50%, -50%); padding: 2rem; border-radius: 8px; }
    .login-popup h3 { margin-bottom: 1rem; }
    .login-popup input { width: 100%; padding: .5rem; margin-bottom: 1rem; border: 1px solid #ddd; border-radius: 4px; }
    .login-popup button { width: 100%; padding: .75rem; border: none; background: #a83232; color: #fff; border-radius: 4px; cursor: pointer; }
  </style>
</head>
<body>
  <header>
    <div class="logo"><img src="/mnt/data/182f1ecd-efcc-4ac9-9ac5-478e394ddcf2.jpg" alt="RasoiRoots"><h1>RasoiRoots</h1></div>
    <nav><a href="#home">Home</a><a href="#products">Products</a><a href="#contact">Contact</a></nav>
    <button class="login-btn" onclick="showLogin()">Login</button>
  </header>

  <div class="hero" id="home">
    <h1>Pure & Homemade Spices for Authentic Flavour</h1>
    <p>We handcraft every spice blend from traditional recipes, bringing warmth and richness to your kitchen.</p>
    <button class="btn-primary" onclick="document.getElementById('products').scrollIntoView()">Shop Now</button>
  </div>

  <section id="products">
    <h2 style="text-align:center; margin-bottom:2rem;">Our Products</h2>
    <div class="products-grid">
      <!-- Example product card -->
      <div class="product"><img src="https://via.placeholder.com/400x300" alt="Red Chilly Powder"><h3>Red Chilly Powder</h3><p class="price">₹70 / 200g</p><button class="cart-btn" onclick="addToCart('Red Chilly Powder')">Add to Cart</button></div>
      <div class="product"><img src="https://via.placeholder.com/400x300" alt="Coriander Powder"><h3>Coriander Powder</h3><p class="price">₹60 / 200g</p><button class="cart-btn" onclick="addToCart('Coriander Powder')">Add to Cart</button></div>
      <div class="product"><img src="https://via.placeholder.com/400x300" alt="Turmeric Powder"><h3>Turmeric Powder</h3><p class="price">₹70 / 200g</p><button class="cart-btn" onclick="addToCart('Turmeric Powder')">Add to Cart</button></div>
      <div class="product"><img src="https://via.placeholder.com/400x300" alt="Garam Masala"><h3>Garam Masala</h3><p class="price">₹200 / 200g</p><button class="cart-btn" onclick="addToCart('Garam Masala')">Add to Cart</button></div>
      <div class="product"><img src="https://via.placeholder.com/400x300" alt="Cumin Seeds"><h3>Cumin Seeds</h3><p class="price">₹90 / 200g</p><button class="cart-btn" onclick="addToCart('Cumin Seeds')">Add to Cart</button></div>
      <div class="product"><img src="https://via.placeholder.com/400x300" alt="Besan"><h3>Besan (Gram Flour)</h3><p class="price">₹100 / 1kg</p><button class="cart-btn" onclick="addToCart('Besan')">Add to Cart</button></div>
      <div class="product"><img src="https://via.placeholder.com/400x300" alt="Mustard Oil"><h3>Mustard Oil</h3><p class="price">₹160 / 1kg</p><button class="cart-btn" onclick="addToCart('Mustard Oil')">Add to Cart</button></div>
    </div>
  </section>

  <section id="contact">
    <h2 style="text-align:center; margin-bottom:2rem;">Contact Us</h2>
    <div style="max-width:800px; margin:0 auto; text-align:center;">
      <p><strong>Email:</strong> rasoiroots@gmail.com</p>
      <p><strong>Phone:</strong> +91 8954152963, +91 9411911398</p>
      <p><strong>Address:</strong> Village – Atmadsarai, 203408, Bulandshahr</p>
      <iframe src="https://www.google.com/maps?q=Atmadsarai+Bulandshahr&output=embed" width="100%" height="300" style="border:0;border-radius:8px;" loading="lazy"></iframe>
    </div>
  </section>

  <div class="cart-sidebar" id="cart-sidebar">
    <h4>Your Cart</h4><div id="cart-items"></div><button class="checkout-btn" onclick="checkout()">Checkout</button>
  </div>

  <!-- Login popup -->
  <div class="overlay" id="overlay" onclick="closeLogin()"></div>
  <div class="login-popup" id="loginPopup">
    <h3>Login</h3>
    <input type="email" id="email" placeholder="Email">
    <input type="password" id="password" placeholder="Password">
    <button onclick="loginUser()">Login</button>
    <button style="margin-top:1rem; background:#ccc; color:#333;" onclick="closeLogin()">Cancel</button>
  </div>

  <footer>&copy; 2025 RasoiRoots | Cash on Delivery Only | ❤️</footer>

  <script>
    let cart = [];
    function addToCart(item) {
      cart.push(item);
      renderCart();
    }
    function renderCart() {
      const el = document.getElementById('cart-items');
      el.innerHTML = '';
      cart.forEach((i, idx) => { el.innerHTML += `<div class="cart-item">${idx+1}. ${i}</div>`; });
    }
    function checkout() {
      if (!cart.length) return alert('Your cart is empty.');
      alert('Order placed: ' + cart.join(', '));
      cart = [];
      renderCart();
    }
    function showLogin() {
      document.getElementById('loginPopup').style.display='block';
      document.getElementById('overlay').style.display='block';
    }
    function closeLogin() {
      document.getElementById('loginPopup').style.display='none';
      document.getElementById('overlay').style.display='none';
    }
    function loginUser() {
      const e = document.getElementById('email').value;
      const p = document.getElementById('password').value;
      if (e==='user@example.com' && p==='password123') { alert('Logged in!'); closeLogin(); }
      else alert('Invalid credentials');
    }
  </script>
</body>
</html>

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RasoiRoots - Pure Homemade Spices</title>
  <style>
    html {
      scroll-behavior: smooth;
    }
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 0;
      background: #fef8f3;
      color: #333;
    }
    header {
      background-color: #a83232;
      color: #fff;
      padding: 10px 20px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .logo {
      display: flex;
      align-items: center;
    }
    .logo img {
      height: 60px;
      margin-right: 15px;
      border-radius: 8px;
    }
    .logo h1 {
      margin: 0;
      font-size: 2rem;
    }
    .slogan {
      flex-grow: 1;
      text-align: center;
      font-size: 1rem;
    }
    .login-btn {
      margin-left: auto;
      background-color: #fff;
      color: #a83232;
      border: 2px solid #fff;
      padding: 8px 15px;
      border-radius: 5px;
      cursor: pointer;
    }
    .login-btn:hover {
      background-color: #822e2e;
      color: white;
    }
    nav {
      background-color: #822e2e;
      padding: 10px;
      text-align: center;
    }
    nav a {
      color: #fff;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }
    .container {
      padding: 30px;
    }
    .product {
      background: #fff5ee;
      padding: 20px;
      margin-bottom: 20px;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
    .product h3 {
      margin-top: 0;
    }
    .price {
      font-weight: bold;
      color: #a83232;
    }
    .cart-btn {
      margin-top: 10px;
      padding: 10px 15px;
      background-color: #a83232;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .cart-btn:hover {
      background-color: #822e2e;
    }
    .cart-section {
      position: fixed;
      top: 100px;
      right: 20px;
      background: #fff;
      border: 1px solid #ccc;
      border-radius: 8px;
      padding: 15px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
      width: 250px;
    }
    .cart-section h4 {
      margin-top: 0;
    }
    .cart-item {
      font-size: 0.9rem;
      margin: 5px 0;
    }
    .checkout-btn {
      margin-top: 10px;
      width: 100%;
      background-color: #822e2e;
      color: #fff;
      border: none;
      padding: 10px;
      border-radius: 5px;
      cursor: pointer;
    }
    .checkout-btn:hover {
      background-color: #a83232;
    }
    .login-popup {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: #fff;
      padding: 20px;
      border: 1px solid #ccc;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
      z-index: 1000;
    }
    .login-popup input {
      display: block;
      margin: 10px 0;
      padding: 8px;
      width: 100%;
    }
    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 999;
      display: none;
    }
    footer {
      background-color: #a83232;
      color: #fff;
      text-align: center;
      padding: 15px;
      position: fixed;
      bottom: 0;
      width: 100%;
    }
  </style>
  <script>
    let cart = [];

    function addToCart(product) {
      cart.push(product);
      updateCart();
    }

    function updateCart() {
      const cartList = document.getElementById("cart-items");
      cartList.innerHTML = "";
      cart.forEach((item, index) => {
        const li = document.createElement("div");
        li.className = "cart-item";
        li.textContent = `${index + 1}. ${item}`;
        cartList.appendChild(li);
      });
    }

    function checkout() {
      if (cart.length === 0) {
        alert("Your cart is empty.");
      } else {
        alert("Thanks for your order! Items: " + cart.join(", "));
        cart = [];
        updateCart();
      }
    }

    function showLogin() {
      document.getElementById("loginPopup").style.display = "block";
      document.getElementById("overlay").style.display = "block";
    }

    function closeLogin() {
      document.getElementById("loginPopup").style.display = "none";
      document.getElementById("overlay").style.display = "none";
    }

    function loginUser() {
      const email = document.getElementById("email").value;
      const password = document.getElementById("password").value;
      if (email === "user@example.com" && password === "password123") {
        alert("Login successful!");
        closeLogin();
      } else {
        alert("Invalid email or password.");
      }
    }
  </script>
</head>
<body>
  <header>
    <div class="logo">
      <img src="logo.jpg" alt="RasoiRoots Logo">
      <h1>RasoiRoots</h1>
    </div>
    <div class="slogan">Pure & Homemade Spices with Authentic Flavour</div>
    <button class="login-btn" onclick="showLogin()">Login / Sign In</button>
  </header>

  <nav>
    <a href="#home">Home</a>
    <a href="#products">Products</a>
    <a href="#contact">Contact</a>
  </nav>

  <div id="home" class="container">
    <h2>Welcome to RasoiRoots!</h2>
    <p>Experience the richness of pure, homemade Indian spices that bring authentic flavour to your kitchen. Our products are crafted with love and tradition.</p>
  </div>

  <div class="container" id="products">
    <div class="product"><h3>Red Chilly Powder</h3><p>200g — <span class="price">₹70</span></p><button class="cart-btn" onclick="addToCart('Red Chilly Powder')">Add to Cart</button></div>
    <div class="product"><h3>Coriander Powder (Dhaniya)</h3><p>200g — <span class="price">₹60</span></p><button class="cart-btn" onclick="addToCart('Coriander Powder')">Add to Cart</button></div>
    <div class="product"><h3>Turmeric Powder</h3><p>200g — <span class="price">₹70</span></p><button class="cart-btn" onclick="addToCart('Turmeric Powder')">Add to Cart</button></div>
    <div class="product"><h3>Garam Masala</h3><p>200g — <span class="price">₹200</span></p><button class="cart-btn" onclick="addToCart('Garam Masala')">Add to Cart</button></div>
    <div class="product"><h3>Cumin Seeds (Jeera)</h3><p>200g — <span class="price">₹90</span></p><button class="cart-btn" onclick="addToCart('Cumin Seeds')">Add to Cart</button></div>
    <div class="product"><h3>Besan (Gram Flour)</h3><p>1kg — <span class="price">₹100</span></p><button class="cart-btn" onclick="addToCart('Besan')">Add to Cart</button></div>
    <div class="product"><h3>Mustard Oil</h3><p>1kg — <span class="price">₹160</span></p><button class="cart-btn" onclick="addToCart('Mustard Oil')">Add to Cart</button></div>
  </div>

  <div class="container" id="contact">
    <h2>Contact Us</h2>
    <p>Email: rasoiroots@gmail.com</p>
    <p>Phone: +91 8954152963, +91 9411911398</p>
    <p>Address: Village - Atmadsarai, 203408, Bulandshahr</p>
    <div style="margin-top: 20px;">
      <iframe
        src="https://www.google.com/maps?q=Atmadsarai+Bulandshahr&output=embed"
        width="100%"
        height="300"
        style="border:0; border-radius: 10px;"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </div>
  </div>

  <div class="cart-section">
    <h4>Your Cart</h4>
    <div id="cart-items"></div>
    <button class="checkout-btn" onclick="checkout()">Checkout</button>
  </div>

  <div id="overlay" class="overlay" onclick="closeLogin()"></div>
  <div id="loginPopup" class="login-popup">
    <h3>Login</h3>
    <input type="email" id="email" placeholder="Email" required />
    <input type="password" id="password" placeholder="Password" required />
    <button onclick="loginUser()">Login</button>
    <button onclick="closeLogin()">Cancel</button>
  </div>

  <footer>
    &copy; 2025 RasoiRoots | Cash on Delivery Only | Designed with ❤️
  </footer>
</body>
</html>
