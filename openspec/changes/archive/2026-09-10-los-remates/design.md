## Context

La web tiene cuatro páginas publicadas (portada y tres cursos), cada una con su bloque `<style>` copiado. El mapa de la lección 2 ya anunciaba contacto y sobre mí como pendientes. El material de la historia de Oscar está confirmado en el apartado "Sobre mí" de `marca.md`.

La deuda del CSS se contrajo a sabiendas en la obra anterior, con una condición explícita: pagarla cuando existieran las seis páginas y se viera el patrón completo. Ese momento es este.

## Goals / Non-Goals

**Goals:**
- Dar una vía de contacto clara y una página que explique quién está detrás.
- Que cada página tenga su letrero propio en el buscador y la marca en la pestaña.
- Dejar el estilo en un solo sitio, para que el próximo cambio cueste una edición y no seis.

**Non-Goals:**
- Formularios, reservas o pagos. Fase informativa.
- Teléfono y WhatsApp: decisión de Oscar, solo correo.
- Fotografías. No hay foto real y no se usan de banco.
- Optimización para buscadores más allá de título y descripción. Nada de sitemap ni datos estructurados hoy.

## Decisions

**Se extrae `estilos.css` y se enlaza desde las seis páginas.** Es la deuda acordada. Alternativa considerada: dejarlo como está y seguir copiando. Descartada porque el coste crece con cada página: hoy son seis ediciones por cada cambio de color, y contacto y sobre mí lo empeorarían. Sigue sin ser una dependencia externa — el archivo vive en el proyecto y viaja con él.

**El favicon se hace en SVG, no en .ico.** Un círculo negro sobre fondo blanco son cuatro líneas de SVG, se ve nítido a cualquier tamaño y no hay que generar ni descargar ningún binario. Alternativa considerada: un `.ico` clásico, que es lo tradicional. Descartada porque exigiría una herramienta externa para generarlo y los navegadores actuales aceptan SVG. Se acepta el matiz: algún navegador antiguo mostrará el icono por defecto, lo cual no rompe nada.

**El punto va sobre fondo blanco explícito, no transparente.** Un punto negro transparente desaparece en una pestaña oscura. Con el fondo blanco dibujado dentro del propio icono, se ve siempre.

**Los títulos siguen el patrón "qué es — Oscar Ojeda".** Es lo que Google enseña como titular, así que se escribe para eso: primero lo que la página ofrece, luego de quién. Alternativa descartada: titulares con gracia — a nadie le sirve una frase ingeniosa en una lista de resultados.

**La navegación crece de tres enlaces a cinco.** Cabecera con los tres cursos, sobre mí y contacto. Se revisa que en móvil no estorbe: por debajo de 34rem el menú de la cabecera ya se oculta, y los enlaces siguen accesibles desde el pie y desde el final de cada página.

**La página de contacto dice las 24-48 horas.** No es un adorno: es la condición real, y quien duda antes de escribir necesita saber qué va a pasar después.

## Risks / Trade-offs

- **Se tocan las seis páginas a la vez** → Es el mayor riesgo de las tres obras. Un fallo al extraer el CSS afectaría a toda la web de golpe. Mitigación: pasear la web entera antes de publicar, página por página, y comprobar cada una en el navegador.
- **Un navegador muy antiguo no mostrará el favicon SVG** → Verá el icono por defecto. No afecta a nada más de la página.
- **Google puede tardar días o semanas en recoger los letreros nuevos** → No es un fallo ni hay nada que arreglar. Se explica y se espera.
- **La página de sobre mí queda sin imagen** → Se asume: mejor sin foto que con una de banco. El hueco queda listo.
