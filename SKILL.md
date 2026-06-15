---
name: source-to-brief
zh_name: "Source to Brief"
en_name: "Source to Brief"
description: |
  Turn substantial source materials into grounded Markdown research briefs for downstream Open Design artifacts.
  Use when a user needs to digest PDFs, articles, reports, papers, interviews, transcripts, policy documents, product research, competitive material, or folders of sources before creating a deck, prototype, PM spec, dashboard, decision room, or design brief.
zh_description: "Converts source materials into Markdown research briefs for downstream design artifacts."
en_description: |
  Converts long-form source material into a structured research brief that can feed decks, prototypes, product specs, dashboards, decision rooms, and other Open Design workflows.
triggers:
  - "source to brief"
  - "research brief"
  - "research notes"
  - "turn this PDF into a brief"
  - "summarize sources for a deck"
  - "prepare research for a prototype"
  - "material to brief"
  - "source packet to brief"
  - "report to product brief"
od:
  mode: template
  platform: desktop
  scenario: research
  preview:
    type: markdown
    entry: brief.md
    reload: debounce-100
  example_prompt: |
    Turn this mixed source packet into a research brief for a product strategy deck. Preserve key claims, evidence, open questions, and downstream artifact recommendations.
  example_prompt_i18n:
    zh-CN: "Turn this source packet into a research brief for a product strategy deck, preserving claims, evidence, open questions, and downstream artifact recommendations."
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
    - name: depth
      type: enum
      values: [concise, standard, deep]
      default: standard
    - name: note_language
      type: enum
      values: [English, Chinese, source-language]
      default: English
  outputs:
    primary: brief.md
    secondary: [source-map.md]
  capabilities_required:
    - file_write
---

# Source to Brief

## Purpose

Create a grounded Markdown research brief that prepares long-form source material for downstream Open Design artifacts.

The brief should help the next agent, designer, strategist, PM, or researcher decide:

- what to make next
- which claims are supported
- which evidence should travel downstream
- what remains uncertain
- what questions still need source work

The downstream artifact may be a deck, prototype, PM spec, dashboard, decision room, design brief, or another Open Design artifact.

Do not frame the output as ordinary study notes unless the user explicitly asks for study notes.

Prefer terms such as:

- `research brief`
- `source synthesis`
- `material digest`
- `evidence map`
- `artifact recommendations`

## Interaction Defaults

Before drafting, ask only for missing choices that materially affect the output.

Ask about the downstream artifact when it is unclear:

- `deck`
- `prototype`
- `pm-spec`
- `dashboard`
- `decision-room`
- `design-brief`
- another named artifact type

Ask about brief language when it is unclear.

Ask about depth when it is unclear:

- `concise`
- `standard`
- `deep`

Ask whether the user wants portable Markdown enhancements.

When mentioning Markdown, explain briefly that it works well in:

- Open Design preview
- GitHub or GitLab
- Obsidian
- Typora
- VS Code
- plain text review

For folders or multiple files, ask whether to:

- create one integrated brief
- process files separately
- create a source map plus one integrated brief

For complex, broad, or controversial materials, ask whether to supplement with web or database scholarship.

Ask for destination and filename only when it matters.

Default to `brief.md`.

Create `source-map.md` when the source set is mixed, citation-heavy, or likely to be reused downstream.

If the material is too long for one pass, process it in batches and then produce one integrated brief.

Keep the user informed about the batch plan.

## Inputs

Use the user's source material and artifact goal.

Source material may include:

- PDF
- PPTX or PPT
- Word document
- EPUB
- Markdown
- TXT
- transcript
- report
- article
- essay
- interview
- speech
- literature
- policy document
- technical paper
- competitive research
- user research
- customer notes
- local folder of materials

Use any provided downstream target:

- deck
- prototype
- PM spec
- dashboard
- decision room
- design brief
- another Open Design artifact

Use the audience or decision context when provided.

Use the requested note language and depth when provided.

Use local reference folders or source hierarchy supplied by the user.

If the material cannot be read reliably, explain what is missing.

If the material is too fragmentary to support a grounded brief, ask for clearer source text or permission to produce a limited brief.

## Workflow

1. Build the internal runtime contract from `references/runtime-contract.md`.
2. Diagnose the material internally.
3. Identify the document profile.
4. Identify the content map.
5. Identify the scholarship map.
6. Identify the downstream artifact plan.
7. Select the material-type structure.
8. Read `references/material-type-structures.md` before drafting.
9. Match the source genre.
10. Use the genre pattern for research articles, empirical articles, technical papers, reviews, theory essays, book chapters, lectures, primary texts, case studies, reports, or multi-source folders.
11. Select the discipline adapter.
12. Read `references/discipline-adapters.md` when the material involves philosophy, humanities, social sciences, AI, business, management, finance, or AI-business overlap.
13. If the material is a review, survey, state-of-the-art article, overview, handbook, encyclopedia, or literature-review article, also read `references/review-article-patterns.md`.
14. Use source hierarchy and citation rules from `references/source-quality.md` when adding scholarly discussion.
15. Ask before supplementing with external scholarship for complex, broad, or controversial material.
16. Use `references/output-formats.md` to render portable Markdown.
17. Draft the final brief.
18. Save the final brief as `brief.md` unless the user chose another filename.
19. For mixed or citation-heavy source sets, save a compact `source-map.md`.
20. In `source-map.md`, list source role, trust level, and reusable claims.
21. Run the P0 quality gates in `references/checklist.md` before delivery.
22. Verify each declared output file exists.

## Brief Structure

Adapt section names to the chosen language and downstream artifact.

Use this as the default shape:

```markdown
# Research Brief: <topic>

Reading path: <source type>; <domain>; <downstream artifact>; <decision focus>.

## 1. Executive Orientation

## 2. Source Map

## 3. Core Claims And Evidence

## 4. User, Market, Product, Or Policy Implications

## 5. Tensions, Unknowns, And Risks

## 6. Downstream Artifact Recommendations

## 7. Reusable Content Blocks

## 8. References And Source Notes
```

For design or product workflows, include reusable blocks only when they are actually grounded in the sources.

Reusable blocks may include:

- problem statement candidates
- audience or persona cues
- evidence-backed claims for a deck
- prototype requirements
- scenario beats
- PM spec requirements
- PM spec non-goals
- dashboard metrics
- dashboard dimensions
- decision-room questions
- short attributed quotes or excerpts

## Hard Rules

- Base the main reconstruction on the source material.
- Separate source reconstruction from external scholarly or web supplementation.
- Ask before using external scholarly expansion unless the user already requested it.
- Do not invent authors.
- Do not invent titles.
- Do not invent years.
- Do not invent page numbers.
- Do not invent DOIs.
- Do not invent URLs.
- Do not invent quotes.
- Do not invent statistics.
- Do not invent formulas.
- Do not invent data.
- Do not invent citations.
- Use `--`, `unknown`, or a labelled gap where the source does not support a detail.
- Do not produce a generic summary.
- Preserve definitions when they matter.
- Preserve distinctions when they matter.
- Preserve argument steps when they matter.
- Preserve evidence when it matters.
- Preserve examples when they matter.
- Preserve limitations when they matter.
- Preserve objections when they matter.
- Preserve conclusion boundaries when they matter.
- Do not expose the internal review process in the final brief.
- Do not create decorative Markdown.
- Use tables only when they reduce cognitive load.
- Use diagrams only when they reduce cognitive load.
- Use Mermaid charts only when they reduce cognitive load.
- Do not claim that the brief is ready for a downstream artifact unless the artifact recommendations are traceable to the source.
- Keep the output readable in plain Markdown.
- Keep the output readable in Open Design Markdown preview.

## Source Reconstruction Versus Supplementation

Treat source reconstruction as the main product.

Source reconstruction means extracting, organizing, and preserving what the provided materials actually support.

External supplementation means adding context from web, database, scholarly, or model-background knowledge beyond the supplied materials.

Keep these layers visibly separate.

If external supplementation was not used, say so in the source notes.

If external supplementation was used, mark it clearly and cite the source used.

Never blur external context into the source's own claims.

## Open Design Positioning

Treat this skill as a pre-artifact research layer.

It does not replace deck, prototype, PM spec, dashboard, decision-room, or design-brief skills.

It prepares grounded source intelligence for those downstream artifact skills.

When delivering the result, briefly name the likely next Open Design artifact path.

Use examples such as:

- `Next artifact fit: deck` when the material supports a narrative presentation.
- `Next artifact fit: prototype` when the material contains user needs, flows, or interaction requirements.
- `Next artifact fit: pm-spec` when the material contains requirements, constraints, and tradeoffs.
- `Next artifact fit: dashboard` when the material contains metrics, dimensions, and monitoring needs.
- `Next artifact fit: decision-room` when the material contains competing options, risks, and unresolved questions.

## Outputs

Always write a primary Markdown artifact.

The default primary artifact is:

```text
brief.md
```

Write an optional secondary artifact when the source set is mixed, citation-heavy, or likely to be reused.

The optional secondary artifact is:

```text
source-map.md
```

Before final delivery, verify that declared output files exist.
