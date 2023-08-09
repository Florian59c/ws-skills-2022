# GraphQL

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la différence entre REST et GraphQL ✔️
- les besoins auxquels répond GraphQL ✔️
- la définition d'un schéma ✔️
- Query ✔️
- Mutation ✔️
- Subscription ❌

## 💻 J'utilise

### Un exemple personnel commenté ✔️

/* Entity */


// le contenu et les parametres de la table Users
@ObjectType()
@Entity()
class Users {
    @PrimaryGeneratedColumn()
    @Field()
    id: number

    @Column({ unique: true })
    @Field()
    pseudo: string

    @Column({ unique: true })
    @Field()
    email: string

    @Column()
    hashedPassword: string

    @Column()
    @Field()
    bestScore: number
}


/* requetes */


    // requete de type Get qui retourne un tableau d'utilisateurs
    @Query(() => [User])
    // fonction asynchrone "getUsers" qui renvoie une promesse de tableau d'utilisateur
    async getUsers(): Promise<User[]> {
        // recupere et renvoie tous les utilisateurs contenue dans la table Users
        const getUser = await datasource.getRepository(User).find();
        return getUser;
    };

    // renvoie un tableau d'utilisateurs limité a 10 et classés par rapport à la colonne "bestScore" de l'entier le plus petit au plus grand
    // permet en gros d'obtenir les 10 meilleurs joueurs afin de les afficher
    @Query(() => [User])
    async get10BestUsers(): Promise<User[]> {
        const get10BestUsers = (await datasource.getRepository(User)
            .find({ order: { bestScore: "ASC" }, take: 10 }));
        return get10BestUsers;
    };

    // requete de type Post qui ajoute un nouvel utilisateur
    @Mutation(() => User)
    // le decorateur @Arg permet de renseigner des informations venu du body
    async createUser(@Arg("data") { pseudo, email, password }: UsersInput): Promise<User> {
        // chaque nouvel utilisateur a un score prédéfinie au moment de son inscription
        const bestScore = 86400;
        // on hash le password avant l'envoi en bdd
        const hashedPassword = await hashPassword(password);
        // création du nouvel utilisateur avec les données qu'il a fournis, son password hashé et son score de base
        return await datasource.getRepository(User).save({ pseudo, email, hashedPassword, bestScore });
    }


/* InputType */


// les parametres de typage des @Args de la requete createUser ci-dessus
@InputType()
export class UsersInput {
    @Field()
    @MaxLength(30)
    pseudo: string

    @Field()
    @IsEmail()
    email: string

    @Field()
    @MinLength(8)
    password: string
}

### Utilisation dans un projet ✔️

https://github.com/Florian59c/Point-n-click

Description : Jeu de type point-n-click

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

### Point de blocage ✔️

Description:

Quelques difficultés lors du typage. J'ai parfois du mal a typer les arguments. Je pense que c'est dû a un manque d'expérience et que je n'aurai plus ces difficultés à force de pratiquer.

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌
- J'ai fait une [présentation](...) ❌ 
