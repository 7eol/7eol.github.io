<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biolink Test</title>
    <style>
        @font-face {
            font-family: 'TT Norms Pro Regular';
            src: url('TT Norms Pro Regular.woff') format('woff');
            font-weight: normal;
            font-style: normal;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'TT Norms Pro Regular', sans-serif;
            height: 100vh;
            overflow: hidden;
            background: black;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }

        .background-video {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: -1;
            filter: blur(10px);
            pointer-events: none;
        }

        .overlay-message {
            font-size: 2rem;
            text-align: center;
            cursor: pointer;
            z-index: 1;
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .content {
            display: none;
            opacity: 0;
            transition: opacity 1s ease;
            text-align: center;
            z-index: 2;
        }

        .profile-container img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin-bottom: 20px;
        }

        .profile-container h1 {
            font-size: 2rem;
            margin-bottom: 15px;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 10px;
        }

        .button {
            width: 30px;
            height: 30px;
            cursor: pointer;
            transition: transform 0.3s ease, filter 0.3s ease;
            display: inline-flex;
            justify-content: center;
            align-items: center;
            filter: drop-shadow(0 0 0px lightgray);
        }

        .button svg {
            width: 35px;
            height: 35px;
            fill: lightgray;
        }

        .button:hover {
            transform: scale(1.1);
            filter: drop-shadow(0 0 10px lightgray);
        }

        .volume-button {
            position: fixed;
            top: 10px;
            left: 10px;
            cursor: pointer;
            z-index: 3;
            width: 40px;
            height: 40px;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            transition: width 0.3s ease;
        }

        .volume-button:hover {
            width: 120px; /* Expands to the right */
        }

        .volume-slider-container {
            position: absolute;
            top: 0;
            left: 40px;
            width: 80px;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease;
        }

        .volume-button:hover .volume-slider-container {
            opacity: 1;
            pointer-events: auto;
        }

        .volume-slider {
            width: 100%;
        }
    </style>
</head>
<body>
    <video class="background-video" id="background-video" muted loop>
        <source src="backgroundvideo.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

    <div class="overlay-message" id="overlay-message">
        Click anywhere to enter
    </div>

    <audio id="background-audio" loop>
        <source src="backgroundaudio.mp3" type="audio/mp3">
        Your browser does not support the audio tag.
    </audio>

    <div class="content" id="content">
        <div class="profile-container">
            <img id="profile-img" src="pfp.gif" alt="Profile Picture">
            <h1>7</h1>
            <div class="buttons">
                <div class="button">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zM17 16.59L15.59 18 12 14.41 8.41 18 7 16.59 10.59 13 7 9.41 8.41 8 12 11.59 15.59 8 17 9.41 13.41 13 17 16.59z"></path>
                    </svg>
                </div>
                <div class="button">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M3 9v6h3l4 4V5L6 9H3zm15 6c0-.55-.45-1-1-1h-2v2h2c.55 0 1-.45 1-1z"></path>
                    </svg>
                </div>
            </div>
        </div>
    </div>

    <div class="volume-button" id="volume-button">
        <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="0 0 24 24">
            <path fill="currentColor" d="M3 9v6h3l4 4V5L6 9H3zm15 6c0-.55-.45-1-1-1h-2v2h2c.55 0 1-.45 1-1z"></path>
        </svg>
        <div class="volume-slider-container">
            <input type="range" class="volume-slider" min="0" max="1" step="0.01" value="0.5">
        </div>
    </div>

    <script>
        const overlayMessage = document.getElementById('overlay-message');
        const content = document.getElementById('content');
        const backgroundVideo = document.getElementById('background-video');
        const backgroundAudio = document.getElementById('background-audio');
        const volumeSlider = document.querySelector('.volume-slider');

        // Handle click to enter
        overlayMessage.addEventListener('click', () => {
            overlayMessage.style.display = 'none';
            content.style.display = 'block';
            setTimeout(() => {
                content.style.opacity = 1;
            }, 0);

            // Play video and audio
            backgroundVideo.play();
            backgroundAudio.play();
        });

        // Adjust audio volume
        volumeSlider.addEventListener('input', (event) => {
            backgroundAudio.volume = event.target.value;
        });
    </script>
</body>
</html>
