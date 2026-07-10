# Franco Motos — sitio web

Sitio de una sola página (`index.html`), sin build ni dependencias: se abre directo en el navegador
o se publica tal cual en GitHub Pages / Netlify / Vercel.

## Estructura

```
index.html
images/
  logo/            → logo de la marca
  hero/            → las 3 fotos grandes que rotan en el inicio
  icons/           → ícono de WhatsApp
  motos/
    <id-de-la-moto>/
      negro.jpg
      blanco.jpg
      rojo.jpg
      azul.jpg
      verde.jpg
```

Cada moto tiene su propia carpeta en `images/motos/`, nombrada igual que su "identificador interno"
(por ejemplo `images/motos/energy-110-full/`). Adentro, cada color tiene su propio archivo. **Si un
color no tiene foto, esa carpeta simplemente no tiene ese archivo** — el sitio automáticamente
muestra ese botón de color como "no disponible" (tachado), no rompe nada.

## Cómo agregar o cambiar una foto

1. Buscá (o creá) la carpeta `images/motos/<id-de-la-moto>/`.
2. Poné ahí el archivo con el nombre del color: `negro.jpg`, `blanco.jpg`, `rojo.jpg`, `azul.jpg`
   o `verde.jpg` (podés usar `.jpg`, `.png` o `.webp`, lo que tengas).
3. Andá al [panel interno](#panel-interno-oculto) y en el campo de ese color pegá la ruta, por
   ejemplo: `images/motos/energy-110-full/rojo.jpg`.
4. Generá el código, reemplazalo en `index.html`, subí los cambios al repo.

## Cómo agregar una moto totalmente nueva

1. Creá la carpeta `images/motos/<id-nuevo>/` y poné ahí las fotos que tengas (al menos una).
2. Entrá al panel interno, elegí "Moto nueva", completá los datos (el identificador se sugiere solo
   a partir del nombre).
3. En cada campo de color, escribí la ruta `images/motos/<id-nuevo>/<color>.jpg`.
4. Guardá en la lista, generá el código, reemplazalo en `index.html`, subí los cambios.

## Panel interno (oculto)

No está linkeado en ningún lado del sitio público. Se entra escribiendo esto en el navegador:

```
tusitio.com/index.html#panel-interno-fm
```

Clave por defecto: `francomotos2026` (buscá `CLAVE_ADMIN` dentro de `index.html` para cambiarla).

**Importante:** esto no es un backend. El panel te arma el bloque de código actualizado
(`const motos = [ ... ];`) para que lo copies y pegues vos mismo en `index.html`, reemplazando el
bloque existente, y subas el archivo de nuevo. Recién ahí lo ven los visitantes — no hay guardado
automático ni base de datos.

## Publicar cambios (GitHub Pages / Netlify / Vercel)

1. Editá `index.html` (a mano, o con el código que te da el panel interno).
2. Si agregaste fotos nuevas, asegurate de que estén dentro de `images/`.
3. Hacé commit y push a este repositorio.
4. Tu hosting (GitHub Pages / Netlify / Vercel) va a re-publicar el sitio automáticamente.

## Nota sobre las fotos de motoroma.com.ar

Varias fotos "blanco"/"rojo" que traía el sitio original apuntaban a motoroma.com.ar y esas URLs ya
no funcionan (devuelven error 404 — no es algo que rompimos nosotros, dejaron de estar disponibles
en el sitio de origen). Se sacaron para que no se vea un ícono de imagen rota; esos colores quedan
marcados como "no disponibles" hasta que subas una foto real en su carpeta correspondiente.
