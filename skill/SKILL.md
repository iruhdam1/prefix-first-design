---
name: prefix-first-design
version: 2.2.0
description: >
  A session framework for AI-assisted product design based on Prefix-First Design.
  Helps designer-builders cast a stable brief once, explore against it freely,
  ship decisions with the work, and check that the brief still holds as products live on.
  Built from 15+ shipped prototypes by Madhuri Maram (madhurimaram.com).
owner: "[Your name]"
context: AI-assisted product/UX prototyping and shipping
---

# Prefix-First Design

A session framework for designing and shipping with AI tools (Claude, v0, Cursor, agents).
The brief is the scaffold: protect the stable parts so the dynamic parts can move freely.
The scaffold quality determines what gets built on it.

Vocabulary: the **brief** is the stable base (the "prefix"). A **locked decision** is one
the next phase builds on. The **session close-out** is the decision ledger you carry forward —
written for two readers: you (skim) and the next agent (instructions).

---

## Light path vs full path

- **Light path** — paste [`SKILL-compact.md`](SKILL-compact.md) as message one. One session,
  one brief, close-out at the end. Use for exploration days and throwaway prototypes.
- **Full path** — this file in the repo, plus a brief / page ledger / decision log that ships
  with the work, plus monthly still-holds for live products. Use when sessions stack and
  the product has to stay coherent.

Same brief. Same rules. Different weight.

---

## When to use this skill

Activate when a user:
- Shares a problem frame and asks to prototype or explore design directions
- Opens a new design session and needs to establish context
- Is mid-session and losing coherence or repeating context
- Is handing off work to a developer, stakeholder, agent, or new session
- Is working in a repo that contains a brief, page ledger, or decision log

Do not activate for one-off questions, quick edits, or tasks with no
stated product or user context.

---

## Instructions for Claude

### Start by reading

Before generating anything, read what already exists:

- The last session close-out (if the human pasted one, or it lives in the repo)
- The brief, page ledger, or decision log if the project has one

Mirror the state in 2–3 plain lines: where things stand, what's locked, what needs
the human before work starts. Then confirm direction. Do not draft or build until
the brief is held.

### Grade the brief before you build on it

When the user shares a brief (or you find one in the repo), check it before ideating.
Be a warm roast, not a bureaucrat — one short pass, specific, then move on.

Check each field:

- **PROBLEM FRAME contains a solution.** "A dashboard that shows…" is not a problem —
  it's a feature request wearing a trench coat. Say so, and ask what the user can't do today.
- **USER is a persona, not a person.** "Busy professionals" holds nothing. Ask for one real
  detail: what do they already know, what are they in the middle of doing?
- **CONSTRAINTS are preferences.** "Should feel modern" is taste, not a constraint.
  Keep only what is genuinely not allowed to change — technical, business, scope.
- **PRINCIPLES don't filter.** If a principle couldn't reject any idea, it's decoration.
  Ask: what would this principle say no to?

If two or more fields fail, do not ideate yet. Say what's vague, why exploring against it
would waste the session, and offer to fix the brief together first. A sharpened brief is
the first deliverable, not a delay.

If the brief is solid, say so in one line. Optionally run the frame pass (below), then start.

### Optional frame pass (after a solid brief)

Grading checks whether the brief is sharp. The frame pass asks what the brief left open —
the questions the designer didn't know to ask.

Only run it when an answer would change scope, sequencing, taste, or priorities.
Hard cap: 3–5 questions. If nothing meets that bar, say so in one line and skip.

1. **Blindspot brief** — a few sentences on what good looks like in this domain, what this
   project has already decided, and the known potholes. Unknown unknowns, not a plan summary.
2. **Interview** — one question at a time, ordered by blast radius (biggest plan change first).
   Anchor each question to the brief. Offer concrete options and mark a recommendation.
3. **Fold** — write answers into the brief (or ledger) in place. Add taste checkpoints when
   the human will need to eyeball something at verification time.

Prompt to use:
> "Brief graded. Run a frame pass — only questions that would change what we build."

### Treat the brief as infrastructure

Never suggest solutions that contradict the stated problem frame or constraints
without explicitly flagging the conflict first.

### Deviation vs drift

Not every departure is a brief crisis.

- **Deviation** — an implementation detail that still serves the same problem frame and
  locked decisions. Log it (in the close-out or ledger) and continue.
- **Drift** — the conversation or the build starts answering a different problem, or
  quietly overturns a locked decision. Stop. Name what changed. Make the user choose:
  update the brief deliberately, or return to it.

Never quietly follow drift. Never treat every pixel change as drift.

### Stop at drift — name it, don't ride it

If the conversation moves away from the brief, stop before producing more output.
Name exactly what changed: "We started with [X]; this direction assumes [Y]."
Then make the user choose: update the brief deliberately, or return to it.
Never quietly follow the drift — a prototype that answers a different question
than the brief asked is the most expensive kind of progress.

### Separate exploration from decisions

Label outputs clearly:
- EXPLORING — ideas being tested against the brief
- DECIDED — locked; added to the brief for the next phase to build on

### Flag repeated context

If the user re-explains something already in the brief, note it:
"That's already in the brief — should I update it or use what's there?"
Repeated context is a signal the brief is too vague to hold. Offer to sharpen it.

### End every session with a close-out

Before closing, output the Session Close-out template from Section 3.

---

## Section 1 — The Brief Template

This is the stable base. Set it once. Do not rewrite it mid-session.
If something here turns out to be wrong, stop, update it deliberately,
and start a new session from the revised base.

```
PROBLEM FRAME
What is the user problem we are solving?
[1–3 sentences. Be specific. Avoid solution language.]

USER
Who is this for? What do they already know? What are they trying to do?
[1–3 sentences. Real details beat personas.]

CONSTRAINTS (fixed)
What is genuinely not allowed to change?
[Hard constraints only — technical, business, scope. Not preferences.]

DESIGN PRINCIPLES
What are we optimising for in this product?
[2–4 principles max. These filter decisions, not generate ideas.]

WHAT HAS ALREADY BEEN DECIDED
What decisions are load-bearing going into this session?
[Locked decisions from prior sessions that the current session builds on.]
```

---

## Section 2 — The Three Rituals

### Ritual 1 — Cast the brief (before any tool)

Fill in Section 1 completely before generating anything.
If you can't fill it in, that is the design problem to solve first.

Prompt to use:
> "Here is my brief. Grade it, then hold it as the base for this session."

As you work, lock decisions the moment they're made:
> "We've decided [X]. Lock it into the brief."

A locked decision is one the next phase builds on — not a note, not a maybe.

Run all ideation against the stable brief. Go wide — multiple directions,
divergent concepts, variations. If an exploration reveals the brief was wrong,
stop and update it explicitly. Do not quietly revise the problem frame mid-session.

> "Explore [X] against the current brief. Don't change the problem frame."

### Ritual 2 — Ship the decisions (when work lives in a repo)

The brief doesn't stay in the chat — it ships with the work. Keep a brief file,
page ledger, or decision log in the repo, and read it before changing anything.
Decisions travel with the work, not in anyone's head.

Every handoff — to a developer, a stakeholder, an agent, another session —
carries the brief forward, not just the artifact. A prototype without its
problem frame is just a screen.

Prompt to use:
> "Prepare a handoff block for [developer / next session / stakeholder].
>  Include the current brief, locked decisions, and open questions."

### Ritual 3 — Check it still holds (for live products)

Live products drift away from their briefs. Once a month, 20 minutes, three questions:

1. Is the brief still true? (Have the users or constraints changed?)
2. Did anything ship that contradicts a locked decision?
3. What did we learn that should become a locked decision?

Log one dated entry in a `still-holds.md` file (template in `examples/`).
Before testing with users, apply the same check: does this still match what we
said was true at the start? If not, that is the finding — a broken brief is
more valuable than a broken interaction.

> "Review what we've built against the brief. What has held?
>  What does this reveal about the problem frame?"

---

## Section 3 — Session Close-out Template

Run this at the end of every session. It is the decision ledger for two readers:
the human skims the top; the next session's agent follows the bottom.

Paste the whole block into the next session (or leave it in the repo). The next
agent starts by reading it — see Start by reading.

```
## Session close-out — [Date] — [Session name or goal]

[One short paragraph for the human: what this session focused on, what's left,
and the recommended focus next time. Plain English. No file dumps.]

Brief state at close:
  Problem frame: [current version]
  User: [current version]
  Constraints: [current version]
  Principles: [current version]

Locked this session (add to brief):
  - [Decision 1]
  - [Decision 2]

Explored but not locked (do not carry forward as constraints):
  - [Idea 1]
  - [Idea 2]

Deviations logged (same brief, different implementation detail):
  - [Deviation — or "none"]

Open questions for next session:
  - [Question 1]
  - [Question 2]

Brief changes made:
  - [What changed and why — or "none. It held."]

---

**For the next agent:**

1. Start by reading this close-out and any brief / page ledger / decision log in the repo.
2. Mirror state in 2–3 lines, then hold the brief. Do not build until the brief is held.
3. Recommended focus: **[one phrase]**
4. Agent-doable without the human:
   - [Item — or "None"]
5. Needs the human — do not pick up unsupervised:
   - [Item — or "None"]
6. Out of scope:
   - [Item — or "None"]
```

---

## Section 4 — Common Failure Modes

**You re-explained the user in message 4.**
The brief was too vague to hold. Go back to Section 1, make the user
description more specific, lock it in.

**The exploration quietly changed the problem frame.**
Stop. Name what changed. Decide: new session or brief update?
Either is fine — but make it explicit before continuing.

**You treated every implementation detail as drift.**
Log a deviation and continue when the problem frame still holds.
Reserve the stop for real drift — a different problem or a broken lock.

**You handed off the artifact without the context.**
Use the two-reader close-out before the next session starts.
The brief must travel with the work, not separately from it.

**The session got long and coherence dropped.**
Summarise decisions made into a new Session Close-out, open a new session,
paste it in as the brief.

**Something doesn't work in testing but you're not sure if it's
the interaction or the problem frame.**
Test the brief first. Ask a user: "Does this match the problem you
actually have?" before asking "Can you complete this task?"

---

## Credits

Framework by Madhuri Maram — madhurimaram.com
Named after a prompt-caching idea: the prefix is the part of the context that
doesn't change, and changing it means paying full cost again. Same rule, applied
to design sessions.
