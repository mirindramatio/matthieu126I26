
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
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 10;
        }

        /* ===== ANIMATIONS ===== */
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
            0%, 100% { filter: drop-shadow(0 0 5px rgba(123, 216, 255, 0.3)); }
            50% { filter: drop-shadow(0 0 25px rgba(172, 148, 255, 0.5)); }
        }

        @keyframes aura-spiral {
            0% { transform: rotate(0deg) scale(1); opacity: 0.1; }
            50% { transform: rotate(180deg) scale(1.1); opacity: 0.2; }
            100% { transform: rotate(360deg) scale(1); opacity: 0.1; }
        }

        @keyframes katana-swing {
            0% { transform: translateY(0) rotate(-10deg); opacity: 0.2; }
            25% { transform: translateY(-15px) rotate(15deg); opacity: 0.3; }
            50% { transform: translateY(5px) rotate(5deg); opacity: 0.25; }
            75% { transform: translateY(-10px) rotate(-5deg); opacity: 0.3; }
            100% { transform: translateY(0) rotate(-10deg); opacity: 0.2; }
        }

        @keyframes shuriken-spin {
            0% { transform: rotate(0deg) scale(1); opacity: 0.2; }
            50% { transform: rotate(180deg) scale(1.1); opacity: 0.3; }
            100% { transform: rotate(360deg) scale(1); opacity: 0.2; }
        }

        @keyframes shuriken-float {
            0% { transform: translateY(0) rotate(0deg); }
            25% { transform: translateY(-10px) rotate(90deg); }
            50% { transform: translateY(5px) rotate(180deg); }
            75% { transform: translateY(-5px) rotate(270deg); }
            100% { transform: translateY(0) rotate(360deg); }
        }

        @keyframes weapon-dance {
            0% { transform: translate(0, 0) rotate(0deg); }
            20% { transform: translate(15px, -10px) rotate(45deg); }
            40% { transform: translate(-10px, 15px) rotate(90deg); }
            60% { transform: translate(20px, 5px) rotate(135deg); }
            80% { transform: translate(-15px, -10px) rotate(180deg); }
            100% { transform: translate(0, 0) rotate(360deg); }
        }

        @keyframes light-ray {
            0% { transform: rotate(0deg) scale(1); opacity: 0; }
            25% { transform: rotate(90deg) scale(1.2); opacity: 0.1; }
            50% { transform: rotate(180deg) scale(1.5); opacity: 0.2; }
            75% { transform: rotate(270deg) scale(1.2); opacity: 0.1; }
            100% { transform: rotate(360deg) scale(1); opacity: 0; }
        }

        @keyframes float-slow {
            0%, 100% { transform: translateY(0) translateX(0); }
            50% { transform: translateY(-12px) translateX(8px); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        @keyframes glow-soft {
            0%, 100% { filter: drop-shadow(0 0 5px rgba(123, 216, 255, 0.2)); }
            50% { filter: drop-shadow(0 0 20px rgba(172, 148, 255, 0.4)); }
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

        @keyframes gradientFlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes mist-weave {
            0% { transform: translateX(0) translateY(0) scale(1); }
            25% { transform: translateX(30px) translateY(-15px) scale(1.1); }
            50% { transform: translateX(-20px) translateY(20px) scale(0.95); }
            75% { transform: translateX(15px) translateY(-10px) scale(1.05); }
            100% { transform: translateX(0) translateY(0) scale(1); }
        }

        @keyframes rotate3d {
            0% { transform: perspective(500px) rotateY(0deg); }
            50% { transform: perspective(500px) rotateY(180deg); }
            100% { transform: perspective(500px) rotateY(360deg); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
        }

        @keyframes glitch {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(2px, -2px); }
            60% { transform: translate(-2px, -2px); }
            80% { transform: translate(2px, 2px); }
            100% { transform: translate(0); }
        }

        @keyframes pulse-scale {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        @keyframes slide-bounce {
            0% { transform: translateX(0); }
            25% { transform: translateX(-10px); }
            50% { transform: translateX(10px); }
            75% { transform: translateX(-5px); }
            100% { transform: translateX(0); }
        }

        @keyframes color-pulse {
            0%, 100% { filter: hue-rotate(0deg); }
            50% { filter: hue-rotate(30deg); }
        }

        @keyframes float-extreme {
            0% { transform: translate(0, 0) rotate(0deg); }
            25% { transform: translate(10px, -15px) rotate(5deg); }
            50% { transform: translate(-10px, 10px) rotate(-5deg); }
            75% { transform: translate(15px, -10px) rotate(3deg); }
            100% { transform: translate(0, 0) rotate(0deg); }
        }

        @keyframes spin-slow {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        @keyframes spin-medium {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(720deg); }
        }

        @keyframes spin-fast {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(1440deg); }
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.1; }
            50% { opacity: 0.3; }
        }

        @keyframes wave {
            0% { transform: translateX(0) translateY(0); }
            25% { transform: translateX(-10px) translateY(5px); }
            50% { transform: translateX(0) translateY(-5px); }
            75% { transform: translateX(10px) translateY(5px); }
            100% { transform: translateX(0) translateY(0); }
        }

        /* ===== ÉLÉMENTS D'AURA ===== */
        .aura {
            position: fixed;
            pointer-events: none;
            z-index: 0;
            border-radius: 50%;
            filter: blur(60px);
        }

        .aura-1 {
            top: 5%;
            left: 5%;
            width: 700px;
            height: 700px;
            background: radial-gradient(circle, rgba(123, 216, 255, 0.12) 0%, transparent 70%);
            animation: aura-pulse 15s ease-in-out infinite, color-pulse 20s linear infinite;
        }

        .aura-2 {
            bottom: 5%;
            right: 5%;
            width: 800px;
            height: 800px;
            background: radial-gradient(circle, rgba(172, 148, 255, 0.1) 0%, transparent 70%);
            animation: aura-pulse 18s ease-in-out infinite reverse, color-pulse 25s linear infinite reverse;
        }

        .aura-3 {
            top: 40%;
            right: 15%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(123, 216, 255, 0.08) 0%, transparent 70%);
            animation: aura-flow 25s ease-in-out infinite, float-extreme 30s ease-in-out infinite;
        }

        .aura-4 {
            bottom: 30%;
            left: 10%;
            width: 650px;
            height: 650px;
            background: radial-gradient(circle, rgba(172, 148, 255, 0.09) 0%, transparent 70%);
            animation: aura-float 22s ease-in-out infinite, spin-slow 40s linear infinite;
        }

        .aura-5 {
            top: 60%;
            left: 20%;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.05) 0%, transparent 70%);
            animation: aura-spiral 30s linear infinite, pulse-scale 8s ease-in-out infinite;
        }

        .aura-6 {
            top: 20%;
            right: 25%;
            width: 450px;
            height: 450px;
            background: radial-gradient(circle, rgba(123, 216, 255, 0.06) 0%, transparent 70%);
            animation: mist-weave 28s ease-in-out infinite, bounce 12s ease-in-out infinite;
        }

        .aura-line {
            position: fixed;
            width: 2px;
            height: 100%;
            background: linear-gradient(180deg, transparent, rgba(123,216,255,0.15), rgba(172,148,255,0.15), transparent);
            filter: blur(8px);
            pointer-events: none;
            z-index: 0;
        }

        .aura-line-1 { left: 15%; animation: aura-float 16s ease-in-out infinite, wave 14s ease-in-out infinite; }
        .aura-line-2 { right: 25%; animation: aura-float 20s ease-in-out infinite reverse, wave 18s ease-in-out infinite reverse; }
        .aura-line-3 { left: 45%; animation: aura-float 24s ease-in-out infinite, shake 22s ease-in-out infinite; }
        .aura-line-4 { right: 35%; animation: aura-float 18s ease-in-out infinite reverse, glitch 12s ease-in-out infinite; }

        .aura-cloud {
            position: fixed;
            background: rgba(255,255,255,0.02);
            border-radius: 1000px;
            filter: blur(50px);
            pointer-events: none;
            z-index: 0;
            animation: aura-flow 30s ease-in-out infinite, float-slow 40s ease-in-out infinite;
        }

        .aura-cloud-1 {
            top: 10%;
            right: 5%;
            width: 600px;
            height: 180px;
            box-shadow: 80px 40px 0 0 rgba(123,216,255,0.02);
        }

        .aura-cloud-2 {
            bottom: 15%;
            left: 5%;
            width: 700px;
            height: 200px;
            box-shadow: 100px 50px 0 0 rgba(172,148,255,0.02);
            animation-delay: 5s;
        }

        .aura-cloud-3 {
            top: 40%;
            right: 15%;
            width: 500px;
            height: 150px;
            box-shadow: 70px 35px 0 0 rgba(255,255,255,0.02);
            animation-delay: 10s;
        }

        .aura-cloud-4 {
            top: 70%;
            left: 20%;
            width: 550px;
            height: 160px;
            box-shadow: 75px 38px 0 0 rgba(123,216,255,0.02);
            animation-delay: 15s;
        }

        .ninja-weapon {
            position: fixed;
            font-size: 2rem;
            pointer-events: none;
            z-index: 0;
            filter: drop-shadow(0 0 15px rgba(172, 148, 255, 0.3));
            opacity: 0.25;
        }

        .katana-1 {
            top: 15%;
            left: 8%;
            transform: rotate(-15deg);
            animation: katana-swing 18s ease-in-out infinite, glow-soft 5s ease-in-out infinite;
        }

        .katana-2 {
            top: 75%;
            right: 10%;
            transform: rotate(160deg);
            animation: katana-swing 22s ease-in-out infinite reverse, glow-soft 6s ease-in-out infinite 1s;
        }

        .katana-3 {
            bottom: 20%;
            left: 15%;
            transform: rotate(45deg);
            animation: katana-swing 20s ease-in-out infinite, glow-soft 7s ease-in-out infinite 2s;
        }

        .katana-4 {
            top: 45%;
            right: 20%;
            transform: rotate(-120deg);
            animation: katana-swing 24s ease-in-out infinite reverse, glow-soft 8s ease-in-out infinite 3s;
        }

        .katana-5 {
            bottom: 35%;
            right: 30%;
            transform: rotate(90deg);
            animation: katana-swing 26s ease-in-out infinite, glow-soft 9s ease-in-out infinite 4s;
        }

        .katana-6 {
            top: 60%;
            left: 25%;
            transform: rotate(-45deg);
            animation: katana-swing 28s ease-in-out infinite reverse, glow-soft 10s ease-in-out infinite 5s;
        }

        .shuriken-1 {
            top: 10%;
            right: 15%;
            font-size: 1.8rem;
            animation: shuriken-spin 12s linear infinite, float 8s ease-in-out infinite;
        }

        .shuriken-2 {
            bottom: 15%;
            left: 20%;
            font-size: 1.8rem;
            animation: shuriken-spin 15s linear infinite reverse, float 9s ease-in-out infinite 2s;
        }

        .shuriken-3 {
            top: 30%;
            left: 30%;
            font-size: 1.8rem;
            animation: shuriken-float 14s ease-in-out infinite, spin-slow 20s linear infinite;
        }

        .shuriken-4 {
            bottom: 40%;
            right: 15%;
            font-size: 1.8rem;
            animation: shuriken-spin 18s linear infinite, bounce 10s ease-in-out infinite;
        }

        .shuriken-5 {
            top: 70%;
            right: 35%;
            font-size: 1.8rem;
            animation: shuriken-float 16s ease-in-out infinite reverse, spin-medium 25s linear infinite;
        }

        .shuriken-6 {
            top: 85%;
            left: 10%;
            font-size: 1.8rem;
            animation: shuriken-spin 20s linear infinite reverse, slide-bounce 12s ease-in-out infinite;
        }

        .shuriken-7 {
            bottom: 25%;
            right: 40%;
            font-size: 1.8rem;
            animation: shuriken-float 22s ease-in-out infinite, spin-fast 30s linear infinite;
        }

        .shuriken-8 {
            top: 40%;
            left: 45%;
            font-size: 1.8rem;
            animation: shuriken-spin 24s linear infinite, shake 8s ease-in-out infinite;
        }

        .aura-particle {
            position: fixed;
            width: 5px;
            height: 5px;
            background: rgba(172, 148, 255, 0.3);
            border-radius: 50%;
            filter: blur(3px);
            pointer-events: none;
            z-index: 0;
            animation: weapon-dance 35s ease-in-out infinite, twinkle 5s ease-in-out infinite;
        }

        .aura-particle-1 { top: 8%; left: 8%; }
        .aura-particle-2 { top: 18%; left: 38%; animation-delay: 2s; }
        .aura-particle-3 { top: 28%; left: 68%; animation-delay: 4s; }
        .aura-particle-4 { top: 38%; left: 18%; animation-delay: 6s; }
        .aura-particle-5 { top: 48%; left: 48%; animation-delay: 8s; }
        .aura-particle-6 { top: 58%; left: 78%; animation-delay: 10s; }
        .aura-particle-7 { top: 68%; left: 28%; animation-delay: 12s; }
        .aura-particle-8 { top: 78%; left: 58%; animation-delay: 14s; }
        .aura-particle-9 { top: 13%; left: 83%; animation-delay: 16s; }
        .aura-particle-10 { top: 63%; left: 3%; animation-delay: 18s; }
        .aura-particle-11 { top: 23%; left: 93%; animation-delay: 20s; }
        .aura-particle-12 { top: 73%; left: 13%; animation-delay: 22s; }

        .aura-ray {
            position: fixed;
            width: 100%;
            height: 100%;
            background: conic-gradient(
                from 0deg,
                transparent,
                rgba(123,216,255,0.04) 45deg,
                transparent 90deg,
                rgba(172,148,255,0.04) 135deg,
                transparent 180deg,
                rgba(123,216,255,0.04) 225deg,
                transparent 270deg,
                rgba(172,148,255,0.04) 315deg,
                transparent 360deg
            );
            pointer-events: none;
            z-index: 0;
            animation: light-ray 50s linear infinite;
        }

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
            padding: 1.2rem 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.6rem;
            font-weight: 400;
            color: #ffffff;
            text-decoration: none;
            letter-spacing: 2px;
            transition: all 0.4s;
            position: relative;
            text-shadow: 0 0 20px rgba(123,216,255,0.4);
            animation: aura-glow 5s ease-in-out infinite, float 6s ease-in-out infinite;
        }

        .logo::before {
            content: '';
            position: absolute;
            top: -8px;
            left: -8px;
            right: -8px;
            bottom: -8px;
            background: radial-gradient(circle, rgba(123,216,255,0.15) 0%, transparent 70%);
            filter: blur(15px);
            animation: aura-pulse 6s ease-in-out infinite;
            z-index: -1;
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: -6px;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, #7bd8ff, #ac94ff, transparent);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.5s;
        }

        .logo:hover {
            transform: translateY(-3px) scale(1.05);
            text-shadow: 0 0 30px rgba(172,148,255,0.6);
        }

        .logo:hover::after {
            transform: scaleX(1);
            transform-origin: left;
        }

        .nav-links {
            display: flex;
            gap: 4rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #b0c4de;
            font-weight: 300;
            font-size: 1.1rem;
            transition: all 0.4s;
            position: relative;
            letter-spacing: 1.5px;
            animation: float 8s ease-in-out infinite;
            animation-delay: calc(0.2s * var(--i));
        }

        .nav-links a:nth-child(1) { --i: 1; }
        .nav-links a:nth-child(2) { --i: 2; }
        .nav-links a:nth-child(3) { --i: 3; }

        .nav-links a::before {
            content: '';
            position: absolute;
            bottom: -6px;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, #7bd8ff, #ac94ff);
            transform: scaleX(0);
            transition: transform 0.4s;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            background: radial-gradient(circle, rgba(123,216,255,0.15) 0%, transparent 70%);
            filter: blur(10px);
            opacity: 0;
            transition: opacity 0.4s;
            z-index: -1;
        }

        .nav-links a:hover {
            color: #ffffff;
            text-shadow: 0 0 15px rgba(123,216,255,0.4);
            transform: translateY(-3px);
        }

        .nav-links a:hover::before {
            transform: scaleX(1);
        }

        .nav-links a:hover::after {
            opacity: 1;
        }

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
            animation: zoomIn 1.5s ease-out;
        }

        .hero h1 {
            font-size: 4.2rem;
            font-weight: 300;
            margin-bottom: 1.5rem;
            color: #ffffff;
            line-height: 1.2;
            text-shadow: 0 0 30px rgba(123,216,255,0.4);
            animation: aura-glow 6s ease-in-out infinite, float 7s ease-in-out infinite;
            letter-spacing: 3px;
        }

        .hero p {
            font-size: 1.4rem;
            color: #b0c4de;
            margin-bottom: 3rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            font-weight: 300;
            letter-spacing: 1.5px;
            line-height: 1.9;
            animation: fadeInUp 1.8s ease-out 0.4s both, glow-soft 5s ease-in-out infinite 2s;
        }

        .btn {
            display: inline-block;
            padding: 16px 50px;
            background: rgba(123,216,255,0.04);
            color: #ffffff;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 300;
            letter-spacing: 2.5px;
            transition: all 0.5s;
            border: 1px solid rgba(123,216,255,0.25);
            backdrop-filter: blur(10px);
            font-size: 1rem;
            position: relative;
            overflow: hidden;
            animation: aura-glow 5s ease-in-out infinite, pulse-scale 4s ease-in-out infinite;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(123,216,255,0.15) 0%, transparent 70%);
            animation: aura-spiral 20s linear infinite;
            opacity: 0;
            transition: opacity 0.5s;
        }

        .btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.15), transparent);
            transition: left 0.8s;
        }

        .btn:hover {
            background: rgba(172,148,255,0.08);
            border-color: rgba(172,148,255,0.4);
            transform: translateY(-6px) scale(1.05);
            box-shadow: 0 25px 35px -15px rgba(0,0,0,0.6);
        }

        .btn:hover::before {
            opacity: 1;
        }

        .btn:hover::after {
            left: 100%;
        }

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
            animation: gradientFlow 25s ease infinite;
        }

        .apropos-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: start;
            position: relative;
            z-index: 10;
            padding-top: 2rem;
        }

        .apropos-text {
            animation: fadeInLeft 1.3s ease-out;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(15px);
            padding: 3.5rem;
            border-radius: 50px;
            border: 1px solid rgba(255,255,255,0.3);
            box-shadow: 0 40px 60px -25px rgba(0,0,0,0.3);
            position: relative;
            overflow: hidden;
            grid-column: 1;
        }

        .apropos-text::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.15) 0%, transparent 70%);
            animation: aura-spiral 40s linear infinite;
            pointer-events: none;
        }

        .apropos-text h2 {
            font-size: 3rem;
            font-weight: 300;
            margin-bottom: 2rem;
            color: #0f172a;
            position: relative;
            display: inline-block;
            letter-spacing: 2.5px;
            text-shadow: 0 0 15px rgba(255,255,255,0.3);
            animation: float 8s ease-in-out infinite;
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -12px;
            left: 0;
            width: 150px;
            height: 2px;
            background: linear-gradient(90deg, #0f172a, rgba(15,23,42,0.2));
            animation: slide-bounce 6s ease-in-out infinite;
        }

        .apropos-text p {
            color: #0f172a;
            margin-bottom: 1.3rem;
            font-size: 1.15rem;
            line-height: 2;
            font-weight: 400;
            transition: all 0.5s;
            position: relative;
            z-index: 2;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
        }

        .apropos-text p:nth-child(2) { animation-delay: 0.1s; }
        .apropos-text p:nth-child(3) { animation-delay: 0.2s; }
        .apropos-text p:nth-child(4) { animation-delay: 0.3s; }
        .apropos-text p:nth-child(5) { animation-delay: 0.4s; }

        .apropos-text p:hover {
            transform: translateX(12px) scale(1.02);
            color: #000000;
            text-shadow: 0 0 10px rgba(255,255,255,0.3);
        }

        .apropos-text p:last-of-type {
            font-style: italic;
            color: #0f172a;
            margin-top: 2.5rem;
            padding: 1.8rem;
            background: rgba(255,255,255,0.25);
            border-radius: 25px;
            border-left: 5px solid #0f172a;
            font-size: 1.2rem;
            font-weight: 400;
            backdrop-filter: blur(8px);
            animation: aura-glow 5s ease-in-out infinite, pulse-scale 6s ease-in-out infinite;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            margin-top: 3rem;
        }

        .skill {
            padding: 12px 28px;
            background: rgba(255,255,255,0.2);
            border: 1px solid rgba(255,255,255,0.4);
            border-radius: 40px;
            color: #0f172a;
            font-weight: 400;
            font-size: 1rem;
            transition: all 0.5s;
            backdrop-filter: blur(8px);
            cursor: default;
            position: relative;
            overflow: hidden;
            animation: fadeInUp 1s ease-out, float 10s ease-in-out infinite;
            animation-fill-mode: both;
        }

        .skill:nth-child(1) { animation-delay: 0.1s; }
        .skill:nth-child(2) { animation-delay: 0.2s; }
        .skill:nth-child(3) { animation-delay: 0.3s; }

        .skill::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.25) 0%, transparent 70%);
            animation: aura-spiral 25s linear infinite;
            opacity: 0;
            transition: opacity 0.5s;
        }

        .skill:hover {
            transform: translateY(-8px) scale(1.05);
            background: rgba(255,255,255,0.35);
            border-color: rgba(255,255,255,0.7);
            box-shadow: 0 20px 30px -10px rgba(0,0,0,0.2);
        }

        .skill:hover::before {
            opacity: 1;
        }

        .apropos-image {
            position: relative;
            display: flex;
            justify-content: center;
            animation: fadeInRight 1.3s ease-out;
            grid-column: 2;
            margin-top: -20px;
        }

        .image-frame {
            position: relative;
            width: 100%;
            max-width: 400px;
            border-radius: 15px;
            padding: 6px;
            background: rgba(255,255,255,0.15);
            box-shadow: 0 30px 50px -20px rgba(0,0,0,0.3);
            z-index: 2;
        }

        .apropos-image img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            transition: transform 0.3s ease;
            display: block;
            opacity: 1;
            position: relative;
            z-index: 3;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .apropos-image img:hover {
            transform: scale(1.02);
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
        }

        #contact {
            min-height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            position: relative;
            background: linear-gradient(135deg, 
                rgba(3,7,18,0.96) 0%, 
                rgba(10,15,25,0.96) 33%,
                rgba(15,20,30,0.96) 66%,
                rgba(3,7,18,0.96) 100%);
            background-size: 400% 400%;
            animation: gradientFlow 30s ease infinite;
        }

        #contact h2 {
            font-size: 3rem;
            font-weight: 300;
            margin-bottom: 1.5rem;
            color: #ffffff;
            letter-spacing: 2.5px;
            text-shadow: 0 0 25px rgba(123,216,255,0.4);
            animation: aura-glow 6s ease-in-out infinite, float 8s ease-in-out infinite;
        }

        .contact-subtitle {
            color: #b0c4de;
            font-size: 1.3rem;
            margin-bottom: 3.5rem;
            font-weight: 300;
            letter-spacing: 1.5px;
            animation: fadeInUp 1.5s ease-out 0.2s both, glow-soft 6s ease-in-out infinite 3s;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .contact-card {
            background: rgba(20,25,40,0.35);
            backdrop-filter: blur(15px);
            padding: 2rem 1.5rem;
            border-radius: 30px;
            border: 1px solid rgba(123,216,255,0.15);
            transition: all 0.6s;
            animation: fadeInUp 1.2s ease-out, float 12s ease-in-out infinite;
            animation-fill-mode: both;
            position: relative;
            overflow: hidden;
        }

        .contact-card:nth-child(1) { animation-delay: 0.2s; }
        .contact-card:nth-child(2) { animation-delay: 0.4s; }
        .contact-card:nth-child(3) { animation-delay: 0.6s; }

        .contact-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(123,216,255,0.08) 0%, transparent 70%);
            animation: aura-spiral 30s linear infinite;
            opacity: 0;
            transition: opacity 0.6s;
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
            transition: transform 0.8s;
        }

        .contact-card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: rgba(172,148,255,0.3);
            background: rgba(25,30,45,0.45);
            box-shadow: 0 40px 50px -20px rgba(0,0,0,0.6);
        }

        .contact-card:hover::before {
            opacity: 1;
        }

        .contact-card:hover::after {
            transform: translateX(100%);
        }

        .contact-icon {
            font-size: 2.8rem;
            margin-bottom: 1.2rem;
            display: inline-block;
            opacity: 0.9;
            filter: drop-shadow(0 0 15px rgba(123,216,255,0.2));
            animation: aura-float 7s ease-in-out infinite;
        }

        .contact-card h3 {
            font-size: 1.4rem;
            color: #ffffff;
            margin-bottom: 0.8rem;
            font-weight: 300;
            letter-spacing: 1.5px;
            animation: glow-soft 5s ease-in-out infinite;
        }

        .contact-card p {
            color: #b0c4de;
            margin-bottom: 1.5rem;
            font-size: 0.95rem;
            font-weight: 300;
        }

        .contact-link {
            display: inline-block;
            padding: 10px 28px;
            background: rgba(123,216,255,0.06);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 300;
            font-size: 0.9rem;
            border: 1px solid rgba(123,216,255,0.2);
            transition: all 0.5s;
            position: relative;
            overflow: hidden;
            letter-spacing: 1px;
            animation: pulse-scale 4s ease-in-out infinite;
        }

        .contact-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.15), transparent);
            transition: left 0.7s;
        }

        .contact-link:hover {
            background: rgba(172,148,255,0.12);
            color: #ffffff;
            border-color: rgba(172,148,255,0.4);
            transform: translateY(-4px) scale(1.02);
        }

        .contact-link:hover::before {
            left: 100%;
        }

        .social-links {
            display: flex;
            gap: 2rem;
            justify-content: center;
            margin-top: 3.5rem;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            padding: 12px 32px;
            background: rgba(20,25,40,0.4);
            color: #b0c4de;
            text-decoration: none;
            border-radius: 30px;
            border: 1px solid rgba(123,216,255,0.15);
            transition: all 0.5s;
            font-weight: 300;
            letter-spacing: 1.5px;
            position: relative;
            overflow: hidden;
            animation: fadeInUp 1.5s ease-out 0.8s both, float 10s ease-in-out infinite;
            font-size: 0.95rem;
        }

        .social-link:nth-child(1) { animation-delay: 0.8s; }
        .social-link:nth-child(2) { animation-delay: 1s; }

        .social-link::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(172,148,255,0.1) 0%, transparent 70%);
            animation: aura-spiral 25s linear infinite;
            opacity: 0;
            transition: opacity 0.5s;
        }

        .social-link:hover {
            background: rgba(30,35,50,0.5);
            color: #ffffff;
            border-color: rgba(172,148,255,0.3);
            transform: translateY(-6px) scale(1.02);
        }

        .social-link:hover::before {
            opacity: 1;
        }

        .whatsapp-section {
            padding: 120px 0;
            background: linear-gradient(135deg, 
                rgba(3,7,18,0.98) 0%, 
                rgba(10,15,25,0.98) 50%,
                rgba(15,20,30,0.98) 100%);
        }

        .whatsapp-container {
            max-width: 1000px;
            margin: 0 auto;
            background: rgba(20,25,40,0.35);
            backdrop-filter: blur(20px);
            padding: 4rem;
            border-radius: 70px;
            border: 1px solid rgba(123,216,255,0.15);
            animation: zoomIn 1.5s ease-out, pulse-scale 8s ease-in-out infinite;
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
            animation: aura-spiral 45s linear infinite, glow-soft 10s ease-in-out infinite;
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
            opacity: 0.9;
            animation: aura-float 6s ease-in-out infinite;
            filter: drop-shadow(0 0 25px rgba(37,211,102,0.3));
        }

        .whatsapp-header h3 {
            font-size: 2.8rem;
            font-weight: 300;
            color: #ffffff;
            letter-spacing: 2px;
            animation: glow-soft 5s ease-in-out infinite;
        }

        .whatsapp-header h3 span {
            color: #25D366;
            opacity: 0.95;
            text-shadow: 0 0 20px rgba(37,211,102,0.3);
            animation: pulse-scale 4s ease-in-out infinite;
        }

        .whatsapp-subtitle {
            text-align: center;
            color: #b0c4de;
            margin-bottom: 3rem;
            font-weight: 300;
            letter-spacing: 1px;
            font-size: 1.2rem;
        }

        .messaging-platforms {
            display: flex;
            gap: 2rem;
            justify-content: center;
            margin-bottom: 2rem;
        }

        .platform-card {
            flex: 1;
            background: rgba(20,25,40,0.3);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 30px;
            border: 1px solid rgba(255,255,255,0.1);
            transition: all 0.3s;
        }

        .platform-card:hover {
            transform: translateY(-5px);
            border-color: rgba(255,255,255,0.2);
            background: rgba(30,35,50,0.4);
        }

        .platform-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: inline-block;
            animation: float 5s ease-in-out infinite;
        }

        .platform-card h4 {
            font-size: 1.5rem;
            color: #ffffff;
            margin-bottom: 1rem;
            font-weight: 300;
        }

        .platform-card p {
            color: #b0c4de;
            margin-bottom: 1.5rem;
            font-size: 0.95rem;
        }

        .platform-link {
            display: inline-block;
            padding: 10px 25px;
            background: rgba(123,216,255,0.1);
            color: #ffffff;
            text-decoration: none;
            border-radius: 30px;
            font-size: 0.9rem;
            border: 1px solid rgba(123,216,255,0.2);
            transition: all 0.3s;
        }

        .platform-link:hover {
            background: rgba(172,148,255,0.2);
            border-color: rgba(172,148,255,0.4);
            transform: translateY(-2px);
        }

        .messaging-separator {
            text-align: center;
            margin: 1rem 0;
            color: #b0c4de;
            font-size: 1.1rem;
            letter-spacing: 1px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
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
            margin-bottom: 0.8rem;
            color: #b0c4de;
            font-weight: 300;
            font-size: 1rem;
            letter-spacing: 1px;
            animation: fadeInLeft 0.8s ease-out, float 8s ease-in-out infinite;
            animation-fill-mode: both;
        }

        .form-group:nth-child(1) label { animation-delay: 0.2s; }
        .form-group:nth-child(2) label { animation-delay: 0.4s; }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 14px 22px;
            background: rgba(10,15,25,0.5);
            border: 1px solid rgba(123,216,255,0.2);
            border-radius: 20px;
            font-size: 1rem;
            color: #e0f2fe;
            transition: all 0.5s;
            font-family: inherit;
            animation: fadeInRight 0.8s ease-out;
            animation-fill-mode: both;
        }

        .form-group:nth-child(1) input { animation-delay: 0.3s; }
        .form-group:nth-child(2) input { animation-delay: 0.5s; }
        .form-group.full-width textarea { animation-delay: 0.7s; }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: rgba(172,148,255,0.5);
            background: rgba(15,20,30,0.6);
            transform: scale(1.01) translateY(-2px);
            box-shadow: 0 0 0 4px rgba(172,148,255,0.1);
        }

        .form-group input:hover,
        .form-group textarea:hover {
            border-color: rgba(172,148,255,0.4);
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        .whatsapp-btn, .messenger-btn {
            width: 100%;
            padding: 16px 45px;
            color: #ffffff;
            border: none;
            border-radius: 40px;
            font-size: 1.2rem;
            font-weight: 300;
            cursor: pointer;
            transition: all 0.6s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1.2rem;
            margin-top: 1.5rem;
            letter-spacing: 1.5px;
            position: relative;
            overflow: hidden;
            z-index: 2;
            animation: pulse-scale 4s ease-in-out infinite;
        }

        .whatsapp-btn {
            background: rgba(37,211,102,0.1);
            border: 1px solid rgba(37,211,102,0.25);
        }

        .messenger-btn {
            background: rgba(0,132,255,0.1);
            border: 1px solid rgba(0,132,255,0.25);
        }

        .whatsapp-btn::before, .messenger-btn::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: aura-spiral 25s linear infinite;
            opacity: 0;
            transition: opacity 0.6s;
        }

        .whatsapp-btn::after, .messenger-btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.15), transparent);
            transition: left 0.8s;
        }

        .whatsapp-btn:hover {
            background: rgba(37,211,102,0.15);
            border-color: rgba(37,211,102,0.4);
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 25px 35px -15px rgba(37,211,102,0.2);
        }

        .messenger-btn:hover {
            background: rgba(0,132,255,0.15);
            border-color: rgba(0,132,255,0.4);
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 25px 35px -15px rgba(0,132,255,0.2);
        }

        .whatsapp-btn:hover::before, .messenger-btn:hover::before {
            opacity: 1;
        }

        .whatsapp-btn:hover::after, .messenger-btn:hover::after {
            left: 100%;
        }

        .availability-info {
            margin-top: 3rem;
            padding: 2.2rem;
            background: rgba(10,15,25,0.4);
            border-radius: 40px;
            border: 1px solid rgba(123,216,255,0.15);
            backdrop-filter: blur(8px);
            position: relative;
            z-index: 2;
            animation: glow-soft 6s ease-in-out infinite;
        }

        .schedule {
            display: flex;
            justify-content: center;
            gap: 2.5rem;
            margin: 2rem 0;
            flex-wrap: wrap;
        }

        .time-badge {
            padding: 10px 25px;
            background: rgba(20,25,40,0.5);
            border-radius: 40px;
            display: flex;
            align-items: center;
            gap: 1rem;
            border: 1px solid rgba(123,216,255,0.2);
            color: #b0c4de;
            font-weight: 300;
            font-size: 1rem;
            transition: all 0.5s;
            animation: fadeInUp 1s ease-out, float 10s ease-in-out infinite;
            animation-fill-mode: both;
            letter-spacing: 1px;
        }

        .time-badge:nth-child(1) { animation-delay: 0.3s; }
        .time-badge:nth-child(2) { animation-delay: 0.6s; }

        .time-badge:hover {
            border-color: rgba(172,148,255,0.4);
            color: #ffffff;
            transform: translateY(-4px) scale(1.02);
            background: rgba(25,30,45,0.6);
        }

        .time-badge.morning { border-left: 4px solid #7bd8ff; }
        .time-badge.afternoon { border-left: 4px solid #ac94ff; }

        .availability-status {
            display: inline-block;
            padding: 8px 25px;
            background: rgba(37,211,102,0.12);
            border-radius: 40px;
            color: #25D366;
            font-weight: 300;
            font-size: 0.95rem;
            border: 1px solid rgba(37,211,102,0.25);
            animation: aura-glow 4s ease-in-out infinite, pulse-scale 5s ease-in-out infinite;
            letter-spacing: 1px;
        }

        footer {
            background: rgba(3, 7, 18, 0.7);
            color: #b0c4de;
            text-align: center;
            padding: 2.5rem 0;
            border-top: 1px solid rgba(123,216,255,0.15);
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
            background: radial-gradient(circle at 20% 30%, rgba(123,216,255,0.05) 0%, transparent 40%),
                        radial-gradient(circle at 80% 70%, rgba(172,148,255,0.05) 0%, transparent 40%);
            animation: aura-pulse 15s ease-in-out infinite;
        }

        footer::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, transparent, #7bd8ff, #ac94ff, transparent);
            animation: aura-flow 10s linear infinite, slide-bounce 12s ease-in-out infinite;
        }

        footer p {
            font-size: 1rem;
            font-weight: 300;
            letter-spacing: 1.5px;
            animation: aura-float 8s ease-in-out infinite, glow-soft 5s ease-in-out infinite;
            position: relative;
            z-index: 2;
        }
    </style>
</head>
<body>
    <div class="aura aura-1"></div>
    <div class="aura aura-2"></div>
    <div class="aura aura-3"></div>
    <div class="aura aura-4"></div>
    <div class="aura aura-5"></div>
    <div class="aura aura-6"></div>
    
    <div class="aura-line aura-line-1"></div>
    <div class="aura-line aura-line-2"></div>
    <div class="aura-line aura-line-3"></div>
    <div class="aura-line aura-line-4"></div>
    
    <div class="aura-cloud aura-cloud-1"></div>
    <div class="aura-cloud aura-cloud-2"></div>
    <div class="aura-cloud aura-cloud-3"></div>
    <div class="aura-cloud aura-cloud-4"></div>
    
    <div class="ninja-weapon katana-1">⚔️</div>
    <div class="ninja-weapon katana-2">⚔️</div>
    <div class="ninja-weapon katana-3">⚔️</div>
    <div class="ninja-weapon katana-4">⚔️</div>
    <div class="ninja-weapon katana-5">⚔️</div>
    <div class="ninja-weapon katana-6">⚔️</div>
    
    <div class="ninja-weapon shuriken-1">✴️</div>
    <div class="ninja-weapon shuriken-2">✴️</div>
    <div class="ninja-weapon shuriken-3">✴️</div>
    <div class="ninja-weapon shuriken-4">✴️</div>
    <div class="ninja-weapon shuriken-5">✴️</div>
    <div class="ninja-weapon shuriken-6">✴️</div>
    <div class="ninja-weapon shuriken-7">✴️</div>
    <div class="ninja-weapon shuriken-8">✴️</div>
    
    <div class="aura-particle aura-particle-1"></div>
    <div class="aura-particle aura-particle-2"></div>
    <div class="aura-particle aura-particle-3"></div>
    <div class="aura-particle aura-particle-4"></div>
    <div class="aura-particle aura-particle-5"></div>
    <div class="aura-particle aura-particle-6"></div>
    <div class="aura-particle aura-particle-7"></div>
    <div class="aura-particle aura-particle-8"></div>
    <div class="aura-particle aura-particle-9"></div>
    <div class="aura-particle aura-particle-10"></div>
    <div class="aura-particle aura-particle-11"></div>
    <div class="aura-particle aura-particle-12"></div>
    
    <div class="aura-ray"></div>

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
                    <span class="skill">HTML</span>
                    <span class="skill">CSS</span>
                    <span class="skill">JavaScript</span>
                </div>
            </div>
            <div class="apropos-image">
                <div class="image-frame">
                    <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/642754626_122112963513211419_7763551596132436351_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=HrPMD1Mzk-wQ7kNvwF-W0Kk&_nc_oc=AdmitmpVlD_NkLZbjv5bb1BdGCCLKrDWIu8jwSkutlrW38sKkCh-4igqUNpNQk8v2sg&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=UrnADD8nIJ14FGwl_Mt82Q&_nc_ss=8&oh=00_AfxextLBeI-e-uEMJr1xXOL4FM1WFzyiLwUla6pesQhiMA&oe=69AAF757" alt="Photo de profil">
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
                    <h3>Messagerie <span>Directe</span></h3>
                </div>
                
                <p class="whatsapp-subtitle">
                    Envoyez-moi un message instantanément sur la plateforme de votre choix
                </p>

                <div class="messaging-platforms">
                    <!-- WhatsApp Card -->
                    <div class="platform-card">
                        <div class="platform-icon">📱</div>
                        <h4>WhatsApp</h4>
                        <p>+261 38 62 876 80</p>
                        <a href="https://wa.me/261386287680?text=Bonjour%20Matthieu%2C%20je%20souhaite%20vous%20contacter%20pour%20un%20projet" 
                           class="platform-link" 
                           target="_blank">
                            Envoyer sur WhatsApp
                        </a>
                    </div>

                    <!-- Facebook Messenger Card -->
                    <div class="platform-card">
                        <div class="platform-icon">💬</div>
                        <h4>Facebook Messenger</h4>
                        <p>RATIANARIVO Mirindra Matthieu</p>
                        <a href="https://m.me/ratianarivo.mirindra" 
                           class="platform-link" 
                           target="_blank">
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

                <div style="display: flex; gap: 1rem; justify-content: center;">
                    <button class="whatsapp-btn" id="sendWhatsAppBtn">
                        <span>📤</span>
                        WhatsApp
                        <span>→</span>
                    </button>
                    <button class="messenger-btn" id="sendMessengerBtn">
                        <span>💬</span>
                        Messenger
                        <span>→</span>
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

        document.getElementById('sendMessengerBtn').addEventListener('click', function() {
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
            
            // Construction du message pour Messenger
            var texteMessage = `Bonjour Matthieu, je suis ${nom}.`;
            
            if (telephone) {
                texteMessage += ` Mon téléphone: ${telephone}.`;
            }
            
            texteMessage += ` ${message}`;
            
            // Redirection vers Messenger avec le profil Facebook
            // Note: L'utilisateur devra être connecté à Facebook
            window.open(`https://m.me/ratianarivo.mirindra?text=${encodeURIComponent(texteMessage)}`, '_blank');
        });

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
            } else {
                statusElement.innerHTML = '⏰ HORS HORAIRE - Réponse à mon retour';
                statusElement.style.background = 'rgba(255,165,0,0.15)';
                statusElement.style.color = '#FFA500';
            }
        }

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

        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const auraElements = document.querySelectorAll('.aura, .aura-cloud, .ninja-weapon, .aura-line, .aura-particle');
            auraElements.forEach((el, index) => {
                const speed = 0.05 + (index * 0.01);
                el.style.transform = `translateY(${scrolled * speed}px)`;
            });
        });

        document.addEventListener('DOMContentLoaded', function() {
            updateAvailability();
            setInterval(updateAvailability, 60000);
        });
    </script>
</body>
</html>
