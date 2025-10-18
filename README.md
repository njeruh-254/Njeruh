<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Art Studio | Gallery & Commissions</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            line-height: 1.6;
            color: #333;
            background-color: #fafafa;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: #2c3e50;
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #e74c3c;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
            font-weight: 500;
        }

        .nav-links a:hover {
            color: #e74c3c;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), 
                        url('https://images.unsplash.com/photo-1541961017774-22349e4a1262?ixlib=rb-4.0.3') center/cover;
            color: white;
            text-align: center;
            padding: 150px 0 100px;
            margin-top: 60px;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            font-weight: 300;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .btn {
            display: inline-block;
            background: #e74c3c;
            color: white;
            padding: 15px 35px;
            text-decoration: none;
            border-radius: 30px;
            transition: all 0.3s;
            font-size: 1.1rem;
            border: 2px solid #e74c3c;
        }

        .btn:hover {
            background: transparent;
            color: #e74c3c;
        }

        /* Gallery Section */
        .gallery {
            padding: 80px 0;
            background: white;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #2c3e50;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .artwork {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .artwork:hover {
            transform: translateY(-5px);
        }

        .artwork img {
            width: 100%;
            height: 300px;
            object-fit: cover;
            transition: transform 0.3s;
        }

        .artwork:hover img {
            transform: scale(1.05);
        }

        .artwork-info {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(44, 62, 80, 0.9);
            color: white;
            padding: 1rem;
            transform: translateY(100%);
            transition: transform 0.3s;
        }

        .artwork:hover .artwork-info {
            transform: translateY(0);
        }

        /* About Section */
        .about {
            padding: 80px 0;
            background: #ecf0f1;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: #2c3e50;
        }

        .about-text p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }

        .about-image {
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .about-image img {
            width: 100%;
            height: 400px;
            object-fit: cover;
        }

        /* Services Section */
        .services {
            padding: 80px 0;
            background: white;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .service-card {
            background: #f8f9fa;
            padding: 2.5rem 2rem;
            text-align: center;
            border-radius: 10px;
            transition: all 0.3s;
            border: 1px solid #e9ecef;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
            background: white;
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .service-card h3 {
            color: #2c3e50;
            margin-bottom: 1rem;
        }

        /* Contact Section */
        .contact {
            padding: 80px 0;
            background: #2c3e50;
            color: white;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px;
            margin-bottom: 1rem;
            border: none;
            border-radius: 5px;
            font-family: inherit;
        }

        .contact-form textarea {
            height: 150px;
            resize: vertical;
        }

        .contact-info h3 {
            margin-bottom: 1.5rem;
            color: #e74c3c;
        }

        .contact-info p {
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        /* Footer */
        footer {
            background: #34495e;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin: 1rem 0;
        }

        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: #e74c3c;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                gap: 1rem;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .about-content,
            .contact-grid {
                grid-template-columns: 1fr;
            }
            
            .gallery-grid {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">ArtStudio</div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#gallery">Gallery</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h1>Transform Spaces with Unique Art</h1>
            <p>Commission original artwork that tells your story. Custom pieces created with passion and precision.</p>
            <a href="#contact" class="btn">Commission Your Piece</a>
        </div>
    </section>

    <!-- Gallery Section -->
    <section class="gallery" id="gallery">
        <div class="container">
            <h2 class="section-title">Featured Artwork</h2>
            <div class="gallery-grid">
                <div class="artwork">
                    <img src="https://images.unsplash.com/photo-1579783902614-a3fb3927b6a5?ixlib=rb-4.0.3" alt="Abstract Art">
                    <div class="artwork-info">
                        <h3>Ethereal Dreams</h3>
                        <p>Acrylic on Canvas • 24" x 36"</p>
                    </div>
                </div>
                <div class="artwork">
                    <img src="https://images.unsplash.com/photo-1541961017774-22349e4a1262?ixlib=rb-4.0.3" alt="Portrait">
                    <div class="artwork-info">
                        <h3>Silent Contemplation</h3>
                        <p>Oil Painting • 30" x 40"</p>
                    </div>
                </div>
                <div class="artwork">
                    <img src="https://images.unsplash.com/photo-1515405295579-ba7b45403062?ixlib=rb-4.0.3" alt="Landscape">
                    <div class="artwork-info">
                        <h3>Mountain Serenity</h3>
                        <p>Watercolor • 18" x 24"</p>
                    </div>
                </div>
                <div class="artwork">
                    <img src="https://images.unsplash.com/photo-1513475382585-d06e58bcb0e0?ixlib=rb-4.0.3" alt="Modern Art">
                    <div class="artwork-info">
                        <h3>Urban Rhythm</h3>
                        <p>Mixed Media • 36" x 36"</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2>About the Artist</h2>
                    <p>With over 10 years of professional experience, I specialize in creating bespoke artwork that captures emotion and tells unique stories. My work spans various mediums including oil, acrylic, watercolor, and mixed media.</p>
                    <p>Each piece is meticulously crafted to resonate with its environment and owner. I believe art should not just decorate space, but transform it—creating atmosphere, sparking conversation, and inspiring daily life.</p>
                    <p>My studio practice is built on collaboration, ensuring every commissioned piece perfectly reflects the client's vision while maintaining artistic integrity.</p>
                    <a href="#contact" class="btn">Start Your Project</a>
                </div>
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1544725176-7c40e5a71c5e?ixlib=rb-4.0.3" alt="Artist at Work">
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <div class="container">
            <h2 class="section-title">Art Services</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">🎨</div>
                    <h3>Custom Commissions</h3>
                    <p>Bespoke artwork tailored to your space, style, and story. Perfect for homes, offices, or special gifts.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🏢</div>
                    <h3>Corporate Art</h3>
                    <p>Large-scale installations and collections for commercial spaces, hotels, and corporate environments.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">💝</div>
                    <h3>Special Occasions</h3>
                    <p>Memorable pieces for weddings, anniversaries, and milestone celebrations that become family heirlooms.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🖼️</div>
                    <h3>Art Consultation</h3>
                    <p>Professional guidance on art selection, placement, and curation for your home or business.</p>
                </div>
            </div>
        </div>
    </section>

<!-- Contact Section -->
<section class="contact" id="contact">
    <div class="container">
        <h2 class="section-title">Start Your Art Journey</h2>
        <div class="contact-grid">
            <div class="contact-info">
                <h3>Get In Touch</h3>
                <p>📧 <a href="mailto:njaginjeruh@gmail.com" style="color: #e74c3c;">njaginjeruh@gmail.com</a></p>
                <p>📞 <a href="tel:+254111204305" style="color: #e74c3c;">(254) 111-204305</a></p>
                <p>📍 Nairobi,Kenya</p>
                <p>⏰ Response within 24 hours</p>
                
                <div style="margin-top: 2rem; background: rgba(255,255,255,0.1); padding: 2rem; border-radius: 10px;">
                    <h4>📩 Ready to work together?</h4>
                    <p>Send me an email directly and I'll get back to you ASAP!</p>
                    <a href="mailto:njaginjeruh@gmail.com?subject=Art Commission Inquiry&body=Hi there! I'm interested in commissioning artwork..." 
                       class="btn" style="margin-top: 1rem;">
                        Email Me Now
                    </a>
                </div>
            </div>
            
            <div class="contact-info">
                <h3>Follow My Work</h3>
                <div class="social-links">
                    <a href="https://instagram.com/yourprofile" style="font-size: 2rem;">📷 Instagram</a><br><br>
                    <a href="https://facebook.com/yourprofile" style="font-size: 2rem;">📘 Facebook</a><br><br>
                    <a href="https://pinterest.com/yourprofile" style="font-size: 2rem;">📌 Pinterest</a><br><br>
                    <a href="https://yourwebsite.com" style="font-size: 2rem;">🌐 My Portfolio</a>
                </div>
            </div>
        </div>
    </div>
</section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2024 ArtStudio. All rights reserved.</p>
            <p>Creating meaningful art for meaningful spaces</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Form submission
        document.getElementById('commissionForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your inquiry! I will get back to you within 24 hours.');
            this.reset();
        });

        // Add loading animation to artwork
        document.querySelectorAll('.artwork').forEach(artwork => {
            artwork.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px)';
            });
            
            artwork.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0)';
            });
        });

        // Header background on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(44, 62, 80, 0.95)';
            } else {
                header.style.background = '#2c3e50';
            }
        });
    </script>
</body>
</html>
