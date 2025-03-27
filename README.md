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
        <h1>Vertretungsplan</h1>
        <select id="classSelect">
            <option value="5a">5A</option>
            <option value="5b">5B</option>
            <option value="5c">5C</option>
            <option value="5e">5E</option>
            <option value="6a">6A</option>
            <option value="6b">6B</option>
            <option value="6c">6C</option>
            <option value="6e">6E</option>
            <option value="7a">7A</option>
            <option value="7b">7B</option>
            <option value="7c">7C</option>
            <option value="7e">7E</option>
            <option value="8a">8A</option>
            <option value="8b">8B</option>
            <option value="8c">8C</option>
            <option value="8e">8E</option>
            <option value="9a">9A</option>
            <option value="9b">9B</option>
            <option value="9c">9C</option>
            <option value="9e">9E</option>
            <option value="10a">10A</option>
            <option value="10b">10B</option>
            <option value="10c">10C</option>
            <option value="10e">10E</option>
        </select>
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
            <div class="plan" id="planContent">
                <!-- Die Zeilen für die Stunden kommen hier dynamisch -->
            </div>
        </div>

        <div class="info-panel">
            <h2>Wichtige Informationen</h2>
            <div class="info" id="infoContent">
                <!-- Dynamische Informationen für die Klasse und Gruppe -->
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

select {
    font-size: 16px;
    padding: 10px;
    margin-top: 10px;
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

#planContent {
    display: flex;
    flex-direction: column;
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
// Plan für jede Klasse (von 5A bis 10E)
const plans = {
    "5a": [
        ["Mathe", "Englisch", "Biologie", "Chemie", "Deutsch"],
        ["Englisch", "Mathe", "Biologie", "Sport", "Französisch"],
        ["Mathe", "Deutsch", "Biologie", "Sport", "Geografie"],
        ["Englisch", "Mathe", "Chemie", "Französisch", "Geschichte"],
        ["Deutsch", "Sport", "Chemie", "Mathe", "Französisch"]
    ],
    "5b": [
        // Pläne für 5B (kann nach Bedarf angepasst werden)
    ],
    // Weitere Klassen hier hinzufügen (6a, 6b, 7a, usw.)
    "10a": [
        // Beispielplan für 10A
        ["Mathe", "Deutsch", "Englisch", "Chemie", "Sport"],
        ["Mathe", "Französisch", "Biologie", "Englisch", "Geografie"],
        ["Deutsch", "Englisch", "Sport", "Französisch", "Mathe"],
        ["Chemie", "Biologie", "Englisch", "Mathe", "Deutsch"],
        ["Französisch", "Sport", "Mathe", "Englisch", "Deutsch"]
    ],
    // Weiterhin für 10b, 10c, 10e etc.
};

// Wichtige Informationen pro Klasse und Gruppe
const info = {
    "5a": "Woche der Mathe-Wiederholung. Bitte vorbereiten.",
    "10a": "Woche der Prüfungsvorbereitung. Beachte geänderte Zeiten für Deutsch.",
    // Weitere Infos für andere Klassen
};

// Funktion zum Wechseln der Klasse
document.getElementById("classSelect").addEventListener("change", function() {
    const selectedClass = this.value;
    updatePlan(selectedClass);
    updateInfo(selectedClass);
});

// Plan und Infos anzeigen
function updatePlan(className) {
    const planContent = document.getElementById("planContent");
    planContent.innerHTML = ""; // Plan zurücksetzen

    if (plans[className]) {
        plans[className].forEach(day => {
            const stundeRow = document.createElement("div");
            stundeRow.classList.add("stunde");
            day.forEach(fach => {
                const fachDiv = document.createElement("div");
                fachDiv.classList.add("fach");
                fachDiv.textContent = fach;
                stundeRow.appendChild(fachDiv);
            });
            planContent.appendChild(stundeRow);
        });
    }
}

function updateInfo(className) {
    const infoContent = document.getElementById("infoContent");
    infoContent.innerHTML = ""; // Infos zurücksetzen

    if (info[className]) {
        const infoParagraph = document.createElement("p");
        infoParagraph.textContent = info[className];
        infoContent.appendChild(infoParagraph);
    }
}

// Initialer Plan laden (z.B. für 5A)
updatePlan("5a");
updateInfo("5a");
