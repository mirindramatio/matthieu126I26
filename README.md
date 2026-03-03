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
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 50%, #dbeafe 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ===== ANIMATIONS AVANCÉES ===== */
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0); }
            50% { transform: translateY(-20px) rotate(1deg); }
        }

        @keyframes float-slow {
            0%, 100% { transform: translateY(0) scale(1); }
            50% { transform: translateY(-15px) scale(1.02); }
        }

        @keyframes float-fast {
            0%, 100% { transform: translateY(0) rotate(-1deg); }
            50% { transform: translateY(-10px) rotate(1deg); }
        }

        @keyframes pulse-glow {
            0%, 100% { 
                opacity: 0.4;
                transform: scale(1);
                filter: blur(20px);
            }
            50% { 
                opacity: 0.8;
                transform: scale(1.2);
                filter: blur(30px);
            }
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

        @keyframes border-pulse {
            0%, 100% { 
                box-shadow: 0 0 20px rgba(56, 189, 248, 0.2);
                border-color: rgba(56, 189, 248, 0.3);
            }
            50% { 
                box-shadow: 0 0 40px rgba(56, 189, 248, 0.4);
                border-color: rgba(56, 189, 248, 0.8);
            }
        }

        @keyframes gradient-shift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes wave {
            0% { transform: translateX(0) translateY(0); }
            25% { transform: translateX(-25%) translateY(5px); }
            50% { transform: translateX(-50%) translateY(0); }
            75% { transform: translateX(-25%) translateY(-5px); }
            100% { transform: translateX(0) translateY(0); }
        }

        @keyframes spin-slow {
            from { transform: rotate(0deg) scale(1); }
            to { transform: rotate(360deg) scale(1.1); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-60px) rotate(-2deg);
            }
            to {
                opacity: 1;
                transform: translateX(0) rotate(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(60px) rotate(2deg);
            }
            to {
                opacity: 1;
                transform: translateX(0) rotate(0);
            }
        }

        @keyframes zoomIn {
            from {
                opacity: 0;
                transform: scale(0.8) rotate(-5deg);
            }
            to {
                opacity: 1;
                transform: scale(1) rotate(0);
            }
        }

        @keyframes flipIn {
            from {
                opacity: 0;
                transform: perspective(400px) rotateY(90deg);
            }
            to {
                opacity: 1;
                transform: perspective(400px) rotateY(0);
            }
        }

        @keyframes tiltIn {
            from {
                opacity: 0;
                transform: perspective(500px) rotateX(20deg) translateY(30px);
            }
            to {
                opacity: 1;
                transform: perspective(500px) rotateX(0) translateY(0);
            }
        }

        /* ===== ÉLÉMENTS DÉCORATIFS DYNAMIQUES ===== */
        .orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(40px);
            pointer-events: none;
            z-index: -1;
            animation: pulse-glow 8s ease-in-out infinite;
        }

        .orb-1 {
            top: 10%;
            left: 5%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(56,189,248,0.4) 0%, rgba(139,92,246,0.2) 70%);
            animation-delay: 0s;
        }

        .orb-2 {
            bottom: 10%;
            right: 5%;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(139,92,246,0.3) 0%, rgba(56,189,248,0.2) 70%);
            animation-delay: 2s;
        }

        .orb-3 {
            top: 40%;
            right: 20%;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(251,146,60,0.2) 0%, rgba(56,189,248,0.2) 70%);
            animation-delay: 4s;
        }

        .floating-shape {
            position: fixed;
            border: 2px solid rgba(56,189,248,0.2);
            pointer-events: none;
            z-index: -1;
        }

        .shape-1 {
            top: 15%;
            left: 10%;
            width: 150px;
            height: 150px;
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            animation: float-slow 14s ease-in-out infinite, rotate-slow 40s linear infinite;
        }

        .shape-2 {
            bottom: 20%;
            right: 12%;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border-style: dashed;
            animation: float-fast 10s ease-in-out infinite, rotate-reverse 30s linear infinite;
        }

        .shape-3 {
            top: 30%;
            right: 25%;
            width: 100px;
            height: 100px;
            border-radius: 20px;
            transform: rotate(45deg);
            animation: bounce 6s ease-in-out infinite;
        }

        .floating-icon {
            position: fixed;
            font-size: 2rem;
            opacity: 0.2;
            pointer-events: none;
            z-index: -1;
            filter: drop-shadow(0 10px 15px rgba(0,0,0,0.1));
        }

        .icon-1 { top: 20%; left: 8%; animation: float 12s ease-in-out infinite; }
        .icon-2 { top: 70%; right: 10%; animation: float-slow 15s ease-in-out infinite reverse; }
        .icon-3 { bottom: 30%; left: 15%; animation: bounce 8s ease-in-out infinite; }
        .icon-4 { bottom: 40%; right: 20%; animation: spin-slow 20s linear infinite; }
        .icon-5 { top: 50%; left: 25%; animation: float-fast 9s ease-in-out infinite; }
        .icon-6 { top: 80%; right: 30%; animation: rotate-slow 25s linear infinite; }

        /* Particules */
        .particle {
            position: fixed;
            width: 4px;
            height: 4px;
            background: rgba(56,189,248,0.3);
            border-radius: 50%;
            pointer-events: none;
            z-index: -1;
        }

        .particle-1 { top: 30%; left: 20%; animation: float 7s ease-in-out infinite; }
        .particle-2 { top: 60%; left: 40%; animation: float 9s ease-in-out infinite reverse; }
        .particle-3 { top: 40%; left: 70%; animation: float 8s ease-in-out infinite; }
        .particle-4 { top: 70%; left: 80%; animation: float 10s ease-in-out infinite reverse; }
        .particle-5 { top: 20%; left: 90%; animation: float 6s ease-in-out infinite; }

        /* ===== HEADER ULTRA MODERNE ===== */
        header {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.02);
            border-bottom: 1px solid rgba(255,255,255,0.5);
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
            font-size: 1.5rem;
            font-weight: 700;
            color: #0f172a;
            text-decoration: none;
            letter-spacing: -0.5px;
            background: linear-gradient(135deg, #0f172a, #38bdf8, #8b5cf6);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient-shift 5s ease infinite;
            transition: all 0.3s;
        }

        .logo:hover {
            transform: scale(1.05);
            filter: drop-shadow(0 10px 15px rgba(56,189,248,0.3));
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

        .nav-links a::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, #38bdf8, #8b5cf6, #38bdf8);
            background-size: 200% auto;
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.3s;
            animation: gradient-shift 3s ease infinite;
        }

        .nav-links a:hover {
            color: #0f172a;
            transform: translateY(-2px);
        }

        .nav-links a:hover::before {
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
            overflow: hidden;
        }

        /* Accueil */
        #accueil {
            background: linear-gradient(135deg, 
                rgba(56,189,248,0.1) 0%, 
                rgba(139,92,246,0.1) 50%,
                rgba(56,189,248,0.1) 100%);
            background-size: 200% 200%;
            animation: gradient-shift 10s ease infinite;
            text-align: center;
        }

        .hero {
            max-width: 900px;
            margin: 0 auto;
            animation: zoomIn 1.2s cubic-bezier(0.23, 1, 0.32, 1);
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            color: #0f172a;
            line-height: 1.2;
            background: linear-gradient(135deg, #0f172a, #38bdf8, #8b5cf6, #0f172a);
            background-size: 300% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient-shift 8s ease infinite;
            text-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .hero p {
            font-size: 1.4rem;
            color: #475569;
            margin-bottom: 2.5rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            animation: tiltIn 1.4s ease-out 0.2s both;
        }

        .btn {
            display: inline-block;
            padding: 16px 45px;
            background: linear-gradient(135deg, #0f172a, #1e293b, #38bdf8);
            background-size: 200% auto;
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            letter-spacing: 0.5px;
            transition: all 0.4s;
            border: 1px solid rgba(255,255,255,0.2);
            position: relative;
            overflow: hidden;
            box-shadow: 0 15px 30px -5px rgba(0,0,0,0.2);
            animation: border-pulse 3s infinite;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.6s;
        }

        .btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 25px 40px -5px rgba(56,189,248,0.4);
            background-position: right center;
        }

        .btn:hover::before {
            left: 100%;
        }

        /* À propos - Photo à droite, texte à gauche */
        #apropos {
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.9) 0%, 
                rgba(240,249,255,0.9) 100%);
            backdrop-filter: blur(10px);
        }

        .apropos-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: center;
        }

        .apropos-text {
            animation: slideInLeft 1s cubic-bezier(0.23, 1, 0.32, 1);
        }

        .apropos-text h2 {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 2rem;
            color: #0f172a;
            position: relative;
            display: inline-block;
        }

        .apropos-text h2::before {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #38bdf8, #8b5cf6, #38bdf8);
            background-size: 200% auto;
            border-radius: 2px;
            animation: gradient-shift 3s ease infinite, slideInLeft 0.5s ease-out;
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            right: 0;
            width: 30px;
            height: 4px;
            background: linear-gradient(90deg, #8b5cf6, #38bdf8);
            border-radius: 2px;
            opacity: 0.5;
        }

        .apropos-text p {
            color: #475569;
            margin-bottom: 1.2rem;
            font-size: 1.1rem;
            line-height: 1.8;
            transform: translateX(0);
            transition: all 0.4s;
            padding-left: 0;
            border-left: 3px solid transparent;
        }

        .apropos-text p:hover {
            transform: translateX(15px);
            color: #0f172a;
            border-left-color: #38bdf8;
            padding-left: 15px;
        }

        .apropos-text p:last-of-type {
            font-style: italic;
            color: #38bdf8;
            margin-top: 2rem;
            padding: 1.5rem;
            background: linear-gradient(135deg, #f0f9ff, #ffffff);
            border-radius: 20px;
            border-left: 4px solid #38bdf8;
            box-shadow: 0 10px 30px -10px rgba(56,189,248,0.2);
            animation: border-pulse 3s infinite;
            font-size: 1.2rem;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2.5rem;
        }

        .skill {
            padding: 10px 28px;
            background: white;
            border: 1px solid #e2e8f0;
            border-radius: 30px;
            color: #1e293b;
            font-weight: 600;
            font-size: 0.95rem;
            transition: all 0.4s;
            box-shadow: 0 4px 10px rgba(0,0,0,0.02);
            cursor: default;
            position: relative;
            overflow: hidden;
            animation: flipIn 0.8s ease-out;
            animation-fill-mode: both;
        }

        .skill:nth-child(1) { animation-delay: 0.1s; }
        .skill:nth-child(2) { animation-delay: 0.2s; }
        .skill:nth-child(3) { animation-delay: 0.3s; }
        .skill:nth-child(4) { animation-delay: 0.4s; }
        .skill:nth-child(5) { animation-delay: 0.5s; }

        .skill::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(56,189,248,0.2), transparent);
            transition: left 0.5s;
        }

        .skill:hover {
            border-color: transparent;
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 15px 30px -5px rgba(56,189,248,0.3);
            background: linear-gradient(135deg, #f0f9ff, #ffffff);
        }

        .skill:hover::before {
            left: 100%;
        }

        .apropos-image {
            position: relative;
            display: flex;
            justify-content: center;
            animation: slideInRight 1s cubic-bezier(0.23, 1, 0.32, 1);
        }

        .apropos-image::before {
            content: '';
            position: absolute;
            top: -30px;
            left: -30px;
            right: -30px;
            bottom: -30px;
            background: radial-gradient(circle, rgba(56,189,248,0.3) 0%, transparent 70%);
            border-radius: 40px;
            animation: pulse-glow 5s ease-in-out infinite;
            z-index: 1;
        }

        .apropos-image::after {
            content: '';
            position: absolute;
            top: -20px;
            left: -20px;
            right: -20px;
            bottom: -20px;
            border: 3px dashed rgba(56,189,248,0.3);
            border-radius: 30px;
            animation: rotate-slow 30s linear infinite;
            z-index: 1;
        }

        .apropos-image img {
            width: 100%;
            max-width: 400px;
            height: auto;
            border-radius: 30px;
            box-shadow: 
                0 30px 40px -20px rgba(0,0,0,0.3),
                0 0 0 5px rgba(255,255,255,0.5),
                0 0 0 8px rgba(56,189,248,0.1);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            z-index: 2;
            filter: brightness(1.02) contrast(1.02);
            animation: float 6s ease-in-out infinite;
        }

        .apropos-image img:hover {
            transform: scale(1.08) rotate(2deg);
            box-shadow: 
                0 40px 60px -20px rgba(56,189,248,0.4),
                0 0 0 8px rgba(255,255,255,0.8),
                0 0 0 12px rgba(56,189,248,0.2);
        }

        /* Contact */
        #contact {
            background: linear-gradient(135deg, 
                rgba(56,189,248,0.05) 0%, 
                rgba(139,92,246,0.05) 50%,
                rgba(56,189,248,0.05) 100%);
            background-size: 200% 200%;
            animation: gradient-shift 12s ease infinite;
            text-align: center;
        }

        #contact h2 {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: #0f172a;
            animation: zoomIn 1s ease-out;
        }

        .contact-subtitle {
            color: #64748b;
            font-size: 1.2rem;
            margin-bottom: 3rem;
            animation: tiltIn 1.2s ease-out 0.2s both;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            padding: 2.5rem 2rem;
            border-radius: 30px;
            box-shadow: 0 20px 40px -15px rgba(0,0,0,0.1);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 1px solid rgba(255,255,255,0.5);
            position: relative;
            overflow: hidden;
            animation: flipIn 0.8s ease-out;
            animation-fill-mode: both;
        }

        .contact-card:nth-child(1) { animation-delay: 0.1s; }
        .contact-card:nth-child(2) { animation-delay: 0.2s; }
        .contact-card:nth-child(3) { animation-delay: 0.3s; }

        .contact-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, #38bdf8, #8b5cf6, #38bdf8);
            background-size: 200% auto;
            transform: translateX(-100%);
            transition: transform 0.6s;
            animation: gradient-shift 3s ease infinite;
        }

        .contact-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 100px;
            height: 100px;
            background: radial-gradient(circle, rgba(56,189,248,0.1) 0%, transparent 70%);
            border-radius: 50%;
            transform: translate(50%, 50%);
            transition: all 0.5s;
        }

        .contact-card:hover {
            transform: translateY(-20px) scale(1.02);
            box-shadow: 0 30px 50px -15px rgba(56,189,248,0.3);
            background: white;
        }

        .contact-card:hover::before {
            transform: translateX(0);
        }

        .contact-card:hover::after {
            transform: translate(30%, 30%) scale(1.5);
        }

        .contact-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            animation: bounce 4s ease-in-out infinite;
            filter: drop-shadow(0 10px 10px rgba(0,0,0,0.1));
        }

        .contact-card:hover .contact-icon {
            animation: bounce 1s ease-in-out infinite;
        }

        .contact-card h3 {
            font-size: 1.4rem;
            color: #0f172a;
            margin-bottom: 0.8rem;
            font-weight: 700;
        }

        .contact-card p {
            color: #64748b;
            margin-bottom: 1.5rem;
            font-size: 1rem;
            font-weight: 500;
        }

        .contact-link {
            display: inline-block;
            padding: 12px 32px;
            background: #f8fafc;
            color: #334155;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.95rem;
            transition: all 0.4s;
            border: 1px solid #e2e8f0;
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
            background: linear-gradient(90deg, transparent, rgba(56,189,248,0.2), transparent);
            transition: left 0.5s;
        }

        .contact-link:hover {
            background: linear-gradient(135deg, #38bdf8, #8b5cf6);
            color: white;
            border-color: transparent;
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 15px 30px -5px rgba(56,189,248,0.4);
        }

        .contact-link:hover::before {
            left: 100%;
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
            background: white;
            color: #334155;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.4s;
            border: 1px solid #e2e8f0;
            box-shadow: 0 5px 15px rgba(0,0,0,0.02);
            animation: flipIn 0.8s ease-out 0.4s both;
        }

        .social-link:hover {
            background: #0f172a;
            color: white;
            border-color: #0f172a;
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 20px 30px -5px rgba(0,0,0,0.2);
        }

        /* Formulaire WhatsApp */
        .whatsapp-section {
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.95) 0%, 
                rgba(240,249,255,0.95) 100%);
            padding: 100px 0;
            position: relative;
            border-top: 1px solid rgba(56,189,248,0.2);
            border-bottom: 1px solid rgba(56,189,248,0.2);
        }

        .whatsapp-container {
            max-width: 900px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(20px);
            padding: 3.5rem;
            border-radius: 60px;
            box-shadow: 0 40px 60px -20px rgba(0,0,0,0.2);
            border: 1px solid rgba(255,255,255,0.5);
            animation: zoomIn 1s ease-out;
            position: relative;
            overflow: hidden;
        }

        .whatsapp-container::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(37,211,102,0.1) 0%, transparent 70%);
            animation: rotate-slow 30s linear infinite;
        }

        .whatsapp-header {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2rem;
            position: relative;
            z-index: 1;
        }

        .whatsapp-icon-large {
            font-size: 4rem;
            animation: bounce 3s ease-in-out infinite;
            filter: drop-shadow(0 10px 15px rgba(37,211,102,0.3));
        }

        .whatsapp-header h3 {
            font-size: 2.5rem;
            font-weight: 700;
            color: #0f172a;
        }

        .whatsapp-header h3 span {
            color: #25D366;
            position: relative;
        }

        .whatsapp-header h3 span::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 3px;
            background: #25D366;
            transform: scaleX(0);
            transform-origin: right;
            animation: slideInLeft 0.5s ease-out 1s forwards;
        }

        .whatsapp-subtitle {
            text-align: center;
            color: #64748b;
            margin-bottom: 3rem;
            font-size: 1.1rem;
            position: relative;
            z-index: 1;
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            margin-bottom: 2rem;
            position: relative;
            z-index: 1;
        }

        .form-group {
            text-align: left;
        }

        .form-group label {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.8rem;
            color: #334155;
            font-weight: 600;
            font-size: 0.95rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 14px 20px;
            border: 2px solid #e2e8f0;
            border-radius: 20px;
            font-size: 1rem;
            transition: all 0.4s;
            background: white;
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #38bdf8;
            box-shadow: 0 0 0 6px rgba(56,189,248,0.1);
            transform: scale(1.02);
        }

        .form-group input:hover,
        .form-group textarea:hover {
            border-color: #94a3b8;
            transform: translateY(-2px);
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        .whatsapp-btn {
            width: 100%;
            padding: 18px 40px;
            background: linear-gradient(135deg, #25D366, #128C7E, #25D366);
            background-size: 200% auto;
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.5s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
            position: relative;
            overflow: hidden;
            z-index: 1;
            animation: border-pulse 3s infinite;
        }

        .whatsapp-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.6s;
            z-index: -1;
        }

        .whatsapp-btn:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 25px 40px -5px rgba(37,211,102,0.4);
            background-position: right center;
        }

        .whatsapp-btn:hover::before {
            left: 100%;
        }

        .availability-info {
            margin-top: 2.5rem;
            padding: 2rem;
            background: rgba(255,255,255,0.5);
            border-radius: 30px;
            border: 1px solid rgba(255,255,255,0.8);
            backdrop-filter: blur(5px);
            position: relative;
            z-index: 1;
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
            background: white;
            border-radius: 40px;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            border: 1px solid #e2e8f0;
            box-shadow: 0 5px 15px rgba(0,0,0,0.02);
            transition: all 0.4s;
            animation: flipIn 0.8s ease-out;
            animation-fill-mode: both;
        }

        .time-badge:nth-child(1) { animation-delay: 0.2s; }
        .time-badge:nth-child(2) { animation-delay: 0.4s; }

        .time-badge:hover {
            transform: scale(1.05) translateY(-3px);
            box-shadow: 0 15px 25px -5px rgba(0,0,0,0.1);
            border-color: #38bdf8;
        }

        .time-badge.morning { border-left: 5px solid #f59e0b; }
        .time-badge.afternoon { border-left: 5px solid #3b82f6; }

        .availability-status {
            display: inline-block;
            padding: 8px 25px;
            border-radius: 40px;
            font-weight: 600;
            font-size: 0.95rem;
            margin-top: 1rem;
            animation: pulse-glow 3s ease-in-out infinite;
        }

        /* Footer */
        footer {
            background: white;
            color: #64748b;
            text-align: center;
            padding: 2.5rem 0;
            border-top: 1px solid #e2e8f0;
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, transparent, #38bdf8, #8b5cf6, transparent);
            animation: shimmer 4s infinite;
        }

        footer p {
            font-size: 1rem;
            animation: float 4s ease-in-out infinite;
        }

        /* Vague décorative */
        .wave {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 100px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23ffffff" fill-opacity="0.1" d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,122.7C672,117,768,139,864,154.7C960,171,1056,181,1152,165.3C1248,149,1344,107,1392,85.3L1440,64L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-repeat: no-repeat;
            background-size: cover;
            pointer-events: none;
            animation: wave 15s linear infinite;
            opacity: 0.3;
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

            .apropos-text h2::before {
                left: 50%;
                transform: translateX(-50%);
            }

            .apropos-text h2::after {
                display: none;
            }

            .apropos-text p:hover {
                transform: translateX(0);
                padding-left: 0;
            }

            .apropos-image {
                order: 1;
            }

            .hero h1 {
                font-size: 2.5rem;
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

            .hero p {
                font-size: 1.2rem;
            }

            .form-grid {
                grid-template-columns: 1fr;
            }

            .whatsapp-container {
                padding: 2rem;
                margin: 0 20px;
            }

            .schedule {
                gap: 1rem;
            }

            .orb-1, .orb-2, .orb-3 {
                opacity: 0.3;
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
    <!-- Orbes lumineux -->
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>
    <div class="orb orb-3"></div>
    
    <!-- Formes flottantes -->
    <div class="floating-shape shape-1"></div>
    <div class="floating-shape shape-2"></div>
    <div class="floating-shape shape-3"></div>
    
    <!-- Icônes décoratives -->
    <div class="floating-icon icon-1">⚡</div>
    <div class="floating-icon icon-2">✨</div>
    <div class="floating-icon icon-3">💫</div>
    <div class="floating-icon icon-4">🌟</div>
    <div class="floating-icon icon-5">○</div>
    <div class="floating-icon icon-6">◈</div>
    
    <!-- Particules -->
    <div class="particle particle-1"></div>
    <div class="particle particle-2"></div>
    <div class="particle particle-3"></div>
    <div class="particle particle-4"></div>
    <div class="particle particle-5"></div>

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
        <div class="wave"></div>
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
                    <span class="skill">UI/UX</span>
                </div>
            </div>
            <div class="apropos-image">
                <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/642754626_122112963513211419_7763551596132436351_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=HrPMD1Mzk-wQ7kNvwF-W0Kk&_nc_oc=AdmitmpVlD_NkLZbjv5bb1BdGCCLKrDWIu8jwSkutlrW38sKkCh-4igqUNpNQk8v2sg&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=UrnADD8nIJ14FGwl_Mt82Q&_nc_ss=8&oh=00_AfxextLBeI-e-uEMJr1xXOL4FM1WFzyiLwUla6pesQhiMA&oe=69AAF757" alt="Photo de profil - RATIANARIVO Mirindra Matthieu">
            </div>
        </div>
        <div class="wave"></div>
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
        <div class="wave"></div>
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
                    <p style="margin-top: 1rem; color: #64748b; font-size: 0.95rem;">
                        <span>📱 +261 38 62 876 80</span> • <span>⚡ Réponse rapide garantie</span>
                    </p>
                </div>
            </div>
        </div>
        <div class="wave"></div>
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
                statusElement.style.border = '2px solid #a5d6a7';
            } else {
                statusElement.innerHTML = '⏰ HORS HORAIRE - Réponse à mon retour';
                statusElement.style.background = '#fff3e0';
                statusElement.style.color = '#b85c00';
                statusElement.style.border = '2px solid #ffb74d';
            }
        }

        // Animation au scroll
        function revealOnScroll() {
            var elements = document.querySelectorAll('.apropos-text, .apropos-image, .contact-card, .whatsapp-container');
            
            elements.forEach(function(element) {
                var windowHeight = window.innerHeight;
                var revealTop = element.getBoundingClientRect().top;
                var revealPoint = 150;
                
                if (revealTop < windowHeight - revealPoint) {
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }
            });
        }

        document.addEventListener('DOMContentLoaded', function() {
            updateAvailability();
            setInterval(updateAvailability, 60000);
            
            // Animation initiale
            revealOnScroll();
        });

        window.addEventListener('scroll', revealOnScroll);

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

        // Animation de particules aléatoires
        function createParticles() {
            for (let i = 0; i < 20; i++) {
                let particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animation = `float ${5 + Math.random() * 10}s ease-in-out infinite`;
                particle.style.animationDelay = Math.random() * 5 + 's';
                document.body.appendChild(particle);
            }
        }
        
        // createParticles(); // Décommentez si vous voulez plus de particules
    </script>
</body>
</html>
