# Money2Abroad

Outward remittance platform for Indian travel agents — a static marketing & utility site with live FX, GST/TCS calculators, RBI guidelines, and onboarding flow.

## Live site

🔗 **https://kunaldsoni.github.io/money2abroad/**

> Replace with your production domain once configured (e.g. `https://money2abroad.com`).

## Tech stack

| Layer | Choice |
|---|---|
| Markup | Static HTML5 (no framework) |
| Styles | Hand-written CSS in [`css/main.css`](css/main.css) — design tokens via CSS variables (JPMC-inspired palette: cream `#eee7dc`, copper `#8b5a2b`, black ink) |
| Typography | Google Fonts — Inter, Playfair Display, Source Serif 4, JetBrains Mono |
| Interactivity | Vanilla JavaScript (inline per-page) — calculators, live FX ticker, mobile nav toggle |
| FX data | Public `currency-api` (24h % change, mid-market rates) |
| Hosting | GitHub Pages (static) |
| Build | None — files served as-is |

## Pages

| Page | Path | Purpose |
|---|---|---|
| Home | [`index.html`](index.html) | Hero, live FX ticker, home calculator, product walkthrough |
| Remittance for Travel Agents | [`remittance-for-travel-agents/index.html`](remittance-for-travel-agents/index.html) | Primary landing for travel-agent ICP |
| GST Calculator | [`gst-calculator/index.html`](gst-calculator/index.html) | GST on forex services calculator |
| TCS Calculator | [`tcs-calculator/index.html`](tcs-calculator/index.html) | TCS on foreign exchange calculator |
| RBI Guidelines | [`rbi-guidelines/index.html`](rbi-guidelines/index.html) | LRS / outward-remittance compliance reference |
| FAQ | [`faq/index.html`](faq/index.html) | Customer-facing Q&A |
| About | [`about-us/index.html`](about-us/index.html) | Company story |
| Contact | [`contact-us/index.html`](contact-us/index.html) | Email / get-onboarded CTA |

## Project structure

```
.
├── index.html                          # Home
├── about-us/index.html
├── contact-us/index.html
├── faq/index.html
├── gst-calculator/index.html
├── tcs-calculator/index.html
├── rbi-guidelines/index.html
├── remittance-for-travel-agents/index.html
├── css/
│   └── main.css                        # Single stylesheet for the entire site
├── assets/                             # Images, icons, etc.
├── Money2Abroad Logo.jpg
└── README.md
```

## Run locally

No build step required. From the repo root:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>. Hard-refresh (Cmd+Shift+R) after CSS edits to bypass the browser cache.

## Design system (tokens)

Defined at the top of [`css/main.css`](css/main.css):

| Token | Value | Use |
|---|---|---|
| `--bg` | `#eee7dc` | Page background (cream) |
| `--bg-soft` | `#ffffff` | Nav / cards |
| `--ink` | `#000000` | Body text |
| `--ink-2` | `#2a2a2a` | Secondary text |
| `--ink-3` | `#5c5c5c` | Tertiary text |
| `--accent` | `#8b5a2b` | Copper CTA / brand accent |
| `--accent-deep` | `#6b4520` | Hover / pressed state |
| `--line` | `rgba(0,0,0,0.10)` | Hairline borders |
| `--pad` | `clamp(20px, 4vw, 56px)` | Responsive horizontal padding |

### Buttons

- `.btn-accent` — outlined copper pill (primary nav CTA), copper-fill swipe on hover.
- `.btn-primary` — filled copper pill (in-page CTA), darker swipe on hover.
- `.btn-ghost` — outlined ink pill (secondary).
- `.hc-cta` — home calculator action (matches `.btn-primary` styling).

All hover states use the same skewed gradient swipe (`cubic-bezier(.7,.05,.25,1)`) so CTAs feel like a family.

## Conventions

- Logo links to home; there is no separate "Home" nav item.
- Current page is indicated by a copper underline under the nav pill — no font-weight change (so the layout doesn't shift between pages).
- `.btn-accent` in the nav has a `min-width: 180px` so "Email us" / "Get onboarded" CTAs render at the same width on every page.

## Deployment

The site is served from the `main` branch via GitHub Pages.

1. Merge feature branch → `main` via PR.
2. GitHub Pages auto-rebuilds (~1 min).
3. Hard-refresh the live URL to verify.

## Repository

[github.com/KunalDSoni/money2abroad](https://github.com/KunalDSoni/money2abroad)
