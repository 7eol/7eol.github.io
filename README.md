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

        .button {
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            overflow: hidden;
            cursor: pointer;
        }

        .button img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .button a {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            text-indent: -9999px;
        }

        /* Volume slider */
        .volume-slider {
            position: fixed;
            top: 10px;
            left: 10px;
            z-index: 9999;
            background: rgba(0, 0, 0, 0.5);
            padding: 10px;
            border-radius: 5px;
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

    <!-- Volume Control Slider -->
    <div class="volume-slider">
        <label for="volume">Volume</label>
        <input type="range" id="volume" min="0" max="1" step="0.01" value="1" onchange="setVolume(this.value)">
    </div>

    <!-- Profile and Links -->
    <div class="profile-container">
        <img src="pfp.gif" alt="Profile Picture">
        <h1>7</h1>

        <div class="buttons">
            <div class="button">
                <a href="https://www.youtube.com/@7eyesofluck" target="_blank">YouTube</a>
                <img src="youtube.jpg" alt="YouTube Logo">
            </div>
            <div class="button">
                <a href="https://link2.com" target="_blank">Link 2</a>
                <img src="button2.jpg" alt="Button Image 2">
            </div>
            <div class="button">
                <a href="https://link3.com" target="_blank">Link 3</a>
                <img src="button3.jpg" alt="Button Image 3">
            </div>
        </div>
    </div>

    <script>
        // Function to adjust the volume of the background audio
        function setVolume(volume) {
            var audio = document.getElementById('background-audio');
            audio.volume = volume;
        }
    </script>

</body>
</html>

