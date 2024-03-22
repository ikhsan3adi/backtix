## Back-end service (NestJS)

- [Bahasa Indonesia](./api-service.md)
- [English](./api-service.en.md)

Sudah termasuk aplikasi admin panel didalamnya

```
apps/api
apps/admin-panel
```

### Persyaratan Sistem

Pastikan sistem Anda memenuhi persyaratan berikut sebelum memulai instalasi:

- Node.js v18 or higher
- PostgreSQL 15 or higher
- Redis v5 or higher

### Langkah-langkah Instalasi

1. Clone/extract Repository

2. Install dependencies:
```bash
npm i
```

#### Setup environment

- Rename `.env.example` to `.env`

#### Setup database

- Atur `DATABASE_URL` di `.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

- Jalankan migrasi untuk membuat tabel yang diperlukan

```bash
npx prisma migrate deploy
```

- Jalankan database seeder untuk membuat user `superadmin`

```bash
npm run db:seed
```

#### Setup **Google sign in** server & client ID

- Buat project baru di [Google Cloud Console](https://console.cloud.google.com/projectcreate)

- Setelah selesai membuat projek, pilih `APIs & Services`, lalu pilih `OAuth consent screen` disebelah kiri

- Masukkan nama aplikasi, email dan `Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

- **Server** client ID

  - Pilih `Credentials` di sidebar kiri, klik `CREATE CREDENTIALS`, pilih `OAuth client ID`

  ![Cloud Console](/assets/Screenshot_2.png)


  - Pilih `Web application` application type, beri nama lalu save/create

  ![Cloud Console](/assets/Screenshot_3.png)

  - Salin `Client ID` dan `Client secret` ke file `.env`

  ```sh
  # google oauth
  SERVER_GOOGLE_CLIENT_ID=
  SERVER_GOOGLE_CLIENT_SECRET=
  ```

- **Web app** client ID

  - `CREATE CREDENTIALS` kembali, pilih `OAuth client ID`

  - Pilih `Web application` application type, beri nama dan `Authorized JavaScript origins` seperti di gambar (jika menggunakan localhost), lalu save/create

  ![Cloud Console](/assets/Screenshot_4.png)

  - Salin `Client ID` dan `Client secret` ke file `.env`

  ```sh
  # optional web only
  WEB_APP_GOOGLE_CLIENT_ID=
  WEB_APP_GOOGLE_CLIENT_SECRET=
  ```
  - Klik `DOWNLOAD JSON` dan simpan Client ID. Web Client ID akan digunakan di flutter mobile app.

#### Setup midtrans server & client key

- Pergi ke [Dashboard Midtrans](https://dashboard.midtrans.com/), pilih environment `sandbox`(recommended) atau `production`
- Masuk ke `Settings` > `Access Keys`, lalu salin client dan server key ke file `.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

- Configurasi variabel `.env` lainnya sesuai kebutuhan.

### How to run

1. Generate `metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2. Run app

```bash
npm run start
```
- Development mode

```bash
npm run start:dev
```

2. Swagger API docs

- Buka http://localhost:3000/api/docs (sesuaikan base url)

3. Test (optional)

```bash
npm test
```

### Screenshots

![Swagger API Docs](/assets/swagger.png)
