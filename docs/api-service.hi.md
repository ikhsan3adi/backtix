## बैक-एंड सर्विस (NESTJS)

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

इसमें व्यवस्थापक एप्लिकेशन पैनल शामिल है

    apps/api
    apps/admin-panel

### सिस्टम आवश्यकताएं

सुनिश्चित करें कि आपका सिस्टम इंस्टॉलेशन शुरू करने से पहले निम्नलिखित आवश्यकताओं को पूरा करता है:

-   Node.js v18 या उच्चतर
-   Postgresql 15 या उच्चतर
-   Redis V5 या उच्चतर

### स्थापना चरण

1.  क्लोन/एक्सट्रैक्ट रिपॉजिटरी

2.  निर्भरता स्थापित करें:

```bash
npm i
```

#### सेटअप वातावरण

-   नाम बदलें`.env.example`को`.env`

#### सेटअप डेटाबेस

-   तय करना`DATABASE_URL`का`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   आवश्यक तालिका बनाने के लिए माइग्रेशन चलाएं

```bash
npx prisma migrate deploy
```

-   उपयोगकर्ता बनाने के लिए डेटाबेस सीडर चलाएं`superadmin`

```bash
npm run db:seed
```

#### स्थापित करना**Google में साइन इन करें**सर्वर और ग्राहक आईडी

-   पर एक नई परियोजना बनाएं[Google Cloud Console](https://console.cloud.google.com/projectcreate)

-   एक बार परियोजना बनाने के बाद, चयन करें`APIs & Services`, उसके बाद चुनो`OAuth consent screen`बाईं तरफ

-   आवेदन, ईमेल और का नाम दर्ज करें`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **सर्वर**ग्राहक आईडी

    -   चुनना`Credentials`बाईं साइडबार पर, क्लिक करें`CREATE CREDENTIALS`, चुनना`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   चुनना`Web application`एप्लिकेशन प्रकार, बेरी नाम लालू सहेजें/बनाएं

    ![Cloud Console](/assets/Screenshot_3.png)

-   अनुवाद`Client ID`और`Client secret`ke file`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **वेब अप्प**ग्राहक आईडी

    -   `CREATE CREDENTIALS`वापस, चुनें`OAuth client ID`

    -   चुनना`Web application`अनुप्रयोग प्रकार, नाम और`Authorized JavaScript origins`चित्र की तरह (यदि लोकलहोस्ट का उपयोग कर रहा है), तो सहेजें/बनाएं

    ![Cloud Console](/assets/Screenshot_4.png)

    -   अनुवाद`Client ID`और`Client secret`ke file`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   क्लिक`DOWNLOAD JSON`और क्लाइंट आईडी सहेजें। वेब क्लाइंट आईडी का उपयोग मोबाइल ऐप फ्लूट में किया जाएगा।

#### सेटअप midtrans सर्वर और क्लाइंट कुंजी

-   जाओ[डैशबोर्ड मिडट्रान्स](https://dashboard.midtrans.com/), पर्यावरण का चयन करें`sandbox`(अनुशंसित) या`production`
-   प्रवेश करना`Settings`>`Access Keys`, lalu salin client dan server key ke file`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   परिवर्तनीय विन्यास`.env`आवश्यकतानुसार अन्य।

### कैसे चलाएं

1.  उत्पन्न`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  रन ऐप

```bash
npm run start
```

-   विकास विधा

```bash
npm run start:dev
```

2.  स्वैगर एपीआई डॉक्स

-   खुला http&#x3A; // localhost: 3000/आग/डॉक्स (आधार URL समायोजित करें)

3.  परीक्षण (वैकल्पिक)

```bash
npm test
```

### स्क्रीनशॉट

![Swagger API Docs](/assets/swagger.png)
