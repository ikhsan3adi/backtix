## Application mobile (Flutter)

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

### Exigences du système

Assurez-vous que votre système répond aux exigences suivantes avant de démarrer l'installation:

-   Flutter SDK v3.16 ou plus

### Étapes d'installation

1.  Référentiel de clones / extraits

2.  Installez les dépendances:

```bash
flutter pub get
```

3.  Courir`build_runner`Pour générer des fichiers`*.g.dart`

```bash
dart run build_runner build
```

#### Environnement de configuration

1.  Rebaptiser`.env.example`à`.env`

2.  Ajuster`API_BASE_URL`déposer`.env`

#### Clé du client MidTrans

-   Terminer l'étape précédente à[Service back-end - Configuration du serveur MidTrans et de la clé client](api-service.md#setup-midtrans-server--client-key)

-   Traduction**clé client**Dossier de`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### Installation**Google Connectez-vous**ID client

-   Terminer l'étape précédente à[Service back-end - Configuration de Google Connectez-vous en ID de serveur et client](api-service.md#setup-google-sign-in-server--client-id)

-   Traduction`Web Client ID`Et`Server Client ID`Dossier de`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   Traduction`Web Client ID`le`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **Androïde**ID client

    -   Ouvrez le terminal, accédez au répertoire du projet d'application

    -   Puis hébergez le dossier Android

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   Exécutez les commandes suivantes

        -   Pour Linux et macOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   Pour les fenêtres

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   : Avertissement: changer`<path-to-project>`avec le répertoire des applications du projet d'application.
            Exemple:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   Il vous sera demandé de saisir un mot de passe, exemple`backtix`

    -   Ouvrir le fichier`android/app/build.gradle`Modifiez ensuite cette section:
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

    -   Ouvrez le terminal, pointez du dossier`android`Dans le projet d'application, puis exécutez la commande suivante:

        ```bash
        ./gradlew signingReport
        ```

    -   Valeur de recherche et de copie`SHA1`depuis`variant: debug`le plus élevé.

        ![Terminal](/assets/Screenshot_5.png)

    -   Aller à[Console Cloud Google](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   Choisir`Credentials`Dans la barre latérale gauche, cliquez`CREATE CREDENTIALS`, choisir`OAuth client ID`

    -   Choisir`Android`type d'application

    -   Nom, et`Package name`. Le nom du package peut être vu à partir du fichier`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   Si vous souhaitez modifier le nom du package, vous pouvez utiliser[change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   Entrer`SHA1`À partir de l'étape précédente, puis enregistrez / créez
