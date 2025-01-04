<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexa Bot Status</title>
    <style>
        /* Allgemeine Einstellungen */
        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            font-family: 'Arial', sans-serif;
            overflow: hidden;  /* Verhindert Scrollen */
        }

        /* Ladebildschirm mit dem Bild als Hintergrund */
        #loadingScreen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column; /* Text und Ladebalken untereinander anordnen */
            z-index: 1000; /* Setzt es über alle anderen Elemente */
            background: url('https://i.imgur.com/I5GvJTR.jpg') no-repeat center center/cover; /* Bild als Hintergrund */
            animation: colorChange 4s infinite alternate; /* Farbwechsel */
            opacity: 1;
            transition: opacity 1s ease-out;
        }

        /* Der Text "Lädt..." mit einer Galaxy Animation */
        .loading-text {
            font-size: 2rem;
            color: #39ff14;
            text-shadow: 0 0 5px #39ff14, 0 0 10px #39ff14, 0 0 20px #39ff14;
            animation: galaxyAnim 2s infinite alternate;
            margin-bottom: 20px; /* Abstand zwischen Text und Balken */
        }

        /* Galaxy Animation für den Text */
        @keyframes galaxyAnim {
            0% {
                transform: scale(1);
                opacity: 1;
            }
            100% {
                transform: scale(1.2);
                opacity: 0.6;
            }
        }

        /* Der Ladebalken */
        .progress-bar-container {
            width: 80%; /* Breite des Ladebalkens */
            height: 20px;
            background-color: rgba(0, 0, 0, 0.7);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }

        .progress-bar {
            width: 0%; /* Anfangsbreite des Balkens */
            height: 100%;
            background-color: #39ff14; /* Neon Green */
            border-radius: 10px;
            animation: loadProgress 4s linear forwards; /* Ladebalken Animation */
        }

        /* Ladebalken Animation (von 0% auf 100% in 4 Sekunden) */
        @keyframes loadProgress {
            0% {
                width: 0%;
            }
            100% {
                width: 100%;
            }
        }

        /* YouTube Video als Hintergrund */
        .background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1; /* Damit der Hintergrund hinter dem Inhalt bleibt */
        }

        /* Der iframe-Container für das Video */
        .background iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none; /* Verhindert, dass das Video Interaktionen blockiert */
            border: none;
        }

        /* Zentrale Box für den Inhalt */
        .container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            color: #fff;
            z-index: 1;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.7);
        }

        .status-box {
            background: rgba(0, 0, 0, 0.7);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
        }

        .status-box p {
            font-size: 1.5rem;
            margin: 10px 0;
            text-shadow: 1px 1px 5px rgba(0, 0, 0, 0.6);
        }

        .status-box .status {
            font-size: 1.2rem;
            color: #39ff14; /* Neon Green */
        }

        .footer {
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            color: #fff;
            font-size: 1rem;
            text-shadow: 1px 1px 5px rgba(0, 0, 0, 0.6);
        }

        .footer a {
            color: #39ff14;
            text-decoration: none;
        }

    </style>
</head>
<body>

    <!-- Ladebildschirm -->
    <div id="loadingScreen">
        <div class="loading-text">Lädt...</div>
        <div class="progress-bar-container">
            <div class="progress-bar"></div>
        </div>
    </div>

    <!-- YouTube Video Hintergrund -->
    <div class="background">
        <iframe src="https://www.youtube.com/embed/eTD0WWFIDAg?autoplay=1&mute=1&loop=1&playlist=eTD0WWFIDAg&modestbranding=1&controls=0&showinfo=0&rel=0"
                frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>

    <!-- Inhalt Container -->
    <div class="container">
        <h1>Nexa Bot Status</h1>

        <!-- Status Box -->
        <div class="status-box">
            <p><strong>Bot Status:</strong> <span class="status">Online</span></p>
        </div>
    </div>

    <!-- Footer -->
    <div class="footer">
        <p>Gemacht von <a href="https://www.nexastudios.com" target="_blank">Nexa Studios</a></p>
    </div>

    <!-- JavaScript für den Ladebildschirm -->
    <script>
        // Nach 4 Sekunden Ladebildschirm ausblenden
        setTimeout(function() {
            document.getElementById('loadingScreen').style.opacity = 0;
        }, 4000);
    </script>

</body>
</html>
