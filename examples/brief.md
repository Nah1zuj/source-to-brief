# Research Brief: AI Meeting Notes For Product Teams

Reading path: product research packet; AI collaboration workflow; downstream artifact: product strategy deck; decision focus: whether to prototype an AI meeting-note assistant for small product teams.

## 1. Executive Orientation

The source packet argues that small product teams lose decision context after meetings because notes are fragmented across transcripts, chat threads, task tools, and personal documents. The strongest opportunity is not "automatic transcription" by itself, but a workflow that turns meeting material into decisions, owners, risks, and follow-up prompts that product teams can reuse.

The material supports a product strategy deck or PM spec more strongly than a high-fidelity prototype. It contains clear pain points, user roles, workflow requirements, and adoption risks, but it does not yet include enough interaction detail to specify final screens.

Next artifact fit: deck, then PM spec.

## 2. Source Map

| Source | Role In Brief | Reusable Claims | Gaps |
| --- | --- | --- | --- |
| User interview notes | Primary user pain evidence | Meetings create action items, but rationale is often lost | Sample size unknown |
| Internal workflow memo | Operational context | Teams already use Slack, Linear, and shared docs | No integration priority ranking |
| Competitive scan | Market framing | Existing tools emphasize recording and summaries | Pricing and retention data missing |

External supplementation: not used.

## 3. Core Claims And Evidence

### Claim A: The durable pain is decision memory, not raw note capture

The interviews repeatedly describe the same failure pattern: a meeting ends with apparent alignment, but later teammates disagree about why a decision was made, what tradeoffs were accepted, or who owns the next step. This suggests the product should optimize for retrievable decision context.

### Claim B: Summaries must become operational artifacts

The workflow memo shows that teams do not want another note destination. They want notes that move into existing systems. The brief should therefore treat Slack, Linear, and shared docs as output surfaces rather than optional integrations.

### Claim C: Trust depends on source traceability

The competitive scan implies that generic summaries are easy to produce and hard to trust. The product should expose the source moment behind important decisions, risks, and assigned actions. Unsupported details should be shown as `unknown` instead of being guessed.

## 4. Product Implications

| Product Area | Implication | Evidence Strength |
| --- | --- | --- |
| Core workflow | Generate decisions, owners, risks, and follow-ups after a meeting | Strong |
| Collaboration | Push outputs to existing team tools | Medium |
| Trust | Link generated claims to transcript moments or source notes | Strong |
| Admin | Let teams define what counts as a decision or action item | Medium |

## 5. Tensions, Unknowns, And Risks

- Teams may reject a new note surface even if they like the summary quality.
- The source packet does not prove willingness to pay.
- Privacy and recording consent are likely adoption blockers, but the supplied material does not quantify them.
- Accuracy expectations differ across decisions, tasks, and informal summaries.

## 6. Downstream Artifact Recommendations

For a product strategy deck:

- Frame the problem as lost decision memory.
- Show the current workflow split across meeting transcripts, chat, tasks, and docs.
- Position the product as a decision-context layer rather than a transcription tool.
- Use source traceability as the trust differentiator.

For a PM spec:

- Define required outputs: decision log, action items, risk list, open questions, and source links.
- Define non-goals: live meeting assistant, calendar scheduling, and generic knowledge base search.
- Require an `unknown` state for unsupported details.

For a prototype:

- Start with post-meeting review, not live capture.
- Prototype the flow from transcript to decision log to Linear/Slack export.

## 7. Reusable Content Blocks

Problem statement candidate:

> Product teams do not just lose notes; they lose the reasoning behind decisions.

Positioning line:

> A meeting-note assistant that turns conversations into traceable decisions, owners, and follow-ups.

Deck slide candidates:

- "The real meeting problem is decision memory"
- "Summaries are not enough unless they become workflow objects"
- "Trust comes from source-linked claims"

## 8. References And Source Notes

This brief is based only on the provided source packet. No external web or database research was added.

