## Admin panel (SvelteKit)

- [Bahasa Indonesia](./admin-panel.md)
- [English](./admin-panel.en.md)

### Persyaratan Sistem

Pastikan sistem Anda memenuhi persyaratan berikut sebelum memulai instalasi:

- Node.js v18 or higher
- PostgreSQL 15 or higher
- Redis v5 or higher

### Langkah-langkah Instalasi

1. Ikuti langkah instalasi [Back-end service](api-service.md) terlebih dahulu

2. Setup environment
    
    Rename `.env.example` to `.env`
    
    Nilai host & port / origin harus berbeda dengan api service

### How to run

1. Build

```bash
npm run admin:build
```

2. Run app

```bash
npm run admin:start
```

- or development mode

```bash
npm run admin:dev
```

### Screenshots

![Dashboard](/assets/admin/dashboard.png)

![Events](/assets/admin/events.png)
![Events Dark](/assets/admin/events-dark.png)

![Events Detail](/assets/admin/event-detail.png)

![Users](/assets/admin/users.png)
![Users Dark](/assets/admin/users-dark.png)

![Settings](/assets/admin/settings.png)