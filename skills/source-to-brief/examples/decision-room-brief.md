# Design Intelligence Brief: Compliance Banner Decision

Reading path: synthetic policy excerpt + synthetic design memo -> compliance tradeoff -> decision-room

## 1. Decision Context

Support a decision room choosing between a persistent disclosure banner, a contextual consent step, or a settings-first approach.

## 2. Source Inventory

| Source | Role | Reliability Notes |
|---|---|---|
| Synthetic policy excerpt | Constraint evidence | Synthetic example; not legal advice |
| Synthetic design memo | Product options and tradeoffs | Synthetic example; stakeholder evidence |

## 3. Problem Frame

The product needs to disclose data use clearly without adding unnecessary friction to routine workflows.

## 4. Evidence-Backed Insights

| Insight | Evidence | Confidence | Design / Product Implication | Source Gap |
|---|---|---|---|---|
| Disclosure must occur before the affected action. | Synthetic policy excerpt states notice must precede collection. | High | Any option must show notice before data capture. | Real jurisdiction not supplied. |
| Persistent banner is visible but may be noisy. | Design memo lists visibility as benefit and fatigue as risk. | Medium | Treat banner as safe but potentially high-friction. | No usability test supplied. |
| Contextual consent aligns with action timing. | Design memo maps notice to the affected action. | Medium | Consider contextual consent as leading option. | Legal review not supplied. |

## 5. Opportunity Areas

- Contextual disclosure at the moment of affected action.
- Settings page for durable review.
- Decision criteria that balance compliance visibility and workflow friction.

## 6. Artifact Translation

Decision room:

- Competing options: persistent banner, contextual consent step, settings-first disclosure.
- Decision criteria: policy fit, user comprehension, workflow friction, implementation effort.
- Tradeoffs: banner maximizes visibility; contextual consent fits timing; settings-first is low friction but may be insufficient.
- Risks: compliance interpretation is synthetic; no legal review or user testing supplied.
- Unresolved questions: what exact policy jurisdiction applies; what data event triggers notice.
- Recommended next decision: shortlist contextual consent plus settings review, pending legal review.

## 7. Assumptions, Risks, And Unknowns

- Assumption: contextual consent satisfies the timing requirement.
- Risk: settings-first approach may fail the notice-before-action requirement.
- Unknown: exact regulatory language and product data flow.

## 8. Reusable Blocks

- Decision criterion: Notice must be visible before the affected data action.
- Option framing: Contextual consent may reduce global UI noise while preserving action-level disclosure.
- Open question: Which data collection event triggers the notice requirement?

## 9. Source Notes

This example uses synthetic supplied sources only. No external supplementation was used.
