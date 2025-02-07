# Clinic<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Serenity Flow | Массажный салон</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        /* Глобальные стили */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Nunito Sans', sans-serif;
        }

        body {
            background: #FFF9F0;
            color: #4A4A4A;
        }

        /* Шапка */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(245, 230, 211, 0.7), rgba(255, 249, 240, 0.9)),
                        url('https://images.unsplash.com/photo-1544161515-4ab6ce6db874?ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80');
            background-size: cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 20px;
        }

        .hero-content {
            max-width: 800px;
        }

        .hero h1 {
            font-size: 4rem;
            color: #6BA2A5;
            margin-bottom: 20px;
            animation: fadeIn 1.5s;
        }

        .tagline {
            font-size: 1.5rem;
            color: #D57E6B;
            margin-bottom: 40px;
        }

        /* Кнопка */
        .cta-button {
            display: inline-block;
            padding: 15px 40px;
            background: #6BA2A5;
            color: white;
            text-decoration: none;
            border-radius: 30px;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(107, 162, 165, 0.4);
        }

        /* Услуги */
        .services {
            padding: 80px 20px;
            background: #F5E6D3;
        }

        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .service-card {
            background: white;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .service-card h3 {
            color: #6BA2A5;
            margin: 20px 0;
            font-size: 1.5rem;
        }

        /* О нас */
        .about {
            padding: 80px 20px;
            display: flex;
            align-items: center;
            gap: 50px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .about-image {
            flex: 1;
            border-radius: 15px;
            overflow: hidden;
        }

        .about-image img {
            width: 100%;
            height: auto;
        }

        .about-text {
            flex: 1;
        }

        /* Футер */
        footer {
            background: #6BA2A5;
            color: white;
            padding: 40px 20px;
            text-align: center;
        }

        /* Анимации */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .about {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Шапка -->
    <section class="hero">
        <div class="hero-content">
            <h1>Serenity Flow</h1>
            <p class="tagline">Где тело и разум находят покой</p>
            <a href="#contact" class="cta-button">Записаться онлайн</a>
        </div>
    </section>

    <!-- Услуги -->
    <section class="services">
        <div class="service-grid">
            <div class="service-card">
                <h3>🕯️ Классический массаж</h3>
                <p>Снятие напряжения мышц и улучшение кровообращения</p>
            </div>
            <div class="service-card">
                <h3>🌿 Ароматерапия</h3>
                <p>Комплекс релаксации с эфирными маслами</p>
            </div>
            <div class="service-card">
                <h3>💆 СПА-ритуалы</h3>
                <p>Многокомпонентные программы для тела</p>
            </div>
        </div>
    </section>

    <!-- О нас -->
    <section class="about">
        <div class="about-image">
            <img src="<iframe src="https://assets.pinterest.com/ext/embed.html?id=847591592405472120" height="359" width="345" frameborder="0" scrolling="no" ></iframe>" alt="Интерьер салона">
        </div>
        <div class="about-text">
            <h2>Наш салон</h2>
            <p>Пространство гармонии с натуральными материалами, мягким светом и индивидуальным подходом к каждому гостю.</p>
        </div>
    </section>

    <!-- Футер -->
    <footer id="contact">
        <p>📍 Адрес: Бескудниковский бульвар  11 к.1 </p>
        <p>📞 +7 (915)1311104 </p>
        <p>🕒 Ежедневно с 10:00 до 22:00</p>
    </footer>

    <script>
        // Плавный скролл
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Анимация карточек при скролле
        const cards = document.querySelectorAll('.service-card');
        const observer = new IntersectionObserver(entries => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });

        cards.forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(20px)';
            observer.observe(card);
        });
    </script>
</body>
</html>
