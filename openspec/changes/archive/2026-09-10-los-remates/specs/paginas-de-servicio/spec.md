## MODIFIED Requirements

### Requirement: Estilo coherente con la portada
Las páginas de servicio SHALL compartir con la portada la hoja de estilos común `estilos.css`, que es de donde salen las variables de color, la tipografía, la cabecera y el pie. NO SHALL llevar su propio bloque `<style>` con el estilo copiado. El fondo y los colores SHALL declararse explícitamente en esa hoja. NO SHALL usarse librerías ni dependencias externas.

#### Scenario: El visitante navega entre portada y servicio
- **WHEN** el visitante pasa de la portada a una página de curso
- **THEN** reconoce que sigue en la misma web: mismos colores, misma tipografía, misma cabecera

#### Scenario: La página se abre en el móvil
- **WHEN** un visitante abre una página de servicio en la pantalla de un móvil
- **THEN** el texto se lee sin zoom y nada se sale de la pantalla

#### Scenario: Se cambia un detalle de estilo
- **WHEN** hay que ajustar un color o un tamaño compartido
- **THEN** se toca solo `estilos.css`, no cada página por separado

### Requirement: Enlazado del silo
Cada página de servicio SHALL enlazar a la portada, a las otras dos páginas de servicio, a `contacto.html` y a `sobre-mi.html`. La navegación SHALL permitir moverse entre cualquier par de páginas sin usar el botón atrás del navegador.

#### Scenario: El visitante salta de un curso a otro
- **WHEN** el visitante está en la página de un curso y quiere ver otro
- **THEN** encuentra en esa misma página un enlace a los otros dos cursos y a la portada

#### Scenario: El visitante decide escribir desde un curso
- **WHEN** el visitante termina de leer una página de curso y quiere contactar
- **THEN** encuentra el enlace a la página de contacto sin volver a la portada
