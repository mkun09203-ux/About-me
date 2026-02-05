<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aaditya Deep Sea Dev</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            background: #000b1a;
            height: 100vh;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Consolas', monospace;
        }

        /* Deep Sea Background */
        .ocean {
            position: absolute;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, #003a5d 0%, #000b1a 100%);
            z-index: -2;
        }

        /* 🐋 Realistic Blue Whale Animation */
        .whale {
            position: absolute;
            width: 450px;
            top: 35%;
            left: -500px;
            opacity: 0.7;
            filter: drop-shadow(0 0 15px #00d4ff);
            z-index: -1;
            /* Yahan humne ek active public link dala hai */
            content: url('https://pngimg.com/uploads/whale/whale_PNG14.png');
            animation: swim 25s linear infinite;
        }

        @keyframes swim {
            0% { left: -500px; transform: translateY(0) rotate(5deg); }
            50% { transform: translateY(-40px) rotate(-3deg); }
            100% { left: 110%; transform: translateY(0) rotate(5deg); }
        }

        /* Sea Bubbles */
        .bubble {
            position: absolute;
            background: rgba(255, 255, 255, 0.15);
            border-radius: 50%;
            bottom: -50px;
            animation: rise 8s infinite ease-in;
        }

        @keyframes rise {
            0% { bottom: -50px; transform: scale(1); opacity: 0.8; }
            100% { bottom: 110%; transform: scale(1.5); opacity: 0; }
        }

        /* Glassmorphism Window */
        .window {
            width: 380px;
            background: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 0 40px rgba(0, 212, 255, 0.2);
            transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            z-index: 10;
        }

        .header { display: flex; gap: 8px; margin-bottom: 20px; }
        .dot { width: 12px; height: 12px; border-radius: 50%; }
        .r { background: #ff5f56; } .y { background: #ffbd2e; } .g { background: #27c93f; }

        .about-me {
            color: #ffffff;
            line-height: 1.8;
            font-size: 16px;
        }

        .keyword { color: #ff79c6; }
        .var { color: #00d4ff; }
        .val { color: #50fa7b; }

        /* Social Menu & Fingerprint */
        .social-menu {
            position: absolute;
            bottom: 40px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .fingerprint {
            width: 80px;
            height: 80px;
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid #00d4ff;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            color: #00d4ff;
            font-size: 38px;
            cursor: pointer;
            box-shadow: 0 0 25px rgba(0, 212, 255, 0.4);
            transition: 0.3s;
        }

        .icons-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-bottom: 25px;
            opacity: 0;
            transform: translateY(40px) scale(0.8);
            transition: 0.6s ease;
            pointer-events: none;
        }

        /* Animation Trigger */
        .active-window { transform: translateY(-120px) scale(0.85); opacity: 0.4; filter: blur(2px); }
        .active-icons { opacity: 1; transform: translateY(0) scale(1); pointer-events: auto; }

        .icon-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 12px 18px;
            border-radius: 12px;
            text-decoration: none;
            color: #fff;
            display: flex;
            align-items: center;
            gap: 12px;
            border: 1px solid rgba(0, 212, 255, 0.3);
            font-size: 14px;
        }
    </style>
</head>
<body>

    <div class="ocean"></div>
    <div class="whale"></div>

    <script>
        // Generating Bubbles
        for(let i=0; i<20; i++) {
            let b = document.createElement('div');
            b.className = 'bubble';
            let size = Math.random() * 15 + 5 + 'px';
            b.style.width = size; b.style.height = size;
            b.style.left = Math.random() * 100 + '%';
            b.style.animationDelay = Math.random() * 5 + 's';
            b.style.animationDuration = Math.random() * 5 + 5 + 's';
            document.body.appendChild(b);
        }
    </script>

    <div class="window" id="win">
        <div class="header">
            <div class="dot r"></div><div class="dot y"></div><div class="dot g"></div>
        </div>
        <div class="about-me">
            <span class="keyword">ABOUT</span> <span class="var">ME</span>:<br>
            &nbsp;&nbsp;Name = <span class="val">"Aaditya"</span><br>
            &nbsp;&nbsp;TG = <span class="val">"xeon_aaditya"</span><br>
            &nbsp;&nbsp;SKILL = [<span class="val">"AI"</span>, <span class="val">"Developer"</span>]<br>
            &nbsp;&nbsp;GOAL= <span class="val">"Next Gen Tech"</span><br><br>
            <span class="keyword">print</span>(<span class="val">"Unlock Social Matrix..."</span>)
        </div>
    </div>

    <div class="social-menu">
        <div class="icons-grid" id="iconBox">
            <a href="https://t.me/xeon_aaditya" class="icon-card"><i class="fab fa-telegram fa-lg" style="color: #00d4ff;"></i> Telegram</a>
            <a href="https://www.facebook.com/share/1CWS3FFYLw/" class="icon-card"><i class="fab fa-facebook fa-lg" style="color: #1877F2;"></i> Facebook</a>
            <a href="https://www.instagram.com/xeon__aaditya?igsh=MWo1djd0YnhqbDhxcA==" class="icon-card"><i class="fab fa-instagram fa-lg" style="color: #ff79c6;"></i> Instagram</a>
            <a href="https://github.com/mkun09203-ux" class="icon-card"><i class="fab fa-github fa-lg"></i> GitHub</a>
        </div>
        <div class="fingerprint" onclick="runMotion()">
            <i class="fas fa-fingerprint"></i>
        </div>
    </div>

    <script>
        function runMotion() {
            document.getElementById('win').classList.toggle('active-window');
            document.getElementById('iconBox').classList.toggle('active-icons');
        }
    </script>
</body>
</html>
