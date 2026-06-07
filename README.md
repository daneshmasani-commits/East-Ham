# East Ham Dental Care — Dental Clinic Website

A single-page, static website for **East Ham Dental Care**, a family-run dental practice on Barking Road, East Ham, London (NHS & private treatment), run by the Deo family.

> ⚠️ **This is a pitch template.** The practice has not engaged us yet — this is a tailored draft to show what we can produce. Some content is placeholder and clearly flagged with `[TO CONFIRM]` / `[TO ADD]` both on the page (highlighted) and in code comments. See the checklist at the bottom.

It is a sibling to our G K Ooi & Associates site — same structure and technical quality bar, deliberately distinct visual identity (sage/forest green + warm cream + brass, with Fraunces + Figtree typography instead of the reference's blues and Inter).

## Tech

- Plain **HTML + CSS + vanilla JavaScript** — no framework, no build step, no jQuery.
- Mobile-first, responsive (tested at 360 / 768 / 1024 / 1440px).
- Semantic, accessible HTML (landmarks, ARIA, alt text, full keyboard navigation).
- Deployable to any static host (Netlify, Vercel, GitHub Pages).

## File structure

```
/
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── main.js
├── assets/
│   ├── logo.png          # client-supplied logo (tooth + leaves + wordmark; background knocked out, transparent)
│   └── favicon.svg
└── README.md
```

> Stock images are referenced via hosted **Unsplash URLs** in the HTML (no API key, nothing to download). Swap these for the client's real photography when available.

## How to view locally

It's a static site, so any of these work:

**Option 1 — open the file directly**
Double-click `index.html`, or open it in your browser.

**Option 2 — run a tiny local server (recommended; avoids any file:// quirks)**
```bash
# Python 3
python3 -m http.server 8000
# then visit http://localhost:8000
```
or
```bash
# Node
npx serve .
```

## Features implemented (per brief)

- Sticky top nav with smooth-scroll anchors and **active-section highlighting**.
- Mobile hamburger menu.
- Persistent **Book Now** button — floating bottom-right on desktop, sticky bottom bar on mobile.
- Hero, About (2×2 value cards with custom monoline brass icons), Services (expandable items), Reviews (auto-rotating carousel), Team grid, FAQ accordion (one open at a time), Booking form, Find us (map), Footer.
- Reviews carousel: ~6s auto-advance, pause on hover/focus, prev/next, dot indicators, keyboard arrows, respects `prefers-reduced-motion`.
- Booking form: HTML5 + JS validation, silent submit to **Formspree** (`https://formspree.io/f/mqeopwwg`), inline success/error messages, no external app opens.
- **Cookie consent banner** on first visit; the Google Map iframe only loads **after** consent (UK GDPR).
- GDC compliance placeholder line in the footer.

## ✅ Placeholders to confirm with the client

These are flagged on-page (highlighted) and as `[TO CONFIRM]` / `[TO ADD]` comments in `index.html`:

- [ ] **Founding year** (hero headline currently reads "since [year TBC]") and family-history details.
- [ ] **Real bios and photos** for every team member.
- [ ] **GDC registration numbers** for each clinician (footer compliance line).
- [ ] Confirmation that **all listed services are offered** (and any to add/remove).
- [ ] **Real pricing** (currently indicative private prices + standard NHS bands).
- [ ] **Real email address** (currently `contact@easthamdentalcare.co.uk` placeholder).
- [ ] **Full names** for J Fowles, B Deo, and all dental nurses.
- [ ] **Additional 5★ reviews** — 5 real reviews are in; 4 clearly-marked `[TO ADD: 5★ review]` slots remain (target 3–5 more from the practice's Google listing, 64 total).
- [ ] **Opening hours** (currently Mon–Fri 9–5, Sat & Sun closed).
- [ ] **Privacy policy** and **cookie policy** content (footer + cookie banner links).
- [ ] **Complaints procedure** wording.
- [ ] Whether they are **currently accepting new patients** (FAQ 6).

## Notes for developers

- Colour palette and type scale live as CSS custom properties at the top of `css/styles.css` — change them in one place.
- The map embed URL is stored in `data-map-src` on `#mapEmbed` and injected by JS only after consent.
- To reset the cookie choice while testing: clear `localStorage` key `eastham_cookie_consent` (DevTools → Application → Local Storage).
- The logo (`assets/logo.png`) is the client-supplied mark with its mockup background knocked out to transparency. On the dark footer it sits on a light "chip" (`.footer-brand-chip`) so its colours read; swap in a reversed/white version if the client supplies one.
