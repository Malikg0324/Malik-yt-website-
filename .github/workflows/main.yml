<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Video Link Player</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background: #333;
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }

        nav {
            background: #444;
            padding: 10px;
            text-align: center;
        }

        nav a {
            color: #fff;
            margin: 0 15px;
            text-decoration: none;
        }

        nav button {
            background: #555;
            color: #fff;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
        }

        .container {
            padding: 20px;
            text-align: center;
        }

        footer {
            background: #333;
            color: #fff;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            width: 100%;
            bottom: 0;
        }

        .hidden {
            display: none;
        }

        #searchBar {
            text-align: center;
            margin: 10px 0;
        }

        #searchBar input {
            padding: 5px;
            width: 200px;
        }

        #searchBar button {
            padding: 5px 10px;
        }

        #videoContainer {
            margin-top: 20px;
        }

        iframe {
            width: 80%;
            max-width: 560px;
            height: 315px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Video Link Player</h1>
        <nav>
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#contact">Contact</a>
            <button id="searchButton">Search</button>
        </nav>
    </header>

    <div id="searchBar" class="hidden">
        <input type="text" id="searchInput" placeholder="Type to search...">
        <button id="executeSearch">Go</button>
    </div>

    <div class="container">
        <section id="videoSection">
            <h2>Paste Video Link</h2>
            <input type="text" id="videoInput" placeholder="Paste video link here...">
            <button id="loadVideo">Load Video</button>
            <div id="videoContainer"></div>
        </section>

        <section id="home">
            <h2>Home</h2>
            <p>Welcome to the home section of the website.</p>
        </section>
        <section id="about">
            <h2>About</h2>
            <p>Learn more about what we do.</p>
        </section>
        <section id="contact">
            <h2>Contact Information</h2>
            <p>Email: info@example.com</p>
            <p>Phone: (123) 456-7890</p>
        </section>
    </div>

    <footer>
        <button onclick="goBack()">Back</button>
        <p>&copy; 2024 Video Link Player</p>
    </footer>

    <script>
        document.getElementById('searchButton').addEventListener('click', function() {
            var searchBar = document.getElementById('searchBar');
            if (searchBar.classList.contains('hidden')) {
                searchBar.classList.remove('hidden');
            } else {
                searchBar.classList.add('hidden');
            }
        });

        document.getElementById('executeSearch').addEventListener('click', function() {
            var query = document.getElementById('searchInput').value.toLowerCase();
            var sections = document.querySelectorAll('.container section');
            sections.forEach(function(section) {
                if (section.id === query) {
                    section.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        document.getElementById('loadVideo').addEventListener('click', function() {
            var videoLink = document.getElementById('videoInput').value;
            var videoContainer = document.getElementById('videoContainer');

            // Check if the link is a YouTube link
            if (videoLink.includes('youtube.com') || videoLink.includes('youtu.be')) {
                var videoID;

                // Extract video ID from YouTube link
                if (videoLink.includes('youtube.com')) {
                    var urlParams = new URLSearchParams(new URL(videoLink).search);
                    videoID = urlParams.get('v');
                } else if (videoLink.includes('youtu.be')) {
                    videoID = videoLink.split('/').pop();
                }

                // Append UTM parameters to track the source
                var utmParams = "?utm_source=video_queue&utm_medium=embed&utm_campaign=video_embed";
                var videoSrc = 'https://www.youtube.com/embed/' + videoID + utmParams;

                // Create iframe element
                var iframe = document.createElement('iframe');
                iframe.src = videoSrc;
                iframe.width = '560';
                iframe.height = '315';
                iframe.frameBorder = '0';
                iframe.allow = 'accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture';
                iframe.allowFullscreen = true;

                // Clear previous video and append new iframe
                videoContainer.innerHTML = '';
                videoContainer.appendChild(iframe);
            } else {
                videoContainer.innerHTML = 'Invalid YouTube URL';
            }
        });

        function goBack() {
            window.history.back();
        }
    </script>
</body>
</html>
