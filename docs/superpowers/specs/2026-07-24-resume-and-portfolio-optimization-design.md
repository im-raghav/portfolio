# Resume Rebuild & Portfolio Alignment — Design

## Goal

Himanshu is actively job-hunting (ASAP). Produce a polished, ATS-friendly
full-stack resume (currently only exists as a PDF with no editable source),
and align the live portfolio (`index.html`) with it so both documents tell
the same, honest story to a recruiter who checks both.

## Context

- Existing resume: `~/Desktop/himanshu_raghav_full-stack-developer.pdf` (PDF only,
  no docx/source). A second variant, `Himanshu_Raghav_Data_Engineer_Resume.pdf`,
  also exists but is out of scope for this pass (user chose full-stack
  positioning; the data-engineer variant is left untouched).
- Portfolio currently claims skills/tech (Next.js, Django, Docker, Vercel,
  CI/CD, Drizzle ORM, pgvector, TensorFlow/Keras, LLM API integration) that
  don't appear anywhere on the resume. User confirmed these are real,
  production-used skills — the resume is simply out of date.
- Portfolio's About section says "over 4 years of professional experience"
  while the stat card next to it says "5+ Years Experience" — a direct
  self-contradiction on the same screen.
- Portfolio has no SEO metadata (`<meta name="description">`, Open Graph,
  Twitter Card, canonical link, favicon) — a Google/LinkedIn search for the
  portfolio URL currently shows nothing useful.
- No resume is linked from the portfolio; a recruiter reading the site can't
  download one.

## Non-goals

- No visual/layout redesign of the portfolio. Content and metadata only.
- No fabricated metrics (user counts, %, revenue) not already grounded in
  existing material. Strengthen wording/specificity instead of inventing numbers.
- No changes to the Data Engineer resume variant.
- No naming of Opalina's clients/sector beyond what's already public on the
  live portfolio (PushPolitics, Narendra Modi site, Pariksha Pe Charcha, Mann
  Ki Baat are already named there).
- No OG image asset generation — OG/Twitter tags will use text fields only
  (title/description/url); no image unless the user supplies one later.

## Changes

### 1. New resume (`resume.html` → `resume.pdf`)

Single-page, single-column, standard section headings (ATS parsers choke on
multi-column layouts and non-standard headers) — visually clean but plain-text
extractable. Sections:

- **Header**: Name, "Full Stack Software Engineer", location, email, phone,
  LinkedIn, GitHub, and the portfolio URL (`im-raghav.github.io/portfolio`).
- **Professional Summary**: 5+ yrs, React/Angular/Next.js/Node.js/TypeScript,
  PostgreSQL/MongoDB, AWS/Docker, end-to-end ownership from schema to
  production UI — mirrors the portfolio's hero/about framing.
- **Technical Skills**, regrouped:
  - Core Stack: JavaScript, TypeScript, React, Next.js, Angular, Node.js, Express
  - Backend & Data: Python, Django, PostgreSQL, MongoDB, SQL, Drizzle ORM, REST API Design
  - Cloud & DevOps: AWS (EC2/RDS), Docker, Vercel, CI/CD, Apache
  - AI/ML: LLM API Integration, TensorFlow, Keras
  - Practices & Tools: System Architecture, Agile, Git, Jira, Confluence
- **Professional Experience** (same two roles, tightened bullets):
  - Opalina Technologies — PushPolitics (React/Angular/Node/NationBuilder),
    Pariksha Pe Charcha / Mann Ki Baat (event-driven, high-traffic), Narendra
    Modi site/app (multilingual CMS), DAM platform bullet upgraded with the
    tech it actually used (Next.js, PostgreSQL, AWS, Docker, AI-assisted
    metadata, CDN pipeline — currently only on the portfolio, not the resume),
    CMS microsites.
  - DXC Technology — same responsibilities, tightened action verbs.
- **Projects**: DAM platform (flagged as production system), GAN-generated
  fake image detection, CCTV surveillance system — same facts as current PDF.
- **Education**: Amity University, B.Tech CSE, 2017–2021, CGPA 7.57.

No invented metrics. Every added skill/tech claim traces to something already
stated on the live portfolio (which the user has confirmed is accurate).

### 2. Portfolio fixes (`index.html`)

- Fix the age self-contradiction: "over 4 years of professional experience" →
  "over 5 years of professional experience" in the About section paragraph
  (the stat card already correctly says 5+).
- Add SEO metadata in `<head>`: `<meta name="description">`, Open Graph
  (`og:title`, `og:description`, `og:type`, `og:url`), Twitter Card
  (`summary` type, title/description), `<link rel="canonical">`, and a simple
  favicon (inline SVG data URI using the existing `<HR/>` monogram styling —
  no new binary asset needed).
- Add a "Download Resume" link/button (hero button row or nav) pointing at
  `resume.pdf`, which will live at the repo root next to `index.html`.

### 3. Delivery mechanism

- Write `resume.html` as a standalone styled document (own `<style>`, not
  reusing portfolio CSS — resume needs print-safe, ATS-safe formatting: no
  fixed pixel backgrounds, no CSS gradients-as-text, no absolute-position
  decorative elements that could confuse text extraction).
- Render to PDF via headless Edge (`msedge.exe --headless --disable-gpu
  --print-to-pdf=resume.pdf file:///.../resume.html`) — confirmed available at
  `C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe`. No browser
  dialogs involved, fully scriptable.
- Both `resume.html` (editable source, kept in the repo for future edits) and
  `resume.pdf` (the artifact linked from the portfolio) are committed.

## Files touched

- `resume.html` (new)
- `resume.pdf` (new, generated)
- `index.html` (edits: About copy fix, `<head>` SEO tags, download-resume link)

## Success criteria

- `resume.pdf` opens correctly, is one page, and every skill/tech claim on it
  also appears somewhere on the live portfolio (mutual consistency).
- Pasting the resume's text into a plain-text editor preserves reading order
  (basic ATS-parseability smoke test).
- Portfolio About section no longer contradicts its own stat card.
- Portfolio `<head>` has description/OG/Twitter/canonical/favicon tags that
  validate (well-formed, no placeholder text left in).
- "Download Resume" link on the portfolio successfully downloads `resume.pdf`.
