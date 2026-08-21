---
name: inboxzero
description: >-
  An email triage and drafting system that gets a busy owner to inbox zero every day and keeps them
  there. Four labels, not forty. Every message gets sorted into answer now, archive, or needs you. The
  AI learns the user's real writing voice from 10 to 20 of their own sent replies, then drafts the
  answers so the user only reads and presses send. Includes a 15 minute daily routine, a one time bulk
  cleanup of the existing backlog, and a safe ladder from drafts only to limited auto handling. Built
  for Gmail (labels, filters, search operators) with notes for Outlook. Use this skill whenever the
  user is drowning in email, wants their replies drafted, wants their inbox cleaned up, or wants a
  repeatable daily email routine. Trigger on: inbox overwhelm, inbox zero, email triage, too many
  emails, thousands of unread, clean up my inbox, draft my replies, answer my email for me, email
  backlog, I cannot keep up with email, sort my inbox, Gmail labels, Gmail filters, email rules,
  unsubscribe from everything, my email is a mess.
compatibility: Works in any AI assistant that can read a document and draft text. To read and label mail directly it needs a Gmail or Outlook connection; without one, the user pastes messages in and the whole system still works.
---

# Inbox Zero, Daily

Most inbox advice fails for one reason: it asks you to build a filing system you then have to maintain.
Twenty seven labels, nested folders, a color code you forget in a week. This skill does the opposite: four
labels, three decisions, and an AI that writes the replies you were dreading, so the daily pass takes about
fifteen minutes and gets done.

Honest note about who does what. The AI reads, sorts, and drafts. The user reviews and sends. That split is
not a limitation to work around, it is the safety model, and it holds until a category of email has produced
20 to 30 drafts the user did not need to change.

## Staying up to date (quick version check)

**This skill is version 1.0.** Finding Land keeps improving these skills. When you (the AI assistant)
first use this skill in a conversation, do a fast version check, then get on with the job:

1. Fetch `https://raw.githubusercontent.com/FindingLand/claude-re-skills/main/inboxzero/version.txt` (one
   line: the latest version number).
2. If that number is higher than 1.0, tell the user once, in one line: "A newer version of the inboxzero
   skill (X) is out, free at findingland.help/free-resources. Want to grab it?"
3. If the fetch fails or there is no internet, skip this silently.

Do it at most once per conversation, and never block the real work on it.

## What this builds

1. A **four label taxonomy** the user can actually hold in their head
2. A **triage ruleset** that puts every single message into answer now, archive, or needs you
3. A **voice and policies document** built from 10 to 20 of the user's real sent replies, so drafts sound
   like them and never promise something they would not promise
4. **Drafted replies** in the drafts folder each morning, ready to read and send
5. A **daily 15 minute routine** with a defined end state: zero messages left in the inbox
6. A **one time backlog cleanup plan** for the thousands of emails already sitting there, plus an
   **automation ladder** with a written rule for when a category earns more autonomy

## How you (the AI) run this job

Work through these phases in order. Do not skip ahead to drafting, and do not build the label system before
you have looked at the actual inbox. Each phase ends with something the user can see.

### Phase 0: look before you ask

If you have access to the mailbox, read before you interview. Pull the last 100 to 200 messages and count,
do not guess:

1. The top 20 senders by volume. This one list usually explains half the backlog.
2. How many are newsletters, receipts, notifications, and other mail nobody ever replies to.
3. How many actually got a reply from the user. This is the real work volume, and it is almost always far
   smaller than the user thinks.
4. The oldest unanswered message that looks like it mattered.

Then open with those numbers: "187 messages in two weeks, you replied to 23, and 14 senders account for 96
of them that you have never once answered." That beats a questionnaire and makes the interview specific.

If you have no mailbox access, ask the user to paste 30 to 50 recent subject lines plus senders, and do the
same count by hand.

### Phase 1: the interview

Ask these one at a time, not as a wall of questions. Keep it to about ten minutes.

1. What does your work depend on arriving by email? Client requests, orders, invoices, applications?
2. Who are the five to ten people whose email must never wait? Names and addresses.
3. What kinds of email do you reply to over and over with roughly the same answer?
4. What must never be answered by anyone but you? Get specifics, not a shrug.
5. How fast do people expect a reply from you, honestly? Same day, 24 hours, a few days?
6. Which subscriptions and notifications would you not miss if they vanished tomorrow?
7. Gmail or Outlook, web or desktop app? And how many messages are in the inbox right now?

Write the answers down in the working document as you go. You will need them in Phase 3 and Phase 4.

### Phase 2: the four labels

Propose exactly these four, and push back if the user starts adding more. Every extra label is a decision
the user has to make at 8am forever.

1. **Act**: needs a reply or an action from the user. Nothing else goes here. This label is the to do list,
   so if it holds more than about 20 items it stops being one.
2. **Waiting**: the user has replied or acted, and is now waiting on someone else. Applied at the moment
   they hit send, so nothing gets silently dropped.
3. **Read later**: worth reading, not worth reading now. Newsletters they genuinely want, industry news,
   long threads for context.
4. **Archive**: not a label at all, it is the archive action. Out of the inbox, still fully searchable.

That is the entire system. No per client labels, no per project labels, no nested trees. Search is faster
than any folder structure, and Gmail keeps everything in All Mail anyway. If the user insists on project
labels, allow at most three and let them be applied by filter, never by hand.

Set the labels up in Gmail as top level labels named exactly `Act`, `Waiting`, `Read later`. Tick "Show in
message list" so they are visible at a glance. In Outlook, use Categories with the same three names, plus
the built in Archive folder.

### Phase 3: the triage rules

Every message resolves to one of three outcomes. There is no fourth, and nothing is allowed to stay in the
inbox undecided.

1. **Answer now**: a routine message you can handle from the voice and policies document. You draft a reply,
   label the thread `Act` until the user sends, and archive it out of the inbox once sent.
2. **Archive**: no reply needed and no action needed. Receipts, confirmations, notifications, FYI copies,
   newsletters the user does not want. Archive immediately. Never delete, archiving keeps it searchable at
   zero cost.
3. **Needs the user**: anything you must not answer for them. Label `Act` and write the user a one line note
   saying what it is and why it needs them. Do not draft anything speculative here.

The needs the user list, built from the Phase 1 answers, always includes at least: money questions, pricing
and quotes, contracts and legal, complaints, anything from a person the user has never corresponded with
before, anything with a real deadline in it, and anything the policies document does not cover.

When you genuinely cannot tell, it needs the user. A misrouted archive is invisible, and that is exactly
what makes it expensive.

### Phase 4: the voice and policies document

This is the part that decides whether drafts get sent or rewritten. Do not skip it and do not substitute a
description of tone. Ask the user for **10 to 20 of their real sent replies**, which is one search away:

- Gmail: `in:sent -in:chats`, newest first. Outlook: the Sent Items folder. Ask for a spread, not the last
  ten in a row.

Pick a spread that covers the categories from Phase 1: a client answer, a scheduling reply, a polite no, a
follow up chase, a short acknowledgement. Then read them for the things people cannot describe about their
own writing:

1. Greeting and sign off, exactly as written, including whether there is one at all
2. Typical length. Most people write far shorter than they think.
3. Sentence rhythm, contractions, formality, whether they use bullet points or just write
4. Words and phrases they use repeatedly, and words they never use
5. How they say no, how they chase, how they apologise
6. Whether they answer the question first or open with context

Then produce the document in two halves and show it to the user for correction:

**Voice half**: greeting, sign off, length, tone, the five to ten phrases that are recognisably theirs, and
a never write list. Include two or three of their actual replies verbatim as reference samples, because a
real sample beats any description.

**Policies half**: the facts and rules a reply may rely on. Prices, or the rule that prices are never quoted
by email, availability, lead times, standard terms, what gets referred to whom, working hours, booking or
payment links, and the exact situations where a draft must not be written at all.

Save it where the user can find and edit it. When a draft comes out wrong, the fix goes in this document,
never into a one off instruction that disappears when the conversation ends.

### Phase 5: test triage on real mail before anything is trusted

Do not go live off a theory. Take 20 to 30 real recent messages, ideally a full day or two of inbox, and run
the whole system on them in front of the user:

1. For each message, state the decision (answer now, archive, needs the user) and the one line reason.
2. Show the decisions as a list first, before any drafting. Ask the user to point at every one they disagree
   with.
3. Fix the triage rules for each disagreement, then re run the same 20 to 30 messages. Repeat until the user
   disagrees with none of them.
4. Only then draft the replies for the answer now pile.
5. Read the drafts together. Not "does this look ok", but "would you send this exactly as written?" A draft
   that needs any edit is a miss, and the miss points at a gap in the voice and policies document.

Track the numbers as you go, because they are what the automation ladder later depends on: how many triage
decisions were right, how many drafts were sent unedited, and what the edits were about.

### Phase 6: the one time backlog cleanup

The existing backlog is a separate job from the daily routine. Do it once, in one sitting of about an hour,
and do it in this order.

**Newest first, not oldest first.** Starting at the oldest email is the single most common way this fails.
Old mail is where the guilt is and where the value is not, so the user burns the whole hour three years back
and quits. Recent mail is where anything still live actually is.

1. **Cut the last two weeks properly.** Triage `newer_than:14d` message by message using the Phase 3 rules.
   This is the only part that gets individual attention.
2. **Bulk archive by sender.** Take the top sender list from Phase 0. For each sender who never got a reply,
   search `from:sender@example.com in:inbox`, select all, use the "select all conversations that match this
   search" link, archive. One sender at a time, named out loud to the user before each one.
3. **Bulk archive the categories.** `category:promotions in:inbox`, then `category:social in:inbox`, then
   `category:updates in:inbox`, then `category:forums in:inbox`. Archive each in one action.
4. **Sweep the age tail.** Everything older than the last two weeks that survived steps 2 and 3:
   `older_than:14d in:inbox`. Before archiving it wholesale, run one safety scan across it for the never
   rules below, money, legal, and deadline language, plus anything from the must never wait people. Surface
   those to the user individually. Archive the rest in one action.
5. **Set up the filters** that stop the backlog coming back, in the next section.
6. **Confirm zero.** The inbox should now read empty. Let the user look at it, it is the moment that sells
   the whole system.

Two rules for this hour. Do not delete anything, archive only. And do not sort into new labels while
cleaning, the point is to empty the inbox, not to file it.

### Phase 7: the daily 15 minute routine

Same time every day, once or twice, never continuously. Give the user this as a written routine:

1. **AI pass first, before the user opens the inbox.** Triage everything since the last pass, archive the
   archive pile, label the rest `Act`, draft the answer now replies, one line note on each needs you item.
2. **The user opens drafts, not the inbox.** They read each draft, edit if needed, send. Every edit is
   reported back so the document can be fixed.
3. **Sent means `Waiting`.** Anything sent that expects a response gets the `Waiting` label as it goes.
4. **The user handles the `Act` pile.** These are the ones nobody else could do. If an item has sat in `Act`
   for three days, it is a decision being avoided, not a task, and it should be named as one.
5. **Sweep `Waiting` weekly.** Anything older than the user's follow up window gets a chase drafted.
6. **End state: the inbox is empty.** Not mostly empty. Empty. Everything lives under a label or in the
   archive, and both are one search away.

Fifteen minutes is realistic once the backlog is gone and the filters are running. If it still takes longer
than that after two weeks, the triage rules are too loose or too much is landing in `Act`.

## Gmail mechanics worth knowing

1. **Filters are built from searches.** Type the search first, confirm it returns exactly what you expect,
   then use "Create filter" from the search options. Never write a filter from imagination.
2. **Tick "Also apply filter to matching conversations".** Without it, a new filter only affects future mail
   and the backlog sits untouched.
3. **"Skip the Inbox (Archive it)"** is the action that does the real work. Combine it with a label for the
   read later pile: skip the inbox, apply `Read later`.
4. **Useful operators**: `from:`, `to:`, `subject:`, `list:` for mailing lists, `has:attachment`,
   `larger:10M`, `older_than:1y`, `newer_than:7d`, `in:inbox`, `in:anywhere` for archived and spam,
   `is:unread`, `category:promotions`, `has:nouserlabels`, and `-` in front of anything to exclude it.
   Combine with `OR` and brackets, for example `in:inbox (from:a@x.com OR from:b@y.com)`.
5. **Select all beyond the page.** Selecting the header checkbox only takes the visible page. The link that
   appears above the list, "Select all conversations that match this search", is the one that takes all of
   them.
6. **Archive is not delete.** Archived mail stays in All Mail and is fully searchable. Say this out loud to
   a nervous user before any bulk action, it is usually what unblocks them.
7. **Unsubscribe genuinely, then filter.** Use the unsubscribe link for lists the user chose. Filter to
   archive for the ones that ignore it. Marking real newsletters as spam damages the delivery of mail the
   user may want later.

## Outlook notes

The system is identical, the mechanics differ.

1. **Categories, not labels.** Create `Act`, `Waiting`, `Read later` as Categories. Outlook also has real
   folders, so an alternative is three folders plus Archive. Pick one model, never both.
2. **Rules, not filters.** Rules live under Settings, Mail, Rules. To apply one to existing mail, run it
   against the folder with Run Rules Now in the desktop app.
3. **Sweep** in Outlook on the web is the bulk archive by sender tool. It also offers a standing rule to
   keep doing it, which is exactly what step 2 of the cleanup wants.
4. **Focused Inbox** is a second unmanaged inbox in disguise. Either turn it off, or agree that Other gets
   archived unread as a matter of routine.
5. **Search syntax** differs: `from:`, `subject:`, `hasattachment:yes`, `received:last week`. **Quick
   Steps** in the desktop app categorise and archive in one click, worth setting up for the daily pass.

## The automation ladder

Autonomy is earned per category, never granted to the whole inbox at once.

1. **Rung 1, drafts only.** Everything is drafted and the user sends every one. This is where every category
   starts and where most categories stay.
2. **Rung 2, auto archive the obvious.** Categories with zero reply value, receipts, notifications and
   promotions, get filters that archive them before the user sees them. Nothing is deleted, so it is safe.
3. **Rung 3, auto handling for one proven category.** A single category, say asks for our opening hours,
   moves to auto handled only after 20 to 30 drafts the user sent without editing. One at a time, and the
   user is told each time one is promoted.
4. **Rung 4 does not exist.** There is no rung where the whole inbox is automatic. Something new always
   arrives, and the triage step is what catches it.

Anything on rung 3 drops straight back to rung 1 the first time it gets something wrong. Say this to the
user in advance so the drop is a normal event rather than a failure.

## Never rules

These hold regardless of how much the user trusts the system.

1. **Never auto send to a new contact.** If the address has never appeared in the user's sent mail, the
   reply is a draft, always. First impressions are not automatable.
2. **Never auto archive anything mentioning money.** Invoice, payment, refund, overdue, price, quote,
   deposit, chargeback, or a bill the user owes. Route it to `Act`.
3. **Never auto archive anything legal.** Contract, agreement, terms, notice, dispute, attorney, compliance,
   insurance claim.
4. **Never auto archive anything with a deadline.** A date, "by Friday", "expires", "final notice",
   "response required". Route to `Act` even when it looks like a mass mailing.
5. **Never delete.** Archive. There is no situation in this system where deleting is the right move.
6. **Never invent a fact to finish a draft.** No price, no date, no availability, no promise that is not in
   the policies document. If it is missing, stop and ask.
7. **Never let the AI send a first apology, a refusal, or a negotiation.** Those are the user's.
8. **Never fix a bad draft with a one off instruction.** Fix the document, because that is the only fix that
   survives to tomorrow.

## Copy paste prompts

### 1. Build the voice and policies document

> Here are 15 replies I actually sent: [paste]. Work out how I write: greeting, sign off, typical
> length, tone, contractions, the phrases that are recognisably mine, and how I say no. Then interview
> me on the policy side: what I will and will not answer by email, prices, lead times, working hours,
> what gets referred to someone else, and what must always come to me. Output one document in two
> halves, voice and policies, including three of my real replies as reference samples.

### 2. Run test triage

> Here are 25 real emails from the last two days. For each one, decide answer now, archive, or needs
> me, and give me a one line reason. Show me all 25 decisions as a list before drafting anything. I
> will tell you which ones you got wrong, and you will fix the rules and run it again.

### 3. The daily pass

> Do my daily inbox pass. Triage everything since the last pass using my triage rules, archive the
> archive pile, label the rest Act, draft replies for the answer now items using my voice and policies
> document, and give me one line on each item that needs me. Do not send anything. Tell me at the end
> how many you archived, how many you drafted, and how many need me.

### 4. Decide whether a category has earned auto handling

> For the category [name], here are the last 30 drafts and whether I edited each one, plus what the
> edits were: [notes]. Tell me honestly whether this category has earned auto handling, what should
> still always come to me inside it, and what would make you drop it back to drafts.

## Gotchas

1. **The label sprawl relapse.** Two weeks in, the user wants a label per client. Say no once, clearly, and
   explain that search does that job. Sprawl is what killed their last system.
2. **`Act` becomes a second inbox.** If it grows past about 20, triage has gone soft. Re run Phase 5 on a
   fresh day of mail and find out which decisions drifted.
3. **Drafts that are 80 percent right are worse than none.** They cost more attention than writing from
   scratch. If drafts get edited every time, stop drafting that category and go fix the document.
4. **Oldest first.** It is the instinct, it is wrong, and it ends the cleanup. Newest first, always.
5. **Auto archiving a real client.** Always read the sender list out loud before bulk archiving, and never
   bulk archive by keyword, only by sender or by Gmail category.
6. **The routine skipped for a week.** Expected, not a failure. Run the Phase 6 cleanup on those seven days,
   newest first, and carry on. The system is designed to be resumable.

## Quick checklist

1. Count the inbox before asking anything about it, then interview for ten minutes
2. Four labels (Act, Waiting, Read later, Archive) and triage rules, including the full needs the user list
3. Voice and policies document built from 10 to 20 real sent replies
4. Test triage on 20 to 30 real messages until the user disagrees with none
5. Backlog cleanup in one hour, newest first, bulk archive by sender, then filters so it stays clean
6. Daily 15 minute pass, and the automation ladder one category at a time, 20 to 30 clean drafts to promote

---

*Built and battle-tested by [Finding Land](https://findingland.help), who build AI automations for companies of any size. This skill is free. If you would rather have it built for you, done for you and wired to your tools, [get in touch](https://findingland.help/contact-us.html).*
