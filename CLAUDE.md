# Telecom × AI Pitch Site

## What This Is
A 5-page strategic pitch microsite targeting telecom operators (C-level, strategy, digital, AI teams) globally, with focus on Africa, Indonesia, and MENA. Positions Yango Tech as the end-to-end partner enabling telecoms to become AI inference distributors and platform owners. Core thesis: "Build your own inference infrastructure — don't rent someone else's."

## Brand System
**Yango Tech** — applied from the `yango-web-style` skill package.

Key tokens:
- Primary: `#FF1A1A` (red, CTAs only)
- Body bg: `#F5F5F5`
- Dark sections: `#000` / `#141414`
- Fonts: Yango Headline (900, headings), Yango Group Text (body/UI)
- Border radius: 1.875rem cards, 2rem pills/buttons
- No shadows, no gradients on surfaces

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Static HTML/CSS/JS (5 pages + shared.css) |
| Server | Express.js (static file server) |
| Hosting | Railway (auto-deploy from GitHub) |
| DNS | Cloudflare CNAME → Railway domain |
| Database | None (static site) |

## Pages

| File | Purpose |
|------|---------|
| `public/index.html` | Main pitch — hero, problem, opportunity, strategic fork, analogy, solution layers, use cases, CTA |
| `public/use-cases.html` | Real operator case studies (Safaricom, Indosat, MTN, NVIDIA/T-Mobile, Ooredoo, e&) + detailed Yango Tech use case mockups |
| `public/b2b.html` | Enterprise AI products with dashboard mockups, chat UIs, pricing cards |
| `public/b2c.html` | Consumer AI products with phone mockups, AI-bundled data plans, pricing |
| `public/research.html` | Deep research page with sourced claims from McKinsey, BCG, Deloitte, GSMA, NVIDIA, Fortune |
| `public/shared.css` | Full Yango Tech boilerplate CSS — fonts, tokens, components, nav, footer, animations |

## Local Dev

```bash
npm install
npm start
# Open http://localhost:3000
```

## Deploy

1. Push to GitHub
2. Connect repo in Railway dashboard
3. Railway auto-detects Node.js, runs `npm start`
4. Add custom domain in Railway → Settings → Domains
5. In Cloudflare: CNAME `telecom-ai` → `<railway-domain>.up.railway.app` (Proxied)
6. Open https://telecom-ai.chernikov.tech to confirm

## Conventions

- All page-specific CSS is inlined in `<style>` blocks — only `shared.css` is external
- Navigation and footer are duplicated per page (no build tool / no partials)
- All headings use Yango Headline, uppercase, with `letter-spacing: calc(1em / 50)`
- Body text is sentence case with `letter-spacing: 0.05em`
- UI chrome (nav, tags, buttons, labels) is uppercase with `letter-spacing: 0.12em`
- Scroll animations use IntersectionObserver with `.yt-fade-in` / `.yt-visible`
- Nav switches to dark mode (`.yt-nav--dark`) when scrolled past hero

## Do Not

- Do not add box-shadow to any cards — use white-on-#F5F5F5 contrast only
- Do not use any fonts other than Yango Headline and Yango Group Text
- Do not use gradient backgrounds on cards or sections (only hero bg radials)
- Do not use light-tinted red (rgba, #FFB3B3, etc.) for readable text on white backgrounds
- Do not split CSS into separate files per page — keep shared.css + inline page styles
- Do not add a build step — this is intentionally a zero-build static site served by Express

## Owner

Evgeny Chernikov — COO, Yango Tech
eechernikov@yango.com

<!-- REVIEW: confirm the 3 context questions were answered:
  1. Use-case description specific enough? ✅ Telecom AI pitch site for C-level operators
  2. Conventions captured? ✅ Yango web style, no build, inline CSS
  3. "Do Not" list has project-specific rules? ✅ 6 rules covering brand, architecture, and styling
-->
