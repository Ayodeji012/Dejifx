<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DejiFX - Forex Trading Guide</title>
    <style>
        /* ===== Global Styles ===== */
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            line-height: 1.6;
            color: #333;
            background-color: #f5f5f5;
            overflow-x: hidden;
        }

        /* ===== Animated Background ===== */
        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .animated-bg::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #003366 0%, #004080 100%);
            z-index: 1;
        }

        .animated-bg video {
            position: absolute;
            top: 50%;
            left: 50%;
            min-width: 100%;
            min-height: 100%;
            width: auto;
            height: auto;
            transform: translate(-50%, -50%);
            opacity: 0.4;
        }

        /* ===== Container ===== */
        .container {
            width: 85%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px 0;
            position: relative;
            z-index: 1;
        }

        /* ===== Header & Navigation ===== */
        header {
            background: linear-gradient(135deg, #003366 0%, #004080 100%);
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(5px);
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            margin-right: auto;
            color: white;
            text-decoration: none;
        }

        nav ul {
            list-style: none;
            padding: 0;
            margin: 0;
            display: flex;
            justify-content: flex-end;
            align-items: center;
            gap: 20px;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            padding: 8px 15px;
            border-radius: 4px;
            position: relative;
        }

        nav a:hover {
            color: #4CAF50;
            background-color: rgba(255, 255, 255, 0.1);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 0;
            height: 2px;
            background: #4CAF50;
            transition: all 0.3s ease;
            transform: translateX(-50%);
        }

        nav a:hover::after {
            width: 80%;
        }

        /* ===== Hero Section ===== */
        #hero {
            background:linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80') no-repeat center/cover;
            color: white;
            text-align: center;
            padding: 150px 0;
            position: relative;
        }

        #hero h2 {
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.7);
        }

        #hero p {
            font-size: 1.3rem;
            max-width: 700px;
            margin: 0 auto 30px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
        }

        /* ===== Discord CTA Section ===== */
        #discord-cta {
            background: linear-gradient(135deg, rgba(76,175,80,0.9) 0%, rgba(46,125,50,0.9) 100%) url('https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80') no-repeat center/cover;;
            color: white;
            text-align: center;
            padding: 100px 0;
            position: relative;
            overflow: hidden;
            margin: 60px 0;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        #discord-cta::before {
            content: '';
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            background: linear-gradient(135deg, rgba(76,175,80,0.3) 0%, rgba(46,125,50,0.3) 100%) url('https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80') no-repeat center/cover;;
            z-index: -1;
            filter: blur(10px);
        }

        #discord-cta h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }

        #discord-cta p {
            font-size: 1.2rem;
            margin-bottom: 25px;
        }

        /* ===== Trading Strategies ===== */
        #trading-strategies {
            padding: 80px 0;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1);
            margin: 60px 0;
        }

        #trading-strategies h2 {
            text-align: center;
            margin-bottom: 50px;
            font-size: 2.5rem;
            color: #003366;
            position: relative;
        }

        #trading-strategies h2::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: #4CAF50;
            margin: 15px auto;
            border-radius: 2px;
        }

        .strategy-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            justify-content: center;
        }

        .strategy-item {
            background: white;
            border: 1px solid #eee;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .strategy-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(0,51,102,0.05) 0%, rgba(0,64,128,0.05) 100%);
            z-index: -1;
        }

        .strategy-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .strategy-item h3 {
            color: #003366;
            margin-top: 0;
            font-size: 1.5rem;
        }

        /* ===== Buttons ===== */
        .cta-button {
            display: inline-block;
            background: #4CAF50;
            color: white;
            padding: 15px 35px;
            text-decoration: none;
            border-radius: 30px;
            font-weight: bold;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-size: 1.1rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
        }

        .cta-button:hover {
            background: #45a049;
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        .cta-button::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 5px;
            height: 5px;
            background: rgba(255, 255, 255, 0.5);
            opacity: 0;
            border-radius: 100%;
            transform: scale(1, 1) translate(-50%);
            transform-origin: 50% 50%;
        }

        .cta-button:hover::after {
            animation: ripple 1s ease-out;
        }

        .discord-button {
            background: #5865F2;
        }

        .discord-button:hover {
            background: #4752C4;
        }

        /* ===== Footer ===== */
        footer {
            background: linear-gradient(135deg, rgba(0,51,102,0.9) 0%, rgba(0,34,68,0.9) 100%);
            color: white;
            text-align: center;
            padding: 40px 0;
            margin-top: 80px;
            position: relative;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.1;
            background:linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80') no-repeat center/cover;
            z-index: -1;
        }

        footer a {
            color: #4CAF50;
            text-decoration: none;
            transition: color 0.3s;
            font-weight: bold;
        }

        footer a:hover {
            color: #45a049;
            text-decoration: underline;
        }

        /* ===== Animations ===== */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes ripple {
            0% {
                transform: scale(0, 0);
                opacity: 1;
            }
            20% {
                transform: scale(25, 25);
                opacity: 1;
            }
            100% {
                opacity: 0;
                transform: scale(40, 40);
            }
        }

        #hero, #discord-cta, #trading-strategies {
            animation: fadeIn 1s ease-out;
        }

        .strategy-item {
            animation: fadeIn 0.8s ease-out;
            animation-fill-mode: both;
        }

        .strategy-item:nth-child(1) { animation-delay: 0.2s; }
        .strategy-item:nth-child(2) { animation-delay: 0.4s; }
        .strategy-item:nth-child(3) { animation-delay: 0.6s; }

        /* ===== Mobile Responsiveness ===== */
        @media (max-width: 768px) {
            .container {
                width: 90%;
            }
            
            nav ul {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
            
            #hero {
                padding: 100px 0;
            }
            
            #hero h2 {
                font-size: 2.2rem;
            }
            
            .strategy-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="animated-bg">
        <video autoplay muted loop playsinline>
            <source src="https://assets.mixkit.co/videos/preview/mixkit-stock-market-graph-background-15847-large.mp4" type="video/mp4">
        </video>
    </div>

    <!-- Header with Navigation -->
    <header>
        <div class="container">
            <nav>
                <a href="#home" class="logo">DejiFX</a>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About Forex</a></li>
                    <li><a href="#strategies">Trading Strategies</a></li>
                    <li><a href="https://discord.gg/xGXxxAzf" class="cta-button discord-button" target="_blank">Join Discord</a></li>
                    <li><a href="https://telegram.org/dl" class="cta-button telegram-button" target="_blank">Join Telegram</a></li>
                    <li><a href="https://www.instagram.com/invites/contact/?utm_source=ig_contact_invite&utm_medium=copy_link&utm_content=wnpwldf" class="cta-buttton instagram-button" target="_blank">Join Instagram</a>                                                                                                          
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home">
        <div class="container">
            <div id="hero">
                <h2>Master Forex Trading with DejiFX</h2>
                <p>Learn proven strategies, get market analysis, and join a community of traders dedicated to success in the forex market.</p>
                <a href="#strategies" class="cta-button">Explore Strategies</a>
            </div>
        </div>
    </section>

    <!-- Discord CTA Section -->
    <section id="discord-cta">
        <div class="container">
            <h2>Join Our Trading Community</h2>
            <p>Get real-time signals, expert discussions, and trading support from our active community of traders.</p>
            <a href="https://discord.gg/xGXxxAzf" class="cta-button discord-button" target="_blank">
                Join Our Discord Server
                <a href="https://telegram.org/dl" class="cta-button telegram-button" target="_blank">
                    Join Telegram
                    <a href="https://www.instagram.com/invites/contact/?utm_source=ig_contact_invite&utm_medium=copy_link&utm_content=wnpwldf" class="cta-button instagram-button" target="_blank">
                    Join Instagram
            </a>
            <p><small>Link opens in Discord app if installed</small></p>
            <p><small>Link opens in Telegram app if installed</small></p>
            <p><small>Link opens in Instagram app if installed</small></p>
        </div>
    </section>

    <!-- About Forex Section -->
    <section id="about" class="container">
        <div style="background: white; padding: 40px; border-radius: 10px; box-shadow: 0 5px 25px rgba(0,0,0,0.1);">
            <h2 style="text-align: center; color: #003366; font-size: 2.5rem; margin-bottom: 30px;">About Forex Trading</h2>
            <p style="font-size: 1.1rem; line-height: 1.8; margin-bottom: 20px;">
                Forex (foreign exchange) trading involves buying and selling currencies on the global market. 
                It's the largest financial market in the world, with over $6 trillion traded daily.
            </p>
            <p style="font-size: 1.1rem; line-height: 1.8;">
                At DejiFX, we provide the tools, education, and community support to help you navigate this dynamic market 
                and develop profitable trading strategies.
            </p>
        </div>
    </section>

    <!-- Trading Strategies -->
    <section id="strategies">
        <div id="trading-strategies" class="container">
            <h2>Popular Trading Strategies</h2>
            <div class="strategy-grid">
                <div class="strategy-item">
                    <h3>Day Trading</h3>
                    <p>Profit from short-term price movements within a single trading day. Our community provides real-time analysis and signals to help identify the best entry and exit points.</p>
                </div>
                <div class="strategy-item">
                    <h3>Swing Trading</h3>
                    <p>Capture gains over several days or weeks by analyzing market swings. Learn to identify key support and resistance levels with our expert guidance.</p>
                </div>
                <div class="strategy-item">
                    <h3>Position Trading</h3>
                    <p>Long-term approach based on fundamental analysis of currency trends. Our community discusses macroeconomic factors that drive currency valuations.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer with Discord Link -->
    <footer>
        <div class="container">
            <p>&copy; 2025 DejiFX. All rights reserved. 
               <a href="https://discord.gg/xGXxxAzf" target="_blank">Join Our Discord Community</a> 
               <a href="https://telegram.org/dl" target="_blank">Join Our Telegram Community</a>
                <a href="https://www.instagram.com/invites/contact/?utm_source=ig_contact_invite&utm_medium=copy_link&utm_content=wnpwldf" target="_blank">Join Our Instagram Community</a>                                                                                                                                                                     
               <a href="#home">Back to Top</a>
            </p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Add active class to current section in navigation
        window.addEventListener('scroll', function() {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('nav ul li a');
            
            let current = '';
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                
                if (pageYOffset >= (sectionTop - 300)) {
                    current = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === `#${current}`) {
                    link.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>        
