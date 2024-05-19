## Service back-end (NestJS)

-   [indonésien](api-service.md)
-   [Anglais](api-service.en.md)

Il comprend une application de panneau d'administration

    apps/api
    apps/admin-panel

### Configuration requise

Assurez-vous que votre système répond aux exigences suivantes avant de démarrer l'installation :

-   Node.js v18 ou supérieur
-   PostgreSQL 15 ou supérieur
-   Redis v5 ou supérieur

### Étapes d'installation

1.  Cloner/extraire le référentiel

2.  Installer les dépendances :

```bash
npm i
```

#### Environnement de configuration

-   Renommer`.env.example`à`.env`

#### Base de données de configuration

-   Organiser`DATABASE_URL`De`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Exécutez la migration pour créer les tables requises

```bash
npx prisma migrate deploy
```

-   Exécutez le seeder de base de données pour créer des utilisateurs`superadmin`

```bash
npm run db:seed
```

#### Installation**Connectez-vous à Google**ID serveur et client

-   Créez un nouveau projet sur[Google Cloud Console](https://console.cloud.google.com/projectcreate)

-   Une fois que vous avez fini de créer un projet, sélectionnez-le`APIs & Services`, puis sélectionnez`OAuth consent screen`sur le côté gauche

-   Entrez le nom de l'application, l'e-mail et`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Serveur**identité du client

    -   Sélectionner`Credentials`dans la barre latérale gauche, cliquez sur`CREATE CREDENTIALS`, sélectionner`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Sélectionner`Web application`type d'application, beri nama lalu enregistrer/créer

    ![Cloud Console](/assets/Screenshot_3.png)

-   Traduction`Client ID`et`Client secret`J'ai donné`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Application Web**identité du client

    -   `CREATE CREDENTIALS`retour, sélectionnez`OAuth client ID`

    -   Sélectionner`Web application`type de candidature, donnez un nom et`Authorized JavaScript origins`comme sur l'image (si vous utilisez localhost), puis enregistrez/créez

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Traduction`Client ID`et`Client secret`J'ai donné`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Cliquez sur`DOWNLOAD JSON`et enregistrez l'ID client. L'ID client Web sera utilisé dans l'application mobile Flutter.

#### Configurer le serveur Midtrans et la clé client

-   Aller à[Tableau de bord Midtrans](https://dashboard.midtrans.com/), sélectionnez l'environnement`sandbox`(recommandé) atau`production`
-   Entrez pour`Settings`>`Access Keys`, puis copiez les clés client et serveur dans le fichier`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   Configuration variable`.env`d'autres selon les besoins.

### Comment courir

1.  Générer`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  Exécuter l'application

```bash
npm run start
```

-   Mode de développement

```bash
npm run start:dev
```

2.  Documentation sur l'API Swagger

-   Ouvrez http&#x3A;//localhost:3000/api/docs (ajustez l'URL de base)

3.  Test (facultatif)

```bash
npm test
```

### Captures d'écran

![Swagger API Docs](/assets/swagger.png)
