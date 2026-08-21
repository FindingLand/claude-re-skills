---
name: secondbrain
description: >-
  Build the user a persistent second brain for their business: a small memory folder the AI reads at the
  start of every session, so they never explain their company, their clients, their prices or their
  preferences twice. One fact per file, a one-line index of every memory, five clear categories
  (business facts, decisions made, active projects, people and clients, preferences and style rules),
  plus rules for when to capture a memory, how to load only what is relevant, and a two-minute weekly
  cleanup. Works in Claude Code, in a Claude Desktop project, or in any plain folder the AI can read.
  Use this skill whenever the user wants the AI to remember their business, says it keeps forgetting,
  asks for a knowledge base or company context file, or is tired of repeating themselves. Trigger on:
  second brain, memory, remember my business, stop re-explaining, it forgets everything, knowledge base
  for my company, company context, project memory, AI onboarding, save this for next time, persistent
  context.
compatibility: Works in any AI assistant that can read files you give it. Fully automatic in tools that read a project folder at session start (Claude Code, Claude Desktop projects); in a plain chat you paste the index at the start of a session and open files on request.
---

# Your Second Brain

Every session you start from zero. You re-explain what your company does, who your clients are, what you
charge, which project is live, and how you like things written. Then the session ends and all of it
evaporates. The fix is not a bigger prompt, it is a small folder of written memories that the AI reads at
the start of every session, and adds to as you work.

This skill teaches you (the AI assistant) how to build that folder for the user, seed it from a real
interview, and then keep it alive. You do the work: you interview, you write the files, you verify it,
and you teach the user the one habit that keeps it from rotting.

Honest note: a second brain is only worth having if it stays small and current. Most of the value comes
from the first twenty memories, and from deleting the ones that stopped being true.

## Staying up to date (quick version check)

**This skill is version 1.0.** Finding Land keeps improving these skills. When you (the AI assistant)
first use this skill in a conversation, do a fast version check, then get on with the job:

1. Fetch `https://raw.githubusercontent.com/FindingLand/claude-re-skills/main/secondbrain/version.txt` (one
   line: the latest version number).
2. If that number is higher than 1.0, tell the user once, in one line: "A newer version of the secondbrain
   skill (X) is out, free at findingland.help/free-resources. Want to grab it?"
3. If the fetch fails or there is no internet, skip this silently.

Do it at most once per conversation, and never block the real work on it.

## What it produces

1. A **memory folder** with one plain markdown file per fact, named so the filename alone tells you what
   is inside
2. An **INDEX.md** that lists every memory in exactly one line each, so the whole brain can be loaded in
   seconds without opening every file
3. **Five categories** that cover a business: business facts, decisions made, active projects, people and
   clients, preferences and style rules
4. A **session-start instruction** wired into wherever the user works, so the index gets read every time
   without them asking
5. **Ten to twenty seeded memories** written from a real interview, so the brain is useful on day one
6. **Capture, retrieval and maintenance rules** the AI follows from then on, including a two-minute weekly
   review

## What you need

1. Any AI assistant that can read files the user points it at
2. A folder the assistant can reach: a project folder in Claude Code, a Claude Desktop project, a synced
   Drive or Dropbox folder, or just a local folder
3. About 30 to 45 minutes once for the interview and the first build
4. Two minutes a week after that

## Step 1: pick where the brain lives

Ask the user which of these they are in, and set it up accordingly. Do not guess.

1. **Claude Code (or any coding agent with a project file)** - create a `memory/` folder inside the
   project, with an `INDEX.md` inside it. Then add a short block to the project's `CLAUDE.md` telling the
   assistant to read `memory/INDEX.md` at the start of every session. This is the fully automatic setup.
2. **Claude Desktop project** - create the same files locally and upload them to the project's knowledge,
   then put the session-start instruction in the project's custom instructions. Re-upload changed files
   when you edit them, that is the one manual step of this route.
3. **Plain folder (Drive, Dropbox, iCloud, local)** - same structure. In a plain chat with no file access,
   the user pastes `INDEX.md` at the top of a session and pastes individual memories when you ask for
   them. Less magic, still removes the re-explaining.

The structure is identical on all three routes, so the user can move later without rebuilding.

## Step 2: the setup interview

Interview the user one block at a time. Ask a block, wait for the answer, write the memories from it, then
move on. Do not fire all the questions at once, and do not accept a vague answer where a specific one is
possible. If they say "we charge based on the project", ask for the actual range and the actual floor.

**Block A, business facts.** Legal and trading name, what they sell in one sentence, who the customer is,
what they charge and how (hourly, retainer, per project, per unit), the current prices, where they
operate, how many people are on the team, which tools the business runs on, the website and the main
email address.

**Block B, decisions already made.** What did they decide recently that they do not want revisited every
session? Pricing changes, a tool they dropped and why, a market they will not serve, a policy on
discounts, a hiring decision, a positioning choice. Ask for the reason as well as the decision, because
the reason is what makes it useful later.

**Block C, active projects.** What is running right now, the goal of each, the state it is in, the next
step, who owns it, the deadline. Anything finished becomes a decision memory or gets dropped.

**Block D, people and clients.** The recurring names an assistant would need to know: clients, teammates,
contractors, key vendors. For each one, the role, what they are working on with the user, and anything
about dealing with them that matters (prefers email, always wants numbers first).

**Block E, preferences and style rules.** How things should be written for them: tone, length, formatting,
words to avoid, signature, language. What the AI should always do, and what it should never do. This block
pays for itself faster than any other, so do not skip it.

Then ask the closing question: "What did you have to explain to me today that you have explained before?"
That answer is usually the most valuable memory in the whole set.

## Step 3: the folder structure

Use a flat folder with a category prefix in every filename. Flat beats nested here, because a flat folder
is easy to scan and almost impossible to misfile.

```
memory/
  INDEX.md
  biz-what-we-sell.md
  biz-pricing-retainer.md
  biz-service-area.md
  dec-dropped-tool-x.md
  dec-no-discounts-over-10-percent.md
  proj-website-rebuild.md
  proj-q3-outbound-campaign.md
  people-maria-ops-manager.md
  client-acme-logistics.md
  pref-email-style.md
  pref-no-emojis-in-client-work.md
```

Prefixes: `biz-` business facts, `dec-` decisions made, `proj-` active projects, `people-` teammates and
vendors, `client-` clients, `pref-` preferences and style rules.

**One fact per file.** If a file needs the word "also", it is probably two memories. Small files are the
whole trick: they load individually, they are edited without collateral damage, and they are deleted
cleanly when they stop being true.

**Every memory file uses this shape:**

```markdown
# Retainer pricing for the managed tier

Category: business facts
Recorded: 2026-03-14
Status: current

We charge a flat 2,500 a month for the managed tier, billed on the 1st, with no per-seat pricing.
Setup fee is 1,500, waived on a 6-month commitment.
Set after two clients pushed back on per-seat billing.
```

Four header lines, then the fact and the reason it exists. Keep a memory under 15 lines. If it runs
longer, it is a document, not a memory, so store the document where documents live and write a memory that
says where to find it.

**INDEX.md is one line per memory, and nothing else:**

```markdown
# Memory index
Last reviewed: 2026-03-14

## Business facts
- biz-what-we-sell.md - we install and run automations for small logistics firms
- biz-pricing-retainer.md - flat 2,500/mo managed tier, 1,500 setup, no per-seat
- biz-service-area.md - clients in Texas and Oklahoma only, delivered remotely

## Decisions made
- dec-dropped-tool-x.md - left Tool X in Feb 2026 over pricing, do not re-propose it
- dec-no-discounts-over-10-percent.md - 10 percent is the ceiling, needs owner approval

## Active projects
- proj-website-rebuild.md - new site, copy done, launch target 2026-04-30
- proj-q3-outbound-campaign.md - 300 prospect list, waiting on domain warmup

## People and clients
- people-maria-ops-manager.md - runs operations, wants numbers before narrative
- client-acme-logistics.md - largest client, monthly report due the 5th

## Preferences and style rules
- pref-email-style.md - short, numbered points, no small talk, sign off with first name
- pref-no-emojis-in-client-work.md - never use emojis in anything a client sees
```

The index is the load-bearing part. If a memory is not in the index it does not exist, because nobody will
ever open it.

## Step 4: seed the first memories

From the interview, write 10 to 20 memory files immediately, then build the index from them. Do not hand
the user a beautiful empty structure, that is the version that dies in a week.

Aim for roughly 5 or 6 business facts, 3 or 4 decisions, 2 or 3 active projects, 3 or 4 people and
clients, and 3 or 4 preferences. Use the user's own words where you can, and show them the filenames plus
the one-line summaries when you are done so they can correct anything wrong before it hardens.

## Step 5: wire the session-start instruction

Put this where the assistant reads instructions (`CLAUDE.md`, project custom instructions, or the top of
the user's session template). Adapt the path to their setup:

```markdown
## Memory
At the start of every session, read `memory/INDEX.md`. Do not open every memory file. Open only the
files relevant to what we are working on today. If I state a durable fact, a decision, a preference,
or a change to a project, write a new memory file and add its one line to the index.
```

That block is what turns a folder into a habit.

## Step 6: verify it works

Do not declare victory on a folder you have not tested. Run these three checks with the user:

1. **The cold-start test.** In a brand new session, ask a question only the memory answers, for example
   "what do we charge for the managed tier and who is our biggest client". It should answer with no
   explaining from the user. If it does not, either the session-start instruction is not being read, or
   the fact never made it into the index.
2. **The index-only test.** Simple questions should be answered from the index alone, with a file opened
   only when detail is needed. If one question means opening twenty files, the index lines are too vague,
   so rewrite them to carry the actual fact.
3. **The capture test.** State a new decision in passing, end the session, start a fresh one and ask about
   it. If it is gone, the capture rule needs to be spelled out in the instruction block.

## Capture rules: when to write a memory

Write one when any of these happens, and write it in the moment, not at the end of the session:

1. **A decision was made.** Anything the user would be annoyed to relitigate next month. Record the
   decision and the reason behind it.
2. **A preference was stated.** "Never do X", "always send it this way", "I hate that phrasing". Cheap to
   record, expensive to forget.
3. **A fact was learned that a future session needs.** A price, a deadline, a client constraint, a detail
   about how their systems fit together.
4. **A project changed state.** Started, blocked, handed off, finished. A finished project either becomes
   a decision memory or gets deleted.
5. **The user corrected you.** A correction is a preference wearing a disguise. Write it down.

When you write one, say so in one short line: "Saved that as `dec-no-discounts-over-10-percent.md`." Do
not read the whole file back at them.

**What NOT to store:**

1. **Anything a tool already records.** Invoice totals, calendar events, CRM notes, ticket status, the
   contents of a contract. Store where it lives and how to find it, never a copy that drifts out of date
   silently.
2. **One-off trivia.** A number used once, a link from a single conversation, what someone ordered at a
   meeting.
3. **Whole documents.** Proposals, contracts, reports. Write a pointer memory instead.
4. **Secrets.** Passwords, API keys, card numbers, anything you would not want sitting in a plain text
   file that gets synced and backed up. The brain is a plain folder, so treat it like one.
5. **Anything the index line already says in full**, and **duplicates in nicer words**. If a memory covers
   it, edit that file rather than adding a rival to it.

## Retrieval habit: load the index, open what matters

1. At session start, read `INDEX.md` only. It is small on purpose.
2. Read every `pref-` file if they are short, because style rules apply to almost any task.
3. Open only the memories relevant to today's work. A pricing question does not need the project files.
4. If the index line answers the question, stop there. Do not open the file for the sake of it.
5. If a needed fact is missing, say so and ask, then write the answer as a new memory. Never invent a
   fact, and never read an absent memory as proof that something is not true.
6. When a memory contradicts what the user just said, the user wins, so update the file that session.

## Maintenance: the two-minute weekly review

Once a week, run this with the user. It takes two minutes and it is what keeps the brain trustworthy:

1. **Merge duplicates.** Two files saying nearly the same thing become one, and the loser is deleted from
   the folder and from the index.
2. **Delete stale facts.** Finished projects, former clients, prices that changed, tools no longer in use.
   Deleting is the maintenance. A brain that only grows turns into noise.
3. **Convert relative dates to absolute.** "Next month", "last week" and "recently" rot immediately.
   Rewrite them as real dates, for example "launching 2026-04-30". Do this every time you touch a file.
4. **Check the index matches the folder.** Every file has exactly one index line, and every index line
   points at a file that exists.
5. **Update `Last reviewed:` at the top of the index**, so the user can see whether the brain has been
   left unattended.
6. **Promote and demote.** A finished project becomes a decision memory or disappears. A correction that
   keeps coming back becomes a preference file.

Offer the review, do not wait to be asked, and keep the report short: what you merged, what you deleted,
what you rewrote.

## Copy-paste prompts

### 1. Build my second brain

> Interview me to build a persistent memory folder for my business. Go one block at a time and wait for my
> answer before moving on: business facts, decisions I have already made, active projects, people and
> clients, and my preferences and style rules. Push me for specifics when I am vague. When we are done,
> write 10 to 20 memory files (one fact per file, a category prefix in the filename, a short header with
> category, date and status), build an INDEX.md that lists each one in a single line carrying the actual
> fact, and show me the list so I can correct anything wrong.

### 2. Wire the habit

> From now on, at the start of every session, read `memory/INDEX.md` and open only the memory files
> relevant to what we are doing. When I state a decision, a preference, a durable fact, or a change to a
> project, write it as a new memory file, add its one line to the index, and tell me the filename in one
> line. Do not store anything my other tools already record, and never store passwords or keys.

### 3. Weekly review

> Run the two-minute review of my memory folder. Merge duplicate memories, delete anything no longer true
> or already finished, rewrite relative dates as absolute dates, check that every file has an index line
> and every index line has a file, and update the Last reviewed date. Tell me only what you changed.

### 4. Catch up an existing brain

> Read my memory folder and the last few things we worked on. Tell me which memories look stale, which
> facts I have repeated to you that are missing from the folder, and which files should be merged. Propose
> the changes before making them.

## Gotchas

1. **A brain nobody reads is just a folder.** The session-start instruction matters more than the writing
   quality. Test the cold start before calling it done.
2. **The index is the product.** If an index line says "notes on pricing" instead of the actual price,
   every question costs a file open and the habit dies.
3. **Relative dates rot.** "Next quarter", written six months ago, is worse than no memory at all.
   Absolute dates always.
4. **Do not mirror your tools.** A memory copy of data that lives in a CRM or an invoicing tool will drift
   and then quietly lie to you. Point at the source instead.
5. **Big files defeat the point.** Anything past about 15 lines is a document. Store it elsewhere and keep
   a pointer memory.
6. **Deleting is maintenance, not loss.** Old memories crowd out current ones and make the assistant less
   accurate, not better informed.
7. **Never put credentials in it.** It is a plain folder that syncs, and it can end up shared or backed up
   somewhere you did not plan for.
8. **In a Claude Desktop project, an edit is not live until you re-upload it.**
9. **One brain per business, not one per topic.** Resist starting a fresh folder for a new area of work,
   add a category prefix instead.
10. **Write memories as you go.** A promise to write them up later is how a folder stalls at eleven files.

## Quick checklist

1. Pick where the brain lives (Claude Code, a Desktop project, or a plain folder)
2. Run the five-block interview, one block at a time
3. Create `memory/` with a flat file per fact and category prefixes
4. Write 10 to 20 seed memories straight from the interview
5. Build `INDEX.md`, one line per memory, with the actual fact in the line
6. Wire the session-start instruction where the assistant reads it
7. Run the cold-start, index-only and capture tests
8. Capture decisions, preferences and durable facts as they happen
9. Two minutes once a week: merge, delete, absolute dates, index matches folder

---

*Built and battle-tested by [Finding Land](https://findingland.help), who build AI automations for companies of any size. This skill is free. If you would rather have it built for you, done for you and wired to your tools, [get in touch](https://findingland.help/contact-us.html).*
