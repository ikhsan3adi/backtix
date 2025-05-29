## Ứng dụng di động (Flutter)

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

### Yêu cầu hệ thống

Đảm bảo hệ thống của bạn đáp ứng các yêu cầu sau khi bắt đầu cài đặt:

-   Flutter SDK v3.16 trở lên

### Các bước cài đặt

1.  Bản sao/Trích xuất kho lưu trữ

2.  Cài đặt phụ thuộc:

```bash
flutter pub get
```

3.  Chạy`build_runner`Để tạo tập tin`*.g.dart`

```bash
dart run build_runner build
```

#### Môi trường thiết lập

1.  Đổi tên`.env.example`ĐẾN`.env`

2.  Điều chỉnh`API_BASE_URL`tài liệu`.env`

#### Khóa máy khách Midtrans

-   Hoàn thành bước trước tại[Dịch vụ back -end - Thiết lập khóa máy chủ & máy chủ Midtrans](api-service.md#setup-midtrans-server--client-key)

-   Dịch**Khóa máy khách**Tệp của`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### Cài đặt**Google đăng nhập**ID máy khách

-   Hoàn thành bước trước tại[Dịch vụ back -end - Thiết lập Google Đăng nhập vào máy chủ & ID máy khách](api-service.md#setup-google-sign-in-server--client-id)

-   Dịch`Web Client ID`Và`Server Client ID`Tệp của`.env`

```sh
# frontend google signin / web client id
GOOGLE_CLIENT_ID=xxxx.apps.googleusercontent.com
# backend / server client id
GOOGLE_SERVER_CLIENT_ID=xxxx.apps.googleusercontent.com
```

-   Dịch`Web Client ID`các`android/app/src/main/res/values/strings.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
  <string name="default_web_client_id">YOUR_CLIENT_ID</string> 
</resources>
```

-   **Android**ID máy khách

    -   Mở thiết bị đầu cuối, điều hướng đến thư mục dự án ứng dụng

    -   Sau đó lưu trữ vào thư mục Android

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   Chạy các lệnh sau

        -   Đối với Linux và MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   Cho Windows

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   : CẢNH BÁO: Thay đổi`<path-to-project>`với thư mục ứng dụng của dự án ứng dụng.
            Ví dụ:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   Bạn sẽ được yêu cầu nhập mật khẩu, ví dụ`backtix`

    -   Mở tệp`android/app/build.gradle`Sau đó thay đổi phần này:
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

    -   Mở thiết bị đầu cuối, chỉ vào thư mục`android`Trong dự án ứng dụng, sau đó chạy lệnh sau:

        ```bash
        ./gradlew signingReport
        ```

    -   Tìm kiếm và sao chép giá trị`SHA1`từ`variant: debug`cao nhất.

        ![Terminal](/assets/Screenshot_5.png)

    -   Đi đến[Bảng điều khiển đám mây Google](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   Chọn`Credentials`Ở thanh bên trái, nhấp vào`CREATE CREDENTIALS`, chọn`OAuth client ID`

    -   Chọn`Android`loại ứng dụng

    -   Tên, và`Package name`. Tên gói có thể được nhìn thấy từ tệp`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   Nếu bạn muốn thay đổi tên gói bạn có thể sử dụng[thay đổi_app_package_name](https://pub.dev/packages/change_app_package_name)

-   Đi vào`SHA1`Từ bước trước, sau đó lưu/tạo
