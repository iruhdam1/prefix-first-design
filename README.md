# Prefix-First Design

**You've explained your user three times today. Twice to the same AI.**

You prototype in Cursor, ship from a repo, and still rebuild context from scratch every session — re-explain the user, re-establish the constraints, watch the output drift from what you meant. The fix isn't better prompts. It's a brief that doesn't move.

Prefix-First Design treats the brief as scaffolding. Set the stable parts once, explore against them freely, carry decisions forward explicitly. The scaffold quality determines what gets built on it.

By [Madhuri Maram](https://madhurimaram.com) · [Read the full article](https://madhurimaram.com/work/ai/patterns/prefix-first)

**What you get:**

- A **brief template** — problem, user, hard constraints, locked decisions. Five fields, one screen.
- **Session rules for Claude** — it grades your brief before ideating, flags drift when the problem quietly changes, and labels every output EXPLORING or DECIDED.
- A **close-out ritual** — 60 seconds at session end so tomorrow's session starts where today's stopped.

## Starting fresh? Paste this.

Copy [`skill/SKILL-compact.md`](skill/SKILL-compact.md), fill in the brackets, make it message one in any Claude, v0, or Cursor session. Five minutes before you open a tool; it pays back the first time you *don't* re-explain your user.

## Have a repo? Add this file.

Drop [`skill/SKILL.md`](skill/SKILL.md) into your project — Claude Projects instructions, `.claude/skills/`, or referenced from `CLAUDE.md`. Agents read the brief before touching anything. Decisions travel with the work, not in your head.

**Proof:** [Four concepts in 45 minutes from one brief that never moved →](examples/tone-selector-prefix.md)

---

## The three rituals

**1. Cast the brief** — before you open Figma or Cursor, write down what isn't allowed to change: the user problem, the real constraints, the principles you're optimising for. If you can't fill in the brief, *that's* the design problem — solve it first.

**2. Ship the decisions** — when work lives in a repo, the brief lives there too. A page ledger, a decision log — whatever form, agents and teammates read it before changing anything. At Aampe, I run a [playground of shipped internal tools](https://madhuri.substack.com/p/building-an-app-playground-using-claude-replit) this way: when I asked an agent to fix a CTA gap on the Relay page, it read the page ledger first and didn't re-litigate a footer decision from three sessions ago. The ledger did the arguing for me. ([How that working setup looks day to day →](https://madhuri.substack.com/p/designing-with-ai-agent-aampe))

**3. Check it still holds** — live products drift. Once a month, 20 minutes, three questions: Is the brief still true? Did anything ship that contradicts a locked decision? What did we learn that should *become* a locked decision? One dated entry in a `still-holds.md` log. That's the whole ritual. (It's how [tinydesignshop.com](https://tinydesignshop.com) stays coherent across agent sessions.)

---

## Inside a session

All ideation runs against the stable brief. Go wide — multiple directions, divergent concepts. Everything is labeled:

- **EXPLORING** — ideas being tested against the brief
- **DECIDED** — locked; the next phase builds on it

If exploration reveals the brief was wrong, stop and update it out loud. Never quietly revise the problem mid-session — that's how a working prototype ends up answering a question nobody asked.

## Closing a session

End with a session close-out. Here's a real one:

> **Session close-out — Dec 12 — Tone selector, concept round**
>
> - **Locked:** Primary interaction is a tone selector, not a freeform prompt. Users pick presets, they don't write instructions.
> - **Explored, not locked:** Spider-chart tone analysis — promising, needs a real copy dataset.
> - **Open for next session:** Does intensity need its own control, or is it a tone property?
> - **Brief changes:** none. It held.

Paste it into the next session's brief as WHAT HAS ALREADY BEEN DECIDED. The empty template is in [`skill/SKILL.md`](skill/SKILL.md).

---

## What's in this repo

```
prefix-first-design/
├── README.md                       — this file
├── skill/
│   ├── SKILL.md                    — full skill: session rules + brief template + close-out
│   └── SKILL-compact.md            — single-session version, paste as message one
└── examples/
    ├── tone-selector-prefix.md     — a real filled brief and what it enabled
    └── still-holds-template.md     — the monthly three-question check
```

---

*Why "prefix"? Prompt caching keeps the stable part of the context — the prefix — and only reprocesses what changes. Change the prefix, pay full cost again. Same rule, applied to design sessions. That's the whole metaphor; you never need to think about it again.*

Framework by [Madhuri Maram](https://madhurimaram.com) — named after a prompt-caching idea, built from 15+ shipped prototypes.

Version 2.1.0 · MIT — copy, adapt, use freely. Attribution appreciated but not required.
