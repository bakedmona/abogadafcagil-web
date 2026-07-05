# Sitio web — Francisca Gil, Abogada

Sitio construido con [Astro](https://astro.build). Se publica automáticamente en
GitHub Pages cada vez que se sube un cambio a la rama `main` (ver
`.github/workflows/deploy.yml`).

## Estructura

```
src/
  components/   Cada sección del sitio en su propio archivo
    Header.astro
    Hero.astro
    About.astro
    Areas.astro
    Contact.astro
    Footer.astro
  layouts/
    BaseLayout.astro   Estructura HTML base, fuentes, metadatos
  pages/
    index.astro        Une los componentes en la página principal
  styles/
    global.css          Colores y estilos compartidos
public/
  CNAME                Dominio personalizado (abogadafcagil.cl)
```

## Flujo de trabajo

Este proyecto está pensado para que los cambios se pidan por chat (texto,
voz o imágenes) y se apliquen directamente en estos archivos — nunca es
necesario editar código a mano.

- No es necesario correr `npm run build` manualmente: GitHub Actions lo hace
  solo al hacer push a `main`.
- Si se agregan páginas nuevas, van dentro de `src/pages/`.
- Los estilos generales (colores, tipografía) están en `src/styles/global.css`.
- Cada sección tiene sus propios estilos dentro de su archivo `.astro`.

## Primer despliegue (una sola vez)

1. Crear el repositorio en GitHub y subir esta carpeta.
2. En GitHub: **Settings → Pages → Build and deployment → Source**, elegir
   **"GitHub Actions"** (no "Deploy from a branch").
3. Configurar el dominio personalizado en **Settings → Pages → Custom domain**
   con `abogadafcagil.cl` (el archivo `CNAME` ya está incluido).
4. Configurar los registros DNS en el proveedor del dominio apuntando a
   GitHub Pages (ver conversación con Claude para el detalle de los registros).
