# Baybridge Logistics — Website Build Brief

Give this to Claude Code: "Read BUILD-BRIEF.md and build the site."

## Reference site

The client's mentor asked for this to follow **https://www.apclogistics.com** closely in design and structure.

**How to use that reference:** match the information architecture, page layout, section ordering, navigation pattern, and professional tone. Do **not** copy their text verbatim — it is copyrighted, and more importantly most of their claims are false for Baybridge (APC has offices on three continents, an in-house customs department, a proprietary tracking platform called FlowControl, and a corporate CSR programme; Baybridge is a newly registered sole proprietor working on commission). Write fresh copy that fits the same slots.

**What to carry over from APC:**
- Top nav with a Services dropdown, About, Contact
- Hero with a short confident tagline, then a paragraph of positioning
- A numbered "Why choose us" list
- A services grid where each service is a card with a heading and a short paragraph
- An FAQ section near the bottom
- A quiet footer that repeats the service links
- Restrained, corporate, plain-spoken tone. No hype, no exclamation marks.

**What to drop:** Track & Trace, Career, News/Insights blog, e-commerce fulfilment, cargo insurance, CSR/charity section, multi-region contact tabs, social icons. None apply yet.

## Business facts

- Trade name: **Baybridge Logistics**
- Legal name: Ashwin Kumar (Proprietorship)
- GSTIN: **33APMPK1708A1ZG**
- Registered: 19 August 2026
- Jurisdiction: Chennai-South, Tamil Nadu
- Model: commission-based logistics agent — freight coordination and customs clearance liaison
- Principal's background: 20+ years in enterprise ERP and supply chain consulting (Capgemini, GE Healthcare, TCS), work across 18+ countries

Mark as `[FILL IN]`, do not invent: phone, email, office address, specific carrier/NVOCC relationships, ports regularly worked.

## Honesty constraints — non-negotiable

Claude Code must not write, imply, or design around any of the following:
- A global office network, overseas branches, or "our teams worldwide"
- An in-house customs department or in-house staff of any kind
- A proprietary IT platform, tracking system, or dashboard
- Years of freight-forwarding experience (the ERP/supply-chain years are real; freight years are not)
- Client names, logos, testimonials, shipment volumes, or case studies
- Certifications not held (AEO, FIATA, IATA, FFFAI membership, ISO)

Where APC says "our global network," Baybridge says what is actually true: a Chennai base, direct access to the Chennai–Ennore–Kattupalli cluster, and partner carriers and brokers engaged per shipment.

## Brand assets

In `/brand/`:
- `baybridge-logo-horizontal.svg` — primary, use in header
- `baybridge-logo-horizontal-reversed.svg` — for dark backgrounds/footer
- `baybridge-logo-stacked.svg` — square placements
- `baybridge-mark.svg` — favicon and social avatar

**Palette** (derive all CSS colors from these):
- Navy `#10365A` — primary, headings, logo
- Gold `#C8862B` — accent only: rules, active nav underline, link hover. Use sparingly.
- Slate `#5A6B7D` — secondary text
- Mist `#C9D2DB` — borders, dividers
- Paper `#FFFFFF` and `#F5F7F9` — alternating section backgrounds

**Type:** serif display (Georgia or a similar web-safe serif) for headings to match the logo wordmark; system sans for body. Do not load heavy webfonts.

## Page structure

Multi-page, matching APC's shape. Or single-page with anchors if Claude Code judges that cleaner for this scope — but nav labels must stay the same either way.

### Home
1. **Hero** — short tagline, one positioning paragraph, "Get in touch" button.
2. **Positioning block** — the case for a small, principal-led agent: one point of contact, documentation handled by someone who has run enterprise supply chains, no layered markups. This replaces APC's "era of progress" technology block.
3. **Why Baybridge** — numbered 01–05, same visual pattern as APC. Content should be things that are actually true and actually differentiating: principal-led (you deal with the owner), documentation and compliance discipline from an ERP background, Chennai port cluster proximity, commission model with transparent costs, GST registered and verifiable.
4. **Services grid** — cards, see below.
5. **FAQ** — 4–6 questions. Suggested: What does a commission-based agent do? Which ports do you work? Do you handle customs clearance directly or through a licensed broker? What documents do I need for an import consignment? How are your charges structured?
6. **Contact CTA strip**.

### Services (individual pages or grid cards)
Mirror APC's card pattern. Baybridge's applicable set:
- **Ocean freight coordination** — FCL and LCL bookings through partner carriers and NVOCCs
- **Air freight coordination** — time-sensitive consignments
- **Customs clearance liaison** — coordination with licensed customs brokers, documentation preparation, filing support `[CONFIRM exact scope — see note below]`
- **Import and export documentation** — commercial invoice, packing list, BL/AWB, bill of entry support
- **Origin and FTA compliance support** — Proof of Origin, CAROTAR Form I, preference claims under India's trade agreements
- **Project and oversize cargo coordination** `[CONFIRM if in scope]`

> **Note for Ashwin, not for the site:** until the CBLR 2018 customs broker licence is obtained, wording must be "coordination with licensed customs brokers" or "clearance liaison" — not "we clear your cargo." Filing a bill of entry without a licence is a regulatory problem, and the site is the first place a customs officer or client would look.

### About
- The principal: name, background, why the ERP/supply-chain history matters for freight documentation accuracy
- The model: what a commission-based agent is, stated plainly
- Registration details: GSTIN, proprietorship, Chennai jurisdiction
- No "our philosophy" / "our genes" corporate abstraction — APC can afford that, a new agent can't

### Contact
- Form: name, company, email, phone, enquiry type (import / export / customs / other), message
- Wire to Formspree or Netlify Forms — no backend. Add code comments explaining the setup step.
- Direct email, phone, address as text
- GSTIN displayed

## Tech

- Static HTML/CSS, minimal JS. No build step. Deploy to Netlify, Vercel, or GitHub Pages.
- Mobile-first. Most first contacts will open this on a phone.
- Favicon from `baybridge-mark.svg`.
- Meta description and Open Graph tags, following APC's pattern: name the service and the location. Target phrases: freight forwarding agent Chennai, customs clearance Chennai, logistics agent Tamil Nadu.
- Accessible: visible focus states, alt text, contrast that passes AA against the navy.

## Deliverables

1. The site, deployable as-is
2. `README.md` — local preview, deploy steps for one host, Formspree wiring, and where every `[FILL IN]` lives
3. HTML comments at each placeholder

## Out of scope

Quote calculator, shipment tracking, login, payments, blog.
