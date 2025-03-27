<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blade of the Fallen - Hub</title>
    <style>
        body {
            background-color: black;
            color: red;
            font-family: Arial, sans-serif;
        }
        header {
            text-align: center;
            padding: 20px;
            font-size: 2.5em;
            background-color: #222;
        }
        .container {
            width: 80%;
            margin: 0 auto;
        }
        nav {
            display: flex;
            justify-content: center;
            margin: 20px 0;
        }
        nav a {
            margin: 0 15px;
            padding: 10px 20px;
            background-color: red;
            color: white;
            text-decoration: none;
            font-size: 1.2em;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }
        nav a:hover {
            background-color: #cc0000;
        }
        .content-section {
            display: none;
        }
        .active {
            display: block;
        }
        .section-title {
            font-size: 2em;
            margin-top: 20px;
        }
        .section-content {
            margin-top: 10px;
            font-size: 1.2em;
        }
    </style>
</head>
<body>

    <header>
        Blade of the Fallen - Community Hub
    </header>

    <nav>
        <a href="javascript:void(0);" onclick="showPage('sword-discussion')">Sword Discussion</a>
        <a href="javascript:void(0);" onclick="showPage('general-info')">General Info</a>
        <a href="javascript:void(0);" onclick="showPage('updates')">Game Updates</a>
        <a href="javascript:void(0);" onclick="showPage('community-events')">Community Events</a>
    </nav>

    <div class="container">
        <div id="sword-discussion" class="content-section">
            <h2 class="section-title">Sword Discussion</h2>
            <p class="section-content">Share your thoughts and experiences about sword fighting in Blade of the Fallen.</p>
            <form class="comment-form">
                <input type="text" id="username" placeholder="Enter your username" required>
                <textarea id="comment" rows="4" placeholder="Write your comment here..." required></textarea>
                <button type="button" onclick="addComment('sword-discussion')">Submit Comment</button>
            </form>
            <div id="comments-container"></div>
        </div>

        <div id="general-info" class="content-section">
            <h2 class="section-title">General Information</h2>
            <p class="section-content">Welcome to Blade of the Fallen. Here you can learn about the game, its mechanics, and more.</p>
        </div>

        <div id="updates" class="content-section">
            <h2 class="section-title">Game Updates</h2>
            <p class="section-content">Stay updated on the latest patches and updates for Blade of the Fallen.</p>
        </div>

        <div id="community-events" class="content-section">
            <h2 class="section-title">Community Events</h2>
            <p class="section-content">Check out the upcoming events, challenges, and competitions hosted by the community.</p>
        </div>
    </div>

    <footer>
        <div class="container">
            <p>&copy; 2025 Blade of the Fallen. All rights reserved.</p>
        </div>
    </footer>

    <script>
        function showPage(pageId) {
            // Hide all sections
            var sections = document.querySelectorAll('.content-section');
            sections.forEach(function(section) {
                section.classList.remove('active');
            });

            // Show the selected section
            document.getElementById(pageId).classList.add('active');
        }

        function addComment(pageId) {
            var username = document.getElementById('username').value;
            var comment = document.getElementById('comment').value;
            if (username && comment) {
                var commentSection = document.createElement('div');
                commentSection.classList.add('comment-box');
                commentSection.innerHTML = `<strong>${username}</strong>: <p>${comment}</p>`;
                document.getElementById('comments-container').appendChild(commentSection);

                // Clear input fields
                document.getElementById('username').value = '';
                document.getElementById('comment').value = '';
            } else {
                alert("Please fill in both fields!");
            }
        }

        // Show the first section by default
        showPage('sword-discussion');
    </script>
</body>
</html>
