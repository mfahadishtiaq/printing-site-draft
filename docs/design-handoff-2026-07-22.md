# AZ Printing — Design Handoff

Written 2026-07-22. Everything a design session needs to take this page from
"well-written but AI-shaped" to something that looks like a studio made it.
Give this file plus the live link. Nothing else is required reading.

**Live page:** https://mfahadishtiaq.github.io/printing-site-draft/AZ-Printing-Demo.html
**Repo:** https://github.com/mfahadishtiaq/printing-site-draft (`AZ-Printing-Demo.html`
is canonical; the root `index.html` is a rejected v1 and must be ignored)

---

## 1. The business

Family-run print and sign shop at 499 Ray Lawson Blvd, Unit 24, Brampton, ON
L6Y 4E6. Phone 416-731-9229. Both verified real (postal code checked against
Google, 2026-07-22) and already live in the page and its LocalBusiness schema. Owner is Fahad's uncle, 65, who ran a print and
shipping counter for about 25 years before buying this shop. Two customer types
on one page: South Asian families ordering wedding and shaadi cards, and small
businesses ordering cards, signs, apparel and repeat jobs.

Goal: local phone calls, WhatsApp messages and quote-form submissions, plus
ranking for "printing Brampton". Not e-commerce, not a brochure for investors.

## 2. What is already decided and must not be re-litigated

- **Direction F is approved** (accepted 2026-07-19 against a rendered page, not a
  written spec). Bright white base, near-black ink, flame orange `#FF4D1C` for
  display only, red `#D92B0E` for buttons and links, CMYK as a press-ink motif.
  Fonts: Fraunces (display), Literata (body), Familjen Grotesk (labels).
  Full spec and tokens: `docs/design-direction.md`.
- **Heavy motion is the signature, not decoration.** Staggered reveals, hero word
  rise, 3.5s showcase crossfade, marquee, hover wipes, count-ups. Progressive
  enhancement plus `prefers-reduced-motion` are non-negotiable. Do not flatten
  the motion in the name of restraint.
- **All copy is final** and was chosen line by line by Fahad. See
  `docs/copy-deck.md`. Design may re-*arrange* copy; it may not re-*write* it.
  If a layout needs different words, raise it, do not silently change them.
- **The reviews section is deliberately empty** until real Google reviews exist.
  Nothing fake goes there, ever.
- Self-contained single HTML file, inline CSS, no build step, deploys to GitHub
  Pages.

## 3. What is deliberate versus unfinished

| On the page | Status |
| --- | --- |
| Yellow striped preview banner | Temporary scaffolding, will be deleted |
| Empty reviews cards | Deliberate, waiting on real Google reviews |
| `[$X]`, `[X business days]`, `[hours]` in the FAQ | Waiting on the owner |
| Stats band: 24-hour rush, 1200 jobs | Invented numbers, will be replaced or cut |
| "25 years of printing experience" | REAL, belongs to the owner not the shop |
| Phone number and address | REAL |
| Four "recent projects" | Invented sample jobs, will become real work |

## 4. Why it currently reads as AI-made

An honest diagnosis, most damaging first. The copy is no longer the problem;
these are.

1. **The photographs are AI-generated.** This is the single biggest tell and no
   amount of layout work fixes it. Real photos of this shop, this owner, and jobs
   that actually left the counter would do more than every other item on this
   list combined. The plan already exists in `team/website-archive.md` as gate G3:
   eight photos, one afternoon, zero dollars.
2. **Everything lives in one centred 1120px column.** Section after section of
   the same width, same rhythm, same centre line. Real editorial design breaks
   the column: full-bleed images, offset text, an element that runs off the edge.
3. **Uniform rounded cards.** The work grid, the doors and the review cards are
   all the same soft-cornered rectangle with the same border and the same radius.
   Four equal tiles in a row is the most template-coded pattern there is.
4. **No texture and no real material.** This is a print shop. Paper grain, ink
   density, the edge of a card, the weave of a shirt, a cutting mat, registration
   marks on a real proof. The page is currently smoother than anything the
   business actually sells.
5. **Nothing is at true scale.** Print is physical and every product has a real
   ratio (business card 3.5:2, invitation 5:7, banner 24:9, poster 1:1.414).
   Showing products at their true trim size is both more honest and impossible
   for a generic template to imitate.
6. **The stats band is three big orange numbers, centred.** The most generic
   module on the internet.

An earlier session already wrote a grep-testable "ambition floor" for exactly
this, and it still applies: no section with more than four equal-weight items,
at least two asymmetric sections above 900px, one element at 70vw or wider, at
least three structurally distinct section types, homepage 7 to 9 screenfuls at
390px.

### Measured, not guessed (studio critic pass, 2026-07-22)

Computed at 1400px, so these are facts about the current build rather than
impressions:

- `.doors` = `556px 556px`, `.why` = `538px 538px`, `.show` =
  `268px 268px 268px 268px`, `.stats` and `.revs` = `repeat(3,1fr)`.
  **Zero asymmetric sections against a required minimum of two.**
- Six sections open with the identical `eyebrow` + `h2.uline` skeleton.
- `.door`, `.piece` and `.rev` share `border-radius:18px` + `1px solid
  var(--border)`: the same card, three sections running.
- The v1 design was rejected in this repo for "five `repeat(N,1fr)` grids under
  identical centred headings". This page has five grids and six identical heads.
  The structural fault that killed v1 is present in the approved direction.

### Non-visual findings the design pass should know about

These belong to structure and journey rather than to colour and type, and a
redesign is the natural moment to fix them:

- All four work tiles link to `href="#"`, so every one of them scrolls the
  customer back to the top of the page.
- Both audience doors resolve to the same `#quote` form, so the dual-audience
  fork the homepage architecture rests on does not actually fork. The event door
  even says "Visit the shop to see the materials" while its arrow fires at a
  form.
- The stats band restates the hero's "twenty-five years" as the largest number
  on the page, which breaks the studio rule that nothing claimed in the hero is
  repeated below it.
- From the doors section down, almost every line could be pasted onto a
  competitor's site unchanged. Everything uncopyable about this business (the
  languages, Ray Lawson Blvd, the owner at the counter) sits in the top two
  screenfuls. If the redesign can pull one concrete local detail further down
  the page, that is worth more than any single visual move.

## 5. What a good design pass would deliver

- The same content, restructured so no two sections share a skeleton.
- At least one full-bleed or edge-breaking moment.
- Products shown at true trim ratios rather than uniform tiles.
- A materials layer: paper, ink, texture, the physical evidence of a press.
- The stats band either rebuilt or removed.
- Motion preserved and, where possible, made to do work the layout cannot.
- Judged at 360px on a phone first, desktop second. The owner will look at it on
  a phone and so will most customers.

## 6. What must survive the redesign

- Click-to-call, floating WhatsApp button and the quote form on every page.
- Strong text contrast. Light grey body text is unacceptable.
- Never stock photography of people.
- No em-dashes in site copy, no trade jargon, no invented facts.
- `noindex` stays until the placeholders are gone.

## 7. Open facts, still owed by the owner

Starting prices for common jobs, turnaround in business days, whether design work
is charged, whether a proof is shown on every job, delivery minimum, opening
hours. Plus two claims the copy currently makes: that everything is printed
in-house, and that artwork is kept on file for repeat orders.
