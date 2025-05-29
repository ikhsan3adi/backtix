# Backtix

> Evento de código aberto e aplicativo de bilheteria

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

## Código -fonte

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

* * *

> [!IMPORTANTE]
>
> ## Instalação &_Como correr_
>
> [Serviço de API de back-end](docs/api-service.md)
>
> [Admin-pain](docs/admin-panel.md)
>
> [Aplicativo móvel](docs/mobile-app.md)
>
> * * *
>
> [!OBSERVAÇÃO]
>
> ## Pilha de tecnologia
>
> -   Serviço de API / back-end
>
>     -   [Não 10](https://nestjs.com/)TypeScript
>     -   Prisma ORM
>     -   PostGresql
>     -   Redis
>     -   Swagger (API Docs)
>
> -   Web do painel de administrador (monorepo com serviço de API)
>
>     -   [Svelteki 2](https://kit.svelte.dev/)TypeScript
>     -   Componente da interface do usuário Flowbite
>     -   Tailwind CSS
>
> -   Aplicativo móvel
>
>     -   [Flutter 3](https://flutter.dev/)
>         -   Bloco
>         -   Congelado
>         -   Adaptação
>         -   fpDart

* * *

O aplicativo para fazer eventos e vendas de ingressos on -line é uma plataforma que fornece conveniência para os usuários acessarem e participarem de vários eventos. Aqui está uma descrição
Recursos de aplicativo principal curtos:

-   Autenticação:

    Este aplicativo oferece autenticação segura através do JSON Web Token (JWT) e do Google assinando. Os usuários podem inserir facilmente sua conta com um método de autenticação confortável e seguro.

-   Ativação da conta por e -mail:

    Para aumentar a segurança e garantir a autenticidade do usuário, o aplicativo requer ativação da conta por e -mail. Os usuários receberão um código de ativação para confirmar e ativar sua conta.

-   Pesquisa de evento mais próxima:

    Os usuários podem encontrar eventos que ocorrem mais próximos de sua localização. Esse recurso permite que os usuários encontrem e participem de eventos realizados ao seu redor.

-   Compra de ingressos com Midtrans:

    Este aplicativo fornece serviços de vendas de ingressos on -line usando gateways de pagamento MIDTRANS. Os usuários podem comprar ingressos facilmente para eventos que estão em demanda com uma variedade de opções de pagamento confortáveis.

-   Faça um evento com aprovação do administrador:

    Os usuários que desejam realizar um evento podem passar pelo aplicativo. No entanto, o evento será publicado após a aprovação do administrador. Isso é para garantir a qualidade e a relevância do evento exibido na plataforma.

-   Código QR Scan para o fabricante de eventos:

    Esse recurso permite que o fabricante de eventos verifique facilmente a presença de visitantes digitalizando o código QR no ticket. Isso ajuda no gerenciamento de eventos e na validação de ingressos com eficiência.

-   Retirar saldo e renda:

    O fabricante de eventos pode atrair seus saldos e renda através dos recursos de retirada fornecidos pelo aplicativo. Isso fornece flexibilidade ao organizador do evento para gerenciar seus resultados financeiros facilmente.

-   Notificação em tempo real

    Com a ajuda de_serviço de fundo_(Android & iOS), os usuários receberão notificações em tempo real sobre o status do evento, status de retirada, compra e venda de ingressos.

## Apoio e doação

[![Donate paypal](https://img.shields.io/badge/Donate-PayPal-green.svg?style=for-the-badge)](https://paypal.me/ikhsan3adi?country.x=ID&locale.x=en_US)[![Donate saweria](https://img.shields.io/badge/Donate-Saweria-red?style=for-the-badge&link=https%3A%2F%2Fsaweria.co%2Fxiboxann)](https://saweria.co/xiboxann)
