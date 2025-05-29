## الخدمة الخلفية (NESTJS)

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

يتضمن لوحة تطبيق المسؤول فيه

    apps/api
    apps/admin-panel

### متطلبات النظام

تأكد من أن نظامك يفي بالمتطلبات التالية قبل بدء التثبيت:

-   node.js v18 أو أعلى
-   PostgreSQL 15 أو أعلى
-   redis v5 أو أعلى

### خطوات التثبيت

1.  استنساخ/مستخلص مستودع

2.  تثبيت التبعيات:

```bash
npm i
```

#### بيئة الإعداد

-   إعادة تسمية`.env.example`ل`.env`

#### إعداد قاعدة البيانات

-   تعيين`DATABASE_URL`ل`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   تشغيل الترحيل لجعل الجدول المطلوب

```bash
npx prisma migrate deploy
```

-   قم بتشغيل قاعدة البيانات لإنشاء مستخدم`superadmin`

```bash
npm run db:seed
```

#### يثبت**تسجيل الدخول جوجل**معرف الخادم والعميل

-   إنشاء مشروع جديد في[وحدة التحكم السحابية Google](https://console.cloud.google.com/projectcreate)

-   بمجرد الانتهاء من صنع المشروع ، حدد`APIs & Services`، ثم اختر`OAuth consent screen`على اليسار

-   أدخل اسم التطبيق والبريد الإلكتروني و`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **الخادم**معرف العميل

    -   يختار`Credentials`على الشريط الجانبي الأيسر ، انقر`CREATE CREDENTIALS`، يختار`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   يختار`Web application`نوع التطبيق ، Beri nama lalu حفظ/إنشاء

    ![Cloud Console](/assets/Screenshot_3.png)

-   ترجمة`Client ID`و`Client secret`ملف`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **تطبيق الويب**معرف العميل

    -   `CREATE CREDENTIALS`مرة أخرى ، اختر`OAuth client ID`

    -   يختار`Web application`نوع التطبيق والاسم و`Authorized JavaScript origins`كما هو الحال في الصورة (إذا كنت تستخدم مضيفًا محليًا) ، فاحفظ/إنشاء

    ![Cloud Console](/assets/Screenshot_4.png)

    -   ترجمة`Client ID`و`Client secret`ملف`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   انقر`DOWNLOAD JSON`وحفظ معرف العميل. سيتم استخدام معرف عميل الويب في رفرفة تطبيق الهاتف المحمول.

#### إعداد Midtrans Server & Client Key

-   اذهب إلى[لوحة القيادة Midtrans](https://dashboard.midtrans.com/)، حدد البيئة`sandbox`(موصى به) أو`production`
-   يدخل`Settings`>`Access Keys`، ثم انسخ مفتاح العميل والخادم إلى الملف`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   التكوين المتغير`.env`الآخرين حسب الحاجة.

### كيفية الجري

1.  يولد`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  تشغيل التطبيق

```bash
npm run start
```

-   وضع التطوير

```bash
npm run start:dev
```

2.  مستندات Swagger API

-   افتح http&#x3A; // localhost: 3000/fire/docs (اضبط عنوان URL الأساسي)

3.  اختبار (اختياري)

```bash
npm test
```

### لقطات الشاشة

![Swagger API Docs](/assets/swagger.png)
