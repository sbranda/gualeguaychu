# Gualeguaychú, lunes a sábado — Guía interactiva (PWA)

Guía de viaje instalable: itinerario día por día (lunes por la tarde a sábado por la mañana), mapa interactivo, curiosidades, tips y checklist offline. Mismo esquema que la guía de Tucumán, con contenido propio de Gualeguaychú.

## Estructura

```
index.html      → la app completa
manifest.json   → metadata de la PWA (nombre, ícono, colores)
sw.js           → service worker para funcionamiento offline
icon-192.svg    → ícono chico
icon-512.svg    → ícono grande
```

## Itinerario incluido

- **Día 1 (lunes, tarde)** — Llegada en micro desde la Terminal de Liniers y primer paseo por la Costanera.
- **Día 2 (martes)** — Casco histórico: Plaza San Martín, Museo Casa de Haedo, Azotea de Lapalma y Teatro Gualeguaychú.
- **Día 3 (miércoles)** — Parque Unzué y Corsódromo / Museo del Carnaval.
- **Día 4 (jueves)** — Termas del Guaychú y Balneario Ñandubaysal.
- **Día 5 (viernes)** — Excursión de día completo al Delta: Villa Paranacito.
- **Día 6 (sábado, mañana)** — Última vuelta por el Puerto, compras y partida.
- **Día extra opcional (7 días)** — Museo Ferroviario, Instituto Magnasco y Puente Internacional Gral. San Martín.

Desde **Ajustes → Configurar días** se puede mover la fecha real de llegada y extender el viaje a 7 días; la app reordena las fechas y los días de la semana solos.

## Deploy en GitHub Pages (gratis, 5 minutos)

1. Creá un repo nuevo en GitHub, por ejemplo `gualeguaychu-guia`.
2. Subí estos 5 archivos a la raíz del repo (no en una subcarpeta).
3. Andá a **Settings → Pages**.
4. En "Source" elegí la rama `main` y carpeta `/ (root)`. Guardá.
5. Esperá 1-2 minutos. La URL queda en:
   `https://TU-USUARIO.github.io/gualeguaychu-guia/`

## Instalar como app

- **Android (Chrome)**: abrí la URL, va a aparecer un cartel para "Instalar app" o lo hacés manual desde el menú ⋮ → "Instalar app" / "Agregar a pantalla de inicio".
- **iPhone (Safari)**: abrí la URL → botón compartir (□↑) → "Agregar a pantalla de inicio".

Una vez instalada, abre en pantalla completa sin barra del navegador y el service worker cachea la app para que funcione aunque no haya señal (las fotos y el mapa sí necesitan internet la primera vez que se cargan).

## Actualizar contenido

Todo el contenido (itinerario, curiosidades, tips, checklist) está en los arrays `BLOCKS`, `TIPS`, `HISTORIA`, `EXTRAS` y `CHECKLIST_ITEMS` dentro de `index.html`, en el bloque `<script>`. Para editar, basta con tocar esos textos y volver a subir el archivo al repo — GitHub Pages se actualiza solo.

Si cambiás `sw.js` o agregás archivos nuevos al "app shell", subí también la versión del `CACHE_NAME` en `sw.js` (por ejemplo de `v1` a `v2`) para que los usuarios que ya instalaron la app reciban la actualización.

## Notas sobre los datos

- Las coordenadas de cada parada son aproximadas (a nivel de manzana/predio), suficientes para ubicarse en el mapa, no para navegación GPS de precisión.
- Los horarios de micros, precios de entradas y horarios de museos cambian con frecuencia — la app lo aclara en cada tip y conviene confirmarlos antes de viajar.
- Las fotos se cargan desde Wikimedia Commons; si algún archivo cambió de nombre o fue borrado, la app simplemente oculta esa imagen sin romper el resto de la tarjeta.
