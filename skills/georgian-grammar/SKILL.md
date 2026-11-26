---
name: georgian-grammar
description: Rule-based grammar, spelling, punctuation and style for Georgian (ქართული). Use whenever you write, edit, proofread, translate into or out of, or explain Georgian text — articles, emails, UI strings, product copy, chat replies — or whenever the user writes in Georgian. Covers case marking by tense series (nominative/ergative/dative subjects), verb person and number agreement, inversion verbs, the eleven screeves, preverbs, version and causatives, noun declension with syncope and truncation, adjectives, numerals, dates and time, pronouns, postpositions, negation (არ/ვერ/ნუ), reported-speech particles (-ო/-მეთქი/-თქო), punctuation, polite register, calques, and the meaning errors AI systems make when translating Georgian.
license: CC-BY-4.0
---

# Georgian grammar

Use this skill to produce and check standard modern literary Georgian, written in Mkhedruli.

- The rules are in `references/`. Each rule has an ID (e.g. `VSER-02`) and a tag:
  - **[norm]**: a grammar or spelling rule;
  - **[convention]**: established practice;
  - **[style]**: a preference.
- Only **[norm]** violations are errors. **[convention]** and **[style]** items are suggestions.

## Core checks: run on every Georgian output

These cover most of the errors in machine-written Georgian. Fix any violation before you answer.

1. **Subject and object case follow the verb's series** (VSER-02).
   - Series I (present, future): `ბავშვი წერილს წერს`.
   - Series II (aorist, optative): `ბავშვმა წერილი დაწერა`.
   - Series III (perfect): `ბავშვს წერილი დაუწერია`.
   - Verbs of motion or change keep a nominative subject: `ბავშვი მოვიდა`.
   - Test: an aorist 3rd plural in `-ეს` means an ergative subject; one in `-ნენ` means a nominative subject.
2. **Inversion verbs take a dative experiencer:** `ნინოს უყვარს მუსიკა`, `მიყვარხარ`, `ძმა მყავს`, `მანქანა მაქვს` (VPER-05, VPER-08).
3. **After a number or quantifier, the noun and verb are singular:** `სამი სტუდენტი მოვიდა` (NUM-02, NUM-03).
4. **Plural things take a singular verb:** `ამბები მოხდა`, `ოთახები ნათელია` (AGR-01).
5. **A preposed adjective declines only partly:** `დიდ სახლს`, `დიდი სახლის`, `დიდმა სახლმა` (ADJ-02). **Possessives keep `-ს`:** `ჩემს მეგობარს` (PRON-03).
6. **Stems change in declension:** `სტუმრის`, `დედის`, `ფანჯრის` (CASE-04, CASE-05). Vowel-stem personal names don't truncate: `ნანას`, `გიორგიმ` (CASE-08).
7. **Postpositions require their case:** `დედისთვის`, `სახლში`, `ოთახიდან`, `მეგობრისგან`, `ჩემკენ` (POSTP-01, POSTP-02).
8. **Polite `თქვენ` takes plural verbs:** `თქვენ იცით`. Address with the vocative: `ბატონო გიორგი` (VPER-07, REG-02).
9. **Negation:**
   - `ვერ` = can't, `არ` = don't;
   - prohibition is `ნუ` + present/future, or `არ` + optative (`ნუ წახვალ`, `არ წახვიდე`). Never `ნუ` + aorist (NEG-01, VSER-04).
10. **Conjunctions and clauses:**
    - cause is `რადგან`, purpose is `რათა` + optative;
    - `რომელიც` takes its case from its own clause (CONJ-02, PRON-06).
11. **Spelling and punctuation:**
    - `ქართული`, `ინგლისური`; `მე-2`, `21-ე`, `XIX საუკუნე`; no Mtavruli capitals;
    - `„…“` quotes; a dash with spaces, never a hyphen;
    - a comma before `რომ`, none before a single `და` (SPELL-02, NUM-05, PUNCT-02/05/06).
12. **Natural style:**
    - a direct verb, not a light-verb calque (`დაეხმარა`, not `დახმარება აღმოუჩინა`);
    - active voice, not `მიერ` passives;
    - no translated articles, no English filler (STYLE-01/02, VOICE-02).

## Modes

### Write (generate Georgian)

1. Choose the register and the form of address (`შენ` / `თქვენ`) once, and keep them (REG-01).
2. Compose in Georgian sentence structure. Don't translate English word by word: articles, infinitives, "have", "for me" and passives all restructure (TRANS-09).
3. Check the text in two passes:
   - **grammar**: the core checks above, plus the relevant reference;
   - **spelling, punctuation and style**.
4. Output the text only. Don't attach a change log unless asked.

### Correct (proofread or edit)

1. Read the whole text first. Note its register, terminology and intent.
2. Make **minimal** edits:
   - fix every [norm] violation;
   - keep the author's meaning, voice and word choices;
   - don't rewrite correct sentences into your own style;
   - don't "fix" dialect or poetry that is clearly deliberate.
3. Output the corrected text. Then list the changes, one per line:
   `✗ original → ✓ correction — short reason (RULE-ID)`
   Put [style] or [convention] suggestions in a separate "Suggestions" list, or leave them out if the user asked only for corrections.
4. If the text is correct, say so. Never invent errors to look useful.
5. Symptom index for fast lookup: `references/15-common-errors.md`.

### Explain (grammar questions, multiple choice)

1. Name the layer: spelling, word form, syntax, punctuation, word choice or register.
2. Answer from the rule. Give the rule ID and one short example.
3. For multiple choice, check **every** option. Name the error in each rejected option before choosing.
4. If the answer depends on a dictionary fact the references don't settle (a specific word's spelling, plural or verb form), say so, and suggest checking the orthographic dictionary (ena.ge). Don't guess.

### Translate

Follow `references/14-translation-fidelity.md`. Keep every participant, direction, causation, degree of certainty, condition, evidentiality, and whose words are being reported. Don't add or drop information.

## Which reference to load

| Problem | File |
|---|---|
| Spelling, letters, joined/separate/hyphenated writing, loanwords | `references/01-spelling.md` |
| Noun cases, plural, stem changes, personal names, titles | `references/02-nouns-cases.md` |
| Adjectives, comparison, numbers, ordinals, dates, clock time | `references/03-adjectives-numerals.md` |
| Pronouns, possessives, მისი/თავისი, relatives, indefinites | `references/04-pronouns.md` |
| Verb person and number, inversion, "to be", "to have", polite თქვენ | `references/05-verb-person.md` |
| Tenses (screeves), case by series, imperative, aspect, irregular verbs | `references/06-verb-series.md` |
| Passive, version (for oneself or someone), causative, preverbs | `references/07-voice-version-preverbs.md` |
| Verbal nouns, participles, translating infinitives | `references/08-verbal-nouns.md` |
| Postpositions, adverbs, conjunctions, particles, negation | `references/09-function-words.md` |
| Word order, agreement, clauses, reported speech | `references/10-syntax.md` |
| Commas, colon vs dash, quotation marks, dialogue, spacing | `references/11-punctuation.md` |
| Register, politeness, etiquette, calques, natural style, UI copy | `references/12-register-style.md` |
| Foreign names, countries and nationalities, brands, abbreviations | `references/13-names-loanwords.md` |
| Translation and meaning preservation | `references/14-translation-fidelity.md` |
| Correction checklist by symptom | `references/15-common-errors.md` |

Load only the files you need. For a short reply the core checks are usually enough. For any text longer than a paragraph, also load `12-register-style.md`.

## When you are unsure

- Don't build a verb form, plural or spelling by analogy. Use a form you know is standard, or rephrase so the doubtful form isn't needed.
- If a doubt remains in an explanation, say so briefly and name the safer alternative.
- Prefer standard literary Georgian unless the user asks for colloquial, dialectal or archaic style.

## Sources

The rules are restated in our own words from:
- the ირბახი textbooks (K. Gabunia, *ზოგადი კურსი*; R. Zekalashvili, *მოკლე კურსი*; N. Davitashvili, *შემსწავლელის გრამატიკა I*);
- A. Arabuli, *ქართული მეტყველების კულტურა* (2008), via G. Zhgamadze's CC BY 4.0 skill;
- BTU, *Georgian Grammar for AI — Stage 1* (CC BY 4.0);
- L. Ildani's georgian-grammar-codex-skill (Apache-2.0).

Full credits: `NOTICE.md` in the repository.
