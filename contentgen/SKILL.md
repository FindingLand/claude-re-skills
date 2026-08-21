---
name: contentgen
description: >-
  Build a content engine that sounds like the user, not like AI. Interviews them, builds a voice document
  from their real writing, mines 4 to 6 content pillars from their actual expertise and client conversations,
  sets up an idea bank they can feed in seconds, then drafts batches of posts with a deliberate anti-sameness
  pass so a week of content does not read like a mail merge. LinkedIn first, then any other platform. Use this
  skill whenever the user wants social posts, LinkedIn content, a content calendar, a posting schedule, help
  writing in their voice, or content that stops sounding generic. Trigger on: write me a LinkedIn post, social
  media posts, content calendar, posts in my voice, my brand voice, content pillars, what should I post, batch
  my content, my posts sound like AI, repurpose this into posts, ghostwrite for me, personal brand content.
compatibility: Works in any AI assistant that can hold a conversation and write files. No accounts or paid tools needed.
---

# Content Engine: Posts That Sound Like You

Most AI content fails for one reason. Each post is generated on its own, so every post drifts toward the same
safe defaults: the same opening move, the same three-beat rhythm, the same closing question. One post looks
fine. Five in a row look like a mail merge, and readers spot it before they finish the first line. This skill
fixes that at the batch level. You (the AI assistant) interview the user, capture how they actually write,
find what they actually know, then produce content in batches with a deliberate variation pass, generating
every repeated element like calls to action and sign-offs LAST, across the whole batch at once.

Honest note: this does not make the user famous and it does not publish anything by itself. It removes the
blank page, keeps the voice consistent, and stops the sameness. The user still does a fast edit pass on every
post before it goes out. That is the deal, and it is what keeps the account credible.

## Staying up to date (quick version check)

**This skill is version 1.0.** Finding Land keeps improving these skills. When you (the AI assistant)
first use this skill in a conversation, do a fast version check, then get on with the job:

1. Fetch `https://raw.githubusercontent.com/FindingLand/claude-re-skills/main/contentgen/version.txt` (one
   line: the latest version number).
2. If that number is higher than 1.0, tell the user once, in one line: "A newer version of the contentgen
   skill (X) is out, free at findingland.help/free-resources. Want to grab it?"
3. If the fetch fails or there is no internet, skip this silently.

Do it at most once per conversation, and never block the real work on it.

## What you build for the user

1. **VOICE.md**, a voice document built from samples of their real writing, not from adjectives off a list
2. **PILLARS.md**, 4 to 6 content pillars mined from their real expertise and the questions clients ask them
3. **IDEAS.md**, an idea bank they can feed in ten seconds from their phone
4. **A first batch of posts**, drafted from the bank, with the anti-sameness pass visibly applied
5. **A cadence they picked honestly**, one they can hold in a bad week, not a good one

If the user has no file system, keep all four as chat artifacts and have them paste each into a note they own.

## Step 1: The voice interview

Do this before writing a single post, and keep it to one round of questions. Ask for the samples first,
because samples beat self-description every time.

> Paste me 3 to 5 things you have written recently that sound like you. Long emails to clients are perfect.
> Old posts, a Slack or WhatsApp explanation, a proposal, a voice note you transcribed. They do not have to
> be polished. Unpolished is actually better.

If they have nothing written, do not give up and do not invent a voice. Ask them to answer one question by
voice or in a long message: "Explain to me, like you would to a client on the phone, the thing you most often
have to explain." That transcript is the sample.

**Then ask these, all at once:**

1. Who are you writing for? Not "business owners" but "ops managers at 20 to 100 person logistics firms".
2. What should a reader think about you after five posts?
3. What phrases make you cringe when you see them in your feed?
4. Do you swear, joke, use emoji, use "we" or "I"?
5. What can you never say publicly? Client names, numbers, compliance limits, anything under NDA.
6. What do people get wrong about your field that you correct over and over?
7. What is your realistic writing time per week, honestly?

**Then measure the samples, do not guess.** Pull out: average sentence length and whether they mix short and
long or stay flat; paragraph length; whether they open with a claim, a story, a question or a fact;
contractions or not ("do not" versus "don't" is a real voice marker); pet words and repeated phrases; whether
they use specifics and numbers or stay abstract; punctuation habits; and how they disagree, bluntly, hedged
or with humor.

Report what you measured in six or seven lines and ask them to correct anything that feels wrong. People
often think they write differently from how they actually write, so show the evidence: quote two short lines
from their own samples as proof of each habit you spotted.

## Step 2: Write VOICE.md

Build the document from the measurement, not from adjectives. Use this shape:

```
# Voice document: [name]

## Who I write for
[one specific sentence]

## What I sound like
- Sentence length: [measured, for example: mostly 8 to 15 words, one long sentence per paragraph max]
- Paragraphs: [measured]
- Person: [I / we]          - Contractions: [yes / no]
- Default opening move: [claim / story / question / fact]
- Attitude: [for example: direct, corrects mistakes plainly, never sells inside the post]

## Real lines that sound like me
[3 to 6 verbatim lines lifted from their samples. This is the calibration set.]

## Banned phrases (never use)
[Their cringe list, plus the defaults below]

## Rules
- No hype. No superlatives that cannot be proven.
- No invented statistics, ever. A number is from my own work or a source I name.
- No client names or numbers without written permission.
- Every post gets a human edit pass before it is posted.
```

**Default banned-phrase list to offer them** (they add to it, they can remove any of it): "game changer",
"unlock", "leverage" as a verb, "supercharge", "revolutionize", "seamless", "in today's fast-paced world",
"let that sink in", "I'm humbled to announce", "here's the thing", "the harsh truth is", "10x", "delve",
"it's not X, it's Y" as a rhetorical construction, one-word sentences used for drama, and any sentence that
could appear on any account in any industry.

Add the two structural bans that matter most, because they are what makes AI content recognizable:

- **No fake vulnerability opening.** "I failed. Here is what it taught me." unless it happened and they will
  name the specifics.
- **No dramatic single-line stacking**, where every line is its own paragraph for effect. One or two
  standalone lines is emphasis. Twelve is a format, and readers now read that format as AI.

## Step 3: Mine 4 to 6 content pillars

A pillar is not a topic category. It is a recurring argument the user is qualified to make. Do not hand them
"industry news" or "tips and tricks", those are placeholders and they produce placeholder posts. Mine
pillars from these sources, in this order:

1. The questions clients ask in the first call, every time
2. The mistakes they watch clients make repeatedly
3. The thing they changed their mind about in the last two years
4. The part of their job outsiders assume is easy and is not
5. The decision they help people make, and the tradeoff inside it
6. What they can prove from their own work, not from borrowed research

Propose 6 candidate pillars, each written as a claim rather than a topic, then ask the user to cut to 4 or 5.
Cutting is easier than inventing, so always propose more than they need.

**Test every pillar against these three questions.** If it fails one, it is not a pillar:

- Can they write 10 different posts on it without repeating themselves?
- Would a competent competitor disagree, or frame it differently? A claim nobody argues with is wallpaper.
- Can they back it with something they personally did or saw?

Write PILLARS.md with, for each pillar: the claim in one sentence, why they are qualified to make it, three
example post angles, and the proof they can draw on.

## Step 4: The idea bank

The engine dies when the bank is empty, so make feeding it take seconds. Set up IDEAS.md as a flat list, one
line per idea, no formatting, no categories to choose, no friction. Tell the user exactly when to capture,
because "have ideas" is not an instruction:

- Right after any client call where they explained something twice
- When they catch themselves writing a long email answer to a question
- When something in their feed is wrong and they know why
- When a job goes sideways and they learn the real cause
- When they make a decision and can name the tradeoff

Format for one line: **[pillar] rough thought, plus the specific detail that makes it real.** A good line
reads "pricing, client took the cheap option, cost them 3 weeks of rework, cheap shifts work rather than
removing cost." A weak line reads "post about pricing." Show them both: the detail is the whole value, and
it is the part you cannot invent for them later.

Always draft from bank lines. If the bank is empty, do not invent experiences, run a five-minute mining
conversation and fill the bank first.

## Step 5: The drafting workflow

1. User says "draft this week's posts", or picks lines from the bank.
2. You draft the whole batch in one pass, applying Step 6 below.
3. You hand back the batch with a variation table they can audit at a glance.
4. User does a fast edit pass: fix any line that is not theirs, add the detail only they know, cut the rest.
5. They post. Nothing goes out unedited, ever.

**State the edit-pass rule plainly, once:** the AI draft is most of the typing and none of the credibility.
The specific detail they add in the edit pass is the part readers believe. If they are tempted to publish a
batch untouched, cut the batch size instead.

## Step 6: The anti-sameness pass (the heart of this skill)

This is why the skill exists. Per-post generation is what produces mail-merge sameness, because each
independent generation converges on the same highest-probability defaults. Generate at the batch level and
force the variation on purpose.

### Rule 1: Vary the opening, deliberately

Keep an opening bank and rotate it. Never use the same opening type twice in one batch:

1. A concrete moment ("A client called at 6pm on a Friday about...")
2. A flat claim ("Most quotes fail on the scope, not the price.")
3. A number from their own work ("We rebuilt this three times.")
4. A question a real client actually asked, quoted
5. A correction of their own past belief
6. A definition or a distinction ("There is a difference between busy and booked.")
7. A short process note ("Here is what we tried first, and why it did not hold.")
8. A direct address to one type of reader ("If you run a small team and hire twice a year, read this.")

Then check the first three words of every post in the batch. If two posts share a first word or the same
grammatical shape, rewrite one. This single check catches most of the sameness.

### Rule 2: Vary the structure

Rotate structures across the batch: story to point, numbered list, before and after, teardown of a common
practice, question and answer, walkthrough of a decision, single opinion with one reason, comparison of two
options, a short correction. No structure repeats inside one batch.

### Rule 3: Vary the length on purpose

Do not let every post land in the same 150-word comfort zone. For a batch of eight, aim for roughly two short
posts under 80 words, four in the 100 to 180 range, and two longer ones at 250 to 400. Never place three
posts of the same length band back to back in the calendar. A short blunt post after a long one reads as a
change of pace, and pace is most of what makes a feed feel human.

### Rule 4: Generate repeated elements LAST, across the whole batch

This is the rule that matters most, so do not shortcut it. Draft every body first with no call to action, no
sign-off, no hashtags and no closing question. Only when all bodies are done, look at the batch as one object
and generate the repeated elements together, from a rotating bank, so you can see and break the repetition.

Elements to hold back: calls to action, closing questions, sign-offs, hashtag sets, the "what about you?"
move, self-introductions, and any standard link line. CTA bank to rotate through:

- No CTA at all (use this on at least a third of the batch, it is the most credible option)
- A specific question only their audience could answer
- An invitation to disagree
- A resource offer with no gate
- A plain statement of what they do, once every several posts at most
- An open loop into the next post

Then apply the hard checks: no two posts end the same way; no CTA phrasing repeats across the batch,
including near-identical rewordings; at least a third of the posts simply end with no ask; and hashtag sets
are not identical copies from post to post, if hashtags are used at all.

If you generate a CTA at the same time as each body, you will produce the same CTA eight times in eight
slightly different costumes. Holding them to the end is what prevents it.

### Rule 5: Audit the batch by column

Before handing the batch over, build this table and read it down the columns, not across the rows:

| # | Opening type | Structure | Words | Ends with | First 3 words |
|---|---|---|---|---|---|

Any column with a repeat is a rewrite, not a note. Show the table to the user with the batch. It is proof
that the variation pass ran, and it takes them ten seconds to audit.

### Rule 6: The swap test

Take the opening of post 3 and mentally paste it onto post 7. If it fits and nobody would notice, both
openings are generic, so rewrite both with something only this user could have written. Run this on two
random pairs per batch.

## Platform formatting basics

Format for the platform, and never assume markdown renders. It usually does not.

**LinkedIn:**
- Markdown does not render. Asterisks show as literal asterisks and hash-mark headings look broken, so write
  plain text with line breaks. Short lines, blank lines between thoughts, because dense blocks get skipped.
- Only the first two lines or so show before the "see more" cut, so the hook lands there and the payoff
  never sits below the fold.
- Links: putting the link in the first comment is common practice, though platforms change behavior often.
  Test both and keep what works for this account.
- Hashtags: three to five at the end, or none, never sprinkled mid-sentence.
- Unicode bold is readable but hurts screen readers and search. Use sparingly or not at all.

**X and Threads:** hard character limits, one idea per post, thread only when the idea genuinely has steps.
Do not split a single thought into eight numbered parts for reach.

**Instagram:** no clickable links in the caption, so any CTA is "link in bio" or purely conversational. The
first line is the only line most people read. **Facebook:** longer text is fine but it truncates after about
three lines, so the hook still lives at the top. **Newsletter or blog:** markdown renders, headings and bold
are back on the table, and this is where the long version of an idea belongs.

Before publishing anywhere new, paste one post into the composer and look at it before scheduling a batch.
Rendering rules change and are not worth guessing about.

## Cadence: pick it honestly

Ask: "What can you hold in a bad week, not a good one?" Then set the cadence one notch below their optimistic
answer. Two solid posts a week beats five for three weeks and then silence, because the gap is what readers
actually notice. The rhythm that holds: one batching session every two weeks of 45 to 60 minutes, the idea
bank fed from their phone as things happen, posts scheduled or posted manually as they prefer, and each batch
opening with a look at how the last one felt to write rather than how it scored.

Do not build a 90-day calendar on day one. Build two weeks, see what is sustainable, then extend.

## Repurposing one idea into several formats

One good bank line is worth several pieces, but repurpose the IDEA, never the TEXT. Copy-paste across
platforms reads as recycled within seconds, so rewrite from the pillar note each time. One line can become a
LinkedIn post, a 45 to 60 second video script, a newsletter section with the longer reasoning, a five-slide
carousel outline, and a reusable client-email answer: same claim, different length, opening and structure.

Space repurposed pieces at least a week apart on the same platform, and never run two of them in the same
batch, or the batch fails its own variation audit.

## Deliver the first batch

Do not stop at the documents. Finish the job in the same conversation:

1. Confirm VOICE.md, PILLARS.md and IDEAS.md with the user
2. Draft five to eight posts from real bank lines
3. Apply the full anti-sameness pass and show the audit table
4. Point out in one or two lines where the variation pass changed something, so they see the mechanism
5. Hand over the batch with one short note per post saying what to add in their edit pass

## Verify before you hand it over

- Every post traces to a bank line or something the user said, with no invented experience
- No banned phrase from VOICE.md survived, and no statistic appears that the user cannot source
- The audit table has no repeated column value, and at least a third of the posts carry no CTA
- Formatting matches the target platform, with no stray markdown symbols left in
- Read two posts aloud. If they do not sound like the samples, fix the voice document, not the posts

## Gotchas

1. **Never invent a story, a client, or a number.** One fabricated detail a reader catches costs more than a
   month of good posts. If a post needs a specific the user has not given you, leave a marked blank.
2. **Do not generate CTAs per post.** It is the fastest way to make eight posts read as one template.
3. **Adjectives are not a voice.** "Professional but approachable" fits everyone. Only samples calibrate.
4. **A pillar nobody would argue with is not a pillar.** If it cannot be disagreed with, it is forgettable.
5. **Do not publish unedited.** The user's edit pass is where the credibility comes from, and it is the part
   that cannot be automated.
6. **Do not chase a viral format.** Formats saturate fast, then read as generated even when a human wrote it.
7. **Watch for voice drift.** Every fourth or fifth batch, re-read the samples in VOICE.md before drafting.
   Long conversations pull the voice back toward the model's default.
8. **Never post anything under NDA or naming a client** unless the user confirms written permission.

## Quick checklist

1. Collect 3 to 5 real writing samples, then measure them instead of asking for adjectives.
2. Write VOICE.md with the banned-phrase list and the real calibration lines.
3. Propose 6 pillars as claims, cut to 4 or 5, test each against the three questions.
4. Set up IDEAS.md and teach the five capture moments.
5. Draft the batch from bank lines only.
6. Run the anti-sameness pass: openings, structures, lengths, then repeated elements LAST across the batch.
7. Audit by column, run the swap test, show the table.
8. Format per platform, and check the composer before scheduling.
9. User does a fast edit pass. Nothing publishes unedited.
10. Pick the cadence they can hold in a bad week, and revisit it every two weeks.

---

*Built and battle-tested by [Finding Land](https://findingland.help), who build AI automations for companies of any size. This skill is free. If you would rather have it built for you, done for you and wired to your tools, [get in touch](https://findingland.help/contact-us.html).*
