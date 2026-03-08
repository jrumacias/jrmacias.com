# Project Progress Log

## Status: v1 Live — Site live at https://jrmacias.com

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
- **Styling**: Tailwind CSS 4 + CSS custom properties for theming
- **Language**: TypeScript (strict)
- **Node**: v24.14.0 via nvm
- **Fonts**: JetBrains Mono (self-hosted via @fontsource/jetbrains-mono)
- **Contact**: Formspree (https://formspree.io/f/mbdzlklq) — AJAX submission
- **Contact protection (future)**: Cloudflare Turnstile CAPTCHA — planned

### Design
- Dark mode default, light mode toggle (top-right, `[ light ]` / `[ dark ]`)
- Theme persisted in localStorage, applied before paint (no flash)
- "hello, i'm juan." with slow flowing text shine animation (6s, CSS gradient)
- "send a message →" button reveals contact form (smooth CSS grid transition)
- Contact form: email + message fields, AJAX submit, inline success state
- Subtle dot grid background
- Blog component planned for a future session

---

## Session Log

### Session 1 — 2026-03-07
**Completed**:
- Installed nvm + Node.js v24.14.0, gh CLI, Vercel CLI
- Scaffolded Astro 5 + Tailwind CSS 4 + TypeScript (strict)
- Pushed to GitHub, deployed to Vercel
- Cloudflare set up (DDoS, WAF, SSL) — nameservers updated in Namecheap
- Verified https://jrmacias.com live through Cloudflare → Vercel

### Session 2 — 2026-03-07
**Completed**:
- Created `src/layouts/Layout.astro` — base HTML shell, theme init script
- Created `src/components/ThemeToggle.astro` — `[ light ]` / `[ dark ]` fixed button
- Rewrote `src/pages/index.astro` — greeting, reveal-on-click contact form
- Updated `src/styles/global.css` — CSS vars for theme tokens, shine tokens
- Self-hosted JetBrains Mono via @fontsource
- Text shine animation on greeting (CSS background-clip gradient)
- Fixed GitHub default branch: renamed `master` → `main`
- PR #1 merged → auto-deployed to production

### Session 2 continued
**Completed**:
- Replaced Astro default favicon with pixel art vinyl record SVG (16×16 grid)
- Stripped full name from all page metadata (title → `jrmacias`, description → `jrmacias.com`)
- PR #2 merged → auto-deployed

**Next Steps** (future sessions):
1. **Blog** — see plan below
2. **Cloudflare Turnstile** CAPTCHA on contact form (requires a Vercel serverless function)
3. Consider a `/uses` or `/about` page

---

## Blog — Implementation Plan

### Tech
- **Astro Content Collections** (built-in) — type-safe markdown posts with Zod schema
- **MDX** — markdown + ability to embed Astro components in posts
- **`@tailwindcss/typography`** — `prose` class for beautiful default post styling

### File Structure (to create)
```
src/
├── content/
│   ├── config.ts          ← Zod schema (title, date, description, cover, tags)
│   └── blog/
│       └── first-post.md  ← example post
└── pages/
    └── blog/
        ├── index.astro    ← post listing page (/blog)
        └── [slug].astro   ← individual post page (/blog/my-post)
```

### Image Handling (camera photos)
Two options — decide before session:

**Option A — Astro processes at build time (start here)**
- Pre-resize camera photos to max ~2400px wide before adding to repo (use Squoosh, Lightroom export, or Preview)
- Store in `src/assets/blog/` (NOT `public/`)
- Use Astro's `<Image>` component (`astro:assets`) — auto-converts to WebP, generates responsive `srcset`, lazy loads
- Keep individual files under ~500KB
- Good for: occasional photos, simple workflow

**Option B — Cloudflare R2 (upgrade when needed)**
- Upload full-res photos to Cloudflare R2 (free egress, pay per GB stored)
- Reference by URL in markdown frontmatter / body
- Keeps git repo lean no matter how many posts
- Good for: photo-heavy posts, lots of content

**Rule: never commit raw camera files to git.**

### Post Frontmatter Shape
```md
---
title: "Post title"
date: 2026-03-07
description: "One sentence summary."
cover: "./images/photo.jpg"   # optional
tags: ["travel", "notes"]     # optional
draft: false
---
```

### Session 3 Steps (in order)
1. `npm install @tailwindcss/typography`
2. Create `src/content/config.ts` with Zod schema
3. Create `src/pages/blog/index.astro` (post listing)
4. Create `src/pages/blog/[slug].astro` (post detail with `prose` styling)
5. Write a first test post
6. Add blog link to homepage

---
