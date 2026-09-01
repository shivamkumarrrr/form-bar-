# form.bar Business Landing Page — Build Spec

## Project Overview

Rebuild the B2B landing page for form.bar (a custom furniture manufacturer). The current page is at `form.bar/de-DE/service/business-service`. We are building a standalone HTML landing page that will replace it later.

**Client:** form.bar (by okinlab GmbH, Saarbrücken)
**Middleman:** Patrick (relays questions to the form.bar client)
**Budget:** max 20 hours for first version
**Deadline:** End of September 2026

## What Patrick Wants Improved

- Better reference images (current page shows images only on mobile — known bug)
- Better target audience addressing
- The page should look and feel like it belongs to the form.bar ecosystem

## Target Audiences

### 1. Companies with representative reception areas
- Arztpraxen (medical practices)
- Steuerberater (tax advisors)
- Rechtsanwalt (lawyers)
- Friseur (hair salons)
- Marketing-Agentur (marketing agencies)
- Architekten (architects)

### 2. Upscale retail
- Mode (fashion)
- Geschirr (tableware/ceramics)
- Kaffee (specialty coffee)

## Main Products to Feature

- **Empfangstheke** (reception desks)
- **Designregale** (design shelves / display shelving)
- **Individuelle Konstruktionen** (custom constructions — e.g. restaurant interiors, bar counters, wall cladding, room dividers)

## Current Business Page Structure (what exists now)

1. Hero: "Du arbeitest im Bereich..." with industry list (Design & Architektur, Einzelhandel & Showrooms, Healthcare, Praxen, Kita/Schule & Ferienhäuser, Büroausstattung, Hotel & Gastronomie)
2. CTA: "Dann werde Mitglied und inspiriere deine Kunden & deine Mitarbeiter" with "JETZT BEITRETEN" button
3. "Schnelle Lieferzeiten auf Anfrage"
4. Project showcase with tabs: Ladengeschäfte, Messen, Gastronomie, Büros
5. Another "JETZT BEITRETEN" button
6. Contact section: "Deine Kontaktmöglichkeiten" — Live-Chat, E-Mail, Rückruf, Direkt anrufen, WhatsApp
7. "Weitere Farben auf Anfrage" section about custom materials
8. "Das sagen unsere Kunden" — testimonials with star ratings
9. Footer

## Tone & Language

- German language
- Uses "du" (informal) — consistent with the rest of form.bar
- Friendly, professional, design-forward
- Not corporate stiff — approachable but competent

---

## Design System

### Fonts

**Font family: Carnero W01** (licensed webfont, NOT on Google Fonts)

All font files hosted on `static.form.bar/fe-ressources/fonts/`. Use these @font-face declarations:

```css
@font-face {
  font-family: "Carnero W01 Light";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769275/919a2130-c858-48ac-ab81-57d322308e09.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769275/01c6b44f-408f-4297-a149-11eec4aa91eb.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Light Italic";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769283/0eb538c9-492e-40d1-939f-cec781ce1684.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769283/7fd40b62-80b9-4e66-8abf-292aa004d43e.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Book";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769291/eda3d5a2-6c59-44b9-95b6-15448937cbe6.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769291/adfa959a-0970-4b31-ac74-5dcdb30dd4ee.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Book Italic";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769299/3b3d5ea8-4c29-4fbd-9b01-5613d3d491ba.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769299/039a60b0-f97a-4596-9dbd-2da3b5aff3e2.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Regular";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769304/6e2aa19a-7c07-464f-a7f5-d77c3e88a25c.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769304/df488456-1e38-44ee-9615-e76b634db259.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Italic";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769311/14690c94-4a90-4608-a728-b2777a54f684.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769311/342bbb58-e6f2-4aee-82a2-dedc61cc4b77.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Semibold";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769319/7217b91c-61e9-48fd-8c63-e791a88971a7.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769319/5920bb16-b902-446b-9253-d918ee15def5.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Semibold Italic";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769325/846d4265-946b-4725-87fa-6fff8b610129.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769325/30b88e12-fa3e-4976-ac06-9db4f9669f33.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Bold";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769335/c2b01d18-dfd4-481e-a5f5-50a1f6d19528.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769335/4846658e-32a6-4963-8c3b-ccb9a24c1d77.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Bold Italic";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769343/11418712-62a3-4947-b9e6-ca1e6714c07a.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769343/01437eec-3731-437a-95f0-fee030f4fa55.woff") format("woff");
}

@font-face {
  font-family: "Carnero W01 Black";
  font-display: swap;
  src: url("https://static.form.bar/fe-ressources/fonts/5769351/9eda3eaa-c10c-4b78-8146-16525faf2e79.woff2") format("woff2"),
       url("https://static.form.bar/fe-ressources/fonts/5769351/7f719f16-e879-479a-8991-3430d2e60ebf.woff") format("woff");
}
```

**Font usage by context:**
- Headings: "Carnero W01 Bold"
- Subheadings: "Carnero W01 Regular"
- Labels / Buttons: "Carnero W01 Regular"
- Body / Paragraphs: "Carnero W01 Light" (small), "Carnero W01 Book" (medium+)
- Links: "Carnero W01 Semibold" with underline
- Quotes: "Carnero W01 Book Italic"
- Logo text: "Carnero W01 Semibold Italic"
- Fallback stack: "Segoe UI", Roboto, Arial, sans-serif

**Font sizes (desktop):**
- Heading L: 116px
- Heading M: 89px (XL screens: 116px, below 1023px: 55px)
- Heading S: 55px
- Heading XS: 34px
- Subheading L: 55px
- Subheading M: 34px
- Subheading S: 28px
- Subheading XS: 21px
- Text L: 28px
- Text M: 21px
- Text S: 16px
- Text XS: 13px
- Line heights: 120% (headings), 140% (everything else)

### Colors

**Primary (anthracite blue-grey):**
- `#383B4A` — primary (text, dark backgrounds)
- `#5B5E6E` — primary shade light (hover text, descriptions)
- `rgba(91, 94, 110, 0.7)` — primary transparent

**Secondary (mint green — used for CTAs, accents):**
- `#91E3B7` — secondary (CTA buttons, highlights)
- `#63B48A` — secondary shade dark (text highlights)
- `#C9ECD9` — secondary shade light (hover states)
- `#EEFDF4` — secondary shade lighter
- `rgba(145, 227, 183, 0.8)` — secondary transparent

**Tertiary (grey):**
- `#B4B6BE` — tertiary
- `#ECEFF0` — tertiary light (light backgrounds, borders)
- `#FAFAFA` — tertiary lighter (almost white backgrounds)

**Neutral:**
- `#FFFFFF` — white

**Accent colors:**
- `#C9FFF5` — blue lagoon
- `#FFDCD4` — red oxide
- `#FFFFBD` — yellow sand
- `#E8E7F3` — lilac

**Alert/Warning:**
- `#A94442` — warning (error text)
- `#FFBAAA` — warning light
- `#FFDCD4` — warning lighter

### Spacing Scale

Fibonacci-near progression (skips 5):
- 4xs: 3px
- 3xs: 8px
- 2xs: 13px
- xs: 21px
- s: 34px
- m: 55px
- l: 89px
- xl: 144px
- 2xl: 233px
- 3xl: 377px
- 4xl: 610px
- 5xl: 987px

### Border Radii
- xs: 3px
- s: 8px
- m: 21px
- l: 34px
- xl: 55px

### Borders
- xs: 1px
- s: 2px
- m: 3px

### Breakpoints
- xs: 480px
- s: 768px
- m: 1023px
- l: 1400px
- xl: 1700px

### Page Margins (% based, responsive)
**Body margins:**
- xs/s: 5%
- m: 5%
- l: 8%
- xl: 10%

**Section margins:**
- xs/s: 5%
- m: 10%
- l: 15%
- xl: 20%

### Shadows
- Default: `3px 3px 8px 0 #ECEFF0`

### Transitions
- Short: 0.1s
- Default: 0.3s
- Long: 1s

### Menu Height
- 59px

---

## Reference Content — Magazine Links

These are existing form.bar magazine articles about business customers. Use them for reference images, testimonials, and case study content. Visit each to pull photos and quotes.

### Empfangstheken (Reception Desks)
- Honighalle: `https://www.form.bar/de-DE/inspiration/magazin/honighalle`
- Agentur-Theke (Benjamin Knur): `https://www.form.bar/de-DE/inspiration/magazin/benjamin-knur`

### Office / Büro
- Michael Hilgers – Office Produkte: `https://www.form.bar/de-DE/inspiration/magazin/michael-hilgers`
- Office Regal (Konstantin Küspert): `https://www.form.bar/de-DE/inspiration/magazin/konstantin-küspert`
- Homeoffice (Paula Biesenkamp): `https://www.form.bar/de-DE/inspiration/magazin/paula-biesenkamp`

### Marketing / Agentur
- Dennis Lück – Marketing Agentur des Jahres: `https://www.form.bar/de-DE/inspiration/magazin/dennis-lück`
- Sideboard/Sitzbank Agentur (Claudia Henze): `https://www.form.bar/de-DE/inspiration/magazin/claudia-henze`

### Retail / Showroom
- Black Henn – Verkaufsregal: `https://www.form.bar/de-DE/inspiration/magazin/blackhen`
  - Video: `https://www.instagram.com/reel/DbF7s-BoyFG/`

### Gastronomie / Food
- SterneKoch Erfurt, Akustikregal (Klaus Erfort): `https://www.form.bar/de-DE/inspiration/magazin/klaus-erfort`

### Gaming / Creative
- Fabienne – Gaming Industry: `https://www.form.bar/de-DE/inspiration/magazin/fabiennexiii`

### Musik
- Holger – Berufsmusiker: `https://www.form.bar/de-DE/inspiration/magazin/holger-wohlfahrt`

### Besprechung / Konferenz
- Besprechungstisch (Alexandra Jürgens): `https://www.form.bar/de-DE/inspiration/magazin/alexandra-jürgens`

### Brand / Corporate
- Adidas Brand Regal: `https://www.form.bar/de-DE/inspiration/magazin/filmstars`

### Healthcare / Praxis
- Zahnarztpraxis: `https://okinlab.com/work/zahnarztpraxis/`

### Kita / Education
- Kita Blümchen: `https://okinlab.com/work/kinderkrippe/`

### Gallery (filter by Business-Design)
`https://www.form.bar/de-DE/inspiration/galerie`

### YouTube
`https://www.youtube.com/c/FormBar`

## Business Customers (for social proof / logo strip)

These are actual form.bar business customers:
Bosch, Villeroy & Boch, Audi, Adidas, Google, Sky, Globus, Augenklinik Sulzbach, Bose, HKS, Roccat, Universität des Saarlandes, Spiegel, Kaffeehaus Soest, Airyoga, Evangelische Kirche Hannover, Grundschule Sudweyhe, Forschungsgruppe Verhaltensbiologie, Passlack Consulting, Wohnungswesen Münster, Luxembourg Science Center, Tourismus Zentrale Merzig, Polarforschung, Caritas, MunichMed

---

## Build Instructions

### Output
Single `index.html` file with all CSS inline. No external dependencies except the Carnero font files from static.form.bar.

### Visual Direction
- Match form.bar's existing aesthetic: clean, white backgrounds, rounded corners, spacious layout
- Mint green (#91E3B7) CTA buttons with dark text (#383B4A)
- Dark anthracite (#383B4A) header/footer sections
- Product images in rounded containers
- Subtle, modern — not loud or salesy

### Page Sections to Build

1. **Navigation** — formbar logo (in Carnero Semibold Italic), simple nav
2. **Hero** — B2B focused headline addressing business owners, subtitle about custom furniture for commercial spaces
3. **Industry tabs/cards** — Target audiences with relevant imagery (from magazine links above)
4. **Products** — Empfangstheken, Designregale, Sonderkonstruktionen with real images from the magazine articles
5. **Client logos** — Social proof strip with the business customer names listed above
6. **Process** — How it works (Beratung, Entwurf, Fertigung, Lieferung)
7. **References/Testimonials** — Pull real quotes from the magazine articles
8. **Contact/CTA** — Multiple contact options (matching current page: Live-Chat, E-Mail, Rückruf, WhatsApp, phone)
9. **Footer** — formbar branding

### Image Strategy
- Visit each magazine link above and download/reference the best business-relevant images
- For image placeholders where real images aren't available yet, use dashed-border boxes with descriptive text of what image should go there
- Prioritize: reception desks, retail shelving, office setups, restaurant/gastro interiors

### Do NOT
- Invent statistics (like "64.000+ Kunden") unless verified from the actual site
- Make up testimonial quotes — only use real ones from the magazine articles
- Use any font other than Carnero W01 variants
- Use warm/wood-tone color palettes — stick to the cool anthracite + mint green
- Use serif fonts like Fraunces or Georgia
- Add dark mode (form.bar doesn't have one)
