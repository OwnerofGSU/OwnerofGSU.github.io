<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Website</title>
    <style>
        /* CSS styles can be added here */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f2f2f2; /* Gray background similar to ChatGPT */
            background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTIVeCiDEpYTYKXB88w6rYkcX0wlUTBGNtJwFhC-IKzAw&s');
            background-size: cover;
            background-repeat: no-repeat;
            background-attachment: fixed;
            background-position: center;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        header {
            background-color: rgba(0, 0, 0, 0.5);
            color: #fff;
            padding: 10px;
            text-align: center;
        }
        main {
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.8); /* Adjust transparency if needed */
            border-radius: 10px;
            margin: 20px auto;
            max-width: 600px;
        }
        footer {
            background-color: rgba(0, 0, 0, 0.5);
            color: #fff;
            padding: 10px;
            text-align: center;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        .password-form {
            background-color: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            max-width: 400px;
            margin: auto;
        }
        input[type="password"] {
            padding: 10px;
            margin-bottom: 10px;
        }
        button {
            padding: 10px 20px;
            margin-top: 10px;
            background-color: #333;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        /* Loader styles */
        .loader {
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(255, 255, 255, 0.8);
            background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTIVeCiDEpYTYKXB88w6rYkcX0wlUTBGNtJwFhC-IKzAw&s');
            background-size: cover;
            background-repeat: no-repeat;
            background-attachment: fixed;
            background-position: center;
            z-index: 1000;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }

        .loader-inner {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 20px;
        }

        .loader .bar {
            display: inline-block;
            width: 20px;
            height: 80px;
            margin: 0 5px;
            background-color: #000;
            animation: loader_animation 1s infinite ease-in-out;
        }

        @keyframes loader_animation {
            0% {
                transform: scaleY(0.1);
            }
            50% {
                transform: scaleY(1);
            }
            100% {
                transform: scaleY(0.1);
            }
        }
    </style>
</head>
<body>

<div class="password-form" id="passwordForm">
    <h2>Hello Comrade, Enter the Code Here</h2>
    <!-- Text input field -->
    <input placeholder="Enter your password..." class="input" name="password" type="password" id="passwordInput">
    <!-- Button to submit the password -->
    <button onclick="checkPassword()">Submit</button>
</div>

<div class="loader">
    <span class="bar"></span>
    <span class="bar"></span>
    <span class="bar"></span>
</div>

<main id="main" style="display: none;">
    <!-- Content goes here -->
    <button onclick="showTickets()">What are tickets?</button>
    <div>
        <button onclick="makeTicket()">Make a Ticket</button>
    </div>
    <div id="ticketForm" style="display: none;">
        <form onsubmit="submitTicket(event)">
            <label for="ticketText">I would like to sell:</label><br>
            <textarea id="ticketText" name="ticketText" rows="4" cols="50"></textarea><br>
            <label for="discordUser">Discord User:</label><br>
            <input type="text" id="discordUser" name="discordUser"><br><br>
            <input type="submit" value="Send">
        </form>
    </div>
</main>

<footer>
    <p>© 2024 My Website. All rights reserved.</p>
</footer>

<script>
    function checkPassword() {
        var password = document.getElementById("passwordInput").value;
        if (password === "gsu") {
            // Show loader for 10 seconds
            document.getElementById("passwordForm").style.display = "none";
            document.querySelector(".loader").style.display = "flex";
            setTimeout(function() {
                // Hide loader and show main content after 10 seconds
                document.querySelector(".loader").style.display = "none";
                document.getElementById("main").style.display = "block";
            }, 10000);
        } else {
            // Display an alert if the password is incorrect
            alert("Incorrect password. Please try again.");
        }
    }

    function showTickets() {
        alert("Tickets are texts where buyers are offering cryptocurrency or PayPal for digital items, and you, as the seller, are getting paid either with cryptocurrency or PayPal. It's a secure and convenient way to exchange digital goods for currency.");
    }

    function makeTicket() {
        alert("You are making a ticket. Please provide the necessary details.");
        document.getElementById("ticketForm").style.display = "block";
    }

    function submitTicket(event) {
        event.preventDefault();
        var ticketText = document.getElementById("ticketText").value;
        var discordUser = document.getElementById("discordUser").value;
        var data = {
            content: "Ticket: " + ticketText + "\nDiscord User: " + discordUser
        };
        fetch("https://discord.com/api/webhooks/1243975322190483517/Isfa0s2kyyU6uum-04Vd_fivk-45lPEuu7KBnge2UND9Zzsu8a4HDX0erFvTy3E8RjCm", {
            method: "POST",
            headers: {
                "Content-Type": "application/json"
            },
            body: JSON.stringify(data)
        })
        .then(response => {
            if (!response.ok) {
                throw new Error("Network response was not ok");
            }
            alert("Ticket submitted successfully!");
            document.getElementById("ticketForm").reset();
        })
        .catch(error => {
            console.error("There was a problem with your fetch operation:", error);
            alert("An error occurred while submitting the ticket. Please try again later.");
        });
    }
</script>

</body>
</html>
