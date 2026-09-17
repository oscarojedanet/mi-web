## Why

La web funciona pero no se parece a lo que dice `marca.md`. La marca pide "aire limpio, moderno y serio, sin ruido ni decoración de más" y hoy hay fondos de puntitos, aros decorativos en cinco secciones y una figura abstracta ocupando el mejor sitio de la portada. Además hay un fallo real: por debajo de 640 píxeles de ancho el menú de la cabecera desaparece (`display: none`) y no hay ningún botón para abrirlo, así que quien entra desde el móvil solo puede navegar con los enlaces del pie.

## What Changes

- **Se quita la decoración sobrante.** Fuera los fondos de puntitos (`.hero::before`, `.cabecera-curso::before`), los aros de las secciones (`.pruebas::before`, `.cursos::before`, `.suave::before`, `.contacto::before/after`, `.destacado::before/after`) y la figura de aros de la portada (`.figura`). Queda un único elemento gráfico en toda la web: el punto de la marca, que además pasa a numerar las lecciones.
- **La cabecera de la portada enseña el curso, no un adorno.** Donde estaba la figura abstracta va una ficha con las cinco lecciones y la condición del feedback.
- **Titular nuevo en la portada.** Pasa a ser la frase-resumen de `marca.md`: "El curso de marketing que no te da plantillas", con el resto de la frase como entradilla. **BREAKING** respecto al titular que fija hoy el spec de portada.
- **El menú funciona en móvil.** Botón "Menú" en la cabecera y panel a pantalla completa. Hoy no hay forma de abrirlo.
- **Tipografía propia del proyecto.** Se añade Geist (licencia SIL Open Font License, gratuita) en `fuentes/`, servida desde el propio proyecto. Hoy la web usa la letra que tenga cada ordenador, así que se ve distinta en cada sitio.
- **Las tarjetas de curso cuentan con qué llegas y con qué sales**, con el material que ya está en `marca.md`.
- **Ficha del curso en las páginas de servicio**: un recuadro con lo que incluye el curso y la llamada a escribir, al lado del contenido.
- **Sin precios.** Decisión de Oscar del 17 de septiembre de 2026: el maquetado deja sitio para añadirlos más adelante, pero no se muestra ninguna cifra ni se inventa.

## Capabilities

### New Capabilities
- `sistema-visual`: la hoja común `estilos.css` entendida como sistema — los colores con nombre, la tipografía servida desde el proyecto, las piezas que se repiten (botones, tarjetas, el punto) y el límite de decoración. Recoge y sustituye lo que hoy dicen de pasada los requisitos "Estilo y colores explícitos" de portada y "Estilo coherente con la portada" de páginas de servicio.
- `navegacion`: la cabecera y el pie que comparten las seis páginas, y la obligación de que el menú se pueda abrir en cualquier ancho de pantalla.

### Modified Capabilities
- `portada`: cambia el titular (ahora la frase-resumen de `marca.md`), la cabecera pasa a enseñar el curso en vez de una figura decorativa, y las tarjetas de curso añaden "con qué llegas" y "con qué sales". El requisito de estilo se va a `sistema-visual`.
- `paginas-de-servicio`: se añade la ficha del curso con lo que incluye. El requisito de estilo se va a `sistema-visual`.

## Impact

- **Archivos de la web**: `estilos.css` (reescritura), `index.html`, `curso-marketing.html`, `curso-cliente-ideal.html`, `curso-propuesta-de-valor.html`, `sobre-mi.html`, `contacto.html` (cabecera, pie y bloques afectados).
- **Archivos nuevos**: `fuentes/Geist-Regular.woff2` y `fuentes/Geist-SemiBold.woff2` (unos 80 KB entre los dos), más su licencia.
- **Dependencias externas**: ninguna nueva. La letra se descarga una vez y vive dentro del proyecto, igual que las imágenes, según la regla de `AGENTS.md`.
- **Contenido**: no se toca `marca.md` y no se escribe ningún texto que no salga de ahí.
- **Diseño de referencia**: el lienzo aprobado está en https://claude.ai/artifact/9SSMgTV8H1JSzg84P3xZ4S
