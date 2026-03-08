# Project Progress Log

## Status: Infrastructure Complete — Ready to build the site

---

## Decisions Made

### Infrastructure
- **Registrar**: Namecheap — nameservers pointed to Cloudflare
- **Security/CDN**: Cloudflare (free) — DDoS, WAF, bot protection, SSL, hides origin IP
- **Hosting**: Vercel (free) — CI/CD auto-deploys from GitHub `main`
- **Code**: https://github.com/jrumacias/jrmacias.com
- **Live URL**: https://jrmacias.com

### Tech Stack
- **Framework**: Astro 5
- **Styling**: Tailwind CSS 4
- **Language**: TypeScript (strict)
- **Node**: v24.14.0 via nvm
- **Fonts**: JetBrains Mono
- **Contact protection**: Resend (email delivery) + Cloudflare Turnstile (CAPTCHA) — planned

### Design
- Dark mode default, light mode toggle
- Clean minimal tech blog aesthetic
- Subtle y2k flairs: grid textures, monospace accents, small glitch/terminal touches
- JetBrains Mono throughout
- Blog component planned for a future session

---

## Session Log

### Session 1 — 2026-03-07
**Completed**:
- Installed nvm + Node.js v24.14.0
- Installed gh CLI to ~/.local/bin, Vercel CLI globally
- Scaffolded Astro 5 + Tailwind CSS 4 + TypeScript (strict) project
- Disabled Astro telemetry
- Initial commit pushed to https://github.com/jrumacias/jrmacias.com
- Deployed to Vercel, connected GitHub repo (auto-deploys on push to main)
- Set up Cloudflare — nameservers updated in Namecheap
- Added A record in Cloudflare → Vercel (76.76.21.21), www CNAME
- Cloudflare SSL set to "Full" mode
- Verified: https://jrmacias.com returns HTTP 200 through Cloudflare → Vercel

**Next Steps** (start of next session):
1. Create a feature branch: `git checkout -b feat/initial-design`
2. Build the base Layout component (src/layouts/Layout.astro)
   - Import JetBrains Mono font
   - Dark/light mode toggle with localStorage persistence
   - Global CSS variables for color tokens
3. Build the home page hero section
4. Add subtle y2k design flairs (grid background, monospace accents)
5. Commit, push, open PR → merge to main → auto-deploy

---
