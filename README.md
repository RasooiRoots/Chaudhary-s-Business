# Chaudhary-s-Business
website for homemade products
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RasoiRoots - Pure Homemade Spices</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body, button { font-family: 'Segoe UI', sans-serif; }
    a { text-decoration: none; color: inherit; }
    ul { list-style: none; }
    header { position: fixed; top: 0; width: 100%; z-index: 1000; background: #fff; box-shadow: 0 2px 8px rgba(0,0,0,0.1); }
    .nav-container { max-width: 1200px; margin: auto; display: flex; align-items: center; justify-content: space-between; padding: 1rem; }
    .logo { font-weight: bold; font-size: 1.5rem; color: #a83232; }
    nav ul { display: flex; gap: 2rem; }
    nav a { font-weight: 600; color: #333; }
    .cart-icon { position: relative; cursor: pointer; }
    .cart-count { position: absolute; top: -6px; right: -6px; background: #a83232; color: #fff; font-size: .75rem; padding: 2px 6px; border-radius: 50%; }
    .hero { height: 80vh; background: #f4e9e1; display: flex; align-items: center; justify-content: center; text-align: center; color: #333; margin-top: 80px; }
    .hero-content h1 { font-size: 3rem; margin-bottom: 1rem; }
    .btn-primary { background: #a83232; color: #fff; padding: 1rem 2rem; border: none; border-radius: 4px; font-size: 1rem; cursor: pointer; }
    .btn-primary:hover { background: #822e2e; }
    section#products, section#contact { padding: 4rem 1rem; }
    .products-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem; max-width: 1200px; margin: auto; }
    .product { background: #fff; padding: 1rem; border-radius: 10px; box-shadow: 0 2px 8px rgba(0,0,0,0.05); text-align: center; }
    .price { color: #a83232; font-weight: bold; font-size: 1.2rem; margin: 1rem 0; }
    .product button { background: #a83232; color: white; padding: 10px 15px; border: none; border-radius: 5px; cursor: pointer; }
    .product button:hover { background: #822e2e; }
    .cart-drawer { position: fixed; top: 0; right: -320px; width: 320px; height: 100%; background: #fff; box-shadow: -2px 0 8px rgba(0,0,0,0.1); transition: right .3s; z-index: 1001; display: flex; flex-direction: column; }
    .cart-drawer.open { right: 0; }
    .cart-header, .cart-footer { padding: 1rem; border-bottom: 1px solid #eee; }
    .cart-items { flex: 1; padding: 1rem; overflow-y: auto; }
    .cart-item { margin-bottom: .75rem; border-bottom: 1px solid #f0f0f0; padding-bottom: .5rem; }
    .checkout-btn { width: 100%; background: #822e2e; color: white; padding: 10px; border: none; border-radius: 4px; cursor: pointer; }
    footer { background-color: #a83232; color: #fff; text-align: center; padding: 2rem .5rem; }
    .overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.5); display: none; z-index: 1002; }
    .login-popup { position: fixed; top: 50%; left: 50%; transform: translate(-50%,-50%); background: #fff; padding: 2rem; border-radius: 8px; width: 320px; box-shadow: 0 0 12px rgba(0,0,0,0.2); z-index: 1003; display: none; }
    .login-popup input { width: 100%; padding: .75rem; margin-bottom: 1rem; border: 1px solid #ddd; border-radius: 4px; }
  </style>
</head>
<body>

<header>
  <div class="nav-container">
    <div class="logo">RasoiRoots</div>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#products">Products</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><a href="track.html">Track Order</a></li>
      </ul>
    </nav>
    <div>
      <button onclick="showLogin()">Login</button>
      <span class="cart-icon" onclick="toggleCart()">🛒<span class="cart-count" id="cart-count">0</span></span>
    </div>
  </div>
</header>

<div class="hero" id="home">
  <div class="hero-content">
    <h1>Pure & Homemade Spices for Authentic Flavour</h1>
    <p>Hand-crafted blends to bring warmth & depth to your meals.</p>
    <button class="btn-primary" onclick="document.getElementById('products').scrollIntoView()">Shop Now</button>
  </div>
</div>

<section id="products">
  <h2 style="text-align:center;margin-bottom:2rem;">Our Products</h2>
  <div class="products-grid">
    <div class="product"><h3>Red Chilly Powder</h3><p class="price">₹70 / 200g</p><button onclick="addToCart('Red Chilly Powder')">Add to Cart</button></div>
    <div class="product"><h3>Coriander Powder</h3><p class="price">₹60 / 200g</p><button onclick="addToCart('Coriander Powder')">Add to Cart</button></div>
    <div class="product"><h3>Turmeric Powder</h3><p class="price">₹70 / 200g</p><button onclick="addToCart('Turmeric Powder')">Add to Cart</button></div>
  </div>
</section>

<section id="contact">
  <h2>Contact Us</h2>
  <p style="text-align:center;">
    Email: rasoiroots@gmail.com<br>
    Phone: 8954152963, 9411911398<br>
    Address: Village – Atmadsarai, 203408, Bulandshahr
  </p>
  <iframe src="https://www.google.com/maps?q=Atmadsarai+Bulandshahr&output=embed"
    width="100%" height="300" style="border:0;border-radius:8px;margin-top:2rem;" loading="lazy"></iframe>
</section>

<footer>
  &copy; 2025 RasoiRoots | Cash on Delivery Only | Designed with ❤️
</footer>

<div class="cart-drawer" id="cartDrawer">
  <div class="cart-header">
    <h4>Your Cart</h4>
    <button onclick="toggleCart()">✕</button>
  </div>
  <div class="cart-items" id="cartItemsList"></div>
  <div class="cart-footer">
    <button class="checkout-btn" onclick="checkout()">Checkout</button>
  </div>
</div>

<div class="overlay" id="overlay" onclick="closeLogin()"></div>
<div class="login-popup" id="loginPopup">
  <h3>Login</h3>
  <input type="email" id="email" placeholder="Email">
  <input type="password" id="password" placeholder="Password">
  <button onclick="loginUser()">Login</button>
</div>

<script>
  let cart = [];

  function toggleCart() {
    document.getElementById('cartDrawer').classList.toggle('open');
  }

  function addToCart(item) {
    cart.push(item);
    document.getElementById('cart-count').textContent = cart.length;
    renderCart();
    document.getElementById('cartDrawer').classList.add('open');
  }

  function renderCart() {
    const list = document.getElementById('cartItemsList');
    list.innerHTML = cart.map((item, i) => `<div class="cart-item">${i + 1}. ${item}</div>`).join('');
  }

  function checkout() {
    if (!cart.length) return alert("Your cart is empty.");
    alert("Order received: " + cart.join(", "));
    cart = [];
    document.getElementById('cart-count').textContent = 0;
    renderCart();
    toggleCart();
  }

  function showLogin() {
    document.getElementById("overlay").style.display = "block";
    document.getElementById("loginPopup").style.display = "block";
  }

  function closeLogin() {
    document.getElementById("overlay").style.display = "none";
    document.getElementById("loginPopup").style.display = "none";
  }

  function loginUser() {
    const email = document.getElementById("email").value.trim();
    const password = document.getElementById("password").value.trim();
    if (email === "user@example.com" && password === "password123") {
      alert("Login successful!");
      closeLogin();
    } else {
      alert("Invalid email or password.");
    }
  }
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Track Your Order | RasoiRoots</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body { margin: 0; font-family: 'Segoe UI', sans-serif; background: #fef8f3; color: #333; }
    header { background-color: #a83232; color: white; padding: 1.5rem; text-align: center; }
    main { padding: 2rem; max-width: 600px; margin: auto; background: #fff; box-shadow: 0 2px 12px rgba(0,0,0,0.05); border-radius: 10px; margin-top: 2rem; }
    h1 { text-align: center; margin-bottom: 2rem; font-size: 2rem; }
    input[type="text"] { width: 100%; padding: 1rem; margin-bottom: 1rem; border: 1px solid #ccc; border-radius: 5px; font-size: 1rem; }
    button { width: 100%; padding: 1rem; background-color: #a83232; color: white; font-size: 1rem; border: none; border-radius: 5px; cursor: pointer; }
    button:hover { background-color: #822e2e; }
    .result { margin-top: 2rem; text-align: center; font-size: 1.1rem; color: #444; }
    footer { margin-top: 3rem; text-align: center; padding: 1rem; background: #a83232; color: white; }
  </style>
</head>
<body>

<header>
  <h2>RasoiRoots</h2>
  <p>Track Your Order</p>
</header>

<main>
  <h1>Order Tracking</h1>
  <input type="text" id="orderId" placeholder="Enter your Order ID (e.g. #1234)">
  <button onclick="trackOrder()">Track Order</button>
  <div id="result" class="result"></div>
</main>

<footer>
  &copy; 2025 RasoiRoots | For any query email us at rasoiroots@gmail.com
</footer>

<script>
  function trackOrder() {
    const id = document.getElementById("orderId").value.trim();
    const result = document.getElementById("result");
    if (!id) {
      result.innerHTML = "⚠️ Please enter a valid Order ID.";
    } else {
      result.innerHTML = `📦 Your order <strong>${id}</strong> is in transit.<br>Expected delivery in <strong>3–5 business days</strong>.`;
    }
  }
</script>

</body>
</html>
