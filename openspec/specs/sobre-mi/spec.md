# Sobre mí

## Purpose

La página `sobre-mi.html`: quién es Oscar y por qué enseña lo que enseña. En una web pequeña es de las más leídas, porque la gente contrata a personas — y aquí más, porque lo que se vende es que enseña él y contesta él.

## Requirements

### Requirement: Página de sobre mí
La web SHALL tener una página `sobre-mi.html` que cuente quién es Oscar, con los textos del apartado "Sobre mí" de `marca.md`, confirmados por él. NO SHALL inventarse biografía, credenciales ni logros.

#### Scenario: El visitante quiere saber quién enseña
- **WHEN** el visitante entra en sobre mí
- **THEN** lee los diez años de Oscar en marketing para empresas, por qué se cansó de las plantillas y por qué eligió enseñar a los que empiezan solos

#### Scenario: Se plantea añadir un mérito no confirmado
- **WHEN** haría falta un dato biográfico que no está en `marca.md`
- **THEN** se le pregunta a Oscar y se escribe con su respuesta, nunca se rellena

### Requirement: La historia explica las decisiones del negocio
La página SHALL conectar la historia con cómo son los cursos: enseñar el porqué en vez de dar plantillas, y contestar Oscar los correos en persona.

#### Scenario: El visitante busca motivos para fiarse
- **WHEN** el visitante termina de leer la página
- **THEN** entiende de dónde salen las dos decisiones que diferencian los cursos, en lugar de leer una declaración de intenciones sin respaldo

### Requirement: Sin foto por ahora
La página NO SHALL usar fotografías de banco de imágenes. Mientras no haya una foto real de Oscar, la página funciona sin imagen.

#### Scenario: No hay foto disponible
- **WHEN** se construye la página y Oscar no ha aportado una foto suya
- **THEN** la página se publica sin fotografía, y se deja el hueco preparado para cuando la haya
