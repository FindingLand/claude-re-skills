---
name: webbuilder
description: >-
  Build, publish, and edit a real business website for free. The AI interviews the business owner
  first (what the business does, services, who buys, brand colors, pages needed), then writes a
  clean static site with copy that speaks the customer's language, enforces hard color-contrast and
  mobile-readability rules before anything ships, and wires up a working contact form that emails
  every lead. Publishes free on Netlify (drag-and-drop or GitHub) with a custom domain and automatic
  HTTPS. Use this skill whenever the user wants a business website, a landing page, a company site, a
  small-business site, a contact or lead form, to go live on a custom domain, to redesign or edit an
  existing site, or to stop paying a monthly website-builder subscription. Trigger on: build my
  website, business website, company website, landing page, small business site, website for my
  business, contact form, publish my site, custom domain, redesign my site, edit my website.
compatibility: Works in any AI assistant that can write files and, optionally, run git. No paid
  tools required.
---

# Build a Business Website (free)

This skill turns your AI assistant into the person who builds and maintains your website. You answer
a short interview once, the AI writes a clean, fast website in your own words, and from then on you
change it by just asking ("change my hours", "add this new service", "update my phone number"). No
monthly builder subscription, no page-builder lock-in.

Honest note: this builds a fast, professional site with real working copy and a real, working contact
form. It is not a booking engine, an online store, or a full CMS out of the box (those need paid
add-ons or extra integrations), but a plain site connects cleanly to those later. You bring accurate
details about the business; the AI builds and maintains the structure.

## Staying up to date (quick version check)

**This skill is version 1.0.** Finding Land keeps improving these skills. When you (the AI assistant)
first use this skill in a conversation, do a fast version check, then get on with the job:

1. Fetch `https://raw.githubusercontent.com/FindingLand/claude-re-skills/main/webbuilder/version.txt` (one
   line: the latest version number).
2. If that number is higher than 1.0, tell the user once, in one line: "A newer version of the webbuilder
   skill (X) is out, free at findingland.help/free-resources. Want to grab it?"
3. If the fetch fails or there is no internet, skip this silently.

Do it at most once per conversation, and never block the real work on it.

## What it costs (the honest version)

- **Building it: free.** The AI writes the files. No charge.
- **Hosting it: free.** Netlify's free tier hosts a static site, gives you HTTPS, and emails you every
  contact-form submission. The free plan covers 100 form submissions per month, 100 GB bandwidth, and
  300 build minutes per month, which is plenty for one small-business site.
- **A custom domain (yourbusiness.com): about 10 to 15 dollars a YEAR** from any registrar. Optional,
  you can launch on a free yourbusiness.netlify.app address first and add a domain later.
- **About 9 dollars a MONTH, only if** you want Netlify's built-in analytics, or you outgrow the free
  form or build limits. In practice you only hit that with well over 100 leads a month (a good problem)
  or dozens of redeploys a day. Most small businesses never leave the free tier.

Setup takes an afternoon the first time. After that, edits take minutes.

## What the AI builds for you

A single, fast, mobile-friendly site (plain HTML, CSS, and JS, no fragile page builder, no framework)
with sections built to match what the interview turns up, typically:

1. A hero with what the business does, who it is for, and one clear call to action (call, book, get a
   quote, buy, whatever the interview says the visitor should do first)
2. An About section (the story, how long the business has been running, what makes it different)
3. A services or products section (cards or a short list, benefit-first descriptions, pricing if the
   owner wants it public)
4. Real proof: testimonials with a real name and business or city, or client logos, or before/after
   work photos, whichever fits this business
5. A contact and lead-capture form that emails every submission straight to the owner's inbox
6. Click-to-call and click-to-email, social links, hours, address or service area, in the footer

### What actually makes a business site convert

- **One primary call to action, above the fold.** Decide in the interview whether the goal is a call,
  a booking, a quote request, or a purchase, then make that single action the loudest thing on the
  page. A page with three competing buttons converts worse than a page with one clear one.
- **Speak the customer's language, not the owner's.** Write about the outcome the customer gets, not
  the internal process. A plumber's customer cares about "hot water again today," not "24 years of
  pipefitting experience," even if the second line supports the first.
- **Real photos beat stock photos.** A real photo of the owner, the team, the shop, or the work beats
  a generic stock image every time, because it is proof the business actually exists.
- **Short lead form.** Name, one contact method, and a message box. Every extra required field drops
  completion. Ask qualifying questions later, in the reply or the call, not on the form.
- **Proof near the ask.** Put a testimonial or a "recent work" strip right next to the contact form so
  the reader has a reason to trust the business at the exact moment they decide to reach out.
- **Fast and mobile-first.** Most small-business traffic arrives on a phone. Compressed images and no
  heavy framework mean the page loads in about a second, which is itself a conversion factor.

## The build, step by step

Follow these in order. The AI does the building; the owner does only the account steps (logging in,
clicking publish), because those are tied to their accounts.

### Step 1 - Interview the business first

Before writing a single line of code, ask the owner these questions (skip any they clearly already
answered in their first message):

- What does the business do, in one sentence a stranger would understand?
- What specific services or products does it sell? Is this a one-page site, or does each service or
  product deserve its own page?
- Who buys, and what do they care about most: price, speed, trust, expertise, convenience? This drives
  the words on the page, not just the design.
- Does the business already have a logo or brand colors? If yes, use them. If no, propose a simple
  pairing (for example, a dark neutral plus one accent color) and confirm it before building.
- How many pages does this need: a single page, or separate home, about, services, and contact pages?
- Contact details: phone, email, address or service area, hours, and any social links to include.
- Any existing copy, photos, reviews, or an old site to pull real content from, so nothing gets
  invented.
- Is there a domain already, or should the site launch on a free netlify.app address first?

Copy-paste starter prompt once those answers are in hand:
"Build me a small-business website as a single folder of static HTML, CSS, and JS (no framework, no
build step). [One page / these pages: list them]. Sections: hero, about, services or products,
testimonials, and a contact form. Make the contact form a Netlify Form that emails me. Mobile-first,
fast, accessible, with sensible page-title and meta-description SEO tags. Here are the business
details: [paste the interview answers]."

### Step 2 - Write the site

Keep it to plain HTML, CSS, and JS, no framework and no build step, so it can be dragged straight onto
a host with nothing to install. Write every headline and paragraph in the customer's language from the
interview, not filler ("industry-leading solutions") and not invented claims. If a page needs a fact
the owner has not given yet, mark it clearly (for example "[confirm hours]") instead of guessing.

### Step 3 - Hard readability rules (non-negotiable)

Bad contrast is the single most common reason a first draft looks unfinished. Apply these on every
page, every time:

- **Set text and background color together, as a pair, in the same rule.** Never set a text color
  without also setting or confirming its background, and never leave either to an inherited or browser
  default. An unset background under a colored text rule is how "white text on white" bugs happen.
- **Hit real contrast ratios.** Body text needs at least a 4.5 to 1 contrast ratio against its
  background; large text (roughly 24px and up, or bold and 19px and up) and UI elements like button
  borders need at least 3 to 1. These are the standard WCAG AA numbers, so treat them as a floor, not
  a suggestion.
- **Use pairs you can trust.** Near-black text (about #1a1a1a to #222222) on white or very pale
  backgrounds is always safe. Light text is only safe on a background that is clearly darker than
  mid-gray. Avoid gray-on-gray, light-on-light, and a light brand color used as text on a white or pale
  background, all common ways a "clean" palette turns unreadable.
- **Check every place text actually appears**, not just the body copy: headings, links (including the
  hover and visited states), button text against its own button background, placeholder text inside
  form fields (placeholder gray on white is a frequent silent failure), and footer text against the
  footer background (dark-on-dark footers are another common miss).
- **Check contrast at phone width, specifically**, not only on a wide desktop preview. Resize the
  browser, or use the device toolbar, down to about 375px wide and look again at every section. Lighter
  font rendering and smaller buttons on some phones can turn a borderline desktop pairing into one that
  fails on a phone.
- When in doubt, do not eyeball it: pick from the trusted pairs above, or check the live page against a
  contrast checker (for example WebAIM's) before calling a page done.

### Step 4 - Mobile check before shipping

Before anything is called finished, resize the preview to a phone width (about 375 to 390px) and
confirm, in order: no horizontal scrollbar anywhere on the page; every button and link is big enough to
tap with a thumb (roughly 44 by 44px); images scale down and never overflow their container; the
navigation collapses to something usable on a small screen; body text has real side padding instead of
running edge to edge; and every headline still reads cleanly, since a phrase that fits nicely on
desktop can wrap awkwardly or overflow on a phone. Fix anything that fails before moving on.

### Step 5 - Pick a contact form option

1. **Netlify Forms (default when hosting on Netlify).** Add `data-netlify="true"` and a hidden
   `form-name` input to the form tag, a honeypot field (a hidden `bot-field` that silently traps spam
   bots), and `action="/thank-you.html"` plus a simple `thank-you.html` success page. Free tier covers
   100 submissions a month. This only truly emails once the site is live on Netlify (Step 7), so a
   local preview just shows the success page.
2. **A plain `mailto:` link, as a fallback only.** If the site is not going on Netlify, or the owner
   wants zero setup, a `mailto:` button opens the visitor's own email app. It needs no backend at all,
   but it depends on the visitor having a mail client configured, so use it only when Netlify Forms is
   not an option.
3. **A third-party form service (for example Formspree or an embedded Google Form).** Useful if the
   site is hosted somewhere other than Netlify, or the owner wants autoresponders or a spreadsheet of
   submissions. Each service has its own free-tier limits, so check the current limits before relying
   on one.

Default to option 1 whenever the site is going on Netlify; only reach for 2 or 3 when it genuinely is
not.

### Step 6 - Publish free on Netlify

Create a free account at netlify.com. For a first launch with no git set up yet, the fastest path is
**drag-and-drop**: go to app.netlify.com, choose "Add new site" then "Deploy manually", and drag the
site folder straight onto the page. Netlify gives a live `yourbusiness.netlify.app` URL in seconds. For
ongoing edits without re-dragging every time, connect a GitHub repo instead ("Import an existing
project"), set no build command and the publish directory to the repo root, and every push then
auto-publishes in about 10 seconds. Use drag-and-drop to get live fast; move to the GitHub path once
edits start coming often.

### Step 7 - Turn on lead emails

In Netlify: **Forms, then "Enable form detection", then redeploy once** (Netlify only finds the form on
a deploy, so the very first form will not register until you redeploy, or re-drag the folder, after
enabling). Then **Project configuration, Notifications, Form submission notifications, Add
notification, Email**, and enter the owner's email. Send a real test submission to confirm it lands,
and check it is not sitting in spam. Consider a second notification address or a webhook so a lead
never slips through.

### Step 8 - Add a custom domain (optional)

Buy `yourbusiness.com` at any registrar, about 10 to 15 dollars a year. In Netlify: **Domain
management, Add a domain**, then at the registrar point the records Netlify shows (an apex record to
Netlify's load balancer and a `www` CNAME to the netlify.app address). Netlify issues HTTPS
automatically once DNS propagates, usually minutes to a few hours. If that domain is also used for
email, do not touch the existing MX or SPF/DKIM records, only add the website records Netlify gives.

## Look at it before you ship it (the iteration loop)

After every real change, actually look at the page, do not just trust that the code is correct.
Screenshot it or open it in a browser preview, at both a normal desktop width and a phone width.

- Read every headline and button out loud against the interview answers: does it sound like this
  specific business, or like generic filler that could belong to anyone?
- Look for the usual failure modes: overlapping elements, text touching the edge of the screen, a
  button that does not stand out, a color pair that is hard to read, a stretched or oddly cropped
  image, broken alignment at phone width.
- Fix whatever looks off, then look again. Repeat before calling it done. Ship after a full pass looks
  right at both sizes, not just after the file writes without an error.

## Images, speed, and SEO

- **Compress before upload.** A phone photo can be 4 to 8 MB and will crush load time. Resize photos to
  about 1600px wide and export as JPG or WebP under roughly 300KB each. Ask the AI to do this.
- **Self-host images in an `images/` folder** and always set `width`, `height`, and descriptive `alt`
  text. Alt text like "storefront on Oak Street" helps both accessibility and image search.
- **Fill the SEO basics.** A unique `<title>` ("[Business], [What it does] in [City]"), a one-sentence
  meta description, and clean headings. For a local business, the city and neighborhood names in real
  copy do more than any keyword trick.
- **Add the local-business signal.** A footer with the business name, address or service area, and
  hours, plus click-to-call, is what both search engines and visitors look for.

## Editing later (the whole point)

Once it is live, the owner never opens a page builder again. They just ask the AI:
- "Add this service: [name, short description, price if public]"
- "Mark [service or product] as no longer offered"
- "Swap the photo on the about section for the new one"
- "Change the phone number to ..."
- "Add a Spanish version of the about section"

The AI edits the files and pushes; Netlify republishes in about 10 seconds. If the site was deployed by
drag-and-drop, the AI hands over the updated folder to drag again.

## If you add booking, payments, or another API-based tool later (keep keys safe)

If the site later needs a booking widget, a payment processor, or any service that requires an API key,
never put that key in the website's front-end code (anyone can read it in the browser). Use a
**Netlify Function**: a small server-side file in `netlify/functions/` that holds the key in a Netlify
**environment variable** and returns only the clean data the page needs. Ask the AI to "add a Netlify
Function that proxies [service] so my API key stays server-side." Environment-variable changes only
take effect after a redeploy.

## Gotchas (save yourself the headache)

1. **The contact form will not email until you redeploy** after enabling form detection (Step 7). This
   trips up everyone once.
2. **Deploy only the website folder**, never a parent folder that holds private files or notes.
3. **Self-host and compress images** inside an `images/` folder; do not hot-link someone else's URL, or
   pictures break later and pages load slowly.
4. **Keep editing through the same path** (git, or always re-dragging the latest folder), so the live
   site and the working files never drift apart.
5. **API keys never go in page code.** Use a Netlify Function instead, as above.
6. **Free Netlify password protection does not exist.** If a page needs to stay private, use a long
   unguessable filename and do not link it from anywhere public.
7. **Do not fake testimonials or reviews.** Use real ones with permission, or leave the section out
   until there are some.
8. **Skipping the interview produces generic copy.** A site built from a one-line request instead of
   real answers reads like a template and undersells the business; always get the details first.

## Quick checklist

1. Interview done: what the business does, services, who buys, brand colors, pages needed, contact
   details
2. Site written in the customer's language, plain HTML/CSS/JS, no framework
3. Every text and background set as a pair, contrast checked, including at phone width
4. Mobile check passed: no horizontal scroll, tappable buttons, images scale, nav works small
5. Contact form chosen (Netlify Forms by default) and wired up, with a thank-you page and honeypot
6. Images compressed and self-hosted, SEO title and description filled in
7. Published on Netlify (drag-and-drop for a fast first launch, or GitHub for ongoing auto-deploys)
8. Form detection enabled, redeployed, email notification set, and tested (check spam)
9. Screenshot or open the live page and fix anything that looks off before calling it done
10. (Optional) custom domain added, HTTPS auto-issued
11. From now on: just ask the AI to make any change

---

*Built and battle-tested by [Finding Land](https://findingland.help), who build AI automations for companies of any size. This skill is free. If you would rather have it built for you, done for you and wired to your tools, [get in touch](https://findingland.help/contact-us.html).*
