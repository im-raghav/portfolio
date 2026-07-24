# Portfolio Content Refresh & Repositioning — Design

## Goal

Refresh stale content on `im-raghav.github.io/portfolio` (single-file static site,
`index.html`) and broaden its positioning so it reads credibly for backend,
frontend, or full-stack roles — not just "full-stack" — while keeping the
existing visual design, structure, and single-file architecture unchanged.

## Non-goals

- No visual/layout redesign. Same dark theme, same section structure.
- No build tooling / framework introduced. Stays a single static `index.html`.
- No fabricated stats or claims not grounded in real experience.
- No naming of Opalina's actual client or project codename for the DAM platform.

## Changes

### Hero
- Typing-loop titles broadened for backend/frontend/full-stack keyword coverage.
  Replace current list (`Full Stack Developer`, `Software Engineer`, `React & Angular Dev`,
  `Node.js Developer`, `Problem Solver`) with a set that explicitly covers backend
  and frontend framing, e.g.: `Full-Stack Developer`, `Backend Engineer`,
  `Frontend Engineer`, `Node.js / Next.js Developer`, `Problem Solver`.
- Hero description rewritten to call out both API/infra work and UI/UX work
  explicitly, not just "full stack" as a label.

### About
- Copy tightened/broadened to match hero positioning (minor edit, not a rewrite).
- Stat cards updated:
  - `4+ Years Experience` → `5+ Years Experience` (Feb 2021 – present ≈ 5.4 yrs)
  - `2 Companies` — unchanged
  - `10+ Projects Delivered` — unchanged
  - `99% ML Model Accuracy` → `5+ National-Scale Platforms` (grounded in
    PushPolitics, Narendra Modi website/app, Pariksha Pe Charcha, Mann Ki Baat,
    and the DAM platform — all already referenced in the Experience section)

### Skills
Replace the current section with:
- **Languages**: JavaScript, TypeScript, Python, Java, SQL
- **Frameworks & Libraries**: Next.js, React, Node.js, Express, Angular, Django
- **Data**: PostgreSQL, Drizzle ORM, MongoDB, pgvector
- **Infra & Cloud**: AWS (EC2/RDS), Docker, Vercel, CI/CD, CDN & media pipelines
- **AI/ML**: LLM API integration, TensorFlow, Keras

### Projects
- Add a new featured project card: **"Enterprise Digital Asset Management Platform"**
  — Next.js, PostgreSQL, AWS (EC2/RDS), Docker, AI-powered auto-tagging/OCR/face
  search, CDN-backed media pipeline. Fully generic — no client or sector named.
- De-emphasize the two existing academic/research projects (GAN Fake Image
  Detection, CCTV Surveillance): move out of the main `project-card` grid into a
  smaller, compact "Other Projects / Research" list below the featured cards.

### Contact form
- Replace the fake `handleSubmit` JS (which just fakes a success animation and
  never sends anything) with a real POST to a Formspree endpoint
  (`https://formspree.io/f/{FORM_ID}`). Keep the existing success-state UI
  (button text swap, green background, reset after 3s).
- `{FORM_ID}` is a placeholder the user will supply (free Formspree account);
  left clearly marked in the code if not supplied before implementation.

### Footer
- `Designed & built by Himanshu Raghav · 2024` → year computed dynamically via
  `new Date().getFullYear()` so it doesn't go stale again.

## Files touched

- `index.html` only (content, inline `<style>` untouched except as needed for
  the de-emphasized project list styling, inline `<script>` for form + footer year).

## Success criteria

- Page still renders correctly as a static file (no server/build step).
- All new content factually grounded (no invented numbers/claims).
- No mention of Opalina's client/sector for the DAM project.
- Contact form actually submits (once Formspree ID is supplied) instead of
  silently doing nothing.
- Footer year is self-updating.
