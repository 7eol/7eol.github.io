<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Glowing Buttons</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: black;
        }

        .buttons {
            display: flex;
            gap: 20px;
        }

        .button {
            display: inline-flex;
            justify-content: center;
            align-items: center;
            width: 60px;
            height: 60px;
            position: relative;
            cursor: pointer;
        }

        .button svg {
            width: 40px;
            height: 40px;
            fill: white;
            transition: filter 0.3s ease, transform 0.3s ease;
            filter: drop-shadow(0 0 5px rgba(255, 255, 255, 0.5));
        }

        .button:hover svg {
            transform: scale(1.1);
            filter: drop-shadow(0 0 15px rgba(255, 255, 255, 1));
        }
    </style>
</head>
<body>
    <div class="buttons">
        <div class="button">
            <a href="https://youtube.com/@7eyesofluck" target="_blank">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="1.99 5 20.01 14.01">
                    <path d="M21.593 7.203a2.506 2.506 0 0 0-1.762-1.766C18.265 5.007 12 5 12 5s-6.264-.007-7.831.404a2.56 2.56 0 0 0-1.766 1.778c-.413 1.566-.417 4.814-.417 4.814s-.004 3.264.406 4.814c.23.857.905 1.534 1.763 1.765c1.582.43 7.83.437 7.83.437s6.265.007 7.831-.403a2.515 2.515 0 0 0 1.767-1.763c.414-1.565.417-4.812.417-4.812s.02-3.265-.407-4.831zM9.996 15.005l.005-6l5.207 3.005l-5.212 2.995z"></path>
                </svg>
            </a>
        </div>
        <div class="button">
            <a href="https://tiktok.com/@7eyesofluck" target="_blank">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="3.2 2 17.43 19.99">
                    <path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.2 1.74a2.89 2.89 0 0 1 2.31-4.64a2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.05A6.33 6.33 0 0 0 5 20.1a6.34 6.34 0 0 0 10.86-4.43v-7a8.16 8.16 0 0 0 4.77 1.52v-3.4a4.85 4.85 0 0 1-1-.1z"></path>
                </svg>
            </a>
        </div>
        <div class="button">
            <a href="https://github.com/7eol" target="_blank">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="2.05 2 19.95 19.46">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M12.026 2c-5.509 0-9.974 4.465-9.974 9.974c0 4.406 2.857 8.145 6.821 9.465c.499.09.679-.217.679-.481c0-.237-.008-.865-.011-1.696c-2.775.602-3.361-1.338-3.361-1.338c-.452-1.152-1.107-1.459-1.107-1.459c-.905-.619.069-.605.069-.605c1.002.07 1.527 1.028 1.527 1.028c.89 1.524 2.336 1.084 2.902.829c.091-.645.351-1.085.635-1.334c-2.214-.251-4.542-1.107-4.542-4.93c0-1.087.389-1.979 1.024-2.675c-.101-.253-.446-1.268.099-2.64c0 0 .837-.269 2.742 1.021a9.582 9.582 0 0 1 2.496-.336a9.554 9.554 0 0 1 2.496.336c1.906-1.291 2.742-1.021 2.742-1.021c.545 1.372.203 2.387.099 2.64c.64.696 1.024 1.587 1.024 2.675c0 3.833-2.33 4.675-4.552 4.922c.355.308.675.916.675 1.846c0 1.334-.012 2.41-.012 2.737c0 .267.178.577.687.479C19.146 20.115 22 16.379 22 11.974C22 6.465 17.535 2 12.026 2z"></path>
                </svg>
            </a>
        </div>
    </div>
</body>
</html>
