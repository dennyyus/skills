# claude-skills

Custom skills for Claude Code by Denny Yusuf.

## Skills

### `dy-pm-skills`

One skill, two frameworks. Invoke with an argument:

| Command | What it does |
|---|---|
| `/dy-pm-skills validation` | Stress-tests a product problem statement |
| `/dy-pm-skills strategy` | Builds or evaluates a product strategy |

---

#### `validation` — Problem Validation

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

#### `strategy` — PSD Framework

A structured three-phase framework for building or evaluating product strategy. Based on the PM practice of Denny Yusuf, referencing Michael Porter's segmentation approach and Shreyas Doshi's product thinking.

**Phases:** Positioning (vision) → Segmentation (strategy) → Differentiation (execution)

**Trigger when:**
- Defining product strategy or market positioning
- Identifying target segments
- Building a competitive differentiation table
- Answering "who should we build for", "how do we differentiate", or "where do we play"
- Reviewing a positioning map, segmentation matrix, or competitive comparison

---

## Installation

Place the skill folder in your Claude Code skills directory:

```
~/.claude/skills/dy-pm-skills/SKILL.md
```

Or copy directly from this repo:

```
curl -o ~/.claude/skills/dy-pm-skills/SKILL.md --create-dirs \
  https://raw.githubusercontent.com/dennyyus/claude-skills/main/dy-pm-skills.md
```
