Rasoi Roots
website for homemade products
Made in India
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>RasoiRoots - Natural Spices</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #111;
      color: #fff;
    }
    header {
      background-color: #222;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    header h1 {
      margin: 0;
      color: #ffa500;
    }
    nav a {
      color: #fff;
      margin-left: 1.5rem;
      text-decoration: none;
      font-weight: bold;
    }
    .hero {
      background: url('https://source.unsplash.com/1600x600/?spices,organic') no-repeat center center/cover;
      height: 60vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }
    .hero h2 {
      color: #fff;
      font-size: 3rem;
      margin-bottom: 1rem;
    }
    .hero button {
      padding: 1rem 2rem;
      font-size: 1.2rem;
      background-color: #ffa500;
      color: #000;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }
    .section {
      padding: 2rem;
      background-color: #1c1c1c;
    }
    .section h3 {
      text-align: center;
      color: #ffa500;
    }
    .products {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
      margin-top: 2rem;
    }
    .product {
      background-color: #333;
      border: 1px solid #555;
      padding: 1rem;
      width: 200px;
      border-radius: 10px;
      text-align: center;
    }
    .product h4 {
      color: #ffa500;
    }
    .product button {
      margin-top: 1rem;
      padding: 0.5rem 1rem;
      border: none;
      background-color: #ffa500;
      color: #000;
      cursor: pointer;
      border-radius: 5px;
    }
    .cart-popup, .login-popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: #222;
      padding: 2rem;
      border-radius: 10px;
      display: none;
      z-index: 10;
    }
    .popup-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.6);
      display: none;
      z-index: 5;
    }
    .map, .contact, .reviews {
      margin-top: 2rem;
    }
    .cart-popup ul {
      list-style: none;
      padding: 0;
    }
    .cart-popup ul li {
      margin-bottom: 10px;
    }
    .reviews p {
      background: #444;
      padding: 1rem;
      border-radius: 5px;
      margin: 0.5rem 0;
    }
  </style>
</head>
<body>
  <header>
    <h1>RasoiRoots</h1>
    <nav>
      <a href="#" onclick="toggleLoginPopup()">Login / Sign Up</a>
      <a href="#" onclick="showCart()">Cart (<span id="cart-count">0</span>)</a>
    </nav>
  </header>

  <div class="hero">
    <h2>Pure. Authentic. Homemade Spices.</h2>
    <button onclick="document.getElementById('products').scrollIntoView({ behavior: 'smooth' })">Shop Now</button>
  </div>

  <div class="section" id="products">
    <h3>Our Products</h3>
    <div class="products">
      <div class="product"><h4>Red Chilly Powder</h4><p>₹75 (200g)</p><button onclick="addToCart('Red Chilly Powder', 75)">Add to Cart</button></div>
      <div class="product"><h4>Garam Masala</h4><p>₹200 (200g)</p><button onclick="addToCart('Garam Masala', 200)">Add to Cart</button></div>
      <div class="product"><h4>Turmeric Powder</h4><p>₹80 (200g)</p><button onclick="addToCart('Turmeric Powder', 80)">Add to Cart</button></div>
      <div class="product"><h4>Dhania Powder</h4><p>₹80 (200g)</p><button onclick="addToCart('Dhania Powder', 80)">Add to Cart</button></div>
      <div class="product"><h4>Cumin Seeds</h4><p>₹120 (200g)</p><button onclick="addToCart('Cumin Seeds', 120)">Add to Cart</button></div>
      <div class="product"><h4>Mustard Oil</h4><p>₹170 (1L)</p><button onclick="addToCart('Mustard Oil', 170)">Add to Cart</button></div>
      <div class="product"><h4>Besan</h4><p>₹100 (1kg)</p><button onclick="addToCart('Besan', 100)">Add to Cart</button></div>
    </div>
  </div>

  <div class="section reviews">
    <h3>Customer Reviews</h3>
    <p>🌟🌟🌟🌟🌟 - "The masalas are so authentic!" - Priya</p>
    <p>🌟🌟🌟🌟 - "Great quality and packaging." - Aman</p>
  </div>

  <div class="section contact">
    <h3>Contact Us</h3>
    <p><strong>Address:</strong> Atmadsarai, 203408 (Bulandshahr)</p>
    <p><strong>Phone:</strong> 8954152963, 9411911398</p>
    <div class="map">
      <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d7013.10749881545!2d77.83320958044123!3d28.492982870475725!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x390ca3772100734b%3A0x2b85934592a389b9!2sBrajpal%20Madhyan-%20oil%20mill%20%2C%20flour%20mill%20and%20spices%20point.!5e0!3m2!1sen!2sin!4v1752819092269!5m2!1sen!2sin" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
  </div>

  <div class="popup-bg" id="popup-bg" onclick="closePopups()"></div>
  <div class="cart-popup" id="cart-popup">
    <h3>Your Cart</h3>
    <ul id="cart-items"></ul>
    <p><strong>Total:</strong> ₹<span id="cart-total">0</span></p>
    <button onclick="checkout()">Buy Now</button>
    <button onclick="closePopups()">Close</button>
  </div>
  <div class="login-popup" id="login-popup">
    <h3>Login / Sign Up</h3>
    <input type="text" placeholder="Username" /><br><br>
    <input type="password" placeholder="Password" /><br><br>
    <button onclick="alert('Logged in!')">Submit</button>
    <button onclick="closePopups()">Close</button>
  </div>

  <script>
    let cart = [];

    function addToCart(product, price) {
      cart.push({ product, price });
      updateCartDisplay();
    }

    function updateCartDisplay() {
      const items = document.getElementById('cart-items');
      items.innerHTML = '';
      let total = 0;
      cart.forEach((item, index) => {
        total += item.price;
        items.innerHTML += `<li>${item.product} - ₹${item.price} <button onclick="removeFromCart(${index})">Remove</button></li>`;
      });
      document.getElementById('cart-count').innerText = cart.length;
      document.getElementById('cart-total').innerText = total;
    }

    function removeFromCart(index) {
      cart.splice(index, 1);
      updateCartDisplay();
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

    function checkout() {
      alert('Thank you for your purchase!');
      cart = [];
      updateCartDisplay();
      closePopups();
    }
  </script>
</body>
</html>
