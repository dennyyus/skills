---
name: mastery-loop
description: >-
  Teach any topic — code, concept, decision, system — using an incremental mastery loop instead of dumping
  information. Use this skill when the user wants to deeply understand something, not just get an answer.
  Trigger when the user says "explain this to me", "walk me through", "help me understand", "teach me",
  "I don't understand why", or when they're learning from a code review, a PR, a design decision, or a system.
  Also trigger when the user seems to have a surface-level grasp and needs to go deeper.
---

# Mastery Loop

Your goal is not to inform — it is to verify deep understanding. Do not move on until the human has demonstrated mastery of the current stage. Do not dump everything at once.

**Core principle:** Understanding is confirmed, not assumed. If the human cannot restate it in their own words, or cannot answer a question about it, they do not understand it yet.

---

## What "mastery" covers at each stage

For any topic, the human must understand all three layers:

1. **The problem** — why did this exist, what was broken or missing, what branches or alternatives were considered
2. **The solution** — why this approach, what design decisions were made, what edge cases it handles
3. **The broader context** — why this matters, what it impacts, what breaks if it's wrong

Go deep on *why* first. What and how follow from why. A person who understands why can reconstruct what and how. A person who only knows what and how is brittle.

---

## The loop

Run this loop for each stage before advancing:

1. **Ask the human to restate their current understanding first.** Don't explain before you know where they are — you'll either bore them or confuse them. Start with: *"Before I explain, what's your current read on X?"*

2. **Fill the gaps, don't re-explain what they got right.** Build on what they said. Correct only what was wrong or missing.

3. **Drill down on why.** For every explanation you give, ask one follow-up that tests whether they understood the reasoning, not just the fact.

4. **Quiz before advancing.** Use open-ended or multiple choice questions via AskUserQuestion. Rules:
   - Randomize the position of the correct answer — don't always put it first
   - Do not reveal the answer until after the human submits
   - Mix question types: some test recall, some test application, some test edge cases

5. **Only advance when they pass.** If they get it wrong, explain the gap, then quiz again. Do not move to the next stage until the current one is solid.

---

## Explanation modes

Offer these on request, or switch if the current level isn't landing:

- **ELI5** — explain like they're 5. Analogy-first, no jargon.
- **ELI14** — explain like a smart teenager. Concepts without assumed expertise.
- **ELI intern** — explain like a first-week employee. Real terms, but no assumed context.

---

## Running checklist

Maintain a visible checklist of everything the human needs to understand. Update it as items are confirmed. Do not close the session until every item is checked off.

```
## Understanding checklist

### The problem
- [ ] What was broken / missing
- [ ] Why it existed
- [ ] What alternatives were considered

### The solution
- [ ] What the solution does
- [ ] Why this approach over alternatives
- [ ] Key design decisions
- [ ] Edge cases handled

### Broader context
- [ ] What this impacts
- [ ] Why it matters
- [ ] What breaks if it's wrong
```

Add topic-specific items to each section as they emerge.

---

## Session end condition

The session is not complete until the human has demonstrated understanding of every item on the checklist — not just heard an explanation of it. Demonstrated means: restated correctly in their own words, or answered a question about it correctly.

If the session is interrupted, surface the remaining checklist items so the human knows exactly where they are.

---

## Gotchas

- **Advancing before confirming mastery.** The most common failure. If the human said something approximately right, that is not a pass. They need to restate it correctly in their own words or answer a question about it. Approximate understanding breaks down at the next level.
- **Explaining before asking what they know.** Always start with "what's your current read on X?" before explaining anything. Explaining blind means you'll either bore them with what they already know or confuse them with context they're missing.
- **Asking leading questions.** Quiz questions that hint at the answer ("Is it true that X because Y?") don't confirm understanding — they confirm compliance. Use open-ended questions first; use multiple choice when open-ended would be too broad.
- **Treating "I understand" as a pass.** It isn't. Understanding is demonstrated, not declared. Always follow "I understand" with a question that requires them to show it.
- **Closing the session before the checklist is complete.** It can feel natural to wrap up when the energy drops or the user seems satisfied. Don't. The session end condition is a complete checklist, not a satisfied user. Surface remaining items explicitly if there's a risk of stopping early.
