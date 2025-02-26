<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome To Orpak Software and SOPs</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            background: linear-gradient(to bottom right, #e0f7fa, #80deea);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 20px;
            color: #333;
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
            min-height: 100vh;
        }
        h1 {
            color: #007BFF;
            text-align: center;
            margin-bottom: 20px;
            font-size: 2.5em;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
        }
        .maker-name {
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 0.8em;
            color: #007BFF;
        }
        .login-container {
            text-align: center;
            margin-bottom: 20px;
            background-color: #ffffff;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            width: 100%;
            max-width: 400px;
            transition: transform 0.2s;
        }
        .login-container:hover {
            transform: scale(1.02);
        }
        input[type="text"], input[type="password"] {
            width: calc(100% - 22px);
            padding: 10px;
            margin: 10px 0; /* Increased margin for better spacing */
            border-radius: 4px;
            border: 1px solid #ccc;
            font-size: 1em;
            transition: border 0.3s;
            outline: none; /* Remove outline */
        }
        input[type="text"]:focus, input[type="password"]:focus {
            border-color: #007BFF;
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
            transition: background-color 0.3s ease, transform 0.3s;
            display: flex; /* Allow for icon alignment */
            align-items: center; /* Center text and icons vertically */
            outline: none; /* Remove outline */
        }
        button:hover {
            background-color: #0056b3;
            transform: scale(1.05);
        }
        .error-message {
            color: red;
            margin-top: 10px;
            display: none; /* Hidden by default */
        }
        .loading-indicator {
            display: none; /* Hidden by default */
            margin-top: 10px;
            color: #007BFF;
        }
        .critical-probe-snaps {
            display: none; /* Initially hidden */
            background-color: #ffffff;
            border: 1px solid #ccc;
            border-radius: 12px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 400px; /* Small size */
            font-size: 0.9em; /* Smaller font size */
        }
        .toggle-arrow {
            cursor: pointer;
            color: #007BFF;
            font-size: 1.5em;
            margin-bottom: 10px;
        }
        .notice-board, .updates-board {
            display: none;
            background-color: rgba(255, 215, 0, 0.9);
            border: 2px solid #FFA500;
            border-radius: 12px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            width: 250px;
            position: absolute;
            text-align: left;
            color: red;
            overflow: hidden;
        }
        .notice-title, .update-title {
            color: #007BFF;
            font-size: 1.5em;
            margin-bottom: 10px;
        }
        .notice-content {
            height: auto;
            overflow: visible;
        }
        .notice {
            padding: 5px 0;
            display: none;
        }
        .notice-board {
            left: 20px;
            top: 100px;
        }
        .updates-board {
            right: 20px;
            top: 100px;
            background-color: rgba(173, 216, 230, 0.9);
        }
        .box {
            background-color: #ffffff;
            border: 1px solid #ccc;
            border-radius: 12px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 800px;
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
            gap: 15px;
            margin: 0 auto;
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
            height: 100px;
        }
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
        .mandatory-item:nth-child(3) { background-color: #FF4081; }
        .mandatory-item:nth-child(4) { background-color: #FFC107; }

        .software-item:hover, .mandatory-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.2);
        }
        a {
            text-decoration: none;
            color: white;
            font-weight: bold;
        }
        a:hover {
            text-decoration: underline;
        }
        .floating-buttons {
            position: absolute;
            top: 20px;
            right: 20px;
        }
        .logout-button {
            background-color: transparent;
            border: none;
            cursor: pointer;
            font-size: 24px;
            color: #dc3545;
        }
        .highlight {
            color: #dc3545;
            transform: scale(1.2);
            transition: transform 0.3s ease, color 0.3s ease;
        }

        /* Dark Green Icon */
        .dark-green-icon {
            position: fixed;
            top: 20px; /* Adjust this value to position it vertically */
            right: 20px; /* Adjust this value to position it horizontally */
            background-color: #006400; /* Dark Green */
            color: white;
            border: none;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            display: none; /* Hidden initially */
            justify-content: center;
            align-items: center;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            font-size: 24px;
            transform: translateY(-50%); /* Center it vertically */
        }

        /* Popup Styles */
        .popup {
            display: none; /* Hidden by default */
            position: fixed;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5); /* Black background with transparency */
            justify-content: center;
            align-items: center;
        }
        .popup-content {
            background-color: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            text-align: center;
            width: 90%; /* Adjust the width to make it smaller */
            max-width: 400px; /* Set a maximum width */
        }
        .popup input[type="text"] {
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            width: 80%;
        }
        .popup button {
            margin-top: 10px;
        }
        .result-box {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #007BFF;
            border-radius: 4px;
            background-color: #f0f8ff; /* Light blue background for result box */
            color: #007BFF; /* Blue text color */
        }

        /* Confirmation Popup Styles */
        .confirmation-popup {
            display: none; /* Hidden by default */
            position: fixed;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5); /* Black background with transparency */
            justify-content: center;
            align-items: center;
        }
        .confirmation-popup-content {
            background-color: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            text-align: center;
            width: 90%; /* Adjust the width to make it smaller */
            max-width: 400px; /* Set a maximum width */
        }

        @media (max-width: 600px) {
            h1 {
                font-size: 1.8em;
            }
            .login-container, .notice-board, .updates-board, .box, .critical-probe-snaps {
                width: 90%;
                max-width: none;
            }
            .software-item, .mandatory-item {
                height: auto;
                padding: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="maker-name">KoushalStar</div>
    <h1>Welcome To Orpak Software and SOPs</h1>

    <div class="critical-probe-snaps" id="criticalProbeSnaps" role="region" aria-labelledby="criticalProbeTitle">
        <div class="toggle-arrow" id="toggleArrow" tabindex="0" role="button" aria-expanded="false" aria-controls="criticalProbeContent">
            <i class="fas fa-chevron-down"></i> Critical ATG Probe Snaps
        </div>
        <div class="critical-probe-content" id="criticalProbeContent" style="display: none;">
            <ol>
                <li>Electrical audit to be done for AC input inside ATG Console</li>
                <li>For barrier cards DC input to console and DC output to probes to be checked.</li>
                <li>For barrier communication port volt to be checked at in and out for Probe both.</li>
                <li>Communication Volt from ATG console and Master WGT separately to be checked.</li>
                <li>Probe connection inside Console as well as Tank chamber to be checked as per standard installation & direct probe checking method to be applied.</li>
                <li>Connection for earthing and shield cables to be properly tightened and thimble/LUX may be used to connect properly with Console body.</li>
                <li>Probe installation inside tank chamber.</li>
                <li>Distance between probe and STP or Dicant Pipe (305 mm or 610mm)</li>
                <li>Product, Density & Water Floats with magnet ring to be checked properly</li>
                <li>Probe Serial Number and manufacture year to be checked for warranty claim replacement</li>
                <li>TLS 4B - Check Probe Sr. No. it’s correct or 000000. (In Setup then Devices)</li>
                <li>In Diagnostics/Probe/Overview menu check Probe data for send and received.</li>
                <li>Inventory report for last 15 days to be downloaded</li>
                <li>Alarm Report for last 15 days to be downloaded for any Probe behavior</li>
                <li>Event log report for last 15 days to correlate with Alarm report and FCC Uptime</li>
                <li>Tank Truck Receipts report if any dummy receipt captured or post decantation what was the max height captured for product</li>
            </ol>
        </div>
    </div>

    <div class="login-container" id="loginContainer" role="form" aria-labelledby="loginHeader">
        <h2 id="loginHeader">Login</h2>
        <input type="text" id="username" placeholder="Username" required aria-required="true" aria-label="Username">
        <input type="password" id="password" placeholder="Password" required aria-required="true" aria-label="Password">
        <button id="loginButton" aria-label="Login"><i class="fas fa-sign-in-alt"></i> Login</button>
        <div class="loading-indicator" id="loadingIndicator"><i class="fas fa-spinner fa-spin"></i> Loading...</div>
        <div id="loginMessage" class="error-message" role="alert"></div>
    </div>

    <div class="notice-board" id="noticeBoard" role="region" aria-labelledby="noticeBoardTitle">
        <div class="notice-title" id="noticeBoardTitle">Notice Board</div>
        <div class="notice-content">
            <div class="notice">1. VR ATG Probe follow the instruction of consumption</div>
            <div class="notice">2. Probe installation upload the Snaps</div>
            <div class="notice">3. HPCL ITPS Verification With L1 & HPCL ITPS Transaction History.</div>
            <div class="notice">4. HPCL, IOCL, BPCL And NAYARA New Software Need to Update On All Sites</div>
            <div class="notice">5. Take All Sites Access Details with ID And Password.</div>
        </div>
    </div>

    <div class="updates-board" id="updatesBoard" role="region" aria-labelledby="updatesBoardTitle">
        <div class="update-title" id="updatesBoardTitle">Upcoming Updates</div>
        <div class="update" id="update1">1. Critical Material Rank</div>
        <div class="update" id="update2">2. UPS Repair SOP Updated</div>
        <div class="update" id="update3">3. Software Status</div>
        <div class="update" id="update4">4. Assessments Test Ranking Status Updated </div>
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
            <div class="mandatory-item" id="hpclVendor"> 
                <a href="https://drive.google.com/file/d/1ac418hLzLG4-FYYqEtTccZMU1E1X-dpW/view?usp=sharing" target="_blank">Critical Part Validation</a>
            </div>
            <div class="mandatory-item" id="bpclBLNo">
                <a href="#" id="teamViewerId">TeamViewer Id</a>
            </div>
            <div class="mandatory-item" id="hpclItpsVendor"> <a href="#">HPCL itps vender</a></div>
            <div class="mandatory-item" id="bpclBL"> <a href="#">BPCL BL No.</a></div>
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
        <button id="loginIcon" title="Login" aria-label="Login"><i class="fas fa-sign-in-alt"></i></button>
        <button class="logout-button" id="logoutIcon" title="Logout" aria-label="Logout"><i class="fas fa-sign-out-alt"></i></button>
    </div>

    <!-- Dark Green Icon -->
    <button class="dark-green-icon" id="darkGreenIcon" title="Assisment Test Rank" style="display: none;" aria-label="Assessment Test Rank">
        <i class="fas fa-search"></i>
    </button>

    <!-- Search Data Popup -->
    <div class="popup" id="searchDataPopup" role="dialog" aria-labelledby="searchDataTitle" aria-modal="true">
        <div class="popup-content">
            <h2 id="searchDataTitle">Search Data</h2>
            <input type="text" id="fseTeamId" placeholder="FSE Team Id" aria-label="FSE Team Id" />
            <input type="text" id="fsePersonId" placeholder="FSE Person Id" aria-label="FSE Person Id" />
            <input type="text" id="employeeCode" placeholder="Employee Code" aria-label="Employee Code" />
            <button id="searchButton" aria-label="Search"><i class="fas fa-search"></i> Search</button>
            <div class="loading-indicator" id="searchLoadingIndicator"><i class="fas fa-spinner fa-spin"></i> Loading...</div>
            <button id="closeSearchPopup" aria-label="Close Search Popup">Close</button>
            <div class="result-box" id="searchResult" style="display: none;"></div>
            <div class="error-message" id="searchErrorMessage" role="alert"></div>
        </div>
    </div>

    <!-- New Popup for TeamViewer Input -->
    <div class="popup" id="teamViewerPopup" role="dialog" aria-labelledby="teamViewerTitle" aria-modal="true">
        <div class="popup-content">
            <h2 id="teamViewerTitle">Enter TeamViewer Details</h2>
            <input type="text" id="roCodeInput" placeholder="Ro Code" required aria-required="true" aria-label="Ro Code">
            <input type="text" id="roNameInput" placeholder="Ro Name" required aria-required="true" aria-label="Ro Name">
            <input type="text" id="teamViewerIdInput" placeholder="TeamViewer Id" required aria-required="true" aria-label="TeamViewer Id">
            <input type="password" id="teamViewerPassInput" placeholder="TeamViewer Password" required aria-required="true" aria-label="TeamViewer Password">
            <input type="password" id="adminPassInput" placeholder="Admin Password" required aria-required="true" aria-label="Admin Password">
            <button id="submitTeamViewerDetails" aria-label="Submit TeamViewer Details"><i class="fas fa-paper-plane"></i> Submit</button>
            <button id="closeTeamViewerPopup" aria-label="Close TeamViewer Popup">Close</button>
            <div class="result-box" id="teamViewerResultMessage" style="display: none;"></div>
        </div>
    </div>

    <!-- New Confirmation Popup -->
    <div class="confirmation-popup" id="confirmationPopup" role="dialog" aria-labelledby="confirmationTitle" aria-modal="true">
        <div class="confirmation-popup-content">
            <h2 id="confirmationTitle">Data Submitted</h2>
            <p>Thank You for Support</p>
            <button id="closeConfirmationPopup" aria-label="Close Confirmation Popup">Close</button>
        </div>
    </div>

    <!-- Popup for Ro Code Entry -->
    <div class="popup" id="roCodePopup" role="dialog" aria-labelledby="roCodeTitle" aria-modal="true">
        <div class="popup-content">
            <h2 id="roCodeTitle">Enter Ro Code</h2>
            <input type="text" id="roCode" placeholder="Ro Code" required aria-required="true" aria-label="Ro Code">
            <button id="submitRoCode" aria-label="Submit Ro Code"><i class="fas fa-paper-plane"></i> Submit</button>
            <button id="closePopup" aria-label="Close Ro Code Popup">Close</button>
            <div class="result-box" id="resultMessage" style="display: none;"></div>
        </div>
    </div>

    <script>
        const loginButton = document.getElementById('loginButton');
        const loginIcon = document.getElementById('loginIcon');
        const logoutIcon = document.getElementById('logoutIcon');
        const mainContent = document.getElementById('mainContent');
        const sopContent = document.getElementById('sopContent');
        const loginContainer = document.getElementById('loginContainer');
        const loginMessage = document.getElementById('loginMessage');
        const noticeBoard = document.getElementById('noticeBoard');
        const updatesBoard = document.getElementById('updatesBoard');
        const notices = document.querySelectorAll('.notice');
        const criticalProbeSnaps = document.getElementById('criticalProbeSnaps');
        const criticalProbeContent = document.getElementById('criticalProbeContent');
        const toggleArrow = document.getElementById('toggleArrow');

        // Loading indicators
        const loadingIndicator = document.getElementById('loadingIndicator');
        const searchLoadingIndicator = document.getElementById('searchLoadingIndicator');
        const searchErrorMessage = document.getElementById('searchErrorMessage');

        // Dark Green Icon functionality
        const darkGreenIcon = document.getElementById('darkGreenIcon');
        const searchDataPopup = document.getElementById('searchDataPopup');
        const closeSearchPopup = document.getElementById('closeSearchPopup');
        const searchButton = document.getElementById('searchButton');
        const searchResult = document.getElementById('searchResult');

        // Data for searching
        const data = [
            { "FSE Team Id": "OIRJFSE14", "FSE Person Id": "VIJENDRAS", "Employee Code": "3256829", "Percentage": 60, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE27", "FSE Person Id": "CHETANP", "Employee Code": "3256856", "Percentage": 57, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE23", "FSE Person Id": "AMITP", "Employee Code": "3256914", "Percentage": 73, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE03", "FSE Person Id": "YOGESHKS", "Employee Code": "3257267", "Percentage": 70, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE25", "FSE Person Id": "MADHUK", "Employee Code": "3256818", "Percentage": 80, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE13", "FSE Person Id": "ARJUNT", "Employee Code": "3256825", "Percentage": 73, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE18", "FSE Person Id": "MAHESHKS", "Employee Code": "3256839", "Percentage": 73, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE29", "FSE Person Id": "MAHENDRAP", "Employee Code": "3256850", "Percentage": 77, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE21", "FSE Person Id": "HITESHS", "Employee Code": "3256949", "Percentage": 77, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE02", "FSE Person Id": "SAVANR", "Employee Code": "3256855", "Percentage": 77, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE01", "FSE Person Id": "N/A", "Employee Code": "A092478692", "Percentage": 53, "Year Points": 2 },
    { "FSE Team Id": "OIRJFSE34", "FSE Person Id": "BLKISHANA", "Employee Code": "A092479411", "Percentage": 50, "Year Points": 2 },
    { "FSE Team Id": "OIRJFSE28", "FSE Person Id": "VINODKB", "Employee Code": "3256875", "Percentage": 70, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE16", "FSE Person Id": "SUKHMANDERS", "Employee Code": "100546790", "Percentage": 90, "Year Points": 5 },
    { "FSE Team Id": "OIRJFSE33", "FSE Person Id": "PIYUSHS", "Employee Code": "3256846", "Percentage": 70, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE31", "FSE Person Id": "ARJUNN", "Employee Code": "3368696", "Percentage": 67, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE24", "FSE Person Id": "Bherudl", "Employee Code": "3256944", "Percentage": 83, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE03", "FSE Person Id": "ALOKS", "Employee Code": "3256886", "Percentage": 87, "Year Points": 5 },
    { "FSE Team Id": "OIRJFSE12", "FSE Person Id": "PRATAPS", "Employee Code": "3256945", "Percentage": 77, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE05", "FSE Person Id": "RAVIKANTS", "Employee Code": "3256889", "Percentage": 73, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE19", "FSE Person Id": "PAWANKM", "Employee Code": "3256874", "Percentage": 77, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE09", "FSE Person Id": "PANKAJS", "Employee Code": "3256887", "Percentage": 73, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE01", "FSE Person Id": "SURAJB", "Employee Code": "3256912", "Percentage": 77, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE08", "FSE Person Id": "JAIS", "Employee Code": "3256923", "Percentage": 60, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE11", "FSE Person Id": "SHAITANS", "Employee Code": "3256895", "Percentage": 53, "Year Points": 3 },
    { "FSE Team Id": "OIRJFSE22", "FSE Person Id": "SURENDARBC", "Employee Code": "3601764", "Percentage": 77, "Year Points": 4 },
    { "FSE Team Id": "OIRJFSE15", "FSE Person Id": "GOPALS", "Employee Code": "3256827", "Percentage": 50, "Year Points": 2 },
    { "FSE Team Id": "OIRJFSE35", "FSE Person Id": "HITESHB", "Employee Code": "3637536", "Percentage": 0, "Year Points": 0 },
    { "FSE Team Id": "OIRJFSE07", "FSE Person Id": "ALAMERK", "Employee Code": "3256870", "Percentage": 67, "Year Points": 3 }
// Add more entries as needed...
        ];

        // Show the search data popup when the icon is clicked
        darkGreenIcon.onclick = function() {
            searchDataPopup.style.display = 'flex';
        };

        // Close the search popup
        closeSearchPopup.onclick = function() {
            searchDataPopup.style.display = 'none';
            document.getElementById('fseTeamId').value = '';
            document.getElementById('fsePersonId').value = '';
            document.getElementById('employeeCode').value = '';
            searchResult.style.display = 'none'; // Hide result box
            searchErrorMessage.style.display = 'none'; // Hide error message
        };

        // Perform the search when the search button is clicked
        searchButton.onclick = function() {
            const fseTeamId = document.getElementById('fseTeamId').value;
            const fsePersonId = document.getElementById('fsePersonId').value;
            const employeeCode = document.getElementById('employeeCode').value;

            // Show loading indicator
            searchLoadingIndicator.style.display = 'block';
            searchResult.style.display = 'none'; // Hide result box
            searchErrorMessage.style.display = 'none'; // Hide error message

            // Simulate a delay for loading (remove this in production)
            setTimeout(() => {
                const filteredData = data.filter(item => 
                    (fseTeamId ? item["FSE Team Id"] === fseTeamId : true) &&
                    (fsePersonId ? item["FSE Person Id"] === fsePersonId : true) &&
                    (employeeCode ? item["Employee Code"] === employeeCode : true)
                );

                // Hide loading indicator
                searchLoadingIndicator.style.display = 'none';

                if (filteredData.length > 0) {
                    searchResult.style.display = 'block';
                    searchResult.innerHTML = filteredData.map(item => 
                        `FSE Team Id: ${item["FSE Team Id"]}, FSE Person Id: ${item["FSE Person Id"]}, Employee Code: ${item["Employee Code"]}, Percentage: ${item.Percentage}, Year Points: ${item["Year Points"]}`
                    ).join('<br>');
                } else {
                    searchErrorMessage.style.display = 'block';
                    searchErrorMessage.textContent = 'No results found.';
                }
            }, 1000); // Simulated loading time
        };

        // Popup functionality for TeamViewer Id
        const teamViewerPopup = document.getElementById('teamViewerPopup');
        const teamViewerIdLink = document.getElementById('teamViewerId');
        const closeTeamViewerPopup = document.getElementById('closeTeamViewerPopup');
        const submitTeamViewerDetails = document.getElementById('submitTeamViewerDetails');
        const teamViewerResultMessage = document.getElementById('teamViewerResultMessage');

        // Show the TeamViewer popup when the link is clicked
        teamViewerIdLink.onclick = function() {
            teamViewerPopup.style.display = 'flex';
        };

        // Close the TeamViewer popup
        closeTeamViewerPopup.onclick = function() {
            teamViewerPopup.style.display = 'none';
            // Clear input fields
            document.getElementById('roCodeInput').value = '';
            document.getElementById('roNameInput').value = '';
            document.getElementById('teamViewerIdInput').value = '';
            document.getElementById('teamViewerPassInput').value = '';
            document.getElementById('adminPassInput').value = '';
            teamViewerResultMessage.style.display = 'none'; // Hide result message box
        };

        // Show the confirmation popup after successful submission
        submitTeamViewerDetails.onclick = function() {
            const roCode = document.getElementById('roCodeInput').value;
            const roName = document.getElementById('roNameInput').value;
            const teamViewerId = document.getElementById('teamViewerIdInput').value;
            const teamViewerPass = document.getElementById('teamViewerPassInput').value;
            const adminPass = document.getElementById('adminPassInput').value;

            if (roCode && roName && teamViewerId && teamViewerPass && adminPass) {
                fetch('https://script.google.com/macros/s/AKfycbxE8qSguwe_0RHkAM0BokcWSKG2Ic-xVBmwVAoB5M2Z0EI7vV9AzbvkAk8fuWA-gcs/exec', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/x-www-form-urlencoded'
                    },
                    body: new URLSearchParams({
                        roCode: roCode,
                        roName: roName,
                        teamViewerId: teamViewerId,
                        teamViewerPass: teamViewerPass,
                        adminPass: adminPass
                    })
                })
                .then(response => response.json())
                .then(data => {
                    teamViewerResultMessage.style.display = 'block';
                    teamViewerResultMessage.textContent = data.result; // Assuming the Apps Script returns a JSON object with a 'result' key
                    teamViewerResultMessage.style.color = 'green';

                    // Show confirmation popup
                    document.getElementById('confirmationPopup').style.display = 'flex';

                    // Reset input fields
                    document.getElementById('roCodeInput').value = '';
                    document.getElementById('roNameInput').value = '';
                    document.getElementById('teamViewerIdInput').value = '';
                    document.getElementById('teamViewerPassInput').value = '';
                    document.getElementById('adminPassInput').value = '';
                })
                .catch(error => {
                    console.error('Error:', error);
                    teamViewerResultMessage.style.display = 'block';
                    teamViewerResultMessage.textContent = 'An error occurred. Please try again.';
                    teamViewerResultMessage.style.color = 'red';
                });
            } else {
                teamViewerResultMessage.style.display = 'block';
                teamViewerResultMessage.textContent = 'Please fill in all fields.';
                teamViewerResultMessage.style.color = 'red';
            }
        };

        // Close the confirmation popup
        document.getElementById('closeConfirmationPopup').onclick = function() {
            document.getElementById('confirmationPopup').style.display = 'none';
        };

        // Existing Popup functionality for Ro Code Entry
        const roCodePopup = document.getElementById('roCodePopup');
        const submitRoCode = document.getElementById('submitRoCode');
        const closePopup = document.getElementById('closePopup');
        const resultMessage = document.getElementById('resultMessage');

        document.getElementById('hpclItpsVendor').onclick = function() {
            roCodePopup.style.display = 'flex';
        };

        closePopup.onclick = function() {
            roCodePopup.style.display = 'none';
            document.getElementById('roCode').value = ''; // Clear input
            resultMessage.style.display = 'none'; // Hide result message box
        };

        const roData = [
                                    { "RoCode": "118767", "Result": "RAJKAMAL ENTERPRISES-2001849" },
    { "RoCode": "119967", "Result": "NAWAL KISHORE & CO-2008500" },
    { "RoCode": "143802", "Result": "JAIRAJ & COMPANY-2004245" },
    { "RoCode": "183221", "Result": "BP RAJGARH-2008551" },
    { "RoCode": "190851", "Result": "SAI BP-2014318" },
    { "RoCode": "115540", "Result": "RODHILAL NANDLAL CHAUDHRY-2001807" },
    { "RoCode": "118761", "Result": "KAWAI FILLING STATION-2001844" },
    { "RoCode": "119154", "Result": "AGRAWAL FILLING CENTER-2008419" },
    { "RoCode": "119156", "Result": "AZAD FILLING STATION-2008421" },
    { "RoCode": "119160", "Result": "A.R. DHANIRAM KALYANDAS-2008425" },
    { "RoCode": "119163", "Result": "GOPAL DASS & SONS-2008428" },
    { "RoCode": "119166", "Result": "GUPTA SERVICE STATION-2008431" },
    { "RoCode": "119169", "Result": "KALA & COMPANY-2008434" },
    { "RoCode": "119173", "Result": "HARI SINGH & SONS-2008438" },
    { "RoCode": "119179", "Result": "PREMCHAND KISHANCHAND JAIN-2008444" },
    { "RoCode": "119191", "Result": "SURESH FILLING STATION-2008456" },
    { "RoCode": "119193", "Result": "JAGANNATH FILLING CENTRE-2008458" },
    { "RoCode": "119925", "Result": "GANGARAM JAMNADHAR-2008462" },
    { "RoCode": "119926", "Result": "HARI OM FILLING STATION-2008463" },
    { "RoCode": "119932", "Result": "KALYAN SERVICE STATION-2008468" },
    { "RoCode": "119933", "Result": "KAMAL MANI FUEL SERVICES-2008469" },
    { "RoCode": "119943", "Result": "SHEKHAWATI FILLING STATION-2008479" },
    { "RoCode": "119953", "Result": "FAUJI BHAI-2008488" },
    { "RoCode": "119964", "Result": "MOZMABAD FILLING STATION-2008498" },
    { "RoCode": "119978", "Result": "SHRI KRISHAN FILLING CENTRE-2008509" },
    { "RoCode": "119980", "Result": "CHAMANLAL MOHINDER PRATAP-2004129" },
    { "RoCode": "119982", "Result": "GANGA DHAR MOHANLAL-2004131" },
    { "RoCode": "119983", "Result": "GAURISHANKAR FILLING STATION-2004132" },
    { "RoCode": "119987", "Result": "JAI KISSAN FILLING STATION-2004136" },
    { "RoCode": "120003", "Result": "PILI BANGAN FILLING STATION-2004151" },
    { "RoCode": "120006", "Result": "PRAKASH SINGH JASBIR SINGH-2004154" },
    { "RoCode": "120009", "Result": "SHIV FILLING STATION-2008510" },
    { "RoCode": "120169", "Result": "HIMMAT PETROL SERVICE-2004172" },
    { "RoCode": "120178", "Result": "SHRI KARNI PETROLEUM SERVICE-2004180" },
    { "RoCode": "120181", "Result": "BHATIYANI FILLING STATION-2004182" },
    { "RoCode": "120187", "Result": "SAINIK FILLING STN-2004186" },
    { "RoCode": "120190", "Result": "BHAGAWATI FILLING STATION-2004187" },
    { "RoCode": "120196", "Result": "AUWA AUTOMOBILES-2004192" },
    { "RoCode": "120199", "Result": "MAHAKALI FILLING STATION-2004195" },
    { "RoCode": "120202", "Result": "JAI FILLING STATION-2004197" },
    { "RoCode": "120213", "Result": "SURENDRAKUMAR JINENDRAKUMAR-2004206" },
    { "RoCode": "120248", "Result": "SUPREME PETROLEUM-2001868" },
    { "RoCode": "120252", "Result": "KISAN DIESEL SERVICE-2004215" },
    { "RoCode": "120253", "Result": "RATHI FILLING STATION-2004216" },
    { "RoCode": "120254", "Result": "SWATANTRATA SENANI FLG STN-2004217" },
    { "RoCode": "120255", "Result": "SHYAM DIESELS-2004218" },
    { "RoCode": "120257", "Result": "PAGARIA FILLING STATION-2004220" },
    { "RoCode": "120995", "Result": "VEER ARJUN FILLING STATION-2004221" },
    { "RoCode": "120997", "Result": "SAHID BANWARI FILLING STATION-2008513" },
    { "RoCode": "122755", "Result": "SHRI SHYAM PETROLEUM-2008514" },
    { "RoCode": "132747", "Result": "SHAHEED BIRENDRA FILLING STATI-2008518" },
    { "RoCode": "135391", "Result": "HIMMAT PETROL SERVICE-2004228" },
    { "RoCode": "136067", "Result": "SWATANTRTA SANGRAM SAINANI FLG-2001881" },
    { "RoCode": "139070", "Result": "PUROHIT FILLING STATION-2008525" },
    { "RoCode": "139311", "Result": "KHETESHWAR FILLING STATION-2004231" },
    { "RoCode": "140903", "Result": "KASWA FINLEASE PVT.LTD.-2008529" },
    { "RoCode": "141303", "Result": "M.S.TRANSPORT CO.-2008533" },
    { "RoCode": "141315", "Result": "C R HIGHWAY SERVICES-2004237" },
    { "RoCode": "141742", "Result": "S.R.PETROL PUMP-2004238" },
    { "RoCode": "141874", "Result": "JODHANA FILLING STATION-2001890" },
    { "RoCode": "142108", "Result": "CHANDKHERI ROAD CARRIERS-2001892" },
    { "RoCode": "142168", "Result": "RAMNIWAS VIJAY VARGIYA-2008538" },
    { "RoCode": "142730", "Result": "GARG TRANSPORT COMPANY-2008540" },
    { "RoCode": "142836", "Result": "RAJKAMAL BORING COMPANY-2001893" },
    { "RoCode": "143027", "Result": "JAI AMBE ENTERPRISES-2001894" },
    { "RoCode": "144652", "Result": "SHREE GANESH FILLING STATION-2001897" },
    { "RoCode": "145305", "Result": "PUNIA FILLING STATION-2004250" },
    { "RoCode": "145351", "Result": "SR PETROLEUM-2004252" },
    { "RoCode": "145544", "Result": "SAMBARIYA FILLING STATION-2001903" },
    { "RoCode": "145551", "Result": "DEEGWAL FILLING STATION-2001907" },
    { "RoCode": "145782", "Result": "SHRI KANHAIYA FILLING STATION-2001910" },
    { "RoCode": "145851", "Result": "BALAJI FILLING STATION-2004258" },
    { "RoCode": "145853", "Result": "B.P. FUEL-2004260" },
    { "RoCode": "145875", "Result": "PREM FILLING STATION-2008550" },
    { "RoCode": "146085", "Result": "SRI PIPLESHWAR AUTOMOBILES-2004262" },
    { "RoCode": "146234", "Result": "MALANI FILLING STATION-2004263" },
    { "RoCode": "146334", "Result": "JAGDAMBA FILLING STATION-2008555" },
    { "RoCode": "146335", "Result": "BHAGWAN FILLING STATION-2008556" },
    { "RoCode": "146804", "Result": "BANAS PETROLEUM-2001916" },
    { "RoCode": "146828", "Result": "GOKHRU FILLING STN-2001917" },
    { "RoCode": "146883", "Result": "ARUN FILLING STATION-2004264" },
    { "RoCode": "146885", "Result": "CHAUDHRY PETROL PUMP-2004266" },
    { "RoCode": "146979", "Result": "LEKH RAM BHADOO-2004267" },
    { "RoCode": "147330", "Result": "LAXMI PETROLEUM-2004271" },
    { "RoCode": "147549", "Result": "PARMAR FILLING STATION-2001923" },
    { "RoCode": "147550", "Result": "AMAR FILLING STATION-2001924" },
    { "RoCode": "147571", "Result": "SHIV-SHAKTI FILLING STATION-2001925" },
    { "RoCode": "148031", "Result": "SHRI MAHADEV FUELS-2004274" },
    { "RoCode": "148106", "Result": "KISAN BHARAT FILLING STATION-2008565" },
    { "RoCode": "148207", "Result": "BANSAL FILLING STATION-2008566" },
    { "RoCode": "148208", "Result": "SHREE GANPATI FILLING STATION-2008567" },
    { "RoCode": "148209", "Result": "SHRI BALAJI FILLING STATION-2008568" },
    { "RoCode": "148530", "Result": "VINAYAK PETROLEUM (NRL)-2008571" },
    { "RoCode": "148663", "Result": "BHAMBU FILLING STN-2004278" },
    { "RoCode": "148753", "Result": "JYOTI FILLING STATION-2004279" },
    { "RoCode": "149067", "Result": "ROOPESHWARI FILLING STATION-2001928" },
    { "RoCode": "149243", "Result": "PATODI FILLING STATION-2004282" },
    { "RoCode": "149244", "Result": "S.K. FILLING STATION-2004283" },
    { "RoCode": "149326", "Result": "PUROHIT SERVICE STATION-2004285" },
    { "RoCode": "149416", "Result": "AGRAWAL SERVICE CENTRE-2008578" },
    { "RoCode": "149420", "Result": "PACHWARA FILLING STATION-2008580" },
    { "RoCode": "149440", "Result": "DIXIT FILLING STATION-2008581" },
    { "RoCode": "149702", "Result": "DURGA PETROLEUM-2008583" },
    { "RoCode": "149703", "Result": "HETUMSAR FILLING STATION-2008584" },
    { "RoCode": "149706", "Result": "JAI BAJRANG BALI SERVICE STATI-2008587" },
    { "RoCode": "149707", "Result": "PARASNATH FILLING STATION-2008588" },
    { "RoCode": "149720", "Result": "BALAJI SERVICE STATION-2008590" },
    { "RoCode": "150610", "Result": "SOLANKI FILLING STATION (NRL)-2008592" },
    { "RoCode": "150736", "Result": "OM ENERGY STATION (NRL)-2008593" },
    { "RoCode": "150913", "Result": "AMAN AUTOMOBILES (NRL)-2008594" },
    { "RoCode": "151107", "Result": "MAHAMAYA SERVICE STATION-2008596" },
    { "RoCode": "153231", "Result": "AMBAY FILLING STATION-2008597" },
    { "RoCode": "153241", "Result": "DEVNARAYAN FILLING STATION-2004292" },
    { "RoCode": "154119", "Result": "SHRI MAHADEV FILLING STATION-2004295" },
    { "RoCode": "154492", "Result": "BABA RAMDEV FILLING STATION-2004296" },
    { "RoCode": "154599", "Result": "JAGARWAD RETAILS & AUTOMOBILES-2008598" },
    { "RoCode": "154735", "Result": "HARDIK FILLING STATION-2008599" },
    { "RoCode": "154988", "Result": "SANWALIYA FILLING STATION-2001930" },
    { "RoCode": "154992", "Result": "SHREE BALAJI FILLING STATION-2001931" },
    { "RoCode": "155419", "Result": "PRAKASH FILLING STATION-2001933" },
    { "RoCode": "155605", "Result": "VYAS FILLING CENTRE-2008600" },
    { "RoCode": "155857", "Result": "MANISHA FILLING STATION-2008601" },
    { "RoCode": "156015", "Result": "SIDDHI VINAYAK PETROLEUM-2004301" },
    { "RoCode": "156081", "Result": "KHETANATH FILLING STATION-2004303" },
    { "RoCode": "157233", "Result": "SUPREME FUEL SUPPLIERS-2008607" },
    { "RoCode": "157309", "Result": "SHREE GIRIRAJDHARAN FILLING ST-2001937" },
    { "RoCode": "157448", "Result": "R.K. SERVICE STATION-2008608" },
    { "RoCode": "157888", "Result": "PAWAN PUTRA FILLING STATION-2001938" },
    { "RoCode": "158419", "Result": "BHAGWANA RAM FILLING STATION-2004310" },
    { "RoCode": "158477", "Result": "AAI MATA FILLING STATION-2004311" },
    { "RoCode": "158631", "Result": "ARCHAN FILLING STATION-2008612" },
    { "RoCode": "158635", "Result": "MINESH FILLING STATION-2008613" },
    { "RoCode": "159060", "Result": "TATHAGAT FILLING STATION-2001940" },
    { "RoCode": "160037", "Result": "HARSHWAL FILLING STATION-2008615" },
    { "RoCode": "161318", "Result": "ASHOK FILLING STATION-2008617" },
    { "RoCode": "164052", "Result": "SHIV SHAKTI FUELS-2001949" },
    { "RoCode": "164113", "Result": "K R BERWAL & SONS-2004316" },
    { "RoCode": "165365", "Result": "GAYATRI FUELS-2008620" },
    { "RoCode": "167175", "Result": "RAMAPEER FILLING STATION-2004317" },
    { "RoCode": "167176", "Result": "SRINATH FILLING STATION-2004318" },
    { "RoCode": "167202", "Result": "POKRAN FILLING CENTRE-2004319" },
    { "RoCode": "167623", "Result": "SHREE VINAYAK PETROLEUM-2001954" },
    { "RoCode": "167986", "Result": "MARWAR FILLING STATION-2004320" },
    { "RoCode": "168829", "Result": "GOYAL FILLING STATION-2008626" },
    { "RoCode": "170744", "Result": "SHREE KAYA VARNESHWAR FILLING-2001961" },
    { "RoCode": "170765", "Result": "PADRU FILLING STATION-2004325" },
    { "RoCode": "171218", "Result": "SIDDHI VINAYAK FILLING STATION-2001965" },
    { "RoCode": "171318", "Result": "RIDHI SIDHI PETROLEUM-2004328" },
    { "RoCode": "172166", "Result": "FULMUKTESHWAR PETROLEUM-2004332" },
    { "RoCode": "172416", "Result": "MAHALAXMI FILLING STATION-2008630" },
    { "RoCode": "172714", "Result": "ROYAL FILLING STATION-2001971" },
    { "RoCode": "172984", "Result": "KHUSHI FILLING STATION-2008632" },
    { "RoCode": "173248", "Result": "RAJESH FILLING STATION-2004338" },
    { "RoCode": "173249", "Result": "NEHRA FILLING STATION-2004339" },
    { "RoCode": "173435", "Result": "BHAWANI FILLING STATION-2004341" },
    { "RoCode": "173558", "Result": "KHETANI FILLING STATION-2004342" },
    { "RoCode": "173805", "Result": "GOYAL FUEL POINT-2002145" },
    { "RoCode": "174039", "Result": "RATANLAL GODARA DIESEL PUMP-2004344" },
    { "RoCode": "174654", "Result": "SHIVSHAKTI FUEL CENTRE-2009579" },
    { "RoCode": "174842", "Result": "MAA BAYAN FILLING STATION-2002410" },
    { "RoCode": "175119", "Result": "GURUKRIPA AUTO FUELS-2009577" },
    { "RoCode": "175599", "Result": "RATHORE TRANSPORT COMPANY-2010568" },
    { "RoCode": "176294", "Result": "ROYAL FILLING STATION-2005939" },
    { "RoCode": "176329", "Result": "CHANDRAWET DVS PETRO SERVICE-2006316" },
    { "RoCode": "176333", "Result": "SIDDHI VINAYAK FILLING STATION-2010362" },
    { "RoCode": "176524", "Result": "JAMNALAL FILLING STATION-2009978" },
    { "RoCode": "176526", "Result": "DEVNARAIN FILLING STATION-2010459" },
    { "RoCode": "176802", "Result": "RAJ FILLING STATION-2010449" },
    { "RoCode": "177632", "Result": "JEET FILLING STATION-2010555" },
    { "RoCode": "177654", "Result": "LAXMI FILLING STATION-2011474" },
    { "RoCode": "177916", "Result": "NARAYAN FUEL STATION-2010678" },
    { "RoCode": "177950", "Result": "NATIONAL SERVICE STATION-2010655" },
    { "RoCode": "177952", "Result": "GOYAL PETROLEUM-2010677" },
    { "RoCode": "178119", "Result": "ARJUN AUTO FUELS-2010991" },
    { "RoCode": "178224", "Result": "SHREE RADHA BHAGWAN FILLING ST-2010681" },
    { "RoCode": "178517", "Result": "ROOP RAJAT FILLING STATION-2011255" },
    { "RoCode": "179014", "Result": "KUMAWAT PETROLEUM-2011222" },
    { "RoCode": "179045", "Result": "CHITAWA FILLING STATION-2011334" },
    { "RoCode": "179046", "Result": "JAY FILLING STATION-2011411" },
    { "RoCode": "179074", "Result": "RANJEET FILLING STATION-2011335" },
    { "RoCode": "179284", "Result": "ATHARVA FILLING STATION-2011416" },
    { "RoCode": "179285", "Result": "PARAMPREM FILLING STATION-2011417" },
    { "RoCode": "179459", "Result": "MARWAR FILLING STATION-2011539" },
    { "RoCode": "179530", "Result": "DADHIMATI FILLING STATION-2011538" },
    { "RoCode": "179755", "Result": "MATESHWARI FILLING STATION-2011502" },
    { "RoCode": "179898", "Result": "MOGAR FILLING STATION-2011788" },
    { "RoCode": "179903", "Result": "ASWAL FILLING STATION-2011789" },
    { "RoCode": "179998", "Result": "AJAY FILLING STATION-2011676" },
    { "RoCode": "180051", "Result": "RADHA NARAYAN PETROLEUM-2011254" },
    { "RoCode": "180194", "Result": "DEV FILLING CENTER-2011692" },
    { "RoCode": "180248", "Result": "GANGA PETROLEUM-2011867" },
    { "RoCode": "180428", "Result": "AKSHAR PETROLEUM-2011889" },
    { "RoCode": "180452", "Result": "SANWLA FILLING STATION-2011697" },
    { "RoCode": "180461", "Result": "PRAJAPATI FILLING STATION-2011758" },
    { "RoCode": "180511", "Result": "NAGAR PETRO STATION-2011657" },
    { "RoCode": "180517", "Result": "SHREE SALASAR BALAJI-2012016" },
    { "RoCode": "180580", "Result": "RANSI FUEL SERVICES-2011964" },
    { "RoCode": "180581", "Result": "SHREE BABA RAMDEV FILLING STAT-2011962" },
    { "RoCode": "181322", "Result": "JAI JUNA BABA FILLING STATION-2012199" },
    { "RoCode": "181603", "Result": "JOSHI PETROLEUM-2012283" },
    { "RoCode": "182200", "Result": "SHREE BALAJI PETROLEUM-2012537" },
    { "RoCode": "182525", "Result": "PRAHLADKA FILLING STATION-2012576" },
    { "RoCode": "182637", "Result": "RAJ BANGRA FILLING STATION-2012676" },
    { "RoCode": "182638", "Result": "SHREE JASWANT FILLING STATION-2012675" },
    { "RoCode": "182775", "Result": "VISHNU FILLING STATION-2012609" },
    { "RoCode": "183334", "Result": "GANPATI FILLING STATION-2012744" },
    { "RoCode": "183700", "Result": "SHREE LUMBARAM FILLING STATION-2012833" },
    { "RoCode": "183819", "Result": "SANMATI FILLING STATION-2012911" },
    { "RoCode": "184073", "Result": "VIKRAM PETROLEUM-2012961" },
    { "RoCode": "184199", "Result": "JSK FILLING STATION-2013042" },
    { "RoCode": "184200", "Result": "SAMRAT PETROLEUM-2013040" },
    { "RoCode": "184202", "Result": "VINAYAK FILLING STATION-2013006" },
    { "RoCode": "184248", "Result": "GANPATI PETROLEUM-2013021" },
    { "RoCode": "184269", "Result": "SHRI GOPAL FILLING STATION-2013044" },
    { "RoCode": "184353", "Result": "AISHWARYA FUEL HUB-2013034" },
    { "RoCode": "184583", "Result": "KRISHNA AUTO FUELS-2013104" },
    { "RoCode": "184959", "Result": "CHHOGALA SHYAM FILLING STATION-2013109" },
    { "RoCode": "185033", "Result": "YASHRATAN FILLING STATION-2013142" },
    { "RoCode": "185236", "Result": "SHRI ALVA MAA FILLING STATION-2013199" },
    { "RoCode": "185359", "Result": "SHREE BOHRA GANESH FILLING STA-2013148" },
    { "RoCode": "185390", "Result": "MANDALNATH AUTOMOBILES-2011412" },
    { "RoCode": "185590", "Result": "KARWASARA FILLING STATION-2013284" },
    { "RoCode": "185592", "Result": "MUSADDILAL FILLING STATION-2013262" },
    { "RoCode": "185593", "Result": "RUKMANI NAGAR FILLING STATION-2013158" },
    { "RoCode": "185768", "Result": "NARPAT PETROLEUM-2013165" },
    { "RoCode": "185832", "Result": "SHIVAM FILLING STATION-2013161" },
    { "RoCode": "185915", "Result": "MORAK FILLING STATION-2013160" },
    { "RoCode": "186063", "Result": "SHRI KOTADA BALAJI FILLING STA-2013437" },
    { "RoCode": "186149", "Result": "MATRRA PETROLEUM-2013243" },
    { "RoCode": "186359", "Result": "SHREEJI FILLING STATION-2013617" },
    { "RoCode": "186434", "Result": "AGWAAN FILLING STATION-2013508" },
    { "RoCode": "187017", "Result": "BHARDWAJ FILLING STATION-2013605" },
    { "RoCode": "187120", "Result": "G R FILLING STATION-2013583" },
    { "RoCode": "187124", "Result": "THAGARIA FILLING STATION-2013606" },
    { "RoCode": "187183", "Result": "HIRALAL BHATTAR PETROLEUMS-2013282" },
    { "RoCode": "187350", "Result": "GURU NANAK FUEL STATION-2013535" },
    { "RoCode": "187379", "Result": "MUKTESHWAR FILLING STATION-2013507" },
    { "RoCode": "187387", "Result": "BAJRANG PETROLEUM-2013783" },
    { "RoCode": "187499", "Result": "SHRI RAM HARSHAN PETROLEUM-2013440" },
    { "RoCode": "187642", "Result": "BURHANI FILLING STATION-2013849" },
    { "RoCode": "187793", "Result": "BASAWA PETROLEUM-2013264" },
    { "RoCode": "187794", "Result": "SHREE GOPAL FILLING STATION-2013870" },
    { "RoCode": "188117", "Result": "BHAGWANDAN KOJUDAN-2013794" },
    { "RoCode": "188157", "Result": "MEHTA FILLING STATION-2013382" },
    { "RoCode": "188286", "Result": "RAMESHWARI FILLING STATION-2012677" },
    { "RoCode": "188326", "Result": "BAROD FILLING STATION-2013936" },
    { "RoCode": "188369", "Result": "MANAK MOTI PETROLEUM-2013639" },
    { "RoCode": "188379", "Result": "KUBER FILLING STATION-2013671" },
    { "RoCode": "188488", "Result": "SHRI SAKAMBRI FILLING STATION-2013701" },
    { "RoCode": "188489", "Result": "DEVDARSHAN FILLING STATION-2013784" },
    { "RoCode": "188667", "Result": "SHRI GANESH FILLING STATION-2013931" },
    { "RoCode": "189026", "Result": "SHREE GANESH FILLING STATION-2013518" },
    { "RoCode": "189358", "Result": "VMAX PETROLEUM KANKROLI-2013586" },
    { "RoCode": "189548", "Result": "RAJASTHAN FUEL STATION-2013957" },
    { "RoCode": "189778", "Result": "SIRADHANA PETROLEUM-2014072" },
    { "RoCode": "189779", "Result": "MEHTA PETROLEUM-2014032" },
    { "RoCode": "189883", "Result": "K.L.M. FILLING STATION-2014161" },
    { "RoCode": "189897", "Result": "VAYU SAINIK FILLING STATION-2014169" },
    { "RoCode": "190034", "Result": "RATAN ENTERPRISES-2014115" },
    { "RoCode": "190035", "Result": "VARNIKA FILLING STATION-2014191" },
    { "RoCode": "190037", "Result": "ARADHYA PETROLEUM-2013534" },
    { "RoCode": "190108", "Result": "PACHAURI FILLING STATION-2013871" },
    { "RoCode": "190267", "Result": "SIDDHI VINAYAK PETROLEUM SERVI-2014071" },
    { "RoCode": "190321", "Result": "SHRI BALAJI SERVICE STATION-2014114" },
    { "RoCode": "190353", "Result": "SHRI RAM FILLING STATION-2014252" },
    { "RoCode": "190355", "Result": "SHREE DHARMRAJ PETROLEUM-2014089" },
    { "RoCode": "190363", "Result": "CHOUHAN PETROL PUMP-2013782" },
    { "RoCode": "190407", "Result": "SHIV KRIPA FILLING STATION-2014104" },
    { "RoCode": "190850", "Result": "BALAJI PETROLEUM-2014159" },
    { "RoCode": "190995", "Result": "MAS FINANCE & PETROLEUM-2014313" },
    { "RoCode": "190998", "Result": "BUNTY FUEL STATION,-2014329" },
    { "RoCode": "191227", "Result": "ALFA FUEL CENTRE-2014219" },
    { "RoCode": "191281", "Result": "KRISHNA AUTO FUELS-2014371" },
    { "RoCode": "191282", "Result": "PRITHVI FILLING STATION-2013840" },
    { "RoCode": "191851", "Result": "SHAHID BHAL SINGH FILLING STAT-2014470" },
    { "RoCode": "191879", "Result": "HARI OM PETROLEUM-2014582" },
    { "RoCode": "191970", "Result": "MAA MATESHWARI FUEL CENTER-2014463" },
    { "RoCode": "191989", "Result": "SHRI TANOT RAI FILLING STATION-2014393" },
    { "RoCode": "192275", "Result": "BALAJI PETROLEUM-2014370" },
    { "RoCode": "192391", "Result": "PANCHMUKHI FILLING STATION AND-2014665" },
    { "RoCode": "192425", "Result": "PINK CITY FUEL CENTRE-2014400" },
    { "RoCode": "192456", "Result": "SHREE BALAJI FILLING STATION-2014643" },
    { "RoCode": "192497", "Result": "MOOL SINGH SERVICE STATION-2014484" },
    { "RoCode": "192578", "Result": "SHRI SHAYAM FILLING STATION-2013438" },
    { "RoCode": "192850", "Result": "VEER TEJAJI FUEL STATION-2014735" },
    { "RoCode": "193133", "Result": "SHREE MANGILAL FILLING STATION-2014637" },
    { "RoCode": "193504", "Result": "DR.P.D.ARORA FUEL STATION-2014865" },
    { "RoCode": "193568", "Result": "KRISHNA FILLING STATION-2014642" },
    { "RoCode": "193592", "Result": "SHRI JAGDAMBA PETROLEUM-2014838" },
    { "RoCode": "194016", "Result": "SAINATH FILLING STATION-2015017" },
    { "RoCode": "194017", "Result": "BHAIRAV KRIPA PETROLEUM-2013937" },
    { "RoCode": "199112", "Result": "MATESHWARI FILLING CENTER-2008549" },
    { "RoCode": "219303", "Result": "VARDHMAN FILLING STATION-2020788" },
    { "RoCode": "219557", "Result": "DURGA FILLING STATION-2018833" },
    { "RoCode": "219640", "Result": "ROJHA FILLING STATION-2018221" },
    { "RoCode": "223762", "Result": "SANWARIYA FILLING STATION-2021398" },
    { "RoCode": "119994", "Result": "LAXMI OIL CO.-2004142" },
    { "RoCode": "190994", "Result": "SHRI PALIWAL FILLING STATION-2014119" },
    { "RoCode": "193502", "Result": "SHRI SAHADEV PETROLEUM-2014666" },
    { "RoCode": "16510910", "Result": "J.S FILLING STATION-Paytm" },
    { "RoCode": "16859970", "Result": "SANKHALA HP FILLING STATION-Paytm" },
    { "RoCode": "16595150", "Result": "HP FUEL STATION-Paytm" },
    { "RoCode": "16859660", "Result": "MAA PHITALAMATA FILLING STATIO-Paytm" },
    { "RoCode": "16859550", "Result": "ANANDILAL FILLING STATION-IMSL" },
    { "RoCode": "16859800", "Result": "VAIBHAV MULTIPURPOSE STATION-Paytm" },
    { "RoCode": "16595320", "Result": "SHRI GOVIND PETROLEUMS-Paytm" },
    { "RoCode": "16634170", "Result": "SAWAN BHARTI FILLING STATION-Paytm" },
    { "RoCode": "16634960", "Result": "NARAYAN FILLING STATION-Paytm" },
    { "RoCode": "16634970", "Result": "SETH SANWALIYA FILLING STATION-Paytm" },
    { "RoCode": "16634980", "Result": "VINAYAK FUEL CENTRE-Paytm" },
    { "RoCode": "16553810", "Result": "SHEKHAWATI TRANSPORT COMPANY-Paytm" },
    { "RoCode": "16594060", "Result": "TIRUPATI BALAJI FILLING STATIO-Paytm" },
    { "RoCode": "16595550", "Result": "SHREE JAGDISH FILLING STATION-Paytm" },
    { "RoCode": "16636300", "Result": "TODAWATA FILLING STATION-Paytm" },
    { "RoCode": "16636280", "Result": "SAHARAN HIDUSTHAN PETROLEUM-Paytm" },
    { "RoCode": "16634040", "Result": "LAKSHMA DEVI FILLING STATIOIN-Paytm" },
    { "RoCode": "16859700", "Result": "NIRMALA INDIA PETROLEUM-IMSL" },
    { "RoCode": "16595950", "Result": "KARAN FILLING STATION-Paytm" },
    { "RoCode": "16594560", "Result": "humra pump bhande balal ji-Paytm" },
    { "RoCode": "16567510", "Result": "KAMAKHYA KRISHNA SERVICE-Paytm" },
    { "RoCode": "16634010", "Result": "PINKCITY FUEL CENTER-Paytm" },
    { "RoCode": "16595710", "Result": "ALFA FILLING STATION-Paytm" },
    { "RoCode": "16859650", "Result": "RAJASTHAN FILLING STATION-Paytm" },
    { "RoCode": "16859570", "Result": "CALIBRE FILLING CENTER-IMSL" },
    { "RoCode": "16594540", "Result": "HUMARA PUMP KANVAR KA BAS-Paytm" },
    { "RoCode": "16635110", "Result": "NIRMALA PETROLEUM-Paytm" },
    { "RoCode": "16635180", "Result": "DEEPAK FUEL CENTRE-Paytm" },
    { "RoCode": "11544212", "Result": "MITTAL PETROLEUMS-Paytm" },
    { "RoCode": "11569022", "Result": "SERVICE CENTRE-Paytm" },
    { "RoCode": "16528810", "Result": "MEENA FILLING STATION-Paytm" },
    { "RoCode": "16594160", "Result": "KESAR FILLING CENTRE-Paytm" },
    { "RoCode": "16594360", "Result": "JAI SANTOSHI MAA FILLING STATI-Paytm" },
    { "RoCode": "16594580", "Result": "HUMARA PUMP TIGADIA MODE-Paytm" },
    { "RoCode": "16594630", "Result": "HAMARA PUMP AKODA-Paytm" },
    { "RoCode": "16636230", "Result": "SHRI KALYAN FILLING STATION-IMSL" },
    { "RoCode": "11568012", "Result": "AGARWAL MOTORS-Paytm" },
    { "RoCode": "16587030", "Result": "RADHA KRISHAN SERVICE STATION-Paytm" },
    { "RoCode": "16410910", "Result": "INDUS AGENCIES-IMSL" },
    { "RoCode": "16595680", "Result": "TIBRA HP-IMSL" },
    { "RoCode": "16859670", "Result": "PUSHPA FUELS STATION-IMSL" },
    { "RoCode": "16587040", "Result": "BAINADA SERVICE STATION-Paytm" },
    { "RoCode": "16634190", "Result": "NISHU FILLING STATION-Paytm" },
    { "RoCode": "16859780", "Result": "CHANDRA FILLING STATION-0" },
    { "RoCode": "16594050", "Result": "SAI FILLING STATION-Paytm" },
    { "RoCode": "16857210", "Result": "RAJAWAT HP CENTER-Paytm" },
    { "RoCode": "16859710", "Result": "SANKALP HP CENTRE-Paytm" },
    { "RoCode": "16859520", "Result": "AKASH FILLING STATION-Paytm" },
    { "RoCode": "16405510", "Result": "GAURAV FILLING STATION-Paytm" },
    { "RoCode": "16859680", "Result": "Rahi Filling Station-IMSL" },
    { "RoCode": "13920810", "Result": "AMAR SAHEED FILLING STATION-IMSL" },
    { "RoCode": "16764210", "Result": "ABHISHEK FILLING STN-Paytm" },
    { "RoCode": "16594990", "Result": "MAURYA FILLING STATION-Paytm" },
    { "RoCode": "16595050", "Result": "MARA PUMP KARAN FS-Paytm" },
    { "RoCode": "16595370", "Result": "OMKARA FILLING STATION-Paytm" },
    { "RoCode": "16595890", "Result": "JAKHAR PETROLEUM-Paytm" },
    { "RoCode": "16634300", "Result": "GORA FILLING STATION-IMSL" },
    { "RoCode": "16634350", "Result": "SARADA FUEL STATION_-Paytm" },
    { "RoCode": "16634370", "Result": "SHIVA FILLING STATION-Paytm" },
    { "RoCode": "16636260", "Result": "NAMAN PETROLEUM-Paytm" },
    { "RoCode": "16636250", "Result": "GURU JAMBHESHWAR PETRO CITY-Paytm" },
    { "RoCode": "16524710", "Result": "BIDAWAT FUEL FILLING STATION-Paytm" },
    { "RoCode": "16595940", "Result": "KAMMA FILLING STATION-Paytm" },
    { "RoCode": "16859690", "Result": "SANDEEP SINGH JOGINDER SINGH-Paytm" },
    { "RoCode": "16859720", "Result": "DUSAD FILLING STATION-Paytm" },
    { "RoCode": "16014510", "Result": "SHARMA PETROLEUM AGENCY-IMSL" },
    { "RoCode": "16595930", "Result": "J. R. KALWA FILLING STATION-Paytm" },
    { "RoCode": "11476230", "Result": "MADANLAL BHATIA AND SONS-Paytm" },
    { "RoCode": "16594380", "Result": "GROVER FILLING STATION-Paytm" },
    { "RoCode": "16634050", "Result": "SHREE BHAWANI FS-Paytm" },
    { "RoCode": "11638010", "Result": "RAMESH AND COMPANY-Paytm" },
    { "RoCode": "16636270", "Result": "HINDUSTHAN FILLING STATION-IMSL" },
    { "RoCode": "16634390", "Result": "RAMANA PETRO SERVICE-Paytm" },
    { "RoCode": "16636240", "Result": "SURAJ SUKHI FILLING STATION-Paytm" },
    { "RoCode": "16524610", "Result": "SHRI GANESH FILLING STN-IMSL" },
    { "RoCode": "16594750", "Result": "HAMARA PUMP SAWAI CHHOTTI-IMSL" },
    { "RoCode": "16859810", "Result": "DHUKIA FILLING STATION-Paytm" },
    { "RoCode": "16636210", "Result": "HIRA NAND MIDHA AND SONS-Paytm" },
    { "RoCode": "11720010", "Result": "Mohan Lal Agarwal-Paytm" },
    { "RoCode": "11658020", "Result": "KEJRIWAL BROTHERS-Paytm" },
    { "RoCode": "11655020", "Result": "MOHANLAL SHANKARDAS-Paytm" },
    { "RoCode": "11475810", "Result": "Ramanand Ratanlal-Paytm" },
    { "RoCode": "11470310", "Result": "ARJUN DAS DHANRAJ-Paytm" },
    { "RoCode": "16859580", "Result": "Shree Balaji fs-IMSL" },
    { "RoCode": "16859590", "Result": "MAHDEV Fs-Paytm" },
    { "RoCode": "11466310", "Result": "HANUMAN PRASAD RAGHUNATH P-IMSL" },
    { "RoCode": "16595560", "Result": "SAGAR FILLING STATION-Paytm" },
    { "RoCode": "16859560", "Result": "KIRTISHESH RAMWATAR FS-IMSL" },
    { "RoCode": "16859630", "Result": "KATARIA FILLING STATION-IMSL" },
    { "RoCode": "16859640", "Result": "JASANA FILLING STATION-IMSL" },
    { "RoCode": "16859730", "Result": "JEET FILLING STN-IMSL" },
    { "RoCode": "16859910", "Result": "ASHADEVI SANTOSH FS-IMSL" },
    { "RoCode": "16636710", "Result": "Nehal Service Station-Paytm" },
    { "RoCode": "16595010", "Result": "BAGDI FILLING STATION-IMSL" },
    { "RoCode": "11485012", "Result": "Behari Ram Sewa Ram-Paytm" },
    { "RoCode": "16636930", "Result": "Suman Petroleum-Paytm" },
    { "RoCode": "11511110", "Result": "Krishi Kalptaru filling stn-Paytm" },
    { "RoCode": "11531010", "Result": "LAXMAN SWAROOP COMPANY-Paytm" },
    { "RoCode": "11598010", "Result": "SHARMA AND COMPANY-Paytm" },
    { "RoCode": "13916210", "Result": "Luxmi Automobile-Paytm" },
    { "RoCode": "16595570", "Result": "HP Laxmi Filling STN-Paytm" },
    { "RoCode": "16595420", "Result": "GEHLOT FILLING STATION-IMSL" },
    { "RoCode": "16852710", "Result": "Janu Service Station-Paytm" },
    { "RoCode": "16636910", "Result": "Shiv Petroleum-Paytm" },
    { "RoCode": "16594070", "Result": "Maan Highway Service Station-Paytm" },
    { "RoCode": "11494310", "Result": "Arya Service Center-Paytm" },
    { "RoCode": "16595920", "Result": "Koshal Filling Station-Paytm" },
    { "RoCode": "16634210", "Result": "SHIV SHAKTI FILLING STATION-IMSL" },
    { "RoCode": "16594350", "Result": "Pratapgarh Filling Station-IMSL" },
    { "RoCode": "11467620", "Result": "Badri Prasad Surya Prakash-Paytm" },
    { "RoCode": "16594390", "Result": "Jagdamba Filling Station-IMSL" },
    { "RoCode": "16594830", "Result": "Shaheb ji Filling Station-Paytm" },
    { "RoCode": "16595020", "Result": "Sarita Filling Station-Paytm" },
    { "RoCode": "16595540", "Result": "HP D AND D COMPANY-Paytm" },
    { "RoCode": "16595970", "Result": "Pooran Filling Station-Paytm" },
    { "RoCode": "16634120", "Result": "Mangalam Filling Station-IMSL" },
    { "RoCode": "16595360", "Result": "HP Khatana Filling Sta-Paytm" },
    { "RoCode": "16859960", "Result": "Adhoc OmSagar Petroleum-0" },
    { "RoCode": "16514510", "Result": "KRISHNA FILLING STATION-IMSL" },
    { "RoCode": "16595780", "Result": "SHRI PARMANAND FS-Paytm" },
    { "RoCode": "11468410", "Result": "DWARKA LAL AGRAWAL-Paytm" },
    { "RoCode": "16595750", "Result": "JAI DURGA PETROLEUM-Paytm" },
    { "RoCode": "16594030", "Result": "Joshi Brothers-Paytm" },
    { "RoCode": "16594730", "Result": "HAMARA PUMP BALOD BARI-Paytm" },
    { "RoCode": "16635170", "Result": "VINAYAK FILLING STATION-Paytm" },
    { "RoCode": "11613010", "Result": "MAHAVEER PRASAD KHANDELWAL-Paytm" },
    { "RoCode": "16634920", "Result": "SHRI NATH PETROLEUM-Paytm" },
    { "RoCode": "16636810", "Result": "SAI KRIPA FILLING STATION-Paytm" },
    { "RoCode": "16636890", "Result": "AATEF ALHAAN CO.-Paytm" },
    { "RoCode": "16636790", "Result": "CHOUDHARY CHANDARBHAN FILLING -IMSL" },
    { "RoCode": "16859830", "Result": "Jeen Bhawani fs-Paytm" },
    { "RoCode": "16636760", "Result": "SHREE RADHE GOPAL FILLING STAT-Paytm" },
    { "RoCode": "16636850", "Result": "CHAHAR FILLING STATION-Paytm" },
    { "RoCode": "16859920", "Result": "DUDHAWA FILLING STATION -Paytm" },
    { "RoCode": "16594660", "Result": "HAMARA PUMP CHANANA-Paytm" },
    { "RoCode": "16594700", "Result": "HAMARA PUMP GADA KHERA_-Paytm" },
    { "RoCode": "16594770", "Result": "HAMARA PUMP NAGWA-Paytm" },
    { "RoCode": "16595870", "Result": "R P AND SONS PETROLEUM-Paytm" },
    { "RoCode": "16338110", "Result": "JUGAL KISHORE AND SONS-Paytm" },
    { "RoCode": "16634270", "Result": "AAYUSH FUEL MART-Paytm" },
    { "RoCode": "16079910", "Result": "AJEETGARH FILLING STATION-IMSL" },
    { "RoCode": "16509910", "Result": "SWATANTRA SAINANI FILLING STAT-Paytm" },
    { "RoCode": "16514410", "Result": "Madan Mohan FS-Paytm" },
    { "RoCode": "16636800", "Result": "S D FILLING STATION-Paytm" },
    { "RoCode": "16636870", "Result": "H S FILLING STATION-Paytm" },
    { "RoCode": "16636770", "Result": "R S FILLING STATION-Paytm" },
    { "RoCode": "16859940", "Result": "BAGARIA FILLING STATION-IMSL" },
    { "RoCode": "16636840", "Result": "VINAYAK FILLING STATION-Paytm" },
    { "RoCode": "11467910", "Result": "RAMESHWAR LAL PRAHLADKA-IMSL" },
    { "RoCode": "16859840", "Result": "KHATRI PETROLEUM-Paytm" },
    { "RoCode": "16636780", "Result": "DAYA FILLING STATION-IMSL" },
    { "RoCode": "11470510", "Result": "SHANKAR LAL BROTHERS-Paytm" },
    { "RoCode": "16594610", "Result": "HAMARA PUMP CHANWARA-Paytm" },
    { "RoCode": "16595760", "Result": "HARDEV LAMBA FILLING STATION-Paytm" },
    { "RoCode": "16535710", "Result": "SIDH BABA FILLING STATION-Paytm" },
    { "RoCode": "16594720", "Result": "HAMARA PUMP OJATOO-IMSL" },
    { "RoCode": "16594370", "Result": "GURU KRIPA FILLING STATION-Paytm" },
    { "RoCode": "13922910", "Result": "JEEN MATA FILLING STATION-IMSL" },
    { "RoCode": "16595620", "Result": "BABA BALAKNATH FS-Paytm" },
    { "RoCode": "11471210", "Result": "SURAJMAL DALMIA-Paytm" },
    { "RoCode": "11726010", "Result": "BAIJNATH SUNDARAM-Paytm" },
    { "RoCode": "11467220", "Result": "HEERA GOYAL AND BROTHERS-Paytm" },
    { "RoCode": "11522210", "Result": "NAVEEN FILlING CENTRE-Paytm" },
    { "RoCode": "11467310", "Result": "NEW SHAH OIL STORE-Paytm" },
    { "RoCode": "11725010", "Result": "GHANSHYAM DAS MURLIDHAR-Paytm" },
    { "RoCode": "13922110", "Result": "VIJAY FILLING STATION-IMSL" },
    { "RoCode": "16634930", "Result": "Kulhari Filling Station-Paytm" },
    { "RoCode": "16636290", "Result": "SHARAN FILLING STATION-Paytm" },
    { "RoCode": "16636310", "Result": "SHRI SIDDHI VINAYAK FUEL MART-Paytm" },
    { "RoCode": "16636830", "Result": "SANTOSH FILLING STATION-IMSL" },
    { "RoCode": "16859820", "Result": "KISHAN PETROL PUMP-Paytm" },
    { "RoCode": "16859850", "Result": "SHREE SHYAM FILLING STATION-IMSL" },
    { "RoCode": "16594850", "Result": "VAKRANGEE HP FUELS -Paytm" },
    { "RoCode": "16594930", "Result": "SUMAN HP FILLING STATION-Paytm" },
    { "RoCode": "16595330", "Result": "TRIVENI FILLING CENTRE-Paytm" },
    { "RoCode": "16635190", "Result": "CHOUDHARY CHHAJU RAM FILLING-Paytm" },
    { "RoCode": "16521610", "Result": "MAHADEV FILLING STATION-IMSL" },
    { "RoCode": "16859620", "Result": "SHRI KRISHAN HP CENTER-IMSL" },
    { "RoCode": "16636860", "Result": "SALURAM PRAHLAD CHAND FUEL STN-Paytm" },
    { "RoCode": "16859880", "Result": "DHUNDHADA FUELS-Paytm" },
    { "RoCode": "11561010", "Result": "AGRA ROAD SERVICE CENTRE-Paytm" },
    { "RoCode": "16081710", "Result": "MANGALE SERVICE STATION-Paytm" },
    { "RoCode": "16859740", "Result": "GANPATI FUEL STATION-IMSL" },
    { "RoCode": "16636330", "Result": "DURGA SUMAN FILLING STATION-Paytm" },
    { "RoCode": "41070666", "Result": "ADHOC KANWAR KA BAAS-Paytm" },
    { "RoCode": "11567010", "Result": "NEW RAJASTHAN PETRO SERVICE-Paytm" },
    { "RoCode": "16071510", "Result": "KATARIA FILLING CENTRE-Paytm" },
    { "RoCode": "11509110", "Result": "CHAND FILLING STATION-Paytm" },
    { "RoCode": "16595530", "Result": "BHAGIRATH FILLING STATION-Paytm" },
    { "RoCode": "11738010", "Result": "TAMBI ENTERPRISES-Paytm" },
    { "RoCode": "11469620", "Result": "SARAOGIS-IMSL" },
    { "RoCode": "11470720", "Result": "HIGHWAY SERVICE STATION-Paytm" },
    { "RoCode": "11468310", "Result": "PAREEK AUTO SERVICE-Paytm" },
    { "RoCode": "11471110", "Result": "DASOT SERVICE CENTRE-Paytm" },
    { "RoCode": "16594550", "Result": "GANESHAM-Paytm" },
    { "RoCode": "16634950", "Result": "Manish Petroleum-Paytm" },
    { "RoCode": "16636820", "Result": "Shriram Filling Station-Paytm" },
    { "RoCode": "16636880", "Result": "DULI CHAND FILLING STATION-IMSL" },
    { "RoCode": "16859610", "Result": "BHAGWATI FILLING STATION-Paytm" },
    { "RoCode": "16859760", "Result": "SHREE BALAJI FILLING STATION-Paytm" },
    { "RoCode": "16651400", "Result": "MAHI FUAL STATION-Paytm" },
    { "RoCode": "16624200", "Result": "Swagat Associates-Paytm" },
    { "RoCode": "16625150", "Result": "BABA RAMDEV FUEL SERVICES-Paytm" },
    { "RoCode": "16625220", "Result": "shiv filling station-Paytm" },
    { "RoCode": "16625290", "Result": "B.R.D. FILLING STATION-Paytm" },
    { "RoCode": "16651550", "Result": "HP CENTRE-IMSL" },
    { "RoCode": "16600790", "Result": "KRISHANA FILLING STATION-Paytm" },
    { "RoCode": "11475210", "Result": "Gehlot Service Station-Paytm" },
    { "RoCode": "16624080", "Result": "Vaibhav Filling Station-Paytm" },
    { "RoCode": "16648020", "Result": "GURU KRIPA PETROLIUM-IMSL" },
    { "RoCode": "16557610", "Result": "HAMARA PUMP JAJIWAL-IMSL" },
    { "RoCode": "16625160", "Result": "Shanti Filling Station -Paytm" },
    { "RoCode": "16624580", "Result": "MA ASHAPURA FILLING STATION-Paytm" },
    { "RoCode": "16624620", "Result": "Highway Filling Center-Paytm" },
    { "RoCode": "16624350", "Result": "Salawas Petroleum-Paytm" },
    { "RoCode": "11628010", "Result": "C.prakashmal jain-Paytm" },
    { "RoCode": "16600050", "Result": "Paliwal Filling Station-Paytm" },
    { "RoCode": "16624180", "Result": "SURAJ AND SONS-Paytm" },
    { "RoCode": "11473320", "Result": "PURSHOTAMDAS JAGDISH CHANDRA-Paytm" },
    { "RoCode": "11472610", "Result": "MARWAR PETROL SERVICE-Paytm" },
    { "RoCode": "11581020", "Result": "GANESHI LAL AND SONS-Paytm" },
    { "RoCode": "16600450", "Result": "K.K TRAVELS-Paytm" },
    { "RoCode": "16600510", "Result": "Shree Sevice Station-Paytm" },
    { "RoCode": "16601380", "Result": "Kamla Filling Station-Paytm" },
    { "RoCode": "16624240", "Result": "MS GOPAL FILLING STATION-Paytm" },
    { "RoCode": "16624340", "Result": "Tanishq Energy Station-Paytm" },
    { "RoCode": "16624540", "Result": "Bhaskar Filling Station-Paytm" },
    { "RoCode": "16651450", "Result": "NEW RAJPUTANA FILLING STAION-IMSL" },
    { "RoCode": "16651580", "Result": "Sai Kripa Fuels-Paytm" },
    { "RoCode": "16624360", "Result": "SALAWAS FILLING STATION-Paytm" },
    { "RoCode": "41066652", "Result": "SAI FILLING STATION-Paytm" },
    { "RoCode": "16600690", "Result": "CHAGAN LAL SONI-Paytm" },
    { "RoCode": "16651750", "Result": "MSHSD ADHOC BIKANER F.S-Paytm" },
    { "RoCode": "16601230", "Result": "Shree Kalyan Hamara Pump-Paytm" },
    { "RoCode": "16648380", "Result": "OAD AAMBANI FILLING STATION-IMSL" },
    { "RoCode": "16629260", "Result": "NITIKA FILLING STATION-IMSL" },
    { "RoCode": "11611010", "Result": "CHANDRA ENGINEERING CORP.-Paytm" },
    { "RoCode": "16585610", "Result": "SAGAR MOTARS-Paytm" },
    { "RoCode": "16600640", "Result": "KALWA PETRO POINT-IMSL" },
    { "RoCode": "16600900", "Result": "R K PETROLEUM-Paytm" },
    { "RoCode": "16624470", "Result": "shree vinayak petroleums-Paytm" },
    { "RoCode": "16651120", "Result": "SARAN FILLING STATION-Paytm" },
    { "RoCode": "16601170", "Result": "SHRI HINGLAJ FILLING STATION-Paytm" },
    { "RoCode": "16334910", "Result": "SHAHEED B.L NAIN F.S-IMSL" },
    { "RoCode": "16600410", "Result": "BIKANER FILLING STATION-Paytm" },
    { "RoCode": "16601020", "Result": "HAMARA PUMP BIKAMPUR-Paytm" },
    { "RoCode": "11475510", "Result": "BIHANI BROTHERS-IMSL" },
    { "RoCode": "16601880", "Result": "JAISUKHRAM OMPARKASH-Paytm" },
    { "RoCode": "16521510", "Result": "HAMARA PUMP BAJJU-Paytm" },
    { "RoCode": "16600150", "Result": "SHAHID KANSINGH AUTOMOBILES-Paytm" },
    { "RoCode": "11695010", "Result": "RAJENDRA PETROL SERVICE-IMSL" },
    { "RoCode": "11471910", "Result": "NEW JAISALMER AUTOMOBILES-IMSL" },
    { "RoCode": "16624440", "Result": "l.r.fuel station-Paytm" },
    { "RoCode": "16554510", "Result": "SANJAY CITY FILLING -Paytm" },
    { "RoCode": "16648400", "Result": "PUNAM SARAN PETROL PUMP-IMSL" },
    { "RoCode": "16648430", "Result": "LEKHRAM BHADU PETROLIUM-IMSL" },
    { "RoCode": "16624500", "Result": "MS HSD DHAISAR FILLINGH STATIO-Paytm" },
    { "RoCode": "16585410", "Result": "JAI BHAWANI BUS SERVICE-Paytm" },
    { "RoCode": "16600010", "Result": "SARAN PETROLIUM-Paytm" },
    { "RoCode": "16600020", "Result": "SHARMA TRAVEL-Paytm" },
    { "RoCode": "16601240", "Result": "V.K JOIYA PETRO POINT-0" },
    { "RoCode": "16601860", "Result": "TARD PETROLIUM-0" },
    { "RoCode": "16624370", "Result": "MAA KALKA FILLING STATION-IMSL" },
    { "RoCode": "16624480", "Result": "G R KHALIYA FILLING STATION-Paytm" },
    { "RoCode": "16624530", "Result": "JUJHAR JAGANNATH BHADU-Paytm" },
    { "RoCode": "16651130", "Result": "SHREE RAM FILLING STATION-Paytm" },
    { "RoCode": "16651150", "Result": "SHRI HARI PETROLEUM-Paytm" },
    { "RoCode": "16651160", "Result": "BALAJI FILLING STATION-IMSL" },
    { "RoCode": "16651170", "Result": "JRD DIESELS-IMSL" },
    { "RoCode": "16651180", "Result": "LAXMINATH FILLING STATION -Paytm" },
    { "RoCode": "16651190", "Result": "DO BHAI PETROL PUMP -IMSL" },
    { "RoCode": "16651700", "Result": "SMB FILLING STATION -Paytm" },
    { "RoCode": "16651710", "Result": "SHRI KESHRICHAND SARSWAT AUTO -Paytm" },
    { "RoCode": "16651720", "Result": "BHATI FILLING STATION -Paytm" },
    { "RoCode": "16651730", "Result": "SHREE BABA RAMDEV FILLING STAT-Paytm" },
    { "RoCode": "16651760", "Result": "HP SERVICE CENTER POKRAN-Paytm" },
    { "RoCode": "16651770", "Result": "AMRIT FUEL STATION-Paytm" },
    { "RoCode": "16651780", "Result": "HARDIK PETROLEUM -IMSL" },
    { "RoCode": "41066707", "Result": "SHRI KARNI PETROLEUM-IMSL" },
    { "RoCode": "16624210", "Result": "J B PETROLEUM-Paytm" },
    { "RoCode": "16625180", "Result": "SHRINATH AUTOMOBIES-Paytm" },
    { "RoCode": "16836430", "Result": "ARVIND PETROLEUM-Paytm" },
    { "RoCode": "16624450", "Result": "PATALESHWAR PETROLEUM-Paytm" },
    { "RoCode": "16651200", "Result": "DHARNIDHAR PETROLEUM-IMSL" },
    { "RoCode": "16601010", "Result": "HANUMAN PETROLEUM-Paytm" },
    { "RoCode": "16333710", "Result": "PRAVEEN FILLING CENTRE-IMSL" },
    { "RoCode": "16334510", "Result": "SAHID BHIKARAM HIGHWAY CENTER-Paytm" },
     { "RoCode": "16624120", "Result": "VANDANA FILLING STATION-IMSL" },
    { "RoCode": "16651220", "Result": "MUNIRAJ PETROLEUM-IMSL" },
    { "RoCode": "16625120", "Result": "GUDAMALNI FILLING STATION-Paytm" },
    { "RoCode": "16624030", "Result": "BHAGWATI PETROLIUEM-Paytm" },
    { "RoCode": "16625080", "Result": "JAY JASNATH PETROL PUMP-Paytm" },
    { "RoCode": "16625040", "Result": "MAHADEV PETROLEUM-IMSL" },
    { "RoCode": "16601040", "Result": "GAUEAV HP CENTER-Paytm" },
    { "RoCode": "16648390", "Result": "SHIVAM PETROLEUM-IMSL" },
    { "RoCode": "16625200", "Result": "MAHADEV FUELS SERVICE CENTER-Paytm" },
    { "RoCode": "16624680", "Result": "JAMBHESHWAR HAMARA PUMP-Paytm" },
    { "RoCode": "16600950", "Result": "AGARWAL PETROLEUM-IMSL" },
    { "RoCode": "16601600", "Result": "Rajasthan Diesels-0" },
    { "RoCode": "16601730", "Result": "BAJRANG SINGH AUTOMOBILE-Paytm" },
    { "RoCode": "16601740", "Result": "MS MANISHA SERVICE STATIO-Paytm" },
    { "RoCode": "16624220", "Result": "Vande Petroleum-Paytm" },
    { "RoCode": "16624740", "Result": "SHRI MAHADEV FUELS-IMSL" },
    { "RoCode": "16625020", "Result": "GANPATI PETROLEUM-Paytm" },
    { "RoCode": "16625270", "Result": "SATYAM AUTOMOBILES-Paytm" },
    { "RoCode": "16648070", "Result": "KANAK PETROLEUM-IMSL" },
    { "RoCode": "16648210", "Result": "VIRATRA PETROLEUM-Paytm" },
    { "RoCode": "16648230", "Result": "SHREE CHAMUNDA PETROLUM-IMSL" },
    { "RoCode": "16648290", "Result": "GAURAV FUEL STATION-Paytm" },
    { "RoCode": "16651210", "Result": "MAHALAXMI FUEL SERVICE-IMSL" },
    { "RoCode": "16651240", "Result": "JAI MAHALAXMI PETROLEUM-Paytm" },
    { "RoCode": "16651250", "Result": "MAHADEV FILLING STATION-Paytm" },
    { "RoCode": "16651280", "Result": "SHREE RAM FILLING STATION-Paytm" },
    { "RoCode": "16651290", "Result": "HAZI MUSE KHAN AND SONS-Paytm" },
    { "RoCode": "16651460", "Result": "M/s Shivay Petroleum, Motinagar-Paytm" },
    { "RoCode": "16651470", "Result": "MSHSD SHANTINATH PETROLEUM-IMSL" },
    { "RoCode": "16651480", "Result": "MSHSD MAHADEV DIESELS AND AUTO-Paytm" },
    { "RoCode": "16651520", "Result": "BHAGYA LAXMI PETROLEUM-Paytm" },
    { "RoCode": "16651570", "Result": "SHRI MOHANGARH PETROLEUM-IMSL" },
    { "RoCode": "16651640", "Result": "M/S NEELKANTH PETROLEUM-Paytm" },
    { "RoCode": "16624650", "Result": "KHIMAJ MATA FS-IMSL" },
    { "RoCode": "16624960", "Result": "SATYAM PETROLEUM-Paytm" },
    { "RoCode": "16648220", "Result": "ARIHANT HP FUEL STATION-IMSL" },
    { "RoCode": "16625940", "Result": "HUDDA PETROL PUMP-IMSL" },
    { "RoCode": "16624090", "Result": "POTALIYA PETROLEUM-Paytm" },
    { "RoCode": "16601680", "Result": "SHREE KRISHNA PETROLEM-Paytm" },
    { "RoCode": "16625980", "Result": "RAMSNEHI PETROLIUMSERVICE-Paytm" },
    { "RoCode": "16625970", "Result": "MANSING FILLING SATION-IMSL" },
    { "RoCode": "11531110", "Result": "MAHESH AUTOMOBILES-IMSL" },
    { "RoCode": "16648470", "Result": "KHOJA FILLING STATION-Paytm" },
    { "RoCode": "16329510", "Result": "JUHI FILLING CENTER-Paytm" },
    { "RoCode": "16600700", "Result": "MAULASAR FILLING STATION-Paytm" },
    { "RoCode": "16601430", "Result": "MAHADEV FILLING STATION-IMSL" },
    { "RoCode": "16601450", "Result": "RANWAN FILLING STATION-Paytm" },
    { "RoCode": "16601540", "Result": "MS BALAJI SERVICE STATION-Paytm" },
    { "RoCode": "16648060", "Result": "RATAN PETROLEM-IMSL" },
    { "RoCode": "16648410", "Result": "SHREE SHAYAM FILLING STATION-Paytm" },
    { "RoCode": "16625100", "Result": "GAURA PTROL PUMP-Paytm" },
    { "RoCode": "11518110", "Result": "RANWHA SERVICE CENTER-Paytm" },
    { "RoCode": "11474310", "Result": "RAJSTHAN PETROL SERVICE-Paytm" },
    { "RoCode": "16848420", "Result": "SHREE BABA RAMDEV F.S-Paytm" },
    { "RoCode": "11683020", "Result": "NAGAUR PETROL SERVICE-Paytm" },
    { "RoCode": "16600730", "Result": "SETHI FILLING STATION-Paytm" },
    { "RoCode": "16625230", "Result": "JANTA FILLING STATION-Paytm" },
    { "RoCode": "16625060", "Result": "SHRI RAM PETROL PUMP-Paytm" },
    { "RoCode": "16625110", "Result": "AMAR PREM FILLING STATION-Paytm" },
    { "RoCode": "16601150", "Result": "HAMARA PUMP EDWA-Paytm" },
    { "RoCode": "16848390", "Result": "Ananya fuel station-IMSL" },
    { "RoCode": "11718010", "Result": "NAHAR BOTHERS-IMSL" },
    { "RoCode": "16601650", "Result": "SHRI GOVERDHAN PETROLUM-Paytm" },
    { "RoCode": "16601710", "Result": "SHREE SALASAR DARBAR PETROLEM-Paytm" },
    { "RoCode": "16625950", "Result": "H H FILLING STATION-IMSL" },
    { "RoCode": "16648030", "Result": "G.S FILLING STATION-Paytm" },
    { "RoCode": "16648040", "Result": "JAJAMPURI BABA FILLING STATION-IMSL" },
    { "RoCode": "16648050", "Result": "BABA RAMDEV FILLING STATION-Paytm" },
    { "RoCode": "16648420", "Result": "MAHADEV FILLING STATION-IMSL" },
    { "RoCode": "16648440", "Result": "Inaniyan Filling Station-Paytm" },
    { "RoCode": "16648480", "Result": "KRISHNA FILLING STATION-IMSL" },
    { "RoCode": "16651340", "Result": "SAI PETROL PUMP-Paytm" },
    { "RoCode": "16651350", "Result": "M/S KRISHNA FILLING STATION-Paytm" },
    { "RoCode": "16651360", "Result": "SHREE SHYAM FILLING STATION-Paytm" },
    { "RoCode": "16651370", "Result": "SANSKAR FILLING STATION-Paytm" },
    { "RoCode": "16651380", "Result": "BABA RAMDEV PETROLEUM-Paytm" },
    { "RoCode": "16651390", "Result": "LADNUN HIGHWAY FILLING STATION-Paytm" },
    { "RoCode": "16651500", "Result": "MAHADEV FILLING STATION -Paytm" },
    { "RoCode": "16651510", "Result": "FOJI FILLING STATION -IMSL" },
    { "RoCode": "16651540", "Result": "SHREE SITARAM PETROLEUM-Paytm" },
    { "RoCode": "16651800", "Result": "Babulal Chhogaram Raika Fillin-Paytm" },
    { "RoCode": "16848400", "Result": "KNB FILLING STATION-Paytm" },
    { "RoCode": "11557110", "Result": "Shri Ram Filling Station-Paytm" },
    { "RoCode": "16648180", "Result": "BALAJI FILLING STATION-IMSL" },
    { "RoCode": "11472920", "Result": "GEHLOT AGRO SERVICE CENTRE-Paytm" },
    { "RoCode": "11519310", "Result": "DHOLIYA FILLING STATION-Paytm" },
    { "RoCode": "16600120", "Result": "HAMARA PUMP KAJAWANA -Paytm" },
    { "RoCode": "16600160", "Result": "HAMARA PUMP RIYANBADI-Paytm" },
    { "RoCode": "16600430", "Result": "Marudhar Filling Station-Paytm" },
    { "RoCode": "16600670", "Result": "SHIV FILLING STATION-Paytm" },
    { "RoCode": "16601480", "Result": "SHRI DADUDAYAL FILLING STATION-Paytm" },
    { "RoCode": "16601500", "Result": "MS NAGANARAY FILLING STATION-Paytm" },
    { "RoCode": "16601990", "Result": "SHRI LAXMAN FILLING CENTER-Paytm" },
    { "RoCode": "16624020", "Result": "SAYAR FILLING STATION-IMSL" },
    { "RoCode": "16534910", "Result": "HAMARA PUMP GOTAN-Paytm" },
    { "RoCode": "16569710", "Result": "SHREE RISHABHDEV FILLING STATION-IMSL" },
    { "RoCode": "16648260", "Result": "SHAKUN FILLING STATION-Paytm" },
    { "RoCode": "16601630", "Result": "SHRI MOHAN FILLING STATION-Paytm" },
    { "RoCode": "16601340", "Result": "Baghela Filling Station-IMSL" },
    { "RoCode": "16648250", "Result": "SHREE BHADARIYA RAY F.S-IMSL" },
    { "RoCode": "16600560", "Result": " -Paytm" },
    { "RoCode": "16625140", "Result": "Manwar Filling Station-Paytm" },
    { "RoCode": "16624250", "Result": "HARIOM HAMARA PUMP-Paytm" },
    { "RoCode": "16648170", "Result": "Sai filling station-IMSL" },
    { "RoCode": "16624810", "Result": "CHANDRA FILL AND FLY-Paytm" },
    { "RoCode": "16601130", "Result": "HAMARA PUMP KALAU FANTA-Paytm" },
    { "RoCode": "16624730", "Result": "SHIV ROOP RAJAT FS-Paytm" },
    { "RoCode": "16601470", "Result": "SHRI HANUMANT PETROLEM-Paytm" },
    { "RoCode": "16624230", "Result": "SHIV BHOLE FILLING STATION-Paytm" },
    { "RoCode": "16601980", "Result": "GOSWAMI FILLING CENTRE-IMSL" },
    { "RoCode": "16587550", "Result": "HAMARA PUMP TINWARI-Paytm" },
    { "RoCode": "16601660", "Result": "PARIHAR SERVICE STATION-Paytm" },
    { "RoCode": "16624770", "Result": "BHARAT MATA AUTOMOBILES-Paytm" },
    { "RoCode": "16625010", "Result": "BHATI FILLING STATION-IMSL" },
    { "RoCode": "16648190", "Result": "MAHENDRA FILLING STATION-IMSL" },
    { "RoCode": "16648280", "Result": "MS ADESH FILLING STATION-IMSL" },
    { "RoCode": "16651010", "Result": "Bhomiya G Filling Station-IMSL" },
    { "RoCode": "16651020", "Result": "SURESH PETROLEUM-IMSL" },
    { "RoCode": "16651050", "Result": "BABA RAMDEV PETROLEUM-Paytm" },
    { "RoCode": "16651060", "Result": "GURUDEV FILLING STATION-Paytm" },
    { "RoCode": "16651080", "Result": "SOLANKI PETROL PUMP-Paytm" },
    { "RoCode": "16624630", "Result": "CHOUDHARY MEERSA FS-Paytm" },
    { "RoCode": "41066638", "Result": "GANPATI FILLING STATION -Paytm" },
    { "RoCode": "16647370", "Result": "MEHADEV HP FILLING STATION-Paytm" },
    { "RoCode": "11466012", "Result": "FRIENDS FILLING STATION-0" },
    { "RoCode": "16647470", "Result": "NEELKANTH FILLING STATION-IMSL" },
    { "RoCode": "16647410", "Result": "PRABAL HP FILLING STATION-IMSL" },
    { "RoCode": "16599560", "Result": "HARIKRIPA FS-Paytm" },
    { "RoCode": "16599370", "Result": "JAI SHREE KRISHNA ENT.-Paytm" },
    { "RoCode": "16598840", "Result": "HUMARA PUMP SEMARI-IMSL" },
    { "RoCode": "16296210", "Result": "GAUTAM RISHI FILLINGSTATION -Paytm" },
    { "RoCode": "16334710", "Result": "DHULEV PETROL PUMP-Paytm" },
    { "RoCode": "16598750", "Result": "vijay laxmi filling stastion-Paytm" },
    { "RoCode": "16633720", "Result": "Eklingnath filling station-Paytm" },
    { "RoCode": "16647340", "Result": "GUJRESHWER FS-Paytm" },
    { "RoCode": "16641290", "Result": "VARTIKA HP FILLING STATIN-IMSL" },
    { "RoCode": "11491410", "Result": "FILL AND FLY-Paytm" },
    { "RoCode": "16633850", "Result": "VC PETROLEUM-Paytm" },
    { "RoCode": "16647180", "Result": "SHIVMANI HP-IMSL" },
    { "RoCode": "16647150", "Result": "PANDIT HP STATION-IMSL" },
    { "RoCode": "16647190", "Result": "L and R hp pump-IMSL" },
    { "RoCode": "16647310", "Result": "MEWAR FILLING STATION-IMSL" },
    { "RoCode": "16647320", "Result": "SHANTI HP CENTER-IMSL" },
    { "RoCode": "16647330", "Result": "MAHI HP CENTER-Paytm" },
    { "RoCode": "16647390", "Result": "Aashutosh hp station-IMSL" },
    { "RoCode": "16652380", "Result": "HEERA HP FILLING STATION-IMSL" },
    { "RoCode": "41067410", "Result": "ADHOC GATUM RISHI FS-Paytm" },
    { "RoCode": "16647040", "Result": "CHANDRA HP PETROLEUM-IMSL" },
    { "RoCode": "16647450", "Result": "SANJANA HP FILLING-Paytm" },
    { "RoCode": "16601520", "Result": "KUSHAL JAGDISH CHOUDHARY-Paytm" },
    { "RoCode": "16641070", "Result": "SHREE BALAJI FS-IMSL" },
    { "RoCode": "16641060", "Result": "SHIV GOURI FILLING STATION-Paytm" },
    { "RoCode": "16624600", "Result": "SHRI BHAIRAV FUELS-Paytm" },
    { "RoCode": "16569810", "Result": "ROOPRAJAT FILLING STATION-Paytm" },
    { "RoCode": "16647110", "Result": "ALWAR FILLING STATION-Paytm" },
    { "RoCode": "16652030", "Result": "RONAK HP AUTOMOBILES-IMSL" },
    { "RoCode": "16647120", "Result": "MAA JAMWAI FILLING STATION-IMSL" },
    { "RoCode": "11687010", "Result": "SURESH KUMAR GHISOOLAL-Paytm" },
    { "RoCode": "16647160", "Result": "MAA KOUSHALYA HP-IMSL" },
    { "RoCode": "16081610", "Result": "Shiva Filling Station-Paytm" },
    { "RoCode": "16600480", "Result": "SHREE GURU FILLING STATION-Paytm" },
    { "RoCode": "16624380", "Result": "Ashapura filling station-Paytm" },
    { "RoCode": "16601310", "Result": "SONGRA FILLING STATION-Paytm" },
    { "RoCode": "11474110", "Result": "SAROJ AUTOMMOBILES-Paytm" },
    { "RoCode": "11688010", "Result": "SURESHKUMAR GHISULAL CO.-Paytm" },
    { "RoCode": "16587640", "Result": "HAMARA PUMP SARANGWAS-Paytm" },
    { "RoCode": "16601900", "Result": "BHANWAL MATA FILLING STATION-Paytm" },
    { "RoCode": "16624840", "Result": "BALA SATI FILLING STATION-Paytm" },
    { "RoCode": "16647100", "Result": "SAGAR FILLING STATION-IMSL" },
    { "RoCode": "16647170", "Result": "MCD HP FILLING STATION-Paytm" },
    { "RoCode": "16647460", "Result": "ROOP SHREE HP FILLING STATION-IMSL" },
    { "RoCode": "16652020", "Result": "SINGH HP FILLING STATION-IMSL" },
    { "RoCode": "16652040", "Result": "SHREE BALAJI HP PETROLIUM-Paytm" },
    { "RoCode": "16647010", "Result": "YOGIRAJ HP-IMSL" },
    { "RoCode": "16541410", "Result": "HAMARA PUMP DANPUR-Paytm" },
    { "RoCode": "16647060", "Result": "MANGAL MURTI HP FILLING STATIO-IMSL" },
    { "RoCode": "16652050", "Result": "SOHAN HP ENERGY-Paytm" },
    { "RoCode": "16652400", "Result": "JAINAM HP FULES-Paytm" },
    { "RoCode": "16599010", "Result": "HIMALAYA PARBHU KRIPA-0" },
    { "RoCode": "16599390", "Result": "JAGDISH FILLING STATION-IMSL" },
    { "RoCode": "13922610", "Result": "PARGATI PETROLEUM-0" },
    { "RoCode": "16598660", "Result": "NILGIRI FS-Paytm" },
    { "RoCode": "16656290", "Result": "MS HSD HP SERVICES CENTER-Paytm" },
    { "RoCode": "11615010", "Result": "NIMBHERA FILLING STATION-Paytm" },
    { "RoCode": "16648150", "Result": "BALAJI HP-IMSL" },
    { "RoCode": "16648090", "Result": "SOMNATH FILLING STATION-IMSL" },
    { "RoCode": "16641110", "Result": "SHRI SDDHI VINAYAK FS-Paytm" },
    { "RoCode": "16599930", "Result": "TIRURAJ PETROLEUM-IMSL" },
    { "RoCode": "16583810", "Result": "HUMARA PUMP SIYAKHERI-IMSL" },
    { "RoCode": "16599580", "Result": "UDAI PETROLIEUM-Paytm" },
    { "RoCode": "16633690", "Result": "shri shiv ganpati petroleum-Paytm" },
    { "RoCode": "16599960", "Result": "GIRNAR FILLING STATION-IMSL" },
    { "RoCode": "16599950", "Result": "LOVE KUSH FILLING STATION-IMSL" },
    { "RoCode": "16599200", "Result": "BANSWARA HP STATION-IMSL" },
    { "RoCode": "16599550", "Result": "SS FILLING STATION-Paytm" },
    { "RoCode": "16599720", "Result": "MATESHWARI FILLING STATION-IMSL" },
    { "RoCode": "11537110", "Result": "HADOTI SERVICE STATION-Paytm" },
    { "RoCode": "16599980", "Result": "NAYAK FILLING STATION-IMSL" },
    { "RoCode": "16641480", "Result": "BANESHWARI HP-IMSL" },
    { "RoCode": "16641490", "Result": "PAWAN TANAY HP-IMSL" },
    { "RoCode": "16647230", "Result": "BHAGYA SITAMAN HP-Paytm" },
    { "RoCode": "16648100", "Result": "DEVASHEESH HP PETROLEUM-IMSL" },
    { "RoCode": "16647050", "Result": "Namokar HP Filling station-IMSL" },
    { "RoCode": "16638020", "Result": "HP JAWAI PETRO CHEM-IMSL" },
    { "RoCode": "16600940", "Result": "MOHANLAL MAHESH KUMAR AGARWAL-IMSL" },
    { "RoCode": "16624550", "Result": "KRISHNA FILLING STATION-IMSL" },
    { "RoCode": "16587220", "Result": "HAMARA PUMP NANA-Paytm" },
    { "RoCode": "16624390", "Result": "VINAYAK PETROLEUM SERVICE-Paytm" },
    { "RoCode": "16601690", "Result": "BHOMIAJI AUTOMOBILES-Paytm" },
    { "RoCode": "16601770", "Result": "JAI GURUDEV FILLING STATION-IMSL" },
    { "RoCode": "16600210", "Result": "HAMARA PUMP MANADAR-IMSL" },
    { "RoCode": "41068772", "Result": "ADHOC JAI GURUDEV FS-Paytm" },
    { "RoCode": "11475310", "Result": "SHANKARLAL AGARWAL AND COM.-Paytm" },
    { "RoCode": "16635980", "Result": "DRISHTI FUELS-IMSL" },
    { "RoCode": "16624700", "Result": "KISSHAN FILLING STATION-IMSL" },
    { "RoCode": "16601580", "Result": "shree jagdamba filling station-Paytm" },
    { "RoCode": "11475312", "Result": "SHANKARLAL AGARWAL AND COMPANY-IMSL" },
    { "RoCode": "11716020", "Result": "BHAJANRAM GIRDHARILAL AND SONS-IMSL" },
    { "RoCode": "16601750", "Result": "ARIHANT PETROLEUM-0" },
    { "RoCode": "16647070", "Result": "SHREE CHAMUNDA PETROLEUM-IMSL" },
    { "RoCode": "16647080", "Result": "MEWAT FILLING STATION-0" },
    { "RoCode": "16647240", "Result": "SHREE SHAMBHU SINGH HP PETROLE-IMSL" },
    { "RoCode": "16647270", "Result": "MAHENDRA HP-IMSL" },
    { "RoCode": "16652000", "Result": "SHRI RAMESHWAR HP FS-IMSL" },
    { "RoCode": "16600090", "Result": "HAMARA PUMP RAMNAGR-Paytm" },
    { "RoCode": "16649490", "Result": "SHREE JI HP FILLING STATION-Paytm" },
    { "RoCode": "16647200", "Result": "MS HSD KALKA FILLING STATION-IMSL" },
    { "RoCode": "16649440", "Result": "SHRI KESHAV HP FILLING STATION-Paytm" },
    { "RoCode": "11523210", "Result": "CHARBHUJA FILLING STATION-Paytm" },
    { "RoCode": "16599440", "Result": "JAI DHANOP FUEL STATION-Paytm" },
    { "RoCode": "16647490", "Result": "BHARUNATH HP FILLING STATION-IMSL" },
    { "RoCode": "16598940", "Result": "MAA DHANOP PETROLIEUM-Paytm" },
    { "RoCode": "16598980", "Result": "SHANKER PETROLEUM-Paytm" },
    { "RoCode": "16599140", "Result": "MS HSD KHIOWAL FILLING STATIO-Paytm" },
    { "RoCode": "16598780", "Result": "GAZY FILLING STATION -Paytm" },
    { "RoCode": "11517110", "Result": "JAGDEMBA FILLING STATION-IMSL" },
    { "RoCode": "16649420", "Result": "TRIPUTI HP FILLING STATION-IMSL" },
    { "RoCode": "16649720", "Result": "BHURAJIHPAND SONS-IMSL" },
    { "RoCode": "16599330", "Result": "BHAGWAN HP FILLING STATION-Paytm" },
    { "RoCode": "16599900", "Result": "SHREE DEV HP FILLING STATION-Paytm" },
    { "RoCode": "16599800", "Result": "RAJ FILLING STATION-Paytm" },
    { "RoCode": "16647250", "Result": "RAMESHWARI HP FILLING STATION-IMSL" },
    { "RoCode": "11508010", "Result": "CHHAGANWAL BAGTAWARMAL-Paytm" },
    { "RoCode": "16635990", "Result": "MS HSD GARIB NIWAZ HP FILLING-IMSL" },
    { "RoCode": "16598920", "Result": "SHRI HARI PETROLEUM-Paytm" },
    { "RoCode": "16647290", "Result": "RADHA KRISHNA PETROLIEUM-IMSL" },
    { "RoCode": "16647420", "Result": "SHREE GANESH HP -IMSL" },
    { "RoCode": "16647430", "Result": "ASHOK PETROLEUM-IMSL" },
    { "RoCode": "16647440", "Result": "PARAM GURUKRIPA FILLING STATIO-IMSL" },
    { "RoCode": "16649520", "Result": "SHRI CHARBHUJA PETROLEUM-Paytm" },
    { "RoCode": "11605010", "Result": "MAHAVEER SERVICE STN.-Paytm" },
    { "RoCode": "16647910", "Result": "GIRRAJ BABA FILLING STATION-Paytm" },
    { "RoCode": "11503010", "Result": "THA NATIONAL AUTO SUPPLY-Paytm" },
    { "RoCode": "11525010", "Result": "RAMESH CHAND BIDHA RAM-0" },
    { "RoCode": "16587200", "Result": "HAMARA PUMP CHIKSANA-Paytm" },
    { "RoCode": "16594340", "Result": "KANHAIYA SERVICE STATION-Paytm" },
    { "RoCode": "16594150", "Result": "Shubhlaxmi Filling Station-0" },
    { "RoCode": "16594740", "Result": "SADHNA H.P.-Paytm" },
    { "RoCode": "16594900", "Result": "NANDANI HP-IMSL" },
    { "RoCode": "16595840", "Result": "SHUKLA FILLING STATION-Paytm" },
    { "RoCode": "16549710", "Result": "GREEN GLOBE CHARITABLE TRUST-Paytm" },
    { "RoCode": "11470910", "Result": "UDAI CHAND MITTAL-Paytm" },
    { "RoCode": "16595500", "Result": "SHRI RAM FILLING STATION-Paytm" },
    { "RoCode": "16637620", "Result": "A S FILLING STATION-Paytm" },
    { "RoCode": "16594460", "Result": "SOLANKI FILLING STATION-Paytm" },
    { "RoCode": "16584710", "Result": "Hamara Pump Angrawali-Paytm" },
    { "RoCode": "11492410", "Result": "TRILOK FILLING STATION-Paytm" },
    { "RoCode": "16647900", "Result": "Maa Mahakali Filling Station-IMSL" },
    { "RoCode": "16647970", "Result": "SHRI LAXMI FILLING STATION-Paytm" },
    { "RoCode": "16647630", "Result": "Urmila Filling Station-Paytm" },
    { "RoCode": "16598340", "Result": "Shivam Filling Station-Paytm" },
    { "RoCode": "16598860", "Result": "Abhilasha Service Station-Paytm" },
    { "RoCode": "16550810", "Result": "Hamara Pump Mayla-Paytm" },
    { "RoCode": "16650160", "Result": "Jai Hind Filling Station-Paytm" },
    { "RoCode": "16647610", "Result": "PREM FILLING STATION-Paytm" },
    { "RoCode": "16598890", "Result": "SHIV SHAKTI FILLING STATION-Paytm" },
    { "RoCode": "16598020", "Result": "SHREE BANKEY BIHARI AUTOMOBILE-Paytm" },
    { "RoCode": "16599990", "Result": "MAHARAJA MOOL SINGH FS-Paytm" },
    { "RoCode": "16633700", "Result": "Shree Ramdoot FS-Paytm" },
    { "RoCode": "16530810", "Result": "HAMARA PUMP SANGOD-Paytm" },
    { "RoCode": "16550710", "Result": "HAMARA PUMP KARWAR-IMSL" },
    { "RoCode": "16598320", "Result": "HONEY FILLING STATION-Paytm" },
    { "RoCode": "16650100", "Result": "Yashoda Filling Station-Paytm" },
    { "RoCode": "16584510", "Result": "HAMARA PUMP BHAWANIPURA-Paytm" },
    { "RoCode": "16598090", "Result": "Soni Filling Station-Paytm" },
    { "RoCode": "16584610", "Result": "Hamara Pump Khatoli-Paytm" },
    { "RoCode": "16598310", "Result": "Shri Satguru Filling Satation-Paytm" },
    { "RoCode": "16556810", "Result": "Hamara Pump Barod-Paytm" },
    { "RoCode": "16652650", "Result": "ADHOC GS Filling Station-Paytm" },
    { "RoCode": "16599070", "Result": "AGRAWAL SERVICE STATION-Paytm" },
    { "RoCode": "16599180", "Result": "Hamara Pump Mundla-Paytm" },
    { "RoCode": "16599630", "Result": "VINAYAK PETROLEUM-Paytm" },
    { "RoCode": "16598120", "Result": "RAJ FILLING STATION-Paytm" },
    { "RoCode": "16599310", "Result": "UTTAM PETROLEUM CORPORATION-Paytm" },
    { "RoCode": "11556110", "Result": "MARUTI FILLING STATION-Paytm" },
    { "RoCode": "16599410", "Result": "Shivam Service Station-Paytm" },
    { "RoCode": "16647620", "Result": "MAHAVEER FILLING STATION-Paytm" },
    { "RoCode": "16647650", "Result": "ARHAM FILLING STATION-Paytm" },
    { "RoCode": "16650170", "Result": "ANAND FILLING STATION-IMSL" },
    { "RoCode": "16650180", "Result": "AMAN FILLING STATION-IMSL" },
    { "RoCode": "16652600", "Result": "BALAJI REFUELING STATION-Paytm" },
    { "RoCode": "16550610", "Result": "AGRAWAL FILLING STATION-Paytm" },
    { "RoCode": "16652520", "Result": "ROOPGANGA FILLING STATION-IMSL" },
    { "RoCode": "11535210", "Result": "ROHIT SERVICE STATION-Paytm" },
    { "RoCode": "16599060", "Result": "RAJAT FILLING STATION-Paytm" },
    { "RoCode": "11483010", "Result": "NAVRANG OIL COMPANY-Paytm" },
    { "RoCode": "16594020", "Result": "MAHANANDA FILLING STATION-Paytm" },
    { "RoCode": "16599690", "Result": "shri parshvnath petroleum-Paytm" },
    { "RoCode": "16652960", "Result": "ADHOC ROOPGANGA FILLING STN-Paytm" },
    { "RoCode": "11684020", "Result": "GURUBUX SINGH INDERPAL SINGH-Paytm" },
    { "RoCode": "16634800", "Result": "SHREE JI PETROLEUM-Paytm" },
    { "RoCode": "12048010", "Result": "RAJASTHAN PETROLEUM HOUSE-Paytm" },
    { "RoCode": "16650450", "Result": "SHRI BALAJI FULES-Paytm" },
    { "RoCode": "16587020", "Result": "KARGIL HERO FUEL STATION-Paytm" },
    { "RoCode": "16647930", "Result": "SHRI BALAJI PETROLEUM-Paytm" },
    { "RoCode": "16633800", "Result": "R R FILLING STATION-Paytm" },
    { "RoCode": "16650460", "Result": "CHETAK PETROLUM-Paytm" },
    { "RoCode": "16599270", "Result": "DEEPAK PETROLEUM-Paytm" },
    { "RoCode": "16636160", "Result": "Shri Kalyan Petroleum-Paytm" },
    { "RoCode": "16582410", "Result": "SHRI KARNI FILLING STATION-Paytm" },
    { "RoCode": "16599290", "Result": "MOHAN FILLING STATION -IMSL" },
    { "RoCode": "11465510", "Result": "SWASTIK MOTORS-Paytm" },
    { "RoCode": "16633670", "Result": "CHARBHUJA FILLING STATION-Paytm" },
    { "RoCode": "16636030", "Result": "SHIVAM FUELS-Paytm" },
    { "RoCode": "16633780", "Result": "YASH PETROLIEUM-Paytm" },
    { "RoCode": "11593012", "Result": "SARDAR MOTOR SERVICE HSD-Paytm" },
    { "RoCode": "16650050", "Result": "SHREE BHAGWAT FILLING STATION-IMSL" },
    { "RoCode": "16647990", "Result": "SHIV SHAKTI FILLING STATION-IMSL" },
    { "RoCode": "16587610", "Result": "HAMARA PUMP-Paytm" },
    { "RoCode": "16633600", "Result": "SHRI BHAIRAW PETROLEUM-Paytm" },
    { "RoCode": "16633550", "Result": "SHRIMAT PETRO-DIESEL PUMP-Paytm" },
    { "RoCode": "11465310", "Result": "GANGWAL SERVICE STATION-Paytm" },
    { "RoCode": "11466510", "Result": "JAIN BROTHERS-Paytm" },
    { "RoCode": "16598270", "Result": "R S Filling Station-Paytm" },
    { "RoCode": "16599250", "Result": "SHRIJI TRADERS-Paytm" },
    { "RoCode": "16633660", "Result": "GARG PETROLEUM-Paytm" },
    { "RoCode": "16633680", "Result": "SHANTI SAINI FILLING STATION-Paytm" },
    { "RoCode": "16647940", "Result": "NL MUNDAWADIYA PETROLEUM-IMSL" },
    { "RoCode": "16647950", "Result": "NAVKAR FILLING STATION-Paytm" },
    { "RoCode": "16647980", "Result": "PATEL PETROLEUM-IMSL" },
    { "RoCode": "16650000", "Result": "VISHWAKARMA FILLING STATION-IMSL" },
    { "RoCode": "16650010", "Result": "SHREE BHAIRAVAAYA FILLING STN-Paytm" },
    { "RoCode": "16650020", "Result": "SHREE BALAJI PETROL PUMP-IMSL" },
    { "RoCode": "16650040", "Result": "RADHA RAMAN PETROLEUM-Paytm" },
    { "RoCode": "16650060", "Result": "MATESHWARI FILLING STATION-IMSL" },
    { "RoCode": "16650070", "Result": "SHRI BALAJI PETROLEUM-IMSL" },
    { "RoCode": "16650090", "Result": "KGN FILLING STATION-Paytm" },
    { "RoCode": "16650490", "Result": "SHRI RAM PETROLEUM-Paytm" },
    { "RoCode": "16652990", "Result": "Adhoc Shivam Fuels-Paytm" },
    { "RoCode": "16633540", "Result": "KARNI PETROLEUM-Paytm" },
    { "RoCode": "16599420", "Result": "KULDEEP AUTOMOBILES -Paytm" },
    { "RoCode": "16599450", "Result": "MUNDRA PETROLEUM-Paytm" },
    { "RoCode": "16595110", "Result": "BHAGIRATH FILLING STATION-Paytm" },
    { "RoCode": "16650320", "Result": "Parasram Rajora Filling Statio-Paytm" },
    { "RoCode": "16594620", "Result": "Shri Krishna HP Automobile-Paytm" },
    { "RoCode": "16636010", "Result": "Ranthambore Highway Fs-Paytm" },
    { "RoCode": "16636350", "Result": "Deavashish Filling Station-Paytm" },
    { "RoCode": "16650030", "Result": "BALAJI FILLING STATION-Paytm" },
    { "RoCode": "16595400", "Result": "Solanki FIlling Station-Paytm" },
    { "RoCode": "16595460", "Result": "RAJ SERVICE STATION-Paytm" },
    { "RoCode": "16595860", "Result": "AvtarSingh Filling station-Paytm" },
    { "RoCode": "16403910", "Result": "SHRI GANPATI SERVICE STN-Paytm" },
    { "RoCode": "11471710", "Result": "ASHOKA HP FUEL CENTRE-Paytm" },
    { "RoCode": "16634150", "Result": "SHRI HARSH FILIING-Paytm" },
    { "RoCode": "16634260", "Result": "Manmohan Enterprises-Paytm" },
    { "RoCode": "11529110", "Result": "NARUKA MOTORS-Paytm" },
    { "RoCode": "11548010", "Result": "VISHWANATH AND COMPNY-Paytm" },
    { "RoCode": "16528410", "Result": "BAJRANG FILLING STATION-Paytm" },
    { "RoCode": "16595470", "Result": "ARUN FILLING STATION-Paytm" },
    { "RoCode": "16650360", "Result": "KAMLA FILLING STATION-Paytm" },
    { "RoCode": "16637640", "Result": "suraj filling station-Paytm" },
    { "RoCode": "16599040", "Result": "HAMARA PUMP DATWAS-Paytm" },
    { "RoCode": "16594650", "Result": "JAI KAILA MAIYA FILLING STN-Paytm" },
    { "RoCode": "16598850", "Result": "Shivam Filling Station-Paytm" },
    { "RoCode": "16495810", "Result": "janta filling station-Paytm" },
    { "RoCode": "16633980", "Result": "JAIN FILLING STATION-Paytm" },
    { "RoCode": "11553110", "Result": "Shree Narsingh Automobiles-IMSL" },
    { "RoCode": "16595000", "Result": "HAMARA PUMP MALARNA-Paytm" },
    { "RoCode": "16647830", "Result": "Poswal Filling Station-Paytm" },
    { "RoCode": "16587210", "Result": "HAMARA PUMP PAHARI-Paytm" },
    { "RoCode": "11468810", "Result": "AGARWAL OIL COMPANY-Paytm" },
    { "RoCode": "16595160", "Result": "HAMARA PUMP SHIWAR-Paytm" },
    { "RoCode": "16637790", "Result": "SHREE NARSINGH FILLING STATION-IMSL" },
    { "RoCode": "16647820", "Result": "Bhagwati Filling Station-Paytm" },
    { "RoCode": "16647840", "Result": "RISHIKA FILLING STATION-Paytm" },
    { "RoCode": "16647850", "Result": "Shreeji Filling Station-Paytm" },
    { "RoCode": "16647860", "Result": "Balaji Service Station-IMSL" },
    { "RoCode": "16647880", "Result": "Himanshu Filling Station-IMSL" },
    { "RoCode": "16650330", "Result": "Shri Narayan Filling Station-IMSL" },
    { "RoCode": "16650340", "Result": "Shree Shyam Filling STN-Paytm" },
    { "RoCode": "16650350", "Result": "Maa Filling Station-Paytm" },
    { "RoCode": "16650370", "Result": "MAA SHANTI FILLING STATION-Paytm" },
    { "RoCode": "16650380", "Result": "Siya Ram Filling STN-IMSL" },
    { "RoCode": "16598760", "Result": "Hamara Pump Jain FS-Paytm" },
    { "RoCode": "16598690", "Result": "shri kalyan filling station-Paytm" },
    { "RoCode": "16598550", "Result": "Arun Filling Station-Paytm" },
    { "RoCode": "16599340", "Result": "Shree Kanha Filling Station-Paytm" },
    { "RoCode": "16647740", "Result": "Reyansh Fuels-IMSL" },
    { "RoCode": "16083910", "Result": "Master Service Station-Paytm" },
    { "RoCode": "16599730", "Result": "HP Raja Rajveer F S-Paytm" },
    { "RoCode": "16598250", "Result": "Mahalaxmi Filling Station-Paytm" },
    { "RoCode": "16633510", "Result": "Mala Service Station-Paytm" },
    { "RoCode": "16633890", "Result": "Patidar Fuels-Paytm" },
    { "RoCode": "16494610", "Result": "Shrinath Filling Station-Paytm" },
    { "RoCode": "16512610", "Result": "Kamkhera Filling Station-Paytm" },
    { "RoCode": "16550510", "Result": "Hamara Pump Bakani-Paytm" },
    { "RoCode": "16599080", "Result": "National Fuel Station-Paytm" },
    { "RoCode": "16633590", "Result": "Riddhima Filling Station-Paytm" },
    { "RoCode": "16494510", "Result": "Bala ji filling station-Paytm" },
    { "RoCode": "16598110", "Result": "Ambika Filling Station-Paytm" },
    { "RoCode": "16599740", "Result": "HP Raja Kamkhera Balaji FS-Paytm" },
    { "RoCode": "16599240", "Result": "Sanwariya Filling Station-Paytm" },
    { "RoCode": "16598540", "Result": "RISHABH FILLING STATION-Paytm" },
    { "RoCode": "16599670", "Result": "Hamara Pomp Oswal FS-Paytm" },
    { "RoCode": "16558910", "Result": "Dr. BS Chandrawat FS-Paytm" },
    { "RoCode": "11542110", "Result": "Kapil Filling Station-Paytm" },
    { "RoCode": "16598150", "Result": "Hamara Pump Manoharthana-0" },
    { "RoCode": "16598260", "Result": "Shree Balaji filling station-Paytm" },
    { "RoCode": "16598800", "Result": "Menash Trading Company-Paytm" },
    { "RoCode": "16599190", "Result": "HP Raja Arihant FS-IMSL" },
    { "RoCode": "16599350", "Result": "Satyam Filling Station-Paytm" },
    { "RoCode": "16599490", "Result": "BABA FILLING STATION-Paytm" },
    { "RoCode": "16599620", "Result": "Mayank Filling Station-Paytm" },
    { "RoCode": "16599760", "Result": "HP Raja Shree Balaji Petrolem-Paytm" },
    { "RoCode": "16633500", "Result": "HP Raja Nageshwar F S-IMSL" },
    { "RoCode": "16633870", "Result": "Jai Gurudev Filling Station-Paytm" },
    { "RoCode": "16633880", "Result": "Annapurna Service Station-Paytm" },
    { "RoCode": "16636080", "Result": "MAHAKAL FILLING STATION-Paytm" },
    { "RoCode": "16647750", "Result": "JAYRAJ FILLING STATION-IMSL" },
    { "RoCode": "16599710", "Result": "HP Raja Bharadiya FS-Paytm" },
    { "RoCode": "16598900", "Result": "GAUGHAT FILLING STATION-Paytm" }];

        submitRoCode.onclick = function() {
            const roCode = document.getElementById('roCode').value;
            const result = roData.find(item => item.RoCode === roCode);
            if (result) {
                resultMessage.style.display = 'block'; // Show result box
                resultMessage.textContent = `Result: ${result.Result}`;
                resultMessage.style.border = '1px solid #007BFF'; // Optional: Add border
            } else {
                resultMessage.style.display = 'block'; // Show result box
                resultMessage.textContent = 'Ro Code not found.';
                resultMessage.style.border = '1px solid red'; // Optional: Add border
            }
        };

        toggleArrow.onclick = function() {
            const isVisible = criticalProbeContent.style.display === 'block';
            criticalProbeContent.style.display = isVisible ? 'none' : 'block';
            toggleArrow.innerHTML = isVisible ? '<i class="fas fa-chevron-down"></i> Critical ATG Probe Snaps' : '<i class="fas fa-chevron-up"></i> Critical ATG Probe Snaps';
        };

        loginButton.addEventListener('click', function () {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            // Show loading indicator
            loadingIndicator.style.display = 'block';
            loginMessage.style.display = 'none'; // Hide previous error message

            // Simulate a delay for loading (remove this in production)
            setTimeout(() => {
                // Check credentials
                if (username === 'Orpak' && password === 'U$4F7dc8') {
                    loginMessage.textContent = '';
                    loginContainer.style.display = 'none';
                    mainContent.style.display = 'block';
                    sopContent.style.display = 'block';
                    noticeBoard.style.display = 'block';
                    updatesBoard.style.display = 'block';
                    criticalProbeSnaps.style.display = 'none'; // Hide the critical probe snaps box
                    loginIcon.style.display = 'none';
                    logoutIcon.style.display = 'block';
                    logoutIcon.classList.add('highlight');

                    // Show the dark green icon
                    darkGreenIcon.style.display = 'flex';

                    // Show all notices immediately
                    notices.forEach(notice => {
                        notice.style.display = 'block';
                    });
                } else {
                    loginMessage.textContent = 'Invalid username or password.';
                    loginMessage.style.display = 'block'; // Show error message
                }

                // Hide loading indicator
                loadingIndicator.style.display = 'none';
            }, 1000); // Simulated loading time
        });

        logoutIcon.addEventListener('click', function () {
            loginContainer.style.display = 'block';
            mainContent.style.display = 'none';
            sopContent.style.display = 'none';
            noticeBoard.style.display = 'none';
            updatesBoard.style.display = 'none';
            criticalProbeSnaps.style.display = 'block'; // Show the critical probe snaps box again
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
            loginIcon.style.display = 'block';
            logoutIcon.style.display = 'none';
            logoutIcon.classList.remove('highlight');

            // Hide the dark green icon
            darkGreenIcon.style.display = 'none';

            // Reset notices display
            notices.forEach(notice => {
                notice.style.display = 'none';
            });
        });
    </script>
</body>
</html>
