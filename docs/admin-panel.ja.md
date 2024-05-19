## 管理パネル (SvelteKit)

-   [インドネシア語](admin-panel.md)
-   [英語](admin-panel.en.md)

### システム要求

インストールを開始する前に、システムが次の要件を満たしていることを確認してください。

-   Node.js v18以降
-   PostgreSQL 15 以降
-   Redis v5 以降

### インストール手順

1.  インストール手順に従います[バックエンドサービス](api-service.md)初め

2.  セットアップ環境

    名前を変更する`.env.example`に`.env`

    ホストとポート/オリジンの値は API サービスとは異なる必要があります

### 走り方

1.  建てる

```bash
npm run admin:build
```

2.  アプリを実行する

```bash
npm run admin:start
```

-   または開発モード

```bash
npm run admin:dev
```

### スクリーンショット

![Dashboard](/assets/admin/dashboard.png)

![Events](/assets/admin/events.png)![Events Dark](/assets/admin/events-dark.png)

![Events Detail](/assets/admin/event-detail.png)

![Users](/assets/admin/users.png)![Users Dark](/assets/admin/users-dark.png)

![Settings](/assets/admin/settings.png)
