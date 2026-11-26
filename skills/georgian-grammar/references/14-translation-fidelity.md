# 14 · Translation fidelity: keep the meaning

Load this when translating into or out of Georgian, summarizing Georgian text, or checking a translation. A grammatically perfect sentence can still lose who did what, which direction, how certain, or whose words.

Sources: BTU, *Georgian Grammar for AI — Stage 1*, module 07 (error taxonomy), as adapted and corrected by GZ (`common-ai-errors.md`, `about-this-source.md`) · A §2.1.6 (causatives, preverbs, series III).

---

## TRANS-01 · Keep every participant [norm]

- **Don't drop** a stated subject, object, recipient or person made to act (causee).
- **Don't invent** one either:
  - ✗ adding `ვიღაცამ` (someone) or `რაღაც` (something) for a participant Georgian left unspoken;
  - ✗ guessing a specific person who isn't in the source.
- Georgian drops pronouns the verb already marks (SYN-02). When translating out of Georgian, recover them from the verb markers, not from a guess.

## TRANS-02 · Case is not role [norm]

- A **dative** noun is not always a recipient. It can be:
  - the **agent** in series III: `ბავშვს წერილი დაუწერია` = the child has written a letter;
  - the **experiencer** of an inversion verb: `ბავშვს უყვარს` = the child loves.
- In series III the **recipient** moves into a `-თვის` phrase: `დედისთვის მიუწერია` = has written to mother, not "for mother's sake".
- The first word of a sentence is not necessarily the subject. Read the case and the verb markers (SYN-01).

## TRANS-03 · Keep causatives [norm]

- `დააწერინა` = had or made someone write. Don't flatten it to `დაწერა`, and don't swap the causer and the person made to act (CAUS-01).
- Don't read a plain verb as a causative.

## TRANS-04 · Keep direction and completion [norm]

- `შემოვიდა` (came in, toward here) ≠ `შევიდა` (went in).
- `ჩამოვიდა` (arrived here, came down) ≠ `ჩავიდა` (went down there).
- A preverb that marks completion (`დაწერა`, finished writing) shouldn't become an ongoing action (`წერდა`), or the reverse.
- When translating *into* Georgian, choose the preverb from the speaker's viewpoint (PREV-01).

## TRANS-05 · Keep certainty, condition and obligation [norm]

| Source meaning | Keep it as | Don't turn it into |
|---|---|---|
| possible / probable (`შეიძლება`, `ალბათ`, `იქნებ`) | possibility | a fact |
| recommendation (`ჯობს`, `სასურველია`, `რეკომენდებულია, რომ…`) | advice | an obligation (`უნდა`, `აუცილებელია`, `სავალდებულოა`) |
| real condition (`თუ…`) or unreal condition (`რომ` + pluperfect) | that type of condition | a statement of fact |
| not witnessed (`თურმე`, evidential perfect `წასულა`) | "apparently", "it turns out" | a plainly witnessed past |

- Keep the order of events: a pluperfect (`წასულიყო`) happened before the other past event.
- When translating into Georgian, express the source's hedge or condition with the matching form (VSER-03). Don't add a hedge the source doesn't have.

## TRANS-06 · Keep whose words they are [norm]

- `მოვალო` = he/she said they would come. It is not "I'll come".
- `-მეთქი` marks the speaker's own words; `-თქო` marks a message to pass on (SYN-07).
- Don't drop these particles in translation, and add them when rendering reported speech into natural Georgian.

## TRANS-07 · Idioms: translate the meaning [norm]

- Translate the meaning, and keep the emotional or social effect:

| Idiom | Meaning |
|---|---|
| `თავი დაანება` | quit, stopped |
| `გული გაუტყდა` | was disappointed, heartbroken |
| `ხელი მოაწერა` | signed |
| `თვალი მოჰკრა` | caught a glimpse |

- Don't read a literal phrase as an idiom just because it could be one.
- When translating into Georgian, replace a foreign idiom with a natural Georgian expression or plain words. Never translate it word for word.

## TRANS-08 · Don't over- or under-expand [norm]

- One compact Georgian verb can carry several facts: person, object, direction, completion, causation, evidentiality. Render all of them, not just the root meaning.
- Don't add specifics, explanations or hedges that aren't in the source.
- If the source is genuinely ambiguous, keep the ambiguity or name the possible readings. Don't silently pick one.

## TRANS-09 · Restructure English into Georgian patterns [norm / style]

| English pattern | Georgian pattern | Rule |
|---|---|---|
| "I have a car / a brother" | `მანქანა მაქვს`, `ძმა მყავს` | VPER-08 |
| "I like / love / want" | dative experiencer: `მომწონს`, `მიყვარს`, `მინდა` | VPER-05 |
| "washed his hands", "put on her coat" | subjective version, no possessive: `ხელები დაიბანა`, `პალტო ჩაიცვა` | VERS-02 |
| "bought it for me" | objective version: `მიყიდა` | VERS-02 |
| "was built by the company" | active: `კომპანიამ ააშენა` | VOICE-02 |
| "to do", "-ing" | optative or verbal noun | VNOUN-03 |
| "the child broke the glass" (by accident) | `ბავშვს ჭიქა გაუტყდა` | VOICE-02 |
| generic "you" or "they say" | 3rd plural `ამბობენ`, or a 2nd singular generic | |
| articles "a / the" | usually nothing | STYLE-01 |
