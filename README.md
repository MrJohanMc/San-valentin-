# San-valentin-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi San Valentín?</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #ffe4e1;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: #333;
        }

        .container {
            text-align: center;
            position: relative;
        }

        .hearts {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
            top: 0;
            left: 0;
            z-index: -1;
        }

        .heart {
            width: 20px;
            height: 20px;
            background: pink;
            position: absolute;
            animation: float 4s infinite ease-in-out;
            transform: rotate(45deg);
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(45deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-10vh) rotate(45deg);
                opacity: 0;
            }
        }

        .heart:before, .heart:after {
            content: '';
            width: 20px;
            height: 20px;
            background: pink;
            position: absolute;
            border-radius: 50%;
        }

        .heart:before {
            top: -10px;
            left: 0;
        }

        .heart:after {
            left: 10px;
            top: 0;
        }

        h1 {
            color: #ff1493;
            margin-bottom: 20px;
        }

        .message {
            font-size: 1.2rem;
            margin-bottom: 30px;
            color: #444;
        }

        .image-container {
            margin: 20px auto;
        }

        img {
            width: 200px;
            height: 200px;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid #ff1493;
        }

        .buttons {
            margin-top: 20px;
        }

        button {
            padding: 10px 20px;
            font-size: 1rem;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            margin: 5px;
            transition: transform 0.2s;
        }

        button:hover {
            transform: scale(1.1);
        }

        .yes {
            background-color: #ff69b4;
            color: #fff;
        }

        .no {
            background-color: #ddd;
            color: #444;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="hearts"></div>
        <h1>¿Quieres ser mi San Valentín?</h1>
        <p class="message">Gracias por hacerme compañía, armarme y llegar a mi vida. Después de todo esto, ¿quieres ser mi San Valentín?</p>
        <div class="image-container">
            <img src="IMG_0379.png" alt="Tu foto" />
        </div>
        <div class="buttons">
            <button class="yes" onclick="sendResponse('yes')">Sí</button>
            <button class="no" onclick="sendResponse('no')">No</button>
        </div>
    </div>

    <audio autoplay loop>
        <source src="barro.mp3" type="audio/mpeg">
        Tu navegador no soporta la reproducción de audio.
    </audio>

    <script>
        const heartsContainer = document.querySelector('.hearts');

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 2 + 3 + 's';
            heartsContainer.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        setInterval(createHeart, 300);

        function sendResponse(response) {
            if (response === 'yes') {
                alert('¡Ella aceptó ser tu San Valentín! ❤️');
                // Aquí podrías agregar funcionalidad para enviar un correo o notificación.
            } else {
                alert('¡Oh no! Lo siento 😔');
            }
        }
    </script>
</body>
</html>
