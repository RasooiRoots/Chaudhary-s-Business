# Chaudhary-s-Business
website for homemade products
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RasoiRoots - Pure Homemade Spices</title>
  <link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>🌶️</text></svg>">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body, button { font-family: 'Segoe UI', sans-serif; }
    a { text-decoration: none; color: inherit; }
    ul { list-style: none; }

    header {
      position: fixed; top: 0; width: 100%; z-index: 1000;
      background: #fff; box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
    .nav-container {
      max-width: 1200px; margin: auto;
      display: flex; align-items: center;
      justify-content: space-between; padding: 1rem;
    }
    .logo { font-weight: bold; font-size: 1.5rem; color: #a83232; }
    nav ul { display: flex; gap: 2rem; }
    nav a { font-weight: 600; color: #333; }
    .cart-icon {
      position: relative; cursor: pointer;
    }
    .cart-count {
      position: absolute; top: -6px; right: -6px;
      background: #a83232; color: #fff;
      font-size: .75rem; padding: 2px 6px;
      border-radius: 50%;
    }

    .hero {
      height: 80vh; background: #f4e9e1;
      display: flex; align-items: center;
      justify-content: center; text-align: center;
      color: #333; margin-top: 80px;
    }
    .hero-content h1 {
      font-size: 3rem; margin-bottom: 1rem;
    }
    .btn-primary {
      background: #a83232; color: #fff;
      padding: 1rem 2rem; border: none;
      border-radius: 4px; font-size: 1rem;
      cursor: pointer;
    }
    .btn-primary:hover { background: #822e2e; }

    section#products, section#contact {
      padding: 4rem 1rem;
    }
    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem; max-width: 1200px; margin: auto;
    }
    .product {
      background: #fff;
      padding: 1rem;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.05);
      text-align: center;
    }
    .price {
      color: #a83232; font-weight: bold;
      font-size: 1.2rem; margin: 1rem 0;
    }
    .product button {
      background: #a83232; color: white;
      padding: 10px 15px; border: none;
      border-radius: 5px; cursor: pointer;
    }
    .product button:hover { background: #822e2e; }

    .cart-drawer {
      position: fixed; top: 0; right: -320px;
      width: 320px; height: 100%;
      background: #fff; box-shadow: -2px 0 8px rgba(0,0,0,0.1);
      transition: right .3s; z-index: 1001;
      display: flex; flex-direction: column;
    }
    .cart-drawer.open { right: 0; }
    .cart-header, .cart-footer {
      padding: 1rem; border-bottom: 1px solid #eee;
    }
    .cart-items { flex: 1; padding: 1rem; overflow-y: auto; }
    .cart-item {
      margin-bottom: .75rem;
      border-bottom: 1px solid #f0f0f0;
      padding-bottom: .5rem;
    }
    .checkout-btn {
      width: 100%; background: #822e2e; color: white;
      padding: 10px; border: none; border-radius: 4px;
      cursor: pointer;
    }

    footer {
      background-color: #a83232;
      color: #fff;
      text-align: center;
      padding: 2rem .5rem;
    }

    .overlay {
      position: fixed; inset: 0;
      background: rgba(0,0,0,0.5);
      display: none; z-index: 1002;
    }
    .login-popup {
      position: fixed; top: 50%; left: 50%;
      transform: translate(-50%,-50%);
      background: #fff; padding: 2rem;
      border-radius: 8px; width: 320px;
      box-shadow: 0 0 12px rgba(0,0,0,0.2);
      z-index: 1003; display: none;
    }
    .login-popup input {
      width: 100%; padding: .75rem;
      margin-bottom: 1rem; border: 1px solid #ddd;
      border-radius: 4px;
    }

    .testimonial {
      background: #fff0e6;
      padding: 4rem 1rem;
      text-align: center;
    }

    #loader {
      position: fixed; top: 0; left: 0;
      width: 100%; height: 100%;
      background: white;
      display: flex; align-items: center;
      justify-content: center;
      font-size: 2rem; color: #a83232;
      z-index: 2000;
    }
  </style>
</head>
<body>

<div id="loader">Loading...</div>

<header>
  <div class="nav-container">
    <div class="logo">RasoiRoots</div>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#products">Products</a></li>
        <li><a href="#contact">Contact</a></li>
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
  <div style="text-align:center;margin-bottom:2rem;">
    <input type="text" id="searchInput" placeholder="Search products..." onkeyup="filterProducts()" style="padding:10px;width:300px;border:1px solid #ccc;border-radius:4px;">
  </div>
  <div class="products-grid">
    <div class="product"><h3>Red Chilly Powder</h3><p class="price">₹70 / 200g</p><button onclick="addToCart('Red Chilly Powder')">Add to Cart</button></div>
    <div class="product"><h3>Coriander Powder</h3><p class="price">₹60 / 200g</p><button onclick="addToCart('Coriander Powder')">Add to Cart</button></div>
    <div class="product"><h3>Turmeric Powder</h3><p class="price">₹70 / 200g</p><button onclick="addToCart('Turmeric Powder')">Add to Cart</button></div>
    <div class="product"><h3>Garam Masala</h3><p class="price">₹200 / 200g</p><button onclick="addToCart('Garam Masala')">Add to Cart</button></div>
    <div class="product"><h3>Cumin Seeds</h3><p class="price">₹90 / 200g</p><button onclick="addToCart('Cumin Seeds')">Add to Cart</button></div>
    <div class="product"><h3>Besan</h3><p class="price">₹100 / 1kg</p><button onclick="addToCart('Besan')">Add to Cart</button></div>
    <div class="product"><h3>Mustard Oil</h3><p class="price">₹160 / 1kg</p><button onclick="addToCart('Mustard Oil')">Add to Cart</button></div>
  </div>
</section>

<section class="testimonial">
  <h2 style="margin-bottom:2rem;">What Our Customers Say</h2>
  <blockquote style="font-style:italic;color:#444;">
    “RasoiRoots masalas bring back the taste of my childhood. Pure, aromatic, and perfect!”
  </blockquote>
  <p style="margin-top:1rem;font-weight:bold;">— Aarti Sharma, Delhi</p>
</section>

<section id="contact">
  <h2 style="text-align:center;margin-bottom:2rem;">Contact Us</h2>
  <p style="text-align:center;">
    <strong>Email:</strong> rasoiroots@gmail.com<br>
    <strong>Phone:</strong> +91 8954152963, +91 9411911398<br>
    <strong>Address:</strong> Village – Atmadsarai, 203408, Bulandshahr
  </p>
  <iframe src="https://www.google.com/maps?q=Atmadsarai+Bulandshahr&output=embed" width="100%" height="300" style="border:0;border-radius:8px;margin-top:2rem;" loading="lazy"></iframe>
</section>

<footer>&copy; 2025 RasoiRoots | Cash on Delivery Only | Designed with ❤️</footer>

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
  window.addEventListener("load", function () {
    document.getElementById("loader").style.display = "none";
  });

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
    if (cart.length === 0) return alert("Your cart is empty.");
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
    const e = document.getElementById('email').value;
    const p = document.getElementById('password').value;
    if (e === "user@example.com" && p === "password123") {
      alert("Login successful!");
      closeLogin();
    } else {
      alert("Invalid email or password.");
    }
  }

  function filterProducts() {
    const query = document.getElementById("searchInput").value.toLowerCase();
    document.querySelectorAll(".product").forEach(card => {
      const name = card.querySelector("h3").textContent.toLowerCase();
      card.style.display = name.includes(query) ? "block" : "none";
    });
  }
</script>

</body>
</html>
