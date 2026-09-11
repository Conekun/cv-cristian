# Contexto del proyecto — Sitio personal de Cristian Conejeros

## Qué es

Sitio web personal que **reemplaza el CV en PDF** de Cristian Conejeros.
Página única, estática y autocontenida: todo el CSS y el JS viven dentro de `index.html`.
Sin build, sin dependencias, sin framework. Se despliega en Vercel como sitio estático.

**Objetivo actual (sep 2026): postulación a Ecommerce Manager.** El sitio está
reposicionado hacia ese cargo. La tesis es que *la página misma es la prueba*: si el cargo
pide alguien que sepa organizar, vender y hacer todo dentro de una web, lo más convincente
es que el sitio que lo presenta esté construido por él y se comporte como una tienda.

**Posicionamiento honesto — respetar.** Cristian NO ha administrado una tienda online
(nada de Shopify, VTEX, Jumpseller, medios de pago ni logística: no inventar experiencia
que no tiene). Lo que sí trae: growth y adquisición digital, pauta, marca, contenido
audiovisual propio, análisis de datos — y su diferenciador real, que construye él mismo
sitios y landings.

**El sitio ya no declara el vacío (sep 2026).** Hubo dos frases que lo reconocían — *"No
vengo de administrar una tienda…"* en `#ecommerce` y *"No he administrado una tienda, pero
sé cómo funciona una ficha de producto"* en `#ficha` — y **Cristian las quitó**. La bajada
de Ecommerce quedó como *"Busco que la gente llegue, entienda y decida — y construyo el
sitio donde eso pasa"*: habla de intención, no de historial.

**No es una mentira y no hay que "restaurarlas".** Callar algo no es afirmar lo contrario, y
las cuatro frases que sí reclamaban experiencia de tienda ya se corrigieron (ver la tabla
más abajo). **La regla que sigue en pie es la otra: nunca escribir que administró una
tienda, ni dar por hecha una práctica que no ha tenido.**

## Estado actual

- `index.html` — el sitio completo y funcional
- `README.md` — instrucciones de deploy y personalización
- Repo git inicializado, rama `main`, primer commit hecho, **sin remote todavía**

## Dirección de diseño

Referencia visual: portafolio retro-groovy (crema + verde bosque + ámbar + coral, serif
funky de alto contraste, estrellas de 4 puntas, píldoras negras, bloques de color a sangre,
texto fantasma en outline de fondo). **No es una copia** — la composición es propia.

### Paleta (variables CSS en `:root`)

```
--cream    #F4EDE2   fondo claro
--cream-hi #FBF6EE   crema alto
--forest   #1F3A2E   verde bosque
--forest-hi#2B4E3D
--amber    #F2A81D   ámbar
--amber-hi #FFC24D
--coral    #E4552E   coral (acento principal)
--ink      #131211   negro
--ink-soft #4C463E   texto secundario
```

### Tipografías (Google Fonts)

- **Display: Fraunces** (variable). El look retro viene de los ejes `SOFT` y `WONK`,
  aplicados con `font-variation-settings: "SOFT" 40..90, "WONK" 1`.
- **Cuerpo: Jost** (geométrica).

### Ritmo de secciones

Bandas de color a sangre, alternadas:
`hero (cream)` → `marquee (ink)` → `Sobre mí (forest)` → `Experiencia (cream)` →
`Formación (forest)` → `Skills (amber)` → `Ecommerce (cream)` → `Ficha de producto (forest)` →
`Portafolio (cream)` → `Contacto (ink)`

Cristian pidió Ecommerce **después de Skills**. La Ficha quedó entre Ecommerce y Portafolio
para no dejar dos bandas cream pegadas: el orden respeta la alternancia de color.
En el nav no aparece "Ficha" (serían 7 enlaces): se llega por el botón del hero y por la
barra flotante.

### Sección "Ecommerce" (`#ecommerce`)

Cuatro tarjetas numeradas con el embudo — **01 Atraer · 02 Convertir · 03 Retener ·
04 Medir** — y debajo un bloque negro `.proof` ("Esta página es la muestra") con los
contadores 1 archivo / 0 dependencias / IA dirigida por mí.

**No decir que el sitio está "escrito a mano" ni "línea por línea".** Cristian lo construyó
con IA y lo corrigió explícitamente (sep 2026). El encuadre correcto es que la IA fue la
herramienta y el criterio es de él — y que eso *es* la demostración de "Desarrollo con IA",
la habilidad que está vendiendo para el cargo. No es una concesión: es el argumento.

**Tono: realista y humilde, pero con seguridad (sep 2026).** Cristian revisó la sección y
dijo que los copy sonaban *demasiado autosuficientes*. Se sacaron las variantes de
"no espera a nadie" / "no dependo de nadie" / "sin esperar a nadie", que se repetían en tres
tarjetas y en el bloque `.proof`. El criterio: describir el proceso, no declararse
independiente de los demás. Donde el "yo" suena a alarde, sirve la **voz impersonal**:
Cristian escribió él mismo el remate de la tarjeta 02 — *"Si algo no está funcionando, se
testea otra opción y se implementa"* — y ése es el registro modelo para el resto.
También salieron los remates de superioridad tipo "sin reportes de adorno".
Se prefiere el hecho concreto por sobre la frase de eslogan.
>>> Resuelto: el segundo párrafo de la bio (`#sobre-mi`) terminaba en *"sin esperar a
nadie"* y ahora cierra con *"; si algo no convierte, se ajusta y se vuelve a medir"*,
en el mismo registro impersonal.

### Portafolio como catálogo de tienda (`#portafolio`)

En vez de "En preparación", las tarjetas usan **estados de stock** (`.work__stock`):
`En stock` (verde, con punto que late) para el portafolio de Canva que sí existe,
`Próximo lanzamiento` (ámbar) para Makana y `Agotado · reposición en camino` (coral) para
Trefimet, cuyo título va tachado (`.work__card--out`).
Los dos casos que no están listos son enlaces `mailto:` de tipo *avísame cuando vuelva a
estar disponible*. Se descartó "En construcción" por cliché noventero y porque comunica
"no terminé" en vez de "hay demanda".

### Sección "Ficha de producto" (`#ficha`)

Una PDP real donde el producto es Cristian. Tiene breadcrumbs, badges de confianza,
precio ("Conversemos"), dos grupos de variantes con radios accesibles
(**Formato**: jornada completa / por proyecto — **Modalidad**: presencial / híbrido /
remoto), descripción que cambia con el formato (atributo `data-desc`), estado de stock,
tabla de especificaciones y dos acciones: "Sumar al equipo" (agrega al carrito) y
"Guardar como PDF" (`window.print()`).
La columna izquierda (`.pdp__col`) va **foto → código de barras → especificaciones**, para
que la tabla se lea como parte del producto y no como un apéndice; la derecha queda solo con
la identidad y la compra. Ya **no es sticky**: con las especificaciones dentro es demasiado
larga para que tenga sentido. Debajo de la foto lleva una etiqueta (`.pdp__code`) con **un código de barras Code 39 real
y escaneable** que codifica `CC-2026`, más el SKU como pie.

El patrón está generado y verificado con round-trip (se decodifica de vuelta a `*CC-2026*`);
son 45 `<rect>` con anchos 2 (angosto) y 6 (ancho), separadores de 2 y zonas mudas de 20.
Si cambias el texto del código hay que regenerar el patrón, no basta con editar el SKU.

Se evaluó sumar un QR que abriera el sitio o LinkedIn (la cámara del iPhone no lee Code 39,
solo QR, así que el código actual en la práctica no se escanea). **Cristian prefirió dejarlo
como está** (sep 2026): vale como guiño de etiqueta de producto, no como utilidad.

**Ojo con `.pdp__label`:** ese nombre ya lo usan los rótulos "FORMATO" y "MODALIDAD"
(`display:block; opacity:.62`). La etiqueta del código de barras se llama `.pdp__code`
justamente porque la primera versión colisionó y heredaba la opacidad.

### Carrito y checkout (`#minicart`)

"Sumar al equipo" lleva ícono de carrito de supermercado y **agrega al carrito** en vez de
abrir el correo. El nav tiene un botón carrito con contador (`.navcart`), y se abre un panel
lateral con dos pasos:

1. **Tu carrito** — línea de producto con la foto, las variantes elegidas, "Cantidad: 1
   (único disponible)", total "Conversemos" y el botón *Ir al checkout*.
2. **Checkout** — el mensaje se arma solo y queda **editable en la página**: campos de
   asunto y cuerpo, botón *Copiar el mensaje*, y enlaces a Gmail, Outlook y `mailto:`
   que se refrescan con cada tecla.

**Por qué no `mailto:` directo:** Cristian lo pidió explícitamente (sep 2026). `mailto:`
abre la app de correo del sistema y mucha gente no la tiene configurada — el enlace no hace
nada y se pierde el contacto. Copiar y pegar funciona siempre. El `mailto:` sigue existiendo
como opción secundaria y como respaldo sin JavaScript (el `href` de `#pdp-cta` se mantiene
sincronizado por `syncPdp`).

El copiado usa `navigator.clipboard` con respaldo a `document.execCommand('copy')` para
contextos sin API segura (por ejemplo abrir el archivo con `file://`).

### Detalles de producto web

- Barra de progreso de scroll fija arriba (`.progress`)
- Barra flotante inferior tipo *add to cart* (`.cartbar`): aparece al pasar el hero y se
  esconde cuando `#ficha` entra en pantalla

### Movimiento

- Subrayado "squiggle" SVG bajo "Cristian" que se dibuja al cargar (`stroke-dashoffset`)
- Roles rotativos en el hero (keyframes CSS)
- Píldoras flotantes, estrellas que giran y titilan
- Marquee horizontal infinito (se pausa al hacer hover)
- Texto fantasma con parallax al scroll (JS, atributo `data-ghost`)
- Reveals al entrar en viewport: `IntersectionObserver`, clases `.reveal` + `.in`,
  todo gated por la clase `.js` en `<html>` para que sin JS el contenido igual se vea
- Todo respeta `prefers-reduced-motion`

## Reglas técnicas (respetar)

- **Un solo archivo.** CSS y JS inline en `index.html`. No agregar build tools ni frameworks.
- Fuentes desde Google Fonts vía `<link>`. Todo lo demás autocontenido.
- Responsive hasta 390px de ancho. Nunca scroll horizontal.
- `@media print`: el sitio tiene que imprimirse como un CV limpio en blanco y negro.
- **Un solo tema visual** (no hay dark mode). Los colores siempre explícitos.
- Accesibilidad: foco visible, `aria-hidden` en lo decorativo, contraste cuidado.

## Contenido (verificado con Cristian — NO inventar datos)

### Datos de contacto

- Cristian Conejeros — Santiago, Chile
- cconejerosbravo@gmail.com  ← el PDF original decía `gmail.cl`, era un typo, ya corregido
- +569 5886 9612
- Portafolio actual (Canva): https://cristiaconejeros.my.canva.site/portafolio-cristian-conejeros

### Qué se puede reclamar y qué no (sep 2026)

Cristian **nunca ha creado una página de ecommerce real** ni ha administrado una tienda:
sin plataforma (Shopify/VTEX/Woo), sin catálogo, sin medios de pago, sin logística. Quiere
mostrar que sabe **sin sonar experto ni mentir**. Se auditó el sitio y se corrigieron cuatro
frases que insinuaban experiencia de tienda:

| Antes | Ahora |
|---|---|
| "Si voy a decir que **sé armar una tienda**, lo justo es mostrarlo" | *(la bajada de la ficha quedó solo con la instrucción de uso)* |
| "sostiene la relación **después de la primera compra**… el **segundo pedido** cueste menos" | "sostiene la relación cuando la campaña ya terminó… la próxima conversión no parta de cero" |
| "Construyo la página donde ocurre **la venta**" (rol del hero) | "Construyo las páginas donde ocurre la conversión" |
| "La página **que vende**" (tarjeta Convertir) | "La página donde se decide" |

**El criterio:** la precisión distingue a quien sabe de quien alardea; un vacío no delata,
una frase vaga sí. Y el vacío de Cristian es el barato de cerrar — la tienda ya existe en
cualquier empresa que contrate un Ecommerce Manager; lo difícil es traer tráfico, marca y
criterio de datos.

**Excepción legítima:** la descripción de la variante "Jornada completa" dice "me hago cargo
del canal digital: … la página donde ocurre la venta". Eso describe **el trabajo que
tomaría**, no lo que ya hizo. Postular implica decir que puedes hacerlo.

### "Ecommerce & Growth" se eliminó como etiqueta personal (sep 2026)

Cristian objetó que `Enfoque: Ecommerce & Growth` describía **lo que quiere lograr, no lo
que hace**: su enfoque real es marketing. Se eligió *"el cargo real adelante"*: primero lo
verificable, y que el interés por ecommerce lo cuente la sección entera dedicada a eso.

- `Enfoque` → **Marca, contenido y adquisición** (antes "Ecommerce & Growth")
- `<title>` y `og:title` → **Cristian Conejeros — Líder de Marketing**
- `.pdp__sub` → **Líder de Marketing · Marca, contenido y adquisición**
- `.badge--1` → **Marketing & Growth**
- Rol rotativo del hero → **Marketing, growth y adquisición digital**
- `.cartbar` → **Líder de Marketing · Santiago**
- `meta description` → empieza con "Marketing digital, growth y ecommerce" (marketing
  primero; "ecommerce" se queda solo como palabra clave de búsqueda)

Sobrevive donde es nombre de sección o categoría, no etiqueta personal: el enlace del nav,
el título de la sección `#ecommerce` y el breadcrumb "Equipo / Marketing / Ecommerce".

**Si se vuelve a tocar, revisar los siete lugares juntos.** Si el título dice una cosa y la
ficha otra, se nota.

### Hero

> Publicista, casi ingeniero comercial y bastante inquieto. Llevo el marketing de una
> startup chilena y termino metido en todo: el contenido, la página, los números que hay
> detrás. Cuando cierro el computador: música, fútbol y la gente de siempre.

**El hero habla de la persona, no del puesto (sep 2026).** Cristian descartó la versión
anterior ("Llevo el marketing… y construyo las páginas donde ocurre la conversión") porque
*"solo hablaba de trabajo"*. Pidió algo sobre él. Se eligió el registro del **inquieto**:
"bastante inquieto" y "termino metido en todo" son rasgos, no tareas, y de paso explican
por qué hace el contenido y las páginas él mismo.

La última frase es material que dio él: música, fútbol, amigos y familia. Se redactó como
*"Cuando cierro el computador: música, fútbol y la gente de siempre"* — "cerrar el
computador" es una imagen que hace de bisagra entre el trabajo y la vida, y evita el
conector plano ("fuera de eso"). **"La gente de siempre" reemplaza a "estar con mis amigos
y mi familia"**, que es la formulación de manual. Se descartaron "fuera del trabajo soy
poco original" y "lo que no cambia".

**Pendiente:** falta un detalle concreto (su equipo, qué escucha, si juega o solo mira).
"Un partido de la U" dice mucho más que "fútbol", y esa línea es lo único de la página que
nadie más podría escribir. La frase aguanta **un** detalle, no dos.

Ojo: el eyebrow del hero ya **no lleva la estrella** SVG, es solo texto, y la bio de
`#sobre-mi` **ya no abre con las credenciales** ("Publicista, líder de marketing y casi
ingeniero comercial") porque ahora se repetirían con el hero — arranca directo con la frase
favorita de Cristian.

**El hero pasó por tres registros (sep 2026) y terminó en el más seco.**

1. *"…construyo **yo mismo los sitios** donde ocurre la conversión"* — descartada: a
   Cristian le sonaba a declararse **experto**, y no lo es todavía.
2. *"Me metí a construir… y **en eso sigo aprendiendo**"* — descartada: el matiz frena
   justo en el hero, que es lo primero que se lee, y hace que la lista de tres cuelgue de
   una disculpa.
3. **Actual:** los hechos sin narrativa de trayecto. Se le quitó el "yo mismo", que era lo
   que más cargaba el tono de autoridad, y se dejaron "las páginas" en vez de "los sitios".

También se descartaron las versiones que contaban el aprendizaje como iniciativa
("me faltaba entender la página, así que aprendí a construirla" / "no solo a pedirlas").

**Nada de matices en el hero.** Los que había en la sección Ecommerce y en la ficha
Cristian los terminó quitando también (ver arriba): el sitio no habla del vacío en ninguna
parte. Lo que no puede hacer es reclamar lo contrario.
La `<meta name="description">` refleja el hero: si cambia uno, revisar el otro.

### Bio

> Publicista, líder de marketing y casi ingeniero comercial. Construyo marca, cuento
> historias y *las llevo hasta donde se vende: una feria, un stand, una página*. Cada
> detalle tiene que verse tan bien como funciona. Produzco el contenido audiovisual, cuido
> la coherencia visual y acelero el proceso con IA, sin perder criterio.

**Segundo párrafo (sep 2026), para aterrizar el cargo de ecommerce:**

> Ese mismo criterio lo llevo al canal digital: traer al que importa, explicarle en dos
> segundos y que la página haga el resto. *Armo el sitio, escribo el copy y reviso los
> números*; si algo no convierte, se ajusta y se vuelve a medir.

**El trío de verbos cambió (sep 2026) — esto reemplaza la regla anterior.** Durante meses
la instrucción fue *no tocar* "Construyo marca, cuento historias y coordino ferias y
eventos". Cristian mismo lo reabrió: le sigue gustando la frase, pero **tiene poca relación
con el cargo de ecommerce**. Se conservó el ritmo de tres tiempos y se cambió solo el
destino: *"y las llevo hasta donde se vende: una feria, un stand, una página"*. Las ferias
no desaparecen, pasan a ser un formato más — el canal digital entra en la misma lista en vez
de quedar relegado al párrafo siguiente. Se descartaron "armo el lugar donde eso se convierte
en venta" (perdía las ferias) y dejar la frase intacta con un puente aparte.
Las ferias siguen respaldadas en Experiencia (Trefimet).
En el panel de datos al lado, "Base / Santiago, Chile" pasó a **"Enfoque / Ecommerce &
Growth"** — Santiago sigue apareciendo en el hero, la ficha y contacto.

Esta bio se iteró bastante. Cristian prefiere **tono punchy, frases cortas**.
El ritmo de *"Construyo marca, cuento historias y…"* es el que más le gusta: **respetar el
trío de verbos**, aunque el tercero ya se haya actualizado. Evitar adjetivos genéricos tipo "proactivo", "visión estratégica",
"adaptable a entornos dinámicos": los descartó explícitamente por sonar a piloto automático.

### Experiencia

1. **Makana** — Líder de Marketing — feb 2026 → actualidad
   Startup chilena de bienestar laboral (app de salud y hábitos + equipos de recuperación
   física para empresas; foco en minería y construcción). 6 bullets: liderazgo del área
   (estrategia, equipo, presupuesto), estrategia de adquisición y crecimiento B2C,
   narrativa y posicionamiento B2B, estrategia de embajadores e influencers, programa
   insignia de contenido, alineación estratégica con el CEO.
   *Ojo: es startup, no hay "gerencias" — se dice CEO.*

2. **Trefimet** — Encargado de marketing y comunicación — 2024 → ene 2026
   Ingeniería en lanzas térmicas. 5 bullets: estrategias de marketing, identidad
   corporativa, contenido audiovisual, ferias y stands, comunicación interna.

3. **Blue Express · Copec** — Práctica profesional en Marketing digital — 2024
   4 bullets: campañas en redes, piezas audiovisuales, atención a clientes, eventos.

**Ojo con el orden.** Las tarjetas van de más nueva a más antigua (Makana → Trefimet →
Blue Express), pero la **bajada de la sección narra la carrera hacia adelante**: práctica →
industria técnica → startup. Una versión anterior lo decía al revés ("de una startup a una
industria técnica") y Cristian lo corrigió (sep 2026). Texto actual:

> De una práctica en marketing digital a la comunicación de una industria técnica, y de ahí
> a liderar el área en una startup. Cada paso, más cerca del canal digital y de los números.

### Formación

- Universidad Andrés Bello — Ingeniería Comercial — 2025, en curso
- AIEP — Diplomado en Marketing Digital y Gestión Estratégica — 2025
- Universidad del Desarrollo — Publicidad, titulado con distinción — 2024

### Habilidades y competencias

Habilidades: Marketing digital · Gestión de redes sociales · Producción audiovisual ·
Comunicación estratégica · Redacción creativa · Comunicación interna · **Desarrollo con IA** ·
Growth y adquisición digital

Competencias: Liderazgo de equipos · Análisis de datos · Gestión de proyectos ·
Fotografía y video · Gestión de presupuesto

**"Desarrollo con IA" es deliberado**: se refiere a que construye webs, plataformas y
automatizaciones con IA, no a "usar ChatGPT". Ya se descartaron las variantes
"IA aplicada al marketing", "Desarrollo de productos digitales con IA", "Vibe coding",
"Desarrollo de soluciones con IA". El wording final es exactamente **"Desarrollo con IA"**.

## Pendientes

0. **Datos de ecommerce.** Si Cristian consigue números reales (conversión, ROAS, costo
   por adquisición, descargas de la app en Makana), la sección `#ecommerce` los pide a
   gritos. Hoy no hay ninguno y por eso no se muestran cifras de desempeño.
1. ~~Foto.~~ **Hecha** (sep 2026). `foto.jpg` (913×1050, recorte final del propio
   Cristian) aparece en tres lugares: hero, ficha de producto y miniatura circular de la
   barra flotante. Los monogramas "CC" y su CSS ya se eliminaron.
   `foto-original.jpg` es el recorte previo, guardado como respaldo y sin usar en el HTML.
   **Si cambias la foto, actualiza también los atributos `width`/`height`** de los tres
   `<img>`: si no calzan con el archivo, el navegador reserva mal el espacio al cargar.
2. **Redes sociales.** Falta LinkedIn (y lo que quiera sumar). Van en el hero y en el footer.
3. **Casos de portafolio.** Hay dos tarjetas marcadas "En preparación":
   - *Makana: crecimiento digital* — faltan los números reales (crecimiento en redes y
     cantidad de descargas de la app). Cristian tiene esos datos.
   - *Trefimet: marca industrial* — ferias, stands, material promocional.
4. **Migrar el portafolio de Canva** a este sitio.
5. **Deploy en Vercel** con subdominio `.vercel.app`. El repo todavía no tiene remote.

## Cómo trabajar con Cristian

Habla español de Chile. Prefiere **iterar de a poco, sección por sección**, revisando los
textos uno por uno. Cuando pide cambiar algo, le sirve que le den **varias opciones
concretas para elegir**, no una sola propuesta cerrada.
