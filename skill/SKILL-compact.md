# Prefix-First Design — Compact Version

For pasting into individual sessions (Claude, v0, Cursor, etc.)
Fill in the brackets before sending. Takes under 2 minutes.

---

```
# Prefix-First Design — Session Base

PROBLEM FRAME: [1–2 sentences. What user problem are we solving?]
USER: [1–2 sentences. Who is this for and what are they trying to do?]
CONSTRAINTS: 
  - [Hard constraint 1]
  - [Hard constraint 2]
PRINCIPLES:
  - [What we're optimising for]
  - [What we're optimising for]
DECIDED: [Prior decisions this session builds on, or "none yet"]

Instructions:
- Hold this prefix as the stable base for this session.
- Do not suggest solutions that contradict it without flagging first.
- Label outputs as EXPLORING or DECIDED.
- End the session with a Breakpoint Summary.
```

---

## Breakpoint Summary (run at end of session)

Copy this, fill it in, paste into the next session as DECIDED.

```
BREAKPOINT SUMMARY — [Date]

Problem frame: [current version]
User: [current version]
Constraints: [current version]
Principles: [current version]

Decided this session:
  - [Decision 1]
  - [Decision 2]

Explored but not decided:
  - [Idea 1]

Open questions:
  - [Question 1]
```

---

For the full skill file with failure modes and workflow steps, see `skill/SKILL.md`.
