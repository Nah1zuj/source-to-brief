# Checklist

Run this checklist before emitting the final `<artifact>` or declaring the brief complete.

## P0

- The skill writes a primary `brief.md` artifact.
- The Markdown preview renders cleanly.
- The brief is grounded in the provided source material.
- The brief distinguishes source reconstruction from external supplementation.
- The brief does not invent authors, titles, years, page numbers, DOIs, URLs, quotations, statistics, claims, or source attributions.
- The brief preserves core claims, evidence, assumptions, examples, objections, limitations, and open questions.
- The brief includes downstream artifact recommendations when relevant.
- The output is useful as a reusable research brief, not merely a short summary.

## P1 Quality Checks

- The title and reading path make the topic, material type, domain, and downstream artifact clear.
- The brief clearly names the downstream artifact target or states that it was unspecified.
- The brief includes a source map or source note that distinguishes primary source reconstruction from any external supplementation.
- If external web/database scholarship was used, it was requested or approved by the user and is clearly marked.
- If external supplementation was not used, the brief says so briefly in the source notes or references section.
- Open questions, unsupported details, and source gaps are labelled honestly with `--`, `unknown`, or plain-language caveats.
- Downstream artifact recommendations are traceable to the source material.
- The output contains no in-app process logs, OCR ledgers, prompt transcript, hidden checklist, or self-review narration unless the user explicitly asked for an audit.
- Section headings match the user's language and the target artifact.
- Tables, diagrams, or Mermaid blocks reduce cognitive load rather than decorating the brief.
- Reusable content blocks are specific enough to feed a deck, prototype, PM spec, dashboard, decision room, or design brief.
- Mixed-source briefs synthesize across sources instead of stacking mini-summaries.
- Classical, literary, narrative, or canonical materials preserve the source's order, form, rhetoric, imagery, and historical context when relevant.
- Technical, empirical, or policy materials preserve methods, constraints, evidence quality, assumptions, and limitations when relevant.

## Open Design Submission Checks

- `SKILL.md` includes complete English display copy for localized fallback.
- `triggers` are concrete and match realistic user phrasing.
- `od.preview.type` is `markdown` and `od.outputs.primary` points to the produced Markdown file.
- `od.example_prompt` can run end-to-end and produce the declared primary output.
- A high-quality example brief exists under `examples/` or the target Open Design contribution includes an equivalent preview artifact.
- The skill stays in a single self-contained folder.
- No unrelated framework, daemon, package, or locale files are required for the contribution.
