# AGENTS.md — BTS Mood Space

This document is for AI agents and developers working on the codebase.

## Project Overview

BTS Mood Space is a fan-made emotional comfort website for BTS ARMY. It is a single-page application built on **TanStack Start** and deployed to **Netlify**.

## Directory Structure

```
src/
├── routes/
│   ├── __root.tsx          # Root shell: <html>, <head> (Google Fonts link tags), <body>
│   ├── index.tsx           # Entire homepage — all sections in one route component
│   └── products/           # Scaffold remnant — not linked from homepage
├── data/
│   └── products.ts         # Scaffold data — not used by homepage
├── styles.css              # All custom CSS: CSS variables, glassmorphism, animations
└── router.tsx              # TanStack Router setup
```

## Key Design Decisions

### Single-route architecture
All content lives in `src/routes/index.tsx`. The site is a single scrollable page with anchor-based navigation (`#mood`, `#music`, `#members`, `#comfort`). No sub-routes needed. To add pages, follow TanStack Start file-based routing: `src/routes/your-page.tsx`.

### CSS strategy
Tailwind CSS 4 is available for utilities, but the majority of styling is **custom CSS** in `src/styles.css`. This is intentional — the glassmorphism aesthetic, CSS variable palette, and animation system require precise custom CSS.

- **CSS variables** in `:root` control the entire color palette. Edit those to retheme.
- **`.glass`** — primary glassmorphism card class (`backdrop-filter: blur`).
- **`.btn-primary` / `.btn-ghost`** — the two button variants.
- **Background orbs** (`.bg-orb-*`) — animated radial gradients using `position: fixed`, pointer-events none.

### Fonts
Poppins (body) + Playfair Display (display/italic headings) loaded from Google Fonts via `<link>` tags in `__root.tsx`. The `.display-font` CSS class applies Playfair Display.

### State
Minimal local React `useState` only:
- `activeTrack` — highlights selected playlist track
- `activeMood` — highlights selected mood card

No global state library needed.

## Coding Conventions

- **TypeScript strict mode** — no `any`; use `type` keyword for type-only imports
- **Components**: PascalCase; SVG icon components defined at top of file as small functions
- **CSS classes**: kebab-case, semantic names (`.mood-card`, `.track-item`)
- **Inline `style` props**: only for dynamic/computed values (e.g. per-member avatar colors)
- **Animations**: CSS-only via `@keyframes` + `animation-delay`. Never animate layout properties.

## Adding New Sections

1. Add a `<section>` inside `BTSMoodSpace` in `src/routes/index.tsx`
2. Give it an `id` for anchor nav
3. Add the anchor to the `nav-links` array in the nav
4. Style new elements in `src/styles.css` following existing patterns

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | TanStack Start |
| Routing | TanStack Router v1 (file-based) |
| Frontend | React 19 |
| Build | Vite 7 |
| Styling | Tailwind CSS 4 + custom CSS |
| Language | TypeScript 5.7 (strict) |
| Fonts | Poppins + Playfair Display |
| Deployment | Netlify |

## Environment Variables

No environment variables required for the base site. If AI features are added later, use `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, etc.
