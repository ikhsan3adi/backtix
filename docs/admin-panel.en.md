## Admin panel (SvelteKit)

-   [Indonesian](admin-panel.md)
-   [English](admin-panel.en.md)

### System Requirements

Make sure your system meets the following requirements before starting the installation:

-   Node.js v18 or higher
-   PostgreSQL 15 or higher
-   Redis v5 or higher

### Installation Steps

1.  Ikuti langkah instalasi [Back-end service](api-service.md)first

2.  Setup environment

    Rename`.env.example`to`.env`

    The host & port / origin values ​​must be different from the api service

### How to run

1.  Build

```bash
npm run admin:build
```

2.  Run app

```bash
npm run admin:start
```

-   or development mode

```bash
npm run admin:dev
```

### Screenshots

![Dashboard](/assets/admin/dashboard.png)

![Events](/assets/admin/events.png)![Events Dark](/assets/admin/events-dark.png)

![Events Detail](/assets/admin/event-detail.png)

![Users](/assets/admin/users.png)![Users Dark](/assets/admin/users-dark.png)

![Settings](/assets/admin/settings.png)
