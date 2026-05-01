# fantasy-kingdom-game
Bouw jouw eigen koninkrijk en vorm allianties of voer oorlog tegen andere koninkrijken 
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <title>Fantasy Kingdom</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<h1>🌍 Fantasy Kingdom</h1>

<div id="map-container">
    <img src="https://i.imgur.com/8QZ7Z6T.jpeg" id="map">
</div>

<div id="game-ui" class="hidden">
    <h2 id="kingdom-name"></h2>
    <p>💰 Goud: <span id="gold">0</span></p>
    <p>🌾 Voedsel: <span id="food">0</span></p>

    <button onclick="collectGold()">Verzamel goud</button>
    <button onclick="collectFood()">Verzamel voedsel</button>
</div>

<script src="script.js"></script>
body {
    font-family: Arial;
    text-align: center;
    background: #1e1e2f;
    color: white;
}

#map {
    width: 80%;
    cursor: pointer;
    border: 3px solid white;
}

.hidden {
    display: none;
}

button {
    margin: 10px;
    padding: 10px;
    font-size: 16px;
}
let kingdom = null;

document.getElementById("map").addEventListener("click", function() {
    if (!kingdom) {
        const name = prompt("Geef je koninkrijk een naam:");

        kingdom = {
            name: name,
            gold: 100,
            food: 50
        };

        document.getElementById("kingdom-name").innerText = name;
        updateUI();

        document.getElementById("game-ui").classList.remove("hidden");
    }
});

function collectGold() {
    kingdom.gold += 10;
    updateUI();
}

function collectFood() {
    kingdom.food += 5;
    updateUI();
}

function updateUI() {
    document.getElementById("gold").innerText = kingdom.gold;
    document.getElementById("food").innerText = kingdom.food;
}
</html>
