# form.bar Business Landing Page — Build Spec

## Project Overview

Rebuild the B2B landing page for **form.bar** (custom furniture manufacturer by okinlab GmbH, Saarbrücken). The current page lives at `form.bar/de-DE/service/business-service`. We are building a standalone HTML landing page that will replace it later.

**Client:** form.bar (by okinlab GmbH, Saarbrücken)
**Founders:** Nikolas Feth (architect) & Alessandro Quaranta
**Founded:** 2013
**Team:** ~20 employees
**Partner network:** 80+ carpentry workshops across Germany and Europe
**Middleman:** Patrick (relays questions to the form.bar client)
**Budget:** max 20 hours for first version
**Deadline:** End of September 2026

## What Patrick Wants Improved

From the original briefing:
- "Bessere Referenzen Bilder" — better reference/project images (current page has a bug where images only show on mobile)
- "Bessere Ansprache" — better addressing of target audiences
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

- **Empfangstheken** (reception desks) — organic-shaped reception counters for lobbies, practices, agencies
- **Designregale** (design shelves) — display shelving for retail, showrooms, offices
- **Individuelle Konstruktionen** (custom constructions) — restaurant interiors, bar counters, wall cladding, room dividers, conference tables, acoustic elements

## Current Business Page (what exists now — to be replaced)

Based on screenshots of `form.bar/de-DE/service/business-service`:

1. Hero: "Du arbeitest im Bereich..." listing industries: Design & Architektur, Einzelhandel & Showrooms, Healthcare, Praxen, Kita/Schule & Ferienhäuser, Büroausstattung, Hotel & Gastronomie
2. CTA: "Dann werde Mitglied und inspiriere deine Kunden & deine Mitarbeiter" + "JETZT BEITRETEN" button
3. "Schnelle Lieferzeiten auf Anfrage"
4. Project showcase with category tabs: Ladengeschäfte, Messen, Gastronomie, Büros — with project images
5. Another "JETZT BEITRETEN" button
6. Contact section: "Deine Kontaktmöglichkeiten" — Live-Chat starten, E-Mail schreiben, Rückruf buchen, Podcast buchen, Direkt anrufen, WhatsApp
7. "Weitere Farben auf Anfrage" — info about custom materials and colors
8. "Das sagen unsere Kunden" — customer testimonials with star ratings
9. Footer with 4.74 rating badge, newsletter signup, links (SERVICE, FORM.BAR, FORM.BAR+, BUSINESS), social icons

## Tone & Language

- German language
- Uses "du" (informal) — consistent with the rest of form.bar's site
- Friendly, professional, design-forward
- Not corporate stiff — approachable but competent

---

## Design System

All values extracted from the actual form.bar LESS source files (variables-base.less, variables.less, fonts.less).

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

**Font usage by context (from the LESS mixins):**
| Context | Font Family | Line Height |
|---------|-----------|-------------|
| Headings | "Carnero W01 Bold" | 120% |
| Subheadings | "Carnero W01 Regular" | 140% |
| Labels | "Carnero W01 Regular" | 140% |
| Buttons | "Carnero W01 Regular" (m/s/xs), "Carnero W01 Semibold" (l) | 140% |
| Paragraphs (s) | "Carnero W01 Light" | 140% |
| Paragraphs (m+) | "Carnero W01 Book" (m), "Carnero W01 Light" (m alt) | 140% |
| Links | "Carnero W01 Semibold" + underline | 140% |
| Quotes | "Carnero W01 Book Italic" | 140% |
| Logo text | "Carnero W01 Semibold Italic" | 140% |
| Fallback | "Segoe UI", Roboto, Arial, sans-serif | — |

**Font sizes (desktop → mobile below 1023px):**
| Token | Desktop | Mobile |
|-------|---------|--------|
| Heading L | 116px | 89px |
| Heading M | 89px (116px on XL 1700px+, 70px on 1023-1400px, 55px below 1023px) | 55px |
| Heading S | 55px | 55px |
| Heading XS | 34px | 34px |
| Subheading L | 55px | 55px |
| Subheading M | 34px | 34px |
| Subheading S | 28px | 28px |
| Subheading XS | 21px | 21px |
| Text L | 28px | 28px |
| Text M | 21px | 21px |
| Text S | 16px | 16px |
| Text XS | 13px | 13px |

### Colors

**Primary (anthracite blue-grey):**
- `#383B4A` — primary (text color, dark backgrounds, primary buttons)
- `#5B5E6E` — primary shade light (hover text, description text)
- `rgba(91, 94, 110, 0.7)` — primary transparent (overlays)

**Secondary (mint green — CTA buttons, success states, accents):**
- `#91E3B7` — secondary (CTA buttons, active states, logo highlight)
- `#63B48A` — secondary shade dark (text highlights)
- `#C9ECD9` — secondary shade light (hover states, success backgrounds)
- `#EEFDF4` — secondary shade lighter

**Tertiary (neutral grey):**
- `#B4B6BE` — tertiary (disabled text, placeholders, dividers)
- `#ECEFF0` — tertiary light (light backgrounds, borders, inactive areas)
- `#FAFAFA` — tertiary lighter (near-white section backgrounds)

**Neutral:**
- `#FFFFFF` — white (default background, neutral controls)

**Accent colors (used sparingly for variety):**
- `#C9FFF5` — blue lagoon
- `#FFDCD4` — red oxide
- `#FFFFBD` — yellow sand
- `#E8E7F3` — lilac

### Spacing Scale

Values from `variables-base.less`. Fibonacci-near progression:

| Token | Value | Used for |
|-------|-------|----------|
| 4xs | 3px | Tiny gaps, border widths |
| 3xs | 8px | Small padding, icon gaps |
| 2xs | 13px | Inner padding, small gaps |
| xs | 21px | Default gap, standard padding |
| s | 34px | Section inner spacing |
| m | 55px | Large gaps, section padding |
| l | 89px | Major section spacing |
| xl | 144px | Hero-level spacing |
| 2xl | 233px | Page-level spacing |
| 3xl | 377px | — |
| 4xl | 610px | — |
| 5xl | 987px | Max content widths |

### Border Radii
| Token | Value |
|-------|-------|
| xs | 3px |
| s | 8px |
| m | 21px |
| l | 34px |
| xl | 55px |

form.bar uses generous rounded corners — product cards and images typically use radius-m (21px) or radius-l (34px). The product images on the Möbel page use large rounded corners (visible in screenshots).

### Breakpoints
| Token | Value |
|-------|-------|
| xs | 480px |
| s | 768px |
| m | 1023px |
| l | 1400px |
| xl | 1700px |

### Page Margins (responsive, percentage-based)

| Screen | Body margin | Section margin |
|--------|------------|----------------|
| xs (< 480px) | 5% | 5% |
| s (480-767px) | 5% | 5% |
| m (768-1023px) | 5% | 10% |
| l (1024-1399px) | 8% | 15% |
| xl (1400+) | 10% | 20% |

### Other Tokens
- **Shadows:** `3px 3px 8px 0 #ECEFF0`
- **Transitions:** short 0.1s, default 0.3s, long 1s
- **Menu height:** 59px
- **Borders:** xs=1px, s=2px, m=3px

### Scroll Reveal Animations

The site uses a `.sr` (scroll reveal) system from `baseClasses.less`:
- `.sr` — base class, starts hidden (opacity: 0)
- `.sr.sr-visible` — revealed state (opacity: 1)
- Variants: `.sr-fade-up`, `.sr-fade-down`, `.sr-fade-left`, `.sr-fade-right`, `.sr-zoom-in`
- Transition: 1s ease-out

Implement scroll reveal with IntersectionObserver in the landing page.

---

## Reference Content

### Magazine Articles (visit each for images, quotes, case studies)

These are form.bar magazine articles featuring real business customers. **Visit each link to extract real photos and real customer quotes** — do not invent quotes.

| Category | Customer | Product | Link |
|----------|----------|---------|------|
| Empfangstheke | Julius Schießer, Honighalle (unpackaged store, Friedrichsdorf) | Reception desk/counter | `https://www.form.bar/de-DE/inspiration/magazin/honighalle` |
| Agentur-Theke | Benjamin Knur | Agency reception counter | `https://www.form.bar/de-DE/inspiration/magazin/benjamin-knur` |
| Office | Michael Hilgers | Office furniture products | `https://www.form.bar/de-DE/inspiration/magazin/michael-hilgers` |
| Office Regal | Konstantin Küspert | Office shelf | `https://www.form.bar/de-DE/inspiration/magazin/konstantin-küspert` |
| Homeoffice | Paula Biesenkamp | Home office setup | `https://www.form.bar/de-DE/inspiration/magazin/paula-biesenkamp` |
| Marketing-Agentur | Dennis Lück (BrinkertLück Creatives, top EU ad professional) | Shelf — quote: "The shape of the shelf inspires me" | `https://www.form.bar/de-DE/inspiration/magazin/dennis-lück` |
| Agentur Sideboard | Claudia Henze | Sideboard & bench | `https://www.form.bar/de-DE/inspiration/magazin/claudia-henze` |
| Verkaufsregal | Black Henn | Retail display shelf | `https://www.form.bar/de-DE/inspiration/magazin/blackhen` |
| Gastronomie | Klaus Erfort (2-Michelin-star chef, GästeHaus, Saarbrücken) | Acoustic shelf | `https://www.form.bar/de-DE/inspiration/magazin/klaus-erfort` |
| Gaming | Fabienne | Gaming industry setup | `https://www.form.bar/de-DE/inspiration/magazin/fabiennexiii` |
| Musik | Holger Wohlfahrt | Musician's shelf | `https://www.form.bar/de-DE/inspiration/magazin/holger-wohlfahrt` |
| Besprechung | Alexandra Jürgens | Conference table | `https://www.form.bar/de-DE/inspiration/magazin/alexandra-jürgens` |
| Corporate | Adidas | Brand shelf | `https://www.form.bar/de-DE/inspiration/magazin/filmstars` |
| Healthcare | Zahnarztpraxis (dental practice) | Practice furniture | `https://okinlab.com/work/zahnarztpraxis/` |
| Education | Kita Blümchen (daycare) | Children's furniture | `https://okinlab.com/work/kinderkrippe/` |

**Video:** Black Henn Instagram Reel — `https://www.instagram.com/reel/DbF7s-BoyFG/`
**Gallery** (filter by Business-Design): `https://www.form.bar/de-DE/inspiration/galerie`
**YouTube:** `https://www.youtube.com/c/FormBar`

### Business Customers (social proof)

These are verified form.bar business customers (from internal reference document). Use for a "Vertrauen uns" / "Trusted by" logo strip or name list:

**Big names:** Bosch, Villeroy & Boch, Audi, Adidas, Google, Sky, Bose, Spiegel
**Institutions:** Universität des Saarlandes, Luxembourg Science Center, Evangelische Kirche Hannover, Grundschule Sudweyhe, Forschungsgruppe Verhaltensbiologie, Polarforschung, Caritas
**Healthcare:** Augenklinik Sulzbach, MunichMed
**Business:** HKS, Roccat, Passlack Consulting, Wohnungswesen Münster, Tourismus Zentrale Merzig, Kaffeehaus Soest, Airyoga, Globus

---

## Build Plan

### Output
Single `index.html` file with all CSS inline (in `<style>` tags). No external dependencies except the Carnero W01 font files from `static.form.bar`.

### Visual Direction

Study the existing form.bar site (screenshots provided + live site at form.bar) to match their aesthetic:
- **Clean white backgrounds** with `#FAFAFA` alternate sections
- **Mint green (#91E3B7) CTA buttons** with dark `#383B4A` text
- **Dark anthracite (#383B4A)** for text, header area, and footer band
- **Generous rounded corners** (21px-34px on cards and images, matching the Möbel page product tiles)
- **Spacious layout** with percentage-based responsive margins
- Product images shown in soft green archway/niche backgrounds (as seen on the Möbel page — the rendered product images sit in sage-green arched alcoves)
- Navigation: "formbar" logo in Carnero Semibold Italic, with main nav items: SELBST FORMEN (green pill button), MÖBEL, INSPIRATION, SERVICE, plus flag/phone/cart/profile icons
- Bottom banner: dark anthracite background with "Let's work together!" text + photo, "Jetzt teilnehmen" green CTA

### Page Sections (in order)

#### 1. Navigation Bar
- Match the existing form.bar nav exactly: logo left, centered nav items, utility icons right
- Height: 59px
- Logo: "formbar" in Carnero Semibold Italic, with "BUSINESS" subtitle

#### 2. Hero Section
- Full-width, addressing business owners directly with "du"
- Headline that speaks to the value proposition for businesses
- Industry list (from target audiences above) — styled as tags or a visual list
- Large hero image showing an impressive business installation (use best image from magazine articles, or placeholder)
- CTA: "Jetzt beitreten" (matching existing) or "Beratung anfragen"

#### 3. Project Showcase (with category tabs)
- Tabbed gallery: Ladengeschäfte, Messen, Gastronomie, Büros (matching current page's tabs)
- Pull real project images from the magazine article links above
- Each project card: image + brief description + link to magazine article
- This is the section Patrick specifically wants improved with better images

#### 4. Products / Leistungen
- Three product cards: Empfangstheken, Designregale, Sonderkonstruktionen
- Each with a strong image, short description, and CTA
- Use images from magazine articles that match each product type

#### 5. Target Audience Section
- Two columns or cards:
  1. "Repräsentative Geschäftsräume" — Praxen, Kanzleien, Agenturen, Architekten, Friseure
  2. "Gehobener Einzelhandel" — Mode, Keramik/Geschirr, Kaffee, Concept Stores
- Industry tags for each
- Relevant imagery

#### 6. Social Proof / Kundenlogos
- "Vertrauen uns" or similar heading
- Display the big-name business customers: Bosch, Adidas, Google, Audi, Bose, Sky, Villeroy & Boch, Spiegel
- Simple text list or logo strip (logos would need to be sourced separately)

#### 7. Testimonials
- "Das sagen unsere Kunden" — pull REAL quotes from the magazine articles only
- Verified quote from Dennis Lück: "The shape of the shelf inspires me"
- Visit other magazine links to extract more real quotes
- Star ratings if available from the articles
- The current page has a 4.74 rating badge — keep this if the source can be verified

#### 8. Process / So funktioniert's
- 4 steps: Beratung → Entwurf → Fertigung → Lieferung
- Simple, clean step cards

#### 9. Contact / Kontaktmöglichkeiten
- Match the current page's contact options:
  - Live-Chat starten
  - E-Mail schreiben
  - Rückruf buchen
  - Direkt anrufen
  - WhatsApp
- Each as a card/button with icon

#### 10. CTA Band
- Dark anthracite background
- "Let's work together!" or similar
- "Jetzt beitreten" green CTA button
- Photo of team/business context

#### 11. Footer
- Match existing form.bar footer structure
- formbar logo + "forme deine Welt"
- Contact info, links (SERVICE, FORM.BAR, FORM.BAR+, BUSINESS)
- Rating badge (4.74)
- Newsletter signup
- Social icons
- Legal links (AGB, Datenschutz, Widerruf, Impressum)

### Responsive Behavior
- Use the breakpoints and margin system from the design system above
- Mobile-first approach
- Product grids: 3 columns desktop → 2 tablet → 1 mobile
- Nav collapses to hamburger on mobile

### Image Strategy

1. **First priority:** Visit each magazine link and extract the best business-relevant photos (reception desks, retail shelving, office setups, restaurant interiors)
2. **For any section where real images aren't available:** Use dashed-border placeholder boxes (`border: 2px dashed #ECEFF0`) with descriptive text of what image should go there
3. **Image treatment:** Rounded corners (radius-m 21px or radius-l 34px), matching the product tile style on the Möbel page

### Animations & Motion

The page should feel alive and polished — not static. form.bar's own site uses scroll-reveal animations and smooth transitions. Implement the following:

#### Scroll Reveal (matching form.bar's system)
- Elements fade/slide in as they enter the viewport
- Use IntersectionObserver (vanilla JS, no library needed)
- Variants to use:
  - **Fade up** — most content sections, cards, text blocks (translate Y 30-40px → 0)
  - **Fade in** — images, logos (opacity 0 → 1)
  - **Staggered** — grid items (cards, logos, process steps) appear one after another with 100-150ms delay between each
- Timing: 0.6-0.8s ease-out, trigger when element is ~20% visible
- Elements should only animate once (not re-trigger on scroll back up)

#### Hover Effects
- **CTA buttons:** subtle scale (1.02-1.03) + slight shadow increase on hover, 0.3s transition
- **Product/project cards:** gentle lift (translateY -4px) + shadow deepening on hover
- **Contact option cards:** background color shift to mint green lighter (#EEFDF4) on hover
- **Links:** color transition to secondary shade dark (#63B48A)
- **Tab buttons:** active tab gets mint green underline/background with smooth transition

#### Hero Section
- Hero image or content area: subtle parallax or scale effect on scroll (optional, keep it subtle)
- Headline: fade-up on page load with slight delay between headline and subtitle
- CTA buttons: fade-in after headline, staggered

#### Tab/Category Switching (Project Showcase)
- Smooth crossfade between tab content (opacity transition, 0.3s)
- Active tab indicator animates (slides) to selected tab position
- Content inside tabs can have a subtle slide-left/slide-right depending on direction

#### Logo/Client Strip
- Optional: slow continuous horizontal scroll (CSS marquee-style animation) for the client names/logos
- Or: static grid that fades in with staggered timing

#### Counter/Stats (if included)
- Count-up animation for any numbers when they scroll into view
- Use requestAnimationFrame for smooth counting

#### Smooth Scrolling
- `scroll-behavior: smooth` on html
- Anchor links (nav → sections) scroll smoothly
- Optional: slightly offset scroll position to account for sticky nav

#### Performance
- Use `will-change: transform, opacity` sparingly on animated elements
- Prefer CSS transforms over layout-triggering properties
- Use `prefers-reduced-motion` media query to disable animations for accessibility:
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

#### What NOT to animate
- No heavy parallax or scroll-jacking
- No loading spinners or skeleton screens (it's a static page)
- No bouncing or elastic effects (doesn't match form.bar's calm aesthetic)
- No auto-playing video backgrounds
- Keep it elegant and subtle — form.bar is a design brand, not a gaming site

### Technology Note

form.bar's main site is built with Vue.js (evidence: Vue `:deep()` selectors in their CSS, component-based architecture). However, for this standalone landing page:
- **Build as a single HTML file** with inline `<style>` and `<script>` tags
- This keeps it framework-agnostic and easy to integrate later into their Vue/Nuxt app or GrapeJS editor
- All animations should be vanilla CSS + vanilla JS (IntersectionObserver, requestAnimationFrame)
- No external JS libraries needed — GSAP is overkill for what we need
- If you want a library for scroll animations, you may use a lightweight one loaded from CDN (e.g., `gsap` from cdnjs), but vanilla JS is preferred

### Do NOT
- Invent statistics — only use numbers that can be verified from the actual site or official sources (verified: 80+ partner carpentries, ~20 employees, founded 2013)
- Make up testimonial quotes — only use real ones found on the magazine article pages
- Use any font other than Carnero W01 variants with the exact font-face declarations above
- Use warm/wood-tone color schemes — stick to the cool anthracite (#383B4A) + mint green (#91E3B7) palette
- Use serif fonts like Fraunces, Georgia, or any Google Font
- Add dark mode (form.bar doesn't have one)
- Invent a design system — use the exact values documented above from the LESS source files
