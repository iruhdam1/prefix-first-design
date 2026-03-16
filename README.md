# Prefix-First Design

A prototyping framework for AI-assisted design and prototyping, named after how prompt caching works.

By [Madhuri Maram](https://madhurimaram.com) · [Read the full article](https://madhuri.substack.com/p/prefix-first-design-claude-skill)

---

## The idea

Most designers rebuild context from scratch every AI session. Re-explain the user, re-establish the constraints, re-orient the model. Then wonder why sessions lose coherence or take forever to get somewhere useful.

Prompt caching in Claude Code works on a simple rule: cache the stable parts, vary only what needs to vary. Change anything in the cached prefix and you pay full cost again.

Prefix-First Design applies the same rule to design sessions.

Set the base once. Explore against it freely. Carry decisions forward explicitly. Never rebuild what you've already established.

---

## What's in this repo

```
prefix-first-design/
├── README.md                          — this file
├── skill/
│   ├── SKILL.md                       — full skill file for Claude Projects
│   └── SKILL-compact.md               — lightweight version for single sessions
└── examples/
    └── tone-selector-prefix.md        — filled prefix example from real work
```

---

## How to use

### Option A — Claude Project (recommended)

1. Open or create a Claude Project at claude.ai
2. Go to Project Instructions
3. Copy the contents of `skill/SKILL.md`
4. Paste it as your project instruction
5. Start every session by filling in the prefix template and sending it as your first message

Claude will hold your prefix as the session base, flag when the conversation drifts from it, label outputs as EXPLORING or DECIDED, and close every session with a Breakpoint Summary.

### Option B — Single session

1. Copy the contents of `skill/SKILL-compact.md`
2. Fill in the bracketed fields
3. Paste it as the first message in any Claude, v0, or Cursor session

---

## The five steps

**1. Cast the Prefix** — Write down what isn't allowed to change before you open any tool: the user problem, real constraints, design principles. Set it once.

**2. Lay Breakpoints** — When you make a decision mid-session, lock it into the prefix explicitly. Not as a note — as a constraint the next phase builds on.

**3. Explore in Messages** — All ideation runs against the stable base. If exploration reveals the prefix was wrong, that's a new session, not a quiet edit.

**4. Fork With Context** — Every handoff carries the prefix forward. A prototype without its problem frame is just a screen.

**5. Test the Prefix** — Before testing with users, ask: does this still match what we said was true at the start? A broken prefix is more valuable than a broken interaction.

---

## Versions

| File | Use for |
|------|---------|
| `skill/SKILL.md` | Claude Projects — paste as project instruction |
| `skill/SKILL-compact.md` | Individual sessions — paste as first message |

---

## Credits

Framework by [Madhuri Maram](https://madhurimaram.com)  
Structurally informed by [Claude Code's prompt caching architecture](https://www.anthropic.com)  
Version 2.0.0

---

## Licence

MIT — copy, adapt, use freely. Attribution appreciated but not required.
