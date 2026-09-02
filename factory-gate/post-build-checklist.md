# Gorilla HIS — Post-Build Checklist v3.2

Post-Build verifies implementation, business coverage, product continuity, hospital-facing realism, role/handoff clarity and rendered craft.

## A. Blueprint Traceability
Create:

| ID / Item | Blueprint requirement | Evidence in index.html | Interaction / State | Result |
|---|---|---|---|---|

- [ ] Main Workflow = PASS
- [ ] Critical Requirement = PASS
- [ ] Missing Blueprint categories are N/A, not invented
- [ ] no critical item marked PARTIAL and still passed

## B. Binding Reuse Verification
Create:

| Pre-Build commitment | Approved source | Evidence in index.html | Actually reused? | Result |
|---|---|---|---|---|

- [ ] central tokens actually used
- [ ] semantic icon mapping actually used
- [ ] relevant approved interaction primitives actually reused
- [ ] deliberate divergence documented
- [ ] no false reuse claim based only on reading/citing a file

## C. Legacy Continuity Verification
Create:

| Legacy element | Preserve / Improve / Replace | Evidence in rendered UI | Continuity result |
|---|---|---|---|

Verify:
- [ ] shell/navigation still belongs to Gorilla HIS
- [ ] patient/task context follows familiar HIS grammar where relevant
- [ ] tabs/worklist/forms/actions retain recognizable product behavior
- [ ] density remains appropriate for real hospital work
- [ ] modernization is evolution, not an unrelated redesign

If recognizable continuity depends only on logo/color = FAIL.

## D. Functional QA
- [ ] Main Workflow click-through works end-to-end
- [ ] no dead primary navigation/menu
- [ ] no dead Main Workflow tab
- [ ] no dead Main Workflow button
- [ ] material actions update visible state/data where expected
- [ ] modal/drawer open/close/confirm/cancel works
- [ ] search/filter works when present
- [ ] no workflow-breaking JS error
- [ ] relevant Loading/Empty/Error/Success/Disabled/Validation states represented
- [ ] confirmation for important action when required
- [ ] fictional data only
- [ ] no real external API/data transmission

### D.1 Mandatory Interaction Inventory
Create:

| Control ID / Label | Type | Screen / Role | Expected Behavior | Observable Result | Test Result |
|---|---|---|---|---|---|

Every visible primary menu and every Main Workflow control must appear.

### D.2 Mandatory Functional Smoke Test — Runtime Required
Run the actual mockup and record evidence:
- [ ] click every primary navigation item at least once
- [ ] click every Main Workflow tab at least once
- [ ] open and close every modal/drawer family at least once
- [ ] execute at least one valid save/add/update action for each major workflow stage
- [ ] verify at least one validation/permission/error path when relevant
- [ ] verify visible state/data change after material actions
- [ ] verify search/filter when present
- [ ] verify context/back preservation when workflow depends on it
- [ ] console errors = 0 for the Main Workflow run

If browser/runtime execution is blocked, record the limitation. **Do not claim Functional Smoke Test PASS.**

Dead primary menu/tab/action = HARD FAIL.

## E. Role / Handoff / Swimlane Verification
When the workflow contains 3+ meaningful roles or repeated cross-role handoffs:
- [ ] Role-Based Swimlane exists or is directly accessible
- [ ] one lane per meaningful hospital role/team
- [ ] steps are chronological
- [ ] handoffs visibly cross lane boundaries
- [ ] current ownership / next action is understandable
- [ ] lane labels match actual permission/action ownership
- [ ] exception/return path represented when materially relevant
- [ ] Swimlane is workflow communication, not decorative BPMN

If an action appears under one role in the Swimlane but is executable by a conflicting role without rationale = FAIL.

## F. Reference Benchmark Delta
When the user supplied an existing mockup/reference, create:

| Dimension | Reference Baseline | New Candidate | Better / Same / Worse | Evidence |
|---|---|---|---|---|

At minimum compare:
- workflow clarity
- interaction completeness
- decision hierarchy
- component/control finish
- information density/scanability
- role/handoff visibility
- product continuity
- hospital-facing realism

Any `Worse` result in Main Workflow interaction, role clarity or hospital-facing realism = RETURN TO BUILDER.

## G. Hospital-Facing Realism
- [ ] normal product surfaces do not expose `Demo`, `Discovery Mockup`, `Prototype`, `WA`, `GAP`, `TBD`, `CR`, `HSR`, `AI-generated` or internal QA text unless explicitly requested
- [ ] unresolved production rules are expressed with realistic product states/disabled/validation language when they must be visible
- [ ] governance classification remains preserved in Blueprint/Gap/Design Notes/Post-Build
- [ ] labels, data and interactions read like a hospital application rather than a Factory test harness

## H. Decision Architecture Verification
- [ ] Decision Question answerable within ~5 seconds
- [ ] Primary Evidence dominant enough
- [ ] Exception attached to relevant evidence
- [ ] Primary Action visible at decision point
- [ ] Secondary Evidence does not compete with main story

## I. Visual Concept Verification
Restate the Pre-Build Visual Concept Signature and verify:
- [ ] recognizable Gorilla continuity is visible
- [ ] workflow-specific authored idea is visible
- [ ] concrete operating improvement is visible
- [ ] result is materially better than simply restyling the legacy/reference page

## J. Product Feeling Verification
- [ ] intended qualities are visible
- [ ] prohibited feelings absent
- [ ] page feels authored as one product surface
- [ ] shell/chrome does not dominate work
- [ ] page does not feel like generic AI/SaaS output

## K. Surface / Typography / Instrument Verification
- [ ] Canvas vs Work Surface intentional
- [ ] elevated/instrument surfaces meaningful
- [ ] not flat white + hairlines everywhere
- [ ] not Card Everywhere
- [ ] typography creates hierarchy before containers
- [ ] values/units/metadata use deliberate hierarchy
- [ ] controls have deliberate feel

## L. Interaction Craft
- [ ] hover/selected/pressed/focus deliberate
- [ ] workflow changes have visible causal feedback
- [ ] state change feedback is attached to the changed object where practical
- [ ] motion restrained and functional
- [ ] no decorative perpetual animation
- [ ] no material action represented only by a generic toast when visible state should change

## M. Anti-Template Test
FAIL when the page could plausibly become CRM/fintech/LMS/logistics/admin after label swaps, or when it is mainly repeated rounded rectangles/easy grids.

## N. Dryness / Barren Test
FAIL when the screen feels sterile, bureaucratic, unfinished, or like a styled spreadsheet because minimalism removed product richness/control feel.

## O. BMW Evolution Test
Answer:
1. What Gorilla HIS DNA is preserved?
2. What legacy/reference friction was improved?
3. What crafted detail makes the screen better to operate?
4. Would an existing Gorilla user know where they are and what to do?
5. What is materially better than the supplied reference candidate, when one exists?

Weak answer to 1 or 4 = FAIL continuity.
Only color/logo/radius/shadow/icon evidence = FAIL craft.

## P. iPhone Test
- [ ] refined when decoration is reduced
- [ ] depth improves hierarchy rather than ornament
- [ ] controls feel deliberate
- [ ] visual complexity reduced without removing useful information

## Q. Review Usability Test
- [ ] `START_HERE.md` exists
- [ ] Purpose stated
- [ ] Review Role(s) stated
- [ ] first click stated
- [ ] Main Review Flow is 4–8 clear steps
- [ ] expected result stated for critical actions
- [ ] clickable controls listed
- [ ] Working Assumption / TBD treatment documented outside normal product UI
- [ ] non-developer reviewer can operate the prototype without guessing

Missing guide or unclear journey = UX FAIL.

## R. Premium HIS Visual Gate
Run `factory-gate/premium-his-visual-gate.md` plus current Master additions:
- Legacy Continuity
- Review Usability
- Interaction Completeness
- Hospital-Facing Realism
- Reference Benchmark Delta when applicable
- Role Swimlane/Handoff clarity when applicable

If rendered inspection is impossible, record:
`VISUAL REVIEW LIMITATION — Premium status cannot be self-certified.`

## S. Builder Status
Allowed:
- `FAIL — Return to Builder`
- `Candidate — Ready for Independent QA`
- `Candidate — Ready for Human Visual Review`

Forbidden self-status:
- Premium
- World-class
- Gold Standard
