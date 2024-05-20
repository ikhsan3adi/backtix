## मोबाइल ऐप (स्पंदन)

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

### सिस्टम आवश्यकताएं

इंस्टॉलेशन शुरू करने से पहले सुनिश्चित करें कि आपका सिस्टम निम्नलिखित आवश्यकताओं को पूरा करता है:

-   स्पंदन SDK v3.16 या उच्चतर

### स्थापना चरण

1.  क्लोन/एक्सट्रेक्ट रिपॉजिटरी

2.  निर्भरताएँ स्थापित करें:

```bash
flutter pub get
```

3.  दौड़ना`build_runner`फ़ाइलें उत्पन्न करने के लिए`*.g.dart`

```bash
dart run build_runner build
```

#### सेटअप वातावरण

1.  नाम बदलें`.env.example`को`.env`

2.  अनुकूलित करें`API_BASE_URL`फ़ाइलों का`.env`

#### मिडट्रांस क्लाइंट कुंजी

-   पिछले चरण को पूरा करें[बैक-एंड सेवा - सेटअप मिडट्रांस सर्वर और क्लाइंट कुंजी](api-service.md#setup-midtrans-server--client-key)

-   अनुवाद**ग्राहक कुंजी**के फाइल`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### स्थापित करना**गूगल साइन इन करें**ग्राहक ID

-   पिछले चरण को पूरा करें[बैक-एंड सेवा - Google साइन इन सर्वर और क्लाइंट आईडी सेटअप करें](api-service.md#setup-google-sign-in-server--client-id)

-   अनुवाद`Web Client ID`और`Server Client ID`के फाइल`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   अनुवाद`Web Client ID`के`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **एंड्रॉयड**ग्राहक ID

    -   एक टर्मिनल खोलें, एप्लिकेशन प्रोजेक्ट निर्देशिका पर नेविगेट करें

    -   फिर एंड्रॉइड फ़ोल्डर में नेविगेट करें

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   निम्न आदेश चलाएँ

        -   Linux और MacOS के लिए

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   विंडोज के लिए

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   :चेतावनी: बदलें`<path-to-project>`एप्लिकेशन प्रोजेक्ट निर्देशिका पथ के साथ।
            उदाहरण:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   उदाहरण के लिए, आपसे पासवर्ड दर्ज करने के लिए कहा जाएगा`backtix`

    -   खुली फ़ाइलें`android/app/build.gradle`फिर इस भाग को बदलें:
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

    -   टर्मिनल खोलें, फ़ोल्डर पर जाएँ`android`एप्लिकेशन प्रोजेक्ट में, फिर निम्न कमांड चलाएँ:

        ```bash
        ./gradlew signingReport
        ```

    -   मान खोजें और कॉपी करें`SHA1`से`variant: debug`उच्चतम।

        ![Terminal](/assets/Screenshot_5.png)

    -   जाओ[गूगल क्लाउड कंसोल](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   चुनना`Credentials`बाएँ साइडबार में, क्लिक करें`CREATE CREDENTIALS`, चुनना`OAuth client ID`

    -   चुनना`Android`आवेदन का प्रकार

    -   इसे एक नाम दें, और`Package name`. पैकेज का नाम फ़ाइल से जाना जा सकता है`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   यदि आप पैकेज का नाम बदलना चाहते हैं, तो आप इसका उपयोग कर सकते हैं[Change_app_package_name](https://pub.dev/packages/change_app_package_name)

-   प्रवेश करना`SHA1`पिछले चरण से, फिर सहेजें/बनाएं
