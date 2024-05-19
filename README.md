# BackTix

> Open Source Event & Ticketing App

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

---

Aplikasi pembuatan acara dan penjualan tiket online ini merupakan platform yang menyediakan kemudahan bagi pengguna untuk mengakses dan berpartisipasi dalam berbagai acara. Berikut adalah deskripsi
singkat fitur-fitur utama aplikasi:

- Autentikasi:

  Aplikasi ini menawarkan autentikasi yang aman melalui JSON Web Token (JWT) dan Google Sign-In. Pengguna dapat dengan mudah masuk ke akun mereka dengan metode otentikasi yang nyaman dan aman.

- Aktivasi Akun Melalui Email:

  Untuk meningkatkan keamanan dan memastikan keaslian pengguna, aplikasi memerlukan aktivasi akun melalui email. Pengguna akan menerima kode aktivasi untuk mengonfirmasi dan mengaktifkan akun mereka.

- Pencarian Acara Terdekat:

  Pengguna dapat mencari acara yang berlangsung terdekat dengan lokasi mereka. Fitur ini memungkinkan pengguna untuk menemukan dan berpartisipasi dalam acara yang diselenggarakan di sekitar mereka.

- Pembelian Tiket dengan Midtrans:

  Aplikasi ini menyediakan layanan penjualan tiket online dengan menggunakan gateway pembayaran Midtrans. Pengguna dapat dengan mudah membeli tiket untuk acara yang diminati dengan berbagai opsi pembayaran yang nyaman.

- Membuat Acara dengan Persetujuan Admin:

  Pengguna yang ingin mengadakan acara dapat membuatnya melalui aplikasi. Namun, acara akan dipublikasikan setelah mendapatkan persetujuan dari admin. Hal ini untuk memastikan kualitas dan relevansi acara yang ditampilkan di platform.

- Scan QR Code untuk Pembuat Acara:

  Fitur ini memungkinkan pembuat acara untuk dengan mudah memverifikasi kehadiran pengunjung dengan melakukan scan QR code pada tiket. Hal ini membantu dalam manajemen acara dan validasi tiket secara efisien.

- Withdraw Saldo dan Pendapatan:

  Pembuat acara dapat menarik saldo dan pendapatan mereka melalui fitur withdraw yang disediakan oleh aplikasi. Ini memberikan fleksibilitas kepada penyelenggara acara untuk mengelola hasil keuangan mereka dengan mudah.

- Notifikasi Real-Time

  Dengan bantuan _background service_ (Android & IOS), pengguna akan menerima notifikasi real-time tentang status acara, status penarikan, pembelian dan penjualan tiket.

## Tech Stack

- API service / back-end

    - [NestJS 10](https://nestjs.com/) TypeScript
    - Prisma ORM
    - PostgreSQL
    - Redis
    - Swagger(API docs)

- Admin panel web (Monorepo with API service)

    - [SvelteKit 2](https://kit.svelte.dev/) TypeScript
    - Flowbite UI component
    - Tailwind CSS

- Mobile app

    - [Flutter 3](https://flutter.dev/)
      - BLoC
      - Freezed
      - Retrofit
      - fpdart

## Source Code

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

## Instalasi & _How to run_

[Back-end API service](docs/api-service.md)

[Admin-panel](docs/admin-panel.md)

[Mobile app](docs/mobile-app.md)

