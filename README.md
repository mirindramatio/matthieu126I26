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
            color: #0f172a;
            background: linear-gradient(135deg, #0a0f1a 0%, #141c2c 100%);
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

        /* ===== ANIMATIONS SPECTACULAIRES ===== */
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0); }
            50% { transform: translateY(-20px) rotate(2deg); }
        }

        @keyframes float-slow {
            0%, 100% { transform: translateY(0) scale(1); }
            50% { transform: translateY(-15px) scale(1.02); }
        }

        @keyframes pulse-glow {
            0%, 100% { opacity: 0.2; filter: blur(30px); transform: scale(1); }
            50% { opacity: 0.4; filter: blur(40px); transform: scale(1.2); }
        }

        @keyframes rotate-slow {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes rotate-reverse {
            from { transform: rotate(360deg); }
            to { transform: rotate(0deg); }
        }

        @keyframes shimmer {
            0% { background-position: -200% 0; }
            100% { background-position: 200% 0; }
        }

        @keyframes borderPulse {
            0%, 100% { border-color: rgba(56, 189, 248, 0.3); box-shadow: 0 0 20px rgba(56, 189, 248, 0.2); }
            50% { border-color: rgba(139, 92, 246, 0.6); box-shadow: 0 0 40px rgba(139, 92, 246, 0.4); }
        }

        @keyframes lightRays {
            0% { transform: rotate(0deg) scale(1); opacity: 0.1; }
            50% { transform: rotate(180deg) scale(1.2); opacity: 0.2; }
            100% { transform: rotate(360deg) scale(1); opacity: 0.1; }
        }

        @keyframes sparkle {
            0%, 100% { opacity: 0; transform: scale(0); }
            50% { opacity: 1; transform: scale(1); }
        }

        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-60px) rotate(-2deg); }
            to { opacity: 1; transform: translateX(0) rotate(0); }
        }

        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(60px) rotate(2deg); }
            to { opacity: 1; transform: translateX(0) rotate(0); }
        }

        @keyframes zoomIn {
            from { opacity: 0; transform: scale(0.8) rotate(-5deg); }
            to { opacity: 1; transform: scale(1) rotate(0); }
        }

        /* ===== ÉLÉMENTS DÉCORATIFS GÉNÉRAUX ===== */
        .orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(50px);
            pointer-events: none;
            z-index: 0;
            animation: pulse-glow 10s ease-in-out infinite;
        }

        .orb-1 {
            top: 10%;
            left: 5%;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(56,189,248,0.15) 0%, transparent 70%);
        }

        .orb-2 {
            bottom: 10%;
            right: 5%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(139,92,246,0.12) 0%, transparent 70%);
            animation-delay: 3s;
        }

        .orb-3 {
            top: 40%;
            right: 20%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(251,146,60,0.08) 0%, transparent 70%);
            animation-delay: 6s;
        }

        .floating-icon {
            position: fixed;
            font-size: 2rem;
            opacity: 0.15;
            pointer-events: none;
            z-index: 0;
        }

        .icon-1 { top: 15%; left: 8%; animation: float 12s ease-in-out infinite; }
        .icon-2 { top: 70%; right: 10%; animation: float-slow 15s ease-in-out infinite reverse; }
        .icon-3 { bottom: 25%; left: 12%; animation: float 14s ease-in-out infinite; }
        .icon-4 { bottom: 35%; right: 15%; animation: rotate-slow 25s linear infinite; }

        /* ===== HEADER ===== */
        header {
            background: rgba(10, 15, 25, 0.7);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border-bottom: 1px solid rgba(56, 189, 248, 0.15);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            animation: slideInLeft 1s ease-out;
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
            color: #e0f2fe;
            text-decoration: none;
            letter-spacing: -0.5px;
            text-shadow: 0 0 15px rgba(56, 189, 248, 0.5);
            transition: all 0.3s;
        }

        .logo:hover {
            text-shadow: 0 0 25px rgba(139, 92, 246, 0.8);
            transform: translateY(-2px);
        }

        .nav-links {
            display: flex;
            gap: 3rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #b0c4de;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, #38bdf8, #8b5cf6);
            transform: scaleX(0);
            transition: transform 0.3s;
        }

        .nav-links a:hover {
            color: #e0f2fe;
            text-shadow: 0 0 10px rgba(56, 189, 248, 0.5);
        }

        .nav-links a:hover::after {
            transform: scaleX(1);
        }

        /* ===== SECTION ACCUEIL ===== */
        #accueil {
            min-height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero {
            max-width: 900px;
            margin: 0 auto;
            animation: zoomIn 1.2s ease-out;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            color: #e0f2fe;
            line-height: 1.2;
            text-shadow: 0 0 20px rgba(56, 189, 248, 0.5);
            animation: float 6s ease-in-out infinite;
        }

        .hero p {
            font-size: 1.4rem;
            color: #b0c4de;
            margin-bottom: 2.5rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        .btn {
            display: inline-block;
            padding: 16px 45px;
            background: linear-gradient(135deg, rgba(56, 189, 248, 0.2), rgba(139, 92, 246, 0.2));
            color: #e0f2fe;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            border: 1px solid rgba(56, 189, 248, 0.3);
            backdrop-filter: blur(5px);
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
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
            transform: translateY(-5px);
            border-color: #8b5cf6;
            box-shadow: 0 20px 30px -5px rgba(139, 92, 246, 0.3);
        }

        .btn:hover::before {
            left: 100%;
        }

        /* ===== SECTION À PROPOS - BLEU CIEL ===== */
        #apropos {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            background: linear-gradient(135deg, 
                #e0f2fe 0%,
                #bae6fd 25%,
                #7dd3fc 50%,
                #38bdf8 75%,
                #0ea5e9 100%);
            background-size: 400% 400%;
            animation: gradientFlow 15s ease infinite;
        }

        @keyframes gradientFlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Éléments décoratifs spéciaux pour la section bleue */
        .blue-decor {
            position: absolute;
            pointer-events: none;
            z-index: 1;
        }

        .blue-decor-1 {
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 30%, rgba(255,255,255,0.3) 0%, transparent 30%),
                        radial-gradient(circle at 80% 70%, rgba(255,255,255,0.2) 0%, transparent 30%);
            animation: pulse-glow 8s ease-in-out infinite;
        }

        .blue-decor-2 {
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 20px,
                rgba(255,255,255,0.05) 20px,
                rgba(255,255,255,0.05) 40px
            );
            animation: rotate-slow 60s linear infinite;
        }

        .blue-decor-3 {
            bottom: 0;
            right: 0;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(255,255,255,0.2) 0%, transparent 70%);
            border-radius: 50%;
            filter: blur(30px);
            animation: float 15s ease-in-out infinite;
        }

        .blue-decor-4 {
            top: 20%;
            right: 10%;
            width: 200px;
            height: 200px;
            border: 3px dashed rgba(255,255,255,0.2);
            border-radius: 50%;
            animation: rotate-slow 25s linear infinite;
        }

        .blue-decor-5 {
            bottom: 30%;
            left: 5%;
            width: 150px;
            height: 150px;
            background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.3) 2px, transparent 2px);
            background-size: 20px 20px;
            animation: float-slow 20s ease-in-out infinite;
        }

        /* Flocons de lumière */
        .light-particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: white;
            border-radius: 50%;
            filter: blur(2px);
            opacity: 0.3;
            animation: sparkle 4s ease-in-out infinite;
        }

        .light-particle:nth-child(1) { top: 20%; left: 10%; animation-delay: 0s; }
        .light-particle:nth-child(2) { top: 40%; left: 30%; animation-delay: 1s; }
        .light-particle:nth-child(3) { top: 60%; left: 50%; animation-delay: 2s; }
        .light-particle:nth-child(4) { top: 80%; left: 70%; animation-delay: 3s; }
        .light-particle:nth-child(5) { top: 30%; left: 80%; animation-delay: 4s; }
        .light-particle:nth-child(6) { top: 70%; left: 20%; animation-delay: 5s; }

        .apropos-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: center;
            position: relative;
            z-index: 10;
        }

        .apropos-text {
            animation: slideInLeft 1s ease-out;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            padding: 3rem;
            border-radius: 40px;
            border: 1px solid rgba(255,255,255,0.3);
            box-shadow: 0 30px 50px -20px rgba(0,0,0,0.2);
        }

        .apropos-text h2 {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 2rem;
            color: #0f172a;
            position: relative;
            display: inline-block;
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #0f172a, #1e293b);
            border-radius: 2px;
        }

        .apropos-text p {
            color: #0f172a;
            margin-bottom: 1.2rem;
            font-size: 1.1rem;
            line-height: 1.8;
            transition: all 0.4s;
            font-weight: 500;
        }

        .apropos-text p:hover {
            transform: translateX(10px);
            color: #ffffff;
            text-shadow: 0 0 10px rgba(255,255,255,0.3);
        }

        .apropos-text p:last-of-type {
            font-style: italic;
            color: #0f172a;
            margin-top: 2rem;
            padding: 1.5rem;
            background: rgba(255,255,255,0.3);
            border-radius: 20px;
            border-left: 4px solid #0f172a;
            font-size: 1.2rem;
            font-weight: 600;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2.5rem;
        }

        .skill {
            padding: 10px 28px;
            background: rgba(255, 255, 255, 0.3);
            border: 1px solid rgba(255,255,255,0.4);
            border-radius: 30px;
            color: #0f172a;
            font-weight: 600;
            font-size: 0.95rem;
            transition: all 0.4s;
            backdrop-filter: blur(5px);
            cursor: default;
            position: relative;
            overflow: hidden;
            animation: zoomIn 0.8s ease-out;
            animation-fill-mode: both;
        }

        .skill:nth-child(1) { animation-delay: 0.1s; }
        .skill:nth-child(2) { animation-delay: 0.2s; }
        .skill:nth-child(3) { animation-delay: 0.3s; }
        .skill:nth-child(4) { animation-delay: 0.4s; }
        .skill:nth-child(5) { animation-delay: 0.5s; }

        .skill:hover {
            transform: translateY(-5px) scale(1.05);
            background: rgba(255,255,255,0.5);
            border-color: white;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.2);
            color: #0f172a;
        }

        /* Photo de profil avec design très spécial */
        .apropos-image {
            position: relative;
            display: flex;
            justify-content: center;
            animation: slideInRight 1s ease-out;
        }

        /* Cadre principal */
        .image-frame {
            position: relative;
            width: 100%;
            max-width: 450px;
            aspect-ratio: 1/1;
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            background: linear-gradient(135deg, #ffffff, #e0f2fe);
            padding: 8px;
            box-shadow: 
                0 40px 60px -20px rgba(0,0,0,0.3),
                0 0 0 2px rgba(255,255,255,0.5),
                0 0 0 5px rgba(56,189,248,0.3);
            animation: borderPulse 4s ease-in-out infinite;
        }

        /* Effet de lumière tournante */
        .image-frame::before {
            content: '';
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.5),
                rgba(56,189,248,0.5),
                rgba(139,92,246,0.5),
                rgba(255,255,255,0.5));
            border-radius: inherit;
            filter: blur(20px);
            animation: rotate-slow 10s linear infinite;
            z-index: -1;
        }

        /* Cercles concentriques */
        .image-frame .circle-1,
        .image-frame .circle-2,
        .image-frame .circle-3 {
            position: absolute;
            border-radius: 50%;
            border: 2px dashed rgba(255,255,255,0.3);
            animation: rotate-slow 15s linear infinite;
        }

        .image-frame .circle-1 {
            top: -20px;
            left: -20px;
            right: -20px;
            bottom: -20px;
            border-width: 2px;
        }

        .image-frame .circle-2 {
            top: -30px;
            left: -30px;
            right: -30px;
            bottom: -30px;
            border-width: 1px;
            animation-direction: reverse;
            animation-duration: 20s;
        }

        .image-frame .circle-3 {
            top: -40px;
            left: -40px;
            right: -40px;
            bottom: -40px;
            border-width: 1px;
            border-style: dotted;
            animation-duration: 25s;
        }

        /* Rayons de lumière */
        .light-rays {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 200%;
            height: 200%;
            background: conic-gradient(
                from 0deg,
                transparent,
                rgba(255,255,255,0.1) 10deg,
                transparent 20deg,
                rgba(255,255,255,0.1) 30deg,
                transparent 40deg,
                rgba(56,189,248,0.1) 50deg,
                transparent 60deg,
                rgba(139,92,246,0.1) 70deg,
                transparent 80deg
            );
            animation: lightRays 20s linear infinite;
            border-radius: 50%;
            z-index: -1;
        }

        /* Étoiles filantes */
        .shooting-star {
            position: absolute;
            width: 100px;
            height: 2px;
            background: linear-gradient(90deg, white, transparent);
            filter: blur(2px);
            opacity: 0.3;
            animation: lightRay 8s linear infinite;
        }

        .shooting-star-1 {
            top: 20%;
            right: 10%;
            transform: rotate(45deg);
            animation-delay: 0s;
        }

        .shooting-star-2 {
            bottom: 30%;
            left: 5%;
            transform: rotate(-30deg);
            animation-delay: 4s;
        }

        @keyframes lightRay {
            0% {
                transform: translateX(-100%) translateY(-100%) rotate(45deg);
                opacity: 0;
            }
            10% {
                opacity: 0.3;
            }
            20% {
                transform: translateX(100%) translateY(100%) rotate(45deg);
                opacity: 0;
            }
            100% {
                transform: translateX(100%) translateY(100%) rotate(45deg);
                opacity: 0;
            }
        }

        .apropos-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: inherit;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: block;
            filter: brightness(1.05) contrast(1.02);
            box-shadow: inset 0 0 20px rgba(255,255,255,0.3);
        }

        .apropos-image img:hover {
            transform: scale(1.02);
            filter: brightness(1.1) contrast(1.05);
        }

        /* Badges décoratifs */
        .badge {
            position: absolute;
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(5px);
            padding: 8px 18px;
            border-radius: 30px;
            color: #0f172a;
            font-weight: 600;
            font-size: 0.9rem;
            border: 1px solid rgba(255,255,255,0.3);
            animation: float 5s ease-in-out infinite;
            white-space: nowrap;
        }

        .badge-1 {
            top: 10%;
            right: -20px;
            animation-delay: 0s;
        }

        .badge-2 {
            bottom: 15%;
            left: -20px;
            animation-delay: 2s;
        }

        .badge-3 {
            top: 40%;
            left: -30px;
            animation-delay: 4s;
        }

        /* ===== SECTION CONTACT ===== */
        #contact {
            min-height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            position: relative;
            background: linear-gradient(135deg, 
                rgba(10,15,25,0.95) 0%, 
                rgba(20,25,40,0.95) 100%);
        }

        #contact h2 {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: #e0f2fe;
            text-shadow: 0 0 15px rgba(56, 189, 248, 0.3);
        }

        .contact-subtitle {
            color: #b0c4de;
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
            background: rgba(20, 25, 40, 0.6);
            backdrop-filter: blur(10px);
            padding: 2.5rem 2rem;
            border-radius: 30px;
            border: 1px solid rgba(56, 189, 248, 0.15);
            transition: all 0.5s;
            animation: zoomIn 0.8s ease-out;
            animation-fill-mode: both;
        }

        .contact-card:nth-child(1) { animation-delay: 0.1s; }
        .contact-card:nth-child(2) { animation-delay: 0.2s; }
        .contact-card:nth-child(3) { animation-delay: 0.3s; }

        .contact-card:hover {
            transform: translateY(-15px) scale(1.02);
            border-color: rgba(139, 92, 246, 0.3);
            box-shadow: 0 30px 40px -15px rgba(139, 92, 246, 0.2);
        }

        .contact-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            animation: float 4s ease-in-out infinite;
        }

        .contact-card h3 {
            font-size: 1.4rem;
            color: #e0f2fe;
            margin-bottom: 0.8rem;
        }

        .contact-card p {
            color: #b0c4de;
            margin-bottom: 1.5rem;
        }

        .contact-link {
            display: inline-block;
            padding: 12px 32px;
            background: rgba(56, 189, 248, 0.1);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 50px;
            border: 1px solid rgba(56, 189, 248, 0.2);
            transition: all 0.4s;
        }

        .contact-link:hover {
            background: linear-gradient(135deg, rgba(56,189,248,0.2), rgba(139,92,246,0.2));
            color: #e0f2fe;
            border-color: #8b5cf6;
            transform: translateY(-3px);
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
            padding: 12px 30px;
            background: rgba(20, 25, 40, 0.6);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 50px;
            border: 1px solid rgba(56, 189, 248, 0.15);
            transition: all 0.4s;
        }

        .social-link:hover {
            background: rgba(139, 92, 246, 0.15);
            color: #e0f2fe;
            border-color: #8b5cf6;
            transform: translateY(-5px);
        }

        /* ===== SECTION WHATSAPP ===== */
        .whatsapp-section {
            padding: 100px 0;
            background: linear-gradient(135deg, 
                rgba(10,15,25,0.98) 0%, 
                rgba(15,20,30,0.98) 100%);
        }

        .whatsapp-container {
            max-width: 900px;
            margin: 0 auto;
            background: rgba(20, 25, 40, 0.6);
            backdrop-filter: blur(15px);
            padding: 3.5rem;
            border-radius: 60px;
            border: 1px solid rgba(56, 189, 248, 0.15);
            animation: zoomIn 1s ease-out;
        }

        .whatsapp-header {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .whatsapp-icon-large {
            font-size: 4rem;
            animation: float 3s ease-in-out infinite;
            filter: drop-shadow(0 0 15px rgba(37,211,102,0.3));
        }

        .whatsapp-header h3 {
            font-size: 2.5rem;
            font-weight: 700;
            color: #e0f2fe;
        }

        .whatsapp-header h3 span {
            color: #25D366;
            text-shadow: 0 0 15px rgba(37,211,102,0.3);
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .form-group {
            text-align: left;
        }

        .form-group label {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.8rem;
            color: #b0c4de;
            font-weight: 600;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 14px 20px;
            background: rgba(10, 15, 25, 0.6);
            border: 2px solid rgba(56, 189, 248, 0.15);
            border-radius: 20px;
            font-size: 1rem;
            color: #e0f2fe;
            transition: all 0.4s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #38bdf8;
            box-shadow: 0 0 0 4px rgba(56,189,248,0.1);
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        .whatsapp-btn {
            width: 100%;
            padding: 18px 40px;
            background: linear-gradient(135deg, rgba(37,211,102,0.2), rgba(18,140,126,0.2));
            color: #e0f2fe;
            border: 1px solid rgba(37,211,102,0.3);
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.5s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
        }

        .whatsapp-btn:hover {
            transform: translateY(-5px);
            border-color: #25D366;
            box-shadow: 0 20px 30px -5px rgba(37,211,102,0.2);
        }

        .availability-info {
            margin-top: 2.5rem;
            padding: 2rem;
            background: rgba(10, 15, 25, 0.4);
            border-radius: 30px;
            border: 1px solid rgba(56, 189, 248, 0.15);
        }

        .schedule {
            display: flex;
            justify-content: center;
            gap: 2.5rem;
            margin: 1.5rem 0;
            flex-wrap: wrap;
        }

        .time-badge {
            padding: 10px 25px;
            background: rgba(20, 25, 40, 0.6);
            border-radius: 40px;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            border: 1px solid rgba(56, 189, 248, 0.2);
            color: #b0c4de;
            transition: all 0.4s;
        }

        .time-badge:hover {
            transform: scale(1.05);
            border-color: #8b5cf6;
            color: #e0f2fe;
        }

        .time-badge.morning { border-left: 4px solid #38bdf8; }
        .time-badge.afternoon { border-left: 4px solid #8b5cf6; }

        .availability-status {
            display: inline-block;
            padding: 8px 25px;
            background: rgba(37,211,102,0.1);
            border-radius: 40px;
            color: #25D366;
            font-weight: 600;
            border: 1px solid rgba(37,211,102,0.2);
            animation: glowPulse 3s ease-in-out infinite;
        }

        /* ===== FOOTER ===== */
        footer {
            background: rgba(5, 10, 15, 0.8);
            color: #b0c4de;
            text-align: center;
            padding: 2.5rem 0;
            border-top: 1px solid rgba(56, 189, 248, 0.1);
        }

        footer p {
            font-size: 1rem;
            animation: float 6s ease-in-out infinite;
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
                font-size: 2.5rem;
            }

            .badge-1, .badge-2, .badge-3 {
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
                font-size: 2rem;
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

            .contact-card {
                padding: 2rem 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Orbes lumineux -->
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>
    <div class="orb orb-3"></div>
    
    <!-- Icônes flottantes -->
    <div class="floating-icon icon-1">✨</div>
    <div class="floating-icon icon-2">💫</div>
    <div class="floating-icon icon-3">🌟</div>
    <div class="floating-icon icon-4">⚡</div>

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
        <!-- Éléments décoratifs bleus -->
        <div class="blue-decor blue-decor-1"></div>
        <div class="blue-decor blue-decor-2"></div>
        <div class="blue-decor blue-decor-3"></div>
        <div class="blue-decor blue-decor-4"></div>
        <div class="blue-decor blue-decor-5"></div>
        
        <!-- Particules de lumière -->
        <div class="light-particle"></div>
        <div class="light-particle"></div>
        <div class="light-particle"></div>
        <div class="light-particle"></div>
        <div class="light-particle"></div>
        <div class="light-particle"></div>

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
                    <span class="skill">UI/UX</span>
                </div>
            </div>
            <div class="apropos-image">
                <div class="image-frame">
                    <div class="circle-1"></div>
                    <div class="circle-2"></div>
                    <div class="circle-3"></div>
                    <div class="light-rays"></div>
                    <div class="shooting-star shooting-star-1"></div>
                    <div class="shooting-star shooting-star-2"></div>
                    <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/642754626_122112963513211419_7763551596132436351_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=HrPMD1Mzk-wQ7kNvwF-W0Kk&_nc_oc=AdmitmpVlD_NkLZbjv5bb1BdGCCLKrDWIu8jwSkutlrW38sKkCh-4igqUNpNQk8v2sg&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=UrnADD8nIJ14FGwl_Mt82Q&_nc_ss=8&oh=00_AfxextLBeI-e-uEMJr1xXOL4FM1WFzyiLwUla6pesQhiMA&oe=69AAF757" alt="Photo de profil - RATIANARIVO Mirindra Matthieu">
                </div>
                <div class="badge badge-1">✨ Développeur</div>
                <div class="badge badge-2">💡 Créatif</div>
                <div class="badge badge-3">🚀 Passionné</div>
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
                statusElement.style.background = 'rgba(37,211,102,0.15)';
                statusElement.style.color = '#25D366';
                statusElement.style.border = '1px solid rgba(37,211,102,0.3)';
            } else {
                statusElement.innerHTML = '⏰ HORS HORAIRE - Réponse à mon retour';
                statusElement.style.background = 'rgba(255,165,0,0.15)';
                statusElement.style.color = '#FFA500';
                statusElement.style.border = '1px solid rgba(255,165,0,0.3)';
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
