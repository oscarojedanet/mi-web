## Context

El proyecto tiene un `index.html` provisional que solo dice "Web en construcción". Las decisiones de marca y el material del negocio están en `marca.md`: azul oscuro, tipografía sans-serif limpia, el punto negro como identidad, y las referencias de gusto (Stripe, Trade Republic, BBVA — limpias, modernas, serias).

El mapa de la web está decidido: portada, tres páginas de servicio, y contacto y sobre mí para más adelante. Esta obra construye solo la portada.

## Goals / Non-Goals

**Goals:**
- Que quien llegue entienda en segundos quién es Oscar, qué vende y para quién.
- Que encuentre la puerta del curso que le interesa.
- Que la página se vea bien en móvil, que es donde la verá la mayoría.

**Non-Goals:**
- Las páginas de los tres cursos (siguiente obra).
- Contacto y sobre mí (lección 5).
- Formularios, pagos o reservas. Esta web es informativa.
- Logo en imagen: no hay archivo, se usa el punto negro dibujado con CSS.

## Decisions

**Un solo archivo HTML con el CSS dentro.** Sin librerías, sin archivo de estilos aparte, sin proceso de construcción. Es lo que manda `AGENTS.md` y es lo que necesita esta web: cinco páginas estáticas no justifican montar herramientas. Alternativa descartada: un CSS compartido en archivo aparte — tiene sentido cuando existan las cinco páginas, y entonces se hará; hoy sería adelantar trabajo sin saber aún qué se repite.

**Colores declarados explícitamente, con `color-scheme: light`.** Si no se declara, algunos navegadores en modo oscuro cambian los colores por su cuenta y el resultado es impredecible. Se declara el fondo, el color del texto y el azul de marca como variables CSS al principio, para que la siguiente obra las reutilice.

**Tipografía del sistema, no Google Fonts.** Se usa la pila de fuentes sans-serif del sistema operativo. Alternativa descartada: cargar una tipografía de Google — sería una dependencia externa (prohibida por `AGENTS.md`), ralentiza la carga y manda datos del visitante a otro servidor. Las fuentes del sistema en 2026 son limpias y modernas, que es lo que se pidió.

**Los enlaces a los cursos se crean ya, apuntando a archivos que no existen.** Alternativa descartada: dejarlos sin enlace y añadirlos después — obliga a volver a tocar la portada y es fácil olvidar alguno. Se dejan los huecos de las puertas y la siguiente obra pone las puertas.

**Nombres de archivo de las futuras páginas:** `curso-marketing.html`, `curso-cliente-ideal.html`, `curso-propuesta-de-valor.html`. Descriptivos y en castellano, coherentes con el idioma de la web.

## Risks / Trade-offs

- **Los tres enlaces dan error 404 hasta la siguiente obra** → Es temporal y conocido. La portada publicada ya cumple su trabajo de presentar; si alguien pulsa un curso antes de tiempo, ve un error. Se resuelve en la lección 4, que es lo siguiente que se hace.
- **El CSS se repetirá en las páginas de servicio** → Aceptado por ahora. Cuando existan las cinco páginas se verá qué se repite de verdad y se decidirá entonces si merece un archivo común.
- **Sin logo real** → La portada se apoya en tipografía y en el punto negro. El día que haya logo, se sustituye sin tocar nada más.
