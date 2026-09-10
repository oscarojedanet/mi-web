## ADDED Requirements

### Requirement: Página de contacto
La web SHALL tener una página `contacto.html` con el correo contacto@oscarojeda.net visible como texto y un botón que abra el gestor de correo con esa dirección ya puesta.

#### Scenario: El visitante quiere escribir
- **WHEN** el visitante pulsa el botón de contacto
- **THEN** se abre su gestor de correo con la dirección de Oscar en el destinatario

#### Scenario: El visitante prefiere copiar la dirección
- **WHEN** el visitante no usa un gestor de correo en ese dispositivo
- **THEN** puede leer y copiar la dirección, porque está escrita como texto visible y no solo dentro del botón

### Requirement: Sin formularios ni servicios externos
La página de contacto NO SHALL incluir un formulario que guarde o envíe datos, ni depender de ningún servicio externo. El correo visible es la única vía en esta fase.

#### Scenario: Se plantea añadir un formulario
- **WHEN** alguien propone sustituir el correo por un formulario de contacto
- **THEN** se rechaza en esta fase: un formulario exige un servicio donde guardar o enviar lo escrito, y eso queda fuera del alcance de la web informativa

### Requirement: Qué esperar al escribir
La página de contacto SHALL decir qué pasa después de escribir, con la condición real confirmada por Oscar: contesta él, en 24-48 horas.

#### Scenario: El visitante duda si le contestarán
- **WHEN** el visitante lee la página antes de escribir
- **THEN** sabe que le contesta Oscar en persona y en cuánto tiempo
