## Serviço de back-end (NestJS)

<a href="./api-service.md">
  <img alt="Translation" src="https://img.shields.io/badge/Bahasa_Indonesia-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.en.md">
  <img alt="Translation" src="https://img.shields.io/badge/English-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.zh-CN.md">
  <img alt="Translation" src="https://img.shields.io/badge/简体中文-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.ja.md">
  <img alt="Translation" src="https://img.shields.io/badge/日本語-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.ar.md">
  <img alt="Translation" src="https://img.shields.io/badge/Arabic_عربي-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.pt.md">
  <img alt="Translation" src="https://img.shields.io/badge/Português-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.es.md">
  <img alt="Translation" src="https://img.shields.io/badge/Español-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.fr.md">
  <img alt="Translation" src="https://img.shields.io/badge/Français-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.vi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Tiếng_Việt-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.hi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Hindi_हिंदी-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

Inclui um aplicativo de painel de administração

    apps/api
    apps/admin-panel

### Requisitos de sistema

Certifique-se de que seu sistema atenda aos seguintes requisitos antes de iniciar a instalação:

-   Node.js v18 ou superior
-   PostgreSQL 15 ou superior
-   Redis v5 ou superior

### Etapas de instalação

1.  Clonar/extrair repositório

2.  Instale dependências:

```bash
npm i
```

#### Ambiente de configuração

-   Renomear`.env.example`para`.env`

#### Banco de dados de configuração

-   Arranjo`DATABASE_URL`De`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Execute a migração para criar as tabelas necessárias

```bash
npx prisma migrate deploy
```

-   Execute o semeador de banco de dados para criar usuários`superadmin`

```bash
npm run db:seed
```

#### Configurar**Login do Google**ID do servidor e do cliente

-   Crie um novo projeto em[Console do Google Cloud](https://console.cloud.google.com/projectcreate)

-   Quando terminar de criar um projeto, selecione-o`APIs & Services`e selecione`OAuth consent screen`no lado esquerdo

-   Digite o nome do aplicativo, e-mail e`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Servidor**ID do Cliente

    -   Selecione`Credentials`na barra lateral esquerda, clique em`CREATE CREDENTIALS`, selecione`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Selecione`Web application`tipo de aplicativo, beri nama lalu salvar/criar

    ![Cloud Console](/assets/Screenshot_3.png)

-   Tradução`Client ID`e`Client secret`Eu dei`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Aplicativo web**ID do Cliente

    -   `CREATE CREDENTIALS`voltar, selecione`OAuth client ID`

    -   Selecione`Web application`tipo de aplicativo, dê um nome e`Authorized JavaScript origins`como na imagem (se estiver usando localhost), então salve/crie

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Tradução`Client ID`e`Client secret`Eu dei`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Clique`DOWNLOAD JSON`e salve o ID do cliente. O ID do cliente da Web será usado no aplicativo móvel flutter.

#### Configurar servidor midtrans e chave do cliente

-   Vá para[Painel Midtrans](https://dashboard.midtrans.com/), selecione o ambiente`sandbox`(recomendado) ou`production`
-   Entrar para`Settings`>`Access Keys`e copie as chaves do cliente e do servidor para o arquivo`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   Configuração variável`.env`outros conforme necessário.

### Como correr

1.  Gerar`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  Executar aplicativo

```bash
npm run start
```

-   Modo de desenvolvimento

```bash
npm run start:dev
```

2.  Documentos da API Swagger

-   Abra http&#x3A;//localhost:3000/api/docs (ajuste o URL base)

3.  Teste (opcional)

```bash
npm test
```

### Capturas de tela

![Swagger API Docs](/assets/swagger.png)
