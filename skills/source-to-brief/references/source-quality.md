# Source Quality For Design Intelligence Briefs

The brief must preserve the difference between:

1. supplied-source evidence
2. model inference, clearly labeled as inference rather than evidence
3. optional external supplementation
4. unsupported gaps

## Design Evidence Priority

### High Confidence

- repeated user interview patterns
- observed user behavior
- analytics data
- customer support logs
- verified internal metrics
- official policy documentation
- official technical documentation
- direct source excerpts with stable location

### Medium Confidence

- small-sample interviews
- stakeholder statements
- credible market or industry reports
- competitor feature scans
- meeting notes
- sales or customer-success anecdotes with partial detail

### Low Confidence

- vendor claims
- unsourced slides
- single anecdote
- speculative strategy memo
- model inference, clearly labeled as inference rather than evidence
- outdated market data
- search snippets

## Rule

Do not present low-confidence material as a strong design conclusion. Label it as an assumption, weak signal, hypothesis, or open question.

## Evidence Types

User evidence:

- interviews, transcripts, diary studies, surveys, usability sessions, field notes, user-research notes, and product-discovery notes
- Strongest when patterns repeat across users or when quotes have stable attribution inside the supplied material

Behavioral evidence:

- observed behavior, workflow traces, analytics, event logs, support tickets, and customer success notes
- Strongest when sample, timeframe, and metric definitions are available

Business evidence:

- revenue, adoption, churn, funnel, sales, support, retention, pricing, and operating constraints
- Strongest when tied to verified internal metrics or clearly identified reports

Market evidence:

- market reports, competitor scans, analyst summaries, category research, positioning pages, and pricing material
- Treat vendor or competitor claims as positioned claims, not neutral facts

Policy evidence:

- laws, regulations, official policy documents, compliance guidance, public-sector reports, and internal policy memos
- Preserve rule, scope, affected users, obligations, and uncertainty

Technical evidence:

- product docs, engineering memos, technical papers, API docs, benchmarks, architecture notes, and implementation constraints
- Separate capability, limitation, feasibility, latency, cost, data, and operational risk

Stakeholder evidence:

- meeting notes, executive memos, strategy docs, sales anecdotes, and internal proposals
- Useful for intent and constraints, but mark as stakeholder perspective unless independently supported

External web supplementation:

- Use only when requested or approved, except when needed to verify a user-requested current fact
- Keep it separate from supplied sources and cite links used

## Academic Or Scholarly Sources

Use academic or scholarly source hierarchy only as a secondary mode when the user explicitly asks for academic interpretation or the supplied materials are primarily scholarly.

Higher-confidence scholarly materials include:

- user-provided primary texts, papers, books, datasets, or reading packets
- peer-reviewed journal articles
- academic books and book chapters
- university press publications
- official reports from universities, labs, think tanks, or public agencies
- conference papers in fields where they are primary venues
- official documentation or technical reports for technical systems

Lower-confidence scholarly-adjacent materials include:

- general encyclopedias
- blogs
- media articles
- vendor white papers
- unsourced slide decks
- search snippets

These sources may provide context, but they should not override the design evidence priority when the brief is preparing a downstream Open Design artifact.

## Citation And Attribution Rules

- Clearly mark which references are supplied sources and which were externally supplemented.
- If external supplementation was not used, say so briefly in Source Notes.
- If external supplementation was used, cite the sources used and label them separately.
- Use in-prose attribution when attribution clarifies ownership of a claim.
- Do not invent authors, titles, years, page numbers, DOIs, URLs, quotes, statistics, claims, or source attributions.
- Do not cite search snippets as if they were full sources.
- If precise bibliographic data cannot be verified, say so briefly or omit the source.
- For direct quotations, use short excerpts only when wording matters and the source location is stable enough to identify.

## Source Reconstruction Versus Supplementation

Source reconstruction extracts, organizes, and preserves what the supplied materials actually support.

External supplementation adds context beyond the supplied materials. It can clarify or verify context, but it must not overwrite the source's own claims.

Unsupported gaps should remain visible as gaps. Use labels such as `unknown`, `not supplied`, `weak signal`, `hypothesis`, or `requires verification`.

## Forbidden Behaviors

- Do not write strong artifact recommendations from unsupported claims.
- Do not blend model inference into supplied-source evidence.
- Do not use external context to make supplied evidence look stronger than it is.
- Do not present stakeholder preference as user evidence.
- Do not present competitor marketing as market proof.
- Do not write the final brief as a source ledger unless the user asks for an audit.
