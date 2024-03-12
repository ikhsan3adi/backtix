## Admin panel (SvelteKit)

### Persyaratan Sistem

Pastikan sistem Anda memenuhi persyaratan berikut sebelum memulai instalasi:

- Node.js v18 or higher
- PostgreSQL 15 or higher
- Redis v5 or higher

### Langkah-langkah Instalasi

1. Ikuti langkah instalasi [Back-end service](https://github.com/ikhsan3adi/backtix/blob/main/docs/api-service.md) terlebih dahulu

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