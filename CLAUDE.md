# CLAUDE.md - GAND.TR

## Project Overview

Static landing page for **Gand Technology Services** — a premium software consulting firm based in Istanbul & Tokyo. Domain: `gand.tr`. Hosted on GitHub Pages.

## Tech Stack

- **HTML5 + CSS3 + minimal JS** — no build tools, no frameworks
- **Google Fonts**: Cinzel (headings), Cormorant Garamond (body), Cormorant SC (accents)
- **JavaScript**: Theme toggle only (~40 lines, IIFE, no globals)
- **Hosting**: GitHub Pages with custom domain via CNAME
- **Single file**: All content lives in `index.html` (~920 lines)

## File Structure

```
index.html                Main (and only) page — HTML + CSS + theme JS
CNAME                     GitHub Pages custom domain → gand.tr
robots.txt                Crawler permissions (all allowed)
.project-instructions.md  Design brief & SEO requirements
CLAUDE.md                 This file
```

## Design Language

- **Aesthetic**: Nordic/Old Turkic mythology — dark, elegant, runic
- **3 Themes**: Mid (default, aged manuscript), Dark (OLED-friendly), Light (warm vellum)
- **Color system**: All colors via CSS custom properties, swapped per `[data-theme]`
- **Typography**: Cinzel uppercase headings, Cormorant Garamond body, Cormorant SC accents
- **CSS art**: Staff (Gandr) and Stone (Balbal) icons — pure CSS pseudo-elements, theme-adaptive
- **Rune symbols**: Elder Futhark Unicode characters (ᚲ ᛟ ᚱ ᛊ)
- **Ornamental dividers**: Fading gradient lines with rune centerpiece between sections

## Theme System

- **Toggle**: 3-symbol pill in nav (Sun/Half/Moon) with sliding indicator
- **Persistence**: `localStorage` key `gand-theme`
- **Default**: Respects `prefers-color-scheme`, falls back to `mid`
- **Anti-FOUC**: Synchronous inline script in `<head>` sets `data-theme` before paint
- **No-JS fallback**: `:root` matches mid theme, site works without JavaScript

## Page Sections

1. **Nav** — Logo "GAND.TR" + "EST. MMXXV" + theme toggle
2. **Hero** — "Craft. Culture. Code." + mailto CTA (`contact@gand.tr`)
3. **Ornament divider**
4. **Philosophy** — Two-column: The Staff (Gandr) / The Stone (Balbal)
5. **Ornament divider**
6. **Services** — "Our Craft" heading + Carving, Foundation, Restoration cards
7. **Selected Works** — Centered card for Skriv.ist with external link
8. **Footer** — Runic decorations, locations, copyright

## Rules

1. **Preserve the aesthetic** — Nordic/Steppe mythology visual language must be maintained
2. **No frameworks or build tools** — intentionally minimal and fast
3. **Minimal JavaScript** — theme toggle only, no libraries
4. **Cultural accuracy** — Gandr (Norse staff) and Balbal (Turkic memorial stones) symbolism matters
5. **CTA is critical** — "Initiate Contact" mailto link must always be prominent
6. **SEO is done** — meta tags, OG/Twitter cards, JSON-LD schema, robots.txt all in place
7. **All colors use CSS variables** — never hardcode hex values outside theme definitions
8. **No inline styles** — all styling via CSS classes in the `<style>` block

## Accessibility

- Skip-to-content link (hidden, focusable)
- `<main>` landmark wrapping content
- `aria-label` on nav and theme toggle
- `focus-visible` states on all interactive elements
- `prefers-reduced-motion` disables transitions/animations
- WCAG AA contrast ratios in all three themes

## Responsive Breakpoints

- **1024px** — tighter gaps, smaller card min-width
- **768px** — single-column layouts, hide "EST. MMXXV", compact nav
- **480px** — smaller hero text, reduced padding

## SEO

Fully implemented: meta description, keywords, OG cards, Twitter cards, JSON-LD ProfessionalService schema. Target keywords: software consulting, bespoke development, Ruby, Go, system architecture, Istanbul, Tokyo.

## Git Workflow

- Branch: `master`
- Deploy: Push to master → auto-deploys via GitHub Pages
- Commit style: Emoji prefixes (`:sparkles:`, `:construction:`, etc.)
