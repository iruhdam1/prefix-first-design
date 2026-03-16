---
name: prefix-first-design
version: 2.0.0
description: >
  A prototyping workflow for AI-assisted design based on the Prefix-First Design framework.
  Helps designers set a stable context base once, explore against it freely,
  and carry decisions forward across sessions and handoffs.
  Based on lessons from building AI prototypes by Madhuri Maram (madhurimaram.com).
owner: "[Your name]"
context: AI-assisted product/UX prototyping
---

# Prefix-First Design

A session framework for designing with AI tools (Claude, v0, Cursor, etc.)
Based on lessons from building 15+ AI prototypes since 2024.
Structurally informed by how prompt caching works in Claude Code.

The core constraint: protect the stable parts so the dynamic parts can move freely.

---

## When to use this skill

Activate when a user:
- Shares a problem frame and asks to prototype or explore design directions
- Opens a new design session and needs to establish context
- Is mid-session and losing coherence or repeating context
- Is handing off work to a developer, stakeholder, or new session

Do not activate for one-off questions, quick edits, or tasks with no
stated product or user context.

---

## Instructions for Claude

**Treat the prefix as infrastructure.**
Never suggest solutions that contradict the stated problem frame or constraints
without explicitly flagging the conflict first.

**Ask before drifting.**
If the conversation moves away from the prefix, pause and ask:
"This seems to go beyond the prefix — should we update it or keep exploring within it?"

**Separate exploration from decisions.**
Label outputs clearly:
- EXPLORING — ideas being tested against the prefix
- DECIDED — something ready to be added to the prefix for the next session

**Flag repeated context.**
If the user re-explains something already in the prefix, note it:
"You've already set this in the prefix — should I update it or use what's there?"

**End every session with a Breakpoint Summary.**
Before closing, output the Breakpoint Summary template from Section 3.

---

## Section 1 — The Prefix Template

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
[Decisions from prior sessions that the current session builds on.]
```

---

## Section 2 — Workflow Steps

### Step 1 — Cast the Prefix
Fill in Section 1 completely before generating anything.
If you can't fill it in, that is the design problem to solve first.

Prompt to use:
> "Here is my prefix. Hold this as the base for this session."

### Step 2 — Lay Breakpoints as You Decide
When a decision gets made mid-session, add it to WHAT HAS ALREADY BEEN DECIDED.
A breakpoint is a decision the next phase builds on — not a note, not a maybe.

Prompt to use:
> "We've decided [X]. Add this to the prefix as a breakpoint."

### Step 3 — Explore in Messages
Run all ideation against the stable prefix.
Go wide — multiple directions, divergent concepts, variations.
If an exploration reveals the prefix was wrong, stop and update it explicitly.
Do not quietly revise the problem frame mid-session.

Prompt to use:
> "Explore [X] against the current prefix. Don't change the problem frame."

### Step 4 — Fork With Context
Every handoff — to a developer, a stakeholder, another Claude session —
carries the prefix forward, not just the artifact.

Prompt to use:
> "Prepare a handoff block for [developer / next session / stakeholder].
>  Include the current prefix, decisions made, and open questions."

### Step 5 — Test the Prefix, Not Just the Prototype
Before testing with users, ask: does this still match what we said was true at the start?
If not, that is the finding — not a failure, but a signal to update the base.

Prompt to use:
> "Review what we've built against the prefix. What has held?
>  What does this reveal about the problem frame?"

---

## Section 3 — Breakpoint Summary Template

Run this at the end of every session.
Paste it into the next session's prefix as WHAT HAS ALREADY BEEN DECIDED.

```
BREAKPOINT SUMMARY — [Date] — [Session name or goal]

Prefix state at close:
  Problem frame: [current version]
  User: [current version]
  Constraints: [current version]
  Principles: [current version]

Decisions made this session (add to prefix):
  - [Decision 1]
  - [Decision 2]

Explored but not decided (do not carry forward as constraints):
  - [Idea 1]
  - [Idea 2]

Open questions for next session:
  - [Question 1]
  - [Question 2]

Prefix changes made:
  - [What changed and why]
```

---

## Section 4 — Common Failure Modes

A "cache miss" in this framework means a moment where context was lost
or had to be repeated unnecessarily — the design equivalent of paying
full cost when you shouldn't have to.

**You re-explained the user in message 4.**
The prefix was too vague to hold. Go back to Section 1, make the user
description more specific, mark it as a breakpoint.

**The exploration quietly changed the problem frame.**
Stop. Name what changed. Decide: new session or prefix update?
Either is fine — but make it explicit before continuing.

**You handed off the artifact without the context.**
Use the handoff block prompt before the next session starts.
The prefix must travel with the work, not separately from it.

**The session got long and coherence dropped.**
Summarise decisions made into a new Breakpoint Summary, open a new session,
paste it in as the prefix.

**Something doesn't work in testing but you're not sure if it's
the interaction or the problem frame.**
Test the prefix first. Ask a user: "Does this match the problem you
actually have?" before asking "Can you complete this task?"

---

## Credits

Framework by Madhuri Maram
madhurimaram.com
