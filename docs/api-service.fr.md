## Service arrière (NESTJS)

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

Comprend le panneau de demande d'administration dans l'informatique

    apps/api
    apps/admin-panel

### Exigences du système

Assurez-vous que votre système répond aux exigences suivantes avant de démarrer l'installation:

-   Node.js v18 ou plus
-   Postgresql 15 ou plus
-   Redis v5 ou supérieur

### Étapes d'installation

1.  Référentiel de clones / extraits

2.  Installez les dépendances:

```bash
npm i
```

#### Environnement de configuration

-   Rebaptiser`.env.example`à`.env`

#### Configuration de la base de données

-   Ensemble`DATABASE_URL`De`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Exécuter la migration pour faire le tableau requis

```bash
npx prisma migrate deploy
```

-   Exécutez le Seeder de la base de données pour créer un utilisateur`superadmin`

```bash
npm run db:seed
```

#### Installation**Google Connectez-vous**ID de serveur et client

-   Créer un nouveau projet à[Console Cloud Google](https://console.cloud.google.com/projectcreate)

-   Une fois terminé de fabriquer le projet, sélectionnez`APIs & Services`, alors choisissez`OAuth consent screen`à gauche

-   Entrez le nom de l'application, de l'e-mail et`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Serveur**ID client

    -   Choisir`Credentials`Dans la barre latérale gauche, cliquez`CREATE CREDENTIALS`, choisir`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Choisir`Web application`Type d'application, Beri Nama Lalu Save / Create

    ![Cloud Console](/assets/Screenshot_3.png)

-   Traduction`Client ID`Et`Client secret`Dossier de`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Application Web**ID client

    -   `CREATE CREDENTIALS`Retour, choisissez`OAuth client ID`

    -   Choisir`Web application`Type d'application, nom et`Authorized JavaScript origins`Comme dans l'image (si vous utilisez localhost), alors enregistrez / créez

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Traduction`Client ID`Et`Client secret`Dossier de`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Faire un clic`DOWNLOAD JSON`et enregistrer l'ID client. L'ID du client Web sera utilisé dans l'application mobile Flutter.

#### Configuration du serveur MidTrans et de la clé client

-   Aller à[Tableau de bord Midtrans](https://dashboard.midtrans.com/), Sélectionner l'environnement`sandbox`(recommandé) ou`production`
-   Entrer`Settings`>`Access Keys`, puis copiez le client et la clé du serveur dans le fichier`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   Configuration variable`.env`d'autres au besoin.

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

2.  Docs API Swagger

-   Ouvrir http&#x3A; // localhost: 3000 / feu / docs (ajustez l'URL de base)

3.  Test (facultatif)

```bash
npm test
```

### Captures d'écran

![Swagger API Docs](/assets/swagger.png)
