# PC Alto Rendimiento – Landing Interactiva

Proyecto web estático que presenta una configuración de PC de alto rendimiento (Ryzen 7 7800X3D + RTX 4070) orientada a eSports y creadores. Incluye cálculo de precio total, listado de componentes con copia y exportación CSV, galería interactiva con zoom/modal y formulario de contacto con validación accesible.

## Características
- Landing moderna y responsive con enfoque en rendimiento y claridad.
- Listado de componentes dinámico generado desde `app.js`.
- Cálculo de total estimado con interruptor para incluir/excluir el monitor (`localStorage`).
- Botón para copiar el listado completo al portapapeles.
- Exportación de componentes a CSV con codificación UTF‑8 BOM.
- Galería con carrusel, zoom progresivo y modal de imagen.
- Formulario de contacto con validación básica y mensajes de error.
- Metadatos SEO, Open Graph y `Schema.org Product` actualizados en tiempo real con el total.
- Buenas prácticas de accesibilidad: `skip-link`, roles/labels ARIA, `:focus-visible`.

## Estructura
```
├── index.html       # Página principal y contenido
├── styles.css       # Estilos base y componentes UI
├── app.js           # Lógica: datos, render, total, exportaciones, carrusel, formulario
└── images/          # Imágenes de componentes y medios
```

## Ejecución local
- No requiere dependencias ni build: abre `index.html` en tu navegador.
- Opcional: usa una extensión de servidor local (p. ej. Live Server) para una mejor experiencia.

## Personalización rápida
- Componentes: edita el arreglo `COMPONENTES` en `app.js`.
  - Rellena `url` con el enlace real del producto (reemplaza `PEGA_AQUI_URL_DEL_PRODUCTO`).
  - Ajusta `precio`, `tienda` y `nota` según tus fuentes.
- Imágenes: mapea categorías en `IMAGENES` y añade los archivos a `images/`.
- Metadatos SEO: cambia `<title>`, `<meta name="description">`, Open Graph y `canonical` en `index.html`.
- WhatsApp: actualiza el enlace `https://wa.me/XXXXXXXXX` en la sección "Precio y solicitud".
- Marca/branding: modifica la cabecera, logo y textos en `index.html` y estilos en `styles.css`.

## Cálculo del total
- El total se calcula sumando los precios de `COMPONENTES`.
- El interruptor "Incluir monitor en el total" persiste con `localStorage` usando la clave `incluyeMonitor`.
- El total se refleja en la UI y también sincroniza `lowPrice`/`highPrice` del JSON‑LD.

## Exportar datos
- Copiar listado: genera un texto con categoría, nombre, precio y enlace (si existe) y lo copia al portapapeles.
- Descargar CSV: crea `componentes.csv` con cabeceras `n;categoria;nombre;precio;moneda;tienda;url;nota`.

## Accesibilidad y UX
- `skip-link` para saltar al contenido.
- Estados de foco visibles (`:focus-visible`).
- Roles ARIA, labels y atributos `aria-*` en controles principales.
- Botones deshabilitados con `aria-disabled` cuando no hay URL de producto.

## Despliegue
- Al ser estático, puedes publicar el proyecto en cualquier hosting de archivos:
  - GitHub Pages, Netlify, Vercel (como sitio estático), o tu propio servidor.
- Asegúrate de mantener la ruta `images/` relativa.

## Compatibilidad
- Probado en navegadores modernos (Chromium/Firefox). No requiere polyfills.

## Notas
- Los precios son estimados y pueden variar por tienda y disponibilidad.
- Algunas imágenes son representativas del componente; sustituye por tus recursos propios si lo necesitas.