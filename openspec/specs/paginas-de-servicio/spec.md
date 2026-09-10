# Páginas de servicio

## Purpose

Las páginas de cada curso: `curso-marketing.html`, `curso-cliente-ideal.html` y `curso-propuesta-de-valor.html`. Son las puertas de la estructura silo — la portada reparte hacia ellas y cada una profundiza en un solo curso.

## Requirements

### Requirement: Una página por curso
La web SHALL tener una página propia por cada curso: `curso-marketing.html`, `curso-cliente-ideal.html` y `curso-propuesta-de-valor.html`. Cada página SHALL hablar de un solo curso.

#### Scenario: El visitante entra en un curso desde la portada
- **WHEN** el visitante pulsa uno de los tres cursos en la portada
- **THEN** aterriza en una página que habla solo de ese curso, sin mezclarlo con los otros dos

### Requirement: El esqueleto de la página de servicio
Cada página de servicio SHALL seguir este orden: primero el dolor con el que llega el cliente, después el deseo con el que sale, después en qué consiste el curso, y al final el contacto. El cliente y su problema van antes que el servicio.

#### Scenario: El visitante se reconoce antes de que le vendan
- **WHEN** el visitante lee la página de arriba abajo
- **THEN** lo primero que encuentra es su propio problema descrito, y solo después la explicación del curso

### Requirement: Los textos salen de marca.md
Los textos de cada página SHALL salir del apartado "Los cursos" de `marca.md` y del material del cliente (deseos y puntos de dolor). NO SHALL inventarse contenido sobre los cursos: si falta material, se pregunta a Oscar antes de escribir.

#### Scenario: Falta material para una sección
- **WHEN** el material de `marca.md` no cubre algo que la página necesita
- **THEN** se le pregunta a Oscar y se escribe con su respuesta, nunca con frases genéricas de negocio

#### Scenario: El curso de marketing detalla su contenido
- **WHEN** el visitante quiere saber qué hay dentro del curso de marketing
- **THEN** la página lista las cinco lecciones y las condiciones del feedback por correo (sin límite, respuesta en 24-48 horas), tal como están en `marca.md`

### Requirement: Enlazado del silo
Cada página de servicio SHALL enlazar a la portada, a las otras dos páginas de servicio, a `contacto.html` y a `sobre-mi.html`. La navegación SHALL permitir moverse entre cualquier par de páginas sin usar el botón atrás del navegador.

#### Scenario: El visitante salta de un curso a otro
- **WHEN** el visitante está en la página de un curso y quiere ver otro
- **THEN** encuentra en esa misma página un enlace a los otros dos cursos y a la portada

#### Scenario: El visitante decide escribir desde un curso
- **WHEN** el visitante termina de leer una página de curso y quiere contactar
- **THEN** encuentra el enlace a la página de contacto sin volver a la portada

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
