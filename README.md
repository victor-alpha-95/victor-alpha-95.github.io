# Vatsalya Awasthi — Personal Website & Self-Publishing System

A minimalist personal site that also runs itself: it publishes, monitors, measures, writes, and grows an audience — with a human approval gate at every step.

**Live:** https://victor-alpha-95.github.io/ · **Short link:** https://tinyurl.com/vatsalyaawasthi

![How the system creates value and where it saves effort](value-flow.png)

---

## 1. What this is (in one line)
A fast, static personal website wrapped in a set of approval-gated automations for publishing project summaries, monitoring uptime, measuring traffic, drafting + distributing writing in the owner's voice, and capturing an audience.

## 2. Principles (the rules everything obeys)
- **Human-in-the-loop.** Nothing is published under the owner's name without his explicit, per-item approval.
- **Noun → verb.** The site is not a static page; it is a process that compounds over time.
- **Discretion.** No confidential specifics (numbers, deal sizes, counterparties) on any public surface.
- **Organic, not "AI-slop."** All writing passes a qualitative + quantitative human-voice standard.
- **Durability over cleverness.** Flat static files, free hosting, no build step that can rot.

## 3. The system, decomposed (MECE)
Eight independent parts, no overlap, together covering the whole project.

### 3.1 Website (the surface)
Flat, hand-built HTML/CSS. Monochrome design, one accent, auto dark/light, WCAG-AA, Lighthouse-95+ target. Sections: Home (Hero · About · Experience · Projects · Writing · Stay in touch), plus `/projects` and `/writing` lists and individual pages.

### 3.2 Project auto-publish (input: completed work)
At the end of a substantive project, the owner is asked whether to publish a concise summary. On approval it generates a page from a fixed template and links it from Projects + the homepage. Briefs are kept in sync with each project's source README.

### 3.3 Uptime monitoring (input: the live URL)
A daily automated check plus an always-on external monitor. On downtime it flags the diagnosed cause (DNS, build failure, HTTPS, render, bandwidth) and proposes/applies a fix.

### 3.4 Psychographic engine (input: the owner's social activity)
Reads the owner's reposts/likes/posts to map his curiosity clusters and writing taste. Refreshed monthly. Drives topic selection. *(Profile output is kept private, not published here.)*

### 3.5 Content engine (input: ideas + voice)
Weekly, it drafts one article in the owner's voice from an idea bank (themes + recent activity + projects), and proposes it. Publishes only on approval.

### 3.6 Human-voice standard (quality gate)
A qualitative + quantitative anti-"AI-slop" standard (banned vocabulary/structures, em-dash budget, sentence-length burstiness, specificity, stance), enforced by a measurement script before anything is proposed.

### 3.7 Distribution engine (output: reach)
Reshapes an approved piece into platform-native formats — canonical website article, a LinkedIn post, and an X thread — built for organic engagement. Posting needs explicit per-platform approval.

### 3.8 Discoverability & audience (output: found, and kept)
- **Analytics:** Cloudflare Web Analytics (cookieless, no consent banner) on every page.
- **SEO/GEO:** per-page meta + Open Graph, `Person` and `BlogPosting` JSON-LD, sitemap, robots — so both search engines and AI answer-engines can find and cite the work.
- **RSS:** `/feed.xml` for the Writing section, with autodiscovery in every page.
- **Owned audience:** an email capture (subscribe form) and a public **WhatsApp Channel**, surfaced in the hero, footer, and Writing page.

## 4. Repository structure (what's in this repo)
```
index.html                         Home (Hero, About, Experience, Projects, Writing, Subscribe)
projects.html · project-<slug>.html    Projects index + individual summaries
writing.html · article-<slug>.html     Writing index + individual articles
thanks.html                        Post-subscribe confirmation page
site.css                           Shared stylesheet (design tokens)
og.png                             Social share image
value-flow.svg · value-flow.png    The value/effort diagram (themed SVG + PNG)
feed.xml                           Writing RSS feed
robots.txt · sitemap.xml           Crawl/index
.nojekyll                          Serve files as-is (no Jekyll)
README.md · PROJECT.md             This documentation
```
The publishing/monitoring/writing automations and their specs live in the owner's private workspace, not in this public repo.

## 5. Hosting & deployment
- **Host:** GitHub Pages (free, automatic HTTPS, custom-domain ready).
- **Deploy:** push/upload changed files to `main`; Pages serves the repo root within ~1–2 minutes.
- **Layout:** flat (no subfolders); sub-pages link `site.css` root-relative.

## 6. Automation cadence
| Task | When | Output |
|---|---|---|
| Uptime check | Daily | Up/down status + diagnosed cause |
| Content proposal | Weekly (Mon) | One drafted article proposed for approval |
| Psychographic refresh | Monthly (1st) | Updated curiosity map + new-writing flag |

## 7. Tech stack
HTML5 · hand-written CSS (custom properties) · vanilla JS (year stamp only) · GitHub Pages · Cloudflare Web Analytics (cookieless) · FormSubmit (no-backend email capture) · UptimeRobot (external monitor). No frameworks, no build, no trackers beyond cookieless analytics; fonts are system-stack for speed and privacy.

## 8. Status & roadmap
- **Live:** website, project auto-publish, uptime monitoring, psychographic engine, content engine, human-voice standard, distribution engine, analytics, RSS, schema, WhatsApp channel, email capture.
- **Next:** custom domain (optional); a managed newsletter (e.g. Buttondown) once the list grows; a "professional register" extension to the voice guide.

See `PROJECT.md` for the full build narrative, decisions, and design invariants.
