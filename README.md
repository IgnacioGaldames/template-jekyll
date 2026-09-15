# template-jekyll

Template base para proyectos Jekyll con Bootstrap 5, SEO optimizado e integraciones de analytics configurables.

## Stack

| Herramienta | Versión |
|---|---|
| Jekyll | latest |
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

# Build de producción
JEKYLL_ENV=production bundle exec jekyll build
```

## Configuración

Edita [`_config.yml`](_config.yml) para personalizar el sitio:

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

## Analytics

Las integraciones se activan automáticamente si el valor en `_config.yml` no está vacío.
Google Analytics solo se carga en producción (`JEKYLL_ENV=production`).

| Variable | Plataforma |
|---|---|
| `google_analytics_id` | Google Analytics 4 |
| `gtm_id` | Google Tag Manager |
| `fb_pixel_id` | Meta (Facebook) Pixel |

## Licencia

MIT
