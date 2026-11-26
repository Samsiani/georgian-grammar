# Georgian Grammar Skill

An agent skill that helps Claude and other AI agents write, correct, translate and explain **Georgian (ქართული)** accurately.

It holds **128 numbered rules** in 15 reference files. They cover case marking by tense series, verb agreement and inversion, declension with stem changes, numerals and dates, postpositions, negation, reported speech, punctuation, polite register, calques, and translation fidelity. Each rule has an ID, a tag (`[norm]`, `[convention]` or `[style]`), correct and incorrect examples, and its source.

ქართული ვერსია: [README.ka.md](README.ka.md)

## What it does

| Mode | What happens |
|---|---|
| **Write** | Drafts Georgian in Georgian sentence structure, then checks it against the core rules before answering. |
| **Correct** | Makes minimal edits that fix only real rule violations, and lists each change with its rule ID. Correct text is left alone. |
| **Explain** | Answers grammar questions from the rules. For multiple-choice questions it checks every option. |
| **Translate** | Keeps who did what, direction, causation, certainty, conditions, evidentiality, and whose words are reported. |

## Install

### Claude Code (plugin)

In Claude Code, run:

```
/plugin marketplace add Samsiani/georgian-grammar
/plugin install georgian-grammar@georgian-grammar
```

### Claude Code (manual)

```bash
git clone https://github.com/Samsiani/georgian-grammar.git
cp -R georgian-grammar/skills/georgian-grammar ~/.claude/skills/georgian-grammar
```

For a single project, copy the folder to `.claude/skills/georgian-grammar` inside that project instead.

### Claude apps (claude.ai, Claude Desktop)

1. Download `georgian-grammar.zip` from the [latest release](https://github.com/Samsiani/georgian-grammar/releases/latest).
2. In Claude, open **Settings → Capabilities**. In **Skills**, upload the zip. Code execution must be enabled for skills.

### Other agents (Codex and any agent that supports Agent Skills)

Copy only the `skills/georgian-grammar` folder into the agent's skills directory, for example:

```bash
cp -R skills/georgian-grammar ~/.codex/skills/georgian-grammar
```

Agents that read `AGENTS.md` will also find a pointer to the skill in this repository.

> Other Georgian skills also use the name `georgian-grammar`. If you install one manually next to this one, rename one of the folders. Plugin installs are namespaced and don't clash.

## Structure

```
.claude-plugin/          plugin.json, marketplace.json (Claude Code)
skills/georgian-grammar/
  SKILL.md               modes, 12 core checks, reference map
  references/            15 rule files (01-spelling … 15-common-errors)
evals/cases.md           25 test cases: corrections, clean texts, writing tasks
.github/workflows/       builds the release zip on every v* tag
```

## Testing

`evals/cases.md` has 19 texts with errors, 3 correct texts that must come back unchanged, and 3 writing or explanation tasks. Run them with and without the skill and compare. A native speaker should review the expected answers before relying on them.

## Sources and credits

The rules are restated in our own words. No source text is copied, and the source books are not included. Main sources:

- **ირბახი program textbooks** (Ministry of Education and Science of Georgia, 2016):
  - K. Gabunia, *ქართული ენის გრამატიკის ზოგადი კურსი*;
  - R. Zekalashvili, *ქართული ენის გრამატიკის მოკლე კურსი*;
  - N. Davitashvili, *შემსწავლელის გრამატიკა, ნაწილი I*.
- **A. Arabuli**, *ქართული მეტყველების კულტურა* (2008): the writing norms, used through G. Zhgamadze's CC BY 4.0 restatement.
- **G. Zhgamadze**, [georgian-grammar-skill](https://github.com/guramzhgamadze/georgian-grammar-skill) (CC BY 4.0).
- **BTU**, [*Georgian Grammar for Artificial Intelligence — Stage 1*](https://github.com/BTU-Business-and-Technology-University/georgian-grammar-for-ai) (CC BY 4.0): the error taxonomy.
- **L. Ildani**, [georgian-grammar-codex-skill](https://github.com/levan-ildani/georgian-grammar-codex-skill) (Apache-2.0): workflow ideas.

Full attribution and the list of changes are in [NOTICE.md](NOTICE.md).

## Contributing

Corrections from native speakers and linguists are welcome. Open an issue or a pull request that names:
- the rule ID;
- the wrong and right forms;
- a source.

Keep rule IDs unique, tag every rule, and restate sources in your own words.

## License

- Rule content (`skills/`, `evals/`, documentation): [CC BY 4.0](LICENSE).
- GitHub workflow files: [MIT](LICENSE-CODE).
