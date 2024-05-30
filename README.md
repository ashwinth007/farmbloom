<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FARMBLOOM</title>
    <style>
        body {
            background-image: url("C:/Users/ashwi/Downloads/farming.jpg"); /* Ensure this path is correct */
            background-repeat: no-repeat;
            background-size: cover;
            font-family: Arial, sans-serif;
            color: #333;
        }

        .container {
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
            padding: 20px;
            width: 100%;
            max-width: 500px;
            margin: 50px auto;
            text-align: center;
        }

        input {
            display: block;
            width: 100%;
            margin-bottom: 15px;
            padding: 10px;
            box-sizing: border-box;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        button {
            padding: 15px;
            border-radius: 10px;
            margin-top: 15px;
            margin-bottom: 15px;
            border: none;
            color: white;
            cursor: pointer;
            background-color: #4CAF50;
            width: 100%;
            font-size: 16px;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #45a049;
        }

        label {
            display: block;
            width: 100%;
            margin-top: 10px;
            margin-bottom: 5px;
            text-align: left;
            color: #555;
            font-weight: bold;
        }

        .clearfix::after {
            content: "";
            clear: both;
            display: table;
        }

        .clearfix button {
            width: 48%;
            float: left;
        }

        .clearfix .cancelbtn {
            background-color: #f44336;
            margin-right: 4%;
        }

        .message {
            color: red;
            font-weight: bold;
        }

        p {
            margin-top: 1rem;
            font-size: 0.9rem;
        }

        a {
            color: dodgerblue;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>WELCOME TO FARMBLOOM</h1>
    <h2>LOGIN | SIGN UP</h2>

    <form id="loginForm" action="login_action_page.php" method="post">
        <label for="loginUsername">Username:</label>
        <input type="text" id="loginUsername" name="loginUsername" placeholder="Enter your Username" required>

        <label for="loginPassword">Password:</label>
        <input type="password" id="loginPassword" name="loginPassword" placeholder="Enter your Password" required>

        <button type="submit">Login</button>
    </form>
    <p>NOT REGISTERED? <a href="#signup">Create an account</a></p>
</div>

<div class="container" id="signup">
    <h1>Sign Up</h1>
    <p>Please fill in this form to create an account.</p>
    <hr>

    <form id="signupForm" action="signup_action_page.php" method="post">
        <label for="username">Username</label>
        <input type="text" id="username" placeholder="Enter Username" name="username" required>

        <label for="email">Email</label>
        <input type="email" id="email" placeholder="Enter Email" name="email" required>

        <label for="password">Password</label>
        <input type="password" id="password" placeholder="Enter Password" name="password" required>

        <label for="confirmPassword">Repeat Password</label>
        <input type="password" id="confirmPassword" placeholder="Repeat Password" name="confirmPassword" required>

        <label>
            <input type="checkbox" checked="checked" name="remember" style="margin-bottom:15px"> Remember me
        </label>

        <p>By creating an account you agree to our <a href="#">Terms & Privacy</a>.</p>

        <div class="clearfix">
            <button type="button" class="cancelbtn">Cancel</button>
            <button type="submit" class="signupbtn">Sign Up</button>
        </div>
        <p id="message" class="message"></p>
    </form>
</div>

<script>
document.getElementById('signupForm').addEventListener('submit', function(event) {
    event.preventDefault();

    var username = document.getElementById('username').value;
    var email = document.getElementById('email').value;
    var password = document.getElementById('password').value;
    var confirmPassword = document.getElementById('confirmPassword').value;
    var message = document.getElementById('message');

    if (password !== confirmPassword) {
        message.textContent = 'Passwords do not match!';
        return;
    }

    // Assuming the form submission is successful
    message.textContent = 'Sign up successful! Redirecting...';

    // Redirect to the weather forecast page after 2 seconds
    setTimeout(function() {
        window.location.href = 'p5.html'; // Replace with the actual URL of your weather forecast page
    }, 2000);
});
</script>

</body>
</html>
