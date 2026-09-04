# Gorilla HIS — Benchmark Improvement Standard v1.1

Status: `HIGHEST DESIGN AUTHORITY IN BENCHMARK MODE`

## 1. Purpose
A benchmark is a **quality floor and comparison instrument**. It is not a source file to rename, skin, or use as the candidate implementation by default.

Core model:
`BENCHMARK → DECOMPOSE → COMPARE → IDENTIFY GAP → PRESERVE STRENGTH → IMPROVE WEAKNESS → DESIGN NEW CANDIDATE → RENDER → PROVE BETTER`

A candidate that is functionally richer but visibly/operationally worse than the benchmark is a Factory failure.

## 2. Trigger
Activate `BENCHMARK IMPROVEMENT MODE` when:
- user says benchmark / compare and improve / เอาจุดดีแล้วทำให้ดีกว่า;
- a Human-approved HTML/mockup/screenshot is supplied as a quality target;
- a Human-approved Gold Standard exists without an explicit exact-copy request.

Explicit `Copy 100% / pixel-match / exactly` activates `EXACT_REFERENCE_REPLICATION_STANDARD.md` instead.

## 3. Benchmark Evidence — READ, ANALYZE, DO NOT BLINDLY CLONE
When benchmark HTML exists, read its HTML/CSS/DOM/JS directly as **executable design evidence**.

Extract at minimum:
- DOM/component hierarchy;
- shell/topbar/navigation geometry;
- viewport/work-surface proportions;
- typography family/size/weight/line-height;
- spacing rhythm/whitespace distribution;
- color/border/radius/shadow grammar;
- tabs/filter/search composition;
- table density/row height/rich-cell hierarchy;
- button/status/affordance grammar;
- interaction placement/progressive disclosure;
- first-viewport information hierarchy.

**HARD RULE:** reading source does not grant permission to use the benchmark source as the candidate implementation.

Prohibited in Benchmark Mode unless explicitly justified:
`Benchmark HTML → copy file → rename → inject/replace business functions → candidate`

That is source cloning, not benchmark improvement.

Source cloning belongs to Exact Replication Mode when the user explicitly requests exact replication.

## 4. Functional Baseline vs Design Benchmark
Keep these authorities separate:

- `Hospital Workflow / validated candidate logic` = Business + Functional Baseline.
- `Human-approved benchmark` = UX/UI Quality Baseline.

Correct synthesis:
`Validated Functional Model → UX Decision Architecture → Benchmark Strength Extraction → New Candidate Composition → Functional Transplant/Preservation → Rendered Comparison`.

Do not let benchmark code replace a stronger validated state machine, transaction model, queue topology, entitlement logic, history, reassessment, or exception handling.

## 5. Three-Layer Benchmark
Compare candidate against benchmark in three layers.

### A. Visual Quality
`shell | typography | density | spacing | hierarchy | table rhythm | controls | colors | borders | radius | shadow | whitespace | first-glance silhouette`

### B. UX Quality
`5-second comprehension | workload visibility | status clarity | next-action clarity | click burden | cognitive load | scanability | affordance clarity | detail-on-demand | error prevention`

### C. Workflow / Function Quality
`workflow coverage | state continuity | ownership/handoff | longitudinal history | reassessment | versioning | entitlement/ledger | exception/recovery | closure | runtime function`

Never win one layer by sacrificing another.

## 6. Workflow-Authored Composition
Candidate composition must derive from:
`Actual Workflow → Work Obligation → Operational Capability → UX Decision Architecture → Work Surface → Interaction Pattern → Composition`.

For every primary workspace define:
`User Goal → Decision Question → Primary Evidence → Attention/Exception → Primary Action → Secondary Action → Detail on Demand`.

The benchmark informs quality and proven interaction grammar; workflow determines what the product must actually be.

## 7. Preserve / Improve / Replace — BEFORE BUILD
Before candidate build, classify each material benchmark characteristic:
- `PRESERVE` — proven strength relevant to this workflow;
- `IMPROVE` — useful but materially improvable;
- `REPLACE` — pattern is weak or inappropriate for the real workflow;
- `N/A` — benchmark characteristic does not apply.

Every `IMPROVE` or `REPLACE` requires a reason tied to a measurable dimension:
workflow fidelity, task speed, scanability, cognitive load, state/next-action clarity, safety, data visibility, accessibility/readability, responsive behavior, or error prevention.

“Cleaner”, “more modern”, “premium”, or designer preference alone is insufficient.

## 8. Anti-Copy / Anti-Skin Gate — HARD GATE
Before render, reviewer must ask:
1. Is candidate structurally just the benchmark with renamed labels/data?
2. Was benchmark DOM/CSS used wholesale without a workflow reason?
3. Were existing validated functions discarded because benchmark lacked them?
4. Is the candidate merely the old mockup with a benchmark-like CSS skin?
5. Can the designer explain the new composition from user work and decision needs?

If 1–4 = Yes or 5 = No:
`FAIL — BENCHMARK METHODOLOGY / SOURCE CLONING`.

## 9. 5-Second Operational Test
For each primary workspace a user should rapidly answer:
1. Where am I / what work is this?
2. What needs attention now?
3. What patient/transaction/task is this?
4. What is the current state/owner?
5. What should I do next?
6. What evidence supports that action?

Recommended first-glance hierarchy:
`Context → Situation/Attention → Evidence/Work → Exception → Next Action → Detail`.

## 10. Work Surface Over Template
Premium HIS is not card count or whitespace volume.

First viewport gives the largest useful area to actual work/evidence. Avoid:
- generic KPI-card grids dominating operational pages;
- wide navigation consuming task space without benefit;
- equal cards for unequal importance;
- card-sprawl;
- detached primary actions;
- decorative containers;
- passive tables with no lifecycle action.

High information density is acceptable when controlled, scannable, and decision-oriented.

## 11. Worklist Benchmark Rule
When the module is queue/worklist driven, first viewport prioritizes:
`Type → Identity → Reason/Service → Source → Priority → Status → Owner → Time/Aging → Progress → Next Action`.

Row = actionable work object, not decorative summary.
Next Action is first-class; users must not infer it from status code.

## 12. Interaction Craft
Use interaction principles operationally:
- Hick: stage choices; reduce simultaneous competing actions;
- Fitts: frequent/important action near affected object and easy to acquire;
- Proximity: evidence and related action stay together;
- Progressive disclosure: secondary detail on demand;
- destructive/corrective action requires deliberate confirmation and traceability where applicable.

State-changing action must visibly mutate state/data/owner/history; Toast-only success is not sufficient.

## 13. First-Viewport No-Regression Gate
At the same viewport compare:
- header/navigation footprint;
- content start position;
- work-surface-to-whitespace ratio;
- useful rows/work visible;
- patient/work identity prominence;
- workload visibility;
- status clarity;
- next-action clarity;
- visual noise;
- whitespace efficiency.

If candidate wastes more viewport, hides more work, or requires more interpretation without material benefit:
`FAIL — BENCHMARK REGRESSION`.

## 14. Before / Benchmark / Candidate Matrix — MANDATORY
Independent reviewer produces:
`Dimension | Benchmark Strength | Candidate Decision | Result | Evidence/Reason`

Minimum dimensions:
1. Shell/navigation
2. Typography/readability
3. Density/whitespace
4. Worklist/table
5. Search/filter/tabs
6. Status/action distinction
7. Primary workflow visibility
8. Interaction/click burden
9. Longitudinal/context evidence
10. Overall visual quality

Result values:
`PRESERVED / IMPROVED / REGRESSED — JUSTIFIED / REGRESSED — FAIL`.

No matrix = Benchmark Gate not executed.

## 15. Rendered Comparison — MANDATORY
Render benchmark and candidate at the same viewport. Compare side-by-side; use overlay/image diff when practical.

Reviewer must answer:
- What was preserved?
- What was improved?
- What became worse?
- Is every regression justified by workflow/safety?
- Would a neutral reviewer choose Candidate over Benchmark for the intended hospital job?

If No:
`FAIL — BENCHMARK NOT EXCEEDED`.

## 16. Human Visual Veto
If the user says the benchmark looks/works better, candidate immediately returns to FAIL regardless of Master compliance, self-score, or Function PASS. Correct the design; do not argue compliance.

## 17. Relationship to Function
Correct objective:
`Benchmark UX/UI Strengths PRESERVED + Validated Factory Workflow/Function PRESERVED + Material Weaknesses IMPROVED`.

Therefore:
`Function PASS + Benchmark Regression = FACTORY FAIL`.
`Visual PASS + Functional Regression = FACTORY FAIL`.
`Source Clone + Rename = BENCHMARK METHODOLOGY FAIL`.

## 18. Gold Promotion
Candidate may become Gold only after:
- Workflow/Function PASS;
- Runtime PASS;
- Anti-Copy/Anti-Skin PASS;
- Benchmark Comparison PASS;
- no unjustified material visual/UX regression;
- Human Visual Review PASS.

## 19. Final Rule
**Benchmark is comparison, not copying. Preserve what already works, understand why it works, retain the stronger functional model, design the candidate around the real hospital job, improve measurable weaknesses, and prove the result is better.**