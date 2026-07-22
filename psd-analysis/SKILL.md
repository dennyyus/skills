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

A structured three-phase analysis for building or evaluating product strategy.

**Core sequence:** Positioning → Segmentation → Differentiation

Positioning is a vision tool (where we aspire to be). Segmentation is a strategy tool (who we're building for). Differentiation is an execution tool (how we win with that segment). This order is non-negotiable: vision sets direction, strategy narrows the target, execution proves the claim.

Most failure modes below share one root cause: the analyst quietly reverse-engineers the artifact to flatter the product. Treat every clean result — an empty quadrant, a lone cell, an all-strong row — as an error until proven otherwise.

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

Verify claims at the **primary source** — the competitor's own site, pricing page, FAQ. Never characterize a rival from the client's SEO or comparison-blog content; "X vs Y" search results are usually polluted by the client's own marketing and will hand you a flattering, wrong picture.

While verifying, check whether a rival's position is **brand-locked**: if a competitor's brand ideology is the opposite pole of your differentiator, it cannot copy you without a brand U-turn. A brand-locked gap is far more durable than a feature gap — note it, it feeds Phase 3 durability.

**2. Positioning map**

Build a 2x2 map. Axes must be derived from how users actually decide, not from where the product already excels. Test: would a user evaluate options along this dimension? If axes were chosen to isolate the product in a favorable quadrant, flag as vanity positioning.

Prefer **jobs-based axes** — who does the work, what the customer hires the product for (cf. Teixeira's decoupling maps) — over deal-structure or product-attribute axes. Customer-type axes (e.g. Hertz vs Enterprise) are legitimate for where-to-play maps, but only if the two players genuinely serve different customers; verify that before using, don't assume it.

Plot all competitor groups, then run these checks:

- **Diagonal test.** If all players fall on one diagonal, the axes are correlated — you've drawn one dimension twice. Collapse to a single spectrum, or replace one axis. A 2x2 earns its second dimension only when the off-diagonal cells hold real businesses.
- **One player, one home cell.** A brand appearing in multiple cells is a refusal to choose, not strong positioning. Assign each player a single home cell. Choosing a home cell can be a strategic act, not just a description — e.g. picking the cell with the best unit economics against current demand evidence; if that's the move, say so and name the data that would validate it. Product lines that genuinely sit elsewhere are line extensions — draw them as arrows from the home cell, not as second homes.
- **Vanity-cell standing rule.** If the product lands alone in a cell, treat it as an error until proven otherwise. This pattern recurs in disguises — expect to catch yourself two or three times per map: a binary axis (has-it / doesn't), a compound axis ("certified + protected") that fuses two things to manufacture a private corner, or an unverifiable customer split. Kill each one and re-plot.
- **Empty quadrant.** A clean empty quadrant with no rivals is suspicious — either the axes are reverse-engineered, or key competitors are missing.

**Zoom-in (situational).** When the contested action is inside one cell, a second map drawn inside that cell is legitimate (e.g. Zipcar re-segmenting home-city renters). Keep it as a one-off artifact for that decision, not a standing part of the deliverable.

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

Three disciplines when picking dimensions:
- **Attributes become axes only on evidence.** Promote an attribute to an axis only when it's tied to divergent LTV or churn — never on intuition that it "feels" segmenting. Everything else is a within-cell modifier (see step 3).
- **Capacity is not disposition, and neither is "rich vs poor."** Ability-to-pay (cash-flow slack, visible in billing telemetry) and value-orientation (aspiration-led vs value-led) are independent. Disposition is usually a within-cell modifier and an underwriting signal, not an axis.
- **Transitional states are not segments.** Anything a customer resolves out of within a term or two — "try-first", undecided, trialing — is a funnel stage. Don't give it a cell; measure what it resolves into.

**2. Build the segmentation table**

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

**3. Strip the matrix down to its layers**

The delivered matrix is the clean top layer. Everything you worked through to get there — transitional/funnel states, dispositions, personas, GTM overlays — does not belong in the cells. Pull it into an explicit **"layers below the matrix"** list, e.g.:
- Funnel stages (trial → resolved)
- Catalog / creative splits
- Underwriting signals (disposition, ability-to-pay)
- GTM overlays (channel, motion)

This keeps the matrix pointable while preserving the working-out for whoever operationalizes it.

**4. Run the segmentation checklist (mandatory)**

Score the segmentation against Shreyas Doshi's five tests before writing the narrative. Score honestly — partial and conditional passes are the useful signal, not a formality to wave through. If it fails outright, rebuild the dimensions rather than proceeding.

1. **Consistent needs** — core needs within each segment are fairly consistent, with non-trivial variance across segments. If two segments want the same thing, they are not distinct segments.
2. **Product-specific** — the approach is specific to your product or category. A generic cut (company size, age, geography) that could apply to any product won't drive decisions for yours.
3. **Prioritizable** — you can set genuinely different priorities, with clarity on highest-priority and explicit non-priorities. This is the matrix in step 2.
4. **Findable** — there is a reliable way to identify and reach customers in each segment. This is usually the weakest test for internal-state axes (needs, disposition, intent). Mitigate with a signup intent question plus telemetry so the base self-classifies — say so if that's the plan.
5. **Winnable** — you can build a differentiated value proposition for the highest-priority segments such that you can plausibly win, and winning is worthwhile. This is what Phase 3's differentiation table has to prove. Winnability is often conditional on roadmap gaps — if the product can't win the #1 segment today, say so plainly: *"the segmentation is ahead of the product."*

**5. Priority-1 segment narrative**

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

Factor-set hygiene:
- **Drop parity factors.** A factor everyone scores 3 on can't swing a decision — fold it into a composite instead of giving it a row.
- **Single-segment factors belong in segmentation.** A factor only one segment perceives is a segmentation signal, not a differentiation axis — move it back to Phase 2.
- **Watch factor altitude.** Composite, customer-language factors (the 5±2 a customer would actually name) aid retention and readability but hide granular Bs. Carry "thin" annotations — the ghosts of the weak sub-factors — so the roadmap doesn't lose them.

**2. Score competitors**

Use competitor groups from Phase 1 (no re-mapping needed). Score each group per factor on a 1–3 scale:
- 1 = weak or absent
- 2 = adequate
- 3 = strong

Two scoring disciplines:
- **Score the segment's USE of the factor, not the competitor's general competence.** A telco's polished billing app is not a 3 on "self-serve line rotation" if the priority-1 segment can't actually do that job with it. Grade against the job, not the brand's overall capability.
- **Denominator bias.** Complaint logs and interview grievances measure what breaks, not how often it breaks. Don't grade a B off squeaky-wheel evidence without an incidence rate. Also check whose pain it is — pain concentrated in a non-priority segment should not down-score a factor for the priority segment.

**Benchmarks.** Out-of-market players (global leaders the customer can't actually buy) may appear as marked calibration columns — italicized, footnoted — but are never scored as real choices. Use them to (a) calibrate what a 3 looks like, (b) locate global whitespace, (c) import cautionary operational lessons.

**3. Assign B/T/D for the product**

For each factor, assign one of:
- **B** (Below threshold) — product does not meet the minimum bar this segment expects. Action: fix or reconsider segment fit.
- **T** (Threshold) — product meets the bar but does not stand out. Action: maintain, don't over-invest.
- **D** (Differentiation) — product is genuinely ahead in a way that matters to this segment. Action: protect, deepen, amplify.

**Grade-inflation guard.** Any score negotiated upward during iteration needs an operational B-test: *"would a priority-1 customer reject the product on this factor alone?"* Answer it from segment-cut churn reasons and funnel completion — not from debate in the room. Record the test result next to the table so the score is auditable.

**4. Build the table**

| Factor | [Group 1] | [Group 2] | *[Benchmark]* | [Product] |
|---|---|---|---|---|
| Factor A | 1–3 | 1–3 | *1–3* | B/T/D |
| Factor B | 1–3 | 1–3 | *1–3* | B/T/D |

Benchmark columns, if any, are italicized/footnoted as calibration — not choices the customer can make.

**5. Stress-test D claims**

For each D, ask: is this a structural moat or a temporary head start?
- Structural moats: data advantages, network effects, regulatory position, brand-locked rivals (Phase 1), deep segment trust built over time
- Temporary head starts: features that competitors can copy in 6–12 months

Flag temporary head starts — they are not real differentiation without a plan to widen the gap.

**6. Read the shape of the table**

Before writing the narrative, read the pattern of the product's column:
- **All-T (no Bs, no Ds)** — the profile of a competent #2: nothing losing, nothing winning. The strategy then lives entirely in the T→D conversions. Name them and their gating decisions; don't let an all-T table masquerade as a strategy.
- **B on a key factor** — a blocker; fix before the strategy is viable.
- **D on a factor the priority-1 segment doesn't care about** — meaningless; ignore it.

**7. Strategy narrative**

Write 2–3 sentences summarizing:
- Where the Ds land (the actual strategic bets)
- What Bs are blockers that need resolving before the strategy is viable
- Roadmap implication: Bs on key factors = fix first; Ts = maintain; Ds = build depth; named T→D conversions = the growth path

---

## Guard Rails

- **No vanity positioning.** Axes and factors must reflect user decision criteria, not product strengths. A product alone in a cell is an error until proven otherwise.
- **No cherry-picked competitors.** Always include the strongest archetype, even if unflattering.
- **Verify at the primary source.** Competitor claims come from the competitor, not from the client's SEO.
- **Attributes become axes only on evidence** of divergent LTV/churn — never on intuition.
- **No disconnected phases.** Competitor groups from Phase 1 feed Phase 3. Segment criteria from Phase 2 feed Phase 3 factors. If the phases are internally inconsistent, flag it before proceeding.
- **D without durability is misleading.** A D that competitors can replicate in a year is a roadmap item, not a strategic position.
- **Segment first, differentiate second.** A D on a factor the priority-1 segment doesn't care about is meaningless.

---

## Output Format

Deliver each phase sequentially. Do not combine phases into a single artifact — they answer different questions and may have different audiences.

After all three phases, offer a one-paragraph synthesis: how the positioning vision, the target segment, and the differentiation table connect into a coherent strategy.

The PSD output is the **engine** of a strategy doc, not the doc itself. Offer to assemble it into a Rumelt-kernel structure:

1. **Diagnosis** — the situation stated with the unflattering metrics, not the flattering ones
2. **Vision** — where this goes if it works
3. **Priorities and explicit non-priorities** — what we are and are not doing
4. **Evidence** — including willingness-to-pay
5. **Differentiation** — the Phase 3 table
6. **Game plan** — the coherent set of actions
7. **30-day actions** — what happens now

Two things on every deliverable:

- **A "what would make this wrong" section.** List the assumptions that, if false, break the analysis — and lead with the single cheapest data pull that gates the most phases (e.g. the end-of-term decision mix). If the client funds only one query, it should be that one.
- **Framing for the room.** Before the strategy is ratified, offer the same content two ways: an *analysis* framing (hypotheses + open questions) or a *strategy* framing (decisions + actions). Same substance, different political weight — let the user pick based on where the decision actually stands.

---

## Gotchas — quick self-audit

Each item is explained where it fires, in the phase above. This is the scan pass before shipping: any line that trips means go back and fix.

**Positioning**
- Product lands alone in a cell → error until proven otherwise (binary / compound / unverifiable-split axis)
- All players on one diagonal → correlated axes; collapse or swap
- One brand across multiple cells → pick a home cell, rest are arrows
- Empty quadrant, no strong rival → axes reverse-engineered or competitor missing
- Competitor claim sourced from client SEO → re-verify at primary source

**Segmentation**
- "Try-first" / undecided given a cell → funnel stage, not a segment
- Capacity confused with disposition, or "rich vs poor" → independent; disposition is within-cell
- Axis promoted on intuition → require divergent LTV/churn first
- Two cells tied on rank → force the order, name the reason
- X-cell with no reason → is it "can't afford" (risk) or "can't win" (marketing)?
- Internal-state axis with no signup signal → not findable yet; add intent question + telemetry

**Differentiation**
- Scored competitor competence, not the segment's use → regrade against the job
- B graded off complaint logs → need an incidence rate, and check whose segment
- Score drifted up in the room → run the operational B-test, record it
- All-T column read as a strategy → competent #2; the strategy is the T→D conversions
- D a rival can copy in 6–12 months → roadmap item, not a moat (brand-locked gaps are more durable)

**Chain integrity**
- Phase 3 factors not from the Phase 2 #1 segment, or groups not the Phase 1 archetypes → phases don't chain
- No priority-1 narrative → the matrix has no anchor
- Jumped to differentiation before the segment is locked → reorder
