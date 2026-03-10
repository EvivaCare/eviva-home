# Oviva Care – Landing (Astro)

Landing de Oviva Care con **Astro**: rápido, optimizado para **SEO** y con **i18n** (español e inglés).

## Por qué Astro

- **Rendimiento:** HTML estático por defecto, poco o ningún JavaScript.
- **SEO:** Cada ruta es una página estática con `<html lang>`, `canonical`, `hreflang` y Open Graph.
- **i18n:** Rutas `/en/` y `/es/` con textos en `src/locales/`.

## Estructura

```text
src/
├── components/       # Componentes reutilizables
│   ├── Button/      # ButtonPrimary, ButtonOutline (estilo Figma)
│   ├── Hero.astro
│   ├── Countdown.astro
│   ├── Feeling.astro
│   ├── Dive.astro
│   ├── Meet.astro
│   ├── Oviva.astro
│   ├── Testimonials.astro
│   ├── CTA.astro
│   ├── Footer.astro
│   └── WaveSep.astro
├── layouts/
│   └── BaseLayout.astro   # Meta, canonical, hreflang, Open Graph
├── locales/
│   ├── en.json
│   └── es.json
├── pages/
│   ├── index.astro       # Elección de idioma (noindex)
│   └── [lang]/
│       └── index.astro   # Landing en /en/ y /es/
└── styles/
    ├── variables.css    # Colores, tipografía, espaciado, animaciones
    └── global.css       # Base + utilidades + animaciones
```

## Variables globales

En `src/styles/variables.css`:

- **Colores:** `--color-brand-magenta`, `--color-grey-*`, `--color-orange*`, etc.
- **Tipografía:** `--font-heading`, `--font-body`, tamaños `--font-heading-1-size`…
- **Espaciado:** `--spacing-8` … `--spacing-156`
- **Animaciones:** `--animate-duration`, `--animate-ease`

Clases de utilidad en `global.css`: `.font-heading-1` … `.font-heading-6`, `.font-body`, `.font-tiny`, `.animate-fade-in`, `.animate-fade-in-up`.

## Idiomas

- **Rutas:** `/` (elige idioma), `/en/`, `/es/`.
- **Textos:** `src/locales/en.json` y `src/locales/es.json`. Cada página recibe el objeto `t` y lo pasa a los componentes.

## SEO

- `canonical` y `hreflang` para `/en/` y `/es/`.
- Meta `description` y Open Graph por página.
- `lang` correcto en `<html>`.
- La raíz `/` tiene `noindex` y enlaza a ambas versiones.

## Comandos

| Comando        | Acción                    |
|----------------|---------------------------|
| `npm run dev`  | Servidor en `localhost:4321` |
| `npm run build`| Genera `dist/` estático   |
| `npm run preview` | Previsualiza `dist/`   |

## Diseño

Tokens basados en Figma (Oviva Care – Prototype). Botones alineados con los nodos de diseño (CTA primario y variante outline “Contact us”).
