# Gorilla HIS — Enterprise Worklist & Queue UX Standard v1.0

Status: `MANDATORY WHEN WORKLIST/QUEUE IS DERIVED`

Purpose: make operational lists behave like modern professional hospital work surfaces, not dashboards, card galleries or passive tables.

## 1. Core Principle
**Operational system ≠ Dashboard. Dashboard summarizes. Worklist gets work done.**

When a module has incoming/assigned/pending work, first viewport must prioritize scanning, triage, ownership and next action.

## 2. Worklist Architecture
Preferred architecture when appropriate:

`Compact Module Header → Attention / My Work strip (optional) → Search/Filter/Sort command bar → Dense Operational Worklist → Contextual detail/workspace`

The Attention strip is optional and small. It must not push the real worklist below the first viewport.

## 3. Hybrid Worklist Pattern
For modules where recent/urgent/personal work deserves emphasis, use:
- **Attention Zone / My Work:** only a few high-value items, due/urgent/recent/blocked;
- **All Work:** dense list/table for complete operational workload.

Do not duplicate every row as a card. Cards are for attention, not the primary high-volume work inventory.

## 4. First-Viewport 5-Second Test
Without explanation, user must identify:
- total/current workload;
- which items need attention first;
- transaction type;
- patient/case/task identity;
- current status;
- owner/unassigned state;
- age/due/priority when relevant;
- progression/remaining when relevant;
- **Next Action**.

If user opens the page and cannot answer “what should I work on now?” → `FAIL — WORKLIST UX`.

## 5. Row as Work Object
A row/list item represents an actionable work object, not a decorative summary.

Typical information hierarchy:
`Type → Identity → Reason/Service → Source → Priority → Status → Owner → Time/Aging → Progress → Next Action`

Exact columns derive from workflow. Do not show fields just because database contains them.

The row must support either direct primary action or opening directly into the correct lifecycle workspace.

## 6. Next Action is First-Class
Do not force users to infer next action from status codes.

Examples of lifecycle-driven labels:
`รับงาน / ประเมิน / Verify / ส่งอนุมัติ / พิจารณา / ติดต่อผู้ป่วย / ประเมินครั้งถัดไป / บันทึกผล / แก้ไข / ปิดงาน`.

Action vocabulary must use hospital/domain terminology.

## 7. Density
Hospital worklists often have high volume. Optimize for scan speed:
- compact but readable row height;
- Thai main text normally ≥13px;
- secondary metadata may be smaller but readable;
- align IDs/times/numbers consistently;
- avoid excessive vertical padding;
- avoid card-per-row with large radius/shadow;
- use whitespace as grouping, not as empty luxury;
- allow useful columns to consume desktop width.

Premium density means more decision value per viewport without cognitive clutter.

## 8. Navigation Footprint
Worklist owns the width. Persistent navigation should normally be compact/collapsible when the module benefits from wide rows. Large sidebar + large topbar + tabs + cards that squeeze the worklist = FAIL.

## 9. Search / Filter / Sort
Controls must reflect actual operational retrieval:
- search by high-value identifiers/names;
- My Work / All / Unassigned where relevant;
- transaction type;
- status/stage;
- priority/urgency;
- unit/source;
- date/age/due;
- exception/blocked;
- service/category when material.

High-frequency filters stay visible; advanced filters may be disclosed. Filter state and result count must be clear.

## 10. Attention Encoding
Use semantic emphasis sparingly:
- urgent/overdue/critical exception;
- unassigned/new;
- waiting approval/handoff;
- blocked/returned;
- due follow-up.

Do not color every row. Status chips must not become confetti. Meaning should survive grayscale through text/position/shape.

## 11. Modern Worklist Craft
A modern worklist is not defined by rounded cards. It is defined by:
- excellent scan hierarchy;
- low-friction filters;
- contextual primary action;
- clear state/owner;
- compact attention summary;
- responsive density;
- row hover/selection/focus states;
- keyboard-friendly interaction where appropriate;
- stable column alignment;
- persistent context during detail work;
- fast return to same list position/filter.

## 12. Master-Detail Behavior
Choose based on task:
- full-page workspace when task is deep/complex;
- side inspector/drawer when user needs rapid list comparison;
- split view when list context must remain visible during repeated review.

After completing/handing off a task, return user to a meaningful next-work state, not a dead success page.

## 13. Empty / Loading / Error / Stale
Worklist must define:
- initial loading/skeleton appropriate to density;
- no results vs no work distinction;
- filter-empty state;
- interface/data-load failure;
- stale data/retry when material;
- permission-limited list;
- optimistic action failure/recovery when used.

## 14. Responsive / Adaptive
On narrower desktop/tablet:
- preserve identity, status and next action first;
- collapse low-value columns into secondary detail;
- do not hide primary action;
- maintain scan alignment;
- avoid turning every row into an oversized mobile card unless viewport truly requires it.

## 15. Anti-Patterns — Hard FAIL
- KPI dashboard occupies most first viewport while work is below fold;
- large equal cards for every work item;
- passive table with no lifecycle action;
- status-only rows requiring user to guess next step;
- oversized navigation squeezes worklist;
- excessive badges/colors/shadows/radius;
- tiny Thai text to achieve density;
- action detached from row/object;
- no owner/assignment when ownership is part of workflow;
- no progression/remaining for repeated or quantity-based work;
- opening a record always lands on generic Overview instead of the work stage that needs action.

## 16. Worklist Review Artifact
For every derived worklist record:
`Primary User | Work Object | Expected Volume | Scan Fields | Attention Rules | Filters | Sort Default | Primary Row Action | Open Behavior | Ownership | Aging/SLA | Progress | Responsive Priority`.

## 17. Final Gate
**Modern ≠ cards. Dense ≠ cramped. Premium ≠ empty.**

A Gorilla HIS worklist should feel like a precise professional instrument: users can scan workload quickly, understand priority/state/ownership, and act on the next task with minimal cognitive effort.