# TokenLens — Marketing

Static marketing / presentation assets for **TokenLens** — an AI spend, usage, productivity, and governance intelligence platform.

> **Main message:** *Control your company's AI spend before it becomes your next cloud bill.*

Live page: <https://khizarooo.github.io/tokenlens-marketing/tokenlens-overview.html>

---

## Contents

| File | Description |
|---|---|
| `tokenlens-overview.html` | Self-contained 11-slide overview deck. No build step — open directly in any browser. |
| `.github/workflows/static.yml` | Deploys the repo root to GitHub Pages on every push to `main`. |

---

## Usage

```bash
# No server, no build — just open it
start tokenlens-overview.html      # Windows
open  tokenlens-overview.html      # macOS
xdg-open tokenlens-overview.html   # Linux
```

GitHub Pages serves it from the `/tokenlens-marketing/` subpath. The deck is fully self-contained (inline CSS/JS, inline SVG favicon, no relative asset paths), so the subpath works without configuration.

---

## Themes

- **Dark** (museum-black, default) and **light** (warm off-white) — the *Signal Gallery* identity shared with the TokenLens website.
- A toggle (top-right, sun/moon) switches themes.
- First load respects `prefers-color-scheme`; the choice is then remembered in `localStorage` (`tl-theme`).

Palette mirrors `tokenlens-idea/app/globals.css` (`.signal-gallery`): emerald `#38F8A1`, cyan `#52E5FF`, amber `#F8C471`, red `#FF5C7A`. No purple in this surface.

---

## Responsive support

| Behaviour | Mobile (< 769px) | Desktop (≥ 769px) |
|---|---|---|
| Layout | Natural vertical-scroll document, all sections stacked, auto height | One-slide-at-a-time deck, each `min-height: 100svh` |
| Navigation | Scroll | `← →` / Space / click nav buttons / swipe / `F` fullscreen |
| Typography | `clamp()` — fluid from 320px up | same |
| Touch targets | ≥ 48px | — |

Verified to have no horizontal overflow at 320, 375, 390, 430, 768, 1024, 1366, and 1440 px. Includes `prefers-reduced-motion` and print stylesheets.

### Controls (desktop)

| Key / action | Result |
|---|---|
| `← →`, Space, PageUp/Down | Previous / next slide |
| `Home` / `End` | First / last slide |
| `F` | Toggle fullscreen |
| Swipe / nav buttons | Previous / next slide |

---

## Lead capture (honest, static-safe)

This is a static page — there is **no backend and no secrets**. The **Book a Demo** / **Contact Us** buttons:

- Route to the public website's `/demo` and `/contact` pages **once that site is deployed** — set `WEBSITE_URL` near the top of the `<script>` in `tokenlens-overview.html`.
- Until then, they fall back to `mailto:khizar.imtiaz@gmail.com` (the `LEAD_NOTIFICATION_EMAIL` target). No fake form submission, no fake backend.

---

## Content source of truth

All product claims, provider readiness wording, roadmap phrasing, and security statements are aligned to **`tokenlens-idea`** (the canonical repo):

- `AI_CONTEXT.md`, `docs/WEBSITE_CONTENT.md`, `docs/CLAIMS_AND_COPY_GUARDRAILS.md`, `docs/ROADMAP.md`.

If this deck ever conflicts with those docs, **the docs win** — update the deck to match.

Provider readiness shown here: Claude + Claude Code **Live**; OpenAI / GitHub Copilot / Cursor / Microsoft 365 Copilot **connector implemented, validation pending**; Gemini / Perplexity **limited (no aggregate admin API)**. No SOC 2 claim, no customers/logos/testimonials, no unsourced savings percentages.

---

## Stack

Plain HTML + CSS + vanilla JS. Zero dependencies. Zero build step. One lightweight Google Fonts request (Plus Jakarta Sans + JetBrains Mono) with full system-font fallback if blocked or offline.
