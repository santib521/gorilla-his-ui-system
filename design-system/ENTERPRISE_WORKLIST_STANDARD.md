# Gorilla HIS — Premium Operational Worklist Standard v1.2

Status: `MANDATORY WHEN WORKLIST/QUEUE IS DERIVED`

## 1. Purpose
Create a worklist that feels like a premium professional instrument, not a compliance table and not a generic admin dashboard.

**The worklist should make the user want to work from it.**

## 2. Core Outcome
On opening the page, the user should quickly understand:
`What work exists → What deserves attention → What state it is in → What to do next`.

How the designer achieves this is flexible.

## 3. Preferred Design Thinking
Start with the work, not components:
- What are the real work objects?
- What does the user scan repeatedly?
- What differences matter for prioritization?
- What action is most common at each state?
- What information can be hidden until selection?
- What deserves visual emphasis?

Then choose the composition.

## 4. Worklist Composition — OPTIONS, NOT TEMPLATE
A strong pattern may be:
`Compact Header → optional small Attention/My Work zone → Search/Filter command bar → Operational List → contextual workspace`.

But this is not mandatory. A split-view queue, grouped list, timeline list, schedule-worklist hybrid, or another composition is valid if it serves the work better.

**Do not make every Gorilla module look identical.**

## 5. Benchmark-Derived Enterprise Ledger Pattern — PREFERRED WHEN FITS THE JOB
For transaction-heavy hospital work where users compare many records, values, statuses, quantities or next actions, consider an **Enterprise Ledger Worklist** pattern.

Characteristics extracted from strong reference worklists:
- compact summary tiles above the list only when each summary maps to actionable work;
- one dominant bounded worklist surface rather than many competing cards;
- command/search controls integrated into the list header;
- clear column architecture with stable alignment;
- rich cells combining primary + secondary context instead of excessive columns;
- quantitative values shown as instruments: quantity, amount, score, used/remaining, dates;
- restrained semantic status chips;
- compact but readable row height;
- subtle row banding/tonal separation to support horizontal scanning;
- primary action visually obvious but proportionate, with secondary/history actions quieter;
- totals/counts belong at the edge/footer of the list, not as oversized dashboard numbers.

Use this pattern only when users really scan and compare multiple transactions. It is a **reference grammar, not a mandatory layout**.

## 6. Attention / Summary
Summary information is useful only when it changes what the user does.

A small set of counts, urgent items, recent work, approval waiting, due follow-up, or active entitlement may be shown elegantly. Do not create KPI cards simply because dashboards usually have cards.

When summary tiles are used:
- each tile must be clickable/filterable/navigational;
- one dominant number + short operational label is usually enough;
- secondary value may show amount/exception when decision-relevant;
- avoid decorative charts or duplicated metrics;
- keep the entire summary zone shallow enough that the worklist remains visible in the first viewport.

Summary must support the worklist, not compete with it.

## 7. Row / Item Hierarchy
Each item represents a real actionable work object. Choose fields for decision value, not completeness.

Typical hierarchy may include:
`Type → Patient/Case → Reason/Service → Context/Source → Assessment/Progress → State → Next Action`.

Owner, aging, priority, quantity, amount, appointment or requester should appear when they materially affect the user's decision.

The designer may combine fields into a richer cell rather than creating excessive columns.

### Rich-cell hierarchy
When combining data in one cell:
- line 1 = primary decision object, usually patient/case/service;
- line 2 = secondary context such as HN, unit, requester, date;
- line 3 only when it adds material decision value;
- primary/secondary contrast should come from weight/tone/alignment before extra badges.

## 8. Quantitative Scanability
When work includes money, quantity, score, quota, entitlement, utilization or repeated visits, the worklist should allow side-by-side comparison without opening every case.

Preferred treatment:
- use tabular numerals when available;
- keep unit adjacent to value;
- show `used / approved` and `remaining` together;
- show amount used/remaining when material;
- visually distinguish exception/shortfall without relying on color alone;
- progress bars are optional and should be compact, not decorative.

If a user must open each row merely to know how much has been used or remains, the worklist is incomplete when that information drives action.

## 9. Next Action
The next valid action should be obvious from the item's lifecycle. It may be a button, contextual action, row affordance or open-to-stage behavior.

Examples: `รับงาน / ประเมิน / ลง SMDA / Verify / ส่งอนุมัติ / พิจารณา / ติดต่อผู้ป่วย / ประเมินครั้งถัดไป / บันทึกเยี่ยมบ้าน / ปิด Case`.

Primary action should be visually stronger than history/secondary action, but not so large or saturated that every row becomes a wall of buttons.

Do not make users decode a status and then hunt through menus to discover the action.

## 10. Premium Density
Premium worklists balance density and calmness.

Aim for:
- useful information per viewport;
- comfortable Thai reading;
- stable alignment;
- clear primary/secondary text;
- restrained status treatment;
- enough whitespace to separate meaning;
- subtle hover/selection/focus states;
- numbers/progress that are easy to compare.

Avoid both extremes: cramped spreadsheet and oversized card gallery.

### Density benchmark test
At a standard desktop viewport, ask whether the visible rows communicate enough real work to justify their vertical space. If row height is high while decision value is low, redesign.

## 11. Search / Filter / Sort
Expose only high-value frequent controls first. Advanced filters may stay behind disclosure.

Possible dimensions: identity, My Work/All/Unassigned, transaction type, stage, urgency, unit/source, date/age, blocked/returned, service/category.

Prefer a compact command bar that feels attached to the worklist. Do not scatter search, reset, filters and actions across unrelated areas.

Do not fill the toolbar with every possible filter.

## 12. Status & Attention Encoding
Use color as a supporting signal, not the entire language. Meaning should remain understandable in grayscale through wording, position, weight, icon/shape or progress.

Reserve stronger emphasis for genuinely actionable states such as urgent, new/unassigned, returned, blocked, waiting approval or due follow-up.

Status chips should be compact and semantic. Avoid long outlined labels that dominate the row.

## 13. Contextual Work
Opening an item should take the user to the work that needs doing, not always to a generic Overview.

Choose full page, side inspector, drawer or split view based on task depth and need to preserve list context.

After completing/handoff, return to a useful work state with the list/filter/context preserved.

## 14. 8 UX/UI Principles in Worklist Design
Use as design instincts:
- familiar work vocabulary and grouping;
- fewer simultaneous choices;
- easy-to-hit frequent actions;
- chunked information;
- polished visual quality;
- proximity of evidence/action;
- consistent semantic styling;
- clear, satisfying handoff/completion feedback.

Do not add eight visible UI elements to prove the eight principles were used.

## 15. Premium Visual Direction
The desired feeling is **quiet confidence**:
- restrained, sophisticated color;
- high-quality Thai typography;
- precise spacing;
- controlled corner radius and shadow;
- purposeful iconography;
- strong scan rhythm;
- no decorative clutter;
- no generic SaaS-dashboard feel.

Preferred visual behavior for ledger-style worklists:
- soft neutral page canvas;
- white/light primary work surface;
- subtle borders over heavy shadows;
- header row clearly differentiated but not dark/heavy;
- stronger typographic hierarchy than box hierarchy;
- colored values only when meaningfully exceptional/actionable;
- compact, crafted buttons with state-driven emphasis.

A premium screen may be simple. Simplicity is successful when important work becomes easier to see and act on.

## 16. Reference Benchmark
When a user/reference candidate demonstrates stronger hierarchy, scanability or premium craft, analyze it as design evidence. Preserve its useful principles while adapting to Gorilla HIS and actual workflow.

For screenshot references, explicitly extract:
`summary proportion | worklist-to-whitespace ratio | header treatment | row height | primary/secondary type scale | cell grouping | numerical emphasis | status treatment | action hierarchy | border/shadow/radius discipline`.

Do not reject a better visual idea merely because it differs from a preferred Factory pattern.

## 17. Hard Failures
- user cannot tell what to work on;
- passive list with no natural action path;
- important workflow information buried;
- next action unclear;
- worklist displaced by decorative dashboard content;
- excessive card/badge/color/shadow noise;
- cramped or tiny typography;
- generic admin template with weak domain identity;
- repeated/quantity work hides progress;
- item opens to the wrong lifecycle stage;
- summary cards look operational but are not interactive;
- primary action and history action have equal visual weight;
- row height/whitespace materially exceeds the decision value shown;
- design is visibly inferior to a credible reference in hierarchy/scanability without operational justification.

## 18. Review — SHORT AND OUTCOME-BASED
Reviewer answers:
1. Can I understand the workload quickly?
2. Can I see what deserves attention?
3. Can I distinguish transaction/state/progress?
4. Can I compare key quantitative values without opening each case?
5. Is the next action obvious?
6. Does the screen feel calm, premium and professional?
7. Does it fit this specific hospital job rather than a generic dashboard?
8. Can I continue the actual workflow naturally?
9. If a benchmark exists, is the candidate at least equal in scan rhythm, density and visual finish?

If yes and runtime/workflow tests pass, the worklist is a valid candidate.

## 19. Final Rule
**Modern ≠ cards. Dense ≠ cramped. Premium ≠ empty. Master ≠ template.**

**Strong enterprise worklists behave like an operational ledger: compact, comparable, actionable and calm.**

Design for the job first; use the rules to protect quality, not to replace design judgment.