## Aplicativo móvel (vibração)

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

### Requisitos do sistema

Verifique se o seu sistema atende aos seguintes requisitos antes de iniciar a instalação:

-   Flutter SDK v3.16 ou superior

### Etapas de instalação

1.  Repositório de clone/extrato

2.  Instale dependências:

```bash
flutter pub get
```

3.  Correr`build_runner`Para gerar arquivos`*.g.dart`

```bash
dart run build_runner build
```

#### Ambiente de configuração

1.  Renomear`.env.example`para`.env`

2.  Ajustar`API_BASE_URL`arquivo`.env`

#### Chave do cliente Midtrans

-   Complete a etapa anterior em[Serviço de back -end - Configurar o servidor Midtrans e a chave do cliente](api-service.md#setup-midtrans-server--client-key)

-   Tradução**chave do cliente**Arquivo de`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### Configurar**Google Entrar**ID do cliente

-   Complete a etapa anterior em[Serviço de back -end - Configurar o Google Sign in Server e Client ID](api-service.md#setup-google-sign-in-server--client-id)

-   Tradução`Web Client ID`E`Server Client ID`Arquivo de`.env`

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

-   **Android**ID do cliente

    -   Abra o terminal, navegue para o diretório do projeto de aplicativo

    -   Em seguida, hospede a pasta Android

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   Execute os seguintes comandos

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

        -   : Aviso: Mudança`<path-to-project>`com o diretório de aplicativos do projeto de aplicativo.
            Exemplo:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   Você será solicitado a inserir uma senha, exemplo`backtix`

    -   Abra o arquivo`android/app/build.gradle`Em seguida, altere esta seção:
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

    -   Abra o terminal, aponte para a pasta`android`No projeto de aplicativo, execute o seguinte comando:

        ```bash
        ./gradlew signingReport
        ```

    -   Pesquisar e copiar valor`SHA1`de`variant: debug`o mais alto.

        ![Terminal](/assets/Screenshot_5.png)

    -   Vá para[Google Cloud Console](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   Escolher`Credentials`Na barra lateral esquerda, clique`CREATE CREDENTIALS`, escolher`OAuth client ID`

    -   Escolher`Android`Tipo de aplicativo

    -   Nome e`Package name`. O nome do pacote pode ser visto no arquivo`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   Se você quiser alterar o nome do pacote, você pode usar[Change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   Digitar`SHA1`A partir da etapa anterior, salve/crie/crie
