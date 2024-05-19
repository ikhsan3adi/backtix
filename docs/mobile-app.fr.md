## Application mobile (Flutter)

-   [indonésien](mobile-app.md)
-   [Anglais](mobile-app.en.md)

### Configuration requise

Assurez-vous que votre système répond aux exigences suivantes avant de démarrer l'installation :

-   SDK Flutter v3.16 ou supérieur

### Étapes d'installation

1.  Cloner/extraire le référentiel

2.  Installer les dépendances :

```bash
flutter pub get
```

3.  Courir`build_runner`générer des fichiers`*.g.dart`

```bash
dart run build_runner build
```

#### Environnement de configuration

1.  Renommer`.env.example`à`.env`

2.  Personnaliser`API_BASE_URL`de fichiers`.env`

#### Clé client Midtrans

-   Effectuez l'étape précédente dans[Service back-end - Configuration du serveur Midtrans et de la clé client](api-service.md#setup-midtrans-server--client-key)

-   Traduction**clé client**J'ai donné`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### Installation**Connectez-vous à Google**identité du client

-   Effectuez l'étape précédente dans[Service back-end - Configuration du serveur de connexion Google et de l'ID client](api-service.md#setup-google-sign-in-server--client-id)

-   Traduction`Web Client ID`et`Server Client ID`J'ai donné`.env`

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

-   **Android**identité du client

    -   Ouvrez un terminal, accédez au répertoire du projet d'application

    -   Accédez ensuite au dossier Android

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   Exécutez la commande suivante

        -   Pour Linux et MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   Pour les fenêtres

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   :avertissement : Remplacer`<path-to-project>`avec le chemin du répertoire du projet d’application.
            Exemple:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   Il vous sera demandé de saisir un mot de passe, par exemple`backtix`

    -   Ouvrir des fichiers`android/app/build.gradle`puis changez cette partie :
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

    -   Ouvrez le terminal, accédez au dossier`android`dans le projet d'application, puis exécutez la commande suivante :

        ```bash
        ./gradlew signingReport
        ```

    -   Rechercher et copier des valeurs`SHA1`depuis`variant: debug`le plus haut.

        ![Terminal](/assets/Screenshot_5.png)

    -   Aller à[Google Cloud Console](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   Sélectionner`Credentials`dans la barre latérale gauche, cliquez sur`CREATE CREDENTIALS`, sélectionner`OAuth client ID`

    -   Sélectionner`Android`type de demande

    -   Donnez-lui un nom, et`Package name`. le nom du package peut être connu à partir du fichier`android/app/build.gradle`

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

-   Entrer`SHA1`de l'étape précédente, puis enregistrez/créez
