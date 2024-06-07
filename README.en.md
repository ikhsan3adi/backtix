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
>     -   [NestJS 10](https://nestjs.com/)TypeScript
>     -   Prisma ORM
>     -   PostgreSQL
>     -   Redis
>     -   Swagger(API docs)
>
> -   Admin panel web (Monorepo with API service)
>
>     -   [SvelteKit 2](https://kit.svelte.dev/)TypeScript
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

This online event creation and ticket sales application is a platform that makes it easy for users to access and participate in various events. Following is the description
Briefly the main features of the application:

-   Authentication:

    The app offers secure authentication via JSON Web Token (JWT) and Google Sign-In. Users can easily log in to their accounts with convenient and secure authentication methods.

-   Account Activation Via Email:

    To increase security and ensure user authenticity, the application requires account activation via email. Users will receive an activation code to confirm and activate their account.

-   Nearby Event Search:

    Users can search for events taking place closest to their location. This feature allows users to discover and participate in events held near them.

-   Ticket Purchase with Midtrans:

    This application provides online ticket sales services using the Midtrans payment gateway. Users can easily purchase tickets for events of interest with a variety of convenient payment options.

-   Creating an Event with Admin Approval:

    Users who want to hold events can create them through the app. However, the event will be published after getting approval from the admin. This is to ensure the quality and relevance of the events displayed on the platform.

-   Scan QR Code for Event Creator:

    This feature allows event creators to easily verify visitor attendance by scanning the QR code on the ticket. This helps in efficient event management and ticket validation.

-   Withdraw Balance and Income:

    Event creators can withdraw their balance and earnings via the withdrawal feature provided by the application. This gives event organizers the flexibility to manage their financial results with ease.

-   Real-Time Notifications

    With the help of_background service_(Android & IOS), users will receive real-time notifications about event status, withdrawal status, ticket purchases and sales.

## Support and donate

[![Donate paypal](https://img.shields.io/badge/Donate-PayPal-green.svg?style=for-the-badge)](https://paypal.me/xannxett?country.x=ID&locale.x=en_US)[![Donate saweria](https://img.shields.io/badge/Donate-Saweria-red?style=for-the-badge&link=https%3A%2F%2Fsaweria.co%2Fxiboxann)](https://saweria.co/xiboxann)
