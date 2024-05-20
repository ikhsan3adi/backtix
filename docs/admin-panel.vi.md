## Bảng quản trị (SvelteKit)

<a href="./admin-panel.md">
  <img alt="Translation" src="https://img.shields.io/badge/Bahasa_Indonesia-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./admin-panel.en.md">
  <img alt="Translation" src="https://img.shields.io/badge/English-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./admin-panel.zh-CN.md">
  <img alt="Translation" src="https://img.shields.io/badge/简体中文-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./admin-panel.ja.md">
  <img alt="Translation" src="https://img.shields.io/badge/日本語-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./admin-panel.ar.md">
  <img alt="Translation" src="https://img.shields.io/badge/Arabic_عربي-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./admin-panel.pt.md">
  <img alt="Translation" src="https://img.shields.io/badge/Português-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./admin-panel.es.md">
  <img alt="Translation" src="https://img.shields.io/badge/Español-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./admin-panel.fr.md">
  <img alt="Translation" src="https://img.shields.io/badge/Français-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./admin-panel.vi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Tiếng_Việt-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./admin-panel.hi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Hindi_हिंदी-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

### yêu cầu hệ thống

Đảm bảo hệ thống của bạn đáp ứng các yêu cầu sau trước khi bắt đầu cài đặt:

-   Node.js v18 trở lên
-   PostgreSQL 15 trở lên
-   Redis v5 trở lên

### Các bước cài đặt

1.  Thực hiện theo các bước cài đặt[Dịch vụ phụ trợ](api-service.md)Đầu tiên

2.  Môi trường thiết lập

    Đổi tên`.env.example`ĐẾN`.env`

    Giá trị máy chủ & cổng/nguồn gốc phải khác với dịch vụ api

### Cách chạy

1.  Xây dựng

```bash
npm run admin:build
```

2.  Chạy ứng dụng

```bash
npm run admin:start
```

-   hoặc chế độ phát triển

```bash
npm run admin:dev
```

### Ảnh chụp màn hình

![Dashboard](/assets/admin/dashboard.png)

![Events](/assets/admin/events.png)![Events Dark](/assets/admin/events-dark.png)

![Events Detail](/assets/admin/event-detail.png)

![Users](/assets/admin/users.png)![Users Dark](/assets/admin/users-dark.png)

![Settings](/assets/admin/settings.png)
