---
name: friction-log
description: Run a friction log on a live product — use it as a real user with a specific job, capture every moment of friction with screenshots, and publish a structured log the owning team can act on. Use whenever someone wants to audit, review, tear down or pressure-test a product's UX or funnel: "run a friction log", "audit our checkout", "walk the signup as a user", "why are people dropping off here", "review the mobile flow", "do a teardown of <competitor>". Also use when someone already has screenshots of a flow and wants them turned into a findings doc. Covers the method (job story with a trigger, arriving through the real channel, separating deliberate design choices from actual defects), the output format, and the operational traps in driving a browser at mobile width and publishing to Notion.
---

# Friction log

A detailed record of everything that caused friction while using a product for a real job. Method credit: [sbensu](https://blog.sbensu.com/posts/friction-logs/).

It is deliberately dull to anyone except the team that owns the product. That's the point — it trades breadth for concrete, reproducible moments. Resist turning it into a strategy memo.

## The thing that decides whether this is any good

**Separate deliberate product decisions from defects.** This is where friction logs lose credibility, usually in the first five minutes of the review.

A team will happily fix a wrong number. They will not accept being told a considered decision is a bug — and once they've rejected one finding on those grounds, they discount the rest of the document.

The test:

> A **defect** is where the product says something untrue, contradicts itself, or breaks.
> A **choice you'd have made differently** is not a defect. At most it's a risk — name it, and name the tradeoff the team was making.

Patterns that look like bugs to a first-time auditor and are almost always intentional:

- An account wall placed *after* the user has configured something — deferring signup until they're invested is standard and correct
- Terms and conditions surfacing at the final click
- No total or lifetime cost shown on a subscription — no subscription business publishes this
- Upsells and cross-sells inside the flow
- Scarcity and urgency messaging
- A default option that happens to suit the business

Before filing any of these, ask: *what would the team say if I told them?* If the answer is "yes, on purpose, and here's why" — either drop it or rewrite it as the narrower thing that survives. Something usually does, and it's sharper than the original. A hidden term selector isn't a bug; a rationale line reading *"Step up savings, stay flexible"* on the term that saves least and locks in longest is a copy defect, it's cheap to fix, and nobody will argue.

## 1. Set up

**Pick a job, not a persona.** A persona ("young professional, budget-conscious, wants a phone") is a demographic with a budget attached. No triggering event means no urgency, no alternatives, no definition of progress — and someone who isn't struggling with anything can't fail a product. You'll end up reaching for "is this good value" as the only test available, which is exactly the kind of finding a team overturns.

Write a job story:

> *When [situation with a trigger], I want to [motivation], so I can [outcome].*

Then fill in four things, because every finding hangs off them:

| | |
|---|---|
| **Trigger** | What just happened that started this? Phone broke, contract ended, new model launched, moving house. |
| **Competing alternatives** | What else solves this? Include the boring ones — do nothing, buy cheap locally, repair it. |
| **Progress looks like** | How does this person know they've won? |
| **Deal-breakers** | Write them down *before* starting. Otherwise you'll quietly relax them when you hit a blocker and miss that the product failed. |

The job determines which findings matter. Someone replacing a phone that died this morning cares about delivery date and approval odds, and does no arithmetic. Someone upgrading a working phone cares about total cost and trade-in value. Run the wrong job and you'll produce findings that evaporate under scrutiny. If the product serves several jobs, pick one, say which, and note the others — a single flow serving two opposed jobs is often the real finding.

**Do minimal research.** Know who it's for and what it does. Not more. You want a beginner's mind.

**Confirm the team wants it.** This takes hours and it's uncomfortable to receive.

## 2. Arrive the way users actually arrive

Check the real channel mix first — analytics, GA, whatever exists. Don't assume.

This matters more than it sounds. If 43% of sessions come from TikTok, entering via Google and the homepage tests a journey almost nobody takes, and misses the friction specific to the real one: in-app browsers, deep links landing on a product page with no browse context, and ad promises the page doesn't honour.

Two checks worth making on any paid-social-heavy product:

- **In-app browsers are webviews.** Google blocks OAuth inside embedded webviews (`disallowed_useragent`), so a "Sign in with Google" button can be completely broken for the largest traffic source while working perfectly for anyone testing in Safari or Chrome.
- **What does the ad promise?** Screenshot the creative. A gap between the promise and the landing experience is a real finding, and it's invisible if you start from the homepage.

## 3. Walk the flow

**Screenshot everything.** Every screen, every state, every moment something felt off. Screenshots are the substance; prose is connective tissue.

**Nothing is too small — but always name the consequence.** "The banner is too big" is a preference and will be ignored. "The banner pushes the first product card below the fold, so a shopper arriving from search sees an ad before a price" is something a team can act on or argue with. If you can't say what it cost you, you haven't found anything yet.

**Notice what you feel.** Confusion, irritation, distrust, delight. We're trained to suppress this at work and it's the highest-signal data in the exercise. Mark intensity inline as you go: 🔴 defect or blocker, 🟡 friction, 🟢 delight.

**Record delight too.** It tells the team what to protect, and a log that's only complaints reads as an attack.

**Note where you'd have given up.** Say so explicitly. Each one is the product losing the game, whether or not you personally knew a workaround. Then use your knowledge to continue.

**Verify numbers independently.** Anything arithmetic — tax lines, totals, discounts, term pricing — recompute yourself. A wrong number is the most valuable and least arguable finding available, and also the most embarrassing to get wrong.

**Track the environment per finding.** If any of the walkthrough runs on staging, a sandbox, or a test account, then seed data — placeholder images, dummy names and addresses, nonsense pricing, broken test SKUs — is not a finding. Exclude it explicitly and say you have. Readers who spot one obviously-fake item will discount the whole document. Label real findings with where they were seen, so the team knows what to re-check on production.

## 4. Write it up

Structure, in order. Template and worked example in `references/output-format.md`.

1. **Header** — date, environments, viewport, who ran it
2. **Job story** — the block from step 1
3. **Exclusions** — one line on what's seed data and out of scope
4. **Summary** — one-sentence verdict, then findings as tables
5. **The log** — screen by screen, chronological, screenshots inline, short bullets marked 🔴🟡🟢
6. **Needs confirming** — what you couldn't determine
7. **Still open** — what a second pass should cover

Use tables in the summary, not prose. Severity buckets written as paragraphs turn into a wall of complaints that nobody finishes:

| | Finding | § | Seen on |
|---|---|---|---|
| 🔴 | **Short bold claim.** One sentence of evidence. | 4 | Production |

**Rank the top three explicitly.** You'll find more than anyone can act on, and an unranked list of thirty gets shelved.

**Say whether the product did the job.** One deal-breaker is enough. Most of the flow working is not a defence — state plainly whether this person would have finished.

**A comic can carry the job story** where prose won't. If the log needs a protagonist the team will remember, the `flow-comic` skill turns the job story into a storyboard prompt. Draw the happy path for a persona introduction; keep contested findings in the tables, where they can be argued with. A comic makes everything look authoritative, so don't illustrate anything you haven't confirmed.

## 5. Send it

Four things to say on handover, because they change how it lands:

- You don't expect everything to be fixed
- Many are tradeoffs with no free improvement available
- It's about the product, not the people who built it
- You're around to reproduce anything

## Operational gotchas

Driving a browser at mobile width and publishing to Notion both have traps that will silently waste an hour. **Read `references/gotchas.md` before starting.**

The two that cost the most:

- **A true phone viewport usually needs the human.** Chrome won't resize below roughly 670px, `resize_window` silently no-ops on a maximised window, and DevTools device mode gives the right viewport but kills mouse input. Settle the viewport before anything else and ask early rather than burning turns discovering this.
- **Notion edits can fail silently.** When one API call carries several edits, non-matching ones are dropped while the call still reports success. Verify against the rendered page after every edit.

## Reference files

- `references/output-format.md` — document template and worked example
- `references/gotchas.md` — browser, viewport and Notion API traps
