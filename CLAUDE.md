# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Landing page for **Flashcards Craft** — an AI-powered Anki flashcard generator for language learners. This is a static site (no build system, no bundler, no framework) deployed via GitHub Pages to `flashcards.stefanovskyi.com`. The main app lives at `app.flashcards.stefanovskyi.com` (separate repo).

## Development

Serve locally with any static file server:

```bash
python3 -m http.server 8000
# or
npx serve .
```

No build step, no tests, no linter. Changes go live on push to `main` via GitHub Pages.

## Architecture

- **`index.html`** — Single-page landing. All JavaScript is inline (mobile menu toggle, flashcard flip, PostHog analytics tracking). Uses Lucide icons via CDN (`lucide.createIcons()`).
- **`styles.css`** — All styles, including responsive breakpoints. No preprocessor. CSS custom properties defined in `:root` follow the "Luminous Curator" design system.
- **`assets/`** — SVGs (logo, decorative twig, bird) and PNGs (Anki icon, hero illustration).
- **`design-system/`** — Design token reference docs (not consumed by code).
- **`DESIGN.md`** — Full design system spec ("Luminous Curator"). Read this before making visual changes.

## Design System: Luminous Curator

Key constraints to follow when editing styles:

- **Primary color:** `#facc15` (yellow) — used sparingly for CTAs and accents
- **No borders for layout separation** — use surface color layering instead (white cards on light-blue backgrounds)
- **No gradients on buttons** — all interactive elements are flat, solid fills
- **No purple/pink tones** — depth comes from blue-tinted grays and charcoals
- **Border radius:** strictly `8px` (`0.5rem`)
- **Shadows:** always tinted with deep slate (`rgba(19, 27, 46, ...)`), never pure black
- **Font:** Plus Jakarta Sans (loaded from Google Fonts)
- **Flashcard flip:** uses 3D CSS transforms with `backface-visibility: hidden` and spring-feel cubic-bezier

## Analytics

PostHog is integrated inline in `index.html`. Three CTA buttons are tracked: `btn-get-started`, `btn-start-generating`, `btn-start-creating-decks`.
