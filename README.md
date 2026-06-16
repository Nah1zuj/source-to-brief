# Source to Brief

`source-to-brief` is a portable Open Design community skill that turns messy source materials into source-grounded, artifact-ready Markdown briefs.

It is designed for the stage before artifact generation:

```text
source materials -> source-grounded brief -> downstream Open Design artifact
```

## What It Does

Use this skill when a user has PDFs, reports, interviews, transcripts, policy documents, product research, competitor materials, meeting notes, or mixed source folders and needs to prepare them for:

- deck
- prototype
- PM spec
- dashboard
- decision room
- design brief

## What It Produces

Primary output:

- `brief.md`

Optional secondary output:

- `source-map.md`

## Output Schema

The default `brief.md` should include:

1. Decision Context
2. Source Inventory
3. Problem Frame
4. Evidence-Backed Insights
5. Opportunity Areas
6. Artifact Translation
7. Assumptions, Risks, and Unknowns
8. Reusable Blocks
9. Source Notes

## Open Design Fit

This skill does not replace artifact-producing skills. It prepares grounded source intelligence for them.

## Portable Skill Shape

The intended Open Design path is:

```text
skills/source-to-brief/SKILL.md
```

with local references, examples, and evals.

## Quality Principles

- Keep outputs source-grounded.
- Do not fabricate citations, statistics, authors, URLs, page numbers, or quotes.
- Separate supplied-source reconstruction from optional external supplementation.
- Keep Markdown preview-friendly.
- Avoid heavy external runtime assumptions.
