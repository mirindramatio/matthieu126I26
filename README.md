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

        /* ===== ANIMATIONS ULTRA DYNAMIQUES ===== */
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0); }
            33% { transform: translateY(-25px) rotate(3deg); }
            66% { transform: translateY(15px) rotate(-2deg); }
        }

        @keyframes float-slow {
            0%, 100% { transform: translateY(0) scale(1); }
            25% { transform: translateY(-20px) scale(1.03); }
            50% { transform: translateY(10px) scale(0.98); }
            75% { transform: translateY(-10px) scale(1.02); }
        }

        @keyframes float-extreme {
            0% { transform: translate(0, 0) rotate(0deg); }
            20% { transform: translate(20px, -20px) rotate(5deg); }
            40% { transform: translate(-15px, 15px) rotate(-5deg); }
            60% { transform: translate(10px, -10px) rotate(3deg); }
            80% { transform: translate(-20px, 20px) rotate(-3deg); }
            100% { transform: translate(0, 0) rotate(0deg); }
        }

        @keyframes pulse-glow {
            0%, 100% { opacity: 0.2; filter: blur(40px); transform: scale(1); }
            25% { opacity: 0.4; filter: blur(60px); transform: scale(1.3); }
            50% { opacity: 0.6; filter: blur(50px); transform: scale(1.5); }
            75% { opacity: 0.3; filter: blur(45px); transform: scale(1.2); }
        }

        @keyframes pulse-color {
            0% { filter: hue-rotate(0deg) brightness(1); }
            25% { filter: hue-rotate(90deg) brightness(1.2); }
            50% { filter: hue-rotate(180deg) brightness(1.1); }
            75% { filter: hue-rotate(270deg) brightness(1.3); }
            100% { filter: hue-rotate(360deg) brightness(1); }
        }

        @keyframes rotate-slow {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes rotate-medium {
            from { transform: rotate(0deg) scale(1); }
            to { transform: rotate(720deg) scale(1.1); }
        }

        @keyframes rotate-fast {
            from { transform: rotate(0deg); }
            to { transform: rotate(1440deg); }
        }

        @keyframes rotate-reverse {
            from { transform: rotate(360deg); }
            to { transform: rotate(0deg); }
        }

        @keyframes scale-pulse {
            0%, 100% { transform: scale(1); }
            25% { transform: scale(1.1); }
            50% { transform: scale(0.9); }
            75% { transform: scale(1.05); }
        }

        @keyframes skew-pulse {
            0%, 100% { transform: skew(0deg); }
            25% { transform: skew(5deg); }
            50% { transform: skew(-5deg); }
            75% { transform: skew(3deg); }
        }

        @keyframes shimmer {
            0% { background-position: -200% 0; }
            100% { background-position: 200% 0; }
        }

        @keyframes borderPulse {
            0%, 100% { border-color: rgba(56, 189, 248, 0.3); box-shadow: 0 0 20px rgba(56, 189, 248, 0.2); }
            25% { border-color: rgba(139, 92, 246, 0.6); box-shadow: 0 0 40px rgba(139, 92, 246, 0.4); }
            50% { border-color: rgba(236, 72, 153, 0.6); box-shadow: 0 0 60px rgba(236, 72, 153, 0.4); }
            75% { border-color: rgba(34, 197, 94, 0.6); box-shadow: 0 0 40px rgba(34, 197, 94, 0.4); }
        }

        @keyframes lightRays {
            0% { transform: rotate(0deg) scale(1); opacity: 0.1; }
            25% { transform: rotate(180deg) scale(1.5); opacity: 0.3; }
            50% { transform: rotate(360deg) scale(2); opacity: 0.2; }
            75% { transform: rotate(540deg) scale(1.5); opacity: 0.3; }
            100% { transform: rotate(720deg) scale(1); opacity: 0.1; }
        }

        @keyframes sparkle {
            0%, 100% { opacity: 0; transform: scale(0) rotate(0deg); }
            25% { opacity: 0.5; transform: scale(1) rotate(90deg); }
            50% { opacity: 1; transform: scale(1.5) rotate(180deg); }
            75% { opacity: 0.5; transform: scale(1) rotate(270deg); }
        }

        @keyframes wave {
            0% { transform: translateX(0) translateY(0); }
            25% { transform: translateX(-15%) translateY(5px); }
            50% { transform: translateX(-30%) translateY(-5px); }
            75% { transform: translateX(-15%) translateY(5px); }
            100% { transform: translateX(0) translateY(0); }
        }

        @keyframes glitch {
            0%, 100% { transform: translate(0); }
            20% { transform: translate(-5px, 3px); }
            40% { transform: translate(5px, -3px); }
            60% { transform: translate(-3px, 2px); }
            80% { transform: translate(3px, -2px); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            25% { transform: translateY(-30px); }
            50% { transform: translateY(15px); }
            75% { transform: translateY(-15px); }
        }

        @keyframes spin3d {
            0% { transform: perspective(500px) rotateY(0deg); }
            50% { transform: perspective(500px) rotateY(180deg); }
            100% { transform: perspective(500px) rotateY(360deg); }
        }

        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-100px) rotate(-10deg); }
            to { opacity: 1; transform: translateX(0) rotate(0); }
        }

        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(100px) rotate(10deg); }
            to { opacity: 1; transform: translateX(0) rotate(0); }
        }

        @keyframes zoomIn {
            from { opacity: 0; transform: scale(0.5) rotate(-20deg); }
            to { opacity: 1; transform: scale(1) rotate(0); }
        }

        @keyframes flipIn {
            from { opacity: 0; transform: perspective(400px) rotateY(180deg) scale(0.5); }
            to { opacity: 1; transform: perspective(400px) rotateY(0) scale(1); }
        }

        @keyframes dropIn {
            from { opacity: 0; transform: translateY(-200px) rotate(180deg); }
            to { opacity: 1; transform: translateY(0) rotate(0); }
        }

        /* ===== ÉLÉMENTS DÉCORATIFS DYNAMIQUES ===== */
        .orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(50px);
            pointer-events: none;
            z-index: 0;
            animation: pulse-glow 12s ease-in-out infinite;
        }

        .orb-1 {
            top: 5%;
            left: 5%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(56,189,248,0.2) 0%, transparent 70%);
            animation-delay: 0s;
        }

        .orb-2 {
            bottom: 5%;
            right: 5%;
            width: 700px;
            height: 700px;
            background: radial-gradient(circle, rgba(139,92,246,0.18) 0%, transparent 70%);
            animation-delay: 2s;
        }

        .orb-3 {
            top: 40%;
            right: 15%;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(236,72,153,0.15) 0%, transparent 70%);
            animation-delay: 4s;
        }

        .orb-4 {
            bottom: 30%;
            left: 10%;
            width: 450px;
            height: 450px;
            background: radial-gradient(circle, rgba(34,197,94,0.12) 0%, transparent 70%);
            animation-delay: 6s;
        }

        .orb-5 {
            top: 60%;
            left: 20%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(249,115,22,0.1) 0%, transparent 70%);
            animation-delay: 8s;
        }

        .floating-shape {
            position: fixed;
            border: 2px solid rgba(255,255,255,0.1);
            pointer-events: none;
            z-index: 0;
        }

        .shape-1 {
            top: 10%;
            left: 8%;
            width: 200px;
            height: 200px;
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            animation: float-extreme 20s ease-in-out infinite, rotate-slow 30s linear infinite;
        }

        .shape-2 {
            bottom: 15%;
            right: 10%;
            width: 250px;
            height: 250px;
            border-radius: 50%;
            border-style: dashed;
            animation: float-slow 18s ease-in-out infinite, rotate-reverse 25s linear infinite;
        }

        .shape-3 {
            top: 30%;
            right: 20%;
            width: 150px;
            height: 150px;
            border-radius: 20px;
            transform: rotate(45deg);
            animation: bounce 12s ease-in-out infinite, pulse-color 20s linear infinite;
        }

        .shape-4 {
            bottom: 25%;
            left: 15%;
            width: 180px;
            height: 180px;
            border-radius: 40% 60% 60% 40% / 40% 40% 60% 60%;
            border-width: 3px;
            border-style: dotted;
            animation: float 16s ease-in-out infinite, rotate-medium 40s linear infinite;
        }

        .floating-icon {
            position: fixed;
            font-size: 2.5rem;
            opacity: 0.2;
            pointer-events: none;
            z-index: 0;
            filter: drop-shadow(0 10px 20px rgba(0,0,0,0.3));
        }

        .icon-1 { top: 12%; left: 10%; animation: float 14s ease-in-out infinite, rotate-slow 30s linear infinite; }
        .icon-2 { top: 65%; right: 12%; animation: float-slow 18s ease-in-out infinite, rotate-reverse 40s linear infinite; }
        .icon-3 { bottom: 20%; left: 18%; animation: bounce 10s ease-in-out infinite, scale-pulse 8s ease-in-out infinite; }
        .icon-4 { bottom: 40%; right: 20%; animation: float-extreme 22s ease-in-out infinite, pulse-color 15s linear infinite; }
        .icon-5 { top: 45%; left: 25%; animation: spin3d 20s ease-in-out infinite; }
        .icon-6 { top: 75%; right: 30%; animation: glitch 8s ease-in-out infinite, rotate-slow 25s linear infinite; }

        .particle {
            position: fixed;
            width: 6px;
            height: 6px;
            background: rgba(255,255,255,0.4);
            border-radius: 50%;
            pointer-events: none;
            z-index: 0;
            animation: sparkle 5s ease-in-out infinite;
        }

        .particle-1 { top: 15%; left: 15%; animation-delay: 0s; }
        .particle-2 { top: 25%; left: 45%; animation-delay: 1s; }
        .particle-3 { top: 35%; left: 75%; animation-delay: 2s; }
        .particle-4 { top: 45%; left: 25%; animation-delay: 3s; }
        .particle-5 { top: 55%; left: 55%; animation-delay: 4s; }
        .particle-6 { top: 65%; left: 85%; animation-delay: 5s; }
        .particle-7 { top: 75%; left: 35%; animation-delay: 6s; }
        .particle-8 { top: 85%; left: 65%; animation-delay: 7s; }
        .particle-9 { top: 20%; left: 80%; animation-delay: 8s; }
        .particle-10 { top: 70%; left: 10%; animation-delay: 9s; }

        .rainbow-line {
            position: fixed;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, 
                #ff0000, #ff8000, #ffff00, #00ff00, 
                #00ffff, #0000ff, #8000ff, #ff00ff, #ff0000);
            background-size: 200% auto;
            animation: shimmer 10s linear infinite, wave 15s ease-in-out infinite;
            opacity: 0.2;
            pointer-events: none;
            z-index: 0;
        }

        .rainbow-line-1 { top: 20%; }
        .rainbow-line-2 { bottom: 30%; transform: rotate(5deg); }

        /* ===== HEADER ULTRA DYNAMIQUE ===== */
        header {
            background: rgba(10, 15, 25, 0.7);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-bottom: 2px solid transparent;
            border-image: linear-gradient(90deg, #38bdf8, #8b5cf6, #ec4899, #22c55e, #38bdf8);
            border-image-slice: 1;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            animation: slideInLeft 1s ease-out, borderPulse 5s ease-in-out infinite;
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
            color: transparent;
            background: linear-gradient(135deg, #38bdf8, #8b5cf6, #ec4899, #22c55e);
            background-size: 300% auto;
            -webkit-background-clip: text;
            background-clip: text;
            animation: gradientFlow 8s linear infinite, float 6s ease-in-out infinite;
            text-decoration: none;
            letter-spacing: -0.5px;
            transition: all 0.3s;
        }

        @keyframes gradientFlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .logo:hover {
            transform: scale(1.1) rotate(5deg);
            filter: drop-shadow(0 0 30px rgba(56,189,248,0.8));
        }

        .nav-links {
            display: flex;
            gap: 3rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #b0c4de;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.4s;
            position: relative;
            padding: 0.5rem 0;
        }

        .nav-links a::before {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, #38bdf8, #8b5cf6, #ec4899, #22c55e);
            background-size: 300% auto;
            transform: scaleX(0);
            transition: transform 0.4s;
            animation: gradientFlow 4s linear infinite;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            top: -5px;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(56,189,248,0.2) 0%, transparent 70%);
            filter: blur(10px);
            opacity: 0;
            transition: opacity 0.4s;
        }

        .nav-links a:hover {
            color: white;
            transform: translateY(-3px);
            text-shadow: 0 0 20px rgba(56,189,248,0.5);
        }

        .nav-links a:hover::before {
            transform: scaleX(1);
        }

        .nav-links a:hover::after {
            opacity: 1;
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
            animation: zoomIn 1.5s cubic-bezier(0.23, 1, 0.32, 1);
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            color: transparent;
            background: linear-gradient(135deg, #ffffff, #38bdf8, #8b5cf6, #ec4899, #ffffff);
            background-size: 300% auto;
            -webkit-background-clip: text;
            background-clip: text;
            animation: gradientFlow 8s linear infinite, float 7s ease-in-out infinite;
            line-height: 1.2;
            text-shadow: 0 0 30px rgba(56,189,248,0.3);
        }

        .hero p {
            font-size: 1.5rem;
            color: #b0c4de;
            margin-bottom: 2.5rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            animation: slideInRight 1.3s ease-out 0.3s both, pulse-color 10s linear infinite;
        }

        .btn {
            display: inline-block;
            padding: 18px 50px;
            background: linear-gradient(135deg, rgba(56,189,248,0.3), rgba(139,92,246,0.3), rgba(236,72,153,0.3));
            background-size: 200% auto;
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1.2rem;
            border: 2px solid transparent;
            border-image: linear-gradient(90deg, #38bdf8, #8b5cf6, #ec4899);
            border-image-slice: 1;
            backdrop-filter: blur(10px);
            transition: all 0.5s;
            position: relative;
            overflow: hidden;
            animation: borderPulse 4s ease-in-out infinite, float 5s ease-in-out infinite;
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

        .btn::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.2) 0%, transparent 70%);
            animation: rotate-slow 15s linear infinite;
        }

        .btn:hover {
            transform: translateY(-8px) scale(1.1) rotate(2deg);
            box-shadow: 0 30px 40px -5px rgba(139,92,246,0.4);
            background-position: right center;
        }

        .btn:hover::before {
            left: 100%;
        }

        /* ===== SECTION À PROPOS - BLEU CIEL ULTRA DYNAMIQUE ===== */
        #apropos {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            background: linear-gradient(135deg, 
                #e0f2fe 0%,
                #bae6fd 15%,
                #7dd3fc 30%,
                #38bdf8 45%,
                #0ea5e9 60%,
                #0284c7 75%,
                #0369a1 90%,
                #0c4a6e 100%);
            background-size: 400% 400%;
            animation: gradientFlow 20s ease infinite;
        }

        /* Éléments décoratifs ultra dynamiques */
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
            background: radial-gradient(circle at 20% 30%, rgba(255,255,255,0.4) 0%, transparent 30%),
                        radial-gradient(circle at 80% 70%, rgba(255,255,255,0.3) 0%, transparent 30%),
                        radial-gradient(circle at 40% 50%, rgba(139,92,246,0.2) 0%, transparent 40%);
            animation: pulse-glow 10s ease-in-out infinite, rotate-slow 40s linear infinite;
        }

        .blue-decor-2 {
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 30px,
                rgba(255,255,255,0.1) 30px,
                rgba(255,255,255,0.1) 60px
            );
            animation: rotate-medium 50s linear infinite;
        }

        .blue-decor-3 {
            bottom: 0;
            right: 0;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, transparent 70%);
            border-radius: 50%;
            filter: blur(50px);
            animation: float-extreme 25s ease-in-out infinite, pulse-color 15s linear infinite;
        }

        .blue-decor-4 {
            top: 20%;
            right: 10%;
            width: 300px;
            height: 300px;
            border: 5px dashed rgba(255,255,255,0.3);
            border-radius: 50%;
            animation: rotate-fast 30s linear infinite, scale-pulse 8s ease-in-out infinite;
        }

        .blue-decor-5 {
            bottom: 30%;
            left: 5%;
            width: 250px;
            height: 250px;
            background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.5) 4px, transparent 4px);
            background-size: 30px 30px;
            animation: float 20s ease-in-out infinite, rotate-slow 35s linear infinite;
        }

        .blue-decor-6 {
            top: 60%;
            left: 15%;
            width: 200px;
            height: 200px;
            border: 3px dotted rgba(255,255,255,0.4);
            border-radius: 40% 60% 60% 40% / 40% 40% 60% 60%;
            animation: bounce 15s ease-in-out infinite, rotate-reverse 45s linear infinite;
        }

        /* Flocons de lumière améliorés */
        .light-particle {
            position: absolute;
            width: 8px;
            height: 8px;
            background: white;
            border-radius: 50%;
            filter: blur(3px);
            opacity: 0.4;
            animation: sparkle 6s ease-in-out infinite;
            box-shadow: 0 0 20px rgba(255,255,255,0.5);
        }

        .light-particle:nth-child(1) { top: 15%; left: 8%; animation-delay: 0s; }
        .light-particle:nth-child(2) { top: 25%; left: 25%; animation-delay: 0.5s; }
        .light-particle:nth-child(3) { top: 35%; left: 45%; animation-delay: 1s; }
        .light-particle:nth-child(4) { top: 45%; left: 65%; animation-delay: 1.5s; }
        .light-particle:nth-child(5) { top: 55%; left: 85%; animation-delay: 2s; }
        .light-particle:nth-child(6) { top: 65%; left: 15%; animation-delay: 2.5s; }
        .light-particle:nth-child(7) { top: 75%; left: 35%; animation-delay: 3s; }
        .light-particle:nth-child(8) { top: 85%; left: 55%; animation-delay: 3.5s; }
        .light-particle:nth-child(9) { top: 20%; left: 75%; animation-delay: 4s; }
        .light-particle:nth-child(10) { top: 70%; left: 95%; animation-delay: 4.5s; }

        .apropos-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: center;
            position: relative;
            z-index: 10;
        }

        .apropos-text {
            animation: slideInLeft 1.2s cubic-bezier(0.23, 1, 0.32, 1);
            background: rgba(255, 255, 255, 0.25);
            backdrop-filter: blur(15px);
            padding: 3.5rem;
            border-radius: 50px;
            border: 2px solid rgba(255,255,255,0.4);
            box-shadow: 0 40px 60px -20px rgba(0,0,0,0.3);
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
            background: radial-gradient(circle, rgba(255,255,255,0.2) 0%, transparent 70%);
            animation: rotate-slow 30s linear infinite;
        }

        .apropos-text h2 {
            font-size: 3rem;
            font-weight: 800;
            margin-bottom: 2rem;
            color: transparent;
            background: linear-gradient(135deg, #0f172a, #1e293b, #0f172a);
            background-size: 200% auto;
            -webkit-background-clip: text;
            background-clip: text;
            animation: gradientFlow 6s linear infinite;
            position: relative;
            display: inline-block;
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 120px;
            height: 5px;
            background: linear-gradient(90deg, #0f172a, #38bdf8, #8b5cf6, #0f172a);
            background-size: 300% auto;
            border-radius: 3px;
            animation: gradientFlow 4s linear infinite, scale-pulse 3s ease-in-out infinite;
        }

        .apropos-text p {
            color: #0f172a;
            margin-bottom: 1.2rem;
            font-size: 1.15rem;
            line-height: 1.9;
            transition: all 0.5s;
            font-weight: 500;
            position: relative;
            z-index: 2;
            animation: slideInRight 0.8s ease-out;
            animation-fill-mode: both;
        }

        .apropos-text p:nth-child(2) { animation-delay: 0.1s; }
        .apropos-text p:nth-child(3) { animation-delay: 0.2s; }
        .apropos-text p:nth-child(4) { animation-delay: 0.3s; }
        .apropos-text p:nth-child(5) { animation-delay: 0.4s; }

        .apropos-text p:hover {
            transform: translateX(15px) scale(1.02);
            color: #ffffff;
            text-shadow: 0 0 15px rgba(255,255,255,0.5);
        }

        .apropos-text p:last-of-type {
            font-style: italic;
            color: #0f172a;
            margin-top: 2.5rem;
            padding: 1.8rem;
            background: rgba(255,255,255,0.4);
            border-radius: 30px;
            border-left: 6px solid #0f172a;
            font-size: 1.25rem;
            font-weight: 700;
            backdrop-filter: blur(5px);
            animation: borderPulse 4s ease-in-out infinite;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            margin-top: 3rem;
        }

        .skill {
            padding: 12px 32px;
            background: rgba(255, 255, 255, 0.4);
            border: 2px solid rgba(255,255,255,0.5);
            border-radius: 40px;
            color: #0f172a;
            font-weight: 700;
            font-size: 1rem;
            transition: all 0.5s;
            backdrop-filter: blur(8px);
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
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
            transition: left 0.6s;
        }

        .skill::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(56,189,248,0.2) 0%, transparent 70%);
            animation: rotate-slow 15s linear infinite;
        }

        .skill:hover {
            transform: translateY(-8px) scale(1.08) rotate(2deg);
            background: rgba(255,255,255,0.6);
            border-color: white;
            box-shadow: 0 20px 35px -5px rgba(0,0,0,0.3);
            color: #0f172a;
        }

        .skill:hover::before {
            left: 100%;
        }

        /* Photo de profil avec design ultra spécial */
        .apropos-image {
            position: relative;
            display: flex;
            justify-content: center;
            animation: slideInRight 1.2s cubic-bezier(0.23, 1, 0.32, 1);
        }

        .image-frame {
            position: relative;
            width: 100%;
            max-width: 500px;
            aspect-ratio: 1/1;
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            background: linear-gradient(135deg, #ffffff, #e0f2fe, #bae6fd, #7dd3fc);
            background-size: 300% auto;
            animation: gradientFlow 10s ease infinite;
            padding: 10px;
            box-shadow: 
                0 50px 70px -20px rgba(0,0,0,0.4),
                0 0 0 3px rgba(255,255,255,0.7),
                0 0 0 8px rgba(56,189,248,0.4),
                0 0 0 15px rgba(139,92,246,0.2);
            animation: borderPulse 5s ease-in-out infinite, rotate-slow 40s linear infinite;
        }

        .image-frame::before {
            content: '';
            position: absolute;
            top: -20px;
            left: -20px;
            right: -20px;
            bottom: -20px;
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.6),
                rgba(56,189,248,0.6),
                rgba(139,92,246,0.6),
                rgba(236,72,153,0.6),
                rgba(255,255,255,0.6));
            border-radius: inherit;
            filter: blur(30px);
            animation: rotate-medium 15s linear infinite, pulse-glow 8s ease-in-out infinite;
            z-index: -1;
        }

        .image-frame .circle-1,
        .image-frame .circle-2,
        .image-frame .circle-3,
        .image-frame .circle-4,
        .image-frame .circle-5 {
            position: absolute;
            border-radius: 50%;
            border: 3px dashed rgba(255,255,255,0.4);
            animation: rotate-slow 20s linear infinite;
        }

        .image-frame .circle-1 {
            top: -30px;
            left: -30px;
            right: -30px;
            bottom: -30px;
            border-width: 3px;
            animation-duration: 25s;
        }

        .image-frame .circle-2 {
            top: -40px;
            left: -40px;
            right: -40px;
            bottom: -40px;
            border-width: 2px;
            animation-direction: reverse;
            animation-duration: 30s;
        }

        .image-frame .circle-3 {
            top: -50px;
            left: -50px;
            right: -50px;
            bottom: -50px;
            border-width: 2px;
            border-style: dotted;
            animation-duration: 35s;
        }

        .image-frame .circle-4 {
            top: -60px;
            left: -60px;
            right: -60px;
            bottom: -60px;
            border-width: 1px;
            border-style: solid;
            animation-duration: 40s;
            border-color: rgba(255,255,255,0.3);
        }

        .image-frame .circle-5 {
            top: -70px;
            left: -70px;
            right: -70px;
            bottom: -70px;
            border-width: 2px;
            border-style: double;
            animation-duration: 45s;
            animation-direction: reverse;
        }

        .light-rays {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 250%;
            height: 250%;
            background: conic-gradient(
                from 0deg,
                transparent,
                rgba(255,255,255,0.2) 10deg,
                transparent 20deg,
                rgba(56,189,248,0.2) 30deg,
                transparent 40deg,
                rgba(139,92,246,0.2) 50deg,
                transparent 60deg,
                rgba(236,72,153,0.2) 70deg,
                transparent 80deg,
                rgba(34,197,94,0.2) 90deg,
                transparent 100deg
            );
            animation: lightRays 20s linear infinite;
            border-radius: 50%;
            z-index: -1;
        }

        .shooting-star {
            position: absolute;
            width: 200px;
            height: 3px;
            background: linear-gradient(90deg, white, transparent);
            filter: blur(3px);
            opacity: 0.4;
            animation: lightRay 10s linear infinite;
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
            animation-delay: 3s;
        }

        .shooting-star-3 {
            top: 60%;
            left: 20%;
            transform: rotate(15deg);
            animation-delay: 6s;
        }

        .shooting-star-4 {
            bottom: 40%;
            right: 15%;
            transform: rotate(-15deg);
            animation-delay: 9s;
        }

        @keyframes lightRay {
            0% {
                transform: translateX(-200%) translateY(-200%) rotate(45deg);
                opacity: 0;
            }
            10% {
                opacity: 0.4;
            }
            20% {
                transform: translateX(200%) translateY(200%) rotate(45deg);
                opacity: 0;
            }
            100% {
                transform: translateX(200%) translateY(200%) rotate(45deg);
                opacity: 0;
            }
        }

        .apropos-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: inherit;
            transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: block;
            filter: brightness(1.1) contrast(1.05) saturate(1.1);
            box-shadow: inset 0 0 40px rgba(255,255,255,0.4);
            animation: scale-pulse 8s ease-in-out infinite;
        }

        .apropos-image img:hover {
            transform: scale(1.05) rotate(3deg);
            filter: brightness(1.2) contrast(1.1) saturate(1.2);
            box-shadow: 0 0 50px rgba(255,255,255,0.5);
        }

        /* Badges décoratifs améliorés */
        .badge {
            position: absolute;
            background: rgba(255,255,255,0.25);
            backdrop-filter: blur(10px);
            padding: 10px 25px;
            border-radius: 40px;
            color: #0f172a;
            font-weight: 700;
            font-size: 1rem;
            border: 2px solid rgba(255,255,255,0.4);
            animation: float 6s ease-in-out infinite, borderPulse 4s ease-in-out infinite;
            white-space: nowrap;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .badge-1 {
            top: 5%;
            right: -10px;
            animation-delay: 0s;
        }

        .badge-2 {
            bottom: 10%;
            left: -10px;
            animation-delay: 2s;
        }

        .badge-3 {
            top: 40%;
            left: -20px;
            animation-delay: 4s;
        }

        .badge-4 {
            bottom: 30%;
            right: -15px;
            animation-delay: 6s;
        }

        .badge:hover {
            transform: scale(1.1);
            background: rgba(255,255,255,0.4);
        }

        /* ===== SECTION CONTACT AMÉLIORÉE ===== */
        #contact {
            min-height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            position: relative;
            background: linear-gradient(135deg, 
                rgba(10,15,25,0.95) 0%, 
                rgba(20,25,40,0.95) 33%,
                rgba(30,35,50,0.95) 66%,
                rgba(10,15,25,0.95) 100%);
            background-size: 400% 400%;
            animation: gradientFlow 20s ease infinite;
        }

        #contact h2 {
            font-size: 3rem;
            font-weight: 800;
            margin-bottom: 1rem;
            color: transparent;
            background: linear-gradient(135deg, #38bdf8, #8b5cf6, #ec4899);
            -webkit-background-clip: text;
            background-clip: text;
            animation: gradientFlow 6s linear infinite, float 5s ease-in-out infinite;
        }

        .contact-subtitle {
            color: #b0c4de;
            font-size: 1.3rem;
            margin-bottom: 3rem;
            animation: slideInLeft 1s ease-out 0.2s both, pulse-color 12s linear infinite;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
            margin: 3rem 0;
        }

        .contact-card {
            background: rgba(20, 25, 40, 0.7);
            backdrop-filter: blur(15px);
            padding: 3rem 2rem;
            border-radius: 40px;
            border: 2px solid rgba(56,189,248,0.2);
            transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            animation: flipIn 1s ease-out;
            animation-fill-mode: both;
        }

        .contact-card:nth-child(1) { animation-delay: 0.1s; }
        .contact-card:nth-child(2) { animation-delay: 0.3s; }
        .contact-card:nth-child(3) { animation-delay: 0.5s; }

        .contact-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, #38bdf8, #8b5cf6, #ec4899, #22c55e);
            background-size: 300% auto;
            transform: translateX(-100%);
            transition: transform 0.6s;
            animation: gradientFlow 4s linear infinite;
        }

        .contact-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, rgba(56,189,248,0.15) 0%, transparent 70%);
            border-radius: 50%;
            transform: translate(50%, 50%);
            transition: all 0.6s;
            animation: rotate-slow 20s linear infinite;
        }

        .contact-card:hover {
            transform: translateY(-20px) scale(1.05);
            border-color: rgba(139,92,246,0.4);
            box-shadow: 0 40px 50px -15px rgba(139,92,246,0.3);
        }

        .contact-card:hover::before {
            transform: translateX(100%);
        }

        .contact-card:hover::after {
            transform: translate(30%, 30%) scale(2);
        }

        .contact-icon {
            font-size: 4rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            animation: bounce 5s ease-in-out infinite, pulse-color 10s linear infinite;
            filter: drop-shadow(0 0 20px rgba(56,189,248,0.3));
        }

        .contact-card h3 {
            font-size: 1.6rem;
            color: #e0f2fe;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .contact-card p {
            color: #b0c4de;
            margin-bottom: 2rem;
            font-size: 1.1rem;
        }

        .contact-link {
            display: inline-block;
            padding: 14px 38px;
            background: rgba(56,189,248,0.15);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 60px;
            font-weight: 600;
            font-size: 1rem;
            border: 2px solid rgba(56,189,248,0.3);
            backdrop-filter: blur(8px);
            transition: all 0.5s;
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
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }

        .contact-link:hover {
            background: linear-gradient(135deg, rgba(56,189,248,0.3), rgba(139,92,246,0.3));
            color: white;
            border-color: #8b5cf6;
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 20px 30px -5px rgba(139,92,246,0.4);
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
            padding: 15px 40px;
            background: rgba(20,25,40,0.7);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 60px;
            font-weight: 600;
            font-size: 1.1rem;
            border: 2px solid rgba(56,189,248,0.2);
            backdrop-filter: blur(8px);
            transition: all 0.5s;
            animation: dropIn 1s ease-out 0.8s both;
        }

        .social-link:hover {
            background: rgba(139,92,246,0.2);
            color: white;
            border-color: #8b5cf6;
            transform: translateY(-8px) scale(1.05) rotate(2deg);
            box-shadow: 0 25px 35px -5px rgba(139,92,246,0.3);
        }

        /* ===== SECTION WHATSAPP AMÉLIORÉE ===== */
        .whatsapp-section {
            padding: 120px 0;
            background: linear-gradient(135deg, 
                rgba(10,15,25,0.98) 0%, 
                rgba(15,20,30,0.98) 50%,
                rgba(20,25,40,0.98) 100%);
            background-size: 300% 300%;
            animation: gradientFlow 15s ease infinite;
        }

        .whatsapp-container {
            max-width: 1000px;
            margin: 0 auto;
            background: rgba(20,25,40,0.7);
            backdrop-filter: blur(20px);
            padding: 4rem;
            border-radius: 80px;
            border: 3px solid rgba(56,189,248,0.2);
            animation: zoomIn 1.2s ease-out, borderPulse 6s ease-in-out infinite;
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
            background: radial-gradient(circle, rgba(37,211,102,0.08) 0%, transparent 70%);
            animation: rotate-medium 40s linear infinite;
        }

        .whatsapp-header {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2.5rem;
            position: relative;
            z-index: 2;
        }

        .whatsapp-icon-large {
            font-size: 5rem;
            animation: bounce 4s ease-in-out infinite, pulse-color 8s linear infinite;
            filter: drop-shadow(0 0 30px rgba(37,211,102,0.4));
        }

        .whatsapp-header h3 {
            font-size: 3rem;
            font-weight: 800;
            color: transparent;
            background: linear-gradient(135deg, #25D366, #128C7E, #075E54);
            -webkit-background-clip: text;
            background-clip: text;
            animation: gradientFlow 6s linear infinite;
        }

        .whatsapp-header h3 span {
            color: #25D366;
            text-shadow: 0 0 20px rgba(37,211,102,0.4);
            animation: sparkle 3s ease-in-out infinite;
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2.5rem;
            margin-bottom: 2.5rem;
            position: relative;
            z-index: 2;
        }

        .form-group {
            text-align: left;
        }

        .form-group label {
            display: flex;
            align-items: center;
            gap: 0.8rem;
            margin-bottom: 1rem;
            color: #b0c4de;
            font-weight: 600;
            font-size: 1.1rem;
            animation: slideInLeft 0.8s ease-out;
            animation-fill-mode: both;
        }

        .form-group:nth-child(1) label { animation-delay: 0.2s; }
        .form-group:nth-child(2) label { animation-delay: 0.4s; }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 16px 25px;
            background: rgba(10,15,25,0.6);
            border: 3px solid rgba(56,189,248,0.2);
            border-radius: 30px;
            font-size: 1.1rem;
            color: #e0f2fe;
            transition: all 0.5s;
            font-family: inherit;
            animation: slideInRight 0.8s ease-out;
            animation-fill-mode: both;
        }

        .form-group:nth-child(1) input { animation-delay: 0.3s; }
        .form-group:nth-child(2) input { animation-delay: 0.5s; }
        .form-group.full-width textarea { animation-delay: 0.7s; }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #25D366;
            box-shadow: 0 0 0 8px rgba(37,211,102,0.15);
            transform: scale(1.02) translateY(-2px);
            background: rgba(20,25,40,0.8);
        }

        .form-group input:hover,
        .form-group textarea:hover {
            border-color: #8b5cf6;
            transform: translateY(-2px);
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        .whatsapp-btn {
            width: 100%;
            padding: 20px 50px;
            background: linear-gradient(135deg, rgba(37,211,102,0.3), rgba(18,140,126,0.3));
            color: white;
            border: 3px solid rgba(37,211,102,0.4);
            border-radius: 60px;
            font-size: 1.4rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.6s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 1.5rem;
            position: relative;
            overflow: hidden;
            z-index: 2;
            backdrop-filter: blur(5px);
            animation: borderPulse 4s ease-in-out infinite, float 5s ease-in-out infinite;
        }

        .whatsapp-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.7s;
        }

        .whatsapp-btn::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(37,211,102,0.1) 0%, transparent 70%);
            animation: rotate-slow 20s linear infinite;
        }

        .whatsapp-btn:hover {
            transform: translateY(-8px) scale(1.05);
            border-color: #25D366;
            box-shadow: 0 30px 40px -5px rgba(37,211,102,0.3);
            background: linear-gradient(135deg, rgba(37,211,102,0.4), rgba(18,140,126,0.4));
        }

        .whatsapp-btn:hover::before {
            left: 100%;
        }

        .availability-info {
            margin-top: 3rem;
            padding: 2.5rem;
            background: rgba(10,15,25,0.5);
            border-radius: 50px;
            border: 2px solid rgba(56,189,248,0.2);
            backdrop-filter: blur(8px);
            position: relative;
            z-index: 2;
        }

        .schedule {
            display: flex;
            justify-content: center;
            gap: 3rem;
            margin: 2rem 0;
            flex-wrap: wrap;
        }

        .time-badge {
            padding: 12px 30px;
            background: rgba(20,25,40,0.7);
            border-radius: 50px;
            display: flex;
            align-items: center;
            gap: 1rem;
            border: 2px solid rgba(56,189,248,0.3);
            color: #b0c4de;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.5s;
            animation: slideInUp 1s ease-out;
            animation-fill-mode: both;
        }

        .time-badge:nth-child(1) { animation-delay: 0.2s; }
        .time-badge:nth-child(2) { animation-delay: 0.4s; }

        .time-badge:hover {
            transform: scale(1.1) translateY(-5px);
            border-color: #8b5cf6;
            color: white;
            box-shadow: 0 15px 25px -5px rgba(139,92,246,0.3);
        }

        .time-badge.morning { border-left: 6px solid #38bdf8; }
        .time-badge.afternoon { border-left: 6px solid #8b5cf6; }

        .availability-status {
            display: inline-block;
            padding: 10px 30px;
            background: rgba(37,211,102,0.15);
            border-radius: 50px;
            color: #25D366;
            font-weight: 700;
            font-size: 1rem;
            border: 2px solid rgba(37,211,102,0.3);
            animation: sparkle 4s ease-in-out infinite, borderPulse 3s ease-in-out infinite;
        }

        @keyframes slideInUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* ===== FOOTER AMÉLIORÉ ===== */
        footer {
            background: linear-gradient(135deg, rgba(5,10,15,0.9), rgba(10,15,25,0.9));
            color: #b0c4de;
            text-align: center;
            padding: 3rem 0;
            border-top: 3px solid transparent;
            border-image: linear-gradient(90deg, #38bdf8, #8b5cf6, #ec4899, #22c55e);
            border-image-slice: 1;
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 30%, rgba(56,189,248,0.1) 0%, transparent 40%),
                        radial-gradient(circle at 80% 70%, rgba(139,92,246,0.1) 0%, transparent 40%);
            animation: pulse-glow 12s ease-in-out infinite;
        }

        footer::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #38bdf8, #8b5cf6, #ec4899, #22c55e, transparent);
            animation: shimmer 6s linear infinite;
        }

        footer p {
            font-size: 1.1rem;
            animation: float 6s ease-in-out infinite, pulse-color 15s linear infinite;
            position: relative;
            z-index: 2;
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

            .badge-1, .badge-2, .badge-3, .badge-4 {
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
                gap: 1.5rem;
            }

            .orb-1, .orb-2, .orb-3, .orb-4, .orb-5 {
                opacity: 0.2;
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
                font-size: 2rem;
            }

            .time-badge {
                width: 100%;
                justify-content: center;
            }

            .social-links {
                flex-direction: column;
                align-items: center;
            }

            .social-link {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <!-- Orbes lumineux multiples -->
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>
    <div class="orb orb-3"></div>
    <div class="orb orb-4"></div>
    <div class="orb orb-5"></div>
    
    <!-- Formes flottantes -->
    <div class="floating-shape shape-1"></div>
    <div class="floating-shape shape-2"></div>
    <div class="floating-shape shape-3"></div>
    <div class="floating-shape shape-4"></div>
    
    <!-- Icônes flottantes -->
    <div class="floating-icon icon-1">✨</div>
    <div class="floating-icon icon-2">💫</div>
    <div class="floating-icon icon-3">🌟</div>
    <div class="floating-icon icon-4">⚡</div>
    <div class="floating-icon icon-5">🌀</div>
    <div class="floating-icon icon-6">🌈</div>
    
    <!-- Particules -->
    <div class="particle particle-1"></div>
    <div class="particle particle-2"></div>
    <div class="particle particle-3"></div>
    <div class="particle particle-4"></div>
    <div class="particle particle-5"></div>
    <div class="particle particle-6"></div>
    <div class="particle particle-7"></div>
    <div class="particle particle-8"></div>
    <div class="particle particle-9"></div>
    <div class="particle particle-10"></div>
    
    <!-- Lignes arc-en-ciel -->
    <div class="rainbow-line rainbow-line-1"></div>
    <div class="rainbow-line rainbow-line-2"></div>

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
        <!-- Éléments décoratifs bleus ultra dynamiques -->
        <div class="blue-decor blue-decor-1"></div>
        <div class="blue-decor blue-decor-2"></div>
        <div class="blue-decor blue-decor-3"></div>
        <div class="blue-decor blue-decor-4"></div>
        <div class="blue-decor blue-decor-5"></div>
        <div class="blue-decor blue-decor-6"></div>
        
        <!-- Particules de lumière multiples -->
        <div class="light-particle"></div>
        <div class="light-particle"></div>
        <div class="light-particle"></div>
        <div class="light-particle"></div>
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
                    <div class="circle-4"></div>
                    <div class="circle-5"></div>
                    <div class="light-rays"></div>
                    <div class="shooting-star shooting-star-1"></div>
                    <div class="shooting-star shooting-star-2"></div>
                    <div class="shooting-star shooting-star-3"></div>
                    <div class="shooting-star shooting-star-4"></div>
                    <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/642754626_122112963513211419_7763551596132436351_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=HrPMD1Mzk-wQ7kNvwF-W0Kk&_nc_oc=AdmitmpVlD_NkLZbjv5bb1BdGCCLKrDWIu8jwSkutlrW38sKkCh-4igqUNpNQk8v2sg&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=UrnADD8nIJ14FGwl_Mt82Q&_nc_ss=8&oh=00_AfxextLBeI-e-uEMJr1xXOL4FM1WFzyiLwUla6pesQhiMA&oe=69AAF757" alt="Photo de profil - RATIANARIVO Mirindra Matthieu">
                </div>
                <div class="badge badge-1">✨ Développeur</div>
                <div class="badge badge-2">💡 Créatif</div>
                <div class="badge badge-3">🚀 Passionné</div>
                <div class="badge badge-4">🎨 Designer</div>
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
                    <p style="margin-top: 1.5rem; color: #b0c4de; font-size: 1rem;">
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
                statusElement.style.background = 'rgba(37,211,102,0.2)';
                statusElement.style.color = '#25D366';
                statusElement.style.border = '2px solid rgba(37,211,102,0.4)';
            } else {
                statusElement.innerHTML = '⏰ HORS HORAIRE - Réponse à mon retour';
                statusElement.style.background = 'rgba(255,165,0,0.2)';
                statusElement.style.color = '#FFA500';
                statusElement.style.border = '2px solid rgba(255,165,0,0.4)';
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

        // Animation parallaxe simple
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const orbs = document.querySelectorAll('.orb');
            orbs.forEach((orb, index) => {
                orb.style.transform = `translateY(${scrolled * 0.1 * (index % 2 === 0 ? 1 : -1)}px)`;
            });
        });

        document.addEventListener('DOMContentLoaded', function() {
            updateAvailability();
            setInterval(updateAvailability, 60000);
            
            // Créer des particules supplémentaires aléatoirement
            for (let i = 0; i < 20; i++) {
                let particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animation = `sparkle ${5 + Math.random() * 10}s ease-in-out infinite`;
                particle.style.animationDelay = Math.random() * 5 + 's';
                document.body.appendChild(particle);
            }
        });
    </script>
</body>
</html>
