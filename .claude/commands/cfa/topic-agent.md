Run CK's CFA Level II topic-note agent.

First read and follow `.claude/glossary-note-agent.md`, `CLAUDE.md`, and `AGENTS.md`.

Use this command to find thin or missing generated concept notes from `CFA_Glossary/` and the Level II topic map, then create or improve them as if CK had asked, "Explain this concept."

User arguments, if provided:

```text
$ARGUMENTS
```

Interpret the arguments as the scope:

- If CK gives a number, process exactly that many high-priority terms.
- If CK gives a subject, module, topic, or term, restrict the search to that scope.
- If CK gives both, apply both constraints.
- If CK gives no argument, process exactly one high-priority term.

Required workflow for each term:

1. Work serially, one term at a time.
2. Search the vault first to avoid duplicates.
3. Use the subject-specific NotebookLM notebook as the CFA source foundation.
4. Cross-check `2026-l2-topics-combined-4.md`, local subject notes, existing generated notes, and glossary entries.
5. Use the project MCP data connections when the concept reasonably allows real-world data:
   - `financial-datasets`
   - `edgar-tools`
   - `alphavantage`
   - `macro-data`
6. Choose one consistent company, security, client case, deal, or market event for the concept, and carry it through the intuition, formulas, worked example, traps, and any Real-World Application note.
7. Create or improve the generated note in the correct `Level 2/<subject>/Generated Notes/<NN Module Name>/` folder.
8. Validate YAML, folder placement, formulas, wikilinks, arithmetic, data assumptions, and explanation depth.
9. Commit only the files changed for this command. Do not include unrelated user changes.
10. Stop after the requested scope is complete and report the changed files plus the commit hash.

Keep the chat response concise. Do not paste the full note in chat unless CK explicitly asks.
