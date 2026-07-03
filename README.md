# Synodic

Single-page stealth surface. Charcoal/concrete brutalist field, procedural
gold/copper veins, a jewel-toned WebGL fluid simulation contained in a single
aperture. Meaning at full strength, offer offstage.

## Deploy (GitHub Pages)

1. Commit `index.html` to the repo **root** on `main`.
2. Repo → **Settings → Pages** → *Deploy from a branch* → `main` / `/ (root)`.
3. Live at `https://brendanwhitaker.github.io/Synodic/` (or your custom domain).

## Font — ITC Avant Garde Gothic

You have the license. Add the files, don't hotlink them:

1. Create a `fonts/` folder in the repo root.
2. Drop in your `.woff2` files (Book + Medium at minimum).
3. In `index.html`, match the `src:url(...)` paths in the two `@font-face`
   blocks to your filenames.

Until the files are present the page falls back to Century Gothic, so it never
renders broken — but the real geometry only arrives with your font.

## Swap points

- **Thesis line** — the `<p class="thesis">` sentence. Placeholder is the
  severe register; swap freely.
- **Inbox** — the `mailto:` on the *Inquiries* link.
- **Palette / motion** — jewel stops live in the `pal()` function; flow speed
  is the `u_time*0.03` factor (lower = slower/more geological).

## Notes

- The fluid is WebGL with a CSS-gradient fallback if the context fails.
- `prefers-reduced-motion` is respected (fluid freezes, no reveal transitions).
- `noindex` is set — stealth by default. Remove the meta tag if you want it
  discoverable.
- Gold veins are seeded on `1642`; the pattern is stable across reloads.
