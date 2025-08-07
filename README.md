<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Khyati Trivedi | Full Stack Developer</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Press+Start+2P&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6e48aa;
            --secondary: #9d50bb;
            --accent: #4776E6;
            --dark: #1a1a2e;
            --light: #f8f9fa;
            --neon: #0ff0fc;
            --neon-pink: #ff2ced;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
            scroll-behavior: smooth;
        }
        
        body {
            background-color: var(--dark);
            color: var(--light);
            background-image: 
                radial-gradient(circle at 25% 25%, rgba(110, 72, 170, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 75% 75%, rgba(157, 80, 187, 0.1) 0%, transparent 50%);
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Animation */
        header {
            position: relative;
            padding: 80px 0;
            text-align: center;
            overflow: hidden;
        }
        
        .hero-gif {
            width: 300px;
            height: 300px;
            object-fit: contain;
            margin: 0 auto;
            filter: drop-shadow(0 0 15px var(--neon));
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        h1 {
            font-size: 3.5rem;
            margin: 20px 0;
            background: linear-gradient(90deg, var(--neon), var(--neon-pink));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: 700;
            position: relative;
            display: inline-block;
        }
        
        h1::after {
            content: '';
            position: absolute;
            width: 100%;
            height: 4px;
            bottom: -5px;
            left: 0;
            background: linear-gradient(90deg, var(--neon), var(--neon-pink));
            border-radius: 2px;
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.5s ease;
        }
        
        h1:hover::after {
            transform: scaleX(1);
            transform-origin: left;
        }
        
        .tagline {
            font-size: 1.5rem;
            margin-bottom: 30px;
            position: relative;
            display: inline-block;
        }
        
        .tagline::before, .tagline::after {
            content: '✦';
            position: absolute;
            color: var(--neon);
            top: 50%;
            transform: translateY(-50%);
            opacity: 0;
            transition: all 0.3s ease;
        }
        
        .tagline::before {
            left: -30px;
        }
        
        .tagline::after {
            right: -30px;
        }
        
        .tagline:hover::before, .tagline:hover::after {
            opacity: 1;
        }
        
        /* Section Styling */
        section {
            padding: 60px 0;
            position: relative;
        }
        
        section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80%;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(110, 72, 170, 0.5), transparent);
        }
        
        h2 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            color: var(--neon);
            text-align: center;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }
        
        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--neon), transparent);
            border-radius: 3px;
        }
        
        /* About Me */
        .about-content {
            display: flex;
            align-items: center;
            gap: 40px;
            margin-top: 40px;
        }
        
        .about-text {
            flex: 1;
            font-size: 1.1rem;
            line-height: 1.8;
            position: relative;
            padding: 20px;
            border-radius: 10px;
            background: rgba(26, 26, 46, 0.7);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(110, 72, 170, 0.3);
            box-shadow: 0 10px 30px rgba(110, 72, 170, 0.1);
            transition: all 0.3s ease;
        }
        
        .about-text:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(110, 72, 170, 0.2);
            border-color: var(--neon);
        }
        
        .about-text p {
            margin-bottom: 15px;
        }
        
        .about-image {
            flex: 1;
            text-align: center;
        }
        
        .about-image img {
            width: 100%;
            max-width: 400px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            transition: all 0.3s ease;
            filter: brightness(0.9);
        }
        
        .about-image img:hover {
            transform: scale(1.03);
            filter: brightness(1);
            box-shadow: 0 15px 35px rgba(110, 72, 170, 0.4);
        }
        
        /* Skills */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }
        
        .skill-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            border-radius: 10px;
            background: rgba(26, 26, 46, 0.7);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(110, 72, 170, 0.3);
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .skill-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(110, 72, 170, 0.2);
            border-color: var(--neon);
            background: rgba(110, 72, 170, 0.1);
        }
        
        .skill-item i, .skill-item img {
            font-size: 2.5rem;
            margin-bottom: 10px;
            transition: all 0.3s ease;
        }
        
        .skill-item:hover i, .skill-item:hover img {
            transform: scale(1.2);
            filter: drop-shadow(0 0 5px var(--neon));
        }
        
        .skill-item span {
            font-size: 0.9rem;
            text-align: center;
            opacity: 0.8;
            transition: all 0.3s ease;
        }
        
        .skill-item:hover span {
            opacity: 1;
            color: var(--neon);
        }
        
        /* Goals */
        .goals-list {
            max-width: 800px;
            margin: 40px auto 0;
        }
        
        .goal-item {
            position: relative;
            padding: 25px;
            margin-bottom: 20px;
            border-radius: 10px;
            background: rgba(26, 26, 46, 0.7);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(110, 72, 170, 0.3);
            transition: all 0.3s ease;
            overflow: hidden;
        }
        
        .goal-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 5px;
            height: 100%;
            background: linear-gradient(to bottom, var(--neon), var(--neon-pink));
            transition: all 0.3s ease;
        }
        
        .goal-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(110, 72, 170, 0.2);
            border-color: var(--neon);
        }
        
        .goal-item:hover::before {
            width: 10px;
        }
        
        .goal-item i {
            margin-right: 10px;
            color: var(--neon);
        }
        
        /* Contact */
        .contact-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 40px;
        }
        
        .contact-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: rgba(26, 26, 46, 0.7);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(110, 72, 170, 0.3);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .contact-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, var(--neon), var(--neon-pink));
            opacity: 0;
            transition: all 0.3s ease;
            z-index: -1;
        }
        
        .contact-link:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 10px 20px rgba(110, 72, 170, 0.3);
            border-color: var(--neon);
        }
        
        .contact-link:hover::before {
            opacity: 1;
        }
        
        .contact-link i {
            font-size: 1.8rem;
            color: var(--light);
            transition: all 0.3s ease;
        }
        
        .contact-link:hover i {
            color: white;
            transform: scale(1.2);
        }
        
        /* Particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }
        
        .particle {
            position: absolute;
            background: var(--neon);
            border-radius: 50%;
            opacity: 0.5;
            animation: float-particle linear infinite;
        }
        
        @keyframes float-particle {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.5;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .tagline {
                font-size: 1.2rem;
            }
            
            .about-content {
                flex-direction: column;
            }
            
            .skills-container {
                grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            }
        }
    </style>
</head>
<body>
    <!-- Particles Background -->
    <div class="particles" id="particles"></div>
    
    <!-- Header -->
    <header>
        <div class="container">
            <img src="https://i.pinimg.com/originals/0b/83/92/0b83923c0f4964e8ad5313c0c55bdde5.gif" class="hero-gif" alt="Anime Coding">
            <h1>Khyati Trivedi</h1>
            <p class="tagline">Full Stack Developer | Tech Explorer | Problem Solver</p>
        </div>
    </header>
    
    <!-- About Me -->
    <section id="about">
        <div class="container">
            <h2>💡 About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>🚀 Tech enthusiast blending creativity & code with a passion for building meaningful digital experiences.</p>
                    <p>🦾 Currently mastering the art of development as a Computer Applications student, crafting solutions that bridge technology and human needs.</p>
                    <p>🌱 Love architecting full-stack applications that solve real problems, not just write code.</p>
                    <p>🏆 3⭐ on HackerRank for Problem Solving—always up for a coding challenge!</p>
                    <p>📈 Constantly expanding my skills in this ever-evolving tech landscape.</p>
                </div>
                <div class="about-image">
                    <img src="https://i.pinimg.com/originals/25/65/7d/25657d13569db5c58e4458b88c2e9b6b.gif" alt="Anime Developer">
                </div>
            </div>
        </div>
    </section>
    
    <!-- Skills -->
    <section id="skills">
        <div class="container">
            <h2>🛠️ My Tech Stack</h2>
            <div class="skills-container">
                <div class="skill-item">
                    <i class="fab fa-html5"></i>
                    <span>HTML5</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-css3-alt"></i>
                    <span>CSS3</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-js"></i>
                    <span>JavaScript</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-react"></i>
                    <span>React</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-angular"></i>
                    <span>Angular</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-node-js"></i>
                    <span>Node.js</span>
                </div>
                <div class="skill-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original.svg" alt="Express">
                    <span>Express</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-bootstrap"></i>
                    <span>Bootstrap</span>
                </div>
                <div class="skill-item">
                    <img src="https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg" alt="Tailwind">
                    <span>Tailwind</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-java"></i>
                    <span>Java</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-python"></i>
                    <span>Python</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-git-alt"></i>
                    <span>Git</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-github"></i>
                    <span>GitHub</span>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Goals -->
    <section id="goals">
        <div class="container">
            <h2>🌟 On My Radar</h2>
            <div class="goals-list">
                <div class="goal-item">
                    <p><i class="fas fa-rocket"></i> Crafting an AI-powered platform for better student mental wellness. Because we all need support in this digital age.</p>
                </div>
                <div class="goal-item">
                    <p><i class="fas fa-paint-brush"></i> Building a real-time collaboration app for remote teams—think digital whiteboarding meets creative workspace with vibes.</p>
                </div>
                <div class="goal-item">
                    <p><i class="fas fa-code"></i> Contributing to open-source projects that make web development more accessible to beginners.</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Contact -->
    <section id="contact">
        <div class="container">
            <h2>📡 Let's Connect</h2>
            <div class="contact-links">
                <a href="https://www.linkedin.com/in/khyati-trivedi" class="contact-link" target="_blank">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="https://github.com/khyati-trivedi" class="contact-link" target="_blank">
                    <i class="fab fa-github"></i>
                </a>
                <a href="mailto:your-email@example.com" class="contact-link">
                    <i class="fas fa-envelope"></i>
                </a>
                <a href="https://twitter.com/yourhandle" class="contact-link" target="_blank">
                    <i class="fab fa-twitter"></i>
                </a>
            </div>
        </div>
    </section>
    
    <script>
        // Create particles
        const particlesContainer = document.getElementById('particles');
        const particleCount = 30;
        
        for (let i = 0; i < particleCount; i++) {
            const particle = document.createElement('div');
            particle.classList.add('particle');
            
            // Random properties
            const size = Math.random() * 5 + 2;
            const posX = Math.random() * window.innerWidth;
            const duration = Math.random() * 20 + 10;
            const delay = Math.random() * 10;
            const color = `hsl(${Math.random() * 60 + 180}, 100%, 70%)`;
            
            particle.style.width = `${size}px`;
            particle.style.height = `${size}px`;
            particle.style.left = `${posX}px`;
            particle.style.bottom = `-10px`;
            particle.style.animationDuration = `${duration}s`;
            particle.style.animationDelay = `${delay}s`;
            particle.style.background = color;
            
            particlesContainer.appendChild(particle);
        }
        
        // Add scroll animation
        const sections = document.querySelectorAll('section');
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = 1;
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });
        
        sections.forEach(section => {
            section.style.opacity = 0;
            section.style.transform = 'translateY(20px)';
            section.style.transition = 'all 0.6s ease';
            observer.observe(section);
        });
        
        // Add hover effect to skills
        const skillItems = document.querySelectorAll('.skill-item');
        
        skillItems.forEach(item => {
            item.addEventListener('mouseenter', () => {
                const icon = item.querySelector('i, img');
                if (icon) {
                    icon.style.transform = 'scale(1.2) rotate(10deg)';
                }
            });
            
            item.addEventListener('mouseleave', () => {
                const icon = item.querySelector('i, img');
                if (icon) {
                    icon.style.transform = 'scale(1) rotate(0deg)';
                }
            });
        });
    </script>
</body>
</html>
