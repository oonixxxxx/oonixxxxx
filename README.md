<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>oonixxxxx | Fullstack Developer</title>
    <meta name="description" content="Портфолио fullstack разработчика">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="stylesheet" href="https://unpkg.com/aos@2.3.1/dist/aos.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #6467f2;
            --primary-light: #818cf8;
            --text: #1f2937;
            --text-light: #4b5563;
            --background: #e4e4eb;
            --border: #e5e7eb;
            --radius: 12px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            font-size: 16px;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: var(--text);
            background-color: var(--background);
            overflow-x: hidden;
        }

        /* Preloader */
        .preloader {
            position: fixed;
            inset: 0;
            z-index: 9999;
            background: var(--background);
            display: grid;
            place-items: center;
            transition: opacity 0.3s ease;
        }

        .loader {
            width: 48px;
            height: 48px;
            border: 3px solid var(--border);
            border-top-color: var(--primary);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 1.5rem;
            right: 1.5rem;
            z-index: 1000;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: var(--radius);
            padding: 1rem 2rem;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
        }

        .nav-list {
            display: flex;
            gap: 1.5rem;
            list-style: none;
        }

        .nav-link {
            color: var(--text);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            padding: 0.5rem 0;
            transition: var(--transition);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: var(--transition);
        }

        .nav-link:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 2rem;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero-title {
            font-size: clamp(3rem, 10vw, 5rem);
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            letter-spacing: -0.05em;
        }

        .text-gradient {
            background: linear-gradient(45deg, var(--primary), var(--primary-light));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-subtitle {
            font-size: clamp(1.25rem, 4vw, 2rem);
            color: var(--text-light);
            font-weight: 300;
            margin-bottom: 2rem;
            position: relative;
            padding-bottom: 1rem;
        }

        .hero-subtitle::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 2px;
            background: var(--primary);
        }

        /* Scroll Indicator */
        .scroll-indicator {
            margin-top: 4rem;
        }

        .mouse {
            width: 30px;
            height: 50px;
            border: 2px solid var(--primary);
            border-radius: 15px;
            margin: 0 auto;
            position: relative;
            animation: scroll 2s infinite;
        }

        .mouse::after {
            content: '';
            position: absolute;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            width: 4px;
            height: 10px;
            background: var(--primary);
            border-radius: 2px;
            animation: wheel 2s infinite;
        }

        /* Skills Section */
        .skills {
            padding: 6rem 0;
        }

        .skills-grid {
            display: grid;
            gap: 2rem;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        }

        .skill-card {
            background: white;
            padding: 2rem;
            border-radius: var(--radius);
            text-align: center;
            transition: var(--transition);
        }

        .skill-card:hover {
            transform: translateY(-10px);
        }

        .skill-card i {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        /* Projects Section */
        .projects {
            padding: 6rem 0;
        }

        .projects-grid {
            display: grid;
            gap: 2rem;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        }

        .project-card {
            background: white;
            border-radius: var(--radius);
            overflow: hidden;
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-5px);
        }

        .project-image {
            height: 250px;
            overflow: hidden;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .project-card:hover img {
            transform: scale(1.05);
        }

        .project-content {
            padding: 1.5rem;
        }

        .tech-list {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
            margin-top: 1rem;
        }

        .tech-list li {
            background: rgba(99, 102, 241, 0.1);
            color: var(--primary);
            padding: 0.3rem 1rem;
            border-radius: 50px;
            font-size: 0.85rem;
        }

        /* Contact Section */
        .contact {
            padding: 6rem 0;
        }

        .social-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .social-card {
            background: white;
            padding: 1.5rem;
            border-radius: var(--radius);
            text-align: center;
            transition: var(--transition);
        }

        .social-card:hover {
            transform: translateY(-5px);
        }

        .social-card i {
            font-size: 1.5rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        /* Footer */
        .footer {
            padding: 3rem 0;
            background: var(--text);
            color: white;
            text-align: center;
        }

        /* Animations */
        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        @keyframes scroll {
            0% { transform: translateY(0); }
            50% { transform: translateY(10px); }
            100% { transform: translateY(0); }
        }

        @media (max-width: 768px) {
            .navbar {
                width: calc(100% - 2rem);
                top: 1rem;
                padding: 1rem;
            }
            
            .nav-list {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .projects-grid, .skills-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="preloader">
        <div class="loader"></div>
    </div>

    <nav class="navbar">
        <ul class="nav-list">
            <li class="nav-item"><a href="#home" class="nav-link">Главная</a></li>
            <li class="nav-item"><a href="#skills" class="nav-link">Навыки</a></li>
            <li class="nav-item"><a href="#projects" class="nav-link">Проекты</a></li>
            <li class="nav-item"><a href="#contact" class="nav-link">Контакты</a></li>
        </ul>
    </nav>

    <main>
        <!-- Hero Section -->
        <section id="home" class="hero">
            <div class="container">
                <div class="hero-content">
                    <h1 class="hero-title" data-aos="fade-up" data-aos-delay="200">
                        Привет, я <span class="text-gradient">oonixxxxx</span>
                    </h1>
                    <p class="hero-subtitle" data-aos="fade-up" data-aos-delay="300">
                        Fullstack разработчик и UI дизайнер
                    </p>
                    <div class="scroll-indicator" data-aos="fade-up" data-aos-delay="400">
                        <div class="mouse"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="skills">
            <div class="container">
                <h2 class="section-title" data-aos="fade-up">Технологии</h2>
                <div class="skills-grid">
                    <div class="skill-card" data-aos="zoom-in">
                        <i class="fab fa-js"></i>
                        <h3>JavaScript</h3>
                        <p>React, Node.js, TypeScript</p>
                    </div>
                    <div class="skill-card" data-aos="zoom-in" data-aos-delay="100">
                        <i class="fab fa-python"></i>
                        <h3>Python</h3>
                        <p>Django, Data Analysis</p>
                    </div>
                    <div class="skill-card" data-aos="zoom-in" data-aos-delay="200">
                        <i class="fas fa-database"></i>
                        <h3>PostgreSQL</h3>
                        <p>Оптимизация и проектирование БД</p>
                    </div>
                    <div class="skill-card" data-aos="zoom-in" data-aos-delay="300">
                        <i class="fab fa-css3-alt"></i>
                        <h3>CSS</h3>
                        <p>Flexbox, Grid, Анимации</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="projects">
            <div class="container">
                <h2 class="section-title" data-aos="fade-up">Проекты</h2>
                <div class="projects-grid">
                    <article class="project-card" data-aos="fade-up">
                        <div class="project-image">
                            <img src="https://source.unsplash.com/random/800x600?code" alt="Проект" loading="lazy">
                        </div>
                        <div class="project-content">
                            <h3>Messenger</h3>
                            <p>Blue Messenger Pro: a fast and secure messenger built with Java, React & PostgreSQL. Communicate easily, share files, and stay confident in your data's security. Reliable, fast, & modern!</p>
                            <ul class="tech-list">
                                <li>JavaScript</li>
                                <li>CSS</li>
                                <li>HTML</li>
                                <li>Dockerfile</li>
                                <li>Java</li>
                            </ul>
                        </div>
                    </article>

                    <article class="project-card" data-aos="fade-up" data-aos-delay="100">
                        <div class="project-image">
                            <img src="https://source.unsplash.com/random/800x600?app" alt="Проект" loading="lazy">
                        </div>
                        <div class="project-content">
                            <h3>Flask Authentication App</h3>
                            <p>Это простое веб-приложение на Flask, которое демонстрирует базовую аутентификацию пользователей. Приложение позволяет пользователям регистрироваться, входить в систему и просматривать защищенные страницы.</p>
                            <ul class="tech-list">
                                <li>HTML</li>
                                <li>Python</li>
                                <li>CSS</li>
                            </ul>
                        </div>
                    </article>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="contact">
            <div class="container">
                <h2 class="section-title" data-aos="fade-up">Контакты</h2>
                <div class="social-grid">
                    <a href="https://github.com/oonixxxxx" class="social-card" data-aos="zoom-in">
                        <i class="fab fa-github"></i>
                        <span>GitHub</span>
                    </a>
                    <a href="https://t.me/onixexe" class="social-card" data-aos="zoom-in" data-aos-delay="100">
                        <i class="fab fa-telegram"></i>
                        <span>Telegram</span>
                    </a>
                    <a href="https://linkedin.com" class="social-card" data-aos="zoom-in" data-aos-delay="200">
                        <i class="fab fa-linkedin"></i>
                        <span>LinkedIn</span>
                    </a>
                    <a href="https://youtube.com" class="social-card" data-aos="zoom-in" data-aos-delay="300">
                        <i class="fab fa-youtube"></i>
                        <span>YouTube</span>
                    </a>
                </div>
            </div>
        </section>
    </main>

    <footer class="footer">
        <div class="container">
            <p>© 2024 oonixxxxx. Все права защищены</p>
        </div>
    </footer>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Инициализация AOS
            AOS.init({
                duration: 800,
                once: true,
                easing: 'ease-out',
                offset: 100
            });

            // Плавная прокрутка
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth',
                            block: 'start'
                        });
                    }
                });
            });

            // Прелоадер
            window.addEventListener('load', () => {
                const preloader = document.querySelector('.preloader');
                if (preloader) {
                    preloader.style.opacity = '0';
                    setTimeout(() => preloader.remove(), 500);
                }
            });

            // Параллакс эффект для карточек проектов
            document.querySelectorAll('.project-card').forEach(card => {
                card.addEventListener('mousemove', (e) => {
                    const rect = card.getBoundingClientRect();
                    const x = e.clientX - rect.left;
                    const y = e.clientY - rect.top;
                    card.style.transform = `
                        perspective(1000px)
                        rotateX(${(y - rect.height/2)/30}deg)
                        rotateY(${-(x - rect.width/2)/30}deg)
                    `;
                });

                card.addEventListener('mouseleave', () => {
                    card.style.transform = 'none';
                });
            });
        });
    </script>
</body>
</html>
