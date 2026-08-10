# Cómo publicar una entrada en el blog

Publicar una entrada son **tres pasos**: crear la página, añadir la tarjeta al listado y desplegar.
Esta carpeta (`blog/_plantillas/`) es solo material de trabajo: está excluida de los buscadores
en `robots.txt` y no aparece enlazada desde ninguna parte de la web.

---

## Paso 1 — Crear la página de la entrada

1. Elige un **slug**: minúsculas, sin tildes ni eñes, palabras separadas por guiones.
   Ejemplo: `redes-de-bots-elecciones-moldavia`.
2. Crea la carpeta `blog/<slug>/` y copia dentro `_plantillas/post.html` con el nombre `index.html`.
   La URL final será `https://falcoinsights.com/blog/<slug>/`.

   ```bash
   mkdir -p blog/redes-de-bots-elecciones-moldavia
   cp blog/_plantillas/post.html blog/redes-de-bots-elecciones-moldavia/index.html
   ```

3. Abre el `index.html` nuevo y sustituye los marcadores. Están en dos zonas:

   **a) En la cabecera del archivo** (primeras líneas, es lo que ven Google y LinkedIn):
   - `<title>` → `TITULAR DE LA ENTRADA – Falco Insights`
   - `meta name="description"` → resumen de 150-155 caracteres
   - `link rel="canonical"`, `og:url` → sustituye `SLUG-DE-LA-ENTRADA` por tu slug
   - `og:title`, `og:description` → mismo titular y resumen
   - `og:image` → ruta de la imagen de portada (importante: es la miniatura al compartir en LinkedIn)
   - `article:published_time` → fecha en formato `AAAA-MM-DD`

   **b) En el cuerpo del artículo** (busca las mayúsculas):
   - `TITULAR DE LA ENTRADA`, la entradilla, la firma y la fecha
   - `AN&Aacute;LISIS` → la categoría que corresponda (ver lista abajo)
   - `AAAA-MM-DD` y `DD de MES de AAAA` → fecha de publicación
   - `X min de lectura` → cuenta unas 200 palabras por minuto
   - `NOMBRE-DE-LA-IMAGEN.jpg` → imagen de `/imagenes/genericas/` o una nueva que subas

4. Borra los bloques opcionales que no uses. Están marcados con comentarios:
   imagen de portada, caja de claves, cita destacada e imagen interior.

> **Tildes y eñes:** el archivo está en UTF-8, puedes escribir acentos directamente en el texto.
> Los `&aacute;` de la plantilla son entidades HTML heredadas y funcionan igual; no hace falta imitarlas.

## Paso 2 — Añadir la tarjeta al listado

1. Abre `blog/index.html` y busca el bloque `<div class="falco-blog-grid" id="falco-blog-grid">`.
2. Copia dentro el contenido de `_plantillas/tarjeta.html` y rellena los mismos datos
   (slug, titular, fecha, categoría, imagen y resumen).
3. **La entrada más reciente va siempre la primera.** Si quieres que ocupe todo el ancho como
   pieza destacada, añádele la clase `is-destacado`:
   `<article class="falco-post-card is-destacado" data-categoria="analisis">`
   Solo una tarjeta destacada a la vez, y siempre la primera.
4. Cuando publiques la primera entrada, el aviso de "estamos preparando las primeras
   publicaciones" desaparece solo. No hay que tocar nada.

## Paso 3 — Publicar

```bash
git add .
git commit -m "Publica entrada: <titular>"
git push
```

Netlify despliega solo en un par de minutos. Conviene añadir también la URL nueva a
`sitemap.xml` (en la raíz del repo) para que Google la indexe antes.

---

## Categorías disponibles

El valor de `data-categoria` en la tarjeta controla los filtros del listado. Usa uno de estos
(o varios separados por espacio, p. ej. `data-categoria="analisis influenza"`):

| `data-categoria` | Etiqueta visible | Para qué |
|---|---|---|
| `analisis` | ANÁLISIS | Análisis propios de casos, campañas o narrativas |
| `actualidad` | ACTUALIDAD | Noticias y comentarios breves sobre hechos recientes |
| `metodologia` | METODOLOGÍA | Marcos, técnicas y divulgación (Cialdini, FCAME, TTPs...) |
| `influenza` | INFLUENZA | Novedades y capacidades de la plataforma |

Si añades una categoría nueva, hay que crear también su botón en `blog/index.html`
(bloque `<div class="falco-blog-filtros">`). Los filtros sin ninguna entrada se ocultan solos.

## Comprobar antes de publicar

```bash
python3 -m http.server 8000      # desde la raíz del repo
```

Abre `http://localhost:8000/blog/` y revisa el listado y la entrada nueva, también
estrechando la ventana para ver cómo queda en móvil.
