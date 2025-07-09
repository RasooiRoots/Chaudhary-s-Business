# Chaudhary-s-Business
website for homemade products
<!DOCTYPE html>
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
