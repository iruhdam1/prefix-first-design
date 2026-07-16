# Prefix-First Design — Compact Version (light path)

For pasting into individual sessions (Claude, v0, Cursor, etc.)
Fill in the brackets before sending. Takes under 2 minutes.

For repo work that stacks across sessions, use the full skill (`skill/SKILL.md`)
plus a brief or page ledger — that's the full path.

---

```
# Prefix-First Design — Session Brief

PROBLEM FRAME: [1–2 sentences. What user problem are we solving? No solution language.]
USER: [1–2 sentences. A real person mid-task, not a persona.]
CONSTRAINTS:
  - [Hard constraint 1 — genuinely not allowed to change]
  - [Hard constraint 2]
PRINCIPLES:
  - [What we're optimising for — must be able to say no to an idea]
  - [What we're optimising for]
DECIDED: [Locked decisions this session builds on, or "none yet"]

Instructions:
- If I pasted a prior close-out, read it first. Mirror state in 2–3 lines before building.
- Grade this brief before ideating. If the problem frame contains a solution,
  the user is a vague persona, or the constraints are preferences — say so
  and help me fix it before generating anything.
- After a solid brief: optionally run a short frame pass (≤5 questions that would
  change what we build; options + recommendation). Skip if nothing qualifies.
- Then hold the brief as the stable base for this session.
- Do not suggest solutions that contradict it without flagging first.
- Drift (different problem / broken lock): stop and name what changed.
  Deviation (same brief, different implementation detail): log it and continue.
- Label all outputs as EXPLORING or DECIDED.
- End the session with a two-reader Session Close-out.
```

---

## Session Close-out (run at end of session)

Copy this, fill it in, paste into the next session as DECIDED (or as message one).

```
## Session close-out — [Date]

[One short paragraph: focus, leftovers, recommended next focus.]

Problem frame: [current version]
User: [current version]
Constraints: [current version]
Principles: [current version]

Locked this session:
  - [Decision 1]
  - [Decision 2]

Explored but not locked:
  - [Idea 1]

Deviations logged:
  - [or "none"]

Open questions:
  - [Question 1]

---

**For the next agent:**
Start by reading this close-out. Hold the brief before building.
Recommended focus: **[one phrase]**
Agent-doable: [items or "None"]
Needs the human: [items or "None"]
Out of scope: [items or "None"]
```

---

For the full skill with the three rituals and failure modes, see `skill/SKILL.md`.
