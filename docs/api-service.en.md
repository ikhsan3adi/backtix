## Back-end service (NestJS)

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

Includes the admin application panel in it

    apps/api
    apps/admin-panel

### System requirements

Make sure your system meets the following requirements before starting the installation:

-   Node.js v18 or higher
-   PostgreSQL 15 or higher
-   Redis v5 or higher

### Installation steps

1.  Clone/extract Repository

2.  Install dependencies:

```bash
npm i
```

#### Setup environment

-   Rename`.env.example`to`.env`

#### Setup database

-   Set`DATABASE_URL`Of`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Run migration to make the required table

```bash
npx prisma migrate deploy
```

-   Run the Database Seeder to create a user`superadmin`

```bash
npm run db:seed
```

#### Setup**Google sign in**server & client ID

-   Create a new project at[Google Cloud Console](https://console.cloud.google.com/projectcreate)

-   Once finished making the project, select`APIs & Services`, then choose`OAuth consent screen`on the left

-   Enter the name of the application, email and`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Server**client ID

    -   Choose`Credentials`On the left sidebar, click`CREATE CREDENTIALS`, choose`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Choose`Web application`application type, beri nama lalu save/create

    ![Cloud Console](/assets/Screenshot_3.png)

-   Translation`Client ID`And`Client secret`File of`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Web app**client ID

    -   `CREATE CREDENTIALS`Back, choose`OAuth client ID`

    -   Choose`Web application`Application type, name and`Authorized JavaScript origins`Like in the picture (if using localhost), then save/create

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Translation`Client ID`And`Client secret`File of`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Click`DOWNLOAD JSON`and save client ID. Web Client ID will be used in the mobile app flutter.

#### Setup midtrans server & client key

-   Go to[Dashboard Midtrans](https://dashboard.midtrans.com/), select Environment`sandbox`(recommended) atau`production`
-   Enter`Settings`>`Access Keys`, then copy the client and server key to the file`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   Variable configuration`.env`others as needed.

### How to run

1.  Generate`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  Run app

```bash
npm run start
```

-   Development mode

```bash
npm run start:dev
```

2.  Swagger API docs

-   Open http&#x3A; // localhost: 3000/fire/docs (adjust the base url)

3.  Test (optional)

```bash
npm test
```

### Screenshots

![Swagger API Docs](/assets/swagger.png)
