## बैक-एंड सेवा (NestJS)

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

इसमें एक व्यवस्थापक पैनल एप्लिकेशन शामिल है

    apps/api
    apps/admin-panel

### सिस्टम आवश्यकताएं

इंस्टॉलेशन शुरू करने से पहले सुनिश्चित करें कि आपका सिस्टम निम्नलिखित आवश्यकताओं को पूरा करता है:

-   Node.js v18 या उच्चतर
-   PostgreSQL 15 या उच्चतर
-   रेडिस v5 या उच्चतर

### स्थापना चरण

1.  क्लोन/एक्सट्रेक्ट रिपॉजिटरी

2.  निर्भरताएँ स्थापित करें:

```bash
npm i
```

#### सेटअप वातावरण

-   नाम बदलें`.env.example`को`.env`

#### सेटअप डेटाबेस

-   व्यवस्थित करना`DATABASE_URL`का`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   आवश्यक तालिकाएँ बनाने के लिए माइग्रेशन चलाएँ

```bash
npx prisma migrate deploy
```

-   उपयोगकर्ता बनाने के लिए डेटाबेस सीडर चलाएँ`superadmin`

```bash
npm run db:seed
```

#### स्थापित करना**गूगल साइन इन करें**सर्वर और क्लाइंट आईडी

-   पर एक नया प्रोजेक्ट बनाएं[गूगल क्लाउड कंसोल](https://console.cloud.google.com/projectcreate)

-   एक बार जब आप प्रोजेक्ट बनाना पूरा कर लें, तो उसे चुनें`APIs & Services`, फिर चुनें`OAuth consent screen`बायीं तरफ पर

-   एप्लिकेशन का नाम, ईमेल और दर्ज करें`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **सर्वर**ग्राहक ID

    -   चुनना`Credentials`बाएँ साइडबार में, क्लिक करें`CREATE CREDENTIALS`, चुनना`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   चुनना`Web application`आवेदन प्रकार, बेरी नामा लालू सहेजें/बनाएं

    ![Cloud Console](/assets/Screenshot_3.png)

-   अनुवाद`Client ID`और`Client secret`के फाइल`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **वेब अप्प**ग्राहक ID

    -   `CREATE CREDENTIALS`वापस, चयन करें`OAuth client ID`

    -   चुनना`Web application`आवेदन का प्रकार, एक नाम दें और`Authorized JavaScript origins`चित्र के अनुसार (यदि लोकलहोस्ट का उपयोग कर रहे हैं), तो सहेजें/बनाएं

    ![Cloud Console](/assets/Screenshot_4.png)

    -   अनुवाद`Client ID`और`Client secret`के फाइल`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   क्लिक`DOWNLOAD JSON`और क्लाइंट आईडी सेव करें। वेब क्लाइंट आईडी का उपयोग फ़्लटर मोबाइल ऐप में किया जाएगा।

#### मिडट्रांस सर्वर और क्लाइंट कुंजी सेटअप करें

-   जाओ[डैशबोर्ड मिडट्रांस](https://dashboard.midtrans.com/), पर्यावरण का चयन करें`sandbox`(अनुशंसित) अताउ`production`
-   में दर्ज`Settings`>`Access Keys`, लालू सलीन क्लाइंट डान सर्वर कीय के फाइल`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   परिवर्तनीय विन्यास`.env`आवश्यकतानुसार अन्य।

### कैसे चलायें

1.  उत्पन्न`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  ऐप चलाएँ

```bash
npm run start
```

-   विकास मोड

```bash
npm run start:dev
```

2.  स्वैगर एपीआई दस्तावेज़

-   http&#x3A;//localhost:3000/api/docs खोलें (आधार यूआरएल समायोजित करें)

3.  परीक्षण (वैकल्पिक)

```bash
npm test
```

### स्क्रीनशॉट

![Swagger API Docs](/assets/swagger.png)
