## ADDED Requirements

### Requirement: Ficha de lo que incluye el curso
Cada página de servicio SHALL mostrar una ficha que resuma lo que incluye ese curso y lleve al contacto. La ficha SHALL ir a la altura del contenido del curso, no escondida al final. En el curso de marketing SHALL recoger las cinco lecciones grabadas, el feedback por correo sin límite y la respuesta en 24-48 horas contestada por Oscar, tal como están en `marca.md`.

#### Scenario: El visitante quiere saber qué se lleva por su dinero
- **WHEN** el visitante llega a la parte de la página que explica el curso
- **THEN** tiene a la vista una ficha con lo que incluye, sin tener que reconstruirlo leyendo toda la página

#### Scenario: El visitante se decide a mitad de página
- **WHEN** el visitante ya está convencido antes de llegar al final
- **THEN** la ficha le ofrece escribir en ese mismo momento, sin seguir bajando

### Requirement: El dolor y el deseo se leen juntos
La página SHALL presentar "con qué llegas" y "con qué sales" como un par que se lee de una vez, no como dos secciones separadas por el resto del contenido. El orden SHALL seguir siendo el dolor antes que el deseo.

#### Scenario: El visitante se reconoce y ve la salida
- **WHEN** el visitante lee la parte alta de la página
- **THEN** encuentra su problema descrito y, al lado, el resultado con el que termina el curso

### Requirement: Los precios no se inventan
Las páginas de servicio NO SHALL mostrar ningún precio mientras `marca.md` no recoja las cifras. La ficha del curso SHALL dejar sitio para añadirlo sin rehacerla.

#### Scenario: Se revisa la ficha del curso
- **WHEN** el visitante lee la ficha
- **THEN** no encuentra ninguna cifra inventada ni un hueco vacío que parezca un error

## REMOVED Requirements

### Requirement: Estilo coherente con la portada
**Reason**: El estilo compartido deja de ser un requisito de las páginas de servicio y pasa a la nueva capacidad `sistema-visual`, que lo recoge entero. Estaba duplicado con el requisito equivalente de la portada, así que cualquier cambio de estilo obligaba a tocar dos specs.
**Migration**: Lo que decía este requisito está ahora en `sistema-visual`, en el requisito "Un solo sitio para el estilo": hoja común `estilos.css`, sin bloque `<style>` por página, sin librerías ni dependencias externas, fondo y colores declarados explícitamente, y un solo sitio donde tocar para cambiar un color. El escenario de que la página se lea en el móvil lo cubre ahora `navegacion` junto con `sistema-visual`.
