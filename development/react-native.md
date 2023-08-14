# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les différences et points communs entre du code react et du code react native ✔️
- ce que devient et comment est interprêté le code javascript dans une application react native ❌ / ✔️
- les avantages et inconvénients de react native ✔️
- la différence entre react native et expo ✔️
- les principales briques qui composent react native (core components) ✔️
- comment écrire du style en react native ✔️
- comment est géré le layout en react native ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté ❌ / ✔️

import Trajet from "./screens/Trajet";
import { ApolloProvider } from "@apollo/client";
import apolloClient from './gql/apolloClient';
import { NavigationContainer } from '@react-navigation/native'; import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import Login from './screens/Login';
import Ionicons from '@expo/vector-icons/Ionicons';
import NotificationsSreen from "./screens/NotificationsSreen";

export default function App() {

  const Tab = createBottomTabNavigator();

  return (
    // client apollo dans le contexte pour accéder au server
    <ApolloProvider client={apolloClient}>
      // navigation sous forme de bar en bas du mobile
      <NavigationContainer>
        // les options et affichage des icons de navigation
        <Tab.Navigator
          screenOptions={({ route }) => ({
            tabBarIcon: ({ focused, color, size }) => {
              if (route.name === "Trajet") {
                return (
                  <Ionicons
                    name={focused ? "car-sport" : "car-sport-outline"}
                    size={size}
                    color={color}
                  />
                );
              } else if (route.name === "Login") {
                return (
                  <Ionicons
                    name={focused ? "person-circle" : "person-circle-outline"}
                    size={size}
                    color={color}
                  />
                );
              } else if (route.name === "Notifications") {
                return (
                  <Ionicons
                    name={focused ? "notifications-circle" : "notifications-circle-outline"}
                    size={size}
                    color={color}
                  />
                );
              }
              return (
                <Ionicons
                  name={"alert-circle"}
                  size={size}
                  color={color}
                />
              );
            },
            // les styles de la barre
            tabBarActiveTintColor: "#518071",
            tabBarInactiveTintColor: "gray",
            tabBarStyle: { height: 60, paddingBottom: 10 },
            headerTitleAlign: "center",
            headerTintColor: "#518071"
          })}
        >
        // les routes affichées à l'écran en fonction de l'icon sur leqeul on appui (dans la tab barre)
          <Tab.Screen name="Login" component={Login} />
          <Tab.Screen name="Trajet" component={Trajet} />
          <Tab.Screen name="Notifications" component={NotificationsSreen} />
        </Tab.Navigator>
      </NavigationContainer>
    </ApolloProvider>
  );
}

### Utilisation dans un projet ✔️

https://github.com/WildCodeSchool/2211-wns-neumann-copilot

Description : Le native-client de Copilote

### Utilisation en production si applicable ❌ / ✔️

[lien du projet](...)

Description :

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
- J'ai fait une [présentation](...) ❌ / ✔️
