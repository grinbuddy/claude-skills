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

---

Built in the field on [Project Terra](https://bantaydagat.org) — an
open-source marine conservation effort in the Philippines — working with
Claude. The skill exists because a one-word morning catch-up turned out to be
the single highest-leverage habit in a partner-heavy project.
