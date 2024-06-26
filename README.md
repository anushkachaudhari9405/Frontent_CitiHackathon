# Frontent_CitiHackathon
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Clickable Components</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
            position: relative;
        }

        .container {
            display: flex;
            gap: 20px;
            margin-top: auto;
            margin-bottom: auto;
        }

        .component {
            width: 150px;
            height: 150px;
            background-color: #3498db;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 20px;
            border-radius: 10px;
            transition: transform 0.3s, background-color 0.3s;
            cursor: pointer;
        }

        .component:hover {
            transform: scale(1.1);
            background-color: #2980b9;
        }

        .profile-icon {
            position: absolute;
            top: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: #2c3e50;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 24px;
            cursor: pointer;
        }

        .profile-icon:hover {
            background-color: #1a252f;
        }

        .name {
            position: absolute;
            top: 30px;
            left: 30px;
            font-size: 50px;
            font-weight: bold;
            color: #2c3e50;
        }

        .footer {
            position: absolute;
            bottom: 0;
            width: 100%;
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 10px 0;
        }

        .popup {
            position: absolute;
            top: 70px;
            right: 10px;
            width: 250px;
            background-color: white;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            display: none;
            flex-direction: column;
            z-index: 1000;
            transition: opacity 0.3s ease;
        }

        .popup-header {
            padding: 10px;
            background-color: #3498db;
            color: white;
            border-top-left-radius: 10px;
            border-top-right-radius: 10px;
            text-align: center;
        }

        .popup a {
            padding: 10px;
            text-decoration: none;
            color: #3498db;
            border-bottom: 1px solid #ccc;
            display: flex;
            justify-content: center;
        }

        .popup a:hover {
            background-color: #f0f0f0;
        }

        .popup a:last-child {
            border-bottom: none;
        }
    </style>
</head>
<body>
    <div class="name">Your Name</div>
    <div class="profile-icon" onclick="togglePopup()">
        <span>&#128100;</span>
    </div>
    <div class="popup" id="popupMenu">
        <div class="popup-header">Profile Options</div>
        <a href="profile1.html">Cart</a>
        <a href="profile2.html">History</a>
        <a href="profile3.html">Profile Option 3</a>
    </div>
    <div class="container">
        <div class="component" onclick="window.location.href='page1.html'">TCS</div>
        <div class="component" onclick="window.location.href='page2.html'">INFSYS</div>
        <div class="component" onclick="window.location.href='page3.html'">AXIS</div>
        <div class="component" onclick="window.location.href='page4.html'">TATA MOTORS</div>
    </div>
    <div class="footer">
        &copy; 2024 Your Name. All rights reserved.
    </div>

    <script>
        function togglePopup() {
            var popup = document.getElementById('popupMenu');
            if (popup.style.display === 'block') {
                popup.style.display = 'none';
            } else {
                popup.style.display = 'block';
            }
        }

        // Close the popup if clicked outside
        window.onclick = function(event) {
            var popup = document.getElementById('popupMenu');
            if (!event.target.matches('.profile-icon, .profile-icon *')) {
                if (popup.style.display === 'block') {
                    popup.style.display = 'none';
                }
            }
        }
    </script>
</body>
</html>
