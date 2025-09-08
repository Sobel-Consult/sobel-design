# SOBEL Design v1

Fertige, versionierte Styles (CSS-Variablen + Basis-Komponenten) für schnelle, markenkonforme UIs.

## Inhalte
- `dist/sobel.css` – Tokens + Komponenten (Buttons, Inputs, Badge, Card, Navbar)
- `assets/sobel-logo.jpeg` – Logo
- `tokens/brand.tokens.json` – Token-Quelle (JSON)
- `examples/index.html` – Mini-Testseite

## Nutzung (CDN über jsDelivr)
1. Repo veröffentlichen unter eurer GitHub-Organisation (z. B. `sobelconsult/sobel-design`).
2. Tag/Release anlegen: `v1.0.0`.
3. In beliebigen Projekten einbinden:
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sobelconsult/sobel-design@v1.0.0/dist/sobel.css">
```
> Logo-Pfad in der Consumer-App setzen (oder Logo dorthin kopieren):
```html
<style>:root{ --logo-url: url('/assets/sobel-logo.jpeg'); }</style>
```

## Nutzung (lokal im Projekt)
Lege `sobel.css` in `/public/styles/` und binde ein:
```html
<link rel="stylesheet" href="/styles/sobel.css">
```

### React/Next/Vite
- Next.js: Import in `src/pages/_app.tsx` oder `src/app/layout.tsx`:
```ts
import '@/styles/sobel.css'
```
- Vite/CRA: Import in `src/main.tsx`:
```ts
import '/public/styles/sobel.css'
```

## Versionierung
- Jede größere Änderung → neues Tag `vX.Y.Z`.
- Alte Projekte bleiben stabil, wenn sie auf ein Tag zeigen (`@v1.0.0`).

## Lizenz
MIT
