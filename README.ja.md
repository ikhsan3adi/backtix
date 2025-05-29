# backtix

> オープンソースイベントとチケットアプリ

<img src="assets/social_preview.png" alt="BackTix">

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

## ソースコード

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

* * *

> [！重要!]
>
> ## インストール＆_実行方法_
>
> [バックエンドAPIサービス](docs/api-service.md)
>
> [管理者パネル](docs/admin-panel.md)
>
> [モバイルアプリ](docs/mobile-app.md)
>
> * * *
>
> [！注記!]
>
> ## 技術スタック
>
> -   APIサービス /バックエンド
>
>     -   [いいえ10](https://nestjs.com/)タイプスクリプト
>     -   プリスマオーム
>     -   postgreSql
>     -   Redis
>     -   swagger（api docs）
>
> -   管理パネルWeb（APIサービス付きモノレポ）
>
>     -   [Svelteki 2](https://kit.svelte.dev/)タイプスクリプト
>     -   フローバイトUIコンポーネント
>     -   Tailwind CSS
>
> -   モバイルアプリ
>
>     -   [フラッター3](https://flutter.dev/)
>         -   ブロック
>         -   凍結
>         -   レトロフィット
>         -   fpdart

* * *

イベントやオンラインチケット販売を行うためのアプリケーションは、ユーザーがさまざまなイベントにアクセスして参加するための利便性を提供するプラットフォームです。これが説明です
短いメインアプリケーション機能：

-   認証：

    このアプリケーションは、JSON Webトークン（JWT）とGoogleサインインを介して安全な認証を提供します。ユーザーは、快適で安全な認証方法で簡単にアカウントを入力できます。

-   メールによるアカウントのアクティブ化：

    セキュリティを増やし、ユーザーの信頼性を確保するために、アプリケーションにはメールでアカウントのアクティブ化が必要です。ユーザーは、アカウントを確認およびアクティブにするためのアクティベーションコードを受け取ります。

-   最寄りのイベント検索：

    ユーザーは、自分の場所に最も近いイベントを見つけることができます。この機能により、ユーザーはそれらの周りに開催されるイベントを見つけて参加できます。

-   ミッドトランでのチケット購入：

    このアプリケーションは、MidTrans Payment Gatewaysを使用してオンラインチケット販売サービスを提供します。ユーザーは、さまざまな快適な支払いオプションを使用して、需要のあるイベント用のチケットを簡単に購入できます。

-   管理者の承認を得てイベントを行う：

    イベントを開催したいユーザーは、アプリケーションを通じて行うことができます。ただし、イベントは管理者から承認を受けた後に公開されます。これは、プラットフォームに表示されるイベントの品質と関連性を確保するためです。

-   イベントメーカーのQRコードスキャン：

    この機能により、イベントメーカーは、チケットのQRコードをスキャンすることにより、訪問者の存在を簡単に確認できます。これは、イベント管理とチケットの検証に効率的に役立ちます。

-   バランスと収入を引き下げる：

    イベントメーカーは、アプリケーションが提供する撤回機能を通じて、残高と収入を引き付けることができます。これにより、イベントのオーガナイザーに財務結果を簡単に管理できるようになります。

-   リアルタイム通知

    の助けを借りて_バックグラウンドサービス_（Android＆iOS）、ユーザーは、イベントのステータス、引き出しステータス、購入、チケット販売に関するリアルタイムの通知を受け取ります。

## サポートと寄付

[![Donate paypal](https://img.shields.io/badge/Donate-PayPal-green.svg?style=for-the-badge)](https://paypal.me/ikhsan3adi?country.x=ID&locale.x=en_US)[![Donate saweria](https://img.shields.io/badge/Donate-Saweria-red?style=for-the-badge&link=https%3A%2F%2Fsaweria.co%2Fxiboxann)](https://saweria.co/xiboxann)
