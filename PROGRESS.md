# Project Progress Log

## Status: Infrastructure Setup — Vercel + Cloudflare remaining

---

## Decisions Made

### Infrastructure
- **Registrar**: Namecheap — keep as registrar, point nameservers to Cloudflare
- **Security/CDN**: Cloudflare (free) — DDoS, WAF, bot protection, SSL, hides origin IP
- **Hosting**: Vercel (free) — CI/CD auto-deploys from GitHub `main`
- **Code**: https://github.com/jrumacias/jrmacias.com

### Tech Stack
- **Framework**: Astro 5
- **Styling**: Tailwind CSS 4
- **Language**: TypeScript (strict)
- **Node**: v24.14.0 via nvm
- **Fonts**: JetBrains Mono
- **Contact protection**: Resend (email delivery) + Cloudflare Turnstile (CAPTCHA)

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
- Installed gh CLI to ~/.local/bin
- Scaffolded Astro 5 + Tailwind CSS 4 + TypeScript (strict) project
- Disabled Astro telemetry
- Initial commit pushed to https://github.com/jrumacias/jrmacias.com

**Next Steps** (in order):
1. Connect GitHub repo to Vercel (import project in Vercel dashboard)
2. Set up Cloudflare — create free account, add jrmacias.com site
3. Point Namecheap nameservers to Cloudflare
4. Add Vercel deployment domain in Cloudflare DNS
5. Verify site is live at https://jrmacias.com
6. Begin building the site: Layout, hero, dark/light mode toggle, JetBrains Mono

---
