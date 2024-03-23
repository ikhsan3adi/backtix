## Mobile app (Flutter)

-   [Indonesian](mobile-app.md)
-   [English](mobile-app.en.md)

### System Requirements

Make sure your system meets the following requirements before starting the installation:

-   Flutter SDK v3.16 or higher

### Installation Steps

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

2.  Customize`API_BASE_URL`of files`.env`

#### Midtrans client key

-   Complete the previous step in[Back-end service - Setup midtrans server & client key](api-service.md#setup-midtrans-server--client-key)

-   Translation**client key**I gave`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### Setup**Google sign in**client ID

-   Complete the previous step in[Back-end service - Setup Google sign in server & client ID](api-service.md#setup-google-sign-in-server--client-id)

-   Translation`Web Client ID`and`Server Client ID`I gave`.env`

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

    -   Open a terminal, navigate to the application project directory

    -   Then navigate to the android folder

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   Run the following command

        -   For Linux and MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   For windows

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   :warning: Replace`<path-to-project>`with the application project directory path.
            Example:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   You will be asked to enter a password, for example`backtix`

    -   Book file`android/app/build.gradle`then change this part:
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

    -   Open terminal, navigate to folder`android`in the application project, then run the following command:

        ```bash
        ./gradlew signingReport
        ```

    -   Search and copy values`SHA1`from`variant: debug`the highest.

        ![Terminal](/assets/Screenshot_5.png)

    -   Go to[Google Cloud Console](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   Select`Credentials`in the left sidebar, click`CREATE CREDENTIALS`, select`OAuth client ID`

    -   Select`Android`application type

    -   Give it a name, and`Package name`. package name can be known from the file`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   If you want to change the package name, you can use[change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   Enter`SHA1`from the previous step, then save/create
