# Chaudhary-s-Business
website for homemade products
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" /><meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RasoiRoots - Pure Homemade Spices</title>
  <style>
    /* Reset & base */
    *{margin:0;padding:0;box-sizing:border-box;}
    body,button{font-family:'Segoe UI',sans-serif;}
    a{text-decoration:none;color:inherit;}
    ul{list-style:none;}

    /* Navbar */
    header{position:fixed;top:0;width:100%;z-index:1000;transition:background .3s;}
    header.scrolled{background:#fff;box-shadow:0 2px 8px rgba(0,0,0,0.1);}
    .nav-container{max-width:1200px;margin:auto;display:flex;align-items:center;justify-content:space-between;padding:1rem;}
    .logo img{height:40px;}
    nav ul{display:flex;gap:2rem;}
    nav a{font-weight:600;color:#333;}
    .cart-icon{position:relative;cursor:pointer;}
    .cart-count{position:absolute;top:-6px;right:-6px;background:#a83232;color:#fff;font-size:.75rem;padding:2px 6px;border-radius:50%;}

    /* Hero */
    .hero{height:80vh;background:url('https://via.placeholder.com/1600x900')center/cover;display:flex;align-items:center;justify-content:center;text-align:center;color:#fff;}
    .hero-content h1{font-size:3rem;margin-bottom:1rem;}
    .btn-primary{background:#a83232;color:#fff;padding:1rem 2rem;border:none;border-radius:4px;font-size:1rem;cursor:pointer;transition:background .3s;}
    .btn-primary:hover{background:#822e2e;}

    /* Products */
    section#products{padding:4rem 1rem;background:#f9f7f4;}
    .products-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:2rem;max-width:1200px;margin:auto;}
    .product{background:#fff;border-radius:8px;overflow:hidden;box-shadow:0 2px 8px rgba(0,0,0,0.05);text-align:center;transition:transform .3s;}
    .product:hover{transform:translateY(-5px);}
    .product img{width:100%;height:200px;object-fit:cover;}
    .product-info{padding:1rem;}
    .price{color:#a83232;font-weight:bold;font-size:1.2rem;margin:1rem 0;}
    .product button{background:#a83232;color:#fff;padding:.75rem 1rem;border:none;border-radius:4px;cursor:pointer;transition:background .3s;}
    .product button:hover{background:#822e2e;}

    /* Cart drawer */
    .cart-drawer{position:fixed;top:0;right:-320px;width:320px;height:100%;background:#fff;box-shadow:-2px 0 8px rgba(0,0,0,0.1);transition:right .4s;z-index:1001;display:flex;flex-direction:column;}
    .cart-drawer.open{right:0;}
    .cart-header{padding:1rem;border-bottom:1px solid #eee;display:flex;justify-content:space-between;align-items:center;}
    .cart-items{flex:1;overflow:auto;padding:1rem;}
    .cart-item{margin-bottom:.75rem;border-bottom:1px solid #f0f0f0;padding-bottom:.5rem;}
    .cart-footer{padding:1rem;border-top:1px solid #eee;}
    .checkout-btn{width:100%;background:#822e2e;color:#fff;padding: .75rem;border:none;border-radius:4px;cursor:pointer;}

    /* Sections */
    section#contact{padding:4rem 1rem;max-width:800px;margin:auto;text-align:center;}
    footer{background:#a83232;color:#fff;text-align:center;padding:2rem .5rem;margin-top:4rem;}

    /* Login Popup */
    .overlay{position:fixed;inset:0;background:rgba(0,0,0,0.5);display:none;z-index:1002;}
    .login-popup{position:fixed;top:50%;left:50%;transform:translate(-50%,-50%);background:#fff;padding:2rem;border-radius:8px;box-shadow:0 0 12px rgba(0,0,0,0.2);width:320px;z-index:1003;display:none;}
    .login-popup h3{margin-bottom:1rem;}
    .login-popup input{width:100%;padding:.75rem;margin-bottom:1rem;border:1px solid #ddd;border-radius:4px;}
    .login-popup button{width:100%;padding:.75rem;background:#a83232;color:#fff;border:none;border-radius:4px;cursor:pointer;transition:background .3s;}
    .login-popup button:hover{background:#822e2e;}

    /* Scroll offset for anchors */
    .anchor{display:block;padding-top:100px;margin-top:-100px;}
  </style>
</head>
<body>

<header id="header">
  <div class="nav-container">
    <a href="#home" class="logo"><img src="/mnt/data/182f1ecd-efcc-4ac9-9ac5-478e394ddcf2.jpg" alt="RasoiRoots"></a>
    <nav><ul><li><a href="#home">Home</a></li><li><a href="#products">Products</a></li><li><a href="#contact">Contact</a></li></ul></nav>
    <div>
      <button class="login-btn" onclick="showLogin()">Login</button>
      <span class="cart-icon" onclick="toggleCart()">🛒<span class="cart-count" id="cart-count">0</span></span>
    </div>
  </div>
</header>

<div class="hero" id="home"><div class="hero-content anchor"><h1>Pure & Homemade Spices for Authentic Flavour</h1><p>Hand-crafted blends to bring warmth & depth to your meals.</p><button class="btn-primary" onclick="document.getElementById('products').scrollIntoView()">Shop Now</button></div></div>

<section id="products"><div class="anchor"></div><h2 style="text-align:center;margin-bottom:2rem;">Our Products</h2><div class="products-grid">
  <div class="product"><img src="https://via.placeholder.com/400x300" alt=""><div class="product-info"><h3>Red Chilly Powder</h3><p class="price">₹70 / 200g</p><button onclick="addToCart('Red Chilly Powder')">Add to Cart</button></div></div>
  <div class="product"><img src="https://via.placeholder.com/400x300" alt=""><div class="product-info"><h3>Coriander Powder</h3><p class="price">₹60 / 200g</p><button onclick="addToCart('Coriander Powder')">Add to Cart</button></div></div>
  <div class="product"><img src="https://via.placeholder.com/400x300" alt=""><div class="product-info"><h3>Turmeric Powder</h3><p class="price">₹70 / 200g</p><button onclick="addToCart('Turmeric Powder')">Add to Cart</button></div></div>
  <div class="product"><img src="https://via.placeholder.com/400x300" alt=""><div class="product-info"><h3>Garam Masala</h3><p class="price">₹200 / 200g</p><button onclick="addToCart('Garam Masala')">Add to Cart</button></div></div>
  <div class="product"><img src="https://via.placeholder.com/400x300" alt=""><div class="product-info"><h3>Cumin Seeds</h3><p class="price">₹90 / 200g</p><button onclick="addToCart('Cumin Seeds')">Add to Cart</button></div></div>
  <div class="product"><img src="https://via.placeholder.com/400x300" alt=""><div class="product-info"><h3>Besan (Gram Flour)</h3><p class="price">₹100 / 1kg</p><button onclick="addToCart('Besan')">Add to Cart</button></div></div>
  <div class="product"><img src="https://via.placeholder.com/400x300" alt=""><div class="product-info"><h3>Mustard Oil</h3><p class="price">₹160 / 1kg</p><button onclick="addToCart('Mustard Oil')">Add to Cart</button></div></div>
</div></section>

<section id="contact"><div class="anchor"></div><h2 style="text-align:center;margin-bottom:2rem;">Contact Us</h2><p><strong>Email:</strong> rasoiroots@gmail.com</p><p><strong>Phone:</strong> +91 8954152963, +91 9411911398</p><p><strong>Address:</strong> Village – Atmadsarai, 203408, Bulandshahr</p><iframe src="https://www.google.com/maps?q=Atmadsarai+Bulandshahr&output=embed" width="100%" height="300" style="border:0;border-radius:8px;margin-top:1rem;" loading="lazy"></iframe></section>

<div class="cart-drawer" id="cartDrawer">
  <div class="cart-header"><h4>Your Cart</h4><button onclick="toggleCart()">✕</button></div>
  <div class="cart-items" id="cartItemsList"></div>
  <div class="cart-footer"><button class="checkout-btn" onclick="checkout()">Checkout</button></div>
</div>

<div class="overlay" id="overlay" onclick="closeLogin()"></div>
<div class="login-popup" id="loginPopup">
  <h3>Login</h3><input type="email" id="email" placeholder="Email"><input type="password" id="password" placeholder="Password">
  <button onclick="loginUser()">Login</button>
</div>

<footer>&copy; 2025 RasoiRoots | Cash on Delivery Only | Designed with ❤️</footer>

<script>
  // Navbar background on scroll
  window.addEventListener('scroll',()=> document.getElementById('header').classList.toggle('scrolled',window.scrollY>50));

  // Cart drawer logic
  const drawer = document.getElementById('cartDrawer'), countEl = document.getElementById('cart-count'), listEl = document.getElementById('cartItemsList');
  let cart = [];
  function toggleCart(){drawer.classList.toggle('open');}
  function addToCart(item){
    cart.push(item);
    countEl.textContent = cart.length;
    renderCart();
    drawer.classList.add('open');
  }
  function renderCart(){
    listEl.innerHTML = cart.map((i,idx)=>`<div class="cart-item">${idx+1}. ${i}</div>`).join('');
  }
  function checkout(){
    if(cart.length===0)return alert('Your cart is empty.');
    alert('Order received: '+cart.join(', '));
    cart=[]; countEl.textContent=0; renderCart(); toggleCart();
  }
  // Login popup
  const overlay=document.getElementById('overlay'), loginBox=document.getElementById('loginPopup');
  function showLogin(){overlay.style.display='block';loginBox.style.display='block';}
  function closeLogin(){overlay.style.display='none';loginBox.style.display='none';}
  function loginUser(){
    const e=document.getElementById('email').value, p=document.getElementById('password').value;
    if(e==='user@example.com'&&p==='password123'){alert('Login successful!');closeLogin();}
    else alert('Invalid credentials.');
  }
</script>
</body>
</html>
