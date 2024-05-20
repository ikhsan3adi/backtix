# BackTix

> Aplicativo de código aberto para eventos e ingressos

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

Este aplicativo online de criação de eventos e venda de ingressos é uma plataforma que facilita o acesso e a participação dos usuários em diversos eventos. A seguir está a descrição
Resumidamente as principais características do aplicativo:

-   Autenticação:

    O aplicativo oferece autenticação segura via JSON Web Token (JWT) e Google Sign-In. Os usuários podem fazer login facilmente em suas contas com métodos de autenticação convenientes e seguros.

-   Ativação de conta por e-mail:

    Para aumentar a segurança e garantir a autenticidade do usuário, o aplicativo exige a ativação da conta via e-mail. Os usuários receberão um código de ativação para confirmar e ativar sua conta.

-   Pesquisa de eventos próximos:

    Os usuários podem pesquisar eventos que ocorrem mais próximos de sua localização. Este recurso permite que os usuários descubram e participem de eventos realizados perto deles.

-   Compra de ingressos com Midtrans:

    Este aplicativo fornece serviços de venda de ingressos on-line usando o gateway de pagamento Midtrans. Os usuários podem comprar facilmente ingressos para eventos de interesse com uma variedade de opções de pagamento convenientes.

-   Criando um evento com aprovação do administrador:

    Os usuários que desejam realizar eventos podem criá-los por meio do aplicativo. No entanto, o evento será publicado após aprovação do administrador. Isso é para garantir a qualidade e relevância dos eventos exibidos na plataforma.

-   Digitalize o código QR para o Event Creator:

    Este recurso permite que os criadores de eventos verifiquem facilmente a presença dos visitantes, digitalizando o código QR no ingresso. Isso ajuda no gerenciamento eficiente de eventos e na validação de ingressos.

-   Retirar Saldo e Renda:

    Os criadores de eventos podem sacar seu saldo e ganhos por meio do recurso de saque fornecido pelo aplicativo. Isso dá aos organizadores de eventos a flexibilidade para gerenciar seus resultados financeiros com facilidade.

-   Notificações em tempo real

    Com a ajuda de_serviço em segundo plano_(Android e IOS), os usuários receberão notificações em tempo real sobre o status do evento, status de retirada, compras e vendas de ingressos.

## Pilha de tecnologia

-   Serviço de API/back-end

    -   [NestJS 10](https://nestjs.com/)Texto datilografado
    -   Prisma ORM
    -   PostgreSQL
    -   Redis
    -   Swagger (documentos da API)

-   Web do painel de administração (Monorepo com serviço API)

    -   [SvelteKit 2](https://kit.svelte.dev/)Texto datilografado
    -   Componente de interface do usuário Flowbite
    -   CSS do vento favorável

-   Aplicativo móvel

    -   [Vibração 3](https://flutter.dev/)
        -   Bloco
        -   Congelado
        -   Reforma
        -   fpdart

## Código fonte

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

## Instalação e_Como correr_

[Serviço de API de back-end](docs/api-service.md)

[Painel de administração](docs/admin-panel.md)

[Aplicativo móvel](docs/mobile-app.md)
