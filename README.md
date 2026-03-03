
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - RATIANARIVO Mirindra Matthieu</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #2d3436;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Animations sophistiquées */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-40px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(40px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }

        @keyframes glow {
            0%, 100% {
                box-shadow: 0 0 20px rgba(102, 126, 234, 0.3);
            }
            50% {
                box-shadow: 0 0 40px rgba(102, 126, 234, 0.6);
            }
        }

        @keyframes gradientShift {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }

        /* Header élégant */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            animation: fadeInUp 0.8s ease;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 600;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-decoration: none;
            position: relative;
            transition: all 0.3s;
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            transition: width 0.3s;
        }

        .logo:hover::after {
            width: 100%;
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #2d3436;
            font-weight: 500;
            position: relative;
            transition: all 0.3s;
        }

        .nav-links a::before {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            transition: width 0.3s;
        }

        .nav-links a:hover {
            color: #667eea;
            transform: translateY(-2px);
        }

        .nav-links a:hover::before {
            width: 100%;
        }

        /* Sections */
        section {
            padding: 120px 0;
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: gradientShift 15s ease infinite;
            pointer-events: none;
        }

        /* Accueil */
        #accueil {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            text-align: center;
            color: white;
            position: relative;
        }

        .hero {
            animation: scaleIn 1s ease;
        }

        .hero h1 {
            font-size: 3.2rem;
            margin-bottom: 1rem;
            font-weight: 700;
            animation: fadeInUp 1s ease;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        .hero p {
            font-size: 1.4rem;
            max-width: 700px;
            margin: 0 auto 2.5rem;
            opacity: 0.9;
            animation: fadeInUp 1s ease 0.2s both;
            font-weight: 300;
        }

        .btn {
            display: inline-block;
            padding: 15px 40px;
            background: white;
            color: #667eea;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            animation: fadeInUp 1s ease 0.4s both, float 3s ease-in-out infinite;
        }

        .btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 20px 30px rgba(0,0,0,0.3);
            background: #f8f9fa;
        }

        /* À propos */
        #apropos {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }

        .apropos-content {
            display: flex;
            align-items: center;
            gap: 4rem;
        }

        .apropos-text {
            flex: 1;
            animation: fadeInLeft 1s ease;
        }

        .apropos-text h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            display: inline-block;
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 3px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 3px;
        }

        .apropos-text p {
            color: #4a5568;
            margin-bottom: 1.2rem;
            font-size: 1.1rem;
            line-height: 1.8;
            transition: all 0.3s;
            padding: 10px;
            border-radius: 10px;
        }

        .apropos-text p:hover {
            background: rgba(102, 126, 234, 0.1);
            transform: translateX(10px);
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2.5rem;
        }

        .skill {
            padding: 10px 25px;
            background: white;
            border-radius: 50px;
            color: #667eea;
            font-weight: 600;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.2);
            transition: all 0.3s;
            cursor: default;
            animation: scaleIn 0.5s ease;
            border: 1px solid rgba(102, 126, 234, 0.2);
        }

        .skill:hover {
            transform: translateY(-3px) scale(1.05);
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        .apropos-image {
            flex: 1;
            display: flex;
            justify-content: center;
            animation: fadeInRight 1s ease;
        }

        .apropos-image img {
            width: 80%;
            max-width: 350px;
            height: auto;
            border-radius: 20px;
            box-shadow: 0 30px 40px rgba(0,0,0,0.2);
            transition: all 0.5s;
            border: 4px solid white;
            animation: float 6s ease-in-out infinite;
        }

        .apropos-image img:hover {
            transform: scale(1.05) rotate(2deg);
            box-shadow: 0 40px 60px rgba(102, 126, 234, 0.4);
        }

        /* Contact */
        #contact {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
            position: relative;
        }

        #contact h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        .contact-content > p {
            font-size: 1.3rem;
            margin-bottom: 3rem;
            opacity: 0.9;
            animation: fadeInUp 1s ease 0.2s both;
            font-weight: 300;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2.5rem 2rem;
            border-radius: 20px;
            transition: all 0.4s;
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: scaleIn 0.8s ease;
            animation-fill-mode: both;
        }

        .contact-card:nth-child(1) { animation-delay: 0.2s; }
        .contact-card:nth-child(2) { animation-delay: 0.4s; }
        .contact-card:nth-child(3) { animation-delay: 0.6s; }

        .contact-card:hover {
            transform: translateY(-15px) scale(1.03);
            background: rgba(255, 255, 255, 0.2);
            border-color: rgba(255, 255, 255, 0.4);
            box-shadow: 0 30px 40px rgba(0,0,0,0.2);
        }

        .contact-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            animation: float 4s ease-in-out infinite;
        }

        .contact-card:hover .contact-icon {
            animation: glow 2s ease-in-out infinite;
        }

        .contact-card h3 {
            font-size: 1.6rem;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .contact-card p {
            margin-bottom: 1.5rem;
            opacity: 0.9;
            font-size: 1.1rem;
            word-break: break-word;
        }

        .contact-link {
            display: inline-block;
            padding: 12px 30px;
            background: white;
            color: #667eea;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .contact-link:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 15px 25px rgba(0,0,0,0.3);
            background: #f8f9fa;
        }

        .card-whatsapp .contact-link {
            background: #25D366;
            color: white;
        }

        .card-whatsapp .contact-link:hover {
            background: #128C7E;
        }

        .card-phone .contact-link {
            background: #5F9EA0;
            color: white;
        }

        .card-email .contact-link {
            background: #4682B4;
            color: white;
        }

        .contact-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 2rem;
        }

        .contact-links .contact-link {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.3);
            min-width: 140px;
            animation: fadeInUp 0.8s ease;
            animation-fill-mode: both;
        }

        .contact-links .contact-link:nth-child(1) { animation-delay: 0.8s; }
        .contact-links .contact-link:nth-child(2) { animation-delay: 1s; }

        .contact-links .contact-link:hover {
            background: white;
            color: #667eea;
            transform: translateY(-3px) scale(1.05);
        }

        /* Footer */
        footer {
            background: #2d3436;
            color: white;
            text-align: center;
            padding: 2rem 0;
            position: relative;
            overflow: hidden;
        }

        footer p {
            opacity: 0.9;
            font-size: 1.1rem;
            animation: fadeInUp 1s ease;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #667eea, transparent);
            animation: slide 3s linear infinite;
        }

        @keyframes slide {
            0% {
                left: -100%;
            }
            100% {
                left: 100%;
            }
        }

        /* Particules de fond */
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: particleFloat 20s infinite linear;
        }

        @keyframes particleFloat {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 0.8rem;
            }

            .nav-links {
                gap: 1.5rem;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .apropos-content {
                flex-direction: column-reverse;
                text-align: center;
                gap: 2rem;
            }

            .apropos-text h2::after {
                left: 50%;
                transform: translateX(-50%);
            }

            .skills {
                justify-content: center;
            }

            .logo {
                font-size: 1.3rem;
            }

            .contact-cards {
                grid-template-columns: 1fr;
                max-width: 400px;
                margin-left: auto;
                margin-right: auto;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.8rem;
            }

            .btn {
                padding: 12px 30px;
                font-size: 1rem;
            }

            .contact-card {
                padding: 2rem 1.5rem;
            }

            .contact-link {
                padding: 10px 25px;
                font-size: 0.95rem;
            }
        }

        /* Scrollbar personnalisée */
        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }

        ::-webkit-scrollbar-thumb {
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 5px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(135deg, #764ba2, #667eea);
        }
    </style>
</head>
<body>
    <div class="particles">
        <div class="particle" style="width: 3px; height: 3px; left: 10%; animation-duration: 15s;"></div>
        <div class="particle" style="width: 4px; height: 4px; left: 30%; animation-duration: 18s;"></div>
        <div class="particle" style="width: 2px; height: 2px; left: 50%; animation-duration: 12s;"></div>
        <div class="particle" style="width: 5px; height: 5px; left: 70%; animation-duration: 20s;"></div>
        <div class="particle" style="width: 3px; height: 3px; left: 90%; animation-duration: 14s;"></div>
    </div>

    <header>
        <nav>
            <a href="#accueil" class="logo">RATIANARIVO Mirindra Matthieu</a>
            <div class="nav-links">
                <a href="#accueil">Accueil</a>
                <a href="#apropos">À propos</a>
                <a href="#contact">Contact</a>
            </div>
        </nav>
    </header>

    <section id="accueil">
        <div class="container hero">
            <h1>Bonjour, je suis RATIANARIVO Mirindra Matthieu</h1>
            <p>Développeur créatif passionné par la création d'expériences web uniques et mémorables</p>
            <a href="#apropos" class="btn">Découvrir mon univers</a>
        </div>
    </section>

    <section id="apropos">
        <div class="container apropos-content">
            <div class="apropos-text">
                <h2>À propos de moi</h2>
                <p>Je suis un développeur passionné par le site web. J'aime transformer des idées créatives en solutions numériques fonctionnelles. J'ai acquis des bases en programmation (HTML, CSS, JavaScript).</p>
                <p>Motivé, sérieux et curieux d'apprendre, je cherche une opportunité qui me permettra de développer mes compétences pratiques et de mieux comprendre le fonctionnement des sites web simples, ce qui m'aide à développer ma logique et ma créativité.</p>
                <p>Je reste à votre disposition pour un entretien et vous remercie de l'attention portée à ma candidature.</p>
                <p>Ma philosophie est simple : <em>"La technologie construit le système, l'expérience construit la relation".</em></p>
                <div class="skills">
                    <span class="skill">HTML5</span>
                    <span class="skill">CSS3</span>
                    <span class="skill">JavaScript</span>
                    <span class="skill">Responsive Design</span>
                </div>
            </div>
            <div class="apropos-image">
                <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/642754626_122112963513211419_7763551596132436351_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=HrPMD1Mzk-wQ7kNvwF-W0Kk&_nc_oc=AdmitmpVlD_NkLZbjv5bb1BdGCCLKrDWIu8jwSkutlrW38sKkCh-4igqUNpNQk8v2sg&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=UrnADD8nIJ14FGwl_Mt82Q&_nc_ss=8&oh=00_AfxextLBeI-e-uEMJr1xXOL4FM1WFzyiLwUla6pesQhiMA&oe=69AAF757" alt="Photo de profil">
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container contact-content">
            <h2>Travaillons ensemble</h2>
            <p>Vous avez un projet en tête ? N'hésitez pas à me contacter !</p>
            
            <div class="contact-cards">
                <!-- Carte WhatsApp -->
                <div class="contact-card card-whatsapp">
                    <span class="contact-icon">📱</span>
                    <h3>WhatsApp</h3>
                    <p>+261 38 62 876 80</p>
                    <a href="https://wa.me/261386287680?text=Bonjour%20Matthieu%2C%20je%20souhaite%20vous%20contacter%20pour%20un%20projet" 
                       class="contact-link" 
                       target="_blank">
                        Envoyer un message
                    </a>
                </div>

                <!-- Carte Téléphone -->
                <div class="contact-card card-phone">
                    <span class="contact-icon">📞</span>
                    <h3>Téléphone</h3>
                    <p>+261 38 62 876 80</p>
                    <a href="tel:+261386287680" class="contact-link">
                        Appeler maintenant
                    </a>
                </div>

                <!-- Carte Email -->
                <div class="contact-card card-email">
                    <span class="contact-icon">✉️</span>
                    <h3>Email</h3>
                    <p>mirindramatthieu@gmail.com</p>
                    <a href="mailto:mirindramatthieu@gmail.com?subject=Contact%20depuis%20mon%20portfolio&body=Bonjour%20Matthieu%2C" 
                       class="contact-link">
                        Envoyer un email
                    </a>
                </div>
            </div>

            <!-- Liens sociaux supplémentaires -->
            <div style="margin-top: 3rem;">
                <p style="margin-bottom: 1.5rem; opacity: 0.9; font-size: 1.1rem;">Ou retrouvez-moi sur :</p>
                <div class="contact-links">
                    <a href="#" class="contact-link">LinkedIn</a>
                    <a href="#" class="contact-link">GitHub</a>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2026 RATIANARIVO Mirindra Matthieu. Tous droits réservés.</p>
        </div>
    </footer>

    <script>
        // Animation smooth scroll pour les liens
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
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

        // Animation au scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('section, .contact-card, .skill').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
