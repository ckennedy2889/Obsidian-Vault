# Practice Question Workflow

When the user shares a screenshot of a CFA Level 2 practice question, follow this workflow exactly.

## 1. Classify the Question

Determine which CFA subject the question belongs to (one of the ten curriculum folders):

- `01 - Ethical and Professional Standards`
- `02 - Quantitative Methods`
- `03 - Economics`
- `04 - Financial Statement Analysis`
- `05 - Corporate Issuers`
- `06 - Equity Investments`
- `07 - Fixed Income`
- `08 - Derivatives`
- `09 - Alternative Investments`
- `10 - Portfolio Management`

## 2. Save the Screenshot

Copy the user's screenshot into:

```
Level 2/<subject>/Generated Notes/Practice Questions/attachments/
```

Use a descriptive kebab-case filename in the format:

```
YYYY-MM-DD-<topic-slug>.png
```

Example: `2026-04-11-h-model-wilson-company.png`

If the `Practice Questions/` or `attachments/` subfolders don't exist yet, create them first.

## 3. Create the Markdown Note

Save the explanation as a new markdown file at:

```
Level 2/<subject>/Generated Notes/Practice Questions/<descriptive-title>.md
```

Use this exact structure:

````markdown
---
title: "Practice Q - <short descriptive title>"
subject: "<CFA subject name>"
tags: [CFA-L2, practice-question, <topic-tag>]
source: "<exam/book/seminar source if visible, otherwise 'unknown'>"
date: YYYY-MM-DD
---

# <Descriptive Title>

## Question

![[attachments/<filename>]]

<Transcribe the full question stem and all answer choices below the embedded image, in case the image ever fails to render.>

---

## Correct Answer: <Letter — Value>

Explain the WHY in full narrative detail, following every CLAUDE.md preference (flowing prose, real-world analogy if useful, heavy wikilinks, tangible computation):

- **What is this testing?** — Name the concept being tested and why the exam writers chose it.
- **The correct approach** — Lay out the formula / framework / decision rule. Show the full form of any formula.
- **Step-by-step computation** — Walk through every intermediate value. Never skip arithmetic. Use LaTeX blocks for calculations.
- **The intuition** — Explain *why* the formula works, not just how to plug in numbers. Connect to the underlying economics.
- **Wikilinks everywhere** — Every CFA-specific term should link to the relevant `Level 2/<subject>/Generated Notes/` note or glossary entry (e.g., `[[H-Model]]`, `[[Gordon Growth Model]]`, `[[Required Rate of Return]]`).

---

## The Trap — Most Tempting Wrong Answer

Identify which distractor is the most seductive and explain:

- **Why it looks right** at first glance — what partial reasoning leads there?
- **The specific mistake** — typical errors: using $D_0$ instead of $D_1$, forgetting to halve the transition period in H-Model, mixing leading and trailing P/E, using cost of debt instead of WACC, etc.
- **How to avoid it** — a concrete check or habit that catches this error on exam day.

---

## Key Takeaway

A 1–2 sentence memory hook that locks in the insight. Use a callout:

> [!tip] Memory Hook
> <Short, punchy rule the user can recall in 5 seconds.>

---

## Related Concepts

- [[Concept 1]] — primary formula/framework tested
- [[Concept 2]] — secondary link
- [[Concept 3]] — related glossary term
````

## 4. Rules and Conventions

- Follow all existing `CLAUDE.md` explanation preferences: detailed, fresh-learner perspective, narrative style (not bullet outlines), real-world analogies, tangible computation, heavy wikilinks.
- **Never embed practice questions inside the main concept notes** — those live only in `Practice Questions/` subfolders.
- If the screenshot shows the answer being revealed (e.g., from a solutions manual), still explain the reasoning fresh as if solving from scratch.
- If multiple questions appear in one screenshot, create **one note per question**.
- Always check for existing `Practice Questions/` and `attachments/` subfolders first; create them if missing.
- Always use the "Correct + most tempting wrong" approach: explain the correct answer in full, then identify and debunk the single most common distractor.
- Link heavily to existing `Level 2/<subject>/Generated Notes/` and `CFA_Glossary/` entries via wikilinks.
