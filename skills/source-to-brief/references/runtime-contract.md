# Runtime Contract

Use this contract internally before drafting. It is not a visible section in the final brief unless the user asks for an audit.

## BriefProfile

Build a compact profile:

- topic
- source_types
- downstream_artifact
- decision_context
- audience, if supplied
- depth: concise | standard | deep
- brief_language
- source_reliability_notes
- external_supplementation_status: not-used | ask-user | user-approved | user-declined

## SourceMap

Identify the source roles:

- controlling source
- supporting sources
- contradictory sources
- source gaps
- source reliability
- stable excerpts or locations, only when supplied and verifiable

## DesignIntelligenceMap

Identify:

- core problem
- affected users, customers, stakeholders, or systems
- evidence-backed insights
- confidence labels
- implications
- opportunity areas
- assumptions
- risks
- unknowns
- reusable blocks

## ArtifactPlan

Before writing, choose:

- downstream artifact target
- artifact contract from `artifact-contracts.md`
- artifact-specific reusable blocks
- output filename, defaulting to `brief.md`
- whether `source-map.md` is needed

## Runtime Boundary

This contract guides reasoning and quality control. Do not print these maps as a checklist. Transform them into a clean design intelligence brief whose sections fit the source material and downstream artifact.
