## 移动应用程序（颤振）

-   [印度尼西亚](mobile-app.md)
-   [英语](mobile-app.en.md)

### 系统要求

开始安装之前，请确保您的系统满足以下要求：

-   Flutter SDK v3.16 或更高版本

### 安装步骤

1.  克隆/提取存储库

2.  安装依赖项：

```bash
flutter pub get
```

3.  跑步`build_runner`生成文件`*.g.dart`

```bash
dart run build_runner build
```

#### 设置环境

1.  改名`.env.example`到`.env`

2.  定制`API_BASE_URL`文件数`.env`

#### 中转客户端密钥

-   完成上一步[后端服务 - 设置 midtrans 服务器和客户端密钥](api-service.md#setup-midtrans-server--client-key)

-   翻译**客户端密钥**我给了`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### 设置**谷歌登录**客户ID

-   完成上一步[后端服务 - 设置 Google 登录服务器和客户端 ID](api-service.md#setup-google-sign-in-server--client-id)

-   翻译`Web Client ID`和`Server Client ID`我给了`.env`

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

    -   然后导航到 android 文件夹

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   运行以下命令

        -   适用于 Linux 和 MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   对于窗户

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   ：警告：更换`<path-to-project>`与应用程序项目目录路径。
            例子：

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   系统会要求您输入密码，例如`backtix`

    -   打开文件`android/app/build.gradle`然后更改这部分：
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

    -   打开终端，导航到文件夹`android`在应用程序项目中，然后运行以下命令：

        ```bash
        ./gradlew signingReport
        ```

    -   搜索和复制值`SHA1`从`variant: debug`最高的。

        ![Terminal](/assets/Screenshot_5.png)

    -   去[谷歌云控制台](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   选择`Credentials`在左侧边栏中，单击`CREATE CREDENTIALS`， 选择`OAuth client ID`

    -   选择`Android`应用类型

    -   给它一个名字，然后`Package name`。从文件中可以知道包名`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   如果你想改变包名，你可以使用[更改应用程序包名称](https://pub.dev/packages/change_app_package_name)

-   进入`SHA1`从上一步开始，然后保存/创建
