# Explain Workflow

When the user asks you to explain a CFA concept, follow this workflow exactly.

## 1. Pick the Subject Notebook

Map the concept to one of the ten subject notebooks from the table in CLAUDE.md. Use the subject-specific ID. Only fall back to the master notebook if the subject is genuinely ambiguous.

## 2. Query NotebookLM

Run:

```
notebooklm use <subject-notebook-id>
notebooklm ask "<prompt>"
```

Use this prompt template — fill in `<CONCEPT>` and `<LOS>`:

---

**NotebookLM query template:**

```
Give me a thorough, exam-focused explanation of <CONCEPT> for CFA Level 2.

I need you to cover:
1. What this concept is and why it exists — the real economic or financial problem it solves
2. Every formula involved — show where each term comes from, not just the final expression
3. The assumptions the formula rests on, and what breaks when they fail
4. A fully worked numerical example with every intermediate step
5. How CFA Level 2 typically tests this concept — question types, traps, and the most tempting wrong answer
6. Anything a candidate needs to know to fully satisfy this LOS: <LOS verb + statement>

Be comprehensive. Do not summarise or skip steps. I will use your explanation as the foundation for a detailed study note.
```

---

## 3. Build the Note from NotebookLM's Output

Use NotebookLM's response as your primary source material. Do not pad or invent — stay faithful to what it says, but transform it fully per CLAUDE.md preferences:

- Rewrite into flowing narrative prose (no bullet outlines)
- Lead with a real-world analogy
- LaTeX for all formulas (`$...$` inline, `$$...$$` display)
- Show full formula derivation before the final form
- Include the worked numerical example with every step shown
- Add comparison tables where relevant (IFRS vs GAAP, model variants, etc.)
- Add ASCII diagrams or visual layouts where they aid understanding
- Wikilink every CFA-specific term to `Level 2/<subject>/Generated Notes/` or `CFA_Glossary/`
- Walk the explanation ladder: Rule → why → mechanism → assumptions → failure mode → exam implication
- Include an Exam Traps section
- End with a Memory Hook

## 4. Save the Note

Check `CFA_Glossary/`, the subject folder, and `Level 2/<subject>/Generated Notes/` first — if a note already exists, improve it instead of creating a duplicate.

Save to `Level 2/<subject>/Generated Notes/<Concept>.md` with standard frontmatter:

```yaml
---
title: "<Concept>"
subject: "<CFA subject>"
tags: [CFA-L2, <topic-tag>]
aliases: [<alternative names>]
---
```

## 5. Show the Explanation

Display the full explanation in your response, not just a link to the saved file.
