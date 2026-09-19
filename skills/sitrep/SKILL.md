---
name: sitrep
description: Situation report — check every source of truth for this project, report what changed since last check, who holds each open ball, and what the user's highest-leverage moves are. Use when the user says "sitrep", asks to be caught up, or opens a session after a gap.
---

# Sitrep

Produce a situation report: not a status dump, a **decision surface**. The
reader has been away; give them exactly what changed, what's waiting on whom,
and what their next move should be — then stop.

## 1. Find this project's sources of truth

Look for a `## Sitrep sources` section in the project's CLAUDE.md. It lists
what to check and how (commands, queries, files, dashboards). Check ALL of
them, in parallel where possible.

If no such section exists, infer reasonable sources (recent git log, inbox
searches for known counterparties, project tracking files, CI status), run
the sitrep from those — and then OFFER to write the `## Sitrep sources`
section so the next sitrep is deterministic. Keep the manifest current: when
a new recurring source appears in the project's life, add it.

## 2. Report structure (in this order)

1. **Headline** — one line: the single most important development, or
   "quiet since <last marker>."
2. **What changed** — deltas only. Never re-describe standing state the
   user already knows; a sitrep that repeats yesterday's sitrep is noise.
   If nothing changed on a channel, one clause says so.
3. **Balls in others' courts** — who owes what, and how long it's been
   outstanding. Flag items that have drifted OUT OF THE COUNTERPARTY'S OWN
   PATTERN (someone who replies same-day going silent for 5 days is signal;
   a slow replier at 5 days is not). Distinguish "aging normally" from
   "worth a nudge" and say which.
4. **The user's court** — their open items, ranked by what each unblocks,
   not by age. Name the single cheapest high-leverage move first. Include
   anything the user committed to that has not visibly happened (check sent
   mail / commits / files before assuming).
5. **Verdict** — "nothing on fire" or the opposite, explicitly. If a
   deadline is approaching, count the days.

## 3. Conduct rules

- **Verify, don't assume.** "You said you'd send X" → check whether X was
  actually sent before listing it as done or undone — and when a draft file
  exists, read the sent body against it and report any difference. Editors
  can preview a stale copy; the user may have pasted an old version.
- **Deltas need a baseline** — keep or find the previous sitrep's state
  (conversation history, a log file, or the sources themselves) so "no
  change" is a checked claim, not a guess.
- **Surface silence as data** when it breaks a pattern; otherwise let quiet
  channels be quiet.
- **End with at most one question or offer** — the sitrep's job is to make
  the user's next 5 minutes obvious, not to open ten threads.
- **Blind spots**: name any channel you cannot see (e.g., WhatsApp, LinkedIn,
  a system without access) so the user knows to fill that gap themselves.
- Tables for the courts; prose for everything else; no headers for a quiet
  day — a short sitrep is a feature.

## 4. Per-project manifest format (what to put in CLAUDE.md)

```markdown
## Sitrep sources
- <command to run>            # what it reveals
- <inbox/search query>        # which counterparties matter
- <file or directory to read> # where commitments/threads are tracked
- Blind spots: <channels the user must check themselves>
- Counterparty patterns: <name — usual response latency>
```
