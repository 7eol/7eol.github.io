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
            cursor: pointer;
        }

        .background-video {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: blur(10px);
            z-index: -1;
            transition: filter 1s ease-in-out;
            pointer-events: none;
        }

        .overlay-message {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: white;
            font-size: 2rem;
            text-align: center;
            cursor: pointer;
            z-index: 100;
        }

        .content {
            visibility: hidden;
            opacity: 0;
            transition: opacity 1s ease-in-out;
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

        .upload-button {
            position: fixed;
            top: 10px;
            right: 10px;
            background-color: #008CBA;
            color: white;
            padding: 10px;
            border: none;
            cursor: pointer;
            font-size: 16px;
        }

        .dashboard {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.7);
            display: none;
            z-index: 10001;
            justify-content: center;
            align-items: center;
        }

        .dashboard-content {
            background: white;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
        }

        .dashboard-content input[type="file"] {
            margin-bottom: 10px;
        }

        .dashboard-content button {
            padding: 10px;
            background-color: #008CBA;
            color: white;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <video class="background-video" id="background-video" muted>
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

    <div class="content">
        <div class="profile-container">
            <img id="profile-img" src="default-profile.jpg" alt="Profile Picture">
            <h1>Username</h1>
            <div class="buttons">
                <div class="button">
                    <a href="https://www.youtube.com" target="_blank">
                        <img src="youtube.jpg" alt="YouTube Logo">
                    </a>
                </div>
                <div class="button">
                    <a href="https://link2.com" target="_blank">
                        <img src="button2.jpg" alt="Link 2">
                    </a>
                </div>
            </div>
        </div>
    </div>

    <button class="upload-button" id="upload-btn">Open Dashboard</button>

    <div class="dashboard" id="dashboard">
        <div class="dashboard-content">
            <h3>Upload Files</h3>
            <input type="file" id="background-upload" accept="video/mp4">
            <input type="file" id="profile-upload" accept="image/*">
            <button id="save-upload">Save Changes</button>
        </div>
    </div>

    <div class="volume-button" id="volume-btn">
        <img src="volume-icon.png" alt="Volume Control">
    </div>
    <div class="volume-slider-container" id="volume-slider-container">
        <input type="range" id="volume-slider" class="volume-slider" min="0" max="1" step="0.01">
    </div>

    <script>
        document.getElementById("overlay-message").addEventListener("click", function () {
            document.getElementById("background-video").play();
            document.getElementById("background-audio").play();
            document.getElementById("overlay-message").style.display = "none";
            document.querySelector(".content").style.visibility = "visible";
            document.querySelector(".content").style.opacity = 1;
            document.getElementById("background-video").style.filter = "blur(0)";
        });

        document.getElementById("volume-btn").addEventListener("click", function () {
            const volumeSliderContainer = document.getElementById("volume-slider-container");
            volumeSliderContainer.style.display = volumeSliderContainer.style.display === "block" ? "none" : "block";
        });

        document.getElementById("volume-slider").addEventListener("input", function () {
            const audio = document.getElementById("background-audio");
            audio.volume = this.value;
        });

        document.getElementById("upload-btn").addEventListener("click", function () {
            document.getElementById("dashboard").style.display = "flex";
        });

        document.getElementById("save-upload").addEventListener("click", function () {
            const backgroundFile = document.getElementById("background-upload").files[0];
            const profileFile = document.getElementById("profile-upload").files[0];

            if (backgroundFile) {
                const reader = new FileReader();
                reader.onload = function () {
                    document.getElementById("background-video").src = reader.result;
                    document.getElementById("background-video").load();
                };
                reader.readAsDataURL(backgroundFile);
            }

            if (profileFile) {
                const reader = new FileReader();
                reader.onload = function () {
                    document.getElementById("profile-img").src = reader.result;
                };
                reader.readAsDataURL(profileFile);
            }

            document.getElementById("dashboard").style.display = "none";
        });
    </script>
</body>
</html>
