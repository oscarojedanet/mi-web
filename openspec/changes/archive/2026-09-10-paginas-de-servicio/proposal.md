## Why

La portada ya presenta el negocio y reparte hacia los tres cursos, pero esos tres enlaces apuntan al vacío: las páginas no existen y dan error 404. La estructura silo está a medias. Quien llega interesado en un curso concreto no tiene dónde aterrizar.

## What Changes

- Se crean tres páginas nuevas, una por curso: marketing para emprendedores, cliente ideal y propuesta de valor.
- Cada página lleva el mismo esqueleto, que es el recorrido mental del cliente: el dolor con el que llega, el deseo con el que sale, en qué consiste el curso y el correo de contacto.
- Los textos salen del apartado "Los cursos" de `marca.md`. Nada inventado.
- Se completa el enlazado del silo: cada página vuelve a la portada y salta a las otras dos.
- Los tres enlaces de la portada dejan de dar error.
- El estilo es el de la portada: las mismas variables de color, la misma tipografía, la misma cabecera y el mismo pie. La web tiene que sentirse una sola cosa.

## Capabilities

### New Capabilities
- `paginas-de-servicio`: las páginas de cada curso — qué debe contener cada una, en qué orden, y cómo se enlazan entre sí y con la portada.

### Modified Capabilities
- `portada`: sus tres enlaces dejan de apuntar a páginas inexistentes. El escenario que daba el 404 por bueno ya no aplica.

## Impact

- Tres archivos nuevos: `curso-marketing.html`, `curso-cliente-ideal.html`, `curso-propuesta-de-valor.html`.
- `index.html` no cambia de contenido: sus enlaces ya apuntan a esos nombres.
- No se añaden dependencias. Cada página sigue siendo un archivo HTML con su CSS dentro.
- El CSS se repite en las cuatro páginas. Se acepta a sabiendas (ver `design.md`).
