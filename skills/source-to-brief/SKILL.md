---
name: source-to-brief
description: |
  Turn source materials into source-grounded, artifact-ready Markdown briefs for downstream Open Design artifacts.
inputs:
  - name: source_material
    type: string
    required: true
  - name: downstream_artifact
    type: enum
    values: [deck, prototype, pm-spec, dashboard, decision-room, design-brief, other]
    default: deck
  - name: decision_context
    type: string
    required: false
  - name: depth
    type: enum
    values: [concise, standard, deep]
    default: standard
  - name: brief_language
    type: enum
    values: [English, Chinese, source-language]
    default: English
outputs:
  primary: brief.md
  secondary:
    - source-map.md
triggers:
  - source to brief
  - source packet to brief
  - research brief for deck
  - prepare sources for prototype
  - prepare sources for PM spec
  - summarize sources for design brief
  - turn interviews into design brief
  - turn report into product brief
  - create evidence-backed brief
od:
  mode: utility
  platform: desktop
  scenario: research
  preview:
    type: markdown
    entry: brief.md
    reload: debounce-100
  example_prompt: |
    Turn this mixed source packet into a source-grounded brief for a product strategy deck. Preserve evidence, confidence, open questions, and reusable artifact blocks.
  design_system:
    requires: false
    sections: []
  inputs:
    - name: source_material
      type: string
      required: true
    - name: downstream_artifact
      type: enum
      values: [deck, prototype, pm-spec, dashboard, decision-room, design-brief, other]
      default: deck
    - name: decision_context
      type: string
      required: false
    - name: depth
      type: enum
      values: [concise, standard, deep]
      default: standard
    - name: brief_language
      type: enum
      values: [English, Chinese, source-language]
      default: English
  outputs:
    primary: brief.md
    secondary:
      - source-map.md
  capabilities_required:
    - file_write
---

# Source to Brief

## Purpose

Create a source-grounded Markdown brief that prepares messy source materials for downstream Open Design artifacts.

The skill answers:

- What does the supplied material actually support?
- Which insights can safely travel into a deck, prototype, PM spec, dashboard, decision room, or design brief?
- Which claims are grounded, uncertain, or unsupported?
- What reusable blocks can downstream artifact-generating skills consume?

This is a design-facing pre-artifact research layer, not a generic summarizer. Academic or discipline-heavy handling remains available as a secondary mode when the source material requires it.

## Community Contribution Shape

Keep the skill portable and self-contained:

```text
skills/source-to-brief/
|-- SKILL.md
|-- examples/
|-- evals/
`-- references/
```

Do not require package installs, servers, databases, daemons, browser automation, app bridges, API keys, or custom runtime tools as part of the core contract. Use host capabilities to read supplied files, then produce Markdown.

## Interaction Defaults

Before drafting, ask only for missing choices that materially affect the output.

Clarify the downstream artifact when it is not supplied:

- `deck`
- `prototype`
- `pm-spec`
- `dashboard`
- `decision-room`
- `design-brief`
- `other`

Use `standard` depth and English by default unless the user requests a different depth or language. Default to `brief.md` as the primary output. Create `source-map.md` when the source set is mixed, citation-heavy, or likely to be reused downstream.

If external web or database supplementation would be useful, ask first unless the user already requested it. If it is used, keep it visibly separate from supplied-source reconstruction.

## Inputs

Source material may include:

- PDFs, reports, policy documents, or technical documents
- interviews, transcripts, support notes, user research, or meeting notes
- product research, competitor scans, market reports, or business materials
- mixed folders or source packets
- academic, literary, legal, or discipline-heavy sources when explicitly relevant

Use the user's decision context, audience, downstream artifact target, language, and depth when provided. If the material cannot be read reliably, explain the limit and produce only a limited brief or ask for clearer source text.

## Workflow

1. Build the internal runtime contract from `references/runtime-contract.md`.
2. Identify the downstream artifact and decision context.
3. Read `references/artifact-contracts.md` before generating artifact recommendations.
4. Prefer `references/design-workflow-adapters.md` for design, product, research, market, policy, technical, meeting-note, or competitor materials.
5. Use `references/evidence-confidence.md` to label major insights where the source material supports doing so.
6. Use `references/source-quality.md` to preserve the boundary between supplied evidence, model inference, external supplementation, and unsupported gaps.
7. Use `references/material-type-structures.md` when source genre affects the reconstruction.
8. Use `references/discipline-adapters.md` only as a secondary fallback for explicitly academic or discipline-heavy sources.
9. If the material is a review, survey, field overview, handbook, encyclopedia entry, or literature-review article, also read `references/review-article-patterns.md`.
10. Use `references/output-formats.md` to render portable Markdown.
11. Draft `brief.md` using the default schema below.
12. Create `source-map.md` when useful for mixed sources, citation-heavy packets, or downstream reuse.
13. Run the P0 gates in `references/checklist.md`.
14. Verify each declared output file exists.

## Default Brief Structure

Use this as the default shape:

```markdown
# Design Intelligence Brief: <topic>

Reading path: <source types> -> <decision context> -> <downstream artifact>

## 1. Decision Context

What decision, design direction, or downstream artifact this brief is meant to support.

## 2. Source Inventory

List source materials, source roles, and reliability notes.

## 3. Problem Frame

Reconstruct the core user, product, market, business, policy, or technical problem from the sources.

## 4. Evidence-Backed Insights

| Insight | Evidence | Confidence | Design / Product Implication | Source Gap |
|---|---|---|---|---|

## 5. Opportunity Areas

List what can be designed, improved, prototyped, positioned, measured, or tested.

## 6. Artifact Translation

Translate the brief into the selected downstream artifact.

## 7. Assumptions, Risks, And Unknowns

Separate source-supported facts from assumptions and missing information.

## 8. Reusable Blocks

Only include blocks grounded in the supplied sources.

## 9. Source Notes

Explain what came from supplied sources, what came from optional external supplementation, and what remains unsupported.
```

## Artifact Translation Requirements

For `deck`, include:

- narrative thesis
- 3-5 slide claims
- strongest evidence
- recommended storyline

For `prototype`, include:

- target user
- scenario
- core flow
- required screens or states
- interaction requirements
- testable assumptions

For `pm-spec`, include:

- problem statement
- user stories
- functional requirements
- non-goals
- constraints
- success metrics
- risks

For `dashboard`, include:

- decision to monitor
- metrics
- dimensions
- data sources
- cadence
- caveats

For `decision-room`, include:

- competing options
- decision criteria
- tradeoffs
- risks
- unresolved questions

For `design-brief`, include:

- audience
- problem
- goals
- constraints
- deliverables
- success criteria

## Reusable Blocks

Only include blocks grounded in supplied sources:

- problem statement candidates
- user need statements
- artifact-ready claims
- product requirements
- prototype prompts
- dashboard metric candidates
- decision-room questions
- short attributed quotes or excerpts

Do not invent quotes, source attributions, page numbers, statistics, URLs, DOIs, authors, or citations. If a useful block is not supported, mark it as an assumption, weak signal, or open question instead.

## Source Reconstruction Versus Supplementation

Treat supplied-source reconstruction as the main product.

External supplementation means adding context from web, database, scholarly, or model-background knowledge beyond the supplied materials. Keep these layers visibly separate:

1. supplied-source evidence
2. model inference
3. optional external supplementation
4. unsupported gaps

If external supplementation was not used, say so in the source notes. If it was used, cite the sources used and keep them separate from the supplied source inventory.

## Hard Rules

- Primary output is `brief.md`.
- Optional secondary output is `source-map.md`.
- Output must be portable Markdown.
- Major claims must be grounded in supplied sources.
- Evidence confidence should be labelled where useful.
- Artifact recommendations must be traceable to source evidence.
- Reusable blocks must be source-grounded.
- Do not fabricate citations, authors, titles, years, page numbers, DOIs, URLs, quotes, statistics, formulas, data, claims, or source attributions.
- Do not blur external context into the source's own claims.
- Do not present low-confidence material as a strong design conclusion.
- Do not produce a generic summary.
- Do not expose the internal review process in the final brief.
- Use tables and diagrams only when they reduce cognitive load.

## Outputs

Always write a primary Markdown artifact:

```text
brief.md
```

Write an optional secondary artifact when the source set is mixed, citation-heavy, or likely to be reused:

```text
source-map.md
```

Before final delivery, verify that declared output files exist.
