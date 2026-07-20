<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Hamodi! 🐱🎮</title>
    <!-- خط بيكسلي يشبه ماينكرافت -->
    <link href="https://fonts.googleapis.com/css2?family=VT323&family=Press+Start+2P&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Press Start 2P', 'Segoe UI', cursive, sans-serif;
            background: #2d132c;
            background-image: 
                radial-gradient(#801336 15%, transparent 16%),
                radial-gradient(#ee4540 15%, transparent 16%);
            background-size: 60px 60px;
            background-position: 0 0, 30px 30px;
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            text-align: center;
            overflow: hidden;
            position: relative;
        }

        /* كارت ماينكرافت الخشبي مع حواف البيكسل */
        .card {
            background: #5c3d2e;
            border: 8px solid #2b1704;
            outline: 6px solid #8b5a2b;
            padding: 35px 20px;
            border-radius: 4px;
            box-shadow: 0 20px 0 #120a02, inset 0 0 20px rgba(0,0,0,0.6);
            max-width: 90%;
            width: 380px;
            z-index: 10;
            position: relative;
        }

        .cat-pixel {
            font-size: 3.8rem;
            margin-bottom: 15px;
            display: inline-block;
            filter: drop-shadow(4px 4px 0px #000);
            animation: pixelHop 1s infinite alternate steps(2);
        }

        @keyframes pixelHop {
            0% { transform: translateY(0); }
            100% { transform: translateY(-12px); }
        }

        h1 {
            font-size: 1.2rem;
            color: #ffcc00;
            margin-bottom: 20px;
            text-shadow: 3px 3px 0px #000;
            line-height: 1.6;
        }

        p {
            font-size: 0.75rem;
            color: #ffffff;
            line-height: 1.8;
            margin-bottom: 25px;
            text-shadow: 2px 2px 0px #000;
            background: rgba(0,0,0,0.3);
            padding: 15px;
            border: 4px solid #3d2314;
        }

        /* زر بستايل ماينكرافت */
        .music-btn {
            font-family: 'Press Start 2P', cursive, sans-serif;
            background: #55ff55;
            color: #000;
            border: 4px solid #00aa00;
            border-bottom: 8px solid #006600;
            padding: 15px 10px;
            font-size: 0.7rem;
            font-weight: bold;
            cursor: pointer;
            text-shadow: none;
            transition: all 0.1s;
            width: 100%;
        }

        .music-btn:active {
            border-bottom: 4px solid #006600;
            transform: translateY(4px);
        }

        /* قطط وقلوب بيكسل متساقطة */
        .pixel-rain {
            position: fixed;
            top: -10vh;
            font-size: 2rem;
            user-select: none;
            pointer-events: none;
            z-index: 1;
            animation: fall linear forwards;
            filter: drop-shadow(2px 2px 0px #000);
        }

        @keyframes fall {
            0% {
                transform: translateY(0);
                opacity: 1;
            }
            100% {
                transform: translateY(105vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <div class="card">
        <div class="cat-pixel">🐱🎂🐱</div>
        <h1>HAPPY BIRTHDAY HAMODI! 🎉</h1>
        <p>كل عام وأنت بخير حمودي! سنة جديدة مليانة مغامرات ونجاحات يا رب ✨🎮</p>
        
        <button class="music-btn" onclick="playMusic()">▶ PRESS TO PLAY MUSIC 🎵</button>
        
        <audio id="birthdaySong" loop>
            <source src="song.mp3" type="audio/mpeg">
            متصفحك لا يدعم تشغيل الصوت.
        </audio>
    </div>

    <script>
        function playMusic() {
            var audio = document.getElementById("birthdaySong");
            var btn = document.querySelector(".music-btn");
            
            if (audio.paused) {
                audio.play();
                btn.innerHTML = "⏸ PAUSE MUSIC";
                btn.style.background = "#ff5555";
                btn.style.borderColor = "#aa0000";
                btn.style.borderBottomColor = "#660000";
            } else {
                audio.pause();
                btn.innerHTML = "▶ PRESS TO PLAY MUSIC 🎵";
                btn.style.background = "#55ff55";
                btn.style.borderColor = "#00aa00";
                btn.style.borderBottomColor = "#006600";
            }
        }

        // إطلاق عناصر بيكسلي كيوت (قطط، سمك، قلوب بيكسل)
        function createPixelItem() {
            const item = document.createElement('div');
            item.classList.add('pixel-rain');
            
            // أيقونات قطط وجيمينج بستايل البيكسل
            const items = ['🐱', '😸', '🐟', '💖', '🧁', '🎮', '🐾', '✨'];
            item.innerText = items[Math.floor(Math.random() * items.length)];
            
            item.style.left = Math.random() * 100 + "vw";
            item.style.animationDuration = Math.random() * 3 + 3 + "s";
            
            document.body.appendChild(item);
            
            setTimeout(() => {
                item.remove();
            }, 6000);
        }

        setInterval(createPixelItem, 300);
    </script>

</body>
</html>
