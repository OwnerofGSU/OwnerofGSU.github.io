<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Picture Page</title>
    <style>
        /* Style for the button */
        .button {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            height: 80vh; /* Set the height to 80% of the viewport height */
            width: 80vw; /* Set the width to 80% of the viewport width */
            background: #333;
            cursor: pointer;
            font-family: Consolas, Courier New, monospace;
            border: solid #404c5d 1px;
            font-size: 16px;
            color: rgb(161, 161, 161);
            border-radius: 5px;
            box-shadow: -1px -5px 15px #41465b, 5px 5px 15px #41465b,
                inset 5px 5px 10px #212121, inset -5px -5px 10px #212121;
        }

        .button:hover {
            box-shadow: 1px 1px 13px #20232e, -1px -1px 13px #545b78;
            color: #d6d6d6;
        }

        .button:active {
            box-shadow: 1px 1px 13px #20232e, -1px -1px 33px #545b78;
            color: #d6d6d6;
        }
    </style>
</head>
<body>
    <button class="button">Click me</button>
    <img src="https://i.imgur.com/pQT0l.gif" alt="Animated Picture">
</body>
</html>

