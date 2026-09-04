# Gorilla HIS — Exact Reference Replication Standard v1.0

Status: `HIGHEST DESIGN AUTHORITY WHEN USER REQUESTS EXACT/COPY 100%`

## 1. Trigger
Activate **EXACT REPLICATION MODE** when the user says or clearly means:
- Copy 100%
- เหมือนแบบนี้เลย
- เอาหน้าตาตามนี้
- replicate exactly / pixel-match / same UI
- or explicitly identifies a Human-approved HTML/screenshot as the UI to reproduce.

When active, this standard overrides Visual DNA defaults, generic Gorilla shell rules, Design Freedom, benchmark adaptation, and any instruction to improve/exceed/reinterpret the supplied visual.

## 2. Core Rule
**Do not redesign the reference. Reproduce it.**

The reference owns:
`DOM/layout geometry → shell → topbar → rail/sidebar → typography → font scale → spacing → colors → borders → radius → shadow → tabs → filters → table rhythm → row height → buttons → badges → icons → alignment → whitespace → responsive behavior`.

Hospital workflow/business truth owns the data, labels, states, actions and functional behavior placed inside that visual system.

## 3. Build Strategy — HARD RULE
When source HTML is available:
1. Start from the approved reference HTML/CSS/DOM.
2. Preserve its visual classes, layout structure and tokens as far as possible.
3. Transplant/adapt business data and JavaScript behavior **into the reference structure**.
4. Do **not** start from an older module mockup and add CSS overrides hoping to make it look like the reference.
5. Do not retain legacy shell/layout CSS that fights the reference.

When only screenshot is available:
1. reconstruct visual geometry first;
2. render;
3. compare side-by-side;
4. correct measurable differences before adding deep workflow behavior.

## 4. No Creative Substitution
In Exact Replication Mode the designer may not independently change:
- wide sidebar ↔ icon rail;
- topbar composition;
- page title placement;
- card count/proportion;
- work-surface width;
- tab treatment;
- table header/body density;
- primary action color/shape;
- status chip grammar;
- typography family/size/weight hierarchy;
- major spacing/radius/shadow;
- information grouping visible in the approved reference.

A change is allowed only when required by workflow/safety or explicitly requested by the user. Document the exception.

## 5. Functional Grafting Rule
Visual replication must not delete required workflow. Add functions by using the reference's own visual grammar:
- new workflow state → existing badge/status grammar;
- new action → existing button hierarchy;
- new queue → existing tab/filter/list grammar;
- deep professional work → reference modal/drawer/workspace grammar;
- extra evidence → progressive disclosure before changing first-viewport composition.

## 6. Reference Freeze
Before coding, create a `REFERENCE FREEZE` note containing:
- reference file/image identity;
- viewport used for comparison;
- shell dimensions;
- major region bounding boxes/proportions;
- font family and key sizes if source HTML exists;
- primary/secondary colors;
- row height/table density;
- button/status/tab treatment.

These values are frozen until Human Review changes them.

## 7. Visual Diff Gate — MANDATORY
Render the candidate at the same viewport as the reference and compare side-by-side or by image diff.

Check at minimum:
1. shell/topbar/rail geometry;
2. main work-surface position and width;
3. page title/context position;
4. tabs/attention strip/command bar position;
5. table header and row heights;
6. typography family, size, weight and line-height;
7. button/badge dimensions and colors;
8. border/radius/shadow;
9. whitespace distribution;
10. overall first-glance silhouette.

If a normal reviewer can immediately tell that the candidate is a different design, result is:
`FAIL — EXACT REFERENCE REPLICATION`.

Functional PASS cannot override this failure.

## 8. Pixel Similarity Principle
"Copy 100%" means **visual fidelity first, adaptation second**. Exact pixel identity may be limited by browser/font rendering, but the Factory must aim for the closest reproducible result and must not knowingly introduce design differences.

Do not claim `100% MATCH` unless rendered comparison supports it.

## 9. Conflict Resolution
Priority in Exact Replication Mode:
1. Hospital Business Truth / Safety
2. User's explicit exact-reference instruction
3. This Exact Reference Replication Standard
4. Human-approved reference HTML/screenshot
5. Module workflow/function requirements
6. Other Gorilla Visual/UX Masters
7. Designer preference

Other Masters may add behavior but may not restyle the approved reference.

## 10. Failure Pattern Prohibited
The following pattern is explicitly prohibited:
`Old Mockup → append CSS overrides → declare it now follows the reference`.

Correct pattern:
`Approved Reference → preserve visual skeleton → graft validated workflow/function → render → visual diff → fix → runtime test`.

## 11. Final Gate
For exact-reference work:
`Business Truth PASS + Function PASS + Runtime PASS + EXACT REPLICATION PASS → Candidate for Human Review`.

If Exact Replication fails, the artifact is not ready regardless of workflow completeness.