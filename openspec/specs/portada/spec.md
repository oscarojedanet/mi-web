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
La portada SHALL terminar con el correo de contacto contacto@oscarojeda.net, pulsable para abrir el gestor de correo.

#### Scenario: El visitante quiere escribir
- **WHEN** el visitante pulsa el correo al final de la portada
- **THEN** se abre su gestor de correo con la dirección puesta

### Requirement: Estilo y colores explícitos
La portada SHALL usar tipografía sans-serif limpia, azul oscuro como color de marca y el punto negro como elemento de identidad, según `marca.md`. El fondo y los colores del texto SHALL declararse explícitamente en el CSS. La página NO SHALL usar librerías ni dependencias externas.

#### Scenario: El navegador está en modo oscuro
- **WHEN** un visitante con el navegador en modo oscuro abre la portada
- **THEN** la página se ve con sus colores propios, sin heredar el modo oscuro ni quedar texto ilegible

#### Scenario: La portada se abre en el móvil
- **WHEN** un visitante abre la portada en la pantalla de un móvil
- **THEN** el texto se lee sin zoom y nada se sale de la pantalla
