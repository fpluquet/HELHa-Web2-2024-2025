# Énoncé du projet de Web2 2024-2025

Vous allez réaliser un projet de gestion de livraison pour une entreprise de transport nommée **FastDeliver** dont voici les spécifications.

## 1. **Introduction**

Le projet **FastDeliver** est une application web de gestion de livraison qui permet à une entreprise de suivre les colis et d'attribuer les livraisons aux livreurs. L'interface se divise en plusieurs parties :

1. une page d'accueil pour les clients (index.html)
2. une page d'authentification pour les administrateurs et les livreurs (login.html)
3. un tableau de bord d'administration (admin.html) et une page de création/édition de livraison (edit-delivery.html)
4. un espace de suivi de livraison pour les livreurs (driver-next-delivery.html)
5. une page de suivi de livraison pour les clients (tracking.html)

Un administrateur pourra gérer les livraisons (et éditer les informations du client liées à cette livraison). Les livreurs pourront consulter les livraisons qui leur sont attribuées, éditer le statut (la marquer comme livrée ou signaler les problèmes éventuels). Les clients uniquement pourront suivre l'état de leur colis en entrant un numéro de suivi.

Les utilisateurs sont hardcodés (il n'y a pas de gestion d'utilisateurs dans l'application) et les mots de passe sont stockés sous forme hashée (avec du sel) dans la base de données (faites un script JS côté serveur qui crée les utilisateurs dans la base de données). Voici les utilisateurs disponibles :

| Nom         | Email                  | Mot de passe | Rôle          |
|-------------|------------------------|--------------|---------------|
| Jean Martin | admin@fastdeliver.com  | admin123     | Administrateur|
| Emma Roux   | emma@fastdeliver.com   | driver123    | Livreur       |
| Marc Bernard| marc@fastdeliver.com   | driver123    | Livreur       |
| Lucas Dubois| lucas@fastdeliver.com  | driver123    | Livreur       |

Une vidéo présentant toute l'application est disponible ici : [https://youtu.be/myXpqbOJ8iw](https://youtu.be/myXpqbOJ8iw).

Une démonstration du côté responsive de l'application est disponible ici : [https://youtu.be/pRsYRhqcxAM](https://youtu.be/pRsYRhqcxAM).

## 2. **Structure et Style**

- **CSS & Responsive Design :** L'interface est responsive et s'adapte à différents écrans. Vous pouvez utiliser des frameworks CSS comme Bootstrap ou TailwindCSS pour faciliter le développement.
- **Scripts :** Des scripts JavaScript gèrent les fonctionnalités de filtrage, de manipulation de données et les actions utilisateur (comme la connexion et la gestion des livraisons). Le client web est donc un client lourd qui communique avec l'API pour récupérer et mettre à jour les données.

## 3. **Contraintes techniques**

- **Base de données :** Les informations sur les livraisons, les clients, et les livreurs sont stockées dans une base de données SQLite via une API sur mesure. Vous ne pouvez pas utiliser d'ORM. Les données doivent être cohérentes et bien structurées pour permettre une gestion efficace des livraisons. Vous ne devez avoir qu'une seule base de données pour l'ensemble de l'application (mais vous aurez plusieurs tables).
- **Données JSON :** Les données sont échangées en format JSON entre le client web et le serveur. Les requêtes HTTP doivent être correctement gérées et les réponses doivent être bien formatées. Structurez vos données de manière logique et cohérente pour faciliter la manipulation côté client. Ne renvoyez pas de données inutiles ou sensibles. Par exemple, un livreur ne doit pas pouvoir accéder aux informations d'un autre livreur.
- **API :** L'application web communique avec une API pour récupérer et mettre à jour les données. Cette API sera écrite en NodeJS et Express. L'API doit être bien documentée et respecter les normes REST.
- **Unité de serveur :** Vous ne devez développer qu'un seul serveur, qui servira à la fois l'API et les fichiers statiques (HTML, CSS, JS). Vous pouvez utiliser des middlewares pour gérer les routes et les requêtes.
- **Qualité du code** : Le code du client et du serveur doit être bien structuré, commenté, et respecter les bonnes pratiques de développement web. Les noms de variables, fonctions, et classes doivent être explicites et cohérents.
- **Sécurité :** Les mots de passe doivent être stockés de manière sécurisée (hashés). Votre application doit être protégée contre les attaques XSS et l'injection SQL.
- **Connexion :** Les utilisateurs doivent être authentifiés pour accéder aux pages protégées. Les sessions doivent être gérées de manière sécurisée via des tokens ou des cookies sécurisés. Vous pouvez utiliser des JWT pour gérer les sessions via des librairies dédiées.
- **Compréhension des besoins :** Votre application doit respecter les fonctionnalités demandées et les contraintes de design. Toute fonctionnalité manquante ou non conforme aux spécifications pourra entraîner des pénalités.
- **Compréhension du code :** Vous devez être capable d'expliquer votre code et de justifier vos choix de conception. Vous pouvez être interrogé sur les technologies utilisées, les librairies, les méthodes de développement, etc.
- **TypeScript et Sass :** Vous pouvez utiliser TypeScript pour améliorer la qualité de votre code et éviter les erreurs courantes. Cependant, cela n'est pas obligatoire. Idem pour Sass, qui peut vous aider à structurer votre CSS de manière plus efficace.
- **Gestion des erreurs :** Votre application doit gérer les erreurs de manière élégante et informative pour l'utilisateur. Les messages d'erreur doivent être clairs et précis, sans révéler d'informations sensibles. Vous ne pouvez pas ne pas gérer les erreurs (par exemple, en laissant des pages blanches ou des messages d'erreur uniquement dans la console).
- **Git :** Vous devez utiliser Git pour gérer votre code source. Chaque membre du groupe doit contribuer au projet et les commits doivent être clairs et bien documentés. Vous devez utiliser des branches pour travailler sur des fonctionnalités spécifiques et fusionner vos modifications de manière cohérente. S'il y a un doute sur la quantité de travail fourni par chaque membre du groupe, les commits et les branches seront examinés pour évaluer la contribution de chacun. Vieillez donc à bien committer avec vos propres identifiants.
- **package.json :** Vous devez fournir un fichier `package.json` avec les dépendances nécessaires pour exécuter votre application. Vous devez également fournir un script `start` pour lancer votre application et un script `init` pour initialiser la base de données avec des données des utilisateurs.
- **README.md :** Vous devez fournir un fichier `README.md` avec des instructions claires pour installer et exécuter votre application. Vous y mettrez également le lien vers la vidéo de démonstration de votre application (voir les modalités de remises). 

## 4. Grille d'évaluation

Vous serez jugés sur la quantité et la qualité de votre projet. La quantité se réfère aux fonctionnalités implémentées et conformes aux spécifications, tandis que la qualité concerne la propreté du code, la sécurité, la clarté et le respect des bonnes pratiques.

### Evaluation de la quantité


| **Critère**                                         | **Description**                                                                                     | **Points** |
| --------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ---------- |
| **1. Fonctionnalités et complétion**                |                                                                                                     | **/40**    |
| - **Page d’accueil (index.html)**                   | Présentation des services, champ de recherche pour le suivi des colis.                              | 5          |
| - **Page d'authentification**                       | Interface de connexion fonctionnelle avec redirection appropriée selon le rôle de l’utilisateur.    | 5          |
| - **Tableau de bord Administrateur**                | Affichage des livraisons, outils de recherche/filtre et actions (ajout, modification, suppression). | 10         |
| - **Page d'édition de livraison**                   | Champs modifiables et actions de sauvegarde/annulation, liaison avec l'API.                         | 5          |
| - **Suivi de livraison pour les livreurs**          | Affichage de la prochaine livraison et options "Livré" et "Problème".                               | 5          |
| - **Suivi de livraison pour les clients**           | Historique et timeline de livraison, informations sur le destinataire.                              | 5          |
| - **Autres pages fonctionnelles**                   | Autres pages ou fonctions essentielles sont bien implémentées et respectent l’énoncé.               | 5          |
| **2. Respect du design**                            |                                                                                                     | **/20**    |
| - **Fidélité au design**                            | Respect du design décrit dans la vidéo ou les indications de style.                                 | 10         |
| - **Responsive Design**                             | Adaptabilité correcte sur les différents formats d’écran (mobile, tablette, desktop).               | 5          |
| - **Animations et transitions**                     | Application des animations et transitions spécifiées dans l’énoncé.                                 | 5          |
| **3. Utilisation de l'API et gestion de données**   |                                                                                                     | **/40**    |
| - **Appels API bien structurés**                    | Utilisation efficace de l’API pour les requêtes, bonnes pratiques REST respectées (les bonnes méthodes pour les bonnes routes, de bons chemins, ...).                  | 25         |
| - **Gestion de la base de données (SQLite)**        | Intégration correcte et performante, sauvegarde et récupération des données.                        | 15         |
| **4. Originalité et effort additionnel (bonus)**    |                                                                                                     | **/+10**   |
| - **Fonctionnalités supplémentaires ou créativité** | Ajout de fonctionnalités pertinentes ou amélioration notable de l'interface.                        | +10        |
| **Total**                                           |                                                                                                     | **/100**   |


### Evaluation de la qualité

| **Critère**                        | **Description**                                                                                      | **Points** |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------- |
| - **Structure du code**            | Organisation logique, séparation des préoccupations, utilisation appropriée de modules et fonctions. | 25         |
| - **Clarté et documentation**      | Code clair, bien commenté, avec des noms de variables et fonctions explicites.                       | 25         |
| - **Respect des bonnes pratiques** | Conformité aux bonnes pratiques de développement web (HTML sémantique, CSS organisé, JS efficace).   | 25         |
| - **Sécurité**                     | Gestion des sessions, protection contre XSS et injection SQL, hashage des mots de passe.             | 25         |
| **Total**                          |                                                                                                      | **/100**   |

### **Points finaux**

La qualité pondère la quantité. Un projet complet mais mal codé peut avoir une note inférieure à un projet partiel mais bien codé. Par exemple, si vous codez 50 % des fonctionnalités et que la qualité de votre code est parfaite, vous obtiendrez 50 % de la note maximale. 

Mais si vous implémentez toutes les fonctionnalités mais que la qualité du code est médiocre, la note finale sera inférieure à 50 %. Si vous codez 50% des fonctionnalités et que la qualité de votre code est de 50%, vous obtiendrez une note autour de 25%.

### **Critères de bonus et de pénalités**

- **Bonus (jusqu'à 10 points)** : Améliorations significatives (par exemple, l'ajout d’une fonctionnalité innovante ou une optimisation notable). Il faut cependant que le projet de base soit complet.
- **Pénalités** :
  - **Retard** : Si le code n'est pas rendu (pour quelque raison que ce soit) pour la veille de l'examen, vous ne pourrez pas passer l'examen. Aucune dérogation ne sera prise en considération, puisque vous avez tous les jours avant la veille de l'examen pour déposer au moins une version de votre code.

## 5. Modalités du Q1

- Le projet doit être fait en groupe de 2 ou 3, ou exceptionnellement seul.
- Le projet doit être remis sur votre git assigné au plus tard la veille de l’examen du Q1, sur la branche principale du git (pas une autre branche). Le professeur prendra la dernière version disponible sur cette branche.
- À cette même date, vous réaliserez une vidéo (une par groupe) qui explique explicitement ce qui a été fait dans le projet et ce qui n'a pas été fait. Cette vidéo doit montrer une démonstration complète de votre application (un peu comme la vidéo présentée ici). Vous devez également expliquer les grandes lignes de votre code et les choix de conception que vous avez faits. La vidéo doit être déposée sur un service de partage de vidéos (YouTube, Google Drive, etc.). Le lien vers la vidéo doit être inclus dans le README.md de votre projet.
- **Pour obtenir votre repository git, indiquez votre nom d’utilisateur GitHub sur le document partagé avant le 20/11/2024 : https://annuel2.framapad.org/p/groupes-web2-ab3w?lang=fr**
- Votre projet devra respecter scrupuleusement le design montré dans la vidéo (y compris les différentes animations et le responsive design)
- L’examen de Q1 sera individuel et sera composé de questions sur papier et/ou de modifications à apporter sur votre code.
- Pour rappel, si vous n’obtenez pas au moins 8/20 à l'examen, la note est dite absorbante et devient la note de l'UE, indépendamment de la note obtenue pour le projet en tant que tel.

## 6. Modalités du Q3

- Si vous n’obtenez pas au moins 10/20 au Q1, vous pouvez repasser l’examen au Q3. Celui-ci sera basé sur les mêmes modalités qu’au Q1 et sur le même énoncé. Vous devez donc continuer à travailler sur votre projet pour l’améliorer et le compléter.
- Votre projet doit être remis au plus tard la veille de l'examen de Q3, toujours sur le git qui vous a été assigné. Si vous n'êtes plus dans le même groupe, vous pouvez demander un nouveau dépôt GitHub pour Q3.
- A cette même date, vous réaliserez une vidéo (une par groupe) qui explique explicitement ce qui a été fait dans le projet et ce qui n'a pas été fait. Suivez les mêmes modalités que pour le Q1.
- Pour rappel et tout comme au Q1, si vous n’obtenez pas au moins 8/20 à l'examen, la note est dite absorbante et devient la note de l'UE, indépendamment de la note obtenu pour le projet en tant que tel.
