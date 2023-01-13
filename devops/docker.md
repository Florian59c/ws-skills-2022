# Docker

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la création d'une image docker ✔️
- l'éxécution d'un container ✔️
- l'orchestration de containers avec docker-compose ❌ / ✔️ (en cours, car décalage suite au ratrappage d'une matinéé ou j'était absent)


## 💻 J'utilise

### Un exemple personnel commenté ✔️

// l'image utiliser pour le projet
FROM node:lts-alpine

// execution de commande pour creer le repertoire du projet
RUN mkdir /app
WORKDIR /app

// permet de recuperer les fichiers contenant la listes des dépendances utilisés dans le projet
COPY .npmrc .
COPY package*.json .
// installe toutes les dépendance
RUN npm i

// recuprère le code du projet depuis l'image
COPY src ./src
COPY public ./public
COPY tsconfig.json .
COPY tailwind.config.js .
COPY postcss.config.js .
COPY codegen.yml .

// permet de demarrer le projet
CMD npm start

### Utilisation dans un projet ❌

[lien github](...)

Description :

### Utilisation en production si applicable❌

[lien du projet](...)

Description :

### Utilisation en environement professionnel ✔️

Description : Docker est utiliser avec Kubernetes en entreprise pour le partage du projet

## 🌐 J'utilise des ressources

### Kubernetes

- https://cloud.google.com/learn/what-is-kubernetes?hl=fr
- Puisque je l'utilise en entreprise, j'ai choisi de lire de la documentation pour en comprendre les bases.

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
