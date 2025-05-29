# BackTix

> Open Source Event & Ticketing App

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

## Source Code

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

* * *

> [!IMPORTANT]
>
> ## Installation &_How to run_
>
> [Back-end API service](docs/api-service.md)
>
> [Admin-panel](docs/admin-panel.md)
>
> [Mobile app](docs/mobile-app.md)
>
> * * *
>
> [!NOTE]
>
> ## Tech Stack
>
> -   API service / back-end
>
>     -   [NO 10](https://nestjs.com/)TypeScript
>     -   Prisma ORM
>     -   PostgreSQL
>     -   Redis
>     -   Swagger(API docs)
>
> -   Admin panel web (Monorepo with API service)
>
>     -   [Svelteki 2](https://kit.svelte.dev/)TypeScript
>     -   Flowbite UI component
>     -   Tailwind CSS
>
> -   Mobile app
>
>     -   [Flutter 3](https://flutter.dev/)
>         -   BLoC
>         -   Freezed
>         -   Retrofit
>         -   fpdart

* * *

The application for making events and online ticket sales is a platform that provides convenience for users to access and participate in various events. Here is a description
Short Main Application Features:

-   Authentication:

    This application offers safe authentication through JSON Web Token (JWT) and Google Sign-in. Users can easily enter their account with a comfortable and safe authentication method.

-   Account activation via email:

    To increase security and ensure the authenticity of the user, the application requires account activation via email. Users will receive an activation code to confirm and activate their account.

-   Nearest Event Search:

    Users can find events that take place closest to their location. This feature allows users to find and participate in events held around them.

-   Ticket purchase with Midtrans:

    This application provides online ticket sales services using midtrans payment gateways. Users can easily buy tickets for events that are in demand with a variety of comfortable payment options.

-   Make an event with admin approval:

    Users who want to hold an event can make it through the application. However, the event will be published after getting approval from the admin. This is to ensure the quality and relevance of the event displayed on the platform.

-   QR Code Scan for the event maker:

    This feature allows the event maker to easily verify the presence of visitors by scanning the QR Code on the ticket. This helps in event management and ticket validation efficiently.

-   Withdraw balance and income:

    The event maker can attract their balances and income through the Withdraw features provided by the application. This provides flexibility to the organizer of the event to manage their financial results easily.

-   Real-time notification

    With the help of_background service_(Android & iOS), users will receive real-time notifications about the status of the event, withdrawal status, purchase and ticket sales.

## Support and donation

[![Donate paypal](https://img.shields.io/badge/Donate-PayPal-green.svg?style=for-the-badge)](https://paypal.me/ikhsan3adi?country.x=ID&locale.x=en_US)[![Donate saweria](https://img.shields.io/badge/Donate-Saweria-red?style=for-the-badge&link=https%3A%2F%2Fsaweria.co%2Fxiboxann)](https://saweria.co/xiboxann)
