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

Bao gồm bảng ứng dụng quản trị viên trong đó

    apps/api
    apps/admin-panel

### Yêu cầu hệ thống

Đảm bảo hệ thống của bạn đáp ứng các yêu cầu sau khi bắt đầu cài đặt:

-   Node.js v18 trở lên
-   PostgreSql 15 trở lên
-   Redis v5 trở lên

### Các bước cài đặt

1.  Bản sao/Trích xuất kho lưu trữ

2.  Cài đặt phụ thuộc:

```bash
npm i
```

#### Môi trường thiết lập

-   Đổi tên`.env.example`ĐẾN`.env`

#### Cơ sở dữ liệu thiết lập

-   Bộ`DATABASE_URL`Của`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Chạy di chuyển để thực hiện bảng cần thiết

```bash
npx prisma migrate deploy
```

-   Chạy bộ gieo hạt cơ sở dữ liệu để tạo người dùng`superadmin`

```bash
npm run db:seed
```

#### Cài đặt**Google đăng nhập**ID máy chủ & khách hàng

-   Tạo một dự án mới tại[Bảng điều khiển đám mây Google](https://console.cloud.google.com/projectcreate)

-   Sau khi hoàn thành thực hiện dự án, chọn`APIs & Services`, sau đó chọn`OAuth consent screen`bên trái

-   Nhập tên của ứng dụng, email và`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Máy chủ**ID máy khách

    -   Chọn`Credentials`Ở thanh bên trái, nhấp vào`CREATE CREDENTIALS`, chọn`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Chọn`Web application`loại ứng dụng, beri nama lalu lưu/tạo

    ![Cloud Console](/assets/Screenshot_3.png)

-   Dịch`Client ID`Và`Client secret`Tệp của`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Ứng dụng web**ID máy khách

    -   `CREATE CREDENTIALS`Quay lại, chọn`OAuth client ID`

    -   Chọn`Web application`Loại ứng dụng, tên và`Authorized JavaScript origins`Giống như trong hình (nếu sử dụng localhost), sau đó lưu/tạo

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Dịch`Client ID`Và`Client secret`Tệp của`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Nhấp`DOWNLOAD JSON`và lưu id máy khách. ID máy khách web sẽ được sử dụng trong Flutter ứng dụng di động.

#### Thiết lập khóa máy chủ & máy chủ Midtrans

-   Đi đến[Bảng điều khiển midtrans](https://dashboard.midtrans.com/), chọn môi trường`sandbox`(đề nghị) hoặc`production`
-   Đi vào`Settings`>`Access Keys`, sau đó sao chép khóa máy khách và máy chủ vào tệp`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   Cấu hình biến`.env`những người khác khi cần thiết.

### Làm thế nào để chạy

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

2.  DOCS API Swagger

-   Mở http&#x3A; // localhost: 3000/fire/Docs (điều chỉnh URL cơ sở)

3.  Kiểm tra (tùy chọn)

```bash
npm test
```

### Ảnh chụp màn hình

![Swagger API Docs](/assets/swagger.png)
