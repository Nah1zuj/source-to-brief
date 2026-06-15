---
name: source-to-brief
zh_name: "Source to Brief"
en_name: "Source to Brief"
description: |
  Turn substantial source materials into grounded Markdown research briefs for downstream Open Design artifacts. Use when a user needs to digest PDFs, articles, reports, papers, interviews, transcripts, policy documents, product research, competitive material, or folders of sources before creating a deck, prototype, PM spec, dashboard, decision room, or design brief.
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

Create a grounded Markdown research brief that prepares long-form material for downstream Open Design artifacts. The brief should help the next agent or designer decide what to make, what claims are supported, what remains uncertain, and which evidence or source details should travel into a deck, prototype, PM spec, dashboard, decision room, or design brief.

Do not frame the output as ordinary study notes unless the user explicitly asks for that. Prefer terms such as `research brief`, `source synthesis`, `material digest`, `evidence map`, and `artifact recommendations`.

## Interaction Defaults

Before drafting, ask only for missing choices that materially affect the output:

- Target downstream artifact: `deck`, `prototype`, `pm-spec`, `dashboard`, `decision-room`, `design-brief`, or another artifact type.
- Brief language when unclear.
- Depth: `concise`, `standard`, or `deep`.
- Whether to use portable Markdown enhancements. Mention that Markdown works well in Open Design preview, GitHub/GitLab, Obsidian, Typora, and VS Code, while remaining readable as plain text.
- For folders or multiple files: whether to create one integrated brief, process files separately, or create a source map plus integrated brief.
- For complex, broad, or controversial materials: whether to supplement with web/database scholarship.
- Destination and filename. Default to `brief.md`; create `source-map.md` when the source set is mixed or citation-heavy.

If the material is too long for one pass, process it in batches and then produce one integrated brief. Keep the user informed about the batch plan.

## Inputs

Use the user's source material and artifact goal:

- Source material: PDF, PPTX/PPT, Word, EPUB, Markdown, TXT, transcript, report, article, essay, interview, speech, literature, policy document, technical paper, competitive research, user research, customer notes, or a local folder of materials.
- Downstream artifact target: deck, prototype, PM spec, dashboard, decision room, design brief, or another OD artifact.
- Audience or decision context, if provided.
- Note language and depth, if provided.
- Local reference folders or source hierarchy supplied by the user.

If the material cannot be read reliably or is too fragmentary to support a grounded brief, explain what is missing and ask for clearer source text or permission to produce a limited brief.

## Workflow

1. Build the internal runtime contract from `references/runtime-contract.md`.
2. Diagnose the material internally:
   - document profile
   - content map
   - scholarship map
   - downstream artifact plan
3. Select the material-type structure. Read `references/material-type-structures.md` before drafting so the brief follows the source genre: research article, empirical article, technical paper, review, theory essay, book chapter, lecture, primary text, case study, report, or multi-source folder.
4. Select the discipline adapter. Read `references/discipline-adapters.md` when the material involves philosophy, humanities, social sciences, AI, business/management, finance, or AI-business overlap.
5. If the material is a review, survey, state-of-the-art article, overview, handbook, encyclopedia, or literature-review article, also read `references/review-article-patterns.md`.
6. Use source hierarchy and citation rules from `references/source-quality.md` when adding scholarly discussion. Ask before supplementing with external scholarship for complex, broad, or controversial material.
7. Use `references/output-formats.md` to render portable Markdown.
8. Draft the final brief and save it as `brief.md` unless the user chose another filename.
9. For mixed or citation-heavy source sets, save a compact `source-map.md` that lists the source role, trust level, and reusable claims.
10. Run the P0 quality gates in `references/checklist.md` before delivery.
11. Verify each declared output file exists.

## Brief Structure

Adapt section names to the chosen language and downstream artifact. Use this as the default shape:

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

For design or product workflows, include reusable blocks only when they are actually grounded in the sources:

- problem statement candidates
- audience or persona cues
- evidence-backed claims for a deck
- prototype requirements or scenario beats
- PM spec requirements and non-goals
- dashboard metrics or dimensions
- decision-room questions
- quotes or excerpts, kept short and attributed

## Hard Rules

- Base the main reconstruction on the source material.
- Separate source reconstruction from external scholarly or web supplementation.
- Ask before using external scholarly expansion unless the user already requested it.
- Do not invent authors, titles, years, page numbers, DOIs, URLs, quotes, statistics, formulas, data, or citations.
- Use `--`, `unknown`, or a labelled gap where the source does not support a detail.
- Do not produce a generic summary. Preserve definitions, distinctions, argument steps, evidence, examples, limitations, objections, and conclusion boundaries when they matter.
- Do not expose the internal review process in the final brief.
- Do not create decorative Markdown. Tables, diagrams, and Mermaid charts are allowed only when they reduce cognitive load.
- Do not claim that the brief is ready for a downstream artifact unless the artifact recommendations are traceable to the source.
- Keep the output readable in plain Markdown and in OD's Markdown preview.

## Open Design Positioning

Treat this skill as a pre-artifact research layer. It does not replace deck, prototype, PM spec, or dashboard skills. It prepares grounded source intelligence for them.

When delivering the result, briefly name the likely next OD artifact path, for example:

- `Next artifact fit: deck` when the material supports a narrative presentation.
- `Next artifact fit: prototype` when the material contains user needs, flows, or interaction requirements.
- `Next artifact fit: pm-spec` when the material contains requirements, constraints, and tradeoffs.
- `Next artifact fit: dashboard` when the material contains metrics, dimensions, and monitoring needs.
- `Next artifact fit: decision-room` when the material contains competing options, risks, and unresolved questions.
