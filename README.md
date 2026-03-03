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
            background: linear-gradient(135deg, #030712 0%, #0a0f1a 50%, #0f1a2f 100%);
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

        /* ===== THÈME MUICHIRO TOKITO - AURA ÉLÉGANTE ===== */
        @keyframes aura-pulse {
            0%, 100% { opacity: 0.15; filter: blur(30px); transform: scale(1); }
            50% { opacity: 0.3; filter: blur(45px); transform: scale(1.1); }
        }

        @keyframes aura-flow {
            0% { transform: translateX(0) translateY(0); opacity: 0.1; }
            33% { transform: translateX(20px) translateY(-10px); opacity: 0.2; }
            66% { transform: translateX(-15px) translateY(15px); opacity: 0.15; }
            100% { transform: translateX(0) translateY(0); opacity: 0.1; }
        }

        @keyframes aura-float {
            0%, 100% { transform: translateY(0) scale(1); opacity: 0.1; }
            50% { transform: translateY(-20px) scale(1.05); opacity: 0.2; }
        }

        @keyframes aura-glow {
            0%, 100% { filter: drop-shadow(0 0 5px rgba(123, 216, 255, 0.2)); }
            50% { filter: drop-shadow(0 0 25px rgba(172, 148, 255, 0.4)); }
        }

        @keyframes aura-spiral {
            0% { transform: rotate(0deg) scale(1); opacity: 0.1; }
            50% { transform: rotate(180deg) scale(1.1); opacity: 0.2; }
            100% { transform: rotate(360deg) scale(1); opacity: 0.1; }
        }

        @keyframes feather-dance {
            0% { transform: translateY(0) rotate(0deg) scale(1); }
            25% { transform: translateY(-20px) rotate(5deg) scale(1.05); }
            50% { transform: translateY(5px) rotate(-5deg) scale(0.95); }
            75% { transform: translateY(-10px) rotate(3deg) scale(1.02); }
            100% { transform: translateY(0) rotate(0deg) scale(1); }
        }

        @keyframes mist-weave {
            0% { transform: translateX(0) translateY(0) scale(1); }
            25% { transform: translateX(30px) translateY(-15px) scale(1.1); }
            50% { transform: translateX(-20px) translateY(20px) scale(0.95); }
            75% { transform: translateX(15px) translateY(-10px) scale(1.05); }
            100% { transform: translateX(0) translateY(0) scale(1); }
        }

        @keyframes particle-dance {
            0% { transform: translate(0, 0) scale(1); opacity: 0.2; }
            20% { transform: translate(15px, -10px) scale(1.2); opacity: 0.4; }
            40% { transform: translate(-10px, 15px) scale(0.9); opacity: 0.3; }
            60% { transform: translate(20px, 5px) scale(1.1); opacity: 0.4; }
            80% { transform: translate(-15px, -10px) scale(1.2); opacity: 0.3; }
            100% { transform: translate(0, 0) scale(1); opacity: 0.2; }
        }

        @keyframes light-ray {
            0% { transform: rotate(0deg) scale(1); opacity: 0; }
            25% { transform: rotate(90deg) scale(1.2); opacity: 0.1; }
            50% { transform: rotate(180deg) scale(1.5); opacity: 0.2; }
            75% { transform: rotate(270deg) scale(1.2); opacity: 0.1; }
            100% { transform: rotate(360deg) scale(1); opacity: 0; }
        }

        /* ===== ÉLÉMENTS D'AURA ===== */
        .aura {
            position: fixed;
            pointer-events: none;
            z-index: 0;
            border-radius: 50%;
            filter: blur(50px);
        }

        .aura-1 {
            top: 10%;
            left: 5%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(123, 216, 255, 0.1) 0%, transparent 70%);
            animation: aura-pulse 12s ease-in-out infinite;
        }

        .aura-2 {
            bottom: 10%;
            right: 5%;
            width: 700px;
            height: 700px;
            background: radial-gradient(circle, rgba(172, 148, 255, 0.08) 0%, transparent 70%);
            animation: aura-pulse 15s ease-in-out infinite reverse;
        }

        .aura-3 {
            top: 40%;
            right: 15%;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(123, 216, 255, 0.05) 0%, transparent 70%);
            animation: aura-flow 20s ease-in-out infinite;
        }

        .aura-4 {
            bottom: 30%;
            left: 10%;
            width: 550px;
            height: 550px;
            background: radial-gradient(circle, rgba(172, 148, 255, 0.06) 0%, transparent 70%);
            animation: aura-float 18s ease-in-out infinite;
        }

        .aura-5 {
            top: 60%;
            left: 20%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.03) 0%, transparent 70%);
            animation: aura-spiral 25s linear infinite;
        }

        .aura-line {
            position: fixed;
            width: 2px;
            height: 100%;
            background: linear-gradient(180deg, transparent, rgba(123,216,255,0.1), rgba(172,148,255,0.1), transparent);
            filter: blur(5px);
            pointer-events: none;
            z-index: 0;
        }

        .aura-line-1 { left: 20%; animation: aura-float 14s ease-in-out infinite; }
        .aura-line-2 { right: 30%; animation: aura-float 18s ease-in-out infinite reverse; }
        .aura-line-3 { left: 60%; animation: aura-float 22s ease-in-out infinite; }

        /* Nuages d'aura */
        .aura-cloud {
            position: fixed;
            background: rgba(255,255,255,0.02);
            border-radius: 1000px;
            filter: blur(40px);
            pointer-events: none;
            z-index: 0;
            animation: aura-flow 25s ease-in-out infinite;
        }

        .aura-cloud-1 {
            top: 15%;
            right: 10%;
            width: 500px;
            height: 150px;
            box-shadow: 60px 30px 0 0 rgba(123,216,255,0.02);
        }

        .aura-cloud-2 {
            bottom: 20%;
            left: 5%;
            width: 600px;
            height: 180px;
            box-shadow: 80px 40px 0 0 rgba(172,148,255,0.02);
        }

        .aura-cloud-3 {
            top: 50%;
            right: 20%;
            width: 400px;
            height: 120px;
            box-shadow: 50px 25px 0 0 rgba(255,255,255,0.02);
            animation-delay: 5s;
        }

        /* Plumes lumineuses */
        .aura-feather {
            position: fixed;
            color: rgba(172, 148, 255, 0.2);
            font-size: 2.2rem;
            pointer-events: none;
            z-index: 0;
            filter: drop-shadow(0 0 15px rgba(123, 216, 255, 0.2));
            animation: feather-dance 20s ease-in-out infinite;
        }

        .aura-feather-1 {
            top: 15%;
            left: 8%;
            transform: rotate(-15deg);
            animation-delay: 0s;
        }

        .aura-feather-2 {
            top: 75%;
            right: 12%;
            transform: rotate(20deg);
            animation-delay: 4s;
        }

        .aura-feather-3 {
            bottom: 30%;
            left: 15%;
            transform: rotate(30deg);
            animation-delay: 8s;
        }

        .aura-feather-4 {
            top: 45%;
            right: 25%;
            transform: rotate(-25deg);
            animation-delay: 12s;
        }

        .aura-feather-5 {
            bottom: 40%;
            right: 35%;
            transform: rotate(10deg);
            animation-delay: 16s;
        }

        /* Particules d'aura */
        .aura-particle {
            position: fixed;
            width: 4px;
            height: 4px;
            background: rgba(172, 148, 255, 0.25);
            border-radius: 50%;
            filter: blur(2px);
            pointer-events: none;
            z-index: 0;
            animation: particle-dance 30s ease-in-out infinite;
        }

        .aura-particle-1 { top: 12%; left: 12%; }
        .aura-particle-2 { top: 22%; left: 42%; animation-delay: 2s; }
        .aura-particle-3 { top: 32%; left: 72%; animation-delay: 4s; }
        .aura-particle-4 { top: 42%; left: 22%; animation-delay: 6s; }
        .aura-particle-5 { top: 52%; left: 52%; animation-delay: 8s; }
        .aura-particle-6 { top: 62%; left: 82%; animation-delay: 10s; }
        .aura-particle-7 { top: 72%; left: 32%; animation-delay: 12s; }
        .aura-particle-8 { top: 82%; left: 62%; animation-delay: 14s; }
        .aura-particle-9 { top: 17%; left: 87%; animation-delay: 16s; }
        .aura-particle-10 { top: 67%; left: 7%; animation-delay: 18s; }

        /* Rayons de lumière */
        .aura-ray {
            position: fixed;
            width: 100%;
            height: 100%;
            background: conic-gradient(
                from 0deg,
                transparent,
                rgba(123,216,255,0.03) 45deg,
                transparent 90deg,
                rgba(172,148,255,0.03) 135deg,
                transparent 180deg,
                rgba(123,216,255,0.03) 225deg,
                transparent 270deg,
                rgba(172,148,255,0.03) 315deg,
                transparent 360deg
            );
            pointer-events: none;
            z-index: 0;
            animation: light-ray 40s linear infinite;
        }

        /* ===== HEADER AVEC AURA ===== */
        header {
            background: rgba(3, 7, 18, 0.5);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(123, 216, 255, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            animation: fadeInDown 1s ease-out;
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
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
            font-weight: 400;
            color: #ffffff;
            text-decoration: none;
            letter-spacing: 2px;
            transition: all 0.3s;
            position: relative;
            text-shadow: 0 0 15px rgba(123,216,255,0.3);
            animation: aura-glow 4s ease-in-out infinite;
        }

        .logo::before {
            content: '';
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            background: radial-gradient(circle, rgba(123,216,255,0.1) 0%, transparent 70%);
            filter: blur(10px);
            animation: aura-pulse 5s ease-in-out infinite;
            z-index: -1;
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, #7bd8ff, #ac94ff, transparent);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.4s;
        }

        .logo:hover {
            transform: translateY(-2px);
            text-shadow: 0 0 25px rgba(172,148,255,0.5);
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
            font-weight: 300;
            font-size: 1rem;
            transition: all 0.3s;
            position: relative;
            letter-spacing: 1px;
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

        .nav-links a::after {
            content: '';
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            background: radial-gradient(circle, rgba(123,216,255,0.1) 0%, transparent 70%);
            filter: blur(8px);
            opacity: 0;
            transition: opacity 0.3s;
            z-index: -1;
        }

        .nav-links a:hover {
            color: #ffffff;
            text-shadow: 0 0 10px rgba(123,216,255,0.3);
        }

        .nav-links a:hover::before {
            transform: scaleX(1);
        }

        .nav-links a:hover::after {
            opacity: 1;
        }

        /* ===== SECTION ACCUEIL AVEC AURA ===== */
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
            animation: fadeInUp 1.5s ease-out;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(40px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 300;
            margin-bottom: 1.5rem;
            color: #ffffff;
            line-height: 1.2;
            text-shadow: 0 0 30px rgba(123,216,255,0.3);
            animation: aura-glow 5s ease-in-out infinite;
            letter-spacing: 2px;
        }

        .hero p {
            font-size: 1.3rem;
            color: #b0c4de;
            margin-bottom: 2.5rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            font-weight: 300;
            letter-spacing: 1px;
            line-height: 1.8;
            animation: fadeInUp 1.5s ease-out 0.3s both;
        }

        .btn {
            display: inline-block;
            padding: 15px 45px;
            background: rgba(123,216,255,0.03);
            color: #ffffff;
            text-decoration: none;
            border-radius: 40px;
            font-weight: 300;
            letter-spacing: 2px;
            transition: all 0.4s;
            border: 1px solid rgba(123,216,255,0.2);
            backdrop-filter: blur(8px);
            font-size: 0.95rem;
            position: relative;
            overflow: hidden;
            animation: aura-glow 4s ease-in-out infinite;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(123,216,255,0.1) 0%, transparent 70%);
            animation: aura-spiral 15s linear infinite;
            opacity: 0;
            transition: opacity 0.4s;
        }

        .btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            transition: left 0.6s;
        }

        .btn:hover {
            background: rgba(172,148,255,0.05);
            border-color: rgba(172,148,255,0.3);
            transform: translateY(-5px);
            box-shadow: 0 20px 30px -10px rgba(0,0,0,0.5);
        }

        .btn:hover::before {
            opacity: 1;
        }

        .btn:hover::after {
            left: 100%;
        }

        /* ===== SECTION À PROPOS - BLEU CIEL AVEC AURA ===== */
        #apropos {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            background: linear-gradient(135deg, 
                #e0f2fe 0%,
                #bae6fd 20%,
                #7dd3fc 40%,
                #38bdf8 60%,
                #0ea5e9 80%,
                #0284c7 100%);
            background-size: 300% 300%;
            animation: gradientFlow 20s ease infinite;
        }

        @keyframes gradientFlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
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
            animation: slideInLeft 1.2s ease-out;
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(15px);
            padding: 3rem;
            border-radius: 40px;
            border: 1px solid rgba(255,255,255,0.3);
            box-shadow: 0 30px 50px -20px rgba(0,0,0,0.2);
            position: relative;
            overflow: hidden;
        }

        .apropos-text::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: aura-spiral 30s linear infinite;
            pointer-events: none;
        }

        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .apropos-text h2 {
            font-size: 2.8rem;
            font-weight: 300;
            margin-bottom: 2rem;
            color: #0f172a;
            position: relative;
            display: inline-block;
            letter-spacing: 2px;
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 120px;
            height: 2px;
            background: linear-gradient(90deg, #0f172a, transparent);
        }

        .apropos-text p {
            color: #0f172a;
            margin-bottom: 1.2rem;
            font-size: 1.1rem;
            line-height: 1.9;
            font-weight: 400;
            transition: all 0.4s;
            position: relative;
            z-index: 2;
        }

        .apropos-text p:hover {
            transform: translateX(10px);
            color: #000000;
        }

        .apropos-text p:last-of-type {
            font-style: italic;
            color: #0f172a;
            margin-top: 2rem;
            padding: 1.5rem;
            background: rgba(255,255,255,0.25);
            border-radius: 20px;
            border-left: 4px solid #0f172a;
            font-size: 1.15rem;
            font-weight: 400;
            backdrop-filter: blur(5px);
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2.5rem;
        }

        .skill {
            padding: 10px 25px;
            background: rgba(255,255,255,0.2);
            border: 1px solid rgba(255,255,255,0.4);
            border-radius: 30px;
            color: #0f172a;
            font-weight: 400;
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

        .skill::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.2) 0%, transparent 70%);
            animation: aura-spiral 20s linear infinite;
            opacity: 0;
            transition: opacity 0.4s;
        }

        .skill:hover {
            transform: translateY(-5px);
            background: rgba(255,255,255,0.3);
            border-color: rgba(255,255,255,0.6);
            box-shadow: 0 15px 25px -10px rgba(0,0,0,0.2);
        }

        .skill:hover::before {
            opacity: 1;
        }

        .apropos-image {
            position: relative;
            display: flex;
            justify-content: center;
            animation: slideInRight 1.2s ease-out;
        }

        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .image-frame {
            position: relative;
            width: 100%;
            max-width: 450px;
            aspect-ratio: 1/1;
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            padding: 8px;
            background: rgba(255,255,255,0.25);
            backdrop-filter: blur(8px);
            box-shadow: 0 30px 50px -20px rgba(0,0,0,0.3);
            animation: aura-float 8s ease-in-out infinite;
            z-index: 2;
        }

        /* Cercles d'aura autour de la photo */
        .aura-circle {
            position: absolute;
            border: 1px solid rgba(255,255,255,0.2);
            border-radius: inherit;
            animation: aura-spiral 20s linear infinite;
        }

        .aura-circle-1 {
            top: -15px;
            left: -15px;
            right: -15px;
            bottom: -15px;
            border-width: 1px;
            border-style: dashed;
        }

        .aura-circle-2 {
            top: -25px;
            left: -25px;
            right: -25px;
            bottom: -25px;
            border-width: 1px;
            border-style: dotted;
            animation-direction: reverse;
            animation-duration: 25s;
        }

        .aura-circle-3 {
            top: -35px;
            left: -35px;
            right: -35px;
            bottom: -35px;
            border-width: 1px;
            border-style: solid;
            opacity: 0.1;
            animation-duration: 30s;
        }

        .aura-circle-4 {
            top: -45px;
            left: -45px;
            right: -45px;
            bottom: -45px;
            border-width: 2px;
            border-style: double;
            opacity: 0.05;
            animation-duration: 35s;
            animation-direction: reverse;
        }

        /* Rayons de lumière derrière la photo */
        .photo-rays {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 200%;
            height: 200%;
            background: conic-gradient(
                from 0deg,
                transparent,
                rgba(255,255,255,0.1) 30deg,
                transparent 60deg,
                rgba(123,216,255,0.1) 90deg,
                transparent 120deg,
                rgba(172,148,255,0.1) 150deg,
                transparent 180deg,
                rgba(255,255,255,0.1) 210deg,
                transparent 240deg,
                rgba(123,216,255,0.1) 270deg,
                transparent 300deg,
                rgba(172,148,255,0.1) 330deg,
                transparent 360deg
            );
            animation: light-ray 30s linear infinite;
            border-radius: 50%;
            z-index: 1;
            opacity: 0.5;
        }

        .apropos-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: inherit;
            transition: all 0.5s;
            display: block;
            filter: brightness(1.05) contrast(1.02);
            opacity: 0.95;
            position: relative;
            z-index: 3;
            animation: aura-glow 5s ease-in-out infinite;
        }

        .apropos-image img:hover {
            transform: scale(1.03);
            opacity: 1;
            filter: brightness(1.1);
        }

        /* Badges avec aura */
        .badge {
            position: absolute;
            background: rgba(255,255,255,0.15);
            backdrop-filter: blur(10px);
            padding: 8px 22px;
            border-radius: 30px;
            color: #0f172a;
            font-weight: 400;
            font-size: 0.9rem;
            border: 1px solid rgba(255,255,255,0.3);
            letter-spacing: 1px;
            animation: aura-float 7s ease-in-out infinite;
            z-index: 5;
            box-shadow: 0 10px 20px -5px rgba(0,0,0,0.1);
        }

        .badge-1 {
            top: 5%;
            right: -5px;
            animation-delay: 0s;
        }

        .badge-2 {
            bottom: 10%;
            left: -5px;
            animation-delay: 3s;
        }

        .badge-3 {
            top: 40%;
            left: -15px;
            animation-delay: 6s;
        }

        .badge:hover {
            background: rgba(255,255,255,0.25);
            transform: scale(1.05);
        }

        /* ===== SECTION CONTACT AVEC AURA ===== */
        #contact {
            min-height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            position: relative;
            background: linear-gradient(135deg, 
                rgba(3,7,18,0.95) 0%, 
                rgba(10,15,25,0.95) 50%,
                rgba(15,20,30,0.95) 100%);
        }

        #contact h2 {
            font-size: 2.8rem;
            font-weight: 300;
            margin-bottom: 1rem;
            color: #ffffff;
            letter-spacing: 2px;
            text-shadow: 0 0 20px rgba(123,216,255,0.3);
            animation: aura-glow 5s ease-in-out infinite;
        }

        .contact-subtitle {
            color: #b0c4de;
            font-size: 1.2rem;
            margin-bottom: 3rem;
            font-weight: 300;
            letter-spacing: 1px;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .contact-card {
            background: rgba(20,25,40,0.3);
            backdrop-filter: blur(15px);
            padding: 2.8rem 2rem;
            border-radius: 30px;
            border: 1px solid rgba(123,216,255,0.1);
            transition: all 0.5s;
            animation: fadeInUp 1s ease-out;
            animation-fill-mode: both;
            position: relative;
            overflow: hidden;
        }

        .contact-card:nth-child(1) { animation-delay: 0.1s; }
        .contact-card:nth-child(2) { animation-delay: 0.2s; }
        .contact-card:nth-child(3) { animation-delay: 0.3s; }

        .contact-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(123,216,255,0.05) 0%, transparent 70%);
            animation: aura-spiral 25s linear infinite;
            opacity: 0;
            transition: opacity 0.5s;
        }

        .contact-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 1px;
            background: linear-gradient(90deg, transparent, #7bd8ff, #ac94ff, transparent);
            transform: translateX(-100%);
            transition: transform 0.6s;
        }

        .contact-card:hover {
            transform: translateY(-10px);
            border-color: rgba(172,148,255,0.2);
            background: rgba(25,30,45,0.4);
            box-shadow: 0 30px 40px -15px rgba(0,0,0,0.5);
        }

        .contact-card:hover::before {
            opacity: 1;
        }

        .contact-card:hover::after {
            transform: translateX(100%);
        }

        .contact-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            opacity: 0.9;
            filter: drop-shadow(0 0 15px rgba(123,216,255,0.2));
            animation: aura-float 6s ease-in-out infinite;
        }

        .contact-card h3 {
            font-size: 1.4rem;
            color: #ffffff;
            margin-bottom: 1rem;
            font-weight: 300;
            letter-spacing: 1px;
        }

        .contact-card p {
            color: #b0c4de;
            margin-bottom: 1.8rem;
            font-size: 1rem;
            font-weight: 300;
        }

        .contact-link {
            display: inline-block;
            padding: 12px 32px;
            background: rgba(123,216,255,0.05);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 300;
            font-size: 0.95rem;
            border: 1px solid rgba(123,216,255,0.15);
            transition: all 0.4s;
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
            background: rgba(172,148,255,0.1);
            color: #ffffff;
            border-color: rgba(172,148,255,0.3);
            transform: translateY(-3px);
        }

        .contact-link:hover::before {
            left: 100%;
        }

        .social-links {
            display: flex;
            gap: 2rem;
            justify-content: center;
            margin-top: 4rem;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            gap: 1rem;
            padding: 12px 35px;
            background: rgba(20,25,40,0.3);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 30px;
            border: 1px solid rgba(123,216,255,0.1);
            transition: all 0.4s;
            font-weight: 300;
            letter-spacing: 1px;
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(172,148,255,0.1) 0%, transparent
