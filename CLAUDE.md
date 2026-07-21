# AZ Printing and Signs — Website Project

Website for AZ Printing and Signs, a family-run print shop at 499 Ray Lawson Blvd, Unit 24,
Brampton, ON L6Y 4E6 (verified against Google, 2026-07-22). Phone 416-731-9229 (REAL). Owner: Fahad's uncle (65, recently bought the business). Goal: local
leads (calls / WhatsApp / quote form) + local SEO ("printing Brampton"). Phase 2 later:
online ordering/payments.

Fahad is learning web development — explain the *why* behind key decisions in 1–2 sentences
as you work. Push back when a request would hurt the result.

## CRITICAL: current state (July 2026)

- The 5 HTML pages in this repo are the **v1 draft whose visual design was REJECTED**.
  They are kept as a *structural/mechanics reference only*.
- The accepted direction is **Direction F** (bright white, flame accent, heavy motion) —
  accepted by Fahad on 2026-07-19 against the rendered page `AZ-Printing-Demo.html`
  (canonical; board copy at `design-boards/direction-final.html`). Full spec and CSS
  tokens in `docs/design-direction.md`. The earlier "Corner Press" warm-craft direction
  and all three v3 boards are REJECTED (`docs/design-directions-v3.md` is historical
  reference only). The next job is rebuilding the 5 pages on Direction F.
- ALL business details in the pages are FAKE placeholders ("PrimePress Printing", fake
  phone/address/prices/reviews). Never let placeholder content ship as real. Real details
  arrive via the client questionnaire (`docs/client-questions.md`).

## Design direction (summary — the spec in docs/ is the contract)

- Direction F: bright white base `#FFFFFF` / `#F6F4F2`, near-black ink `#14100F`, flame
  `#FF4D1C` for display/graphics ONLY (never text under 24px), red `#D92B0E` for buttons,
  links and small accent text (AA). CMYK cyan/magenta/yellow as a press-ink motif only.
- Three type roles: Fraunces (display, wght 800–900, WONK on), Literata (body, 17px/1.65),
  Familjen Grotesk (interface/labels, uppercase micro-type).
- Heavy motion is the signature: staggered reveals, hero word rise, 3.5s showcase
  crossfade (no hover-pause), marquee, hover wipes/tilt, ambient artwork loops, count-ups.
  Progressive enhancement (`.js` gate + timed failsafe reveal) and full
  `prefers-reduced-motion` support are non-negotiable.
- Imagery: nine hand-built CSS/SVG sample pieces stand in for photos, each swappable for
  a real `<img>` later. NEVER stock photos of people. Reviews section stays empty until
  real Google reviews exist.
- Full tokens and usage rules: copy the `:root` block from `docs/design-direction.md`
  verbatim.

## Structure & conventions

- 5 pages: `index.html`, `services.html`, `rates.html`, `about.html`, `contact.html`.
- Each page is fully self-contained (CSS inlined in `<style>`) — zero dependencies except
  Google Fonts. Keep it that way for GitHub Pages.
- Conversion trio on EVERY page: click-to-call link, floating WhatsApp button, short quote
  form (Formspree — action URL is a placeholder until the account exists; form ≤ 5 fields).
- Rates page shows "from $X" price RANGES, never exact prices, never a price table on the
  homepage.
- Semantic HTML5, mobile-first responsive (breakpoints 640 / 900 / 1200, content max 1120px).
- Local SEO: city-name title tags ("… | Printing in Brampton"), LocalBusiness JSON-LD schema
  on every page, per-service landing pages come after launch (see `docs/roadmap.md`).

## Build, preview, deploy

- No build step — edit HTML directly.
- Preview locally: `python3 -m http.server 8000` → http://localhost:8000
- Deploy: push to `main` → GitHub Pages publishes automatically at
  https://mfahadishtiaq.github.io/printing-site-draft/
- Commit messages: short imperative ("Rebuild index on Direction F tokens").

## Team workflow (skills installed at user level: ~/.claude/skills/)

Five roles from Fahad's website studio, ported from Cowork (2026-07-19: moved from this
repo's .claude/skills to ~/.claude/skills so they work across all client projects).
Studio-wide files live one level up in `../team/` — see `../CLAUDE.md` (the umbrella
"Website Development" folder is the studio home). Work flows:
consultant (strategy/brief) → ux-strategist (pages/flows) → design-director (look/tokens) →
frontend-dev (build/QA); archivist maintains memory. Approval gates are real: propose,
wait for Fahad's explicit "approved", then build.

- REMAP for Claude Code: the skills were written for Cowork and reference a "Claude
  Project" / Projects tool that does not exist here. Remap paths as:
  `team/agent-team-charter.md` and `team/website-archive.md` → `../team/` (studio level);
  `printing-business/*.md` → this repo's `docs/` folder
  (this project's detailed decision log stays at `docs/team-archive.md`).
- Building/QA/deploy → follow `web-frontend-dev` skill.
- Visual changes must match `docs/design-direction.md`; disagreements go to the
  design-director role, not silent improvisation.
- Log decisions and status changes in `docs/team-archive.md` (project memory — update it
  at the end of every working session; this file is the CLAUDE.md-adjacent long-term memory).

## Key project docs

- `docs/design-direction.md` — Direction F spec + CSS tokens (build contract once Fahad
  confirms the written spec matches the accepted page)
- `docs/design-directions-v3.md` — rejected v3 exploration (historical reference only)
- `docs/roadmap.md` — 7-phase plan (GBP-first strategy)
- `docs/research-findings.md` — market research: global benchmarks + Brampton competitors
- `docs/client-questions.md` — questionnaire awaiting uncle's answers
- `docs/team-archive.md` — decision log / memory (keep updated)

## Open gates before launch

1. Uncle approves Direction F (he has not seen any direction yet — use the rendered
   demo / preview link, judged on a phone).
2. Questionnaire Parts 1–3 answered → swap ALL placeholders for real details.
3. Storefront sign photo may adjust the flame/red accent family — check before final build.
4. Real domain purchase + Formspree account + Google Business Profile (see roadmap).
