<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Merry Christmas!</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap');

        body {
            background-color: #000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: #fff;
            font-family: 'Arial', sans-serif;
            overflow: hidden;
        }
        .tree {
            font-size: 10em; /* 放大表情符號 */
            text-align: center;
            margin-bottom: 20px;
            animation: twinkle 1s infinite alternate;
        }
        .message {
            font-size: 3em;
            color: #ff6347;
            margin-top: 20px;
            text-align: center;
            font-family: 'Great Vibes', cursive;
        }
        .stars {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
        }
        .star {
            position: absolute;
            color: #fff;
            animation: twinkle 2s infinite alternate;
        }
        @keyframes twinkle {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.5;
            }
        }
        .fireworks {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
        }
        .firework {
            position: absolute;
            bottom: 0;
            width: 3px;
            height: 50px;
            background-color: #fff;
            animation: explode 1s infinite alternate;
        }
        @keyframes explode {
            0% {
                transform: scaleY(1);
                opacity: 1;
            }
            100% {
                transform: scaleY(0);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="tree">🎄</div>
    <div class="message">Merry Christmas!</div>
    <div class="stars"></div>
    <div class="fireworks"></div>
    <script>
        // 星星產生功能
        function createStar() {
            const star = document.createElement('div');
            star.classList.add('star');
            star.textContent = '⭐';
            star.style.left = Math.random() * 100 + 'vw';
            star.style.top = Math.random() * 100 + 'vh';
            star.style.fontSize = Math.random() * 2 + 'em'; // 星星大小隨機
            document.querySelector('.stars').appendChild(star);
        }

        setInterval(createStar, 500); // 每500毫秒產生一顆星星

        // 煙花產生功能
        function createFirework() {
            const firework = document.createElement('div');
            firework.classList.add('firework');
            firework.style.left = Math.random() * 100 + 'vw';
            firework.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 50%)`;
            document.querySelector('.fireworks').appendChild(firework);
        }

        setInterval(createFirework, 300); // 每300毫秒產生一個煙花
    </script>
</body>
</html>
