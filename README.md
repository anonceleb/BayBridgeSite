# Baybridge Logistics — Website

Static HTML/CSS/JS site, no build step. Built per `BUILD-BRIEF.md`.

## Local preview

No dependencies. From this folder, either:

```bash
open index.html
```

or serve it (recommended, so relative paths and forms behave the same as production):

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Structure

```
index.html          Home
services.html        Services (with anchor IDs per service)
about.html            About / registration details
contact.html          Contact form
css/style.css         All styling (palette + type from BUILD-BRIEF.md)
js/main.js             Mobile nav toggle
brand/                 Logo SVGs (favicon, header, footer, stacked)
```

## Deploy

Any static host works. Netlify example:

1. Push this folder to a Git repo.
2. In Netlify: **Add new site → Import an existing project**, connect the repo.
3. Build command: none. Publish directory: `/` (repo root).
4. Deploy.

Vercel and GitHub Pages work the same way — no build command, root as the publish directory.

## Contact form (Formspree)

The form in `contact.html` posts to Formspree by default. To activate it:

1. Create a free account at [formspree.io](https://formspree.io).
2. Create a new form and copy its endpoint (e.g. `https://formspree.io/f/xxxxabcd`).
3. In `contact.html`, replace `YOUR_FORM_ID` in the `<form action="...">` attribute with your real form ID.
4. Verify the email address Formspree sends submissions to.

**Netlify alternative:** if deploying to Netlify, you can use Netlify Forms instead — add `data-netlify="true"` to the `<form>` tag and a hidden `<input name="form-name" value="contact">`, then remove the Formspree `action`. Netlify Forms handles submissions natively, no external service needed. See the HTML comment above the form in `contact.html`.

## `[FILL IN]` placeholders

The brief withheld business details that weren't confirmed. Search the codebase for `[FILL IN]` or the `.fill-in` CSS class to find them:

| Placeholder | Location |
|---|---|
| Business email | `contact.html` — Direct contact list |
| Business phone | `contact.html` — Direct contact list |
| Office address | `contact.html` — Direct contact list |
| Ports regularly worked | `index.html` — FAQ, "Which ports do you work?" |

Two service lines were marked `[CONFIRM]` in the brief and are included as written, pending confirmation:

- **Customs clearance liaison** — scope is described as coordination/documentation/filing support via licensed brokers only, per the brief's regulatory note (no CBLR 2018 licence held).
- **Project and oversize cargo coordination** — included in the services grid; confirm it's actually in scope.

## Honesty constraints (do not remove)

Per `BUILD-BRIEF.md`, the copy deliberately avoids claiming: a global office network, in-house customs department, proprietary tracking platform, freight-forwarding-specific years of experience, client names/case studies, or unheld certifications (AEO, FIATA, IATA, FFFAI, ISO). If you edit copy later, keep these constraints — the customs clearance wording in particular is a regulatory concern, not just a style choice (see comment in `BUILD-BRIEF.md`).

## Out of scope (per brief)

Quote calculator, shipment tracking, login, payments, blog.
