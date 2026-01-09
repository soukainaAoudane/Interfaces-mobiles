# Rapport de Synthèse : Application de Menu de Restaurant

## 1. Objectif de l'Application

L'application a pour but de présenter le menu d'un restaurant de manière interactive et visuellement agréable. Elle permet aux utilisateurs de consulter les plats disponibles, de filtrer par catégorie et de voir les détails de chaque plat, incluant son nom, sa description, son prix et son image.

## 2. Parcours Utilisateur (Workflow)

L'application est structurée autour d'un parcours utilisateur simple et logique en plusieurs étapes :
1.  **Écran d'Accueil (`Login`)** : Une page de bienvenue esthétique avec l'identité du restaurant (logo, image de fond), invitant l'utilisateur à entrer.
2.  **Écran de Filtre (`SpinnerActivity`)** : L'utilisateur est ensuite dirigé vers une page où il peut sélectionner une catégorie de plat (Entrées, Plats principaux, etc.) via un menu déroulant.
3.  **Écran du Menu Principal (`MainActivity`)** : Après avoir cliqué sur "Voir le Menu", l'utilisateur accède à une grille visuelle (`GridView`) présentant tous les plats avec leur photo, nom, et prix.
4.  **Écran de Détail (`DetailActivity`)** : En cliquant sur un plat spécifique depuis le menu, une nouvelle page s'ouvre pour afficher en grand l'image du plat, sa description complète et son prix.

<div align="center">
  <img src="Interface_d'accueil.png" alt="Login" width="500px"/>
</div>

## 3. Outils et Concepts Android Utilisés

Ce projet met en œuvre plusieurs composants fondamentaux du développement Android :

*   **Composants d'Interface (Layouts & Views)** :
    *   **`LinearLayout`, `RelativeLayout`, `ConstraintLayout`** : Utilisés pour structurer l'organisation des écrans. `ConstraintLayout` est notamment utilisé pour l'écran de `Login` afin de créer une mise en page complexe et flexible.
    *   **`ImageView`** : Essentiel pour afficher les images des plats, le logo et les images de fond.
    *   **`TextView`** : Pour afficher tout le contenu textuel (noms des plats, descriptions, prix, titres).
    *   **`Button`** : Pour permettre la navigation entre les écrans (ex: "Entrer", "Voir le Menu").
    *   **`Spinner`** : Le menu déroulant utilisé dans l'écran de filtre pour la sélection des catégories.
    *   **`GridView`** : Le composant clé de l'écran principal, utilisé pour afficher les plats sous forme de grille visuelle.

*   **Gestion des Données et Affichage en Liste** :
    *   **`Plat.java` (Modèle de Données)** : Une classe Java simple (POJO) qui sert de "moule" pour représenter un plat avec ses attributs (nom, description, prix, image).
    *   **`ArrayList<Plat>`** : La collection utilisée pour stocker en mémoire la liste de tous les plats qui composent le menu.
    *   **`PlatAdapter.java` (Adaptateur Personnalisé)** : C'est le pont entre les données (`ArrayList<Plat>`) et l'interface (`GridView`). Il sait comment prendre les informations d'un objet `Plat` et les afficher correctement dans le layout d'un item.

*   **Navigation entre les Écrans** :
    *   **`Activity`** : Chaque écran de l'application est une `Activity` distincte (`Login`, `SpinnerActivity`, `MainActivity`, `DetailActivity`).
    *   **`Intent`** : L'outil principal pour la navigation, utilisé pour démarrer une nouvelle activité.
    *   **`Intent.putExtra()`** : Utilisé pour passer des données d'un écran à l'autre (par exemple, les détails d'un plat de `MainActivity` à `DetailActivity`).

*   **Gestion des Ressources** :
    *   **`drawable`** : Ce dossier contient toutes les ressources graphiques : images des plats (`pizza_margherita.png`), images de fond (`background_restaurant.png`), et fichiers de style XML (`bg_card.xml`).
    *   **`layout`** : Contient tous les fichiers XML qui définissent la structure visuelle des activités.
    *   **`values/colors.xml`** : Utilisé pour centraliser les codes de couleur de l'application.
    *   **`AndroidManifest.xml`** : Le fichier "cœur" de l'application, qui déclare toutes les activités et définit l'activité de démarrage. Sa bonne configuration a été essentielle pour corriger les plantages.


## 4. Conclusion

Cette application est un excellent exemple pratique des principes de base du développement Android. Elle démontre une bonne séparation des responsabilités (données, interface, logique) et utilise les composants standards pour créer une expérience utilisateur complète et fonctionnelle. Les améliorations futures pourraient inclure le filtrage effectif des plats basé sur la catégorie sélectionnée et le chargement des données depuis une source externe (base de données ou API web) plutôt qu'en dur dans le code.
