# Gorilla HIS — Premium Operational Worklist Standard v1.1

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

## 5. Attention / Summary
Summary information is useful only when it changes what the user does.

A small set of counts, urgent items, recent work, approval waiting, due follow-up, or active entitlement may be shown elegantly. Do not create KPI cards simply because dashboards usually have cards.

Summary must support the worklist, not compete with it.

## 6. Row / Item Hierarchy
Each item represents a real actionable work object. Choose fields for decision value, not completeness.

Typical hierarchy may include:
`Type → Patient/Case → Reason/Service → Context/Source → Assessment/Progress → State → Next Action`.

Owner, aging, priority, quantity, amount, appointment or requester should appear when they materially affect the user's decision.

The designer may combine fields into a richer cell rather than creating excessive columns.

## 7. Next Action
The next valid action should be obvious from the item's lifecycle. It may be a button, contextual action, row affordance or open-to-stage behavior.

Examples: `รับงาน / ประเมิน / ลง SMDA / Verify / ส่งอนุมัติ / พิจารณา / ติดต่อผู้ป่วย / ประเมินครั้งถัดไป / บันทึกเยี่ยมบ้าน / ปิด Case`.

Do not make users decode a status and then hunt through menus to discover the action.

## 8. Premium Density
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

## 9. Search / Filter / Sort
Expose only high-value frequent controls first. Advanced filters may stay behind disclosure.

Possible dimensions: identity, My Work/All/Unassigned, transaction type, stage, urgency, unit/source, date/age, blocked/returned, service/category.

Do not fill the toolbar with every possible filter.

## 10. Status & Attention Encoding
Use color as a supporting signal, not the entire language. Meaning should remain understandable in grayscale through wording, position, weight, icon/shape or progress.

Reserve stronger emphasis for genuinely actionable states such as urgent, new/unassigned, returned, blocked, waiting approval or due follow-up.

## 11. Contextual Work
Opening an item should take the user to the work that needs doing, not always to a generic Overview.

Choose full page, side inspector, drawer or split view based on task depth and need to preserve list context.

After completing/handoff, return to a useful work state with the list/filter/context preserved.

## 12. 8 UX/UI Principles in Worklist Design
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

## 13. Premium Visual Direction
The desired feeling is **quiet confidence**:
- restrained, sophisticated color;
- high-quality Thai typography;
- precise spacing;
- controlled corner radius and shadow;
- purposeful iconography;
- strong scan rhythm;
- no decorative clutter;
- no generic SaaS-dashboard feel.

A premium screen may be simple. Simplicity is successful when important work becomes easier to see and act on.

## 14. Reference Benchmark
When a user/reference candidate demonstrates stronger hierarchy, scanability or premium craft, analyze it as design evidence. Preserve its useful principles while adapting to Gorilla HIS and actual workflow.

Do not reject a better visual idea merely because it differs from a preferred Factory pattern.

## 15. Hard Failures
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
- design is visibly inferior to a credible reference in hierarchy/scanability without operational justification.

## 16. Review — SHORT AND OUTCOME-BASED
Reviewer answers:
1. Can I understand the workload quickly?
2. Can I see what deserves attention?
3. Can I distinguish transaction/state/progress?
4. Is the next action obvious?
5. Does the screen feel calm, premium and professional?
6. Does it fit this specific hospital job rather than a generic dashboard?
7. Can I continue the actual workflow naturally?

If yes and runtime/workflow tests pass, the worklist is a valid candidate.

## 17. Final Rule
**Modern ≠ cards. Dense ≠ cramped. Premium ≠ empty. Master ≠ template.**

Design for the job first; use the rules to protect quality, not to replace design judgment.