# JILNOVA Premium V2 — UI Upgrade Kit

Created October 27, 2026. Designed against **the original JILNOVA screenshots and pasted Astro/React UI source**. **No backend or data structures were changed.**

## What's included

- `src/pages/design-v2.astro` — new, safely isolated design review route (`/design-v2`) using existing `JnShell.astro` and real application paths. It does **not** replace `src/pages/index.astro`.
- `src/styles/jilnova-premium.css` — isolated premium home styles (`jv2-*`) plus compatible polish for the existing nav, forms, listing panels, sidebar, dashboard and footer.
- `preview.html` — self-contained interactive HTML design preview with **inline CSS** and no network dependency. Static demo: CTA links scroll within preview; the Astro version uses the original application routes. This HTML preview is not a functioning backend.
- `assets/preview-1440.png`, `assets/preview-768.png`, `assets/preview-390.png` — desktop/tablet/mobile screenshots of the preview from Chromium.

## Integration (after full source import)

1. Create a new branch from the actual Kleap project source (do not overwrite `main`).
2. Copy `src/pages/design-v2.astro` and `src/styles/jilnova-premium.css` to the same paths in the Astro app.
3. Start the project with its **actual** scripts and environment. Navigate to `/design-v2`. Existing home and backend remain untouched.
4. Test login, forms, links, imagery, SSR/hydration and full application routes on a staging deployment. Check desktop/tablet/mobile and keyboard accessibility.
5. Only if approved, replace the content of `src/pages/index.astro` with this home composition while preserving any required existing functionality.
6. If you want consistent upgraded nav / dashboard styling site-wide, add `import '../styles/jilnova-premium.css';` to the frontmatter of `src/components/JnShell.astro` (adjust relative path as appropriate), then rebuild and regression-test. Note that CSS specificity/source order matters; review conflicts before deploying.

## Design principles

- Palette: deep forest `#103B35`, darker `#09251F`, fresh lime `#C4F26A`, warm paper `#F7F7F0`.
- Editorial Arabic headlines, large intentional whitespace, premium non-stock SVG product illustrations.
- Clear split: Reuse & Recycle, honest real-data messaging (no fabricated partners, prices or impact counters).
- Responsive at 390px / 768px / 1440px, respectful of `prefers-reduced-motion`.
- Plain Astro + CSS only. No paid fonts, SaaS UI libraries or image URLs.

## What is and isn't tested

- **PASS:** static HTML rendering in headless Chromium via `set_content` at 390/768/1440 viewport widths; no JS page errors; no horizontal page overflow; screenshots captured. (Browser networking/file navigation is restricted in the authoring environment, hence `set_content`.)
- **NOT TESTED:** Astro compilation, `JnShell` integration, actual site routing, live databases/auth, transactional flows, real assets or device testing. The authentic full application repository was not available; GitHub `main` contains only a README at time of authoring.

## Privacy / safety

- The UI does not collect contact info in the preview.
- Adult-only transactions and general-location only messaging are maintained.
- No external images, fake metrics or fictional customer reviews.
