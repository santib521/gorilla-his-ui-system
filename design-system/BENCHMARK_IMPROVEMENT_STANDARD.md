# Gorilla HIS — Benchmark Improvement Standard v1.0

Status: `HIGHEST DESIGN AUTHORITY IN BENCHMARK MODE`

## 1. Purpose
A benchmark is not decoration, inspiration, or permission to create a merely different design. It is the **quality floor that the candidate must preserve and then improve**.

Core model:
`BENCHMARK → DECOMPOSE → COMPARE → IDENTIFY GAP → PRESERVE STRENGTH → IMPROVE WEAKNESS → RENDER → PROVE BETTER`

A candidate that is functionally richer but visibly/operationally worse than the benchmark is a Factory failure.

## 2. Trigger
Activate `BENCHMARK IMPROVEMENT MODE` when:
- the user says benchmark / เปรียบเทียบแล้วทำให้ดีกว่า / เอาจุดดีของแบบนี้ / ทำให้ดีกว่า reference;
- a Human-approved HTML/mockup/screenshot is supplied as the quality target;
- a Human-approved Gold Standard exists and the user has not explicitly requested Exact Copy Mode.

If user explicitly says Copy 100% / pixel-match / exactly, use `EXACT_REFERENCE_REPLICATION_STANDARD.md` instead.

## 3. Benchmark Is Executable Evidence
When benchmark HTML exists, **read the source HTML/CSS/DOM/JS directly**. Do not reduce it first to prose rules and then design from memory.

Extract at minimum:
- DOM/component hierarchy;
- shell/topbar/navigation geometry;
- viewport and work-surface proportions;
- typography family/size/weight/line-height;
- spacing rhythm and whitespace distribution;
- color/border/radius/shadow tokens;
- tabs/filter/search composition;
- table columns, density, row height and rich-cell hierarchy;
- button/status/affordance grammar;
- interaction placement and progressive disclosure;
- first-viewport information hierarchy.

Screenshot is visual evidence. HTML is executable design evidence. When both exist, use both.

## 4. Three-Layer Benchmark
Every candidate must compare against the benchmark in three layers.

### A. Visual Quality
Compare:
`shell | typography | density | spacing | hierarchy | table rhythm | controls | colors | borders | radius | shadow | whitespace | first-glance silhouette`

### B. UX Quality
Compare:
`5-second comprehension | workload visibility | status clarity | next-action clarity | click burden | cognitive load | scanability | affordance clarity | detail-on-demand | error prevention`

### C. Workflow / Function Quality
Compare:
`workflow coverage | state continuity | ownership/handoff | longitudinal history | reassessment | versioning | entitlement/ledger | exception/recovery | closure | runtime function`

The target is not to win one layer by sacrificing another.

## 5. Preserve Before Improve — HARD RULE
Before changing the benchmark, identify its strengths explicitly.

For every material benchmark strength classify candidate result:
- `PRESERVED`
- `IMPROVED`
- `REGRESSED — JUSTIFIED`
- `REGRESSED — FAIL`

Do not redesign a benchmark strength merely because the designer prefers another pattern.

## 6. Improvement Must Have a Reason
A candidate may differ from the benchmark only when the change improves at least one measurable dimension without materially harming another:
- workflow fidelity;
- task completion speed;
- scanability;
- cognitive load;
- state/next-action clarity;
- patient safety;
- data visibility;
- accessibility/readability;
- responsive behavior;
- error prevention.

"Looks cleaner", "more modern", "premium", or designer preference alone is not sufficient justification.

## 7. Benchmark-First Build Strategy
When benchmark source exists:
1. start from the benchmark's proven composition/patterns where applicable;
2. preserve visual/component grammar;
3. graft validated workflow/functions using the same grammar;
4. add new surfaces only where workflow requires them;
5. use progressive disclosure before expanding first viewport;
6. render early before deep build;
7. compare benchmark vs candidate;
8. fix regressions before continuing.

Prohibited default pattern:
`Old Mockup → generic redesign → CSS approximation → self-declared premium`.

Preferred pattern:
`Benchmark source → preserve proven strengths → graft superior workflow/function → targeted improvement → visual/UX comparison`.

## 8. First-Viewport No-Regression Gate
At the benchmark viewport, compare:
- header/navigation footprint;
- content start position;
- work-surface-to-whitespace ratio;
- primary task visibility;
- table/list rows visible without scrolling;
- patient/work identity prominence;
- status and next action prominence;
- visual noise.

If the candidate wastes more viewport, hides more work, or requires more interpretation without a material benefit, it fails.

## 9. Before / Benchmark / Candidate Matrix — MANDATORY
Independent reviewer must produce a comparison matrix for material dimensions:

`Dimension | Benchmark Strength | Candidate Change | Result | Evidence/Reason`

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

No matrix = Benchmark Gate not executed.

## 10. Rendered Comparison — MANDATORY
Do not pass from source inspection alone.

Render benchmark and candidate at the same viewport. Compare side-by-side. When practical, create overlay/image-diff evidence.

The reviewer must answer:
- What did we preserve?
- What did we improve?
- What became worse?
- Is every regression justified by workflow/safety?
- Would a neutral reviewer reasonably choose the candidate over the benchmark for the intended job?

If the final answer to the last question is No:
`FAIL — BENCHMARK NOT EXCEEDED`.

## 11. Human-Approved Benchmark Veto
Human judgment overrides AI self-scoring.

If the user says the benchmark is better, the candidate is not allowed to defend itself with Master compliance or function completeness. It must return to design/build and correct the regression.

## 12. Relationship to Function
Function richness cannot compensate for poor UX/UI.

Correct objective:
`Benchmark UX/UI Strengths PRESERVED + Factory Workflow/Function Strengths PRESERVED + Material Weaknesses IMPROVED`

Therefore:
`Function PASS + Benchmark Regression = FACTORY FAIL`.

## 13. Gold Promotion
A candidate may become a new Gold Standard only after:
- Workflow/Function PASS;
- Runtime PASS;
- Benchmark Comparison PASS;
- no unjustified material visual/UX regression;
- Human Visual Review PASS.

## 14. Final Rule
**Do not aim to be different from a strong benchmark. Aim to preserve what already works, add what is missing, remove what is weak, and prove that the resulting product is better for the real hospital job.**