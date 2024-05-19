# 回帖

> 开源活动和票务应用程序

<img src="assets/social_preview.png">

<a href="./README.md">
  <img alt="Translation" src="https://img.shields.io/badge/Bahasa_Indonesia-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.en.md">
  <img alt="Translation" src="https://img.shields.io/badge/English-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.zh-CN.md">
  <img alt="Translation" src="https://img.shields.io/badge/简体中文-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.ja.md">
  <img alt="Translation" src="https://img.shields.io/badge/日本語-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.ar.md">
  <img alt="Translation" src="https://img.shields.io/badge/Arabic_عربي-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.pt.md">
  <img alt="Translation" src="https://img.shields.io/badge/Português-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.es.md">
  <img alt="Translation" src="https://img.shields.io/badge/Español-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.fr.md">
  <img alt="Translation" src="https://img.shields.io/badge/Français-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>
<a href="./README.vi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Tiếng_Việt-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

* * *

这个在线活动创建和门票销售应用程序是一个让用户可以轻松访问和参与各种活动的平台。以下是说明
简要介绍该应用程序的主要特点：

-   验证：

    该应用程序通过 JSON Web Token (JWT) 和 Google Sign-In 提供安全身份验证。用户可以通过方便、安全的身份验证方法轻松登录自己的帐户。

-   通过电子邮件激活帐户：

    为了提高安全性并确保用户的真实性，该应用程序需要通过电子邮件激活帐户。用户将收到激活码以确认并激活其帐户。

-   附近活动搜索：

    用户可以搜索距离其位置最近的事件。此功能允许用户发现并参与围绕他们组织的活动。

-   通过 Midtrans 购买门票：

    该应用程序使用 Midtrans 支付网关提供在线门票销售服务。用户可以通过多种便捷的支付方式轻松购买感兴趣的活动门票。

-   创建经管理员批准的活动：

    想要举办活动的用户可以通过应用程序创建活动。不过，该活动将在获得管理员批准后发布。这是为了确保平台上显示的事件的质量和相关性。

-   扫描二维码查看活动创建者：

    此功能允许活动创建者通过扫描门票上的二维码轻松验证访客出席情况。这有助于高效的活动管理和票证验证。

-   提款余额和收入：

    活动创建者可以通过应用程序提供的提款功能提取其余额和收入。这使活动组织者能够灵活地轻松管理其财务业绩。

-   实时通知

    在...的帮助下_后台服务_（Android & IOS），用户将收到有关活动状态、提现状态、购票和售票的实时通知。

## 技术堆栈

-   API服务/后端

    -   [巢JS 10](https://nestjs.com/)打字稿
    -   棱镜 ORM
    -   PostgreSQL
    -   雷迪斯
    -   Swagger（API 文档）

-   管理面板网络（带有 API 服务的 Monorepo）

    -   [SvelteKit 2](https://kit.svelte.dev/)打字稿
    -   Flowbite UI 组件
    -   顺风 CSS

-   移动应用

    -   [颤动3](https://flutter.dev/)
        -   集团
        -   冷冻
        -   改造
        -   飞镖

## 源代码

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

## 安装 ＆_如何跑_

[后端API服务](docs/api-service.md)

[管理面板](docs/admin-panel.md)

[移动应用](docs/mobile-app.md)
