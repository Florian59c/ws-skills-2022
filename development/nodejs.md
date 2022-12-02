# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- Comment développer en utilisant un système de *livereloading* (`nodemon` par exemple) ✔️
- La connexion de mon application à une base de données avec et sans ORM/ODM (avec `mongodb` puis `mongoose` par exemple) ❌
- Le développement d'une API REST et GraphQL (avec les packages `express` et `graphql` par exemple) ✔️
- *Bonus : la manipulation des fichiers système avec `fs` et l'utilisation des streams en NodeJS* ❌

## 💻 J'utilise

### Un exemple personnel commenté ❌ / ✔️

/* dans db.js */
const typeorm = require("typeorm");

module.exports = {
dataSource: new typeorm.DataSource({
    // initialisation de la base de données
    type: "sqlite",
    database: "./wildersdb.sqlite",
    synchronize: true,
    entities: [require("./entity/wilder")],
}),
};

/* dans index.js */
const express = require("express");
const dataSource = require("./db").dataSource;
// appel a la bdd

const wilderController = require("./controller/wilders");

const app = express();
app.use(express.json());
// initialisation et utilisation d'express


const start = async () => {
  await dataSource.initialize();
  // attente de la recuperation de l'api
  app.listen(3000, () => console.log("Server started on 3000"));
  // message de confirmation de connexion a l'api
};

start();

### Utilisation dans un projet ❌

[lien github](...)

Description :

### Utilisation en production si applicable❌

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌

Description :

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ✔️

Description:

encore quelque difficultés pour mettre en place 

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌
- J'ai fait une [présentation](...) ❌
