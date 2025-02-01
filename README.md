
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Get Well Soon Card</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(to right, #ffdde1, #ee9ca7);
            font-family: 'Arial', sans-serif;
            overflow: hidden;
            position: relative;
            animation: gradientShift 10s ease-in-out infinite; /* Dynamic gradient shift */
        }

        /* Background gradient shifting */
        @keyframes gradientShift {
            0% { background: linear-gradient(to right, #ffdde1, #ee9ca7); }
            50% { background: linear-gradient(to right, #ff9a8b, #ffb3c1); }
            100% { background: linear-gradient(to right, #ffdde1, #ee9ca7); }
        }

        /* Floating Hearts, Stars, and Band-aids Animation */
        .heart, .star, .bandage {
            position: absolute;
            font-size: 20px;
            opacity: 0.7;
            animation: floatUp 3s infinite linear;
        }

        .star {
            color: gold;
            font-size: 18px;
        }

        .bandage {
            color: #F4A300;
            font-size: 24px;
        }

        @keyframes floatUp {
            0% { transform: translateY(100vh) scale(0.8); opacity: 1; }
            100% { transform: translateY(-10vh) scale(1.2); opacity: 0; }
        }

        /* Notebook Card */
        .card-container {
            width: 90%;
            max-width: 450px;
            perspective: 1000px;
        }

        .card {
            width: 100%;
            height: 300px;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            transform-style: preserve-3d;
            transition: transform 1s ease-in-out;
            cursor: pointer;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2); /* Added depth */
        }

        .card:active {
            transform: rotateY(180deg); /* Flip on touch */
        }

        .page {
            width: 100%;
            height: 100%;
            position: absolute;
            backface-visibility: hidden;
            border-radius: 15px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            background: white;
            padding: 20px;
            text-align: center;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }

        /* Front Page */
        .front {
            background: #fff;
            border-left: 5px solid #d63384;
        }

        .front h2 {
            color: #d63384;
            font-size: 42px;
            font-family: 'Dancing Script', cursive;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2); /* Shadow effect */
        }

        /* Back Page (Notebook Effect) */
        .back {
            background: #fff;
            transform: rotateY(180deg);
            border-left: 5px solid #ffad60;
            position: relative;
            padding: 30px 20px;
        }

        .back::before {
            content: "";
            position: absolute;
            width: 100%;
            height: 100%;
            background-image: linear-gradient(to bottom, transparent 5px, rgba(0, 0, 0, 0.1) 6px);
            background-size: 100% 20px;
            top: 0;
            left: 0;
            pointer-events: none;
        }

        .back p {
            font-size: 20px;
            color: #444;
            font-style: italic;
            padding: 10px;
            line-height: 1.5;
        }

        /* Notebook Spiral */
        .spiral {
            position: absolute;
            width: 6px;
            height: 100%;
            background: #555;
            left: -3px;
            border-radius: 50%;
        }

        /* Touch Interaction Instructions */
        .instructions {
            position: absolute;
            bottom: 20px;
            font-size: 18px;
            color: white;
            background-color: rgba(0, 0, 0, 0.5);
            padding: 10px;
            border-radius: 10px;
        }

        /* Mobile Responsiveness */
        @media (max-width: 600px) {
            .card-container {
                width: 80%;
            }

            .card {
                height: 250px; 
            }

            .front h2 {
                font-size: 30px;
            }

            .back p {
                font-size: 18px; 
            }

            .instructions {
                font-size: 14px;
                bottom: 10px;
            }
        }

    </style>
</head>
<body>

    <div class="card-container">
        <div class="card">
            <!-- Front Page -->
            <div class="page front">
                <h2>Get Well Soon</h2>
            </div>

            <!-- Back Page (Notebook Effect) -->
            <div class="page back">
                <div class="spiral"></div>
                <p>Wishing you a super-speedy recovery filled with cozy rest, endless smiles, and all the care you deserve. 💖</p>
            </div>
        </div>
    </div>

    <!-- Instructions for Touch Screen Users -->
    <div class="instructions">
        Tap the card to flip it!
    </div>

    <!-- Floating Hearts, Stars, and Band-aids -->
    <script>
        function createHeart() {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "❤️";
            document.body.appendChild(heart);

            let randomLeft = Math.random() * window.innerWidth;
            heart.style.left = `${randomLeft}px`;

            let randomDuration = Math.random() * 2 + 2;
            heart.style.animationDuration = `${randomDuration}s`;

            setTimeout(() => {
                heart.remove();
            }, randomDuration * 1000);
        }

        function createStar() {
            const star = document.createElement("div");
            star.classList.add("star");
            star.innerHTML = "⭐";
            document.body.appendChild(star);

            let randomLeft = Math.random() * window.innerWidth;
            star.style.left = `${randomLeft}px`;

            let randomDuration = Math.random() * 3 + 3;
            star.style.animationDuration = `${randomDuration}s`;

            setTimeout(() => {
                star.remove();
            }, randomDuration * 1000);
        }

        function createBandage() {
            const bandage = document.createElement("div");
            bandage.classList.add("bandage");
            bandage.innerHTML = "🩹";
            document.body.appendChild(bandage);

            let randomLeft = Math.random() * window.innerWidth;
            bandage.style.left = `${randomLeft}px`;

            let randomDuration = Math.random() * 3 + 3;
            bandage.style.animationDuration = `${randomDuration}s`;

            setTimeout(() => {
                bandage.remove();
            }, randomDuration * 1000);
        }

        setInterval(createHeart, 300);
        setInterval(createStar, 500);
        setInterval(createBandage, 700);
    </script>

</body>
</html>
