Redesign the homepage for AZ Printing and Signs, a family-run print and sign shop in Brampton, Ontario. The current page is well written and structurally generic. I need it to stop looking like an AI-built website and start looking like a studio with skilled people made it.

The current page is live and self-contained, open it if you can:
https://mfahadishtiaq.github.io/printing-site-draft/AZ-Printing-Demo.html
Everything you need is also below, so you can work without it.

## The business (all facts here are real and verified)

AZ Printing and Signs, 499 Ray Lawson Blvd, Unit 24, Brampton, ON L6Y 4E6. Phone 416-731-9229, WhatsApp on the same number. Owner is a 65-year-old man who spent about 25 years behind a print and shipping counter before buying this shop. Staff speak English, Punjabi, Urdu and Hindi.

Two customers on one page: South Asian families ordering wedding and shaadi cards, and small businesses ordering cards, flyers, signs, apparel and repeat jobs. The site's job is phone calls, WhatsApp messages and quote-form submissions, plus ranking for "printing Brampton". It is not e-commerce.

## What is locked and not up for debate

**Palette.** White `#FFFFFF`, off-white `#F6F4F2`, near-black ink `#14100F`, soft ink `#5C5650`, borders `#E7E3DF`. Flame orange `#FF4D1C` for display type and graphics only, never text under 24px. Red `#D92B0E` for buttons, links and small accent text. Press inks cyan `#00AEEF`, magenta `#EC008C`, yellow `#FFD400` as a motif only.

**Type.** Fraunces for display (weights 800 to 900, WONK on), Literata for body (17px, line-height 1.65), Familjen Grotesk for interface labels and uppercase micro-type.

**Motion is the signature, not decoration.** Staggered section reveals, hero words rising, a 3.5 second crossfading showcase, a marquee, hover wipes, count-ups. Keep it. Two hard requirements: content must never be invisible when JavaScript fails (gate hidden states behind a confirmed-JS class and add a timed failsafe reveal), and `prefers-reduced-motion` must be fully honoured.

**The copy is final.** Every line was chosen word by word with the client. You may rearrange it and change its emphasis. You may not rewrite it. If a layout genuinely needs different words, say so and I will decide.

**Build constraints.** One self-contained HTML file, CSS inline, no build step, no dependencies except Google Fonts. Deploys to GitHub Pages.

## The copy, verbatim

Nav: Work · Services · Why us · FAQ · 416-731-9229 · Free Quote

HERO
Eyebrow: Print and sign shop · Brampton
H1: The day you're planning. The name *you're building.* (the italic words are flame orange)
Sub: Twenty-five years of printing experience, in a family shop on Ray Lawson Blvd. Explain the job in English, Punjabi, Urdu or Hindi, and we'll get it right the first time.
Buttons: Get a Free Quote · Call 416-731-9229

MARQUEE: Business cards · Vinyl banners · Lawn signs · Wedding cards · T-shirts · Stickers · Flyers · Storefront signs

RECENT PROJECTS (eyebrow "Our work")
- Lawn signs — 25 lawn signs with stakes for a Brampton real estate agent, ready in two days. → See lawn signs
- Team uniforms — 24 shirts printed front and back, delivered in two days. → See apparel
- Vehicle graphics — Door decals for a delivery van, measured, printed and fitted in a single day. → See vehicle graphics
- Storefront signs — A shop-front sign and window graphics, ready for opening day. → See storefront signs

WHAT ARE YOU PRINTING FOR? (eyebrow "Start here")
- For your event — Wedding and shaadi cards, nikkah and mehndi invitations, banners and photo gifts. Visit the shop to see the materials and hold the samples before you decide. → Event printing
- For your business — Business cards, flyers, signs, decals and branded apparel, with your artwork kept on file for repeat orders. Send us the details and we'll prepare a quote. → Business printing

WHY PEOPLE KEEP COMING BACK (eyebrow "Why us")
01 We check your file first — Every file is checked before it goes to press. If the logo is low resolution or the size is not quite right, we contact you first, so you are never charged twice.
02 You deal with the owner — Same family, same shop, every visit. The person who prices your job is the person who prints it, and he is here when you come in.
03 Your printer for all of it — The invitation for the wedding, the sign above the shop, the shirts for the team. Whatever comes next, we print it here.
04 No job too small — One shirt or a thousand flyers, both are welcome. You will know the price and the collection date before anything is printed.

STATS: 25 Years of printing experience · [two other tiles are invented numbers, rebuild or remove this band]

REVIEWS: built and deliberately empty until the shop has real Google reviews. Never put invented testimonials here.

FREQUENTLY ASKED QUESTIONS (eyebrow "Questions")
- What are your prices? — Price depends on the size, the material and how many you need. Business cards start at [$X]. Send us the details through the quote form below and we'll prepare a free quote.
- When will it be ready? — Most jobs take [X business days] from the moment you approve the artwork. If you need it sooner, let us know your date and we'll confirm what's possible before you place the order.
- Can you design it for me? — Yes, we design as well as print. Send us what you have, whether that's a photograph, a rough sketch or an existing file, and we'll prepare print-ready artwork for your approval.
- Can I see it before you print it? — Yes. We send you a proof to review, and printing starts only once you've approved it.
- Do you deliver, or do I pick it up? — We deliver across Brampton and Mississauga on orders over [$X]. Everything else is collected from the shop on Ray Lawson Blvd.
- Where are you, and can I just walk in? — We are located at 499 Ray Lawson Blvd, Unit 24 in Brampton, open [hours]. Visitors are welcome during opening hours, and artwork can be sent ahead on WhatsApp.

QUOTE FORM: Tell us about your job and we'll prepare a free quote. Five fields. Button "Get my quote". Under it: We only use your details to reply to this request.

FOOTER: A family-run print and sign shop serving Brampton, Mississauga and the GTA.

Square brackets are facts the owner has not supplied yet. Leave them visibly bracketed. Never replace them with plausible-sounding numbers.

## Why the current page reads as AI-made

Measured at 1400px, so these are facts about the build and not impressions:

1. **The photographs are AI-generated.** The loudest tell on the page, and no layout fixes it. Design around this: favour layouts that can carry real, ordinary photographs of a small shop, because those are coming.
2. **Zero asymmetric sections, where the studio standard requires at least two.** `.doors` is 556px + 556px, `.why` is 538px + 538px, `.show` is four equal 268px columns, stats and reviews are both `repeat(3,1fr)`. Five equal-column grids in a row.
3. **Six sections open with an identical skeleton:** small uppercase eyebrow, then a large heading with an underline. Same rhythm, same centre line, same 1180px column, top to bottom.
4. **One card, three sections.** The doors, the work tiles and the review cards all share `border-radius:18px` with a `1px solid #E7E3DF` border.
5. **No material.** This business sells physical objects and the page is smoother than anything it prints. There is no paper grain, no ink density, no card edge, no shirt weave, no cutting mat, no registration mark.
6. **Nothing is at true scale.** Every product is squeezed into the same tile, though each has a real trim ratio: business card 3.5:2, invitation 5:7, banner 24:9, poster 1:1.414.

An earlier version of this site was rejected for exactly fault 2 and 3. They came back.

## What I want from the redesign

- Break the single centred column. At least one full-bleed or edge-breaking moment.
- No two sections sharing a skeleton. Vary the section heads as well as the grids.
- At least two asymmetric layouts above 900px, one element at 70vw or wider, no section with more than four equal-weight items.
- Products shown at their true trim ratios rather than uniform tiles.
- A materials layer: paper, ink, texture, the physical evidence of a press.
- The stats band rebuilt or removed.
- Fix two journey problems while you are in there: all four work tiles currently link to `#` and scroll the customer back to the top, and both audience doors resolve to the same quote form, so the dual-audience fork does not actually fork.

## What must survive

Click-to-call, the floating WhatsApp button and the quote form. Strong text contrast, WCAG AA minimum, never light grey body text. No stock or AI photography of people, ever. The empty reviews section. The bracketed placeholders. `noindex` stays in the head until the placeholders are gone.

## How to deliver

Give me a rendered page I can open, not a written specification. Then tell me, briefly: what you changed and why, which of the six problems above each change addresses, and anything in the copy or the content that is fighting your layout.

Judge it at 360px on a phone first and desktop second. The owner is 65 and will look at it on his phone.
