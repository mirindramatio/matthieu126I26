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
            font-family: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;
            line-height: 1.6;
            color: #e0f2fe;
            background: linear-gradient(135deg, #0a0f1a 0%, #0f1a2f 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 10;
        }

        /* ===== THÈME MUICHIRO TOKITO - BRUME ÉLÉGANTE ===== */
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        @keyframes float-slow {
            0%, 100% { transform: translateY(0) translateX(0); }
            50% { transform: translateY(-8px) translateX(5px); }
        }

        @keyframes mist-flow {
            0% { transform: translateX(0) translateY(0); opacity: 0.15; }
            50% { transform: translateX(15px) translateY(-5px); opacity: 0.25; }
            100% { transform: translateX(0) translateY(0); opacity: 0.15; }
        }

        @keyframes mist-pulse {
            0%, 100% { opacity: 0.1; filter: blur(25px); }
            50% { opacity: 0.2; filter: blur(35px); }
        }

        @keyframes feather-float {
            0% { transform: translateY(0) rotate(0deg); opacity: 0.2; }
            50% { transform: translateY(-12px) rotate(3deg); opacity: 0.3; }
            100% { transform: translateY(0) rotate(0deg); opacity: 0.2; }
        }

        @keyframes glow-soft {
            0%, 100% { filter: drop-shadow(0 0 5px rgba(123, 216, 255, 0.2)); }
            50% { filter: drop-shadow(0 0 15px rgba(172, 148, 255, 0.3)); }
        }

        /* ===== ÉLÉMENTS DÉCORATIFS BRUME ===== */
        .mist {
            position: fixed;
            pointer-events: none;
            z-index: 0;
            background: linear-gradient(135deg, rgba(123, 216, 255, 0.03), rgba(172, 148, 255, 0.03));
            filter: blur(40px);
            border-radius: 50%;
        }

        .mist-1 {
            top: 10%;
            left: 5%;
            width: 500px;
            height: 500px;
            animation: mist-flow 18s ease-in-out infinite;
        }

        .mist-2 {
            bottom: 10%;
            right: 5%;
            width: 600px;
            height: 600px;
            animation: mist-flow 22s ease-in-out infinite reverse;
        }

        .mist-3 {
            top: 40%;
            right: 15%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(172, 148, 255, 0.04), transparent);
            animation: mist-pulse 15s ease-in-out infinite;
        }

        /* Nuages légers */
        .cloud {
            position: fixed;
            background: rgba(255, 255, 255, 0.02);
            border-radius: 1000px;
            filter: blur(20px);
            pointer-events: none;
            z-index: 0;
        }

        .cloud-1 {
            top: 15%;
            right: 10%;
            width: 400px;
            height: 100px;
            box-shadow: 50px 20px 0 0 rgba(255,255,255,0.02);
            animation: float-slow 25s ease-in-out infinite;
        }

        .cloud-2 {
            bottom: 20%;
            left: 5%;
            width: 500px;
            height: 120px;
            box-shadow: 60px 30px 0 0 rgba(255,255,255,0.02);
            animation: float 30s ease-in-out infinite reverse;
        }

        /* Plumes de Muichiro */
        .feather {
            position: fixed;
            color: rgba(172, 148, 255, 0.15);
            font-size: 1.8rem;
            pointer-events: none;
            z-index: 0;
            filter: drop-shadow(0 0 8px rgba(123, 216, 255, 0.1));
            animation: feather-float 16s ease-in-out infinite;
        }

        .feather-1 {
            top: 20%;
            left: 8%;
            transform: rotate(-10deg);
            animation-delay: 0s;
        }

        .feather-2 {
            top: 70%;
            right: 12%;
            transform: rotate(15deg);
            animation-delay: 4s;
        }

        .feather-3 {
            bottom: 25%;
            left: 15%;
            transform: rotate(25deg);
            animation-delay: 8s;
        }

        /* Particules de brume */
        .mist-particle {
            position: fixed;
            width: 3px;
            height: 3px;
            background: rgba(172, 148, 255, 0.2);
            border-radius: 50%;
            filter: blur(1px);
            pointer-events: none;
            z-index: 0;
            animation: mist-flow 20s ease-in-out infinite;
        }

        .particle-1 { top: 15%; left: 15%; }
        .particle-2 { top: 25%; left: 45%; animation-delay: 3s; }
        .particle-3 { top: 35%; left: 75%; animation-delay: 6s; }
        .particle-4 { top: 45%; left: 25%; animation-delay: 9s; }
        .particle-5 { top: 55%; left: 55%; animation-delay: 12s; }

        /* ===== HEADER ÉLÉGANT ===== */
        header {
            background: rgba(10, 15, 25, 0.6);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(123, 216, 255, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            animation: fadeInDown 1s ease-out;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
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
            font-weight: 500;
            color: #e0f2fe;
            text-decoration: none;
            letter-spacing: 0.5px;
            transition: all 0.3s;
            position: relative;
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, #7bd8ff, transparent);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.3s;
        }

        .logo:hover {
            color: #ffffff;
        }

        .logo:hover::after {
            transform: scaleX(1);
            transform-origin: left;
        }

        .nav-links {
            display: flex;
            gap: 3rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #b0c4de;
            font-weight: 400;
            font-size: 1rem;
            transition: all 0.3s;
            position: relative;
        }

        .nav-links a::before {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 1px;
            background: #7bd8ff;
            transform: scaleX(0);
            transition: transform 0.3s;
        }

        .nav-links a:hover {
            color: #ffffff;
        }

        .nav-links a:hover::before {
            transform: scaleX(1);
        }

        /* ===== SECTIONS ===== */
        section {
            padding: 120px 0;
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        /* Accueil */
        #accueil {
            text-align: center;
        }

        .hero {
            max-width: 900px;
            margin: 0 auto;
            animation: fadeInUp 1.2s ease-out;
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

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 400;
            margin-bottom: 1.5rem;
            color: #ffffff;
            line-height: 1.2;
            text-shadow: 0 0 20px rgba(123, 216, 255, 0.2);
            animation: glow-soft 4s ease-in-out infinite;
        }

        .hero p {
            font-size: 1.3rem;
            color: #b0c4de;
            margin-bottom: 2.5rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            font-weight: 300;
            letter-spacing: 0.5px;
        }

        .btn {
            display: inline-block;
            padding: 14px 40px;
            background: rgba(123, 216, 255, 0.05);
            color: #e0f2fe;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 400;
            letter-spacing: 1px;
            transition: all 0.3s;
            border: 1px solid rgba(123, 216, 255, 0.2);
            backdrop-filter: blur(5px);
            font-size: 0.95rem;
        }

        .btn:hover {
            background: rgba(123, 216, 255, 0.1);
            border-color: rgba(172, 148, 255, 0.3);
            transform: translateY(-2px);
            box-shadow: 0 10px 20px -5px rgba(0,0,0,0.3);
        }

        /* ===== SECTION À PROPOS - BLEU CIEL ÉLÉGANT ===== */
        #apropos {
            background: linear-gradient(135deg, 
                #e0f2fe 0%,
                #bae6fd 50%,
                #7dd3fc 100%);
            position: relative;
        }

        .apropos-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: center;
            position: relative;
            z-index: 10;
        }

        .apropos-text {
            animation: fadeInLeft 1s ease-out;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 3rem;
            border-radius: 30px;
            border: 1px solid rgba(255,255,255,0.2);
            box-shadow: 0 20px 40px -15px rgba(0,0,0,0.1);
        }

        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .apropos-text h2 {
            font-size: 2.5rem;
            font-weight: 400;
            margin-bottom: 2rem;
            color: #0f172a;
            position: relative;
            display: inline-block;
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 80px;
            height: 2px;
            background: linear-gradient(90deg, #0f172a, transparent);
        }

        .apropos-text p {
            color: #1e293b;
            margin-bottom: 1.2rem;
            font-size: 1.1rem;
            line-height: 1.8;
            font-weight: 400;
            transition: all 0.3s;
        }

        .apropos-text p:hover {
            transform: translateX(5px);
            color: #0f172a;
        }

        .apropos-text p:last-of-type {
            font-style: italic;
            color: #0f172a;
            margin-top: 2rem;
            padding: 1.2rem;
            background: rgba(255,255,255,0.2);
            border-radius: 15px;
            border-left: 3px solid #0f172a;
            font-size: 1.1rem;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            margin-top: 2rem;
        }

        .skill {
            padding: 8px 20px;
            background: rgba(255, 255, 255, 0.15);
            border: 1px solid rgba(255,255,255,0.3);
            border-radius: 25px;
            color: #0f172a;
            font-weight: 400;
            font-size: 0.9rem;
            transition: all 0.3s;
            backdrop-filter: blur(5px);
            cursor: default;
        }

        .skill:hover {
            background: rgba(255,255,255,0.25);
            transform: translateY(-2px);
            border-color: rgba(255,255,255,0.5);
        }

        .apropos-image {
            position: relative;
            display: flex;
            justify-content: center;
            animation: fadeInRight 1s ease-out;
        }

        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Cadre photo élégant - style brume */
        .image-frame {
            position: relative;
            width: 100%;
            max-width: 400px;
            aspect-ratio: 1/1;
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            padding: 6px;
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(5px);
            box-shadow: 0 20px 40px -10px rgba(0,0,0,0.2);
            animation: float-slow 8s ease-in-out infinite;
        }

        /* Effet de brume autour de la photo */
        .image-frame::before {
            content: '';
            position: absolute;
            top: -15px;
            left: -15px;
            right: -15px;
            bottom: -15px;
            background: radial-gradient(circle, rgba(123,216,255,0.1) 0%, transparent 70%);
            border-radius: inherit;
            filter: blur(15px);
            animation: mist-pulse 6s ease-in-out infinite;
            z-index: -1;
        }

        /* Cercle de brume */
        .mist-circle {
            position: absolute;
            top: -20px;
            left: -20px;
            right: -20px;
            bottom: -20px;
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: inherit;
            animation: float 10s ease-in-out infinite;
        }

        .mist-circle-2 {
            top: -30px;
            left: -30px;
            right: -30px;
            bottom: -30px;
            border: 1px dashed rgba(255,255,255,0.1);
            animation: float-slow 14s ease-in-out infinite reverse;
        }

        .apropos-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: inherit;
            transition: all 0.4s;
            display: block;
            filter: brightness(1.02) contrast(1.02);
            opacity: 0.95;
        }

        .apropos-image img:hover {
            transform: scale(1.02);
            opacity: 1;
            filter: brightness(1.05);
        }

        /* Badges discrets */
        .badge {
            position: absolute;
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(8px);
            padding: 6px 18px;
            border-radius: 25px;
            color: #0f172a;
            font-weight: 400;
            font-size: 0.85rem;
            border: 1px solid rgba(255,255,255,0.2);
            letter-spacing: 0.5px;
            animation: float 6s ease-in-out infinite;
        }

        .badge-1 {
            top: 10%;
            right: 0;
        }

        .badge-2 {
            bottom: 15%;
            left: 0;
            animation-delay: 2s;
        }

        /* ===== SECTION CONTACT ÉLÉGANTE ===== */
        #contact {
            background: linear-gradient(135deg, 
                rgba(10,15,25,0.95) 0%, 
                rgba(15,20,30,0.95) 100%);
            text-align: center;
        }

        #contact h2 {
            font-size: 2.5rem;
            font-weight: 400;
            margin-bottom: 1rem;
            color: #ffffff;
            letter-spacing: 0.5px;
        }

        .contact-subtitle {
            color: #b0c4de;
            font-size: 1.2rem;
            margin-bottom: 3rem;
            font-weight: 300;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .contact-card {
            background: rgba(20, 25, 40, 0.4);
            backdrop-filter: blur(10px);
            padding: 2.5rem 2rem;
            border-radius: 20px;
            border: 1px solid rgba(123, 216, 255, 0.1);
            transition: all 0.3s;
            animation: fadeInUp 1s ease-out;
            animation-fill-mode: both;
        }

        .contact-card:nth-child(1) { animation-delay: 0.1s; }
        .contact-card:nth-child(2) { animation-delay: 0.2s; }
        .contact-card:nth-child(3) { animation-delay: 0.3s; }

        .contact-card:hover {
            transform: translateY(-5px);
            border-color: rgba(172, 148, 255, 0.2);
            background: rgba(25, 30, 45, 0.5);
        }

        .contact-icon {
            font-size: 3rem;
            margin-bottom: 1.2rem;
            display: inline-block;
            opacity: 0.8;
            filter: drop-shadow(0 0 10px rgba(123,216,255,0.2));
            animation: float 5s ease-in-out infinite;
        }

        .contact-card h3 {
            font-size: 1.3rem;
            color: #e0f2fe;
            margin-bottom: 0.8rem;
            font-weight: 400;
            letter-spacing: 0.5px;
        }

        .contact-card p {
            color: #b0c4de;
            margin-bottom: 1.5rem;
            font-size: 1rem;
        }

        .contact-link {
            display: inline-block;
            padding: 10px 28px;
            background: rgba(123, 216, 255, 0.05);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 25px;
            font-weight: 400;
            font-size: 0.9rem;
            border: 1px solid rgba(123, 216, 255, 0.15);
            transition: all 0.3s;
        }

        .contact-link:hover {
            background: rgba(123, 216, 255, 0.1);
            color: #ffffff;
            border-color: rgba(172, 148, 255, 0.3);
            transform: translateY(-2px);
        }

        .social-links {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            margin-top: 3rem;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            padding: 10px 28px;
            background: rgba(20,25,40,0.4);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 25px;
            border: 1px solid rgba(123,216,255,0.1);
            transition: all 0.3s;
            font-weight: 400;
        }

        .social-link:hover {
            background: rgba(30,35,50,0.5);
            color: #ffffff;
            border-color: rgba(172,148,255,0.2);
            transform: translateY(-2px);
        }

        /* ===== SECTION WHATSAPP ÉLÉGANTE ===== */
        .whatsapp-section {
            padding: 100px 0;
            background: linear-gradient(135deg, 
                rgba(10,15,25,0.98) 0%, 
                rgba(15,20,30,0.98) 100%);
        }

        .whatsapp-container {
            max-width: 900px;
            margin: 0 auto;
            background: rgba(20,25,40,0.4);
            backdrop-filter: blur(15px);
            padding: 3rem;
            border-radius: 40px;
            border: 1px solid rgba(123,216,255,0.1);
            animation: fadeInUp 1.2s ease-out;
        }

        .whatsapp-header {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .whatsapp-icon-large {
            font-size: 3.5rem;
            opacity: 0.8;
            animation: float 5s ease-in-out infinite;
            filter: drop-shadow(0 0 15px rgba(37,211,102,0.2));
        }

        .whatsapp-header h3 {
            font-size: 2.2rem;
            font-weight: 400;
            color: #ffffff;
            letter-spacing: 0.5px;
        }

        .whatsapp-header h3 span {
            color: #25D366;
            opacity: 0.9;
        }

        .whatsapp-subtitle {
            text-align: center;
            color: #b0c4de;
            margin-bottom: 2.5rem;
            font-weight: 300;
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.8rem;
            margin-bottom: 2rem;
        }

        .form-group {
            text-align: left;
        }

        .form-group label {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.5rem;
            color: #b0c4de;
            font-weight: 400;
            font-size: 0.95rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 18px;
            background: rgba(10,15,25,0.4);
            border: 1px solid rgba(123,216,255,0.15);
            border-radius: 15px;
            font-size: 1rem;
            color: #e0f2fe;
            transition: all 0.3s;
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: rgba(172,148,255,0.4);
            background: rgba(15,20,30,0.5);
        }

        .form-group input:hover,
        .form-group textarea:hover {
            border-color: rgba(172,148,255,0.3);
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        .whatsapp-btn {
            width: 100%;
            padding: 14px 35px;
            background: rgba(37,211,102,0.1);
            color: #ffffff;
            border: 1px solid rgba(37,211,102,0.2);
            border-radius: 30px;
            font-size: 1.1rem;
            font-weight: 400;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
            letter-spacing: 0.5px;
        }

        .whatsapp-btn:hover {
            background: rgba(37,211,102,0.15);
            border-color: rgba(37,211,102,0.3);
            transform: translateY(-2px);
        }

        .availability-info {
            margin-top: 2.5rem;
            padding: 1.8rem;
            background: rgba(10,15,25,0.3);
            border-radius: 25px;
            border: 1px solid rgba(123,216,255,0.1);
        }

        .schedule {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 1.5rem 0;
            flex-wrap: wrap;
        }

        .time-badge {
            padding: 8px 20px;
            background: rgba(20,25,40,0.4);
            border-radius: 30px;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            border: 1px solid rgba(123,216,255,0.15);
            color: #b0c4de;
            font-weight: 400;
            transition: all 0.3s;
        }

        .time-badge:hover {
            border-color: rgba(172,148,255,0.3);
            color: #ffffff;
            transform: translateY(-2px);
        }

        .time-badge.morning { border-left: 3px solid #7bd8ff; }
        .time-badge.afternoon { border-left: 3px solid #ac94ff; }

        .availability-status {
            display: inline-block;
            padding: 6px 20px;
            background: rgba(37,211,102,0.1);
            border-radius: 30px;
            color: #25D366;
            font-weight: 400;
            font-size: 0.9rem;
            border: 1px solid rgba(37,211,102,0.2);
            animation: glow-soft 3s ease-in-out infinite;
        }

        /* ===== FOOTER ===== */
        footer {
            background: rgba(5, 10, 15, 0.6);
            color: #b0c4de;
            text-align: center;
            padding: 2rem 0;
            border-top: 1px solid rgba(123,216,255,0.1);
        }

        footer p {
            font-size: 0.95rem;
            font-weight: 300;
            letter-spacing: 0.5px;
        }

        /* Responsive */
        @media (max-width: 968px) {
            .apropos-content {
                grid-template-columns: 1fr;
                gap: 3rem;
            }

            .apropos-text {
                text-align: center;
                order: 2;
            }

            .apropos-text h2::after {
                left: 50%;
                transform: translateX(-50%);
            }

            .apropos-image {
                order: 1;
            }

            .hero h1 {
                font-size: 2.8rem;
            }

            .badge-1, .badge-2 {
                display: none;
            }
        }

        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 0.5rem;
            }

            .nav-links {
                gap: 2rem;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .form-grid {
                grid-template-columns: 1fr;
            }

            .whatsapp-container {
                padding: 2rem;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.8rem;
            }

            .apropos-text h2 {
                font-size: 2rem;
            }

            .whatsapp-header h3 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <!-- Éléments de brume -->
    <div class="mist mist-1"></div>
    <div class="mist mist-2"></div>
    <div class="mist mist-3"></div>
    
    <!-- Nuages légers -->
    <div class="cloud cloud-1"></div>
    <div class="cloud cloud-2"></div>
    
    <!-- Plumes de Muichiro -->
    <div class="feather feather-1">🕊️</div>
    <div class="feather feather-2">🪶</div>
    <div class="feather feather-3">🍃</div>
    
    <!-- Particules de brume -->
    <div class="mist-particle particle-1"></div>
    <div class="mist-particle particle-2"></div>
    <div class="mist-particle particle-3"></div>
    <div class="mist-particle particle-4"></div>
    <div class="mist-particle particle-5"></div>

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
                    <span class="skill">Responsive</span>
                </div>
            </div>
            <div class="apropos-image">
                <div class="image-frame">
                    <div class="mist-circle"></div>
                    <div class="mist-circle-2"></div>
                    <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/642754626_122112963513211419_7763551596132436351_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=HrPMD1Mzk-wQ7kNvwF-W0Kk&_nc_oc=AdmitmpVlD_NkLZbjv5bb1BdGCCLKrDWIu8jwSkutlrW38sKkCh-4igqUNpNQk8v2sg&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=UrnADD8nIJ14FGwl_Mt82Q&_nc_ss=8&oh=00_AfxextLBeI-e-uEMJr1xXOL4FM1WFzyiLwUla6pesQhiMA&oe=69AAF757" alt="Photo de profil">
                </div>
                <div class="badge badge-1">開発者</div>
                <div class="badge badge-2">霧の呼吸</div>
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
                    Envoyez-moi un message instantanément
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
                statusElement.style.background = 'rgba(37,211,102,0.1)';
                statusElement.style.color = '#25D366';
            } else {
                statusElement.innerHTML = '⏰ HORS HORAIRE - Réponse à mon retour';
                statusElement.style.background = 'rgba(255,165,0,0.1)';
                statusElement.style.color = '#FFA500';
            }
        }

        // Smooth scroll
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

        document.addEventListener('DOMContentLoaded', function() {
            updateAvailability();
            setInterval(updateAvailability, 60000);
        });
    </script>
</body>
</html>
