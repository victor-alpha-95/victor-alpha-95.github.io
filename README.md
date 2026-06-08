# Vatsalya Awasthi — Personal Website & Self-Publishing System

A minimalist personal site that also runs itself: it publishes, monitors, and writes (with a human approval gate at every step). Built AI-natively in a single Cowork project.

**Live:** https://victor-alpha-95.github.io/ · **Short link:** https://tinyurl.com/vatsalyaawasthi

---

## 1. What this is (in one line)
A fast, static personal website wrapped in a set of approval-gated automations for publishing project summaries, monitoring uptime, and drafting + distributing writing in the owner's voice.

## 2. Principles (the rules everything obeys)
- **Human-in-the-loop.** Nothing is published under the owner's name without his explicit, per-item approval.
- **Noun → verb.** The site is not a static page; it is a process that compounds over time.
- **Discretion.** No confidential specifics (numbers, deal sizes, counterparties) in any public surface.
- **Organic, not "AI-slop."** All writing passes a qualitative + quantitative human-voice standard.
- **Durability over cleverness.** Flat static files, free hosting, no build step that can rot.

## 3. The system, decomposed (MECE)
Seven independent parts, no overlap, together covering the whole project.

### 3.1 Website (the surface)
Flat, hand-built HTML/CSS. Monochrome design, one accent, auto dark/light, WCAG-AA, Lighthouse-95+ target. Sections: Home (Hero · About · Experience · Projects · Writing), plus `/projects` and `/writing` lists and individual pages.

### 3.2 Project auto-publish (input: completed work)
At the end of a substantive project, the owner is asked whether to publish a concise summary. On approval it generates a page from a fixed template and links it from Projects + the homepage.

### 3.3 Uptime monitoring (input: the live URL)
A daily automated check plus an always-on external monitor. On downtime it flags the diagnosed cause (DNS, build failure, HTTPS, render, bandwidth) and proposes/applies a fix.

### 3.4 Psychographic engine (input: the owner's social activity)
Reads the owner's reposts/likes/posts to map his curiosity clusters and writing taste. Refreshed monthly. Drives topic selection for the content engine. *(Profile output is kept private, not published here.)*

### 3.5 Content engine (input: ideas + voice)
Weekly, it drafts one article in the owner's voice from an idea bank (themes + recent activity + projects), and proposes it. Publishes only on approval.

### 3.6 Human-voice standard (quality gate)
A qualitative + quantitative anti-"AI-slop" standard (banned vocabulary/structures, em-dash budget, sentence-length burstiness, specificity, stance), enforced by a measurement script before anything is proposed.

### 3.7 Distribution engine (output: reach)
Reshapes an approved piece into platform-native formats — canonical website article, a LinkedIn post, and an X thread — built for organic engagement. Posting needs explicit per-platform approval.

## 4. Repository structure (what's in this repo)
```
index.html                         Home (Hero, About, Experience, Projects, Writing)
projects.html                      Projects index
project-<slug>.html                Individual project summaries
writing.html                       Writing index
article-<slug>.html                Individual articles
site.css                           Shared stylesheet (design tokens)
og.png                             Social share image
robots.txt · sitemap.xml           Crawl/index
.nojekyll                          Serve files as-is (no Jekyll)
README.md · PROJECT.md             This documentation
```
The publishing/monitoring/writing automations and their specs live in the owner's private Cowork workspace, not in this public repo.

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
HTML5 · hand-written CSS (custom properties) · vanilla JS (year stamp only) · GitHub Pages · UptimeRobot (external monitor). No frameworks, no build, no trackers; fonts are system-stack for speed and privacy.

## 8. Status & roadmap
- **Live:** website, project auto-publish, uptime monitoring, psychographic engine, content engine, human-voice standard, distribution engine.
- **Next:** custom domain (optional); a "professional register" extension to the voice guide once more work-style samples exist.

See `PROJECT.md` for the full build narrative, decisions, and design invariants.
