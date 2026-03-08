# jrmacias.com — Claude Code Instructions

## Project Overview
Personal website for Juan R. Macias at jrmacias.com. Goal: simple, clean, modern personal site with a tech blog. First personal project — emphasis on learning best practices.

## Infrastructure Stack
```
Internet → Cloudflare (free) → Vercel (free) ← GitHub (CI/CD)
```
- **Registrar**: Namecheap (nameservers pointed to Cloudflare)
- **DNS / Security**: Cloudflare free tier (DDoS, WAF, bot protection, SSL)
- **Hosting**: Vercel (auto-deploys from GitHub `main` branch)
- **Code**: https://github.com/jrumacias/jrmacias.com

## Tech Stack
- **Framework**: Astro
- **Styling**: Tailwind CSS
- **Language**: TypeScript
- **Package Manager**: npm (via nvm-managed Node.js)
- **Fonts**: JetBrains Mono (Google Fonts or self-hosted)
- **Contact**: Resend (email) + Cloudflare Turnstile (CAPTCHA)

## Design System
- **Default mode**: Dark, with light mode toggle
- **Aesthetic**: Clean, minimal tech blog with subtle y2k flairs
  - Monospace font throughout (JetBrains Mono)
  - Subtle grid or scanline background textures
  - Small terminal/glitch-style accents
  - Mostly restrained — flairs are small, not loud
- **Contact info**: Never in plain HTML text — always behind a form

## Key Commands

```bash
npm run dev      # Start local dev server (http://localhost:4321)
npm run build    # Build for production
npm run preview  # Preview production build locally
```

## Development Guidelines
- Always work on a feature branch, never directly on `main`
- Keep commits small and descriptive (imperative mood: "Add hero section")
- Update `PROGRESS.md` at the end of every working session
- Run a production build before merging to `main`
- Never put contact info (email, phone) in plain HTML

## Project Structure

```
jrmacias.com/
├── public/          # Static assets (favicon, images)
├── src/
│   ├── pages/       # File-based routing — each .astro file = a page
│   ├── layouts/     # Shared page layouts (to be created)
│   ├── components/  # Reusable UI components (to be created)
│   └── styles/
│       └── global.css  # Global styles + Tailwind imports
├── astro.config.mjs # Astro + Tailwind config
├── tsconfig.json    # TypeScript config
├── CLAUDE.md        # This file
└── PROGRESS.md      # Session log
```

## Useful References
- [Astro Docs](https://docs.astro.build)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [Vercel Docs](https://vercel.com/docs)
- [Cloudflare Docs](https://developers.cloudflare.com)
- [JetBrains Mono](https://www.jetbrains.com/lp/mono/)
- Detailed progress log: `PROGRESS.md`
