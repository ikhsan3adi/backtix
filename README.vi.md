# Quay lạiTix

> Ứng dụng bán vé và sự kiện mã nguồn mở

<img src="assets/social_preview.png">

<a href="./README.md">
  <img alt="Translation" src="https://img.shields.io/badge/Bahasa_Indonesia-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.en.md">
  <img alt="Translation" src="https://img.shields.io/badge/English-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.zh-CN.md">
  <img alt="Translation" src="https://img.shields.io/badge/简体中文-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.ja.md">
  <img alt="Translation" src="https://img.shields.io/badge/日本語-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.ar.md">
  <img alt="Translation" src="https://img.shields.io/badge/Arabic_عربي-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.pt.md">
  <img alt="Translation" src="https://img.shields.io/badge/Português-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.es.md">
  <img alt="Translation" src="https://img.shields.io/badge/Español-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.fr.md">
  <img alt="Translation" src="https://img.shields.io/badge/Français-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.vi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Tiếng_Việt-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

* * *

Ứng dụng tạo sự kiện và bán vé trực tuyến này là một nền tảng giúp người dùng dễ dàng truy cập và tham gia vào các sự kiện khác nhau. Sau đây là mô tả
Tóm tắt các tính năng chính của ứng dụng:

-   Xác thực:

    Ứng dụng cung cấp xác thực an toàn thông qua JSON Web Token (JWT) và Đăng nhập bằng Google. Người dùng có thể dễ dàng đăng nhập vào tài khoản của mình bằng các phương thức xác thực thuận tiện và an toàn.

-   Kích hoạt tài khoản qua Email:

    Để tăng tính bảo mật và đảm bảo tính xác thực của người dùng, ứng dụng yêu cầu kích hoạt tài khoản qua email. Người dùng sẽ nhận được mã kích hoạt để xác nhận và kích hoạt tài khoản của mình.

-   Tìm kiếm sự kiện lân cận:

    Người dùng có thể tìm kiếm các sự kiện diễn ra gần vị trí của họ nhất. Tính năng này cho phép người dùng khám phá và tham gia vào các sự kiện được tổ chức xung quanh họ.

-   Mua vé với Midtrans:

    Ứng dụng này cung cấp dịch vụ bán vé trực tuyến sử dụng cổng thanh toán Midtrans. Người dùng có thể dễ dàng mua vé cho các sự kiện quan tâm với nhiều tùy chọn thanh toán thuận tiện.

-   Tạo sự kiện với sự phê duyệt của quản trị viên:

    Người dùng muốn tổ chức sự kiện có thể tạo chúng thông qua ứng dụng. Tuy nhiên, sự kiện sẽ được công bố sau khi nhận được sự chấp thuận của quản trị viên. Điều này nhằm đảm bảo chất lượng và mức độ phù hợp của các sự kiện được hiển thị trên nền tảng.

-   Quét mã QR để tạo sự kiện:

    Tính năng này cho phép người tạo sự kiện dễ dàng xác minh sự tham dự của khách truy cập bằng cách quét mã QR trên vé. Điều này giúp quản lý sự kiện hiệu quả và xác nhận vé.

-   Rút số dư và thu nhập:

    Người tạo sự kiện có thể rút số dư và thu nhập của mình thông qua tính năng rút tiền do ứng dụng cung cấp. Điều này mang lại cho người tổ chức sự kiện sự linh hoạt để quản lý kết quả tài chính của họ một cách dễ dàng.

-   Thông báo theo thời gian thực

    Với sự giúp đỡ của_dịch vụ nền_(Android & iOS), người dùng sẽ nhận được thông báo theo thời gian thực về trạng thái sự kiện, trạng thái rút tiền, mua và bán vé.

## ngăn xếp công nghệ

-   Dịch vụ API/back-end

    -   [NestJS 10](https://nestjs.com/)Bản đánh máy
    -   ORM Prisma
    -   PostgreSQL
    -   làm lại
    -   Swagger(tài liệu API)

-   Web bảng quản trị (Monorepo với dịch vụ API)

    -   [Mảnh dẻKit 2](https://kit.svelte.dev/)Bản đánh máy
    -   Thành phần giao diện người dùng Flowbite
    -   CSS theo gió

-   Ứng dụng di động

    -   [Rung 3](https://flutter.dev/)
        -   BLoC
        -   đông lạnh
        -   Trang bị thêm
        -   fpdart

## Mã nguồn

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

## Cài đặt &_Cách chạy_

[Dịch vụ API phụ trợ](docs/api-service.md)

[Bảng quản trị](docs/admin-panel.md)

[Ứng dụng di động](docs/mobile-app.md)
