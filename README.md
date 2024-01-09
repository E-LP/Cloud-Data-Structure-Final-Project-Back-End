# Développement Web sécurisé - Backend

## 👷 Prérequis

1. Forkez ce référentiel puis clonez-le sur votre ordinateur
2. Installez Insomnia (ou l'outil de test API de votre choix) et importez la collection fournie dans [insomnia-collection.json](insomnia-collection.json)
3. Si vous n'en avez pas, créez une base de données sur Mongo Atlas
4. Créez un fichier `.env` contenant (remplacez par vos données) :
    > MONGO_URI=mongodb+srv://USERNAME:PASSWORD@CLUSTER_URL/paris-films?retryWrites=true&w=majority
    >
    > JWT_SECRET=votre-jwt-secret
5. Installez NodeJS
6. Installer les dépendances : `npm install`
7. Si vous n'avez pas de données dans votre base de données :
    1. Téléchargez l'ensemble de données publiques (OpenData) fourni par le gouvernement français et la ville de Paris, nommé ["Lieux de tournage à Paris"](https://opendata.paris.fr/explore/dataset/lieux-de-tournage- a-paris/informations)
    2. Mettez le jeu de données à la racine de ce référentiel, nommé [lieux-de-tournage-a-paris.json](lieux-de-tournage-a-paris.json)
    3. Exécutez le script d'importation avec `npm run import`
8. Exécutez le backend `npm start`

## Informations rapides

Ce backend se connecte à une base de données MongoDB contenant les emplacements des plateaux de tournage à Paris, en France.

Les lieux de consultation nécessitent un compte. La création, la mise à jour et la suppression d'emplacements nécessitent des privilèges élevés.

Il existe 2 niveaux d'accès : « utilisateur » et « admin ». Chaque utilisateur dispose d'une propriété `role` pour stocker ces données.

Les utilisateurs peuvent s'authentifier avec un jeton Web Json, obtenu en se connectant avec leur « nom d'utilisateur » et leur « mot de passe ».