# REST API

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les verbes HTTP ✔️
- les statuts HTTP ✔️
- les endpoints ✔️
- CORS ✔️
- la nomenclature recommandée pour les routes ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

/* Dans server/src */

/* Dans db.js */


const typeorm = require('typeorm');
const User = require('./entity/user');

// initialisation de la bdd
const datasource = new typeorm.DataSource({
    type: 'sqlite',
    database: './pointnclickdb.sqlite',
    synchronize: true,
    entities: [User],
    logging: ["query", "error"],
});

module.exports = datasource;


/* Dans index.js */


const express = require('express');
const User = require('./entity/user');
const usersController = require('./controller/users');
const datasource = require('./db');
const app = express();

// permet d'acceder au donnees envoyer par le client dans le corp de la requete sur le gestionnaire de routes
// sans ça, req.body sera forcement undefined
app.use(express.json());

// appel de requètes sur divers endpoint, créées dans /controller/users.js
app.post('/users', usersController.create);
app.get('/users', usersController.getAll);
app.delete('/users/:id', usersController.deleteOne);

// attente que la bdd soit initialiser avant que le serveur commence à écouter sur un port
async function start() {
    await datasource.initialize();
    // le port sur lequel on va écouter
    app.listen(3000, () => {
        console.log('le serveur est prêt');
    });
}

// Démarage du serveur
start();


/* Dans controller/users.js */


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
            // validation que l'utilisateur n'existe pas
            if (!req.body.pseudo) {
                return res.status(422).send("impossible d'envoyer un pseudo inexistant");
            }
            const getPseudo = await db.getRepository(user).findOneBy({pseudo: req.body.pseudo})
            console.log(getPseudo);
            if (getPseudo) {
                return res.send("le pseudo existe déjà")
            }
            const createdUser = await db.getRepository(user).save({ pseudo: req.body.pseudo });
            res.send(createdUser);
        } catch (error) {
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


/* Dans entity/User.js */


const { EntitySchema } = require('typeorm');

// creation d'une entité - equivalant au tables et colonnes du sql
// module.exports permet d'exporter le schema (ici dans index.js)
module.exports = new EntitySchema({
    name: "Users",
    columns: {
        id: {
            type: 'int', 
            primary: true,
            generated: true,
        },
        pseudo: {
            type: "text"
        }
    }
});


/* Liste de requetes */

// create
POST http://localhost:3000/users
Content-Type: application/json

{
    "pseudo": "Florian59c"
}

// getAll
GET http://localhost:3000/users

// delete
DELETE http://localhost:3000/users/3

### Utilisation dans un projet ✔️

J'ai créer les requètes dans un projet personnelle en m'appyant sur ce qui a été fait pendant la formation.
J'ai tout passé en graphql, donc je met le lien du commit dans lequel il y a encore les exemples ci-dessus : 

https://github.com/Florian59c/Point-n-click/commit/356a6cb6201f75fcd6f29837243168447c3753a3

### Utilisation en production si applicable❌

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌

Description :

## 🌐 J'utilise des ressources

### Titre

je visionne les video du cours

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
