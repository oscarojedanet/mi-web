# Portada

## Purpose

La página de inicio de la web (`index.html`). Es el escaparate: presenta quién es Oscar, qué vende y para quién, y reparte hacia las páginas de servicio. Es la puerta de entrada de la estructura silo descrita en `marca.md`.

## Requirements

### Requirement: Titular de la portada
La portada SHALL mostrar como titular principal la frase decidida a partir de la propuesta de valor de `marca.md`: "Cursos para emprendedores de servicios basados en comportamiento humano: entiende los fundamentos y consigue clientes por tu cuenta".

#### Scenario: Un visitante abre la portada
- **WHEN** alguien abre `index.html` en su navegador
- **THEN** el titular es lo primero que lee, sin necesidad de hacer scroll

### Requirement: Presentación del negocio
La portada SHALL incluir una presentación breve (dos o tres frases) escrita con el material de `marca.md`, que explique para quién son los cursos y en qué se diferencian. Los textos NO SHALL inventarse ni rellenarse con frases genéricas de negocio.

#### Scenario: El visitante entiende de qué va esto
- **WHEN** el visitante lee la presentación bajo el titular
- **THEN** entiende que los cursos son para emprendedores de servicios que no consiguen clientes estables, y que no se basan en plantillas sino en entender el porqué

### Requirement: Los tres cursos con su enlace
La portada SHALL listar los tres cursos (marketing para emprendedores, cliente ideal, propuesta de valor), cada uno con una línea que diga de qué va, y cada uno enlazado a su página de servicio. Los tres enlaces SHALL llevar a una página existente.

#### Scenario: El visitante busca un curso concreto
- **WHEN** el visitante pulsa el nombre de uno de los tres cursos
- **THEN** el enlace le lleva a la página de ese curso (`curso-marketing.html`, `curso-cliente-ideal.html` o `curso-propuesta-de-valor.html`), que existe y habla de ese curso

### Requirement: Vía de contacto
La portada SHALL terminar con una llamada al contacto que lleve a `contacto.html`, y SHALL mostrar el correo contacto@oscarojeda.net como texto visible en el pie. El botón `mailto:` no vive en la portada: ahora que existe una página de contacto, la portada la usa a ella.

#### Scenario: El visitante quiere escribir desde la portada
- **WHEN** el visitante pulsa la llamada al contacto del final de la portada
- **THEN** llega a la página de contacto, donde encuentra el correo y el botón que abre su gestor

#### Scenario: El visitante solo quiere ver la dirección
- **WHEN** el visitante busca la dirección de correo sin salir de la portada
- **THEN** la lee en el pie de página

### Requirement: La portada lleva a contacto y a sobre mí
La portada SHALL enlazar a `contacto.html` y a `sobre-mi.html`, además de a las tres páginas de servicio.

#### Scenario: El visitante quiere escribir o saber quién está detrás
- **WHEN** el visitante busca cómo contactar o quién enseña los cursos
- **THEN** encuentra en la portada un enlace a la página de contacto y otro a la de sobre mí

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
