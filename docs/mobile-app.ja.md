## モバイルアプリ (Flutter)

-   [インドネシア語](mobile-app.md)
-   [英語](mobile-app.en.md)

### システム要求

インストールを開始する前に、システムが次の要件を満たしていることを確認してください。

-   Flutter SDK v3.16 以降

### インストール手順

1.  リポジトリのクローン/抽出

2.  依存関係をインストールします。

```bash
flutter pub get
```

3.  走る`build_runner`ファイルを生成する`*.g.dart`

```bash
dart run build_runner build
```

#### セットアップ環境

1.  名前を変更する`.env.example`に`.env`

2.  カスタマイズ`API_BASE_URL`ファイルの数`.env`

#### Midtransクライアントキー

-   の前の手順を完了します[バックエンド サービス - ミッドトランス サーバーとクライアント キーのセットアップ](api-service.md#setup-midtrans-server--client-key)

-   翻訳**クライアントキー**私が与えた`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### 設定**Google サインイン**クライアントID

-   の前の手順を完了します[バックエンド サービス - Google サインイン サーバーとクライアント ID のセットアップ](api-service.md#setup-google-sign-in-server--client-id)

-   翻訳`Web Client ID`そして`Server Client ID`私が与えた`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   翻訳`Web Client ID`の`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **アンドロイド**クライアントID

    -   ターミナルを開き、アプリケーションのプロジェクト ディレクトリに移動します。

    -   次に、androidフォルダーに移動します

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   次のコマンドを実行します

        -   Linux および MacOS の場合

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   窓用

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   :警告: 交換してください`<path-to-project>`アプリケーションプロジェクトのディレクトリパスに置き換えます。
            例：

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   パスワードの入力を求められます。たとえば、`backtix`

    -   ファイルを開く`android/app/build.gradle`次に、この部分を変更します。
        ```gradle
        signingConfigs {
          debug {
              keyAlias 'keyalias'
              keyPassword <your-password> // sesuaikan dengan password dari langkah sebelumnya
              storeFile file('androidkey.jks')
              storePassword <your-password> // sesuaikan dengan password dari langkah sebelumnya
          }
        }
        ```

    -   ターミナルを開き、フォルダーに移動します`android`アプリケーション プロジェクトで次のコマンドを実行します。

        ```bash
        ./gradlew signingReport
        ```

    -   値の検索とコピー`SHA1`から`variant: debug`最高。

        ![Terminal](/assets/Screenshot_5.png)

    -   に行く[Googleクラウドコンソール](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   選択する`Credentials`左側のサイドバーで、 をクリックします`CREATE CREDENTIALS`、 選択する`OAuth client ID`

    -   選択する`Android`アプリケーションタイプ

    -   名前を付けて、`Package name`。パッケージ名はファイルから知ることができます`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   パッケージ名を変更したい場合は、次を使用できます[アプリのパッケージ名変更](https://pub.dev/packages/change_app_package_name)

-   入力`SHA1`前のステップから保存/作成します
