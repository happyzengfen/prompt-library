# Contributing

Thank you for improving this repository.

## Scope

This repository is a public package for a single Claude skill. Contributions should preserve the existing runtime behavior unless a maintainer explicitly decides to change the behavior contract.

## Core maintenance rules

1. `references/prompts.md` is the only source of truth for template bodies.
2. `SKILL.md` must stay synchronized with `references/prompts.md`.
3. Keep prompt numbering continuous and stable.
4. Keep prompt titles identical across the index and template headings.
5. Do not duplicate full template text into README, examples, or issue templates.
6. When the user provides source material and asks for direct execution, the skill should not distribute a prompt template.

## Safe changes

Good contribution types:

- improve public documentation
- add or refine examples
- fix Markdown formatting drift
- clarify matching descriptions without changing matching rules
- correct title/index inconsistencies
- improve issue and PR templates

Changes that need extra care:

- editing any template body in `references/prompts.md`
- changing prompt numbering
- changing titles used by the matching index
- changing the trigger or non-trigger contract in `SKILL.md`

## Sync checklist

Before opening a pull request, verify all of the following:

- [ ] `SKILL.md` lists 13 prompts
- [ ] `references/prompts.md` contains the same 13 titles in the same order
- [ ] numbering is continuous with no gaps
- [ ] template bodies remain the authoritative source in `references/prompts.md`
- [ ] examples do not introduce a second source of truth
- [ ] the direct-task bypass behavior is still documented

## Suggested workflow

1. Update `references/prompts.md` if a template title or body changes.
2. Update the index in `SKILL.md` to match exactly.
3. Update examples only when behavior illustrations need to change.
4. Summarize any user-visible change in `CHANGELOG.md`.

## Pull request expectations

Please include:

- a short summary of the change
- why the change is needed
- whether any prompt title, numbering, or body changed
- how you verified index/template consistency
