# Docker

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la création d'une image docker ✔️
- l'éxécution d'un container ✔️
- l'orchestration de containers avec docker-compose ✔️


## 💻 J'utilise

### Un exemple personnel commenté ✔️

// l'image de base utiliser pour le projet (image déjà existante sur dockerhub)
FROM node:lts-alpine

// execution de commande pour creer le repertoire du projet
RUN mkdir /app
// on se déplace dans le répertoire nouvellement créé
WORKDIR /app

// permet de recuperer les fichiers contenant la listes des dépendances utilisés dans le projet
COPY .npmrc .
COPY package*.json .
// installe toutes les dépendance
RUN npm i

// recuprère le code du projet et le copy dans le container
COPY src ./src
COPY public ./public
COPY tsconfig.json .
COPY tailwind.config.js .
COPY postcss.config.js .
COPY codegen.yml .

// au dessus : construction et parametrage de l'image

// permet de demarrer le projet
CMD npm start


/* docker-compose : */

// services qui compose l'application
services:
  db:
    restart: always
    image: postgres:15-alpine
    environment:
      POSTGRES_PASSWORD: postgres
      PGUSER: postgres
    ports:
      - 5432:5432
    // parametrage de la bdd pour vérifier que tous se passe bien avant de lancer le server (fait les verifications a interval régulier)
    healthcheck:
      test: ["CMD-SHELL", "pg_isready"]
      interval: 10s
      timeout: 5s
      retries: 5

  server:
    // demarrage du container automatiquement
    restart: always
    // le server est dépendant du services db
    depends_on:
      db:
        condition: service_healthy
    environment:
      DB_HOST: db
    // build l'image
    build: ./server
    // corrspondance des ports entre la machine et le container
    ports:
      - 4000:4000
      - 4001:4001
    // relaod du serveur a chaque changement
    volumes:
      - ./server/src:/app/src

  client:
    restart: always
    build: ./client
    ports:
      - "3000:3000"
    volumes:
      - ./client/src:/app/src
    environment:
      - CHOKIDAR_USEPOLLING=true

### Utilisation dans un projet ✔️

https://github.com/WildCodeSchool/2211-wns-neumann-copilot

Description : Copilote

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ✔️

Description : Docker est utiliser avec Kubernetes en entreprise

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
