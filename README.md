<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome To Orpak Software and SOPs</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            background: linear-gradient(to bottom right, #e0f7fa, #ffffff);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 20px;
            color: #333;
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
        }
        h1 {
            color: #007BFF;
            text-align: center;
            margin-bottom: 20px;
            font-size: 2.5em;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
        }
        .maker-name {
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 0.8em;
            color: #333;
        }
        .login-container, .logout-container {
            text-align: center;
            margin-bottom: 20px;
            transition: all 0.3s ease;
        }
        .login-container {
            width: 100%;
            max-width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 12px;
            background-color: #ffffff;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
        }
        input[type="text"], input[type="password"] {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border-radius: 4px;
            border: 1px solid #ccc;
            font-size: 1em;
        }
        button {
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 4px;
            padding: 10px;
            cursor: pointer;
            width: 100%;
            font-size: 1em;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #0056b3;
        }
        .logout-button {
            background-color: #dc3545;
            padding: 5px 10px;
            margin-top: 10px;
            width: auto;
        }
        .notice-board, .updates-board {
            display: none; /* Initially hidden */
            background-color: rgba(255, 215, 0, 0.9); /* Gold background with transparency */
            border: 2px solid #FFA500; /* Orange border */
            border-radius: 12px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            width: 250px; /* Fixed width */
            position: absolute; /* Position it absolutely */
            text-align: left;
            color: red; /* Change notice text color to red */
            transition: all 0.3s ease; /* Transition for smooth appearance */
        }
        .notice-board {
            left: 20px; /* Align to the left */
            top: 100px; /* Position from the top */
        }
        .updates-board {
            right: 20px; /* Align to the right */
            top: 100px; /* Position from the top */
            background-color: rgba(173, 216, 230, 0.9); /* Light blue background */
        }
        .notice, .update {
            margin: 10px 0; /* Space between notices */
            font-size: 1.1em; /* Slightly larger font for notices */
        }
        .notice-title, .update-title {
            color: #007BFF; /* Blue color for the title */
            font-size: 1.5em; /* Font size for the title */
            margin-bottom: 10px; /* Margin below the title */
        }
        .box {
            background-color: #ffffff; /* White background for boxes */
            border: 1px solid #ccc; /* Light gray border */
            border-radius: 12px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            width: 100%; /* Full width */
            max-width: 800px; /* Max width for larger screens */
        }
        h2 {
            color: #007BFF;
            text-align: center;
            margin-bottom: 15px;
            font-size: 1.8em;
        }
        .software-container, .mandatory-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 15px; /* Space between grid items */
            margin: 0 auto; /* Centering the items */
        }
        .software-item, .mandatory-item {
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            height: 100px; /* Set height for each box */
        }
        /* Smart color coding for each box */
        .software-item:nth-child(1) { background-color: #4CAF50; }
        .software-item:nth-child(2) { background-color: #2196F3; }
        .software-item:nth-child(3) { background-color: #FF9800; }
        .software-item:nth-child(4) { background-color: #F44336; }
        .software-item:nth-child(5) { background-color: #8E24AA; }
        .software-item:nth-child(6) { background-color: #009688; }
        .software-item:nth-child(7) { background-color: #3F51B5; }
        .software-item:nth-child(8) { background-color: #FF5722; }

        .mandatory-item:nth-child(1) { background-color: #FF4081; }
        .mandatory-item:nth-child(2) { background-color: #FFC107; }

        .software-item:hover, .mandatory-item:hover {
            transform: translateY(-5px); /* Lift effect on hover */
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.2); /* Shadow effect */
        }
        a {
            text-decoration: none; /* Remove underline */
            color: white; /* Link color */
            font-weight: bold;
        }
        a:hover {
            text-decoration: underline; /* Underline on hover */
        }
        .floating-buttons {
            position: absolute;
            top: 20px;
            right: 20px; /* Shift logout button to the right */
        }
        .floating-buttons button {
            background-color: transparent;
            border: none;
            cursor: pointer;
            margin-bottom: 10px;
            font-size: 24px;
            color: #007BFF;
        }
    </style>
</head>
<body>
    <div class="maker-name">KoushalStar</div>
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

    <div class="notice-board" id="noticeBoard">
        <div class="notice-title">Notice Board</div>
        <div class="notice">1. HPCL ITPS Verification With L1 & HPCL ITPS Transaction History.</div>
        <div class="notice">2. HPCL, IOCL, BPCL And NAYARA New Software Need to Update On All Sites.</div>
        <div class="notice">3. HPCL MS To Petrol e20 Conversion need to Update in FCC.</div>
        <div class="notice">4. Take All Sites Access Details with ID And Password.</div>
    </div>

    <div class="updates-board" id="updatesBoard">
        <div class="update-title">Upcoming Updates</div>
        <div class="update" id="update1">1. RDB -CMS Mismatch Software</div>
        <div class="update" id="update2">2. UPS Repair SOP's</div>
        <div class="update" id="update3">3. Critical Validation SOP's</div>
        <div class="update" id="update4">4. Engineer Assessments Test Ranking Status</div>
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

        <h2>Mandatory Activities</h2>
        <div class="mandatory-container">
            <div class="mandatory-item"><a href="https://example.com/mandatory1.pdf" target="_blank">Critical Part Validation</a></div>
            <div class="mandatory-item"><a href="https://example.com/mandatory2.pdf" target="_blank">Mandatory Activity 2</a></div>
        </div>
    </div>

    <div class="box" id="sopContent" style="display: none;">
        <h2>SOP Documents</h2>
        <div class="software-container">
            <div class="software-item"><a href="https://drive.google.com/drive/folders/159TMvskuKCBtS8GO1aXBGuOwrshjUsTV?usp=sharing" target="_blank">ATG/TLS SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1f5LqNqxcK_7NEiLXltGfJgeyDetjgh3d?usp=sharing" target="_blank">FCC SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1LgFJ-SO3uis1HuR4ah-vp-GbUnDU4822?usp=sharing" target="_blank">Router SOP's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1cBQoa0E0H2v3vfYdjCws4PjIp-swGDMZ?usp=sharing" target="_blank">UPS & SPD</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1dajJOPIuZ6Qw9aKhlxL9uCN46VbhmR54?usp=sharing" target="_blank">Du Sop's</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1NqINZsXMvxN3bR0QFkRXrrqaQGggxWKH?usp=sharing" target="_blank">Price Pole</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1XsLTkpFTm19NSTTh-e2lkDbQuo7g1LWE?usp=sharing" target="_blank">OS & Siteomat Installation & Configuration</a></div>
            <div class="software-item"><a href="https://drive.google.com/drive/folders/1C6sb2hNDdt0RLSkmN7yw36iwYcIx86ZY?usp=sharing" target="_blank">Wireless Gateway Terminal</a></div>
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
        const noticeBoard = document.getElementById('noticeBoard');
        const updatesBoard = document.getElementById('updatesBoard');

        loginButton.addEventListener('click', function () {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            // Check credentials
            if (username === 'Orpak' && password === 'U$4F7dc8') {
                loginMessage.textContent = ''; // Clear any previous messages
                loginContainer.style.display = 'none'; // Hide login form
                logoutContainer.style.display = 'block'; // Show logout button
                mainContent.style.display = 'block'; // Show main content
                sopContent.style.display = 'block'; // Show SOP content
                noticeBoard.style.display = 'block'; // Show notice board
                updatesBoard.style.display = 'block'; // Show updates board
                logoutIcon.style.display = 'block'; // Show logout icon
                loginIcon.style.display = 'none'; // Hide login icon

                // Start blinking effect for the update points
                const updates = document.querySelectorAll('.update');
                setInterval(() => {
                    updates.forEach(update => {
                        update.style.visibility = update.style.visibility === 'hidden' ? 'visible' : 'hidden';
                    });
                }, 1000); // Blink every 1 second
            } else {
                loginMessage.textContent = 'Invalid username or password.';
            }
        });

        logoutButton.addEventListener('click', function () {
            loginContainer.style.display = 'block'; // Show login form
            logoutContainer.style.display = 'none'; // Hide logout button
            mainContent.style.display = 'none'; // Hide main content
            sopContent.style.display = 'none'; // Hide SOP content
            noticeBoard.style.display = 'none'; // Hide notice board
            updatesBoard.style.display = 'none'; // Hide updates board
            document.getElementById('username').value = ''; // Clear username field
            document.getElementById('password').value = ''; // Clear password field
            logoutIcon.style.display = 'none'; // Hide logout icon
            loginIcon.style.display = 'block'; // Show login icon
        });

        // Add click event to icons
        loginIcon.addEventListener('click', function () {
            loginContainer.style.display = 'block'; // Show login form
        });

        logoutIcon.addEventListener('click', function () {
            logoutButton.click(); // Trigger logout
        });
    </script>
</body>
</html>
