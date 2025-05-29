## 移动应用程序（颤音）

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

### 系统要求

在开始安装之前，请确保您的系统满足以下要求：

-   flutter SDK v3.16或更高

### 安装步骤

1.  克隆/提取库

2.  安装依赖项：

```bash
flutter pub get
```

3.  跑步`build_runner`生成文件`*.g.dart`

```bash
dart run build_runner build
```

#### 设置环境

1.  重命名`.env.example`到`.env`

2.  调整`API_BASE_URL`文件`.env`

#### 中线客户键

-   完成上一步[后端服务 - 设置中型服务器和客户端密钥](api-service.md#setup-midtrans-server--client-key)

-   翻译**客户端密钥**文件`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### 设置**Google登录**客户ID

-   完成上一步[后端服务 - 设置Google在服务器和客户端ID中](api-service.md#setup-google-sign-in-server--client-id)

-   翻译`Web Client ID`和`Server Client ID`文件`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   翻译`Web Client ID`这`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **安卓**客户ID

    -   打开终端，导航到应用程序项目目录

    -   然后托管到Android文件夹

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   运行以下命令

        -   对于Linux和MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   对于Windows

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   ：警告：更改`<path-to-project>`使用应用程序项目的应用程序目录。
            例子：

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   您将被要求输入密码，示例`backtix`

    -   打开文件`android/app/build.gradle`然后更改此部分：
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

    -   打开终端，指向文件夹`android`在应用程序项目中，然后运行以下命令：

        ```bash
        ./gradlew signingReport
        ```

    -   搜索和复制值`SHA1`从`variant: debug`最高。

        ![Terminal](/assets/Screenshot_5.png)

    -   去[Google Cloud Console](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   选择`Credentials`在左侧栏上，单击`CREATE CREDENTIALS`， 选择`OAuth client ID`

    -   选择`Android`申请类型

    -   名称，和`Package name`。包装名称可以从文件中看到`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   如果要更改包装名称，则可以使用[change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   进入`SHA1`从上一步，然后保存/创建
