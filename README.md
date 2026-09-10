# Cristian Conejeros — CV / Sitio personal

**En vivo: https://cristian-conejeros.vercel.app**
Repo: https://github.com/Conekun/cv-cristian · Deploy automático desde `main` en Vercel.

Sitio web personal de una sola página, estático y autocontenido.
Todo el CSS y el JS viven dentro de `index.html`; las tipografías vienen de Google Fonts.

Está posicionado para postular a **Ecommerce Manager**: además de las secciones de CV
(experiencia, formación, skills) incluye una sección **Ecommerce** con el embudo
Atraer → Convertir → Retener → Medir, y una **ficha de producto** interactiva donde el
producto es Cristian — se eligen formato y modalidad, y el botón "Sumar al equipo" arma
el correo con lo seleccionado.

## Estructura

```
.
├── index.html   ← el sitio completo
├── foto.jpg     ← foto de perfil (hero, ficha y barra flotante)
└── README.md
```

## Ver en local

Abre `index.html` en el navegador (doble clic), o levanta un servidor:

```bash
python3 -m http.server 8000
# luego abre http://localhost:8000
```

## Publicar cambios

El sitio ya está desplegado. Cada `git push` a `main` republica automáticamente:

```bash
git add .
git commit -m "descripción del cambio"
git push
```

En ~20 segundos el cambio está en https://cristian-conejeros.vercel.app

## Cómo se configuró (referencia)

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

### Cambiar la foto

Reemplaza `foto.jpg` en esta carpeta (vertical, idealmente 900×1100 px o más). El archivo
se usa en tres lugares del HTML y el recorte lo resuelve CSS con
`object-fit:cover; object-position:top center`, así que basta con cambiar el archivo.

### Editar la ficha de producto

Las variantes son `<input type="radio">` normales dentro de `.pdp__opts`. Para agregar una
opción de formato, copia un `<label class="pdp__opt">` y dale su propio `data-desc`: ese
texto es el que aparece al seleccionarla, y el valor viaja al correo que arma el botón.

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
