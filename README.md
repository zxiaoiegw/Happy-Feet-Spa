# Happy Feet Spa

Marketing site for Happy Feet Spa (Kansas City) — built with [Astro](https://astro.build).

## Structure

```
src/
  layouts/Layout.astro   shared <head>, header, footer, nav, reveal-on-scroll script
  pages/
    index.astro          home page (video hero, treatments summary, visit info)
    services.astro        full service menu with photos and descriptions
public/
  images/                service photos (served as-is, no processing)
  video/hero.mp4          hero background video
```

Global design tokens (colors, type, spacing) live in `src/layouts/Layout.astro` under `:root`. Page-specific styles live in a `<style>` block at the bottom of each `.astro` page.

## Local development

```bash
npm install
npm run dev       # http://localhost:4321
```

```bash
npm run build      # outputs static site to dist/
npm run preview    # serve the built dist/ locally
```

## Deploying

1. Push this repo to GitHub.
2. In Vercel, "Add New Project" → import the GitHub repo.
3. Vercel auto-detects Astro — no config needed (build command `astro build`, output `dist`).
4. Every push to the default branch redeploys automatically.

## Editing content

- **Prices, hours, phone, address**: edit directly in `src/pages/index.astro` and `src/pages/services.astro` (plain text/HTML, no CMS).
- **Photos**: drop a new file in `public/images/` and reference it as `/images/filename.ext` in the relevant page.
- **Hero video**: replace `public/video/hero.mp4` (keep it short and compressed — under ~5&nbsp;MB is ideal for load speed).
- **Colors/fonts**: the `:root { --paper: ...; --ember: ...; }` block in `src/layouts/Layout.astro`.

## Notes

- The `public images/` folder (with a space in the name) at the project root is the original, unprocessed source photos — it's not used by the site itself (everything the site references lives in `public/images/`, no space). Safe to delete once you've confirmed the site looks right, or keep it as an archive.
- The standalone `index.html` / `services.html` at the project root were the earlier static mockups used during design review — no longer needed now that the Astro pages exist. Safe to delete.
