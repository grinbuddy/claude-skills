---
name: handover
description: Write a date-stamped, topic-scoped handover document so a fresh session can continue the work cheaply — or pick one up and resume from it. Use when the user asks for a handover/handoff doc, wants to fork a topic into its own session, or says to resume/re-open a handover.
---

# Handover

Two modes. Detect which from the request: **write** (capture state for a
future session) or **pickup** (resume from an existing handover).

Handover docs are the project's audit trail of deep dives: date-stamped,
topic-scoped, findable months later. They capture TASK STATE — what memory
must not hold (memory is for durable facts and preferences; a handover is a
snapshot of work in flight).

## Where they live

`handovers/` at the project root. **Default this directory to git-ignored**
— handovers carry names, half-formed thinking, and private context; check
.gitignore and add `handovers/` if absent, telling the user. Only a
deliberately scrubbed handover ever belongs in version control.

Naming: `YYYY-MM-DD_<topic-slug>.md` (e.g. `2026-09-16_entity-formation.md`).
One topic per file — if the session spans several separable topics, ask
whether to fork them into separate handovers; that is the point of the
system.

## Mode 1 — write

1. **Scope it.** If the user named a topic, capture ONLY that thread, not
   the whole session. A general end-of-session handover may still fork into
   several topical files.
2. **Structure:**

```markdown
# Handover — <topic> (<date>)
**Status:** OPEN
**Continues:** <prior handover file, if this extends one> / fresh
**One-line mission:** <what this thread is trying to achieve>
**Pickup grade:** <frontier — judgment/strategy/adversarial work ahead |
mixed — frontier session that should delegate the listed mechanical subtasks
to lower-model subagents | execution — a lower model can run this from the
spec below> <one clause saying why>

## State — where things stand
<decisions made (with the WHY), what's done, what's ruled out>

## Open threads
<each: what, who holds the ball, next concrete action>

## Gotchas
<things the next session would waste an hour rediscovering>

## Pointers — read these, in this order
<repo-relative file paths; POINT at files, never duplicate their content —
 copies drift, pointers don't. Include line refs where useful.>

## Out of scope here
<adjacent topics deliberately excluded, and which handover covers them>
```

3. **Update the index.** `handovers/INDEX.md`, newest first:
   `| date | topic | status | file |` — create it if missing. The index is
   what makes "find that old deep-dive" a ten-second job.
4. **Close or supersede predecessors.** If this handover continues an older
   one, edit the old file's Status to `SUPERSEDED-BY <new file>` and fix its
   index row. Never leave two OPEN handovers on one topic.
5. **Route durable facts to memory, not the handover** — a preference or
   permanent fact learned this session goes in the memory system; the
   handover gets task state only.

## Mode 2 — pickup

1. No file named? Read `handovers/INDEX.md`, show OPEN handovers, confirm
   which (most recent on the named topic is the default guess).
2. Read the handover, then the Pointers **in the order given** — and only
   those files. Resist re-exploring; the doc exists so you don't.
3. Verify before acting: open threads may have moved since the doc was
   written (check the balls-in-court against reality — sent mail, new
   files, replies). State what changed since the handover, then continue
   the work.
3b. Honor the Pickup grade: on a frontier-model session, delegate the
   handover's mechanical subtasks to lower-model subagents rather than
   burning frontier tokens on execution work (see the user's model-economy
   norm in their global CLAUDE.md, if they keep one).
4. When the topic genuinely completes, set Status to `CLOSED` and update
   the index — an accurate index is the audit trail the user keeps this
   system for.
