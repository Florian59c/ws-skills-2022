# Technologies d'applications mobiles

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les différences entre les webapps, les applications hybrides et natives ✔️
- le fonctionnement d'une app React Native, ce qui sera en réalité produit et installé sur le téléphone de mes utilisateur·rices, comment le JS arrive à communiquer avec le natif 
- quelles sont les différentes technologies (frameworks) existantes pour développer des apps mobiles ✔️
- quels sont les principaux points d'attention entre le développement d'une app mobile ou desktop ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

/* mobile native : */


import { StatusBar } from 'expo-status-bar';
import React, { useState } from 'react';
import { Image, ScrollView, StyleSheet, Dimensions, Text, View, ImageBackground, TouchableOpacity } from 'react-native';
import cars from './cars';

export default function Home(props) {
  return (
    <View style={styles.container}>
      // affichage de la barre de staus du mobile (icon de niveau de batterie / réseau (3g/4g)...)
      <StatusBar style="light" />
      // des boutons pressables qui amene vers d'autres vues de maniere dinamyque
      <TouchableOpacity onPress={() => props.navigation.navigate("ListVehicules", { cars })}>
        // pour pouvoir faire du scroll sur la page (pas de limite d'affichage à la verticale)
        <ScrollView>
          <ImageBackground style={styles.imageFond} source={require("./img/hero.jpg")} resizeMode="cover" >
            <Text style={styles.textHeader}>8 véhicules à découvrir</Text>
          </ImageBackground>
        </ScrollView>
      </TouchableOpacity>
    </View>
  );
}

// on definit des variables qui ont la largeur et hauteur de l'ecran
const vw = Dimensions.get("screen").width;
const vh = Dimensions.get("screen").height;

// la liste des styles css
const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
    padding: 10
  },
  imageFond: {
    width: vw - 20,
    height: vh / 4,
    padding: 10,
    justifyContent: "flex-end",
    borderBottomLeftRadius: 10,
    borderBottomRightRadius: 10,
    borderTopRightRadius: 10,
    borderTopLeftRadius: 10,
    overflow: 'hidden',
  },
  textHeader: {
    color: "white",
    fontWeight: "bold",
  }
});


/* web responsive : ( en mobile-fisrt dans l'exemple) */


import React from 'react';
import { Link } from 'react-router-dom';

const Header = () => {
    return (
        <div className='header'>
            <Link to={"/projets"}>
                <h1>Les projets de Flow</h1>
            </Link>
        </div>
    )
}

export default Header

/* le css : */

.header {
  border-bottom: 0.4rem solid rgb(179, 179, 179);
  border-radius: 0 0 2rem 2rem;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
}

.header h1 {
  background-color: rgb(24, 23, 21);
  border-radius: 0 0 2rem 2rem;
  color: rgb(235, 235, 235);
  text-align: center;
  font-size: 5rem;
  font-weight: bold;
  text-shadow: -0.1rem 0.1rem 0.2rem #E0E0E0;
  padding-bottom: 0.2rem;
}

/* taille de la bordure augmenté pour compenser du padding au survol et faire un effet */
.header:hover {
  border-bottom: 0.6rem solid rgb(179, 179, 179);
}

.header h1:hover {
  background-color: rgb(14, 13, 11);
  border-radius: 0 0 2rem 2rem;
  text-shadow: none;
  padding: 0;
}

// pour les ecran superieur au mobile ET tablettes
@media screen and (min-width: 992px) {

  /* header */

  .header {
    /* retire le positionnement de la barre pour les grands ecrans */
    /* ainsi, le header ne reste pas lors du scroll */
    position: relative;
  }
}

### Utilisation dans un projet ✔️

screenshot de quelques vues dans : screens/mobile-Screen.png

native : 1er projet react native que j'ai fait
 - git : https://github.com/Florian59c/Search_Cars

web : mon porte-folio responsive et en mobile first
 - git : https://github.com/Florian59c/Site-Flow

### Utilisation en production si applicable ❌ / ✔️

https://le-site-de-flow.web.app/

### Utilisation en environement professionnel ❌

Description :

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
- J'ai ecrit un [article](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
