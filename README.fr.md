# RetourTix

> Application open source pour événements et billetterie

<img src="assets/social_preview.png">

<a href="./README.md">
  <img alt="Translation" src="https://img.shields.io/badge/Bahasa_Indonesia-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.en.md">
  <img alt="Translation" src="https://img.shields.io/badge/English-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.zh-CN.md">
  <img alt="Translation" src="https://img.shields.io/badge/简体中文-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.ja.md">
  <img alt="Translation" src="https://img.shields.io/badge/日本語-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.ar.md">
  <img alt="Translation" src="https://img.shields.io/badge/Arabic_عربي-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.pt.md">
  <img alt="Translation" src="https://img.shields.io/badge/Português-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.es.md">
  <img alt="Translation" src="https://img.shields.io/badge/Español-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.fr.md">
  <img alt="Translation" src="https://img.shields.io/badge/Français-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.vi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Tiếng_Việt-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.hi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Hindi_हिंदी-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

* * *

Cette application de création d'événements et de vente de billets en ligne est une plateforme qui permet aux utilisateurs d'accéder et de participer facilement à divers événements. Voici la description
En bref les principales fonctionnalités de l'application :

-   Authentification:

    L'application propose une authentification sécurisée via JSON Web Token (JWT) et Google Sign-In. Les utilisateurs peuvent facilement se connecter à leurs comptes grâce à des méthodes d'authentification pratiques et sécurisées.

-   Activation du compte par e-mail :

    Pour augmenter la sécurité et garantir l'authenticité de l'utilisateur, l'application nécessite l'activation du compte par e-mail. Les utilisateurs recevront un code d'activation pour confirmer et activer leur compte.

-   Recherche d'événements à proximité :

    Les utilisateurs peuvent rechercher des événements se déroulant le plus près de leur emplacement. Cette fonctionnalité permet aux utilisateurs de découvrir et de participer aux événements organisés autour d'eux.

-   Achat de billets avec Midtrans :

    Cette application fournit des services de vente de billets en ligne via la passerelle de paiement Midtrans. Les utilisateurs peuvent facilement acheter des billets pour des événements qui les intéressent grâce à diverses options de paiement pratiques.

-   Création d'un événement avec l'approbation de l'administrateur :

    Les utilisateurs qui souhaitent organiser des événements peuvent les créer via l'application. Cependant, l'événement sera publié après avoir obtenu l'approbation de l'administrateur. Il s’agit de garantir la qualité et la pertinence des événements affichés sur la plateforme.

-   Scannez le code QR pour le créateur d'événement :

    Cette fonctionnalité permet aux créateurs d'événements de vérifier facilement la présence des visiteurs en scannant le code QR présent sur le billet. Cela contribue à une gestion efficace des événements et à la validation des billets.

-   Retirer le solde et les revenus :

    Les créateurs d'événements peuvent retirer leur solde et leurs gains via la fonction de retrait fournie par l'application. Cela donne aux organisateurs d’événements la flexibilité de gérer facilement leurs résultats financiers.

-   Notifications en temps réel

    Avec l'aide de_service d'arrière-plan_(Android et IOS), les utilisateurs recevront des notifications en temps réel sur le statut de l'événement, le statut de retrait, les achats et ventes de billets.

## Pile technologique

-   Service API/back-end

    -   [NestJS10](https://nestjs.com/)Manuscrit
    -   ORM Prisma
    -   PostgreSQL
    -   Rédis
    -   Swagger (documentation API)

-   Panneau d'administration Web (Monorepo avec service API)

    -   [SvelteKit 2](https://kit.svelte.dev/)Manuscrit
    -   Composant d'interface utilisateur Flowbite
    -   CSS vent arrière

-   Application mobile

    -   [Flutter 3](https://flutter.dev/)
        -   BLoC
        -   Congelé
        -   Rénovation
        -   fpdart

## Code source

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

## Installation et_Comment courir_

[Service API back-end](docs/api-service.md)

[Panneau d'administration](docs/admin-panel.md)

[Application mobile](docs/mobile-app.md)
