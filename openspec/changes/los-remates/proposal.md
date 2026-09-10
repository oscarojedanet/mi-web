## Why

La web tiene portada y las tres páginas de servicio, pero le faltan las dos páginas que el mapa de la lección 2 ya anunciaba: contacto y sobre mí. Además hay dos cosas sin rematar: los letreros con los que Google enseña cada página, y la pestaña del navegador, que hoy sale sin icono.

Y hay una deuda con fecha de vencimiento: el CSS está copiado en cada archivo. Con seis páginas, cambiar un color costaría seis ediciones. El acuerdo de la obra anterior era pagarla ahora, con el patrón completo a la vista.

## What Changes

- Página de contacto nueva (`contacto.html`): el correo contacto@oscarojeda.net visible y un botón que abre el gestor de correo ya dirigido a Oscar. Solo correo: sin teléfono, sin WhatsApp y sin formulario.
- Página de sobre mí nueva (`sobre-mi.html`): la historia de Oscar tal como está confirmada en `marca.md` — los diez años en marketing para empresas, el cansancio de las plantillas, y por qué eligió a los que empiezan solos.
- Título y descripción propios en las seis páginas, escritos para lo que Google enseña: qué es la página y de quién.
- Favicon: el punto negro de la marca sobre fondo blanco, en SVG.
- Las dos páginas nuevas se enlazan desde la portada y desde el resto de páginas, y la cabecera y el pie de todas se amplían para incluirlas.
- **El CSS común se saca a `estilos.css`.** Las seis páginas pasan a enlazarlo en vez de llevar su propio bloque de estilos.

## Capabilities

### New Capabilities
- `contacto`: la página de contacto — qué vías ofrece y cuáles quedan explícitamente fuera de esta fase.
- `sobre-mi`: la página de la historia de Oscar — qué cuenta y de dónde salen sus textos.
- `letreros-y-marca`: los títulos y descripciones de cada página y el favicon — lo que se ve fuera de la web (buscador y pestaña).

### Modified Capabilities
- `portada`: gana los enlaces a contacto y sobre mí, y pasa a usar el CSS común.
- `paginas-de-servicio`: ganan los enlaces a contacto y sobre mí, y su regla de estilo pasa a decir que la coherencia se consigue con la hoja común, no copiando el bloque de estilos.

## Impact

- Dos archivos nuevos: `contacto.html` y `sobre-mi.html`.
- Un archivo nuevo de estilos: `estilos.css`.
- Un archivo nuevo de icono: `favicon.svg`.
- Las cuatro páginas existentes se modifican: pierden su bloque `<style>`, ganan el enlace a `estilos.css`, el enlace al favicon y los enlaces de navegación a las dos páginas nuevas.
- Sigue sin haber dependencias externas: `estilos.css` y `favicon.svg` viven en el propio proyecto.
- Riesgo concentrado: se tocan las seis páginas a la vez. El paseo completo por la web es obligatorio antes de publicar.
