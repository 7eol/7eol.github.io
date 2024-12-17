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
            transition: filter 1s ease-in-out;
        }

        .overlay-message {
            font-size: 2rem;
            text-align: center;
            cursor: pointer;
            z-index: 1;
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
            gap: 20px;
        }

        .button {
            width: 50px;
            height: 50px;
            position: relative;
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .button a {
            display: inline-block;
            width: 100%;
            height: 100%;
            text-decoration: none;
            color: inherit;
        }

        .button svg {
            width: 35px;
            height: 35px;
            fill: white;
        }

        .button::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            box-shadow: 0 0 15px rgba(255, 255, 255, 0.5);
            opacity: 0.7;
            transition: opacity 0.3s ease, box-shadow 0.3s ease;
        }

        .button:hover::before {
            box-shadow: 0 0 30px rgba(255, 255, 255, 0.8);
            opacity: 1;
        }

        .volume-button {
            position: fixed;
            top: 10px;
            left: 10px;
            cursor: pointer;
            z-index: 3;
        }

        .volume-slider-container {
            position: fixed;
            top: 70px;
            left: 10px;
            display: none;
            background: rgba(0, 0, 0, 0.7);
            padding: 10px;
            border-radius: 5px;
        }

        .volume-slider {
            width: 100px;
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
                    <a target="_blank" href="https://youtube.com/@7eyesofluck">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="1.99 5 20.01 14.01">
                            <path d="M21.593 7.203a2.506 2.506 0 0 0-1.762-1.766C18.265 5.007 12 5 12 5s-6.264-.007-7.831.404a2.56 2.56 0 0 0-1.766 1.778c-.413 1.566-.417 4.814-.417 4.814s-.004 3.264.406 4.814c.23.857.905 1.534 1.763 1.765c1.582.43 7.83.437 7.83.437s6.265.007 7.831-.403a2.515 2.515 0 0 0 1.767-1.763c.414-1.565.417-4.812.417-4.812s.02-3.265-.407-4.831zM9.996 15.005l.005-6l5.207 3.005l-5.212 2.995z"></path>
                        </svg>
                    </a>
                </div>
                <!-- Add more buttons here -->
            </div>
        </div>
    </div>

    <div class="volume-button" id="volume-btn">
        <img src="volume-icon.png" alt="Volume Icon" width="20" height="20">
    </div>

    <div class="volume-slider-container" id="volume-slider-container">
        <input type="range" id="volume-slider" class="volume-slider" min="0" max="1" step="0.01" value="0.3">
    </div>

    <script>
        const audio = document.getElementById("background-audio");
        audio.volume = 0.3;

        document.body.addEventListener("click", function () {
            const video = document.getElementById("background-video");
            if (audio.paused && video.paused) {
                video.play();
                audio.play();
                document.getElementById("overlay-message").style.display = "none";
                document.getElementById("content").style.display = "block";
                document.getElementById("content").style.opacity = 1;
                video.style.filter = "blur(0)";
            }
        });

        document.getElementById("volume-btn").addEventListener("click", function () {
            const volumeSliderContainer = document.getElementById("volume-slider-container");
            volumeSliderContainer.style.display = volumeSliderContainer.style.display === "block" ? "none" : "block";
        });

        document.getElementById("volume-slider").addEventListener("input", function () {
            audio.volume = this.value;
        });
    </script>

</body>
</html>
