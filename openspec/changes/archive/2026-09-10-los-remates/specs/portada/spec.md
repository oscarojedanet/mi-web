## MODIFIED Requirements

### Requirement: Estilo y colores explícitos
La portada SHALL usar tipografía sans-serif limpia, azul oscuro como color de marca y el punto negro como elemento de identidad, según `marca.md`. Los estilos SHALL vivir en la hoja común `estilos.css` del proyecto, no en un bloque `<style>` dentro de la página. El fondo y los colores del texto SHALL declararse explícitamente en esa hoja. La página NO SHALL usar librerías ni dependencias externas: `estilos.css` es parte del proyecto.

#### Scenario: El navegador está en modo oscuro
- **WHEN** un visitante con el navegador en modo oscuro abre la portada
- **THEN** la página se ve con sus colores propios, sin heredar el modo oscuro ni quedar texto ilegible

#### Scenario: La portada se abre en el móvil
- **WHEN** un visitante abre la portada en la pantalla de un móvil
- **THEN** el texto se lee sin zoom y nada se sale de la pantalla

#### Scenario: Se cambia un color de marca
- **WHEN** hay que cambiar un color de la web
- **THEN** se cambia una sola vez en `estilos.css` y afecta a todas las páginas

### Requirement: Vía de contacto
La portada SHALL terminar con una llamada al contacto que lleve a `contacto.html`, y SHALL mostrar el correo contacto@oscarojeda.net como texto visible en el pie. El botón `mailto:` deja de vivir en la portada: ahora que existe una página de contacto, la portada la usa a ella.

#### Scenario: El visitante quiere escribir desde la portada
- **WHEN** el visitante pulsa la llamada al contacto del final de la portada
- **THEN** llega a la página de contacto, donde encuentra el correo y el botón que abre su gestor

#### Scenario: El visitante solo quiere ver la dirección
- **WHEN** el visitante busca la dirección de correo sin salir de la portada
- **THEN** la lee en el pie de página

## ADDED Requirements

### Requirement: La portada lleva a contacto y a sobre mí
La portada SHALL enlazar a `contacto.html` y a `sobre-mi.html`, además de a las tres páginas de servicio.

#### Scenario: El visitante quiere escribir o saber quién está detrás
- **WHEN** el visitante busca cómo contactar o quién enseña los cursos
- **THEN** encuentra en la portada un enlace a la página de contacto y otro a la de sobre mí
