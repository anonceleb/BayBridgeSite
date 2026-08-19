# Handoff: BayBridge Logistics site restyle

## Overview
The original site (github.com/anonceleb/BayBridgeSite) is a static HTML/CSS/JS marketing site for Baybridge Logistics. This bundle restyles it onto the **Industry** design system (steel-blue-on-light wireframe, blueprint cards with registration marks, Barlow / Barlow Condensed type) to fix the generic "AI-default" look. **All copy is unchanged** — this is a visual and structural restyle only, not a rewrite.

## About the design files
These are **drop-in replacements for the same files in the existing repo** — plain HTML/CSS/JS, no build step, same architecture as the original (`index.html`, `services.html`, `about.html`, `contact.html`, `css/style.css`, `js/main.js`, `brand/`). They are production-ready, not throwaway mockups: copy them directly over the equivalents in `anonceleb/BayBridgeSite` and deploy as before (Netlify/Vercel/GitHub Pages, no build command).

## Fidelity
**High-fidelity.** Final colors, type, spacing and component treatment — implement pixel-for-pixel.

## What changed vs. the original repo
- **Palette**: navy/gold/slate → Industry's steel-blue mono scheme (`#5980a6` accent, light `#f2f2f3` ground, ink `#1d1f20`). No gold accent — this system is intentionally single-accent.
- **Type**: Georgia serif + system sans → Barlow Condensed (headings) + Barlow (body), loaded from Google Fonts.
- **Cards**: rounded, filled `.why-list li` / `.service-card` → square, transparent, hairline-bordered **blueprint cards** with `+` corner registration marks (`.blueprint` + `<i class="corner tl/tr/bl/br">`).
- **Buttons**: rounded pill-ish → square-cornered; primary is the one solid accent-filled object on the page.
- **CTA strip / footer**: navy → the accent's deep tonal step (`--color-accent-900`, `#1d2d3d`).
- **Logo**: recolored from the original navy/gold artwork to the new ink/accent tokens (`brand/baybridge-logo-ds.svg`, `-ds-reversed.svg`, `baybridge-mark-ds.svg`). Original SVGs are untouched in the repo if the gold mark is wanted elsewhere.
- Structure, copy, IA, and the honesty constraints from `BUILD-BRIEF.md` (no false claims about offices, tracking platform, certifications, etc.) are all preserved verbatim, including `[FILL IN]` placeholders.

## Design tokens
```
--color-bg:        #f2f2f3   page ground
--color-surface:   #e9e9ea   alternating section fill
--color-text:      #1d1f20   ink
--color-accent:    #5980a6   the one accent — links, buttons, rules, corner marks
--color-accent-100:#eef6ff   tag fill
--color-accent-700:#416180   accent text on light ground (AA-safe for body-size text)
--color-accent-900:#1d2d3d   CTA strip / footer field, reversed type
--color-divider:   rgba(29,31,32,.16)   hairline borders
--color-neutral-*: #f5f5f8 / #d4d4d7 / #b7b7ba / #7a7a7d / #424244

font-heading: "Barlow Condensed", 600 weight — all headings, nav, buttons
font-body:    "Barlow", 400/700 — body copy

Radius: 0 everywhere (square corners — deliberate, not an oversight)
Max content width: 1120px, side gutter clamp(20px, 5vw, 64px)
```
Full component reference (buttons, tags, forms, cards) is in `css/style.css`.

## Screens / pages
1. **index.html (Home)** — hero, positioning block (2-col, accent-rule list), "Why Baybridge" (5 blueprint cards, numbered 01–05), services grid (6 blueprint cards), FAQ (native `<details>`), CTA strip.
2. **services.html** — hero + 6 numbered blueprint service cards (customs-liaison card carries a "Via licensed brokers" outline tag), CTA strip.
3. **about.html** — hero, "how we work", "the model" (on the alt surface band), a 4-item registration fact grid (legal name / GSTIN / jurisdiction / registered date), CTA strip.
4. **contact.html** — direct-contact list (email/phone/office are `[FILL IN]`, styled in accent-italic) + enquiry form (Formspree, same setup comment as the original repo).

All four share `.site-header` (sticky nav, mobile toggle below 860px) and `.site-footer` (accent-900 field, reversed logo, service + company link columns).

## Interactions & behavior
- Mobile nav: `.nav-toggle` button (visible <860px) toggles `.nav__links.is-open` — same JS as the original repo (`js/main.js`), unchanged.
- FAQ: native `<details>/<summary>`, no JS; `+` becomes `−` via `[open]` CSS.
- Focus states: 2px solid accent outline on all interactive elements (`:focus-visible`).
- No new client-side state or animation was introduced.

## Assets
- `brand/baybridge-logo-ds.svg`, `baybridge-logo-ds-reversed.svg`, `baybridge-mark-ds.svg` — recolored from the repo's originals (`baybridge-logo-horizontal.svg` etc.) to the Industry ink/accent tokens. `baybridge-logo-stacked.svg` carried over unchanged (not used on these 4 pages, kept for parity with the repo's `brand/` folder).
- No photography — the original site has none; Industry's `.duotone` image treatment isn't needed unless photos are added later.

## Files in this bundle
```
index.html, services.html, about.html, contact.html   the 4 pages
css/style.css                                          full stylesheet (tokens + components)
js/main.js                                             mobile nav toggle (unchanged from original)
brand/                                                  recolored + carried-over logo SVGs
```

## Next steps for the developer
1. Copy this bundle's files over the same paths in `anonceleb/BayBridgeSite`.
2. Fill in the `[FILL IN]` placeholders (business email/phone/address, ports worked) once confirmed.
3. Replace `YOUR_FORM_ID` in `contact.html` with the real Formspree endpoint (see comment above the form).
4. Deploy as before — no build step, no new dependencies beyond the Google Fonts `@import` already in `css/style.css`.
