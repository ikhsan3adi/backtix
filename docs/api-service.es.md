## Servicio de back-end (Nestjs)

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

Incluye el panel de aplicación de administración en él

    apps/api
    apps/admin-panel

### Requisitos del sistema

Asegúrese de que su sistema cumpla con los siguientes requisitos antes de comenzar la instalación:

-   Node.js v18 o superior
-   PostgreSQL 15 o superior
-   Redis v5 o superior

### Pasos de instalación

1.  Repositorio de clon/extracto

2.  Instalar dependencias:

```bash
npm i
```

#### Entorno de configuración

-   Rebautizar`.env.example`a`.env`

#### Base de datos de configuración

-   Colocar`DATABASE_URL`De`.env`

```sh
DATABASE_URL="postgresql://<username>:<password>@<host>:5432/<db-name>?schema=public"

# example
DATABASE_URL="postgresql://postgres:postgre123@localhost:5432/backtix?schema=public"
```

-   Ejecutar la migración para hacer la tabla requerida

```bash
npx prisma migrate deploy
```

-   Ejecute el sembrador de la base de datos para crear un usuario`superadmin`

```bash
npm run db:seed
```

#### Configuración**Iniciar sesión en Google**ID de servidor y cliente

-   Crear un nuevo proyecto en[Consola de Google Cloud](https://console.cloud.google.com/projectcreate)

-   Una vez terminado de hacer el proyecto, seleccione`APIs & Services`, luego elige`OAuth consent screen`a la izquierda

-   Ingrese el nombre de la aplicación, correo electrónico y`Developer contact information`

![Cloud Console](/assets/Screenshot_1.png)

-   **Servidor**ID de cliente

    -   Elegir`Credentials`En la barra lateral izquierda, haga clic`CREATE CREDENTIALS`, elegir`OAuth client ID`

    ![Cloud Console](/assets/Screenshot_2.png)


-   Elegir`Web application`Tipo de aplicación, beri nama lalu save/create

    ![Cloud Console](/assets/Screenshot_3.png)

-   Traducción`Client ID`Y`Client secret`Archivo de`.env`

    ```sh
    # google oauth
    SERVER_GOOGLE_CLIENT_ID=
    SERVER_GOOGLE_CLIENT_SECRET=
    ```

-   **Aplicación web**ID de cliente

    -   `CREATE CREDENTIALS`Volver, elija`OAuth client ID`

    -   Elegir`Web application`Tipo de aplicación, nombre y`Authorized JavaScript origins`Como en la imagen (si usa localhost), entonces guarde/cree

    ![Cloud Console](/assets/Screenshot_4.png)

    -   Traducción`Client ID`Y`Client secret`Archivo de`.env`

    ```sh
    # optional web only
    WEB_APP_GOOGLE_CLIENT_ID=
    WEB_APP_GOOGLE_CLIENT_SECRET=
    ```

    -   Hacer clic`DOWNLOAD JSON`y guardar la identificación del cliente. La identificación del cliente web se utilizará en el aleteo de la aplicación móvil.

#### Configuración de la tecla Midtrans Server y Cliente

-   Ir a[Dashboard Midtrans](https://dashboard.midtrans.com/), Seleccionar entorno`sandbox`(recomendado) o`production`
-   Ingresar`Settings`>`Access Keys`luego copie la clave del cliente y el servidor al archivo`.env`

```sh
# sandbox
MIDTRANS_URL=https://app.sandbox.midtrans.com/snap/v1/transactions
# production
MIDTRANS_URL=https://app.midtrans.com/snap/v1/transactions

MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
```

-   Configuración variable`.env`otros según sea necesario.

### Cómo correr

1.  Generar`metadata`:

```bash
npm run metadata --workspace=@backtix-service/api
```

2.  Ejecutar la aplicación

```bash
npm run start
```

-   Modo de desarrollo

```bash
npm run start:dev
```

2.  Swagger API Docs

-   Abra http&#x3A; // localhost: 3000/fire/docs (ajuste la URL base)

3.  Prueba (opcional)

```bash
npm test
```

### Capturas de pantalla

![Swagger API Docs](/assets/swagger.png)
