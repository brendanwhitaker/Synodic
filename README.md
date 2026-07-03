# Synodic

Single-page brand site for **Synodic** — a data &amp; research / trend-reporting firm.

A deep-charcoal field carries the Synodic iridescent spectrum (cyan → magenta →
orange): a living, blurred **aurora** behind an oversized gradient **wordmark**,
framed with the restraint of institutional wayfinding — a strict three-row grid,
tracked all-caps signage, a monospace data layer, and corner registration marks.

No build step, no dependencies — one self-contained `index.html`.

## Structure

```
.
├── index.html          # the whole site: markup, styles, and the aurora shader
├── README.md
├── .gitignore
└── assets/
    └── fonts/          # ITC Avant Garde Gothic — .woff2/.woff (web) + .ttf/.eot (source)
```

## Design language

- **Palette** — charcoal field (`--ink #0E0D11`) under the Synodic spectrum
  (`--cyan → --blue → --violet → --magenta → --coral → --orange`), exposed as the
  `--spectrum` gradient token. A dark `.scrim` keeps the field charcoal-dominant
  so the wordmark pops and body copy stays legible.
- **Type** — three strata of ITC Avant Garde Gothic:
  - *Display* — Book→Bold geometric, for the wordmark and thesis.
  - *Wayfinding* — the Condensed cuts, tracked all-caps signage (`.sign`).
  - *Data* — a system monospace stack for the `.io`, the est. line, labels (`.data`).
- **Aurora** — a domain-warped fbm shader (WebGL) mapped to the spectrum, rendered
  full-bleed then blurred and masked in CSS so it reads as soft iridescence rather
  than detail. Falls back to the static `.field-bg` gradient if WebGL is absent.
- **Chrome** — corner registration marks and hairline rules borrow the discipline
  of technical/institutional layout without any of the literalism.

## Swap points

- **Thesis** — the `<p class="thesis">` line.
- **Positioning** — the header `.role` (`Data · Research · Trend Reporting`).
- **Inbox** — the `mailto:` on *Request a briefing* (currently `hello@synodic.io`).
- **Palette / motion** — the spectrum stops live in `:root --*` and the shader
  `pal()`; aurora intensity is the `#aurora` opacity + `.scrim` alphas; wordmark
  shimmer speed is the `shimmer` animation duration; flow speed is `u_time*0.045`.

## Font — ITC Avant Garde Gothic

Licensed files live in `assets/fonts/` and are wired directly in the two
`@font-face` groups at the top of `index.html` (display weights 200–700 plus the
Condensed cuts). If the files are ever missing, the page falls back to Century
Gothic + a monospace stack, so it never renders broken.

## Deploy (GitHub Pages)

1. Push to the repo on `main` (or your default branch).
2. Repo → **Settings → Pages** → *Deploy from a branch* → `main` / `/ (root)`.
3. Live at `https://brendanwhitaker.github.io/synodic/` (or your custom domain).

## Notes

- `prefers-reduced-motion` is respected — the aurora freezes and reveal
  transitions are disabled.
- `noindex` is set by default. Remove the `<meta name="robots">` tag to make the
  page discoverable.
- Everything is inline in `index.html`; the only external assets are the fonts.
