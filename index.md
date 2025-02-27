# Je eerste JavaScript-code

In deze handleiding leer je stap voor stap hoe je je eerste JavaScript-code kunt schrijven en integreren in een HTML-bestand.

## 1. Maak een `script.js`-bestand aan

Begin met het aanmaken van een nieuw bestand genaamd `script.js`. Dit bestand zal je JavaScript-code bevatten.

## 2. Koppel je JavaScript-bestand aan je HTML

Om je JavaScript-bestand te koppelen, voeg je de volgende regel toe net voor de sluitende `</body>`-tag in je HTML-bestand:

> ```
> <script src="script.js"></script>
> ```

Plaats deze `<script>`-tag onderaan de body zodat de HTML-content eerst wordt geladen voordat het JavaScript-bestand wordt ingelezen. Dit zorgt ervoor dat de zichtbare delen van je pagina sneller worden weergegeven en dat de elementen die je met JavaScript wilt manipuleren al bestaan.

## 3. Schrijf JavaScript-code

### Alert

Voeg de volgende code toe aan `script.js`:

> ```
> document.addEventListener("DOMContentLoaded", function() {
>     alert('Dit is een ALERT!');
> });
> ```

Deze code toont een alert-venster zodra de HTML-pagina volledig is geladen.

### Console.log

Vervang de eerdere code in `script.js` door:

> ```
> document.addEventListener("DOMContentLoaded", function() {
>     console.log('Script werkt!');
> });
> ```

Deze code schrijft het bericht 'Script werkt!' naar de console van je browser, wat handig is voor debugging.

### HTML-code toevoegen

Om via JavaScript HTML-code toe te voegen, gebruik je:

> ```
> document.addEventListener("DOMContentLoaded", function() {
>     document.body.innerHTML = "<h1>Hallo, JavaScript!</h1><p>Zo maak je HTML code via JavaScript.</p>";
> });
> ```

Voor meerlijnige strings kun je backticks gebruiken:

> ```
> document.addEventListener("DOMContentLoaded", function() {
>     document.body.innerHTML = `
>         <h1>Hallo, JavaScript!</h1>
>         <p>Zo maak je HTML code via JavaScript.</p>
>     `;
> });
> ```

### Willekeurig woord toevoegen

Voeg in je HTML-bestand het volgende toe waar je de tekst wilt plaatsen:

> ```
> <h1>Random woord</h1>
> <p>Meneer Maes is <mark id="randomText"></mark>.</p>
> ```

In `script.js` voeg je de volgende code toe:

> ```
> document.addEventListener("DOMContentLoaded", function() {
>     // Lijst met willekeurige woorden
>     let randomWords = ["awesome", "cool", "de beste", "fantastisch", "uitzonderlijk", "indrukwekkend"];
> 
>     // Kies een willekeurig woord
>     let chosenWord = Math.floor(Math.random() * randomWords.length);
> 
>     // Voeg het gekozen woord toe aan de HTML-tag met id="randomText"
>     document.getElementById("randomText").innerHTML = randomWords[chosenWord];
> });
> ```

Deze code kiest een willekeurig woord uit de array `randomWords` en plaatst het in het element met het id `randomText`.

## 4. JavaScript basisprincipes

### Puntkomma (`;`)

In JavaScript wordt het puntkomma-symbool (`;`) gebruikt als een statement-terminator, wat betekent dat het aangeeft waar een bepaald statement eindigt. Hoewel het gebruik van puntkomma's niet strikt noodzakelijk is vanwege automatische puntkomma-invoeging, wordt het aanbevolen om ze expliciet toe te voegen om onverwachte resultaten en bugs te voorkomen.

### `document.addEventListener("DOMContentLoaded")`

De code `document.addEventListener("DOMContentLoaded", function() { ... });` zorgt ervoor dat de JavaScript-code pas wordt uitgevoerd nadat de HTML-pagina volledig is geladen. Dit is belangrijk wanneer je met JavaScript de HTML wilt manipuleren, zodat je zeker weet dat alle elementen beschikbaar zijn.

### Comments

In JavaScript kun je op twee manieren opmerkingen (comments) toevoegen aan je code:

**Enkelvoudige regelcomments:**

> ```
> // Dit is een enkelvoudige regelcomment
> let x = 5; // Je kunt ook comments op dezelfde regel als code plaatsen
> ```

**Meerregelige comments:**

> ```
> /*
> Dit is een meerregelige comment.
> Je kunt hier meerdere regels tekst toevoegen.
> Deze comments beginnen met /* en eindigen met */.
> */
> let y = 10;
> ```

Opmerkingen helpen je om je code beter te begrijpen en te onderhouden.

# 🎲 Random Story Generator: Deel 1

In deze handleiding leer je hoe je een dynamische website maakt die een verhaal toont met willekeurige elementen. Dit project gebruikt **HTML, CSS en JavaScript** om een willekeurig gegenereerd verhaal te maken.

---

## 🏗 Stap 1: Basis HTML-structuur

Maak een eenvoudig HTML-bestand en voeg een `span`-element toe waarin het weer dynamisch wordt aangepast.

> 📜 **HTML-bestand (`index.html`)**
> ```html
> <!DOCTYPE html>
> <html lang="nl">
> <head>
>     <meta charset="UTF-8">
>     <meta name="viewport" content="width=device-width, initial-scale=1.0">
>     <title>Random Story Generator</title>
>     <link rel="stylesheet" href="style.css">
> </head>
> <body>
>     <h1>📖 Mijn Random Verhaal</h1>
>     <p>On a <span id="weer">sunny</span> monday.</p>
>     <script src="script.js"></script>
> </body>
> </html>
> ```

📌 Dit stukje HTML bevat een zin met een variabele `<span id="weer"></span>` die later met JavaScript wordt aangepast.

---

## 🎭 Stap 2: JavaScript voor willekeurige woorden

Nu voegen we JavaScript toe om het weer in het verhaal willekeurig te veranderen bij elke herlaad van de pagina.

> 🎮 **JavaScript-bestand (`script.js`)**
> ```javascript
> document.addEventListener("DOMContentLoaded", function () {
>     // Lijst met mogelijke weertypes
>     let randomWordsWeer = ["sunny", "rainy", "misty", "hot", "cold", "dark"];
>
>     // Kies een willekeurig woord uit de lijst
>     let chosenWordWeer = Math.floor(Math.random() * randomWordsWeer.length);
>
>     // Vervang het weer in de HTML
>     document.getElementById("weer").innerHTML = randomWordsWeer[chosenWordWeer];
> });
> ```

📌 Deze code kiest een willekeurig woord uit de lijst en plaatst het in het `<span>`-element.

---

## 🎨 Stap 3: Styling met CSS

We maken de pagina aantrekkelijk met **CSS**. Dit bestand zorgt voor een mooi lettertype, kleuren en centrering.

> 🎨 **CSS-bestand (`style.css`)**
> ```css
> body {
>     font-family: 'Arial', sans-serif;
>     text-align: center;
>     background-color: #f4f4f4;
>     color: #333;
>     margin: 50px;
> }
>
> h1 {
>     color: #ff6600;
> }
>
> span {
>     font-weight: bold;
>     color: #007bff;
> }
> ```

📌 De **achtergrondkleur** is lichtgrijs, de **titel is oranje** en het **willekeurige woord krijgt een blauwe kleur**.

---

## ✅ Resultaat

Elke keer dat je de pagina ververst, verandert het verhaal automatisch! 🎉  

Wil je meer dynamiek toevoegen? Experimenteer met extra woorden of voeg personages toe met dezelfde methode.

