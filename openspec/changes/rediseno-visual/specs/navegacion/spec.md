## ADDED Requirements

### Requirement: Cabecera y pie en las seis páginas
Las seis páginas SHALL compartir la misma cabecera y el mismo pie. La cabecera SHALL llevar la marca (el punto y el nombre) enlazada a la portada, los enlaces a las tres páginas de curso y a sobre mí, y un botón de escribir que lleve a `contacto.html`. El pie SHALL repetir los enlaces, incluido contacto, y mostrar el correo contacto@oscarojeda.net como texto visible.

#### Scenario: El visitante quiere volver al inicio
- **WHEN** el visitante pulsa la marca de la cabecera desde cualquier página
- **THEN** llega a la portada

#### Scenario: El visitante busca la dirección de correo
- **WHEN** el visitante baja al pie de cualquier página
- **THEN** lee la dirección contacto@oscarojeda.net

#### Scenario: El visitante quiere escribir desde cualquier sitio
- **WHEN** el visitante está en cualquier página y decide contactar
- **THEN** encuentra el botón de escribir en la cabecera, sin buscar

### Requirement: El menú se abre en cualquier ancho de pantalla
El menú SHALL poder abrirse en cualquier ancho de pantalla. Cuando los enlaces no quepan en la cabecera, SHALL aparecer un botón que abra un panel con todos ellos. NO SHALL ocultarse el menú sin dejar forma de abrirlo.

#### Scenario: El visitante entra desde el móvil
- **WHEN** un visitante abre la web en una pantalla de 390 píxeles de ancho
- **THEN** ve un botón de menú en la cabecera, y al pulsarlo se despliegan los enlaces a las tres páginas de curso, sobre mí y contacto

#### Scenario: El visitante cierra el menú
- **WHEN** el panel del menú está abierto y el visitante decide no ir a ninguna parte
- **THEN** encuentra un botón de cerrar que le devuelve a la página donde estaba

#### Scenario: El menú funciona sin JavaScript disponible
- **WHEN** el navegador del visitante no ejecuta JavaScript
- **THEN** el menú se sigue pudiendo abrir y los enlaces se siguen pudiendo pulsar

### Requirement: Señal de dónde estás
La cabecera SHALL señalar la página en la que está el visitante, cuando esa página tenga enlace en el menú. Las páginas que no son la portada SHALL llevar además una línea de migas que enlace a la portada.

#### Scenario: El visitante está en la página de un curso
- **WHEN** el visitante abre `curso-marketing.html`
- **THEN** el enlace de marketing en la cabecera se distingue de los demás, y una línea de migas le ofrece volver a la portada
