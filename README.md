# TD n°2: Introduction à JavaScript - Évènements

Ce dépôt contient une série d'exercices pratiques conçus pour vous aider à comprendre et à maîtriser les événements en JavaScript. Chaque exercice aborde un concept différent, allant de la manipulation simple des éléments HTML à la création d'une calculatrice scientifique complète. Ces exercices sont parfaits pour les débutants en JavaScript et pour ceux qui souhaitent renforcer leurs compétences en programmation web.
---
## Exercice 1 : Permutation

### Objectif
L'objectif de cet exercice est de créer un formulaire simple contenant deux zones de texte et un bouton. Lorsque l'utilisateur clique sur le bouton, le contenu des deux zones de texte est permuté. Cet exercice est un classique en programmation et permet de comprendre comment manipuler les valeurs des éléments HTML avec JavaScript.

### Aperçu
1. Ouvrez le fichier `ex1.html` dans votre navigateur.
2. Entrez deux textes différents dans les deux zones de texte.
3. Cliquez sur le bouton "Permuter" pour voir le contenu des deux zones échangé.

### Structure du Code
Le code HTML crée deux champs de texte (`input`) et un bouton. Lorsque l'utilisateur clique sur le bouton, la fonction JavaScript `Permuter()` est appelée. Cette fonction récupère les valeurs des deux champs, les échange, puis les réassigne aux champs.

### Exemple

[🎥 Voir la démonstration](Videos/permutation.mp4)

### Code JavaScript

```markdown

```javascript
function Permuter() {
    var Nb1 = N1.value; // Récupère la valeur du premier champ
    var Nb2 = N2.value; // Récupère la valeur du deuxième champ
    N1.value = Nb2;     // Affecte la valeur du deuxième champ au premier
    N2.value = Nb1;     // Affecte la valeur du premier champ au deuxième
}
```
---

## Exercice 2 : Calculatrice Simple

### Objectif
Cet exercice consiste à créer une calculatrice simple capable d'effectuer les quatre opérations arithmétiques de base : addition, soustraction, multiplication et division. La page contient trois zones de texte : deux pour les nombres et une pour afficher le résultat, ainsi que quatre boutons pour les opérations.

### Aperçu
1. Ouvrez le fichier `ex2.html` dans votre navigateur.
2. Entrez deux nombres dans les deux premières zones de texte.
3. Cliquez sur l'un des boutons d'opération (+, -, *, /) pour afficher le résultat dans la troisième zone de texte.

### Structure du Code
Le code HTML crée trois champs de texte et quatre boutons. Chaque bouton appelle la fonction JavaScript `Op()` avec l'opération correspondante en paramètre. La fonction effectue le calcul et affiche le résultat dans le troisième champ.

### Exemple

<video controls src="Videos/Calcul simple.mp4" title="Calcul Simple"></video>

### Code JavaScript
```javascript
function Op(Value) {
    switch(Value) {
        case "+":
            N3.value = parseFloat(N1.value) + parseFloat(N2.value); // Addition
            break;
        case "-":
            N3.value = parseFloat(N1.value) - parseFloat(N2.value); // Soustraction
            break;
        case "*":
            N3.value = parseFloat(N1.value) * parseFloat(N2.value); // Multiplication
            break;
        case "/":
            N3.value = parseFloat(N1.value) / parseFloat(N2.value); // Division
            break;
    }
}
```

---

## Exercice 3 : Calcul IMC

### Objectif
L'objectif de cet exercice est de développer un calculateur d'indice de masse corporelle (IMC). L'IMC est une mesure couramment utilisée pour évaluer la corpulence d'une personne. Il est calculé en divisant le poids (en kg) par la taille (en mètres) au carré. Cet exercice permet de comprendre comment utiliser JavaScript pour effectuer des calculs et afficher des résultats dynamiques.

### Aperçu
1. Ouvrez le fichier `ex3.html` dans votre navigateur.
2. Entrez votre poids (en kg) et votre taille (en mètres) dans les zones de texte.
3. Cliquez sur le bouton "Calculer" pour afficher votre IMC et la catégorie correspondante (par exemple, "Corpulence normale", "Surpoids", etc.).

### Structure du Code
Le code HTML crée deux champs de texte pour le poids et la taille, un bouton pour déclencher le calcul, et un paragraphe pour afficher le résultat. La fonction JavaScript `Calculer()` effectue le calcul de l'IMC et détermine la catégorie en fonction de la valeur obtenue.

### Exemple

<video controls src="Videos/Calcul IMC.mp4" title="Title"></video>

### Code JavaScript
```javascript
function Calculer() {
    // Calcul de l'IMC
    let resultat = parseFloat(poids.value) / parseFloat(taille.value) ** 2;

    // Initialisation du message de catégorie
    let cat = "Votre IMC est de " + resultat.toFixed(2) + ". Vous êtes en état de ";

    // Détermination de la catégorie en fonction de l'IMC
    if (resultat < 18.5) {
        cat += "Insuffisance pondérale (maigreur)";
    } else if (resultat >= 18.5 && resultat < 25) {
        cat += "Corpulence normale";
    } else if (resultat >= 25 && resultat < 30) {
        cat += "Surpoids";
    } else if (resultat >= 30 && resultat < 35) {
        cat += "Obésité modérée";
    } else if (resultat >= 35 && resultat < 40) {
        cat += "Obésité sévère";
    } else if (resultat >= 40) {
        cat += "Obésité morbide ou massive";
    }

    // Affichage du résultat
    res.innerText = cat;
}
```

---

## Exercice 4 : Calculatrice Avancée

### Objectif
Cet exercice consiste à créer une calculatrice scientifique en utilisant JavaScript pour les calculs et CSS Grid pour la mise en page. La calculatrice prend en charge des opérations avancées telles que les fonctions trigonométriques, les logarithmes, les exponentielles, et bien plus encore.

### Aperçu
1. Ouvrez le fichier `ex4.html` dans votre navigateur.
2. Utilisez les boutons pour entrer des expressions mathématiques.
3. Cliquez sur "=" pour calculer le résultat.

### Structure du Code
Le code HTML utilise une grille CSS pour organiser les boutons de la calculatrice. Chaque bouton appelle la fonction JavaScript `getButtonValue()` avec la valeur du bouton en paramètre. La fonction gère les opérations spéciales (comme les fonctions trigonométriques) et construit l'expression mathématique. La fonction `calculate()` évalue l'expression et affiche le résultat.

### Exemple

<video controls src="Videos/Calcul Avancee.mp4" title="Title"></video>

### Code JavaScript
```javascript
let inverseMode = false;
var expression = "";

function toggleInverse(element) {
    inverseMode = !inverseMode; // Active ou désactive le mode inverse
    element.classList.toggle("active"); // Met en surbrillance le bouton
}

function getButtonValue(Value) {
    const operations = {
        "x²": { expr: "**2", display: "^2" },
        "x^": { expr: "**", display: "^" },
        "×": { expr: "*", display: "×" },
        "÷": { expr: "/", display: "÷" },
        "%": { expr: "/100", display: "%" },
        "π": { expr: Math.PI, display: "π" },
        "e": { expr: Math.E, display: "e" },
        "√": { expr: "Math.sqrt(", display: "√(" },
        "ln": { expr: "Math.log(", display: "ln(" },
        "log": { expr: "Math.log10(", display: "log(" },
        "EXP": { expr: "Math.exp(", display: "EXP(" },
        "cos": { expr: "Math.cos(", display: "cos(" },
        "sin": { expr: "Math.sin(", display: "sin(" },
        "tan": { expr: "Math.tan(", display: "tan(" },
    };

    if (operations[Value]) {
        expression += operations[Value].expr;
        display.innerText += operations[Value].display;
    } else {
        display.innerText += Value;
        expression += Value;
    }
}

function calculate() {
    if (expression !== "") {
        display.innerText = eval(expression); // Évalue l'expression et affiche le résultat
        expression = eval(expression); // Met à jour l'expression avec le résultat
    }
}

function clearDisplay() {
    display.innerText = ""; // Efface l'affichage
    expression = ""; // Réinitialise l'expression
}
```

---

## Comment exécuter les exercices
1. Clonez ce dépôt sur votre machine locale.
2. Ouvrez chaque fichier HTML (`ex1.html`, `ex2.html`, `ex3.html`, `ex4.html`) dans votre navigateur web.
3. Suivez les instructions pour chaque exercice.
