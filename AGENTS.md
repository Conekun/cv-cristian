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
sitios y landings. La frase que ordena todo el sitio es:
*"No vengo de administrar una tienda. Vengo de hacer que la gente llegue, entienda y
decida — y de construir yo mismo el sitio donde eso pasa."*

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

### Hero (reposicionado a ecommerce)

> Llevo el marketing de una startup chilena y construyo las páginas donde ocurre la
> conversión. Tráfico que sirve, una página que se entiende y datos para decidir dónde va
> la próxima moneda.

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

**Dónde va la humildad:** en la sección Ecommerce, no en el hero. Ahí ya está la frase
*"No vengo de administrar una tienda…"*, que llega después de mostrar el trabajo y por eso
se lee como honestidad y no como disculpa.
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
