<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SearchAI - AI-Powered Search, Video & Image Creation</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #4285f4;
            --secondary-color: #34a853;
            --accent-color: #ea4335;
            --yellow-color: #fbbc05;
            --light-color: #f8f9fa;
            --dark-color: #202124;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            color: var(--dark-color);
            line-height: 1.6;
        }
        
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem 2rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            color: var(--yellow-color);
        }
        
        .nav-links {
            display: flex;
            gap: 1.5rem;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .nav-links a:hover {
            color: var(--yellow-color);
        }
        
        .cta-button {
            background: var(--yellow-color);
            color: var(--dark-color);
            border: none;
            border-radius: 24px;
            padding: 0.5rem 1.5rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        
        .hero {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 6rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1620712943543-bcc4688e7485?auto=format&fit=crop&q=80&w=1000') no-repeat center center;
            background-size: cover;
            opacity: 0.1;
            z-index: 0;
        }
        
        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }
        
        .search-container {
            max-width: 800px;
            margin: 2rem auto;
        }
        
        .search-tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 1rem;
            gap: 5px;
        }
        
        .search-tab {
            padding: 0.5rem 1.5rem;
            background: rgba(255,255,255,0.2);
            border: none;
            color: white;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .search-tab.active {
            background: white;
            color: var(--primary-color);
        }
        
        .search-tab:hover {
            background: rgba(255,255,255,0.3);
        }
        
        .search-box {
            display: flex;
            border: 1px solid #dfe1e5;
            border-radius: 24px;
            padding: 0.5rem 1rem;
            background: white;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }
        
        .search-box input {
            flex: 1;
            border: none;
            outline: none;
            font-size: 1rem;
            padding: 0.5rem;
        }
        
        .search-box button {
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 18px;
            padding: 0.5rem 1.5rem;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .search-box button:hover {
            background: #3367d6;
        }
        
        .features {
            padding: 6rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }
        
        .section-header h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 1rem;
        }
        
        .section-header p {
            font-size: 1.1rem;
            color: #555;
            max-width: 700px;
            margin: 0 auto;
        }
        
        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .feature-card {
            background: white;
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
            border: 1px solid #eee;
        }
        
        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 24px rgba(0,0,0,0.1);
        }
        
        .feature-icon {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 1.5rem;
        }
        
        .feature-card h3 {
            color: var(--primary-color);
            margin-top: 0;
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }
        
        .creation-section {
            background: var(--light-color);
            padding: 6rem 2rem;
        }
        
        .creation-container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .creation-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }
        
        .creation-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }
        
        .creation-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 24px rgba(0,0,0,0.1);
        }
        
        .creation-image {
            height: 250px;
            background-size: cover;
            background-position: center;
        }
        
        .video-creation .creation-image {
            background-image: url('https://images.unsplash.com/photo-1574717024453-3545e7cc5e7a?auto=format&fit=crop&q=80&w=1000');
        }
        
        .image-creation .creation-image {
            background-image: url('https://images.unsplash.com/photo-1635070041078-e363dbe005cb?auto=format&fit=crop&q=80&w=1000');
        }
        
        .creation-content {
            padding: 2rem;
        }
        
        .creation-content h3 {
            font-size: 1.8rem;
            margin-top: 0;
            margin-bottom: 1rem;
            color: var(--primary-color);
        }
        
        .creation-content ul {
            padding-left: 1.2rem;
        }
        
        .creation-content li {
            margin-bottom: 0.5rem;
        }
        
        .demo-section {
            padding: 6rem 2rem;
            background: linear-gradient(135deg, #f5f7fa, #e4e8eb);
        }
        
        .demo-container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .demo-video {
            width: 100%;
            height: 500px;
            background: #000;
            border-radius: 12px;
            margin-top: 3rem;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            position: relative;
            overflow: hidden;
        }
        
        .demo-video::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1626785774573-4b799315345d?auto=format&fit=crop&q=80&w=1000') no-repeat center center;
            background-size: cover;
            opacity: 0.7;
        }
        
        .play-button {
            position: relative;
            z-index: 1;
            width: 80px;
            height: 80px;
            background: rgba(255,255,255,0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .play-button i {
            font-size: 2rem;
            color: white;
            margin-left: 5px;
        }
        
        .play-button:hover {
            transform: scale(1.1);
            background: rgba(255,255,255,0.3);
        }
        
        .testimonials {
            padding: 6rem 2rem;
            background: white;
        }
        
        .testimonial-container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .testimonial-card {
            background: var(--light-color);
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
        }
        
        .testimonial-text {
            font-style: italic;
            margin-bottom: 1.5rem;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        
        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-size: cover;
        }
        
        .author-info h4 {
            margin: 0;
            color: var(--primary-color);
        }
        
        .author-info p {
            margin: 0;
            color: #666;
            font-size: 0.9rem;
        }
        
        .pricing {
            padding: 6rem 2rem;
            background: var(--light-color);
        }
        
        .pricing-container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .pricing-card {
            background: white;
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            text-align: center;
            transition: all 0.3s ease;
        }
        
        .pricing-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 24px rgba(0,0,0,0.1);
        }
        
        .pricing-card.popular {
            border: 2px solid var(--primary-color);
            position: relative;
        }
        
        .popular-badge {
            position: absolute;
            top: -12px;
            right: 20px;
            background: var(--primary-color);
            color: white;
            padding: 0.3rem 1rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
        }
        
        .pricing-card h3 {
            color: var(--primary-color);
            font-size: 1.5rem;
            margin-top: 0;
        }
        
        .price {
            font-size: 2.5rem;
            font-weight: bold;
            margin: 1.5rem 0;
            color: var(--dark-color);
        }
        
        .price span {
            font-size: 1rem;
            color: #666;
        }
        
        .pricing-features {
            list-style: none;
            padding: 0;
            margin: 2rem 0;
        }
        
        .pricing-features li {
            padding: 0.5rem 0;
            border-bottom: 1px solid #eee;
        }
        
        .cta-section {
            padding: 6rem 2rem;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            text-align: center;
        }
        
        .cta-container {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .cta-section h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
        }
        
        .cta-section p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }
        
        .cta-buttons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }
        
        .cta-button-primary {
            background: white;
            color: var(--primary-color);
            border: none;
            border-radius: 24px;
            padding: 0.8rem 2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
        }
        
        .cta-button-secondary {
            background: transparent;
            color: white;
            border: 2px solid white;
            border-radius: 24px;
            padding: 0.8rem 2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
        }
        
        .cta-button-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
        }
        
        .cta-button-secondary:hover {
            background: rgba(255,255,255,0.1);
            transform: translateY(-2px);
        }
        
        footer {
            background: var(--dark-color);
            color: white;
            padding: 4rem 2rem 2rem;
        }
        
        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }
        
        .footer-logo {
            font-size: 1.8rem;
            font-weight: bold;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .footer-logo i {
            color: var(--yellow-color);
        }
        
        .footer-about p {
            opacity: 0.8;
            line-height: 1.6;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }
        
        .social-links a {
            color: white;
            font-size: 1.2rem;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            color: var(--yellow-color);
        }
        
        .footer-links h3 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            position: relative;
        }
        
        .footer-links h3::after {
            content: "";
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 40px;
            height: 2px;
            background: var(--yellow-color);
        }
        
        .footer-links ul {
            list-style: none;
            padding: 0;
        }
        
        .footer-links li {
            margin-bottom: 0.8rem;
        }
        
        .footer-links a {
            color: rgba(255,255,255,0.8);
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .footer-links a:hover {
            color: white;
            padding-left: 5px;
        }
        
        .footer-newsletter input {
            width: 100%;
            padding: 0.8rem;
            border: none;
            border-radius: 4px;
            margin-bottom: 1rem;
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            margin-top: 2rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        
        .footer-bottom p {
            opacity: 0.7;
            font-size: 0.9rem;
        }
        
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .nav-links {
                display: none;
            }
            
            .demo-video {
                height: 300px;
            }
            
            .creation-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">
                <i class="fas fa-robot"></i>
                <span>SearchAI</span>
            </div>
            <div class="nav-links">
                <a href="#features">Features</a>
                <a href="#creation">Creation Tools</a>
                <a href="#pricing">Pricing</a>
                <a href="#testimonials">Testimonials</a>
                <a href="#contact">Contact</a>
            </div>
            <button class="cta-button">Get Started</button>
        </nav>
    </header>
    
    <section class="hero">
        <div class="hero-content">
            <h1>AI-Powered Search, Video & Image Creation</h1>
            <p>Discover, create, and share with the most advanced AI platform that understands your needs and helps bring your ideas to life.</p>
            
            <div class="search-container">
                <div class="search-tabs">
                    <button class="search-tab active">Search</button>
                    <button class="search-tab">Create Video</button>
                    <button class="search-tab">Generate Image</button>
                </div>
                <div class="search-box">
                    <input type="text" placeholder="Ask anything or describe what you want to create...">
                    <button><i class="fas fa-search"></i> Go</button>
                </div>
            </div>
        </div>
    </section>
    
    <section class="features" id="features">
        <div class="section-header">
            <h2>Powerful AI Features</h2>
            <p>SearchAI combines advanced search capabilities with powerful creation tools to give you everything you need in one platform</p>
        </div>
        
        <div class="feature-grid">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-search-plus"></i>
                </div>
                <h3>Smart Search</h3>
                <p>Our AI understands context, follows up with clarifying questions, and provides comprehensive answers with sources.</p>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-video"></i>
                </div>
                <h3>AI Video Creation</h3>
                <p>Transform text into engaging videos with realistic voiceovers, animations, and automatic scene generation.</p>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-image"></i>
                </div>
                <h3>Image Generation</h3>
                <p>Create stunning visuals from text descriptions with multiple art styles and customization options.</p>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-brain"></i>
                </div>
                <h3>Content Enhancement</h3>
                <p>Improve your existing content with AI-powered rewriting, summarizing, and optimization tools.</p>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-language"></i>
                </div>
                <h3>Multilingual Support</h3>
                <p>Search and create content in dozens of languages with accurate translations and localization.</p>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-shield-alt"></i>
                </div>
                <h3>Privacy Focused</h3>
                <p>Your data remains yours. We don't sell your information or use it for advertising purposes.</p>
            </div>
        </div>
    </section>
    
    <section class="creation-section" id="creation">
        <div class="creation-container">
            <div class="section-header">
                <h2>AI Creation Tools</h2>
                <p>Turn your ideas into reality with our powerful AI-powered creation tools</p>
            </div>
            
            <div class="creation-grid">
                <div class="creation-card video-creation">
                    <div class="creation-image"></div>
                    <div class="creation-content">
                        <h3>AI Video Creation</h3>
                        <p>Create professional-quality videos in minutes with our AI video generator:</p>
                        <ul>
                            <li>Text-to-video conversion with realistic voiceovers</li>
                            <li>Automatic scene generation and transitions</li>
                            <li>Huge library of stock footage and animations</li>
                            <li>Customizable templates for different video styles</li>
                            <li>Background music and sound effects library</li>
                        </ul>
                        <button class="cta-button" style="margin-top: 1rem;">Try Video Creator</button>
                    </div>
                </div>
                
                <div class="creation-card image-creation">
                    <div class="creation-image"></div>
                    <div class="creation-content">
                        <h3>AI Image Generation</h3>
                        <p>Generate stunning visuals from text descriptions with our AI image creator:</p>
                        <ul>
                            <li>Multiple art styles (realistic, cartoon, painting, etc.)</li>
                            <li>High-resolution output up to 4K</li>
                            <li>Edit and refine generated images</li>
                            <li>Background removal and object isolation</li>
                            <li>Batch generation for multiple variations</li>
                        </ul>
                        <button class="cta-button" style="margin-top: 1rem;">Try Image Generator</button>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <section class="demo-section">
        <div class="demo-container">
            <div class="section-header">
                <h2>See SearchAI in Action</h2>
                <p>Watch how our AI tools can transform your workflow and creativity</p>
            </div>
            
            <div class="demo-video">
                <div class="play-button">
                    <i class="fas fa-play"></i>
                </div>
            </div>
        </div>
    </section>
    
    <section class="testimonials" id="testimonials">
        <div class="testimonial-container">
            <div class="section-header">
                <h2>What Our Users Say</h2>
                <p>Thousands of creators and professionals trust SearchAI for their daily work</p>
            </div>
            
            <div class="testimonial-grid">
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "SearchAI has completely transformed how I create content. I can now produce videos in hours that used to take me days, and the quality is amazing!"
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar" style="background-image: url('https://randomuser.me/api/portraits/women/44.jpg');"></div>
                        <div class="author-info">
                            <h4>Sarah Johnson</h4>
                            <p>Content Creator</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "The image generation tool is incredible. As a small business owner, I can now create professional marketing materials without hiring a designer."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar" style="background-image: url('https://randomuser.me/api/portraits/men/32.jpg');"></div>
                        <div class="author-info">
                            <h4>Michael Chen</h4>
                            <p>Small Business Owner</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "I use SearchAI daily for research. It finds information I couldn't locate through traditional search engines and summarizes it perfectly."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar" style="background-image: url('https://randomuser.me/api/portraits/women/68.jpg');"></div>
                        <div class="author-info">
                            <h4>Dr. Emily Rodriguez</h4>
                            <p>Research Scientist</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <section class="pricing" id="pricing">
        <div class="pricing-container">
            <div class="section-header">
                <h2>Simple, Transparent Pricing</h2>
                <p>Choose the plan that fits your needs</p>
            </div>
            
            <div class="pricing-grid">
                <div class="pricing-card">
                    <h3>Starter</h3>
                    <div class="price">$9<span>/month</span></div>
                    <ul class="pricing-features">
                        <li>100 AI searches per day</li>
                        <li>5 video creations/month</li>
                        <li>10 image generations/month</li>
                        <li>Basic support</li>
                        <li>720p video resolution</li>
                    </ul>
                    <button class="cta-button">Get Started</button>
                </div>
                
                <div class="pricing-card popular">
                    <div class="popular-badge">MOST POPULAR</div>
                    <h3>Pro</h3>
                    <div class="price">$29<span>/month</span></div>
                    <ul class="pricing-features">
                        <li>Unlimited AI searches</li>
                        <li>20 video creations/month</li>
                        <li>50 image generations/month</li>
                        <li>Priority support</li>
                        <li>1080p video resolution</li>
                        <li>Commercial license</li>
                    </ul>
                    <button class="cta-button">Get Started</button>
                </div>
                
                <div class="pricing-card">
                    <h3>Enterprise</h3>
                    <div class="price">$99<span>/month</span></div>
                    <ul class="pricing-features">
                        <li>Unlimited everything</li>
                        <li>100 video creations/month</li>
                        <li>500 image generations/month</li>
                        <li>24/7 premium support</li>
                        <li>4K video resolution</li>
                        <li>Team collaboration</li>
                        <li>API access</li>
                    </ul>
                    <button class="cta-button">Get Started</button>
                </div>
            </div>
        </div>
    </section>
    
    <section class="cta-section">
        <div class="cta-container">
            <h2>Ready to Transform Your Workflow?</h2>
            <p>Join thousands of creators, professionals, and businesses using SearchAI to work smarter and create faster.</p>
            <div class="cta-buttons">
                <button class="cta-button-primary">Start Free Trial</button>
                <button class="cta-button-secondary">Schedule Demo</button>
            </div>
        </div>
    </section>
    
    <footer id="contact">
        <div class="footer-container">
            <div class="footer-about">
                <div class="footer-logo">
                    <i class="fas fa-robot"></i>
                    <span>SearchAI</span>
                </div>
                <p>The most advanced AI platform combining search, video creation, and image generation in one powerful tool.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-facebook"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-linkedin"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
            
            <div class="footer-links">
                <h3>Product</h3>
                <ul>
                    <li><a href="#">Features</a></li>
                    <li><a href="#">Pricing</a></li>
                    <li><a href="#">Video Creator</a></li>
                    <li><a href="#">Image Generator</a></li>
                    <li><a href="#">API</a></li>
                </ul>
            </div>
            
            <div class="footer-links">
                <h3>Resources</h3>
                <ul>
                    <li><a href="#">Documentation</a></li>
                    <li><a href="#">Tutorials</a></li>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">Community</a></li>
                    <li><a href="#">Help Center</a></li>
                </ul>
            </div>
            
            <div class="footer-links">
                <h3>Company</h3>
                <ul>
                    <li><a href="#">About Us</a></li>
                    <li><a href="#">Careers</a></li>
                    <li><a href="#">Press</a></li>
                    <li><a href="#">Partners</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </div>
            
            <div class="footer-newsletter">
                <h3>Stay Updated</h3>
                <p>Subscribe to our newsletter for the latest updates and tips.</p>
                <input type="email" placeholder="Your email address">
                <button class="cta-button" style="width: 100%;">Subscribe</button>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>&copy; 2023 SearchAI Technologies. All rights reserved. | <a href="#" style="color: var(--yellow-color);">Privacy Policy</a> | <a href="#" style="color: var(--yellow-color);">Terms of Service</a></p>
        </div>
    </footer>
</body>
</html>
