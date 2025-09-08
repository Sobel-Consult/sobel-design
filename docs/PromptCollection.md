# SOBEL Prompt Collection (Copy-Paste)

Use these prompts in Codex to bootstrap or retrofit projects with SOBEL v1.

## 1) SYSTEM — Bootstrap (new/empty projects)
```
SYSTEM — SOBEL DESIGN BOOTSTRAP (v1, public)
Goal: Include SOBEL v1 via CDN and use only SOBEL classes/tokens.

CDN:
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sobelconsult/sobel-design@v1.0.0/dist/sobel.css">

Steps (detect & apply automatically):
1) Detect stack (Static HTML / React CRA/Vite / Next Pages / Next App).
2) ALWAYS add the <link> to <head>. No JS imports of remote CSS.
3) Set logo variable if needed:
   :root{ --logo-url: url('/assets/sobel-logo.jpeg'); }
4) Add a test page/section (Navbar + Card + Form) using .btn/.input/.card/.badge/.navbar.
5) Output: list of files + full contents (no explanations).
6) Guardrails: no hex/rgb/hsl; no external fonts/shadows.
```

## 2) TASK — Retrofit existing repo
```
TASK — RETROFIT SOBEL v1 INTO EXISTING REPO (PUBLIC)

CDN:
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sobelconsult/sobel-design@v1.0.0/dist/sobel.css">

Steps:
- Create branch chore/sobel-design-v1
- Insert <link> per stack (Static/CRA/Vite/Next Pages/Next App)
- Optionally set :root --logo-url
- Add sample page at /sobel-test
- Update README section “SOBEL Styles”
- Commit & PR
Output: unified diff or per-file final contents (no commentary).
```

## 3) TASK — Generate PR text
```
TASK — GENERATE PR TEXT (SOBEL v1)

PR TITLE:
Integrate SOBEL design v1

PR BODY (Markdown):
- Adds SOBEL v1 stylesheet via CDN (jsDelivr)
- Injects usage sample (Navbar, Card, Buttons)
- Sets logo via CSS variable (:root --logo-url)

**How to test**
- Start the app and open the sample page (e.g., /sobel-test).
- Verify the primary button color and typography match the SOBEL brand.
- Confirm CSS is loaded from:
  https://cdn.jsdelivr.net/gh/sobelconsult/sobel-design@v1.0.0/dist/sobel.css

**Rollout**
- Merge & ship. Future design changes via tag update (v1.x / v2.x).

Output: Only the final text, no extra comments.
```

## 4) TASK — Self-check & auto-fix
```
TASK — SELF-CHECK (SOBEL v1)

Validate:
- Forbidden colors: hex/rgb/hsl (including rgba/hsla)
- No inline color styles
- Exact link to https://cdn.jsdelivr.net/gh/sobelconsult/sobel-design@v1.0.0/dist/sobel.css present
- Next placement correct (Pages: pages/_document.tsx <Head>; App: app/head.tsx)
- Sample page exists and uses SOBEL classes

If violations exist, fix and reprint the final patch only.
```
