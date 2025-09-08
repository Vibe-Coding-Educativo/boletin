# Repository Guidelines

## Project Structure & Module Organization
- Raíz: `index.html` (UI), `script.js` (lógica/DOM), `style.css` (estilos adicionales), `favicon.svg`.
- Configuración: `config.json` (mapa año → CSV público), `tailwind.config.js`, `postcss.config.js`, `tailwind.css` (entrada de Tailwind).
- Dependencias: `package.json` + `node_modules/`. Salida CSS esperada en `dist/tailwind.css`.

## Build, Test, and Development Commands
- `npm ci`: instala dependencias bloqueadas por `package-lock.json`.
- `npm run dev:css`: compila Tailwind en modo watch a `dist/tailwind.css`.
- `npm run build:css`: compila y minifica Tailwind para producción.
- Desarrollo local: abrir `index.html` en navegador o servir con `python3 -m http.server 8000` y navegar a `http://localhost:8000`.

## Coding Style & Naming Conventions
- HTML con clases utilitarias Tailwind; ids/atributos en kebab-case (ej.: `year-selector`).
- JavaScript: `const/let`, camelCase para funciones/variables, UPPER_SNAKE para constantes. Indentación 2 espacios. Comentarios breves `//`.
- CSS: priorizar utilidades Tailwind; usar `style.css` solo para ajustes finos.
- Cadena de texto en español neutro; mantener tono y términos del proyecto.

## Testing Guidelines
- No hay test automatizados; validación manual en navegador.
- Verificar: carga de CSV (año actual), filtros (mes/semana/búsqueda), apertura de modal, reproducción de audio, deep-link `?boletin=...`, render Markdown (Marked.js) y embeds de YouTube.
- Audio: la última columna `audio` (URL directa) debe renderizarse solo si es distinta de `link`; en tarjetas y modal aparece con la etiqueta “🎧 Podcast (audio)”.
- Probar en tema claro/oscuro y en móvil/escritorio.

## Commit & Pull Request Guidelines
- Mensajes cortos en español. Prefiera Convencional Commits: `feat:`, `fix:`, `docs:`, `refactor:`, `chore:`. Ej.: `feat: soporte de índice en modal`.
- PR: descripción del cambio, motivación, pasos de prueba, capturas si afecta a UI, referencia a issue (`Closes #N`). Asegure que `npm run build:css` no rompe estilos.

## Security & Configuration Tips
- `config.json` contiene URLs públicas (CSV publicado); no incluir secretos.
- La app obtiene datos vía `corsproxy.io` y `raw.githubusercontent.com`. Mantener URLs públicas y verificables.

## Agent-Specific Instructions
- Mantener compatibilidad con `index.html` + `script.js`; cambios de UI mínimos y justificados.
- Durante depuración, ignorar el aviso de consola sobre `cdn.tailwindcss.com` para producción.
- Si prepara build de producción, sustituya el CDN por `dist/tailwind.css` y verifique en local.
