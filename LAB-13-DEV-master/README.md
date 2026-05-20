# MapApplication - Suivi de Géolocalisation Temps Réel
analyste:souaid med amine

MapApplication est une application Android complète permettant de suivre la position géographique d'un appareil en temps réel, de stocker ces données dans une base de données MySQL via une API PHP, et de visualiser l'historique des positions sur une carte interactive (OpenStreetMap).

## 🚀 Fonctionnalités

*   **Suivi GPS en temps réel** : Récupération automatique de la latitude, longitude, altitude et précision.
*   **Synchronisation Cloud** : Envoi automatique des coordonnées à un serveur distant via la bibliothèque Volley.
*   **Identification Unique** : Utilisation de l'identifiant `ANDROID_ID` pour distinguer les appareils.
*   **Cartographie Interactive** : Visualisation des positions enregistrées sur une carte OpenStreetMap (via OSMDroid).
*   **Sécurité Réseau** : Configuration spécifique pour autoriser les tests sur serveur local (`10.0.2.2`).

## 🛠️ Technologies Utilisées

*   **Android (Java)** : Langage de programmation principal.
*   **OSMDroid** : Alternative open-source à Google Maps pour l'affichage de cartes.
*   **Volley** : Gestion optimisée des requêtes HTTP.
*   **PHP (PDO)** : API backend sécurisée pour l'insertion et la récupération des données.
*   **MySQL** : Base de données relationnelle pour le stockage.

## 📋 Prérequis

1.  **Android Studio** (version Jellyfish ou plus récente recommandée).
2.  **XAMPP** ou **WAMP** pour le serveur local.
3.  Un **émulateur Android** ou un appareil physique avec GPS activé.

## ⚙️ Installation

### 1. Configuration du Backend (PHP/MySQL)

1.  Lancez **XAMPP** (Apache et MySQL).
2.  Ouvrez **phpMyAdmin** et créez une base de données nommée `map_project`.
3.  Importez le fichier `backend/database.sql` situé dans ce projet pour créer la table `positions`.
4.  Assurez-vous que les fichiers PHP du dossier `backend/` sont bien placés dans `C:\xampp\htdocs\map_project\`.

### 2. Configuration du Projet Android

1.  Ouvrez le dossier racine dans **Android Studio**.
2.  Laissez Gradle synchroniser les dépendances (automatisé via `libs.versions.toml`).
3.  **Note sur l'émulateur** : L'URL utilisée dans le code est `http://10.0.2.2/`, qui correspond au `localhost` de votre machine depuis l'émulateur.

## 📱 Utilisation

1.  Lancez l'application sur votre appareil/émulateur.
2.  **Permissions** : Acceptez les demandes de localisation au premier lancement.
3.  **Suivi** : L'application commence à envoyer votre position toutes les minutes (si vous bougez d'au moins 150m).
4.  **Visualisation** : Cliquez sur le bouton **"Afficher La Map"** pour voir tous les marqueurs enregistrés dans la base de données.

## 🏗️ Architecture des Fichiers

```text
MapApplication/
├── app/
│   ├── src/main/
│   │   ├── java/com/example/mapapplication/
│   │   │   ├── MainActivity.java      # Logique de suivi et d'envoi
│   │   │   └── GoogleMapActivity.java # Affichage de la carte
│   │   └── res/
│   │       ├── layout/                # Fichiers XML de l'interface
│   │       └── drawable/              # Icônes et marqueurs
├── backend/
│   ├── database.sql                   # Schéma MySQL
│   ├── createPosition.php             # API d'insertion
│   └── getPosition.php               # API de récupération
└── gradle.properties                  # Configuration AndroidX/Jetifier
```

## 🔒 Sécurité et Optimisation

*   **AndroidX** : Le projet est entièrement compatible avec les dernières normes AndroidX.
*   **Jetifier** : Activé pour assurer la compatibilité des anciennes bibliothèques.
*   **Permissions Runtime** : Gestion sécurisée des accès GPS selon les standards Android 6.0+.

 ##  Aperçu:

 <img width="500" height="926" alt="13" src="https://github.com/user-attachments/assets/69cd1a24-3dc4-4d5e-80e6-783db9153470" />
