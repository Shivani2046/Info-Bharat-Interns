<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mamta Bhojnalaya - Authentic Indian Cuisine</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(139, 69, 19, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        .navbar.scrolled {
            background: rgba(139, 69, 19, 0.98);
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: #FFD700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #FFD700;
            transform: translateY(-2px);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #FFD700;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .bar {
            width: 25px;
            height: 3px;
            background: white;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, #8B4513 0%, #D2B48C 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="20" cy="20" r="1" fill="%23fff" opacity="0.1"/><circle cx="80" cy="40" r="1.5" fill="%23fff" opacity="0.08"/><circle cx="40" cy="70" r="1" fill="%23fff" opacity="0.1"/><circle cx="60" cy="90" r="1.2" fill="%23fff" opacity="0.09"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .hero-content {
            z-index: 2;
            max-width: 800px;
            padding: 2rem;
        }

        .hero h1 {
            font-size: 4rem;
            color: white;
            margin-bottom: 1rem;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.3);
            animation: slideInUp 1s ease;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: #FFD700;
            margin-bottom: 2rem;
            animation: slideInUp 1s ease 0.3s both;
        }

        .hero-description {
            font-size: 1.2rem;
            color: white;
            margin-bottom: 3rem;
            opacity: 0.9;
            animation: slideInUp 1s ease 0.6s both;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: slideInUp 1s ease 0.9s both;
        }

        .btn {
            padding: 15px 30px;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(45deg, #FFD700, #FFA500);
            color: #8B4513;
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255, 215, 0, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn-secondary:hover {
            background: white;
            color: #8B4513;
            transform: translateY(-3px);
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Sections */
        .section {
            padding: 5rem 0;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            color: #8B4513;
            margin-bottom: 1rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(45deg, #FFD700, #FFA500);
            border-radius: 2px;
        }

        .section-subtitle {
            text-align: center;
            font-size: 1.2rem;
            color: #666;
            margin-bottom: 4rem;
        }

        /* About Section */
        .about {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #555;
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        .about-image {
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        .about-image img {
            width: 100%;
            height: 400px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .about-image:hover img {
            transform: scale(1.05);
        }

        /* Menu Section */
        .menu {
            background: white;
        }

        .menu-categories {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }

        .category-btn {
            padding: 10px 25px;
            border: 2px solid #8B4513;
            background: transparent;
            color: #8B4513;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .category-btn.active,
        .category-btn:hover {
            background: #8B4513;
            color: white;
            transform: translateY(-2px);
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .menu-item {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 1px solid #f0f0f0;
        }

        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .menu-item-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 1rem;
        }

        .menu-item-title {
            font-size: 1.3rem;
            font-weight: 600;
            color: #8B4513;
            margin-bottom: 0.5rem;
        }

        .menu-item-price {
            font-size: 1.4rem;
            font-weight: bold;
            color: #FFD700;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }

        .menu-item-description {
            color: #666;
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .menu-item-tags {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
        }

        .tag {
            padding: 4px 12px;
            background: #f8f9fa;
            color: #8B4513;
            border-radius: 15px;
            font-size: 0.85rem;
            font-weight: 500;
        }

        .tag.veg {
            background: #d4edda;
            color: #155724;
        }

        .tag.spicy {
            background: #f8d7da;
            color: #721c24;
        }

        /* Gallery Section */
        .gallery {
            background: linear-gradient(135deg, #8B4513 0%, #A0522D 100%);
            color: white;
        }

        .gallery .section-title {
            color: white;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .gallery-item {
            position: relative;
            border-radius: 15px;
            overflow: hidden;
            aspect-ratio: 1;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, rgba(139, 69, 19, 0.8), rgba(255, 215, 0, 0.8));
            opacity: 0;
            transition: opacity 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .gallery-item:hover .gallery-overlay {
            opacity: 1;
        }

        .gallery-text {
            text-align: center;
            color: white;
            font-weight: 600;
            font-size: 1.2rem;
        }

        /* Reservation Section */
        .reservation {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
        }

        .reservation-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .reservation-form {
            background: white;
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #8B4513;
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 15px;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #8B4513;
        }

        .reservation-info {
            padding: 2rem;
        }

        .info-item {
            display: flex;
            align-items: center;
            margin-bottom: 2rem;
            padding: 1.5rem;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        .info-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(45deg, #8B4513, #A0522D);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
            margin-right: 1rem;
        }

        /* Footer */
        .footer {
            background: #222;
            color: white;
            padding: 3rem 0 1rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            color: #FFD700;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .footer-section p,
        .footer-section a {
            color: #ccc;
            text-decoration: none;
            line-height: 1.8;
        }

        .footer-section a:hover {
            color: #FFD700;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-link {
            width: 40px;
            height: 40px;
            background: #8B4513;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            background: #FFD700;
            color: #8B4513;
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid #444;
            color: #888;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu {
                display: flex;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-subtitle {
                font-size: 1.2rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .about-content,
            .reservation-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .menu-grid {
                grid-template-columns: 1fr;
            }

            .gallery-grid {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            }
        }

        /* Loading Animation */
        .loading {
            display: none;
            text-align: center;
            padding: 2rem;
        }

        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid #f3f3f3;
            border-top: 4px solid #8B4513;
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin: 0 auto 1rem;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Success Message */
        .success-message {
            display: none;
            background: #d4edda;
            color: #155724;
            padding: 1rem;
            border-radius: 10px;
            margin-top: 1rem;
            border: 1px solid #c3e6cb;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            backdrop-filter: blur(5px);
        }

        .modal-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 2rem;
            border-radius: 20px;
            max-width: 500px;
            width: 90%;
            text-align: center;
        }

        .modal-close {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 2rem;
            cursor: pointer;
            color: #8B4513;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <div class="logo">🍽️ Mamta Bhojnalaya</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#gallery">Gallery</a></li>
                <li><a href="#reservation">Reserve</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="mobile-menu" id="mobile-menu">
                <div class="bar"></div>
                <div class="bar"></div>
                <div class="bar"></div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Welcome to Mamta Bhojnalaya</h1>
            <p class="hero-subtitle">Authentic Indian Flavors, Crafted with Love</p>
            <p class="hero-description">Experience the rich heritage of Indian cuisine with our carefully curated dishes, prepared using traditional recipes passed down through generations.</p>
            <div class="cta-buttons">
                <a href="#menu" class="btn btn-primary">Explore Menu</a>
                <a href="#reservation" class="btn btn-secondary">Make Reservation</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section about">
        <div class="container">
            <h2 class="section-title">About Mamta Bhojnalaya</h2>
            <p class="section-subtitle">Where tradition meets taste</p>
            <div class="about-content">
                <div class="about-text">
                    <p>Founded in 1985, Mamta Bhojnalaya has been serving authentic Indian cuisine to food lovers for over three decades. Our restaurant is named after our founder's mother, Mamta, whose recipes form the heart of our menu.</p>
                    <p>We believe in using only the freshest ingredients, traditional cooking methods, and time-honored spice blends to create dishes that transport you to the vibrant streets of India. Every meal is prepared with the same love and care that Mamta put into her cooking.</p>
                    <p>From our signature biryanis to our mouthwatering curries, each dish tells a story of heritage, passion, and culinary excellence. We're not just a restaurant; we're a celebration of Indian culture and hospitality.</p>
                </div>
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1585937421612-70a008356fbe?w=600&h=400&fit=crop" alt="Traditional Indian Kitchen" />
                </div>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section id="menu" class="section menu">
        <div class="container">
            <h2 class="section-title">Our Menu</h2>
            <p class="section-subtitle">Discover our delicious offerings</p>
            
            <div class="menu-categories">
                <button class="category-btn active" data-category="all">All Items</button>
                <button class="category-btn" data-category="appetizers">Appetizers</button>
                <button class="category-btn" data-category="mains">Main Course</button>
                <button class="category-btn" data-category="biryani">Biryani</button>
                <button class="category-btn" data-category="desserts">Desserts</button>
                <button class="category-btn" data-category="beverages">Beverages</button>
            </div>

            <div class="menu-grid" id="menu-grid">
                <!-- Menu items will be populated by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="section gallery">
        <div class="container">
            <h2 class="section-title">Gallery</h2>
            <p class="section-subtitle">A visual feast of our culinary artistry</p>
            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1565557623262-b51c2513a641?w=400&h=400&fit=crop" alt="Delicious Biryani" />
                    <div class="gallery-overlay">
                        <div class="gallery-text">Aromatic Biryani</div>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1603894584373-5ac82b2ae398?w=400&h=400&fit=crop" alt="Traditional Thali" />
                    <div class="gallery-overlay">
                        <div class="gallery-text">Complete Thali</div>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1585937421612-70a008356fbe?w=400&h=400&fit=crop" alt="Restaurant Ambiance" />
                    <div class="gallery-overlay">
                        <div class="gallery-text">Warm Ambiance</div>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1606491956689-2ea866880c84?w=400&h=400&fit=crop" alt="Fresh Naan" />
                    <div class="gallery-overlay">
                        <div class="gallery-text">Fresh Breads</div>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1567188040759-fb8a883dc6d8?w=400&h=400&fit=crop" alt="Spicy Curry" />
                    <div class="gallery-overlay">
                        <div class="gallery-text">Rich Curries</div>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1601050690597-df0568f70950?w=400&h=400&fit=crop" alt="Sweet Desserts" />
                    <div class="gallery-overlay">
                        <div class="gallery-text">Sweet Endings</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Reservation Section -->
    <section id="reservation" class="section reservation">
        <div class="container">
            <h2 class="section-title">Make a Reservation</h2>
            <p class="section-subtitle">Book your table for an unforgettable dining experience</p>
            <div class="reservation-content">
                <div class="reservation-form">
                    <form id="reservation-form">
                        <div class="form-group">
                            <label for="name">Full Name</label>
                            <input type="text" id="name" name="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email Address</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Phone Number</label>
                            <input type="tel" id="phone" name="phone" required>
                        </div>
                        <div class="form-group">
                            <label for="date">Reservation Date</label>
                            <input type="date" id="date" name="date" required>
                        </div>
                        <div class="form-group">
                            <label for="time">Preferred Time</label>
                            <select id="time" name="time" required>
                                <option value="">Select Time</option>
                                <option value="12:00">12:00 PM</option>
                                <option value="12:30">12:30 PM</option>
                                <option value="13:00">1:00 PM</option>
                                <option value="13:30">1:30 PM</option>
                                <option value="19:00">7:00 PM</option>
                                <option value="19:30">7:30 PM</option>
                                <option value="20:00">8:00 PM</option>
                                <option value="20:30">8:30 PM</option>
                                <option value="21:00">9:00 PM</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="guests">Number of Guests</label>
                            <select id="guests" name="guests" required>
                                <option value="">Select Guests</option>
                                <option value="1">1 Person</option>
                                <option value="2">2 People</option>
                                <option value="3">3 People</option>
                                <option value="4">4 People</option>
                                <option value="5">5 People</option>
                                <option value="6">6 People</option>
                                <option value="7">7+ People</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="message">Special Requests</label>
                            <textarea id="message" name="message" rows="4" placeholder="Any dietary restrictions, special occasions, or requests..."></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary" style="width: 100%;">Book Table</button>
                        <div class="loading" id="loading">
                            <div class="spinner"></div>
                            <p>Processing your reservation...</p>
                        </div>
                        <div class="success-message" id="success-message">
                            <strong>Reservation Confirmed!</strong> We'll contact you shortly to confirm your booking.
                        </div>
                    </form>
                </div>
                    <div class="info-item">
                        <div class="info-icon">⏰</div>
                        <div>
                            <h4>Opening Hours</h4>
                            <p>Mon-Sun: 11:00 AM - 11:00 PM<br>Kitchen closes at 10:30 PM</p>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon">📞</div>
                        <div>
                            <h4>Contact</h4>
                            <p>Phone: +91 98765 43210<br>Email: info@mamtabhojnalaya.com</p>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon">🎉</div>
                        <div>
                            <h4>Special Events</h4>
                            <p>Private parties, corporate events,<br>and catering services available</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section" style="background: linear-gradient(135deg, #8B4513 0%, #A0522D 100%); color: white;">
        <div class="container">
            <h2 class="section-title" style="color: white;">Get In Touch</h2>
            <p class="section-subtitle" style="color: #FFD700;">We'd love to hear from you</p>
            
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 3rem; margin-top: 3rem;">
                <div>
                    <h3 style="color: #FFD700; margin-bottom: 1.5rem; font-size: 1.5rem;">Visit Us</h3>
                    <div style="background: rgba(255,255,255,0.1); padding: 2rem; border-radius: 15px; backdrop-filter: blur(10px);">
                        <p style="margin-bottom: 1rem; font-size: 1.1rem;"><strong>📍 Address:</strong></p>
                        <p style="margin-bottom: 2rem; line-height: 1.6;">123 Food Street, Sitabuldi<br>Nagpur, Maharashtra 440012<br>India</p>
                        
                        <p style="margin-bottom: 1rem; font-size: 1.1rem;"><strong>📞 Phone:</strong></p>
                        <p style="margin-bottom: 2rem;">+91 98765 43210<br>+91 98765 43211</p>
                        
                        <p style="margin-bottom: 1rem; font-size: 1.1rem;"><strong>📧 Email:</strong></p>
                        <p>info@mamtabhojnalaya.com</p>
                    </div>
                </div>
                
                <div>
                    <h3 style="color: #FFD700; margin-bottom: 1.5rem; font-size: 1.5rem;">Opening Hours</h3>
                    <div style="background: rgba(255,255,255,0.1); padding: 2rem; border-radius: 15px; backdrop-filter: blur(10px);">
                        <div style="display: flex; justify-content: space-between; margin-bottom: 1rem; padding-bottom: 1rem; border-bottom: 1px solid rgba(255,255,255,0.2);">
                            <span>Monday - Thursday</span>
                            <span>11:00 AM - 10:30 PM</span>
                        </div>
                        <div style="display: flex; justify-content: space-between; margin-bottom: 1rem; padding-bottom: 1rem; border-bottom: 1px solid rgba(255,255,255,0.2);">
                            <span>Friday - Sunday</span>
                            <span>11:00 AM - 11:00 PM</span>
                        </div>
                        <div style="display: flex; justify-content: space-between; margin-bottom: 1rem; padding-bottom: 1rem; border-bottom: 1px solid rgba(255,255,255,0.2);">
                            <span>Kitchen Closes</span>
                            <span>30 min before closing</span>
                        </div>
                        <div style="text-align: center; margin-top: 1.5rem; padding: 1rem; background: rgba(255,215,0,0.2); border-radius: 10px;">
                            <p style="color: #FFD700; font-weight: 600;">🎉 Happy Hours: 3 PM - 6 PM</p>
                            <p style="font-size: 0.9rem; margin-top: 0.5rem;">10% off on all beverages</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>🍽️ Mamta Bhojnalaya</h3>
                    <p>Serving authentic Indian cuisine with love and tradition since 1985. Every meal is a celebration of flavors, culture, and hospitality.</p>
                    <div class="social-links">
                        <a href="#" class="social-link">📘</a>
                        <a href="#" class="social-link">📷</a>
                        <a href="#" class="social-link">🐦</a>
                        <a href="#" class="social-link">📺</a>
                    </div>
                </div>
                
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <p><a href="#home">Home</a></p>
                    <p><a href="#about">About Us</a></p>
                    <p><a href="#menu">Our Menu</a></p>
                    <p><a href="#gallery">Gallery</a></p>
                    <p><a href="#reservation">Reservations</a></p>
                    <p><a href="#contact">Contact</a></p>
                </div>
                
                <div class="footer-section">
                    <h3>Services</h3>
                    <p>Dine-in Experience</p>
                    <p>Takeaway Orders</p>
                    <p>Home Delivery</p>
                    <p>Catering Services</p>
                    <p>Private Events</p>
                    <p>Corporate Parties</p>
                </div>
                
                <div class="footer-section">
                    <h3>Contact Info</h3>
                    <p>📍 123 Food Street, Sitabuldi<br>Nagpur, Maharashtra 440012</p>
                    <p>📞 +91 98765 43210</p>
                    <p>📧 info@mamtabhojnalaya.com</p>
                    <p>🕒 Mon-Sun: 11:00 AM - 11:00 PM</p>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2024 Mamta Bhojnalaya. All rights reserved. | Designed with ❤️ for food lovers</p>
            </div>
        </div>
    </footer>
