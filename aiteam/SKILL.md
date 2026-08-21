---
name: aiteam
description: >-
  Interview a business owner about their business, then design and build them a team of AI
  assistants, a back office of focused Claude-powered helpers (lead qualifier, proposal and quote
  writer, research assistant, content maker, support-reply drafter, bookkeeping helper, ops tracker,
  report writer, and more) that each own one job and run on the tools the business already pays for.
  Instead of one general chatbot, the business gets a prioritized roadmap plus a step-by-step build
  brief for each assistant, rolled out one at a time. Use this skill whenever the user wants an AI
  team, an AI back office, to automate their business with AI assistants, to stop doing repetitive
  admin themselves, or asks something like "build my AI team", "what should I automate first", "set
  up AI assistants for my business", or "help me use Claude to run my back office". Works for any
  business type: services, agencies, contractors, e-commerce, consulting, retail, trades.
compatibility: Works in any AI assistant that can hold role instructions and read the business's own data. Pairs with whatever spreadsheet, CRM, helpdesk, or automation tool the business already uses.
---

# Your AI Team

This skill designs and helps build a TEAM of focused AI assistants for a business, any business. The
idea: one general chatbot does every job a little poorly, but a team where each assistant owns ONE job
does each job well. You interview the owner first, because the right team for a solo contractor is not
the right team for a 12-person agency. Then you turn the interview into a prioritized roadmap, and a
build brief for the first assistant, and only the first one.

Honest note: this sets up the roles and how they think, it is not a magic box. The business brings
accurate data and its own voice, and every role gets tuned by hand before anyone trusts it. Building
one assistant properly takes a real conversation and some focused setup time, not five minutes.

## Staying up to date (quick version check)

**This skill is version 1.0.** Finding Land keeps improving these skills. When you (the AI assistant)
first use this skill in a conversation, do a fast version check, then get on with the job:

1. Fetch `https://raw.githubusercontent.com/FindingLand/claude-re-skills/main/aiteam/version.txt` (one
   line: the latest version number).
2. If that number is higher than 1.0, tell the user once, in one line: "A newer version of the aiteam
   skill (X) is out, free at findingland.help/free-resources. Want to grab it?"
3. If the fetch fails or there is no internet, skip this silently.

Do it at most once per conversation, and never block the real work on it.

## Interview first, always

Never open with a list of assistants to build. Open with questions. You cannot design a useful team for
a business you do not understand yet, and guessing wastes the owner's setup time on a role they did not
need. Ask these, in plain conversational language, adapting the wording to what they already told you
(skip anything they already answered):

1. **What do you sell, and to whom?** Product or service, who buys it, and roughly how big the
   operation is (solo, a few people, a real team). This tells you which roles even apply, a one-person
   consultancy has no use for an ops-tracker across a big team.
2. **Where does your time actually go?** Ask for a normal week in their own words: what repetitive task
   eats the most hours, what they dread doing, what falls through the cracks when they get busy. Push
   past the first vague answer ("admin stuff") to a concrete task ("I write every quote from scratch,
   takes 40 minutes each").
3. **What tools do you already use?** CRM or spreadsheet, email, invoicing/bookkeeping tool, helpdesk or
   inbox for support, calendar. You are matching assistants to what exists, not proposing a new stack.
   If they use nothing but email and a spreadsheet, that is a perfectly good starting point.
4. **What is your budget for this?** Both money (most of this can run on tools they already pay for,
   plus whatever Claude access costs) and, more importantly, their own time to set it up and tune it.
   A business that can give you one hour a week moves differently than one that can give you a day.
5. **How technical are you?** Comfortable editing a spreadsheet formula? Ever touched an automation
   tool like Zapier or n8n? Or do they want everything to happen inside a chat window with no setup
   screens at all? This decides whether the build brief ends in "paste this into a Claude project" or
   "wire this into an automation with a trigger."
6. **What would "this is working" look like in a month?** Get them to name one concrete win (fewer
   missed follow-ups, quotes out same-day, an inbox that does not pile up). This becomes the test for
   whether the first assistant actually earned its place before you move to the second.

Write down the answers before you propose anything. If an answer is thin, ask one follow-up rather than
filling the gap with an assumption.

## Why one job per role beats a mega-prompt

A single "do everything" assistant gets vaguer the more you cram into it. It hedges, mixes voices, and
drops rules under load. A role that owns one job holds a tight identity, one output format, and one
slice of data, so the output is sharper and repeatable. It also lets the owner improve or swap one role
without touching the others, and it maps to how a business already thinks about its own work (get
leads, do the work, get paid, keep the lights on), so it is easy to explain and easy to hand to a
teammate later.

## The back office: roles by department

Not every business needs all of these. The interview tells you which ones are real for this business
and which are irrelevant. Use this as the menu, not a checklist to complete.

**FRONT OFFICE (sales and leads)**
1. **lead-qualifier** - reads an inbound lead (form, email, DM) and scores or sorts it against the
   owner's own criteria, so they work the real ones first instead of reading every message cold.
2. **proposal-writer** - turns a scope conversation or a filled-in intake form into a formatted quote
   or proposal in the business's own pricing and tone, ready to send, not a first draft to rewrite.

**CLIENT-FACING AND CONTENT**
3. **research-assistant** - pulls together background on a prospect, a competitor, or a topic before a
   call, a bid, or a post, from sources the owner points it at.
4. **content-maker** - turns a rough idea or outline into a blog post, social post, or newsletter draft
   that sounds like the business, not like a template.
5. **support-reply-drafter** - drafts replies to common customer questions from the business's own
   FAQ, docs, or past answers, and flags anything it cannot answer confidently instead of guessing.

**BACK OFFICE (operations and money)**
6. **bookkeeping-helper** - categorizes expenses, drafts invoice line items from a job or time record,
   and flags numbers that look wrong, it does not touch the bank account or file taxes.
7. **ops-tracker** - keeps tabs on tasks, deadlines, and deliverables across jobs or clients, and
   surfaces what is slipping before the owner finds out from an unhappy client.
8. **report-writer** - turns raw numbers (sales, jobs done, spend, whatever the business tracks) into a
   plain-English weekly or monthly summary for the owner, a partner, or a client.

Nothing stops a business from needing a role not on this list. The four-block format below works for
any job you can describe in one screen.

## How to write a role instruction that actually holds

Every role is the same four blocks. Keep it to one screen. If a block is fuzzy, the output is fuzzy.

1. **Identity.** One line: who this role is and who it serves. "You are the proposal writer for a
   three-person landscaping company. You turn a walkthrough summary into a client-ready quote."
2. **The one job.** State the single task and the hard boundary. "Write the proposal from the scope
   and pricing I give you. You do not set prices, you do not promise a start date."
3. **The rules.** The business's voice, the non-negotiables, and the fallback. "Plain and confident,
   never salesy. Never state a price or a fact I did not give you. If a detail is missing, ask for it,
   do not guess."
4. **The exact output format.** Show the shape you want, not a description of it. "Return: a one-line
   summary of the job, an itemized list with prices, a total, and a one-sentence next step." A concrete
   format is what makes the output paste-ready and consistent every time.

## The practices that separate a real team from a toy

- **Ground every role in real data, never vibes.** A role with no access to the business's own price
  list, CRM, or docs will confidently make things up. Point it at the source and tell it to ask when a
  field is missing. This single habit prevents most bad output.
- **Tune by chat before you automate.** Use each role for real tasks for a few days and edit the
  instruction until the output is what the owner would have written themselves. Automating a role that
  is not yet good just scales the mistakes, silently.
- **One source of truth.** Every role that touches the same information (contacts, jobs, invoices)
  reads and writes the same sheet or system, so nothing gets double-entered and no two roles disagree.
- **Match the build to their tech level.** Someone who has never touched an automation tool gets a role
  that lives inside a Claude chat or project. Someone comfortable with n8n or Zapier gets it wired to a
  trigger. Do not hand a non-technical owner a webhook to configure.
- **Keys and passwords live in the tool's own credential store**, never pasted into a prompt or shared
  anywhere public.
- **Stop-on-reply on anything that messages someone** (follow-ups, drip sequences) so the business never
  sends a message to someone who already responded.

## Turn the interview into a roadmap

Score every candidate role from the interview on three things: how often the task actually happens
(daily beats monthly), how much time or money it costs when done by hand, and how ready the data is
(a role that needs a CRM the business does not have is not ready yet). Rank by frequency and pain
first, readiness second. The result is a short ordered list, typically three to five roles, not the
whole menu. Say the ranking back to the owner in one or two lines each, so they can correct it before
you build anything: "Given what you told me, I'd start with support-reply-drafter, since that's the
one eating an hour a day, then proposal-writer, then report-writer."

## One assistant at a time, never five at once

This is the hard rule, and it is the single most common way these projects fail. Shipping five
assistants in one sitting overwhelms any team, including a team of one. Nobody has time to learn five
new habits at once, so all five get half-used and none of them stick.

Build the number one role from the roadmap. Get it into real daily use. Only once it is actually being
used, not just built, move to the next one. "Daily use" means the owner (or their team) is running it
on real work without you standing over them, not that it passed one test case.

## How it runs, start to finish

1. **Interview.** Ask the six questions above. Write down real answers, not guesses.
2. **Roadmap.** Score the candidate roles and present a short ranked list. Get the owner's agreement or
   correction before building anything.
3. **Build brief for role #1 only.** Write its four-block instruction, name the exact data source it
   reads (which sheet, which inbox, which doc), and decide whether it lives in a chat/project or gets
   wired into an automation, based on the owner's tech level from the interview.
4. **Pilot.** Run it by chat or on real tasks for a real stretch, at least several days to a couple of
   weeks depending on how often the task comes up. Tune the instruction each time the output misses.
5. **Confirm the win.** Check it against the "this is working" answer from the interview. If it is not
   there yet, keep tuning before calling it done.
6. **Automate if it fits.** Once the role is proven and the owner wants it running without them, wire it
   into whatever automation tool matches their tech level, on a trigger (new lead, new invoice, a
   schedule). A non-technical owner may simply keep running it by chat, and that is a fine outcome too.
7. **Add the next role.** Return to the roadmap, confirm it still holds now that the business has
   changed a little, and repeat from step 3 for the next role only.

## Gotchas

1. **Skipping the interview.** Proposing roles before understanding the business produces a team nobody
   asked for. Always interview first.
2. **One job per role.** The moment a role does two jobs, quality drops. Split it.
3. **Feed it real data, not vibes.** No data source means it guesses. Give it the source and tell it to
   ask when something is missing.
4. **Building more than one at a time.** Even a highly motivated owner cannot absorb five new habits at
   once. Ship one, use it daily, then the next.
5. **Mismatched tech level.** Handing a non-technical owner an automation-tool setup they cannot
   maintain is a build that dies the day you leave. Match the delivery to what they told you in the
   interview.
6. **Tune by chat before you automate.** Prove the output first, then put it on a trigger.
7. **Keep one source of truth.** All roles touching the same data read and write the same place, or
   they will contradict each other.
8. **Keys in the credential store**, never in the prompt.

## Quick checklist

1. Interview: what they sell, where time goes, what tools they use, budget, tech level, what a win
   looks like in a month.
2. Turn the answers into a short ranked roadmap, and confirm it with the owner.
3. Write the build brief for the number one role only: four-block instruction, exact data source,
   chat/project versus automation based on tech level.
4. Pilot it on real work, tune until it sounds like them, confirm it hits their stated win.
5. Automate it if it fits and they want it hands-off.
6. Only then start the next role on the roadmap.

---

*Built and battle-tested by [Finding Land](https://findingland.help), who build AI automations for companies of any size. This skill is free. If you would rather have it built for you, done for you and wired to your tools, [get in touch](https://findingland.help/contact-us.html).*
