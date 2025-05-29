## バックエンドサービス（ネスチ）

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

その中に管理者アプリケーションパネルが含まれています

    apps/api
    apps/admin-panel

### システム要件

インストールを開始する前に、システムが次の要件を満たしていることを確認してください。

-   node.js v18以降
-   postgreSql 15以上
-   Redis V5以上

### インストール手順

1.  クローン/抽出リポジトリ

2.  依存関係をインストールします：

```bash
npm i
```

#### セットアップ環境

-   名前を変更します`.env.example`に`.env`

#### データベースのセットアップ

-   セット`DATABASE_URL`の`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   移行を実行して、必要なテーブルを作成します

```bash
npx prisma migrate deploy
```

-   データベースシーダーを実行してユーザーを作成します`superadmin`

```bash
npm run db:seed
```

#### 設定**Googleがサインインします**サーバーとクライアントID

-   で新しいプロジェクトを作成します[Googleクラウドコンソール](https://console.cloud.google.com/projectcreate)

-   プロジェクトの作成が終了したら、選択します`APIs & Services`、選択します`OAuth consent screen`左に

-   アプリケーションの名前、電子メール、および`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **サーバ**クライアントID

    -   選ぶ`Credentials`左側のサイドバーで、クリックします`CREATE CREDENTIALS`、 選ぶ`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   選ぶ`Web application`アプリケーションタイプ、beri nama lalu save/create

    ![Cloud Console](/assets/Screenshot_3.png)

-   翻訳`Client ID`そして`Client secret`のファイル`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Webアプリ**クライアントID

    -   `CREATE CREDENTIALS`戻って、選択してください`OAuth client ID`

    -   選ぶ`Web application`アプリケーションタイプ、名前、および`Authorized JavaScript origins`写真のように（LocalHostを使用している場合）、保存/作成します

    ![Cloud Console](/assets/Screenshot_4.png)

    -   翻訳`Client ID`そして`Client secret`のファイル`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   クリック`DOWNLOAD JSON`クライアントIDを保存します。 WebクライアントIDは、モバイルアプリフラッターで使用されます。

#### MidTransサーバーとクライアントキーのセットアップ

-   行きます[ダッシュボードミッドトラン](https://dashboard.midtrans.com/)、環境を選択します`sandbox`（推奨）または`production`
-   入力`Settings`>`Access Keys`、次に、クライアントとサーバーキーをファイルにコピーします`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   変数構成`.env`必要に応じて他の人。

### 実行方法

1.  生成する`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  アプリを実行します

```bash
npm run start
```

-   開発モード

```bash
npm run start:dev
```

2.  Swagger APIドキュメント

-   http：// localhost：3000/fire/docsを開く（ベースURLを調整）

3.  テスト（オプション）

```bash
npm test
```

### スクリーンショット

![Swagger API Docs](/assets/swagger.png)
