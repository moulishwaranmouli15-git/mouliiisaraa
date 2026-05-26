<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MS Premium Heart</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            height: 100vh;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            background:
                radial-gradient(circle at top, #2b0018, #000000 75%);
            perspective: 1500px;
            font-family: 'Poppins', sans-serif;
        }


        body::before {
            content: "";
            position: absolute;
            width: 700px;
            height: 700px;
            background: radial-gradient(circle, #ff4d8860, transparent 70%);
            animation: bgGlow 5s infinite alternate;
        }



        .stars {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        .star {
            position: absolute;
            color: white;
            opacity: 0.8;
            animation:
                twinkle 2s infinite alternate,
                floatingStars 6s infinite ease-in-out;
        }


        .star:nth-child(1) {
            top: 8%;
            left: 15%;
            font-size: 14px;
        }

        .star:nth-child(2) {
            top: 18%;
            left: 75%;
            font-size: 18px;
        }

        .star:nth-child(3) {
            top: 72%;
            left: 25%;
            font-size: 16px;
        }

        .star:nth-child(4) {
            top: 55%;
            left: 88%;
            font-size: 12px;
        }

        .star:nth-child(5) {
            top: 14%;
            left: 48%;
            font-size: 20px;
        }

        .star:nth-child(6) {
            top: 80%;
            left: 12%;
            font-size: 14px;
        }

        .star:nth-child(7) {
            top: 42%;
            left: 35%;
            font-size: 16px;
        }

        .star:nth-child(8) {
            top: 10%;
            left: 90%;
            font-size: 14px;
        }

        .star:nth-child(9) {
            top: 88%;
            left: 62%;
            font-size: 18px;
        }

        .star:nth-child(10) {
            top: 35%;
            left: 5%;
            font-size: 12px;
        }



        .container {
            position: relative;
            animation: floatHeart 4s ease-in-out infinite;
        }



        svg {
            width: 340px;
            opacity: 0;

            filter:
                drop-shadow(0 0 25px #ff4d88) drop-shadow(0 0 50px #ff4d88) drop-shadow(0 0 90px #ff99bb);

            animation:
                heartEntry 2s forwards,
                heartbeat 1.2s infinite 2s,
                rotateHeart 6s infinite alternate ease-in-out 2s;
        }



        .name {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);

            color: white;
            font-size: 65px;
            font-family: cursive;
            font-weight: bold;
            letter-spacing: 5px;

            text-shadow:
                0 0 10px white,
                0 0 20px #ff4d88,
                0 0 40px #ff4d88,
                0 0 70px #ff99bb;

            animation: msGlow 1s infinite alternate;
        }



        .love-text {

            position: absolute;

            left: 50%;
            bottom: -110px;

            transform: translateX(-50%);

            width: 100%;

            text-align: center;

            color: white;

            font-size: 30px;

            font-family: cursive;

            letter-spacing: 3px;

            text-shadow:
                0 0 10px #ff4d88,
                0 0 20px #ff4d88,
                0 0 40px #ff99bb;

            animation: loveGlow 2s infinite alternate;
        }



        .side-text {

            position: absolute;

            right: -300px;
            top: 50%;

            transform: translateY(-50%);

            width: 250px;

            color: white;

            font-size: 28px;

            font-family: cursive;

            text-align: left;

            line-height: 45px;

            letter-spacing: 2px;

            text-shadow:
                0 0 10px #ff4d88,
                0 0 20px #ff4d88,
                0 0 40px #ff99bb;

            animation: sideGlow 2s infinite alternate;
        }



        .small-heart {
            position: absolute;
            color: #ff7aa8;
            font-size: 22px;
            opacity: 0;
            animation: flyHeart 6s linear infinite;
        }

        .small-heart:nth-child(1) {
            left: -80px;
            top: 50%;
            animation-delay: 0s;
        }

        .small-heart:nth-child(2) {
            right: -80px;
            top: 35%;
            animation-delay: 2s;
        }

        .small-heart:nth-child(3) {
            left: 45%;
            bottom: -70px;
            animation-delay: 4s;
        }



        .sparkle {
            position: absolute;
            width: 8px;
            height: 8px;
            background: white;
            border-radius: 50%;
            box-shadow: 0 0 10px white;
            animation: sparkleAnim 3s infinite;
        }

        .sparkle:nth-child(1) {
            top: 20%;
            left: 15%;
        }

        .sparkle:nth-child(2) {
            top: 30%;
            right: 15%;
        }

        .sparkle:nth-child(3) {
            bottom: 20%;
            left: 30%;
        }

        .sparkle:nth-child(4) {
            bottom: 25%;
            right: 25%;
        }



        @keyframes heartEntry {

            0% {
                opacity: 0;
                transform:
                    scale(0) rotate(-40deg);
            }

            100% {
                opacity: 1;
                transform:
                    scale(1) rotate(0deg);
            }
        }

        @keyframes heartbeat {

            0% {
                transform: scale(1);
            }

            25% {
                transform: scale(1.15);
            }

            50% {
                transform: scale(1);
            }

            75% {
                transform: scale(1.15);
            }

            100% {
                transform: scale(1);
            }
        }

        @keyframes rotateHeart {

            0% {
                transform:
                    rotateY(-18deg) rotateX(5deg);
            }

            50% {
                transform:
                    rotateY(18deg) rotateX(-5deg);
            }

            100% {
                transform:
                    rotateY(-18deg) rotateX(5deg);
            }
        }

        @keyframes floatHeart {

            0% {
                transform: translateY(0px);
            }

            50% {
                transform: translateY(-18px);
            }

            100% {
                transform: translateY(0px);
            }
        }

        @keyframes msGlow {

            from {
                opacity: 0.7;
                transform:
                    translate(-50%, -50%) scale(1);
            }

            to {
                opacity: 1;
                transform:
                    translate(-50%, -50%) scale(1.12);
            }
        }

        @keyframes loveGlow {

            from {
                opacity: 0.6;
                transform:
                    translateX(-50%) scale(1);
            }

            to {
                opacity: 1;
                transform:
                    translateX(-50%) scale(1.08);
            }
        }

        @keyframes sideGlow {

            from {
                opacity: 0.6;
                transform:
                    translateY(-50%) translateX(0px);
            }

            to {
                opacity: 1;
                transform:
                    translateY(-50%) translateX(10px);
            }
        }

        @keyframes twinkle {

            from {
                opacity: 0.2;
                transform: scale(1);
            }

            to {
                opacity: 1;
                transform: scale(1.8);
            }
        }

        @keyframes floatingStars {

            0% {
                transform: translateY(0px);
            }

            50% {
                transform: translateY(-10px);
            }

            100% {
                transform: translateY(0px);
            }
        }

        @keyframes flyHeart {

            0% {
                transform:
                    translateY(0px) scale(0.5);
                opacity: 0;
            }

            40% {
                opacity: 1;
            }

            100% {
                transform:
                    translateY(-260px) scale(1.5);
                opacity: 0;
            }
        }

        @keyframes sparkleAnim {

            0% {
                opacity: 0.2;
                transform: scale(1);
            }

            50% {
                opacity: 1;
                transform: scale(2);
            }

            100% {
                opacity: 0.2;
                transform: scale(1);
            }
        }

        @keyframes bgGlow {

            from {
                transform: scale(1);
                opacity: 0.5;
            }

            to {
                transform: scale(1.1);
                opacity: 1;
            }
        }
    </style>
</head>

<body>


    <div class="stars">

        <div class="star">✦</div>
        <div class="star">✧</div>
        <div class="star">✦</div>
        <div class="star">✧</div>
        <div class="star">✦</div>
        <div class="star">✧</div>
        <div class="star">✦</div>
        <div class="star">✧</div>
        <div class="star">✦</div>
        <div class="star">✧</div>

    </div>



    <div class="container">



        <div class="small-heart">❤</div>
        <div class="small-heart">❤</div>
        <div class="small-heart">❤</div>



        <div class="sparkle"></div>
        <div class="sparkle"></div>
        <div class="sparkle"></div>
        <div class="sparkle"></div>



        <svg viewBox="0 0 600 552">

            <path
                d="M300,107.77C284.68,55.67,239.76,0,162.31,0,64.83,0,0,82.08,0,171.71c0,.48,0,.95,0,1.43-.52,19.5,0,217.94,299.87,379.69v0l0,0,.05,0,0,0,0,0v0C600,391.08,600.48,192.64,600,173.14c0-.48,0-.95,0-1.43C600,82.08,535.17,0,437.69,0,360.24,0,315.32,55.67,300,107.77"
                fill="#ff4d88" />

        </svg>



        <div class="name">MS</div>



        <div class="love-text">
            ✨💖 You Are My Everything To Me 💖✨
        </div>



        <div class="side-text">
            💖 I Am Always With You 💖
        </div>

    </div>

</body>

</html>
