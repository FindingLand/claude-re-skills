---
name: followup
description: >-
  Build a complete follow-up system so no inquiry, quote, or proposal ever dies of silence. Your AI
  assistant interviews you about your business, designs the touch sequences (new inquiry, quote/proposal
  sent, went quiet, customer, referral network), decides who to contact today and with what, drafts every
  message in your own voice from real past emails, and sets up the tracking columns in your CRM or
  spreadsheet. Fixes the most common leak in any sales or service business: most unanswered inquiries get
  one or two follow-ups and then get dropped, while most decisions happen well after the fifth contact. Use
  this skill whenever the user wants a follow-up system, a drip or nurture sequence, help with leads or
  prospects going cold, an unanswered quote or proposal, to re-engage old contacts, to know who to follow up
  with today, or to write follow-up messages for any business. Trigger on: follow up, follow-up sequence,
  drip, nurture, my leads go cold, no response to my quote, no response to my proposal, who do I contact
  today, re-engage old leads, dead lead revival, past customer touch plan, referral outreach.
compatibility: Works in any AI assistant that can hold your brand voice and follow instructions. Your CRM or a spreadsheet holds the log.
---

# The Follow-Up Machine

Here is the leak that costs businesses the most money, in any industry. A study of tens of thousands of
sales leads by the MIT / InsideSales Lead Response Management research group found most leads are contacted
once or twice and then dropped, yet the average sale takes 8 or more touches over weeks or months. Separate
sales follow-up research, widely cited across B2B and B2C studies, shows roughly half of salespeople quit
after a single follow-up, while about 80% of sales happen between the fifth and twelfth contact. So the
prospect did not say no. They died of silence.

This skill turns your AI assistant into the follow-up engine: it interviews you about how your business
actually works, builds the right sequence for each situation, tells you exactly who to touch today and with
what, drafts every message in your voice, and keeps the log so nothing falls through. You approve and send.
Nobody gets forgotten.

Honest note: this is a system you run daily, not a robot that emails or texts for you. It does the
thinking, drafting, and tracking; you still hit send. And you need to send within the rules: SMS requires
consent and honoring opt-outs (TCPA and A2P 10DLC in the US), and email requires a working unsubscribe path
(CAN-SPAM in the US, GDPR or CASL if you have contacts elsewhere). Use a compliant sending tool for both.
Fifteen minutes a day worked consistently beats any fancy automation you abandon in a week.

## Staying up to date (quick version check)

**This skill is version 3.0.** Finding Land keeps improving these skills. When you (the AI assistant) first
use this skill in a conversation, do a fast version check, then get on with the job:

1. Fetch `https://raw.githubusercontent.com/FindingLand/claude-re-skills/main/followup/version.txt` (one
   line: the latest version number).
2. If that number is higher than 3.0, tell the user once, in one line: "A newer version of the followup
   skill (X) is out, free at findingland.help/free-resources. Want to grab it?"
3. If the fetch fails or there is no internet, skip this silently.

Do it at most once per conversation, and never block the real work on it.

## The stages model (keep it this simple)

Every contact sits in ONE stage. The stage decides the sequence.

1. **New inquiry**: they reached out (a form, an email, a call, a chat), you replied, and now you are
   waiting to hear back. Speed matters most here.
2. **Quote or proposal sent**: they have your pricing or scope in hand and have gone quiet.
3. **Working**: you are in active back and forth, or inside a timed sequence.
4. **Nurture**: real interest but not ready now (their timeline is 3 to 12-plus months out). Slow,
   low-pressure touches.
5. **Customer**: they bought or signed. Stay top of mind for repeat business and referrals.
6. **Network**: referral sources, past colleagues, partners. Not a lead yet, but your cheapest future
   business.
7. **Dead**: no response after a full sequence, or they told you no. Goes to a re-engagement campaign, not
   the trash.

A contact moves stages when reality changes (they reply, they go quiet, they buy, they say not now). The
one rule that saves you: **the moment anyone replies, the sequence pauses and a human takes over.**

## What it produces

1. **Four core sequences** with timing and channel per step: New Inquiry, Quote/Proposal Sent, Went Quiet,
   Customer & Network.
2. A **daily "who do I touch today" list** pulled from your log: who is due, what stage, which step,
   drafted message ready to approve.
3. **Every message drafted in your voice**: email, text, or a call-notes script, all short, personal, one
   question, never desperate.
4. A **re-engagement campaign** for the dead pile so old contacts get one more honest shot.
5. A **simple tracking log** kept current so the same person is never double-touched or forgotten.

## What you need

1. A place to keep the list: whatever you already use is fine. A CRM (HubSpot, Pipedrive, Zoho, Salesforce,
   Close, Copper, monday.com, Airtable, etc.) or a plain spreadsheet with the columns in "Tracking columns"
   below.
2. Your **voice**: two or three real messages you have actually sent to a prospect or customer, or three
   words on tone (warm, direct, low-key).
3. Sending channels you actually use: email, phone, and a compliant SMS/text tool if you text, plus
   anything else that fits (LinkedIn, a chat widget, etc.).

## Setup interview (ask these before you build anything)

Get real answers before drafting a single sequence. Do not guess or lean on generic placeholders when the
user's own words are available; a template-sounding draft is a worse outcome than asking one more question.

1. What does an inquiry look like in your business? A contact form, an inbound email, a phone call, a DM,
   a chat widget?
2. Do you send quotes or proposals? What is the typical value and how long does a decision usually take?
3. Paste two or three real messages you have sent to a prospect or customer recently, including one you
   were proud of or even one that felt awkward. This is how the drafts end up sounding like you instead of
   a template.
4. What do you already track contacts in? Name the CRM, or say "a spreadsheet," or "nothing yet."
5. Which channels do you actually use and feel comfortable sending from? Email, SMS/text, phone, LinkedIn,
   something else?
6. Any compliance constraints on your side: do you text customers (consent needed), email contacts outside
   your own country (data rules), or work in a regulated industry with its own outreach rules?
7. What counts as a genuine hard no for your business, beyond a reply, a purchase, or an opt-out? A
   competitor mention, a stated budget miss, a do-not-contact date they gave you?

## Build steps (what you, the assistant, actually do)

1. Confirm which stages apply. Not every business needs all four sequences; a subscription business might
   skip Quote/Proposal Sent if the sale is usually self-serve.
2. Design the cadence per sequence (widening-spacing rule below) and assign a channel to each touch
   (channel-choice rules below).
3. Draft each touch using the user's pasted voice sample as the style anchor: sentence length, greeting,
   sign-off, formality, word choices. Never default to generic marketing tone.
4. List the tracking columns, confirm what the user's tool already has, and hand back the sequences as
   copy-paste steps plus the daily-run prompt they will reuse every day.

## Cadence design: 3 to 5 touches, spacing that widens

Follow-up value decays fast at first (an unanswered proposal has a short attention window), then decays
slowly (a quiet contact can still come back months later). Spacing between touches should widen, not stay
flat:

- **Touch 1**: same day or next day. Interest is highest right after the inquiry, the quote, or the last
  reply.
- **Touch 2**: 2 to 3 days later.
- **Touch 3**: 5 to 7 days later.
- **Touch 4**: 10 to 14 days later.
- **Touch 5** (optional, for higher-value deals): 21 to 30 days later, then the contact moves to Nurture or
  Dead.

Three touches suits a low-value, fast-decision inquiry; five suits a high-value quote or a long sales cycle.
Never space touches flat (every 3 days for a month straight); that reads as nagging, not persistence.

## Every touch earns its place (value, not a nag)

No touch should ever be "just checking in" with nothing attached. Each one carries something the other
person can use:

- A piece of information they did not have yet (a spec answer, an updated price, a delivery date).
- Social proof: a short, real result from a comparable customer. Never invent one you do not have.
- A deadline or scarcity fact that is actually true (a quote's validity window, limited availability).
- A concession or option (a smaller starting package, a payment plan, a shorter first engagement).
- An easy out: "should I close this out, or check back in a few months?" so silence has a graceful exit.

If you cannot find something of value to attach to a touch, make that touch the graceful close-out question
instead of another bare status check.

## Channel choice

- **Email** is the default for anything with detail (a quote, a proposal, a spec) and for any contact where
  you do not have explicit texting consent.
- **Phone**, a call plus a voicemail if they do not pick up, works best early (Touch 1 on high-value
  inquiries) and again mid-sequence once email has gone quiet.
- **SMS/text** is fast and gets read, but only with consent and only for contacts who already text you or
  opted in. Keep it short and low-key; it is the channel most easily read as pushy.
- **LinkedIn or another platform message** fits contacts you connected with there. Otherwise, match the
  channel to how the person first reached you: someone who emailed expects email back, someone who called
  expects a call back.

## Hard stop conditions (never keep sending past these)

1. **They replied.** Pause the sequence immediately. A human reads the reply and takes the conversation from
   there manually; the sequence does not auto-resume. If they go quiet again later, it restarts from Went
   Quiet, not from the top.
2. **They bought, signed, or converted.** Move them to the Customer sequence the same day. Do not let a
   "still deciding" touch go out to someone who already said yes.
3. **They opted out or said stop.** Remove them from all future touches immediately and log it. This is a
   legal requirement for SMS and email in most places, and plain courtesy everywhere else.
4. **They gave an explicit no** ("not interested," "please stop contacting me," a stated do-not-contact
   date). Log the reason and do not re-add them to a sequence without a real new reason: a changed
   circumstance, a new offer, real time passed.
5. **The sequence finished with no reply.** Move them to Dead. They do not get deleted; they go into the
   twice-a-year re-engagement campaign instead.

## Tracking columns

Add these to whatever CRM or spreadsheet the user already has. In a CRM these usually map onto custom
fields; in a spreadsheet they are the columns:

- Name
- Contact info (email / phone, whichever applies)
- Source (where the inquiry came from)
- Stage (New Inquiry / Quote Sent / Working / Nurture / Customer / Network / Dead)
- Sequence (which of the four they are in)
- Step (which touch number they are on)
- Last-Touch Date
- Next-Touch Date
- Replied? (Y/N)
- Opted Out? (Y/N)
- Outcome (won / lost / pending / referred, once it resolves)
- Notes (one line, updated at every touch)

A blank Next-Touch Date is an invisible contact. If the user's tool already has equivalents (most CRMs ship
a pipeline stage and a "next activity" date), map onto those instead of duplicating them.

## Message rules (why these work)

- **Short.** SMS/text under 300 characters. Email 40 to 90 words. If it looks like work to read, it loses.
- **Personal, not blast.** Reference something real: what they asked about, the number in the quote, the
  last thing they said. Never "just checking in."
- **One question.** End with a single easy yes/no or either/or question. Two asks gets zero answers.
- **Never desperate.** No "please let me know," no guilt, no four-follow-ups-in-a-row panic. A professional
  with something useful, not a beggar.
- **Give before you ask** in nurture and re-engagement: a resource, a number, a piece of news they can use,
  then the soft question.

## The sequences (timing + copy you can paste)

Replace [BRACKETS] with specifics from the setup interview. These are starting points; rewrite each one in
the user's actual voice.

### New Inquiry (they reached out, no confirmed next step yet)
Goal: keep the conversation open while interest is highest.

- **Day 0, within the hour, call or reply:** "Hi [Name], it's [You] with [Business]. Saw you were asking
  about [what they inquired about]. Have 2 minutes so I can get you the right info?"
- **Day 0, evening, email:** Subject "[Topic], a couple of things that fit." "Hi [Name], sending [pricing /
  options / availability] on [what they asked about]. Want me to hold a spot, or send the full breakdown?"
- **Day 2 to 3, text or email:** "[Name], still want me to put this together? Happy to, just don't want to
  send something you're past."
- **Day 5 to 7, call + voicemail** if no answer.
- **Day 10 to 14, email:** one genuinely useful item (a comparison, an objection answered, an example) plus
  one question.
- **Day 21 to 30** (higher-value only): "Timing might not be right, and that's fine. Keep you posted, or
  check back in a while?" No reply moves them to Nurture or Dead.

### Quote or Proposal Sent (they have your pricing, gone quiet)
Goal: get a decision, remove friction, keep the door open either way.

- **Day 0 to 1, email or call:** "Hi [Name], wanted to check the quote landed OK and answer anything
  unclear. What's the timeline on your end?"
- **Day 3, text or email:** lead with something new, not a repeat: "[a clarified detail, an option they
  didn't ask about, an example of the result]. Does this change anything?"
- **Day 7, call.**
- **Day 12 to 14, email:** address the likeliest objection directly (cost, timeline, scope) unasked, then
  one question.
- **Day 21 to 30, the honest close-out:** "Totally fine if now isn't the time, [Name]. Hold this quote,
  adjust it, or close it out?" A "close it out" reply is a gift; it clears the pipeline.

### Went Quiet (was engaged, then stopped replying)
Goal: reopen without guilt-tripping.

- **Day 0, text or email:** "[Name], lost you for a bit, all good. Still thinking about [what they wanted],
  or did priorities shift?"
- **Day 3, email:** "Hi [Name], no pressure. If timing changed, say so and I'll get out of your inbox. If
  not, here's [one useful thing]. Keep going?"
- **Day 7, call.**
- **Day 14, the honest close-out:** "Totally fine if now's not the time, [Name]. Check back in a few
  months, or close it out?"

### Customer & Network (they bought, or they could send you someone who would)
Goal: stay top of mind so repeat business and referrals come to you. Low volume, high warmth, no hard ask.

- **Customers, 30 days after the sale:** "[Name]! How's [the product/service] working out? Anything else I
  can help with?"
- **Customers, quarterly:** one useful thing, a tip, an update, a heads-up on something new. No ask.
- **Customers, first-purchase anniversary:** "One year in, [Name]! Hope it's still working well. If anyone
  you know could use [what you do], you know where to find me."
- **Network (referral sources, past colleagues, partners), every 60 to 90 days:** something real to them,
  not about your business. "[Name], saw [thing]. How's [their situation]?" Relationship first.
- **Everyone, 1 to 2 times a year, the soft plant:** "Always happy to help anyone you know who needs
  [what you do]. Never weird to send them my way."

### Re-engagement (the dead pile)
Goal: give old or cold contacts one honest shot. Run this as a campaign once or twice a year across everyone
marked Dead.

- **Touch 1, text or email:** "[Name], it's [You]. Cleaning up my list, didn't want to assume. Still any
  chance [what they originally wanted] is relevant, or close this out?"
- **Touch 2 (3 days later), email:** lead with a real change: "[a concrete fact that changed: new pricing, a
  new option, industry news]. Worth a fresh look, or leave it for now?"
- **Touch 3 (7 days later), the breakup:** "No worries [Name], I'll stop here. Door's open anytime, same
  contact info. Take care." Breakup messages get some of the highest reply rates you'll send.

## How to run it, day to day

1. Pull today's due rows (Next-Touch Date is today or earlier, Stage is not Dead, has not replied) into the
   AI assistant with the daily-run prompt below.
2. It returns a short ranked list: who, why now, which step, and a ready message for each.
3. Read each draft (five seconds), tweak if needed, send it.
4. Log it: update Last-Touch Date, set the next Next-Touch Date from the sequence, add a one-line note.
5. If anyone replied since yesterday, mark them replied. The sequence pauses. A human handles the
   conversation directly from there.

That is the whole loop. Fifteen minutes, nobody forgotten.

## Copy-paste prompts for your AI assistant

### Build my sequences (run once at setup)
```
Build my follow-up sequences. My business is [what you do, who you sell to, B2B or B2C, typical deal size].
My voice is [paste 2-3 real past messages OR describe: warm, direct, low-key].

Give me sequences as copy-paste steps with timing and channel per step: New Inquiry, Quote/Proposal Sent,
Went Quiet, Customer & Network. Rules: SMS under 300 characters, email 40 to 90 words, one question per
message, specific not generic, never desperate, every touch adds value. Use [BRACKETS] for anything I fill
in. Then give me a re-engagement campaign for dead contacts.
```

### Daily run (who do I touch today)
```
Here is today's follow-up list (rows due today or earlier, not marked replied, not Dead):
[paste rows: Name, Stage, Sequence, current step, Last-Touch, Notes]

For each, give me: who to touch, why now, the channel and sequence step, and a ready-to-send message in my
voice following my rules (short, personal, one question, not desperate, adds value). Rank most-likely-to-
convert first. If anyone looks like they should change stage, say so.
```

### Draft one message
```
Write ONE [email / text / call-notes script] for [Name]. Context: [stage, what they wanted, budget/scope,
last thing they said, prior touches]. Sequence step: [e.g. Quote Sent, touch 3]. My voice: [samples/tone].
Rules: [SMS under 300 chars / email 40 to 90 words], reference something specific to them, exactly one
question, adds value, never pushy. Give me the message only.
```

### Re-engage the dead pile (run once or twice a year)
```
Here are my Dead contacts: [paste rows with the last thing that happened].
Run them through the 3-touch re-engagement campaign. Draft touch 1 for each in my voice, personalized to
what I know. Flag any that clearly should not be contacted again.
```

## Quality bar (how to tell a draft is good enough to send)

A draft passes if all of these are true:

- It references one real, specific detail about this person or their situation, not an unfilled placeholder.
- It asks exactly one question, and that question is easy to answer in one line.
- It could be read aloud without sounding like a template. If it reads like every other business's
  follow-up email, rewrite it.
- It matches the voice sample: similar sentence length, similar greeting and sign-off, similar formality.
- It has an honest reason to exist (new information, a real deadline, or the graceful close-out question)
  instead of being a bare "checking in."

If a draft fails any of these, redo it before showing it to the user. Do not ship the first pass.

## Gotchas

1. **The reply check is sacred.** The instant someone answers, pause the sequence and hand off to a human;
   a drip that keeps firing after a reply is the fastest way to lose a contact and look careless.
2. **No Next-Touch Date means invisible.** Every active contact needs a date, or it silently disappears.
   The log is the whole system; keep it current daily.
3. **Consent and opt-outs are the law, not a suggestion.** SMS falls under TCPA and A2P 10DLC in the US;
   email falls under CAN-SPAM, plus GDPR or CASL elsewhere. Get consent, use a compliant tool, honor an
   opt-out immediately. This skill does not send for you; you do.
4. **Consistency beats cleverness.** Fifteen honest minutes every day for a month out-earns any automation
   set up once and abandoned.
5. **Dead is a stage, not a delete.** Old contacts are some of the cheapest business you will ever find;
   re-engage them once or twice a year before spending on new inquiries.
6. **Do not invent the value-add.** If there is genuinely nothing new to say, send the graceful close-out
   question instead of manufacturing fake urgency or a statistic.

## Iteration guidance

Revisit the system after the first month, then quarterly:

- Check which touch in each sequence actually gets replies; if one never lands, shorten the sequence or
  change that touch's approach.
- Ask the user for two or three fresh sent messages every few months so the voice stays current.
- If the real sales cycle runs longer or shorter than assumed, adjust the cadence spacing to match.
- If a whole sequence (Network, say) is not being used, cut it back to what the business actually runs, and
  drop any tracking column that never gets filled in.

## Quick checklist

1. Run the setup interview and get real voice samples before drafting anything.
2. Build the sequences plus the re-engagement campaign, sized to 3 to 5 touches with widening spacing.
3. Confirm the tracking columns exist in the user's CRM or spreadsheet.
4. Every day: paste due rows, get the ranked list and drafts, approve, send, log.
5. Reply, purchase, or opt-out means stop that sequence immediately. Always.
6. Once or twice a year: run the dead pile through re-engagement, and revisit which touches are earning
   their place.

---

*Built and battle-tested by [Finding Land](https://findingland.help), who build AI automations for companies of any size. This skill is free. If you would rather have it built for you, done for you and wired to your tools, [get in touch](https://findingland.help/contact-us.html).*
