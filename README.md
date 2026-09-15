# Template Jekyll

Template base para crear sitios Jekyll rápidos, accesibles y listos para producción. Incluye Bootstrap 5, SEO, feed RSS, sitemap, analítica opcional y una compilación automática en GitHub Actions.

## Stack

| Herramienta | Versión |
|---|---|
| Jekyll | 4.3 |
| Bootstrap | 5.3 |
| FontAwesome | 6.5 |
| jekyll-seo-tag | ✅ |
| jekyll-sitemap | ✅ |
| jekyll-feed | ✅ |

## Inicio rápido

```bash
# Instalar dependencias
bundle install

# Servidor de desarrollo
bundle exec jekyll serve

# Build de producción (PowerShell)
$env:JEKYLL_ENV="production"; bundle exec jekyll build --strict_front_matter

# Build de producción (macOS/Linux)
JEKYLL_ENV=production bundle exec jekyll build --strict_front_matter
```

## Configuración

Antes de publicar, edita [`_config.yml`](_config.yml):

```yaml
title: "Mi Sitio"
url:   "https://www.tusitio.com"
lang:  "es"

# Analytics (dejar vacío para desactivar)
google_analytics_id: "G-XXXXXXXXXX"
gtm_id:              "GTM-XXXXXXX"
fb_pixel_id:         ""

# Redes sociales
twitter_username:  ""
github_username:   ""
linkedin_username: ""
```

## Estructura

```
template-jekyll/
├── _config.yml          # Configuración principal
├── _data/
│   └── navigation.yml   # Ítems del menú
├── _includes/
│   ├── head.html        # <head> con SEO y analytics
│   ├── header.html      # Navbar responsive
│   ├── footer.html      # Scripts al cierre del body
│   ├── head/            # Parciales del <head>
│   └── footer/          # Scripts parciales
├── _layouts/
│   ├── default.html     # Layout base
│   ├── home.html        # Página principal
│   ├── page.html        # Páginas estáticas
│   └── post.html        # Artículos del blog
├── _posts/              # Artículos (YYYY-MM-DD-titulo.md)
├── assets/
│   └── css/
│       └── style.scss   # Estilos principales
├── index.md             # Página de inicio
└── about.md             # Página de ejemplo
```

## Navegación

Edita [`_data/navigation.yml`](_data/navigation.yml):

```yaml
- title: "Inicio"
  url: /

- title: "Blog"
  url: /blog/

- title: "Acerca"
  url: /about/
```

## Estructura recomendada para nuevos proyectos

1. Cambia `title`, `name`, `description`, `url` y `lang`.
2. Reemplaza `index.md` y `about.md` por el contenido real.
3. Actualiza [`_data/navigation.yml`](_data/navigation.yml).
4. Añade imágenes a `assets/images/` y estilos en `assets/css/style.scss`.
5. Crea artículos en `_posts/` con el formato `YYYY-MM-DD-titulo.md`.
6. Configura los secretos o IDs de analítica solo cuando exista consentimiento.

`baseurl` debe ser vacío para un dominio raíz y comenzar con `/` cuando el sitio vive en un subdirectorio. Usa siempre `relative_url` para enlaces internos.

## Analytics

Las integraciones se activan automáticamente si el valor en `_config.yml` no está vacío.
Google Analytics solo se carga en producción (`JEKYLL_ENV=production`).

| Variable | Plataforma |
|---|---|
| `google_analytics_id` | Google Analytics 4 |
| `gtm_id` | Google Tag Manager |
| `fb_pixel_id` | Meta (Facebook) Pixel |

Google Analytics solo se carga en producción y respeta la preferencia `Do Not Track`. Las integraciones permanecen desactivadas cuando sus valores están vacíos.

## Publicar en GitHub Pages

El workflow incluido valida cada pull request. Para publicar desde GitHub Pages, selecciona **Settings > Pages > GitHub Actions** y conserva la rama `master` como rama principal.

## Licencia

MIT
