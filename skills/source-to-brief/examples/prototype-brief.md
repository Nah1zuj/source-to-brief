# Design Intelligence Brief: Onboarding Recovery Flow

Reading path: synthetic interviews + synthetic support notes -> onboarding decision -> prototype

## 1. Decision Context

Support a clickable prototype for users who abandon onboarding after connecting their first data source.

## 2. Source Inventory

| Source | Role | Reliability Notes |
|---|---|---|
| Synthetic interview notes from 5 admins | User evidence | Synthetic example; small sample |
| Synthetic support-note cluster | Behavioral friction signal | Synthetic example; issue frequency not quantified |

## 3. Problem Frame

Admins appear to stall when the product asks for permissions without explaining what happens next or how long setup will take.

## 4. Evidence-Backed Insights

| Insight | Evidence | Confidence | Design / Product Implication | Source Gap |
|---|---|---|---|---|
| Permission anxiety is a repeated blocker. | 4 of 5 synthetic interviews mention uncertainty about access scope. | Medium | Add permission preview and plain-language explanation. | No security review supplied. |
| Users need recovery, not only prevention. | Support notes include repeated "stuck after connect" cases. | Medium | Prototype a resumable setup state. | No event funnel supplied. |
| Time estimate may reduce anxiety. | Two interview notes ask "how long will this take?" | Low | Test a setup duration cue. | Not repeated enough for strong conclusion. |

## 5. Opportunity Areas

- Permission preview before connection.
- Post-connect checklist with current state.
- Recovery screen for incomplete setup.
- Testable setup-time expectation.

## 6. Artifact Translation

Prototype:

- Target user: workspace admin connecting a first data source.
- Scenario: user pauses after permission prompt and returns later.
- Core flow: start setup -> review permissions -> connect source -> see progress -> recover incomplete setup.
- Required screens/states: permission preview, connection progress, paused setup, recovery checklist, success state.
- Interaction requirements: clear resume action, visible next step, reversible permission explanation.
- Testable assumptions: clearer permission language reduces abandonment; recovery checklist increases completion.

## 7. Assumptions, Risks, And Unknowns

- Assumption: permission anxiety is a primary abandonment driver.
- Risk: technical connection failures may be more important than UX clarity.
- Unknown: exact abandonment step and completion rate were not supplied.

## 8. Reusable Blocks

- User need statement: As an admin, I need to understand what access I am granting before I continue setup.
- Prototype prompt: Design a recovery screen that shows connection status, next step, and a safe way to resume.
- Product requirement: The setup flow should preserve incomplete progress and expose a resume action.

## 9. Source Notes

This example uses synthetic supplied sources only. No external supplementation was used.
