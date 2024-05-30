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
            background: rgba(0, 0, 0, 0.5); /* Semi-transparent background */
            cursor: pointer;
        }

        .button-inner {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-family: Consolas, Courier New, monospace;
            font-size: 24px;
            color: white;
            padding: 20px 40px;
            background-color: #333;
            border: none;
            border-radius: 5px;
            box-shadow: 0px 0px 10px 0px rgba(0,0,0,0.75);
        }
    </style>
</head>
<body>
    <button class="button" onclick="showMessage()">
        <div class="button-inner">Click me</div>
    </button>
    <img src="https://i.imgur.com/pQT0l.gif" alt="Animated Picture">
    
    <script>
        function showMessage() {
            alert("Button clicked!");
        }
    </script>
</body>
</html>

