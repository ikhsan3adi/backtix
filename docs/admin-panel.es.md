## Panel de administración (SvelteKit)

-   [indonesio](admin-panel.md)
-   [Inglés](admin-panel.en.md)

### Requisitos del sistema

Asegúrese de que su sistema cumpla con los siguientes requisitos antes de comenzar la instalación:

-   Node.js v18 o superior
-   PostgreSQL 15 o superior
-   Redis v5 o superior

### Pasos de instalación

1.  Siga los pasos de instalación[Servicio de fondo](api-service.md)primero

2.  Entorno de configuración

    Rebautizar`.env.example`a`.env`

    Los valores de host y puerto/origen deben ser diferentes a los del servicio api

### Como correr

1.  Construir

```bash
npm run admin:build
```

2.  Ejecutar aplicación

```bash
npm run admin:start
```

-   o modo de desarrollo

```bash
npm run admin:dev
```

### Capturas de pantalla

![Dashboard](/assets/admin/dashboard.png)

![Events](/assets/admin/events.png)![Events Dark](/assets/admin/events-dark.png)

![Events Detail](/assets/admin/event-detail.png)

![Users](/assets/admin/users.png)![Users Dark](/assets/admin/users-dark.png)

![Settings](/assets/admin/settings.png)
