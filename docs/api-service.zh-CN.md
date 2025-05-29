## 后端服务（Nestjs）

<a href="./api-service.md">
  <img alt="Translation" src="https://img.shields.io/badge/Bahasa_Indonesia-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.en.md">
  <img alt="Translation" src="https://img.shields.io/badge/English-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.zh-CN.md">
  <img alt="Translation" src="https://img.shields.io/badge/简体中文-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.ja.md">
  <img alt="Translation" src="https://img.shields.io/badge/日本語-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.ar.md">
  <img alt="Translation" src="https://img.shields.io/badge/Arabic_عربي-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.pt.md">
  <img alt="Translation" src="https://img.shields.io/badge/Português-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.es.md">
  <img alt="Translation" src="https://img.shields.io/badge/Español-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.fr.md">
  <img alt="Translation" src="https://img.shields.io/badge/Français-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.vi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Tiếng_Việt-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./api-service.hi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Hindi_हिंदी-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

包括管理申请面板

    apps/api
    apps/admin-panel

### 系统要求

在开始安装之前，请确保您的系统满足以下要求：

-   node.js v18或更高
-   Postgresql 15或更高
-   REDIS V5或更高

### 安装步骤

1.  克隆/提取库

2.  安装依赖项：

```bash
npm i
```

#### 设置环境

-   重命名`.env.example`到`.env`

#### 设置数据库

-   放`DATABASE_URL`的`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   运行迁移以制作所需的表

```bash
npx prisma migrate deploy
```

-   运行数据库播种机以创建用户`superadmin`

```bash
npm run db:seed
```

#### 设置**Google登录**服务器和客户端ID

-   创建一个新项目[Google Cloud Console](https://console.cloud.google.com/projectcreate)

-   完成项目后，选择`APIs & Services`，然后选择`OAuth consent screen`在左侧

-   输入应用程序的名称，电子邮件和`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **服务器**客户ID

    -   选择`Credentials`在左侧栏上，单击`CREATE CREDENTIALS`， 选择`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   选择`Web application`申请类型，beri nama lalu保存/创建

    ![Cloud Console](/assets/Screenshot_3.png)

-   翻译`Client ID`和`Client secret`文件`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Web应用程序**客户ID

    -   `CREATE CREDENTIALS`回来，选择`OAuth client ID`

    -   选择`Web application`申请类型，名称和`Authorized JavaScript origins`像图片中（如果使用localhost），然后保存/创建

    ![Cloud Console](/assets/Screenshot_4.png)

    -   翻译`Client ID`和`Client secret`文件`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   点击`DOWNLOAD JSON`并保存客户端ID。 Web客户端ID将在移动应用程序扑朔迷离中使用。

#### 设置中型服务器和客户端密钥

-   去[仪表板中型](https://dashboard.midtrans.com/)，选择环境`sandbox`（建议）或`production`
-   进入`Settings`>`Access Keys`，然后将客户端和服务器键复制到文件`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   可变配置`.env`其他根据需要的。

### 如何运行

1.  产生`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  运行应用程序

```bash
npm run start
```

-   开发模式

```bash
npm run start:dev
```

2.  Swagger API文档

-   打开http：// localhost：3000/fire/docs（调整基本URL）

3.  测试（可选）

```bash
npm test
```

### 屏幕截图

![Swagger API Docs](/assets/swagger.png)
