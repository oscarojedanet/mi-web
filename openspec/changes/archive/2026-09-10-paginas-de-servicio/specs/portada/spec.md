## MODIFIED Requirements

### Requirement: Los tres cursos con su enlace
La portada SHALL listar los tres cursos (marketing para emprendedores, cliente ideal, propuesta de valor), cada uno con una línea que diga de qué va, y cada uno enlazado a su página de servicio. Los tres enlaces SHALL llevar a una página existente.

#### Scenario: El visitante busca un curso concreto
- **WHEN** el visitante pulsa el nombre de uno de los tres cursos
- **THEN** el enlace le lleva a la página de ese curso (`curso-marketing.html`, `curso-cliente-ideal.html` o `curso-propuesta-de-valor.html`), que existe y habla de ese curso
