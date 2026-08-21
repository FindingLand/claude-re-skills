---
name: crmbuilder
description: >-
  Build a business its own CRM in Airtable or Google Sheets, matched to how it actually sells instead of
  a generic template. Interviews the sales process first (how leads arrive, what a deal looks like, the
  stages that really exist, who works each one), then sets up contacts, companies, and deals tables with
  correct linked records, a kanban pipeline view, follow-up date discipline (a Next Action date on every
  open record plus an overdue view), views per role, and automation-ready field design. Also covers
  importing existing spreadsheet data without wrecking it. Use this skill whenever the user wants a CRM,
  a sales pipeline, a way to track leads or customers, to organize contacts and deals, to move off a
  messy spreadsheet, or to stop paying for a CRM platform they do not need. Trigger on: build my CRM,
  CRM, sales pipeline, track leads, organize contacts, customer database, deal tracker, Airtable CRM,
  Google Sheets CRM, pipeline stages, follow-up tracking, lead tracker.
compatibility: >-
  Works in any AI assistant that can write files and call the Airtable API or the Google Sheets API.
  Needs a free Airtable account or a Google account.
---

# Build Your Own CRM, Matched to How You Actually Sell

Most CRM platforms rent you the same generic tables (contacts, deals, tasks) for anywhere from $15 to
$300 a user a month, then charge more as the list grows, and still do not quite match how this
particular business sells. This skill has the AI interview the sales process first, then build a CRM in
Airtable or Google Sheets that fits it: contacts, companies, deals, a pipeline, and follow-up discipline,
for about $0 to $20 a month. It is owned by the business, every row can be exported any time.

Honest note: this is the CRM core (data, pipeline, and follow-up views). It is not a dialer, an email
sender, or a marketing platform, but it is built so those tools can plug into it later through
automation. The business still has to enter accurate data and work the views daily. The AI builds and
maintains the structure, not the sales discipline.

## Staying up to date (quick version check)

**This skill is version 1.0.** Finding Land keeps improving these skills. When you (the AI assistant)
first use this skill in a conversation, do a fast version check, then get on with the job:

1. Fetch `https://raw.githubusercontent.com/FindingLand/claude-re-skills/main/crmbuilder/version.txt` (one
   line: the latest version number).
2. If that number is higher than 1.0, tell the user once, in one line: "A newer version of the crmbuilder
   skill (X) is out, free at findingland.help/free-resources. Want to grab it?"
3. If the fetch fails or there is no internet, skip this silently.

Do it at most once per conversation, and never block the real work on it.

## Step 1: interview the sales process before building anything

This is the step that separates a CRM people actually use from a template nobody opens after week one.
Do not skip it and do not let the user skip it by saying "just give me a standard CRM." There is no
standard sales process, so there is no standard CRM. Ask, in plain conversation, and push past the first
answer if it sounds aspirational rather than real:

- **How does a lead or prospect actually reach you today?** Referral, inbound form, cold outreach,
  walk-in, marketplace, phone call. List every real channel, not the one the owner wishes was the main one.
- **What does a "deal" look like here?** A single sale closed in one call, a multi-week B2B sales cycle,
  a subscription signup, a project quote, a repeat order from an existing account. This decides how much
  pipeline machinery is even worth building.
- **What are the stages that actually exist, in this business's own words?** Ask them to describe, from
  memory, what happens between "never heard of us" and "paid." Write down their words, not a textbook
  pipeline. If they cannot name a stage, it probably does not need to be a field.
- **Who works a deal, and from first contact to close, does it change hands?** One person doing
  everything is a different CRM than a rep handing off to an account manager who hands off to support.
- **What tool runs this today?** A spreadsheet, a notebook, sticky notes, email search, another CRM
  they are unhappy with. If there is an existing spreadsheet, plan to import it (see below) instead of
  starting from zero.
- **What is the one thing that keeps slipping through the cracks?** Almost always the answer is
  "following up." Design around fixing that specific thing, it is usually the single highest-value part
  of this whole build.
- **Does more than one person need access, and do they need to see only their own records or
  everyone's?** This decides whether "views per role" matters on day one or can wait.

Write the answers down in plain language before touching Airtable or Sheets. The table structure below
is a starting shape, not a fixed spec. If the interview turns up a business that sells one thing to one
type of buyer in one call, the whole CRM might reasonably be two tables, not four.

## What it builds

1. **Contacts** table: name, phone, email, role/title, company (linked), source, stage, owner, last
   contact date, next action, next action date, tags, notes.
2. **Companies** table (skip this table entirely for a business that sells to individuals, not
   organizations): name, industry, website, size, linked contacts, linked deals, notes.
3. **Deals / Pipeline** table: deal name, stage, value, expected close date, linked contact, linked
   company, owner, source, notes.
4. **Activities** table, optional, add only if the business wants a logged history: calls, emails,
   meetings, notes, each timestamped and linked to a contact or deal. Skip this at first for a small
   team that will just use the notes field; add it later if "what did we say to this person" becomes a
   real recurring question.
5. **Views that make it usable:** a pipeline kanban grouped by stage, "Follow-ups due today", "New leads
   to work", "Went quiet" (no contact in some interview-derived number of days), and one filtered view
   per person or role who needs to see only their own slice.
6. **Light, safe formulas only:** days since last contact, an overdue flag on next action date, and a
   deal value roll-up per stage. Nothing that sends anything. Sending email, texts, or any multi-step
   logic belongs in an automation tool, never inside the spreadsheet or base itself.

## Airtable or Google Sheets: which one

Ask directly, or infer from what came up in the interview:

- **Airtable** when there is more than one linked relationship to track (contacts to companies to
  deals), when a kanban pipeline view matters, when more than a couple of people will use it, or when
  automations will eventually read from or write to it. Free tier covers up to 1,000 records per base,
  which is plenty to start.
- **Google Sheets** when the business is one person or a very small team, the data is genuinely flat
  (a single list of contacts with a stage column is enough), the owner already lives in Sheets and does
  not want to learn a new tool, or budget is zero and will stay zero. Sheets can still get a helper-tab
  pipeline summary and conditional formatting for overdue follow-ups, just without true linked records
  or a native kanban view.
- **Do not build in both.** Pick one source of truth. A CRM that is half in a sheet and half in Airtable
  is worse than either alone, because nobody knows which one is current.

## Set pipeline stages from the interview, not from a template

Resist the urge to hand over a generic pipeline like "Lead, Qualified, Proposal, Negotiation, Closed."
It sounds right and is wrong more often than not. Use the stages the business described in the
interview, tighten the wording, and cap it at five to seven stages. More than that and nobody updates
the field honestly; salespeople will just leave a deal parked in whatever stage is easiest to click.
One single-select "Stage" field per deal, in that order, is enough. If the business genuinely runs two
different kinds of deals (new business versus renewal, product versus service), split them with a "Deal
type" field and a view filter, not with two separate pipeline fields or two separate bases. Two pipelines
is where CRMs get messy and the numbers stop adding up.

## Field practices that keep data clean

- **Every relationship is a linked record, never typed text.** A contact links to its company and its
  deals. A typed-in company name drifts ("Acme", "Acme Inc", "acme co") and duplicates; a linked record
  stays one source of truth.
- **One "Source" single-select**, built from the channels named in the interview, so the business can
  actually see which channel produces paying customers. Free text here makes that reporting impossible.
- **Dates are date fields, phones are phone fields, money is currency fields.** Correct field types now
  save hours of cleanup later and make formulas and any future automation reliable.
- **"Next action" plus "Next action date" on every open contact and every open deal.** This pair is the
  single most valuable thing in the whole CRM. It is what turns "check the pipeline" into "here is
  exactly who to call today."

## Next action date discipline

Every open record, contact or deal, gets a Next Action (what to do) and a Next Action Date (when). Build
a view filtered to "Next Action Date is on or before today" and sort it oldest first: this is the
overdue list, and it should be the first thing anyone working the pipeline opens each morning. Build a
second view for "Next Action Date is empty" on any record whose stage is not closed, this catches deals
that quietly fell out of the habit. A record with no next action and no date is not being worked, it is
just sitting there.

## Views per role

If the interview turned up more than one person touching the pipeline, build one filtered view per
person or role, not one shared view everyone scrolls through. A rep's view shows only their own open
deals and contacts. A manager's view shows everyone's, plus the overdue list and the stage roll-up. An
account-management or support view, if that handoff exists, shows only deals past "closed won." Filtered
views cost nothing extra in Airtable and keep each person looking at exactly what they need to work, no
more scrolling past someone else's fifty leads to find your own three.

## How it gets built (the AI does the heavy lifting)

1. Run the interview above and write down the plain-language answers before building anything.
2. Create a free Airtable account and a new base (or a new Google Sheet, per the decision above).
3. In Airtable: create the tables, fields, and linked-record relationships through the Airtable API in
   one pass, using the field practices above. In Sheets: build the tabs, header rows, data validation
   for the Stage and Source columns, and conditional formatting for overdue next-action dates.
4. Add the views: pipeline kanban, follow-ups due today, next-action-empty, went quiet, and one view per
   role if that applies. Add the roll-up and overdue-flag formulas.
5. Point real lead sources at it: a web form, an automation-tool webhook (n8n, Zapier, Make), or a
   one-time import of the business's existing spreadsheet (see below).
6. Walk the business through the daily habit: work the overdue view first, update stage and next action
   the moment anything changes, never let a deal sit with no next action date.

## Importing existing spreadsheet data without wrecking it

Most of these builds start from an existing messy spreadsheet, not a blank base, and this is the step
where data gets silently lost if it is rushed.

1. Get a copy of the existing file first and do not touch the original. Work from the copy.
2. Map the old columns to the new clean fields before importing anything. Messy exports are normal:
   "Company" and "Business Name" and "Employer" might all mean the same field, one phone column might
   have three numbers separated by commas, a "Status" column might use five different spellings for the
   same stage. The AI should build the mapping and clean it, not just import the mess as-is.
3. Import companies first, then contacts (linking them to companies), then deals (linking them to both).
   Importing in the wrong order breaks the links.
4. Spot-check at least ten imported records against the original file by hand before trusting the new
   system. Check names, phone numbers, and stage in particular, those are the fields most likely to have
   drifted during a copy-paste history.
5. Keep the old spreadsheet read-only and untouched for at least 30 days as a safety net. Do not delete
   it just because the import looked clean.

## Start minimal

Build the smallest CRM that matches what the interview turned up, not the biggest one that might someday
be useful. A one-person service business selling one thing does not need a Companies table, an
Activities table, or five owner-filtered views, it needs a Contacts table with a stage field and a next
action date. Add a table, a field, or a view only when a real, repeated need shows up in how the
business actually works, never because "a real CRM should have this." A lean CRM that gets updated every
day beats a complete one that gets abandoned in a month. It is much easier to add a table later than to
convince someone to keep filling in eight fields they never look at.

## Automation-ready field design

Design fields now so an automation tool can read and write them later without a rebuild:

- Keep single-select values short, consistent, and spelled exactly one way (a script matching text
  breaks on "Closed Won" versus "closed won" versus "Closed-Won").
- If anything (a webhook, a script, an automation) will write into a table whose field names might get
  renamed later, have it reference fields by field ID, not field name. Field IDs stay stable, field names
  do not, and a renamed column silently breaks every automation that wrote to it by name.
- Keep one clean "Source" and one clean "Stage" field per record; automations and reporting both depend
  on these being reliable single-select values, not free text.
- Do not build multi-step logic (send this email, then wait three days, then check for a reply) inside
  Airtable or Sheets automations. Keep the base or sheet as data plus views, and put branching logic in
  an actual automation tool. Airtable's own automations are capped and cannot really branch or wait for a
  reply, so anything more than "set a field when a record is created" belongs elsewhere.

## What it costs

Airtable is free for small bases (up to 1,000 records, plenty to start), or about $20 a user a month on
a paid plan for bigger volume, more automation runs, or more collaborators. Google Sheets is free with
any Google account. Compare either to $15 to $300 a user a month for a hosted CRM platform, often with
data that is hard to fully export if the business ever wants to leave.

## Gotchas (save yourself the headache)

1. **Linked records, not typed text.** This is the single most common mistake, and it is the one that
   quietly poisons every report built on top of the data later.
2. **Do not run action automations inside the CRM tool itself.** Keep Airtable or Sheets as data plus
   views, and send email, texts, or any multi-step logic from a real automation tool. Data in one place,
   actions in another.
3. **Watch billable seats on a paid Airtable plan.** Give a teammate or a client the lowest access level
   they actually need, or a shared view, instead of a full editor seat, so nobody silently adds a paid
   seat that was never needed.
4. **Derived values are formulas, not typed in by hand.** Days since last contact, an overdue flag, a
   stage roll-up: compute these, never hand-type them, or they go stale the moment anyone stops updating
   them manually.
5. **A pipeline field only stays honest if it has few enough stages that updating it is a five-second
   decision.** The moment updating stage feels like work, people stop doing it and the pipeline view
   becomes fiction.
6. **Do not build a pipeline before the interview.** A CRM built from a template instead of from how this
   business actually sells gets half-adopted at best. The interview step is not optional overhead, it is
   the actual value of this whole exercise.

## Quick checklist

1. Interview the sales process: lead sources, what a deal looks like, real stage names, who works a deal,
   current tool, and the one thing that keeps slipping.
2. Pick Airtable or Google Sheets based on that interview, not by default.
3. Build the minimal table set that matches reality: Contacts always, Companies and Deals when the
   business actually has them, Activities only if a logged history is a real need.
4. Set the pipeline stages from the business's own words, five to seven of them, one single-select field.
5. Add the views: pipeline kanban, follow-ups due today, next-action-empty, went quiet, and one per role
   if more than one person works the pipeline.
6. Import existing spreadsheet data carefully (companies, then contacts, then deals), spot-check it, and
   keep the old file read-only for 30 days.
7. Work the overdue-follow-up view every day. Add fields or tables later only when a real need shows up.

---

*Built and battle-tested by [Finding Land](https://findingland.help), who build AI automations for companies of any size. This skill is free. If you would rather have it built for you, done for you and wired to your tools, [get in touch](https://findingland.help/contact-us.html).*
