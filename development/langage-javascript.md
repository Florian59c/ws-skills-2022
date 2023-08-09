# Langage Javascript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les `structures` de base du langage ✔️
- les normes `ecmascript` ✔️
- l'utilisation de l'`asynchrone` ✔️
- les spécifités du mot-clef `this` ✔️

## 💻 Je code en Javascript

### Un exemple de code commenté ✔️

// creation d'une classe Client qui contient des informations
// chaque valeurs de cette classe seront différentes pour chaque instance en fonction des variables passées en parametre du constructor
class Client {
    constructor(prenom, nom, nbNuit, typeChambre, petitDej) {
        this.prenom = prenom;
        this.nom = nom;
        this.nbNuit = nbNuit;
        this.typeChambre = typeChambre;
        this.petitDej = petitDej;
    }
}

// création d'un tableau vide (qui contiendra des instances de Client)
let tabClient = [];

//évènement sur le clic d'un certain bouton par rapport à son id
let formElement = document.querySelector("#btn-entrer");
formElement.addEventListener("click", () =>
{
    // récupération des valeurs entrées par l'utilisateur dans la bonne variable grace à l'id
    let inputPrenom = document.querySelector("#inputprenom")
    let newPrenom = inputPrenom.value;
    let inputNom = document.querySelector("#inputnom");
    let newNom = inputNom.value;
    let inputnbNuit = document.querySelector("#inputnbnuit");
    let newnbNuit = inputnbNuit.value;
    let inputChambre = document.querySelector("#selectchambre");
    let newChambre = inputChambre.value;
    let newpetitDej;
    // verifie l'état du bouton radio pour changer la valeur de la variable "newpetitDej"
    if (document.querySelector("#radioOui").checked === true) { 
        newpetitDej = "oui";
    }
    else
        newpetitDej = "non";
    // ajout d'une case au tableau de clients qui contiendra une nouvelle instance de la classe Client (créée au dessus) et avec les données renseignés dans les formulaires (qui ont été mis dans les variables juste avant...)
    tabClient.push(new Client(newPrenom, newNom, newnbNuit, newChambre, newpetitDej));
    // on affiche le tableau de clients dans les logs
    console.log(tabClient);
});

### Utilisation dans un projet ✔️

Lien github : 
https://github.com/ze-sarah/Hotel_JS

Description :
il s'agit d'un projet réalisé en binome pendant ma formation DWWM.
Le but était de manipulé le DOM JS et d'utiliser les classes ainsi que des normes de l'ES6 (push, map, etc).

plus largement :
l'application enregistre les paramètre d'un client qui fait une réservation dans l'hotel.
Puis au moment du depart, recherche le client dans le tableau afin de calculer et afficher le prix du séjour.

### J'ai utilisé ce langage en production ✔️

https://hotel-deluxe-fcdw.web.app/

### J'ai utilisé ce langage en environement professionnel ✔️

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ❌

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌
- J'ai fait une [présentation](...) ❌

