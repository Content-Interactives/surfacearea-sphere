# Surface area (sphere) interactive

Vite-built React app with a **React Three Fiber** / **Three.js** scene for sphere surface-area exploration, plus UI (sliders, cards, inputs, draggable calculator) implemented mostly in `src/components/Sphere.jsx`. Curriculum and deployment links live in [Standards.md](Standards.md).

**Live:** https://content-interactives.github.io/surfacearea-sphere

**`package.json` `homepage`:** https://destinynguyen.github.io/surface-area/ — keep `vite.config.js` `base` and gh-pages target consistent with whichever GitHub Pages URL you ship.

## Requirements

- Node.js 18+  
- npm

## Commands

| Command | Purpose |
|---------|---------|
| `npm install` | Install dependencies |
| `npm run dev` | Vite dev server (see `vite.config.js`: port `3001`, `host` `0.0.0.0`, `strictPort`, `open`) |
| `npm run build` | Production bundle → `dist/` |
| `npm run preview` | Serve `dist/` locally |
| `npm run lint` | ESLint |
| `npm run deploy` | `predeploy` runs `vite build`, then `gh-pages -d dist` |

## Stack

| Layer | Packages |
|--------|-----------|
| Runtime | React 19 |
| 3D | `three`, `@react-three/fiber`, `@react-three/drei` |
| Styling | Tailwind CSS 3, PostCSS, Autoprefixer |
| Icons | `lucide-react` |
| Tooling | Vite 6, `@vitejs/plugin-react`, ESLint 9 |

Source is **JavaScript + JSX** (`.jsx`); TypeScript types are available for React via devDependencies.

## Project layout

```
index.html
vite.config.js
tailwind.config.js
postcss.config.js
src/
  main.jsx          # React root
  App.jsx           # Renders <Sphere />
  index.css         # Global styles (incl. Tailwind)
  components/
    Sphere.jsx      # Main lesson UI + Canvas integration
    sphere/
      hooks/useCalculator.js   # Calculator state / drag behavior
      components/Calculator.jsx
    ui/             # alert, button, card, input, slider (patterned components)
public/
```

## Vite

- `base: '/'` — for a project site under a subpath (e.g. `/surfacearea-sphere/`), set `base` to that path so asset URLs resolve on GitHub Pages.

## Embedding

The experience is driven by a large single component (`Sphere.jsx`); check canvas size and layout there if you embed in an iframe or host inside a CMS shell.
