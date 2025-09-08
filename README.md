# Boletín Vibe Coding Educativo

## Descripción

Este proyecto es una aplicación web que presenta de forma interactiva los boletines semanales del grupo de Telegram [Vibe Coding Educativo](https://t.me/vceduca). La plataforma tiene un doble flujo de trabajo:

1.  **Generación de Contenido**: Se utiliza una guía de estilo (`guia_estilo.md`) como prompt para una IA que procesa las conversaciones de Telegram. La IA genera un borrador del boletín que, una vez validado, se publica en una hoja de cálculo de Google Sheets mediante un Google Apps Script (proyecto externo).
2.  **Visualización Web**: La aplicación web carga los datos desde la hoja de cálculo (publicada como CSV) y los presenta en un formato de tarjetas dinámicas con opciones de búsqueda y filtrado.

## Estructura del Proyecto

* `index.html`: Es el archivo principal que contiene la estructura HTML de la página.
* `style.css`: Contiene los estilos CSS personalizados que complementan a Tailwind CSS, incluyendo animaciones y temas, claro y oscuro.
* `script.js`: Contiene toda la lógica de la aplicación en JavaScript. Se encarga de cargar los datos desde el CSV, renderizar las tarjetas de los boletines, gestionar los filtros, la búsqueda, la visualización de modales y el cambio de tema.
* `config.json`: Archivo de configuración que almacena las URLs de los archivos CSV de Google Sheets para cada año.
* `guia_estilo.md`: Es el prompt detallado que se utiliza para instruir a la inteligencia artificial sobre cómo generar el contenido de cada boletín a partir de las conversaciones de Telegram y cómo crear el script de publicación (Apps Script externo).
* `README.md`: Este mismo archivo, con la documentación del proyecto.

## Flujo de Trabajo

### 1. Generación del Contenido del Boletín

El proceso se inicia con la `guia_estilo.md`, un prompt diseñado para una IA.

* **Análisis**: La IA procesa un JSON con las conversaciones de la semana del grupo de Telegram.
* **Creación del borrador**: Genera el contenido para 8 campos: `id_boletin`, `fecha_publicacion`, `titulo_boletin`, `resumen`, `cuerpo_principal_md`, `enlace_podcast_youtube`, `seccion_faq` y `palabras_clave`.
* **Validación y Publicación**: Tras la revisión humana del borrador, la IA genera un `Google Apps Script` que, al ejecutarse, inserta el contenido del boletín en la hoja de cálculo designada, aplicando el formato correcto.

### 2. Visualización en la Web

* **Carga de datos**: La aplicación web lee el archivo `config.json` para obtener la URL del CSV del año seleccionado.
* **Petición y Procesamiento**: Mediante JavaScript, realiza una petición para obtener el archivo CSV, lo procesa y lo convierte en objetos para su uso en la página.
* **Renderizado Dinámico**: El contenido se renderiza dinámicamente en la página, creando las tarjetas y la vista detallada para cada boletín.

## Características

* **Visualización de Boletines**: Muestra cada boletín en una tarjeta con su título, resumen y fecha.
* **Búsqueda y Filtros**: Permite buscar por texto y filtrar los boletines por año, mes y semana.
* **Vista Detallada**: Al hacer clic en un boletín, se abre una vista modal con el contenido completo, incluyendo el cuerpo principal y una sección de preguntas frecuentes (FAQ).
* **Diseño Adaptable (Responsive)**: La interfaz se adapta a diferentes tamaños de pantalla.
* **Modo Oscuro/Claro**: Permite cambiar entre un tema, claro y oscuro para una mejor experiencia de lectura.
* **Enlaces directos**: Cada boletín tiene una URL única que se puede compartir para acceder directamente a él.
* **Reproductor Integrado**: Si el boletín incluye un enlace a un pódcast o vídeo de YouTube, se muestra un reproductor multimedia incrustado. Si existe una columna `audio` con URL directa adicional (mp3/ogg/wav/m4a/aac/flac/webm) distinta de `link`, se añade un reproductor de audio con etiqueta.

## Publicación (proyecto externo)

Este repositorio NO contiene el código de publicación (Google Apps Script). Ese proyecto es independiente y se usa para insertar filas en la hoja de cálculo de destino.

- Editor del proyecto (Apps Script): ver enlace indicado en `guia_estilo.md`.
- Orden de columnas esperado en la hoja (CSV):
  1. Marca de tiempo
  2. id_boletin
  3. fecha_publicacion
  4. titulo_boletin
  5. resumen
  6. cuerpo_principal_md
  7. enlace_podcast_youtube
  8. seccion_faq
  9. palabras_clave
  10. audio (URL directa; "" si no hay audio)

Mantén la columna `audio` como la última para evitar incompatibilidades con el cliente web.

## Tecnologías utilizadas

* **HTML5**: Para la estructura de la página.
* **Tailwind CSS**: Para el diseño y los estilos de la interfaz.
* **JavaScript (Vanilla)**: Para toda la lógica de la aplicación.
* **Marked.js**: Para convertir el contenido de los boletines (escrito en Markdown) a HTML.
* **Google Apps Script**: Para automatizar la publicación de contenido en Google Sheets.

## Autor

* **Juan José de Haro**: [https://bilateria.org](https://bilateria.org)

## Licencia

Este proyecto se distribuye bajo la licencia **Creative Commons Atribución-CompartirIgual 4.0 Internacional (CC BY-SA 4.0)**.

[![Licencia Creative Commons](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-sa/4.0/)
