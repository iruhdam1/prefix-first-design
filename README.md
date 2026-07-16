# Prefix-First Design

**You've explained your user three times today. Twice to the same AI.**

You prototype in Cursor, ship from a repo, and still rebuild context from scratch every session — re-explain the user, re-establish the constraints, watch the output drift from what you meant. The fix isn't better prompts. It's a brief that doesn't move.

Prefix-First Design treats the brief as scaffolding. Set the stable parts once, explore against them freely, carry decisions forward explicitly. The scaffold quality determines what gets built on it.

By [Madhuri Maram](https://madhurimaram.com) · [Read the full article](https://madhurimaram.com/work/ai/patterns/prefix-first)

**What you get:**

- A **brief template** — problem, user, hard constraints, locked decisions. Five fields, one screen.
- **Session rules for agents** — grade the brief before ideating, flag drift when the problem quietly changes, and label every output EXPLORING or DECIDED.
- A **two-reader close-out** — human skim + next-agent instructions, so tomorrow's session starts where today's stopped.

## Light path vs full path

**Light path** — one session. Copy [`skill/SKILL-compact.md`](skill/SKILL-compact.md), fill in the brackets, make it message one in any Cursor, v0, ChatGPT, or agent session. Five minutes before you open a tool; it pays back the first time you *don't* re-explain your user.

**Full path** — work that lives in a repo. Drop [`skill/SKILL.md`](skill/SKILL.md) into your project — agent instructions, a skills folder, or referenced from your project guide (`AGENTS.md` or equivalent). Keep a brief, page ledger, or decision log with the work. Agents start by reading it. Once a month, run the still-holds check.

Same brief. Same rules. Different weight.

**Proof:** [Four concepts in 45 minutes from one brief that never moved →](examples/tone-selector-prefix.md)

---

## The three rituals

**1. Cast the brief** — before you open Figma or Cursor, write down what isn't allowed to change: the user problem, the real constraints, the principles you're optimising for. If you can't fill in the brief, *that's* the design problem — solve it first. After the brief grades clean, an optional **frame pass** asks up to five questions that would actually change what you build — then folds the answers back into the brief.

**2. Ship the decisions** — when work lives in a repo, the brief lives there too. A page ledger, a decision log — whatever form, agents and teammates read it before changing anything. At Aampe, I run a [playground of shipped internal tools](https://madhuri.substack.com/p/building-an-app-playground-using-claude-replit) this way: when I asked an agent to fix a CTA gap on the Relay page, it read the page ledger first and didn't re-litigate a footer decision from three sessions ago. The ledger did the arguing for me. ([How that working setup looks day to day →](https://madhuri.substack.com/p/designing-with-ai-agent-aampe))

**3. Check it still holds** — live products drift. Once a month, 20 minutes, three questions: Is the brief still true? Did anything ship that contradicts a locked decision? What did we learn that should *become* a locked decision? One dated entry in a `still-holds.md` log. That's the whole ritual. (It's how [tinydesignshop.com](https://tinydesignshop.com) stays coherent across agent sessions.)

---

## Inside a session

Start by reading the last close-out and any brief or ledger in the repo. Mirror state in a few lines. Then hold the brief.

All ideation runs against the stable brief. Go wide — multiple directions, divergent concepts. Everything is labeled:

- **EXPLORING** — ideas being tested against the brief
- **DECIDED** — locked; the next phase builds on it

**Deviation vs drift:** an implementation detail that still serves the same problem can be logged and continued. A quiet change to the problem frame or a locked decision is drift — stop, name it, choose. Never quietly revise the problem mid-session — that's how a working prototype ends up answering a question nobody asked.

## Closing a session

End with a two-reader close-out. Top half for you. Bottom half for the next agent (recommended focus, what's agent-doable, what needs you, what's out of scope). Here's the shape:

> **Session close-out — Dec 12 — Tone selector, concept round**
>
> Concept round against a fixed brief. Next: intensity control — property or separate?
>
> - **Locked:** Primary interaction is a tone selector, not a freeform prompt.
> - **Explored, not locked:** Spider-chart tone analysis — needs a real copy dataset.
> - **Open:** Does intensity need its own control?
> - **Brief changes:** none. It held.
>
> **For the next agent:** Start by reading this close-out. Hold the brief before building. Recommended focus: **intensity control**. Needs the human: taste call on intensity. Out of scope: freeform prompt.

The empty template is in [`skill/SKILL.md`](skill/SKILL.md).

---

## What's in this repo

```
prefix-first-design/
├── README.md                       — this file
├── skill/
│   ├── SKILL.md                    — full path: session rules + brief + two-reader close-out
│   └── SKILL-compact.md            — light path: paste as message one
└── examples/
    ├── tone-selector-prefix.md     — a real filled brief and what it enabled
    └── still-holds-template.md     — the monthly three-question check
```

---

*Why "prefix"? Prompt caching keeps the stable part of the context — the prefix — and only reprocesses what changes. Change the prefix, pay full cost again. Same rule, applied to design sessions. That's the whole metaphor; you never need to think about it again.*

Framework by [Madhuri Maram](https://madhurimaram.com) — named after a prompt-caching idea, built from 15+ shipped prototypes.

Version 2.2.0 · MIT — copy, adapt, use freely. Attribution appreciated but not required.
