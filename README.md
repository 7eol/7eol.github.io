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
    </style>
</head>
<body>

    <video class="background-video" autoplay loop>
        <source src="backgroundvideo.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

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

</body>
</html>
