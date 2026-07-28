# Output format

The document has two halves: a **summary** anyone can read in two minutes, and a **screen-by-screen log** only the owning team will read. Both matter — the summary gets it triaged, the log gets it reproduced.

## Template

```markdown
# Friction log — [surface] — [product]

[date] · [environments used] · [viewport] · Screenshots: [name]

**Job story.** *When [trigger], I want to [motivation], so I can [outcome].*

| | |
|---|---|
| **Trigger** | … |
| **Competing alternatives** | … |
| **Progress looks like** | … |
| **Deal-breakers** | … |

> **Environments:** [which legs ran where]. [What is seed data and therefore excluded.]

---

## Summary

**[One-sentence verdict.]** [Two or three sentences on what that means.]

### Bugs — pricing, logic, copy

| | Finding | § | Seen on |
|---|---|---|---|
| 🔴 | **Bold claim.** One sentence of evidence. | 4 | Production |
| 🟡 | … | 6 | Staging |

### UI and flow

| | Finding | § | Seen on |
|---|---|---|---|
| 🔴 | … | 2 | Production |

### Delight

- [What's working, and why it's worth protecting.]

*Below is the log of going through the flow screen by screen. Only interesting to the team that owns this.*

---

## 0 · [Entry point — the channel, not the homepage]

[screenshots, in columns]

[Two sentences of context.]

🟢 **G1** — [what worked, and why]
🟡 **Y1** — [friction, and what it cost]
🔴 **R1** — [defect, with evidence]

## 1 · [Screen name]

…

---

## Needs confirming

[Things you couldn't determine, phrased as checks someone can run.]

## Still open

[What a second pass should cover, and why.]
```

## Notes on the pieces

**Section numbers double as finding IDs.** `R5` in the summary points at section 5. Keep IDs unique across the whole document — duplicates make findings unciteable in tickets, and duplicates happen easily when sections are added later.

**A change of screen is a new section.** Same rule as panels in a storyboard. It keeps the log chronological and makes it obvious where in the funnel each problem sits.

**Screenshots in columns, two or three across.** Stacked full-width screenshots make the document enormous and hide the sequence.

**"Seen on" is doing real work.** When part of the run happens on staging, this column is what stops a reader dismissing the whole document as test-environment noise. It also doubles as the re-check list: everything marked staging needs ten minutes on production before anyone files a ticket.

## Worked examples

Two findings, showing the difference between an observation and a finding.

**Weak — an observation with no consequence:**

> 🟡 Y3 — Banner is too big.

A preference. Nobody can act on it and nobody can argue with it.

**Strong — same observation, with the cost named:**

> 🟡 **Y3** — The promo banner dominates the first screen, pushing the first product card below the fold. On a listing page reached from search, the first thing a shopper sees should be a product and a price, not an ad.

**Strong — a defect, with the arithmetic done:**

> 🔴 **R5** — **"Incl. GST (9%)" uses the tax-exclusive formula.** It computes `gross × 0.09` where an inclusive figure is `gross × 9/109`. On S$105.00 it prints S$9.45 instead of S$8.67. Seen at four different totals, so it's systematic rather than rounding. The customer isn't overcharged, but the tax breakdown on their receipt is wrong.

Note what makes the last one unarguable: the formula, the numbers, the fact it reproduced, and an explicit statement of what *isn't* wrong. That last clause matters — it shows you understood the system rather than pattern-matching on a number that looked odd.

**A finding that survived being challenged**, after the original was overturned as a deliberate choice:

> 🟡 **R3** — **The rationale line on the 18-month term claims two things it doesn't deliver.** *"Step up savings, stay flexible"* sits on the option that saves least in absolute terms and locks in longest. Preselecting the lowest monthly is defensible — for someone who can't put S$1,899 down, S$103/mo is the right answer, and no subscription business publishes lifetime cost. The copy is the part that doesn't survive scrutiny.

The original version of this said the pricing was the problem and recommended showing total-over-term. That was rejected, correctly, as advice no commercial team would take. What remained — the label being untrue — is smaller, cheaper, and got accepted.
