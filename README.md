# Space Travel (Astro)

Sitio informativo inspirado en el reto “Space Tourism” de Frontend Mentor, construido con **Astro 5**. Incluye vistas para destinos, tripulación y tecnología, con navegación responsive para mobile, tablet y desktop.

## Requisitos

- Node 18+  
- pnpm (recomendado)

## Instalación y scripts

```sh
pnpm install         # instala dependencias
pnpm dev             # levanta el servidor en http://localhost:4321
pnpm build           # genera la build estática en ./dist
pnpm preview         # sirve la build para pruebas locales
```

## Estructura principal

```
/
├── public/                # estáticos públicos (favicon, fuentes, imágenes)
├── src/
│   ├── assets/            # imágenes y data.json
│   ├── components/        # UI reutilizable (navegación, secciones, etc.)
│   ├── layouts/           # Layout.astro
│   └── pages/             # rutas: index, destination, crew, technology
└── package.json
```

## Navegación y páginas

- `/` home: hero con botón “Explore” (mobile: apunta a `/destination`).
- `/destination`: pestañas de destinos (Moon, Mars, Europa, Titan) cargadas desde `src/assets/Data/data.json`.
- `/crew`: carrusel por dots para la tripulación.
- `/technology`: conmutador por dots numerados (landscape/portrait según viewport).
- Navegación:
  - Mobile/Tablet: menú lateral (`NaviationsMobile.astro`) + barra superior con logo clicable a `/`.
  - Desktop: barra superior con resalte activo (`ButtonsDesktop.astro`).

## Datos y assets

El contenido (destinos, tripulación, tecnología) proviene de `src/assets/Data/data.json`; las imágenes viven bajo `src/assets/…` y se referencian directamente desde los componentes.

## Estilos

- Variables y fuentes en `src/styles/global.css`.
- Fondos responsivos por página (mobile/tablet/desktop) definidos en cada `.astro` de `src/pages`.

## Accesibilidad y pequeñas notas

- Enlaces de navegación incluyen números visibles y texto; se usan `aria-selected` en los dots.
- Evitamos logs de debug en producción.

## Deploy

Al ser Astro estático, se puede publicar en Netlify, Vercel o GitHub Pages.  
Comando de build: `pnpm build` → subir el contenido de `dist/`.
