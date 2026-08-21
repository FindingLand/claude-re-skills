---
name: replybot
description: >-
  A universal lead-and-customer-reply chatbot builder for any business: agencies, consultants,
  e-commerce shops, local service businesses, and B2B teams. Answer every inbound message in minutes,
  in your voice, on every channel people reach you on: email, your website contact form or live chat,
  WhatsApp, Instagram and Facebook Messenger DMs, SMS, and marketplace or platform messaging (Etsy,
  Amazon, Upwork, Fiverr, Google Business Profile, and similar). You write one policies and facts
  document, and your AI assistant answers new leads and customers from it, using your real rules on
  pricing, availability, scope of work, and refunds, so you stop losing deals and support requests to
  slow replies. Use this skill whenever the user wants to answer leads or customers faster, auto-reply
  to inquiries, set up a chatbot for their business, respond to messages across channels, triage a
  shared inbox, or stop missing leads. Trigger on: reply to my leads, answer inquiries faster, customer
  message bot, lead response bot, auto-reply, speed to lead, respond faster, my chatbot, DM automation,
  inbox automation, triage my messages.
compatibility: Works in any AI assistant that can hold a knowledge document, follow instructions, and draft replies. To send automatically it needs email drafts or a browser agent; some platforms allow it, some do not (see the honest notes).
---

# Your Anywhere Chatbot

Leads and customers message you on half a dozen different channels and you cannot watch all of them at
once. Someone asks "do you have availability next week" or "does this come in a larger size" at 9pm, you
see it the next afternoon, and by then they bought from, or booked, whoever answered first. A fast,
correct first reply wins business that a slower, more polished one loses. This skill turns your AI
assistant into one brain that answers new leads and customer messages in YOUR voice, from YOUR rules,
across every channel you use.

Honest note: this is not a magic bot you flip on and forget. You write one good policies document (the
part that takes real effort), and you start in draft-for-approval mode where the AI writes the reply and
you press send. You only move to auto-send on a channel once you have watched 20 to 30 drafts and trust
it. And some platforms (most marketplaces and many social apps) do not let outside tools post on your
behalf, so on those the AI drafts and you paste. All of that is spelled out below.

## Staying up to date (quick version check)

**This skill is version 3.0.** Finding Land keeps improving these skills. When you (the AI assistant)
first use this skill in a conversation, do a fast version check, then get on with the job:

1. Fetch `https://raw.githubusercontent.com/FindingLand/claude-re-skills/main/replybot/version.txt` (one
   line: the latest version number).
2. If that number is higher than 3.0, tell the user once, in one line: "A newer version of the replybot
   skill (X) is out, free at findingland.help/free-resources. Want to grab it?"
3. If the fetch fails or there is no internet, skip this silently.

Do it at most once per conversation, and never block the real work on it.

## What it produces

1. A **policies + facts document** the AI answers from (pricing rules, availability, scope of work,
   refund or cancellation policy, what to never say)
2. A **triage step** that sorts every inbound message into answer / needs-you / ignore, so the bot only
   speaks when it should and quietly hands you the sensitive ones
3. A **voice + tone profile** so replies sound like you, not like a generic bot
4. **Draft replies** you approve and send (mode 1), moving to **auto-send** per channel once trusted
   (mode 2)
5. A **per-channel wiring plan**: which platforms allow automation, which are draft-and-paste, and how
   to hook each one up honestly

## What you need

1. Any AI assistant that can hold a long document and follow instructions
2. About 60 to 90 minutes once to write the policies document and voice profile (the AI helps you)
3. For email: access to your inbox drafts (Gmail, Outlook, etc.)
4. For platforms with no send API (most marketplaces, some chat widgets, some social DMs): either you
   paste the drafts yourself, or a browser agent tool that can log in and type for you
5. Honesty about your own rules. The bot is only as good as the facts you give it

## The one rule that makes this work: triage first

Do not let the bot answer everything. Before it drafts a single word, it decides one of three things:

1. **Answer** - a normal question it can handle from your policies (pricing, availability, what you
   offer, do you serve my area or industry, how do I get started). It drafts a reply.
2. **Needs you** - anything account-specific or sensitive: a billing dispute, a refund or complaint, a
   contract or scope change, a legal question, price negotiation, or anything your policies do not
   cover. It writes you a short note and drafts nothing. Never let the bot guess on these.
3. **Ignore** - spam, a receipt, a platform notification, an automated message, your own sent mail
   bouncing back. It does nothing.

This triage-first habit is what keeps the bot safe and cheap. It never invents a price, never promises
availability it cannot confirm, and never argues with an angry message. When in doubt, it routes to you.

## The policies document (the brain)

Everything good comes from this document, and every bad or generic reply traces back to something
missing in it. Write it once, keep it in a note or doc the AI can read, and update the doc (never the
prompt) when something changes. Include:

1. **Pricing and availability** - rates or fees, minimum engagement or order size, deposit or retainer,
   open dates or lead times, any pricing rules (bundles, volume or seasonal discounts)
2. **Service or product rules** - what is included and excluded, turnaround or delivery time, service
   area, hours of operation, refund or cancellation policy
3. **Qualification criteria** - budget minimum, project or order type, industry or use case, who is a
   good fit
4. **Questions the bot must always ask a new lead** - timeline, budget range, what they need, company
   size or industry, how they found you. Woven in naturally, not fired off like an interrogation
5. **What automatically disqualifies someone** - budget below your minimum, outside your service area,
   a request outside your scope of work
6. **How to take the next step** - how to book a call, get a quote, place an order, or sign up
7. **Escalation rules** - the exact situations where the bot must stop and hand off to you
8. **Voice and hard rules** - tone (warm, brief, professional), words to avoid, and anything you must
   never say

If you run several product lines, service tiers, or locations with different rules, use two layers: one
general document for company-wide behavior and tone, and a short per-offer sheet for that offer's price,
availability, and rules. The specific sheet always overrides the general document.

## Drafts vs auto-send

Start every channel in **draft mode**: the AI writes the reply, you read it, you send it. This is the
right default, it catches mistakes before a lead or customer ever sees them, and it still gets you
answering in minutes instead of hours.

Move a channel to **auto-send** only after you have reviewed 20 to 30 drafts on that channel and they
are consistently correct. Even then, keep two guards: the triage still routes sensitive messages to you
(auto-send is only for clean lead or customer questions), and you can flip any channel back to draft in
one edit if quality slips. A business-hours gate is worth adding to auto-send too: a reply that fires at
3am reads as a bot. Hold overnight drafts until morning.

## Wiring it per channel (the honest version)

Different platforms allow very different things. Here is the real state of it:

1. **Email and website contact form** - the easiest. Most contact forms email you, so this becomes an
   email reply. The AI can write directly into your inbox as a DRAFT (Gmail and Outlook both support
   draft creation), and you press send. This is the best channel to start on.
2. **Live chat on your website** - tools like Intercom, Drift, or Tidio vary: some expose a real API you
   can wire drafts or auto-send into, others only offer their own built-in AI. Check your tool's API
   docs before assuming either way.
3. **Marketplace and platform messaging** (Etsy, Amazon, Upwork, Fiverr, Google Business Profile, review
   sites, and similar) - most of these have no public send API for outside tools, or their terms
   restrict automated messaging. Treat these as draft-and-paste: the AI drafts the reply, you copy it
   into the platform. Do not bolt an unofficial bot onto them, you risk the account.
4. **WhatsApp** - two honest paths. The free path: treat it like any owned inbox in draft mode, the AI
   drafts in your voice and you paste and send from your phone or WhatsApp Web. The official path: the
   WhatsApp Business API (via a provider like Twilio or 360dialog) allows real auto-send with approval,
   costs a few cents per conversation, and needs a business account, so save it for real volume. Never
   bolt an unofficial bot onto a personal WhatsApp number, accounts get banned for that.
5. **Instagram and Facebook Messenger DMs** - a business or creator account can use the official
   Messenger and Instagram messaging APIs through approved tools, which is real automation but
   setup-heavy. The pragmatic start is the same draft-and-paste loop, upgrading only if DM volume
   justifies it.
6. **Text / SMS** - if you text from a business texting tool (Google Voice, OpenPhone, your CRM's
   texting), the AI drafts and you send; some of those tools have APIs that allow full automation of
   the send once you trust the drafts.

**The universal rule (this is why the skill works on ANY platform):** the brain never changes, only the
last inch does. Your policies document, triage rules, and voice profile are platform-independent. Every
platform you will ever meet lands in one of three modes: (a) an inbox you control (email, forms, some
SMS or chat tools), automate drafts fully; (b) an official API with approval (WhatsApp Business,
Messenger, Instagram), automate once volume justifies the setup; (c) a walled marketplace or platform
inbox (Etsy, Amazon, Upwork, Fiverr, and most others), draft-and-paste. When a new platform shows up next
year, you do not rebuild anything: you classify it into a, b, or c, and your same reply brain is live on
it that day.

Rule of thumb: where you control the inbox (email, forms) you can automate drafts fully. Where a
marketplace owns the messages, the AI drafts and a human (or an at-your-own-risk browser agent) does the
sending. Never claim a platform allows automation when it does not, and keep money, deposit, and
contract-term talk on the platform of record where it is on the record.

## Test before you go live

Never point the bot at real leads or customers until you have watched it handle fake ones. Before any
channel goes live, feed it 8 to 10 test messages you write yourself and read every reply:

1. **The easy ones** - "is this still available?", "how much does this cost?", "do you work with
   businesses my size?" It should answer cleanly from the document, in your voice, and ask any missing
   qualifying question.
2. **The traps** - ask something your document does NOT cover, and something sensitive (a billing
   dispute, a complaint, a contract change). It must refuse to guess and route to you. If it invents an
   answer, the document is thin or the triage rule is loose. Fix that before going live, not after.
3. **The half-answered thread** - paste a thread where the lead already gave their timeline or budget,
   then a later message. The bot must not re-ask what it already knows.

Only after it passes all three does a channel earn draft mode with real leads. Auto-send is a separate,
later bar (20 to 30 clean drafts on that channel). Re-run this test any time you edit the document.

## Setup steps

1. Write the policies + facts document with the AI (use the first prompt below). Be thorough.
2. Give the AI your voice: paste 2 or 3 real replies you have sent, or describe your tone.
3. Set your triage rules: what it answers, what it routes to you, what it ignores.
4. Turn on your easiest channel first (email / contact form) in draft mode.
5. Review drafts daily. Every time one is off, fix the DOCUMENT, not the reply.
6. Add channels one at a time. Auto-send only after 20 to 30 clean drafts on that channel.

## Copy-paste prompts

### 1. Build the policies document

> You are helping me build the knowledge document my lead-and-customer-answering assistant will use.
> Interview me one topic at a time to fill in: pricing and availability, minimum engagement or order
> size, what is included and excluded, service area or hours, refund or cancellation policy,
> qualification criteria (budget, project type, industry fit), the questions you must ask every new
> lead, what disqualifies someone, how a lead takes the next step (book a call, get a quote, place an
> order), and the exact situations where you must stop and hand the message to me. Ask me about anything
> I leave vague. When we are done, output the finished document in clean sections I can save and reuse.

### 2. Set the triage rules

> Here is my policies document: [paste]. From now on, for every inbound message I give you, first
> decide ANSWER, NEEDS-ME, or IGNORE. ANSWER = a normal question you can handle from the document.
> NEEDS-ME = a billing dispute, complaint, negotiation, contract or legal question, or anything the
> document does not cover; for these, do not draft, just tell me in one line why. IGNORE = spam,
> receipts, platform notifications, automated mail. Tell me your decision first, then draft only on
> ANSWER.

### 3. Draft a reply in my voice

> Here is my policies document: [paste]. Here are 2 examples of how I write: [paste]. Here is the full
> message thread with a lead (oldest to newest): [paste]. Draft my reply to their most recent message.
> Rules: answer their actual question first using ONLY facts from the document, do not invent a price or
> a date, do not re-ask anything they already answered, weave in any still-missing qualifying question
> naturally, keep it warm and brief in my voice, and if the document does not cover something, stop and
> tell me instead of guessing. Keep it to one short paragraph with no line breaks so it is safe to paste
> anywhere.

### 4. Decide if a channel is ready for auto-send

> I have reviewed [N] of your drafts on [channel] and here is how many I edited and why: [notes]. Based
> on this, tell me honestly whether this channel is ready to move from draft-for-approval to auto-send,
> what kinds of message should still always route to me, and what gate (like business hours) I should
> keep on.

## Gotchas

1. **Facts in, facts out.** The bot cannot know your refund policy or your minimum order size unless the
   document says it. Missing info is the number one cause of a bad reply. Fix the document, never hack
   the prompt.
2. **Read the whole thread, not the last line.** A lead often answers a question two messages back.
   Always feed the full conversation so the bot does not re-ask or contradict itself.
3. **Never auto-answer the sensitive stuff.** Billing, complaints, negotiation, legal, contract changes:
   these go to you, always. That is what triage is for.
4. **Draft first, auto-send later, and per channel.** Trust is earned on one channel at a time.
5. **Know which platforms allow automation.** Email and forms: yes, drafts. Most marketplace and social
   platform messaging: draft-and-paste only, do not bolt on an unofficial sender. Beware the Enter-key
   auto-send trap: many chat widgets and marketplace message boxes send the moment you press Enter, with
   no draft state, so if you automate typing you must strip line breaks out of the text first or it
   fires half-finished messages.
6. **Keep money and contract terms on the record.** Do not move pricing, deposits, or payment
   instructions to a side channel a platform cannot see.
7. **Single-paragraph replies paste more safely** and read more human on chat platforms than long,
   multi-paragraph messages.

## Quick checklist

1. Write the policies + facts document
2. Give the AI your voice (2 to 3 real replies)
3. Set triage: answer / needs-me / ignore
4. Turn on email/forms in draft mode first
5. Review daily, fix the document when a reply is off
6. Add channels one at a time; auto-send only after 20 to 30 clean drafts

---

*Built and battle-tested by [Finding Land](https://findingland.help), who build AI automations for companies of any size. This skill is free. If you would rather have it built for you, done for you and wired to your tools, [get in touch](https://findingland.help/contact-us.html).*
