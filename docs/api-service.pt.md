## Serviço de back-end (Nestjs)

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

Inclui o painel de aplicativos de administrador nele

    apps/api
    apps/admin-panel

### Requisitos do sistema

Verifique se o seu sistema atende aos seguintes requisitos antes de iniciar a instalação:

-   Node.js v18 ou superior
-   PostgreSql 15 ou superior
-   Redis V5 ou superior

### Etapas de instalação

1.  Repositório de clone/extrato

2.  Instale dependências:

```bash
npm i
```

#### Ambiente de configuração

-   Renomear`.env.example`para`.env`

#### Banco de dados de configuração

-   Definir`DATABASE_URL`De`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Execute a migração para fazer a tabela necessária

```bash
npx prisma migrate deploy
```

-   Execute a semente de banco de dados para criar um usuário`superadmin`

```bash
npm run db:seed
```

#### Configurar**Google Entrar**Servidor e ID do cliente

-   Crie um novo projeto em[Google Cloud Console](https://console.cloud.google.com/projectcreate)

-   Depois de terminar de fazer o projeto, selecione`APIs & Services`, então escolha`OAuth consent screen`à esquerda

-   Digite o nome do aplicativo, email e`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Servidor**ID do cliente

    -   Escolher`Credentials`Na barra lateral esquerda, clique`CREATE CREDENTIALS`, escolher`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Escolher`Web application`Tipo de aplicativo, beri nama lalu salvar/criar

    ![Cloud Console](/assets/Screenshot_3.png)

-   Tradução`Client ID`E`Client secret`Arquivo de`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Aplicativo da web**ID do cliente

    -   `CREATE CREDENTIALS`De volta, escolha`OAuth client ID`

    -   Escolher`Web application`Tipo de aplicativo, nome e`Authorized JavaScript origins`Como na imagem (se estiver usando localhost), salve/crie

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Tradução`Client ID`E`Client secret`Arquivo de`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Clique`DOWNLOAD JSON`e salve ID do cliente. O ID do cliente da Web será usado no aplicativo móvel.

#### Configurar o servidor Midtrans e a chave do cliente

-   Vá para[Painel Midtrans](https://dashboard.midtrans.com/), selecione o ambiente`sandbox`(recomendado) ou`production`
-   Digitar`Settings`>`Access Keys`, então copie a chave do cliente e do servidor para o arquivo`.env`

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

2.  Swagger API Docs

-   Aberto http&#x3A; // localhost: 3000/fogo/docs (ajuste o URL base)

3.  Teste (opcional)

```bash
npm test
```

### Capturas de tela

![Swagger API Docs](/assets/swagger.png)
