# Plan del hogar

Planning semanal de tareas del hogar para dos personas, con rotación, valoración por colores y marcador de puntos. Se instala en el móvil como una app y los datos se sincronizan entre los dos móviles con Firebase.

## Archivos

- `index.html`: la app completa.
- `config.js`: datos de conexión de Firebase (hay que rellenarlos).
- `database.rules.json`: reglas de seguridad para pegar en Firebase.
- `manifest.webmanifest`, `sw.js`, `icons/`: lo que permite instalarla y abrirla sin conexión.

## Configuración de Firebase (una sola vez)

1. Crea un proyecto en https://console.firebase.google.com (plan gratuito Spark).
2. En **Compilación > Realtime Database** pulsa **Crear base de datos**. Elige la región `europe-west1` y empieza en modo bloqueado.
3. En **Compilación > Authentication** pulsa **Comenzar**, activa **Correo electrónico/contraseña** y, en la pestaña **Usuarios**, añade dos usuarios: uno para cada persona, con correos en minúsculas.
4. En **Realtime Database > Reglas** pega el contenido de `database.rules.json`, cambia `CORREO_DE_ALBERTO` y `CORREO_DE_JARA` por los dos correos y pulsa **Publicar**.
5. En **Configuración del proyecto > Tus apps** añade una app web (icono `</>`), copia el objeto `firebaseConfig` y pega sus valores en `config.js`.
6. En **Authentication > Configuración > Acciones del usuario** desactiva el registro de usuarios si aparece esa opción.

## Publicar con GitHub Pages

En el repositorio: **Settings > Pages > Deploy from a branch > main / (root)**. La dirección queda como `https://TU_USUARIO.github.io/NOMBRE_DEL_REPO/`.

## Instalar en el móvil

- **iPhone (Safari):** compartir > **Añadir a pantalla de inicio**.
- **Android (Chrome):** menú de tres puntos > **Instalar aplicación** o **Añadir a pantalla de inicio**.

La primera vez, entra con tu correo y contraseña dentro de la app instalada y elige "Soy ...". La sesión se mantiene después.
