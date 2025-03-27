- 👋 Hi, I’m @stsfkw2vertretungsplan
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
stsfkw2vertretungsplan/stsfkw2vertretungsplan is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vertretungsplan</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <header>
        <h1>Vertretungsplan der 10. Klasse</h1>
        <button class="admin-btn">Admin Login</button>
    </header>

    <div class="container">
        <div class="vertretungsplan">
            <div class="plan-header">
                <span>Montag</span>
                <span>Dienstag</span>
                <span>Mittwoch</span>
                <span>Donnerstag</span>
                <span>Freitag</span>
            </div>
            <div class="plan">
                <!-- Die Zeilen für die Stunden -->
                <div class="stunde">
                    <div class="fach">Mathematik</div>
                    <div class="fach">Englisch</div>
                    <div class="fach">Biologie</div>
                    <div class="fach">Chemie</div>
                    <div class="fach">Deutsch</div>
                </div>
                <!-- Weitere Stunden folgen hier -->
            </div>
        </div>

        <div class="info-panel">
            <h2>Wichtige Informationen</h2>
            <div class="info">
                <p>Es gibt eine Versammlung für alle Schüler der 10. Klasse um 14:00 Uhr am Mittwoch.</p>
                <p>Bitte beachten Sie den geänderten Stundenplan für den Donnerstag wegen einer Lehrerversammlung.</p>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2025 Vertretungsplan Schule</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #4CAF50;
    color: white;
    text-align: center;
    padding: 20px;
}

.container {
    display: flex;
    justify-content: space-between;
    padding: 20px;
}

.vertretungsplan {
    flex: 1;
    margin-right: 20px;
    overflow-x: auto;
}

.plan-header {
    display: flex;
    justify-content: space-between;
    font-weight: bold;
    background-color: #e2e2e2;
    padding: 10px;
}

.plan {
    display: flex;
    flex-direction: column;
}

.stunde {
    display: flex;
    padding: 15px;
    border-bottom: 1px solid #ddd;
}

.fach {
    flex: 1;
    padding: 10px;
    text-align: center;
    background-color: #fff;
    border-right: 1px solid #ddd;
}

.fach:last-child {
    border-right: none;
}

.info-panel {
    width: 300px;
    background-color: #ffffff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}

footer {
    text-align: center;
    padding: 10px;
    background-color: #4CAF50;
    color: white;
}

.admin-btn {
    background-color: #ff5733;
    color: white;
    padding: 10px;
    border: none;
    cursor: pointer;
    margin-top: 20px;
}

.admin-btn:hover {
    background-color: #d45d1c;
}
// Hier könnte ein einfaches Admin-Panel für Lehrer eingebaut werden
document.querySelector('.admin-btn').addEventListener('click', function() {
    alert("Admin Login für Lehrer (dieser Bereich ist noch in Arbeit).");
});

// Fügen Sie später Interaktivität hinzu, wie das Bearbeiten von Stundenplänen, Fächern usw.
