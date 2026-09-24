# The Side Hustle Hub — Launch Checklist

Five files: `index.html` (the hub) and four product pages —
`budget-planner.html`, `ai-analyser.html`, `tutoring.html`, `freelancing.html`.

Work top to bottom. Stage 1 items block launch. Stage 4 is optional polish.

---

## STAGE 1 — Blockers

Nothing should go live until these four are done. The site is currently
non-functional without them.

### ☑ 1. Add the three images — DONE

**Why:** The hub points at `images/hero-speaking.jpg`, `images/stats-bg.jpg`
and `images/story-workshop.jpg`. That folder doesn't exist yet, so your hero
photo, your stats band and your story quote panel are all empty frames right now.
This is the most visible gap on the page.

**Do this:** Make a folder called `images` and put it next to the HTML files.
Export three photos into it with those exact filenames:
- `hero-speaking.jpg` — you with the mic, presenting (4:3, landscape)
- `stats-bg.jpg` — anything wide that works dark; it sits at 35% opacity behind the stats
- `story-workshop.jpg` — you with students around the table (4:3, landscape)

Keep each under 400KB or the page will feel slow on mobile data.

---

### ☐ 2. Connect email delivery

**Why:** All four Free Download buttons open a modal, collect a name and email,
and send them nowhere. `REPLACE_WITH_YOUR_EMAIL_FORM_URL` is still sitting in
the form action on every product page. Right now the core promise of the site
doesn't work.

**Do this:**
1. Create a Kit (ConvertKit) account — the free tier is enough to start
2. Make **one** form, not four. Use a hidden field or four separate forms only if
   you want to know which magnet someone came from (you probably do)
3. Upload each PDF as the incentive so Kit emails it automatically on signup
4. Copy the form's action URL
5. Paste it over `REPLACE_WITH_YOUR_EMAIL_FORM_URL` — once in each of the four
   product pages

**Test it yourself before launch.** Sign up with your own email and confirm the
PDF actually lands in the inbox, not spam.

---

### ☐ 3. Connect Calendly

**Why:** The RM100 call is now your only revenue. Five Book a Call buttons
currently point at `REPLACE_WITH_YOUR_CALENDLY_LINK` — one on each product page
plus the hub's bottom CTA.

**Do this:**
1. Create a Calendly event: 45 minutes, video, limited slots
2. Decide how payment works (see the decision below)
3. Paste the link over `REPLACE_WITH_YOUR_CALENDLY_LINK` in all five files

**Decision you need to make:** the pages currently say *"Pay after you book — no
payment needed to hold the slot."* That's lower friction but means people can
book and ghost, and you'll be chasing RM100 payments. Calendly can take payment
upfront via Stripe instead. If you switch to paying upfront, that line on all
four pages needs rewriting — tell me and I'll change it.

---

### ☐ 4. Confirm all four PDFs actually exist

**Why:** A page that promises a guide you haven't written yet is worse than no
page. The budget planner exists. The tutoring guide existed as a paid product.
The freelancing guide was only ever scoped, as far as I know.

**Do this:** Check each one. If a guide isn't written, don't publish that page
yet — launch with three tiles and add the fourth later. An empty promise costs
more trust than a smaller menu.

---

## STAGE 2 — Two contradictions to resolve

These aren't bugs, they're decisions only you can make.

### ☐ 5. Fix the AI Analyser mismatch

**Why:** `ai-analyser.html` has a Free Download button and a modal promising a
PDF. But the product answers five questions and gives you a personalised match —
that's a tool, not a document. The page and the product don't agree.

**Three options:**
- **A** — Build the quiz as an interactive page. Button becomes "Start The Quiz",
  email captured at the result screen. Best experience, most work.
- **B** — Make the free version a PDF decision tree (a flowchart you follow
  yourself), keep the interactive AI version as something you charge for later.
- **C** — Drop it from launch, publish three tiles, add it when the tool is built.

**Pick one and tell me.** I can't guess this one.

---

### ☑ 6. DONE — Remove "1-on-1 Mentorship" from Coming Soon

**Why:** The hub's Coming Soon section advertises 1-on-1 Mentorship as not yet
available, while all four product pages sell a live RM100 1-on-1 call. You're
telling people the same thing is both available and not.

**Do this:** Delete that card. Three Coming Soon cards is fine — the grid will
still work.

---

## STAGE 3 — Visible placeholder text

Small, fast, and all of it is text a real visitor can currently read.

### ☑ 7. DONE — Delete the testimonial note

`* Replace with real DM screenshots as you collect them` is sitting publicly
under your testimonials. Either delete the line, or better — replace the three
invented testimonials with real ones. They're currently fabricated (Aina, Reza,
Nadia), which is fine as a placeholder and not fine once the site is public.

### ☐ 8. Replace the hero video

The frame currently reads `Embed your video here`. Either embed your story video
or remove the frame entirely.

### ☑ 9. DONE — Fix the copyright year

Every footer says `© 2025`. It's 2026.

### ☑ 10. DONE — Fix the dead links

Five `href="#"` links go nowhere: TikTok and Contact in the hub footer, and
TikTok on each of the four product pages.

### ☐ 11. Verify your social handles

I used `instagram.com/syaaarveeni` and `linkedin.com/in/syaar307` without
confirming either. Check both actually resolve.

### ☑ 12. DONE — Add meta tags to the hub

**Why:** The four product pages have meta descriptions and OG tags. The hub has
neither. That means when someone drops your link in a WhatsApp group — which is
exactly how your audience shares things — the preview is completely blank. No
title, no image, no description. It looks broken and nobody clicks.

**Do this:** Needs a title, a description, and a share image (1200×630).

### ☑ 13. DONE — Rename "Products" in the nav

The nav still says PRODUCTS. Everything is free now. "Free Resources" or
"Resources" is more accurate and sets the right expectation before the click.

---

## STAGE 4 — Deploy

### ☐ 14. Buy a domain
Something short and typeable out loud, since most of your traffic comes from you
saying it in a video.

### ☐ 15. Optimise the images before uploading

**Why:** The three photos are currently embedded inside `index.html` as base64,
which makes it one self-contained 533KB file — convenient while building, slower
than it needs to be once real people are visiting. Embedded images can't be
cached, so every visitor re-downloads all 533KB on every visit, and nothing
renders until the whole file arrives.

They're also far bigger than the page uses. `story-workshop.jpg` is 1350px wide
and displays in a box about 450px wide — roughly nine times more pixels than
needed.

**Do this:** Ask me to split the images back out and compress them properly.
Should land around 120KB total across three files instead of 420KB, with no
visible difference. Result: HTML loads instantly, photos stream in behind it,
and repeat visitors re-download nothing.

**Note:** the reason we embedded them in the first place was that separate image
files weren't loading locally — a folder-structure problem, not a file-size one.
Worth sorting that out at the same time, since Netlify will serve them fine.

---

### ☐ 16. Upload to Netlify
Drag the **whole folder** — all five HTML files plus the `images` folder — in one
go. Uploading files individually breaks the links between pages.

### ☐ 17. Test on a real phone
Not desktop, and not a resized browser window. Specifically check:
- The modal opens and closes on iOS Safari (custom overlays break there most often)
- Every tile links to the right page
- The four-tile grid stacks to two columns properly
- Nothing overflows sideways

### ☐ 18. Test the full funnel yourself
Land on the hub → click a tile → click Free Download → enter your email →
confirm the PDF arrives → click Book a Call → confirm Calendly loads.
Do the whole thing once, on your phone, like a stranger would.

---

## STAGE 5 — Optional, after launch

### ☐ 19. The receipt intro animation
The printing receipt that ends on a blank `SIDE INCOME +______` line. It's the
fun part and it matters least. A memorable intro on a site where the download
button doesn't work is worse than no intro at all.

Before building it I need real numbers — your actual allowance, rent, food and
transport from second year, or from a DM someone sent you. Invented numbers will
be spotted immediately and cost more credibility than the animation gains.

### ☐ 20. Add the call to the hub
The RM100 call is your only revenue but appears on the hub exactly once, as a
button at the very bottom. It probably deserves a proper section.

---

## What I can do without you

Items 6, 7, 9, 10, 12 and 13 need no input — I can clear all six now, which
leaves you a shorter list that's genuinely yours: the images, Kit, Calendly, the
PDFs, the analyser decision, and real testimonials.
