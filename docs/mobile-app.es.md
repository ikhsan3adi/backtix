## Aplicación móvil (Flutter)

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

### Requisitos del sistema

Asegúrese de que su sistema cumpla con los siguientes requisitos antes de comenzar la instalación:

-   Flutter SDK v3.16 o superior

### Pasos de instalación

1.  Clonar/extraer repositorio

2.  Instalar dependencias:

```bash
flutter pub get
```

3.  Correr`build_runner`para generar archivos`*.g.dart`

```bash
dart run build_runner build
```

#### Entorno de configuración

1.  Rebautizar`.env.example`a`.env`

2.  Personalizar`API_BASE_URL`de archivos`.env`

#### Clave de cliente Midtrans

-   Complete el paso anterior en[Servicio back-end: configurar el servidor midtrans y la clave del cliente](api-service.md#setup-midtrans-server--client-key)

-   Traducción**clave de cliente**Di`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### Configuración**Iniciar sesión en Google**Identificación del cliente

-   Complete el paso anterior en[Servicio back-end: configurar el servidor de inicio de sesión de Google y el ID del cliente](api-service.md#setup-google-sign-in-server--client-id)

-   Traducción`Web Client ID`y`Server Client ID`Di`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   Traducción`Web Client ID`el`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **Androide**Identificación del cliente

    -   Abra una terminal, navegue hasta el directorio del proyecto de la aplicación

    -   Luego navega a la carpeta de Android.

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   Ejecute el siguiente comando

        -   Para Linux y MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   Para ventanas

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   :advertencia: Reemplazar`<path-to-project>`con la ruta del directorio del proyecto de la aplicación.
            Ejemplo:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   Se le pedirá que ingrese una contraseña, por ejemplo`backtix`

    -   Abrir archivos`android/app/build.gradle`luego cambia esta parte:
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

    -   Abra la terminal, navegue a la carpeta`android`en el proyecto de la aplicación, luego ejecute el siguiente comando:

        ```bash
        ./gradlew signingReport
        ```

    -   Buscar y copiar valores`SHA1`de`variant: debug`el más alto.

        ![Terminal](/assets/Screenshot_5.png)

    -   Ir a[Consola de Google Cloud](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   Seleccionar`Credentials`en la barra lateral izquierda, haga clic`CREATE CREDENTIALS`, seleccionar`OAuth client ID`

    -   Seleccionar`Android`tipo de aplicacion

    -   Ponle un nombre y`Package name`. El nombre del paquete se puede conocer a partir del archivo.`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   Si desea cambiar el nombre del paquete, puede utilizar[cambiar_nombre_paquete_aplicación](https://pub.dev/packages/change_app_package_name)

-   Ingresar`SHA1`desde el paso anterior, luego guardar/crear
