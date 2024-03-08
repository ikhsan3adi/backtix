# BackTix

<p align="left">
  <img src="assets/backtix_logo_transparent.png" width="200">
</p>

Aplikasi pembuatan acara dan penjualan tiket online ini merupakan platform yang menyediakan kemudahan bagi pengguna untuk mengakses dan berpartisipasi dalam berbagai acara. Berikut adalah deskripsi singkat fitur-fitur utama aplikasi:

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

## Tech Stack

- API service / back-end

    - NestJS 10 TypeScript
    - Prisma ORM
    - PostgreSQL
    - Redis
    - Swagger(API docs)

- Admin panel web (Monorepo with API service)

    - SvelteKit 2 TypeScript
    - Flowbite UI component
    - Tailwind CSS

- Mobile app

    - Flutter 3
      - BLoC
      - Freezed
      - Retrofit
      - fpdart

## Source Code



## Instalasi

[Back-end API service](https://github.com/ikhsan3adi/backtix-support/blob/main/docs/api-service.md)

[Admin-panel](https://github.com/ikhsan3adi/backtix-support/blob/main/docs/admin-panel.md)

[Mobile app](https://github.com/ikhsan3adi/backtix-support/blob/main/docs/mobile-app.md)

