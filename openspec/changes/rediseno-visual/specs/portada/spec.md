## MODIFIED Requirements

### Requirement: Titular de la portada
La portada SHALL mostrar como titular principal la frase-resumen de `marca.md`: "El curso de marketing que no te da plantillas". El resto de esa frase — "te enseño a entender el comportamiento humano para que puedas conseguir clientes por tu cuenta, en cualquier situación" — SHALL ir justo debajo como entradilla. El titular NO SHALL partirse en dos colores ni alargarse con material que no esté en `marca.md`.

#### Scenario: Un visitante abre la portada
- **WHEN** alguien abre `index.html` en su navegador
- **THEN** el titular es lo primero que lee, sin necesidad de hacer scroll

#### Scenario: El visitante lee el titular de un vistazo
- **WHEN** el visitante mira la portada durante un par de segundos
- **THEN** el titular es lo bastante corto para leerlo entero, y dice en qué se diferencia el curso

### Requirement: Los tres cursos con su enlace
La portada SHALL listar los tres cursos (marketing para emprendedores, cliente ideal, propuesta de valor), cada uno enlazado a su página de servicio. Cada curso SHALL decir con qué llega el cliente y con qué sale, tomado del apartado "Los cursos" de `marca.md`. Los tres enlaces SHALL llevar a una página existente.

#### Scenario: El visitante busca un curso concreto
- **WHEN** el visitante pulsa el nombre de uno de los tres cursos
- **THEN** el enlace le lleva a la página de ese curso (`curso-marketing.html`, `curso-cliente-ideal.html` o `curso-propuesta-de-valor.html`), que existe y habla de ese curso

#### Scenario: El visitante compara los tres cursos
- **WHEN** el visitante mira los tres cursos uno al lado de otro
- **THEN** cada uno le dice con qué problema se entra y con qué resultado se sale, para elegir el que le hace falta hoy

## ADDED Requirements

### Requirement: La cabecera de la portada enseña el curso
El primer golpe de vista de la portada SHALL mostrar el curso de marketing: sus cinco lecciones y la condición del feedback por correo, tomadas de `marca.md`. NO SHALL ocupar ese sitio una figura decorativa.

#### Scenario: El visitante llega por primera vez
- **WHEN** el visitante abre la portada y no baja
- **THEN** ya ha visto de qué se compone el curso: cinco lecciones con su título, y que el feedback por correo lo contesta Oscar en 24-48 horas

#### Scenario: Se busca una figura decorativa
- **WHEN** se revisa la cabecera de la portada
- **THEN** no hay aros ni formas abstractas: el espacio lo ocupa información del curso

### Requirement: Los precios no se inventan
La portada NO SHALL mostrar ningún precio mientras `marca.md` no recoja las cifras. El maquetado SHALL dejar sitio para añadirlos sin rehacer las tarjetas.

#### Scenario: Se revisa qué dice la portada sobre el precio
- **WHEN** el visitante lee las tarjetas de curso
- **THEN** no encuentra ninguna cifra inventada ni un hueco vacío que parezca un error

#### Scenario: Oscar decide publicar los precios
- **WHEN** Oscar da las tres cifras
- **THEN** se añaden a las tarjetas sin cambiar su estructura

## REMOVED Requirements

### Requirement: Estilo y colores explícitos
**Reason**: El estilo de la portada deja de ser un requisito suyo y pasa a la nueva capacidad `sistema-visual`, que lo recoge entero y lo amplía (tipografía propia, piezas reutilizables, contención decorativa y contraste). Tenerlo repetido en portada y en páginas de servicio hacía que cualquier cambio de estilo obligara a tocar dos specs.
**Migration**: Lo que decía este requisito está ahora en `sistema-visual`, en los requisitos "Un solo sitio para el estilo" (hoja común, sin librerías, colores explícitos, sin bloque `<style>` por página) y "Tipografía propia servida desde el proyecto". El punto negro y el azul oscuro como colores de marca siguen fijados por `marca.md`.
