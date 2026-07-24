# Portfolio Content Refresh Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Refresh content and broaden positioning of `index.html` (single-file static portfolio site) per `docs/superpowers/specs/2026-07-24-portfolio-refresh-design.md`, with no visual/layout redesign.

**Architecture:** Single static HTML file with inline `<style>` and `<script>`, no build step, deployed via GitHub Pages. All edits are direct in-place edits to `index.html`.

**Tech Stack:** Plain HTML/CSS/JS. No test framework exists (static site) — verification is done via `grep` string checks after each edit plus a final full-page manual browser check (Task 7).

## Global Constraints

- No visual/layout redesign — same dark theme (`--bg`, `--accent`, etc.), same section structure.
- No build tooling or framework introduced. Stays a single static `index.html`.
- No fabricated stats or claims not grounded in real experience.
- Never name Opalina's actual client or the sector (government/defence) for the DAM project — fully generic wording only.
- All edits happen in `C:\Users\HimanshuRaghav\Desktop\portfolio\index.html`.

---

## Task 1: Hero — broaden typing titles and description

**Files:**
- Modify: `index.html:632-635` (hero description paragraph)
- Modify: `index.html:965-971` (typing-loop `titles` array)

**Interfaces:** None (leaf content change, no other task depends on this).

- [ ] **Step 1: Update the hero description**

Edit `index.html`, replacing (lines 632-635):

```html
    <p class="hero-desc">
      Full Stack Developer with 4+ years of experience building scalable web applications,
      high-traffic platforms, and mobile apps. Passionate about clean architecture and impactful products.
    </p>
```

with:

```html
    <p class="hero-desc">
      Software engineer with 5+ years of experience building backend systems, APIs, and
      databases as well as responsive, user-facing interfaces. Comfortable owning a feature
      end-to-end — from schema to production UI — or going deep on either side of the stack.
    </p>
```

- [ ] **Step 2: Update the typing-loop titles array**

Edit `index.html`, replacing (lines 965-971):

```js
  const titles = [
    'Full Stack Developer',
    'Software Engineer',
    'React & Angular Dev',
    'Node.js Developer',
    'Problem Solver',
  ];
```

with:

```js
  const titles = [
    'Full-Stack Developer',
    'Backend Engineer',
    'Frontend Engineer',
    'Node.js / Next.js Developer',
    'Problem Solver',
  ];
```

- [ ] **Step 3: Verify**

Run: `grep -n "Backend Engineer\|Comfortable owning a feature" "C:/Users/HimanshuRaghav/Desktop/portfolio/index.html"`
Expected: both strings found (2 matching lines).

- [ ] **Step 4: Commit**

```bash
cd "C:/Users/HimanshuRaghav/Desktop/portfolio"
git add index.html
git commit -m "content: broaden hero copy for backend/frontend/full-stack positioning"
```

---

## Task 2: About — update stats and broaden copy

**Files:**
- Modify: `index.html:686-689` (about-text third paragraph)
- Modify: `index.html:696-711` (about-stats cards)

**Interfaces:** None.

- [ ] **Step 1: Broaden the "entire stack" paragraph**

Edit `index.html`, replacing (lines 686-689):

```html
        <p>
          I bring expertise across the entire stack — from crafting pixel-perfect responsive UIs
          with <strong>React & Angular</strong>, to building robust RESTful APIs with <strong>Node.js & Django</strong>,
          and managing scalable databases like <strong>MongoDB & PostgreSQL</strong>.
        </p>
```

with:

```html
        <p>
          I bring expertise across the entire stack — from crafting pixel-perfect responsive UIs
          with <strong>React, Angular & Next.js</strong>, to building robust backend systems and
          RESTful APIs with <strong>Node.js & Django</strong>, to managing scalable databases and
          cloud infrastructure with <strong>PostgreSQL, MongoDB & AWS</strong>.
        </p>
```

- [ ] **Step 2: Update the stat cards**

Edit `index.html`, replacing (lines 696-711):

```html
      <div class="about-stats">
        <div class="stat-card">
          <div class="num">4+</div>
          <div class="label">Years Experience</div>
        </div>
        <div class="stat-card">
          <div class="num">2</div>
          <div class="label">Companies</div>
        </div>
        <div class="stat-card">
          <div class="num">10+</div>
          <div class="label">Projects Delivered</div>
        </div>
        <div class="stat-card">
          <div class="num">99%</div>
          <div class="label">ML Model Accuracy</div>
        </div>
      </div>
```

with:

```html
      <div class="about-stats">
        <div class="stat-card">
          <div class="num">5+</div>
          <div class="label">Years Experience</div>
        </div>
        <div class="stat-card">
          <div class="num">2</div>
          <div class="label">Companies</div>
        </div>
        <div class="stat-card">
          <div class="num">10+</div>
          <div class="label">Projects Delivered</div>
        </div>
        <div class="stat-card">
          <div class="num">5+</div>
          <div class="label">National-Scale Platforms</div>
        </div>
      </div>
```

- [ ] **Step 3: Verify**

Run: `grep -n "National-Scale Platforms\|5+" "C:/Users/HimanshuRaghav/Desktop/portfolio/index.html"`
Expected: `National-Scale Platforms` found; two `5+` occurrences (years + platforms stat).

- [ ] **Step 4: Commit**

```bash
cd "C:/Users/HimanshuRaghav/Desktop/portfolio"
git add index.html
git commit -m "content: update about stats (5+ yrs, national-scale platforms) and broaden stack copy"
```

---

## Task 3: Skills — modernize the stack list

**Files:**
- Modify: `index.html:782-828` (`.skills-grid` contents)

**Interfaces:** None.

- [ ] **Step 1: Replace the skills grid**

Edit `index.html`, replacing (lines 782-828, the full `<div class="skills-grid fade-up">...</div>` block):

```html
    <div class="skills-grid fade-up">
      <div class="skill-group">
        <div class="skill-group-title">Languages</div>
        <div class="skill-tags">
          <span class="skill-tag">JavaScript</span>
          <span class="skill-tag">TypeScript</span>
          <span class="skill-tag">Python</span>
          <span class="skill-tag">Java</span>
          <span class="skill-tag">HTML</span>
          <span class="skill-tag">CSS</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Frameworks & Libraries</div>
        <div class="skill-tags">
          <span class="skill-tag">React</span>
          <span class="skill-tag">Angular</span>
          <span class="skill-tag">Node.js</span>
          <span class="skill-tag">Django</span>
          <span class="skill-tag">Bootstrap</span>
          <span class="skill-tag">TensorFlow</span>
          <span class="skill-tag">Keras</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Databases</div>
        <div class="skill-tags">
          <span class="skill-tag">MongoDB</span>
          <span class="skill-tag">PostgreSQL</span>
          <span class="skill-tag">SQL</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Tools & Platforms</div>
        <div class="skill-tags">
          <span class="skill-tag">Git</span>
          <span class="skill-tag">AWS</span>
          <span class="skill-tag">Apache</span>
          <span class="skill-tag">Jira</span>
          <span class="skill-tag">Confluence</span>
          <span class="skill-tag">ClickUp</span>
          <span class="skill-tag">UI/UX Design</span>
          <span class="skill-tag">Agile/Scrum</span>
        </div>
      </div>
    </div>
```

with:

```html
    <div class="skills-grid fade-up">
      <div class="skill-group">
        <div class="skill-group-title">Languages</div>
        <div class="skill-tags">
          <span class="skill-tag">JavaScript</span>
          <span class="skill-tag">TypeScript</span>
          <span class="skill-tag">Python</span>
          <span class="skill-tag">Java</span>
          <span class="skill-tag">SQL</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Frameworks & Libraries</div>
        <div class="skill-tags">
          <span class="skill-tag">Next.js</span>
          <span class="skill-tag">React</span>
          <span class="skill-tag">Node.js</span>
          <span class="skill-tag">Express</span>
          <span class="skill-tag">Angular</span>
          <span class="skill-tag">Django</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Data</div>
        <div class="skill-tags">
          <span class="skill-tag">PostgreSQL</span>
          <span class="skill-tag">Drizzle ORM</span>
          <span class="skill-tag">MongoDB</span>
          <span class="skill-tag">pgvector</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Infra & Cloud</div>
        <div class="skill-tags">
          <span class="skill-tag">AWS (EC2/RDS)</span>
          <span class="skill-tag">Docker</span>
          <span class="skill-tag">Vercel</span>
          <span class="skill-tag">CI/CD</span>
          <span class="skill-tag">CDN & Media Pipelines</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">AI/ML</div>
        <div class="skill-tags">
          <span class="skill-tag">LLM API Integration</span>
          <span class="skill-tag">TensorFlow</span>
          <span class="skill-tag">Keras</span>
        </div>
      </div>
    </div>
```

- [ ] **Step 2: Verify**

Run: `grep -n "Drizzle ORM\|LLM API Integration\|CDN & Media Pipelines" "C:/Users/HimanshuRaghav/Desktop/portfolio/index.html"`
Expected: all three strings found.

- [ ] **Step 3: Commit**

```bash
cd "C:/Users/HimanshuRaghav/Desktop/portfolio"
git add index.html
git commit -m "content: modernize skills section with current stack"
```

---

## Task 4: Projects — add DAM platform card, de-emphasize research projects

**Files:**
- Modify: `index.html:397-452` (add new CSS for compact "other projects" list, after the `.project-accuracy` rule block which ends at line 451)
- Modify: `index.html:837-875` (`.projects-grid` contents — add DAM card, remove the two research project cards)

**Interfaces:** None.

- [ ] **Step 1: Add CSS for the compact "Other Projects" list**

Edit `index.html`, inserting immediately after the `.project-accuracy { ... }` rule (which ends at line 451, right before the `/* ===== EDUCATION ===== */` comment at line 453):

Find this exact block (lines 439-452):

```css
    .project-accuracy {
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
      background: rgba(74,222,128,0.1);
      border: 1px solid rgba(74,222,128,0.2);
      color: var(--green);
      font-size: 0.78rem;
      padding: 0.25rem 0.7rem;
      border-radius: 6px;
      font-weight: 600;
      margin-bottom: 1rem;
    }

    /* ===== EDUCATION ===== */
```

Replace with:

```css
    .project-accuracy {
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
      background: rgba(74,222,128,0.1);
      border: 1px solid rgba(74,222,128,0.2);
      color: var(--green);
      font-size: 0.78rem;
      padding: 0.25rem 0.7rem;
      border-radius: 6px;
      font-weight: 600;
      margin-bottom: 1rem;
    }

    .other-projects-title {
      font-size: 0.75rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.1em;
      color: var(--muted);
      margin: 3rem 0 1rem;
      font-family: 'Fira Code', monospace;
    }
    .other-projects-list { display: flex; flex-direction: column; gap: 0.75rem; }
    .other-project-item {
      display: flex;
      align-items: center;
      flex-wrap: wrap;
      gap: 0.5rem 1.25rem;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 0.9rem 1.25rem;
      transition: border-color 0.2s;
    }
    .other-project-item:hover { border-color: var(--accent); }
    .other-project-item .op-name { font-size: 0.9rem; font-weight: 700; color: var(--text); flex: 0 0 auto; }
    .other-project-item .op-desc { font-size: 0.8rem; color: var(--muted); flex: 1 1 280px; }
    .other-project-item .op-tech { font-size: 0.72rem; color: var(--accent3); font-family: 'Fira Code', monospace; flex: 0 0 auto; }

    /* ===== EDUCATION ===== */
```

- [ ] **Step 2: Replace the projects grid contents**

Edit `index.html`, replacing (lines 837-875, the full `<div class="projects-grid fade-up">...</div>` block plus the two project cards inside it):

```html
    <div class="projects-grid fade-up">

      <div class="project-card">
        <div class="project-icon">🧠</div>
        <div class="project-title">GAN Fake Image Detection Framework</div>
        <div class="project-accuracy">✦ 99%+ Accuracy</div>
        <p class="project-desc">
          A novel neural model-based framework for detecting GAN-generated fake images using a
          combination of frequency spectrum analysis and deep learning. Conducted experiments on
          ~1000 images using unconditional data modeling (StyleGAN2-ADA), achieving state-of-the-art results.
        </p>
        <div class="project-tech">
          <span class="tech-tag">Deep Learning</span>
          <span class="tech-tag">Machine Learning</span>
          <span class="tech-tag">Python</span>
          <span class="tech-tag">StyleGAN2-ADA</span>
          <span class="tech-tag">Frequency Spectrum</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">📷</div>
        <div class="project-title">CCTV Surveillance System (RaspberryPi)</div>
        <p class="project-desc">
          Real-time intelligent CCTV camera surveillance system powered by a machine learning model
          trained using Ensemble Learning. Implemented using OpenCV and Raspberry Pi's camera module
          for live inference and monitoring.
        </p>
        <div class="project-tech">
          <span class="tech-tag">OpenCV</span>
          <span class="tech-tag">RaspberryPi</span>
          <span class="tech-tag">Machine Learning</span>
          <span class="tech-tag">Python</span>
          <span class="tech-tag">Ensemble Learning</span>
        </div>
      </div>

    </div>
```

with:

```html
    <div class="projects-grid fade-up">

      <div class="project-card">
        <div class="project-icon">🗄️</div>
        <div class="project-title">Enterprise Digital Asset Management Platform</div>
        <div class="project-accuracy">✦ Production System</div>
        <p class="project-desc">
          A scalable, enterprise-grade digital asset management platform for organizing, searching,
          and governing large media libraries. Built end-to-end — from database schema and
          access-control design to AI-assisted metadata generation and a CDN-backed delivery pipeline.
        </p>
        <div class="project-tech">
          <span class="tech-tag">Next.js</span>
          <span class="tech-tag">PostgreSQL</span>
          <span class="tech-tag">AWS (EC2/RDS)</span>
          <span class="tech-tag">Docker</span>
          <span class="tech-tag">AI/LLM Integration</span>
          <span class="tech-tag">CDN Pipeline</span>
        </div>
      </div>

    </div>

    <div class="other-projects-title">// other projects & research</div>
    <div class="other-projects-list fade-up">
      <div class="other-project-item">
        <span class="op-name">🧠 GAN Fake Image Detection Framework</span>
        <span class="op-desc">Neural framework detecting GAN-generated fake images via frequency spectrum analysis + deep learning (StyleGAN2-ADA), 99%+ accuracy.</span>
        <span class="op-tech">Deep Learning · Python · StyleGAN2-ADA</span>
      </div>
      <div class="other-project-item">
        <span class="op-name">📷 CCTV Surveillance System (RaspberryPi)</span>
        <span class="op-desc">Real-time intelligent surveillance using an Ensemble Learning model with OpenCV on Raspberry Pi.</span>
        <span class="op-tech">OpenCV · RaspberryPi · Ensemble Learning</span>
      </div>
    </div>
```

- [ ] **Step 3: Verify**

Run: `grep -n "Enterprise Digital Asset Management Platform\|other-projects-list\|op-name" "C:/Users/HimanshuRaghav/Desktop/portfolio/index.html"`
Expected: matches found for the new project title, the list container, and at least 2 `op-name` spans.

Run: `grep -n "Opalina\|government\|defence\|defense" "C:/Users/HimanshuRaghav/Desktop/portfolio/index.html"`
Expected: no matches inside the new project card text (the word "Opalina" will still legitimately appear in the Experience section — confirm any hits are only there, not in the new Projects section).

- [ ] **Step 4: Commit**

```bash
cd "C:/Users/HimanshuRaghav/Desktop/portfolio"
git add index.html
git commit -m "content: add DAM platform project, de-emphasize research projects into compact list"
```

---

## Task 5: Contact form — wire to Formspree

**Files:**
- Modify: `index.html:935-951` (contact form inputs — add `name` attributes)
- Modify: `index.html:1009-1016` (`handleSubmit` JS)

**Interfaces:** None. `FORMSPREE_ENDPOINT` constant is local to the script block, not consumed elsewhere.

- [ ] **Step 1: Add `name` attributes to form fields (required for Formspree)**

Edit `index.html`, replacing (lines 935-951):

```html
      <form class="contact-form" onsubmit="handleSubmit(event)">
        <div class="form-group">
          <label class="form-label">Your Name</label>
          <input class="form-input" type="text" placeholder="John Doe" required />
        </div>
        <div class="form-group">
          <label class="form-label">Email Address</label>
          <input class="form-input" type="email" placeholder="john@example.com" required />
        </div>
        <div class="form-group">
          <label class="form-label">Message</label>
          <textarea class="form-textarea" placeholder="Hi Himanshu, I'd love to connect..." required></textarea>
        </div>
        <button type="submit" class="btn btn-primary" style="width:100%; justify-content:center;">
          Send Message
        </button>
      </form>
```

with:

```html
      <form class="contact-form" onsubmit="handleSubmit(event)">
        <div class="form-group">
          <label class="form-label">Your Name</label>
          <input class="form-input" type="text" name="name" placeholder="John Doe" required />
        </div>
        <div class="form-group">
          <label class="form-label">Email Address</label>
          <input class="form-input" type="email" name="email" placeholder="john@example.com" required />
        </div>
        <div class="form-group">
          <label class="form-label">Message</label>
          <textarea class="form-textarea" name="message" placeholder="Hi Himanshu, I'd love to connect..." required></textarea>
        </div>
        <button type="submit" class="btn btn-primary" style="width:100%; justify-content:center;">
          Send Message
        </button>
      </form>
```

- [ ] **Step 2: Replace the fake `handleSubmit` with a real Formspree POST**

Edit `index.html`, replacing (lines 1009-1016):

```js
  // Contact form
  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('button[type=submit]');
    btn.textContent = 'Message Sent! ✓';
    btn.style.background = '#4ade80';
    setTimeout(() => { btn.textContent = 'Send Message'; btn.style.background = ''; e.target.reset(); }, 3000);
  }
```

with:

```js
  // Contact form
  // TODO: replace YOUR_FORM_ID with your Formspree form ID (create a free form at https://formspree.io)
  const FORMSPREE_ENDPOINT = 'https://formspree.io/f/YOUR_FORM_ID';

  async function handleSubmit(e) {
    e.preventDefault();
    const form = e.target;
    const btn = form.querySelector('button[type=submit]');
    const originalText = btn.textContent;
    btn.disabled = true;
    btn.textContent = 'Sending...';
    try {
      const res = await fetch(FORMSPREE_ENDPOINT, {
        method: 'POST',
        body: new FormData(form),
        headers: { 'Accept': 'application/json' },
      });
      if (res.ok) {
        btn.textContent = 'Message Sent! ✓';
        btn.style.background = '#4ade80';
        form.reset();
      } else {
        btn.textContent = 'Failed — try again';
        btn.style.background = '#f87171';
      }
    } catch (err) {
      btn.textContent = 'Failed — try again';
      btn.style.background = '#f87171';
    } finally {
      setTimeout(() => { btn.textContent = originalText; btn.style.background = ''; btn.disabled = false; }, 3000);
    }
  }
```

- [ ] **Step 3: Verify**

Run: `grep -n "FORMSPREE_ENDPOINT\|name=\"message\"" "C:/Users/HimanshuRaghav/Desktop/portfolio/index.html"`
Expected: both found.

- [ ] **Step 4: Commit**

```bash
cd "C:/Users/HimanshuRaghav/Desktop/portfolio"
git add index.html
git commit -m "feat: wire contact form to Formspree instead of fake success animation"
```

---

## Task 6: Footer — dynamic year

**Files:**
- Modify: `index.html:957-961` (footer HTML)
- Modify: `index.html` end of `<script>` block (add year-setting JS, after the block added in Task 5)

**Interfaces:** None.

- [ ] **Step 1: Replace the hardcoded year with a target span**

Edit `index.html`, replacing (lines 957-961):

```html
<footer>
  <p class="footer-text">
    Designed & built by <span>Himanshu Raghav</span> · <span>2024</span>
  </p>
</footer>
```

with:

```html
<footer>
  <p class="footer-text">
    Designed & built by <span>Himanshu Raghav</span> · <span id="footer-year"></span>
  </p>
</footer>
```

- [ ] **Step 2: Set the year via JS**

Edit `index.html`, adding this at the end of the `<script>` block, immediately before the closing `</script>` tag:

```js

  // Footer year
  document.getElementById('footer-year').textContent = new Date().getFullYear();
```

- [ ] **Step 3: Verify**

Run: `grep -n "footer-year" "C:/Users/HimanshuRaghav/Desktop/portfolio/index.html"`
Expected: 3 matches (the `id="footer-year"` span, and two references in the JS — `getElementById` and nothing else duplicated).

- [ ] **Step 4: Commit**

```bash
cd "C:/Users/HimanshuRaghav/Desktop/portfolio"
git add index.html
git commit -m "fix: compute footer year dynamically instead of hardcoding 2024"
```

---

## Task 7: Full-page verification and push

**Files:** None modified — verification only.

- [ ] **Step 1: Open the page locally in a browser**

Run: `start "C:/Users/HimanshuRaghav/Desktop/portfolio/index.html"` (Windows — opens in default browser)

Manually check:
- Hero typing animation cycles through the 5 new titles without JS errors (open DevTools console, confirm no errors).
- About stat cards show `5+ / 2 / 10+ / 5+` with correct labels.
- Skills section shows the 5 new groups (Languages, Frameworks & Libraries, Data, Infra & Cloud, AI/ML).
- Projects section shows the DAM platform as the single featured card, with the "Other Projects & Research" compact list below showing both older projects.
- Contact form: submitting without a real Formspree ID configured will fail — confirm the button shows "Failed — try again" gracefully (not a JS exception) rather than testing an actual send.
- Footer shows the current year, not "2024".
- No layout breakage at mobile width (resize DevTools to ~375px, confirm nav hamburger, stacked grids, and the other-projects list still read cleanly).

- [ ] **Step 2: Confirm no confidential info leaked**

Run: `grep -in "opalina\|government\|defence\|defense" "C:/Users/HimanshuRaghav/Desktop/portfolio/index.html"`
Expected: any matches are confined to the pre-existing Experience section (job history), never inside the Projects section describing the DAM platform.

- [ ] **Step 3: Push to GitHub Pages**

```bash
cd "C:/Users/HimanshuRaghav/Desktop/portfolio"
git status
git push origin main
```

Confirm `git status` shows a clean tree (all 6 commits from Tasks 1-6 present) before pushing. GitHub Pages auto-deploys from `main` — changes go live at `im-raghav.github.io/portfolio` within a few minutes.

- [ ] **Step 4: Note the outstanding manual dependency**

Reminder for the user (not a code step): the contact form will not actually deliver messages until `YOUR_FORM_ID` in the `FORMSPREE_ENDPOINT` constant (Task 5) is replaced with a real Formspree form ID from a free account at formspree.io.
