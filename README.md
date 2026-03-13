<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sehar - A Special Celebration</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;800;900&family=Cormorant+Garamond:wght@300;400;600;700&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: #000;
        }

        .page {
            width: 100vw;
            height: 100vh;
            position: fixed;
            top: 0;
            left: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.8s ease-in-out;
            overflow-y: auto;
            z-index: 1;
        }

        .page.active {
            opacity: 1;
            pointer-events: auto;
            z-index: 10;
        }

        /* ============ PAGE 0 - WELCOME ============ */
        .page-welcome {
            background: linear-gradient(135deg, #1a0033 0%, #2d0052 25%, #1a0033 50%, #0d001a 75%, #1a0033 100%);
        }

        .particles-bg {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        .blob {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.3;
            mix-blend-mode: screen;
            animation: orbFloat 8s ease-in-out infinite;
        }

        .blob1 { width: 400px; height: 400px; background: #ff006e; top: -100px; right: -100px; }
        .blob2 { width: 350px; height: 350px; background: #b200ff; bottom: -100px; left: -100px; animation-delay: 2s; }
        .blob3 { width: 300px; height: 300px; background: #00d9ff; top: 50%; left: 30%; animation-delay: 4s; }

        @keyframes orbFloat {
            0%, 100% { transform: translate(0, 0); }
            25% { transform: translate(30px, -30px); }
            50% { transform: translate(-20px, 20px); }
            75% { transform: translate(40px, 10px); }
        }

        .content-wrapper {
            position: relative;
            z-index: 10;
            text-align: center;
            animation: slideInDown 1s ease-out;
        }

        @keyframes slideInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .sehar-title {
            font-family: 'Playfair Display', serif;
            font-size: 100px;
            font-weight: 900;
            background: linear-gradient(120deg, #ff006e 0%, #00d9ff 50%, #ff006e 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -2px;
            margin: 0;
            line-height: 1;
            animation: glowPulse 2s ease-in-out infinite;
            margin-bottom: 20px;
        }

        @keyframes glowPulse {
            0%, 100% { filter: drop-shadow(0 0 30px rgba(255, 0, 110, 0.6)); }
            50% { filter: drop-shadow(0 0 50px rgba(0, 217, 255, 0.6)); }
        }

        .subtitle {
            font-family: 'Cormorant Garamond', serif;
            font-size: 28px;
            color: #00d9ff;
            letter-spacing: 3px;
            margin-bottom: 20px;
            animation: slideUp 1s ease-out 0.1s both;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .welcome-text {
            font-size: 16px;
            color: #b0b0ff;
            max-width: 500px;
            line-height: 1.8;
            margin: 30px 0;
            animation: slideUp 1s ease-out 0.2s both;
        }

        .btn {
            margin-top: 30px;
            padding: 14px 45px;
            font-size: 15px;
            font-weight: 600;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            animation: slideUp 1s ease-out 0.3s both;
        }

        .btn-primary {
            background: linear-gradient(120deg, #ff006e 0%, #00d9ff 100%);
            color: white;
            box-shadow: 0 15px 50px -15px rgba(255, 0, 110, 0.6);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 20px 60px -10px rgba(255, 0, 110, 0.8);
        }

        .btn-primary:active {
            transform: translateY(0);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: #00d9ff;
            border: 2px solid #00d9ff;
            margin: 10px;
        }

        .btn-secondary:hover {
            background: rgba(0, 217, 255, 0.2);
            transform: translateY(-2px);
        }

        /* ============ PAGE 1 - MESSAGE ============ */
        .page-message {
            background: linear-gradient(135deg, #0d0221 0%, #1d0b4a 50%, #0d0221 100%);
            padding: 40px 20px;
        }

        .message-card {
            background: rgba(45, 0, 82, 0.85);
            border: 2px solid #ff006e;
            border-radius: 25px;
            padding: 45px 35px;
            backdrop-filter: blur(10px);
            max-width: 750px;
            box-shadow: 0 20px 60px rgba(255, 0, 110, 0.2);
            animation: fadeInScale 0.8s ease-out;
        }

        @keyframes fadeInScale {
            from { opacity: 0; transform: scale(0.95); }
            to { opacity: 1; transform: scale(1); }
        }

        .message-title {
            font-family: 'Playfair Display', serif;
            font-size: 38px;
            color: #ff006e;
            margin-bottom: 25px;
            text-align: center;
        }

        .message-text {
            font-family: 'Cormorant Garamond', serif;
            font-size: 18px;
            color: #d0d0ff;
            line-height: 1.9;
            margin-bottom: 20px;
            font-weight: 300;
        }

        .highlight-text {
            color: #00d9ff;
            font-weight: 600;
            font-style: italic;
        }

        .emoji-sep {
            text-align: center;
            font-size: 24px;
            margin: 25px 0;
            letter-spacing: 8px;
        }

        .button-group {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 35px;
            flex-wrap: wrap;
        }

        /* ============ PAGE 2 - CAKE ============ */
        .page-cake {
            background: linear-gradient(135deg, #ff006e 0%, #b200ff 25%, #6a0dad 50%, #3d0066 75%, #1a0033 100%);
            padding: 40px 20px;
        }

        .cake-title {
            color: white;
            font-size: 32px;
            margin-bottom: 25px;
            font-family: 'Playfair Display', serif;
            animation: slideUp 1s ease-out;
        }

        .cake-container {
            perspective: 1200px;
            margin: 40px 0;
            animation: slideUp 0.8s ease-out 0.2s both;
        }

        .cake-wrapper {
            position: relative;
            width: 250px;
            height: 320px;
            margin: 0 auto;
        }

        .plate {
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 250px;
            height: 18px;
            background: linear-gradient(180deg, #fff5e1 0%, #ffe8b6 100%);
            border-radius: 50%;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5), inset -2px -2px 5px rgba(0, 0, 0, 0.2);
        }

        .cake-body {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            bottom: 18px;
        }

        .layer {
            position: relative;
            width: 180px;
            height: 60px;
            background: linear-gradient(180deg, #f4a460 0%, #d2691e 100%);
            margin-bottom: -12px;
            border-radius: 10px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4), inset -3px -3px 8px rgba(0, 0, 0, 0.3);
            animation: layerDrop 0.6s ease-out;
            overflow: hidden;
        }

        @keyframes layerDrop {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .layer:nth-child(2) { animation-delay: 0.15s; }
        .layer:nth-child(3) { animation-delay: 0.3s; }

        .frosting {
            position: absolute;
            top: -6px;
            left: 0;
            right: 0;
            height: 12px;
            background: linear-gradient(180deg, #ff69b4 0%, #ff1493 100%);
            border-radius: 50%;
        }

        .sprinkle {
            position: absolute;
            width: 3px;
            height: 10px;
            background: linear-gradient(to bottom, #00d9ff, #ff006e);
            top: -10px;
            border-radius: 2px;
            animation: sprinkleSpin 0.6s ease-out;
        }

        @keyframes sprinkleSpin {
            from { opacity: 0; transform: translateY(-10px) rotate(0deg); }
            to { opacity: 1; transform: translateY(0) rotate(360deg); }
        }

        .sprinkle:nth-child(1) { left: 20%; animation-delay: 0.1s; }
        .sprinkle:nth-child(2) { left: 35%; animation-delay: 0.15s; }
        .sprinkle:nth-child(3) { left: 50%; animation-delay: 0.2s; }
        .sprinkle:nth-child(4) { left: 65%; animation-delay: 0.25s; }
        .sprinkle:nth-child(5) { left: 80%; animation-delay: 0.3s; }

        .candle {
            position: absolute;
            width: 7px;
            height: 45px;
            background: linear-gradient(90deg, #ffd700 0%, #ffed4e 100%);
            bottom: 240px;
            border-radius: 4px;
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.4);
            transition: all 0.5s ease;
            animation: candleAppear 0.6s ease-out;
        }

        @keyframes candleAppear {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .candle.lit::after {
            content: '';
            position: absolute;
            bottom: 45px;
            left: 50%;
            transform: translateX(-50%);
            width: 8px;
            height: 18px;
            background: linear-gradient(to top, #ff6b35 0%, #ffcd69 50%, #ffd700 100%);
            border-radius: 50% 50% 50% 0;
            box-shadow: 0 0 15px rgba(255, 107, 53, 0.8);
            animation: flameWave 0.5s ease-in-out infinite;
        }

        @keyframes flameWave {
            0%, 100% { height: 18px; opacity: 1; }
            50% { height: 22px; opacity: 0.9; }
        }

        .candle:nth-child(1) { left: 28%; }
        .candle:nth-child(2) { left: 50%; }
        .candle:nth-child(3) { left: 72%; }

        .candle.blown {
            opacity: 0;
            transform: translateY(-50px);
        }

        .cake-text {
            text-align: center;
            color: white;
            font-size: 24px;
            margin-top: 30px;
            animation: textPop 0.8s ease-out 0.5s both;
        }

        @keyframes textPop {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }

        /* ============ PAGE 3 - MOMENT ============ */
        .page-moment {
            background: linear-gradient(135deg, #00d9ff 0%, #00ffff 25%, #00d9ff 50%, #0099ff 75%, #006699 100%);
            padding: 40px 20px;
        }

        .moment-card {
            background: rgba(0, 50, 100, 0.9);
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 25px;
            padding: 45px 35px;
            backdrop-filter: blur(15px);
            max-width: 700px;
            box-shadow: 0 20px 60px rgba(0, 217, 255, 0.2);
            animation: slideFromRight 0.8s ease-out;
        }

        @keyframes slideFromRight {
            from { opacity: 0; transform: translateX(40px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .moment-title {
            font-family: 'Playfair Display', serif;
            font-size: 38px;
            color: #00ffff;
            margin-bottom: 25px;
            text-align: center;
            text-shadow: 0 0 15px rgba(0, 217, 255, 0.4);
        }

        .moment-text {
            font-family: 'Cormorant Garamond', serif;
            font-size: 18px;
            color: #ffffff;
            line-height: 1.9;
            font-weight: 300;
            text-align: center;
            margin: 15px 0;
        }

        /* ============ PAGE 4 - FUNNY ============ */
        .page-funny {
            background: linear-gradient(135deg, #ff8c00 0%, #ff6347 25%, #ff4500 50%, #cc3300 75%, #993300 100%);
            padding: 40px 20px;
        }

        .gobar-emoji {
            font-size: 120px;
            margin-bottom: 30px;
            animation: gobarBounce 0.8s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        @keyframes gobarBounce {
            0% { opacity: 0; transform: scale(0) rotate(-180deg); }
            50% { opacity: 1; }
            100% { opacity: 1; transform: scale(1) rotate(0deg); }
        }

        .funny-card {
            background: rgba(139, 69, 19, 0.9);
            border: 3px dashed rgba(255, 255, 255, 0.4);
            border-radius: 20px;
            padding: 35px 30px;
            backdrop-filter: blur(10px);
            max-width: 700px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.4);
            animation: jiggle 0.6s ease-out;
        }

        @keyframes jiggle {
            0% { transform: rotate(-2deg); }
            25% { transform: rotate(2deg); }
            50% { transform: rotate(-2deg); }
            75% { transform: rotate(2deg); }
            100% { transform: rotate(0deg); }
        }

        .funny-title {
            font-family: 'Playfair Display', serif;
            font-size: 42px;
            color: #fff5e1;
            margin-bottom: 20px;
            text-align: center;
        }

        .funny-text {
            font-family: 'Cormorant Garamond', serif;
            font-size: 20px;
            color: #ffe8b6;
            line-height: 1.8;
            text-align: center;
            margin: 15px 0;
        }

        .laughing {
            display: flex;
            justify-content: center;
            gap: 20px;
            font-size: 60px;
            margin: 25px 0;
        }

        .laughing span {
            animation: bounce 1s ease-in-out infinite;
        }

        .laughing span:nth-child(2) { animation-delay: 0.15s; }
        .laughing span:nth-child(3) { animation-delay: 0.3s; }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        /* ============ PAGE 5 - ENDING ============ */
        .page-ending {
            background: linear-gradient(135deg, #ff1493 0%, #ff69b4 25%, #ff006e 50%, #c71585 75%, #8b008b 100%);
            padding: 40px 20px;
        }

        .ending-card {
            background: rgba(70, 10, 50, 0.95);
            border: 2px solid #ff006e;
            border-radius: 25px;
            padding: 45px 35px;
            backdrop-filter: blur(15px);
            max-width: 700px;
            box-shadow: 0 20px 60px rgba(255, 20, 147, 0.3);
            animation: endingEntry 0.8s ease-out;
        }

        @keyframes endingEntry {
            from { opacity: 0; transform: scale(0.95); }
            to { opacity: 1; transform: scale(1); }
        }

        .ending-title {
            font-family: 'Playfair Display', serif;
            font-size: 42px;
            background: linear-gradient(120deg, #ff006e 0%, #ff69b4 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 25px;
            text-align: center;
        }

        .ending-text {
            font-family: 'Cormorant Garamond', serif;
            font-size: 18px;
            color: #ffb3d9;
            line-height: 1.8;
            text-align: center;
            margin: 12px 0;
        }

        .dua-text {
            font-style: italic;
            color: #ff69b4;
            font-weight: 600;
        }

        .heart-float {
            position: fixed;
            font-size: 40px;
            pointer-events: none;
        }

        @media (max-width: 768px) {
            .sehar-title { font-size: 50px; }
            .message-title { font-size: 28px; }
            .btn { padding: 10px 30px; font-size: 13px; }
        }
    </style>
</head>
<body>
    <!-- PAGE 0 - WELCOME -->
    <div id="page0" class="page page-welcome active">
        <div class="particles-bg">
            <div class="blob blob1"></div>
            <div class="blob blob2"></div>
            <div class="blob blob3"></div>
        </div>
        <div class="content-wrapper">
            <h1 class="sehar-title">SEHAR</h1>
            <p class="subtitle">✨ A SPECIAL CELEBRATION ✨</p>
            <p class="welcome-text">
                Kuch lamhay hote hain jo sirf tumhare liye banaye jaate hain...
                <br><br>
                Tum unn lamhon mein se ek ho.
            </p>
            <button class="btn btn-primary" onclick="changePage(1)">BEGIN JOURNEY →</button>
        </div>
    </div>

    <!-- PAGE 1 - MESSAGE -->
    <div id="page1" class="page page-message">
        <div class="message-card">
            <h2 class="message-title">A Message for You</h2>
            <p class="message-text">
                Sehar, aaj ka din shayad duniya ke hisaab se <span class="highlight-text">tumhara birthday</span> hai.
            </p>
            <p class="message-text">
                Normally log <span class="highlight-text">'Happy Birthday'</span> bolte hain, lekin Islam mein birthday celebrate karna ya 'Happy Birthday' kehna jaayez nahi maana jata.
            </p>
            <p class="message-text">
                <span class="highlight-text">Isliye main woh lafz nahi bolunga.</span>
            </p>
            <div class="emoji-sep">⭐ ✨ ⭐</div>
            <p class="message-text">
                Lekin iska matlab ye bilkul nahi ke <span class="highlight-text">tum mere liye special nahi ho.</span> Tumhari value mere liye bahut zyada hai.
            </p>
            <p class="message-text">
                Main bas ye chahta hoon ke <span class="highlight-text">Allah tumhe hamesha khush rakhe, sehat de, aur tumhari zindagi mein barkat de.</span>
            </p>
        </div>
        <div class="button-group">
            <button class="btn btn-secondary" onclick="changePage(0)">← BACK</button>
            <button class="btn btn-primary" onclick="changePage(2)">CONTINUE →</button>
        </div>
    </div>

    <!-- PAGE 2 - CAKE -->
    <div id="page2" class="page page-cake">
        <h2 class="cake-title">✨ Theek Hai... ✨</h2>
        
        <div class="cake-container">
            <div class="cake-wrapper">
                <div class="plate"></div>
                
                <div class="cake-body">
                    <div class="layer">
                        <div class="frosting"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                    </div>
                    
                    <div class="layer">
                        <div class="frosting"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                    </div>
                    
                    <div class="layer">
                        <div class="frosting"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                        <div class="sprinkle"></div>
                    </div>
                </div>

                <div class="candle lit"></div>
                <div class="candle lit"></div>
                <div class="candle lit"></div>
            </div>
        </div>

        <div class="cake-text">💨 Phoonk Maro! 💨</div>

        <button class="btn btn-primary" id="blowBtn" onclick="blowCandles()">PHOONK MARO! 🎂</button>

        <div class="button-group" style="margin-top: 30px;">
            <button class="btn btn-secondary" onclick="changePage(1)">← BACK</button>
        </div>
    </div>

    <!-- PAGE 3 - MOMENT -->
    <div id="page3" class="page page-moment">
        <div class="moment-card">
            <h2 class="moment-title">The Moment</h2>
            <p class="moment-text">
                Aur haan… ek chhoti si cheez maine tumhare liye banayi hai.
            </p>
            <p class="moment-text" style="font-size: 24px; margin-top: 25px;">
                🎂 ✨ 💫
            </p>
            <p class="moment-text">
                Kyunki tum mere liye special ho. Bilkul special.
            </p>
        </div>

        <div class="button-group" style="margin-top: 40px;">
            <button class="btn btn-secondary" onclick="changePage(2)">← BACK</button>
            <button class="btn btn-primary" onclick="changePage(4)">SURPRISE →</button>
        </div>
    </div>

    <!-- PAGE 4 - FUNNY -->
    <div id="page4" class="page page-funny">
        <div class="gobar-emoji">💩</div>

        <div class="funny-card">
            <h2 class="funny-title">HAHA! 😭</h2>
            <p class="funny-text">
                Sehar, tumhari <span style="color: #ffed4e; font-weight: 700;">GOBAR WALI AADAT</span> ki yaad mein...
            </p>
            <p class="funny-text">
                Ye <span style="color: #ffed4e; font-weight: 700;">SPECIAL CAKE</span> banaya gaya hai! 🍰
            </p>
            <p class="funny-text">
                Kya funny scene tha assignment banana and sitting there like 💩💩💩
            </p>
            <p class="funny-text">
                "Sehar ko assignment dena matlab sure shot failure!" 😂
            </p>
            <div class="laughing">
                <span>😂</span>
                <span>🤣</span>
                <span>😂</span>
            </div>
        </div>

        <div class="button-group" style="margin-top: 40px;">
            <button class="btn btn-secondary" onclick="changePage(3)">← BACK</button>
            <button class="btn btn-primary" onclick="changePage(5)">CONTINUE →</button>
        </div>
    </div>

    <!-- PAGE 5 - ENDING -->
    <div id="page5" class="page page-ending">
        <div class="ending-card">
            <h2 class="ending-title">Jokes Apart… 💜</h2>
            
            <p class="ending-text">
                Tum meri life ki un logon mein se ho jo
            </p>
            <p class="ending-text" style="font-size: 20px; font-weight: 600; color: #ff69b4;">
                GENUINELY IMPORTANT HAIN
            </p>

            <div style="border-left: 3px solid #ff006e; padding-left: 20px; margin: 25px 0;">
                <p class="ending-text">
                    Aur haan, assignment bana rahi ho… uske liye bhi <span class="dua-text">SHUKRIYA</span> 😊
                </p>
            </div>

            <p class="ending-text" style="margin-top: 30px; font-size: 16px;">
                Allah tumhe hamesha <span class="dua-text">khush</span> rakhe,
            </p>
            <p class="ending-text" style="font-size: 16px;">
                Tumhari har <span class="dua-text">dua qubool</span> ho,
            </p>
            <p class="ending-text" style="font-size: 16px;">
                Aur tumhari zindagi hamesha <span class="dua-text">roshan</span> rahe. ✨
            </p>

            <p style="text-align: center; font-size: 24px; margin-top: 25px;">
                💜 ⭐ 💜
            </p>
        </div>

        <div class="button-group" style="margin-top: 40px; margin-bottom: 40px;">
            <button class="btn btn-secondary" onclick="changePage(4)">← BACK</button>
            <button class="btn btn-primary" onclick="changePage(0)">START AGAIN</button>
        </div>
    </div>

    <script>
        let currentPage = 0;

        function changePage(pageNum) {
            // Hide all pages
            const pages = document.querySelectorAll('.page');
            pages.forEach(page => {
                page.classList.remove('active');
            });

            // Show target page
            document.getElementById('page' + pageNum).classList.add('active');
            currentPage = pageNum;

            // Reset candles when going back to page 2
            if (pageNum === 2) {
                resetCandles();
            }

            // Start floating hearts on page 5
            if (pageNum === 5) {
                startFloatingHearts();
            }
        }

        function blowCandles() {
            const candles = document.querySelectorAll('#page2 .candle');
            candles.forEach((candle, index) => {
                setTimeout(() => {
                    candle.classList.add('blown');
                }, index * 80);
            });

            const btn = document.getElementById('blowBtn');
            btn.textContent = '✨ CANDLES BLOWN! ✨';
            btn.disabled = true;
            btn.style.opacity = '0.6';
            btn.style.cursor = 'not-allowed';

            setTimeout(() => {
                changePage(3);
            }, 1200);
        }

        function resetCandles() {
            const candles = document.querySelectorAll('#page2 .candle');
            candles.forEach(candle => {
                candle.classList.remove('blown');
            });

            const btn = document.getElementById('blowBtn');
            btn.textContent = 'PHOONK MARO! 🎂';
            btn.disabled = false;
            btn.style.opacity = '1';
            btn.style.cursor = 'pointer';
        }

        function startFloatingHearts() {
            const emojis = ['💜', '⭐', '💫', '✨'];
            
            for (let i = 0; i < 20; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.className = 'heart-float';
                    heart.textContent = emojis[Math.floor(Math.random() * emojis.length)];
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.bottom = '-50px';
                    heart.style.animation = `floatUp ${3 + Math.random() * 2}s linear forwards`;
                    document.body.appendChild(heart);

                    setTimeout(() => {
                        heart.remove();
                    }, 5000);
                }, i * 200);
            }
        }

        // Add floating animation
        const style = document.createElement('style');
        style.textContent = `
            @keyframes floatUp {
                0% {
                    opacity: 1;
                    transform: translateY(0) translateX(0);
                }
                100% {
                    opacity: 0;
                    transform: translateY(-100vh) translateX(100px) rotate(360deg);
                }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
