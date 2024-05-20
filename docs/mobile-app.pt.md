## Aplicativo móvel (Flutter)

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

### Requisitos de sistema

Certifique-se de que seu sistema atenda aos seguintes requisitos antes de iniciar a instalação:

-   Flutter SDK v3.16 ou superior

### Etapas de instalação

1.  Clonar/extrair repositório

2.  Instale dependências:

```bash
flutter pub get
```

3.  Correr`build_runner`para gerar arquivos`*.g.dart`

```bash
dart run build_runner build
```

#### Ambiente de configuração

1.  Renomear`.env.example`para`.env`

2.  Customizar`API_BASE_URL`de arquivos`.env`

#### Chave do cliente Midtrans

-   Conclua a etapa anterior em[Serviço de back-end - Configuração do servidor midtrans e chave do cliente](api-service.md#setup-midtrans-server--client-key)

-   Tradução**chave do cliente**Eu dei`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### Configurar**Login do Google**ID do Cliente

-   Conclua a etapa anterior em[Serviço de back-end - Configure o servidor de login do Google e o ID do cliente](api-service.md#setup-google-sign-in-server--client-id)

-   Tradução`Web Client ID`e`Server Client ID`Eu dei`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   Tradução`Web Client ID`o`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **Android**ID do Cliente

    -   Abra um terminal, navegue até o diretório do projeto do aplicativo

    -   Em seguida, navegue até a pasta Android

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   Execute o seguinte comando

        -   Para Linux e MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   Para Windows

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   : aviso: Substitua`<path-to-project>`com o caminho do diretório do projeto do aplicativo.
            Exemplo:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   Você será solicitado a inserir uma senha, por exemplo`backtix`

    -   Abrir arquivos`android/app/build.gradle`então altere esta parte:
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

    -   Abra o terminal, navegue até a pasta`android`no projeto do aplicativo e execute o seguinte comando:

        ```bash
        ./gradlew signingReport
        ```

    -   Pesquisar e copiar valores`SHA1`de`variant: debug`o mais alto.

        ![Terminal](/assets/Screenshot_5.png)

    -   Vá para[Console do Google Cloud](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   Selecione`Credentials`na barra lateral esquerda, clique em`CREATE CREDENTIALS`, selecione`OAuth client ID`

    -   Selecione`Android`tipo de aplicação

    -   Dê um nome a ele e`Package name`. o nome do pacote pode ser conhecido a partir do arquivo`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   Se você quiser alterar o nome do pacote, você pode usar[change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   Digitar`SHA1`da etapa anterior e salve/crie
