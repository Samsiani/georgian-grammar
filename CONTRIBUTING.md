# Contributing

This repository is a Georgian (ქართული) grammar skill. These notes are for people and AI agents who edit it.

## Using the rules

When you write, edit, translate or explain Georgian text, follow `skills/georgian-grammar/SKILL.md`. Load files from `skills/georgian-grammar/references/` as its reference map says.

## Editing this repository

- Every rule is a `## AREA-NN · Title [tag]` heading. The tag is `[norm]`, `[convention]` or `[style]`.
- Keep IDs unique and never renumber existing ones. Add new rules at the end of their area.
- Every cross-reference such as `(VSER-02)` must point to an existing heading. Check before committing:

  ```bash
  cd skills/georgian-grammar/references
  comm -23 <(grep -ohE '\b[A-Z]+-[0-9]+\b' *.md | sort -u) <(grep -ohE '^## [A-Z]+-[0-9]+' *.md | sed 's/## //' | sort -u)
  ```

  The output must be empty.
- Write rules in your own words, and add the source to the file's `Sources:` line. Never paste text from copyrighted books.
- Keep `SKILL.md` short (under 500 lines). Detail belongs in `references/`.
- If you change a rule's meaning, add a matching case to `evals/cases.md`.
