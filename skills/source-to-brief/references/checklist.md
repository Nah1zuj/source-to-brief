# Checklist

Run this checklist before emitting the final artifact or declaring the brief complete.

## P0 Open Design Skill Gates

- [ ] Output is portable Markdown.
- [ ] Primary output is `brief.md`.
- [ ] Optional secondary output is `source-map.md`.
- [ ] The output follows a predictable schema.
- [ ] The brief names the downstream artifact target.
- [ ] Major claims are grounded in supplied sources.
- [ ] External supplementation is clearly separated.
- [ ] No fabricated citations, authors, page numbers, URLs, DOIs, statistics, or quotes.
- [ ] Evidence confidence is labeled where useful.
- [ ] Artifact recommendations are traceable to source evidence.
- [ ] Reusable blocks are only included when grounded.
- [ ] No heavy external runtime assumptions are introduced.

## P1 Quality Checks

- [ ] The title and reading path make the source type, decision context, and downstream artifact clear.
- [ ] Source Inventory lists source roles and reliability notes.
- [ ] Problem Frame reconstructs the user, product, market, business, policy, or technical problem from sources.
- [ ] Evidence-Backed Insights separate evidence, confidence, implication, and source gap.
- [ ] Opportunity Areas are designable, testable, measurable, or decision-relevant.
- [ ] Artifact Translation follows the relevant contract in `artifact-contracts.md`.
- [ ] Assumptions, Risks, And Unknowns separate facts from assumptions and missing information.
- [ ] Reusable Blocks are specific enough to feed a downstream artifact.
- [ ] Mixed-source briefs synthesize across sources instead of stacking mini-summaries.
- [ ] If external supplementation was not used, Source Notes say so briefly.
- [ ] If external supplementation was used, Source Notes cite and separate it.
- [ ] No prompt transcript, hidden checklist, or process log appears in the final brief.

## Portable Skill Checks

- [ ] The target folder is `skills/source-to-brief/`.
- [ ] The target folder contains `SKILL.md`, `references/`, `examples/`, and `evals/`.
- [ ] `SKILL.md` defines inputs and outputs.
- [ ] `triggers` are concrete and design-facing.
- [ ] `od.preview.type` is `markdown`.
- [ ] `od.outputs.primary` points to `brief.md`.
- [ ] No unrelated framework, daemon, package, server, database, API key, app bridge, or locale file is required for the contribution.
