# Publicador de Boletín (proyecto externo)

Este documento aclara cómo debe funcionar el proyecto externo de Google Apps Script que inserta nuevas filas en la hoja de cálculo. Este repositorio solo aloja la web (cliente) y la guía para generar contenidos.

## Enlace del editor
- Usa el editor de Apps Script indicado en `guia_estilo.md` para el proyecto "Publicador de Boletín VCE".

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
- Tras aprobar el borrador (generado según `guia_estilo.md`), pega el Apps Script que añade una nueva fila con los 10 campos en la hoja `boletin` del Spreadsheet configurado.
- Comprueba que la hoja incluye la columna `audio`. Si no existe, añádela al final antes de ejecutar el script.

## Publicación del CSV
- Asegúrate de que la hoja esté publicada como CSV y su URL esté referenciada por año en `config.json` de este repositorio.
