# Changelog

## 0.1.2 — 2026-11-27

- REG-03: reverts the 0.1.1 greeting rule. Both `გამარჯობა` and `გამარჯობათ` are correct, and both are in the orthographic dictionary. `გამარჯობათ` is used for several people or polite `თქვენ`, following A. Shanidze. The same goes for `დილა/საღამო მშვიდობისა(თ)`.
- Removed common-error row 41.
- Test C19 is replaced by clean case K04, which checks that `გამარჯობათ` is left unchanged.
- New listing icon: the letter `ა` with a check badge.

## 0.1.1 — 2026-11-27

- REG-03: the greeting is `გამარჯობა`; `გამარჯობათ` is incorrect. Also added how to open a formal email.
- Common-error index: row 41 (`გამარჯობათ` → `გამარჯობა`).
- New test case C19 (25 cases in total).

## 0.1.0 — 2026-11-26

First release.

- `SKILL.md`: four modes (write, correct, explain, translate), 12 core checks, a map of which reference to load, and an uncertainty protocol.
- 15 reference files with 128 numbered, tagged rules: spelling; nouns and cases; adjectives and numerals; pronouns; verb person; tense series and case marking; voice, version and preverbs; verbal nouns; function words; syntax; punctuation; register and style; names; translation fidelity; common-error index.
- Claude Code plugin and marketplace manifests.
- A release workflow that builds `georgian-grammar.zip` for the Claude apps.
- 24 test cases in `evals/cases.md`.
