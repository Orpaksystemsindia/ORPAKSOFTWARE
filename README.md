<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome To Orpak Software and SOPs</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            background: linear-gradient(to right, #f0f8ff, #e6f7ff); /* Gradient background */
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
            position: relative; /* For positioning buttons */
        }
        h1 {
            color: #333;
            text-align: center;
            margin-bottom: 20px;
        }
        .box {
            background-color: #ffffff; /* White background for boxes */
            border: 1px solid #ccc; /* Light gray border */
            border-radius: 8px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h2 {
            color: #007BFF; /* Color for section headers */
            text-align: center;
            margin-bottom: 15px;
        }
        .software-container {
            display: grid; /* Use CSS Grid for layout */
            grid-template-columns: repeat(4, 1fr); /* Four columns */
            gap: 10px; /* Space between grid items */
            margin: 0 auto; /* Centering the items */
        }
        .software-item {
            border-radius: 8px;
            padding: 10px; /* Reduced padding */
            text-align: center; /* Center text */
            transition: background-color 0.3s;
            cursor: pointer; /* Change cursor to pointer */
            display: flex; /* Flexbox for centering content */
            align-items: center; /* Center vertically */
            justify-content: center; /* Center horizontally */
            color: white; /* Text color */
            font-weight: bold; /* Bold text */
            height: 80px; /* Set height for each box */
        }
        /* Smart color coding for each box */
        .software-item:nth-child(1) { background-color: #4CAF50; } /* Green */
        .software-item:nth-child(2) { background-color: #2196F3; } /* Blue */
        .software-item:nth-child(3) { background-color: #FF9800; } /* Orange */
        .software-item:nth-child(4) { background-color: #F44336; } /* Red */
        .software-item:nth-child(5) { background-color: #8E24AA; } /* Purple */
        .software-item:nth-child(6) { background-color: #009688; } /* Teal */
        .software-item:nth-child(7) { background-color: #3F51B5; } /* Indigo */
        .software-item:nth-child(8) { background-color: #FF5722; } /* Deep Orange */

        .software-item:hover {
            opacity: 0.8; /* Slightly fade on hover */
        }
        a {
            text-decoration: none; /* Remove underline */
            color: white; /* Link color */
            font-weight: bold;
        }
        a:hover {
            text-decoration: underline; /* Underline on hover */
        }
        .login-container, .logout-container {
            text-align: center;
            margin-bottom: 20px;
        }
        /* Adjusted styles for smaller login form */
        .login-container {
            width: 300px; /* Fixed width for login form */
            margin: 0 auto; /* Centering the login form */
            padding: 15px; /* Reduced padding */
            border: 1px solid #ccc; /* Added border */
            border-radius: 8px; /* Rounded corners */
            background-color: #ffffff; /* White background */
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.1); /* Subtle shadow */
        }
        input[type="text"], input[type="password"] {
            width: 100%; /* Full width */
            padding: 8px; /* Reduced padding */
            margin: 5px 0; /* Reduced margin */
            border-radius: 4px;
            border: 1px solid #ccc;
        }
        button {
            background-color: #007BFF; /* Bootstrap primary color */
            color: white;
            border: none;
            border-radius: 4px;
            padding: 8px; /* Reduced padding */
            cursor: pointer;
            width: 100%; /* Full width */
        }
        button:hover {
            background-color: #0056b3; /* Darker blue on hover */
        }
        .logout-button {
            background-color: #dc3545; /* Bootstrap danger color */
            padding: 5px 10px; /* Smaller padding for logout */
            margin-top: 10px; /* Space above the logout button */
            width: auto; /* Automatic width */
        }
        .floating-buttons {
            position: absolute;
            top: 20px;
            right: 20px;
        }
        .floating-buttons button {
            background-color: transparent;
            border: none;
            cursor: pointer;
            margin-bottom: 10px;
            font-size: 24px; /* Icon size */
        }
    </style>
</head>
<body>
    <h1>Welcome To Orpak Software and SOPs</h1>

    <div class="login-container" id="loginContainer">
        <h2>Login</h2>
        <input type="text" id="username" placeholder="Username" required>
        <input type="password" id="password" placeholder="Password" required>
        <button id="loginButton">Login</button>
        <div id="loginMessage" style="color: red;"></div>
    </div>

    <div class="logout-container" id="logoutContainer" style="display: none;">
        <button class="logout-button" id="logoutButton">Logout</button>
    </div>

    <div class="box" id="mainContent" style="display: none;">
        <h2>Available Software</h2>
        <div class="software-container">
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1OwDG1YIGIvk-pfmb5kl-7idfv1X3mXvt?usp=sharing" target="_blank">HPCL Software</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1CvT6pZt1PVo6U6yVOUEY5Yv-jOGY2nHX?usp=sharing" target="_blank">IOCL Software</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/12oC5wVAhaAyjAI6CFtulWTa0Qkd5nczo?usp=sharing" target="_blank">BPCL Software</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1o63SEJXOrQ8daxBY4EsKDks1hpd2BeFM?usp=sharing" target="_blank">NAYARA Software</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1P_YxkZNUyZJGODZW7fzApLt5WGnwx4fd?usp=sharing" target="_blank">HPCL Related SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1M2cLs3brGxSojrgMUSTfBBQe-NOfaanw?usp=sharing" target="_blank">IOCL Related SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/17FpBNsMpH9fkd7ClquCwoNda4anmoVvp?usp=sharing" target="_blank">BPCL Related SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1KxyMnv-yZe76tsQoEdrbRIEnmmJjPvCi?usp=sharing" target="_blank">NAYARA Related SOP's</a></div>
        </div>
    </div>

    <div class="box" id="sopContent" style="display: none;">
        <h2>SOP Documents</h2>
        <div class="software-container">
            <div class="software-item"><a href="https://drive.google.com/drive/folders/159TMvskuKCBtS8GO1aXBGuOwrshjUsTV?usp=sharing" target="_blank">ATG/TLS SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1f5LqNqxcK_7NEiLXltGfJgeyDetjgh3d?usp=sharing" target="_blank">FCC SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1LgFJ-SO3uis1HuR4ah-vp-GbUnDU4822?usp=sharing" target="_blank">Router SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1cBQoa0E0H2v3vfYdjCws4PjIp-swGDMZ?usp=sharing" target="_blank">UPS & SPD</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1dajJOPIuZ6Qw9aKhlxL9uCN46VbhmR54?usp=sharing" target="_blank">Du Sop's</a></div> <!-- Updated Link -->
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1NqINZsXMvxN3bR0QFkRXrrqaQGggxWKH?usp=sharing" target="_blank">Price Pole</a></div> <!-- Updated Link -->
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1XsLTkpFTm19NSTTh-e2lkDbQuo7g1LWE?usp=sharing" target="_blank">OS & Siteomat Installation & Configuration</a></div> <!-- Updated Link -->
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1C6sb2hNDdt0RLSkmN7yw36iwYcIx86ZY?usp=sharing" target="_blank">Wireless Gateway Terminal</a></div> <!-- Updated Link -->
            <div class="software-item"><a href="https://example.com/sop9.pdf" target="_blank">SOP Document 9</a></div>
            <div class="software-item"><a href="https://example.com/sop10.pdf" target="_blank">SOP Document 10</a></div>
        </div>
    </div>

    <div class="floating-buttons">
        <button id="loginIcon" title="Login"><i class="fas fa-sign-in-alt"></i></button>
        <button id="logoutIcon" title="Logout" style="display: none;"><i class="fas fa-sign-out-alt"></i></button>
    </div>

    <script>
        const loginButton = document.getElementById('loginButton');
        const logoutButton = document.getElementById('logoutButton');
        const loginIcon = document.getElementById('loginIcon');
        const logoutIcon = document.getElementById('logoutIcon');
        const mainContent = document.getElementById('mainContent');
        const sopContent = document.getElementById('sopContent');
        const loginContainer = document.getElementById('loginContainer');
        const logoutContainer = document.getElementById('logoutContainer');
        const loginMessage = document.getElementById('loginMessage');

        loginButton.addEventListener('click', function() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            // Check credentials
            if (username === 'Orpak' && password === 'U$4F7dc8') {
                loginMessage.textContent = ''; // Clear any previous messages
                loginContainer.style.display = 'none'; // Hide login form
                logoutContainer.style.display = 'block'; // Show logout button
                mainContent.style.display = 'block'; // Show main content
                sopContent.style.display = 'block'; // Show SOP content
                logoutIcon.style.display = 'block'; // Show logout icon
                loginIcon.style.display = 'none'; // Hide login icon
            } else {
                loginMessage.textContent = 'Invalid username or password.';
            }
        });

        logoutButton.addEventListener('click', function() {
            loginContainer.style.display = 'block'; // Show login form
            logoutContainer.style.display = 'none'; // Hide logout button
            mainContent.style.display = 'none'; // Hide main content
            sopContent.style.display = 'none'; // Hide SOP content
            document.getElementById('username').value = ''; // Clear username field
            document.getElementById('password').value = ''; // Clear password field
            logoutIcon.style.display = 'none'; // Hide logout icon
            loginIcon.style.display = 'block'; // Show login icon
        });

        // Add click event to icons
        loginIcon.addEventListener('click', function() {
            loginContainer.style.display = 'block'; // Show login form
        });

        logoutIcon.addEventListener('click', function() {
            logoutButton.click(); // Trigger logout
        });
    </script>
</body>
</html>
