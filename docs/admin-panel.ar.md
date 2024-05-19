## لوحة الإدارة (SvelteKit)

-   [الاندونيسية](admin-panel.md)
-   [إنجليزي](admin-panel.en.md)

### متطلبات النظام

تأكد من أن نظامك يلبي المتطلبات التالية قبل بدء التثبيت:

-   Node.js v18 أو أعلى
-   PostgreSQL 15 أو أعلى
-   ريديس v5 أو أعلى

### خطوات التثبيت

1.  اتبع خطوات التثبيت[خدمة الخلفية](api-service.md)أولاً

2.  بيئة الإعداد

    إعادة تسمية`.env.example`ل`.env`

    يجب أن تكون قيم المضيف والمنفذ/الأصل مختلفة عن خدمة واجهة برمجة التطبيقات

### كيف تركض

1.  يبني

```bash
npm run admin:build
```

2.  تشغيل التطبيق

```bash
npm run admin:start
```

-   أو وضع التطوير

```bash
npm run admin:dev
```

### لقطات الشاشة

![Dashboard](/assets/admin/dashboard.png)

![Events](/assets/admin/events.png)![Events Dark](/assets/admin/events-dark.png)

![Events Detail](/assets/admin/event-detail.png)

![Users](/assets/admin/users.png)![Users Dark](/assets/admin/users-dark.png)

![Settings](/assets/admin/settings.png)
