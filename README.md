# SOBEL Design v1

Versioned stylesheet (**CSS tokens + base components**) for fast, brand-consistent UIs.

## Contents
- `dist/sobel.css` — tokens & base classes (.btn, .input, .card, .badge, .navbar)
- `assets/sobel-logo.jpeg` — default logo (referenced via CSS variable)
- `tokens/brand.tokens.json` — token source in JSON
- `examples/index.html` — quick smoke test
- `docs/StyleGuide.md` — how the style logic works (for externals)
- `docs/PromptCollection.md` — copy-paste prompts for Codex / guidance docs
- `ci-templates/sobel-style-guard.yml` — tiny CI for consumer apps
- `.github/workflows/cdn-health.yml` — health checks (design repo)

## Usage (CDN via jsDelivr)
Add this to your HTML `<head>`:
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sobelconsult/sobel-design@v1.0.0/dist/sobel.css">
```
Set the logo (optional):
```html
<style>:root{ --logo-url: url('/assets/sobel-logo.jpeg'); }</style>
```

### React / Vite / CRA
Edit `public/index.html` (or `index.html`) and place the `<link>` inside `<head>`.

### Next.js
- **Pages Router**: add the `<link>` inside `<Head>` in `pages/_document.tsx`.
- **App Router**: return the `<link>` from `app/head.tsx`.

## Versioning
- Tag releases (e.g., `v1.0.0`) and reference the tag in the CDN URL.
- Upgrade by changing only the tag in your apps; everything else remains stable.

## License
MIT
