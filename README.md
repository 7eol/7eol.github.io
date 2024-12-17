<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biolink Test</title>
    <style>
        /* @font-face to load custom font */
        @font-face {
            font-family: 'TT Norms Pro Regular';
            src: url('TT Norms Pro Regular.woff') format('woff');
            font-weight: normal;
            font-style: normal;
        }

        /* Apply the custom font to the body */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'TT Norms Pro Regular', sans-serif; /* Use the custom font */
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
            filter: blur(10px); /* Initially apply blur */
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
            gap: 10px;
        }

       .button {
            width: 50px;
            height: 50px;
            overflow: visible; /* Prevent clipping */
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            display: inline-block;

            /* Ensure no rounding */
            border-radius: 0 !important; /* Force no rounding */
    }

    .button img {
            width: 100%; /* Ensures the image fills the button */
            height: auto; /* Maintains aspect ratio */
            object-fit: contain; /* Prevents cropping */
            object-position: center; /* Center-align the image */
            border-radius: 0 !important; /* Force no rounding */
    }


        .button:hover {
            transform: scale(1.1);
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.8); /* Glow effect around the image */
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
            <h1>7</h1> <!-- Changed to "7" -->
            <div class="buttons">
                <div class="button">
                    <a href="https://www.youtube.com/@7eyesofluck" target="_blank">
                        <img src="youtube.png" alt="YouTube"> <!-- YouTube button image -->
                    </a>
                </div>
                <div class="button">
                    <a href="https://link2.com" target="_blank">
                        <img src="button2-icon.png" alt="Button 2">
                    </a>
                </div>
                <div class="button">
                    <a href="https://link3.com" target="_blank">
                        <img src="button3-icon.png" alt="Button 3">
                    </a>
                </div>
            </div>
        </div>
    </div>

    <div class="volume-button" id="volume-btn">
        <img src="volume-icon.png" alt="Volume Control">
    </div>

    <div class="volume-slider-container" id="volume-slider-container">
        <input type="range" id="volume-slider" class="volume-slider" min="0" max="1" step="0.01">
    </div>

    <script>
        // Set the default volume lower
        const audio = document.getElementById("background-audio");
        audio.volume = 0.3;  // Set default volume to 30%

        // Play video and audio when clicked anywhere
        document.body.addEventListener("click", function () {
            if (audio.paused && document.getElementById("background-video").paused) {
                document.getElementById("background-video").play();
                audio.play();
                document.getElementById("overlay-message").style.display = "none";
                document.getElementById("content").style.display = "block";
                document.getElementById("content").style.opacity = 1;
                document.getElementById("background-video").style.filter = "blur(0)"; // Remove blur after play
            }
        });

        // Toggle volume slider
        document.getElementById("volume-btn").addEventListener("click", function () {
            const volumeSliderContainer = document.getElementById("volume-slider-container");
            volumeSliderContainer.style.display = volumeSliderContainer.style.display === "block" ? "none" : "block";
        });

        // Change volume based on slider input
        document.getElementById("volume-slider").addEventListener("input", function () {
            audio.volume = this.value;
        });
    </script>

</body>
</html>
