# Chaudhary-s-Business
website for homemade products
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RasoiRoots – Pure Homemade Spices</title>
  <style>
    * { margin:0; padding:0; box-sizing:border-box; }
    body { font-family:'Segoe UI',sans-serif; color:#333; line-height:1.6; }
    a { text-decoration:none; color:inherit; }
    ul { list-style:none; }
    header { position:fixed; top:0; width:100%; z-index:1000; background:#fff; box-shadow:0 2px 8px rgba(0,0,0,0.1);}
    .nav-container { max-width:1200px; margin:auto; display:flex; align-items:center; justify-content:space-between; padding:1rem; }
    .logo { font-weight:bold; font-size:1.5rem; color:#a83232; }
    nav ul { display:flex; gap:2rem; align-items:center; }
    nav a { font-weight:600; color:#333; cursor:pointer; }
    .cart-icon { position:relative; cursor:pointer; font-size:1.25rem; }
    .cart-count { position:absolute; top:-6px; right:-6px; background:#a83232; color:#fff; font-size:.75rem; padding:2px 6px; border-radius:50%; }
    .hero { height:70vh; background:#f4f0ec; display:flex; align-items:center; justify-content:center; text-align:center; padding-top:80px; }
    .hero h1 { font-size:2.75rem; margin-bottom:1rem; }
    .btn-primary { background:#a83232; color:#fff; padding:1rem 2rem; border:none; border-radius:5px; cursor:pointer; }
    .btn-primary:hover { background:#822e2e; }
    section { padding:4rem 1rem; max-width:1200px; margin:auto; }
    .grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:2rem; }
    .product, .review { background:#fff; padding:1.5rem; border-radius:8px; box-shadow:0 2px 8px rgba(0,0,0,0.05); }
    .product h3 { margin-bottom:.5rem; }
    .price { color:#a83232; font-weight:bold; margin-bottom:1rem; }
    .product button, .checkout-btn { background:#a83232; color:#fff; border:none; padding:.75rem 1.25rem; border-radius:5px; cursor:pointer; }
    .product button:hover, .checkout-btn:hover { background:#822e2e; }
    #reviews .review p { margin-bottom:.75rem; font-style:italic; }
    #reviews .review strong { color:#555; }
    .cart-drawer { position:fixed; top:0; right:-360px; width:360px; height:100%; background:#fff; box-shadow:-2px 0 12px rgba(0,0,0,0.15); transition:right .3s; z-index:1001; display:flex; flex-direction:column; }
    .cart-drawer.open { right:0; }
    .cart-header { padding:1.5rem; border-bottom:1px solid #eee; display:flex; justify-content:space-between; align-items:center; }
    .cart-items { flex:1; overflow-y:auto; padding:1.5rem; }
    .cart-item { margin-bottom:.75rem; }
    .cart-footer { padding:1.5rem; border-top:1px solid #eee; }
    .login-section { padding:4rem 1rem; background:#f9f7f4; margin-top:2rem; border-radius:8px; max-width:400px; margin:auto; }
    .login-section input { width:100%; padding:.75rem; margin-bottom:1rem; border:1px solid #ccc; border-radius:5px; }
    .overlay, .cart-drawer, .login-section { display:none; }
    .overlay.show { display:block; position:fixed; inset:0; background:rgba(0,0,0,0.5); z-index:1000; }
    footer { background:#a83232; color:#fff; text-align:center; padding:2rem 1rem; margin-top:2rem; }
  </style>
</head>
<body>

<header>
  <div class="nav-container">
    <div class="logo">RasoiRoots</div>
    <nav>
      <ul>
        <li><a onclick="scrollToSection('home')">Home</a></li>
        <li><a onclick="scrollToSection('products')">Products</a></li>
        <li><a onclick="scrollToSection('contact')">Contact</a></li>
        <li><a onclick="scrollToSection('login-section')">Login</a></li>
      </ul>
    </nav>
    <div>
      <span class="cart-icon" onclick="toggleCart()">🛒<span id="cart-count" class="cart-count">0</span></span>
    </div>
  </div>
</header>

<div id="home" class="hero">
  <div>
    <h1>Pure & Homemade Spices for Authentic Flavour</h1>
    <p>Hand-crafted blends to bring warmth & depth to your meals.</p>
    <button class="btn-primary" onclick="scrollToSection('products')">Shop Now</button>
  </div>
</div>

<section id="products">
  <h2 style="text-align:center; margin-bottom:2rem;">Our Products</h2>
  <div class="grid">
    <div class="product"><h3>Red Chilly Powder</h3><p class="price">₹70 / 200g</p><button onclick="addToCart('Red Chilly Powder')">Add to Cart</button></div>
    <div class="product"><h3>Coriander Powder</h3><p class="price">₹60 / 200g</p><button onclick="addToCart('Coriander Powder')">Add to Cart</button></div>
    <div class="product"><h3>Turmeric Powder</h3><p class="price">₹70 / 200g</p><button onclick="addToCart('Turmeric Powder')">Add to Cart</button></div>
    <div class="product"><h3>Garam Masala</h3><p class="price">₹200 / 200g</p><button onclick="addToCart('Garam Masala')">Add to Cart</button></div>
    <div class="product"><h3>Cumin Seeds</h3><p class="price">₹90 / 200g</p><button onclick="addToCart('Cumin Seeds')">Add to Cart</button></div>
    <div class="product"><h3>Besan (Gram Flour)</h3><p class="price">₹100 / 1kg</p><button onclick="addToCart('Besan')">Add to Cart</button></div>
    <div class="product"><h3>Mustard Oil</h3><p class="price">₹160 / 1kg</p><button onclick="addToCart('Mustard Oil')">Add to Cart</button></div>
  </div>
</section>

<section id="reviews">
  <h2 style="text-align:center; margin-bottom:2rem;">Customer Reviews</h2>
  <div class="grid">
    <div class="review"><p>“Absolutely love the flavors! My go-to for daily cooking.”</p><strong>– Seema K., Gurugram</strong></div>
    <div class="review"><p>“High-quality spices with authentic taste. Will purchase again!”</p><strong>– Rajiv S., Bulandshahr</strong></div>
    <div class="review"><p>“Fresh, aromatic, and perfect texture. Highly recommended.”</p><strong>– Anjali P., Noida</strong></div>
  </div>
</section>

<section id="contact">
  <h2 style="text-align:center;margin-bottom:2rem;">Contact Us</h2>
  <p style="text-align:center;">Email: rasoiroots@gmail.com<br>Phone: 8954152963, 9411911398<br>Address: Village – Atmadsarai, 203408, Bulandshahr</p>
  <iframe src="https://www.google.com/maps?q=Atmadsarai+Bulandshahr&output=embed"
    width="100%" height="300" style="border:0;border-radius:8px;margin-top:2rem;" loading="lazy"></iframe>
</section>

<section id="login-section" class="login-section">
  <h2 style="text-align:center;margin-bottom:1rem;">Member Login</h2>
  <input id="email" type="email" placeholder="Email">
  <input id="password" type="password" placeholder="Password">
  <button onclick="loginUser()">Login</button>
</section>

<div id="cartDrawer" class="cart-drawer">
  <div class="cart-header"><h4>Your Cart</h4><button onclick="toggleCart()">✕</button></div>
  <div id="cartItems" class="cart-items"></div>
  <div class="cart-footer">
    <button class="checkout-btn" onclick="checkout()">Checkout</button>
    <hr style="margin:1rem 0;">
    <h4>Track Order</h4>
    <input id="orderId" type="text" placeholder="Order ID (e.g. #1234)" style="width:100%; padding:.75rem; border:1px solid #ccc; border-radius:5px; margin: .5rem 0;">
    <button class="checkout-btn" onclick="trackOrder()">Track</button>
    <p id="trackResult" style="margin-top:.75rem; color:#444;"></p>
  </div>
</div>

<div id="overlay" class="overlay"></div>

<footer>
  &copy; 2025 RasoiRoots | Cash on Delivery Only | Designed with ❤️
</footer>

<script>
  function scrollToSection(id) {
    document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
  }

  let cart = [];
  function toggleCart() {
    document.getElementById('cartDrawer').classList.toggle('open');
    document.getElementById('overlay').classList.toggle('show');
  }

  function addToCart(item) {
    cart.push(item);
    document.getElementById('cart-count').textContent = cart.length;
    updateCartItems();
    if (!document.getElementById('cartDrawer').classList.contains('open')) toggleCart();
  }

  function updateCartItems() {
    document.getElementById('cartItems').innerHTML =
      cart.map((itm,i)=>`<div class="cart-item">${i+1}. ${itm}</div>`).join('');
  }

  function checkout() {
    if (!cart.length) return alert('Cart is empty');
    alert('Order placed: ' + cart.join(', '));
    cart=[]; document.getElementById('cart-count').textContent=0; updateCartItems();
    toggleCart();
  }

  function trackOrder() {
    const id=document.getElementById('orderId').value.trim();
    document.getElementById('trackResult').textContent = id
      ? `📦 Order ${id} is in process. Delivery in 3–5 days.`
      : '⚠️ Please enter a valid Order ID.';
  }

  function loginUser() {
    const email=document.getElementById('email').value.trim();
    const pwd=document.getElementById('password').value.trim();
    alert(email==='user@example.com'&&pwd==='password123' ? 'Login successful' : 'Login failed');
  }
</script>
</body>
</html>
