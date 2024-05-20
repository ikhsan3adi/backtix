## Dịch vụ back-end (NestJS)

<a href="./api-service.md">
  <img alt="Translation" src="https://img.shields.io/badge/Bahasa_Indonesia-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.en.md">
  <img alt="Translation" src="https://img.shields.io/badge/English-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.zh-CN.md">
  <img alt="Translation" src="https://img.shields.io/badge/简体中文-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.ja.md">
  <img alt="Translation" src="https://img.shields.io/badge/日本語-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.ar.md">
  <img alt="Translation" src="https://img.shields.io/badge/Arabic_عربي-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.pt.md">
  <img alt="Translation" src="https://img.shields.io/badge/Português-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.es.md">
  <img alt="Translation" src="https://img.shields.io/badge/Español-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.fr.md">
  <img alt="Translation" src="https://img.shields.io/badge/Français-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.vi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Tiếng_Việt-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.hi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Hindi_हिंदी-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

Nó bao gồm một ứng dụng bảng quản trị

    apps/api
    apps/admin-panel

### yêu cầu hệ thống

Đảm bảo hệ thống của bạn đáp ứng các yêu cầu sau trước khi bắt đầu cài đặt:

-   Node.js v18 trở lên
-   PostgreSQL 15 trở lên
-   Redis v5 trở lên

### Các bước cài đặt

1.  Sao chép/trích xuất kho lưu trữ

2.  Cài đặt phụ thuộc:

```bash
npm i
```

#### Môi trường thiết lập

-   Đổi tên`.env.example`ĐẾN`.env`

#### Thiết lập cơ sở dữ liệu

-   Sắp xếp`DATABASE_URL`Của`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Chạy quá trình di chuyển để tạo các bảng cần thiết

```bash
npx prisma migrate deploy
```

-   Chạy trình gieo hạt cơ sở dữ liệu để tạo người dùng`superadmin`

```bash
npm run db:seed
```

#### Cài đặt**Đăng nhập Google**ID máy chủ và máy khách

-   Tạo một dự án mới tại[Bảng điều khiển đám mây của Google](https://console.cloud.google.com/projectcreate)

-   Khi bạn đã tạo xong một dự án, hãy chọn nó`APIs & Services`, sau đó chọn`OAuth consent screen`ở bên trái

-   Nhập tên ứng dụng, email và`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Máy chủ**ID khách hàng

    -   Lựa chọn`Credentials`ở thanh bên trái, hãy nhấp vào`CREATE CREDENTIALS`, lựa chọn`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Lựa chọn`Web application`loại ứng dụng, lưu/tạo beri nama lalu

    ![Cloud Console](/assets/Screenshot_3.png)

-   Dịch`Client ID`Và`Client secret`tôi đã cho`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Ứng dụng web**ID khách hàng

    -   `CREATE CREDENTIALS`quay lại, chọn`OAuth client ID`

    -   Lựa chọn`Web application`loại ứng dụng, đặt tên và`Authorized JavaScript origins`như trong hình (nếu dùng localhost) thì lưu/tạo

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Dịch`Client ID`Và`Client secret`tôi đã cho`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Nhấp chuột`DOWNLOAD JSON`và lưu ID khách hàng. ID khách hàng web sẽ được sử dụng trong ứng dụng di động rung.

#### Thiết lập khóa máy chủ và máy khách midtrans

-   Đi đến[Bảng điều khiển Midtrans](https://dashboard.midtrans.com/), chọn môi trường`sandbox`(được khuyến nghị) tại`production`
-   Nhập vào`Settings`>`Access Keys`, sau đó sao chép khóa máy khách và máy chủ vào tệp`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   Cấu hình biến`.env`những người khác khi cần thiết.

### Cách chạy

1.  Phát ra`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  Chạy ứng dụng

```bash
npm run start
```

-   Chế độ phát triển

```bash
npm run start:dev
```

2.  Tài liệu API Swagger

-   Mở http&#x3A;//localhost:3000/api/docs (điều chỉnh url cơ sở)

3.  Kiểm tra (tùy chọn)

```bash
npm test
```

### Ảnh chụp màn hình

![Swagger API Docs](/assets/swagger.png)
