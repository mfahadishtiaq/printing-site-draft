# Team Archive — Decision Log & Memory (repo copy)
*Exported from the Cowork project 2026-07-19. From now on, UPDATE THIS FILE at the end of every Claude Code working session — it is the project's long-term memory.*

## Status snapshot (2026-07-19, end of direction-gate session)
- v1 "Ink & Paper" (white + CMYK magenta, Space Grotesk): BUILT then REJECTED in full. The 5 pages in this repo are that v1 — mechanics reference only.
- v2 "The Corner Press": **PARTIALLY SUPERSEDED**. Approved from a written spec, never rendered; re-opened same day when Fahad judged the shared work "too basic" and required a premium result.
  - SURVIVES: paper `#FAF5EC` + warm ink `#2A2119` (14.5:1), terracotta `#B84A26` as sole accent (provisional on storefront-sign photo), Fraunces + Inter, no stock people, quiet motion.
  - DEAD: the even 9-step type ramp, Fraunces-at-600-only, radii 6/10/16 + 16px card, `--shadow-warm`, the `rgba(42,33,25,.08)` hairline, marigold `#F2C14E` (1.55:1 — cannot be text, icon or rule), centred `.block-head`, gradient sheets/tiles, the marquee (WCAG 2.2.2), `backdrop-filter` header, global scroll fade-up, all invented testimonials.
  - New colour rulings: `--accent-deep #96391B` for inline links/focus text (terracotta is 4.27:1 on `--paper-2` = AA FAIL); `--accent-on-ink #E8763A` (5.3:1); accent ≤3 uses per viewport-height.
- Homepage must serve BOTH audiences (walk-in/wedding + small-business repeat) on ONE page — forked by **job**, not by audience. No audience-split pages.
- Diagnosis agreed: v1 failed on STRUCTURE (five `repeat(N,1fr)` grids under identical centred headings), not palette — and beneath that, on EMPTY CONTENT. A third repaint would fail a third time.
- Three rendered directions built and critiqued (see below). None approved; all three await Fahad's five calls in `direction-resolution.md` §3.
- Roadmap (docs/roadmap.md): GBP-first. Google Business Profile still at ZERO — this is the project's largest strategic error to date; four design meetings, no reviews.
- Google Business Profile: fresh start confirmed (old business had no Google presence).
- Migration to Claude Code: kit (CLAUDE.md + docs/ + .claude/skills/) committed by Fahad as his first Claude Code exercise.

## The three v3 directions (2026-07-19) — boards in `design-boards/`
Scored by design-director (visual), the client persona (uncle, veto on recognisability), and ux-strategist (conversion). None reached approval.

- **A · The Chapter Rail** — `design-boards/direction-a.html` — **6.7/10** (7 / 7 / 6)
  Thesis: premium = EDITORIAL AUTHORITY. Corner Press rebuilt from the grid up: a persistent 96px chapter rail (numerals 01–07, running eyebrow, real 1px ink rule) from 900px, plus TRUE-TRIM specimens at real product ratios (3.5:2, 5:7, 4:3, 24:9, 8.5:11) so the grid *cannot* collapse into `repeat(3,1fr)`.
  Verdict: system is premium, render is not yet — tallest ratio got the widest column (~840px near-empty wedding tile), artwork sized in `vw` not `cqw`, hero shows a print shop printing nothing. Client: warmest and most "his", but the copy "talks like a design magazine, not a corner shop"; wants shop English, WhatsApp green, same-day/languages/parking above the fold. UX: best desktop mechanics of the three; the dual-audience fork is desktop-only and its B2B branch dead-ends in the walk-in form.
- **C · The Job Ticket** — `design-boards/direction-c.html` — **6.3/10** (7 / 6 / 6)
  Thesis: premium = PRECISION. The print trade's own docket — ruled ledger, register marks, kraft/trace palette, every item a spec (stock · finish · turnaround · from $X) attacking the universal Brampton weakness of pricing opacity (research L19).
  Verdict: clears "too basic" (rule-weight hierarchy, zero radii/shadows, sheet frame) but reads as a FORM not a page — uniform density for ~900px, the "from $00" that IS the argument set smaller than its own heading, thumbnails not work-shown-large, ~25 red placeholder tags as visual confetti. Client: "my shop rendered as its own filing cabinet" — cold; wedding cards reduced to a materials list. UX: CTA desert across three sections and NO mobile nav at all below 900px. Structurally load-bearing on unanswered Q12/Q15/Q16/Q20/Q21.
- **B · The Night Press** — `design-boards/direction-b.html` — **5.3/10** (6 / 4 / 6)
  Thesis: premium = GRAVITAS, argued as a product demo (white ink/foil on black stock is a real upsell). The luxury pole, presented honestly as third of three by its own author.
  Verdict: most intellectually honest board (no 1120px container, correct `opsz` use, measured contrast receipts) but five consecutive `min-height:85vh` vertically-centred acts is the single most template-coded pattern there is, and the thesis object is a centred 760px card. Client vetoed it as the whole site (4/10): "it looks like a jewellery store… he will assume he cannot afford me and I will never know." Keep the dark treatment for a future wedding/shaadi page only.

## Decisions (append new ones with dates)
- 2026-07-19 · 5-page structure; conversion trio every page; "from $X" ranges — evidence-based, survive any redesign. **STILL STANDS.**
- 2026-07-19 · GBP-first strategy; no stock people photos, ever. **STILL STANDS.**
- 2026-07-19 · Warmth strategy: craft lane (warm materials + real photos), never clutter. **STILL STANDS, and confirmed as the architecture** — luxury is at most one contained movement, because the luxury vocabulary is imagery-led and we own zero photographs.
- 2026-07-19 · Terracotta #B84A26 is the ONLY accent; marigold optional in small doses. **SUPERSEDED** — marigold is dead (1.55:1); terracotta reserved for display type, solid fills and eyebrows ≥18px, with `--accent-deep` for links.
- 2026-07-19 · design-direction.md L4 "page structure and conversion mechanics unchanged". **SUPERSEDED / formally surrendered by the design-director** — structure is the diagnosed problem.
- 2026-07-19 · Direction approval gates are real. **STILL STANDS, and hardened**: gates are against rendered boards judged at 360px on a phone, uncle first.
- 2026-07-19 · `rates.html` rescoped to "How pricing works" (from-ranges + what moves the price + what's free); still no price table on the homepage.
- 2026-07-19 · Quote form inline on `index.html` AND `contact.html`, one Formspree endpoint + honeypot. Floating WhatsApp button stays (sticky bottom bar rejected). `thank-you.html` allowed as conversion plumbing, not a nav page.
- 2026-07-19 · Ambition floor, grep-testable in QA: no section with >4 equal-weight items; ≥2 asymmetric sections at ≥900px; one element ≥70vw; ≥3 distinct homepage section structures; homepage 7–9 screenfuls at 390px, ≤600 words of prose.
- 2026-07-19 · Google Fonts stays on the standard `<link>` (gstatic-URL inlining vetoed). Optional 20-line inline-the-CSS build script allowed; output stays self-contained.

## Lessons learned
- **A direction approved from a WRITTEN SPEC is not an approved LOOK.** Corner Press passed a document gate and failed the moment it was imagined rendered. Never approve a direction from prose again — rendered HTML boards, real fonts, real colour, judged at 360px on a phone, uncle first. *(We wrote the "render the boards" lesson below on 2026-07-19 and then did not do it. That is why the day was spent twice.)*
- **A board built on placeholders cannot be judged.** Both the uncle and the design-director independently said the boards read as basic partly *because* `$XX`, `0:00`, three 64px zeros and the word "Placeholder" own the largest type on the page. Content is doing most of the lifting we keep attributing to tokens.
- **Voice is a design surface.** The strongest board lost points not on layout but on prose — "specimen", "the only claim that survives a second reading". Write shop English, not design English.
- **Compute contrast before approving, not during build.** An approved document shipped an AA failure (terracotta on `--paper-2`) that nobody had checked.
- Client details are the bottleneck, not the build — questionnaire out early, launch with marked placeholders.
- Placeholder content must be explicitly marked fake so it can never accidentally ship — but marks must be one quiet system, not 25 red stickers that destroy the thing being judged.
- **Nothing decided in a session is real until it is a diff in `docs/`.**
- Repo is the source of truth; sessions are ephemeral.

## Open gates & blockers
- **G0 — URGENT, does not wait for approval:** `noindex` all five pages (or GitHub Pages off). A fake business name, ~10 invented prices and 3 fabricated testimonials are live, crawlable, and attached to Fahad's real GitHub account. Fabricated testimonials on a public commercial page are Competition Act s.74.01 exposure.
- **G1 — Google Business Profile opened.** Blocks nothing; blocked by nothing; 1–2 week verification postcard; ~100 reviews ≈ top 3 in Brampton (research L21). Currently at zero.
- **G2 — Questionnaire, by phone not email.** Q12, Q24, Q25, Q26, Q33 minimum. Q12/Q24 set the fork order; Q25 sets the ceiling on how "premium" can go before the site lies about the business; Q26 (languages) may be a *typeface* input. Direction C additionally gated on Q15/Q16/Q20/Q21.
- **G3 — Photo shoot: 8 photos, one afternoon, zero dollars** (6 jobs, 1 storefront, 1 owner). **Launch gates on ≥6 job photos + 1 storefront; the build does not.**
- **G4 — Storefront sign photo may adjust terracotta.** Unchanged, still open.
- **G5 — Uncle approves a rendered direction.** He is the veto on recognisability; Fahad is the veto on quality.
- **G6 — Domain + Formspree account.** Unchanged.
- Mobile click-to-call is BROKEN and has been all along: `.nav-cta .btn-outline` is in the `≤640` hide rule at `index.html:411`. One-line fix, worth more than any new mechanism.
- Sequencing recommendation on the table: one probe section (fork band + one work slot) at 360px this week; full three boards only after Q12/Q24/Q26 and ≥3 real photos.

## Session log (append at end of each session)
- 2026-07-19 · Cowork: design reset, roadmap, Corner Press direction + tokens, migration kit prepared.
- 2026-07-19 · Claude Code, direction gate: Corner Press re-opened ("too basic"), dual-audience homepage decided, three directions built and critiqued (A 6.7 / C 6.3 / B 5.3), craft lane settled as the architecture, resolution chaired by web-consultant. Nothing approved yet — awaiting Fahad's five calls.


---

## Session 2026-07-19 (Claude Code) — direction re-opened, rebuilt, and shipped as a link

**Outcome:** Direction F approved in principle. Bright white base, Fraunces (headlines) +
Literata (body) + Familjen Grotesk (interface), flame red-orange accent (#FF4D1C display /
#D92B0E functional), heavy animation, nine hand-drawn CSS/SVG sample pieces.
Live preview: https://claude.ai/code/artifact/62e622db-17ef-435f-aaa7-ad28c36ea86c
Local build: `design-boards/direction-final.html`

**The big correction.** The warm-craft premise (cream/terracotta, "quiet motion") came from
Cowork and was never checked against Fahad's eye. Three boards were produced inside that
premise; all three were rejected. When shown v1 again he said it was the best thing he had
seen — bright, high-contrast, modern. Two full design cycles were spent choosing between
shades of an assumption nobody had validated. `docs/design-direction.md` is now STALE and
contradicts what was built.

### Process lessons — these are the value of this session

1. **Approve rendered pages, never written specs.** Corner Press passed a document gate and
   failed the moment it was seen. Every gate from here is against a rendered page.
2. **Offer categorically different options, not N variations of one.** Eleven neutral
   sans-serifs read to a non-designer as one option shown eleven times. The round that
   worked offered four different *approaches* (one-family / serif body / character sans /
   mono labels) and he chose immediately.
3. **Isolate one variable per specimen.** Font sheets were rendered in black and white so
   colour could not contaminate the judgement; colour was decided separately. Judging two
   things at once means blaming the wrong one.
4. **Never let content visibility depend on JavaScript.** The showcase and all work tiles
   were hidden by default and revealed by an IntersectionObserver. The observer didn't
   fire; every image was invisible while text rendered fine. Fixed with progressive
   enhancement (hidden states apply only when JS is confirmed) plus a timed failsafe that
   reveals everything regardless. An un-animated page beats an invisible one.
5. **Verify visually before claiming something works.** Three rounds were lost to theories
   about stale browser tabs while the real cause was `opacity: 0` on a container. Headless
   Chrome was available the whole time:
   `"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new
   --virtual-time-budget=15000 --window-size=1400,900 --screenshot=out.png "file://…"`
   Use `--dump-dom` plus a `getBoundingClientRect` probe to get real geometry. Use a
   virtual-time budget of 15s or more, or reveal timers get cut off and the page looks blank.
6. **Check the server's root before trusting localhost.** A stale `http.server` held port
   8000 with a deleted working directory and returned 404 for everything, including `/`.

### Tooling findings
- **No image-generation tool is available** in Claude Code (no Higgsfield connector reachable).
- **Canva can generate designs but not showcase imagery** — PNG export is fixed at the
  design's native size (a business card exports at 336×192) and width/height parameters
  error out. All nine samples were hand-built in CSS/SVG instead: sharp at any size, no
  file weight.
- **Published pages block font CDNs.** Fonts must be embedded as `@font-face` data URIs or
  the typography silently falls back. Latin-subset only, used weights only: ~285 KB.

### Still blocked (unchanged, and now the whole critical path)
- **Uncle has never seen any direction.** Approval gate 1 in the roadmap is still open.
  The preview link exists specifically to close it.
- **Questionnaire** Q12/Q15/Q16/Q20/Q21/Q24/Q25 — the FAQ and price anchors are placeholders.
- **Photo shoot.** Nine invented businesses (Sandhu Realty, Aisha & Bilal, Tandoori Kitchen,
  Sharma Plumbing) currently stand in for the portfolio. None can ship.
- **Reviews section is deliberately empty** — nothing fake goes there, ever.
- `docs/design-direction.md` needs rewriting to Direction F; it currently states the opposite.

**Signed off 2026-07-19.** Direction F working and accepted by Fahad. Canonical deliverable:
`AZ-Printing-Demo.html` on the Desktop (self-contained, fonts embedded, opens offline).
Repo copies: `AZ-Printing-Demo.html` and `design-boards/direction-final.html` (linked fonts).

Two final fixes worth remembering:
- **Hover-pause on a hero carousel is a trap.** It was added so a piece could be studied, but
  the hero is exactly where the cursor rests, so the slideshow froze on slide 1 and read as a
  single static image. Removed; rotation 3.5s; dot indicators added so it reads as a slideshow
  even before it moves.
- **Verify with computed styles, not source.** Animations were confirmed by reading
  `getComputedStyle().animationName` out of headless Chrome, and rotation by screenshotting at
  1.5s / 5.2s / 8.7s / 12.2s and confirming four different slides.

---

## 2026-07-19 (later) — Studio migrated from Cowork to Claude Code

Fahad consolidated all website work into `~/Desktop/Website Development/` so nothing
lives in Cowork anymore. Changes affecting this project:

- The 5 team skills moved from this repo's `.claude/skills/` to user-level
  `~/.claude/skills/` (available in every session; single canonical copy).
- Studio-wide files now live one level up: `../CLAUDE.md` (umbrella conventions),
  `../team/agent-team-charter.md` (reconstructed), `../team/website-archive.md`
  (master index of all sites). This file remains the AZ Printing detail log.
- Sister project added: `../meherban-law/` (Pakistani law firm site, paused
  mid-design, migrated from Cowork with drafts + research + business card).
- Claude Code session memory (terminal session + Cowork learnings) merged into this
  project's memory store.

Still open from this morning: rewrite `docs/design-direction.md` (and the CLAUDE.md
design summary) to Direction F — both still describe the rejected Corner Press.

---

## 2026-07-19 (later still) — Direction F written up as the spec

`docs/design-direction.md` rewritten as the Direction F spec, extracted directly from the
accepted page (`AZ-Printing-Demo.html`; verified byte-identical CSS/JS to
`design-boards/direction-final.html` — the demo only adds embedded @font-face data URIs
and pins `color-scheme: light`). CLAUDE.md's current-state, design-summary, docs-list and
launch-gates sections updated to match; all Corner Press references removed from both.
`docs/design-directions-v3.md` kept as historical reference, marked as such in CLAUDE.md.

**Gate honoured:** per the "approve rendered pages, never written specs" lesson, the new
document is marked *awaiting Fahad's confirmation that the written spec matches the page
he accepted* before it becomes the build contract. Nothing has been built on it yet.

Note: mid-session the repo folder moved on disk —
`~/Desktop/Website Development/printing-site-draft/` is now
`~/Desktop/Website Development/Printing Press/printing-site-draft - claude/`. Path
references in the studio CLAUDE.md one level up may need updating to match.

---

## 2026-07-20 — Product photography added to the Direction F demo; demo now live

Fahad supplied 9 AI-generated representative product photos (via a ChatGPT handoff zip).
ChatGPT's accompanying replacement `index.html` was built on the REJECTED v1 PrimePress
homepage, so it was discarded on Fahad's instruction; only the photos were used.

Changes to `AZ-Printing-Demo.html` (approved path: photos into Direction F):
- Hero showcase: slides 2–5 swapped from hand-built art to photos (business cards,
  wedding cards, banners, flyers/brochures) per the design's own "swap for <img>"
  contract. Slide 1 keeps the CMYK press piece as the brand statement.
- Work grid: all four tiles now photos. "Event posters" tile became "Storefront signs"
  to match the supplied photo. Caption/copy micro-edits to stay truthful to imagery
  (wax seals not gold foil; van decals not sticker sheet).
- `images/` (9 JPGs) committed; `project-02-menu-boards` held in reserve for the
  services page rebuild. `noindex` meta added while placeholder details remain.
- QA: responsive 375/1440, slideshow cycling, no console errors, alt text everywhere.

**Live for sharing (e.g., with ChatGPT):**
https://mfahadishtiaq.github.io/printing-site-draft/AZ-Printing-Demo.html
(commit 363c3ac; root index.html is still the old rejected v1 — untouched.)

Tooling: GitHub CLI v2.96.0 installed to ~/bin/gh; Fahad authorized device-flow login,
credentials in macOS keychain — future pushes need no manual auth.

---

## 2026-07-21 — Homepage copy overhaul (copywriter role, page 1 of the page-by-page pass)

Fahad flagged all demo copy as informal / not punchy. Three-lane copy research run
(indie craft shops, volume leaders, Brampton/GTA locals) → `docs/copy-research-2026-07.md`;
voice rules + final homepage copy → `docs/copy-deck.md` (new canonical copy record).

Applied to `AZ-Printing-Demo.html` after Fahad's itemised feedback:
- Hero: Option B chosen — "Look like the business you're building." + two-sentence
  sub leading with the hand-checked-file promise. h1 clamp reduced 124→100px to fit
  the longer line (type roles/weights unchanged).
- Headers simplified per Fahad: "Recent projects." (was "Things we printed this
  month."), "Frequently asked questions." (was "Before you ask."). His rejected
  alternatives: "What left the shop this month", "What are you printing?", "You talk
  to the printer, not a call centre", "A family shop, not a print button".
- New headers by copywriter's call: doors = "Two kinds of jobs walk through our
  door."; why-us = "Four reasons to print with us."
- Doors copy now names occasions (shaadi, nikkah, mehndi) + sensory sample line;
  research shows community naming converts locally and the mid-market shaadi
  position is empty.
- Why-us 01–04 bodies approved as proposed; all em-dash constructions removed
  site-wide in copy; work-card lines rewritten with outcomes ("Ready in two days");
  card links task-shaped ("See lawn signs →"); form sub-line deleted and submit
  button now "Get my quote"; footer line tightened.
- FAQ answers remain PLACEHOLDER templates (rewritten to voice) pending
  questionnaire.

**KEY LESSON (Fahad, explicit): section headers must be simple and clear, never
clever.** Cleverness budget lives in the hero only. Recorded as voice rule 7 in the
copy deck.

Next: Fahad reviews rendered homepage; then remaining pages get the same treatment
during/before the 5-page Direction F rebuild. Demo changes not yet pushed to
GitHub Pages.

---

## 2026-07-22 — Homepage copy rebuilt from scratch, applied and verified

Fahad returned with the site having also been copy-edited by ChatGPT (pushed to
GitHub as commit `eac61fc`, which forked the repo from this local copy). His
verdict: ChatGPT's words were better than the July 21 draft but the work was
sloppy because it had no separated roles. This session rewrote the homepage
option-by-option with him choosing every line.

**Repo state:** local `AZ-Printing-Demo.html` now holds the new copy; `origin/main`
still holds ChatGPT's version. NOT yet pushed — the fork is unresolved on purpose,
pending Fahad's go-ahead.

**Real business details confirmed by Fahad and now live in the file:** phone
416-731-9229 (nav, hero CTA, footer, WhatsApp links), address 499 Ray Lawson Blvd
Unit 24, Brampton L6Y 4E6. The preview banner was rewritten accordingly — it
previously claimed every detail on the page was invented, which became false the
moment the real number landed.

**The 2001 correction.** "Twenty-five years" belongs to the OWNER (his earlier UPS
Store business), not to AZ Printing. Every experience claim was re-attached to him,
the stats tile "12 years printing in Brampton" (invented, and contradicting the
hero) became "25 · Years of printing experience", and a standing rule was added:
never name the former franchise on the site.

**Final homepage copy** — see `docs/copy-deck.md` for the full deck with rejected
alternatives. Headline: "The day you're planning. The name you're building."
Doors header: "What are you printing for?" Why-us header: "Why people keep coming
back." FAQ rebuilt as six customer-voice questions in journey order. Quote form:
"Tell us about your job and we'll prepare a free quote."

**Six new voice rules came out of Fahad's feedback and are now permanent:**
no unbackable guarantees; no claim repeated between hero and body; no negative
words (chasing, blame, problem) even when describing what we prevent; no trade
jargon (he asked what "stock" meant, which settled it); semi-professional register
site-wide, applied retroactively to sections approved before the rule existed; say
when a quote is free and count how often a channel is named.

**New skill created:** `../../.claude/skills/web-copy-workshop/SKILL.md` at the
studio level, encoding the round protocol, all 14 voice rules, the fact-marking
discipline and the apply-and-verify method. This is the answer to "the agents keep
forgetting my feedback".

**Verification:** headless Chrome at 1400px and 390px; lower sections photographed
from scratch copies with upper sections hidden, since anchor scrolling does not
work in headless mode and the preview pane resets to top. h1 clamp reduced
100px → 86px for the two-sentence headline.

**Still blocked on the owner (one phone call closes all of it):** starting prices,
turnaround in business days, whether design work is charged, whether a proof is
shown on every job, the delivery minimum, opening hours. Also unconfirmed: whether
everything is genuinely printed in-house (why-us 03 says "we print it here"), and
whether artwork is kept on file for repeat orders.

**Next:** Fahad is sending the site to Claude design to remove the AI-generated
feel from the visuals. Copy for services, rates, about and contact still to be
written; the About page should carry the owner's history as narrative.

---

## 2026-07-22 (later) — Studio hardened: production rules, copy-workshop, and the critic gate

Fahad's direction: fold everything learned today into the skills themselves, and
build a critic that pushes back before he ever sees the work.

**New:** `team/production-rules.md` — 37 cross-role rules covering how Fahad
decides, approval gates, fact discipline, language, the ambition floor, build
verification, and how to treat outside AI output. All six role skills now point at
it and carry their own role-specific additions. `web-copy-workshop` moved to user
level so it loads in client-repo sessions. `web-critic` created and wired into
`/build-site` as mandatory Phase 5.5.

**The critic was run against this repo's homepage immediately, and it earned its
place.** Verdict REWORK, six blocking findings, twelve worth fixing. The one that
mattered most had been live and public: the LocalBusiness JSON-LD still carried
the v1 fake phone number `905-555-0142` and postal code L6Y 4E3, contradicting the
real 416-731-9229 / L6Y 4E6 shown on the page. Google reads the schema first, and
NAP inconsistency undercuts the entire local-SEO goal. Two copy passes and a human
review had all missed it because nobody looks at the schema block.

It also caught the 2026-07-19 "never let content depend on JavaScript" lesson being
reintroduced in the new FAQ (all six answers invisible with script off), unmarked
placeholder stats, hover-only CTAs invisible on touch, fifteen fake stars rendering
in the "empty" reviews section, sub-AA placeholder text, and alt text claiming
finishes (deckle edges, wax seals, gold foil, screen printing) that no one has
confirmed this shop offers.

Sixteen mechanical fixes applied and pushed, plus FAQPage schema per the deck's
own build note. **Deliberately left open** for the design pass and the next copy
round: the ambition-floor failure (zero asymmetric sections against a required
two, and five equal-column grids, which is the exact fault v1 was rejected for),
all four work tiles linking to `#`, both doors resolving to the same quote form,
the stats band repeating the hero's twenty-five, and the critic's sharpest
observation — that from the doors section down, almost every line could be pasted
onto a competitor's site unchanged, because everything uncopyable sits in the top
two screenfuls.

**Lesson: the QA loop checks work against its own spec; the critic asks whether the
spec was worth building.** Those are different jobs and the studio needed both.

**Open question for Fahad:** the repo's `CLAUDE.md` says L6Y 4E3 and his own commit
says L6Y 4E6. One is wrong and only the uncle can settle it.
