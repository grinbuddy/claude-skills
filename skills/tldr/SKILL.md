---
name: tldr
description: Plain-English recap for a reader who has lost the thread — what happened, whether anything is wrong, and exactly what is needed from them, with no jargon. Use when the user says "tldr", "I'm lost", "in layman's terms", "plain English", "what just happened", "what do you need from me", or seems overwhelmed by a long or technical reply.
---

# TLDR

The reader is smart but has lost the thread. Your last replies were too long,
too technical, or assumed labels they don't carry in their head. Give them the
whole picture in under a minute of reading, then stop.

This is a rewrite of what you already know, not new work. Do not run new
investigations to produce it. If something is unverified, say so in plain
words rather than going to check.

## Shape of the answer

Use these four parts, in this order, with these plain headings.

1. **Bottom line** — one or two sentences. Answer the two questions the
   reader actually has: "Is anything broken?" and "Do I need to do something
   right now?" Lead with bad news if there is any.
2. **What happened** — two to four bullets. What was done and why it
   matters, in everyday words. Say what did NOT change when that is the
   reassuring part ("this is paperwork; the product behaves the same").
3. **What I need from you** — a numbered list, most important first. Each
   item is one decision or one action, and says:
   - what to do or decide, phrased so a one-word reply works;
   - your recommendation, in one clause;
   - what happens if they do nothing.
   If nothing is needed, say "Nothing right now."
4. **What can wait** — one or two lines on things that are parked and need no
   attention. Do not list them all; name the group.

## Language rules

- **No labels on their own.** Ticket numbers, decision-log numbers, checkpoint
  names, file names, branch names, commit hashes, tool names and acronyms are
  out. Describe the thing by what it does. If the reader will need a label to
  find, click or type something, put it in brackets AFTER the plain
  description: "the settings file is almost at its size limit (TICKET-123)".
- **Swap jargon for its effect.** Not "CI is red on pip-audit" but "one of
  the automatic safety checks is failing because a library needs an upgrade;
  it is a known item and nothing is at risk today."
- **Short sentences, everyday words.** One idea per sentence.
- **No tables, no code blocks, no nested bullets.**
- **Numbers only when they change the decision.**
- **Aim for 150 to 250 words.** If it runs longer, you are explaining, not
  summarising; cut.

## Honesty rules

- Never soften or drop bad news to keep it simple. Simple words, same truth.
- Never drop a decision because it is hard to explain. Find the plain
  version of it.
- If something was not checked or not run, say so plainly.
- Do not claim the reader approved anything they have not approved.

## Check before sending

Read each sentence and ask: would a bright friend who has never seen this
project understand it? Does every request say exactly what reply you need?
If not, rewrite that sentence.

## Afterwards

- Stay at this level for the rest of the session. Offer depth ("say 'more'
  on any item") instead of supplying it.
- If the user has had to ask for plain language more than once, and a memory
  or preferences system is available, save that as a standing preference so
  future sessions start in plain language.
