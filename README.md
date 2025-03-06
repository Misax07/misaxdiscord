<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Misax Discord Community</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --main-color: #5865F2;
            --accent-color: #eb459e;
            --dark-bg: #1e1f26;
            --text-light: #ffffff;
            --card-bg: rgba(255, 255, 255, 0.05);
            --card-hover-bg: rgba(255, 255, 255, 0.1);
            --section-spacing: 8rem;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--dark-bg);
            color: var(--text-light);
            line-height: 1.8;
            scroll-behavior: smooth;
        }

        /* Header */
        .header {
            background: linear-gradient(135deg, var(--main-color), var(--accent-color));
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 10%, transparent 10.01%);
            background-size: 20px 20px;
            animation: moveBackground 60s linear infinite;
            opacity: 0.3;
        }

        @keyframes moveBackground {
            from { transform: translateY(0); }
            to { transform: translateY(-1000px); }
        }

        /* Navigation */
        .nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 5%;
            background: rgba(0, 0, 0, 0.3);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(15px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .nav .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--text-light);
            transition: color 0.3s ease;
        }

        .nav .logo:hover {
            color: var(--accent-color);
        }

        .nav .links {
            display: flex;
            gap: 2rem;
        }

        .nav a {
            color: white;
            text-decoration: none;
            padding: 0.8rem 1.5rem;
            border-radius: 8px;
            transition: all 0.3s;
            font-weight: 500;
            position: relative;
        }

        .nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 0;
            height: 2px;
            background: var(--text-light);
            transition: all 0.3s;
        }

        .nav a:hover::after {
            width: 100%;
            left: 0;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 2rem;
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 5rem;
            margin-bottom: 1.5rem;
            color: var(--text-light);
            text-shadow: 0 0 30px rgba(88, 101, 242, 0.5);
            animation: textFloat 3s ease-in-out infinite;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.5rem;
            max-width: 800px;
            margin: 0 auto 2rem;
            color: rgba(255, 255, 255, 0.9);
            animation: fadeInUp 1.5s ease-out;
        }

        @keyframes textFloat {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* About Section */
        .about {
            padding: var(--section-spacing) 5%;
            background: var(--dark-bg);
        }

        .about-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            gap: 3rem;
        }

        .about-text {
            flex: 1;
        }

        .about-text h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
        }

        .about-text p {
            font-size: 1.1rem;
            line-height: 1.8;
            color: rgba(255, 255, 255, 0.9);
        }

        .about-image {
            flex: 1;
            text-align: center;
        }

        .about-image img {
            max-width: 100%;
            border-radius: 15px;
        }

        /* Features Section */
        .features {
            padding: var(--section-spacing) 5%;
            background: rgba(0, 0, 0, 0.2);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .feature-card {
            background: var(--card-bg);
            padding: 3rem 2rem;
            border-radius: 20px;
            text-align: center;
            transition: all 0.4s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            background: var(--card-hover-bg);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        .feature-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            color: var(--main-color);
            transition: transform 0.3s;
        }

        .feature-card:hover .feature-icon {
            transform: scale(1.1);
        }

        /* FAQ Section */
        .faq {
            padding: var(--section-spacing) 5%;
            background: var(--dark-bg);
        }

        .faq-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .faq-item {
            background: var(--card-bg);
            padding: 1.5rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            transition: all 0.3s;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .faq-item:hover {
            transform: translateY(-3px);
            background: var(--card-hover-bg);
        }

        .faq-item h3 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }

        .faq-item p {
            color: rgba(255, 255, 255, 0.8);
        }

        /* Join Section */
        .join {
            text-align: center;
            padding: var(--section-spacing) 5%;
            background: linear-gradient(135deg, var(--main-color), var(--accent-color));
            position: relative;
            overflow: hidden;
        }

        .join::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 10%, transparent 10.01%);
            background-size: 20px 20px;
            animation: moveBackground 30s linear infinite;
            opacity: 0.3;
            pointer-events: none;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 1rem;
            padding: 1.5rem 3rem;
            background: var(--main-color);
            color: white;
            text-decoration: none;
            border-radius: 12px;
            font-weight: bold;
            transition: all 0.3s;
            margin: 2rem 0;
            animation: pulse 2s infinite;
            border: 2px solid transparent;
            font-size: 1.1rem;
        }

        .cta-button:hover {
            background: transparent;
            border-color: var(--main-color);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(88, 101, 242, 0.4);
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Footer */
        .footer {
            padding: 3rem 5%;
            text-align: center;
            background: rgba(0, 0, 0, 0.3);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 3rem;
            }

            .nav .links {
                gap: 1rem;
            }

            .about-content {
                flex-direction: column;
                text-align: center;
            }

            .features-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <nav class="nav">
        <div class="logo">MISAX</div>
        <div class="links">
            <a href="#about">O Nás</a>
            <a href="#features">Výhody</a>
            <a href="#faq">FAQ</a>
            <a href="#join">Připojit se</a>
        </div>
    </nav>

    <header class="header">
        <div class="hero">
            <h1>🌟 Vítejte na Misax Discordu! 🌟</h1>
            <p>Připojte se k naší skvělé komunitě hráčů, vývojářů a kreativních myslí! 🚀</p>
        </div>
    </header>

    <section class="about" id="about">
        <div class="about-content">
            <div class="about-text">
                <h2>O Nás</h2>
                <p>
                    Misax Discord je komunita, která spojuje lidi z celého světa. Naším cílem je vytvořit přátelské a podporující prostředí pro hráče, vývojáře a všechny, kteří sdílejí společnou vášeň pro hry a technologie.
                </p>
            </div>
            <div             </div>
        </div>
    </section>

    <section class="features" id="features">
        <h2 class="section-title">Naše Výhody</h2>
        <div class="features-grid">
            <div class="feature-card">
                <i class="fas fa-gamepad feature-icon"></i>
                <h3>Herní Hub</h3>
                <p>Pravidelné herní sezení, turnaje a hlasové kanály pro vaše oblíbené hry.</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-code feature-icon"></i>
                <h3>Vývojářská Podpora</h3>
                <p>Získejte podporu pro své programovací projekty a spolupracujte s dalšími vývojáři.</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-users feature-icon"></i>
                <h3>Aktivní Komunita</h3>
                <p>50+ členů a stále rosteme. Přátelská atmosféra a ochotný tým.</p>
            </div>
        </div>
    </section>

    <section class="faq" id="faq">
        <h2 class="section-title">Často Kladené Otázky</h2>
        <div class="faq-content">
            <div class="faq-item">
                <h3>Jak se mohu připojit?</h3>
                <p>Stačí kliknout na tlačítko "Připojit se" a následovat odkaz na náš Discord server.</p>
            </div>
            <div class="faq-item">
                <h3>Je účast zdarma?</h3>
                <p>Ano, naše komunita je zcela zdarma a otevřená pro všechny.</p>
            </div>
            <div class="faq-item">
                <h3>Jaké hry hrajeme?</h3>
                <p>Hrajeme širokou škálu her od FPS po strategie. Vždy najdete někoho, kdo hraje to, co vás baví.</p>
            </div>
        </div>
    </section>

    <section class="join" id="join">
        <h2>Chcete se připojit?</h2>
        <p>Klikněte na tlačítko níže a staňte se součástí naší komunity!</p>
        <a href="https://discord.com/invite/y2q8NrJD8w" class="cta-button" target="_blank">
            <i class="fas fa-door-open"></i> Připojit se
        </a>
    </section>

    <footer class="footer">
        <p>&copy; 2025 Misax Community. Všechna práva vyhrazena.</p>
    </footer>
</body>
</html>
