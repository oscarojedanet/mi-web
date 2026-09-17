## 1. El menú móvil

- [x] 1.1 Añadir a `estilos.css` las reglas de la cabecera nueva: `<nav>` de escritorio visible desde 52rem, `<details>` de móvil visible por debajo, y quitar la regla que hoy esconde el menú sin dejar forma de abrirlo
- [x] 1.2 Dar estilo al `<summary>`: quitar el triángulo por defecto, altura mínima de 44 píxeles, y estado abierto con el panel a pantalla completa
- [x] 1.3 Sustituir la cabecera en los seis archivos HTML por la cabecera nueva, con el botón de escribir y la señal de página activa
- [x] 1.4 Comprobar en el navegador a 390 píxeles de ancho: el botón "Menú" abre el panel, los cinco enlaces se pulsan y el botón de cerrar devuelve a la página
- [x] 1.5 Comprobar a 1440 píxeles: se ve el menú en línea y no se ve el botón "Menú"
- [x] 1.6 Commit de la fase

## 2. La letra

- [x] 2.1 Crear la carpeta `fuentes/` y descargar `Geist-Regular.woff2` y `Geist-SemiBold.woff2`
- [x] 2.2 Guardar en `fuentes/` la licencia de Geist (SIL Open Font License) junto a los archivos
- [x] 2.3 Declarar las dos caras con `@font-face` en `estilos.css`, con `font-display: swap` y ruta relativa al proyecto
- [x] 2.4 Cambiar la pila tipográfica de `body` a Geist con las letras del sistema como reserva
- [x] 2.5 Revisar que en toda la hoja solo se usan los pesos 400 y 600, y corregir los 500 y 650 que hay hoy
- [x] 2.6 Comprobar en el navegador que la letra carga desde el proyecto y que no se hace ninguna petición a un servidor ajeno
- [x] 2.7 Commit de la fase

## 3. Fuera la decoración

- [x] 3.1 Borrar de `estilos.css` el bloque entero "Fondos decorativos, dibujados con CSS" y las reglas de apoyo que quedan huérfanas
- [x] 3.2 Borrar la regla `.figura` con sus cuatro aros, y el marcado de la figura en `index.html`
- [x] 3.3 Sustituir la separación entre secciones por líneas finas y cambios de fondo
- [x] 3.4 Ajustar los azules a `#14305e` y `#1e4a8f` y el gris de texto a `#525d6e` en las variables de `:root`
- [x] 3.5 Comprobar el contraste del texto claro sobre fondo azul y del texto secundario sobre fondo gris
- [x] 3.6 Commit de la fase

## 4. La portada

- [x] 4.1 Cambiar el titular por la frase-resumen de `marca.md`, con el resto de la frase como entradilla
- [x] 4.2 Montar la ficha del curso en la cabecera de la portada: cinco lecciones en `<ol>` con el punto numerado, y la línea del feedback
- [x] 4.3 Rehacer las tarjetas de los tres cursos con "llegas con" y "sales con", tomados de `marca.md`, dejando sitio para el precio sin mostrarlo
- [x] 4.4 Pasar las alternativas de rejilla de tarjetas a lista con líneas finas, dejando el azul solo para "Lo que hago yo"
- [x] 4.5 Marcar el hueco de la foto de Oscar en el bloque de quién está detrás
- [x] 4.6 Comprobar que no ha entrado ni una frase que no esté en `marca.md`
- [x] 4.7 Comprobar la portada en el navegador a 390 y a 1440 píxeles
- [x] 4.8 Commit de la fase

## 5. Las páginas de curso, sobre mí y contacto

- [ ] 5.1 Poner "con qué llegas" y "con qué sales" cara a cara en las tres páginas de curso
- [ ] 5.2 Montar la ficha de lo que incluye el curso, a la altura del contenido, con la llamada a escribir y sin precio
- [ ] 5.3 Aplicar el estilo nuevo de lecciones numeradas en `curso-marketing.html`
- [ ] 5.4 Actualizar `sobre-mi.html` y `contacto.html` con las piezas nuevas
- [ ] 5.5 Poner el pie nuevo en los seis archivos
- [ ] 5.6 Comprobar que desde cualquier página se llega a cualquier otra sin usar el botón atrás
- [ ] 5.7 Comprobar las seis páginas en el navegador a 390 y a 1440 píxeles
- [ ] 5.8 Commit de la fase

## 6. Cierre

- [ ] 6.1 Repasar que ningún archivo HTML lleva bloque `<style>` propio ni enlaza nada de fuera del proyecto
- [ ] 6.2 Comprobar que los títulos, las descripciones y el favicon de cada página siguen intactos
- [ ] 6.3 Enseñar el resultado a Oscar antes de archivar el cambio
