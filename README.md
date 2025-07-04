# Boletín Vibe Coding Educativo

## Descripción

Este proyecto es una página web que muestra de forma interactiva los boletines semanales generados a partir de las conversaciones del grupo de Telegram [Vibe Coding Educativo](https://t.me/vceduca). La página carga los datos desde un archivo CSV alojado en Google Sheets y los presenta en un formato de tarjetas fácil de navegar y filtrar.

## Características

* **Visualización de Boletines**: Muestra cada boletín en una tarjeta con su título, resumen y fecha.
* **Búsqueda y Filtros**: Permite buscar por texto y filtrar los boletines por año, mes y semana.
* **Vista Detallada**: Al hacer clic en un boletín, se abre una vista modal con el contenido completo, incluyendo el cuerpo principal y una sección de preguntas frecuentes (FAQ).
* **Diseño Adaptable (Responsive)**: La interfaz se adapta a diferentes tamaños de pantalla, desde ordenadores de escritorio hasta dispositivos móviles.
* **Modo Oscuro/Claro**: Permite cambiar entre un tema, claro y oscuro para una mejor experiencia de lectura.
* **Enlaces directos**: Cada boletín tiene una URL única que se puede compartir para acceder directamente a él.
* **Reproductor Integrado**: Si el boletín incluye un enlace a un pódcast o vídeo de YouTube, se muestra un reproductor multimedia incrustado.

## Tecnologías utilizadas

* **HTML5**: Para la estructura de la página.
* **Tailwind CSS**: Para el diseño y los estilos de la interfaz.
* **JavaScript (Vanilla)**: Para toda la lógica de la aplicación, incluyendo la carga de datos, el filtrado, la renderización de componentes y la interactividad.
* **Marked.js**: Para convertir el contenido de los boletines (escrito en Markdown) a HTML.

## Cómo funciona

1.  Los datos de los boletines se gestionan en una hoja de cálculo de **Google Sheets**.
2.  La hoja de cálculo se publica como un archivo **CSV**.
3.  La aplicación web, mediante JavaScript, realiza una petición para obtener este archivo CSV.
4.  El JavaScript procesa el CSV, lo convierte a un formato de objetos (JSON) y lo utiliza para renderizar dinámicamente el contenido en la página HTML.

## Autor

* **Juan José de Haro**: [https://bilateria.org](https://bilateria.org)

## Licencia

Este proyecto se distribuye bajo la licencia **Creative Commons Atribución-CompartirIgual 4.0 Internacional (CC BY-SA 4.0)**.

[![Licencia Creative Commons](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-sa/4.0/)
