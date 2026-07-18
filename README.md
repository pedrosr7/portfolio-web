# Pedro Sánchez Ramírez — portfolio

Personal developer portfolio for Pedro Sánchez Ramírez (Senior Android Engineer &
Mobile Architect). Static, single-page, bilingual (EN + ES). Own brand — dark OLED,
Android-inspired green accent `#3DDC84`, deliberately distinct from the Aura product brand.

```
portfolio-web/
├── index.html            # English (default)
├── index.es.html         # Spanish
├── CNAME                 # pedro.pampaiter.com
├── robots.txt
├── sitemap.xml
└── assets/
    ├── styles.css        # design system (shared by both languages)
    ├── app.js            # nav, mobile menu, scroll-reveal
    ├── pedro-sanchez-ramirez-cv.pdf
    └── captures/         # real Aura screenshots reused for the case study
        ├── aura-pulse.png · aura-planning.png · aura-insights.png (shown)
        └── aura-coach.png · aura-log.png · aura-newsession.png (spare)
```

## Design system

- **Fonts:** Space Grotesk (display) · Inter (body) · JetBrains Mono (labels/code) — Google Fonts CDN.
- **Palette:** bg `#0A0E14`, text `#E8EDF4`, accent `#3DDC84`. Dark only.
- **Sections:** hero (terminal card) → featured work (Aura case study w/ real screenshots,
  Polymarket cross-platform w/ a hand-authored SVG pipeline diagram) → experience timeline
  → skills → about + education → contact.
- No framework, no build step. `styles.css` + `app.js` are shared across both language files.

## Content sources

- Experience, education, certs, languages: from the CV (`assets/pedro-sanchez-ramirez-cv.pdf`).
- Aura: the owner's own product (KMP + Compose Multiplatform + Ktor + AI). Screenshots reused from `aura-web`.
- Polymarket: client work (via The Left Bit) — described at a high level, **no proprietary detail
  or internal screenshots** by design.

## Links wired

| Where | URL |
|---|---|
| GitHub  | https://github.com/pedrosr7 |
| LinkedIn | https://www.linkedin.com/in/pedro-sánchez-ramírez-b98422159/ |
| Malt     | https://www.malt.com/profile/pedrosanchezramirez |
| Email    | pedro.srh7@gmail.com |
| Aura     | App Store + Google Play + aura.pampaiter.com |

Phone number from the CV is intentionally **not** published (spam). Add it if desired.

## Local preview

```bash
npx serve portfolio-web        # or: open index.html
```

## Deploy — GitHub Pages + custom subdomain (planned)

Target: **https://pedro.pampaiter.com** (subdomain of the existing `pampaiter.com`).

1. Create a repo (e.g. `pedrosr7/portfolio-web`), push this folder to `main`.
2. Settings → Pages → deploy from `main` / root. The `CNAME` file sets the custom domain.
3. In Namecheap DNS add: `CNAME  pedro  →  pedrosr7.github.io`.
4. After DNS propagates, enforce HTTPS:
   `gh api -X PUT repos/pedrosr7/portfolio-web/pages -f https_enforced=true`

Same flow already used for `aura-web`.
