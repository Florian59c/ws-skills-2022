# Integration continue

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les enjeux de l'integration continue ✔️
- la mise en place d'une github action ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

/* Tests unitaires front */

// le nom du test
name: tests-front

// les jobs seront executés sur une pull request
on: pull_request

// liste des actions a faire lors de la PR
jobs:
  test-client:
    // l'OS sur laquel on fait tourner les tests
    runs-on: ubuntu-latest
    // les étapes de actions
    steps:
      // clone du projet
      - name: Check out code
        uses: actions/checkout@v3
      // on install les dépendances (ici dans le dossier client)
      - name: Install npm and deps
        run: cd client && npm i
      // declenche la commande pour démarer les test (toujours dans le dossier client)
      - name: Go to client file and run tests
        run: cd client && npm run test


/* Build et push du front */


name: build and push the production client to dockerhub

// on execute les jobs lors d'un push sur la branche main
on: 
  push:
    branches: ["main"]
  
jobs:
  build-and-push-production-client:
    runs-on: ubuntu-latest
    steps:
      // crée une image docker qui inclu les qemu (pour ubuntu)
      - name: set up QEMU
        uses: docker/setup-qemu-action@v2
      // fait le docker build
      - name: set up Docker Buildx
        uses: docker/setup-buildx-action@v2
      // on se log sur dockerhub
      - name: Login to Docker Hub
        uses: docker/login-action@v2
        // nos identifiants dockerhub - on les stocke via les secrets de github pour que personne n'y ai accès depuis le repo
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}
      // build et push de l'image sur dockerhub
      - name: Build and push
        uses: docker/build-push-action@v4
        // les parametres
        with:
          push: true
          // l'api sur laquelle on va taper
          build-args: "REACT_APP_GRAPHQL_API_URL=http://localhost:4000"
          // le context dans lequel on fait le build
          context: "{{defaultContext}}:client"
          // utilisation des parametre docker de production pour une version optimisé
          file: "Dockerfile.production"
          // nom de l'image envoyé sur dockerhub
          tags: ${{ secrets.DOCKERHUB_USERNAME }}/2211-wns-neumann-copilot-client

### Utilisation dans un projet ✔️

https://github.com/WildCodeSchool/2211-wns-neumann-copilot/tree/main/.github/workflows

Description : la CI de copilote

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ✔️

Description : vérification des tests via gitLab (la CI était déjà en place en entreprise, donc je n'y ai pas touché, mais j'ai vu le fonctionnement).

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ❌ / ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
