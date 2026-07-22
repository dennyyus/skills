---
name: psd-framework
description: >-
  Build or evaluate a structured product strategy using a three-phase framework: Positioning (vision),
  Segmentation (strategy), Differentiation (execution). Use this skill whenever the user wants to define
  product strategy, evaluate market positioning, identify target segments, build a competitive differentiation
  table, or answer questions like "who should we build for", "how do we differentiate", "where do we play",
  or "what's our product strategy". Also trigger when user shares a positioning map, segmentation matrix,
  or competitive comparison and wants feedback.
---

# PSD Framework

A structured three-phase framework for building or evaluating product strategy.

**Core sequence:** Positioning → Segmentation → Differentiation

Positioning is a vision tool (where we aspire to be). Segmentation is a strategy tool (who we're building for). Differentiation is an execution tool (how we win with that segment). This order is non-negotiable: vision sets direction, strategy narrows the target, execution proves the claim.

---

## Phase 1 — Positioning (Vision)

### Goal
Map the competitive landscape and find an open, defensible position. Positioning is aspirational at this stage — it does not need to be fully proven yet.

### Steps

**1. Competitor landscape**

Group competitors into archetypes (typically 2–4 groups). Common archetypes:
- Market leaders (dominant generalist players)
- Category specialists (niche but strong in one area)
- Regional/vertical players (strong in a geography or industry)
- Direct mission competitors (same audience, different model)

For each group, identify: what they claim, who they serve, where they are strong.

**2. Positioning map**

Build a 2x2 map. Axes must be derived from how users actually decide, not from where the product already excels. Test: would a user evaluate options along this dimension? If axes were chosen to isolate the product in a favorable quadrant, flag as vanity positioning.

Plot all competitor groups. A clean empty quadrant with no rivals is suspicious — either the axes are reverse-engineered, or key competitors are missing.

**3. Positioning statement**

> "For [who], [product] aims to be the only [category] that [distinctive promise]."

Flag if:
- The promise is a feature, not a meaningful outcome
- The promise is something most competitors already deliver
- The "who" is too broad to be actionable

---

## Phase 2 — Segmentation (Strategy)

### Goal
Identify the highest-priority winnable segment using a Porter-style needs-based matrix. A good segmentation is worth more than any individual feature decision.

### Steps

**1. Choose segmentation dimensions**

Use needs-based dimensions first. If needs alone are insufficient to create meaningful, distinct segments, move to the next criterion in this priority order:

1. Needs
2. Jobs to be done
3. Category of needs
4. Distribution
5. Adoption motion
6. Decision maker
7. Role
8. Core competency
9. Sophistication
10. Geography

Use the minimum number of dimensions needed. A 2x2 or 3x3 matrix is usually sufficient.

**2. Build the segmentation table**

Rows and columns represent the chosen dimensions. Each cell is either:
- A number (1, 2, 3...) indicating priority — 1 is highest
- An x indicating non-viable or not worth pursuing

Example structure:

| Y: Adoption motion \ X: Needs | Religious-driven | Cause-driven |
|---|---|---|
| RC/DHC givers | **1** | x |
| Routine manual givers | 2 | 4 |
| CC-driven manual givers | 3 | x |

**3. Test the segmentation**

Before writing the priority-1 narrative, run the segmentation through five tests (Shreyas Doshi). If it fails any of these, the segmentation is not yet usable — rebuild the dimensions rather than proceeding.

1. **Consistent needs** — core needs within each segment are fairly consistent, with non-trivial variance across segments. If two segments want the same thing, they are not distinct segments.
2. **Product-specific** — the approach is specific to your product or category. A generic cut (company size, age, geography) that could apply to any product won't drive decisions for yours.
3. **Prioritizable** — you can set genuinely different priorities across segments, with clarity on which are highest priority and which are explicitly not. If everything is a priority, the segmentation isn't doing its job.
4. **Findable** — there is a reliable way to identify and reach customers in each segment. Some creative execution is fine; no way to find them is not.
5. **Winnable** — you can build a differentiated value proposition for the highest-priority segments such that you can plausibly win, and winning is worthwhile.

These chain into the rest of the framework: Prioritizable is the matrix in step 2, Findable is the go-to-market reality the step 4 narrative must address, and Winnable is what Phase 3's differentiation table has to prove. A #1 segment that passes here but earns no D in Phase 3 has failed the Winnable test in practice.

**4. Priority-1 segment narrative**

For the #1 cell, write a short description:
- Who they are (behavioral, not just demographic)
- Their decision criteria when choosing a platform or product
- Their current alternatives (what they'd use if this product didn't exist)
- Why this segment is winnable given the positioning in Phase 1

The segment narrative feeds directly into Phase 3 — the factors in the differentiation table must come from this segment's decision criteria.

---

## Phase 3 — Differentiation (Execution)

### Goal
Build a differentiation table that maps the priority-1 segment's decision criteria against competitor groups, then assigns the product a B/T/D rating for each factor.

### Steps

**1. Define factors**

Factors must come from the priority-1 segment's decision criteria identified in Phase 2 — not from the product's known strengths. Reverse-engineering factors from existing advantages produces a vanity differentiation table.

Typical number of factors: 5–8. More than 10 becomes unmanageable.

**2. Score competitors**

Use competitor groups from Phase 1 (no re-mapping needed). Score each group per factor on a 1–3 scale:
- 1 = weak or absent
- 2 = adequate
- 3 = strong

**3. Assign B/T/D for the product**

For each factor, assign one of:
- **B** (Below threshold) — product does not meet the minimum bar this segment expects. Action: fix or reconsider segment fit.
- **T** (Threshold) — product meets the bar but does not stand out. Action: maintain, don't over-invest.
- **D** (Differentiation) — product is genuinely ahead in a way that matters to this segment. Action: protect, deepen, amplify.

**4. Build the table**

| Factor | [Group 1] | [Group 2] | [Group 3] | [Product] |
|---|---|---|---|---|
| Factor A | 1–3 | 1–3 | 1–3 | B/T/D |
| Factor B | 1–3 | 1–3 | 1–3 | B/T/D |

**5. Stress-test D claims**

For each D, ask: is this a structural moat or a temporary head start?
- Structural moats: data advantages, network effects, regulatory position, deep segment trust built over time
- Temporary head starts: features that competitors can copy in 6–12 months

Flag temporary head starts — they are not real differentiation without a plan to widen the gap.

**6. Strategy narrative**

Write 2–3 sentences summarizing:
- Where the Ds land (the actual strategic bets)
- What Bs are blockers that need resolving before the strategy is viable
- Roadmap implication: Bs on key factors = fix first; Ts = maintain; Ds = build depth

---

## Guard Rails

- **No vanity positioning.** Axes and factors must reflect user decision criteria, not product strengths.
- **No cherry-picked competitors.** Always include the strongest archetype, even if unflattering.
- **No disconnected phases.** Competitor groups from Phase 1 feed Phase 3. Segment criteria from Phase 2 feed Phase 3 factors. If the phases are internally inconsistent, flag it before proceeding.
- **D without durability is misleading.** A D that competitors can replicate in a year is a roadmap item, not a strategic position.
- **Segment first, differentiate second.** A D on a factor the priority-1 segment doesn't care about is meaningless.

---

## Output Format

Deliver each phase sequentially. Do not combine phases into a single artifact — they answer different questions and may have different audiences.

After all three phases, offer a one-paragraph synthesis: how the positioning vision, the target segment, and the differentiation table connect into a coherent strategy.

---

## Gotchas

- **Vanity positioning.** The most common failure mode. Axes chosen to put the product in a favorable empty quadrant are reverse-engineered from strengths, not from user decision criteria. Test every axis: would a real user evaluate options along this dimension? If not, rebuild.
- **Cherry-picked competitors.** Always include the strongest archetype even if it's unflattering. A clean map with no strong rivals is a red flag — either the axes are wrong or the hardest competitor was left out.
- **Disconnected phases.** Phase 3 factors must come from the Phase 2 priority-1 segment's decision criteria. Phase 3 competitor groups must be the same archetypes from Phase 1. If the phases don't chain, the whole framework collapses into three independent artifacts that don't add up to a strategy.
- **D without durability.** A D a competitor can replicate in 6–12 months is a roadmap item, not a strategic position. Flag it explicitly rather than letting it masquerade as a moat.
- **Skipping segment narrative.** The segmentation matrix is worthless without the priority-1 narrative. That narrative is where the strategy lives — who they are, what they care about, what they'd use instead. Without it, Phase 3 has no anchor.
- **Solving for positioning before segmentation.** The phases are ordered for a reason. Don't let the user pressure you into jumping to differentiation before the target segment is locked — differentiation on a factor the priority-1 segment doesn't care about is meaningless.
