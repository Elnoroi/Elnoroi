<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Monicah Fireworks</title>
    <style>
        body {
            margin: 0;
            background-color: black;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            font-family: Arial, sans-serif;
            color: white;
            text-align: center;
        }

        #container {
            position: relative;
        }

        h1, h2 {
            margin: 0;
            animation: colorChange 2s infinite alternate;
        }

        @keyframes colorChange {
            0% { color: #ff0000; }
            25% { color: #ff9f00; }
            50% { color: #00ff00; }
            75% { color: #0099ff; }
            100% { color: #ff00ff; }
        }

        .firework {
            position: absolute;
            width: 4px;
            height: 4px;
            background: radial-gradient(circle, #fff, transparent);
            border-radius: 50%;
            animation: explode 1.5s ease-out forwards;
        }

        @keyframes explode {
            0% { transform: scale(0.5); opacity: 1; }
            100% { transform: scale(4); opacity: 0; }
        }
    </style>
</head>
<body>
    <div id="container">
        <h1>Monicah</h1>
        <h2>gomd</h2>
    </div>

    <script>
        function createFirework(x, y) {
            const firework = document.createElement('div');
            firework.classList.add('firework');
            firework.style.top = `${y}px`;
            firework.style.left = `${x}px`;

            document.body.appendChild(firework);

            setTimeout(() => {
                firework.remove();
            }, 1500);
        }

        setInterval(() => {
            const x = Math.random() * window.innerWidth;
            const y = Math.random() * window.innerHeight;
            createFirework(x, y);
        }, 300);
    </script>
</body>
</html>- 
