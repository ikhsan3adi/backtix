# AtrásTix

> Aplicación de código abierto para eventos y venta de entradas

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

Esta aplicación de creación de eventos y venta de entradas en línea es una plataforma que facilita a los usuarios el acceso y la participación en diversos eventos. A continuación se muestra la descripción.
Brevemente las principales características de la aplicación:

-   Autenticación:

    La aplicación ofrece autenticación segura a través de JSON Web Token (JWT) y Google Sign-In. Los usuarios pueden iniciar sesión fácilmente en sus cuentas con métodos de autenticación convenientes y seguros.

-   Activación de cuenta por correo electrónico:

    Para aumentar la seguridad y garantizar la autenticidad del usuario, la aplicación requiere la activación de la cuenta por correo electrónico. Los usuarios recibirán un código de activación para confirmar y activar su cuenta.

-   Búsqueda de eventos cercanos:

    Los usuarios pueden buscar eventos que tengan lugar más cerca de su ubicación. Esta función permite a los usuarios descubrir y participar en eventos organizados en torno a ellos.

-   Compra de boletos con Midtrans:

    Esta aplicación brinda servicios de venta de boletos en línea utilizando la pasarela de pago Midtrans. Los usuarios pueden comprar fácilmente entradas para eventos de su interés con una variedad de cómodas opciones de pago.

-   Crear un evento con la aprobación del administrador:

    Los usuarios que quieran realizar eventos pueden crearlos a través de la aplicación. Sin embargo, el evento se publicará después de obtener la aprobación del administrador. Esto es para garantizar la calidad y relevancia de los eventos mostrados en la plataforma.

-   Escanee el código QR para el creador de eventos:

    Esta función permite a los creadores de eventos verificar fácilmente la asistencia de los visitantes escaneando el código QR en el boleto. Esto ayuda a una gestión eficiente de eventos y a la validación de entradas.

-   Retirar Saldo e Ingresos:

    Los creadores de eventos pueden retirar su saldo y ganancias a través de la función de retiro proporcionada por la aplicación. Esto brinda a los organizadores de eventos la flexibilidad de administrar sus resultados financieros con facilidad.

-   Notificaciones en tiempo real

    Con la ayuda de_servicio en segundo plano_(Android e IOS), los usuarios recibirán notificaciones en tiempo real sobre el estado del evento, el estado de los retiros, la compra y venta de boletos.

## Pila de tecnología

-   Servicio API/back-end

    -   [NestJS 10](https://nestjs.com/)Mecanografiado
    -   Prisma ORM
    -   PostgreSQL
    -   Redis
    -   Arrogancia (documentos API)

-   Panel de administración web (Monorepo con servicio API)

    -   [EsbeltoKit 2](https://kit.svelte.dev/)Mecanografiado
    -   Componente de interfaz de usuario Flowbite
    -   CSS de viento de cola

-   Aplicación movil

    -   [Aleteo 3](https://flutter.dev/)
        -   Bloque político
        -   Congelado
        -   Retroadaptación
        -   fpdart

## Código fuente

<a href="https://github.com/ikhsan3adi/backtix-app">
  <img height='25em' src="https://img.shields.io/badge/BackTix_App-027DFD?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

<a href="https://github.com/ikhsan3adi/backtix-service">
  <img height='25em' src="https://img.shields.io/badge/BackTix_Api_Service & Admin panel-ea2845?style=for-the-badge&logo=github&logoColor=white" title="ikhsan3adi" />
</a>

## Instalación y_Como correr_

[Servicio API de back-end](docs/api-service.md)

[Panel de administrador](docs/admin-panel.md)

[Aplicación movil](docs/mobile-app.md)
