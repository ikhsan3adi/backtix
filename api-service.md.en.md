## Back-end service (NestJS)

-   [Indonesian](./api-service.md)
-   [English](./api-service.en.md)

It includes an admin panel application

    apps/api
    apps/admin-panel

### System Requirements

Make sure your system meets the following requirements before starting the installation:

-   Node.js v18 or higher
-   PostgreSQL 15 or higher
-   Redis v5 or higher

### Installation Steps

1.  Clone/extract Repository

2.  Install dependencies:

```bash
npm i
```

#### Setup environment

-   Rename`.env.example`to`.env`

#### Setup database

-   Arrange`DATABASE_URL`Of`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Jalankan migrasi untuk membuat tabel yang diperlukan

```bash
npx prisma migrate deploy
```

-   Run the database seeder to create users`superadmin`

```bash
npm run db:seed
```

#### Setup**Google sign in**server & client ID

-   Create a new project at[Google Cloud Console](https://console.cloud.google.com/projectcreate)

-   Once you're done creating a project, select it`APIs & Services`, then select`OAuth consent screen`on the left side

-   Enter the application name, email and`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Server**client ID

    -   Select`Credentials`in the left sidebar, click`CREATE CREDENTIALS`, select`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Select`Web application`application type, beri nama lalu save/create

    ![Cloud Console](/assets/Screenshot_3.png)

-   Translation`Client ID`and`Client secret`I gave`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Web app**client ID

    -   `CREATE CREDENTIALS`back, select`OAuth client ID`

    -   Select`Web application`application type, give a name and`Authorized JavaScript origins`as in the picture (if using localhost), then save/create

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Translation`Client ID`and`Client secret`I gave`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Click`DOWNLOAD JSON`and save the Client ID. Web Client ID will be used in flutter mobile app.

#### Setup midtrans server & client key

-   Go to[Dashboard Midtrans](https://dashboard.midtrans.com/), select environment`sandbox`(recommended) atau`production`
-   Enter to`Settings`>`Access Keys`, then copy the client and server keys to the file`.env`

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

-   Open http&#x3A;//localhost:3000/api/docs (adjust base url)

3.  Test (optional)

```bash
npm test
```

### Screenshots

![Swagger API Docs](/assets/swagger.png)
