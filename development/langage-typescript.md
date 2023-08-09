# TypeScript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'intéret de TypeScript dans l'IDE ✔️
- les types de bases ✔️
- comment et pourquoi étendre une interface ✔️
- les classes et les decorators

## 💻 J'utilise

### Un exemple personnel commenté ✔️

bout de code créer en entreprise : 

// creation d'une interface
export default interface MemberUser {
    id: number;
    email: string;
    phone: string;
}

// fonction retournant une chaine de caractere
public function getPhone(): string
{
    return this.phone
}

bout de code créer sur un projet perso : 

    // la mutation retourn un booleen
    @Mutation(() => Boolean)
    // l'argument userId est de type number et la fonction "deleteUser" retourne une promesse de booleen (promesse car la fonction est asynchrone)
    async deleteUser(@Arg("userId") userId: number): Promise<Boolean> {
        const result = await datasource.getRepository(User).delete(userId);
        if (result.affected === 0) {
            throw new ApolloError("L'utilisateur n'a pas été trouvé", "NOT_FOUND");
        }
        return true;
    }

### Utilisation dans un projet ✔️

https://github.com/Florian59c/Point-n-click

Description : Jeu de type point-n-click

Il y a peu de ts coté front au moment ou j'ai remplie se formulaire, donc je met le lien de copilote également : 
https://github.com/WildCodeSchool/2211-wns-neumann-copilot

### Utilisation en production si applicable❌

[lien du projet](...)

Description :

### Utilisation en environement professionnel ✔️

Description : utilisation de typeScript en entreprise lors de mon stage en octobre et pendant l'alternace (même entreprise...)

## 🌐 J'utilise des ressources

### Titre

le cours, les video de live coding et je pose des questions à mes collegues en entreprise

## 🚧 Je franchis les obstacles

### Point de blocage ✔️

Description:

J'ai encore quelques difficultés un typer les arguments graphql (les inputType) et les states du 1er coup sans erreurs.
Je pense que ça viendra avec un peu plus de pratique.

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌
- J'ai fait une [présentation](...) ❌
