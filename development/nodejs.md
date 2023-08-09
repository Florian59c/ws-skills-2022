# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- Comment développer en utilisant un système de *livereloading* (`nodemon` par exemple) ✔️
- La connexion de mon application à une base de données avec et sans ORM/ODM (avec `mongodb` puis `mongoose` par exemple) ✔️
- Le développement d'une API REST et GraphQL (avec les packages `express` et `graphql` par exemple) ✔️
- *Bonus : la manipulation des fichiers système avec `fs` et l'utilisation des streams en NodeJS* ❌

## 💻 J'utilise

### Un exemple personnel commenté ✔️

const db = require('../db');
const user = require('../entity/user');

/** note : recuperation depuis le client
 * req.body recupere se qui se trouve dans le corp de la requete
 * req.params recupere les parametre dans le chemin http (/users/3)
 * req.query pour recupere des filtres (/users?pseudoStartWith=F)
 */

module.exports = {
    // requete pour créer un utilisateur
    create: async (req, res) => {
        try {
            // validation que l'utilisateur n'existe pas pour pouboir faire l'envoie (qu'il n'y ai pas de doublon)
            if (!req.body.pseudo) {
                return res.status(422).send("impossible d'envoyer un pseudo inexistant");
            }
            // on attend une réponse du server concernant la recherche de l'utilisateur passer dans le body
            const getPseudo = await db.getRepository(user).findOneBy({pseudo: req.body.pseudo})
            console.log(getPseudo);
            // validation que le pseudo que l'on veut enregistrer n'existe pas déjà dans la table
            if (getPseudo) {
                return res.send("le pseudo existe déjà")
            }
            // on envoie le pseudo en bdd
            const createdUser = await db.getRepository(user).save({ pseudo: req.body.pseudo });
            res.send(createdUser);
        } catch (error) {
            // si l'envoie echoue on retourne ou erreur 500 avec un message
            console.error(error);
            res.status(500).send("erreur lors de la creation de l'utilisateur");
        }
    },
    // affiche tous les utilisateurs
    getAll: async (req, res) => {
        try {
            const getUser = await db.getRepository(user).find();
            res.send(getUser);
        } catch (error) {
            console.error(error);
            res.status(500).send("erreur lors de la l'affichage des utilisateurs");
        }
    },
    // supprime un utilisateur en fonction de l'id récupérer dans le endpoint de la requete http
    deleteOne: async (req, res) => {
        try {
            const result = await db.getRepository(user).delete(req.params.id);
            // si l'id présent dans les params n'existe pas en bdd, on renvoie une erreur
            if (result.affected === 0) {
                return res.status(404).send("L'utilisateur n'a pas été trouvé");
            }
            return res.send("suppression effectué");
        } catch (error) {
            console.error(error);
            res.status(500).send("erreur lors de la suppression de l'utilisateur");
        }
    },
};

### Utilisation dans un projet ✔️

J'ai créer les requètes dans un projet personnelle en m'appyant sur ce qui a été fait pendant la formation.
J'ai tout passé en graphql, donc je met le lien du fichier dans le commit dans lequel il y a encore les exemples ci-dessus : 

https://github.com/Florian59c/Point-n-click/commit/356a6cb6201f75fcd6f29837243168447c3753a3#diff-9a81b696cad62809bc35f00c7cd5e6c61e4541ec191b8252d7792b8550e38bb8

### Utilisation en production si applicable ❌

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌

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
