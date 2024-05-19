## Ứng dụng di động (Flutter)

-   [tiếng Indonesia](mobile-app.md)
-   [Tiếng Anh](mobile-app.en.md)

### yêu cầu hệ thống

Đảm bảo hệ thống của bạn đáp ứng các yêu cầu sau trước khi bắt đầu cài đặt:

-   Flutter SDK v3.16 trở lên

### Các bước cài đặt

1.  Sao chép/trích xuất kho lưu trữ

2.  Cài đặt phụ thuộc:

```bash
flutter pub get
```

3.  Chạy`build_runner`để tạo tập tin`*.g.dart`

```bash
dart run build_runner build
```

#### Môi trường thiết lập

1.  Đổi tên`.env.example`ĐẾN`.env`

2.  Tùy chỉnh`API_BASE_URL`của các tập tin`.env`

#### Khóa máy khách Midtrans

-   Hoàn thành bước trước đó trong[Dịch vụ back-end - Setup midtrans server & client key](api-service.md#setup-midtrans-server--client-key)

-   Dịch**khóa khách hàng**tôi đã cho`.env`

```sh
# for debug / sandbox
MIDTRANS_CLIENT_KEY_SANDBOX=SB-Mid-client-xxxx
# for release / production
MIDTRANS_CLIENT_KEY=Mid-client-xxxx
```

#### Cài đặt**Đăng nhập Google**ID khách hàng

-   Hoàn thành bước trước đó trong[Dịch vụ back-end - Thiết lập ID máy chủ và máy khách đăng nhập Google](api-service.md#setup-google-sign-in-server--client-id)

-   Dịch`Web Client ID`Và`Server Client ID`tôi đã cho`.env`

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

-   **Android**ID khách hàng

    -   Mở terminal, điều hướng đến thư mục dự án ứng dụng

    -   Sau đó điều hướng đến thư mục android

        ```bash
        cd <path-to-project>
        cd android
        ```

    -   Chạy lệnh sau

        -   Dành cho Linux và MacOS

        ```bash
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks -keyalg RSA -keysize 2048 -validity 10000 -alias keyalias

        ```

        -   Cho cửa sổ

        ```powershell
        keytool -genkey -v -keystore <path-to-project>/android/app/androidkey.jks ^
        -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
        -alias upload
        ```

        -   :warning: Thay thế`<path-to-project>`với đường dẫn thư mục dự án ứng dụng.
            Ví dụ:

        ```bash
        # linux
        ~/ngoding/PROJECTS/backtix/backtix_app/android/app/androidkey.jks
        # windows
        D:/ngoding/flutter/backtix-app/android/app/androidkey.jks
        ```

        -   Bạn sẽ được yêu cầu nhập mật khẩu, ví dụ`backtix`

    -   Mở tập tin`android/app/build.gradle`sau đó thay đổi phần này:
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

    -   Mở terminal, điều hướng đến thư mục`android`trong dự án ứng dụng, sau đó chạy lệnh sau:

        ```bash
        ./gradlew signingReport
        ```

    -   Tìm kiếm và sao chép giá trị`SHA1`từ`variant: debug`cao nhất.

        ![Terminal](/assets/Screenshot_5.png)

    -   Đi đến[Bảng điều khiển đám mây của Google](https://console.cloud.google.com)

        ![Cloud Console](/assets/Screenshot_2.png)

    -   Lựa chọn`Credentials`ở thanh bên trái, hãy nhấp vào`CREATE CREDENTIALS`, lựa chọn`OAuth client ID`

    -   Lựa chọn`Android`loại ứng dụng

    -   Đặt tên cho nó và`Package name`. tên gói có thể được biết từ tập tin`android/app/build.gradle`

        ```gradle
        android {
            namespace "com.example.backtix_app"
            compileSdkVersion 34
            ndkVersion flutter.ndkVersion
            ...
        }
        ```

        ![Cloud Console](/assets/Screenshot_6.png)


-   Nếu bạn muốn thay đổi tên gói, bạn có thể sử dụng[thay đổi_app_package_name](https://pub.dev/packages/change_app_package_name)

-   Đi vào`SHA1`từ bước trước, sau đó lưu/tạo
