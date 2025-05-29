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

सुनिश्चित करें कि आपका सिस्टम इंस्टॉलेशन शुरू करने से पहले निम्नलिखित आवश्यकताओं को पूरा करता है:

-   SDK V3.16 या उच्चतर स्पंदन

### स्थापना चरण

1.  क्लोन/एक्सट्रैक्ट रिपॉजिटरी

2.  निर्भरता स्थापित करें:

```bash
flutter pub get
```

3.  दौड़ना`build_runner`फ़ाइलों को उत्पन्न करने के लिए`*.g.dart`

```bash
dart run build_runner build
```

#### सेटअप वातावरण

1.  नाम बदलें`.env.example`को`.env`

2.  समायोजित करना`API_BASE_URL`फ़ाइल`.env`

#### Midtrans ग्राहक कुंजी

-   पिछले चरण को पूरा करें[बैक -एंड सर्विस - सेटअप मिडट्रांस सर्वर और क्लाइंट कुंजी](api-service.md#setup-midtrans-server--client-key)

-   अनुवाद**ग्राहक कुंजी**ke file`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### स्थापित करना**Google में साइन इन करें**ग्राहक आईडी

-   पिछले चरण को पूरा करें[बैक -एंड सर्विस - सर्वर और क्लाइंट आईडी में Google साइन सेट करें](api-service.md#setup-google-sign-in-server--client-id)

-   अनुवाद`Web Client ID`और`Server Client ID`ke file`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   अनुवाद`Web Client ID`ke`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **एंड्रॉइड**ग्राहक आईडी

    -   टर्मिनल खोलें, एप्लिकेशन प्रोजेक्ट डायरेक्टरी में नेविगेट करें

    -   फिर Android फ़ोल्डर की मेजबानी करें

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   निम्नलिखित कमांड चलाएं

        -   लिनक्स और मैकओएस के लिए

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   विंडोज के लिए

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   : चेतावनी: परिवर्तन`<path-to-project>`एप्लिकेशन प्रोजेक्ट के एप्लिकेशन डायरेक्टरी के साथ।
            उदाहरण:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   आपको एक पासवर्ड दर्ज करने के लिए कहा जाएगा, उदाहरण`backtix`

    -   फ़ाइल खोलें`android/app/build.gradle`फिर इस खंड को बदलें:
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

    -   टर्मिनल खोलें, फ़ोल्डर की ओर इशारा करें`android`एप्लिकेशन प्रोजेक्ट में, फिर निम्न कमांड चलाएं:

        ```bash
        ./gradlew signingReport
        ```

    -   खोज और प्रतिलिपि मूल्य`SHA1`से`variant: debug`उच्चतम।

        ![Terminal](/assets/Screenshot_5.png)

    -   जाओ[Google Cloud Console](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   चुनना`Credentials`बाईं साइडबार पर, क्लिक करें`CREATE CREDENTIALS`, चुनना`OAuth client ID`

    -   चुनना`Android`अनुप्रयोग प्रकार

    -   नाम, और`Package name`। पैकेज का नाम फ़ाइल से देखा जा सकता है`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   यदि आप पैकेज नाम बदलना चाहते हैं तो आप उपयोग कर सकते हैं[CHANGE_APP_PACKAGE_NAME](https://pub.dev/packages/change_app_package_name)

-   प्रवेश करना`SHA1`पिछले चरण से, फिर सहेजें/बनाएं
