## تطبيق الهاتف المحمول (رفرفة)

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

### متطلبات النظام

تأكد من أن نظامك يفي بالمتطلبات التالية قبل بدء التثبيت:

-   رفرفة SDK v3.16 أو أعلى

### خطوات التثبيت

1.  استنساخ/مستخلص مستودع

2.  تثبيت التبعيات:

```bash
flutter pub get
```

3.  يجري`build_runner`لإنشاء الملفات`*.g.dart`

```bash
dart run build_runner build
```

#### بيئة الإعداد

1.  إعادة تسمية`.env.example`ل`.env`

2.  يُعدِّل`API_BASE_URL`ملف`.env`

#### مفتاح العميل Midtrans

-   أكمل الخطوة السابقة في[الخدمة الخلفية - إعداد Midtrans Server & Client Key](api-service.md#setup-midtrans-server--client-key)

-   ترجمة**مفتاح العميل**ملف`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### يثبت**تسجيل الدخول جوجل**معرف العميل

-   أكمل الخطوة السابقة في[الخدمة الخلفية - إعداد خادم تسجيل الدخول إلى Google ومعرف العميل](api-service.md#setup-google-sign-in-server--client-id)

-   ترجمة`Web Client ID`و`Server Client ID`ملف`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   ترجمة`Web Client ID`ال`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **Android**معرف العميل

    -   افتح الجهاز ، انتقل إلى دليل مشروع التطبيق

    -   ثم استضافة مجلد Android

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   قم بتشغيل الأوامر التالية

        -   لـ Linux و MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   لنظام التشغيل Windows

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   : تحذير: التغيير`<path-to-project>`مع دليل التطبيق لمشروع التطبيق.
            مثال:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   سيُطلب منك إدخال كلمة مرور ، مثال`backtix`

    -   افتح الملف`android/app/build.gradle`ثم قم بتغيير هذا القسم:
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

    -   افتح الجهاز ، أشر إلى المجلد`android`في مشروع التطبيق ، ثم قم بتشغيل الأمر التالي:

        ```bash
        ./gradlew signingReport
        ```

    -   بحث ونسخ القيمة`SHA1`من`variant: debug`الأعلى.

        ![Terminal](/assets/Screenshot_5.png)

    -   اذهب إلى[وحدة التحكم السحابية Google](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   يختار`Credentials`على الشريط الجانبي الأيسر ، انقر`CREATE CREDENTIALS`، يختار`OAuth client ID`

    -   يختار`Android`نوع التطبيق

    -   الاسم ، و`Package name`. يمكن رؤية اسم الحزمة من الملف`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   إذا كنت تريد تغيير اسم الحزمة الذي يمكنك استخدامه[Change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   يدخل`SHA1`من الخطوة السابقة ، ثم حفظ/إنشاء
