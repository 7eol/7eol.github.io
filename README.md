<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biolink Test</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            overflow: hidden;
        }

        .background-video {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: -1;
        }

        .profile-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            color: white;
        }

        .profile-container img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 3px solid white;
        }

        .profile-container h1 {
            margin: 15px 0;
            font-size: 2rem;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        .button img {
            width: 60px;
            height: 60px;
            object-fit: cover;
            cursor: pointer;
        }

        /* Volume button and expanded slider */
        .volume-button {
            position: fixed;
            top: 10px;
            left: 10px;
            cursor: pointer;
            z-index: 9999;
        }

        .volume-slider-container {
            position: fixed;
            top: 70px;
            left: 10px;
            display: none;
            background: rgba(0, 0, 0, 0.5);
            padding: 10px;
            border-radius: 5px;
        }

        .volume-slider {
            width: 100px;
        }

        .buttons .button img {
            width: 100px; /* Modify as needed */
            height: 100px; /* Modify as needed */
        }
    </style>
</head>
<body>

    <!-- Background Video -->
    <video class="background-video" autoplay loop muted>
        <source src="backgroundvideo.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

    <!-- Background Audio -->
    <audio id="background-audio" autoplay loop>
        <source src="backgroundaudio.mp3" type="audio/mp3">
        Your browser does not support the audio tag.
    </audio>

    <!-- Volume Control -->
    <div class="volume-button" onclick="toggleSlider()">
        <img src="volume-icon.png" alt="Volume Icon">
    </div>
    <div class="volume-slider-container" id="volume-slider-container">
        <input type="range" id="volume" min="0" max="1" step="0.01" value="1" class="volume-slider" onchange="setVolume(this.value)">
    </div>

    <!-- Profile and Links -->
    <div class="profile-container">
        <img src="pfp.gif" alt="Profile Picture">
        <h1>7</h1>

        <div class="buttons">
            <div class="button">
                <a href="https://www.youtube.com/@7eyesofluck" target="_blank">
                    <img src="youtube.jpg" alt="YouTube Logo">
                </a>
            </div>
            <div class="button">
                <a href="https://link2.com" target="_blank">
                    <img src="button2.jpg" alt="Button Image 2">
                </a>
            </div>
            <div class="button">
                <a href="https://link3.com" target="_blank">
                    <img src="button3.jpg" alt="Button Image 3">
                </a>
            </div>
        </div>
    </div>

    <script>
        // Function to adjust the volume of the background audio
        function setVolume(volume) {
            var audio = document.getElementById('background-audio');
            audio.volume = volume;
        }

        // Function to toggle the visibility of the volume slider
        function toggleSlider() {
            var sliderContainer = document.getElementById('volume-slider-container');
            sliderContainer.style.display = (sliderContainer.style.display === 'block') ? 'none' : 'block';
        }

        // Check if audio is working by playing it after the page loads
        window.onload = function() {
            var audio = document.getElementById('background-audio');
            audio.play().catch(function(error) {
                console.log("Audio autoplay failed: ", error);
                // Here, you can show an alert or try another method to play the audio
            });
        }
    </script>

</body>
</html>
