# Backtix

> Événement open source et application de billetterie

<img src="assets/social_preview.png" alt="BackTix">

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

## Code source

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

* * *

> [!IMPORTANT]
>
> ## Installation et_Comment courir_
>
> [Service API arrière](docs/api-service.md)
>
> [Panel d'administrateur](docs/admin-panel.md)
>
> [Application mobile](docs/mobile-app.md)
>
> * * *
>
> [!NOTE]
>
> ## Pile technologique
>
> -   Service API / back-end
>
>     -   [N ° 10](https://nestjs.com/)Manuscrit
>     -   Prisma orm
>     -   Postgresql
>     -   Redis
>     -   Swagger (API Docs)
>
> -   WEB PANNEUX ADMINE (MonorePO avec service API)
>
>     -   [Svelteki 2](https://kit.svelte.dev/)Manuscrit
>     -   FlowBite UI Component
>     -   CSS du vent arrière
>
> -   Application mobile
>
>     -   [Flutter 3](https://flutter.dev/)
>         -   BLoC
>         -   Congélé
>         -   Rénover
>         -   fpdart

* * *

L'application pour la réalisation d'événements et les ventes de billets en ligne est une plate-forme qui permet aux utilisateurs d'accéder et de participer à divers événements. Voici une description
Caractéristiques de l'application principale courtes:

-   Authentification:

    Cette application offre une authentification sûre via JSON Web Token (JWT) et Google Sign-In. Les utilisateurs peuvent facilement saisir leur compte avec une méthode d'authentification confortable et sûre.

-   Activation du compte par e-mail:

    Pour augmenter la sécurité et assurer l'authenticité de l'utilisateur, l'application nécessite l'activation du compte par e-mail. Les utilisateurs recevront un code d'activation pour confirmer et activer leur compte.

-   Recherche d'événements la plus proche:

    Les utilisateurs peuvent trouver des événements qui se déroulent le plus près de leur emplacement. Cette fonctionnalité permet aux utilisateurs de trouver et de participer à des événements organisés autour d'eux.

-   Achat de billets avec Midtrans:

    Cette application fournit des services de vente de billets en ligne à l'aide de passerelles de paiement MidTrans. Les utilisateurs peuvent facilement acheter des billets pour des événements qui sont en demande avec une variété d'options de paiement confortables.

-   Faites un événement avec l'approbation de l'administrateur:

    Les utilisateurs qui souhaitent organiser un événement peuvent se réaliser via l'application. Cependant, l'événement sera publié après avoir obtenu l'approbation de l'administrateur. Il s'agit d'assurer la qualité et la pertinence de l'événement affiché sur la plate-forme.

-   SCAND CODE QR pour le fabricant d'événements:

    Cette fonction permet au fabricant d'événements de vérifier facilement la présence de visiteurs en scannant le code QR sur le billet. Cela aide à la gestion des événements et à la validation des billets efficacement.

-   Retirer le solde et le revenu:

    Le fabricant d'événements peut attirer leurs soldes et leurs revenus grâce aux fonctionnalités de retrait fournies par la demande. Cela offre une flexibilité à l'organisateur de l'événement pour gérer facilement leurs résultats financiers.

-   Notification en temps réel

    Avec l'aide de_service de fond_(Android et iOS), les utilisateurs recevront des notifications en temps réel sur l'état de l'événement, l'état de retrait, l'achat et les ventes de billets.

## Soutien et don

[![Donate paypal](https://img.shields.io/badge/Donate-PayPal-green.svg?style=for-the-badge)](https://paypal.me/ikhsan3adi?country.x=ID&locale.x=en_US)[![Donate saweria](https://img.shields.io/badge/Donate-Saweria-red?style=for-the-badge&link=https%3A%2F%2Fsaweria.co%2Fxiboxann)](https://saweria.co/xiboxann)
