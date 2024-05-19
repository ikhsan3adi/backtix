## الخدمة الخلفية (NestJS)

-   [الاندونيسية](api-service.md)
-   [إنجليزي](api-service.en.md)

يتضمن تطبيق لوحة الإدارة

    apps/api
    apps/admin-panel

### متطلبات النظام

تأكد من أن نظامك يلبي المتطلبات التالية قبل بدء التثبيت:

-   Node.js v18 أو أعلى
-   PostgreSQL 15 أو أعلى
-   ريديس v5 أو أعلى

### خطوات التثبيت

1.  استنساخ/استخراج المستودع

2.  تثبيت التبعيات:

```bash
npm i
```

#### بيئة الإعداد

-   إعادة تسمية`.env.example`ل`.env`

#### قاعدة بيانات الإعداد

-   يرتب`DATABASE_URL`ل`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   قم بتشغيل الترحيل لإنشاء الجداول المطلوبة

```bash
npx prisma migrate deploy
```

-   قم بتشغيل بذارة قاعدة البيانات لإنشاء مستخدمين`superadmin`

```bash
npm run db:seed
```

#### يثبت**تسجيل الدخول جوجل**معرف الخادم والعميل

-   إنشاء مشروع جديد في[جوجل السحابية وحدة التحكم](https://console.cloud.google.com/projectcreate)

-   بمجرد الانتهاء من إنشاء المشروع، حدده`APIs & Services`، ثم حدد`OAuth consent screen`على الجانب الأيسر

-   أدخل اسم التطبيق والبريد الإلكتروني و`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **الخادم**معرف العميل

    -   يختار`Credentials`في الشريط الجانبي الأيسر، انقر فوق`CREATE CREDENTIALS`، يختار`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   يختار`Web application`نوع التطبيق، بيري ناما لالو حفظ/إنشاء

    ![Cloud Console](/assets/Screenshot_3.png)

-   ترجمة`Client ID`و`Client secret`أعطيت`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **التطبيق على شبكة الإنترنت**معرف العميل

    -   `CREATE CREDENTIALS`العودة، حدد`OAuth client ID`

    -   يختار`Web application`نوع التطبيق، وإعطاء اسم و`Authorized JavaScript origins`كما في الصورة (إذا كنت تستخدم المضيف المحلي)، ثم احفظ/أنشئ

    ![Cloud Console](/assets/Screenshot_4.png)

    -   ترجمة`Client ID`و`Client secret`أعطيت`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   انقر`DOWNLOAD JSON`وحفظ معرف العميل. سيتم استخدام معرف عميل الويب في تطبيق Flutter للجوال.

#### إعداد خادم midtrans ومفتاح العميل

-   اذهب إلى[لوحة القيادة ميدترانس](https://dashboard.midtrans.com/)، حدد البيئة`sandbox`(مستحسن) أو`production`
-   أدخل إلى`Settings`>`Access Keys`، ثم انسخ مفاتيح العميل والخادم إلى الملف`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   التكوين المتغير`.env`أخرى حسب الحاجة.

### كيف تركض

1.  يولد`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  تشغيل التطبيق

```bash
npm run start
```

-   وضع التنمية

```bash
npm run start:dev
```

2.  مستندات Swagger API

-   افتح http&#x3A;//localhost:3000/api/docs (اضبط عنوان URL الأساسي)

3.  اختبار (اختياري)

```bash
npm test
```

### لقطات الشاشة

![Swagger API Docs](/assets/swagger.png)
