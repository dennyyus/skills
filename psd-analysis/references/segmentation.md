# Phase 2 — Segmentation (Strategy)

Read this before running Phase 2.

**Goal:** identify the highest-priority winnable segment using a Porter-style needs-based matrix. A good segmentation is worth more than any individual feature decision.

**Produces:** a 4–6 cell matrix with forced priority order, a "layers below the matrix" list, a scored five-test checklist, and the priority-1 narrative.

---

## 1. Choose segmentation dimensions

Use needs-based dimensions first. If needs alone are insufficient to create meaningful, distinct segments, move down this priority order:

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

Three disciplines when picking dimensions:
- **Attributes become axes only on evidence.** Promote an attribute to an axis only when it's tied to divergent LTV or churn — never on intuition that it "feels" segmenting. Everything else is a within-cell modifier (see step 3).
- **Capacity is not disposition, and neither is "rich vs poor."** Ability-to-pay (cash-flow slack, visible in billing telemetry) and value-orientation (aspiration-led vs value-led) are independent. Disposition is usually a within-cell modifier and an underwriting signal, not an axis.
- **Transitional states are not segments.** Anything a customer resolves out of within a term or two — "try-first", undecided, trialing — is a funnel stage. Don't give it a cell; measure what it resolves into.

## 2. Build the segmentation table

Rows and columns represent the chosen dimensions. Each cell is either:
- A number (1, 2, 3...) indicating priority — 1 is highest
- An x indicating a segment you are deciding not to pursue

Example structure:

| Y: Adoption motion \ X: Needs | Religious-driven | Cause-driven |
|---|---|---|
| RC/DHC givers | **1** | x |
| Routine manual givers | 2 | 4 |
| CC-driven manual givers | 3 | x |

Standards for the finished matrix:
- **Concrete, pointable labels.** Aim for the canonical Stripe/Slack look: 4–6 cells, two dimensions, labels that name a specific kind of person — not constructs or adjectives. Every cell should conjure an actual customer you could go find.
- **No tied priorities.** Two cells sharing a rank is a deferred decision. Force the ordering and state the reason — "already arriving, so we must serve them" beats "could theoretically win them" — but make the call.
- **X-cells are decisions with named reasons.** Distinguish "can't afford them" (a risk / underwriting reason) from "can't win them" (a stronger alternative already owns them, a marketing reason). The two route to different functions, so name which it is.
- **Encode the growth sequence in the numbers where you can.** Priority numbers can carry an expansion path, not just a ranking (Stripe's 1→2→3 is a route, not a leaderboard). If the expansion lives outside the matrix, name where.

## 3. Strip the matrix down to its layers

The delivered matrix is the clean top layer. Everything you worked through to get there — transitional/funnel states, dispositions, personas, GTM overlays — does not belong in the cells. Pull it into an explicit **"layers below the matrix"** list, e.g.:
- Funnel stages (trial → resolved)
- Catalog / creative splits
- Underwriting signals (disposition, ability-to-pay)
- GTM overlays (channel, motion)

This keeps the matrix pointable while preserving the working-out for whoever operationalizes it.

## 4. Run the five-test checklist (mandatory)

Score the segmentation against Shreyas Doshi's five tests before writing the narrative. Score honestly — partial and conditional passes are the useful signal, not a formality to wave through. If it fails outright, rebuild the dimensions rather than proceeding.

1. **Consistent needs** — core needs within each segment are fairly consistent, with non-trivial variance across segments. If two segments want the same thing, they are not distinct segments.
2. **Product-specific** — the approach is specific to your product or category. A generic cut (company size, age, geography) that could apply to any product won't drive decisions for yours.
3. **Prioritizable** — you can set genuinely different priorities, with clarity on highest-priority and explicit non-priorities. This is the matrix in step 2.
4. **Findable** — there is a reliable way to identify and reach customers in each segment. This is usually the weakest test for internal-state axes (needs, disposition, intent). Mitigate with a signup intent question plus telemetry so the base self-classifies — say so if that's the plan.
5. **Winnable** — you can build a differentiated value proposition for the highest-priority segments such that you can plausibly win, and winning is worthwhile. This is what Phase 3's differentiation table has to prove. Winnability is often conditional on roadmap gaps — if the product can't win the #1 segment today, say so plainly: *"the segmentation is ahead of the product."*

## 5. Priority-1 segment narrative

For the #1 cell, write a short description:
- Who they are (behavioral, not just demographic)
- Their decision criteria when choosing a platform or product
- Their current alternatives (what they'd use if this product didn't exist)
- Why this segment is winnable given the positioning in Phase 1

---

**Hands off to Phase 3:** the priority-1 segment's decision criteria become the Phase 3 factors. Nothing else may. Without this narrative, Phase 3 has no anchor.
