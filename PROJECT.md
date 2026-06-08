# PROJECT.md — Build Narrative & Design Record

A detailed record of how this site and its self-publishing system were designed, built, and deployed — and the decisions behind each part. Companion to `README.md`.

---

## 1. Goal & context
Start from nothing and end with a single, fast, minimalist destination that (a) introduces the owner professionally, (b) links his social profiles, and (c) is architected to grow two sections over time — Projects and Writing — with as little manual upkeep as possible. The implicit goal that emerged: build a *system*, not a page.

## 2. Method (how it was built)
A staged, validation-first approach, each stage approved before the next:
1. **Benchmark** current best-practice personal sites (2025–26 minimalist patterns: one accent, whitespace, stacked cards, fast load).
2. **Propose** a template + stack, then self-review and refine the proposal.
3. **Map requirements** and every go-live step; self-review and refine.
4. **Build** the static site and draft real copy from the owner's CV/profile.
5. **Preview → approve → deploy** to GitHub Pages; verify live (HTTPS, mobile/desktop, both themes, links, Lighthouse).
6. **Iterate**: layered on automations (auto-publish, uptime, psychographic map, content engine, anti-slop standard, distribution engine), each approved in turn.

## 3. Key decisions & rationale
- **Hosting: GitHub Pages.** Free, durable, automatic HTTPS, custom-domain-ready, and git-based — the version-controlled flow is what makes publishing a simple push. Evaluated against Vercel/Netlify; for a static content site, Pages wins on simplicity and longevity.
- **Static HTML over a framework.** Chosen for previewability and a zero-build deploy that can't rot. (Astro was the original recommendation; plain static was adopted as the documented, lower-risk fallback because it deploys with no build step.)
- **Flat file layout.** Unique root-level filenames (`article-<slug>.html`, etc.) rather than nested folders — reliable for web-based uploads and simple to reason about.
- **Design: modern monochrome + one accent.** Reads as credible and current, ages well, loads fastest, and puts the words first. Dark/light auto via `prefers-color-scheme`.
- **Discretion over specifics.** The public site summarizes impact without confidential numbers, deal sizes, or counterparties.

## 4. The seven systems, in detail
1. **Website** — semantic HTML, design-token CSS, accessibility + performance baselines, SEO/OG/Twitter meta, JSON-LD `Person` schema, sitemap, robots.
2. **Project auto-publish** — end-of-project prompt → fixed summary template → approval → `project-<slug>.html` + cards on Projects/Home + sitemap → deploy.
3. **Uptime monitoring** — daily diagnostic check (cause taxonomy + fix) backed by an always-on external monitor for 24/7 coverage.
4. **Psychographic engine** — comprehensive harvest of the owner's social activity, classified into curiosity clusters with most-amplified voices; refreshed monthly; private output.
5. **Content engine** — weekly: pick best idea (themes map + recent activity + projects) → draft in voice → self-check → propose → publish only on approval.
6. **Human-voice standard** — qualitative banned vocabulary/structures + quantitative targets (burstiness ≥8, em-dash budget, specificity, stance), enforced by a measurement script.
7. **Distribution engine** — one approved piece → website article + LinkedIn post + X thread, each platform-native; posting is per-platform, approval-gated.

## 5. Design invariants (don't drift)
- Monochrome + single accent; serif headings (Iowan/Palatino/Georgia), sans body.
- Dark/light auto; Lighthouse ≥95; WCAG 2.1 AA.
- Stacked-card layout for Projects/Writing. No carousels, autoplay, or heavy imagery.
- Homepage shows only the 5 most recent items per section; full lists on section pages.

## 6. Deployment runbook
The repo root mirrors the site (flat). Pages deploys from `main`/root automatically (~1–2 min). Deploy by uploading changed files to the repo (web upload via browser automation is the proven path), then verify the live URL.

## 7. The approval model (the spine of the whole thing)
Every automation is designed to do the heavy, repeatable middle on its own and **stop at the one human moment** — the decision to publish under the owner's name. This single rule is what makes the autonomy safe: speed and tirelessness from the machine, judgment and taste from the human.

## 8. What's deliberately private
The psychographic profile and the internal engine specs live in a private workspace, not this public repo. The repo documents the architecture and the surface, not the owner's personal taste-map.

## 9. Lessons
- The best version of a "small, fixed" deliverable is often a process, not an object.
- Delegation works when you hand over the outcome and keep the judgment.
- Quality control for AI-assisted writing has to be *measurable*, not just felt — hence the voice-check script.
