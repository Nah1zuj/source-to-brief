# Source to Brief

`source-to-brief` is an Open Design-oriented skill that turns substantial source materials into grounded Markdown research briefs.

It is designed as a pre-artifact research layer: source material -> structured research brief -> downstream artifact. The generated brief can feed Open Design workflows such as decks, prototypes, PM specs, dashboards, decision rooms, and design briefs.

## What It Does

Use this skill when you need to digest PDFs, articles, reports, papers, interviews, transcripts, policy documents, product research, competitive material, or folders of sources before creating another artifact.

The primary output is `brief.md`. For mixed or citation-heavy source sets, the skill may also create `source-map.md`.

## Output Shape

A typical brief includes:

- executive orientation
- source map
- core claims and evidence
- product, market, policy, user, or technical implications
- tensions, unknowns, and risks
- downstream artifact recommendations
- reusable content blocks
- references and source notes

## Open Design Fit

This skill is meant to complement artifact-producing skills. It does not replace deck, prototype, PM spec, dashboard, or design-brief skills. Instead, it prepares grounded source intelligence for them.

`SKILL.md` includes Open Design-oriented metadata:

- concrete `triggers`
- `od.mode`
- Markdown preview settings
- example prompt
- declared primary output
- required file-write capability

## Structure

```text
.
|-- SKILL.md
|-- examples/
|   `-- brief.md
|-- evals/
|   |-- basic_acceptance.md
|   `-- evals.json
`-- references/
    |-- checklist.md
    |-- discipline-adapters.md
    |-- material-type-structures.md
    |-- output-formats.md
    |-- review-article-patterns.md
    |-- runtime-contract.md
    `-- source-quality.md
```

## Installation

Install this folder as a standalone skill folder in a compatible Codex, Claude Code, or Open Design skill environment.

For Open Design collaboration, the main question is whether this should be classified as a `utility` skill, a `template` skill, or a community skill bundle.

## Quality Gates

Before completion, the skill runs the P0 gates in `references/checklist.md`: source grounding, honest gaps, no fabricated citations or statistics, traceable downstream recommendations, clean Markdown preview, and verified output files.
