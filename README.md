
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
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f5f5f5;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background-color: #2c3e50;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 5%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.3rem;
            font-weight: bold;
            color: white;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: white;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #87CEEB;
        }

        /* Sections */
        section {
            padding: 100px 0;
            min-height: 100vh;
            display: flex;
            align-items: center;
        }

        /* Accueil */
        #accueil {
            background: linear-gradient(135deg, #87CEEB, #5F9EA0);
            text-align: center;
            color: white;
        }

        .hero h1 {
            font-size: 2.8rem;
            margin-bottom: 1rem;
            color: #2c3e50;
        }

        .hero p {
            font-size: 1.3rem;
            max-width: 600px;
            margin: 0 auto 2rem;
            color: #2c3e50;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: #2c3e50;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.3s;
            border: none;
            cursor: pointer;
            font-weight: 500;
        }

        .btn:hover {
            background-color: #1a252f;
        }

        /* À propos */
        #apropos {
            background-color: white;
        }

        .apropos-content {
            display: flex;
            align-items: center;
            gap: 4rem;
        }

        .apropos-text {
            flex: 1;
        }

        .apropos-text h2 {
            font-size: 2.2rem;
            margin-bottom: 1.5rem;
            color: #2c3e50;
            border-bottom: 3px solid #5F9EA0;
            padding-bottom: 0.5rem;
            display: inline-block;
        }

        .apropos-text p {
            color: #555;
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2rem;
        }

        .skill {
            background-color: #87CEEB;
            padding: 8px 20px;
            border-radius: 20px;
            color: #2c3e50;
            font-weight: 600;
            font-size: 0.95rem;
        }

        .apropos-image {
            flex: 1;
            display: flex;
            justify-content: center;
        }

        .apropos-image img {
            width: 80%;
            max-width: 300px;
            height: auto;
            border-radius: 10px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            border: 3px solid #87CEEB;
        }

        /* Contact */
        #contact {
            background-color: #f8f9fa;
            text-align: center;
        }

        #contact h2 {
            font-size: 2.2rem;
            margin-bottom: 1rem;
            color: #2c3e50;
        }

        .contact-content > p {
            color: #666;
            font-size: 1.2rem;
            margin-bottom: 3rem;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }

        .contact-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .contact-card:hover {
            transform: translateY(-5px);
        }

        .contact-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            display: inline-block;
        }

        .contact-card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #2c3e50;
        }

        .contact-card p {
            color: #666;
            margin-bottom: 1.5rem;
            word-break: break-word;
        }

        .contact-link {
            display: inline-block;
            padding: 10px 25px;
            background-color: #5F9EA0;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.3s;
            font-weight: 500;
            border: none;
            cursor: pointer;
        }

        .contact-link:hover {
            background-color: #4682B4;
        }

        .card-whatsapp .contact-link {
            background-color: #25D366;
        }

        .card-whatsapp .contact-link:hover {
            background-color: #128C7E;
        }

        .card-phone .contact-link {
            background-color: #5F9EA0;
        }

        .card-email .contact-link {
            background-color: #4682B4;
        }

        .contact-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 2rem;
        }

        .contact-links .contact-link {
            background-color: #2c3e50;
            min-width: 120px;
        }

        .contact-links .contact-link:hover {
            background-color: #1a252f;
        }

        /* Footer */
        footer {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 1.5rem 0;
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 0.5rem;
            }

            .nav-links {
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .apropos-content {
                flex-direction: column-reverse;
                text-align: center;
                gap: 2rem;
            }

            .skills {
                justify-content: center;
            }

            .apropos-image img {
                width: 70%;
                max-width: 250px;
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

            .apropos-text h2 {
                font-size: 1.8rem;
            }

            .contact-card {
                padding: 1.5rem;
            }
        }
    </style>
</head>
<body>
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
            <a href="#apropos" class="btn">En savoir plus</a>
        </div>
    </section>

    <section id="apropos">
        <div class="container apropos-content">
            <div class="apropos-text">
                <h2>À propos de moi</h2>
                <p>Je suis un développeur passionné par le site web. J'aime transformer des idées créatives en solutions numériques fonctionnelles. J'ai acquis des bases en programmation (HTML, CSS, JavaScript).</p>
                <p>Motivé, sérieux et curieux d'apprendre, je cherche une opportunité qui me permettra de développer mes compétences pratiques et de mieux comprendre le fonctionnement des sites web simples, ce qui m'aide à développer ma logique et ma créativité.</p>
                <p>Je reste à votre disposition pour un entretien et vous remercie de l'attention portée à ma candidature.</p>
                <p>Ma philosophie est simple : "La technologie construit le système, l'expérience construit la relation".</p>
                <div class="skills">
                    <span class="skill">HTML</span>
                    <span class="skill">CSS</span>
                    <span class="skill">JavaScript</span>
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
            <div style="margin-top: 2rem;">
                <p style="margin-bottom: 1rem; color: #666;">Ou retrouvez-moi sur :</p>
                <div class="contact-links">
                    <a href="#" class="contact-link" style="background-color: #0077b5;">LinkedIn</a>
                    <a href="#" class="contact-link" style="background-color: #333;">GitHub</a>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2026 RATIANARIVO Mirindra Matthieu. Tous droits réservés.</p>
        </div>
    </footer>
</body>
</html>
