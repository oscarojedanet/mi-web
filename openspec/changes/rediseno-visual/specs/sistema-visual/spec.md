## ADDED Requirements

### Requirement: Un solo sitio para el estilo
Todo el estilo compartido de la web SHALL vivir en `estilos.css`. Ninguna página SHALL llevar su propio bloque `<style>` con estilo copiado, ni librerías ni dependencias externas. Los colores SHALL declararse una sola vez como variables con nombre en `:root`, y el fondo y el color del texto SHALL declararse explícitamente para que la página no herede el modo oscuro del navegador.

#### Scenario: Se cambia un color de marca
- **WHEN** hay que cambiar un color de la web
- **THEN** se cambia una sola vez en `estilos.css` y afecta a las seis páginas

#### Scenario: El navegador está en modo oscuro
- **WHEN** un visitante con el navegador en modo oscuro abre cualquier página
- **THEN** la página se ve con sus colores propios, sin texto ilegible

#### Scenario: El visitante navega entre páginas
- **WHEN** el visitante pasa de la portada a una página de curso
- **THEN** reconoce que sigue en la misma web: mismos colores, misma letra, misma cabecera

### Requirement: Tipografía propia servida desde el proyecto
La web SHALL usar una tipografía sans-serif propia, guardada dentro del proyecto en `fuentes/` y declarada con `@font-face` en `estilos.css`. La tipografía NO SHALL enlazarse desde el servidor de un tercero. SHALL declararse una pila de reserva de letras del sistema para que el texto se lea aunque el archivo no cargue, y `font-display: swap` para que nunca haya texto invisible mientras la letra llega.

#### Scenario: El visitante abre la web desde cualquier ordenador
- **WHEN** dos visitantes abren la misma página desde un Windows y desde un Mac
- **THEN** ambos ven la web con la misma letra

#### Scenario: El archivo de la letra no llega
- **WHEN** la conexión falla y el archivo de la tipografía no se descarga
- **THEN** el texto se lee igual con la letra de reserva del sistema, sin quedar invisible ni descolocado

#### Scenario: Se revisa de dónde sale la letra
- **WHEN** se inspeccionan las peticiones que hace la página al abrirse
- **THEN** ninguna va a un servidor ajeno: la tipografía sale del propio proyecto

### Requirement: Contención decorativa
La web SHALL tener un único elemento gráfico de identidad: el punto de la marca descrito en `marca.md`. NO SHALL usarse decoración de fondo (tramas de puntos, aros, degradados decorativos) que no aporte información. Las formas que sí SHALL existir son las que separan o agrupan contenido: líneas finas, fondos de sección y bordes de tarjeta.

#### Scenario: Se revisa una sección cualquiera
- **WHEN** se mira cualquier sección de cualquier página
- **THEN** no hay aros, tramas de puntos ni figuras abstractas de relleno

#### Scenario: Hace falta distinguir dos secciones seguidas
- **WHEN** dos secciones van una detrás de otra y hay que separarlas
- **THEN** se separan con una línea fina o un cambio de fondo, no con decoración

### Requirement: Piezas reutilizables con una sola forma
Los elementos que se repiten SHALL tener una sola definición en `estilos.css` y el mismo aspecto en todas las páginas: botón principal, botón secundario, enlace con flecha, tarjeta, etiqueta de sección y numeración de lecciones. La numeración de lecciones SHALL usar el punto de la marca con el número dentro.

#### Scenario: El mismo botón en dos páginas
- **WHEN** el botón de escribir aparece en la portada y en una página de curso
- **THEN** tiene el mismo tamaño, el mismo color y las mismas esquinas en las dos

#### Scenario: Se añade una página nueva más adelante
- **WHEN** se construye una página nueva
- **THEN** se arma con las piezas que ya existen en `estilos.css`, sin inventar variantes

### Requirement: El texto se lee y los enlaces se pulsan
El texto SHALL cumplir un contraste mínimo de 4,5 a 1 contra su fondo, salvo el texto de 24 píxeles o más, que SHALL cumplir 3 a 1. Los elementos que se pulsan SHALL medir al menos 44 píxeles de alto.

#### Scenario: Un visitante con poca vista lee un párrafo
- **WHEN** lee el texto secundario sobre su fondo
- **THEN** el contraste es suficiente para distinguirlo sin esfuerzo

#### Scenario: Un visitante pulsa un botón en el móvil
- **WHEN** intenta pulsar un botón con el dedo
- **THEN** el botón es lo bastante alto para acertar sin ampliar la página
