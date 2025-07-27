Rasoi Roots
website for homemade products,
Made in India.
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Rasoi Roots - Premium Homemade Spices</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
  <style>
    :root {
      /* Saffron Glow Template (Default) */
      --primary-bg: #2ECC71; /* Emerald Green */
      --secondary-bg: #FF8C00; /* Saffron Orange */
      --accent-bg: #FFC107; /* Deep Turmeric */
      --text-color: #FFFDD0; /* Cream White */
      --secondary-text: #800000; /* Rich Maroon */
      --button-bg: #FF8C00; /* Saffron Orange */
      --button-hover: #FFC107; /* Deep Turmeric */
      --button-text: #800000; /* Rich Maroon */
      --card-bg: #FF8C00; /* Saffron Orange */
      --highlight-color: #FFC107; /* Deep Turmeric */
      --border-color: #FFC107; /* Deep Turmeric */
    }
    /* Monsoon Breeze Template */
    [data-template="monsoon-breeze"] {
      --primary-bg: #006994; /* Peacock Blue */
      --secondary-bg: #98FB98; /* Mint Green */
      --accent-bg: #FF4040; /* Coral Pink */
      --text-color: #FFFFF0; /* Ivory */
      --secondary-text: #000080; /* Navy Blue */
      --button-bg: #98FB98; /* Mint Green */
      --button-hover: #FF4040; /* Coral Pink */
      --button-text: #000080; /* Navy Blue */
      --card-bg: #006994; /* Peacock Blue */
      --highlight-color: #FF4040; /* Coral Pink */
      --border-color: #FF4040; /* Coral Pink */
    }
    /* Spice Bazaar Template */
    [data-template="spice-bazaar"] {
      --primary-bg: #6B8E23; /* Olive Green */
      --secondary-bg: #D2691E; /* Cinnamon Brown */
      --accent-bg: #FF4500; /* Saffron Yellow */
      --text-color: #F5F5DC; /* Beige */
      --secondary-text: #8B0000; /* Deep Red */
      --button-bg: #D2691E; /* Cinnamon Brown */
      --button-hover: #FF4500; /* Saffron Yellow */
      --button-text: #8B0000; /* Deep Red */
      --card-bg: #D2691E; /* Cinnamon Brown */
      --highlight-color: #FF4500; /* Saffron Yellow */
      --border-color: #FF4500; /* Saffron Yellow */
    }
    /* Indian Glance Template */
    [data-template="indian-glance"] {
      --primary-bg: #191970; /* Midnight Blue */
      --secondary-bg: #D4A017; /* Royal Gold */
      --accent-bg: #9B1D64; /* Ruby Red */
      --text-color: #F8F1E9; /* Pearl White */
      --secondary-text: #046307; /* Emerald Green */
      --button-bg: #D4A017; /* Royal Gold */
      --button-hover: #9B1D64; /* Ruby Red */
      --button-text: #046307; /* Emerald Green */
      --card-bg: #D4A017; /* Royal Gold */
      --highlight-color: #9B1D64; /* Ruby Red */
      --border-color: #9B1D64; /* Ruby Red */
    }
    body {
      font-family: 'Open Sans', sans-serif;
      background-color: var(--primary-bg);
      color: var(--text-color);
    }
    h1, h2, h3, h4 {
      font-family: 'Playfair Display', serif;
    }
    .hero-bg {
      background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://images.unsplash.com/photo-1606912977676-c783b234b9f7?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=80') no-repeat center center/cover;
      animation: fadeIn 2s ease-in-out;
    }
    .product-card {
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      background-color: var(--card-bg);
    }
    .product-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 6px 24px rgba(var(--highlight-color), 0.4);
    }
    .highlight {
      animation: highlight 1.5s ease-in-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    @keyframes highlight {
      0% { box-shadow: 0 0 0 0 rgba(var(--highlight-color), 0.7); }
      50% { box-shadow: 0 0 20px 10px rgba(var(--highlight-color), 0.7); }
      100% { box-shadow: 0 0 0 0 rgba(var(--highlight-color), 0.7); }
    }
    .btn-primary {
      background: linear-gradient(to right, var(--button-bg), var(--button-hover));
      color: var(--button-text);
    }
    .btn-primary:hover {
      background: linear-gradient(to right, var(--button-hover), var(--button-bg));
    }
    .btn-secondary {
      background: linear-gradient(to right, var(--secondary-text), #A52A2A);
      color: var(--text-color);
    }
    .btn-secondary:hover {
      background: linear-gradient(to right, #A52A2A, var(--secondary-text));
    }
    #search-message {
      display: none;
      text-align: center;
      color: var(--text-color);
      font-size: 1rem;
      margin-top: 0.5rem;
    }
    #no-results {
      display: none;
      text-align: center;
      color: var(--text-color);
      font-size: 1.2rem;
      margin-top: 2rem;
    }
    #cart-notification {
      display: none;
      position: fixed;
      top: 20px;
      right: 20px;
      background-color: var(--highlight-color);
      color: #1F2937;
      padding: 1rem 2rem;
      border-radius: 0.5rem;
      z-index: 50;
      animation: slideIn 0.5s ease-in-out, slideOut 0.5s ease-in-out 2.5s forwards;
    }
    @keyframes slideIn {
      from { transform: translateX(100%); opacity: 0; }
      to { transform: translateX(0); opacity: 1; }
    }
    @keyframes slideOut {
      from { transform: translateX(0); opacity: 1; }
      to { transform: translateX(100%); opacity: 0; }
    }
    #search-suggestions {
      position: absolute;
      width: 100%;
      max-width: 28rem;
      background-color: #1F2937;
      border: 1px solid var(--border-color);
      border-radius: 0.5rem;
      max-height: 200px;
      overflow-y: auto;
      z-index: 30;
      display: none;
    }
    .suggestion-item {
      padding: 0.5rem 1rem;
      cursor: pointer;
      color: var(--text-color);
    }
    .suggestion-item:hover, .suggestion-item.selected {
      background-color: var(--secondary-text);
    }
    #coupon-message {
      display: none;
      color: var(--text-color);
      font-size: 0.9rem;
      margin-top: 0.5rem;
    }
    .sidebar {
      position: fixed;
      top: 50%;
      left: 0;
      transform: translateY(-50%);
      z-index: 40;
    }
    .sidebar-toggle {
      background-color: var(--card-bg);
      padding: 0.5rem;
      border-radius: 0 0.375rem 0.375rem 0;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      width: 2.5rem;
      height: 2.5rem;
      box-shadow: 2px 0 8px rgba(0, 0, 0, 0.2);
    }
    .sidebar-content {
      position: absolute;
      left: 100%;
      top: 0;
      background-color: var(--card-bg);
      border: 1px solid var(--border-color);
      border-radius: 0.375rem;
      padding: 0.5rem;
      display: none;
      width: 10rem;
    }
    .sidebar:hover .sidebar-content,
    .sidebar-content:hover {
      display: block;
    }
    #template-switcher {
      background-color: var(--secondary-bg);
      color: var(--text-color);
      border: 1px solid var(--border-color);
      border-radius: 0.375rem;
      padding: 0.5rem;
      width: 100%;
    }
    #template-switcher:focus {
      outline: none;
      ring: 2px solid var(--highlight-color);
    }
  </style>
</head>
<body data-template="saffron-glow">
  <!-- Sidebar for Template Switcher -->
  <div class="sidebar">
    <div class="sidebar-toggle">
      <svg class="w-5 h-5" fill="none" stroke="var(--text-color)" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 21a4 4 0 01-4-4V5a2 2 0 012-2h4a2 2 0 012 2v12a4 4 0 01-4 4zm0 0h12a2 2 0 002-2v-4a2 2 0 00-2-2h-2.343M11 7.343l1.657-1.657a2 2 0 012.828 0l2.829 2.829a2 2 0 010 2.828l-8.486 8.485M7 17h.01"></path>
      </svg>
    </div>
    <div class="sidebar-content">
      <select id="template-switcher" onchange="switchTemplate(this.value)" class="text-sm font-semibold">
        <option value="saffron-glow">Saffron Glow</option>
        <option value="monsoon-breeze">Monsoon Breeze</option>
        <option value="spice-bazaar">Spice Bazaar</option>
        <option value="indian-glance">Indian Glance</option>
      </select>
    </div>
  </div>

  <!-- Cart Notification -->
  <div id="cart-notification" class="flex items-center space-x-2">
    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
    </svg>
    <span id="cart-notification-text"></span>
  </div>

  <!-- Header -->
  <header class="text-cream-100 shadow-lg sticky top-0 z-20" style="background-color: var(--secondary-bg);">
    <div class="container mx-auto px-4 py-4 flex items-center justify-between">
      <div class="flex items-center">
        <h1 class="text-3xl font-bold" style="color: var(--text-color);">Rasoi Roots</h1>
      </div>
      <div class="flex-1 mx-6 relative">
        <input type="text" id="search-bar" placeholder="Search for premium spices..." class="w-full max-w-xl p-3 rounded-lg border focus:outline-none focus:ring-2" style="border-color: var(--border-color); background-color: var(--card-bg); color: var(--text-color); focus:ring-color: var(--highlight-color);" autocomplete="off" />
        <div id="search-suggestions"></div>
        <div id="search-message"></div>
      </div>
      <nav class="flex items-center space-x-8">
        <a href="#" onclick="toggleLoginPopup()" class="font-semibold" style="color: var(--text-color); hover:color: var(--highlight-color);">Login / Sign Up</a>
        <a href="#" onclick="showCart()" class="font-semibold flex items-center" style="color: var(--text-color); hover:color: var(--highlight-color);">
          <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"></path>
          </svg>
          Cart (<span id="cart-count">0</span>)
        </a>
      </nav>
    </div>
  </header>

  <!-- Hero Section -->
  <div class="hero-bg h-[80vh] flex flex-col justify-center items-center text-center" style="color: var(--text-color);">
    <h2 class="text-5xl md:text-6xl font-bold mb-6 animate-fade-in">Vibrant Indian Spices, Crafted with Passion</h2>
    <p class="text-lg md:text-xl mb-8 font-light max-w-2xl">Discover the bold, authentic flavors of India, handcrafted to elevate your culinary experience.</p>
    <button onclick="document.getElementById('products').scrollIntoView({ behavior: 'smooth' })" class="btn-primary px-8 py-4 rounded-lg font-semibold text-lg transition duration-300">Shop Our Collection</button>
    <p class="text-lg font-semibold mt-4">Get 10% off on your first order and 5% off on signup!</p>
  </div>

  <!-- Products Section -->
  <div class="section py-16" id="products" style="background-color: var(--primary-bg);">
    <div class="container mx-auto px-4">
      <h3 class="text-4xl font-bold text-center mb-10" style="color: var(--text-color);">Our Signature Spices</h3>
      <div id="product-list" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">
        <div class="product-card rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold" style="color: var(--text-color);">Red Chilly Powder</h4>
          <p style="color: var(--text-color);">₹75 (200g)</p>
          <button onclick="addToCart('Red Chilly Powder', 75)" class="mt-4 btn-secondary px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold" style="color: var(--text-color);">Garam Masala</h4>
          <p style="color: var(--text-color);">₹200 (200g)</p>
          <button onclick="addToCart('Garam Masala', 200)" class="mt-4 btn-secondary px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold" style="color: var(--text-color);">Turmeric Powder</h4>
          <p style="color: var(--text-color);">₹80 (200g)</p>
          <button onclick="addToCart('Turmeric Powder', 80)" class="mt-4 btn-secondary px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold" style="color: var(--text-color);">Dhania Powder</h4>
          <p style="color: var(--text-color);">₹80 (200g)</p>
          <button onclick="addToCart('Dhania Powder', 80)" class="mt-4 btn-secondary px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold" style="color: var(--text-color);">Cumin Seeds</h4>
          <p style="color: var(--text-color);">₹120 (200g)</p>
          <button onclick="addToCart('Cumin Seeds', 120)" class="mt-4 btn-secondary px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold" style="color: var(--text-color);">Mustard Oil</h4>
          <p style="color: var(--text-color);">₹170 (1L)</p>
          <button onclick="addToCart('Mustard Oil', 170)" class="mt-4 btn-secondary px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold" style="color: var(--text-color);">Besan</h4>
          <p style="color: var(--text-color);">₹100 (1kg)</p>
          <button onclick="addToCart('Besan', 100)" class="mt-4 btn-secondary px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
      </div>
      <div id="no-results">No products found matching your search.</div>
    </div>
  </div>

  <!-- Customer Reviews Section -->
  <div class="section py-16" style="background-color: var(--primary-bg);">
    <div class="container mx-auto px-4">
      <h3 class="text-4xl font-bold text-center mb-10" style="color: var(--text-color);">What Our Customers Say</h3>
      <div class="space-y-6">
        <p class="p-6 rounded-xl shadow-md" style="background-color: var(--card-bg); color: var(--text-color);">🌟🌟🌟🌟🌟 - "The masalas are a true taste of tradition!" - Priya</p>
        <p class="p-6 rounded-xl shadow-md" style="background-color: var(--card-bg); color: var(--text-color);">🌟🌟🌟🌟 - "Exceptional quality, beautifully packaged." - Aman</p>
        <p class="p-6 rounded-xl shadow-md" style="background-color: var(--card-bg); color: var(--text-color);">🌟🌟🌟🌟🌟 - "The turmeric powder is so vibrant and fresh!" - Rhea</p>
        <p class="p-6 rounded-xl shadow-md" style="background-color: var(--card-bg); color: var(--text-color);">🌟🌟🌟🌟 - "Mustard oil added such depth to my cooking." - Vikram</p>
        <p class="p-6 rounded-xl shadow-md" style="background-color: var(--card-bg); color: var(--text-color);">🌟🌟🌟🌟🌟 - "Best garam masala I've ever used!" - Sneha</p>
      </div>
    </div>
  </div>

  <!-- Contact Section -->
  <div class="section py-16" style="background-color: var(--secondary-bg);">
    <div class="container mx-auto px-4">
      <h3 class="text-4xl font-bold text-center mb-10" style="color: var(--text-color);">Get in Touch</h3>
      <p class="text-center" style="color: var(--text-color);"><strong>Address:</strong> Atmadsarai, 203408 (Bulandshahr)</p>
      <p class="text-center" style="color: var(--text-color);"><strong>Phone:</strong> 8954152963, 9411911398</p>
      <div class="mt-10">
        <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d7013.10749881545!2d77.83320958044123!3d28.492982870475725!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x390ca3772100734b%3A0x2b85934592a389b9!2sBrajpal%20Madhyan-%20oil%20mill%20%2C%20flour%20mill%20and%20spices%20point.!5e0!3m2!1sen!2sin!4v1752819092269!5m2!1sen!2sin" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
    </div>
  </div>

  <!-- Cart Popup -->
  <div class="popup-bg fixed inset-0 bg-black bg-opacity-70 hidden z-10" id="popup-bg" onclick="closePopups()"></div>
  <div class="cart-popup fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-8 rounded-xl shadow-2xl hidden z-20 max-w-lg w-full" id="cart-popup" style="background-color: var(--card-bg);">
    <h3 class="text-2xl font-bold mb-6" style="color: var(--text-color);">Your Cart</h3>
    <ul id="cart-items" class="space-y-3"></ul>
    <div class="mt-6">
      <div class="flex items-center space-x-2">
        <input type="text" id="coupon-code" placeholder="Enter coupon code" class="w-full p-2 rounded-lg border focus:outline-none focus:ring-2" style="border-color: var(--border-color); background-color: var(--card-bg); color: var(--text-color); focus:ring-color: var(--highlight-color);" />
        <button onclick="applyCoupon()" class="btn-primary px-4 py-2 rounded-lg font-semibold transition duration-300">Apply</button>
      </div>
      <div id="coupon-message"></div>
    </div>
    <p class="mt-6" style="color: var(--text-color);"><strong>Total:</strong> ₹<span id="cart-total">0</span></p>
    <div class="flex justify-end space-x-3 mt-6">
      <button onclick="checkout()" class="btn-primary px-5 py-2 rounded-lg font-semibold transition duration-300">Buy Now</button>
      <button onclick="closePopups()" class="px-5 py-2 rounded-lg font-semibold transition duration-300" style="background-color: var(--secondary-text); color: var(--text-color);">Close</button>
    </div>
  </div>

  <!-- Login Popup -->
  <div class="login-popup fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 p-8 rounded-xl shadow-2xl hidden z-20 max-w-lg w-full" id="login-popup" style="background-color: var(--card-bg);">
    <h3 class="text-2xl font-bold mb-6" style="color: var(--text-color);">Login / Sign Up</h3>
    <input type="text" placeholder="Username" class="w-full p-3 mb-4 border rounded-lg focus:outline-none focus:ring-2" style="border-color: var(--border-color); background-color: var(--card-bg); color: var(--text-color); focus:ring-color: var(--highlight-color);" />
    <input type="password" placeholder="Password" class="w-full p-3 mb-4 border rounded-lg focus:outline-none focus:ring-2" style="border-color: var(--border-color); background-color: var(--card-bg); color: var(--text-color); focus:ring-color: var(--highlight-color);" />
    <div class="flex justify-end space-x-3">
      <button onclick="handleLogin()" class="btn-primary px-5 py-2 rounded-lg font-semibold transition duration-300">Submit</button>
      <button onclick="closePopups()" class="px-5 py-2 rounded-lg font-semibold transition duration-300" style="background-color: var(--secondary-text); color: var(--text-color);">Close</button>
    </div>
  </div>

  <script>
    let cart = [];
    let isLoggedIn = false;
    let isFirstOrder = true;
    let appliedCoupon = null;
    const products = [
      'Red Chilly Powder',
      'Garam Masala',
      'Turmeric Powder',
      'Dhania Powder',
      'Cumin Seeds',
      'Mustard Oil',
      'Besan'
    ];
    const coupons = {
      'FIRST10': { discount: 0.10, condition: () => isFirstOrder },
      'SIGNUP5': { discount: 0.05, condition: () => isLoggedIn }
    };

    function switchTemplate(template) {
      document.body.setAttribute('data-template', template);
    }

    function addToCart(product, price) {
      cart.push({ product, price });
      updateCartDisplay();
      showCartNotification(`${product} added to cart!`);
    }

    function showCartNotification(message) {
      const notification = document.getElementById('cart-notification');
      const notificationText = document.getElementById('cart-notification-text');
      notificationText.innerText = message;
      notification.style.display = 'flex';
      setTimeout(() => {
        notification.style.display = 'none';
      }, 3000);
    }

    function updateCartDisplay() {
      const items = document.getElementById('cart-items');
      items.innerHTML = '';
      let total = 0;
      cart.forEach((item, index) => {
        total += item.price;
        items.innerHTML += `<li class="flex justify-between items-center" style="color: var(--text-color);"><span>${item.product} - ₹${item.price}</span><button onclick="removeFromCart(${index})" class="font-semibold" style="color: var(--secondary-text); hover:color: var(--highlight-color);">Remove</button></li>`;
      });
      if (appliedCoupon) {
        const discount = coupons[appliedCoupon].discount;
        total = total * (1 - discount);
      }
      document.getElementById('cart-count').innerText = cart.length;
      document.getElementById('cart-total').innerText = Math.round(total);
    }

    function removeFromCart(index) {
      cart.splice(index, 1);
      updateCartDisplay();
    }

    function applyCoupon() {
      const couponCode = document.getElementById('coupon-code').value.trim().toUpperCase();
      const couponMessage = document.getElementById('coupon-message');
      
      if (coupons[couponCode] && coupons[couponCode].condition()) {
        appliedCoupon = couponCode;
        couponMessage.style.display = 'block';
        couponMessage.innerText = `Coupon "${couponCode}" applied! ${coupons[couponCode].discount * 100}% off`;
        couponMessage.style.color = 'var(--highlight-color)';
        updateCartDisplay();
      } else {
        appliedCoupon = null;
        couponMessage.style.display = 'block';
        couponMessage.innerText = 'Invalid or inapplicable coupon code.';
        couponMessage.style.color = 'var(--secondary-text)';
        updateCartDisplay();
      }
    }

    function showCart() {
      document.getElementById('popup-bg').style.display = 'block';
      document.getElementById('cart-popup').style.display = 'block';
    }

    function toggleLoginPopup() {
      document.getElementById('popup-bg').style.display = 'block';
      document.getElementById('login-popup').style.display = 'block';
    }

    function closePopups() {
      document.getElementById('popup-bg').style.display = 'none';
      document.getElementById('cart-popup').style.display = 'none';
      document.getElementById('login-popup').style.display = 'none';
    }

    function handleLogin() {
      isLoggedIn = true;
      showCartNotification('Logged in! Use SIGNUP5 for 5% off.');
      closePopups();
    }

    function checkout() {
      if (cart.length === 0) {
        alert('Your cart is empty!');
        return;
      }
      alert('Thank you for your purchase!');
      if (appliedCoupon === 'FIRST10') {
        isFirstOrder = false;
      }
      cart = [];
      appliedCoupon = null;
      document.getElementById('coupon-code').value = '';
      document.getElementById('coupon-message').style.display = 'none';
      updateCartDisplay();
      closePopups();
    }

    // Enhanced Amazon-like Search Functionality
    const searchBar = document.getElementById('search-bar');
    const suggestionsContainer = document.getElementById('search-suggestions');
    const searchMessage = document.getElementById('search-message');
    const noResults = document.getElementById('no-results');
    let selectedIndex = -1;

    function showSuggestions(query) {
      suggestionsContainer.innerHTML = '';
      selectedIndex = -1;
      if (query.trim() === '') {
        suggestionsContainer.style.display = 'none';
        return;
      }

      const filteredProducts = products.filter(product =>
        product.toLowerCase().includes(query.toLowerCase())
      );

      if (filteredProducts.length > 0) {
        filteredProducts.forEach((product, index) => {
          const suggestion = document.createElement('div');
          suggestion.className = 'suggestion-item';
          suggestion.innerText = product;
          suggestion.addEventListener('click', () => selectSuggestion(product));
          suggestionsContainer.appendChild(suggestion);
        });
        suggestionsContainer.style.display = 'block';
      } else {
        suggestionsContainer.style.display = 'none';
      }
    }

    function selectSuggestion(productName) {
      searchBar.value = productName;
      suggestionsContainer.innerHTML = '';
      suggestionsContainer.style.display = 'none';
      searchProduct(productName);
    }

    function searchProduct(query) {
      const products = document.querySelectorAll('.product-card');
      let hasResults = false;
      let foundProduct = null;

      // Remove previous highlights
      products.forEach(product => {
        product.classList.remove('highlight');
        product.style.display = 'block';
      });

      if (query) {
        products.forEach(product => {
          const name = product.querySelector('h4').innerText.toLowerCase();
          if (name.includes(query.toLowerCase())) {
            hasResults = true;
            foundProduct = product;
            product.style.display = 'block';
          } else {
            product.style.display = 'none';
          }
        });

        if (hasResults) {
          searchMessage.style.display = 'block';
          searchMessage.innerText = `Product "${query}" is available!`;
          searchMessage.style.color = 'var(--highlight-color)';
          foundProduct.scrollIntoView({ behavior: 'smooth', block: 'center' });
          foundProduct.classList.add('highlight');
        } else {
          searchMessage.style.display = 'block';
          searchMessage.innerText = `Product "${query}" is not available.`;
          searchMessage.style.color = 'var(--secondary-text)';
          noResults.style.display = 'block';
        }
      } else {
        searchMessage.style.display = 'none';
        noResults.style.display = 'none';
      }
    }

    searchBar.addEventListener('input', function(e) {
      const query = e.target.value.trim();
      showSuggestions(query);
      searchProduct(query);
    });

    searchBar.addEventListener('keydown', function(e) {
      const suggestions = suggestionsContainer.querySelectorAll('.suggestion-item');
      if (suggestions.length === 0) return;

      if (e.key === 'ArrowDown') {
        e.preventDefault();
        selectedIndex = Math.min(selectedIndex + 1, suggestions.length - 1);
        updateSelectedSuggestion(suggestions);
      } else if (e.key === 'ArrowUp') {
        e.preventDefault();
        selectedIndex = Math.max(selectedIndex - 1, -1);
        updateSelectedSuggestion(suggestions);
      } else if (e.key === 'Enter' && selectedIndex >= 0) {
        e.preventDefault();
        selectSuggestion(suggestions[selectedIndex].innerText);
      }
    });

    function updateSelectedSuggestion(suggestions) {
      suggestions.forEach((suggestion, index) => {
        suggestion.classList.toggle('selected', index === selectedIndex);
      });
      if (selectedIndex >= 0) {
        searchBar.value = suggestions[selectedIndex].innerText;
      } else {
        searchBar.value = searchBar.value;
      }
    }

    // Hide suggestions when clicking outside
    document.addEventListener('click', function(e) {
      if (!searchBar.contains(e.target) && !suggestionsContainer.contains(e.target)) {
        suggestionsContainer.style.display = 'none';
      }
    });
  </script>
</body>
</html>
