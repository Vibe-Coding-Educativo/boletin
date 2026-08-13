# Publicador de Boletín (proyecto externo)

Este repositorio solo aloja la web (cliente). Las filas de la hoja de cálculo las escribe la fase 3 de `automatizaciones/boletin-semanal`, con una cuenta de servicio de Google. El Google Apps Script que se usaba antes está retirado.

Lo que sigue es el esquema de columnas que la web espera encontrar en el CSV.

## Esquema de columnas (orden obligatorio)
1. `new Date()` (marca de tiempo)
2. `id_boletin`
3. `fecha_publicacion`
4. `titulo_boletin`
5. `resumen`
6. `cuerpo_principal_md`
7. `enlace_podcast_youtube`
8. `seccion_faq`
9. `palabras_clave`
10. `audio` (URL directa; usar "" si no hay audio)

Notas:
- `audio` debe ser la última columna. Formatos válidos: mp3, ogg, wav, m4a, aac, flac, webm. Evita acentos o saltos de línea.
- Si `link` ya es una URL de audio idéntica a `audio`, no dupliques reproductores; la web ya evita duplicados.

## Flujo recomendado
- La fase 3 de `automatizaciones/boletin-semanal` añade la fila en la hoja `boletin`, y valida el borrador antes de escribir.
- Comprueba que la hoja incluye la columna `audio` al final. La rellena la fase 6 con la URL del MP3 en Internet Archive.

## Publicación del CSV
- Asegúrate de que la hoja esté publicada como CSV y su URL esté referenciada por año en `config.json` de este repositorio.
