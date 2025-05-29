# Backtix

> Sự kiện nguồn mở và ứng dụng bán vé

<img src="assets/social_preview.png" alt="BackTix">

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
<a href="./README.hi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Hindi_हिंदी-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

* * *

## Mã nguồn

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

* * *

> [!QUAN TRỌNG]
>
> ## Cài đặt &_Làm thế nào để chạy_
>
> [Dịch vụ API back-end](docs/api-service.md)
>
> [Quản trị viên](docs/admin-panel.md)
>
> [Ứng dụng di động](docs/mobile-app.md)
>
> * * *
>
> [!GHI CHÚ]
>
> ## Tech Stack
>
> -   Dịch vụ API / Back-End
>
>     -   [Không 10](https://nestjs.com/)TYPEXTRIPT
>     -   Prisma Orm
>     -   Postgresql
>     -   Redis
>     -   Swagger (tài liệu API)
>
> -   Web bảng quản trị (monorepo với dịch vụ API)
>
>     -   [Svelteki 2](https://kit.svelte.dev/)TYPEXTRIPT
>     -   Thành phần UI Flowbite
>     -   Tailwind CSS
>
> -   Ứng dụng di động
>
>     -   [Rung 3](https://flutter.dev/)
>         -   Khối
>         -   Đóng băng
>         -   Trang bị thêm
>         -   fpdart

* * *

Ứng dụng để tạo ra các sự kiện và bán vé trực tuyến là một nền tảng cung cấp sự tiện lợi cho người dùng truy cập và tham gia vào các sự kiện khác nhau. Đây là một mô tả
Các tính năng ứng dụng chính ngắn:

-   Xác thực:

    Ứng dụng này cung cấp xác thực an toàn thông qua mã thông báo JSON Web (JWT) và Google Đăng nhập. Người dùng có thể dễ dàng nhập tài khoản của họ bằng phương pháp xác thực thoải mái và an toàn.

-   Kích hoạt tài khoản qua email:

    Để tăng bảo mật và đảm bảo tính xác thực của người dùng, ứng dụng yêu cầu kích hoạt tài khoản qua email. Người dùng sẽ nhận được mã kích hoạt để xác nhận và kích hoạt tài khoản của họ.

-   Tìm kiếm sự kiện gần nhất:

    Người dùng có thể tìm thấy các sự kiện diễn ra gần nhất với vị trí của họ. Tính năng này cho phép người dùng tìm và tham gia vào các sự kiện được tổ chức xung quanh họ.

-   Mua vé với midtrans:

    Ứng dụng này cung cấp dịch vụ bán vé trực tuyến sử dụng cổng thanh toán Midtrans. Người dùng có thể dễ dàng mua vé cho các sự kiện đang có nhu cầu với nhiều tùy chọn thanh toán thoải mái.

-   Tạo một sự kiện với sự chấp thuận của quản trị viên:

    Người dùng muốn tổ chức một sự kiện có thể thông qua ứng dụng. Tuy nhiên, sự kiện này sẽ được công bố sau khi nhận được sự chấp thuận từ quản trị viên. Điều này là để đảm bảo chất lượng và mức độ phù hợp của sự kiện được hiển thị trên nền tảng.

-   Quét mã QR cho nhà sản xuất sự kiện:

    Tính năng này cho phép nhà sản xuất sự kiện dễ dàng xác minh sự hiện diện của khách truy cập bằng cách quét mã QR trên vé. Điều này giúp quản lý sự kiện và xác nhận vé một cách hiệu quả.

-   Rút số dư và thu nhập:

    Nhà sản xuất sự kiện có thể thu hút số dư và thu nhập của họ thông qua các tính năng rút tiền do ứng dụng cung cấp. Điều này cung cấp sự linh hoạt cho người tổ chức sự kiện để quản lý kết quả tài chính của họ một cách dễ dàng.

-   Thông báo thời gian thực

    Với sự giúp đỡ của_dịch vụ nền_(Android & iOS), người dùng sẽ nhận được thông báo thời gian thực về tình trạng của sự kiện, tình trạng rút tiền, mua và bán vé.

## Hỗ trợ và quyên góp

[![Donate paypal](https://img.shields.io/badge/Donate-PayPal-green.svg?style=for-the-badge)](https://paypal.me/ikhsan3adi?country.x=ID&locale.x=en_US)[![Donate saweria](https://img.shields.io/badge/Donate-Saweria-red?style=for-the-badge&link=https%3A%2F%2Fsaweria.co%2Fxiboxann)](https://saweria.co/xiboxann)
