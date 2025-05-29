# पीछे की ओर

> ओपन सोर्स इवेंट और टिकटिंग ऐप

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

## सोर्स कोड

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" alt="source code" />
</a>

* * *

> [!महत्वपूर्ण]
>
> ## स्थापना और_कैसे चलाएं_
>
> [बैक-एंड एपीआई सेवा](docs/api-service.md)
>
> [व्यवस्थापक पैनल](docs/admin-panel.md)
>
> [मोबाइल एप्लिकेशन](docs/mobile-app.md)
>
> * * *
>
> [!टिप्पणी]
>
> ## टेक स्टैक
>
> -   एपीआई सेवा / बैक-एंड
>
>     -   [नहीं 10](https://nestjs.com/)टाइपप्रति
>     -   प्रिस्मा ओरम
>     -   Postgresql
>     -   रेडिस
>     -   स्वैगर (एपीआई डॉक्स)
>
> -   व्यवस्थापक पैनल वेब (एपीआई सेवा के साथ मोनोरेपो)
>
>     -   [स्वेल्टेकी 2](https://kit.svelte.dev/)टाइपप्रति
>     -   फ्लोबाइट यूआई घटक
>     -   टेलविंड सीएसएस
>
> -   मोबाइल एप्लिकेशन
>
>     -   [स्पंदन 3](https://flutter.dev/)
>         -   ब्लॉक
>         -   freezed
>         -   पुराना वापस
>         -   एफपीडीएआरटी

* * *

ईवेंट और ऑनलाइन टिकट बिक्री बनाने के लिए आवेदन एक ऐसा मंच है जो उपयोगकर्ताओं को विभिन्न घटनाओं में पहुंचने और भाग लेने के लिए सुविधा प्रदान करता है। यहाँ एक विवरण है
लघु मुख्य अनुप्रयोग सुविधाएँ:

-   प्रमाणीकरण:

    यह एप्लिकेशन JSON वेब टोकन (JWT) और Google साइन-इन के माध्यम से सुरक्षित प्रमाणीकरण प्रदान करता है। उपयोगकर्ता आसानी से एक आरामदायक और सुरक्षित प्रमाणीकरण विधि के साथ अपना खाता दर्ज कर सकते हैं।

-   ईमेल के माध्यम से खाता सक्रियण:

    सुरक्षा बढ़ाने और उपयोगकर्ता की प्रामाणिकता सुनिश्चित करने के लिए, एप्लिकेशन को ईमेल के माध्यम से खाता सक्रियण की आवश्यकता होती है। उपयोगकर्ताओं को अपने खाते की पुष्टि और सक्रिय करने के लिए एक सक्रियण कोड प्राप्त होगा।

-   निकटतम घटना खोज:

    उपयोगकर्ता उन घटनाओं को पा सकते हैं जो अपने स्थान के सबसे करीब होती हैं। यह सुविधा उपयोगकर्ताओं को उनके आसपास आयोजित घटनाओं में खोजने और भाग लेने की अनुमति देती है।

-   मिडट्रांस के साथ टिकट खरीद:

    यह एप्लिकेशन मिडट्रांस पेमेंट गेटवे का उपयोग करके ऑनलाइन टिकट बिक्री सेवाएं प्रदान करता है। उपयोगकर्ता आसानी से उन घटनाओं के लिए टिकट खरीद सकते हैं जो विभिन्न प्रकार के आरामदायक भुगतान विकल्पों के साथ मांग में हैं।

-   व्यवस्थापक अनुमोदन के साथ एक घटना करें:

    जो उपयोगकर्ता किसी ईवेंट को आयोजित करना चाहते हैं, वे इसे एप्लिकेशन के माध्यम से बना सकते हैं। हालाँकि, यह घटना व्यवस्थापक से अनुमोदन प्राप्त करने के बाद प्रकाशित की जाएगी। यह प्लेटफ़ॉर्म पर प्रदर्शित घटना की गुणवत्ता और प्रासंगिकता सुनिश्चित करने के लिए है।

-   इवेंट मेकर के लिए क्यूआर कोड स्कैन:

    यह सुविधा इवेंट मेकर को टिकट पर क्यूआर कोड को स्कैन करके आगंतुकों की उपस्थिति को आसानी से सत्यापित करने की अनुमति देती है। यह इवेंट मैनेजमेंट और टिकट सत्यापन को कुशलता से मदद करता है।

-   शेष राशि और आय वापस लें:

    इवेंट मेकर आवेदन द्वारा प्रदान की गई सुविधाओं के माध्यम से अपनी शेष राशि और आय को आकर्षित कर सकता है। यह घटना के आयोजक को उनके वित्तीय परिणामों को आसानी से प्रबंधित करने के लिए लचीलापन प्रदान करता है।

-   वास्तविक समय की अधिसूचना

    की मदद से_पृष्ठभूमि सेवा_(Android & iOS), उपयोगकर्ताओं को घटना की स्थिति, वापसी की स्थिति, खरीद और टिकट बिक्री के बारे में वास्तविक समय की सूचनाएं प्राप्त होगी।

## समर्थन और दान

[![Donate paypal](https://img.shields.io/badge/Donate-PayPal-green.svg?style=for-the-badge)](https://paypal.me/ikhsan3adi?country.x=ID&locale.x=en_US)[![Donate saweria](https://img.shields.io/badge/Donate-Saweria-red?style=for-the-badge&link=https%3A%2F%2Fsaweria.co%2Fxiboxann)](https://saweria.co/xiboxann)
