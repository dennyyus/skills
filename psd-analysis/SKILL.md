---
name: psd-analysis
description: >-
  Build or evaluate a structured product strategy using a three-phase framework: Positioning (vision),
  Segmentation (strategy), Differentiation (execution). Use this skill whenever the user wants to define
  product strategy, evaluate market positioning, identify target segments, build a competitive differentiation
  table, or answer questions like "who should we build for", "how do we differentiate", "where do we play",
  or "what's our product strategy". Also trigger when user shares a positioning map, segmentation matrix,
  or competitive comparison and wants feedback.
---

# PSD Analysis

A three-phase analysis for building or evaluating product strategy.

**Core sequence:** Positioning → Segmentation → Differentiation

Positioning is a vision tool (where we aspire to be). Segmentation is a strategy tool (who we're building for). Differentiation is an execution tool (how we win with that segment). The order matters: vision sets direction, strategy narrows the target, execution proves the claim. Don't run differentiation before the target segment is locked.

**The failure mode to watch for.** Nearly every way this analysis goes wrong reduces to one habit: quietly reverse-engineering the artifact to flatter the product. A lone cell on the map, an empty quadrant, an all-strong row — treat every suspiciously clean result as an error until proven otherwise. Each phase reference carries the specific disguises this takes.

---

## Running it

Each phase has a reference file with its steps and the checks that catch the failure modes. **Read the phase's reference before running that phase** — the detail is what makes the output non-obvious, and it isn't in this file.

| Phase | Read first | Produces |
|---|---|---|
| 1 — Positioning | `references/positioning.md` | Competitor archetypes, 2x2 map, positioning statement |
| 2 — Segmentation | `references/segmentation.md` | Priority-ordered matrix, layers list, five-test scores, priority-1 narrative |
| 3 — Differentiation | `references/differentiation.md` | Scored factor table, D durability verdicts, strategy narrative |

When the output needs to become a document someone ratifies, read `references/strategy-doc.md` (Rumelt-kernel assembly, "what would make this wrong", analysis-vs-strategy framing).

Scope to what's asked. If the user wants feedback on an existing segmentation matrix, run Phase 2 against its reference — don't insist on all three phases.

---

## Guard rails

These hold across all phases:

- **No vanity positioning.** Axes and factors reflect user decision criteria, not product strengths.
- **No cherry-picked competitors.** Include the strongest archetype, even when unflattering.
- **Verify at the primary source.** Competitor claims come from the competitor, never from the client's own SEO or comparison content.
- **Attributes become axes only on evidence** of divergent LTV/churn — never on intuition.
- **The phases must chain.** Phase 1 archetypes are the Phase 3 columns. The Phase 2 priority-1 decision criteria are the Phase 3 factors. If they don't chain, you have three artifacts that don't add up to a strategy — say so before proceeding.
- **D without durability is misleading.** A D a competitor can replicate within a year is a roadmap item, not a strategic position.
- **Segment first, differentiate second.** A D on a factor the priority-1 segment doesn't care about is worth nothing.

---

## Output

Deliver each phase as its own artifact — they answer different questions and often have different audiences. After all three, offer a one-paragraph synthesis tying the positioning vision, the target segment, and the differentiation table into one strategy.

State conditional results plainly rather than smoothing them. "The segmentation is ahead of the product" is a finding, not a failure.

---

## Gotchas

Every failure mode this analysis is prone to, one line each. Scan before shipping: any line that trips means go back to that phase's reference, where it's explained in full. Also usable as a rubric for a reviewer or verifier pass.

**Positioning**
- Product alone in a cell → error until proven otherwise (binary / compound / unverifiable-split axis)
- All players on one diagonal → correlated axes; collapse or swap
- One brand across multiple cells → pick a home cell, rest are arrows
- Empty quadrant, no strong rival → axes reverse-engineered or a competitor is missing
- Competitor claim sourced from client SEO → re-verify at primary source

**Segmentation**
- "Try-first" / undecided given a cell → funnel stage, not a segment
- Capacity confused with disposition, or either read as "rich vs poor" → independent; disposition is within-cell
- Axis promoted on intuition → require divergent LTV/churn first
- Two cells tied on rank → force the order, name the reason
- X-cell with no reason → is it "can't afford" (risk) or "can't win" (marketing)?
- Internal-state axis with no signup signal → not findable yet; add intent question + telemetry

**Differentiation**
- Scored competitor competence, not the segment's use → regrade against the job
- B graded off complaint logs → need an incidence rate, and check whose segment the pain sits in
- Score drifted up during discussion → run the operational B-test, record it
- All-T column read as a strategy → that's a competent #2; the strategy is the named T→D conversions
- D a rival can copy in 6–12 months → roadmap item, not a moat (brand-locked gaps are more durable)

**Chain integrity**
- Phase 3 factors not from the Phase 2 #1 segment, or columns not the Phase 1 archetypes → phases don't chain
- No priority-1 narrative → the matrix has no anchor
- Jumped to differentiation before the segment was locked → reorder
