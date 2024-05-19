## Panneau d'administration (SvelteKit)

-   [indonésien](admin-panel.md)
-   [Anglais](admin-panel.en.md)

### Configuration requise

Assurez-vous que votre système répond aux exigences suivantes avant de démarrer l'installation :

-   Node.js v18 ou supérieur
-   PostgreSQL 15 ou supérieur
-   Redis v5 ou supérieur

### Étapes d'installation

1.  Suivez les étapes d'installation[Service back-end](api-service.md)d'abord

2.  Environnement de configuration

    Renommer`.env.example`à`.env`

    Les valeurs d'hôte et de port/origine doivent être différentes du service API

### Comment courir

1.  Construire

```bash
npm run admin:build
```

2.  Exécuter l'application

```bash
npm run admin:start
```

-   ou mode développement

```bash
npm run admin:dev
```

### Captures d'écran

![Dashboard](/assets/admin/dashboard.png)

![Events](/assets/admin/events.png)![Events Dark](/assets/admin/events-dark.png)

![Events Detail](/assets/admin/event-detail.png)

![Users](/assets/admin/users.png)![Users Dark](/assets/admin/users-dark.png)

![Settings](/assets/admin/settings.png)
