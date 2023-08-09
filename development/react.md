# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'état (_state_) pour contrôler l'affichage d'un composant ✔️
- les composants enfants et les _props_ qu'on leur passe ✔️
- le déclenchement d'instructions en fonction des actions de l'utilisateur ✔️
- le déclenchement d'instructions en fonction de l'étape du cycle de vie du composant ou du changement de valeur de ses props ✔️
- l'usage d'un reducer (_useReducer_) pour gérer un état composé dans un composant ❌
- l'état stocké dans un composant avec un _context provider_ et accessible dans ses descendants via `useContext` ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

export default function App() {

  // initialisation de ma state isDark a false (booleen)
  const [isDark, setIsDark] = useState(false);

  // fonction appelé lors du clic sur le bouton
  // met à jour la state à chaque clic, en inversant le booleen
  const changeMode = () => {
    setIsDark(current => !current);
  };

  // fonction qui retourne le bouton cliquable
  // centralisé ici, car il est répété 2 fois dans la dernière ternaire (1 avec un Link et l'autre sans Link)
  const boutonSwitch = () => {
    return (
      <button className={`bouton ${isDark ? "boutonDark" : "boutonLight"}`} onClick={changeMode}>
        {isDark ? <p>Light Mode ?</p> : <p>Dark Mode</p>}
      </button>
    )
  };

  return (
    <div className='accueil' style={{ backgroundImage: isDark ? `url(${nuit})` : `url(${jour})` }}>
      <div className='contenuAccueil'>
        <div>
          {isDark ?
            <img src={loup} alt="Cercle d'eau en mouvement" />
            :
            <img className='imgLight' src={flow} alt="Loup hurlant à la lune" />
          }
        </div>
        <div>
          <Row justify="center" style={{ flexDirection: isDark ? 'row-reverse' : '', }} >
            <Col>
              <h1 className={`${isDark ? "titreDark" : "titreLight"}`}>F</h1>
            </Col>
            <Col>
              <h1 className={`${isDark ? "titreDark" : "titreLight"}`}>L</h1>
            </Col>
            <Col>
              <h1 className={`${isDark ? "titreDark" : "titreLight"}`}>O</h1>
            </Col>
            <Col>
              <h1 className={`${isDark ? "titreDark" : "titreLight"}`}>W</h1>
            </Col>
          </Row>
        </div>
        <div>
          <h2 className={`${isDark ? "titreDark" : "titreLight"}`}>
            {isDark ? 'appeared !' : 'vous présente ses projets'}
          </h2>
        </div>
        {isDark ? <Link to={"/projets"}> {boutonSwitch()} </Link> : boutonSwitch()}
      </div>
    </div>
  )
}

### Utilisation dans un projet ✔️

https://github.com/Florian59c/Site-Flow

Description : Mon port-folio

### Utilisation en production si applicable ✔️

https://le-site-de-flow.web.app/#/

Description : Mon port-folio

### Utilisation en environement professionnel ❌

Description : utilisation d'angular en milieu professionnel

## 🌐 J'utilise des ressources

### Titre

https://react.dev/reference/react

## 🚧 Je franchis les obstacles

### Point de blocage ✔️

Description:

J'ai encore des difficultés à comprendre ce qu'est le reduceur et à utiliser le hook "useReducer".

Plan d'action : (à valider par le formateur)

- revoir un exemple concret de son utilisation (comment on l'utilise / dans quel cas ...) ❌ / ✔️

- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌
- J'ai fait une [présentation](...)✔️ : presentation de mon port-folio lors de mon passage du titre DWWM + Présentation de "Ant Design" lors des veilles technos du vendredi après-midi (le 25/11/2022)
