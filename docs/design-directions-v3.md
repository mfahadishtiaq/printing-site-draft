# Direction v3 — Final Recommendation

**web-consultant, chairing · 2026-07-19 · For Fahad. Proposal until you say "approved".**
Companion documents: the debate resolution (§0–§4, to be saved as `docs/direction-resolution.md`)
and the three rendered boards in `design-boards/`.

---

## 1. One-paragraph answer

**Build Direction A — The Chapter Rail — as the production architecture, absorb Direction C's
specification discipline into it, and keep Direction B's dark movement as a single contained
section on the homepage only, gated on real content.** A is the recommendation for three reasons,
in order of weight. First, it is the only board that both halves of the veto liked: the design
director scored it 7 and said explicitly *"do not kill this direction — the diagnosis was right,
only the placement was wrong"*, and your uncle scored it 7 and said *"bring it back and I will
most likely approve it"* — no other board got a conditional yes from him. Second, its two
structural moves solve the actual diagnosed disease: v1 was five `repeat(N,1fr)` grids in
identical padding, and the true-trim specimen system makes that grid **physically impossible**
to reform, because a 5:7 wedding card, a 24:9 banner and a 3.5:2 business card cannot line up
into equal boxes. That is discipline enforced by geometry rather than by good intentions — the
thing that failed twice. Third, A's failure mode is cheap: its faults are a mis-assigned grid,
a hero with nothing printed in it, and copy written in design-magazine English. Every one of
those is a build-time fix. C's fault is that its layout is structurally load-bearing on
questionnaire answers we do not have (Q12/Q15/Q16/Q20/Q21) and collapses into empty ruled boxes
without them; B's fault is that your uncle voted no on it as a whole site and the price-anxiety
loss it risks is silent and unmeasurable. **A is not the most exciting board. It is the one that
can be got to a 9 with edits rather than with luck.**

---

## 2. The contract — what "premium" means for AZ Printing

Restated from the resolution §4 and binding on the build:

> Premium here means a page a Brampton restaurant owner would believe was made by a shop that
> does careful work, and that a bride pricing 100 wedding cards would walk into without
> hesitating. It is built from **craft, not expense signals**: paper cream and warm ink at
> 14.5:1, one terracotta accent used no more than three times per screen, Fraunces set with real
> optical sizing rather than at a default weight, generous whitespace, and at least three
> structurally *different* section layouts on the homepage — never the same centred heading over
> the same row of equal boxes. Its authority comes from **specificity, not adjectives**: every
> service carries a number — quantity, turnaround, or "from $X" — because that is how someone
> who does the work daily talks, and because no competitor in Brampton does it
> (`research-findings.md` L19). Its proof is **one job shown large**, and that job is a real
> photograph or a real typeset sample at true trim geometry with a factual caption — never a
> gradient rectangle. It is authored **at 360px first**.

**Falsifiable tests.** No section with more than four equal-weight items · ≥2 asymmetric sections
at ≥900px · one element ≥70vw · homepage 7–9 screenfuls at 390px and ≤600 words of prose · zero
decorative boxes standing in for images · Lighthouse mobile ≥95 performance, 100 accessibility on
all five pages · **the uncle recognises his own shop** · **nothing on the page is invented**.

**One clause added by this session, and it is the most important line in the document:**
premium is also a **voice** test. If a sentence is one your uncle would not say to a customer
across his own counter, it is not premium — it is costing him the flyer half of his business.
See §4.

---

## 3. The three directions, even-handed

### Direction A — The Chapter Rail (average 6.7) · `design-boards/direction-a.html`
**Argues:** premium is *editorial authority* — the site reads like a well-made printed book
about the shop. A persistent 96px chapter rail with section numerals replaces the stack of equal
bands; every job renders at its true product aspect-ratio.
**Scores:** director 7 · uncle 7 · ux 6.
**Strongest quality:** the material system. Zero border-radius except 2px on buttons, zero
box-shadow, depth expressed only as a 2px offset ink rule with real hover physics. The director's
words: *"a director's system, not decoration… no AI-website tell anywhere in the file."* The
uncle independently praised the same thing — different-shaped samples *"looks like a print shop
and not a template"* — and the two-door fork was the first thing in this project he said
described how his shop actually works.
**Weakest quality:** the true-trim grid does not currently resolve. The tallest ratio (5:7
wedding card) was given the widest column, rendering ~840px tall around ~150px of artwork —
roughly 350px of blank paper above and below the largest element on the homepage. Artwork is
sized in `vw` instead of container units, so it cannot scale with the trim it is named after.
The hero shows a print shop printing nothing.
**Wins:** the wedding/family walk-in, and the desktop visitor who wants to feel the shop is
careful. **Loses:** nobody outright — but at 360px it degrades to "tidy", and the ux-strategist
found ~216px of chrome before the first word and no trust signal above the fold.

### Direction C — The Job Ticket (average 6.3) · `design-boards/direction-c.html`
**Argues:** premium is *precision* — the register of the print trade's own job docket. Every
item is a specification, not a description; kraft and trace-paper palette; hierarchy carried
entirely by rule weight.
**Scores:** director 7 · uncle 6 · ux 6.
**Strongest quality:** it is the only board where the **layout itself** attacks the universal
Brampton weakness (`research L19`: no pricing or spec transparency anywhere). "16pt matte
laminate · next business day · from $X · trimmed on the guillotine here, not shipped in from a
broker" — your uncle called that last line his actual competitive advantage. The registration-mark
sheet frame is a signature legible in a 200px thumbnail. The director called it *"visually the
most confident work I have seen on this project."*
**Weakest quality:** it reads as a **form, not a page**. Below the hero there is ~900px of
continuous 14/16px spec text at identical vertical rhythm and identical 64px section padding —
uniform density, which is the specific failure mode of system-designed work. Worse, "from $00",
the number that is its entire argument, renders at 22px, *smaller than the heading above it*.
And the wedding/shaadi row is drawn identically to coroplast.
**Wins:** the restaurant owner reordering menus; the B2B repeat buyer. **Loses:** the bride.
Your uncle: *"a mother planning her daughter's wedding is buying a feeling, and this layout
gives her a materials list."* `research L22` calls that a big local category.
**Gate:** do not commit to C before Q12, Q15, Q16, Q20, Q21 return. Its own author said so.

### Direction B — The Night Press (average 5.3) · `design-boards/direction-b.html`
**Argues:** premium is *gravitas* — white ink and foil on black uncoated stock is a real upsold
print product, so a dark site is a product demonstration, not decoration. The luxury pole,
argued honestly rather than as a strawman.
**Scores:** director 6 · uncle 4 · ux 6.
**Strongest quality:** the typography. Killing the 1120px container so the h1 runs to the page
edge, a ~7.8x scale contrast, correct use of Bodoni Moda's optical-size axis, and the Act III
specimen at 1.62:1 with a double keyline — the one genuinely print-native object across all
three boards. The ux-strategist also rated its "from $45" ledger the single best conversion
decision on any board, because it defuses the price anxiety the direction itself risks.
**Weakest quality:** five consecutive `min-height:85vh` acts, all `justify-content:center` —
the director calls this *"the most template-coded pattern in existence… precisely what a generic
AI website does."* At 390px the headline hits its 42px floor, so the entire visual argument
exists only above ~900px: premium on a 1440px desktop, template on a phone. And it owns a
disqualifying dependency — without six real photographs it collapses into large dark rectangles,
which is the exact object rejected in v1. We own zero photographs.
**Wins:** the shaadi-card customer with a real budget. **Loses:** the pizza place two doors down
that wants 500 flyers by Thursday — and loses him *silently*.

---

## 4. The conflict I have to flag loudly

**Two disagreements, and the second one is the one that will kill this project if we ignore it.**

### 4a. Direction B: the director's admiration vs. the owner's veto
The design director scored B a 6 and called it *"the most intellectually honest of the three
boards… I would sign the rule-weight system"*, and said the fixes take it to a defensible 8 on
desktop. Your uncle scored it **4** and used the words *"I am voting no on this as the whole
site."* His reasoning is not aesthetic, it is commercial: *"my whole business is that no job is
too small and my price is fair. This page says the opposite before anyone reads a word."*
He also caught something none of the four roles did — **his sign says PRINTING AND SIGNS, and
there is not one sign anywhere on that page.** One wedding card is the whole show.

**The director does not contest this and neither do I.** He wrote: *"the price-anxiety risk is a
business objection I do not have authority to overrule but will not pretend the visuals mitigate
— a black-and-copper page reads expensive no matter how well it is set."* B is out as the site.
Your uncle's own proposal is the right disposition: **save that exact treatment for a future
wedding/shaadi-card service page** (roadmap Phase 4), where the audience arrives already
committed and gravitas is an asset instead of a filter.

### 4b. The disagreement nobody scored: **voice**
This is the real finding of the session and I want it in front of you plainly.

The design director assessed A at 7 on typography, grid, restraint and hierarchy — his remit.
Your uncle assessed the same file and his single largest objection was not visual at all:

> *"It does not sound like me. 'Numbers first. They are the only claim that survives a second
> reading.' I have never said a sentence like that in my life. My customer is a restaurant owner
> who wants 1,000 flyers by Friday — he reads that and thinks this is some fancy design studio
> downtown and he cannot afford me. The word 'specimen' is on the customer's page. Nobody in
> Brampton walks in asking for a specimen."*

**Nothing in our scoring rubric was measuring that**, which means a board could have passed every
craft test we set and still triggered exactly the price-anxiety failure we rejected Direction B
for. The luxury risk does not only live in a dark palette. **It lives in the prose**, and A is
currently carrying it. This is how v1 died — approved on internal criteria, rejected by the
person whose shop it is. Voice is now a gate condition, not a copy-polish step.

**Practical consequence:** the words on the production build get written in shop English and
read back to your uncle *out loud* before the build is signed off. "Specimen" → "samples".
"Numbers first…" → "Why people keep coming back." "Every job leaves the shop a different size" →
"What we print." And three plain lines go high on the page that no board currently has:
**same-day / next-day on most jobs · we speak English, Punjabi, Hindi and Urdu · free parking
right outside Unit 24.** In Brampton those three lines are worth more than any type ramp.

---

## 5. Fixes to apply to Direction A before it is the production direction

**Tier 1 — blocking. A is not the direction until these are done.**

1. **Rewrite every customer-facing sentence in shop English.** Delete "specimen" from the site.
   No sentence survives that your uncle would not say across the counter. Read the homepage to
   him aloud; anything he stumbles on gets rewritten.
2. **Fix the true-trim grid.** Tallest ratios into the *narrowest* columns (5:7 wedding, 8.5:11
   letterhead → 4fr; 24:9 banner full-width in its own row; 3.5:2 card and 4:3 lawn sign → 7fr).
   Remove the `grid-row` spans on children 1 and 3 that inflate the rows and leave holes.
3. **Artwork scales with the tile, not the viewport.** `container-type:inline-size` on
   `.trim__paper`; convert every `.art-*` size from `vw` to `cqw`.
4. **Put one true-trim sample above the fold.** The fold currently shows a print shop printing
   nothing, backed by a bordered text box — the most brochure-like element on the page.
5. **Signs must be visible.** Your uncle's catch: at least one lawn sign, one vinyl banner and
   one storefront/vehicle piece shown at real size. Half the revenue is currently invisible.
6. **Add the three welcome lines** (same-day, languages, free parking at Unit 24) directly under
   the h1, replacing the 13px disclaimer that currently wraps below both buttons.
7. **WhatsApp button goes WhatsApp green (#25D366).** Both the uncle and the ux-strategist
   flagged this independently on all three boards. Recognition is that button's entire
   affordance; a terracotta bubble is an unlabelled chip. This is the one place a palette rule
   costs measurable leads, and the design director's accent discipline yields here.
8. **Fix the mobile click-to-call at source** — delete `.nav-cta .btn-outline` from the ≤640 hide
   rule at `index.html:411`. Broken this entire time; worth more than any styling decision here.
9. **Delete every fabricated number and joke placeholder.** No "4.9", no "100+ jobs", no three
   64px zeros as the loudest type on the page, no "Aisha & Rehan, Twelfth of Never". Render
   unknowns as bracketed marks at reduced size, never as display type.
10. **Add navigation for 640–899px.** That band currently has a wordmark and a call button only.

**Tier 2 — required before launch, not before approval.**

11. Import C's specification lines into A's captions — "500 business cards · next day · 16pt
    matte · from $X" on every item. This is the single best idea in the losing boards and it is
    free to transplant. Spec values must be **real or tagged unverified**; C's board asserted
    invented stocks and turnarounds as fact, which is a `CLAUDE.md` violation.
12. Import C's **price-as-display-type**: the "from $" numeral becomes a visual crescendo, not
    22px body text. But **not as a four-row band on the homepage** — that is the price table
    `CLAUDE.md` forbids. Numbers live in the job captions; the band lives on `rates.html`.
13. Vary the chapter rhythm — `.chapter__body` is 96px on all seven sections, which quietly
    reproduces the equal-band stack the direction claims to replace. Uneven density is what
    separates premium from systematic.
14. `h1` to `clamp(38px, 6.4vw, 92px)` — the rail removes 144px from the measure and 9vw
    over-sets the hero at 900–1080px.
15. Cut mobile rail and chapter padding 64px → 32/40px; move the two-door fork above the CTA
    buttons at <900px so the audience split exists on the device most GBP traffic arrives on.
16. Fork's B2B branch must honour its promise: a "repeat order / shop account" option in the
    form's job select, and an empty first option so wedding enquiries stop silently defaulting
    to "Business cards".
17. Add a **Get directions** maps deep-link beside the address, and put hours near the top. For a
    walk-in shop, "are you open now" is the most common phone call.
18. Move the technical token/contrast appendix off the customer page. Your uncle scrolled past
    his own footer into it and thought the site was broken.
19. Real WhatsApp `wa.me` URL, ≥48px target, visible label at 360px,
    `env(safe-area-inset-bottom)`. Remove hardcoded `aria-current="page"`.
20. **One ink-dark movement, homepage only**, in Act-III position — it ships *only if* it holds a
    real photograph or a real sample with real service names and real from-ranges. If the photos
    have not landed, that section renders light and we lose nothing. Inside it, terracotta is
    3.04:1 and cannot be a link; use `--accent-on-ink #E8763A` (5.3:1).

**Colour rulings carried forward:** `--accent-deep #96391B` for inline links and focus text
(terracotta at 4.27:1 on `--paper-2` **fails AA** and an approved doc shipped that failure).
Marigold `#F2C14E` is dead at 1.55:1. Accent ≤3 times per viewport-height.

---

## 6. Approval gates — five questions, each with my recommended default

1. **Direction A as the base, with C's specificity folded in and B retired to a future
   wedding-cards page — agreed?**
   *Recommended default: yes.* If you prefer C's ledger register, say so now, but it cannot be
   committed to before the questionnaire returns, and it currently loses the bride.
2. **Do you accept that voice is a gate, not a polish step?** Every line rewritten in shop
   English and read aloud to your uncle before build sign-off.
   *Recommended default: yes.* This is the finding of the session and it is what killed v1.
3. **Is your uncle the veto on recognisability?** Boards go on his Android phone at 360px before
   any build, and if he does not recognise his shop the direction is wrong regardless of scores.
   *Recommended default: yes — he vetoes recognisability, you veto quality.*
4. **Content before full build?** Emergency actions today (`noindex` the live fake pages, open
   the Google Business Profile, questionnaire by phone), one fixed section of A rendered at 360px
   this week as a probe, full build after Q12/Q24/Q25/Q26 and at least three real photos.
   *Recommended default: yes.* If you want the full build immediately on placeholders, I will
   sequence it — but on the record I expect a third rejection, for the reason A's own author
   gave: a board full of `$XX` will read as basic because it is basic.
5. **Does launch gate on the photo shoot?**
   *Recommended default: yes — build against typeset samples, do not publish without at least
   6 real job photos (must include signs and banners) + 1 storefront.* One afternoon, zero
   dollars, cheapest item on the critical path, and it outranks every token decision we have
   argued for three sessions.

---

## 7. Still blocked

**On the questionnaire** (`docs/client-questions.md`) — by phone, not email:
- **Q12** top 3 money-makers → the order of the job fork band and what the hero speaks to first.
- **Q24** main customers → whether the walk-in or the B2B door comes first on mobile.
- **Q25** why customers choose you → the ceiling on how far "premium" can go before the site is
  lying about the business. *Default assumption: quality at a fair price, family-run, no minimum
  too small.* If the real answer is "cheapest and fastest", parts of §5 change.
- **Q26** languages → a homepage trust line, and possibly a *typeface* input if Gurmukhi or
  Urdu-adjacent setting is needed.
- **Q15/Q16/Q20/Q21** turnaround, minimums, starting prices, willingness to publish ranges →
  every "from $X" and every spec line. Without Q21 the whole specificity strategy collapses and
  we forfeit the one exploitable weakness in the Brampton market (`research L19`).
- **Q1, Q3–Q8, Q33** name spelling, phone, WhatsApp, email, hours, years in business, who answers
  → he can give these today, and the board is unjudgeable without them.

**On photography** (Q28–Q30): 8 photos, one phone, one bright window, zero dollars —
6 finished jobs **including at least one lawn sign and one banner**, 1 storefront, 1 owner.
Blocks: the ink-dark movement (§5.20), the launch itself (§6.5), and the storefront-sign photo
specifically gates the **terracotta accent** — if his sign is a different colour, `#B84A26`
changes and every board above is repainted. Get that one photo first.

**Also outstanding, not blocked on the client:** domain purchase, Formspree account, and the
Google Business Profile — the GBP is the ranking asset (~100 reviews ≈ top 3 in Brampton,
`research L21`) and it currently sits at zero while we have held four meetings about colour.
That is the largest strategic error on this project and it is mine.

---

**On approval:** this file becomes the build contract. `design-direction.md` L2 →
PARTIALLY SUPERSEDED (palette survives; structure and the even nine-step type ramp do not);
`CLAUDE.md` L15–16 and `roadmap.md` Phase 0 reconciled to point here; decisions logged to
`docs/team-archive.md`. The §0 emergency actions do not wait for approval.
