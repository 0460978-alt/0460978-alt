

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My GitHub Website</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #000;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            font-family: sans-serif;
        }
        
        /* Container to handle the true browser fullscreen mode */
        #game-container {
            width: 100%;
            height: 100%;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #000;
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Floating Fullscreen Button Style */
        .fullscreen-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            padding: 10px 15px;
            background-color: rgba(0, 0, 0, 0.7);
            color: #fff;
            border: 2px solid #fff;
            border-radius: 5px;
            cursor: pointer;
            font-size: 14px;
            font-weight: bold;
            z-index: 9999;
            transition: background 0.2s, transform 0.1s;
        }

        .fullscreen-btn:hover {
            background-color: #fff;
            color: #000;
        }

        .fullscreen-btn:active {
            transform: scale(0.95);
        }
    </style>
</head>
<body>

    <div id="game-container">
        <!-- Floating overlay button -->
        <button class="fullscreen-btn" onclick="toggleFullscreen()">Go Fullscreen</button>
        
        <!-- The Embedded Game -->
        <iframe id="game-frame" src="https://garbsoftball.com" allowfullscreen></iframe>
    </div>

    <script>
        function toggleFullscreen() {
            var container = document.getElementById("game-container");
            
            if (!document.fullscreenElement) {
                // Request full hardware screen mode
                if (container.requestFullscreen) {
                    container.requestFullscreen();
                } else if (container.webkitRequestFullscreen) { /* Safari support */
                    container.webkitRequestFullscreen();
                } else if (container.msRequestFullscreen) { /* IE11 support */
                    container.msRequestFullscreen();
                }
            } else {
                // Exit fullscreen if already in it
                if (document.exitFullscreen) {
                    document.exitFullscreen();
                }
            }
        }
    </script>

</body>
</html>
