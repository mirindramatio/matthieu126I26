<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
    <title>Portfolio - RATIANARIVO Mirindra Matthieu</title>
    <style>
        /* ===== RESET & VARIABLES ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-light: #7bd8ff;
            --primary-dark: #ac94ff;
            --bg-dark: #030712;
            --text-light: #e0f2fe;
            --text-muted: #b0c4de;
            --transition: all 0.3s ease;
        }

        html {
            font-size: 16px;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;
            line-height: 1.6;
            color: var(--text-light);
            background: linear-gradient(135deg, var(--bg-dark) 0%, #0a0f1a 50%, #0f1a2f 100%);
            min-height: 100vh;
            overflow-x: hidden;
            width: 100%;
            position: relative;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 10;
        }

        /* ===== ANIMATIONS CONSERVÉES ===== */
        @keyframes aura-pulse {
            0%, 100% { opacity: 0.15; filter: blur(30px); transform: scale(1); }
            50% { opacity: 0.3; filter: blur(45px); transform: scale(1.1); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(40px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInLeft {
            from { opacity: 0; transform: translateX(-40px); }
            to { opacity: 1; transform: translateX(0); }
        }

        @keyframes fadeInRight {
            from { opacity: 0; transform: translateX(40px); }
            to { opacity: 1; transform: translateX(0); }
        }

        @keyframes zoomIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        @keyframes glow-soft {
            0%, 100% { filter: drop-shadow(0 0 5px rgba(123, 216, 255, 0.2)); }
            50% { filter: drop-shadow(0 0 20px rgba(172, 148, 255, 0.4)); }
        }

        /* ===== ÉLÉMENTS D'AURA OPTIMISÉS ===== */
        .aura {
            position: fixed;
            pointer-events: none;
            z-index: 0;
            border-radius: 50%;
            filter: blur(60px);
            will-change: transform, opacity;
        }

        .aura-1 {
            top: 5%;
            left: 5%;
            width: min(700px, 80vw);
            height: min(700px, 80vw);
            background: radial-gradient(circle, rgba(123, 216, 255, 0.12) 0%, transparent 70%);
            animation: aura-pulse 15s ease-in-out infinite;
        }

        .aura-2 {
            bottom: 5%;
            right: 5%;
            width: min(800px, 90vw);
            height: min(800px, 90vw);
            background: radial-gradient(circle, rgba(172, 148, 255, 0.1) 0%, transparent 70%);
            animation: aura-pulse 18s ease-in-out infinite reverse;
        }

        /* Version mobile avec moins d'éléments */
        @media (max-width: 768px) {
            .aura-3, .aura-4, .aura-5, .aura-6,
            .aura-line-3, .aura-line-4,
            .aura-cloud-3, .aura-cloud-4,
            .katana-4, .katana-5, .katana-6,
            .shuriken-5, .shuriken-6, .shuriken-7, .shuriken-8 {
                display: none;
            }
            
            .aura-particle {
                width: 3px;
                height: 3px;
            }
        }

        /* ===== HEADER RESPONSIVE ===== */
        header {
            background: rgba(3, 7, 18, 0.6);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(123, 216, 255, 0.15);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            animation: fadeInDown 1.2s ease-out;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 5%;
            max-width: 1400px;
            margin: 0 auto;
            flex-wrap: wrap;
        }

        .logo {
            font-size: clamp(1.2rem, 4vw, 1.6rem);
            font-weight: 400;
            color: #ffffff;
            text-decoration: none;
            letter-spacing: 2px;
            text-shadow: 0 0 20px rgba(123,216,255,0.4);
            animation: glow-soft 5s ease-in-out infinite, float 6s ease-in-out infinite;
            white-space: nowrap;
        }

        .nav-links {
            display: flex;
            gap: clamp(1rem, 4vw, 4rem);
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-muted);
            font-weight: 300;
            font-size: clamp(0.9rem, 3vw, 1.1rem);
            transition: var(--transition);
            letter-spacing: 1.5px;
            white-space: nowrap;
        }

        /* ===== SECTIONS RESPONSIVES ===== */
        section {
            width: 100%;
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 80px 0 60px;
        }

        #accueil {
            text-align: center;
            padding-top: 100px;
        }

        .hero {
            width: 100%;
            max-width: 900px;
            margin: 0 auto;
            animation: zoomIn 1.5s ease-out;
        }

        .hero h1 {
            font-size: clamp(2rem, 8vw, 4.2rem);
            font-weight: 300;
            margin-bottom: 1.5rem;
            color: #ffffff;
            line-height: 1.2;
            text-shadow: 0 0 30px rgba(123,216,255,0.4);
            letter-spacing: clamp(1px, 2vw, 3px);
        }

        .hero p {
            font-size: clamp(1rem, 4vw, 1.4rem);
            color: var(--text-muted);
            margin-bottom: 3rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            font-weight: 300;
            letter-spacing: 1.5px;
            line-height: 1.9;
            padding: 0 15px;
        }

        .btn {
            display: inline-block;
            padding: clamp(12px, 3vw, 16px) clamp(30px, 8vw, 50px);
            background: rgba(123,216,255,0.04);
            color: #ffffff;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 300;
            letter-spacing: 2.5px;
            border: 1px solid rgba(123,216,255,0.25);
            backdrop-filter: blur(10px);
            font-size: clamp(0.9rem, 3vw, 1rem);
            transition: var(--transition);
            white-space: nowrap;
        }

        .btn:hover {
            background: rgba(172,148,255,0.08);
            border-color: rgba(172,148,255,0.4);
            transform: translateY(-6px) scale(1.05);
        }

        /* ===== SECTION À PROPOS RESPONSIVE ===== */
        #apropos {
            background: linear-gradient(135deg, 
                #e0f2fe 0%, #bae6fd 15%, #7dd3fc 30%, #38bdf8 45%,
                #0ea5e9 60%, #0284c7 75%, #0369a1 90%, #0c4a6e 100%);
            background-size: 400% 400%;
            animation: gradientFlow 25s ease infinite;
        }

        @keyframes gradientFlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .apropos-content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 3rem;
            align-items: center;
            padding: 2rem 0;
        }

        @media (min-width: 992px) {
            .apropos-content {
                grid-template-columns: 1fr 1fr;
                gap: 5rem;
            }
        }

        .apropos-text {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(15px);
            padding: clamp(1.5rem, 5vw, 3.5rem);
            border-radius: clamp(25px, 5vw, 50px);
            border: 1px solid rgba(255,255,255,0.3);
            animation: fadeInLeft 1.3s ease-out;
            width: 100%;
        }

        .apropos-text h2 {
            font-size: clamp(2rem, 6vw, 3rem);
            font-weight: 300;
            margin-bottom: 1.5rem;
            color: #0f172a;
        }

        .apropos-text p {
            color: #0f172a;
            margin-bottom: 1rem;
            font-size: clamp(1rem, 3vw, 1.15rem);
            line-height: 1.8;
        }

        .apropos-text p:last-of-type {
            margin-top: 2rem;
            padding: 1.5rem;
            background: rgba(255,255,255,0.25);
            border-radius: 25px;
            border-left: 5px solid #0f172a;
            font-size: clamp(1rem, 3vw, 1.2rem);
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2rem;
        }

        .skill {
            padding: clamp(8px, 2vw, 12px) clamp(16px, 4vw, 28px);
            background: rgba(255,255,255,0.2);
            border: 1px solid rgba(255,255,255,0.4);
            border-radius: 40px;
            color: #0f172a;
            font-weight: 400;
            font-size: clamp(0.9rem, 2.5vw, 1rem);
            transition: var(--transition);
            backdrop-filter: blur(8px);
        }

        .skill:hover {
            transform: translateY(-8px) scale(1.05);
            background: rgba(255,255,255,0.35);
        }

        .apropos-image {
            display: flex;
            justify-content: center;
            animation: fadeInRight 1.3s ease-out;
            width: 100%;
        }

        .image-frame {
            width: 100%;
            max-width: 400px;
            border-radius: 15px;
            padding: 6px;
            background: rgba(255,255,255,0.15);
        }

        .apropos-image img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            display: block;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        /* ===== SECTION CONTACT RESPONSIVE ===== */
        #contact {
            background: linear-gradient(135deg, 
                rgba(3,7,18,0.96) 0%, rgba(10,15,25,0.96) 33%,
                rgba(15,20,30,0.96) 66%, rgba(3,7,18,0.96) 100%);
            background-size: 400% 400%;
            animation: gradientFlow 30s ease infinite;
        }

        #contact h2 {
            font-size: clamp(2rem, 6vw, 3rem);
            font-weight: 300;
            margin-bottom: 1rem;
            color: #ffffff;
        }

        .contact-subtitle {
            color: var(--text-muted);
            font-size: clamp(1rem, 3vw, 1.3rem);
            margin-bottom: 2.5rem;
            font-weight: 300;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }

        .contact-card {
            background: rgba(20,25,40,0.35);
            backdrop-filter: blur(15px);
            padding: clamp(1.5rem, 4vw, 2rem);
            border-radius: 30px;
            border: 1px solid rgba(123,216,255,0.15);
            transition: var(--transition);
            animation: fadeInUp 1.2s ease-out;
        }

        .contact-icon {
            font-size: clamp(2rem, 6vw, 2.8rem);
            margin-bottom: 1rem;
        }

        .contact-card h3 {
            font-size: clamp(1.2rem, 4vw, 1.4rem);
            color: #ffffff;
            margin-bottom: 0.5rem;
            font-weight: 300;
        }

        .contact-card p {
            color: var(--text-muted);
            margin-bottom: 1.2rem;
            font-size: clamp(0.85rem, 2.5vw, 0.95rem);
            word-break: break-word;
        }

        .contact-link {
            display: inline-block;
            padding: clamp(8px, 2vw, 10px) clamp(16px, 4vw, 28px);
            background: rgba(123,216,255,0.06);
            color: var(--text-muted);
            text-decoration: none;
            border-radius: 30px;
            font-size: clamp(0.8rem, 2.5vw, 0.9rem);
            border: 1px solid rgba(123,216,255,0.2);
            transition: var(--transition);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-top: 2.5rem;
            flex-wrap: wrap;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: clamp(10px, 2vw, 12px) clamp(20px, 5vw, 32px);
            background: rgba(20,25,40,0.4);
            color: var(--text-muted);
            text-decoration: none;
            border-radius: 30px;
            border: 1px solid rgba(123,216,255,0.15);
            transition: var(--transition);
            font-size: clamp(0.85rem, 2.5vw, 0.95rem);
        }

        /* ===== SECTION WHATSAPP RESPONSIVE ===== */
        .whatsapp-section {
            padding: 60px 0;
            background: linear-gradient(135deg, 
                rgba(3,7,18,0.98) 0%, rgba(10,15,25,0.98) 50%, rgba(15,20,30,0.98) 100%);
        }

        .whatsapp-container {
            max-width: 1000px;
            margin: 0 auto;
            background: rgba(20,25,40,0.35);
            backdrop-filter: blur(20px);
            padding: clamp(1.5rem, 5vw, 4rem);
            border-radius: clamp(30px, 8vw, 70px);
            border: 1px solid rgba(123,216,255,0.15);
            animation: zoomIn 1.5s ease-out;
        }

        .whatsapp-header {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: clamp(0.8rem, 3vw, 2rem);
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
        }

        .whatsapp-icon-large {
            font-size: clamp(3rem, 10vw, 5rem);
        }

        .whatsapp-header h3 {
            font-size: clamp(1.8rem, 6vw, 2.8rem);
            font-weight: 300;
            color: #ffffff;
            text-align: center;
        }

        .whatsapp-header h3 span {
            color: #25D366;
        }

        .messaging-platforms {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
            margin: 2rem 0;
        }

        @media (min-width: 640px) {
            .messaging-platforms {
                grid-template-columns: 1fr 1fr;
            }
        }

        .platform-card {
            background: rgba(20,25,40,0.3);
            backdrop-filter: blur(10px);
            padding: 1.5rem;
            border-radius: 30px;
            border: 1px solid rgba(255,255,255,0.1);
            text-align: center;
        }

        .platform-icon {
            font-size: 2.5rem;
            margin-bottom: 0.8rem;
        }

        .platform-card h4 {
            font-size: 1.3rem;
            color: #ffffff;
            margin-bottom: 0.5rem;
            font-weight: 300;
        }

        .platform-card p {
            color: var(--text-muted);
            margin-bottom: 1rem;
            font-size: 0.9rem;
            word-break: break-word;
        }

        .platform-link {
            display: inline-block;
            padding: 8px 20px;
            background: rgba(123,216,255,0.1);
            color: #ffffff;
            text-decoration: none;
            border-radius: 30px;
            font-size: 0.9rem;
            border: 1px solid rgba(123,216,255,0.2);
            transition: var(--transition);
        }

        .messaging-separator {
            text-align: center;
            margin: 1.5rem 0;
            color: var(--text-muted);
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.2rem;
            margin-bottom: 1.5rem;
        }

        @media (min-width: 768px) {
            .form-grid {
                grid-template-columns: 1fr 1fr;
            }
            .form-group.full-width {
                grid-column: 1 / -1;
            }
        }

        .form-group label {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.5rem;
            color: var(--text-muted);
            font-weight: 300;
            font-size: 0.95rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 16px;
            background: rgba(10,15,25,0.5);
            border: 1px solid rgba(123,216,255,0.2);
            border-radius: 20px;
            font-size: 1rem;
            color: var(--text-light);
            font-family: inherit;
            transition: var(--transition);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: rgba(172,148,255,0.5);
            background: rgba(15,20,30,0.6);
        }

        .whatsapp-btn, .messenger-btn {
            width: 100%;
            padding: 14px 25px;
            color: #ffffff;
            border: none;
            border-radius: 40px;
            font-size: 1rem;
            font-weight: 300;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.8rem;
            margin-top: 1rem;
        }

        .whatsapp-btn {
            background: rgba(37,211,102,0.1);
            border: 1px solid rgba(37,211,102,0.25);
        }

        .messenger-btn {
            background: rgba(0,132,255,0.1);
            border: 1px solid rgba(0,132,255,0.25);
        }

        .whatsapp-btn:hover, .messenger-btn:hover {
            transform: translateY(-5px) scale(1.02);
        }

        .whatsapp-btn:hover {
            background: rgba(37,211,102,0.15);
            border-color: rgba(37,211,102,0.4);
        }

        .messenger-btn:hover {
            background: rgba(0,132,255,0.15);
            border-color: rgba(0,132,255,0.4);
        }

        .availability-info {
            margin-top: 2rem;
            padding: 1.5rem;
            background: rgba(10,15,25,0.4);
            border-radius: 40px;
            border: 1px solid rgba(123,216,255,0.15);
        }

        .schedule {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin: 1.5rem 0;
            flex-wrap: wrap;
        }

        .time-badge {
            padding: 8px 16px;
            background: rgba(20,25,40,0.5);
            border-radius: 40px;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            border: 1px solid rgba(123,216,255,0.2);
            color: var(--text-muted);
            font-weight: 300;
            font-size: 0.9rem;
        }

        .time-badge.morning { border-left: 4px solid var(--primary-light); }
        .time-badge.afternoon { border-left: 4px solid var(--primary-dark); }

        .availability-status {
            display: inline-block;
            padding: 6px 20px;
            background: rgba(37,211,102,0.12);
            border-radius: 40px;
            color: #25D366;
            font-weight: 300;
            font-size: 0.9rem;
            border: 1px solid rgba(37,211,102,0.25);
        }

        /* ===== FOOTER RESPONSIVE ===== */
        footer {
            background: rgba(3, 7, 18, 0.7);
            color: var(--text-muted);
            text-align: center;
            padding: 1.5rem 0;
            border-top: 1px solid rgba(123,216,255,0.15);
        }

        footer p {
            font-size: clamp(0.8rem, 2.5vw, 1rem);
            font-weight: 300;
            letter-spacing: 1.5px;
            padding: 0 15px;
        }

        /* ===== UTILITAIRES ===== */
        .text-center {
            text-align: center;
        }

        .w-100 {
            width: 100%;
        }

        .d-flex {
            display: flex;
        }

        .flex-wrap {
            flex-wrap: wrap;
        }

        .gap-1 { gap: 0.5rem; }
        .gap-2 { gap: 1rem; }
        .gap-3 { gap: 1.5rem; }
    </style>
</head>
<body>
    <!-- Éléments d'aura (version allégée pour mobile) -->
    <div class="aura aura-1"></div>
    <div class="aura aura-2"></div>
    <div class="aura aura-3"></div>
    <div class="aura aura-4"></div>
    <div class="aura-line aura-line-1"></div>
    <div class="aura-line aura-line-2"></div>
    <div class="aura-cloud aura-cloud-1"></div>
    <div class="aura-cloud aura-cloud-2"></div>
    
    <!-- Éléments ninja (limités pour les petits écrans) -->
    <div class="ninja-weapon katana-1">⚔️</div>
    <div class="ninja-weapon katana-2">⚔️</div>
    <div class="ninja-weapon katana-3">⚔️</div>
    <div class="ninja-weapon shuriken-1">✴️</div>
    <div class="ninja-weapon shuriken-2">✴️</div>
    <div class="ninja-weapon shuriken-3">✴️</div>
    <div class="ninja-weapon shuriken-4">✴️</div>
    
    <!-- Particules -->
    <div class="aura-particle aura-particle-1"></div>
    <div class="aura-particle aura-particle-2"></div>
    <div class="aura-particle aura-particle-3"></div>
    <div class="aura-particle aura-particle-4"></div>
    
    <div class="aura-ray"></div>

    <header>
        <nav>
            <a href="#accueil" class="logo">Mirindra M.</a>
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
                    <span class="skill">HTML</span>
                    <span class="skill">CSS</span>
                    <span class="skill">JavaScript</span>
                </div>
            </div>
            <div class="apropos-image">
                <div class="image-frame">
                    <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/642754626_122112963513211419_7763551596132436351_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=HrPMD1Mzk-wQ7kNvwF-W0Kk&_nc_oc=AdmitmpVlD_NkLZbjv5bb1BdGCCLKrDWIu8jwSkutlrW38sKkCh-4igqUNpNQk8v2sg&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=UrnADD8nIJ14FGwl_Mt82Q&_nc_ss=8&oh=00_AfxextLBeI-e-uEMJr1xXOL4FM1WFzyiLwUla6pesQhiMA&oe=69AAF757" alt="Photo de profil" loading="lazy">
                </div>
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
                       target="_blank" rel="noopener">
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
                <a href="#" class="social-link" target="_blank" rel="noopener">
                    <span>📋</span> LinkedIn
                </a>
                <a href="#" class="social-link" target="_blank" rel="noopener">
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
                    <h3>Messagerie <span>Directe</span></h3>
                </div>
                
                <p class="whatsapp-subtitle text-center">
                    Envoyez-moi un message instantanément sur la plateforme de votre choix
                </p>

                <div class="messaging-platforms">
                    <div class="platform-card">
                        <div class="platform-icon">📱</div>
                        <h4>WhatsApp</h4>
                        <p>+261 38 62 876 80</p>
                        <a href="https://wa.me/261386287680?text=Bonjour%20Matthieu%2C%20je%20souhaite%20vous%20contacter%20pour%20un%20projet" 
                           class="platform-link" 
                           target="_blank" rel="noopener">
                            Envoyer sur WhatsApp
                        </a>
                    </div>

                    <div class="platform-card">
                        <div class="platform-icon">💬</div>
                        <h4>Facebook Messenger</h4>
                        <p>RATIANARIVO Mirindra Matthieu</p>
                        <a href="https://m.me/ratianarivo.mirindra" 
                           class="platform-link" 
                           target="_blank" rel="noopener">
                            Envoyer sur Messenger
                        </a>
                    </div>
                </div>

                <div class="messaging-separator">— ou envoyez un message personnalisé —</div>

                <div class="form-grid">
                    <div class="form-group">
                        <label>
                            <span>👤</span> Votre nom
                        </label>
                        <input type="text" id="nom" placeholder="Ex: Everson Malcolm">
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

                <div class="d-flex flex-wrap gap-2" style="justify-content: center;">
                    <button class="whatsapp-btn" id="sendWhatsAppBtn">
                        <span>📤</span> WhatsApp <span>→</span>
                    </button>
                    <button class="messenger-btn" id="sendMessengerBtn">
                        <span>💬</span> Messenger <span>→</span>
                    </button>
                </div>

                <div class="availability-info">
                    <div class="schedule">
                        <span class="time-badge morning">
                            <span>🌅</span> MATIN : 8h - 12h
                        </span>
                        <span class="time-badge afternoon">
                            <span>☀️</span> APRÈS-MIDI : 14h - 18h
                        </span>
                    </div>
                    <div class="text-center">
                        <span class="availability-status" id="availabilityStatus">
                            ⏰ Disponible aux horaires indiqués
                        </span>
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
        document.addEventListener('DOMContentLoaded', function() {
            // Gestionnaires pour les boutons
            const whatsappBtn = document.getElementById('sendWhatsAppBtn');
            const messengerBtn = document.getElementById('sendMessengerBtn');
            
            if (whatsappBtn) {
                whatsappBtn.addEventListener('click', function() {
                    const nom = document.getElementById('nom').value.trim();
                    const telephone = document.getElementById('telephone').value.trim();
                    let message = document.getElementById('message').value.trim();
                    
                    if (!nom) {
                        alert('Veuillez entrer votre nom');
                        return;
                    }
                    
                    if (!message) {
                        alert('Veuillez entrer votre message');
                        return;
                    }
                    
                    // Message par défaut si vide
                    if (message === '') {
                        message = 'Bonjour Matthieu, je souhaite vous contacter pour un projet.';
                    }
                    
                    const whatsappNumber = '261386287680';
                    let texteMessage = `*Nouveau message du portfolio*%0A%0A`;
                    texteMessage += `👤 *Nom :* ${nom}%0A`;
                    
                    if (telephone) {
                        texteMessage += `📞 *Téléphone :* ${telephone}%0A`;
                    }
                    
                    texteMessage += `%0A📝 *Message :*%0A${message}`;
                    
                    window.open(`https://wa.me/${whatsappNumber}?text=${texteMessage}`, '_blank');
                });
            }

            if (messengerBtn) {
                messengerBtn.addEventListener('click', function() {
                    const nom = document.getElementById('nom').value.trim();
                    const telephone = document.getElementById('telephone').value.trim();
                    let message = document.getElementById('message').value.trim();
                    
                    if (!nom) {
                        alert('Veuillez entrer votre nom');
                        return;
                    }
                    
                    if (!message) {
                        alert('Veuillez entrer votre message');
                        return;
                    }
                    
                    let texteMessage = `Bonjour Matthieu, je suis ${nom}.`;
                    
                    if (telephone) {
                        texteMessage += ` Mon téléphone: ${telephone}.`;
                    }
                    
                    texteMessage += ` ${message}`;
                    
                    window.open(`https://m.me/ratianarivo.mirindra?text=${encodeURIComponent(texteMessage)}`, '_blank');
                });
            }

            // Navigation smooth
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

            // Gestion de la disponibilité
            function updateAvailability() {
                const now = new Date();
                const hour = now.getHours();
                const minutes = now.getMinutes();
                const currentTime = hour + minutes/60;
                
                const morningStart = 8;
                const morningEnd = 12;
                const afternoonStart = 14;
                const afternoonEnd = 18;
                
                const isAvailable = (currentTime >= morningStart && currentTime < morningEnd) || 
                                   (currentTime >= afternoonStart && currentTime < afternoonEnd);
                
                const statusElement = document.getElementById('availabilityStatus');
                
                if (statusElement) {
                    if (isAvailable) {
                        statusElement.innerHTML = '🟢 DISPONIBLE MAINTENANT';
                        statusElement.style.background = 'rgba(37,211,102,0.15)';
                        statusElement.style.color = '#25D366';
                    } else {
                        statusElement.innerHTML = '⏰ HORS HORAIRE - Réponse à mon retour';
                        statusElement.style.background = 'rgba(255,165,0,0.15)';
                        statusElement.style.color = '#FFA500';
                    }
                }
            }

            updateAvailability();
            setInterval(updateAvailability, 60000);

            // Effet de parallaxe léger (optionnel, désactivé sur mobile pour performance)
            if (window.innerWidth > 768) {
                window.addEventListener('scroll', function() {
                    const scrolled = window.pageYOffset;
                    const auraElements = document.querySelectorAll('.aura, .aura-cloud, .ninja-weapon, .aura-line, .aura-particle');
                    auraElements.forEach((el, index) => {
                        const speed = 0.03 + (index * 0.005);
                        el.style.transform = `translateY(${scrolled * speed}px)`;
                    });
                });
            }
        });
    </script>
</body>
</html>
