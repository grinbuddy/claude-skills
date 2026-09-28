# claude-skills

Personal [Claude Code](https://claude.com/claude-code) skills by
[@grinbuddy](https://github.com/grinbuddy). MIT licensed — take what's useful.

## sitrep

A situation report for the parts of a project that **aren't in the repo**:
inboxes, counterparties, commitments, deadlines — the world around the code.

Most status skills report code state (git, PRs, CI) and do it well. `sitrep`
is the operations-and-relationships complement. One word — `sitrep` — gets
you:

- **Deltas only** since the last check, across every source of truth the
  project declares — never a re-description of what you already know;
- **Balls-in-court**, with pattern-aware aging: five days of silence from a
  same-day replier is a signal; from a slow replier it's a Tuesday;
- **Your court, ranked by leverage** — the cheapest move that unblocks the
  most, first, including commitments *you* made that haven't visibly
  happened (it checks your sent mail before believing you);
- **Named blind spots** — channels the model can't see (WhatsApp, LinkedIn)
  get called out instead of silently omitted;
- **An explicit verdict** — "nothing on fire," or the opposite with a
  countdown.

### Install

Copy `skills/sitrep/SKILL.md` to:

- macOS/Linux: `~/.claude/skills/sitrep/SKILL.md`
- Windows: `%USERPROFILE%\.claude\skills\sitrep\SKILL.md`

Then say `sitrep` in any project.

### Per-project sources

The first run infers sources and offers to write a `## Sitrep sources`
section into the project's `CLAUDE.md` so later runs are deterministic.

Privacy pattern that has served well: keep the *mechanical* sources
(commands, file paths) in the versioned `CLAUDE.md`, and put anything about
*people* — names, inbox queries, response patterns — in a git-ignored file
the manifest points to. Nothing about people belongs in a versioned file if
the repo might ever be public.

### Complements, not competitors

For code-state reporting, see the existing ecosystem: git/PR/CI-grounded
sitreps, multi-agent SITREP coordinators, and live HTML status panels —
e.g. [fullstackhouse/skills](https://github.com/fullstackhouse/skills),
[levnikolaevich/claude-code-skills](https://github.com/levnikolaevich/claude-code-skills).
This skill picks up where the repository's edge ends.

## handover

A date-stamped, topic-scoped handover document so a fresh session can pick
up a thread cheaply — the between-session half of the same economy `sitrep`
serves within a session.

Two modes, detected from the request:

- **write** — capture one thread's task state: decisions (with the why),
  open threads and who holds each ball, gotchas, and *pointers* to files in
  reading order rather than copies of them (copies drift, pointers don't).
  Each handover carries a **pickup grade** — frontier / mixed / execution —
  saying how much model the continuation actually needs, so the next session
  can delegate the mechanical parts to a cheaper tier;
- **pickup** — read the handover and its pointers in order, verify the open
  threads against reality (sent mail, replies, new files) before acting,
  then continue.

Handovers live in a git-ignored `handovers/` directory with a newest-first
`INDEX.md`, so "find that deep-dive from three months ago" is a ten-second
job. Durable facts and preferences go to memory; a handover holds work in
flight only.

### Install

Copy `skills/handover/SKILL.md` to:

- macOS/Linux: `~/.claude/skills/handover/SKILL.md`
- Windows: `%USERPROFILE%\.claude\skills\handover\SKILL.md`

Then say "write a handover for <topic>" or "pick up the <topic> handover".

## tldr

A plain-English recap for the moment you lose the thread. Long sessions drift
into ticket numbers, branch names and acronyms; `tldr` makes the model stop
and rewrite what it already knows for a smart reader who is not carrying
those labels in their head.

The answer always has the same four parts:

- **Bottom line** — is anything broken, and do I need to do something now;
- **What happened** — two to four bullets in everyday words, including what
  did *not* change when that is the reassuring part;
- **What I need from you** — numbered, one decision each, phrased so a
  one-word reply works, with a recommendation and what happens if you do
  nothing;
- **What can wait** — one or two lines, not a list.

The rules that matter: no label appears without a plain description in front
of it, jargon is swapped for its effect, and simple words never soften bad
news or drop a hard decision. It is a rewrite, not new work — nothing gets
re-investigated to produce it.

### Install

Copy `skills/tldr/SKILL.md` to:

- macOS/Linux: `~/.claude/skills/tldr/SKILL.md`
- Windows: `%USERPROFILE%\.claude\skills\tldr\SKILL.md`

Then say `tldr`, "I'm lost" or "in plain English" in any project.

---

Built in the field on [Project Terra](https://bantaydagat.org) — an
open-source marine conservation effort in the Philippines — working with
Claude. `sitrep` exists because a one-word morning catch-up turned out to be the
single highest-leverage habit in a partner-heavy project; `handover` exists
because the second-highest was never dragging a long context into a new day.
