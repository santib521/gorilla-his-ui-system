# Gorilla HIS — Pre-Build Checklist v3.0

Pre-Build must PASS before coding.

## A. Source of Truth
- [ ] Application Blueprint read completely
- [ ] `AI_INSTRUCTIONS.md` read
- [ ] `factory-gate/FACTORY_GATE.md` read
- [ ] `design-system/VISUAL_DNA.md` read
- [ ] `design-system/design-rules.md` read
- [ ] `design-system/ux-rules.md` read
- [ ] `design-system/tokens.css` read
- [ ] `design-system/icon-rules.md` read
- [ ] relevant components/patterns reviewed
- [ ] relevant Gold Standard reviewed, or `N/A — none available`
- [ ] screenshot availability/limitation declared

Missing mandatory authority source = FAIL.

## B. Blueprint Understanding
- [ ] Objective stated from Blueprint only
- [ ] Users/Roles stated from Blueprint only
- [ ] Main Workflow stated
- [ ] Critical Requirements stated
- [ ] Unknown/missing item marked N/A/Question instead of invented

## C. Decision Architecture
- [ ] Decision Question
- [ ] Primary Evidence
- [ ] Exception
- [ ] Primary Action
- [ ] Secondary Evidence

If the first 5-second decision cannot be stated = FAIL / clarify before coding.

## D. Product Feeling Intent
- [ ] 3–5 intended product qualities declared
- [ ] prohibited feelings declared
- [ ] intended qualities are not only styling words such as “blue / rounded / shadow”

Example:
`precision / calm / responsive / crafted / confident`

Must not feel like:
`admin template / barren spreadsheet / AI showcase / consumer toy`

## E. Binding Reuse Contract
For every relevant role record **source path + actual planned use**.

| Role | Source | Planned actual reuse | Status |
|---|---|---|---|
| Visual DNA | `design-system/VISUAL_DNA.md` | | |
| Tokens | `design-system/tokens.css` | | |
| Icons | `design-system/icon-rules.md` | | |
| Shell continuity | `design-system/components/application-shell.html` when suitable | | |
| Controls/Forms/Modal | relevant component(s) | | |
| Workflow pattern | relevant pattern(s) | | |
| Gold Standard | relevant approved artifact / N/A | | |

Rules:
- `Read/Reference ≠ Reuse`.
- Reuse behavior/product continuity when fit is real.
- Do not mechanically copy a Candidate layout if it creates generic or barren composition.
- `premium-operational-layout.html` is deprecated and is not a mandatory source.

## F. Composition Intent
- [ ] authored path stated as `Situation → Evidence → Exception → Action → Detail`
- [ ] composition rationale is based on information importance, not easy grid structure
- [ ] unequal information is allowed unequal visual proportion
- [ ] page does not begin with “3/4/5 cards” as the architecture

## G. Premium Craft Plan
- [ ] Surface Architecture planned: Canvas / Work / Instrument / Elevated / Semantic
- [ ] Typography hierarchy planned
- [ ] numerical/instrument hierarchy planned
- [ ] data visualization decision stated when relevant
- [ ] depth/light strategy stated
- [ ] color strategy stated
- [ ] hover/selected/pressed behavior stated
- [ ] causal motion stated when state transition matters
- [ ] specific crafted detail stated beyond default component assembly

If the plan is only “clean/minimal/modern” = FAIL.

## H. Anti-Template Risk
- [ ] top two generic-template risks stated
- [ ] mitigation stated
- [ ] page would remain purpose-built if brand color/logo were hidden

## I. Dryness / Barren Risk
- [ ] identifies where over-minimalism could make the page sterile
- [ ] explains how surface, type, instrumentation or interaction will retain richness
- [ ] solution does not rely on decorative gradients/shadows/cards

## J. Command Center / Operational Intelligence — when applicable
- [ ] current operating state can be communicated
- [ ] trajectory / time-to-threshold strategy exists
- [ ] bottleneck/exception is visually attached to evidence
- [ ] intervention + projected impact are planned
- [ ] key measures will behave as instruments rather than spreadsheet KPI cells
- [ ] operational visualization selected because it answers the decision question
- [ ] no fixed 2/3 + 1/3 template is being forced without evidence-based reason

## RESULT

`PASS / FAIL`

If FAIL, STOP before coding and state missing/failed items.
