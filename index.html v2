<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio Developer - Vino_Store</title>  <!-- Nama diubah -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        html {
            font-size: 16px;
            scroll-behavior: smooth;
        }
        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #333;
            background: #0a0a0f;
            overflow-x: hidden;
            position: relative;
        }
        #particleCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(135deg, #0a0a0f 0%, #1a1a2e 50%, #16213e 100%);
        }
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #0a0a0f 0%, #1a1a2e 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            transition: all 0.8s ease;
        }
        .loading-screen.hidden {
            opacity: 0;
            visibility: hidden;
            pointer-events: none;
        }
        .loading-content {
            text-align: center;
            animation: loadingPulse 2s infinite ease-in-out;
        }
        .loading-logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
        }
        .loading-logo i {
            font-size: 3rem;
            color: #00d4ff;
            text-shadow: 0 0 20px rgba(0, 212, 255, 0.5);
            animation: logoSpin 3s infinite linear;
        }
        .loading-logo span {
            font-size: 2rem;
            color: #fff;
            font-weight: 700;
            text-shadow: 0 0 10px rgba(0, 212, 255, 0.3);
        }
        .loading-bar {
            width: 300px;
            height: 4px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 2px;
            overflow: hidden;
            margin: 0 auto 20px;
        }
        .loading-progress {
            width: 0;
            height: 100%;
            background: linear-gradient(90deg, #00d4ff, #0099cc, #00d4ff);
            background-size: 200% 100%;
            border-radius: 2px;
            animation: loadingProgress 3s ease-in-out, gradientShift 2s infinite;
        }
        .loading-text {
            color: #ccc;
            font-size: 1rem;
            animation: loadingText 2s infinite ease-in-out;
        }
        @keyframes loadingPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        @keyframes logoSpin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        @keyframes loadingProgress {
            0% { width: 0%; }
            100% { width: 100%; }
        }
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            100% { background-position: 200% 50%; }
        }
        @keyframes loadingText {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }
        .modern-card {
            background: rgba(26, 26, 46, 0.8);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 20px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3), 0 0 0 1px rgba(255, 255, 255, 0.05);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }
        .modern-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.1), transparent);
            transition: left 0.6s ease;
        }
        .modern-card:hover::before {
            left: 100%;
        }
        .modern-card:hover {
            transform: translateY(-10px);
            border-color: rgba(0, 212, 255, 0.5);
            box-shadow: 0 20px 60px rgba(0, 212, 255, 0.2), 0 0 0 1px rgba(0, 212, 255, 0.3);
        }
        .glass-effect {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }
        .neon-text {
            text-shadow: 0 0 5px currentColor, 0 0 10px currentColor, 0 0 15px currentColor, 0 0 20px #00d4ff;
        }
        .neon-border {
            border: 2px solid #00d4ff;
            box-shadow: 0 0 5px #00d4ff, 0 0 10px #00d4ff, 0 0 15px #00d4ff, inset 0 0 5px rgba(0, 212, 255, 0.2);
        }
        .neon-button {
            position: relative;
            background: transparent;
            border: 2px solid #00d4ff;
            color: #00d4ff;
            padding: 12px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            overflow: hidden;
            text-shadow: 0 0 10px #00d4ff;
            box-shadow: 0 0 10px rgba(0, 212, 255, 0.3), inset 0 0 10px rgba(0, 212, 255, 0.1);
        }
        .neon-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.4), transparent);
            transition: left 0.5s ease;
        }
        .neon-button:hover::before {
            left: 100%;
        }
        .neon-button:hover {
            background: rgba(0, 212, 255, 0.1);
            box-shadow: 0 0 20px rgba(0, 212, 255, 0.6), inset 0 0 20px rgba(0, 212, 255, 0.2);
            transform: translateY(-3px);
        }
        .header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: rgba(10, 10, 15, 0.9);
            backdrop-filter: blur(20px);
            z-index: 1000;
            padding: 1rem 0;
            border-bottom: 1px solid rgba(0, 212, 255, 0.2);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.3);
            transition: all 0.3s ease;
        }
        .header.scrolled {
            background: rgba(10, 10, 15, 0.95);
            border-bottom-color: rgba(0, 212, 255, 0.4);
            box-shadow: 0 4px 30px rgba(0, 212, 255, 0.1);
        }
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        .nav-brand h2 {
            color: #00d4ff;
            font-size: 1.5rem;
            font-weight: 700;
            text-shadow: 0 0 20px rgba(0, 212, 255, 0.5);
            animation: brandGlow 3s ease-in-out infinite alternate;
        }
        .nav-brand i {
            margin-right: 8px;
            animation: brandIconRotate 4s ease-in-out infinite;
        }
        @keyframes brandGlow {
            0% { text-shadow: 0 0 20px rgba(0, 212, 255, 0.5); }
            100% { text-shadow: 0 0 30px rgba(0, 212, 255, 0.8), 0 0 40px rgba(0, 212, 255, 0.3); }
        }
        @keyframes brandIconRotate {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(-5deg); }
            75% { transform: rotate(5deg); }
        }
        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        .nav-link {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            padding: 0.5rem 1rem;
            border-radius: 25px;
            position: relative;
            overflow: hidden;
        }
        .nav-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }
        .nav-link:hover::before {
            left: 100%;
        }
        .nav-link:hover {
            color: #00d4ff;
            background: rgba(0, 212, 255, 0.1);
            transform: translateY(-2px);
            text-shadow: 0 0 10px rgba(0, 212, 255, 0.5);
            box-shadow: 0 4px 15px rgba(0, 212, 255, 0.2);
        }
        .nav-link i {
            margin-right: 8px;
        }
        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }
        .hamburger span {
            width: 25px;
            height: 3px;
            background: #fff;
            margin: 3px 0;
            transition: 0.3s;
        }
        .home {
            min-height: 100vh;
            display: flex;
            align-items: center;
            background: transparent;
            position: relative;
            overflow: hidden;
        }
        .home::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 50%, rgba(0, 212, 255, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 80% 20%, rgba(0, 153, 204, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 40% 80%, rgba(0, 212, 255, 0.08) 0%, transparent 50%);
            animation: gradientShift 15s ease-in-out infinite;
            z-index: 0;
        }
        @keyframes gradientShift {
            0%, 100% { 
                background: radial-gradient(circle at 20% 50%, rgba(0, 212, 255, 0.1) 0%, transparent 50%),
                            radial-gradient(circle at 80% 20%, rgba(0, 153, 204, 0.1) 0%, transparent 50%),
                            radial-gradient(circle at 40% 80%, rgba(0, 212, 255, 0.08) 0%, transparent 50%);
            }
            33% {
                background: radial-gradient(circle at 80% 30%, rgba(0, 212, 255, 0.1) 0%, transparent 50%),
                            radial-gradient(circle at 20% 70%, rgba(0, 153, 204, 0.1) 0%, transparent 50%),
                            radial-gradient(circle at 60% 20%, rgba(0, 212, 255, 0.08) 0%, transparent 50%);
            }
            66% {
                background: radial-gradient(circle at 40% 70%, rgba(0, 212, 255, 0.1) 0%, transparent 50%),
                            radial-gradient(circle at 70% 40%, rgba(0, 153, 204, 0.1) 0%, transparent 50%),
                            radial-gradient(circle at 20% 30%, rgba(0, 212, 255, 0.08) 0%, transparent 50%);
            }
        }
        @keyframes float {
            0% { transform: translateY(0px) rotate(0deg); }
            100% { transform: translateY(-100vh) rotate(360deg); }
        }
        .home-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
            min-height: 80vh;
        }
        .home-text h1 {
            font-size: 3.5rem;
            font-weight: 700;
            color: #fff;
            margin-bottom: 1rem;
            line-height: 1.2;
        }
        .highlight {
            color: #00d4ff;
            background: linear-gradient(45deg, #00d4ff, #0099cc);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .typing-text {
            font-size: 1.8rem;
            color: #00d4ff;
            margin-bottom: 1.5rem;
            position: relative;
        }
        .typing-text::after {
            content: '|';
            animation: blink 1s infinite;
        }
        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }
        .home-text p {
            font-size: 1.1rem;
            color: #ccc;
            margin-bottom: 2rem;
            max-width: 500px;
        }
        .home-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }
        .btn {
            padding: 12px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            border: none;
            cursor: pointer;
        }
        .btn-primary {
            background: linear-gradient(45deg, #00d4ff, #0099cc);
            color: #fff;
        }
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.3);
        }
        .btn-secondary {
            background: transparent;
            color: #00d4ff;
            border: 2px solid #00d4ff;
        }
        .btn-secondary:hover {
            background: #00d4ff;
            color: #0f0f23;
            transform: translateY(-3px);
        }
        .profile-card {
            position: relative;
            width: 400px;
            height: 400px;
            margin:
