# Chaudhary-s-Business
website for homemade products
<!DOCTYPE html><html lang="en"><head>
<meta charset="UTF-8"/><meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>RasoiRoots – Pure Homemade Spices</title>
<link rel="stylesheet" href="https://unpkg.com/swiper/swiper-bundle.min.css"/>
<link rel="stylesheet" href="https://unpkg.com/aos@2.3.4/dist/aos.css"/>
<style>
  *{margin:0;padding:0;box-sizing:border-box}body,button,input{font-family:'Segoe UI',sans-serif;scroll-behavior:smooth;}
  a{text-decoration:none;color:inherit;}ul{list-style:none;}
  header{position:fixed;top:0;width:100%;z-index:1000;display:flex;align-items:center;justify-content:space-between;padding:1rem 2rem;transition:background .3s;color:#fff;}
  header.scrolled{background:#fff;box-shadow:0 2px 8px rgba(0,0,0,.1);color:#333}
  .logo{font-size:1.6rem;font-weight:bold;color:inherit;}
  nav ul{display:flex;gap:1.5rem;}
  nav a{cursor:pointer;font-weight:600;color:inherit;}
  .menu-toggle{display:none;cursor:pointer;font-size:1.5rem;}
  .hero{padding-top:80px;}
  .swiper-container{width:100%;height:70vh;}
  .swiper-slide{background:#f4f0ec;display:flex;align-items:center;justify-content:center;font-size:2.5rem;color:#333;}
  section{padding:4rem 2rem;max-width:1200px;margin:auto;}
  .grid{display:grid;gap:1.5rem;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));}
  .product, .review{background:#fff;padding:1.5rem;border-radius:8px;box-shadow:0 2px 8px rgba(0,0,0,.05);position:relative;}
  .product h3{margin-bottom:.5rem;} .price{color:#a83232;font-weight:700;margin:.5rem 0;}
  .qty{display:flex;gap:.5rem;align-items:center;margin:1rem 0;}
  .qty button{width:30px;height:30px;border:none;background:#ddd;border-radius:4px;cursor:pointer;}
  .btn-primary{background:#a83232;color:#fff;padding:.75rem 1.5rem;border:none;border-radius:5px;cursor:pointer;}
  .btn-primary:hover{background:#822e2e;}
  #reviews .review p{font-style:italic;margin-bottom:1rem;}
  #reviews .review strong{color:#555;}
  .newsletter input{padding:.75rem;width:65%;border:1px solid #ccc;border-radius:5px;}
  .newsletter button{padding:.75rem 1.5rem;border:none;background:#a83232;color:#fff;border-radius:5px;cursor:pointer;}
  .login-modal,.overlay,.cart-drawer{position:fixed;}
  .overlay{inset:0;background:rgba(0,0,0,.5);z-index:1000;display:none;}
  .login-modal{top:50%;left:50%;transform:translate(-50%,-50%);width:320px;padding:2rem;background:#fff;border-radius:8px;box-shadow:0 2px 12px rgba(0,0,0,.2);z-index:1001;display:none;}
  .login-modal input{width:100%;padding:.75rem;margin:0.5rem 0;border:1px solid #ccc;border-radius:5px;}
  .cart-drawer{top:0;right:-360px;width:360px;height:100%;background:#fff;z-index:1002;box-shadow:-2px 0 12px rgba(0,0,0,.15);display:flex;flex-direction:column;transition:right .3s;}
  .cart-drawer.open{right:0;} .cart-header{padding:1.5rem;border-bottom:1px solid #eee;display:flex;justify-content:space-between;}
  .cart-items{flex:1;overflow-y:auto;padding:1.5rem;} .cart-item{display:flex;justify-content:space-between;margin-bottom:1rem;}
  .cart-footer{padding:1.5rem;border-top:1px solid #eee;}
  footer{background:#a83232;color:#fff;text-align:center;padding:2rem;}
  @media(max-width:768px){nav ul{display:none;position:absolute;top:70px;left:0;width:100%;flex-direction:column;background:#fff;color:#333;}nav ul.show{display:flex;} .menu-toggle{display:block;color:inherit;}}
</style>
</head>
<body>
<header id="header">
  <div class="logo">RasoiRoots</div>
  <div class="menu-toggle" onclick="toggleMenu()">☰</div>
  <nav><ul id="menu"><li><a onclick="scrollTo('hero')">Home</a></li><li><a onclick="scrollTo('products')">Products</a></li><li><a onclick="scrollTo('reviews')">Reviews</a></li><li><a onclick="scrollTo('newsletter')">Subscribe</a></li><li><a onclick="scrollTo('contact')">Contact</a></li><li><a onclick="openLogin()">Login</a></li></ul></nav>
  <div><span class="cart-icon" onclick="toggleCart()">🛒<span id="cartCount" class="cart-count">0</span></span></div>
</header>
<div class="hero" id="hero">
  <div class="swiper-container"><div class="swiper-wrapper">
    <div class="swiper-slide">Pure Homemade Spices<br><button class="btn-primary" onclick="scrollTo('products')">Shop Now</button></div>
    <div class="swiper-slide">Authentic Flavours Await<br><button class="btn-primary" onclick="scrollTo('products')">Browse Products</button></div>
  </div><div class="swiper-pagination"></div></div>
</div>
<section id="products" data-aos="fade-up">
  <h2 style="text-align:center;margin-bottom:2rem;">Our Products</h2>
  <div style="text-align:center;margin-bottom:2rem;"><input id="search" type="text" placeholder="Search products..." style="padding:.75rem 1rem;width:300px;border:1px solid #ccc;border-radius:5px;"></div>
  <div class="grid" id="productList"></div>
</section>
<section id="reviews" data-aos="fade-up">
  <h2 style="text-align:center;margin-bottom:2rem;">Customer Reviews</h2>
  <div class="swiper-container"><div class="swiper-wrapper">
    <div class="swiper-slide review"><p>“Exceptional aroma and taste—feel like home cooking!”</p><strong>– Seema K.</strong></div>
    <div class="swiper-slide review"><p>“Loved it! Authentic Indian flavour, high quality!”</p><strong>– Rajiv S.</strong></div>
    <div class="swiper-slide review"><p>“Genuine masalas with perfect grind and freshness.”</p><strong>– Anjali P.</strong></div>
  </div><div class="swiper-pagination"></div></div>
</section>
<section id="newsletter" data-aos="fade-up">
  <h2 style="text-align:center;margin-bottom:2rem;">Stay Updated</h2>
  <div class="newsletter" style="text-align:center;">
    <input type="email" placeholder="Enter your email"><button onclick="alert('Subscribed!')">Subscribe</button>
  </div>
</section>
<section id="contact" data-aos="fade-up">
  <h2 style="text-align:center;margin-bottom:2rem;">Contact Us</h2>
  <p style="text-align:center;">Email: rasoiroots@gmail.com<br>Phone: 8954152963, 9411911398<br>Address: Atmadsarai, Bulandshahr</p>
  <iframe src="https://www.google.com/maps?q=Atmadsarai+Bulandshahr&output=embed" width="100%" height="300" style="border:0;border-radius:8px;" loading="lazy"></iframe>
</section>
<!-- Cart Drawer -->
<div class="cart-drawer" id="cartDrawer">
  <div class="cart-header"><h4>Your Cart</h4><button onclick="toggleCart()">✕</button></div>
  <div class="cart-items" id="cartItems"></div>
  <div class="cart-footer">
    <button class="checkout-btn" onclick="checkout()">Checkout</button><hr style="margin:1rem 0;">
    <h4>Track Order</h4><input id="orderId" type="text" placeholder="Order ID (e.g. #1234)" style="width:100%;padding:.75rem;border:1px solid #ccc;border-radius:5px;">
    <button class="checkout-btn" onclick="trackOrder()">Track</button><p id="trackRes" style="margin-top:1rem;color:#444;"></p>
  </div>
</div>
<!-- Login Modal -->
<div class="overlay" id="overlay"></div>
<div class="login-modal" id="loginModal">
  <h3>Login to RasoiRoots</h3>
  <input id="email" type="email" placeholder="Email">
  <input id="password" type="password" placeholder="Password">
  <button class="btn-primary" onclick="loginUser()">Login</button>
  <p><small>Use user@example.com / password123</small></p>
</div>
<footer>©2025 RasoiRoots | Cash on Delivery Only | Designed with ❤️</footer>
<script src="https://unpkg.com/swiper/swiper-bundle.min.js"></script>
<script src="https://unpkg.com/aos@2.3.4/dist/aos.js"></script>
<script>
  AOS.init({duration:800,once:true});
  const swiperHero=new Swiper('.hero .swiper-container',{pagination:{el:'.swiper-pagination',clickable:true},autoplay:{delay:4000}});
  const swiperReviews=new Swiper('#reviews .swiper-container',{slidesPerView:1,loop:true,pagination:{el:'.swiper-pagination'},autoplay:{delay:3500}});
  const products=[{name:'Red Chilly Powder',price:70},{name:'Coriander Powder',price:60},{name:'Turmeric Powder',price:70},{name:'Garam Masala',price:200},{name:'Cumin Seeds',price:90},{name:'Besan',price:100},{name:'Mustard Oil',price:160}];
  function renderProducts(){document.getElementById('productList').innerHTML=products.filter(p=>p.name.toLowerCase().includes(document.getElementById('search').value.toLowerCase())).map(p=>`
    <div class="product"><h3>${p.name}</h3><p class="price">₹${p.price}</p>
      <div class="qty"><button onclick="updateQty(this,-1)">−</button><input type="text" value="1" style="width:40px;text-align:center;border:1px solid #ccc;border-radius:4px;"> <button onclick="updateQty(this,1)">+</button></div>
      <button onclick="addToCart('${p.name}',getQty(this))">Add to Cart</button>
    </div>`).join('');}
  function updateQty(btn,val){const inp=btn.parentNode.querySelector('input');const v=Math.max(1,parseInt(inp.value)+val);inp.value=v;}
  function getQty(btn){return btn.parentNode.querySelector('input').value;}

  let cart=[];function addToCart(name,qty){cart.push({name,qty});document.getElementById('cartCount').textContent=cart.reduce((a,c)=>a+parseInt(c.qty),0);renderCart();toggleCart();}
  function renderCart(){document.getElementById('cartItems').innerHTML=cart.map((c,i)=>`<div class="cart-item">${i+1}. ${c.name} x${c.qty}</div>`).join('');}
  function checkout(){if(!cart.length) return alert('Cart empty');alert('Order placed:'+cart.map(c=>`${c.name} x${c.qty}`).join(', '));cart=[];renderCart();document.getElementById('cartCount').textContent='0';toggleCart();}
  function trackOrder(){const id=document.getElementById('orderId').value.trim(),res=document.getElementById('trackRes');id?res.textContent=`📦 Order ${id} in process. Delivery in 3–5 days.`:res.textContent='⚠️ Enter valid ID.';}
  function toggleCart(){document.getElementById('cartDrawer').classList.toggle('open');document.getElementById('overlay').classList.toggle('show');}
  document.getElementById('search').addEventListener('input', renderProducts);renderProducts();
  function openLogin(){document.getElementById('loginModal').style.display='block';document.getElementById('overlay').style.display='block';}
  function loginUser(){const e=document.getElementById('email').value,p=document.getElementById('password').value;alert(e==='user@example.com'&&p==='password123'?'Login successful':'Invalid credentials');}
  document.getElementById('overlay').onclick=function(){document.getElementById('loginModal').style.display='none';document.getElementById('cartDrawer').classList.remove('open');this.classList.remove('show');};
  window.addEventListener('scroll',()=>document.getElementById('header').classList.toggle('scrolled',window.scrollY>50));
  function toggleMenu(){document.getElementById('menu').classList.toggle('show');}
  function scrollTo(id){toggleMenu();document.getElementById(id).scrollIntoView({behavior:'smooth'});}
</script>
</body></html>
