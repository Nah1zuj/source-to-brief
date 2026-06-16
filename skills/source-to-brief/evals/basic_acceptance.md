# Source to Brief Basic Acceptance

## Prompt

Use `source-to-brief` to turn a source packet into a source-grounded Markdown brief for a downstream Open Design artifact.

The source packet may contain interviews, support notes, competitor scans, market reports, policy documents, technical documents, meeting notes, product research, or mixed materials.

## Pass Conditions

- Identifies the downstream artifact target.
- Produces portable Markdown.
- Saves the primary output as `brief.md` by default.
- Creates optional `source-map.md` when the packet is mixed, citation-heavy, or reusable.
- Follows the predictable brief schema:
  - Decision Context
  - Source Inventory
  - Problem Frame
  - Evidence-Backed Insights
  - Opportunity Areas
  - Artifact Translation
  - Assumptions, Risks, And Unknowns
  - Reusable Blocks
  - Source Notes
- Separates supplied-source evidence from assumptions, model inference, and optional external supplementation.
- Labels evidence confidence where useful.
- Produces artifact-specific reusable blocks.
- Ensures artifact recommendations are traceable to source evidence.
- Does not fabricate citations, source details, authors, URLs, page numbers, DOIs, statistics, quotes, or source attribution.
- Avoids heavy runtime assumptions such as package installs, servers, databases, API keys, daemons, browser automation, app bridges, or hosted services.
- Uses `references/artifact-contracts.md` for downstream artifact translation.
- Prefers `references/design-workflow-adapters.md` for design and product workflows.
- Uses `references/discipline-adapters.md` only as a secondary fallback for explicitly academic or discipline-heavy sources.
- Runs the P0 gates in `references/checklist.md`.

## Design Workflow Eval Coverage

- User interviews + support notes -> onboarding prototype brief.
- Competitor scan + market report -> product strategy deck brief.
- Policy document -> compliance-aware design brief.
- Meeting notes + analytics summary -> PM spec brief.
- Technical paper + product memo -> AI feature prototype brief.

## Strong Output Signals

- The brief is immediately useful to the next artifact-building step.
- Claims, evidence, confidence, and source gaps are easy to inspect.
- Reusable blocks are specific enough for the selected artifact.
- Weak evidence is labelled as a weak signal, assumption, or open question.
- Source Notes make clear whether external supplementation was used.
