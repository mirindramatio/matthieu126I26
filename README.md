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
            background: linear-gradient(135deg, #0b1120 0%, #1a2639 50%, #0f172a 100%);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 30%, rgba(123, 216, 255, 0.08) 0%, transparent 40%),
                        radial-gradient(circle at 80% 70%, rgba(172, 148, 255, 0.08) 0%, transparent 40%);
            pointer-events: none;
            z-index: -1;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 10;
        }

        /* ===== THÈME MUICHIRO TOKITO - NUAGES ET BRUME ===== */
        @keyframes floatCloud {
            0% { transform: translateX(0) translateY(0); opacity: 0.3; }
            50% { transform: translateX(20px) translateY(-10px); opacity: 0.5; }
            100% { transform: translateX(0) translateY(0); opacity: 0.3; }
        }

        @keyframes floatCloudSlow {
            0% { transform: translateX(0) scale(1); opacity: 0.2; }
            50% { transform: translateX(-30px) scale(1.05); opacity: 0.4; }
            100% { transform: translateX(0) scale(1); opacity: 0.2; }
        }

        @keyframes mistFlow {
            0% { transform: translateX(-10%) translateY(0); opacity: 0.15; }
            50% { transform: translateX(10%) translateY(-5%); opacity: 0.25; }
            100% { transform: translateX(-10%) translateY(0); opacity: 0.15; }
        }

        @keyframes fogPulse {
            0%, 100% { opacity: 0.1; filter: blur(20px); }
            50% { opacity: 0.2; filter: blur(30px); }
        }

        @keyframes floatFeather {
            0% { transform: translateY(0) rotate(0deg); opacity: 0.2; }
            50% { transform: translateY(-15px) rotate(5deg); opacity: 0.4; }
            100% { transform: translateY(0) rotate(0deg); opacity: 0.2; }
        }

        @keyframes floatFeatherReverse {
            0% { transform: translateY(0) rotate(0deg); opacity: 0.2; }
            50% { transform: translateY(15px) rotate(-5deg); opacity: 0.4; }
            100% { transform: translateY(0) rotate(0deg); opacity: 0.2; }
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.1; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.2); }
        }

        @keyframes rotateSlow {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes rotateReverse {
            from { transform: rotate(360deg); }
            to { transform: rotate(0deg); }
        }

        @keyframes waveFlow {
            0% { transform: translateX(0) translateY(0); }
            25% { transform: translateX(-5%) translateY(2%); }
            50% { transform: translateX(-10%) translateY(0); }
            75% { transform: translateX(-5%) translateY(-2%); }
            100% { transform: translateX(0) translateY(0); }
        }

        @keyframes glowPulse {
            0%, 100% { filter: drop-shadow(0 0 5px rgba(123, 216, 255, 0.3)); }
            50% { filter: drop-shadow(0 0 15px rgba(172, 148, 255, 0.5)); }
        }

        /* ===== ÉLÉMENTS DÉCORATIFS MUICHIRO ===== */
        .mist {
            position: fixed;
            pointer-events: none;
            z-index: 0;
            background: linear-gradient(135deg, rgba(123, 216, 255, 0.05), rgba(172, 148, 255, 0.05));
            filter: blur(40px);
            border-radius: 50%;
        }

        .mist-1 {
            top: 10%;
            left: 5%;
            width: 500px;
            height: 500px;
            animation: floatCloud 18s ease-in-out infinite;
        }

        .mist-2 {
            bottom: 10%;
            right: 5%;
            width: 600px;
            height: 600px;
            animation: floatCloudSlow 22s ease-in-out infinite reverse;
        }

        .mist-3 {
            top: 40%;
            right: 20%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(172, 148, 255, 0.08), transparent);
            animation: fogPulse 12s ease-in-out infinite;
        }

        .mist-4 {
            bottom: 30%;
            left: 15%;
            width: 350px;
            height: 350px;
            background: radial-gradient(circle, rgba(123, 216, 255, 0.06), transparent);
            animation: mistFlow 20s linear infinite;
        }

        /* Nuages */
        .cloud {
            position: fixed;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 1000px;
            filter: blur(15px);
            pointer-events: none;
            z-index: 0;
        }

        .cloud-1 {
            top: 15%;
            right: 10%;
            width: 300px;
            height: 100px;
            box-shadow: 40px 20px 0 0 rgba(255,255,255,0.02),
                       80px 0 0 0 rgba(255,255,255,0.02),
                       120px -10px 0 0 rgba(255,255,255,0.02);
            animation: floatCloud 25s ease-in-out infinite;
        }

        .cloud-2 {
            bottom: 20%;
            left: 5%;
            width: 400px;
            height: 120px;
            box-shadow: 50px 30px 0 0 rgba(255,255,255,0.02),
                       100px 10px 0 0 rgba(255,255,255,0.02),
                       150px -20px 0 0 rgba(255,255,255,0.02);
            animation: floatCloudSlow 30s ease-in-out infinite reverse;
        }

        .cloud-3 {
            top: 60%;
            right: 15%;
            width: 250px;
            height: 80px;
            box-shadow: 30px 15px 0 0 rgba(255,255,255,0.02),
                       60px -5px 0 0 rgba(255,255,255,0.02);
            animation: mistFlow 28s linear infinite;
        }

        /* Plumes de Muichiro */
        .feather {
            position: fixed;
            color: rgba(172, 148, 255, 0.2);
            font-size: 1.5rem;
            pointer-events: none;
            z-index: 0;
            filter: drop-shadow(0 0 5px rgba(123, 216, 255, 0.2));
            animation: glowPulse 4s ease-in-out infinite;
        }

        .feather-1 {
            top: 20%;
            left: 8%;
            transform: rotate(-15deg);
            animation: floatFeather 12s ease-in-out infinite;
        }

        .feather-2 {
            top: 70%;
            right: 12%;
            transform: rotate(25deg);
            animation: floatFeatherReverse 14s ease-in-out infinite;
        }

        .feather-3 {
            top: 40%;
            left: 20%;
            transform: rotate(45deg);
            animation: floatFeather 16s ease-in-out infinite reverse;
        }

        .feather-4 {
            bottom: 25%;
            right: 25%;
            transform: rotate(-30deg);
            animation: floatFeatherReverse 18s ease-in-out infinite;
        }

        .feather-5 {
            top: 80%;
            left: 30%;
            transform: rotate(10deg);
            animation: floatFeather 20s ease-in-out infinite;
        }

        /* Étoiles/Éclats de brume */
        .mist-particle {
            position: fixed;
            width: 4px;
            height: 4px;
            background: rgba(172, 148, 255, 0.3);
            border-radius: 50%;
            filter: blur(2px);
            pointer-events: none;
            z-index: 0;
            animation: twinkle 5s ease-in-out infinite;
        }

        .particle-1 { top: 15%; left: 15%; animation-delay: 0s; }
        .particle-2 { top: 25%; left: 45%; animation-delay: 1s; }
        .particle-3 { top: 35%; left: 75%; animation-delay: 2s; }
        .particle-4 { top: 45%; left: 25%; animation-delay: 3s; }
        .particle-5 { top: 55%; left: 55%; animation-delay: 4s; }
        .particle-6 { top: 65%; left: 85%; animation-delay: 5s; }
        .particle-7 { top: 75%; left: 35%; animation-delay: 6s; }
        .particle-8 { top: 85%; left: 65%; animation-delay: 7s; }

        /* Symboles de brume */
        .mist-symbol {
            position: fixed;
            font-size: 3rem;
            opacity: 0.1;
            pointer-events: none;
            z-index: 0;
            filter: blur(5px);
        }

        .symbol-1 {
            top: 10%;
            right: 20%;
            transform: rotate(20deg);
            animation: rotateSlow 40s linear infinite;
        }

        .symbol-2 {
            bottom: 15%;
            left: 15%;
            transform: rotate(-15deg);
            animation: rotateReverse 45s linear infinite;
        }

        .symbol-3 {
            top: 50%;
            right: 30%;
            animation: floatFeather 30s ease-in-out infinite;
        }

        /* ===== HEADER ===== */
        header {
            background: rgba(10, 15, 25, 0.7);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border-bottom: 1px solid rgba(123, 216, 255, 0.15);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            animation: slideDown 1s ease-out;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
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
            font-weight: 600;
            color: #e0f2fe;
            text-decoration: none;
            letter-spacing: -0.5px;
            text-shadow: 0 0 10px rgba(123, 216, 255, 0.5);
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
            background: linear-gradient(90deg, #7bd8ff, #ac94ff);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.3s;
        }

        .logo:hover {
            text-shadow: 0 0 20px rgba(172, 148, 255, 0.8);
            transform: translateY(-2px);
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
            font-weight: 500;
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
            background: linear-gradient(90deg, #7bd8ff, #ac94ff);
            transform: scaleX(0);
            transition: transform 0.3s;
        }

        .nav-links a:hover {
            color: #e0f2fe;
            text-shadow: 0 0 10px rgba(123, 216, 255, 0.5);
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

        section::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, transparent, #7bd8ff, #ac94ff, transparent);
            opacity: 0.2;
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
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            color: #e0f2fe;
            line-height: 1.2;
            text-shadow: 0 0 20px rgba(123, 216, 255, 0.5);
            animation: glowPulse 4s ease-in-out infinite;
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
            background: linear-gradient(135deg, rgba(123, 216, 255, 0.2), rgba(172, 148, 255, 0.2));
            color: #e0f2fe;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            letter-spacing: 0.5px;
            transition: all 0.4s;
            border: 1px solid rgba(123, 216, 255, 0.3);
            backdrop-filter: blur(5px);
            box-shadow: 0 10px 30px -5px rgba(0,0,0,0.3);
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
            background: linear-gradient(90deg, transparent, rgba(123, 216, 255, 0.3), transparent);
            transition: left 0.5s;
        }

        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px -5px rgba(123, 216, 255, 0.3);
            border-color: #ac94ff;
            background: linear-gradient(135deg, rgba(123, 216, 255, 0.3), rgba(172, 148, 255, 0.3));
        }

        .btn:hover::before {
            left: 100%;
        }

        /* À propos - Photo à droite, texte à gauche */
        #apropos {
            background: linear-gradient(135deg, 
                rgba(10, 15, 25, 0.8) 0%, 
                rgba(20, 25, 40, 0.8) 100%);
            backdrop-filter: blur(5px);
        }

        .apropos-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: center;
        }

        .apropos-text {
            animation: slideInLeft 1s ease-out;
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .apropos-text h2 {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 2rem;
            color: #e0f2fe;
            position: relative;
            display: inline-block;
            text-shadow: 0 0 15px rgba(123, 216, 255, 0.3);
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, #7bd8ff, #ac94ff);
            border-radius: 2px;
            box-shadow: 0 0 10px #7bd8ff;
        }

        .apropos-text p {
            color: #b0c4de;
            margin-bottom: 1.2rem;
            font-size: 1.1rem;
            line-height: 1.8;
            transition: all 0.4s;
            padding-left: 0;
            border-left: 2px solid transparent;
        }

        .apropos-text p:hover {
            transform: translateX(10px);
            color: #e0f2fe;
            border-left-color: #7bd8ff;
            padding-left: 15px;
            text-shadow: 0 0 10px rgba(123, 216, 255, 0.3);
        }

        .apropos-text p:last-of-type {
            font-style: italic;
            color: #ac94ff;
            margin-top: 2rem;
            padding: 1.5rem;
            background: rgba(123, 216, 255, 0.05);
            border-radius: 20px;
            border-left: 4px solid #ac94ff;
            box-shadow: 0 10px 30px -10px rgba(0,0,0,0.3);
            font-size: 1.2rem;
            backdrop-filter: blur(5px);
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2.5rem;
        }

        .skill {
            padding: 10px 28px;
            background: rgba(123, 216, 255, 0.1);
            border: 1px solid rgba(123, 216, 255, 0.2);
            border-radius: 30px;
            color: #b0c4de;
            font-weight: 600;
            font-size: 0.95rem;
            transition: all 0.4s;
            backdrop-filter: blur(5px);
            cursor: default;
            position: relative;
            overflow: hidden;
            animation: fadeInUp 0.8s ease-out;
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
            background: linear-gradient(90deg, transparent, rgba(123, 216, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .skill:hover {
            border-color: #ac94ff;
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 20px -5px rgba(172, 148, 255, 0.3);
            background: rgba(172, 148, 255, 0.15);
            color: #e0f2fe;
        }

        .skill:hover::before {
            left: 100%;
        }

        .apropos-image {
            position: relative;
            display: flex;
            justify-content: center;
            animation: slideInRight 1s ease-out;
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .apropos-image::before {
            content: '';
            position: absolute;
            top: -20px;
            left: -20px;
            right: -20px;
            bottom: -20px;
            background: radial-gradient(circle, rgba(123, 216, 255, 0.2) 0%, transparent 70%);
            border-radius: 30px;
            animation: fogPulse 5s ease-in-out infinite;
            z-index: 1;
        }

        .apropos-image::after {
            content: '';
            position: absolute;
            top: -15px;
            left: -15px;
            right: -15px;
            bottom: -15px;
            border: 2px dashed rgba(172, 148, 255, 0.3);
            border-radius: 30px;
            animation: rotateSlow 30s linear infinite;
            z-index: 1;
        }

        .apropos-image img {
            width: 100%;
            max-width: 400px;
            height: auto;
            border-radius: 30px;
            box-shadow: 
                0 30px 40px -20px rgba(0,0,0,0.5),
                0 0 0 3px rgba(123, 216, 255, 0.2),
                0 0 0 6px rgba(172, 148, 255, 0.1);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            z-index: 2;
            filter: brightness(1.05) contrast(1.02);
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        .apropos-image img:hover {
            transform: scale(1.05) rotate(2deg);
            box-shadow: 
                0 40px 50px -20px rgba(123, 216, 255, 0.4),
                0 0 0 4px rgba(172, 148, 255, 0.3),
                0 0 0 8px rgba(123, 216, 255, 0.15);
        }

        /* Contact */
        #contact {
            text-align: center;
            background: linear-gradient(135deg, 
                rgba(15, 20, 30, 0.9) 0%, 
                rgba(10, 15, 25, 0.9) 100%);
        }

        #contact h2 {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: #e0f2fe;
            text-shadow: 0 0 15px rgba(123, 216, 255, 0.3);
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
            box-shadow: 0 20px 30px -15px rgba(0,0,0,0.5);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 1px solid rgba(123, 216, 255, 0.15);
            position: relative;
            overflow: hidden;
            animation: fadeInUp 0.8s ease-out;
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
            height: 2px;
            background: linear-gradient(90deg, transparent, #7bd8ff, #ac94ff, transparent);
            transform: translateX(-100%);
            transition: transform 0.6s;
        }

        .contact-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 150px;
            height: 150px;
            background: radial-gradient(circle, rgba(123, 216, 255, 0.1) 0%, transparent 70%);
            border-radius: 50%;
            transform: translate(50%, 50%);
            transition: all 0.5s;
        }

        .contact-card:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: 0 30px 40px -15px rgba(123, 216, 255, 0.2);
            border-color: rgba(172, 148, 255, 0.3);
        }

        .contact-card:hover::before {
            transform: translateX(100%);
        }

        .contact-card:hover::after {
            transform: translate(30%, 30%) scale(1.5);
        }

        .contact-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            animation: floatFeather 4s ease-in-out infinite;
            filter: drop-shadow(0 0 10px rgba(123, 216, 255, 0.3));
        }

        .contact-card h3 {
            font-size: 1.4rem;
            color: #e0f2fe;
            margin-bottom: 0.8rem;
            font-weight: 700;
        }

        .contact-card p {
            color: #b0c4de;
            margin-bottom: 1.5rem;
            font-size: 1rem;
        }

        .contact-link {
            display: inline-block;
            padding: 12px 32px;
            background: rgba(123, 216, 255, 0.1);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.95rem;
            transition: all 0.4s;
            border: 1px solid rgba(123, 216, 255, 0.2);
            backdrop-filter: blur(5px);
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
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            transition: left 0.5s;
        }

        .contact-link:hover {
            background: linear-gradient(135deg, rgba(123, 216, 255, 0.2), rgba(172, 148, 255, 0.2));
            color: #e0f2fe;
            border-color: #ac94ff;
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 10px 20px -5px rgba(172, 148, 255, 0.3);
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
            background: rgba(20, 25, 40, 0.6);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.4s;
            border: 1px solid rgba(123, 216, 255, 0.15);
            backdrop-filter: blur(5px);
            animation: fadeInUp 0.8s ease-out 0.4s both;
        }

        .social-link:hover {
            background: rgba(172, 148, 255, 0.15);
            color: #e0f2fe;
            border-color: #ac94ff;
            transform: translateY(-5px);
            box-shadow: 0 10px 20px -5px rgba(172, 148, 255, 0.2);
        }

        /* Formulaire WhatsApp */
        .whatsapp-section {
            padding: 100px 0;
            position: relative;
            background: linear-gradient(135deg, 
                rgba(10, 15, 25, 0.95) 0%, 
                rgba(15, 20, 30, 0.95) 100%);
        }

        .whatsapp-container {
            max-width: 900px;
            margin: 0 auto;
            background: rgba(20, 25, 40, 0.6);
            backdrop-filter: blur(15px);
            padding: 3.5rem;
            border-radius: 60px;
            box-shadow: 0 40px 60px -20px rgba(0,0,0,0.5);
            border: 1px solid rgba(123, 216, 255, 0.15);
            animation: fadeInUp 1s ease-out;
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
            background: radial-gradient(circle, rgba(37,211,102,0.05) 0%, transparent 70%);
            animation: rotateSlow 40s linear infinite;
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
            animation: floatFeather 3s ease-in-out infinite;
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

        .whatsapp-subtitle {
            text-align: center;
            color: #b0c4de;
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
            color: #b0c4de;
            font-weight: 600;
            font-size: 0.95rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 14px 20px;
            background: rgba(10, 15, 25, 0.6);
            border: 2px solid rgba(123, 216, 255, 0.15);
            border-radius: 20px;
            font-size: 1rem;
            transition: all 0.4s;
            color: #e0f2fe;
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #7bd8ff;
            box-shadow: 0 0 0 4px rgba(123, 216, 255, 0.1);
            background: rgba(20, 25, 40, 0.8);
        }

        .form-group input:hover,
        .form-group textarea:hover {
            border-color: #ac94ff;
        }

        .form-group input::placeholder,
        .form-group textarea::placeholder {
            color: rgba(176, 196, 222, 0.3);
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
            margin-top: 1rem;
            position: relative;
            overflow: hidden;
            z-index: 1;
            backdrop-filter: blur(5px);
        }

        .whatsapp-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            transition: left 0.6s;
            z-index: -1;
        }

        .whatsapp-btn:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 20px 30px -5px rgba(37,211,102,0.2);
            border-color: #25D366;
            background: linear-gradient(135deg, rgba(37,211,102,0.3), rgba(18,140,126,0.3));
        }

        .whatsapp-btn:hover::before {
            left: 100%;
        }

        .availability-info {
            margin-top: 2.5rem;
            padding: 2rem;
            background: rgba(10, 15, 25, 0.4);
            border-radius: 30px;
            border: 1px solid rgba(123, 216, 255, 0.15);
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
            background: rgba(20, 25, 40, 0.6);
            border-radius: 40px;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            border: 1px solid rgba(123, 216, 255, 0.2);
            color: #b0c4de;
            backdrop-filter: blur(5px);
            transition: all 0.4s;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
        }

        .time-badge:nth-child(1) { animation-delay: 0.2s; }
        .time-badge:nth-child(2) { animation-delay: 0.4s; }

        .time-badge:hover {
            transform: scale(1.05) translateY(-3px);
            border-color: #ac94ff;
            color: #e0f2fe;
            box-shadow: 0 10px 20px -5px rgba(172, 148, 255, 0.2);
        }

        .time-badge.morning { border-left: 4px solid #7bd8ff; }
        .time-badge.afternoon { border-left: 4px solid #ac94ff; }

        .availability-status {
            display: inline-block;
            padding: 8px 25px;
            background: rgba(37,211,102,0.1);
            border-radius: 40px;
            color: #25D366;
            font-weight: 600;
            font-size: 0.95rem;
            margin-top: 1rem;
            border: 1px solid rgba(37,211,102,0.2);
            animation: glowPulse 3s ease-in-out infinite;
        }

        /* Footer */
        footer {
            background: rgba(5, 10, 15, 0.8);
            color: #b0c4de;
            text-align: center;
            padding: 2.5rem 0;
            border-top: 1px solid rgba(123, 216, 255, 0.1);
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
            background: linear-gradient(90deg, transparent, #7bd8ff, #ac94ff, transparent);
            animation: waveFlow 8s linear infinite;
        }

        footer p {
            font-size: 1rem;
            animation: floatFeather 6s ease-in-out infinite;
        }

        /* Vague décorative */
        .wave {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 100px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%237bd8ff" fill-opacity="0.05" d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,122.7C672,117,768,139,864,154.7C960,171,1056,181,1152,165.3C1248,149,1344,107,1392,85.3L1440,64L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-repeat: no-repeat;
            background-size: cover;
            pointer-events: none;
            animation: waveFlow 15s linear infinite;
            opacity: 0.3;
            z-index: 0;
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
    <!-- Brume de fond (style Muichiro) -->
    <div class="mist mist-1"></div>
    <div class="mist mist-2"></div>
    <div class="mist mist-3"></div>
    <div class="mist mist-4"></div>
    
    <!-- Nuages -->
    <div class="cloud cloud-1"></div>
    <div class="cloud cloud-2"></div>
    <div class="cloud cloud-3"></div>
    
    <!-- Plumes de Muichiro -->
    <div class="feather feather-1">🕊️</div>
    <div class="feather feather-2">🪶</div>
    <div class="feather feather-3">✨</div>
    <div class="feather feather-4">💨</div>
    <div class="feather feather-5">🌪️</div>
    
    <!-- Particules de brume -->
    <div class="mist-particle particle-1"></div>
    <div class="mist-particle particle-2"></div>
    <div class="mist-particle particle-3"></div>
    <div class="mist-particle particle-4"></div>
    <div class="mist-particle particle-5"></div>
    <div class="mist-particle particle-6"></div>
    <div class="mist-particle particle-7"></div>
    <div class="mist-particle particle-8"></div>
    
    <!-- Symboles de brume -->
    <div class="mist-symbol symbol-1">🌫️</div>
    <div class="mist-symbol symbol-2">☁️</div>
    <div class="mist-symbol symbol-3">💭</div>

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
                    <p style="margin-top: 1rem; color: #b0c4de; font-size: 0.95rem;">
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
    </script>
</body>
</html>
