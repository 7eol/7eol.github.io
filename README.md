<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Page</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            overflow: hidden;
        }

        #background-video {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: -2;
        }

        #overlay-message {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2rem;
            cursor: pointer;
            z-index: 1;
        }

        #content {
            display: none;
            opacity: 0;
            transition: opacity 0.5s ease;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20%;
        }

        .button a {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, #ff0000, #ff7300);
            text-decoration: none;
            color: white;
            font-size: 1.5rem;
            box-shadow: 0 0 15px rgba(255, 0, 0, 0.7);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .button a:hover {
            transform: scale(1.2);
            box-shadow: 0 0 25px rgba(255, 0, 0, 1);
        }

        .volume-button {
            position: fixed;
            top: 20px;
            left: 20px;
            display: flex;
            align-items: center;
            z-index: 10;
        }

        .volume-slider-container {
            display: none;
            margin-left: 10px;
        }

        .volume-slider {
            width: 100px;
        }

        .volume-button:hover .volume-slider-container {
            display: block;
        }

        #volume-icon {
            cursor: pointer;
            width: 30px;
            height: 30px;
        }
    </style>
</head>
<body>
    <video id="background-video" autoplay loop muted>
        <source src="background.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <audio id="background-audio" loop>
        <source src="background.mp3" type="audio/mp3">
        Your browser does not support the audio element.
    </audio>
    <div id="overlay-message">Click anywhere to enter</div>
    <div id="content">
        <div class="buttons">
            <div class="button">
                <a target="_blank" href="https://youtube.com/@7eyesofluck">
                    <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="1.99 5 20.01 14.01">
                        <path fill="currentColor" d="M21.593 7.203a2.506 2.506 0 0 0-1.762-1.766C18.265 5.007 12 5 12 5s-6.264-.007-7.831.404a2.56 2.56 0 0 0-1.766 1.778c-.413 1.566-.417 4.814-.417 4.814s-.004 3.264.406 4.814c.23.857.905 1.534 1.763 1.765c1.582.43 7.83.437 7.83.437s6.265.007 7.831-.403a2.515 2.515 0 0 0 1.767-1.763c.414-1.565.417-4.812.417-4.812s.02-3.265-.407-4.831zM9.996 15.005l.005-6l5.207 3.005l-5.212 2.995z"></path>
                    </svg>
                </a>
            </div>
            <div class="button">
                <a target="_blank" href="https://tiktok.com/@7eyesofluck">
                    <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="3.2 2 17.43 19.99">
                        <path fill="currentColor" d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.2 1.74a2.89 2.89 0 0 1 2.31-4.64a2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.05A6.33 6.33 0 0 0 5 20.1a6.34 6.34 0 0 0 10.86-4.43v-7a8.16 8.16 0 0 0 4.77 1.52v-3.4a4.85 4.85 0 0 1-1-.1z"></path>
                    </svg>
                </a>
            </div>
            <div class="button">
                <a target="_blank" href="https://steamcommunity.com/id/7eol">
                    <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="2 2 19.97 20">
                        <path fill="currentColor" d="M8.21 17.32L7 16.8a2.13 2.13 0 1 0 1.17-2.93l1.28.53a1.58 1.58 0 0 1-1.22 2.92z"></path>
                        <path fill="currentColor" d="M12 2a10 10 0 0 0-10 9.34l5.38 2.21a2.31 2.31 0 0 1 .47-.24A2.62 2.62 0 0 1 9 13.1l2.44-3.56a3.8 3.8 0 1 1 3.8 3.8h-.08l-3.51 2.5a2.77 2.77 0 0 1-5.47.68l-3.77-1.6A10 10 0 1 0 12 2z"></path>
                        <path fill="currentColor" d="M17.79 9.5a2.53 2.53 0 1 0-2.53 2.5a2.54 2.54 0 0 0 2.53-2.5zm-4.42 0a1.9 1.9 0 1 1 1.9 1.91a1.9 1.9 0 0 1-1.9-1.92z"></path>
                    </svg>
                </a>
            </div>
            <div class="button">
                <a target="_blank" href="https://github.com/7eol">
                    <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="2.05 2 19.95 19.46">
                        <path fill="currentColor" d="M12.026 2c-5.509 0-9.974 4.465-9.974 9.974c0 4.406 2.857 8.145 6.821 9.465c.499.09.679-.217.679-.481c0-.237-.008-.865-.011-1.696c-2.775.602-3.361-1.338-3.361-1.338c-.452-1.152-1.107-1.459-1.107-1.459c-.905-.619.069-.605.069-.605c1.002.07 1.527 1.028 1.527 1.028c.89 1.524 2.336 1.084 2.902.829c.091-.645.351-1.085.635-1.334c-2.214-.251-4.542-1.107-4.542-4.93c0-1.087.389-1.979 1.024-2.675c-.101-.253-.446-1.268.099-2.64c0 0 .837-.269 2.742 1.021a9.582 9.582 0 0 1 2.496-.336a9.554 9.554 0 0 1 2.496.336c1.906-1.291 2.742-1.021 2.742-1.021c.545 1.372.203 2.387.099 2.64c.64.696 1.024 1.587 1.024 2.675c0 3.833-2.33 4.675-4.552 4.922c.355.308.675.916.675 1.846c0 1.334-.012 2.41-.012 2.737c0 .267.178.577.687.479C19.146 20.115 22 16.379 22 11.974C22 6.465 17.535 2 12.026 2z" clip-rule="evenodd"></path>
                    </svg>
                </a>
            </div>
            <div class="button">
                <a target="_blank" href="https://roblox.com/users/938926711">
                    <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="0.16 0 23.68 24">
                        <path fill="currentColor" d="M5.164 0L.16 18.928L18.836 24L23.84 5.072Zm8.747 15.354l-5.219-1.417l1.399-5.29l5.22 1.418l-1.4 5.29z"></path>
                    </svg>
                </a>
            </div>
        </div>
    </div>
    <div class="volume-button">
        <img id="volume-icon" src="volume-icon.png" alt="Volume">
        <div class="volume-slider-container">
            <input id="volume-slider" class="volume-slider" type="range" min="0" max="1" step="0.01">
        </div>
    </div>
    <script>
        const overlayMessage = document.getElementById('overlay-message');
        const content = document.getElementById('content');
        const backgroundAudio = document.getElementById('background-audio');
        overlayMessage.addEventListener('click', () => {
            overlayMessage.style.display = 'none';
            content.style.display = 'block';
            setTimeout(() => content.style.opacity = '1', 10);
            backgroundAudio.play();
        });

        const volumeSlider = document.getElementById('volume-slider');
        const volumeIcon = document.getElementById('volume-icon');
        volumeSlider.addEventListener('input', () => {
            backgroundAudio.volume = volumeSlider.value;
        });

        volumeIcon.addEventListener('click', () => {
            backgroundAudio.muted = !backgroundAudio.muted;
            volumeIcon.src = backgroundAudio.muted ? 'mute-icon.png' : 'volume-icon.png';
        });
    </script>
</body>
</html>
