# SOBEL Style Logic — External Guide

This document explains how SOBEL styling works so external teams can use it safely without digging through the codebase.

## 1) Core concept
- **Design tokens** (colors, typography, spacing, radius, shadows) are exposed as **CSS variables** in a single file: `dist/sobel.css`.
- Components are **utility classes** (no JS required): `.btn`, `.input`, `.card`, `.badge`, `.navbar`.
- Apps consume the stylesheet via **CDN** and **must not** define custom colors (hex/rgb/hsl).

## 2) Inclusion
Add the CDN `<link>` to your document `<head>`:
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sobelconsult/sobel-design@v1.0.0/dist/sobel.css">
```
Optionally set the project-specific logo (rendered by `.brand-logo`):
```html
<style>:root{ --logo-url: url('/assets/sobel-logo.jpeg'); }</style>
```

## 3) Tokens (CSS variables)
Important variables (subset):
```css
:root {
  /* Primary brand */
  --brand-blue-main: #0F0FEA;
  --brand-blue-sea:  #0B31A4;
  --brand-blue-dark: #071E63;

  /* Semantic aliases */
  --color-primary: var(--brand-blue-main);
  --color-primary-hover: var(--brand-blue-sea);
  --color-primary-contrast: #FFFFFF;

  /* Typography, spacing, radius, shadow */
  --font-sans: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans";
  --fs-md: 16px;
  --space-4: 16px;
  --radius-md: 10px;
  --shadow-sm: 0 1px 2px rgba(0,0,0,.06);
}
```
Do **not** override these with raw values; if you need a new token, request it upstream.

## 4) Base classes
- **Button**: `.btn` + variant `.btn--primary|.btn--secondary|.btn--ghost` (+ sizes `.btn--sm|.btn--lg`)
- **Input**: `.input`
- **Card**: `.card` (optional `.card--tight`)
- **Badge**: `.badge` + variants `.badge--info|.badge--success|.badge--warning|.badge--danger`
- **Navbar**: `.navbar` with child `.brand` & `.brand-logo`

Example:
```html
<button class="btn btn--primary">Get started</button>
<input class="input" placeholder="Email">
<div class="card"><h2>Section</h2>...</div>
```

## 5) Guardrails (why we block raw colors)
- Enforcing tokens keeps visual consistency and accessibility.
- CI templates (see `ci-templates/sobel-style-guard.yml`) **fail the build** if hex/rgb/hsl appear in app code.
- This prevents “almost correct” colors and drift across projects.

## 6) Accessibility
- Buttons and inputs are designed to meet **WCAG AA** contrast under default themes.
- Do not lower contrast or opacity on primary actions.
- If you embed on colored backgrounds, validate contrast in your product context.

## 7) Versioning & Updates
- Styles are versioned by **tags** (`v1.x`). Refer to a **fixed tag** in your app’s CDN URL.
- When we ship a new minor version, only update the tag if you want the change.
- Breaking changes will bump **major** version (e.g., `v2.0.0`).

## 8) Known limitations
- This is a **CSS-only** baseline; it doesn’t include JS components (modals, pickers).
- If you need advanced components, compose them from base classes or request a component spec.

## 9) Quick smoke test
Open `examples/index.html` locally and verify:
- Navbar renders
- Primary button uses SOBEL blue
- Inputs focus ring uses primary color
