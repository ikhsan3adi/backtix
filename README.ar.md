# backtix

> حدث مفتوح المصدر وتطبيق التذاكر

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

## رمز المصدر

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

* * *

> [!مهم]
>
> ## تثبيت &_كيفية الجري_
>
> [خدمة واجهة برمجة التطبيقات الخلفية](docs/api-service.md)
>
> [لوحة المسؤول](docs/admin-panel.md)
>
> [تطبيق الجوال](docs/mobile-app.md)
>
> * * *
>
> [!ملحوظة]
>
> ## مكدس التكنولوجيا
>
> -   خدمة API / خلفية
>
>     -   [لا 10](https://nestjs.com/)TypeScript
>     -   Prisma orm
>     -   postgresql
>     -   redis
>     -   Swagger (مستندات API)
>
> -   لوحة الإدارة على شبكة الإنترنت (MonoRepo مع خدمة API)
>
>     -   [Svelteki 2](https://kit.svelte.dev/)TypeScript
>     -   مكون FlowBite واجهة المستخدم
>     -   Tailwind CSS
>
> -   تطبيق الجوال
>
>     -   [رفرفة 3](https://flutter.dev/)
>         -   كتلة
>         -   تجميد
>         -   التحديثية
>         -   FPDART

* * *

يعد طلب إنشاء الأحداث ومبيعات التذاكر عبر الإنترنت منصة توفر الراحة للمستخدمين للوصول إلى مختلف الأحداث والمشاركة في مختلف الأحداث. هنا وصف
ميزات التطبيق الرئيسية القصيرة:

-   المصادقة:

    يوفر هذا التطبيق مصادقة آمنة من خلال JSON Web Token (JWT) و Google Sign-In. يمكن للمستخدمين إدخال حسابهم بسهولة باستخدام طريقة مصادقة مريحة وآمنة.

-   تنشيط الحساب عبر البريد الإلكتروني:

    لزيادة الأمان وضمان صحة المستخدم ، يتطلب التطبيق تنشيط الحساب عبر البريد الإلكتروني. سيتلقى المستخدمون رمز التنشيط لتأكيد وتنشيط حسابهم.

-   أقرب بحث عن حدث:

    يمكن للمستخدمين العثور على الأحداث التي تحدث الأقرب إلى موقعهم. تتيح هذه الميزة للمستخدمين العثور على الأحداث المحيطة بها والمشاركة فيها.

-   شراء التذاكر مع Midtrans:

    يوفر هذا التطبيق خدمات مبيعات التذاكر عبر الإنترنت باستخدام بوابات الدفع Midtrans. يمكن للمستخدمين بسهولة شراء تذاكر للأحداث المطلوبة مع مجموعة متنوعة من خيارات الدفع المريحة.

-   اجعل حدثًا بموافقة المسؤول:

    يمكن للمستخدمين الذين يرغبون في عقد حدث ما الوصول إليه من خلال التطبيق. ومع ذلك ، سيتم نشر الحدث بعد الحصول على موافقة من المسؤول. هذا هو ضمان جودة وأهمية الحدث المعروض على المنصة.

-   فحص رمز الاستجابة السريعة لصانع الأحداث:

    تتيح هذه الميزة لصانع الأحداث التحقق بسهولة من وجود الزوار عن طريق مسح رمز الاستجابة السريعة على التذكرة. هذا يساعد في إدارة الأحداث والتحقق من صحة التذاكر بكفاءة.

-   سحب الرصيد والدخل:

    يمكن لصانع الأحداث جذب أرصدة ودخلهم من خلال ميزات السحب التي يوفرها الطلب. يوفر هذا مرونة لمنظم الحدث لإدارة نتائجها المالية بسهولة.

-   إشعار في الوقت الحقيقي

    بمساعدة_خدمة الخلفية_(Android & iOS) ، سيتلقى المستخدمون إشعارات في الوقت الفعلي حول حالة الحدث وحالة السحب وشراء ومبيعات التذاكر.

## الدعم والتبرع

[![Donate paypal](https://img.shields.io/badge/Donate-PayPal-green.svg?style=for-the-badge)](https://paypal.me/ikhsan3adi?country.x=ID&locale.x=en_US)[![Donate saweria](https://img.shields.io/badge/Donate-Saweria-red?style=for-the-badge&link=https%3A%2F%2Fsaweria.co%2Fxiboxann)](https://saweria.co/xiboxann)
