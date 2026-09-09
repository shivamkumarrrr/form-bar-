# form.bar — Business Landing Page

Standalone landing page for form.bar's B2B audience, built to replace
`form.bar/de-DE/service/business-service`.

German copy throughout, informal address ("du"), matching the tone of the rest of
the site.

## What's in here

```
index.html          the whole page — markup, CSS and JS in one file
assets/img/         photos (WebP + JPG fallback, 1120×1120 or wider)
assets/img/logos/   customer logos (SVG)
```

No build step, no dependencies, no framework. Open `index.html` in a browser and
it runs. `package.json` only pulls in Playwright, which was used for screenshot
checks during development — it is not needed to run or ship the page.

## Why a single file

The page is meant to be integrated into form.bar's own stack, not deployed on its
own. Keeping everything in one file means:

- it can be pasted into a CMS block or a Vue/Nuxt single-file component without
  untangling a build pipeline first,
- there are no bundler assumptions to reconcile with the existing setup,
- nothing loads from a third-party CDN, so there is no new external dependency to
  review.

Splitting the CSS and JS into separate files is a five-minute job if that suits
the integration better — the sections are already marked with comments.

## Design tokens

Every colour, spacing value, radius and breakpoint comes from form.bar's own
`variables-base.less` / `variables.less`, declared as CSS custom properties at the
top of `index.html`. The mapping is one to one:

| CSS custom property | LESS variable | Value |
|---|---|---|
| `--c-primary` | `@color-base-primary` | `#383B4A` |
| `--c-primary-light` | `@color-base-primary-shade-light` | `#5B5E6E` |
| `--c-secondary` | `@color-base-secondary` | `#91E3B7` |
| `--c-secondary-dark` | `@color-base-secondary-shade-dark` | `#63B48A` |
| `--c-secondary-light` | `@color-base-secondary-shade-light` | `#C9ECD9` |
| `--c-secondary-lighter` | `@color-base-secondary-shade-lighter` | `#EEFDF4` |
| `--c-tertiary` | `@color-base-tertiary` | `#B4B6BE` |
| `--c-tertiary-light` | `@color-base-tertiary-shade-light` | `#ECEFF0` |
| `--c-tertiary-lighter` | `@color-base-tertiary-shade-lighter` | `#FAFAFA` |
| `--sp-4xs` … `--sp-2xl` | `@size-4xs` … `@size-2xl` | 3 / 8 / 13 / 21 / 34 / 55 / 89 / 144 / 233 px |
| `--r-xs` … `--r-xl` | `@radius-xs` … `@radius-xl` | 3 / 8 / 21 / 34 / 55 px |
| `--shadow` | `.box-shadow-default()` | `3px 3px 8px 0 #ECEFF0` |
| `--t-short` / `--t-default` / `--t-long` | transition durations | 0.1s / 0.3s / 1s |
| `--menu-h` | menu height | 59px |

Breakpoints follow `@breakpoint-xs/s/m/l/xl` — 480, 768, 1023, 1400, 1700 px.

Fonts are Carnero W01, loaded with the `@font-face` declarations from
`fonts.less`, pointing at `static.form.bar/fe-ressources/fonts/…`. No Google
Fonts, no self-hosted copies.

**Two deliberate deviations**, both worth a look during integration:

1. `--c-secondary-text: #2F7A52` is not a form.bar token. It is a darkened mint
   used for small text on white, where `#91E3B7` does not carry enough contrast
   to be readable.
2. Four extra intermediate breakpoints (420, 560, 640, 900 px) handle layouts
   that do not exist in the base system, such as the audience cards and the logo
   wall.

## Before this goes live

The page is complete as a front end. These need someone with backend or account
access:

- **Contact form** — the modal validates and shows a success state, but submits
  nowhere. It needs a real endpoint. Fields: name, company, email, phone,
  project type, timing, message, optional file upload.
- **Three contact buttons are placeholders** (`href="#"`): Live-Chat, Rückruf
  buchen, WhatsApp. Email (`info@form.bar`) and phone
  (`+49 681 410 976 42`) are wired up.
- **Trusted Shops** — the rating block is static markup. form.bar's own widget
  (ID `XD406B59FD645A9A9A3205F0F9B08D2A8`) should replace it during integration;
  it only renders from the real domain, so it cannot be tested from a preview
  URL.
- **Customer logos** — form.bar confirmed in writing that logos may be used.
  Whether each company can be presented as a customer is a separate question and
  should be signed off per company before publication.

## Motion

Scroll reveals use `IntersectionObserver`, fire once, and run 0.6–0.8s ease-out.
Hover states lift cards by 4px. Clicking a logo enlarges it; clicking again,
elsewhere, or Escape resets it. Everything is disabled under
`prefers-reduced-motion: reduce`.

## Browser support

Modern evergreen browsers. Uses CSS custom properties, grid, flexbox,
`aspect-ratio`, `IntersectionObserver` and WebP with JPG fallbacks.

## Contact

Built by Shivam Kumar for form.bar (Okinlab GmbH, Saarbrücken) via PPC GmbH.
