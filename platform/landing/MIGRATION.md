# Landing Page Migration (myotto.ai → proprietary theme)

Mirrors the approach used in `platform/ui` (TokenWiz Bootstrap → BEM migration).

## Source

Fresh wget mirror of https://myotto.ai (Next.js 15 / Turbopack static export,
Tailwind v4, deployment `dpl_Frrbfnq3LRJkzKKYFWDCX3e1pNik`) kept in
`platform/myotto.ai-mirror/`.

## Phase 1 — Audit & strip ✅

- Removed all 34 scripts: Next.js/Turbopack runtime chunks, inline RSC payloads,
  Google Tag Manager, Meta Pixel. Removed preload hints, `data-dpl-id`,
  `next-size-adjust`, and the third-party chat widget (JS-loaded, gone with it).
- Removed inline `style="opacity:0;transform:translateY(6px)"` scroll-reveal
  seeds — without React they left sections permanently invisible.
- Renamed hashed assets: `favicon.ico`, `icon.svg`, `icon.png`, `apple-icon.png`.
- Copied the compiled Tailwind chunk to `styles.css`; copied the 7 Inter woff2
  subsets to `fonts/` and rewrote `@font-face` URLs.
- Pretty-printed `index.html` (was one 82KB minified line).
- Kept all SEO metadata (OG, Twitter, manifest, JSON-LD was script-borne and dropped).

## Phase 2 — Token extraction ✅

`base.css` created with `@layer reset, base, layout, components, utilities`:

- **Fonts**: 29 per-weight `@font-face` rules collapsed to 7 variable-weight
  (`font-weight: 300 600`) unicode-range subsets + Arial-based "Inter Fallback".
- **Tokens** under `:root`: light palette (`--color-background:#fafafa`,
  `--color-foreground:#171717`, `--color-muted:#5c5c5c`, borders `#e0e0e0`/`#d4d4d4`,
  emerald accents), dark presale palette (`--dark-*`), type scale
  (`--text-body-sm/md/lg`, hero 38/54px), tracking (display -0.05em, body -0.02em),
  spacing unit 0.25rem, container 65rem, radii, `--shadow-button`, easings.
- `base.css` is linked before `styles.css`; values are identical so rendering is
  unchanged until phase 3 swaps the Tailwind utilities for BEM components.

## Phase 3 — Component conversion ✅

- `theme.css` created (layout + components layers): `.page`/`.container`,
  `.nav`, `.hero` (spectrum gradient + perspective grids moved from inline
  styles into CSS), `.features`/`.feature` with `__deco` mask variants,
  `.model-row`, `.conn`, `.id-card`, `.spend-card`, `.duo`, `.notif-stack`,
  `.device-tile`, `.footer`, plus atoms `.btn`, `.arrow-btn`, `.tag`, `.dot`.
- `index.html` fully rewritten with BEM classes; zero Tailwind utilities and
  zero inline styles remain. The `reveal-load` entrance animation is kept in
  CSS with a `prefers-reduced-motion` opt-out.
- `styles.css` (compiled Tailwind) is no longer linked — kept on disk only as
  a reference; safe to delete once QA'd.
- See `MIGRATION-CLASS-MAP.md` for the full before/after mapping.

## Phase 4 — Minimal JS ✅

`landing.js` (~20 lines, no dependencies): toggles `.nav--open` on the burger,
which shows `.nav__menu` (mobile-only dropdown, scoped under a max-width query
— no `!important`) and morphs the burger into an ×. Menu closes on link tap
and when the viewport crosses the md breakpoint. `aria-expanded` is kept in
sync. Loaded with `defer`.

## Remaining

- `styles.css` deleted after QA — the page runs entirely on `base.css` + `theme.css`.
- Adapt copy/branding when repurposing as the Fonderie landing page.
