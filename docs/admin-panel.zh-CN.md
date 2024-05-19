## 管理面板（SvelteKit）

-   [印度尼西亚](admin-panel.md)
-   [英语](admin-panel.en.md)

### 系统要求

开始安装之前，请确保您的系统满足以下要求：

-   Node.js v18 或更高版本
-   PostgreSQL 15 或更高版本
-   Redis v5 或更高版本

### 安装步骤

1.  按照安装步骤操作[后端服务](api-service.md)第一的

2.  设置环境

    改名`.env.example`到`.env`

    主机&端口/origin值必须与api服务不同

### 如何跑

1.  建造

```bash
npm run admin:build
```

2.  运行应用程序

```bash
npm run admin:start
```

-   或开发模式

```bash
npm run admin:dev
```

### 截图

![Dashboard](/assets/admin/dashboard.png)

![Events](/assets/admin/events.png)![Events Dark](/assets/admin/events-dark.png)

![Events Detail](/assets/admin/event-detail.png)

![Users](/assets/admin/users.png)![Users Dark](/assets/admin/users-dark.png)

![Settings](/assets/admin/settings.png)
