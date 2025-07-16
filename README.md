<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Travel Explorer | CSS Showcase</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Base styles and reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary: #2c6e49;
            --secondary: #4c956c;
            --accent: #fefee3;
            --light: #fefee3;
            --dark: #1d3557;
            --text: #333;
            --shadow: 0 4px 6px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text);
            background-color: #f9f9f9;
        }
        
        /* Skip to main content link */
        .skip-link {
            position: absolute;
            top: -40px;
            left: 0;
            background: var(--dark);
            color: white;
            padding: 8px;
            z-index: 100;
            transition: top 0.3s;
        }
        
        .skip-link:focus {
            top: 0;
        }
        
        /* Header and navigation */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 99;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            color: var(--accent);
        }
        
        .main-nav {
            display: flex;
            list-style: none;
        }
        
        .main-nav li {
            margin-left: 25px;
        }
        
        .main-nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            padding: 5px 0;
            position: relative;
            transition: var(--transition);
        }
        
        .main-nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: var(--transition);
        }
        
        .main-nav a:hover::after {
            width: 100%;
        }
        
        .main-nav a:hover {
            color: var(--accent);
        }
        
        /* Hero section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1503220317375-aaad61436b1b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            height: 80vh;
            display: flex;
            align-items: center;
            text-align: center;
            color: white;
        }
        
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 0 2px 4px rgba(0,0,0,0.5);
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .btn {
            display: inline-block;
            background: var(--primary);
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border: 2px solid var(--primary);
        }
        
        .btn:hover {
            background: transparent;
            color: white;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        
        /* Section styling */
        section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            color: var(--dark);
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            position: relative;
            display: inline-block;
            padding-bottom: 15px;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--primary);
            border-radius: 2px;
        }
        
        /* Featured destinations - Grid layout */
        .destinations-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .destination-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .destination-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }
        
        .card-img {
            height: 200px;
            width: 100%;
            object-fit: cover;
            display: block;
        }
        
        .card-content {
            padding: 20px;
        }
        
        .card-content h3 {
            margin-bottom: 10px;
            color: var(--dark);
        }
        
        /* Popular tours - Flex layout */
        .tours-container {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            justify-content: center;
        }
        
        .tour-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            flex: 1 1 300px;
            max-width: 350px;
            transition: var(--transition);
        }
        
        .tour-card:hover {
            transform: scale(1.03);
        }
        
        .tour-card:nth-child(even) .card-img {
            border-radius: 50% 20% / 10% 40%;
        }
        
        .tour-card:nth-child(odd) .card-img {
            border-radius: 20% 40% 60% 40%;
        }
        
        /* Gallery section - Grid layout with images */
        .gallery {
            background-color: var(--light);
        }
        
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .gallery-item {
            border-radius: 10px;
            overflow: hidden;
            height: 250px;
            position: relative;
            box-shadow: var(--shadow);
        }
        
        .gallery-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            transition: var(--transition);
        }
        
        .gallery-item:hover .gallery-img {
            transform: scale(1.1);
        }
        
        .gallery-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background: rgba(0,0,0,0.7);
            color: white;
            padding: 10px;
            transform: translateY(100%);
            transition: var(--transition);
        }
        
        .gallery-item:hover .gallery-caption {
            transform: translateY(0);
        }
        
        /* Testimonials */
        .testimonials {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            text-align: center;
        }
        
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .testimonial {
            background: rgba(255,255,255,0.1);
            padding: 30px;
            border-radius: 10px;
            backdrop-filter: blur(5px);
        }
        
        .testimonial img {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            object-fit: cover;
            margin: 0 auto 20px;
            border: 3px solid var(--accent);
        }
        
        .testimonial p {
            font-style: italic;
            margin-bottom: 20px;
        }
        
        /* Contact section */
        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 15px;
        }
        
        .contact-item i {
            font-size: 1.5rem;
            color: var(--primary);
            min-width: 30px;
        }
        
        .contact-form .form-group {
            margin-bottom: 20px;
        }
        
        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: inherit;
            font-size: 1rem;
            transition: var(--transition);
        }
        
        .contact-form input:focus,
        .contact-form textarea:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(44, 110, 73, 0.2);
        }
        
        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 40px 0 20px;
        }
        
        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .footer-logo {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }
        
        .footer-links h3,
        .footer-newsletter h3 {
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-links h3::after,
        .footer-newsletter h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 3px;
            background: var(--primary);
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #ddd;
            text-decoration: none;
            transition: var(--transition);
        }
        
        .footer-links a:hover {
            color: var(--accent);
            padding-left: 5px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            color: white;
            transition: var(--transition);
        }
        
        .social-links a:hover {
            background: var(--primary);
            transform: translateY(-5px);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        
        /* Responsive adjustments */
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
                gap: 20px;
            }
            
            .main-nav {
                width: 100%;
                justify-content: center;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
        }
        
        @media (max-width: 480px) {
            .main-nav {
                flex-direction: column;
                align-items: center;
                gap: 10px;
            }
            
            .main-nav li {
                margin-left: 0;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Skip to main content link -->
    <a href="#main-content" class="skip-link">Skip to Main Content</a>
    
    <!-- Header with navigation -->
    <header>
        <div class="container nav-container">
            <div class="logo">
                <i class="fas fa-map-marked-alt"></i>
                TravelExplorer
            </div>
            <nav>
                <ul class="main-nav">
                    <li><a href="#"><i class="fas fa-home"></i> Home</a></li>
                    <li><a href="#destinations"><i class="fas fa-map-marker-alt"></i> Destinations</a></li>
                    <li><a href="#tours"><i class="fas fa-suitcase-rolling"></i> Tours</a></li>
                    <li><a href="#gallery"><i class="fas fa-images"></i> Gallery</a></li>
                    <li><a href="#contact"><i class="fas fa-envelope"></i> Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>
    
    <!-- Hero Section -->
    <section class="hero">
        <div class="container hero-content">
            <h1>Discover Amazing Places</h1>
            <p>Explore the world with our hand-picked destinations and unforgettable travel experiences</p>
            <a href="#destinations" class="btn">Explore Destinations</a>
        </div>
    </section>
    
    <!-- Main Content -->
    <main id="main-content">
        <!-- Featured Destinations Section -->
        <section id="destinations" class="destinations">
            <div class="container">
                <div class="section-title">
                    <h2>Featured Destinations</h2>
                </div>
                <div class="destinations-grid">
                    <div class="destination-card">
                        <img src="https://images.unsplash.com/photo-1566073771259-6a8506099945?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Santorini, Greece" class="card-img">
                        <div class="card-content">
                            <h3>Santorini, Greece</h3>
                            <p>Explore the iconic white-washed buildings and breathtaking sunsets of this beautiful Greek island.</p>
                            <a href="#" class="btn">View Details</a>
                        </div>
                    </div>
                    
                    <div class="destination-card">
                        <img src="https://images.unsplash.com/photo-1565967511849-76a60a516170?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Kyoto, Japan" class="card-img">
                        <div class="card-content">
                            <h3>Kyoto, Japan</h3>
                            <p>Discover ancient temples, traditional gardens, and the rich cultural heritage of Japan.</p>
                            <a href="#" class="btn">View Details</a>
                        </div>
                    </div>
                    
                    <div class="destination-card">
                        <img src="https://images.unsplash.com/photo-1506970845247-4db2a5e87b4c?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Banff, Canada" class="card-img">
                        <div class="card-content">
                            <h3>Banff, Canada</h3>
                            <p>Experience the stunning beauty of the Canadian Rockies and pristine glacial lakes.</p>
                            <a href="#" class="btn">View Details</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Popular Tours Section -->
        <section id="tours" class="tours">
            <div class="container">
                <div class="section-title">
                    <h2>Popular Tours</h2>
                </div>
                <div class="tours-container">
                    <div class="tour-card">
                        <img src="https://images.unsplash.com/photo-1551632811-561732d1e306?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Amazon Adventure" class="card-img">
                        <div class="card-content">
                            <h3>Amazon Adventure</h3>
                            <p>7-day jungle expedition exploring the biodiversity of the Amazon rainforest.</p>
                            <p class="price">From $1,299</p>
                        </div>
                    </div>
                    
                    <div class="tour-card">
                        <img src="https://images.unsplash.com/photo-1543429776-2782fc586c3c?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="European Highlights" class="card-img">
                        <div class="card-content">
                            <h3>European Highlights</h3>
                            <p>14-day tour through Paris, Rome, Barcelona, and Amsterdam.</p>
                            <p class="price">From $2,499</p>
                        </div>
                    </div>
                    
                    <div class="tour-card">
                        <img src="https://images.unsplash.com/photo-1565967511849-76a60a516170?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Asian Discovery" class="card-img">
                        <div class="card-content">
                            <h3>Asian Discovery</h3>
                            <p>21-day journey through Thailand, Vietnam, Cambodia, and Laos.</p>
                            <p class="price">From $3,199</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Gallery Section -->
        <section id="gallery" class="gallery">
            <div class="container">
                <div class="section-title">
                    <h2>Travel Gallery</h2>
                </div>
                <div class="gallery-grid">
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1501555088652-021faa106b9b?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Northern Lights" class="gallery-img">
                        <div class="gallery-caption">Northern Lights, Iceland</div>
                    </div>
                    
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1526481280693-3bfa7568e0f3?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Safari Adventure" class="gallery-img">
                        <div class="gallery-caption">Safari Adventure, Kenya</div>
                    </div>
                    
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1534008897995-27a23e859048?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Machu Picchu" class="gallery-img">
                        <div class="gallery-caption">Machu Picchu, Peru</div>
                    </div>
                    
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1516483638261-f4dbaf036963?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Great Barrier Reef" class="gallery-img">
                        <div class="gallery-caption">Great Barrier Reef, Australia</div>
                    </div>
                    
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1543429776-2782fc586c3c?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Venice Canals" class="gallery-img">
                        <div class="gallery-caption">Venice Canals, Italy</div>
                    </div>
                    
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1503220317375-aaad61436b1b?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Taj Mahal" class="gallery-img">
                        <div class="gallery-caption">Taj Mahal, India</div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Testimonials Section -->
        <section class="testimonials">
            <div class="container">
                <div class="section-title">
                    <h2>What Travelers Say</h2>
                </div>
                <div class="testimonials-grid">
                    <div class="testimonial">
                        <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="Sarah M.">
                        <p>"The European Highlights tour exceeded all my expectations. The itinerary was perfectly balanced between sightseeing and free time."</p>
                        <p><strong>Sarah M.</strong></p>
                    </div>
                    
                    <div class="testimonial">
                        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="James K.">
                        <p>"Our Amazon Adventure was truly life-changing. The guides were knowledgeable, and we saw wildlife I never imagined I'd see in person."</p>
                        <p><strong>James K.</strong></p>
                    </div>
                    
                    <div class="testimonial">
                        <img src="https://randomuser.me/api/portraits/women/68.jpg" alt="Lisa T.">
                        <p>"Booking with TravelExplorer was seamless. Their attention to detail and customer service made our trip stress-free and memorable."</p>
                        <p><strong>Lisa T.</strong></p>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Contact Section -->
        <section id="contact" class="contact">
            <div class="container">
                <div class="section-title">
                    <h2>Contact Us</h2>
                </div>
                <div class="contact-container">
                    <div class="contact-info">
                        <h3>Get In Touch</h3>
                        <div class="contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <div>
                                <h4>Address</h4>
                                <p>123 Travel Street, Wanderlust City, WC 10001</p>
                            </div>
                        </div>
                        
                        <div class="contact-item">
                            <i class="fas fa-phone"></i>
                            <div>
                                <h4>Phone</h4>
                                <p>+1 (555) 123-4567</p>
                            </div>
                        </div>
                        
                        <div class="contact-item">
                            <i class="fas fa-envelope"></i>
                            <div>
                                <h4>Email</h4>
                                <p>info@travelexplorer.com</p>
                            </div>
                        </div>
                        
                        <div class="contact-item">
                            <i class="fas fa-clock"></i>
                            <div>
                                <h4>Business Hours</h4>
                                <p>Monday - Friday: 9AM - 6PM</p>
                                <p>Saturday: 10AM - 4PM</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="contact-form">
                        <h3>Send a Message</h3>
                        <form>
                            <div class="form-group">
                                <input type="text" placeholder="Your Name" required>
                            </div>
                            
                            <div class="form-group">
                                <input type="email" placeholder="Your Email" required>
                            </div>
                            
                            <div class="form-group">
                                <input type="text" placeholder="Subject">
                            </div>
                            
                            <div class="form-group">
                                <textarea placeholder="Your Message" rows="5" required></textarea>
                            </div>
                            
                            <button type="submit" class="btn">Send Message</button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </main>
    
    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-container">
                <div class="footer-about">
                    <div class="footer-logo">
                        <i class="fas fa-map-marked-alt"></i>
                        TravelExplorer
                    </div>
                    <p>Your trusted partner for unforgettable travel experiences around the globe.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-pinterest"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                
                <div class="footer-links">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#destinations">Destinations</a></li>
                        <li><a href="#tours">Tours</a></li>
                        <li><a href="#gallery">Gallery</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                
                <div class="footer-links">
                    <h3>Popular Destinations</h3>
                    <ul>
                        <li><a href="#">Bali, Indonesia</a></li>
                        <li><a href="#">Santorini, Greece</a></li>
                        <li><a href="#">Kyoto, Japan</a></li>
                        <li><a href="#">Paris, France</a></li>
                        <li><a href="#">Banff, Canada</a></li>
                    </ul>
                </div>
                
                <div class="footer-newsletter">
                    <h3>Newsletter</h3>
                    <p>Subscribe for travel tips and exclusive deals</p>
                    <form>
                        <div class="form-group">
                            <input type="email" placeholder="Your Email" required>
                        </div>
                        <button type="submit" class="btn">Subscribe</button>
                    </form>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2023 TravelExplorer. All rights reserved. | Designed with <i class="fas fa-heart"></i> for travel enthusiasts</p>
            </div>
        </div>
    </footer>
</body>
</html>
