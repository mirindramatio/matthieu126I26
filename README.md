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
            color: #1e293b;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ===== ANIMATIONS ÉLÉGANTES ===== */
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0); }
            50% { transform: translateY(-15px) rotate(1deg); }
        }

        @keyframes float-slow {
            0%, 100% { transform: translateY(0) scale(1); }
            50% { transform: translateY(-10px) scale(1.02); }
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.5; transform: scale(1); }
            50% { opacity: 0.8; transform: scale(1.05); }
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes rotate-slow {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes shimmer {
            0% { background-position: -200% 0; }
            100% { background-position: 200% 0; }
        }

        @keyframes border-glow {
            0%, 100% { box-shadow: 0 0 5px rgba(56, 189, 248, 0.3); }
            50% { box-shadow: 0 0 25px rgba(56, 189, 248, 0.6); }
        }

        @keyframes gradient-shift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* ===== ÉLÉMENTS DÉCORATIFS MINIMALISTES ===== */
        .decor {
            position: fixed;
            pointer-events: none;
            z-index: -1;
        }

        .decor-1 {
            top: 5%;
            left: 2%;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(56,189,248,0.1) 0%, transparent 70%);
            border-radius: 50%;
            animation: float-slow 12s ease-in-out infinite;
        }

        .decor-2 {
            bottom: 5%;
            right: 2%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(139,92,246,0.08) 0%, transparent 70%);
            border-radius: 50%;
            animation: float-slow 15s ease-in-out infinite reverse;
        }

        .decor-3 {
            top: 20%;
            right: 10%;
            width: 150px;
            height: 150px;
            border: 2px dashed rgba(56,189,248,0.2);
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            animation: rotate-slow 30s linear infinite;
        }

        .decor-4 {
            bottom: 20%;
            left: 8%;
            width: 200px;
            height: 200px;
            background: repeating-linear-gradient(45deg, rgba(56,189,248,0.05) 0px, rgba(56,189,248,0.05) 10px, transparent 10px, transparent 20px);
            border-radius: 50%;
            animation: rotate-slow 40s linear infinite;
        }

        .decor-5 {
            top: 40%;
            left: 15%;
            width: 100px;
            height: 100px;
            background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.8) 2px, transparent 2px);
            background-size: 20px 20px;
            opacity: 0.3;
            animation: pulse 5s ease-in-out infinite;
        }

        .decor-6 {
            bottom: 30%;
            right: 15%;
            width: 150px;
            height: 150px;
            border: 3px dotted rgba(139,92,246,0.15);
            border-radius: 50%;
            animation: pulse 7s ease-in-out infinite;
        }

        /* Icônes décoratives */
        .icon-decor {
            position: fixed;
            font-size: 2rem;
            opacity: 0.15;
            pointer-events: none;
            z-index: -1;
        }

        .icon-1 { top: 10%; left: 5%; animation: float 8s ease-in-out infinite; }
        .icon-2 { top: 15%; right: 8%; animation: float 10s ease-in-out infinite reverse; }
        .icon-3 { bottom: 20%; left: 10%; animation: float 9s ease-in-out infinite; }
        .icon-4 { bottom: 25%; right: 12%; animation: float 11s ease-in-out infinite reverse; }
        .icon-5 { top: 40%; left: 20%; animation: rotate-slow 25s linear infinite; }
        .icon-6 { bottom: 40%; right: 20%; animation: rotate-slow 30s linear infinite; }

        /* ===== HEADER ÉLÉGANT ===== */
        header {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.03);
            border-bottom: 1px solid rgba(56, 189, 248, 0.2);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
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
            font-size: 1.4rem;
            font-weight: 600;
            color: #0f172a;
            text-decoration: none;
            letter-spacing: -0.5px;
            background: linear-gradient(135deg, #0f172a, #334155);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            transition: all 0.3s;
        }

        .logo:hover {
            transform: translateY(-2px);
        }

        .nav-links {
            display: flex;
            gap: 3rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #334155;
            font-weight: 500;
            font-size: 1rem;
            transition: all 0.3s;
            position: relative;
            padding: 0.5rem 0;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, #38bdf8, #8b5cf6);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.3s;
        }

        .nav-links a:hover {
            color: #0f172a;
        }

        .nav-links a:hover::after {
            transform: scaleX(1);
            transform-origin: left;
        }

        /* ===== SECTIONS ===== */
        section {
            padding: 120px 0;
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
        }

        /* Accueil */
        #accueil {
            background: linear-gradient(135deg, 
                rgba(56,189,248,0.05) 0%, 
                rgba(139,92,246,0.05) 100%);
            text-align: center;
        }

        .hero {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3.2rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            color: #0f172a;
            line-height: 1.2;
            background: linear-gradient(135deg, #0f172a, #334155);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: float 6s ease-in-out infinite;
        }

        .hero p {
            font-size: 1.3rem;
            color: #475569;
            margin-bottom: 2.5rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .btn {
            display: inline-block;
            padding: 14px 40px;
            background: linear-gradient(135deg, #0f172a, #1e293b);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 500;
            letter-spacing: 0.5px;
            transition: all 0.3s;
            border: 1px solid rgba(255,255,255,0.1);
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.1);
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 30px -5px rgba(56,189,248,0.3);
            background: linear-gradient(135deg, #1e293b, #0f172a);
        }

        .btn:hover::before {
            left: 100%;
        }

        /* À propos */
        #apropos {
            background: white;
        }

        .apropos-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: center;
        }

        .apropos-text h2 {
            font-size: 2.5rem;
            font-weight: 600;
            margin-bottom: 2rem;
            color: #0f172a;
            position: relative;
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, #38bdf8, #8b5cf6);
            border-radius: 2px;
        }

        .apropos-text p {
            color: #475569;
            margin-bottom: 1.2rem;
            font-size: 1.1rem;
            line-height: 1.7;
        }

        .apropos-text p:last-of-type {
            font-style: italic;
            color: #38bdf8;
            margin-top: 2rem;
            padding: 1.5rem;
            background: linear-gradient(135deg, #f0f9ff, #e0f2fe);
            border-radius: 20px;
            border-left: 4px solid #38bdf8;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2rem;
        }

        .skill {
            padding: 8px 25px;
            background: white;
            border: 1px solid #e2e8f0;
            border-radius: 30px;
            color: #1e293b;
            font-weight: 500;
            font-size: 0.95rem;
            transition: all 0.3s;
            box-shadow: 0 2px 10px rgba(0,0,0,0.02);
            cursor: default;
        }

        .skill:hover {
            border-color: #38bdf8;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px -5px rgba(56,189,248,0.2);
            background: linear-gradient(135deg, #f0f9ff, #ffffff);
        }

        .apropos-image {
            position: relative;
            display: flex;
            justify-content: center;
        }

        .apropos-image::before {
            content: '';
            position: absolute;
            top: -20px;
            left: -20px;
            right: -20px;
            bottom: -20px;
            background: radial-gradient(circle, rgba(56,189,248,0.2) 0%, transparent 70%);
            border-radius: 30px;
            animation: pulse 5s ease-in-out infinite;
        }

        .apropos-image img {
            width: 100%;
            max-width: 350px;
            height: auto;
            border-radius: 20px;
            box-shadow: 0 30px 40px -20px rgba(0,0,0,0.3);
            border: 4px solid white;
            transition: all 0.5s;
            position: relative;
            z-index: 2;
        }

        .apropos-image img:hover {
            transform: scale(1.02);
            box-shadow: 0 40px 50px -20px rgba(56,189,248,0.4);
        }

        /* Contact */
        #contact {
            background: linear-gradient(135deg, 
                rgba(56,189,248,0.02) 0%, 
                rgba(139,92,246,0.02) 100%);
            text-align: center;
        }

        #contact h2 {
            font-size: 2.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: #0f172a;
        }

        .contact-subtitle {
            color: #64748b;
            font-size: 1.2rem;
            margin-bottom: 3rem;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .contact-card {
            background: white;
            padding: 2.5rem 2rem;
            border-radius: 20px;
            box-shadow: 0 20px 30px -10px rgba(0,0,0,0.05);
            transition: all 0.4s;
            border: 1px solid rgba(56,189,248,0.1);
            position: relative;
            overflow: hidden;
        }

        .contact-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #38bdf8, #8b5cf6);
            transform: scaleX(0);
            transition: transform 0.4s;
        }

        .contact-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 30px 40px -15px rgba(56,189,248,0.2);
            border-color: rgba(56,189,248,0.2);
        }

        .contact-card:hover::before {
            transform: scaleX(1);
        }

        .contact-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            animation: float 5s ease-in-out infinite;
        }

        .contact-card h3 {
            font-size: 1.3rem;
            color: #0f172a;
            margin-bottom: 0.8rem;
            font-weight: 600;
        }

        .contact-card p {
            color: #64748b;
            margin-bottom: 1.5rem;
            font-size: 1rem;
        }

        .contact-link {
            display: inline-block;
            padding: 10px 28px;
            background: #f8fafc;
            color: #334155;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 500;
            font-size: 0.95rem;
            transition: all 0.3s;
            border: 1px solid #e2e8f0;
        }

        .contact-link:hover {
            background: linear-gradient(135deg, #38bdf8, #8b5cf6);
            color: white;
            border-color: transparent;
            transform: translateY(-2px);
            box-shadow: 0 10px 20px -5px rgba(56,189,248,0.3);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-top: 2rem;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 10px 25px;
            background: white;
            color: #334155;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 500;
            transition: all 0.3s;
            border: 1px solid #e2e8f0;
        }

        .social-link:hover {
            background: #0f172a;
            color: white;
            border-color: #0f172a;
            transform: translateY(-2px);
        }

        /* Formulaire WhatsApp */
        .whatsapp-section {
            background: white;
            padding: 80px 0;
            position: relative;
            border-top: 1px solid #e2e8f0;
        }

        .whatsapp-container {
            max-width: 800px;
            margin: 0 auto;
            background: linear-gradient(135deg, #f8fafc, #f1f5f9);
            padding: 3rem;
            border-radius: 40px;
            box-shadow: 0 30px 40px -20px rgba(0,0,0,0.1);
            border: 1px solid rgba(56,189,248,0.2);
        }

        .whatsapp-header {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .whatsapp-icon-large {
            font-size: 3.5rem;
            animation: float 4s ease-in-out infinite;
        }

        .whatsapp-header h3 {
            font-size: 2.2rem;
            font-weight: 600;
            color: #0f172a;
        }

        .whatsapp-header h3 span {
            color: #25D366;
        }

        .whatsapp-subtitle {
            text-align: center;
            color: #64748b;
            margin-bottom: 2.5rem;
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .form-group {
            text-align: left;
        }

        .form-group label {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.5rem;
            color: #334155;
            font-weight: 500;
            font-size: 0.95rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 18px;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            font-size: 1rem;
            transition: all 0.3s;
            background: white;
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #38bdf8;
            box-shadow: 0 0 0 4px rgba(56,189,248,0.1);
        }

        .form-group input:hover,
        .form-group textarea:hover {
            border-color: #94a3b8;
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        .whatsapp-btn {
            width: 100%;
            padding: 16px 30px;
            background: linear-gradient(135deg, #25D366, #128C7E);
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
            position: relative;
            overflow: hidden;
        }

        .whatsapp-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .whatsapp-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 30px -5px rgba(37,211,102,0.3);
        }

        .whatsapp-btn:hover::before {
            left: 100%;
        }

        .availability-info {
            margin-top: 2rem;
            padding: 1.5rem;
            background: white;
            border-radius: 20px;
            border: 1px solid #e2e8f0;
        }

        .schedule {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 1rem 0;
            flex-wrap: wrap;
        }

        .time-badge {
            padding: 8px 20px;
            background: #f8fafc;
            border-radius: 30px;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            border: 1px solid #e2e8f0;
        }

        .time-badge.morning {
            border-left: 4px solid #f59e0b;
        }

        .time-badge.afternoon {
            border-left: 4px solid #3b82f6;
        }

        .availability-status {
            display: inline-block;
            padding: 6px 18px;
            background: #e8f5e9;
            color: #2e7d32;
            border-radius: 30px;
            font-weight: 500;
            font-size: 0.9rem;
            border: 1px solid #a5d6a7;
            margin-top: 1rem;
        }

        /* Footer */
        footer {
            background: white;
            color: #64748b;
            text-align: center;
            padding: 2rem 0;
            border-top: 1px solid #e2e8f0;
        }

        footer p {
            font-size: 0.95rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 0.5rem;
            }

            .nav-links {
                gap: 1.5rem;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .apropos-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .apropos-text h2::after {
                left: 50%;
                transform: translateX(-50%);
            }

            .apropos-text {
                text-align: center;
            }

            .skills {
                justify-content: center;
            }

            .form-grid {
                grid-template-columns: 1fr;
            }

            .whatsapp-container {
                padding: 2rem 1.5rem;
                margin: 0 20px;
            }

            .schedule {
                gap: 1rem;
            }

            .decor-1, .decor-2, .decor-3, .decor-4 {
                opacity: 0.3;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.8rem;
            }

            .contact-card {
                padding: 2rem 1.5rem;
            }

            .whatsapp-header h3 {
                font-size: 1.8rem;
            }

            .time-badge {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <!-- Éléments décoratifs minimalistes -->
    <div class="decor decor-1"></div>
    <div class="decor decor-2"></div>
    <div class="decor decor-3"></div>
    <div class="decor decor-4"></div>
    <div class="decor decor-5"></div>
    <div class="decor decor-6"></div>
    
    <!-- Icônes décoratives -->
    <div class="icon-decor icon-1">⚡</div>
    <div class="icon-decor icon-2">✨</div>
    <div class="icon-decor icon-3">💫</div>
    <div class="icon-decor icon-4">🌟</div>
    <div class="icon-decor icon-5">○</div>
    <div class="icon-decor icon-6">◈</div>

    <header>
        <nav>
            <a href="#accueil" class="logo">Mirindra Matthieu</a>
            <div class="nav-links">
                <a href="#accueil">Accueil</a>
                <a href="#apropos">À propos</a>
                <a href="#contact">Contact</a>
            </div>
        </nav>
    </header>

    <section id="accueil">
        <div class="container hero">
            <h1>Bonjour, je suis<br>RATIANARIVO Mirindra Matthieu</h1>
            <p>Développeur créatif passionné par la création d'expériences web uniques et mémorables</p>
            <a href="#apropos" class="btn">Découvrir mon parcours</a>
        </div>
    </section>

    <section id="apropos">
        <div class="container apropos-content">
            <div class="apropos-text">
                <h2>À propos de moi</h2>
                <p>Je suis un développeur passionné par la création de sites web. J'aime transformer des idées créatives en solutions numériques fonctionnelles. J'ai acquis des bases solides en programmation (HTML, CSS, JavaScript).</p>
                <p>Motivé, sérieux et curieux d'apprendre, je cherche une opportunité qui me permettra de développer mes compétences pratiques et de mieux comprendre le fonctionnement des projets web. La création de sites simples m'aide à développer ma logique et ma créativité.</p>
                <p>Je reste à votre disposition pour un entretien et vous remercie de l'attention portée à ma candidature.</p>
                <p>"La technologie construit le système, l'expérience construit la relation."</p>
                <div class="skills">
                    <span class="skill">HTML5</span>
                    <span class="skill">CSS3</span>
                    <span class="skill">JavaScript</span>
                    <span class="skill">Responsive Design</span>
                    <span class="skill">UI/UX</span>
                </div>
            </div>
            <div class="apropos-image">
                <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/642754626_122112963513211419_7763551596132436351_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=HrPMD1Mzk-wQ7kNvwF-W0Kk&_nc_oc=AdmitmpVlD_NkLZbjv5bb1BdGCCLKrDWIu8jwSkutlrW38sKkCh-4igqUNpNQk8v2sg&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=UrnADD8nIJ14FGwl_Mt82Q&_nc_ss=8&oh=00_AfxextLBeI-e-uEMJr1xXOL4FM1WFzyiLwUla6pesQhiMA&oe=69AAF757" alt="Photo de profil - RATIANARIVO Mirindra Matthieu">
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container contact-content">
            <h2>Travaillons ensemble</h2>
            <p class="contact-subtitle">Vous avez un projet en tête ? N'hésitez pas à me contacter !</p>
            
            <div class="contact-cards">
                <div class="contact-card">
                    <span class="contact-icon">📱</span>
                    <h3>WhatsApp</h3>
                    <p>+261 38 62 876 80</p>
                    <a href="https://wa.me/261386287680?text=Bonjour%20Matthieu%2C%20je%20souhaite%20vous%20contacter%20pour%20un%20projet" 
                       class="contact-link" 
                       target="_blank">
                        Envoyer un message
                    </a>
                </div>

                <div class="contact-card">
                    <span class="contact-icon">📞</span>
                    <h3>Téléphone</h3>
                    <p>+261 38 62 876 80</p>
                    <a href="tel:+261386287680" class="contact-link">
                        Appeler maintenant
                    </a>
                </div>

                <div class="contact-card">
                    <span class="contact-icon">✉️</span>
                    <h3>Email</h3>
                    <p>mirindramatthieu@gmail.com</p>
                    <a href="mailto:mirindramatthieu@gmail.com?subject=Contact%20depuis%20mon%20portfolio&body=Bonjour%20Matthieu%2C" 
                       class="contact-link">
                        Envoyer un email
                    </a>
                </div>
            </div>

            <div class="social-links">
                <a href="#" class="social-link">
                    <span>📋</span> LinkedIn
                </a>
                <a href="#" class="social-link">
                    <span>💻</span> GitHub
                </a>
            </div>
        </div>
    </section>

    <section class="whatsapp-section">
        <div class="container">
            <div class="whatsapp-container">
                <div class="whatsapp-header">
                    <span class="whatsapp-icon-large">📱</span>
                    <h3>WhatsApp <span>Direct</span></h3>
                </div>
                
                <p class="whatsapp-subtitle">
                    Envoyez-moi un message instantanément via WhatsApp
                </p>

                <div class="form-grid">
                    <div class="form-group">
                        <label>
                            <span>👤</span> Votre nom
                        </label>
                        <input type="text" id="nom" placeholder="Ex: Jean Dupont">
                    </div>

                    <div class="form-group">
                        <label>
                            <span>📞</span> Téléphone
                        </label>
                        <input type="tel" id="telephone" placeholder="Ex: 034 12 345 67">
                    </div>

                    <div class="form-group full-width">
                        <label>
                            <span>💬</span> Votre message
                        </label>
                        <textarea id="message" rows="4" placeholder="Bonjour Matthieu, je souhaite vous contacter pour...">Bonjour Matthieu, je souhaite vous contacter pour un projet.</textarea>
                    </div>
                </div>

                <button class="whatsapp-btn" id="sendWhatsAppBtn">
                    <span>📤</span>
                    Envoyer sur WhatsApp
                    <span>→</span>
                </button>

                <div class="availability-info">
                    <div class="schedule">
                        <span class="time-badge morning">
                            <span>🌅</span> MATIN : 8h - 12h
                        </span>
                        <span class="time-badge afternoon">
                            <span>☀️</span> APRÈS-MIDI : 14h - 18h
                        </span>
                    </div>
                    <div style="text-align: center;">
                        <span class="availability-status" id="availabilityStatus">
                            ⏰ Disponible aux horaires indiqués
                        </span>
                    </div>
                    <p style="margin-top: 1rem; color: #64748b; font-size: 0.9rem;">
                        <span>📱 +261 38 62 876 80</span> • <span>⚡ Réponse rapide garantie</span>
                    </p>
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
        // WhatsApp direct
        document.getElementById('sendWhatsAppBtn').addEventListener('click', function() {
            var nom = document.getElementById('nom').value.trim();
            var telephone = document.getElementById('telephone').value.trim();
            var message = document.getElementById('message').value.trim();
            
            if (!nom) {
                alert('Veuillez entrer votre nom');
                return;
            }
            
            if (!message) {
                alert('Veuillez entrer votre message');
                return;
            }
            
            var whatsappNumber = '261386287680';
            var texteMessage = `*Nouveau message du portfolio*%0A%0A`;
            texteMessage += `👤 *Nom :* ${nom}%0A`;
            
            if (telephone) {
                texteMessage += `📞 *Téléphone :* ${telephone}%0A`;
            }
            
            texteMessage += `%0A📝 *Message :*%0A${message}`;
            
            window.open(`https://wa.me/${whatsappNumber}?text=${texteMessage}`, '_blank');
        });

        // Statut de disponibilité
        function updateAvailability() {
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
            
            var statusElement = document.getElementById('availabilityStatus');
            
            if (isAvailable) {
                statusElement.innerHTML = '🟢 DISPONIBLE MAINTENANT';
                statusElement.style.background = '#e8f5e9';
                statusElement.style.color = '#2e7d32';
                statusElement.style.borderColor = '#a5d6a7';
            } else {
                statusElement.innerHTML = '⏰ HORS HORAIRE - Répondrai à mon retour';
                statusElement.style.background = '#fff3e0';
                statusElement.style.color = '#b85c00';
                statusElement.style.borderColor = '#ffb74d';
            }
        }

        document.addEventListener('DOMContentLoaded', function() {
            updateAvailability();
            // Mettre à jour toutes les minutes
            setInterval(updateAvailability, 60000);
        });

        // Animation smooth scroll
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
    </script>
</body>
</html>
