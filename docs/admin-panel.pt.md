## Painel de administração (SvelteKit)

-   [indonésio](admin-panel.md)
-   [Inglês](admin-panel.en.md)

### Requisitos de sistema

Certifique-se de que seu sistema atenda aos seguintes requisitos antes de iniciar a instalação:

-   Node.js v18 ou superior
-   PostgreSQL 15 ou superior
-   Redis v5 ou superior

### Etapas de instalação

1.  Siga as etapas de instalação[Serviço de back-end](api-service.md)primeiro

2.  Ambiente de configuração

    Renomear`.env.example`para`.env`

    Os valores de host e porta/origem devem ser diferentes do serviço API

### Como correr

1.  Construir

```bash
npm run admin:build
```

2.  Executar aplicativo

```bash
npm run admin:start
```

-   ou modo de desenvolvimento

```bash
npm run admin:dev
```

### Capturas de tela

![Dashboard](/assets/admin/dashboard.png)

![Events](/assets/admin/events.png)![Events Dark](/assets/admin/events-dark.png)

![Events Detail](/assets/admin/event-detail.png)

![Users](/assets/admin/users.png)![Users Dark](/assets/admin/users-dark.png)

![Settings](/assets/admin/settings.png)
