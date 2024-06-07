## Servicio de fondo (NestJS)

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

Incluye una aplicación de panel de administración.

    apps/api
    apps/admin-panel

### Requisitos del sistema

Asegúrese de que su sistema cumpla con los siguientes requisitos antes de comenzar la instalación:

-   Node.js v18 o superior
-   PostgreSQL 15 o superior
-   Redis v5 o superior

### Pasos de instalación

1.  Clonar/extraer repositorio

2.  Instalar dependencias:

```bash
npm i
```

#### Entorno de configuración

-   Rebautizar`.env.example`a`.env`

#### Configurar base de datos

-   Arreglar`DATABASE_URL`De`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Ejecute la migración para crear las tablas requeridas.

```bash
npx prisma migrate deploy
```

-   Ejecute el sembrador de base de datos para crear usuarios.`superadmin`

```bash
npm run db:seed
```

#### Configuración**Iniciar sesión en Google**ID de servidor y cliente

-   Crear un nuevo proyecto en[Consola de Google Cloud](https://console.cloud.google.com/projectcreate)

-   Una vez que haya terminado de crear un proyecto, selecciónelo`APIs & Services`, luego seleccione`OAuth consent screen`En el lado izquierdo

-   Introduzca el nombre de la aplicación, el correo electrónico y`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Servidor**Identificación del cliente

    -   Seleccionar`Credentials`en la barra lateral izquierda, haga clic`CREATE CREDENTIALS`, seleccionar`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Seleccionar`Web application`tipo de aplicación, beri nama lalu guardar/crear

    ![Cloud Console](/assets/Screenshot_3.png)

-   Traducción`Client ID`y`Client secret`Di`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Aplicación Web**Identificación del cliente

    -   `CREATE CREDENTIALS`atrás, seleccione`OAuth client ID`

    -   Seleccionar`Web application`tipo de aplicación, proporcione un nombre y`Authorized JavaScript origins`como en la imagen (si usa localhost), luego guarde/cree

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Traducción`Client ID`y`Client secret`Di`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Hacer clic`DOWNLOAD JSON`y guarde la ID del cliente. El ID de cliente web se utilizará en la aplicación móvil de Flutter.

#### Configurar el servidor midtrans y la clave del cliente

-   Ir a[Transmisión intermedia del tablero](https://dashboard.midtrans.com/), seleccione el entorno`sandbox`(recomendado) atau`production`
-   Entrar a`Settings`>`Access Keys`, luego copie las claves del cliente y del servidor al archivo`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   Configuración variable`.env`otros según sea necesario.

### Como correr

1.  Generar`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  Ejecutar aplicación

```bash
npm run start
```

-   Modo de desarrollo

```bash
npm run start:dev
```

2.  Documentos de la API de Swagger

-   Abra http&#x3A;//localhost:3000/api/docs (ajuste la URL base)

3.  Prueba (opcional)

```bash
npm test
```

### Capturas de pantalla

![Swagger API Docs](/assets/swagger.png)
