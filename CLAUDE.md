# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev        # Dev server at localhost:4321
npm run build      # Production build to ./dist/
npm run preview    # Preview production build locally
```

No linter or test suite is configured.

## Stack

- **Astro 6** — static site generator, file-based routing under `src/pages/`
- **Tailwind CSS 4** + **DaisyUI 5** — styling via `@import "tailwindcss"` and `@plugin "daisyui"` in `src/styles/global.css`
- **astro-icon** — icon component using Heroicons (`heroicons:*`) and Simple Icons (`simple-icons:*`)
- **Cloudflare Pages** adapter (`@astrojs/cloudflare`) — deploy target

## Architecture

Single-page marketing site. All content lives in one route (`src/pages/index.astro`) which composes components in order: `Navbar → Hero → Differentials → Services → Testimonials → Footer → WhatsAppButton`.

**Layout** (`src/layouts/Layout.astro`): sets `lang="es"`, `data-theme="trinity"`, and accepts optional `title`/`description` props for SEO meta tags.

**Theme**: Custom DaisyUI theme named `trinity` defined entirely in `src/styles/global.css`. Key tokens:
- `--color-primary`: `#AD2380` (magenta — navbar, icons, highlights)
- `--color-accent`: `#FBAC37` (orange/gold — CTAs, underline animations)
- `--color-neutral`: `#2a2a2a` (footer background)

**Icons**: Always use `<Icon name="heroicons:icon-name" />` from `astro-icon/components`. Never use emoji as UI icons.

**Navbar** scroll behavior: vanilla JS in a `<script>` tag inside `Navbar.astro` toggles `.scrolled` class on `#main-nav` at 20px scroll, which activates a frosted-glass CSS rule.

**WhatsApp links**: Phone number is `+50683561395`. Links use `https://wa.me/50683561395?text=...` pattern and appear in Navbar, WhatsAppButton, and Footer.
