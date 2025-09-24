# Guía de Publicación de la Landing Page

Aquí tienes los pasos para publicar tu landing page y la página de bienvenida en un servicio de hosting gratuito como Vercel o Netlify.

## Prerrequisitos

*   Una cuenta de [GitHub](https://github.com/).
*   Una cuenta de [Vercel](https://vercel.com/) o [Netlify](https://www.netlify.com/).

## Paso 1: Sube tu Proyecto a GitHub

1.  **Crea un nuevo repositorio en GitHub.**
2.  **Sube la carpeta `LandingPage`** a este repositorio. Asegúrate de que todos los archivos (`index.html`, `welcome.html`, `BoostifyPro 13 cuadrada.png`, etc.) estén incluidos.

## Paso 2: Despliega tu Sitio con Vercel (Recomendado)

1.  **Inicia sesión en Vercel** con tu cuenta de GitHub.
2.  **Importa tu repositorio de GitHub:**
    *   Haz clic en **"Add New..."** y selecciona **"Project"**.
    *   Busca y selecciona el repositorio que acabas de crear.
3.  **Configura el proyecto:**
    *   Vercel detectará automáticamente que es un sitio estático. No necesitas cambiar ninguna configuración de compilación.
    *   Asegúrate de que el **"Root Directory"** apunte a la carpeta `LandingPage` si subiste toda la estructura del proyecto. Si solo subiste el contenido de la carpeta `LandingPage`, no necesitas hacer nada.
4.  **Despliega:**
    *   Haz clic en el botón **"Deploy"**.
    *   Vercel construirá y desplegará tu sitio. Una vez completado, te proporcionará una URL pública.

## Paso 3: Configura las Variables de Entorno (Supabase)

1.  **En tu proyecto de Vercel, ve a la pestaña "Settings" y luego a "Environment Variables".**
2.  **Añade las credenciales de Supabase:**
    *   Crea una variable llamada `SUPABASE_URL` con la URL de tu proyecto de Supabase.
    *   Crea otra variable llamada `SUPABASE_ANON_KEY` con tu clave anónima (`anon key`).
3.  **Actualiza tu código para usar estas variables:**
    *   Para que tu `welcome.html` pueda acceder a estas variables, necesitarás un pequeño servidor o una función sin servidor (serverless function) que las inyecte en el HTML. Vercel puede hacer esto automáticamente si cambias el nombre de tu archivo a `welcome.php` y usas un script de PHP, o si creas una función sin servidor.
    *   **Alternativa más sencilla (pero menos segura):** Pega directamente tus claves de Supabase en el archivo `welcome.html` antes de subirlo a GitHub. Esto es más fácil para empezar, pero no es la mejor práctica de seguridad.

## ¡Listo!

Tu landing page y tu página de bienvenida ahora están en línea. Cualquier cambio que hagas en tu repositorio de GitHub se desplegará automáticamente en Vercel.
