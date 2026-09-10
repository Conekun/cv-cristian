# Cristian Conejeros — CV / Sitio personal

Sitio web personal de una sola página, estático y autocontenido.
Todo el CSS y el JS viven dentro de `index.html`; las tipografías vienen de Google Fonts.

## Estructura

```
.
├── index.html   ← el sitio completo
└── README.md
```

## Ver en local

Abre `index.html` en el navegador (doble clic), o levanta un servidor:

```bash
python3 -m http.server 8000
# luego abre http://localhost:8000
```

## Publicar en Vercel

### Opción A — sin repo (lo más rápido)

1. Entra a https://vercel.com y crea una cuenta.
2. Instala la CLI y despliega desde esta carpeta:

```bash
npm i -g vercel
vercel        # despliegue de prueba
vercel --prod # despliegue definitivo
```

También puedes arrastrar la carpeta al dashboard de Vercel ("Add New… → Project → Deploy").

### Opción B — con repo en GitHub (recomendado: se actualiza solo)

```bash
git init
git add .
git commit -m "Sitio personal"
git branch -M main
git remote add origin https://github.com/USUARIO/REPO.git
git push -u origin main
```

Después, en Vercel: **Add New… → Project → Import Git Repository**, elige el repo y
**Deploy**. No hay que configurar build: es un sitio estático, framework "Other",
output directory la raíz.

Cada `git push` a `main` publica automáticamente.

## Cambiar el dominio

En Vercel: **Project → Settings → Domains**. Ahí puedes usar el subdominio gratuito
`.vercel.app` o conectar un dominio propio.

## Personalizar

### Agregar la foto

En `index.html`, dentro del bloque `.portrait`, reemplaza:

```html
<div class="portrait__mono" aria-hidden="true">CC</div>
```

por:

```html
<img class="portrait__img" src="foto.jpg" alt="Cristian Conejeros">
```

y deja el archivo `foto.jpg` en esta misma carpeta (vertical, idealmente 800×950 px o más).

### Colores

Están todos definidos como variables al inicio del `<style>`:

```css
--cream   #F4EDE2   fondo claro
--forest  #1F3A2E   verde bosque
--amber   #F2A81D   ámbar
--coral   #E4552E   coral
--ink     #131211   negro
```

### Contenido

Cada sección está marcada con comentarios (`<!-- ============ EXPERIENCIA ============ -->`)
para ubicarla rápido.
