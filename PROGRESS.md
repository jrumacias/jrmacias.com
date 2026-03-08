# Project Progress Log

## Status: Setup Phase — Ready to begin Step 1

---

## Decisions Made

### Infrastructure
- **Registrar**: Namecheap — keep as registrar, point nameservers to Cloudflare
- **Security/CDN**: Cloudflare (free) — DDoS, WAF, bot protection, SSL, hides origin IP
- **Hosting**: Vercel (free) — CI/CD auto-deploys from GitHub `main`
- **Code**: GitHub (account confirmed)
- **Architecture**: Internet → Cloudflare → Vercel ← GitHub

### Tech Stack
- **Framework**: Astro
- **Styling**: Tailwind CSS
- **Language**: TypeScript
- **Fonts**: JetBrains Mono
- **Contact protection**: Resend (email delivery) + Cloudflare Turnstile (CAPTCHA)
  - Email never exposed as plain HTML text

### Design
- Dark mode default, light mode toggle
- Clean minimal tech blog aesthetic
- Subtle y2k flairs: grid textures, monospace accents, small glitch/terminal touches
- JetBrains Mono throughout
- Blog component planned for a future session

---

## Open Questions
- [x] GitHub username: `jrumacias` — https://github.com/jrumacias
- [x] Vercel account: created

---

## Session Log

### Session 1 — 2026-03-07
**Goal**: Establish project foundation before writing any code.

**Completed**:
- Created `CLAUDE.md` with full project instructions
- Created `PROGRESS.md` for session tracking
- Confirmed all major architectural and design decisions (see above)

**Next Steps** (in order):
1. Install Node.js via `nvm`
2. Initialize git repo locally
3. Create GitHub repository and push
4. Scaffold Astro project (Tailwind + TypeScript template)
5. Fill in `CLAUDE.md` key commands and project structure
6. Connect GitHub repo to Vercel
7. Set up Cloudflare — point Namecheap nameservers to Cloudflare
8. Point domain to Vercel in Cloudflare DNS
9. Design and build the site (dark mode, JetBrains Mono, y2k flairs)

---
