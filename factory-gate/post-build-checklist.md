# Gorilla HIS — Post-Build Checklist v3.0

Post-Build verifies implementation, business coverage and rendered product craft.

## A. Blueprint Traceability
Create:

| ID / Item | Blueprint requirement | Evidence in index.html | Interaction / State | Result |
|---|---|---|---|---|

- [ ] Main Workflow = PASS
- [ ] Critical Requirement = PASS
- [ ] Missing Blueprint categories are N/A, not invented
- [ ] No critical item marked PARTIAL and still passed

## B. Binding Reuse Verification
Create:

| Pre-Build commitment | Approved source | Evidence in index.html | Actually reused? | Result |
|---|---|---|---|---|

- [ ] central tokens actually used
- [ ] semantic icon mapping actually used
- [ ] relevant approved interaction primitives actually reused
- [ ] any deliberate divergence from Candidate component/layout is documented
- [ ] no false “reuse” claim based only on reading/citing a file

## C. Functional QA
- [ ] Main Workflow click-through works
- [ ] no dead Main Workflow button
- [ ] no workflow-breaking JS error
- [ ] Loading/Empty/Error/Success/Disabled/Validation represented when relevant
- [ ] confirmation for destructive/strategic action when required
- [ ] fictional data only
- [ ] no real external API/data transmission

## D. Decision Architecture Verification
- [ ] Decision Question remains visually answerable within first ~5 seconds
- [ ] Primary Evidence is dominant enough
- [ ] Exception is attached to relevant evidence
- [ ] Primary Action is visible at decision point
- [ ] Secondary Evidence does not compete with the main story

## E. Product Feeling Verification
Compare rendered output against Pre-Build intent.

- [ ] intended qualities are visible
- [ ] prohibited feelings are absent
- [ ] page feels authored as one product surface
- [ ] shell/chrome does not dominate the work

## F. Surface / Depth Verification
- [ ] Canvas vs Work Surface is intentional where appropriate
- [ ] Instrument/Elevated surfaces are used only for meaningful objects
- [ ] page is not flat white + hairlines everywhere
- [ ] page is not Card Everywhere
- [ ] shadows correspond to real elevation/interactivity
- [ ] radius communicates object type rather than being uniformly applied

## G. Typography / Instrument Verification
- [ ] typography creates hierarchy before containers do
- [ ] values/units/labels/metadata have deliberate scale and weight
- [ ] comparable numbers use aligned/tabular treatment where appropriate
- [ ] threshold/delta/trend/forecast/time context is close to key reading when decision-relevant
- [ ] key operational measures do not look like spreadsheet cells or marketing stat cards

## H. Interaction Craft
- [ ] hover/selected/pressed states are deliberate
- [ ] scenario/task/state changes have visible causal feedback
- [ ] motion is restrained and functional
- [ ] reduced-motion is respected when motion is material
- [ ] no decorative perpetual animation

## I. Anti-Template Test
Answer PASS/FAIL:
1. Could labels be swapped to CRM/fintech/logistics and still look plausible?
2. Is the page mainly repeated rounded rectangles?
3. Are proportions dictated by an easy grid rather than information importance?
4. Does hierarchy collapse in grayscale?
5. Is AI visually themed separately?

Any clear YES to 1/2/3/5 or YES to 4 = FAIL Design.

## J. Dryness / Barren Test
Answer PASS/FAIL:
- Does the page feel sterile, bureaucratic, unfinished or like a styled spreadsheet?
- Did “minimal” remove visual richness, instrument quality or control feel?
- Are borders doing all hierarchy work?
- Are important areas visually dead despite rich operational meaning?

Material YES = FAIL Premium Craft.

## K. BMW Test
Question:
**What makes this screen materially more designed than another HIS with the same functions?**

Evidence must include at least two beyond color/logo/icons, e.g. proportion, surface craft, instrumentation, visualization, control feel, causal motion, micro-detail.

No meaningful evidence = FAIL Premium Craft.

## L. iPhone Test
- [ ] refined when decoration is reduced
- [ ] depth improves hierarchy rather than ornament
- [ ] controls feel deliberate
- [ ] visual complexity is reduced without removing useful information

## M. Premium HIS Visual Gate
Run `factory-gate/premium-his-visual-gate.md` VG-01..VG-15.

If rendered inspection is impossible, record:
`VISUAL REVIEW LIMITATION — Premium status cannot be self-certified.`

## N. Builder Status
Allowed output status:
- `FAIL — Return to Builder`
- `Candidate — Ready for Independent QA`
- `Candidate — Ready for Human Visual Review`

Forbidden self-status:
- Premium
- World-class
- Gold Standard

Those require Human Design Approval / explicit promotion.
