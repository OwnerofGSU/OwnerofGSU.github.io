<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Picture Page</title>
    <style>
        /* Style for the button */
        .button {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0, 0, 0, 0.5); /* semi-transparent background */
            cursor: pointer;
        }

        /* Additional styles for the button content */
        .button-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-family: Arial, sans-serif;
            font-size: 24px;
            color: white;
        }
    </style>
</head>
<body>
    <button class="button">
        <div class="button-content">Click me</div>
    </button>
    <img src="https://i.imgur.com/pQT0l.gif" alt="Animated Picture">
</body>
</html>

