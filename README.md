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
            width: 30px;
            height: 30px;
            background-color: #333;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: background-color 0.3s ease;
        }

        .button:hover {
            background-color: #555;
        }

        .volume-button {
            position: absolute;
            top: 20px;
            left: 20px;
            background-color: transparent;
            border: none;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 3;
        }

        /* Additional button styles */
        .social-buttons {
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <!-- Background Video -->
    <video class="background-video" autoplay loop muted>
        <source src="your-video.mp4" type="video/mp4">
    </video>

    <!-- Overlay Message -->
    <div class="overlay-message" onclick="showContent()">Click to enter</div>

    <!-- Main Content -->
    <div class="content">
        <div class="profile-container">
            <img src="profile-image.jpg" alt="Profile Picture">
            <h1>Profile Name</h1>
        </div>

        <!-- Social Media Buttons -->
        <div class="buttons social-buttons">
            <button class="button">YouTube</button>
            <button class="button">TikTok</button>
            <button class="button">Steam</button>
            <button class="button">Discord</button>
        </div>
    </div>

    <!-- Volume Button -->
    <button class="volume-button">
        <img src="volume-icon.png" alt="Volume Icon" style="width: 20px; height: 20px;">
    </button>

    <script>
        function showContent() {
            document.querySelector('.overlay-message').style.display = 'none';
            document.querySelector('.content').style.display = 'block';
            setTimeout(() => {
                document.querySelector('.content').style.opacity = 1;
                document.querySelector('.background-video').style.filter = 'blur(0)';
            }, 100);
        }
    </script>

</body>
</html>
