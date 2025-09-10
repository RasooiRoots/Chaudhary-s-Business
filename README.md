Rasoi Roots
website for homemade products,
Made in India.
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>RasoiRoots - Premium Homemade Spices | Made in India</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary: #3a7d44;
      --primary-dark: #2d6135;
      --secondary: #2d3e2f;
      --light-bg: #f8f9f7;
      --dark-text: #1a1f16;
      --white: #ffffff;
      --light-gray: #e8ebe8;
      --dark-gray: #5c6d5c;
      --gold: #d4af37;
      --silver: #c0c0c0;
    }
    
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Helvetica Neue', Arial, sans-serif;
    }
    
    body {
      background-color: var(--light-bg);
      color: var(--dark-text);
      overflow-x: hidden;
    }
    
    /* Loading Animation */
    .loader {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: var(--white);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 9999;
      transition: opacity 0.5s ease-out;
    }
    
    .loader-spinner {
      width: 50px;
      height: 50px;
      border: 5px solid var(--light-gray);
      border-top: 5px solid var(--primary);
      border-radius: 50%;
      animation: spin 1s linear infinite;
    }
    
    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    
    /* Coupon Banner */
    .coupon-banner {
      background: linear-gradient(135deg, var(--gold) 0%, #f5d742 100%);
      color: var(--secondary);
      text-align: center;
      padding: 10px;
      font-weight: 600;
      position: sticky;
      top: 0;
      z-index: 200;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      animation: pulse 2s infinite;
    }
    
    .coupon-code {
      background-color: var(--white);
      padding: 3px 8px;
      border-radius: 4px;
      font-weight: 700;
      margin: 0 5px;
      display: inline-block;
    }
    
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.02); }
      100% { transform: scale(1); }
    }
    
    /* Header Styles */
    .navbar {
      background-color: var(--white);
      height: 80px;
      display: flex;
      align-items: center;
      color: var(--dark-text);
      padding: 0 30px;
      position: sticky;
      top: 40px;
      z-index: 100;
      box-shadow: 0 2px 20px rgba(0,0,0,0.05);
    }
    
    .navbar-brand {
      font-size: 28px;
      font-weight: 700;
      color: var(--primary);
      margin-right: 40px;
      letter-spacing: 1px;
    }
    
    .navbar-search {
      display: flex;
      flex: 1;
      max-width: 600px;
    }
    
    .navbar-search input {
      height: 45px;
      flex: 1;
      border: 1px solid var(--light-gray);
      padding: 0 20px;
      font-size: 15px;
      border-radius: 4px 0 0 4px;
      outline: none;
    }
    
    .navbar-search button {
      height: 45px;
      width: 50px;
      border: none;
      background-color: var(--primary);
      border-radius: 0 4px 4px 0;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .navbar-search button:hover {
      background-color: var(--primary-dark);
    }
    
    .navbar-search button i {
      color: var(--white);
      font-size: 18px;
    }
    
    .navbar-options {
      display: flex;
      margin-left: auto;
      align-items: center;
    }
    
    .navbar-option {
      margin: 0 20px;
      cursor: pointer;
      font-weight: 500;
      transition: color 0.3s ease;
    }
    
    .navbar-option:hover {
      color: var(--primary);
    }
    
    .navbar-cart {
      display: flex;
      align-items: center;
      margin-left: 20px;
      cursor: pointer;
      position: relative;
    }
    
    .navbar-cart i {
      font-size: 24px;
      color: var(--dark-text);
    }
    
    .navbar-cart-count {
      background-color: var(--primary);
      color: var(--white);
      border-radius: 50%;
      width: 22px;
      height: 22px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 12px;
      position: absolute;
      top: -8px;
      right: -8px;
    }
    
    /* Categories */
    .categories {
      background-color: var(--secondary);
      height: 60px;
      display: flex;
      align-items: center;
      color: var(--white);
      padding: 0 30px;
      position: sticky;
      top: 120px;
      z-index: 90;
    }
    
    .categories-item {
      margin-right: 30px;
      font-size: 15px;
      cursor: pointer;
      transition: color 0.3s ease;
      text-transform: uppercase;
      letter-spacing: 0.5px;
      font-weight: 500;
    }
    
    .categories-item:hover {
      color: var(--gold);
    }
    
    /* Hero Section - Enhanced with Lazy Loading */
    .hero {
      height: 600px;
      background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.4));
      background-size: cover;
      background-position: center;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      color: var(--white);
      text-align: center;
      padding: 0 20px;
      margin-bottom: 80px;
      position: relative;
      overflow: hidden;
    }
    
    .hero-image {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      z-index: -1;
      opacity: 0;
      transition: opacity 1s ease;
    }
    
    .hero-image.loaded {
      opacity: 1;
    }
    
    .hero-content {
      max-width: 800px;
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 1s ease, transform 1s ease;
    }
    
    .hero-content.visible {
      opacity: 1;
      transform: translateY(0);
    }
    
    .hero h1 {
      font-size: 52px;
      margin-bottom: 25px;
      font-weight: 600;
      letter-spacing: 1px;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.3);
    }
    
    .hero p {
      font-size: 20px;
      margin-bottom: 40px;
      max-width: 700px;
      line-height: 1.6;
      text-shadow: 1px 1px 3px rgba(0,0,0,0.3);
    }
    
    .hero-button {
      background-color: var(--gold);
      color: var(--secondary);
      border: none;
      padding: 15px 40px;
      font-size: 18px;
      font-weight: 600;
      border-radius: 4px;
      cursor: pointer;
      transition: all 0.3s ease;
      letter-spacing: 0.5px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }
    
    .hero-button:hover {
      background-color: #e8c340;
      transform: translateY(-2px);
    }
    
    .hero-scroll-indicator {
      position: absolute;
      bottom: 30px;
      left: 50%;
      transform: translateX(-50%);
      animation: bounce 2s infinite;
    }
    
    .hero-scroll-indicator i {
      font-size: 30px;
      color: var(--white);
    }
    
    @keyframes bounce {
      0%, 20%, 50%, 80%, 100% {transform: translateY(0) translateX(-50%);}
      40% {transform: translateY(-20px) translateX(-50%);}
      60% {transform: translateY(-10px) translateX(-50%);}
    }
    
    /* Products Section */
    .products-section {
      padding: 0 30px 80px;
      max-width: 1400px;
      margin: 0 auto;
    }
    
    .section-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      margin-bottom: 40px;
      border-bottom: 1px solid var(--light-gray);
      padding-bottom: 15px;
    }
    
    .section-title {
      font-size: 32px;
      font-weight: 500;
      color: var(--secondary);
    }
    
    .section-subtitle {
      font-size: 16px;
      color: var(--dark-gray);
    }
    
    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 30px;
    }
    
    .product-card {
      background-color: var(--white);
      border-radius: 8px;
      padding: 25px;
      transition: all 0.3s ease;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(0,0,0,0.05);
      border: 1px solid var(--light-gray);
      position: relative;
    }
    
    .product-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 15px 30px rgba(0,0,0,0.1);
    }
    
    .product-badge {
      position: absolute;
      top: 15px;
      right: 15px;
      background-color: var(--gold);
      color: var(--secondary);
      padding: 3px 10px;
      border-radius: 4px;
      font-size: 12px;
      font-weight: 600;
    }
    
    .product-title {
      font-size: 18px;
      margin-bottom: 15px;
      font-weight: 500;
      color: var(--secondary);
      min-height: 50px;
    }
    
    .product-price {
      font-size: 22px;
      font-weight: 600;
      color: var(--primary);
      margin-bottom: 20px;
    }
    
    .product-button {
      width: 100%;
      background-color: var(--primary);
      color: var(--white);
      border: none;
      padding: 12px 0;
      border-radius: 4px;
      font-size: 15px;
      cursor: pointer;
      transition: all 0.3s ease;
      font-weight: 500;
      letter-spacing: 0.5px;
    }
    
    .product-button:hover {
      background-color: var(--primary-dark);
    }
    
    /* Premium Showcase */
    .premium-showcase {
      background: linear-gradient(135deg, #f8f9f7 0%, #e8ebe8 100%);
      padding: 80px 30px;
      margin-bottom: 80px;
    }
    
    .premium-container {
      max-width: 1400px;
      margin: 0 auto;
    }
    
    .premium-header {
      text-align: center;
      margin-bottom: 60px;
    }
    
    .premium-title {
      font-size: 36px;
      margin-bottom: 15px;
      font-weight: 500;
      color: var(--secondary);
    }
    
    .premium-subtitle {
      font-size: 18px;
      color: var(--dark-gray);
      max-width: 700px;
      margin: 0 auto;
      line-height: 1.6;
    }
    
    .premium-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
      gap: 40px;
    }
    
    .premium-card {
      background-color: var(--white);
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 10px 30px rgba(0,0,0,0.08);
      transition: all 0.5s ease;
      height: 100%;
      display: flex;
      flex-direction: column;
    }
    
    .premium-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 20px 40px rgba(0,0,0,0.15);
    }
    
    .premium-image {
      height: 250px;
      overflow: hidden;
    }
    
    .premium-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.8s ease;
    }
    
    .premium-card:hover .premium-image img {
      transform: scale(1.1);
    }
    
    .premium-content {
      padding: 30px;
      flex: 1;
      display: flex;
      flex-direction: column;
    }
    
    .premium-content h3 {
      font-size: 22px;
      margin-bottom: 15px;
      color: var(--secondary);
    }
    
    .premium-content p {
      color: var(--dark-gray);
      margin-bottom: 25px;
      line-height: 1.6;
      flex: 1;
    }
    
    .premium-button {
      background-color: var(--secondary);
      color: var(--white);
      border: none;
      padding: 12px 25px;
      border-radius: 4px;
      cursor: pointer;
      font-size: 15px;
      transition: all 0.3s ease;
      align-self: flex-start;
      font-weight: 500;
    }
    
    .premium-button:hover {
      background-color: var(--primary);
    }
    
    /* Values Section */
    .values-section {
      background-color: var(--secondary);
      color: var(--white);
      padding: 80px 30px;
      margin-bottom: 80px;
    }
    
    .values-container {
      max-width: 1400px;
      margin: 0 auto;
    }
    
    .values-header {
      text-align: center;
      margin-bottom: 60px;
    }
    
    .values-title {
      font-size: 36px;
      margin-bottom: 15px;
      font-weight: 500;
    }
    
    .values-subtitle {
      font-size: 18px;
      color: #d1d9d1;
      max-width: 700px;
      margin: 0 auto;
      line-height: 1.6;
    }
    
    .values-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 40px;
    }
    
    .value-card {
      text-align: center;
      padding: 0 20px;
    }
    
    .value-icon {
      font-size: 50px;
      margin-bottom: 25px;
      color: var(--gold);
    }
    
    .value-title {
      font-size: 22px;
      margin-bottom: 15px;
      font-weight: 500;
    }
    
    .value-description {
      font-size: 16px;
      color: #d1d9d1;
      line-height: 1.6;
    }
    
    /* Testimonials Section */
    .testimonials-section {
      padding: 80px 30px;
      background-color: var(--white);
      margin-bottom: 80px;
    }
    
    .testimonials-container {
      max-width: 1400px;
      margin: 0 auto;
    }
    
    .testimonials-header {
      text-align: center;
      margin-bottom: 60px;
    }
    
    .testimonials-title {
      font-size: 36px;
      margin-bottom: 15px;
      font-weight: 500;
      color: var(--secondary);
    }
    
    .testimonials-subtitle {
      font-size: 18px;
      color: var(--dark-gray);
      max-width: 700px;
      margin: 0 auto;
      line-height: 1.6;
    }
    
    .testimonials-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
      gap: 30px;
    }
    
    .testimonial-card {
      background-color: var(--light-bg);
      border-radius: 12px;
      padding: 40px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.05);
    }
    
    .testimonial-text {
      font-style: italic;
      margin-bottom: 25px;
      line-height: 1.8;
      font-size: 16px;
      position: relative;
    }
    
    .testimonial-text:before {
      content: '"';
      font-size: 60px;
      color: var(--gold);
      position: absolute;
      top: -20px;
      left: -20px;
      opacity: 0.2;
      font-family: serif;
    }
    
    .testimonial-author {
      display: flex;
      align-items: center;
    }
    
    .testimonial-avatar {
      width: 50px;
      height: 50px;
      border-radius: 50%;
      background-color: var(--primary);
      color: var(--white);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 600;
      margin-right: 15px;
    }
    
    .author-info h4 {
      font-size: 18px;
      margin-bottom: 5px;
      color: var(--secondary);
    }
    
    .author-info p {
      color: var(--dark-gray);
      font-size: 14px;
    }
    
    /* Contact Section */
    .contact-section {
      padding: 80px 30px;
      background-color: var(--white);
    }
    
    .contact-container {
      max-width: 1400px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
      gap: 60px;
    }
    
    .contact-info h3, .contact-map h3 {
      font-size: 28px;
      margin-bottom: 30px;
      color: var(--secondary);
      font-weight: 500;
    }
    
    .contact-info p {
      margin-bottom: 20px;
      display: flex;
      align-items: center;
      font-size: 16px;
    }
    
    .contact-info i {
      margin-right: 15px;
      color: var(--primary);
      font-size: 20px;
      width: 30px;
      text-align: center;
    }
    
    .contact-map iframe {
      width: 100%;
      height: 400px;
      border: none;
      border-radius: 12px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.1);
    }
    
    /* Footer */
    .footer {
      background-color: var(--secondary);
      color: var(--white);
      padding: 80px 30px 40px;
    }
    
    .footer-container {
      max-width: 1400px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 40px;
    }
    
    .footer-logo {
      font-size: 28px;
      font-weight: 700;
      color: var(--white);
      margin-bottom: 20px;
      display: block;
    }
    
    .footer-about {
      font-size: 15px;
      color: #d1d9d1;
      line-height: 1.8;
      margin-bottom: 20px;
    }
    
    .footer-social {
      display: flex;
      gap: 15px;
    }
    
    .footer-social a {
      color: var(--white);
      font-size: 20px;
      transition: color 0.3s ease;
    }
    
    .footer-social a:hover {
      color: var(--gold);
    }
    
    .footer-column h4 {
      font-size: 18px;
      margin-bottom: 25px;
      color: var(--white);
      font-weight: 500;
      letter-spacing: 0.5px;
    }
    
    .footer-column ul {
      list-style: none;
    }
    
    .footer-column ul li {
      margin-bottom: 15px;
    }
    
    .footer-column ul li a {
      color: #d1d9d1;
      text-decoration: none;
      font-size: 15px;
      transition: all 0.3s ease;
    }
    
    .footer-column ul li a:hover {
      color: var(--white);
      padding-left: 5px;
    }
    
    .footer-bottom {
      text-align: center;
      padding-top: 60px;
      margin-top: 60px;
      border-top: 1px solid #3e4e3e;
      font-size: 14px;
      color: #a1b1a1;
    }
    
    /* Newsletter Section */
    .newsletter-section {
      background-color: var(--primary);
      padding: 60px 30px;
      color: var(--white);
      text-align: center;
    }
    
    .newsletter-container {
      max-width: 800px;
      margin: 0 auto;
    }
    
    .newsletter-title {
      font-size: 32px;
      margin-bottom: 20px;
    }
    
    .newsletter-subtitle {
      font-size: 18px;
      margin-bottom: 40px;
      opacity: 0.9;
    }
    
    .newsletter-form {
      display: flex;
      max-width: 500px;
      margin: 0 auto;
    }
    
    .newsletter-input {
      flex: 1;
      padding: 15px 20px;
      border: none;
      border-radius: 4px 0 0 4px;
      font-size: 16px;
    }
    
    .newsletter-button {
      background-color: var(--gold);
      color: var(--secondary);
      border: none;
      padding: 0 25px;
      font-weight: 600;
      border-radius: 0 4px 4px 0;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .newsletter-button:hover {
      background-color: #e8c340;
    }
    
    /* Modal Styles */
    .modal-overlay {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background-color: rgba(0,0,0,0.7);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
      opacity: 0;
      visibility: hidden;
      transition: all 0.3s ease;
    }
    
    .modal-overlay.active {
      opacity: 1;
      visibility: visible;
    }
    
    .modal {
      background-color: var(--white);
      border-radius: 12px;
      width: 90%;
      max-width: 500px;
      max-height: 90vh;
      overflow-y: auto;
      padding: 40px;
      position: relative;
      box-shadow: 0 20px 40px rgba(0,0,0,0.2);
    }
    
    .modal-close {
      position: absolute;
      top: 20px;
      right: 20px;
      font-size: 24px;
      cursor: pointer;
      color: var(--dark-gray);
      transition: all 0.3s ease;
    }
    
    .modal-close:hover {
      color: var(--primary);
    }
    
    .modal-title {
      font-size: 24px;
      margin-bottom: 25px;
      color: var(--secondary);
      font-weight: 500;
    }
    
    .cart-item {
      display: flex;
      justify-content: space-between;
      margin-bottom: 20px;
      padding-bottom: 20px;
      border-bottom: 1px solid var(--light-gray);
    }
    
    .cart-item-details {
      flex: 1;
    }
    
    .cart-item-title {
      font-size: 16px;
      margin-bottom: 5px;
      font-weight: 500;
    }
    
    .cart-item-price {
      font-weight: 600;
      color: var(--primary);
    }
    
    .cart-item-remove {
      color: var(--dark-gray);
      font-size: 14px;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .cart-item-remove:hover {
      color: var(--primary);
    }
    
    .coupon-apply {
      margin: 25px 0;
    }
    
    .coupon-input {
      width: 100%;
      padding: 12px;
      border: 1px solid var(--light-gray);
      border-radius: 4px;
      margin-bottom: 10px;
      font-size: 15px;
    }
    
    .coupon-button {
      width: 100%;
      padding: 10px;
      background-color: var(--gold);
      color: var(--secondary);
      border: none;
      border-radius: 4px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .coupon-button:hover {
      background-color: #e8c340;
    }
    
    .cart-total {
      font-size: 20px;
      font-weight: 600;
      margin: 25px 0;
      text-align: right;
    }
    
    .cart-buttons {
      display: flex;
      justify-content: space-between;
      gap: 15px;
    }
    
    .cart-button {
      padding: 12px 25px;
      border: none;
      border-radius: 4px;
      font-weight: 500;
      cursor: pointer;
      transition: all 0.3s ease;
      flex: 1;
    }
    
    .cart-button.primary {
      background-color: var(--primary);
      color: var(--white);
    }
    
    .cart-button.primary:hover {
      background-color: var(--primary-dark);
    }
    
    .cart-button.secondary {
      background-color: var(--light-gray);
      color: var(--dark-text);
    }
    
    .cart-button.secondary:hover {
      background-color: #d8dbd8;
    }
    
    .login-form input {
      width: 100%;
      padding: 12px;
      margin-bottom: 15px;
      border: 1px solid var(--light-gray);
      border-radius: 4px;
      font-size: 16px;
    }
    
    .login-form button {
      width: 100%;
      padding: 12px;
      background-color: var(--primary);
      border: none;
      border-radius: 4px;
      font-size: 16px;
      font-weight: 500;
      color: var(--white);
      cursor: pointer;
      margin-top: 10px;
      transition: all 0.3s ease;
    }
    
    .login-form button:hover {
      background-color: var(--primary-dark);
    }
    
    .form-footer {
      text-align: center;
      margin-top: 20px;
      font-size: 14px;
    }
    
    .form-footer a {
      color: var(--primary);
      text-decoration: none;
      transition: all 0.3s ease;
    }
    
    .form-footer a:hover {
      text-decoration: underline;
    }
    
    /* Payment Modal Styles */
    .payment-section {
      margin-bottom: 30px;
      padding-bottom: 20px;
      border-bottom: 1px solid var(--light-gray);
    }
    
    .payment-section h4 {
      font-size: 18px;
      margin-bottom: 15px;
      color: var(--secondary);
    }
  
    .payment-methods {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }
    
    .payment-method {
      border: 1px solid var(--light-gray);
      border-radius: 8px;
      padding: 15px;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .payment-method:hover {
      border-color: var(--primary);
      background-color: rgba(58, 125, 68, 0.05);
    }
    
    .payment-method input[type="radio"] {
      display: none;
    }
    
    .payment-method input[type="radio"]:checked + label {
      color: var(--primary);
    }
    
    .payment-method label {
      display: flex;
      align-items: center;
      gap: 15px;
      cursor: pointer;
      font-weight: 500;
    }
    
    .payment-method img {
      width: 40px;
      height: 40px;
      object-fit: contain;
    }
    
    .payment-method i {
      font-size: 24px;
      color: var(--primary);
      width: 40px;
      text-align: center;
    }
    
    .upi-id {
      display: flex;
      align-items: center;
      gap: 10px;
      margin: 15px 0;
      padding: 10px 15px;
      background-color: var(--light-bg);
      border-radius: 8px;
    }
    
    .upi-id span {
      font-family: monospace;
      font-size: 18px;
      flex: 1;
    }
    
    .upi-id button {
      background-color: var(--primary);
      color: white;
      border: none;
      padding: 8px 15px;
      border-radius: 4px;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .upi-id button:hover {
      background-color: var(--primary-dark);
    }
    
    .qr-code {
      text-align: center;
      margin: 20px 0;
    }
    
    .qr-code img {
      max-width: 200px;
      border: 1px solid var(--light-gray);
      padding: 10px;
      border-radius: 8px;
    }
    
    .form-group {
      margin-bottom: 15px;
    }
    
    .form-group label {
      display: block;
      margin-bottom: 8px;
      font-size: 14px;
      color: var(--dark-gray);
    }
    
    .form-group input,
    .form-group textarea {
      width: 100%;
      padding: 12px;
      border: 1px solid var(--light-gray);
      border-radius: 4px;
      font-size: 15px;
    }
    
    .form-group textarea {
      resize: vertical;
    }
    
    .payment-buttons {
      display: flex;
      gap: 15px;
      margin-top: 20px;
    }
    
    .payment-button {
      padding: 12px 25px;
      border: none;
      border-radius: 4px;
      font-weight: 500;
      cursor: pointer;
      transition: all 0.3s ease;
      flex: 1;
    }
    
    .payment-button.primary {
      background-color: var(--primary);
      color: var(--white);
    }
    
    .payment-button.primary:hover {
      background-color: var(--primary-dark);
    }
    
    .payment-button.secondary {
      background-color: var(--light-gray);
      color: var(--dark-text);
    }
    
    .payment-button.secondary:hover {
      background-color: #d8dbd8;
    }
    
    #payment-summary {
      max-height: 200px;
      overflow-y: auto;
      margin-bottom: 15px;
    }
    
    .payment-item {
      display: flex;
      justify-content: space-between;
      padding: 8px 0;
      border-bottom: 1px dashed var(--light-gray);
    }
    
    .payment-total {
      font-size: 18px;
      font-weight: 600;
      text-align: right;
      padding: 10px 0;
    }
    
    /* Responsive Styles */
    @media (max-width: 1200px) {
      .navbar {
        padding: 0 20px;
      }
      
      .categories {
        padding: 0 20px;
      }
      
      .products-section, .premium-showcase, .values-section, 
      .testimonials-section, .contact-section {
        padding-left: 20px;
        padding-right: 20px;
      }
    }
    
    @media (max-width: 992px) {
      .hero h1 {
        font-size: 42px;
      }
      
      .hero p {
        font-size: 18px;
      }
      
      .section-title {
        font-size: 28px;
      }
      
      .premium-title, .values-title, .testimonials-title {
        font-size: 32px;
      }
    }
    
    @media (max-width: 768px) {
      .coupon-banner {
        font-size: 14px;
        top: -1px;
      }
      
      .navbar {
        height: 70px;
        top: 39px;
        padding: 0 15px;
      }
      
      .navbar-brand {
        font-size: 24px;
        margin-right: 20px;
      }
      
      .navbar-option {
        margin: 0 15px;
        font-size: 14px;
      }
      
      .categories {
        height: 50px;
        top: 109px;
        overflow-x: auto;
        white-space: nowrap;
      }
      
      .categories-item {
        margin-right: 20px;
        font-size: 14px;
      }
      
      .hero {
        height: 500px;
        margin-bottom: 60px;
      }
      
      .hero h1 {
        font-size: 36px;
      }
      
      .hero-button {
        padding: 12px 30px;
        font-size: 16px;
      }
      
      .premium-grid, .testimonials-grid {
        grid-template-columns: 1fr;
      }
      
      .contact-container {
        grid-template-columns: 1fr;
      }
      
      .contact-map iframe {
        height: 300px;
      }
      
      .newsletter-form {
        flex-direction: column;
      }
      
      .newsletter-input {
        border-radius: 4px;
        margin-bottom: 10px;
      }
      
      .newsletter-button {
        border-radius: 4px;
        padding: 15px;
      }
    }
    
    @media (max-width: 576px) {
      .coupon-banner {
        padding: 8px;
        font-size: 12px;
      }
      
      .navbar {
        height: 60px;
        top: 38px;
      }
      
      .navbar-brand {
        font-size: 20px;
      }
      
      .navbar-search input {
        height: 40px;
        padding: 0 15px;
      }
      
      .navbar-search button {
        height: 40px;
        width: 40px;
      }
      
      .navbar-options {
        display: none;
      }
      
      .categories {
        top: 98px;
      }
      
      .hero {
        height: 400px;
        margin-bottom: 40px;
      }
      
      .hero h1 {
        font-size: 28px;
      }
      
      .hero p {
        font-size: 16px;
      }
      
      .section-title {
        font-size: 24px;
      }
      
      .products-grid {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <!-- Loading Screen -->
  <div class="loader" id="loader">
    <div class="loader-spinner"></div>
  </div>
  
  <!-- Coupon Banner -->
  <div class="coupon-banner">
    <span>Sign up today and get <span class="coupon-code">WELCOME5</span> for 5% off!</span>
    <span>First order? Use <span class="coupon-code">FIRST10</span> for 10% off!</span>
  </div>
  
  <!-- Navigation -->
  <div class="navbar">
    <div class="navbar-brand">RasoiRoots</div>
    <div class="navbar-search">
      <input type="text" id="search-input" placeholder="Search for spices...">
      <button onclick="searchProducts()"><i class="fas fa-search"></i></button>
    </div>
    <div class="navbar-options">
      <div class="navbar-option" onclick="toggleLoginModal()">Account</div>
      <div class="navbar-option">Orders</div>
    </div>
    <div class="navbar-cart" onclick="toggleCartModal()">
      <i class="fas fa-shopping-cart"></i>
      <span class="navbar-cart-count" id="cart-count">0</span>
    </div>
  </div>
  
  <!-- Categories -->
  <div class="categories">
    <div class="categories-item">All Spices</div>
    <div class="categories-item">Powders</div>
    <div class="categories-item">Whole Spices</div>
    <div class="categories-item">Oils</div>
    <div class="categories-item">Flours</div>
    <div class="categories-item">Blends</div>
  </div>
  
  <!-- Hero Section - Enhanced with Lazy Loading -->
  <div class="hero">
    <img 
      src="https://images.unsplash.com/photo-1511836953460-80a2b1c6a896?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=20" 
      data-src="https://images.unsplash.com/photo-1511836953460-80a2b1c6a896?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80" 
      alt="Authentic Indian Spices" 
      class="hero-image"
      id="hero-image"
    >
    <div class="hero-content" id="hero-content">
      <h1>Discover the Essence of Indian Cuisine</h1>
      <p>Elevate your dishes with our handcrafted spices, sourced from the finest farms and crafted using age-old traditions for unparalleled flavor.</p>
      <button class="hero-button" onclick="document.getElementById('products').scrollIntoView({ behavior: 'smooth' })">Explore Our Spices</button>
    </div>
    <div class="hero-scroll-indicator">
      <i class="fas fa-chevron-down"></i>
    </div>
  </div>
  
  <!-- Products Section -->
  <div class="products-section" id="products">
    <div class="section-header">
      <h2 class="section-title">Our Best Sellers</h2>
      <p class="section-subtitle">Pure, authentic spices made with care</p>
    </div>
    <div class="products-grid" id="products-grid">
      <!-- Products will be loaded here by JavaScript -->
    </div>
  </div>
  
  <!-- Newsletter Section -->
  <div class="newsletter-section">
    <div class="newsletter-container">
      <h2 class="newsletter-title">Join Our Spice Community</h2>
      <p class="newsletter-subtitle">Subscribe to get exclusive offers, recipes, and updates on new products</p>
      <div class="newsletter-form">
        <input type="email" class="newsletter-input" placeholder="Enter your email address">
        <button class="newsletter-button">Subscribe</button>
      </div>
    </div>
  </div>
  
  <!-- Values Section -->
  <div class="values-section">
    <div class="values-container">
      <div class="values-header">
        <h2 class="values-title">Our Core Values</h2>
        <p class="values-subtitle">The principles that guide everything we do at RasoiRoots</p>
      </div>
      <div class="values-grid">
        <div class="value-card">
          <div class="value-icon"><i class="fas fa-leaf"></i></div>
          <h3 class="value-title">Purity</h3>
          <p class="value-description">No additives, preservatives or artificial colors - just pure spices as nature intended, with all their natural flavors and health benefits intact.</p>
        </div>
        <div class="value-card">
          <div class="value-icon"><i class="fas fa-home"></i></div>
          <h3 class="value-title">Authenticity</h3>
          <p class="value-description">Prepared in small batches using traditional family recipes and methods that preserve the true essence of Indian spices.</p>
        </div>
        <div class="value-card">
          <div class="value-icon"><i class="fas fa-heart"></i></div>
          <h3 class="value-title">Passion</h3>
          <p class="value-description">A deep love for authentic Indian flavors drives us to source and prepare the finest spices for your kitchen.</p>
        </div>
      </div>
    </div>
  </div>
  
  <!-- Testimonials Section -->
  <div class="testimonials-section">
    <div class="testimonials-container">
      <div class="testimonials-header">
        <h2 class="testimonials-title">What Our Community Says</h2>
        <p class="testimonials-subtitle">Join thousands of home cooks who've transformed their cooking with RasoiRoots spices</p>
      </div>
      <div class="testimonials-grid">
        <div class="testimonial-card">
          <p class="testimonial-text">The spices from RasoiRoots have completely changed my cooking. The flavors are so much more vibrant than anything I've bought from stores. My family can't believe the difference in my dishes!</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">P</div>
            <div class="author-info">
              <h4>Priya Sharma</h4>
              <p>Home Chef, Mumbai</p>
            </div>
          </div>
        </div>
        <div class="testimonial-card">
          <p class="testimonial-text">As a professional chef, I'm extremely particular about my spices. RasoiRoots delivers consistent quality that I can rely on for my restaurant. Their garam masala blend is exceptional.</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">A</div>
            <div class="author-info">
              <h4>Amit Khanna</h4>
              <p>Executive Chef, Delhi</p>
            </div>
          </div>
        </div>
        <div class="testimonial-card">
          <p class="testimonial-text">Living abroad, I've struggled to find authentic Indian spices. RasoiRoots has been a godsend - their products taste just like what my mother used to cook with. The mustard oil is particularly special.</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">S</div>
            <div class="author-info">
              <h4>Sunita Patel</h4>
              <p>Food Blogger, New York</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  
  <!-- Contact Section -->
  <div class="contact-section">
    <div class="contact-container">
      <div class="contact-info">
        <h3>Get In Touch</h3>
        <p><i class="fas fa-map-marker-alt"></i> Atmadsarai, 203408 (Bulandshahr)</p>
        <p><i class="fas fa-phone"></i> 8954152963, 9411911398</p>
        <p><i class="fas fa-envelope"></i> info@rasoiroots.com</p>
        <p><i class="fas fa-clock"></i> Monday-Saturday: 9AM - 6PM</p>
        <p><i class="fas fa-truck"></i> Free shipping on orders over ₹500</p>
      </div>
      <div class="contact-map">
        <h3>Our Location</h3>
        <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d7013.10749881545!2d77.83320958044123!3d28.492982870475725!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x390ca3772100734b%3A0x2b85934592a389b9!2sBrajpal%20Madhyan-%20oil%20mill%20%2C%20flour%20mill%20and%20spices%20point.!5e0!3m2!1sen!2sin!4v1752819092269!5m2!1sen!2sin" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
    </div>
  </div>
  
  <!-- Footer -->
  <div class="footer">
    <div class="footer-container">
      <div class="footer-column">
        <a href="#" class="footer-logo">RasoiRoots</a>
        <p class="footer-about">Handcrafted spices made with traditional methods for authentic Indian flavors. Proudly made in India with love and care.</p>
        <div class="footer-social">
          <a href="#"><i class="fab fa-instagram"></i></a>
          <a href="#"><i class="fab fa-facebook"></i></a>
          <a href="#"><i class="fab fa-whatsapp"></i></a>
          <a href="#"><i class="fab fa-youtube"></i></a>
        </div>
      </div>
      <div class="footer-column">
        <h4>Shop</h4>
        <ul>
          <li><a href="#">All Products</a></li>
          <li><a href="#">Best Sellers</a></li>
          <li><a href="#">New Arrivals</a></li>
          <li><a href="#">Gift Collections</a></li>
          <li><a href="#">Bulk Orders</a></li>
        </ul>
      </div>
      <div class="footer-column">
        <h4>About</h4>
        <ul>
          <li><a href="#">Our Story</a></li>
          <li><a href="#">Traditional Methods</a></li>
          <li><a href="#">Farm Partners</a></li>
          <li><a href="#">Blog</a></li>
          <li><a href="#">Careers</a></li>
        </ul>
      </div>
      <div class="footer-column">
        <h4>Help</h4>
        <ul>
          <li><a href="#">Contact Us</a></li>
          <li><a href="#">Shipping Policy</a></li>
          <li><a href="#">Returns & Exchanges</a></li>
          <li><a href="#">FAQ</a></li>
          <li><a href="#">Recipes</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2023 RasoiRoots. All Rights Reserved. | Made in India with ❤️</p>
    </div>
  </div>
  
  <!-- Cart Modal -->
  <div class="modal-overlay" id="cart-modal">
    <div class="modal">
      <div class="modal-close" onclick="toggleCartModal()">&times;</div>
      <h3 class="modal-title">Your Shopping Cart</h3>
      <div id="cart-items-container"></div>
      
      <div class="coupon-apply">
        <input type="text" class="coupon-input" placeholder="Enter coupon code">
        <button class="coupon-button" onclick="applyCoupon()">Apply Coupon</button>
      </div>
      
      <div class="cart-total">
        Total: ₹<span id="cart-total">0</span>
        <div id="discount-message" style="font-size:14px; color:var(--primary); margin-top:5px;"></div>
      </div>
      <div class="cart-buttons">
        <button class="cart-button secondary" onclick="toggleCartModal()">Continue Shopping</button>
        <button class="cart-button primary" onclick="togglePaymentModal()">Proceed to Buy</button>
      </div>
    </div>
  </div>
  
  <!-- Payment Modal -->
  <div class="modal-overlay" id="payment-modal">
    <div class="modal">
      <div class="modal-close" onclick="togglePaymentModal()">&times;</div>
      <h3 class="modal-title">Complete Your Purchase</h3>
      
      <div class="payment-section">
        <h4>Order Summary</h4>
        <div id="payment-summary"></div>
        <div class="payment-total">
          Total: ₹<span id="payment-total">0</span>
        </div>
      </div>
      
      <div class="payment-section">
        <h4>Select Payment Method</h4>
        <div class="payment-methods">
          <div class="payment-method" onclick="selectPaymentMethod('paytm')">
            <input type="radio" name="payment" id="paytm-radio">
            <label for="paytm-radio">
              <img src="https://logos-download.com/wp-content/uploads/2020/06/Paytm_Logo_icon.png" alt="Paytm">
              <span>Paytm</span>
            </label>
          </div>
          
          <div class="payment-method" onclick="selectPaymentMethod('phonepe')">
            <input type="radio" name="payment" id="phonepe-radio">
            <label for="phonepe-radio">
              <img src="https://logos-download.com/wp-content/uploads/2021/01/PhonePe_Logo_icon.png" alt="PhonePe">
              <span>PhonePe</span>
            </label>
          </div>
          
          <div class="payment-method" onclick="selectPaymentMethod('cod')">
            <input type="radio" name="payment" id="cod-radio">
            <label for="cod-radio">
              <i class="fas fa-money-bill-wave"></i>
              <span>Cash on Delivery</span>
            </label>
          </div>
        </div>
      </div>
      
      <div class="payment-section" id="upi-details" style="display:none;">
        <h4>UPI Payment Details</h4>
        <p>Please send payment to our UPI ID:</p>
        <div class="upi-id">
          <span>9411911398@paytm</span>
          <button onclick="copyUpiId()">Copy</button>
        </div>
        <p>Or scan this QR code:</p>
        <div class="qr-code">
          <img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=9411911398@paytm" alt="UPI QR Code">
        </div>
        <div class="form-group">
          <label for="transaction-id">Transaction ID (after payment):</label>
          <input type="text" id="transaction-id" placeholder="Enter UPI transaction ID">
        </div>
      </div>
      
      <div class="payment-section" id="cod-details" style="display:none;">
        <h4>Cash on Delivery</h4>
        <p>Pay when your order is delivered. Please have exact change ready.</p>
        <div class="form-group">
          <label for="delivery-address">Delivery Address:</label>
          <textarea id="delivery-address" rows="4" placeholder="Enter your complete address"></textarea>
        </div>
      </div>
      
      <div class="payment-buttons">
        <button class="payment-button secondary" onclick="togglePaymentModal()">Back to Cart</button>
        <button class="payment-button primary" onclick="confirmPayment()">Confirm Order</button>
      </div>
    </div>
  </div>
  
  <!-- Login Modal -->
  <div class="modal-overlay" id="login-modal">
    <div class="modal">
      <div class="modal-close" onclick="toggleLoginModal()">&times;</div>
      <h3 class="modal-title">Sign In</h3>
      <div class="login-form">
        <input type="text" placeholder="Email or mobile phone number">
        <input type="password" placeholder="Password">
        <button onclick="handleLogin()">Sign In</button>
        <div class="form-footer">
          <p>New to RasoiRoots? <a href="#">Create an account</a></p>
        </div>
      </div>
    </div>
  </div>
  
  <script>
    // Product data
    const products = [
      { 
        id: 1, 
        name: "Red Chilly Powder (200g)", 
        price: 75, 
        category: "powders", 
        isNew: false, 
        isBestSeller: true,
        description: "Our fiery red chili powder is made from sun-dried, hand-picked chilies ground to perfection. Adds authentic heat and vibrant color to your dishes.",
        image: "https://images.unsplash.com/photo-1576186726580-a816e8b12896?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
      },
      { 
        id: 2, 
        name: "Garam Masala (200g)", 
        price: 200, 
        category: "blends", 
        isNew: false, 
        isBestSeller: true,
        description: "Our signature garam masala blend contains a perfect balance of 12 aromatic spices. Slow-roasted and ground for maximum flavor.",
        image: "https://images.unsplash.com/photo-1586201375761-83865001e31c?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
      },
      { 
        id: 3, 
        name: "Turmeric Powder (200g)", 
        price: 80, 
        category: "powders", 
        isNew: false, 
        isBestSeller: true,
        description: "Pure, golden turmeric powder with its characteristic earthy flavor and brilliant color. Sourced directly from organic farms.",
        image: "https://images.unsplash.com/photo-1599058917765-a780eda07a3e?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
      },
      { 
        id: 4, 
        name: "Dhania Powder (200g)", 
        price: 80, 
        category: "powders", 
        isNew: true, 
        isBestSeller: false,
        description: "Freshly ground coriander powder with a citrusy, slightly sweet flavor. An essential ingredient in countless Indian dishes.",
        image: "https://images.unsplash.com/photo-1470124182917-cc6e71b22ecc?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
      },
      { 
        id: 5, 
        name: "Cumin Seeds (200g)", 
        price: 120, 
        category: "whole", 
        isNew: true, 
        isBestSeller: false,
        description: "Premium quality cumin seeds with their distinctive earthy, nutty flavor. Perfect for tempering and seasoning.",
        image: "https://images.unsplash.com/photo-1558961364-6c8b228a4683?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
      },
      { 
        id: 6, 
        name: "Mustard Oil (1L)", 
        price: 170, 
        category: "oils", 
        isNew: false, 
        isBestSeller: true,
        description: "Cold-pressed mustard oil with its characteristic pungent aroma and rich flavor. Ideal for cooking and traditional remedies.",
        image: "https://images.unsplash.com/photo-1574323347407-f5e1ad6d020b?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
      },
      { 
        id: 7, 
        name: "Besan (1kg)", 
        price: 100, 
        category: "flours", 
        isNew: false, 
        isBestSeller: false,
        description: "Finely milled chickpea flour perfect for making pakoras, kadhi, and various Indian sweets. Gluten-free and protein-rich.",
        image: "https://images.unsplash.com/photo-1599058917765-a780eda07a3e?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
      },
      { 
        id: 8, 
        name: "Black Pepper (100g)", 
        price: 150, 
        category: "whole", 
        isNew: true, 
        isBestSeller: false,
        description: "Premium Malabar black pepper with a robust flavor and enticing aroma. Hand-harvested at peak maturity for optimal taste.",
        image: "https://images.unsplash.com/photo-1517433670267-08bbd4be890f?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
      }
    ];
    
    let cart = [];
    let appliedCoupon = null;
    
    // Coupon codes
    const coupons = {
      "WELCOME5": { discount: 5, type: "percentage", description: "5% off on sign up" },
      "FIRST10": { discount: 10, type: "percentage", description: "10% off first order" }
    };
    
    // Initialize the page
    document.addEventListener('DOMContentLoaded', function() {
      // Hide loader after page loads
      setTimeout(() => {
        document.getElementById('loader').style.opacity = '0';
        setTimeout(() => {
          document.getElementById('loader').style.display = 'none';
        }, 500);
      }, 1500);
      
      renderProducts();
      lazyLoadHeroImage();
      
      // Check for first visit to show welcome coupon
      if (!localStorage.getItem('visitedBefore')) {
        localStorage.setItem('visitedBefore', 'true');
        showWelcomeNotification();
      }
    });
    
    // Lazy load hero image
    function lazyLoadHeroImage() {
      const heroImage = document.getElementById('hero-image');
      const highResImage = new Image();
      
      highResImage.onload = function() {
        heroImage.src = this.src;
        heroImage.classList.add('loaded');
        document.getElementById('hero-content').classList.add('visible');
      };
      
      highResImage.src = heroImage.getAttribute('data-src');
    }
    
    // Show welcome notification
    function showWelcomeNotification() {
      alert("Welcome to RasoiRoots! Use coupon code WELCOME5 for 5% off your first order!");
    }
    
    // Render products to the page
    function renderProducts(filteredProducts) {
      const productsToRender = filteredProducts || products;
      const grid = document.getElementById('products-grid');
      grid.innerHTML = '';
      
      productsToRender.forEach(product => {
        const productElement = document.createElement('div');
        productElement.className = 'product-card';
        
        let badge = '';
        if (product.isNew) {
          badge = '<div class="product-badge">New</div>';
        } else if (product.isBestSeller) {
          badge = '<div class="product-badge">Bestseller</div>';
        }
        
        productElement.innerHTML = `
          ${badge}
          <div class="product-title">${product.name}</div>
          <div class="product-price">₹${product.price}</div>
          <button class="product-button" onclick="addToCart(${product.id})">Add to Cart</button>
        `;
        grid.appendChild(productElement);
      });
    }
    
    // Search functionality
    function searchProducts() {
      const searchTerm = document.getElementById('search-input').value.toLowerCase();
      if (searchTerm.trim() === '') {
        renderProducts();
        return;
      }
      
      const filtered = products.filter(product => 
        product.name.toLowerCase().includes(searchTerm) ||
        product.category.toLowerCase().includes(searchTerm) ||
        product.description.toLowerCase().includes(searchTerm)
      );
      renderProducts(filtered);
    }
    
    // Add event listener for Enter key in search
    document.getElementById('search-input').addEventListener('keypress', function(e) {
      if (e.key === 'Enter') {
        searchProducts();
      }
    });
    
    // Toggle modals
    function toggleCartModal() {
      document.getElementById('cart-modal').classList.toggle('active');
      updateCartDisplay();
    }
    
    function togglePaymentModal() {
      document.getElementById('payment-modal').classList.toggle('active');
      if (document.getElementById('payment-modal').classList.contains('active')) {
        updatePaymentSummary();
      }
    }
    
    function toggleLoginModal() {
      document.getElementById('login-modal').classList.toggle('active');
    }
    
    // Cart functions
    function addToCart(productId) {
      const product = products.find(p => p.id === productId);
      if (product) {
        cart.push(product);
        updateCartDisplay();
        
        // Show notification
        showNotification(`${product.name} added to cart!`);
      }
    }
    
    function showNotification(message) {
      const notification = document.createElement('div');
      notification.style.position = 'fixed';
      notification.style.bottom = '20px';
      notification.style.right = '20px';
      notification.style.backgroundColor = 'var(--primary)';
      notification.style.color = 'white';
      notification.style.padding = '15px 25px';
      notification.style.borderRadius = '4px';
      notification.style.boxShadow = '0 4px 15px rgba(0,0,0,0.2)';
      notification.style.zIndex = '1000';
      notification.style.animation = 'fadeIn 0.3s';
      notification.innerHTML = message;
      
      document.body.appendChild(notification);
      
      setTimeout(() => {
        notification.style.animation = 'fadeOut 0.3s';
        setTimeout(() => {
          document.body.removeChild(notification);
        }, 300);
      }, 2000);
    }
    
    function removeFromCart(index) {
      cart.splice(index, 1);
      updateCartDisplay();
    }
    
    function updateCartDisplay() {
      const container = document.getElementById('cart-items-container');
      container.innerHTML = '';
      
      let subtotal = 0;
      
      if (cart.length === 0) {
        container.innerHTML = '<p style="text-align:center;">Your cart is empty</p>';
      } else {
        cart.forEach((item, index) => {
          subtotal += item.price;
          
          const itemElement = document.createElement('div');
          itemElement.className = 'cart-item';
          itemElement.innerHTML = `
            <div class="cart-item-details">
              <div class="cart-item-title">${item.name}</div>
              <div class="cart-item-price">₹${item.price}</div>
            </div>
            <div class="cart-item-remove" onclick="removeFromCart(${index})">Remove</div>
          `;
          
          container.appendChild(itemElement);
        });
      }
      
      // Calculate total with coupon if applied
      let total = subtotal;
      let discountMessage = '';
      
      if (appliedCoupon) {
        if (appliedCoupon.type === 'percentage') {
          const discountAmount = (subtotal * appliedCoupon.discount) / 100;
          total = subtotal - discountAmount;
          discountMessage = `${appliedCoupon.discount}% off applied (₹${discountAmount.toFixed(2)})`;
        }
      }
      
      document.getElementById('cart-total').textContent = total.toFixed(2);
      document.getElementById('discount-message').textContent = discountMessage;
      document.getElementById('cart-count').textContent = cart.length;
    }
    
    // Apply coupon code
    function applyCoupon() {
      const couponInput = document.querySelector('.coupon-input');
      const couponCode = couponInput.value.trim();
      
      if (coupons[couponCode]) {
        appliedCoupon = coupons[couponCode];
        updateCartDisplay();
        couponInput.value = '';
        
        // Show success notification
        showNotification(`Coupon applied successfully! ${appliedCoupon.description}`);
      } else {
        showNotification('Invalid coupon code. Please try again.');
      }
    }
    
    // Payment functions
    function selectPaymentMethod(method) {
      document.getElementById('upi-details').style.display = 'none';
      document.getElementById('cod-details').style.display = 'none';
      
      if (method === 'paytm' || method === 'phonepe') {
        document.getElementById('upi-details').style.display = 'block';
      } else if (method === 'cod') {
        document.getElementById('cod-details').style.display = 'block';
      }
      
      // Update the radio button
      document.getElementById(`${method}-radio`).checked = true;
    }
    
    function copyUpiId() {
      navigator.clipboard.writeText('9411911398@paytm');
      showNotification('UPI ID copied to clipboard!');
    }
    
    function updatePaymentSummary() {
      const summaryContainer = document.getElementById('payment-summary');
      summaryContainer.innerHTML = '';
      
      if (cart.length === 0) {
        summaryContainer.innerHTML = '<p>No items in cart</p>';
        document.getElementById('payment-total').textContent = '0';
        return;
      }
      
      let subtotal = 0;
      cart.forEach(item => {
        subtotal += item.price;
        
        const itemElement = document.createElement('div');
        itemElement.className = 'payment-item';
        itemElement.innerHTML = `
          <span>${item.name}</span>
          <span>₹${item.price}</span>
        `;
        summaryContainer.appendChild(itemElement);
      });
      
      // Calculate total with coupon if applied
      let total = subtotal;
      if (appliedCoupon) {
        if (appliedCoupon.type === 'percentage') {
          const discountAmount = (subtotal * appliedCoupon.discount) / 100;
          total = subtotal - discountAmount;
          
          const discountElement = document.createElement('div');
          discountElement.className = 'payment-item';
          discountElement.innerHTML = `
            <span>Discount (${appliedCoupon.discount}%)</span>
            <span>-₹${discountAmount.toFixed(2)}</span>
          `;
          summaryContainer.appendChild(discountElement);
        }
      }
      
      document.getElementById('payment-total').textContent = total.toFixed(2);
    }
    
    function confirmPayment() {
      const selectedPayment = document.querySelector('input[name="payment"]:checked');
      if (!selectedPayment) {
        showNotification('Please select a payment method');
        return;
      }
      
      const paymentMethod = selectedPayment.id.replace('-radio', '');
      let message = `Order confirmed! Total: ₹${document.getElementById('payment-total').textContent}\n\n`;
      
      if (paymentMethod === 'cod') {
        const address = document.getElementById('delivery-address').value.trim();
        if (!address) {
          showNotification('Please enter your delivery address');
          return;
        }
        message += `Your order will be delivered to:\n${address}\n\nPlease pay ₹${document.getElementById('payment-total').textContent} when your order arrives.`;
      } else {
        message += `Please complete your ${paymentMethod === 'paytm' ? 'Paytm' : 'PhonePe'} payment to UPI ID: 9411911398@paytm\n\n`;
        
        const transactionId = document.getElementById('transaction-id').value.trim();
        if (transactionId) {
          message += `Transaction ID: ${transactionId}\nWe'll verify your payment and process your order.`;
        } else {
          message += `Once payment is complete, please share the transaction ID with us at 9411911398.`;
        }
      }
      
      showNotification(message);
      
      // Reset everything
      cart = [];
      appliedCoupon = null;
      updateCartDisplay();
      togglePaymentModal();
      toggleCartModal();
    }
    
    // Handle login
    function handleLogin() {
      showNotification('Welcome back! As a thank you, use coupon code FIRST10 for 10% off your first order!');
      toggleLoginModal();
    }
    
    // Close modals when clicking outside
    window.addEventListener('click', function(event) {
      if (event.target === document.getElementById('cart-modal')) {
        toggleCartModal();
      }
      if (event.target === document.getElementById('login-modal')) {
        toggleLoginModal();
      }
      if (event.target === document.getElementById('payment-modal')) {
        togglePaymentModal();
      }
    });
  </script>
</body>
</html>
