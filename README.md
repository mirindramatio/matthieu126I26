<!DOCTYPE html>
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
            color: #2c3e50;
            background: linear-gradient(135deg, #e3f2fd 0%, #bbdef5 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Animations douces */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
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
            0% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-8px);
            }
            100% {
                transform: translateY(0px);
            }
        }

        @keyframes shimmer {
            0% {
                background-position: -200% 0;
            }
            100% {
                background-position: 200% 0;
            }
        }

        @keyframes borderGlow {
            0%, 100% {
                box-shadow: 0 0 5px rgba(135, 206, 235, 0.3);
            }
            50% {
                box-shadow: 0 0 20px rgba(135, 206, 235, 0.6);
            }
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
            100% {
                transform: scale(1);
            }
        }

        @keyframes clockPulse {
            0% {
                opacity: 0.7;
                transform: scale(1);
            }
            50% {
                opacity: 1;
                transform: scale(1.1);
            }
            100% {
                opacity: 0.7;
                transform: scale(1);
            }
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 20px rgba(135, 206, 235, 0.2);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            animation: fadeIn 1s ease-out;
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
            color: #2c3e50;
            text-decoration: none;
            transition: all 0.3s;
            position: relative;
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, #87CEEB, #5F9EA0);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.3s;
        }

        .logo:hover {
            color: #5F9EA0;
        }

        .logo:hover::after {
            transform: scaleX(1);
            transform-origin: left;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #2c3e50;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
        }

        .nav-links a::before {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: #87CEEB;
            transform: scaleX(0);
            transition: transform 0.3s;
        }

        .nav-links a:hover {
            color: #5F9EA0;
        }

        .nav-links a:hover::before {
            transform: scaleX(1);
        }

        /* Sections */
        section {
            padding: 100px 0;
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
        }

        /* Accueil */
        #accueil {
            background: linear-gradient(135deg, #b8e1fc, #9ac9f0);
            text-align: center;
            animation: fadeIn 1.2s ease-out;
        }

        .hero {
            animation: scaleIn 1s ease-out;
        }

        .hero h1 {
            font-size: 2.8rem;
            margin-bottom: 1rem;
            color: #2c3e50;
            animation: float 4s ease-in-out infinite;
        }

        .hero p {
            font-size: 1.3rem;
            max-width: 600px;
            margin: 0 auto 2rem;
            color: #2c3e50;
            opacity: 0;
            animation: fadeIn 1s ease-out 0.3s forwards;
        }

        .btn {
            display: inline-block;
            padding: 12px 35px;
            background: linear-gradient(135deg, #5F9EA0, #4682B4);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            font-weight: 500;
            position: relative;
            overflow: hidden;
            animation: borderGlow 3s infinite;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(95, 158, 160, 0.4);
        }

        .btn:hover::before {
            left: 100%;
        }

        /* À propos */
        #apropos {
            background: linear-gradient(135deg, #ffffff, #f0f9ff);
            animation: fadeIn 1s ease-out;
        }

        .apropos-content {
            display: flex;
            align-items: center;
            gap: 4rem;
        }

        .apropos-text {
            flex: 1;
            animation: slideInLeft 1s ease-out;
        }

        .apropos-text h2 {
            font-size: 2.2rem;
            margin-bottom: 1.5rem;
            color: #2c3e50;
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
            background: linear-gradient(90deg, #87CEEB, #5F9EA0);
            border-radius: 3px;
        }

        .apropos-text p {
            color: #444;
            margin-bottom: 1rem;
            font-size: 1.1rem;
            transition: transform 0.3s;
        }

        .apropos-text p:hover {
            transform: translateX(10px);
            color: #5F9EA0;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2rem;
        }

        .skill {
            background: linear-gradient(135deg, #87CEEB, #b0e0e6);
            padding: 8px 25px;
            border-radius: 30px;
            color: #2c3e50;
            font-weight: 600;
            font-size: 0.95rem;
            transition: all 0.3s;
            animation: scaleIn 0.5s ease-out;
            animation-fill-mode: both;
            cursor: default;
            box-shadow: 0 4px 10px rgba(135, 206, 235, 0.3);
        }

        .skill:nth-child(1) { animation-delay: 0.2s; }
        .skill:nth-child(2) { animation-delay: 0.4s; }
        .skill:nth-child(3) { animation-delay: 0.6s; }

        .skill:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 8px 20px rgba(95, 158, 160, 0.4);
            background: linear-gradient(135deg, #5F9EA0, #87CEEB);
            color: white;
        }

        .apropos-image {
            flex: 1;
            display: flex;
            justify-content: center;
            animation: slideInRight 1s ease-out;
        }

        .apropos-image img {
            width: 80%;
            max-width: 300px;
            height: auto;
            border-radius: 20px;
            box-shadow: 0 20px 30px rgba(135, 206, 235, 0.3);
            transition: all 0.5s;
            border: 4px solid white;
            animation: float 5s ease-in-out infinite;
        }

        .apropos-image img:hover {
            transform: scale(1.05) rotate(2deg);
            box-shadow: 0 30px 40px rgba(95, 158, 160, 0.4);
        }

        /* Contact */
        #contact {
            background: linear-gradient(135deg, #f0f9ff, #e1f5fe);
            text-align: center;
            padding-bottom: 50px;
        }

        #contact h2 {
            font-size: 2.2rem;
            margin-bottom: 1rem;
            color: #2c3e50;
            animation: fadeIn 1s ease-out;
        }

        .contact-content > p {
            color: #555;
            font-size: 1.2rem;
            margin-bottom: 3rem;
            animation: fadeIn 1s ease-out 0.2s both;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
            animation: scaleIn 1s ease-out 0.4s both;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(5px);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(135, 206, 235, 0.2);
            transition: all 0.4s;
            border: 2px solid rgba(255, 255, 255, 0.8);
            animation: scaleIn 0.8s ease-out;
            animation-fill-mode: both;
        }

        .contact-card:nth-child(1) { animation-delay: 0.2s; }
        .contact-card:nth-child(2) { animation-delay: 0.4s; }
        .contact-card:nth-child(3) { animation-delay: 0.6s; }

        .contact-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 40px rgba(95, 158, 160, 0.3);
            border-color: #87CEEB;
            background: white;
        }

        .contact-icon {
            font-size: 2.8rem;
            margin-bottom: 1rem;
            display: inline-block;
            transition: transform 0.3s;
            animation: float 4s ease-in-out infinite;
        }

        .contact-card:hover .contact-icon {
            transform: scale(1.2);
        }

        .contact-card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #2c3e50;
            transition: color 0.3s;
        }

        .contact-card:hover h3 {
            color: #5F9EA0;
        }

        .contact-card p {
            color: #666;
            margin-bottom: 1.5rem;
            word-break: break-word;
        }

        .contact-link {
            display: inline-block;
            padding: 10px 25px;
            background: #5F9EA0;
            color: white;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s;
            font-weight: 500;
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .contact-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .contact-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(95, 158, 160, 0.4);
        }

        .contact-link:hover::before {
            left: 100%;
        }

        .card-whatsapp .contact-link {
            background: #25D366;
        }

        .card-whatsapp .contact-link:hover {
            background: #128C7E;
        }

        .card-phone .contact-link {
            background: #5F9EA0;
        }

        .card-email .contact-link {
            background: #4682B4;
        }

        .contact-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 2rem;
        }

        .contact-links .contact-link {
            background: #2c3e50;
            min-width: 120px;
            animation: scaleIn 0.5s ease-out;
            animation-fill-mode: both;
        }

        .contact-links .contact-link:nth-child(1) { animation-delay: 0.8s; }
        .contact-links .contact-link:nth-child(2) { animation-delay: 1s; }

        .contact-links .contact-link:hover {
            background: #1a252f;
            transform: translateY(-3px) scale(1.05);
        }

        /* Formulaire WhatsApp */
        .whatsapp-form-section {
            background: linear-gradient(135deg, #ffffff, #f8fdff);
            padding: 60px 0;
            border-top: 3px solid #87CEEB;
            border-bottom: 3px solid #87CEEB;
            animation: fadeIn 1.2s ease-out;
        }

        .whatsapp-form-container {
            max-width: 700px;
            margin: 0 auto;
            background: white;
            padding: 40px;
            border-radius: 30px;
            box-shadow: 0 20px 40px rgba(37, 211, 102, 0.15);
            border: 2px solid rgba(37, 211, 102, 0.1);
            animation: scaleIn 0.8s ease-out;
        }

        .whatsapp-header {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
        }

        .whatsapp-icon {
            font-size: 3.5rem;
            animation: pulse 2s infinite;
        }

        .whatsapp-header h3 {
            font-size: 2rem;
            color: #075E54;
            font-weight: 600;
        }

        .whatsapp-header h3 span {
            color: #25D366;
        }

        .whatsapp-subtitle {
            text-align: center;
            color: #555;
            margin-bottom: 30px;
            font-size: 1.1rem;
        }

        .whatsapp-form {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            text-align: left;
            gap: 8px;
        }

        .form-group label {
            font-weight: 600;
            color: #2c3e50;
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .form-group label i {
            font-size: 1.3rem;
        }

        .form-group input,
        .form-group textarea {
            padding: 15px 20px;
            border: 2px solid #e0e0e0;
            border-radius: 15px;
            font-size: 1rem;
            transition: all 0.3s;
            background: #f9f9f9;
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #25D366;
            box-shadow: 0 0 0 4px rgba(37, 211, 102, 0.1);
            background: white;
        }

        .form-group input:hover,
        .form-group textarea:hover {
            border-color: #25D366;
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .send-whatsapp-btn {
            background: linear-gradient(135deg, #25D366, #128C7E);
            color: white;
            border: none;
            padding: 18px 30px;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            position: relative;
            overflow: hidden;
            animation: borderGlow 3s infinite;
        }

        .send-whatsapp-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .send-whatsapp-btn:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 20px 40px rgba(37, 211, 102, 0.3);
        }

        .send-whatsapp-btn:hover::before {
            left: 100%;
        }

        .send-whatsapp-btn i {
            font-size: 1.5rem;
            animation: pulse 2s infinite;
        }

        .whatsapp-info {
            text-align: center;
            margin-top: 25px;
            padding-top: 25px;
            border-top: 2px dashed #25D366;
            color: #555;
            font-size: 0.95rem;
        }

        .whatsapp-info strong {
            color: #075E54;
        }

        .availability-badge {
            background: linear-gradient(135deg, #e8f5e9, #c8e6c9);
            color: #075E54;
            padding: 15px 20px;
            border-radius: 50px;
            font-weight: 600;
            margin-top: 15px;
            border: 2px solid #25D366;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            animation: pulse 3s infinite;
        }

        .availability-badge span {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 1.1rem;
        }

        .availability-badge .clock-icon {
            animation: clockPulse 2s infinite;
        }

        .time-slot {
            background: white;
            padding: 8px 15px;
            border-radius: 30px;
            color: #075E54;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .time-slot.morning {
            border-left: 4px solid #FFA500;
        }

        .time-slot.afternoon {
            border-left: 4px solid #2196F3;
        }

        .dispo-title {
            font-size: 1.2rem;
            color: #075E54;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
            justify-content: center;
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, #5F9EA0, #4682B4);
            color: white;
            text-align: center;
            padding: 1.5rem 0;
            position: relative;
            overflow: hidden;
        }

        footer p {
            animation: float 4s ease-in-out infinite;
            position: relative;
            z-index: 1;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            animation: shimmer 4s infinite;
        }

        /* Vague décorative */
        .wave-bg {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 80px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23ffffff" fill-opacity="0.2" d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,122.7C672,117,768,139,864,154.7C960,171,1056,181,1152,165.3C1248,149,1344,107,1392,85.3L1440,64L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-repeat: no-repeat;
            background-size: cover;
            opacity: 0.3;
            pointer-events: none;
            animation: wave 12s linear infinite;
        }

        @keyframes wave {
            0% {
                transform: translateX(0) scaleX(1);
            }
            50% {
                transform: translateX(-25%) scaleX(1.1);
            }
            100% {
                transform: translateX(0) scaleX(1);
            }
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

            .apropos-text h2::after {
                left: 50%;
                transform: translateX(-50%);
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

            .contact-card:hover {
                transform: translateY(-10px);
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .whatsapp-form-container {
                margin: 0 20px;
                padding: 30px 20px;
            }

            .whatsapp-header {
                flex-direction: column;
                gap: 10px;
            }

            .whatsapp-header h3 {
                font-size: 1.6rem;
            }

            .availability-badge {
                flex-direction: column;
                gap: 10px;
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

            .send-whatsapp-btn {
                padding: 15px 20px;
                font-size: 1rem;
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
        <div class="wave-bg"></div>
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
        <div class="wave-bg"></div>
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
                <p style="margin-bottom: 1rem; color: #555;">Ou retrouvez-moi sur :</p>
                <div class="contact-links">
                    <a href="#" class="contact-link" style="background: #0077b5;">LinkedIn</a>
                    <a href="#" class="contact-link" style="background: #333;">GitHub</a>
                </div>
            </div>
        </div>
        <div class="wave-bg"></div>
    </section>

    <!-- Formulaire WhatsApp direct avec horaires -->
    <section class="whatsapp-form-section">
        <div class="container">
            <div class="whatsapp-form-container">
                <div class="whatsapp-header">
                    <span class="whatsapp-icon">📱</span>
                    <h3>WhatsApp <span>Direct</span></h3>
                </div>
                
                <p class="whatsapp-subtitle">
                    Envoyez-moi un message directement sur WhatsApp en remplissant ce formulaire
                </p>

                <div class="whatsapp-form">
                    <div class="form-row">
                        <div class="form-group">
                            <label>
                                <span>👤</span> Votre nom
                            </label>
                            <input type="text" id="nom" placeholder="Ex: Jean Dupont" value="">
                        </div>

                        <div class="form-group">
                            <label>
                                <span>📞</span> Votre téléphone
                            </label>
                            <input type="tel" id="telephone" placeholder="Ex: 0341234567" value="">
                        </div>
                    </div>

                    <div class="form-group">
                        <label>
                            <span>✉️</span> Votre message
                        </label>
                        <textarea id="message" placeholder="Bonjour Matthieu, je souhaite vous contacter pour...">Bonjour Matthieu, je souhaite vous contacter pour un projet.</textarea>
                    </div>

                    <button class="send-whatsapp-btn" id="sendWhatsAppBtn">
                        <span>📤</span>
                        Envoyer sur WhatsApp
                        <span>➡️</span>
                    </button>

                    <div class="whatsapp-info">
                        <p>📱 <strong>Mon numéro WhatsApp :</strong> +261 38 62 876 80</p>
                        
                        <!-- Nouveau badge de disponibilité avec horaires -->
                        <div class="availability-badge">
                            <div class="dispo-title">
                                <span class="clock-icon">⏰</span>
                                <strong>Toujours disponible aux horaires :</strong>
                            </div>
                            <div style="display: flex; gap: 15px; flex-wrap: wrap; justify-content: center;">
                                <span class="time-slot morning">
                                    <span>🌅</span> MATIN : 8H - 12H
                                </span>
                                <span class="time-slot afternoon">
                                    <span>☀️</span> MIDI : 14H - 18H
                                </span>
                            </div>
                            <div style="margin-top: 10px; font-size: 0.95rem; color: #075E54;">
                                ⚡ Réponse rapide garantie pendant ces créneaux
                            </div>
                        </div>

                        <!-- Message de disponibilité -->
                        <div style="margin-top: 15px; background: #fff3e0; padding: 10px; border-radius: 10px; border-left: 4px solid #FFA500;">
                            <p style="margin: 0; color: #BF360C;">
                                <span>💬</span> Je réponds généralement dans l'heure pendant mes horaires de disponibilité
                            </p>
                        </div>
                    </div>
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
        // Fonction pour envoyer le message WhatsApp
        document.getElementById('sendWhatsAppBtn').addEventListener('click', function() {
            // Récupérer les valeurs du formulaire
            var nom = document.getElementById('nom').value.trim();
            var telephone = document.getElementById('telephone').value.trim();
            var message = document.getElementById('message').value.trim();
            
            // Vérifier si les champs obligatoires sont remplis
            if (nom === '') {
                alert('Veuillez entrer votre nom');
                return;
            }
            
            if (message === '') {
                alert('Veuillez entrer votre message');
                return;
            }
            
            // Numéro WhatsApp (format international sans +)
            var whatsappNumber = '261386287680';
            
            // Construire le message avec les informations
            var texteMessage = `*Nouveau message depuis le portfolio*%0A%0A`;
            texteMessage += `👤 *Nom :* ${nom}%0A`;
            
            if (telephone !== '') {
                texteMessage += `📞 *Téléphone :* ${telephone}%0A`;
            }
            
            texteMessage += `%0A📝 *Message :*%0A${message}%0A%0A`;
            texteMessage += `_Message envoyé via le formulaire WhatsApp direct_`;
            
            // Encoder le message pour l'URL
            var url = `https://wa.me/${whatsappNumber}?text=${texteMessage}`;
            
            // Ouvrir WhatsApp dans un nouvel onglet
            window.open(url, '_blank');
        });

        // Animation supplémentaire pour le bouton
        var whatsappBtn = document.getElementById('sendWhatsAppBtn');
        
        whatsappBtn.addEventListener('mouseenter', function() {
            this.style.transform = 'translateY(-5px) scale(1.02)';
        });
        
        whatsappBtn.addEventListener('mouseleave', function() {
            this.style.transform = 'translateY(0) scale(1)';
        });

        // Optionnel : Remplir automatiquement le message avec un texte par défaut
        document.addEventListener('DOMContentLoaded', function() {
            // Vous pouvez modifier le message par défaut si nécessaire
            var messageField = document.getElementById('message');
            if (messageField.value === '') {
                messageField.value = 'Bonjour Matthieu, je souhaite vous contacter pour un projet.';
            }
        });

        // Afficher un message si en dehors des heures de disponibilité (optionnel)
        function checkAvailability() {
            var now = new Date();
            var hour = now.getHours();
            var minutes = now.getMinutes();
            var currentTime = hour + minutes/60;
            
            var morningStart = 8;
            var morningEnd = 12;
            var afternoonStart = 14;
            var afternoonEnd = 18;
            
            var isAvailable = (currentTime >= morningStart && currentTime < morningEnd) || 
                             (currentTime >= afternoonStart && currentTime < afternoonEnd);
            
            var availabilityElement = document.querySelector('.availability-badge');
            
            if (availabilityElement) {
                if (isAvailable) {
                    // Je suis disponible maintenant
                    availabilityElement.style.background = 'linear-gradient(135deg, #e8f5e9, #a5d6a7)';
                    availabilityElement.style.border = '3px solid #4CAF50';
                    
                    // Ajouter une indication de disponibilité immédiate
                    var dispoNow = document.createElement('div');
                    dispoNow.style.marginTop = '10px';
                    dispoNow.style.color = '#2E7D32';
                    dispoNow.style.fontWeight = 'bold';
                    dispoNow.innerHTML = '🟢 DISPONIBLE MAINTENANT';
                    
                    // Ne pas dupliquer
                    if (!document.querySelector('.dispo-now')) {
                        dispoNow.className = 'dispo-now';
                        availabilityElement.appendChild(dispoNow);
                    }
                } else {
                    // Je ne suis pas disponible maintenant
                    availabilityElement.style.background = 'linear-gradient(135deg, #fff3e0, #ffe0b2)';
                    availabilityElement.style.border = '3px solid #FF9800';
                }
            }
        }
        
        // Appeler la fonction au chargement
        document.addEventListener('DOMContentLoaded', checkAvailability);
    </script>
</body>
</html>
