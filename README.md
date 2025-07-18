Rasoi Roots
website for homemade products
Made in India
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>RasoiRoots</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #fefefe;
    }
    .luxury-bg {
      background: linear-gradient(145deg, #fdf0ec, #f3e1dc);
    }
    .luxury-card {
      background: white;
      border-radius: 1rem;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
    }
  </style>
</head>

<body class="luxury-bg">
  <header class="bg-red-700 text-white p-6 text-center shadow-md sticky top-0 z-50">
    <h1 class="text-4xl font-bold">RasoiRoots</h1>
    <nav class="mt-2 space-x-4">
      <a href="#home" class="hover:underline">Home</a>
      <a href="#products" class="hover:underline">Products</a>
      <a href="#reviews" class="hover:underline">Reviews</a>
      <a href="#contact" class="hover:underline">Contact</a>
      <button onclick="toggleCart()" class="float-right relative">
        <i class="fas fa-shopping-cart"></i>
        <span id="cart-count" class="absolute top-0 right-0 bg-yellow-400 text-black rounded-full text-xs px-2">0</span>
      </button>
    </nav>
  </header>

  <main id="home" class="text-center py-20">
    <h2 class="text-5xl font-bold text-red-700">Welcome to RasoiRoots</h2>
    <p class="mt-4 text-gray-700 text-lg">Authentic Spices & Oils Straight from the Mill to Your Kitchen</p>
  </main>

  <section id="products" class="p-6 max-w-6xl mx-auto">
    <h2 class="text-3xl font-bold text-red-700 mb-6">Our Products</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <!-- Product Items -->
      <div class="luxury-card p-6">
        <h3 class="text-xl font-semibold">Garam Masala</h3>
        <p>₹200</p>
        <button class="bg-red-700 text-white px-4 py-2 mt-2 rounded add-to-cart">Add to Cart</button>
      </div>
      <div class="luxury-card p-6">
        <h3 class="text-xl font-semibold">Mustard Oil</h3>
        <p>₹170</p>
        <button class="bg-red-700 text-white px-4 py-2 mt-2 rounded add-to-cart">Add to Cart</button>
      </div>
      <div class="luxury-card p-6">
        <h3 class="text-xl font-semibold">Red Chilly Powder</h3>
        <p>₹75</p>
        <button class="bg-red-700 text-white px-4 py-2 mt-2 rounded add-to-cart">Add to Cart</button>
      </div>
      <div class="luxury-card p-6">
        <h3 class="text-xl font-semibold">Besan</h3>
        <p>₹100</p>
        <button class="bg-red-700 text-white px-4 py-2 mt-2 rounded add-to-cart">Add to Cart</button>
      </div>
      <div class="luxury-card p-6">
        <h3 class="text-xl font-semibold">Cumin Seeds</h3>
        <p>₹110</p>
        <button class="bg-red-700 text-white px-4 py-2 mt-2 rounded add-to-cart">Add to Cart</button>
      </div>
      <div class="luxury-card p-6">
        <h3 class="text-xl font-semibold">Turmeric Powder</h3>
        <p>₹70</p>
        <button class="bg-red-700 text-white px-4 py-2 mt-2 rounded add-to-cart">Add to Cart</button>
      </div>
      <div class="luxury-card p-6">
        <h3 class="text-xl font-semibold">Dhaniya Powder</h3>
        <p>₹80</p>
        <button class="bg-red-700 text-white px-4 py-2 mt-2 rounded add-to-cart">Add to Cart</button>
      </div>
    </div>
  </section>

  <section id="reviews" class="p-6 bg-gray-100">
    <h2 class="text-3xl font-bold text-red-700 mb-4">Customer Reviews</h2>
    <p>“Amazing quality and authentic flavors. Highly recommend RasoiRoots!”</p>
  </section>

  <section id="contact" class="p-6">
    <h2 class="text-3xl font-bold text-red-700 mb-4">Contact Us</h2>
    <p class="mb-2">Phone: 941191198, 8954152963</p>
    <iframe class="w-full h-64 border-none" src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d7013.10749881545!2d77.83320958044123!3d28.492982870475725!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x390ca3772100734b%3A0x2b85934592a389b9!2sBrajpal%20Madhyan-%20oil%20mill%20%2C%20flour%20mill%20and%20spices%20point.!5e0!3m2!1sen!2sin!4v1752819092269!5m2!1sen!2sin" allowfullscreen loading="lazy"></iframe>
  </section>

  <footer class="bg-red-700 text-white text-center p-4">
    &copy; 2025 RasoiRoots. All rights reserved.
  </footer>

  <!-- Cart Modal -->
  <div id="cart-modal" class="hidden fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
    <div class="bg-white rounded-lg p-6 w-96">
      <h3 class="text-xl font-bold mb-4">Your Cart</h3>
      <ul id="cart-items" class="space-y-2"></ul>
      <button onclick="buyNow()" class="bg-green-600 text-white mt-4 px-4 py-2 rounded">Buy Now</button>
      <button onclick="toggleCart()" class="mt-2 text-red-700 underline">Close</button>
    </div>
  </div>

  <script>
    let cart = [];

    document.querySelectorAll('.add-to-cart').forEach((btn, index) => {
      btn.addEventListener('click', () => {
        const name = btn.parentElement.querySelector('h3').innerText;
        const price = btn.parentElement.querySelector('p').innerText;
        cart.push({ name, price });
        updateCart();
      });
    });

    function updateCart() {
      const cartItems = document.getElementById('cart-items');
      cartItems.innerHTML = '';
      cart.forEach((item, index) => {
        const li = document.createElement('li');
        li.innerHTML = `${item.name} - ${item.price} <button onclick="removeFromCart(${index})" class="text-red-500 ml-2">Remove</button>`;
        cartItems.appendChild(li);
      });
      document.getElementById('cart-count').innerText = cart.length;
    }

    function toggleCart() {
      document.getElementById('cart-modal').classList.toggle('hidden');
    }

    function removeFromCart(index) {
      cart.splice(index, 1);
      updateCart();
    }

    function buyNow() {
      alert('Thank you for your purchase!');
      cart = [];
      updateCart();
      toggleCart();
    }
  </script>
</body>

</html>
