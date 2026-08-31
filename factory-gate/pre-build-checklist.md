# Gorilla HIS — Pre-Build Checklist v3.1

Pre-Build must PASS before coding.

For `PROTOTYPE READY`, use the **FAST PRE-BUILD** format below. Keep it concise and move detailed evidence to Post-Build.

## A. Source of Truth
- [ ] Application Blueprint read completely
- [ ] `AI_INSTRUCTIONS.md` read
- [ ] `factory-gate/FACTORY_GATE.md` read
- [ ] `design-system/VISUAL_DNA.md` read
- [ ] `design-system/LEGACY_DNA.md` read
- [ ] `design-system/design-rules.md` read
- [ ] `design-system/ux-rules.md` read
- [ ] `design-system/tokens.css` read
- [ ] `design-system/icon-rules.md` read
- [ ] relevant components/patterns reviewed
- [ ] relevant Gold Standard reviewed, or `N/A`
- [ ] relevant real Gorilla HIS screenshots reviewed, or limitation declared

Missing mandatory authority source = FAIL.

## B. Blueprint Boundary
State only:
- Blueprint Status
- Objective
- Main Workflow
- Critical safety/data boundary
- Working Assumption/TBD treatment that affects the prototype

Do not expand into long traceability before coding.

## C. Legacy DNA Scan
Create concise Preserve / Improve / Replace decisions.

At minimum inspect when relevant:
- shell/navigation
- patient context/header
- tabs
- worklist/table density
- form/control language
- action placement
- alert/status treatment

If no relevant real screenshot exists, declare limitation.

If the planned screen would look like a different product family = FAIL.

## D. Decision Architecture
- [ ] Decision Question
- [ ] Primary Evidence
- [ ] Exception
- [ ] Primary Action
- [ ] Secondary Evidence

If the first 5-second decision cannot be stated = FAIL.

## E. Visual Concept Signature
Answer in one paragraph:

**What makes this screen unmistakably Gorilla HIS and materially better to operate than the current generation?**

Must include:
- continuity;
- workflow-specific authored idea;
- concrete operating improvement.

Only “clean/modern/premium/blue/rounded” = FAIL.

## F. Binding Reuse Contract
For relevant roles record source path + actual planned use.

| Role | Source | Planned actual reuse | Status |
|---|---|---|---|
| Visual DNA | `design-system/VISUAL_DNA.md` | | |
| Legacy DNA | `design-system/LEGACY_DNA.md` + screenshots | | |
| Tokens | `design-system/tokens.css` | | |
| Icons | `design-system/icon-rules.md` | | |
| Shell continuity | approved shell / screenshot when suitable | | |
| Controls/Forms/Modal | relevant component(s) | | |
| Workflow pattern | relevant pattern(s) | | |
| Gold Standard | relevant approved artifact / N/A | | |

Rules:
- `Read/Reference ≠ Reuse`.
- Do not force irrelevant KPI/Operational components.
- `premium-operational-layout.html` is deprecated and not mandatory.

## G. Anti-Template + Continuity Risks
State only the top two risks and mitigation.

Typical risks:
- generic SaaS/LMS/admin composition;
- clean-sheet redesign that loses Gorilla HIS continuity;
- barren spreadsheet;
- card dashboard.

## H. Result

`PASS / FAIL`

For `PROTOTYPE READY`:

`PASS → begin index.html immediately.`

Do not produce additional long pre-code documents unless a critical risk requires them.