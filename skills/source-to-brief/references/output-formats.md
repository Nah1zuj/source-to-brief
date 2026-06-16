# Output Formats

Default to a `.md` file written in portable Markdown.

The primary output is:

```text
brief.md
```

The optional secondary output is:

```text
source-map.md
```

## Portable Markdown

Markdown output must be platform-neutral:

- standard headings
- paragraphs
- lists
- tables where useful
- short block quotes only when wording matters and attribution is stable
- Mermaid only when it clarifies structure
- source notes at the end

Do not use:

- YAML properties by default
- Obsidian-only links as the only label for a concept
- plugin-dependent syntax
- excessive callouts
- custom CSS or viewer-specific layout
- decorative diagrams

## Default Brief Pattern

Use this predictable schema unless the user asks for a different shape:

```markdown
# Design Intelligence Brief: <topic>

Reading path: <source types> -> <decision context> -> <downstream artifact>

## 1. Decision Context
## 2. Source Inventory
## 3. Problem Frame
## 4. Evidence-Backed Insights
## 5. Opportunity Areas
## 6. Artifact Translation
## 7. Assumptions, Risks, And Unknowns
## 8. Reusable Blocks
## 9. Source Notes
```

## Evidence Table

Use this table when it improves scanability:

```markdown
| Insight | Evidence | Confidence | Design / Product Implication | Source Gap |
|---|---|---|---|---|
```

## Source Notes

Always make the source boundary clear:

- what came from supplied sources
- what came from optional external supplementation
- what is model inference
- what remains unsupported

If external supplementation was not used, say so briefly.

## Source Passages And Quotations

Use block quotes only for short passages that matter for the concept, evidence, or artifact decision.

```markdown
> Short source passage. (Source location, if verified)
```

Rules:

- Do not invent direct quotations.
- Do not infer page numbers or stable locations.
- Do not quote source text as decoration.
- If the location cannot be verified, paraphrase instead.

## Diagrams

Use diagrams only when they reduce cognitive load:

- artifact flow
- decision map
- evidence chain
- prototype flow
- dashboard metric tree
- decision-room option map

Prefer plain tables when tables are clearer.
