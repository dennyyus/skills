# claude-skills

Custom skills for Claude Code, based on the product thinking of Shreyas Doshi.

## Skills

### `problem-validation`

A Socratic framework for finding the true problem behind a product, not the dressed-up version. Uses three tests (Language, Body, Mechanism) to strip away analytical framing and get to the raw human motivation.

**Key features:**
- Asks questions instead of handing over answers — user arrives at the truth themselves
- Separates demand-side and supply-side problems (they're almost always different)
- Probes for two demand-side layers: crisis (what triggers sign-up) and baseline (what drives retention)
- Flags status and validation as a masked problem in social/visibility products

**Trigger when:**
- Someone says "the problem we solve is..." and you want to pressure-test it
- Separating demand-side from supply-side problems
- Checking if a stated problem is actually a solution wrapper
- Exploring why users keep coming back between acute needs

---

### `psd-framework`

A structured three-phase framework for building or evaluating product strategy.

**Phases:** Positioning (vision) → Segmentation (strategy) → Differentiation (execution)

**Trigger when:**
- Defining product strategy or market positioning
- Identifying target segments
- Building a competitive differentiation table
- Answering "who should we build for", "how do we differentiate", or "where do we play"
- Reviewing a positioning map, segmentation matrix, or competitive comparison

---

### `critical-discernment`

A judgment layer for product and strategy questions. Runs a four-step loop (Perceive, Project, Audit, Communicate) on its own first draft before answering, and again when you push back — so the output adds taste on top of the fluent-but-shallow default instead of agreeing with you.

**Key features:**
- Auto-triggers on "what do you think of X", "poke holes in this", PRD and strategy reviews, "should we build or kill X"
- Forces a committed call plus the principle behind it, the assumption to check first, and the specific failure mode
- Anti-capitulation protocol: updates only when a critique is sound and names what was wrong, instead of mirroring the last message
- Spots plausible retrofits: tidy narratives reverse-engineered from an outcome that cannot be acted on
- Models the buyer, champion, and blocker, not just the end user
- Ships with `references/slack-discernment-annotated.md`, a real transcript annotated against the loop

**Trigger when:**
- Pressure-testing a decision, plan, or strategy
- Reviewing a PRD, roadmap, or doc where a real call is at stake
- Giving a second opinion or weighing trade-offs
- You catch yourself about to produce a smooth, agreeable answer to a question that deserves a position

---

## Installation

Each skill is a folder. Place it in your Claude Code skills directory:

```
~/.claude/skills/problem-validation/SKILL.md
~/.claude/skills/psd-framework/SKILL.md
~/.claude/skills/critical-discernment/SKILL.md
~/.claude/skills/critical-discernment/references/slack-discernment-annotated.md
```
