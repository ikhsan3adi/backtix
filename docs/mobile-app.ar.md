## تطبيق الهاتف المحمول (Flutter)

-   [الاندونيسية](mobile-app.md)
-   [إنجليزي](mobile-app.en.md)

### متطلبات النظام

تأكد من أن نظامك يلبي المتطلبات التالية قبل بدء التثبيت:

-   Flutter SDK v3.16 أو أعلى

### خطوات التثبيت

1.  استنساخ/استخراج المستودع

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

2.  يعدل أو يكيف`API_BASE_URL`من الملفات`.env`

#### مفتاح عميل Midtrans

-   أكمل الخطوة السابقة في[الخدمة الخلفية - إعداد خادم midtrans ومفتاح العميل](api-service.md#setup-midtrans-server--client-key)

-   ترجمة**مفتاح العميل**أعطيت`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### يثبت**تسجيل الدخول جوجل**معرف العميل

-   أكمل الخطوة السابقة في[الخدمة الخلفية - إعداد خادم تسجيل الدخول إلى Google ومعرف العميل](api-service.md#setup-google-sign-in-server--client-id)

-   ترجمة`Web Client ID`و`Server Client ID`أعطيت`.env`

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

-   **ذكري المظهر**معرف العميل

    -   افتح محطة، وانتقل إلى دليل مشروع التطبيق

    -   ثم انتقل إلى مجلد android

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   قم بتشغيل الأمر التالي

        -   لنظام التشغيل Linux و MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   للنوافذ

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   :تحذير: استبدال`<path-to-project>`مع مسار دليل مشروع التطبيق.
            مثال:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   سيُطلب منك إدخال كلمة مرور، على سبيل المثال`backtix`

    -   الملفات المفتوحة`android/app/build.gradle`ثم قم بتغيير هذا الجزء:
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

    -   افتح المحطة، انتقل إلى المجلد`android`في مشروع التطبيق، ثم قم بتشغيل الأمر التالي:

        ```bash
        ./gradlew signingReport
        ```

    -   بحث ونسخ القيم`SHA1`من`variant: debug`الاعلى.

        ![Terminal](/assets/Screenshot_5.png)

    -   اذهب إلى[جوجل السحابية وحدة التحكم](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   يختار`Credentials`في الشريط الجانبي الأيسر، انقر فوق`CREATE CREDENTIALS`، يختار`OAuth client ID`

    -   يختار`Android`نوع التطبيق

    -   أعطها اسما، و`Package name`. يمكن معرفة اسم الحزمة من الملف`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   إذا كنت تريد تغيير اسم الحزمة، يمكنك استخدام[Change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   يدخل`SHA1`من الخطوة السابقة ثم حفظ/إنشاء
