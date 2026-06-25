# SETUP

Agent-facing setup notes for openemg.com. Keep concise; update as the project grows.

## Stack

- **SvelteKit 2** + **Svelte 5** (runes mode forced for app code — see `vite.config.ts`)
- **TypeScript** (strict)
- **Tailwind CSS 4** via `@tailwindcss/vite` (no `tailwind.config` file — theme lives in CSS)
- **adapter-auto** (no deployment target chosen yet)

## Prerequisites

- Node 18+ and npm.

## Install & run

```sh
npm install
npm run dev        # dev server (default http://localhost:5173)
npm run build      # production build
npm run preview    # preview the production build
npm run check      # svelte-check: types + a11y (run before finalizing work)
```

## Project layout

- `src/routes/+layout.svelte` — wraps every page with `Navbar` + `Footer`, imports global CSS.
- `src/routes/layout.css` — **the design system**: `@import 'tailwindcss'` + an `@theme` block defining the five brand palettes and the neobrutalism `--shadow-brutal*` tokens. Tailwind 4 auto-generates `bg-/text-/border-/shadow-` utilities from these tokens (e.g. `bg-aquamarine-400`, `shadow-brutal`).
- `src/routes/+page.svelte` — landing page (mission, technology, what-we-offer, `#contact` form).
- `src/routes/tech/+page.svelte` — Surface EMG explainer (`/emg_demo.jpeg`, Wikipedia + paper links).
- `src/routes/demos/+page.svelte` — EEG YouTube embed.
- `src/lib/components/` — reusable UI: `Button`, `Card`, `Navbar`, `Footer`, `InterestForm`. Imported via the `$lib` alias.
- `static/` — `openemg.png` (logo, referenced as `/openemg.png`), `emg_demo.jpeg`, `robots.txt`.

## Design system quick reference

- Brand accent: `aquamarine` (greens). Secondary accents: `fiery-terracotta`, `vivid-orchid`. Neutral: `gunmetal`.
- Neobrutalism look = `border-2 border-gunmetal-900` + `shadow-brutal*` (hard offset, no blur) + bold type. Encapsulated in `Button`/`Card` — reuse those instead of re-styling.
- To add a color step or token, edit the `@theme` block in `src/routes/layout.css`.

## Interest form (Formspree)

- `src/lib/components/InterestForm.svelte` POSTs to the Formspree endpoint
  `https://formspree.io/f/mykqevwq` via `fetch` with `Accept: application/json`, showing
  inline submitting/success/error states. It also sets `action`/`method` on the `<form>` so it
  degrades to a native POST without JS.
- To change the destination, update the `endpoint` constant in that component.
- New Formspree forms require confirming the first submission (Formspree emails the form owner).

## Verifying changes

- `npm run check` must be clean (0 errors/warnings).
- For UI changes, run `npm run dev` and load `/`, `/tech`, `/demos`; the Chrome DevTools MCP can screenshot routes and test the form flow.
- The Svelte MCP `svelte-autofixer` should report no issues for edited components.
