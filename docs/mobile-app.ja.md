## モバイルアプリ（フラッター）

<a href="./mobile-app.md">
  <img alt="Translation" src="https://img.shields.io/badge/Bahasa_Indonesia-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./mobile-app.en.md">
  <img alt="Translation" src="https://img.shields.io/badge/English-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./mobile-app.zh-CN.md">
  <img alt="Translation" src="https://img.shields.io/badge/简体中文-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./mobile-app.ja.md">
  <img alt="Translation" src="https://img.shields.io/badge/日本語-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./mobile-app.ar.md">
  <img alt="Translation" src="https://img.shields.io/badge/Arabic_عربي-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./mobile-app.pt.md">
  <img alt="Translation" src="https://img.shields.io/badge/Português-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./mobile-app.es.md">
  <img alt="Translation" src="https://img.shields.io/badge/Español-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./mobile-app.fr.md">
  <img alt="Translation" src="https://img.shields.io/badge/Français-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./mobile-app.vi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Tiếng_Việt-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./mobile-app.hi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Hindi_हिंदी-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

### システム要件

インストールを開始する前に、システムが次の要件を満たしていることを確認してください。

-   フラッターSDK v3.16以降

### インストール手順

1.  クローン/抽出リポジトリ

2.  依存関係をインストールします：

```bash
flutter pub get
```

3.  走る`build_runner`ファイルを生成します`*.g.dart`

```bash
dart run build_runner build
```

#### セットアップ環境

1.  名前を変更します`.env.example`に`.env`

2.  調整する`API_BASE_URL`ファイル`.env`

#### MidTransクライアントキー

-   での前のステップを完了します[バックエンドサービス - セットアップMIDTRANSサーバーとクライアントキー](api-service.md#setup-midtrans-server--client-key)

-   翻訳**クライアントキー**のファイル`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### 設定**Googleがサインインします**クライアントID

-   での前のステップを完了します[バックエンドサービス - サーバーとクライアントIDのGoogleサインをセットアップ](api-service.md#setup-google-sign-in-server--client-id)

-   翻訳`Web Client ID`そして`Server Client ID`のファイル`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   翻訳`Web Client ID``android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **アンドロイド**クライアントID

    -   端子を開き、アプリケーションプロジェクトディレクトリに移動します

    -   次に、Androidフォルダーをホストします

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   次のコマンドを実行します

        -   LinuxとMacOSの場合

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   Windows用

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   ：警告：変更`<path-to-project>`アプリケーションプロジェクトのアプリケーションディレクトリ付き。
            例：

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   パスワードを入力するように求められます`backtix`

    -   ファイルを開きます`android/app/build.gradle`次に、このセクションを変更します。
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

    -   端子を開き、フォルダーを指します`android`アプリケーションプロジェクトで、次のコマンドを実行します。

        ```bash
        ./gradlew signingReport
        ```

    -   値を検索してコピーします`SHA1`から`variant: debug`最高です。

        ![Terminal](/assets/Screenshot_5.png)

    -   行きます[Googleクラウドコンソール](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   選ぶ`Credentials`左側のサイドバーで、クリックします`CREATE CREDENTIALS`、 選ぶ`OAuth client ID`

    -   選ぶ`Android`アプリケーションタイプ

    -   名前、そして`Package name`。パッケージ名はファイルから見ることができます`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   パッケージ名を変更したい場合は、使用できます[change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   入力`SHA1`前のステップから、保存/作成します
