# AZ Printing and Signs — Design Direction F: "Printed Properly"
*web-design-director · 2026-07-19 · Status: ACCEPTED by Fahad against a rendered page (2026-07-19). This document is the spec extracted from that page — **awaiting Fahad's confirmation before it becomes the build contract**.*

Canonical rendered deliverable: `AZ-Printing-Demo.html` (self-contained, fonts embedded, opens offline).
Repo board copy: `design-boards/direction-final.html` (identical CSS/JS, Google-Fonts-linked).
Preview link: https://claude.ai/code/artifact/62e622db-17ef-435f-aaa7-ad28c36ea86c

Replaces the REJECTED "Corner Press" direction (paper cream / terracotta / Fraunces + Inter,
quiet motion) and everything downstream of it. The warm-craft premise came from Cowork and was
never validated against Fahad's eye; three boards built inside it were all rejected. The
exploration that led here is preserved in `docs/design-directions-v3.md` (historical reference
only — do not build from it). Page structure and conversion mechanics (5 pages, call / WhatsApp
/ quote trio, "from $X" ranges) carry over unchanged.

## Concept

Bright, high-contrast, alive. White paper as the ground (the product itself), near-black ink,
one flame red-orange accent family, editorial serifs with real character, and motion everywhere
it earns its keep. The site should feel like a sharp modern print shop showing off what comes
off its press — not a design magazine, not a template. Every showpiece is a hand-built CSS/SVG
stand-in for one real photo, engineered so the photo swap changes nothing structural.

## Color system (usage rules are the contract, not just the hex)

| Token | Hex | Use | Contrast on white |
|---|---|---|---|
| `--flame` | `#FF4D1C` | Display type, graphics, underlines, big numerals ONLY | 3.3:1 — AA large text only, **never under 24px** |
| `--accent` | `#D92B0E` | Buttons, links, eyebrows, small accent text | 4.88:1 — AA normal text |
| `--accent-deep` | `#B01F04` | Hover / pressed fills | — |
| `--ink` | `#14100F` | Headings, body, dark panels | 18.9:1 |
| `--ink-soft` | `#5C5650` | Secondary text, captions | 7:1+ |
| `--surface` | `#FFFFFF` | Page base | — |
| `--surface-2` | `#F6F4F2` | Alternating `.tint` sections, artwork wells | — |
| `--border` | `#E7E3DF` | Hairlines, card borders | — |
| `--c / --m / --y` | `#00AEEF / #EC008C / #FFD400` | CMYK press-ink **motif only** (registration plates, never UI) | — |

- Flame vs accent is the load-bearing rule: flame is the personality (headline `em`, underline
  draws, stat numerals, sticker fills); accent is everything functional and small. Swapping them
  fails AA.
- WhatsApp button is its own pairing: `#25D366` background, `#062E14` text.
- Dark panels (`--ink` background): white text, flame for accents, `rgba(255,255,255,.72–.86)`
  for secondary. The quote block adds one radial flame glow (`rgba(255,77,28,.30)`), nothing else.
- Wedding-invite gold (`#B08829` / `#C9A227` family) exists only inside that one sample piece.

## Typography — three roles

| Role | Token | Face | Where |
|---|---|---|---|
| Display | `--display` | **Fraunces** (variable, opsz 9–144, wght 600–900 + italic) | h1–h3, logo, big numerals, FAQ questions, marquee |
| Body | `--body` | **Literata** (variable, opsz 7–72, wght 400–600 + italic) | Body copy, buttons, leads, captions |
| Interface | `--ui` | **Familjen Grotesk** (400–700) | Nav links, kickers, labels, uppercase micro-type in artwork |

- Base: Literata 17px / 1.65, antialiased.
- Headings: Fraunces 800 (900 for h1/logo/stats), line-height 1.02, letter-spacing −.03em
  (−.045em at h1 size), `font-variation-settings:'SOFT' 0,'WONK' 1` — the wonk axis ON is part
  of the look. Italic `em` inside h1 takes `--flame`.
- Scale is clamp-based, not a fixed ramp: h1 `clamp(46px, 9vw, 124px)` · `.h2`
  `clamp(32px, 5.6vw, 64px)` · FAQ q `clamp(19px, 2.4vw, 24px)` · lead 19px · body 17px ·
  UI/eyebrow 12–13px.
- Eyebrows: 12px / 600 / uppercase / `.2em` tracking / `--accent`. Nav links: `--ui` 13px / 700 /
  uppercase / `.13em`.
- **Font delivery:** boards and dev use the Google Fonts `<link>` (per the standing decision).
  Any *published/offline* deliverable embeds the fonts as `@font-face` data URIs — published
  pages block font CDNs and the typography silently falls back. Latin subset, used weights only
  (~285 KB). The demo also pins `color-scheme: light` on `:root` in all themes: the premise is
  bright white paper, so the page owns its ground instead of following the viewer's theme.

## Layout

- Container `--maxw: 1180px`, `padding-inline: 24px`. Sections `padding-block: clamp(72px, 10vw, 132px)`,
  alternating white / `--surface-2` (`.tint`).
- Radii by scale: pills `999px` (buttons, caps, dots, WhatsApp) · cards/doors/showcase pieces
  `18px` · hero showcase `22px` · quote panel `26px` · form fields `10px` · printed artwork
  `3–12px` (small radii = paper, big radii = UI; keep the distinction).
- Breakpoints are component-driven, not a fixed set: grids go multi-column at 640 (stats/form/footer),
  700/1100 (work tiles 2-up → 4-up), 760 (why 2-up), 820 (reviews 3-up), 900 (doors 2-up, quote
  padding), 960 (desktop nav).
- Homepage section order (the accepted page): hazard flag → progress bar → nav → hero + showcase
  carousel → marquee → work tiles (4) → doors fork (event / business) → why-us (4) → stats (3) →
  reviews (empty on purpose) → FAQ accordion → quote form on ink → footer → floating WhatsApp.
  The doors are the dual-audience fork — by job, never by audience page.

## Components

- **Buttons:** pill, min-height 56px, Literata 16/600, 16×30 padding. Primary: `--accent` with an
  `--accent-deep` panel that wipes up on hover (`translateY(101%)→0`). Ghost: `--border` outline,
  darkens to ink. On ink panels the primary flips to flame bg + `#2A0A00` text with a white wipe.
  Magnetic cursor-follow on fine pointers.
- **Nav:** fixed, `rgba(255,255,255,.92)` + `blur(14px)`, 72px, Fraunces-900 logo ("AZ" ink +
  "Printing" accent), border appears when stuck, hides scrolling down past 420px, returns on any
  scroll up. Links get a left-to-right accent underline draw on hover.
- **Cards (work tiles `.piece`):** `--surface-2`, 1px border, 18px radius, artwork well on a
  white→surface-2 gradient, hover = big soft shadow + 3D tilt + "page →" link reveal. Every tile
  links toward a future per-service page (SEO: "<service> printing Brampton").
- **Doors (`.door`):** white card, ink panel wipes up on hover, text flips white, arrow nudges.
- **Forms:** live on the ink quote panel; translucent white fields (`rgba(255,255,255,.08)`,
  1px `rgba(255,255,255,.2)` border, 10px radius, min-height 56px), visible labels always,
  white focus border. ≤5 fields + optional textarea; Formspree placeholder action.
- **Physical-object treatment (`.pc`):** every printed sample gets two shadows (tight contact +
  wide ambient) plus a diagonal paper-sheen gradient overlay — this is what makes CSS pieces read
  as objects on a surface, and it stays when photos replace them (on the frame, not the photo).
- **Focus:** 3px `--accent` outline, 3px offset, on every interactive element.

## Motion (the signature of this direction — "max motion", never gratuitous)

Easings: `--ease: cubic-bezier(.16,.84,.44,1)` (general) · `--out: cubic-bezier(.22,1,.36,1)` (reveals).

Choreography inventory, all of which shipped in the accepted page:
1. **Hero words** rise from masked lines (`translateY(112%)→0`, .9s, 70ms stagger) on load.
2. **Reveals:** `.rv` fade-up 28px / .8s, `.wipe` clip-path left-to-right / 1s, both staggered
   80–90ms via `--i`; `.uline` draws a 5px flame underline under every h2 (.9s).
3. **Scroll progress bar:** 3px fixed top, flame→accent gradient.
4. **Hero showcase:** 5 slides crossfade (1s opacity + 1.1s scale 1.04→1) every **3.5s** with
   clickable dot indicators. **NO hover-pause** — the cursor rests on the hero, so pausing reads
   as a frozen static image (learned the hard way). Pauses only when tab hidden or scrolled
   offscreen. Slide 1 runs the CMYK plate-registration animation.
5. **Marquee:** service names on an ink band, 34s linear loop, pauses on hover.
6. **Hover physics:** door ink-wipe, button fill-wipe, card tilt (`rotateX/Y` ≈ 4.5–5.5°,
   `pointer:fine` only), magnetic buttons.
7. **Ambient loops:** the artwork breathes — sway (lawn sign), float (tee/poster/cards/flyer),
   pop (stickers, staggered), pulse (poster disc), gold shine (invite names), drift (banner
   texture). 2.8–7s periods so nothing syncs.
8. **Stats count up** (1400ms, cubic ease-out, fires at 60% visibility).
9. **Parallax:** press sheet ±26px, tile artwork ±30px, rAF-throttled.

Non-negotiable engineering rules (each one is a paid-for lesson):
- **Progressive enhancement:** hidden/animated initial states apply only under a `.js` class set
  by inline script. No-JS gets everything visible; the showcase degrades to a scroll-snap strip.
- **Failsafe reveal:** a 1.2s timer (plus one on `load`) adds `.in` to everything regardless of
  IntersectionObserver behaviour. Content visibility must never depend on an observer firing.
- **`prefers-reduced-motion`:** kills all animation/transitions, shows all content, sets final
  stat values, disables the carousel. The FAQ accordion still works.
- Animate only `transform`/`opacity`/`clip-path`; throttle scroll work through rAF.

## Imagery & placeholders

- Nine hand-built CSS/SVG sample pieces (press sheet, business cards, wedding invite, vinyl
  banner, flyer, lawn sign, tee, sticker sheet, event poster) stand in for the photo shoot. No
  image-generation tooling exists in this stack and Canva can't export at usable sizes — these
  are the imagery strategy until real photos arrive, and they're sharp at any size for free.
- Each showcase slide / tile artwork is one future `<img>` swap; the fade/tilt/shadow machinery
  does not change.
- NO stock photos of people, ever. Reviews section ships built and empty — nothing fake goes
  there, ever.
- Placeholder marking is one quiet system: the yellow/black hazard flag at the top of the page
  plus literal `PLACEHOLDER` text in copy. All names, numbers, prices and sample businesses in
  the demo are invented.

## Accessibility receipts

Computed before approval, not during build: ink 18.9:1 · accent on white 4.88:1 (AA normal) ·
flame 3.3:1 (AA large only, enforced by the ≥24px rule) · WhatsApp `#062E14` on `#25D366` passes.
56px button / 54px WhatsApp touch targets. Carousel has `aria-roledescription` + per-slide labels;
FAQ buttons manage `aria-expanded`; focus-visible everywhere; reduced-motion fully honoured.

## Token spec (contract with web-frontend-dev — copy verbatim)

```css
:root{
  --flame:#FF4D1C;        /* display + graphics ONLY, never small text */
  --accent:#D92B0E;       /* buttons, links, small accent text — AA */
  --accent-deep:#B01F04;  /* hover / pressed */
  --ink:#14100F;          /* 18.9:1 on white */
  --ink-soft:#5C5650;
  --surface:#fff;
  --surface-2:#F6F4F2;
  --border:#E7E3DF;
  --c:#00AEEF; --m:#EC008C; --y:#FFD400;   /* press inks — motif only */

  /* three roles: display = character · body = reading · ui = interface */
  --display:'Fraunces',Georgia,serif;
  --body:'Literata',Georgia,serif;
  --ui:'Familjen Grotesk',system-ui,sans-serif;

  --ease:cubic-bezier(.16,.84,.44,1);
  --out:cubic-bezier(.22,1,.36,1);
  --maxw:1180px;
}
```

Google Fonts request (boards/dev):
`Fraunces:ital,opsz,wght@0,9..144,600..900;1,9..144,600..900` ·
`Literata:ital,opsz,wght@0,7..72,400..600;1,7..72,400..500` ·
`Familjen+Grotesk:wght@400;500;600;700`

## Open items

1. **Fahad confirms this written spec matches the page he accepted** → it becomes the build contract.
2. Uncle has never seen any direction — the preview link exists to close that gate (his veto is
   recognisability; Fahad's is quality).
3. Questionnaire answers (Q12/Q15/Q16/Q20/Q21/Q24/Q25) — FAQ copy and price anchors are placeholders.
4. Photo shoot (≥6 job photos + 1 storefront gates launch, not the build). Storefront sign photo
   may still adjust the accent family — check before final build.
5. Rebuild of the five pages on these tokens has not started; the repo's current pages are still
   rejected v1.
