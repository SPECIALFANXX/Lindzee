<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Page</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #ff7eb3, #ff758c);
            margin: 0;
            padding: 0;
            color: #333;
        }
        .header {
            background: rgba(255, 255, 255, 0.8);
            color: #ff4081;
            padding: 20px;
            text-align: center;
            font-size: 32px;
            font-weight: bold;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        .header-subtitle {
            text-align: center;
            font-size: 20px;
            color: #fff;
            margin-top: 10px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
        }
        .main-container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: calc(100vh - 100px);
        }
        .login-container {
            background-color: #ffffff;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
            width: 350px;
            text-align: center;
        }
        .login-container h2 {
            margin-bottom: 20px;
            color: #ff4081;
            font-size: 24px;
            font-weight: 600;
        }
        .form-group {
            margin-bottom: 20px;
            text-align: left;
        }
        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: #555;
            font-weight: 500;
        }
        .form-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s;
        }
        .form-group input:focus {
            border-color: #ff4081;
            outline: none;
        }
        .form-group button {
            width: 100%;
            padding: 12px;
            background-color: #ff4081;
            color: #fff;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        .form-group button:hover {
            background-color: #e6366e;
        }
        #togglePassword {
            margin-top: 10px;
            background-color: transparent;
            color: #555;
            border: none;
            font-size: 14px;
            cursor: pointer;
        }
        #togglePassword:hover {
            color: #ff4081;
        }
        .error-message {
            color: red;
            font-size: 14px;
            margin-top: 10px;
        }
    </style>
    <script>
        function togglePasswordVisibility() {
            const passwordField = document.getElementById('password');
            const toggleButton = document.getElementById('togglePassword');
            if (passwordField.type === 'password') {
                passwordField.type = 'text';
                toggleButton.textContent = 'Hide Password';
            } else {
                passwordField.type = 'password';
                toggleButton.textContent = 'Show Password';
            }
        }

        function validateLogin(event) {
            event.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const errorMessage = document.getElementById('errorMessage');

            if (username === 'GT622x' && password === '124712') {
                window.location.href = 'home.html';
            } else {
                errorMessage.textContent = 'Invalid Fan ID or PPcode';
            }
        }
    </script>
</head>
<body>
    <div class="header">Lindzee Private Fan Page</div>
    <div class="header-subtitle">Welcome to Lindzee world of fun</div>
    <div class="main-container">
        <div class="login-container">
            <h2>Login</h2>
            <form onsubmit="validateLogin(event)">
                <div class="form-group">
                    <label for="username">Fan ID</label>
                    <input type="text" id="username" name="username" required>
                </div>
                <div class="form-group">
                    <label for="password">PPcode</label>
                    <input type="password" id="password" name="password" required>
                    <button type="button" id="togglePassword" onclick="togglePasswordVisibility()">Show Password</button>
                </div>
                <div class="form-group">
                    <button type="submit">Login</button>
                </div>
                <div id="errorMessage" class="error-message"></div>
            </form>
        </div>
    </div>
</body>
</html>
