# AGENTS.md

## Project snapshot
- Astro + MDX + Tailwind + React site for a research project page.
- Primary content lives in `src/pages/index.mdx` (frontmatter for title/description/favicon/thumbnail + MDX components).
- Reusable UI in `src/components/`, layouts in `src/layouts/`.
- Static assets imported into MDX live in `src/assets/` (bundled by Astro).
- Public/static files (favicon, social thumbnail, etc.) live in `public/`.
- Production build output is `dist/`.

## Common commands
- Install deps: `npm install`
- Dev server: `npm run dev` (alias: `npm start`)
- Type-check + build: `npm run build` (runs `astro check` then `astro build`)
- Preview production build: `npm run preview` (serves `dist/` with `--host`)

## Development best practices
- Edit content in `src/pages/index.mdx`; keep the frontmatter (title/description/favicon/thumbnail) in sync with your latest paper metadata.
- When adding images used inside MDX, put them in `src/assets/` and import at top of the MDX file.
- When updating the favicon or social preview image, place the files in `public/` and update frontmatter to match.
- Prefer existing components in `src/components/` for figures, videos, LaTeX, columns, etc., instead of hand-rolled HTML.
- Run `npm run build` before publishing to catch MDX/type issues.

## Publishing
- Build with `npm run build` and deploy the `dist/` directory to any static host (GitHub Pages, Netlify, Vercel, etc.).
- Use `npm run preview` locally to validate the production build before deployment.
- GitHub Pages automation: `.github/workflows/astro.yml` and `astro2.yml` build on pushes to `main` and deploy via Actions (Node 20, `npm ci`).
