# CLAUDE.md

Obsidian vault for CFA Level 2 exam prep (~2,900 notes). No build system — work is creating and editing Markdown notes.

## Vault Structure

Ten subject folders under `Level 2/`: `01 - Ethical and Professional Standards`, `02 - Quantitative Methods`, `03 - Economics`, `04 - Financial Statement Analysis`, `05 - Corporate Issuers`, `06 - Equity Investments`, `07 - Fixed Income`, `08 - Derivatives`, `09 - Alternative Investments`, `10 - Portfolio Management`. Glossary terms in `CFA_Glossary/`. Each subject folder contains a `Generated Notes/` subfolder. New AI-generated concept notes go in the matching module subfolder: `Level 2/<subject>/Generated Notes/<NN Module Name>/`. If a note already exists on that topic, improve it instead of creating a duplicate.

**Search before creating.** Before writing a new note, check `CFA_Glossary/`, the relevant subject folder, and `Level 2/<subject>/Generated Notes/` for an existing note on the topic. If one exists, improve it instead of duplicating. If no note exists, place the new note in the correct module subfolder under `Generated Notes/`, creating the subfolder if needed.

## Note Conventions

Frontmatter on all notes: `title`, `subject`, `tags: [CFA-L2, ...]`, `aliases`. Use `[[wikilinks]]` for internal links, `$...$` / `$$...$$` for LaTeX, tables for comparisons. Use the `obsidian-markdown` skill when creating/editing notes.

## NotebookLM Integration

Always use the **subject-specific notebook** matching the topic being discussed. Fall back to the master only if the subject is ambiguous.

| Subject | Notebook ID |
|---|---|
| Ethics | `1b26ff8d-6963-47d3-b993-5dade748b8d4` |
| Quantitative Methods | `40f5b71b-6e49-48e7-b918-d0b3751bdbef` |
| Economics | `0c1985b5-96cb-4b76-8dc0-35f935ac07d2` |
| Financial Statement Analysis | `2f87343e-5567-45ce-9381-674c3d708d28` |
| Corporate Issuers | `d7255f4f-76de-4738-834a-a433fc822eec` |
| Equity Investments | `956ab539-d7cf-42b5-9f8b-87b0d4398270` |
| Fixed Income | `be7d4d59-3709-40f8-a6e4-b7bee67b95b7` |
| Derivatives | `4875b7c7-e2d6-4f27-bff0-1224a43fe4e8` |
| Alternative Investments | `22ab4925-3356-437e-b7d6-73d9b9338665` |
| Portfolio Management | `222dfca2-0a96-4873-824b-90e968b866e4` |
| **Master (fallback)** | `8d87dd1c-fb0f-4a04-8236-0791363e690e` |

- **Usage:** `notebooklm use <ID>` then `notebooklm ask "<question>"`
- Save full explanations to `Level 2/<subject>/Generated Notes/<NN Module Name>/` as `.md` files following note conventions above. Keep the chat response short: changed-file link, key takeaway, and any caveat.

## Explanation Preferences

- Fresh learner — build from the ground up, assume nothing
- Lead with a real-world analogy
- When you are explaining, use notebookLM as primary source — follow `.claude/explain-prompt.md` for the exact workflow and query template
- Flowing narrative prose, not bullet outlines
- Show full formula derivation + final form
- Always include a worked numerical example
- Explain the *why*, not just the *what*. When you explain something, imagine i am there questioning everything you say with "why"
- Tables for comparisons (IFRS vs GAAP, model variants)
- Comprehensive length — everything in one note
- Conversational tone — expert mentor
- Heavy use of tables, ASCII diagrams, visual layouts
- Wikilink every concept to related notes across volumes
- Practice questions stay in `Practice Questions/` subfolders — never embed in concept notes
- Do not include a "how I built this," "process," or source/provenance section in ordinary explanation notes or chat responses unless explicitly requested. Use sources internally, but keep the final artifact focused on learning the concept.
- Do not leave details out, it is very important that i learn everything so i am exam ready
- Refer to the 2026-l2-topics-combined-4 to make sure your explanations are sufficient

### Explanation Ladder

Walk every concept down this ladder. Do not stop at a rule or formula.

```
Rule → why the rule exists → mechanism → assumptions → failure mode → exam implication
```

### What to Explain (per concept)

For every CFA concept introduced, cover all of these — not just the formula:

- What it means in plain English
- Why it exists (the problem it solves)
- What assumption makes it true
- What would break if that assumption failed
- How CFA might test it
- Which wrong answer is most tempting and why
- How to remember it under exam pressure

### Preferred Section Order

When building a concept note, follow this order:

1. Real-world analogy
2. Plain-English definition
3. CFA / formula version (with full derivation)
4. Mechanism — why the formula works
5. Worked numerical example
6. Comparison table (if relevant — IFRS vs GAAP, model variants, etc.)
7. Exam traps
8. Memory hook
9. Related wikilinks

## Practice Question Workflow

When the user shares the text of a CFA practice question, follow `.claude/practice-question-prompt.md`.

## Real-World Applications Workflow

After producing a concept note, ground the LOS in a practitioner artifact by running a matching skill on a real company/deal and saving the output to a `Real-World Applications/` subfolder inside the same module folder.

**Save path:** `Level 2/<subject>/Generated Notes/<NN Module Name>/Real-World Applications/<Ticker or Deal> - <Artifact>.md`

**Top of file:** add a `> [!note] Connection to LOS` callout that names the LOS verbs (describe/calculate/interpret/compare…) the artifact reinforces and wikilinks back to the concept note(s).

**Skill → subject mapping:**

| Subject | Skill / Agent |
|---|---|
| FSA | `financial-analysis:3-statement-model`, `:comps`, `:debug-model`, `agents:gl-reconciler` |
| Equity Investments | `equity-research:initiate`, `:thesis`, `:earnings`, `:model-update`, `financial-analysis:dcf` |
| Corporate Issuers | `investment-banking:merger-model`, `:cim`, `:one-pager`, `financial-analysis:lbo` |
| Portfolio Management | `wealth-management:rebalance`, `:tlh`, `:client-review`, `:financial-plan`, `:proposal`, `agents:valuation-reviewer`, `agents:statement-auditor` |
| Alternative Investments | `private-equity:returns`, `:unit-economics`, `:ic-memo`, `:dd-checklist` |
| Fixed Income / Derivatives | `agents:model-builder` |
| Economics | `agents:market-researcher`, `equity-research:sector` |
| Ethics | `agents:kyc-screener` |

**Rules:**
- The Real-World Application note is supplementary — keep concept notes pure (no model output dumped in).
- Apply the same note conventions (frontmatter, wikilinks, tables, no provenance section).
- One artifact per concept is enough; don't run every matching skill.
- If the skill needs a ticker/deal and one isn't specified, ask the user before running it.
