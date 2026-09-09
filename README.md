# form.bar — Business-Landingpage

Eigenständige Landingpage für die B2B-Zielgruppen von form.bar, gebaut als Ersatz
für `form.bar/de-DE/service/business-service`.

Durchgehend deutsche Ansprache in der Du-Form, passend zum Rest der Seite.

## Inhalt

```
index.html                    die komplette Seite – Markup, CSS und JavaScript in einer Datei
assets/img/                   Fotos (WebP mit JPG-Fallback, 1120×1120 oder größer)
assets/img/logos/             Kundenlogos (SVG)
assets/img/logos/SOURCES.md   Herkunft jedes Logos und was daran angepasst wurde
```

Kein Build-Prozess, keine Abhängigkeiten, kein Framework. `index.html` im Browser
öffnen genügt – es gibt nichts zu installieren, also kein `npm install`, kein
`node_modules`, keine `package.json`. Playwright kam während der Entwicklung nur
für Screenshot-Prüfungen zum Einsatz und ist bewusst nicht Teil dieses Pakets.

## Warum eine einzige Datei

Die Seite soll in eure bestehende Umgebung eingebaut werden, nicht eigenständig
laufen. Alles in einer Datei bedeutet:

- sie lässt sich als CMS-Block oder als Vue-Komponente übernehmen, ohne vorher
  eine Build-Pipeline aufzudröseln,
- es gibt keine Bundler-Annahmen, die zu eurem Setup passen müssen,
- nichts lädt von einem fremden CDN, es kommt also keine neue externe
  Abhängigkeit dazu.

CSS und JavaScript in eigene Dateien auszulagern ist eine Sache von fünf Minuten,
falls das für die Integration besser passt – die Abschnitte sind bereits durch
Kommentare getrennt.

## Design-Tokens

Alle Farben, Abstände, Radien und Breakpoints stammen aus euren eigenen Dateien
`variables-base.less` und `variables.less` und sind als CSS-Variablen am Anfang
von `index.html` deklariert. Die Zuordnung ist eins zu eins:

| CSS-Variable | LESS-Variable | Wert |
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
| `--t-short` / `--t-default` / `--t-long` | Übergangsdauern | 0,1s / 0,3s / 1s |
| `--menu-h` | Menühöhe | 59px |

Die Breakpoints folgen `@breakpoint-xs/s/m/l/xl` — 480, 768, 1023, 1400, 1700 px.

Als Schrift kommt Carnero W01 zum Einsatz, eingebunden über die `@font-face`-
Deklarationen aus eurer `fonts.less` mit den Pfaden auf
`static.form.bar/fe-ressources/fonts/…`. Keine Google Fonts, keine eigenen
Kopien der Schriftdateien.

**Zwei bewusste Abweichungen**, die beim Einbau einen Blick wert sind:

1. `--c-secondary-text: #2F7A52` ist kein form.bar-Token, sondern ein
   abgedunkeltes Mint für kleinen Text auf Weiß. `#91E3B7` hat dort zu wenig
   Kontrast, um gut lesbar zu sein.
2. Vier zusätzliche Zwischen-Breakpoints (420, 560, 640, 900 px) für Layouts, die
   es im Grundsystem so nicht gibt, etwa die Zielgruppen-Karten und die
   Logo-Wand.

## Vor dem Livegang

Als Frontend ist die Seite fertig. Für diese Punkte braucht es Zugriff auf euer
Backend oder eure Konten:

- **Kontaktformular** — das Modal validiert und zeigt eine Erfolgsmeldung, sendet
  aber an keinen Endpunkt. Felder: Name, Unternehmen, E-Mail, Telefon, Projektart,
  Zeitrahmen, Nachricht, optionaler Datei-Upload.
- **Drei Kontakt-Buttons sind Platzhalter** (`href="#"`): Live-Chat, Rückruf
  buchen, WhatsApp. E-Mail (`info@form.bar`) und Telefon (`+49 681 410 976 42`)
  sind verlinkt.
- **Footer-Links** — FAQ, f+ Design-Service, Über uns, Team, Presse,
  Business-Service, AGB, Datenschutz, Widerruf und Impressum zeigen noch auf `#`,
  weil mir eure internen URLs nicht vorlagen. Impressum, Datenschutz und Widerruf
  sind Pflichtangaben und müssen vor dem Livegang gesetzt sein.
- **Trusted Shops** — der Bewertungsblock ist statisches Markup. Euer eigenes
  Widget (ID `XD406B59FD645A9A9A3205F0F9B08D2A8`) sollte ihn beim Einbau
  ersetzen; es rendert nur von der echten Domain und lässt sich daher nicht über
  eine Vorschau-URL testen.
- **Kundenlogos** — die Erlaubnis zur Logo-Nutzung liegt schriftlich vor. Ob jede
  Firma öffentlich als Kunde genannt werden kann, ist eine davon getrennte Frage
  und sollte vor der Veröffentlichung pro Firma bestätigt werden.

## Animationen

Die Scroll-Effekte laufen über `IntersectionObserver`, lösen einmalig aus und
dauern 0,6–0,8 s mit ease-out. Karten heben sich beim Hover um 4 px. Ein Klick auf
ein Logo vergrößert es; ein erneuter Klick, ein Klick daneben oder Escape setzt es
zurück. Bei `prefers-reduced-motion: reduce` ist alles davon abgeschaltet.

## Browser-Unterstützung

Aktuelle Browser. Verwendet werden CSS-Variablen, Grid, Flexbox, `aspect-ratio`,
`IntersectionObserver` sowie WebP mit JPG-Fallback.

## Kontakt

Erstellt von Shivam Kumar für form.bar (Okinlab GmbH, Saarbrücken), vermittelt
über die PPC GmbH.
