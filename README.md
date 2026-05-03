# BTS Mood Space

A fan-made sanctuary for BTS ARMY — an emotional comfort website built around BTS music, self-love philosophy, and daily affirmations. The site features a dark glassmorphism aesthetic with a soft purple/lavender palette, smooth animations, and a fully responsive layout.

## Features

- **Mood Selector** — Choose a current emotional state (Calm, Joy, Heal, Grow) to find the right music and words
- **Comfort Playlist** — Curated BTS tracks with interactive selection
- **Member Showcase** — All seven members with personalized color accents
- **Daily Affirmations** — Quotes drawn from BTS lyrics and speeches
- **Featured Lyrics** — Rotating spotlight on meaningful BTS lines

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | TanStack Start |
| Routing | TanStack Router v1 (file-based) |
| Frontend | React 19 |
| Build | Vite 7 |
| Styling | Tailwind CSS 4 + custom CSS (glassmorphism) |
| Language | TypeScript 5.7 (strict mode) |
| Fonts | Poppins + Playfair Display (Google Fonts) |
| Deployment | Netlify |

## Getting Started

```bash
# Install dependencies
npm install

# Start local dev server (with Netlify emulation)
netlify dev

# Or use Vite directly
npm run dev
```

The dev server runs on **http://localhost:8888** (Netlify CLI) or **http://localhost:3000** (Vite).

## Production Build

```bash
npm run build
```

Output is written to `dist/client/` as configured in `netlify.toml`.
