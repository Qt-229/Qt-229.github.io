
    <title>Qt-229 Portfolio | GitHub Pages</title>
    <style>
        /* Reset and base styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary: #2b2d42;
            --secondary: #8d99ae;
            --accent: #ef233c;
            --light: #edf2f4;
            --dark: #1d1f2e;
            --success: #06d6a0;
            --warning: #ffd166;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background-color: var(--light);
            padding-top: 60px;
        }
        
        /* Skip to Main Content link */
        .skip-link {
            position: absolute;
            top: -40px;
            left: 0;
            background: var(--accent);
            color: white;
            padding: 10px;
            z-index: 100;
            text-decoration: none;
            border-radius: 0 0 5px 0;
            transition: top 0.3s;
        }
        
        .skip-link:focus {
            top: 0;
            outline: 3px solid var(--warning);
        }
        
        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: var(--primary);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
            z-index: 99;
        }
        
        .logo {
            color: white;
            font-weight: bold;
            font-size: 1.5rem;
            text-decoration: none;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 20px;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            padding: 10px 15px;
            border-radius: 4px;
            transition: all 0.3s;
            position: relative;
        }
        
        .nav-links a:hover {
            background: var(--accent);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 3px;
            background: var(--warning);
            transition: width 0.3s;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        /* Main content */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .hero {
            text-align: center;
            padding: 50px 20px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--dark) 100%);
            color: white;
            border-radius: 10px;
            margin-bottom: 40px;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 30px;
        }
        
        .btn {
            display: inline-block;
            background: var(--accent);
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .btn:hover {
            background: #d90429;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        /* Grid section */
        .section-title {
            text-align: center;
            margin: 40px 0;
            font-size: 2rem;
            color: var(--primary);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--accent);
            margin: 10px auto;
            border-radius: 2px;
        }
        
        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }
        
        .card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }
        
        .card-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-bottom: 5px solid var(--accent);
        }
        
        .card-content {
            padding: 20px;
        }
        
        .card h3 {
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        /* Flex gallery */
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin-bottom: 50px;
        }
        
        .gallery-item {
            width: 200px;
            height: 200px;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            transition: all 0.3s;
            position: relative;
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
            border: 3px solid var(--light);
            padding: 5px;
            border-radius: 10px;
            background: white;
        }
        
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        
        .gallery-item:hover {
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        
        .gallery-item:nth-child(odd) {
            border-radius: 50% 10px 10px 10px;
        }
        
        .gallery-item:nth-child(even) {
            border-radius: 10px 10px 50% 10px;
        }
        
        /* Features section */
        .features {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            margin-bottom: 50px;
        }
        
        .feature {
            flex: 0 0 calc(33.333% - 20px);
            margin-bottom: 30px;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            text-align: center;
            transition: all 0.3s;
        }
        
        .feature:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        
        .feature i {
            font-size: 2.5rem;
            color: var(--accent);
            margin-bottom: 15px;
        }
        
        .feature h3 {
            margin-bottom: 15px;
            color: var(--primary);
        }
        
        /* Footer */
        footer {
            background: var(--primary);
            color: white;
            padding: 40px 0 20px;
            margin-top: 50px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .footer-section h3 {
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-section h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background: var(--accent);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: var(--light);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: var(--accent);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            margin-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        
        /* Responsive design */
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                padding: 15px;
            }
            
            .nav-links {
                margin-top: 15px;
            }
            
            .nav-links li {
                margin: 0 10px;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .feature {
                flex: 0 0 100%;
            }
        }
        
        @media (max-width: 480px) {
            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .nav-links li {
                margin: 5px;
            }
            
            .hero {
                padding: 30px 15px;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .gallery-item {
                width: 150px;
                height: 150px;
            }
        }
    </style>
</head>
    <!-- Skip to Main Content Link -->
    <a href="#main-content" class="skip-link">Skip to Main Content</a>
    
    <!-- Navigation -->
    <nav class="navbar">
        <a href="#" class="logo">Qt-229</a>
        <ul class="nav-links">
            <li><a href="#">Home</a></li>
            <li><a href="#portfolio">Portfolio</a></li>
            <li><a href="#gallery">Gallery</a></li>
            <li><a href="#features">Features</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
    
    <main id="main-content" class="container">
        <!-- Hero Section -->
        <section class="hero">
            <h1>Welcome to Qt-229 GitHub Pages</h1>
            <p>A showcase of accessible web design with CSS styling techniques including flexbox, grid, and responsive layouts.</p>
            <a href="#portfolio" class="btn">View Portfolio</a>
        </section>
        
        <!-- Portfolio Grid -->
        <h2 class="section-title" id="portfolio">Portfolio Projects</h2>
        <div class="grid-container">
            <div class="card">
                <img src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=600&h=400&q=80" alt="Coding Project" class="card-img">
                <div class="card-content">
                    <h3>Web Development</h3>
                    <p>Modern responsive website built with HTML5, CSS3 and JavaScript.</p>
                </div>
            </div>
            
            <div class="card">
                <img src="https://images.unsplash.com/photo-1551650975-87deedd944c3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=600&h=400&q=80" alt="Mobile App" class="card-img">
                <div class="card-content">
                    <h3>Mobile Application</h3>
                    <p>Cross-platform mobile app developed with React Native.</p>
                </div>
            </div>
            
            <div class="card">
                <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=600&h=400&q=80" alt="Data Visualization" class="card-img">
                <div class="card-content">
                    <h3>Data Visualization</h3>
                    <p>Interactive data dashboards using D3.js and Chart.js.</p>
                </div>
            </div>
        </div>
        
        <!-- Image Gallery -->
        <h2 class="section-title" id="gallery">Photo Gallery</h2>
        <div class="gallery">
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1501854140801-50d01698950b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=400&h=400&q=80" alt="Mountain landscape">
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1475924156734-496f6cac6ec1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=400&h=400&q=80" alt="Ocean view">
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1469474968028-56623f02e42e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=400&h=400&q=80" alt="Forest scenery">
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1505142468610-359e7d316be0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=400&h=400&q=80" alt="Mountain lake">
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1418065460487-3e41a6c84dc5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=400&h=400&q=80" alt="Tropical forest">
            </div>
        </div>
        
        <!-- Features Section -->
        <h2 class="section-title" id="features">Key Features</h2>
        <div class="features">
            <div class="feature">
                <i>🔍</i>
                <h3>Accessibility First</h3>
                <p>Designed with accessibility in mind, including skip links, proper contrast, and semantic HTML.</p>
            </div>
            
            <div class="feature">
                <i>📱</i>
                <h3>Fully Responsive</h3>
                <p>Adapts to all screen sizes from mobile to desktop with a flexible grid system.</p>
            </div>
            
            <div class="feature">
                <i>🎨</i>
                <h3>Modern Design</h3>
                <p>Clean aesthetics with thoughtful typography, spacing, and color choices.</p>
            </div>
        </div>
    </main>
    
    <!-- Footer -->
    <footer id="contact">
        <div class="footer-content">
            <div class="footer-section">
                <h3>About Qt-229</h3>
                <p>This project demonstrates modern web development techniques with a focus on accessibility and responsive design.</p>
            </div>
            
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul class="footer-links">
                    <li><a href="#">Home</a></li>
                    <li><a href="#portfolio">Portfolio</a></li>
                    <li><a href="#gallery">Gallery</a></li>
                    <li><a href="#features">Features</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Contact</h3>
                <ul class="footer-links">
                    <li>Email: contact@qt-229.github.io</li>
                    <li>GitHub: github.com/Qt-229</li>
                </ul>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2023 Qt-229 GitHub Pages. All rights reserved.</p>
        </div>
    </footer>
</html>
