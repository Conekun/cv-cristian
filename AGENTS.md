# Contexto del proyecto — Sitio personal de Cristian Conejeros

## Qué es

Sitio web personal que **reemplaza el CV en PDF** de Cristian Conejeros.
Página única, estática y autocontenida: todo el CSS y el JS viven dentro de `index.html`.
Sin build, sin dependencias, sin framework. Se despliega en Vercel como sitio estático.

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
`Formación (forest)` → `Skills (amber)` → `Portafolio (cream)` → `Contacto (ink)`

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

### Bio

> Publicista, líder de marketing y casi ingeniero comercial. Construyo marca, cuento
> historias y coordino ferias y eventos donde cada detalle tiene que verse tan bien como
> funciona. Produzco el contenido audiovisual, cuido la coherencia visual y acelero el
> proceso con IA, sin perder criterio.

Esta bio se iteró bastante. Cristian prefiere **tono punchy, frases cortas**.
La frase *"Construyo marca, cuento historias y coordino ferias y eventos"* es la que más
le gusta — **no tocarla**. Evitar adjetivos genéricos tipo "proactivo", "visión estratégica",
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

1. **Foto.** Reemplazar el monograma "CC" (`.portrait__mono`) por
   `<img class="portrait__img" src="foto.jpg" alt="Cristian Conejeros">`.
   Vertical, ~800×950 px o más. La clase CSS ya existe y está lista.
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
