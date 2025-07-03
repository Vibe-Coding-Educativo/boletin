### Instrucciones para la IA: Generación de contenido para el Boletín Semanal

**Misión principal:** Tu tarea es procesar un archivo JSON que contiene las conversaciones semanales del grupo de Telegram "Vibe Coding Educativo". A partir de este análisis, debes generar el contenido necesario para rellenar los campos de un formulario. El resultado final debe ser un conjunto de textos, cada uno correspondiente a un campo específico.

A continuación se detalla el contenido que debes generar para cada campo del formulario.

### Contenido a generar por campo

#### 1. Campo: `id_boletin`
* **Tarea:** Genera un identificador único para el boletín.
* **Formato:** Utiliza el formato `AÑO-SEMANA_YYYY-MM-DD_YYYY-MM-DD`.
* **Ejemplo:** Para la semana del 30 de junio al 6 de julio de 2025 (que es la semana 27), el ID sería: `2025-27_2025-06-30_2025-07-06`.

#### 2. Campo: `fecha_publicacion`
* **Tarea:** Proporciona la fecha actual.
* **Formato:** Utiliza el formato `AAAA-MM-DD`.

#### 3. Campo: `titulo_boletin`
* **Tarea:** Crea un título que refleje de manera clara y concisa los temas principales del boletín.
* **Formato sugerido:** *"Boletín semanal de IA educativa: [tema destacado]"*.
* **Restricción:** Asegúrate de no repetir títulos de semanas anteriores.

#### 4. Campo: `resumen`
* **Tarea:** Escribe un párrafo breve y llamativo (2-3 frases) que resuma los puntos más destacados del boletín.

#### 5. Campo: `cuerpo_principal_md`
* **Tarea:** Este es el campo más extenso. Debes generar un texto completo en formato **Markdown** que contenga las siguientes secciones. Sigue esta estructura rigurosamente:

    * **Introducción:**
        * Escribe un párrafo que sirva de introducción general, señalando si hubo temas que generaron mayor debate o interés.
    * **Principales temas:**
        * Organiza los temas en secciones claras usando subtítulos (`### Título del Tema`).
        * Para cada tema, incluye: una explicación concisa, las reflexiones clave de los miembros, aplicaciones prácticas y enlaces a recursos con títulos descriptivos.
        * Prioriza los temas según su relevancia en las conversaciones.
    * **Aplicaciones de la comunidad:**
        * Crea una sección destacada con este título.
        * Identifica y lista **todas** las aplicaciones, herramientas o proyectos creados y compartidos por los miembros del grupo durante la semana.
        * Para cada aplicación, incluye el nombre de la misma, su autor (el miembro del grupo) y una breve descripción de su funcionalidad y el enlace correspondiente.
    * **Sección de otros enlaces compartidos:**
        * Crea una sección para incluir todos los enlaces que no fueron mencionados en las secciones anteriores.
        * Añade una breve descripción sobre el contenido de cada enlace.
    * **Definición de términos técnicos:**
        * Explica en orden alfabético los términos técnicos mencionados, de manera comprensible y con ejemplos educativos si es posible.
    * **Repositorio de la comunidad:**
        * Inserta una sección final destacada con el siguiente texto exacto:
        `### Visita nuestro repositorio de aplicaciones`
        `No olvides consultar el [Repositorio de Aplicaciones Educativas](https://vibe-coding-educativo.github.io/app_edu/) donde recopilamos todos los proyectos de la comunidad.`
    * **Nota final obligatoria:**
        * Incluye la siguiente nota al final del todo: *"Este resumen ha sido generado por Gemini a partir de las conversaciones del grupo de Telegram [Vibe Coding Educativo](https://t.me/vceduca) y puede contener omisiones, errores o imprecisiones."*

#### 6. Campo: `enlace_podcast_youtube`
* **Tarea:** Este campo contendrá el enlace a un vídeo de YouTube o podcast. El dato será proporcionado directamente en la petición de generación. No debes buscarlo en el JSON de conversaciones.

#### 7. Campo: `seccion_faq`
* **Tarea:** Identifica en las conversaciones preguntas explícitas que hayan recibido respuestas claras y estructúralas como una lista de preguntas y respuestas. Si no las hay, deja este campo vacío.

#### 8. Campo: `palabras_clave`
* **Tarea:** Basándote en los temas principales, genera entre 5 y 7 palabras clave o etiquetas separadas por comas.

### Estilo, tonalidad y errores a evitar
* **Tonalidad:** Profesional pero accesible. Lenguaje claro y comprensible.
* **Claridad:** Párrafos concisos, estructura lógica.
* **Reflexión:** Si se tocan temas éticos, incluye una breve reflexión sobre sus implicaciones.
* **Errores prohibidos:**
    * No uses frases como *"este artículo"* o *"este enlace"*. Usa títulos descriptivos.
    * No uses jerga técnica sin explicarla.
    * Asegúrate de que **todos** los enlaces del JSON aparecen en el boletín.
    * Evita las palabras y expresiones prohibidas: *"bienvenidos," "explorar," "profundo," "en resumen," "en conclusión."*
