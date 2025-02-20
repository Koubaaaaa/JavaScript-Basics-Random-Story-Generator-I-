JavaScript Basics & Random Story Generator I 

📄 Beschrijving

Deze eenvoudige webpagina toont een willekeurig woord uit een vooraf gedefinieerde lijst in een zin.

🧱 Opbouw van de code

1. HTML-structuur

`<!doctype html>`
`<html>`
  `<head>`
    `<meta charset="UTF-8" />`
    `<meta name="viewport" content="width=device-width" />`
    `<link rel="icon" href="images/favicon.png" />`
    `<title>JavaScript basics</title>`
  `</head>`
  `<body>`
    `<h1>Random woord</h1>`
    `<p>Mohamed is <mark id="randomTekst"></mark>.</p>`
    `<script src="script.js"></script>`
  `</body>`
`</html>`

2. JavaScript-functionaliteit

`document.addEventListener("DOMContentLoaded", function() {
    // Array Lijst met willekeurige woorden
    let randomWoorden = ["geweldig", "cool", "de beste", "fantastisch", "uitzonderlijk", "indrukwekkend"];

    // Kies een willekeurig woord
    let gekozenWoord = Math.floor(Math.random() * randomWoorden.length);
    
    // Voeg het gekozen woord toe aan de HTML-tag met id = "randomTekst"
    document.getElementById("randomTekst").innerHTML = randomWoorden[gekozenWoord];
});`

