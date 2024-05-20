# バックティック

> オープンソースのイベントおよびチケット発行アプリ

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
<a href="./README.hi.md">
  <img alt="Translation" src="https://img.shields.io/badge/Hindi_हिंदी-blue?style=for-the-badge&logo=googletranslate&logoColor=blue&labelColor=white">
</a>

* * *

このオンラインイベント作成・チケット販売アプリケーションは、ユーザーが様々なイベントに簡単にアクセス・参加できるプラットフォームです。以下は説明です
アプリケーションの主な機能を簡単に説明します。

-   認証:

    このアプリは、JSON Web Token (JWT) と Google サインインを介した安全な認証を提供します。ユーザーは、便利で安全な認証方法を使用して、自分のアカウントに簡単にログインできます。

-   電子メールによるアカウントのアクティベーション:

    セキュリティを強化し、ユーザーの信頼性を確保するために、アプリケーションでは電子メールによるアカウントのアクティブ化が必要です。ユーザーは、アカウントを確認してアクティブ化するためのアクティベーション コードを受け取ります。

-   近くのイベント検索:

    ユーザーは、自分のいる場所の近くで開催されるイベントを検索できます。この機能により、ユーザーは近くで開催されるイベントを見つけて参加することができます。

-   Midtrans でチケットを購入:

    このアプリケーションは、Midtrans ペイメントゲートウェイを使用したオンラインチケット販売サービスを提供します。ユーザーは、さまざまな便利な支払いオプションを使用して、興味のあるイベントのチケットを簡単に購入できます。

-   管理者の承認を得てイベントを作成する:

    イベントを開催したいユーザーはアプリからイベントを作成できます。ただし、イベントは管理者の承認を得た上で掲載させていただきます。これは、プラットフォームに表示されるイベントの品質と関連性を保証するためです。

-   イベント作成者の QR コードをスキャンします:

    この機能により、イベント作成者はチケットの QR コードをスキャンすることで訪問者の出席を簡単に確認できます。これは、効率的なイベント管理とチケットの検証に役立ちます。

-   出金残高と収入:

    イベント作成者は、アプリケーションが提供する出金機能を介して残高と収益を引き出すことができます。これにより、イベント主催者は財務結果を簡単に管理できる柔軟性が得られます。

-   リアルタイム通知

    の助けを借りて_バックグラウンドサービス_(Android および IOS)、ユーザーはイベントのステータス、退会ステータス、チケットの購入と販売に関するリアルタイムの通知を受け取ります。

## 技術スタック

-   APIサービス/バックエンド

    -   [ネストJS 10](https://nestjs.com/)TypeScript
    -   プリズマORM
    -   PostgreSQL
    -   レディス
    -   Swagger(API ドキュメント)

-   管理パネルWeb（APIサービス付きモノレポ）

    -   [スベルトキット 2](https://kit.svelte.dev/)TypeScript
    -   Flowbite UI コンポーネント
    -   追い風 CSS

-   モバイルアプリ

    -   [フラッター 3](https://flutter.dev/)
        -   ブロック
        -   凍結
        -   後付け
        -   FPダート

## ソースコード

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

## インストールと_走り方_

[バックエンドAPIサービス](docs/api-service.md)

[管理パネル](docs/admin-panel.md)

[モバイルアプリ](docs/mobile-app.md)
