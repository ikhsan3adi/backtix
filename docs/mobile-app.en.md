## Mobile app (Flutter)

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

### System requirements

Make sure your system meets the following requirements before starting the installation:

-   Flutter SDK v3.16 or higher

### Installation steps

1.  Clone/extract Repository

2.  Install dependencies:

```bash
flutter pub get
```

3.  Run`build_runner`to generate files`*.g.dart`

```bash
dart run build_runner build
```

#### Setup environment

1.  Rename`.env.example`to`.env`

2.  Adjust`API_BASE_URL`of file`.env`

#### Midtrans client key

-   Complete the previous step at[Back-end service - Setup midtrans server & client key](api-service.md#setup-midtrans-server--client-key)

-   Translation**client key**File of`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### Setup**Google sign in**client ID

-   Complete the previous step at[Back-end service - Setup Google sign in server & client ID](api-service.md#setup-google-sign-in-server--client-id)

-   Translation`Web Client ID`And`Server Client ID`File of`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   Translation`Web Client ID`the`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **Android**client ID

    -   Open the terminal, navigate to the Application Project Directory

    -   Then host to the Android folder

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   Run the following commands

        -   For linux and macos

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   For Windows

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   : Warning: Change`<path-to-project>`with the Path Directory of the Application Project.
            Example:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   You will be asked to enter a password, example`backtix`

    -   Book gave`android/app/build.gradle`Then change this section:
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

    -   Open the terminal, point to the folder`android`In the application project, then run the following command:

        ```bash
        ./gradlew signingReport
        ```

    -   Search and copy value`SHA1`from`variant: debug`the highest.

        ![Terminal](/assets/Screenshot_5.png)

    -   Go to[Google Cloud Console](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   Choose`Credentials`On the left sidebar, click`CREATE CREDENTIALS`, choose`OAuth client ID`

    -   Choose`Android`application type

    -   Name, and`Package name`. Package Name can be seen from the file`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   If you want to change the package name you can use[change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   Enter`SHA1`From the previous step, then save/create
