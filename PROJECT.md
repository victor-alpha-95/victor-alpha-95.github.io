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

## 4. The eight systems, in detail
1. **Website** — semantic HTML, design-token CSS, accessibility + performance baselines, SEO/OG/Twitter meta, JSON-LD `Person` schema, sitemap, robots.
2. **Project auto-publish** — end-of-project prompt → fixed summary template → approval → `project-<slug>.html` + cards on Projects/Home + sitemap → deploy.
3. **Uptime monitoring** — daily diagnostic check (cause taxonomy + fix) backed by an always-on external monitor for 24/7 coverage.
4. **Psychographic engine** — monthly harvest of the owner's social attention (posts, reposts, likes, bookmarks/saved — private items summarized into theme tallies only, never reproduced), classified into seven theme clusters, *each carrying an editorial thesis* (a held belief, what it argues against, and the lived experience that makes it credible). New themes detected outside the clusters are flagged for the owner's approval, never silently added. Private output.
5. **Content engine** — a *scored idea bank*: every idea rated on audience resonance, attention heat, differentiation ("could anyone else write this?"), timeliness, and ease; re-ranked monthly; replenished with freshly minted ideas plus at most one bounded "exploratory" adjacent-theme suggestion; a monthly triage puts the unreviewed tail in front of the owner (promote / park / kill — nothing rots, and nothing dies without his word). Weekly: top-ranked idea → draft in voice → binding quality gate → propose → publish only on approval.
6. **Human-voice standard** — qualitative banned vocabulary/structures + quantitative targets (burstiness ≥8, em-dash budget, specificity, stance), enforced by a measurement script. **Binding:** a draft ships only fully clean or with each flag explicitly waived in writing.
7. **Distribution engine** — one approved piece → website article (always first) + LinkedIn native + X long-form, each platform-native. Posting is *slotted and ask-first*: scheduled slots (Tue/Thu evening) ping the owner with the exact ready copy and post only on his explicit yes at that moment — content approval and posting approval are separate gates, both required, every time.
8. **Discoverability & audience** — cookieless Cloudflare Web Analytics on every page; `Person` + `BlogPosting` JSON-LD, Open Graph, sitemap and robots for search + AI answer-engines; an RSS feed (`/feed.xml`) with autodiscovery; and two owned-audience capture points — an email subscribe form and a public WhatsApp Channel.

### 4b. The closed loop (v2, June 2026)
What turned a pipeline into a system: the parts now feed each other on a fixed rhythm.
- **Monthly (1st):** a metrics pass harvests audience signals (site, search, social, email) → the psychographic refresh combines them with the owner's fresh attention data → every cluster gets a verdict (heat up / hold / cool / divergence) → the idea bank is re-scored and re-sorted, new ideas are minted, and a triage digest collects the owner's verdicts on the tail. Divergences between what the owner loves and what the audience rewards surface as questions, never auto-resolved toward the audience — voice fidelity outranks engagement.
- **Weekly (Mon):** the top-scored idea is drafted in the owner's voice, passes the binding voice gate, and is proposed. On approval it publishes (website → RSS → email → WhatsApp), and the distribution pack queues for the slots.
- **Slotted (Tue/Thu):** each platform post goes out only on the owner's yes at the slot, followed by his reply window — because author-engaged replies, not posting volume, are what the platforms actually reward.

The whole chain, with the three human moments starred, is captured in `value-flow.svg` (and `value-flow.png`):

![Value chain: monthly intelligence (attention + audience signals → psychographic profile → scored idea bank with owner triage), weekly production (draft → binding voice gate → owner approval → publish), slotted ask-first distribution (LinkedIn Tue, X Thu — posting only on an explicit yes), and a dashed feedback line returning performance data to the monthly intelligence pass.](value-flow.png)

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

## 9. Changelog
- **v1 (8 Jun 2026):** site live; eight systems designed; first essays published.
- **v2 (12 Jun 2026):** the closed loop. Full technical-SEO pass (canonical URLs + social cards on every page, branded 404, author-entity consistency); voice gate made binding; idea bank rebuilt as a scored pipeline with monthly triage; psychographic engine extended to bookmarks/saved behind a novelty gate; monthly metrics → recalibration → re-ranking loop wired end-to-end; slotted ask-first distribution (LinkedIn Tue / X Thu). Every change passed an independent adversarial review before shipping.

## 10. Lessons
- The best version of a "small, fixed" deliverable is often a process, not an object.
- Delegation works when you hand over the outcome and keep the judgment.
- Quality control for AI-assisted writing has to be *measurable*, not just felt — hence the voice-check script.
- A pipeline becomes a system the day its output data starts choosing its next input — and it stays trustworthy only because three moments remain human: the triage, the approval, and the yes before each post.
