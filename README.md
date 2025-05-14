<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>The Fuel Factor</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Montserrat', sans-serif;
      background: #fdfdfd;
      color: #222;
      scroll-behavior: smooth;
    }
    header {
      background: linear-gradient(135deg, #1a2980, #26d0ce);
      color: white;
      text-align: center;
      padding: 8rem 2rem;
      animation: fadeIn 2s ease-out;
      position: relative;
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
      overflow: hidden;
    }
    header::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: url('https://www.transparenttextures.com/patterns/cubes.png');
      opacity: 0.1;
      animation: fadeIn 3s ease-out;
    }
    header::after {
      content: '';
      position: absolute;
      bottom: -50px;
      left: 0;
      right: 0;
      height: 100px;
      background: linear-gradient(to bottom right, transparent 49%, white 50%);
    }
    header h1 {
      font-size: 3.5rem;
      font-weight: 800;
      margin: 0;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
      letter-spacing: -1px;
    }
    header p {
      font-size: 1.4rem;
      margin: 1rem 0 0;
      opacity: 0.9;
      font-weight: 400;
    }
    nav {
      background: rgba(26, 26, 26, 0.95);
      backdrop-filter: blur(10px);
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      padding: 1rem;
      gap: 2rem;
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: 0 2px 15px rgba(0,0,0,0.1);
    }
    nav a {
      color: #eee;
      text-decoration: none;
      font-weight: 600;
      transition: all 0.3s ease;
      padding: 0.5rem 1rem;
      border-radius: 25px;
    }
    nav a:hover {
      color: #26d0ce;
      background: rgba(255,255,255,0.1);
      transform: translateY(-2px);
    }
    .hero {
      background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b') no-repeat center center/cover;
      color: white;
      text-align: center;
      padding: 8rem 2rem;
      animation: fadeIn 2s ease-out;
      position: relative;
    }
    .hero h2 {
      font-size: 3rem;
      font-weight: 800;
      margin: 0;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
    }
    .hero p {
      font-size: 1.4rem;
      margin-top: 1.5rem;
      opacity: 0.95;
      max-width: 800px;
      margin-left: auto;
      margin-right: auto;
    }
    .section {
      max-width: 1200px;
      margin: auto;
      padding: 6rem 2rem;
      animation: slideUp 1s ease-out;
      position: relative;
    }
    .section::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(26, 41, 128, 0.2), transparent);
    }
    .section h3 {
      font-size: 2.5rem;
      font-weight: 700;
      color: #1a2980;
      margin-bottom: 3rem;
      text-align: center;
      position: relative;
    }
    .section h3::after {
      content: '';
      display: block;
      width: 60px;
      height: 4px;
      background: linear-gradient(90deg, #1a2980, #26d0ce);
      margin: 1rem auto 0;
      border-radius: 2px;
    }
    .product-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 2.5rem;
      margin-top: 3rem;
    }
    .product-card {
      background: white;
      border-radius: 16px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.08);
      overflow: hidden;
      transition: all 0.4s ease;
    }
    .product-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 15px 40px rgba(0,0,0,0.12);
    }
    .product-card img {
      width: 100%;
      height: 280px;
      object-fit: cover;
      transition: transform 0.4s ease;
    }
    .product-card:hover img {
      transform: scale(1.05);
    }
    .product-card .info {
      padding: 2rem;
      text-align: center;
    }
    .product-card h4 {
      font-size: 1.3rem;
      margin: 0 0 0.75rem 0;
      color: #333;
    }
    .product-card .price {
      font-size: 1.6rem;
      font-weight: 700;
      color: #1a2980;
      margin: 0 0 1.5rem 0;
    }
    .product-card a {
      display: inline-block;
      padding: 0.8rem 2rem;
      border-radius: 30px;
      background: linear-gradient(135deg, #1a2980, #26d0ce);
      color: white;
      font-weight: 600;
      text-decoration: none;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(26, 41, 128, 0.2);
    }
    .product-card a:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(26, 41, 128, 0.3);
    }
    .tips-section {
      background: linear-gradient(135deg, #f6f9fc, #eef2f7);
      padding: 6rem 2rem;
    }
    .tips-section h3 {
      color: #1a2980;
      text-shadow: none;
    }
    .tips-section ul {
      list-style: none;
      padding: 0;
      max-width: 800px;
      margin: 3rem auto 0;
    }
    .tips-section li {
      background: white;
      border-left: 4px solid #26d0ce;
      border-radius: 12px;
      padding: 1.5rem 2rem;
      margin-bottom: 1.5rem;
      box-shadow: 0 4px 15px rgba(0,0,0,0.05);
      transition: all 0.3s ease;
      position: relative;
      font-size: 1.1rem;
      line-height: 1.6;
    }
    .tips-section li:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 25px rgba(0,0,0,0.08);
    }
    footer {
      background: #1a1a1a;
      color: white;
      text-align: center;
      padding: 3rem 1rem;
      margin-top: 4rem;
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    @keyframes slideUp {
      from { transform: translateY(50px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }
    @keyframes popIn {
      0% { transform: scale(0.9); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }

    @keyframes pulse {
      0% { box-shadow: 0 0 0 0 rgba(0, 119, 204, 0.4); }
      70% { box-shadow: 0 0 0 10px rgba(0, 119, 204, 0); }
      100% { box-shadow: 0 0 0 0 rgba(0, 119, 204, 0); }
    }

    @media (max-width: 600px) {
      .hero h2 {
        font-size: 2rem;
      }
      .hero p {
        font-size: 1rem;
      }
    }
    .cta-button {
      display: inline-block;
      padding: 1rem 2.5rem;
      background: white;
      color: #1a2980;
      text-decoration: none;
      border-radius: 30px;
      font-weight: 600;
      margin-top: 2rem;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }
    .cta-button:hover {
      transform: translateY(-3px);
      box-shadow: 0 6px 20px rgba(0,0,0,0.15);
    }
    .stats-container {
      display: flex;
      justify-content: center;
      gap: 4rem;
      margin-top: 3rem;
      flex-wrap: wrap;
    }
    .stat-item {
      text-align: center;
    }
    .stat-number {
      font-size: 2.5rem;
      font-weight: 800;
      color: white;
      margin: 0;
    }
    .stat-label {
      font-size: 1rem;
      opacity: 0.9;
      margin: 0.5rem 0 0;
    }
    .product-features {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
      margin-top: 3rem;
    }
    .feature-item {
      text-align: center;
      padding: 2rem;
      background: white;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.05);
      transition: all 0.3s ease;
    }
    .feature-item:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 25px rgba(0,0,0,0.1);
    }
    .feature-icon {
      font-size: 2.5rem;
      color: #1a2980;
      margin-bottom: 1rem;
    }
    .testimonials {
      background: linear-gradient(135deg, #f6f9fc, #eef2f7);
      padding: 4rem 0;
      margin-top: 4rem;
    }
    .testimonial-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 2rem;
    }
    .testimonial-card {
      background: white;
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.05);
      position: relative;
    }
    .testimonial-card::before {
      content: '"';
      position: absolute;
      top: 1rem;
      left: 1.5rem;
      font-size: 4rem;
      color: rgba(26, 41, 128, 0.1);
      font-family: serif;
    }
    .testimonial-text {
      font-style: italic;
      margin-bottom: 1.5rem;
      line-height: 1.6;
    }
    .testimonial-author {
      font-weight: 600;
      color: #1a2980;
    }
    .newsletter-section {
      background: linear-gradient(135deg, #1a2980, #26d0ce);
      color: white;
      padding: 4rem 2rem;
      text-align: center;
      margin-top: 4rem;
    }
    .newsletter-form {
      max-width: 500px;
      margin: 2rem auto 0;
      display: flex;
      gap: 1rem;
    }
    .newsletter-input {
      flex: 1;
      padding: 1rem 1.5rem;
      border: none;
      border-radius: 30px;
      font-size: 1rem;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }
    .newsletter-button {
      padding: 1rem 2rem;
      background: white;
      color: #1a2980;
      border: none;
      border-radius: 30px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    .newsletter-button:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>
  <header>
    <h1>The Fuel Factor</h1>
    <p>Your trusted source for health, fitness & supplement picks</p>
    <a href="#products" class="cta-button">Explore Products</a>
    <div class="stats-container">
      <div class="stat-item">
        <p class="stat-number">10K+</p>
        <p class="stat-label">Happy Customers</p>
      </div>
      <div class="stat-item">
        <p class="stat-number">500+</p>
        <p class="stat-label">Products</p>
      </div>
      <div class="stat-item">
        <p class="stat-number">98%</p>
        <p class="stat-label">Satisfaction Rate</p>
      </div>
    </div>
  </header>
  <nav>
    <a href="#">Home</a>
    <a href="#products">Products</a>
    <a href="#about">About</a>
    <a href="#tips">Tips</a>
  </nav>
  <section class="hero">
    <div style="background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b') no-repeat center center/cover; padding: 6rem 2rem; color: white; text-align: center;">
      <h2 style="font-size: 2.75rem; font-weight: 800; margin: 0;">Elevate Your Health Game</h2>
      <p style="font-size: 1.2rem; margin-top: 1rem; opacity: 0.95;">Curated supplements, workout gear, and wellness picks — all in one place.</p>
    </div>
  </section>
  <section class="section" id="products" style="background: linear-gradient(135deg, #f0f9ff, #e0f7fa); padding: 4rem 2rem; text-align: center;">
  <h3 style="font-size: 2rem; font-weight: 700; color: #0077cc; margin-bottom: 2rem;">Featured Products</h3>
  <div class="product-grid" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 2rem; max-width: 1000px; margin: 0 auto;">
    <div style="background: #fff; border-radius: 12px; overflow: hidden; border-left: 5px solid #00bcd4; box-shadow: 0 6px 18px rgba(0,0,0,0.06); transition: transform 0.3s ease; text-align: center;" onmouseover="this.style.transform='translateY(-5px)'" onmouseout="this.style.transform='none'">
      <a href="#"><img src="https://images.unsplash.com/photo-1600189897281-77f3dd3d9956" alt="Whey Protein Stock Image" style="width: 100%; aspect-ratio: 1 / 1; height: 320px; object-fit: cover;"></a>
      <div style="padding: 1.5rem;">
        <h4 style="margin: 0 0 0.5rem 0; font-size: 1.2rem; color: #333;">Premium Whey Protein</h4>
        <p style="margin: 0 0 1rem 0; font-size: 1.4rem; font-weight: 600; color: #0077cc;">$49.99</p>
        <a href="#" target="_blank" style="display: inline-block; padding: 0.6rem 1.5rem; border-radius: 30px; background-color: #0077cc; color: white; font-weight: 600; text-decoration: none; transition: all 0.3s ease;" onmouseover="this.style.transform='scale(1.05)'" onmouseout="this.style.transform='scale(1)'">Buy Now</a>
      </div>
    </div>
    <div style="background: #fff; border-radius: 12px; overflow: hidden; border-left: 5px solid #00bcd4; box-shadow: 0 6px 18px rgba(0,0,0,0.06); transition: transform 0.3s ease; text-align: center;" onmouseover="this.style.transform='translateY(-5px)'" onmouseout="this.style.transform='none'">
      <a href="#"><img src="https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b" alt="Pre-Workout Supplement" style="width: 100%; aspect-ratio: 1 / 1; height: 320px; object-fit: cover;"></a>
      <div style="padding: 1.5rem;">
        <h4 style="margin: 0 0 0.5rem 0; font-size: 1.2rem; color: #333;">Energy Pre-Workout</h4>
        <p style="margin: 0 0 1rem 0; font-size: 1.4rem; font-weight: 600; color: #0077cc;">$39.99</p>
        <a href="#" target="_blank" style="display: inline-block; padding: 0.6rem 1.5rem; border-radius: 30px; background-color: #0077cc; color: white; font-weight: 600; text-decoration: none; transition: all 0.3s ease;" onmouseover="this.style.transform='scale(1.05)'" onmouseout="this.style.transform='scale(1)'">Buy Now</a>
      </div>
    </div>
    <div style="background: #fff; border-radius: 12px; overflow: hidden; border-left: 5px solid #00bcd4; box-shadow: 0 6px 18px rgba(0,0,0,0.06); transition: transform 0.3s ease; text-align: center;" onmouseover="this.style.transform='translateY(-5px)'" onmouseout="this.style.transform='none'">
      <a href="#"><img src="https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b" alt="BCAA Supplement" style="width: 100%; aspect-ratio: 1 / 1; height: 320px; object-fit: cover;"></a>
      <div style="padding: 1.5rem;">
        <h4 style="margin: 0 0 0.5rem 0; font-size: 1.2rem; color: #333;">BCAA Recovery</h4>
        <p style="margin: 0 0 1rem 0; font-size: 1.4rem; font-weight: 600; color: #0077cc;">$29.99</p>
        <a href="#" target="_blank" style="display: inline-block; padding: 0.6rem 1.5rem; border-radius: 30px; background-color: #0077cc; color: white; font-weight: 600; text-decoration: none; transition: all 0.3s ease;" onmouseover="this.style.transform='scale(1.05)'" onmouseout="this.style.transform='scale(1)'">Buy Now</a>
      </div>
    </div>
  </div>
</section>
  <section class="section" id="about">
    <h3>Why Choose The Fuel Factor?</h3>
    <div class="product-features">
      <div class="feature-item">
        <div class="feature-icon">⭐</div>
        <h4>Premium Quality</h4>
        <p>All products are carefully selected and tested for maximum effectiveness.</p>
      </div>
      <div class="feature-item">
        <div class="feature-icon">🚚</div>
        <h4>Fast Shipping</h4>
        <p>Get your supplements delivered to your doorstep within 2-3 business days.</p>
      </div>
      <div class="feature-item">
        <div class="feature-icon">💪</div>
        <h4>Expert Support</h4>
        <p>Our team of fitness experts is always ready to help you achieve your goals.</p>
      </div>
    </div>
  </section>

  <section class="testimonials">
    <h3>What Our Customers Say</h3>
    <div class="testimonial-grid">
      <div class="testimonial-card">
        <p class="testimonial-text">"The quality of supplements is outstanding. I've seen significant improvements in my performance since switching to The Fuel Factor."</p>
        <p class="testimonial-author">- Michael R., Fitness Trainer</p>
      </div>
      <div class="testimonial-card">
        <p class="testimonial-text">"Fast shipping and excellent customer service. The pre-workout supplements have been a game-changer for my training."</p>
        <p class="testimonial-author">- Sarah L., Marathon Runner</p>
      </div>
      <div class="testimonial-card">
        <p class="testimonial-text">"Best supplement store I've found. The products are authentic and the results are amazing."</p>
        <p class="testimonial-author">- David K., Bodybuilder</p>
      </div>
    </div>
  </section>

  <section class="newsletter-section">
    <h3>Stay Updated</h3>
    <p>Subscribe to our newsletter for exclusive offers and fitness tips</p>
    <form class="newsletter-form">
      <input type="email" placeholder="Enter your email" class="newsletter-input" required>
      <button type="submit" class="newsletter-button">Subscribe</button>
    </form>
  </section>
  
  <footer>
    &copy; 2025 The Fuel Factor. All rights reserved.
  </footer>
  
</body>
</html>
