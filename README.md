<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Hamodi! 💖✨</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #2b1055, #7597de, #ff758c, #ff7eb3);
            background-size: 400% 400%;
            animation: gradientBG 12s ease infinite;
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            text-align: center;
            overflow: hidden;
            position: relative;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* كارد التهنئة الزجاجي الكيوت */
        .card {
            background: rgba(255, 255, 255, 0.18);
            padding: 40px 25px;
            border-radius: 30px;
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
            backdrop-filter: blur(14px);
            -webkit-backdrop-filter: blur(14px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            max-width: 90%;
            width: 360px;
            z-index: 10;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .icon {
            font-size: 4.5rem;
            margin-bottom: 15px;
            display: inline-block;
            filter: drop-shadow(0 0 12px rgba(255,182,193,0.9));
        }

        h1 {
            font-size: 2.1rem;
            color: #fff;
            margin-bottom: 15px;
            text-shadow: 0 0 15px rgba(255, 105, 180, 0.9);
            font-weight: 800;
        }

        p {
            font-size: 1.15rem;
            color: #fce4ec;
            line-height: 1.7;
            margin-bottom: 30px;
            text-shadow: 0 1px 3px rgba(0,0,0,0.3);
        }

        /* زر تشغيل الأغنية */
        .music-btn {
            background: linear-gradient(45deg, #ff758c, #ff7eb3);
            color: white;
            border: none;
            padding: 16px 32px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 10px 20px rgba(255, 117, 140, 0.5);
            transition: all 0.3s ease;
            outline: none;
        }

        .music-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 25px rgba(255, 117, 140, 0.7);
        }

        .music-btn:active {
            transform: scale(0.95);
        }

        /* تأثير القلوب والورود العائمة */
        .heart {
            position: fixed;
            top: -10vh;
            font-size: 1.5rem;
            user-select: none;
            pointer-events: none;
            z-index: 1;
            animation: fall linear forwards;
        }

        @keyframes fall {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(105vh) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <div class="card">
        <div class="icon">🎂✨</div>
        <h1>كل عام وأنت بخير حمودي! 💖</h1>
        <p>أتمنى لك سنة جديدة مليانة نجاح وسعادة وتحقيق لكل أحلامك يا رب 🌸✨</p>
        
        <button class="music-btn" onclick="playMusic()">اضغط هنا لتشغيل الأغنية 🎵</button>
        
        <audio id="birthdaySong" loop>
            <source src="song.mp3" type="audio/mpeg">
            متصفحك لا يدعم تشغيل الصوت.
        </audio>
    </div>

    <script>
        // تشغيل وإيقاف الأغنية
        function playMusic() {
            var audio = document.getElementById("birthdaySong");
            var btn = document.querySelector(".music-btn");
            
            if (audio.paused) {
                audio.play();
                btn.innerHTML = "إيقاف الأغنية ⏸️";
                btn.style.background = "linear-gradient(45deg, #42e695, #3bb2b8)";
            } else {
                audio.pause();
                btn.innerHTML = "تشغيل الأغنية 🎵";
                btn.style.background = "linear-gradient(45deg, #ff758c, #ff7eb3)";
            }
        }

        // كود القلوب والورود المتساقطة والعائمة
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            
            const shapes = ['💖', '🌸', '💕', '✨', '🌷', '💗', '🎈'];
            heart.innerText = shapes[Math.floor(Math.random() * shapes.length)];
            
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration = Math.random() * 3 + 2 + "s";
            heart.style.fontSize = Math.random() * 1.5 + 1 + "rem";
            
            document.body.appendChild(heart);
            
            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        setInterval(createHeart, 250);
    </script>

</body>
</html>
