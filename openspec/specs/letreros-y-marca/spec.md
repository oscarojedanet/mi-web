# Letreros y marca

## Purpose

Lo que se ve de la web desde fuera: el título y la descripción con los que un buscador la enseña, y el icono que aparece en la pestaña del navegador.

## Requirements

### Requirement: Título propio en cada página
Cada página de la web SHALL tener su propio `<title>`, que diga qué es la página y de quién. NO SHALL repetirse el mismo título en dos páginas.

#### Scenario: Google enseña un resultado
- **WHEN** una página de la web aparece en un buscador
- **THEN** el titular que se ve es el `<title>` de esa página concreta, con el nombre de Oscar y el asunto de la página

#### Scenario: El visitante tiene varias pestañas abiertas
- **WHEN** el visitante abre dos páginas de la web a la vez
- **THEN** puede distinguirlas por el texto de la pestaña

### Requirement: Descripción propia en cada página
Cada página SHALL tener su `<meta name="description">` propia, de una o dos frases, escrita con material de `marca.md`.

#### Scenario: Google enseña el resumen del resultado
- **WHEN** una página aparece en un buscador
- **THEN** el texto de debajo del titular describe esa página en concreto, con las palabras del negocio y no con relleno genérico

### Requirement: Favicon de marca
La web SHALL tener un favicon propio: el punto negro de la marca sobre fondo blanco, servido desde el propio proyecto. Todas las páginas SHALL enlazarlo.

#### Scenario: El visitante abre cualquier página
- **WHEN** se abre cualquiera de las páginas de la web
- **THEN** la pestaña del navegador muestra el punto negro, no el icono genérico del navegador

#### Scenario: El icono se ve a tamaño mínimo
- **WHEN** el icono se muestra a 16 píxeles
- **THEN** sigue siendo reconocible, por ser una silueta simple y opaca sin trazos finos

### Requirement: Google tarda en leer los letreros
Los letreros SHALL considerarse puestos en cuanto están publicados, con independencia de cuándo los recoja un buscador.

#### Scenario: Los buscadores todavía muestran datos antiguos o ninguno
- **WHEN** se consulta el buscador poco después de publicar
- **THEN** puede no reflejar aún los títulos y descripciones nuevos, y eso no es un fallo de la web: los buscadores pasan a leer a su propio ritmo, de días a semanas
