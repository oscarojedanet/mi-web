## Context

La portada está construida y publicada, con sus variables de color, su cabecera y su pie definidos. Sus tres enlaces apuntan a `curso-marketing.html`, `curso-cliente-ideal.html` y `curso-propuesta-de-valor.html`, que no existen.

El material de los tres cursos está en el apartado "Los cursos" de `marca.md`: dolor, deseo, y para el de marketing también el temario de cinco lecciones y las condiciones del feedback (sin límite, respuesta en 24-48 horas). La decisión de negocio está tomada: el curso de marketing toca por encima lo que los otros dos hacen a fondo.

## Goals / Non-Goals

**Goals:**
- Que quien busca un curso concreto aterrice en una página que habla solo de eso.
- Que se reconozca en el problema antes de que le expliquen el servicio.
- Que pueda moverse entre los tres cursos y la portada sin volver atrás.
- Que la web se sienta una sola cosa.

**Non-Goals:**
- Precios y botón de compra. No hay material de precios en `marca.md` y no se inventa.
- Formularios de inscripción, pagos o reservas. Esta web es informativa.
- Contacto completo y sobre mí (lección 5).
- Testimonios nominales de alumnos: existe el dato de los 30 alumnos, pero no hay frases concretas recogidas.

## Decisions

**Un archivo HTML por curso, con su CSS dentro.** Mismo criterio que la portada y lo que manda `AGENTS.md`. Alternativa considerada: sacar el CSS a un `estilos.css` común ahora que hay cuatro páginas y el estilo se repite. Descartada por poco tiempo, no por siempre: con la lección 5 llegan contacto y sobre mí, y ahí serán seis páginas repitiendo lo mismo. Ese es el momento natural de extraerlo, con todo el patrón a la vista y no a medias. El coste de esperar es tener que tocar cuatro archivos si hoy cambia un color; asumible, y se anota como deuda consciente.

**Nombres de archivo planos, no carpetas.** Se mantienen `curso-marketing.html` y compañía, que es a lo que ya apunta la portada. Alternativa considerada: una carpeta por curso con su `index.html` dentro, para que la dirección quede `/curso-marketing/` en vez de `/curso-marketing.html`. Es algo más limpio de cara a Google y de cara a quien lee la barra del navegador. Descartada hoy porque obligaría a cambiar los enlaces de la portada recién publicada y a mover archivos, y la ganancia es pequeña para una web de seis páginas. Si algún día la web crece, se cambia con redirecciones.

**Cabecera y pie idénticos a la portada, copiados en cada página.** Sin plantillas ni sistema de componentes, que exigiría herramientas y contradice `AGENTS.md`. Con seis páginas, copiar es más barato que montar maquinaria.

**La navegación entre cursos va al final de cada página, no solo en la cabecera.** El menú de arriba ya permite saltar, pero quien termina de leer una página está en el momento de decidir. Poner ahí las otras dos puertas es donde de verdad se usa.

**El nivel de detalle es distinto por página, y se asume.** El curso de marketing tiene temario y condiciones de feedback; los otros dos, solo dolor y deseo. Se escribe lo que hay. Alternativa descartada: rellenar los dos cortos para que parezcan iguales — sería inventar, y `AGENTS.md` lo prohíbe.

## Risks / Trade-offs

- **Las páginas de cliente ideal y propuesta de valor quedan cortas** → Es honesto: refleja el material que existe hoy. Cuando Oscar defina su temario, se amplían. Una página corta y verdadera vale más que una larga inventada.
- **El CSS repetido en cuatro archivos** → Deuda consciente, con fecha de revisión: la lección 5, cuando existan las seis páginas. Mientras tanto, un cambio de color obliga a tocar cuatro archivos.
- **Sin precios, el visitante interesado se queda a medias** → Su salida es el correo, que está en todas las páginas. Cuando haya decisión de precios, se añade.
