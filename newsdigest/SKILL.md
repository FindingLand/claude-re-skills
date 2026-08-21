---
name: newsdigest
description: >-
  Delivers a personalized industry news brief: a tight, signal-only briefing across three time
  windows (today, this week, this month) covering ONLY the topics that could change a decision the
  user actually makes, in ANY industry (software, healthcare, retail, manufacturing, hospitality,
  finance, logistics, agriculture, professional services, and more). It filters hard to cut
  clickbait and noise, and it works for any role: a founder, an operator, a buyer, a salesperson,
  and a compliance lead reading the same headline should each get a different "so what," and this
  skill writes that read aimed at the user specifically once they say their industry, role, and
  the decisions they make. The first reply is a scannable list of headlines only; the user drills
  into any item by number for the "why it matters to you" read. Use this whenever the user wants a
  news brief, morning briefing, digest, industry update, competitor watch, regulatory watch, to be
  caught up on their industry or market, or asks "any news on X." On first run it reads industry,
  role, and decisions from preferences.md, or runs a short interview. Trigger even when the user
  does not say "news," as long as they want to stay current on the industry they operate in. Also
  covers how to run it as a recurring daily or weekly routine.
compatibility: Works in any AI assistant that can search the web and read files. No account or setup fee.
---

# Your Personalized Industry Brief

Every industry throws a firehose of headlines at people every day, and most of them do not change a
single decision anyone actually makes. But the small share that do (a competitor's price move, a
regulator's ruling, a key supplier going under, a new tool that changes how the work gets done) are
buried under the noise, and by the time someone notices, the decision has already been made without
that information. Reading enough sources to catch the real signal costs 20 to 40 minutes a day most
people do not have.

This skill inverts that. The user tells it their industry, their role, and the decisions they actually
make day to day, plus the topics they want tracked. It searches only those, cuts the clickbait and the
ten-articles-about-one-thing noise, and hands over the shortest possible glance: headlines only. When
the user wants the "so what," they say a number and get a read written for their specific role and
decisions, not a generic summary of the industry.

Honest note: this is a briefing tool, not a research analyst or a data terminal. It reads public news
and public sources, not the user's internal systems, CRM, inventory, or financials, so treat any number
it surfaces as a starting point to verify, not the final word. It saves the reading time, not the
diligence.

## Staying up to date (quick version check)

**This skill is version 3.0.** Finding Land keeps improving these skills. When you (the AI assistant)
first use this skill in a conversation, do a fast version check, then get on with the job:

1. Fetch `https://raw.githubusercontent.com/FindingLand/claude-re-skills/main/newsdigest/version.txt` (one
   line: the latest version number).
2. If that number is higher than 3.0, tell the user once, in one line: "A newer version of the newsdigest
   skill (X) is out, free at findingland.help/free-resources. Want to grab it?"
3. If the fetch fails or there is no internet, skip this silently.

Do it at most once per conversation, and never block the real work on it.

## What it produces

1. A **signal-only headline list** grouped into three windows (today, this week, this month), numbered
   continuously so the user can point at any item.
2. A **role-and-decision read on demand**: say a number and get the facts plus "what this means for
   you," aimed at the role and decisions set once in preferences, so the read is always specific.
3. An **honest empty answer** when a window had nothing that matters. It says so instead of padding.
4. A **preferences file** that remembers the user's industry, role, decisions, topics, and sources so it
   never re-interviews them.

## There is no fixed topic map, because the industry is unknown until the user says so

A skill built for one industry can ship with a hardcoded list of topics. This one cannot, because it
has to work for a bakery owner and a biotech CFO alike. Instead of a fixed list, build the topic list
WITH the user during setup, using this checklist as a starting prompt (not a fence; add anything specific
they name):

1. **Market and demand**: what customers in their segment are doing, buying, or asking for.
2. **Competitors**: pricing moves, launches, expansions, exits, funding, partnerships.
3. **Regulation and policy**: laws, rulings, licensing, compliance deadlines that touch their business.
4. **Costs and supply chain**: input prices, key suppliers or vendors, shipping, energy, key materials.
5. **Technology and tools**: new tools, platforms, or AI capabilities that change how the work gets done.
6. **Talent and labor**: wage law, hiring trends, skills shortages, union activity in their field.
7. **Capital and financing**: lending conditions, investment activity, or funding news relevant to them.

Most users only care about three or four of these. Push for specifics: not "regulation" but "FDA device
approvals," not "competitors" but "the two other shops in my zip code," not "costs" but "the price of
the resin we mold with." A tight, specific list is the whole point.

## Why it matters to THEIR decisions (the framing engine)

This is what makes the brief worth reading. The same headline means different things depending on how
someone makes decisions, so the drill-down has to be written for the role and decisions in the user's
preferences, never for "the industry" in general. A few examples of how this plays out across very
different businesses:

- **"Wheat futures up 12% this month."** A bakery owner reads this as a cost-of-goods problem hitting
  next month's margin, so the read is about whether to lock in a supplier contract now or wait. A
  commodities trader reads the same headline as a position to take. A gluten-free snack maker barely
  cares, because it does not touch their input costs at all, so this item might not even clear the
  relevance filter for them.
- **"New data-privacy law passes in a major state."** A software CTO reads this as an engineering and
  data-retention deadline. A sales VP reads it as a talking point that could slow down deals in that
  state until compliance is confirmed. A marketing lead reads it as a constraint on how customer data
  can be used in campaigns going forward. Same law, three different actions.
- **"A major shipping carrier announces a rate hike."** A retail buyer reads this as a landed-cost
  problem to reprice or renegotiate. A warehouse ops manager reads it as a reason to revisit which
  carrier handles which lanes. A small e-commerce seller reads it as a margin hit that might force a
  shipping-fee change on their own storefront.

When explaining an item, name the user's role and decision and give the read for THAT specifically. Do
not give a generic "this affects the industry." Say what this person should be thinking about or doing
next, in one to three lines.

## What you need

- The **industry** (and sub-segment if it helps: "commercial HVAC installers," not just "construction").
- The **role**, so the reads are aimed at the right seat (owner, operator, buyer, salesperson, compliance,
  finance, a specific function, or a mix; a mix is fine, name the primary one).
- The **decisions** the user actually makes: pricing, hiring, supplier choice, expansion, budget calls,
  what they report to a boss or a board. This is more useful than a job title alone.
- The **topics** to track, built from the checklist above plus anything specific.
- Optional: named sources the user trusts, and anything to always avoid.

That is the whole setup. No account, no API key, no fee.

## Setup: fill preferences once (or answer a few questions)

First check whether `preferences.md` (in this skill's folder) has real content or is still the template.

- **If it has real content**, use it silently. Confirm in one line what the brief covers, for example:
  "Briefing you as the ops lead at a regional HVAC installer: supplier prices, licensing rules, and
  competitor moves in your service area." Then search.
- **If it is still the template**, run a short interview in ONE message. Ask for:
  1. **Industry** (and sub-segment): what business the user is actually in.
  2. **Role**: their seat, and if useful, who they report to or answer for.
  3. **Decisions**: the two or three calls they actually make that news could change.
  4. **Topics** from the checklist above (plus anything specific), and optionally **sources** and an
     **avoid** list.

  Keep it to one message. This tool exists to save time, so do not turn setup into a form. After they
  answer, save it (see persistence below) and go straight to the brief.

## How to run it day to day

**Step 1: load the setup.** Read `preferences.md`, or run the interview once.

**Step 2: search the three windows.** Compute the windows from the ACTUAL current date at runtime:
- **Today** = last 24 hours. **This week** = last 7 days. **This month** = last 30 days.

For each topic, run date-scoped web searches, phrased so results are recent and on-topic, and localized
to the user's market where the topic is local (a region, a customer segment, a specific set of named
competitors). Run searches for different topics in parallel where you can. If the user named sources,
bias to them. Headlines, dates, and a one-line sense of what happened are enough for the glance; save
full reads for the drill-down.

**Step 3: filter, dedupe, rank.** This is the heart of it. Cut aggressively. Keep an item only if it is
both:
- **Relevant**: squarely inside one of the user's topics AND their industry/segment.
- **Important**: a real development someone with this role would act on. A decision, a data release, a
  rule change, a competitor move, a launch. Not a rumor, not a hot take, not a listicle.

Cut clickbait, generic opinion pieces, national or global fluff that does not touch the user's actual
business, and anything on the avoid list. Dedupe across windows and sources: the same story from five
outlets is one item, and a developing story goes in the tightest window where its newest meaningful
development falls, not in every window. Rank within each window by importance to THIS user, most
important first. Apply the per-window cap (default 5). If a window has fewer important items, show
fewer. If none, say so.

**Step 4: the glance.** The first reply is headlines only. No summaries, no preamble beyond one optional
context line. Group by window, newest window first, number continuously. Use this shape:

```
Here's your brief. Say a number for what any of them means for you.

TODAY
1. [headline, one line, plain and factual]
2. [headline, one line]

THIS WEEK
3. [headline, one line]

THIS MONTH
4. [headline, one line]
```

Rules: one line each, wire-service plain, no teasers. No links or source names in the glance (those
come in the drill-down). If a window is empty, write for example `THIS WEEK: nothing that moves your
business.` and move on. Close with one short line on how to go deeper. Do not editorialize and do not
add an "other news" section.

**Step 5: drill down on request.** When the user says a number, a range ("3 to 5"), "the today ones," or
a topic, expand only those. Use web fetch to read the actual articles so the detail is accurate. For
each:
- **What happened**: 2 to 4 sentences of concrete facts, with the real number where there is one (the
  price change, the percent, the date a rule takes effect).
- **What it means for YOU**: one to three lines using the framing engine above, named to the user's role
  and decisions. This is the payoff. Make it a read they can act on, not a platitude.
- **Source**: one or two links to the best primary or reputable coverage, with the date.

Keep it factual and neutral on the facts, opinionated only in the clearly-labeled role-and-decision read,
and always grounded in what the source actually says. If sources conflict or a number is unconfirmed,
say so plainly. The pattern is always: shortest useful answer first, more only on demand.

## Keeping preferences updated

Every time the user changes industry, role, decisions, topics, sources, or avoids, update
`preferences.md` in the same session so the next run is accurate without re-asking. How to persist
follows the `PERSISTENCE` line in the file: if it names a method (local only, or push to a repo or
synced folder), follow it exactly. If there is no `PERSISTENCE` setting yet, ask once how the user wants
it kept and record the answer as the `PERSISTENCE` line so you never ask again. A cloud or git copy is
worth recommending, because their setup then survives a lost laptop and follows them across devices.

## Preferences file format

`preferences.md` lives in this skill's folder. When the file still looks like the template (the example
values or the PLACEHOLDER marker), treat it as empty and run the interview. Save real setup in this
shape:

```
# My industry brief preferences

INDUSTRY:
- [industry and sub-segment, e.g. "regional HVAC installation and repair"]

ROLE:
- [your seat, e.g. "operations lead, reports to the owner"]

DECISIONS YOU MAKE:
- [e.g. which supplier to buy parts from]
- [e.g. when to raise service prices]
- [e.g. whether to add a second crew]

TOPICS:
- [from the checklist, e.g. supplier and parts pricing]
- [e.g. licensing and code changes in your state]
- [any specific extra, e.g. the two competitors you actually watch by name]

SOURCES:
- [named outlets/newsletters/trade publications, or "reputable general sources"]

AVOID:
- [topics or kinds of story to never show, e.g. national economic opinion pieces]

ITEMS PER WINDOW: [number, default 5]

PERSISTENCE: [how to save changes, e.g. "local file only" or "update this file and push to my <repo> git repo"]
```

## Copy-paste prompts

Run the brief:
```
Give me my industry brief.
```

First-time setup by hand (skip the interview):
```
Set up my industry brief. Industry: [your industry]. Role: [your seat]. Decisions I make: [list two
or three]. Topics: [pick from the checklist]. Sources: [outlets, or "reputable general"]. Avoid:
[anything you never want]. Save this to preferences.
```

Drill in:
```
3 to 5, and tell me what each means for me.
```

Ask about one topic on the fly:
```
Any supplier or pricing news this week that changes anything for me?
```

## Running it as a recurring routine

The brief is most useful when it shows up on its own instead of waiting to be asked. A few ways to make
that happen, in order of how little setup they take:

1. **A scheduled task inside the assistant, if the platform has one.** Some assistants can run a saved
   prompt on a cron-like schedule (for example, "every weekday at 7am"). If that feature exists here,
   set it up to run "Give me my industry brief" and point it at this skill and the user's preferences
   file. Confirm the exact time and the schedule wording the platform expects; do not guess at syntax it
   does not support.
2. **A calendar-based trigger.** A recurring calendar event with a reminder ("Read my industry brief")
   works in any assistant that can be opened from a notification, and it costs nothing to set up.
3. **A standing habit tied to something the user already does daily**, such as opening their inbox or
   their task manager. Suggest they open this conversation (or a fresh one that reads preferences.md)
   right after that habit, so it rides along instead of competing for a new slot in their day.
4. **An OS-level scheduled job**, if the user is comfortable with one, that runs a script or CLI command
   which invokes the assistant with the brief prompt at a fixed time and delivers the output by email or
   message. This takes more setup and is worth it mainly for someone who wants the brief to land before
   they are even at a keyboard.

Whichever method the user picks, confirm the cadence (daily, weekdays only, or weekly) and the time, and
write it down as a line in `preferences.md` (for example `SCHEDULE: weekdays, 7am`) so a future session
can remind the user what they set up, and can be re-scheduled or turned off with a plain-language request.

## A few principles to hold onto

- Attention is the scarce resource. Fewer, better items beats a long list every time.
- Localize everything to the user's actual business. "The market is up" in general is noise; a move that
  touches their customers, their suppliers, or their competitors by name is signal.
- The role-and-decision read is the product. A headline the user cannot act on does not belong in the
  brief.
- Never pad. An honest "nothing moved your business today" is a feature, not a failure.
- Real numbers, verified. Surface the price or the percentage, but tell the user to confirm it before
  they act on it.
- Stay neutral on facts, aimed on the user's decisions, and respect the source scope and avoid list
  exactly.

---

*Built and battle-tested by [Finding Land](https://findingland.help), who build AI automations for companies of any size. This skill is free. If you would rather have it built for you, done for you and wired to your tools, [get in touch](https://findingland.help/contact-us.html).*
