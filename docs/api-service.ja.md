## バックエンドサービス (NestJS)

-   [インドネシア語](api-service.md)
-   [英語](api-service.en.md)

管理パネルアプリケーションが含まれています

    apps/api
    apps/admin-panel

### システム要求

インストールを開始する前に、システムが次の要件を満たしていることを確認してください。

-   Node.js v18以降
-   PostgreSQL 15 以降
-   Redis v5 以降

### インストール手順

1.  リポジトリのクローン/抽出

2.  依存関係をインストールします。

```bash
npm i
```

#### セットアップ環境

-   名前を変更する`.env.example`に`.env`

#### データベースのセットアップ

-   整える`DATABASE_URL`の`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   移行を実行して必要なテーブルを作成します

```bash
npx prisma migrate deploy
```

-   データベース シーダーを実行してユーザーを作成する`superadmin`

```bash
npm run db:seed
```

#### 設定**Google サインイン**サーバーとクライアントID

-   新しいプロジェクトを次の場所に作成します[Googleクラウドコンソール](https://console.cloud.google.com/projectcreate)

-   プロジェクトの作成が完了したら、それを選択します`APIs & Services`を選択し、`OAuth consent screen`左側に

-   アプリケーション名、電子メールアドレスを入力し、`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **サーバ**クライアントID

    -   選択する`Credentials`左側のサイドバーで、 をクリックします`CREATE CREDENTIALS`、 選択する`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   選択する`Web application`アプリケーションタイプ、ベリナマラル保存/作成

    ![Cloud Console](/assets/Screenshot_3.png)

-   翻訳`Client ID`そして`Client secret`私が与えた`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **ウェブアプリ**クライアントID

    -   `CREATE CREDENTIALS`戻る、選択`OAuth client ID`

    -   選択する`Web application`アプリケーションの種類、名前を付けて、`Authorized JavaScript origins`図のように（ローカルホストを使用している場合）、保存/作成します

    ![Cloud Console](/assets/Screenshot_4.png)

    -   翻訳`Client ID`そして`Client secret`私が与えた`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   クリック`DOWNLOAD JSON`クライアント ID を保存します。 Web クライアント ID は Flutter モバイル アプリで使用されます。

#### ミッドトランスサーバーとクライアントキーのセットアップ

-   に行く[ダッシュボードミッドトランス](https://dashboard.midtrans.com/)、環境を選択してください`sandbox`(推奨) アタウ`production`
-   に入力してください`Settings`＞`Access Keys`、次にクライアントとサーバーのキーをファイルにコピーします`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   変数設定`.env`その他必要に応じて。

### 走り方

1.  生成する`metadata`：

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  アプリを実行する

```bash
npm run start
```

-   開発モード

```bash
npm run start:dev
```

2.  Swagger API ドキュメント

-   http&#x3A;//localhost:3000/api/docs を開きます (ベース URL を調整します)。

3.  テスト（オプション）

```bash
npm test
```

### スクリーンショット

![Swagger API Docs](/assets/swagger.png)
