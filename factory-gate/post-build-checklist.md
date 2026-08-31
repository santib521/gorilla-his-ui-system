# Gorilla HIS — Post-Build Checklist v3.1

Post-Build verifies implementation, business coverage, product continuity, demo usability and rendered craft.

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
- [ ] Main Workflow click-through works
- [ ] no dead Main Workflow button
- [ ] no workflow-breaking JS error
- [ ] relevant Loading/Empty/Error/Success/Disabled/Validation states represented
- [ ] confirmation for important action when required
- [ ] fictional data only
- [ ] no real external API/data transmission

## E. Decision Architecture Verification
- [ ] Decision Question answerable within ~5 seconds
- [ ] Primary Evidence dominant enough
- [ ] Exception attached to relevant evidence
- [ ] Primary Action visible at decision point
- [ ] Secondary Evidence does not compete with main story

## F. Visual Concept Verification
Restate the Pre-Build Visual Concept Signature and verify:
- [ ] recognizable Gorilla continuity is visible
- [ ] workflow-specific authored idea is visible
- [ ] concrete operating improvement is visible
- [ ] result is materially better than simply restyling the legacy page

## G. Product Feeling Verification
- [ ] intended qualities are visible
- [ ] prohibited feelings absent
- [ ] page feels authored as one product surface
- [ ] shell/chrome does not dominate work

## H. Surface / Typography / Instrument Verification
- [ ] Canvas vs Work Surface intentional
- [ ] elevated/instrument surfaces meaningful
- [ ] not flat white + hairlines everywhere
- [ ] not Card Everywhere
- [ ] typography creates hierarchy before containers
- [ ] values/units/metadata use deliberate hierarchy
- [ ] controls have deliberate feel

## I. Interaction Craft
- [ ] hover/selected/pressed/focus deliberate
- [ ] workflow changes have visible causal feedback
- [ ] motion restrained and functional
- [ ] no decorative perpetual animation

## J. Anti-Template Test
FAIL when the page could plausibly become CRM/fintech/LMS/logistics/admin after label swaps, or when it is mainly repeated rounded rectangles/easy grids.

## K. Dryness / Barren Test
FAIL when the screen feels sterile, bureaucratic, unfinished, or like a styled spreadsheet because minimalism removed product richness/control feel.

## L. BMW Evolution Test
Answer:
1. What Gorilla HIS DNA is preserved?
2. What legacy friction was improved?
3. What crafted detail makes the screen better to operate?
4. Would an existing Gorilla user know where they are and what to do?

Weak answer to 1 or 4 = FAIL continuity.
Only color/logo/radius/shadow/icon evidence = FAIL craft.

## M. iPhone Test
- [ ] refined when decoration is reduced
- [ ] depth improves hierarchy rather than ornament
- [ ] controls feel deliberate
- [ ] visual complexity reduced without removing useful information

## N. Demo Usability Test
- [ ] `START_HERE.md` exists
- [ ] Purpose stated
- [ ] Demo Role(s) stated
- [ ] first click stated
- [ ] Main Demo Flow is 4–8 clear steps
- [ ] expected result stated for critical actions
- [ ] clickable controls listed
- [ ] Working Assumption / TBD treatment visible
- [ ] non-developer reviewer can play the prototype without guessing
- [ ] optional in-product Demo Guide exists when practical

Missing guide or unclear journey = UX FAIL.

## O. Premium HIS Visual Gate
Run `factory-gate/premium-his-visual-gate.md` plus current Master additions:
- VG-16 Legacy Continuity
- VG-17 Demo Usability

If rendered inspection is impossible, record:
`VISUAL REVIEW LIMITATION — Premium status cannot be self-certified.`

## P. Builder Status
Allowed:
- `FAIL — Return to Builder`
- `Candidate — Ready for Independent QA`
- `Candidate — Ready for Human Visual Review`

Forbidden self-status:
- Premium
- World-class
- Gold Standard
