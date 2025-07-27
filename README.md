Rasoi Roots
website for homemade products
Made in India
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Rasoi Roots - Premium Homemade Spices</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Open Sans', sans-serif;
      background-color: #00C4B4;
      color: #FFFFFF;
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
    }
    .product-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 6px 24px rgba(255, 111, 97, 0.4);
    }
    .highlight {
      animation: highlight 1.5s ease-in-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    @keyframes highlight {
      0% { box-shadow: 0 0 0 0 rgba(255, 111, 97, 0.7); }
      50% { box-shadow: 0 0 20px 10px rgba(255, 111, 97, 0.7); }
      100% { box-shadow: 0 0 0 0 rgba(255, 111, 97, 0.7); }
    }
    .btn-gold {
      background: linear-gradient(to right, #FFD700, #FFC107);
    }
    .btn-gold:hover {
      background: linear-gradient(to right, #FFC107, #FFD700);
    }
    .btn-coral {
      background: linear-gradient(to right, #FF6F61, #FF8A80);
    }
    .btn-coral:hover {
      background: linear-gradient(to right, #FF8A80, #FF6F61);
    }
    #search-message {
      display: none;
      text-align: center;
      color: #FFFFFF;
      font-size: 1rem;
      margin-top: 0.5rem;
    }
    #no-results {
      display: none;
      text-align: center;
      color: #FFFFFF;
      font-size: 1.2rem;
      margin-top: 2rem;
    }
    #cart-notification {
      display: none;
      position: fixed;
      top: 20px;
      right: 20px;
      background-color: #FFD700;
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
      border: 1px solid #FFD700;
      border-radius: 0.5rem;
      max-height: 200px;
      overflow-y: auto;
      z-index: 30;
      display: none;
    }
    .suggestion-item {
      padding: 0.5rem 1rem;
      cursor: pointer;
      color: #FFFFFF;
    }
    .suggestion-item:hover, .suggestion-item.selected {
      background-color: #FF6F61;
    }
    #coupon-message {
      display: none;
      color: #FFFFFF;
      font-size: 0.9rem;
      margin-top: 0.5rem;
    }
  </style>
</head>
<body>
  <!-- Cart Notification -->
  <div id="cart-notification" class="flex items-center space-x-2">
    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
    </svg>
    <span id="cart-notification-text"></span>
  </div>

  <!-- Header -->
  <header class="bg-teal-800 text-white shadow-lg sticky top-0 z-20">
    <div class="container mx-auto px-4 py-4 flex items-center justify-between">
      <div class="flex items-center">
        <h1 class="text-3xl font-bold text-gold-400">Rasoi Roots</h1>
      </div>
      <div class="flex-1 mx-6 relative">
        <input type="text" id="search-bar" placeholder="Search for premium spices..." class="w-full max-w-xl p-3 rounded-lg border border-gold-400 focus:outline-none focus:ring-2 focus:ring-gold-500 bg-teal-900 text-white" autocomplete="off" />
        <div id="search-suggestions"></div>
        <div id="search-message"></div>
      </div>
      <nav class="flex items-center space-x-8">
        <a href="#" onclick="toggleLoginPopup()" class="text-gold-400 hover:text-gold-300 font-semibold">Login / Sign Up</a>
        <a href="#" onclick="showCart()" class="text-gold-400 hover:text-gold-300 font-semibold flex items-center">
          <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"></path>
          </svg>
          Cart (<span id="cart-count">0</span>)
        </a>
      </nav>
    </div>
  </header>

  <!-- Hero Section -->
  <div class="hero-bg h-[80vh] flex flex-col justify-center items-center text-center text-white">
    <h2 class="text-5xl md:text-6xl font-bold mb-6 animate-fade-in">Vibrant Indian Spices, Crafted with Passion</h2>
    <p class="text-lg md:text-xl mb-8 font-light max-w-2xl">Discover the bold, authentic flavors of India, handcrafted to elevate your culinary experience.</p>
    <button onclick="document.getElementById('products').scrollIntoView({ behavior: 'smooth' })" class="btn-gold text-teal-900 px-8 py-4 rounded-lg font-semibold text-lg transition duration-300">Shop Our Collection</button>
    <p class="text-lg font-semibold mt-4">Get 10% off on your first order and 5% off on signup!</p>
  </div>

  <!-- Products Section -->
  <div class="section bg-teal-700 py-16" id="products">
    <div class="container mx-auto px-4">
      <h3 class="text-4xl font-bold text-center text-gold-400 mb-10">Our Signature Spices</h3>
      <div id="product-list" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">
        <div class="product-card bg-teal-900 rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold text-gold-400">Red Chilly Powder</h4>
          <p class="text-white">₹75 (200g)</p>
          <button onclick="addToCart('Red Chilly Powder', 75)" class="mt-4 btn-coral text-white px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card bg-teal-900 rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold text-gold-400">Garam Masala</h4>
          <p class="text-white">₹200 (200g)</p>
          <button onclick="addToCart('Garam Masala', 200)" class="mt-4 btn-coral text-white px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card bg-teal-900 rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold text-gold-400">Turmeric Powder</h4>
          <p class="text-white">₹80 (200g)</p>
          <button onclick="addToCart('Turmeric Powder', 80)" class="mt-4 btn-coral text-white px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card bg-teal-900 rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold text-gold-400">Dhania Powder</h4>
          <p class="text-white">₹80 (200g)</p>
          <button onclick="addToCart('Dhania Powder', 80)" class="mt-4 btn-coral text-white px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card bg-teal-900 rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold text-gold-400">Cumin Seeds</h4>
          <p class="text-white">₹120 (200g)</p>
          <button onclick="addToCart('Cumin Seeds', 120)" class="mt-4 btn-coral text-white px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card bg-teal-900 rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold text-gold-400">Mustard Oil</h4>
          <p class="text-white">₹170 (1L)</p>
          <button onclick="addToCart('Mustard Oil', 170)" class="mt-4 btn-coral text-white px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
        <div class="product-card bg-teal-900 rounded-xl shadow-lg p-6 text-center">
          <h4 class="text-2xl font-semibold text-gold-400">Besan</h4>
          <p class="text-white">₹100 (1kg)</p>
          <button onclick="addToCart('Besan', 100)" class="mt-4 btn-coral text-white px-5 py-2 rounded-lg font-semibold transition duration-300">Add to Cart</button>
        </div>
      </div>
      <div id="no-results">No products found matching your search.</div>
    </div>
  </div>

  <!-- Customer Reviews Section -->
  <div class="section bg-teal-700 py-16">
    <div class="container mx-auto px-4">
      <h3 class="text-4xl font-bold text-center text-gold-400 mb-10">What Our Customers Say</h3>
      <div class="space-y-6">
        <p class="bg-teal-900 p-6 rounded-xl shadow-md text-white">🌟🌟🌟🌟🌟 - "The masalas are a true taste of tradition!" - Priya</p>
        <p class="bg-teal-900 p-6 rounded-xl shadow-md text-white">🌟🌟🌟🌟 - "Exceptional quality, beautifully packaged." - Aman</p>
        <p class="bg-teal-900 p-6 rounded-xl shadow-md text-white">🌟🌟🌟🌟🌟 - "The turmeric powder is so vibrant and fresh!" - Rhea</p>
        <p class="bg-teal-900 p-6 rounded-xl shadow-md text-white">🌟🌟🌟🌟 - "Mustard oil added such depth to my cooking." - Vikram</p>
        <p class="bg-teal-900 p-6 rounded-xl shadow-md text-white">🌟🌟🌟🌟🌟 - "Best garam masala I've ever used!" - Sneha</p>
      </div>
    </div>
  </div>

  <!-- Contact Section -->
  <div class="section bg-teal-800 py-16">
    <div class="container mx-auto px-4">
      <h3 class="text-4xl font-bold text-center text-gold-400 mb-10">Get in Touch</h3>
      <p class="text-center text-white"><strong>Address:</strong> Atmadsarai, 203408 (Bulandshahr)</p>
      <p class="text-center text-white"><strong>Phone:</strong> 8954152963, 9411911398</p>
      <div class="mt-10">
        <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d7013.10749881545!2d77.83320958044123!3d28.492982870475725!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x390ca3772100734b%3A0x2b85934592a389b9!2sBrajpal%20Madhyan-%20oil%20mill%20%2C%20flour%20mill%20and%20spices%20point.!5e0!3m2!1sen!2sin!4v1752819092269!5m2!1sen!2sin" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
    </div>
  </div>

  <!-- Cart Popup -->
  <div class="popup-bg fixed inset-0 bg-black bg-opacity-70 hidden z-10" id="popup-bg" onclick="closePopups()"></div>
  <div class="cart-popup fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-teal-900 p-8 rounded-xl shadow-2xl hidden z-20 max-w-lg w-full" id="cart-popup">
    <h3 class="text-2xl font-bold text-gold-400 mb-6">Your Cart</h3>
    <ul id="cart-items" class="space-y-3"></ul>
    <div class="mt-6">
      <div class="flex items-center space-x-2">
        <input type="text" id="coupon-code" placeholder="Enter coupon code" class="w-full p-2 rounded-lg border border-gold-400 focus:outline-none focus:ring-2 focus:ring-gold-500 bg-teal-800 text-white" />
        <button onclick="applyCoupon()" class="btn-gold text-teal-900 px-4 py-2 rounded-lg font-semibold transition duration-300">Apply</button>
      </div>
      <div id="coupon-message"></div>
    </div>
    <p class="mt-6 text-white"><strong>Total:</strong> ₹<span id="cart-total">0</span></p>
    <div class="flex justify-end space-x-3 mt-6">
      <button onclick="checkout()" class="btn-gold text-teal-900 px-5 py-2 rounded-lg font-semibold transition duration-300">Buy Now</button>
      <button onclick="closePopups()" class="bg-teal-700 text-white px-5 py-2 rounded-lg font-semibold hover:bg-teal-600 transition duration-300">Close</button>
    </div>
  </div>

  <!-- Login Popup -->
  <div class="login-popup fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-teal-900 p-8 rounded-xl shadow-2xl hidden z-20 max-w-lg w-full" id="login-popup">
    <h3 class="text-2xl font-bold text-gold-400 mb-6">Login / Sign Up</h3>
    <input type="text" placeholder="Username" class="w-full p-3 mb-4 border border-gold-400 rounded-lg focus:outline-none focus:ring-2 focus:ring-gold-500 bg-teal-900 text-white" />
    <input type="password" placeholder="Password" class="w-full p-3 mb-4 border border-gold-400 rounded-lg focus:outline-none focus:ring-2 focus:ring-gold-500 bg-teal-900 text-white" />
    <div class="flex justify-end space-x-3">
      <button onclick="handleLogin()" class="btn-gold text-teal-900 px-5 py-2 rounded-lg font-semibold transition duration-300">Submit</button>
      <button onclick="closePopups()" class="bg-teal-700 text-white px-5 py-2 rounded-lg font-semibold hover:bg-teal-600 transition duration-300">Close</button>
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
        items.innerHTML += `<li class="flex justify-between items-center text-white"><span>${item.product} - ₹${item.price}</span><button onclick="removeFromCart(${index})" class="text-red-400 hover:text-red-300 font-semibold">Remove</button></li>`;
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
        couponMessage.style.color = '#FFD700';
        updateCartDisplay();
      } else {
        appliedCoupon = null;
        couponMessage.style.display = 'block';
        couponMessage.innerText = 'Invalid or inapplicable coupon code.';
        couponMessage.style.color = '#FF6F61';
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
          searchMessage.style.color = '#FFD700';
          foundProduct.scrollIntoView({ behavior: 'smooth', block: 'center' });
          foundProduct.classList.add('highlight');
        } else {
          searchMessage.style.display = 'block';
          searchMessage.innerText = `Product "${query}" is not available.`;
          searchMessage.style.color = '#FF6F61';
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


  
