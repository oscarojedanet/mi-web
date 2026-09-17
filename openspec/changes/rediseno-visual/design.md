## Context

La web son seis páginas HTML sueltas que comparten `estilos.css`. No hay build, no hay plantillas: la cabecera y el pie están copiados a mano en cada archivo. Eso condiciona todo lo de abajo — cualquier cambio en la cabecera se hace seis veces, así que conviene que la cabecera sea corta y que el trabajo se concentre en la hoja de estilos.

El diseño aprobado está en el lienzo https://claude.ai/artifact/9SSMgTV8H1JSzg84P3xZ4S, con cinco tableros: portada en escritorio, portada en móvil, menú móvil abierto, página de curso y sistema visual.

Restricciones que vienen de `AGENTS.md` y de `marca.md`:

- Sin librerías ni dependencias externas.
- Las imágenes y los archivos viven dentro del proyecto, nunca enlazados desde el servidor de otro.
- Los textos salen de `marca.md`. No se inventa nada.
- Azul oscuro como color de marca, punto negro como identidad, letra sans-serif limpia.

## Goals / Non-Goals

**Goals:**

- Que la web se parezca a lo que dice `marca.md`: limpia, seria, sin decoración de más.
- Que el menú se pueda abrir desde el móvil. Hoy no se puede.
- Que la portada enseñe el curso en lugar de una figura abstracta.
- Que la letra sea la misma en todos los ordenadores, sin depender de nadie.
- Que el estilo quede en un solo sitio, para que el próximo cambio sea barato.

**Non-Goals:**

- Precios. Decisión de Oscar: todavía no. El maquetado deja sitio.
- Fotos reales. No las hay aún. Donde va la foto de Oscar queda un hueco marcado, no una foto de banco.
- Modo oscuro. La web declara sus colores y punto.
- Tienda, carrito o pasarela de pago. Se vende por correo.
- Reescribir textos. Los que hay salen de `marca.md` y se conservan; solo cambia dónde y cómo se colocan.

## Decisions

### 1. La letra: Geist, dos pesos, dentro del proyecto

**Qué se hace:** se descargan `Geist-Regular.woff2` (peso 400) y `Geist-SemiBold.woff2` (peso 600) a `fuentes/`, con su licencia al lado, y se declaran con `@font-face` en `estilos.css`.

**Por qué Geist:** es gratuita (licencia SIL Open Font License, la misma familia de licencias que usan las tipografías de Google), sans-serif, de formas limpias y algo condensadas — la línea de Stripe y Trade Republic que pide `marca.md`. Está pensada para pantalla y se lee bien a tamaños pequeños.

**Por qué dentro del proyecto y no enlazada:** `AGENTS.md` lo dice para las imágenes y la razón es la misma aquí. Enlazar la letra desde el servidor de Google o de Vercel significa que la web deja de verse bien el día que ellos cambien algo, y que cada visitante hace una petición a un tercero. Descargada una vez, es nuestra para siempre.

**Por qué solo dos pesos:** cada peso es un archivo de unos 40 KB. Con 400 para el texto y 600 para los titulares hay contraste de sobra. Tres pesos serían 120 KB para una diferencia que casi nadie nota. Alternativa descartada: el archivo "variable" de Geist, que trae todos los pesos en uno (unos 60 KB) pero obliga a sintaxis `@font-face` más delicada; con dos pesos fijos no hay nada que pueda fallar.

**Red de seguridad:** se declara una pila de reserva (`system-ui`, `Segoe UI`, etc.) y `font-display: swap`. Si el archivo no llega, el texto se lee igual con la letra del sistema. Nunca hay texto invisible esperando a la letra.

### 2. El menú móvil: `<details>` y `<summary>`, sin JavaScript

**Qué se hace:** en la cabecera van dos cosas — un `<nav>` con los enlaces, que se ve en pantallas anchas, y un `<details><summary>Menú</summary>…</details>` con los mismos enlaces, que se ve en pantallas estrechas. CSS decide cuál se enseña según el ancho.

**Por qué `<details>`:** es HTML de toda la vida, pensado justo para esto: un botón que despliega contenido. Funciona sin una línea de JavaScript, se abre con el teclado y los lectores de pantalla lo anuncian correctamente, todo eso gratis. La alternativa habitual (una casilla de verificación escondida con CSS) hace lo mismo pero engañando al navegador, y los lectores de pantalla lo leen como "casilla sin marcar", que no es lo que es.

**Por qué sin JavaScript:** el proyecto no tiene ni un archivo `.js` y no hace falta que lo tenga. Un menú es abrir y cerrar; el navegador ya sabe hacerlo.

**Coste asumido:** los cinco enlaces aparecen dos veces en la cabecera, y la cabecera está copiada en seis archivos. Es la única duplicación que añade este cambio. La alternativa —un solo juego de enlaces que se transforme en menú desplegable con CSS— depende de un detalle del navegador que Chrome cambió hace poco y que no se comporta igual en Firefox y en Safari. Se prefiere markup un poco más largo y previsible antes que markup corto que un día se rompa solo.

### 3. La ficha del curso en la cabecera de la portada

**Qué se hace:** donde está `.figura` (el rectángulo azul con aros) va una tarjeta con las cinco lecciones numeradas y la línea del feedback.

**Por qué:** es el sitio más visto de la web y hoy lo ocupa un adorno. La tarjeta dice lo mismo que diría el visitante si le preguntaran "¿y esto qué es?": cinco lecciones, con nombre, y que las dudas las contesta Oscar. Es la misma idea que hay detrás de las referencias de `marca.md`: enseñar el producto, no decorar alrededor.

**Cómo se marca:** las lecciones van en una lista ordenada `<ol>`, porque son una lista ordenada. El número de cada lección es el punto de la marca con el número dentro, así el único elemento gráfico de la web trabaja en vez de decorar.

### 4. La decoración se va entera

**Qué se borra de `estilos.css`:** el bloque de "Fondos decorativos, dibujados con CSS" completo — las tramas de puntos de `.hero::before` y `.cabecera-curso::before`, los aros de `.pruebas::before`, `.cursos::before`, `.suave::before`, `.contacto::before/after` y `.destacado::before/after`, y la regla `.figura` con sus cuatro aros.

**Por qué de golpe y no poco a poco:** son un sistema, no adornos sueltos: todos dependen de `position: relative; overflow: hidden` en los contenedores y de `z-index: 1` en los hijos. Quitar la mitad deja reglas huérfanas que nadie sabrá para qué estaban. Se va el bloque entero y con él las reglas de apoyo.

**Qué ocupa su sitio:** líneas finas (`#e3e7ed`) y cambios de fondo (`#f6f7f9`) para separar secciones. Separan igual y no piden atención.

### 5. Los colores se quedan casi donde están

Los azules actuales (`#16305c`, `#23508f`) se ajustan a `#14305e` y `#1e4a8f`, un punto más profundos, y el gris de texto secundario sube de `#4d5766` a `#525d6e`. Son cambios de matiz, no de identidad: sigue siendo el mismo azul oscuro de `marca.md`. El motivo es el contraste — con la letra nueva y los tamaños nuevos, estos valores cumplen el mínimo de 4,5 a 1 en todos los sitios donde se usan, incluido el texto claro sobre fondo azul.

### 6. Un solo archivo de estilos

`estilos.css` sigue siendo uno solo, ordenado por secciones con comentarios. No se parte en varios archivos ni se añade ningún paso de compilación. Con seis páginas, un archivo que se lee de arriba abajo es más fácil de mantener que cinco archivos que hay que ir cruzando — y sobre todo, cualquiera puede abrirlo y entenderlo sin instalar nada.

## Risks / Trade-offs

- **Se tocan los seis archivos HTML a la vez** → se trabaja por fases y se hace un commit por fase, de modo que cualquier paso se puede deshacer solo. La fase 1 (el menú móvil) va primero porque arregla un fallo real y se sostiene aunque no se hiciera nada más.
- **La cabecera crece: los enlaces van dos veces** → asumido a conciencia en la decisión 2. A cambio, el menú no puede romperse.
- **La letra son dos archivos nuevos de 40 KB** → se cargan solo una vez y el navegador los guarda. Con `font-display: swap`, el texto se ve desde el primer instante aunque la letra tarde.
- **Los textos se recolocan y alguno se parte distinto** → todos salen de `marca.md` y ninguno se reescribe. Al terminar cada fase se comprueba que no ha entrado ni una frase que no estuviera en el material.
- **El hueco de la foto de Oscar queda a la vista** → es a propósito, y `AGENTS.md` lo respalda: mejor un hueco honesto que una foto de banco que habría que quitar después. Sale en cuanto haya foto real.

## Migration Plan

Cinco fases, cada una con su commit y cada una utilizable por sí sola:

1. **El menú móvil.** Arregla el fallo. Toca los seis HTML y `estilos.css`.
2. **La letra.** Descargar Geist a `fuentes/`, declararla, ajustar tamaños y pesos.
3. **Fuera la decoración.** Borrar el bloque decorativo de `estilos.css` y la figura de la portada.
4. **La portada.** Titular nuevo, ficha del curso en la cabecera, tarjetas con "llegas con" y "sales con", lista de alternativas.
5. **Las páginas de curso, sobre mí y contacto.** Ficha del curso, dolor y deseo juntos, y el pie nuevo.

Para volver atrás: cada fase es un commit, así que se deshace con `git revert` de ese commit sin tocar los demás.

## Open Questions

- **Los precios.** Oscar decidió el 17 de septiembre de 2026 no publicarlos todavía. Cuando dé las tres cifras, entran en las tarjetas y en la ficha sin rehacer nada.
- **La foto de Oscar.** El hueco está reservado en la portada. Falta la foto.
- **Testimonios de los 30 alumnos.** `marca.md` dice que hay 30 alumnos aplicándolo con resultados, pero no recoge ni una frase suya. Si algún día las hay, el sitio natural es debajo de las tres cifras de la portada.
