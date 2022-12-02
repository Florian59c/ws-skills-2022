# Langage Javascript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les `structures` de base du langage ✔️
- les normes `ecmascript` ✔️
- l'utilisation de l'`asynchrone` ✔️
- les spécifités du mot-clef `this` ✔️

## 💻 Je code en Javascript

### Un exemple de code commenté ❌ / ✔️

class Client {
    constructor(prenom, nom, nbNuit, typeChambre, petitDej) {
        this.prenom = prenom;
        this.nom = nom;
        this.nbNuit = nbNuit;
        this.typeChambre = typeChambre;
        this.petitDej = petitDej;
    }
}

let tabClient = [];

// recup dans une variable la classe btn qui sont les boutons envoyer
let formElement = document.querySelector("#btn-entrer");
formElement.addEventListener("click", () => //quand on clique sur le bouton envoyer a l'entrer
{
    let inputPrenom = document.querySelector("#inputprenom")
    let newPrenom = inputPrenom.value;
    let inputNom = document.querySelector("#inputnom");
    let newNom = inputNom.value;
    let inputnbNuit = document.querySelector("#inputnbnuit");
    let newnbNuit = inputnbNuit.value;
    let inputChambre = document.querySelector("#selectchambre");
    let newChambre = inputChambre.value;
    let newpetitDej;
    if (document.querySelector("#radioOui").checked === true) { 
        // verifie que le bouton radio "oui" est cocher
        newpetitDej = "oui";
    }
    else
        newpetitDej = "non";
    tabClient.push(new Client(newPrenom, newNom, newnbNuit, newChambre, newpetitDej)); 
    // tabclient.push ajoute une case au tableau / dans la case, on met un client / les infos sur le client sont dans la parenthese
    console.log(tabClient);
});

### Utilisation dans un projet ✔️

projet effectué en groupe :
https://github.com/ze-sarah/Hotel_JS

Description :

### J'ai utilisé ce langage en production ✔️

https://hotel-deluxe-fcdw.web.app/

Description :

### J'ai utilisé ce langage en environement professionnel ❌

Description :

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

