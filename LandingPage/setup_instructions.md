# Configuración de Supabase y n8n para Captura de Datos

Sigue estos pasos para configurar una base de datos gratuita en Supabase y un flujo de trabajo en n8n para guardar la información de los nuevos clientes.

## 1. Configuración de Supabase

1.  **Crea una cuenta en [Supabase](https://supabase.com/).** El plan gratuito es suficiente.
2.  **Crea un nuevo proyecto.**
3.  **Ve al Editor SQL** (el ícono de la base de datos en el menú de la izquierda).
4.  **Crea una nueva tabla** para los clientes ejecutando el siguiente comando SQL:

    ```sql
    CREATE TABLE clientes (
      id SERIAL PRIMARY KEY,
      nombre_completo TEXT,
      email TEXT,
      telefono TEXT,
      nombre_empresa TEXT,
      fecha_registro TIMESTAMPTZ DEFAULT NOW()
    );
    ```

5.  **Obtén tus credenciales de API:**
    *   Ve a **Configuración del Proyecto** (el ícono de engranaje).
    *   Selecciona la pestaña **API**.
    *   Necesitarás la **URL** y la clave **`anon` `public`**.

## 2. Actualizar `welcome.html`

A continuación, modificaré el archivo `welcome.html` para que envíe los datos a Supabase. Solo necesitarás reemplazar los valores `TU_SUPABASE_URL` y `TU_SUPABASE_ANON_KEY` con tus propias credenciales.

## 3. Flujo de Trabajo en n8n

Este flujo de trabajo se activará cada vez que se registre un nuevo cliente en Supabase.

1.  **Importa el JSON del archivo `new_client_workflow.json` en tu instancia de n8n.**
2.  **Configura el "Supabase Trigger":**
    *   Conecta tu cuenta de Supabase a n8n.
    *   Asegúrate de que la tabla seleccionada sea `clientes`.
    *   Activa el flujo de trabajo.

Ahora, cada vez que un cliente complete el formulario en `welcome.html`, sus datos se guardarán en Supabase y el flujo de trabajo de n8n se ejecutará.
