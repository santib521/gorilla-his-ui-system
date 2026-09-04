# Gorilla HIS — Premium Operational Worklist Standard v1.3

Status: `MANDATORY WHEN WORKLIST/QUEUE IS DERIVED`

## 1. Purpose
Create a worklist that behaves like a premium hospital work instrument: compact, comparable, actionable and calm.

The Human-approved `index_10.html` reference is the current visual floor for operational worklists.

## 2. Core Outcome
On opening the page, users should quickly understand:
`What work exists → What deserves attention → What state it is in → What to do next`.

## 3. Canonical Visual Grammar — HUMAN APPROVED
When a tabular/ledger worklist fits the job, default composition should closely follow:

`Page Context → optional Patient/Case Context → Tabs/Attention Strip → Attached Command Bar → Dominant White Worklist Surface → Contextual Drawer/Modal`

Visual qualities to preserve:
- cool-gray canvas;
- one dominant white work surface;
- subtle border/optical shadow;
- restrained 8–12px radii;
- IBM Plex Sans Thai typography target;
- indigo/blue primary actions;
- pale semantic status treatment;
- compact row density;
- numerical fields treated as instruments;
- no decorative dashboard sprawl.

## 4. Shell Relationship
The worklist belongs inside the Gorilla operational shell:
- 52px white topbar;
- 64px dark icon-first command rail;
- rail visually subordinate to the table;
- worklist uses the majority of viewport width.

Do not use a wide text-heavy sidebar by default.

## 5. Worklist Composition
Preferred transaction-heavy pattern:
- shallow page/context header;
- optional compact attention strip;
- tabs only when they represent genuinely different queues;
- search/filter/sort controls attached to the list;
- one dominant table/list;
- contextual detail in drawer/full workspace when deeper work is needed.

Do not create multiple competing cards around a small table.

## 6. Attention / Summary
Summary elements are optional and must support action.

If used:
- shallow, compact and clickable;
- show one operational count/value per item;
- do not displace the worklist below the fold;
- no decorative charting;
- active/attention rows may use a subtle semantic background wash.

## 7. Command Bar
Use a compact attached command bar:
- search input generally 220–360px;
- frequent filters as compact pills/chips/selects;
- result count at the edge;
- primary create/action button only when it is a frequent entry action;
- advanced filters behind disclosure.

Controls should feel part of the worklist, not scattered across the page.

## 8. Table Header
Reference-derived header treatment:
- subtle gray surface;
- thin bottom border;
- compact vertical padding;
- technical 10–11px text when uppercase/letter-spaced labels are appropriate;
- otherwise 12px semibold Thai labels;
- never large dark header bars.

Headers must remain readable and stable during scan.

## 9. Row Density
Reference target:
- body approximately 14px-class typography;
- around 10px vertical cell padding;
- enough height for one primary + one secondary line;
- no giant whitespace;
- subtle hover state;
- optional semantic attention wash;
- closed/off rows may reduce emphasis but remain legible and inspectable.

If row height is high while decision value is low = redesign.

## 10. Rich Cell Hierarchy
Use rich cells before adding excessive columns.

Typical hierarchy:
- line 1: patient / case / service — strongest;
- line 2: HN/VN/unit/requester/date — smaller muted text;
- line 3 only when it changes a decision.

Patient name should visually dominate HN and metadata.

## 11. Type / History Indicator
Transaction type may be shown as a compact small label/badge attached near the primary object rather than consuming an entire column when that saves scan width.

Prior-history presence should normally use a small recognizable icon/cue; open History on interaction. Do not waste a full text column when the binary cue is enough.

## 12. Quantitative Instrumentation
For money, quantity, quota, score, dates and utilization:
- use tabular/aligned numerals;
- keep units adjacent;
- show used/approved and remaining together when they drive work;
- compact progress bar may supplement values;
- do not force users to open each case to discover material remaining quantity/value.

## 13. Status Encoding
Status is passive information, not an action.

Status badges:
- small;
- pale semantic background;
- darker semantic text;
- thin border or no heavy border;
- no hover/cursor treatment unless intentionally interactive.

Users must be able to distinguish status from clickable controls immediately.

## 14. Action Hierarchy
Primary next action:
- compact filled indigo/blue button;
- strongest action in the row;
- ~32px height for row actions.

Secondary:
- white outlined or quiet action.

History/timeline/icon actions:
- visually quieter than primary.

Never present every possible action as equal saturated buttons.

## 15. Tabs
If queues are distinct, use flat tabs with:
- 12–14px semibold text;
- primary-color active text;
- subtle selected background;
- thin 2px active underline;
- optional compact count badge.

Do not use oversized card tabs.

## 16. Appointment / Daily Service Worklist
When work is appointment-driven, the table should expose without opening the case:
- appointment date/time;
- patient/HN;
- arrival/Alive time;
- VN when created;
- responsible worker/service;
- arrival/contact status;
- reassessment/Score status;
- utilization status;
- next action.

Use a Date filter prominently because the queue is date-centered.

Recommended lifecycle actions:
`Scheduled → Alive/Arrived → Reassessment → Use Confirmation → Completed / Cancelled`

Alive must visibly mutate time/state/VN when applicable.

## 17. Reassessment in Worklist
If current work depends on prior assessment:
- show current Score and version when available;
- show prior Score/delta when material;
- expose `ประเมิน Score + SDMA` when due;
- after save, expose `แก้ไข Score/SDMA` when correction is allowed;
- edits must be versioned amendments, not destructive overwrite.

## 18. Contextual Work
Opening a row should take the user to the correct lifecycle stage, not a generic overview.

Use:
- full page for deep professional work;
- right drawer for contextual inspection/history;
- modal for a focused bounded decision.

After handoff/save, return to a meaningful list state with filter context preserved.

## 19. Button vs Badge Clarity — HARD GATE
A user should know what is clickable without trial-and-error.

Interactive:
- cursor/hover/focus state;
- border/fill consistent with control grammar.

Passive:
- no button-like elevation/hover;
- status wording and semantic badge grammar.

Confusing passive labels with controls = `FAIL — AFFORDANCE CLARITY`.

## 20. Typography
Follow `VISUAL_DNA.md` and `tokens.css`.

Current target:
- IBM Plex Sans Thai for operational text;
- body/table ~14px-class;
- metadata 10–12px;
- patient identity 14px/600;
- technical numbers may use aligned/mono treatment.

## 21. Premium Visual Direction
Desired feeling: **quiet precision**.

Use:
- white primary surface;
- cool neutral canvas;
- indigo/blue action hierarchy;
- precise spacing;
- restrained semantic color;
- thin dividers;
- subtle optical shadow;
- consistent line icons.

Avoid:
- giant KPI dashboards;
- card sprawl;
- oversized rounded tiles;
- rainbow buttons;
- heavy shadows;
- wide dark navigation competing with work;
- generic SaaS admin composition.

## 22. Human Reference Extraction Contract
For every new worklist candidate compare against approved reference on:
`command-rail footprint | page-context height | work-surface proportion | toolbar density | header treatment | row height | patient/metadata hierarchy | quantitative emphasis | status treatment | action hierarchy | border/radius/shadow discipline | typography | hover/focus craft`

Candidate must be equal or better unless workflow/safety requires deviation.

## 23. Hard Failures
- user cannot tell what to work on;
- materially different queues collapsed into one confusing list;
- worklist displaced by dashboard decoration;
- row action unclear;
- status looks clickable when it is not;
- clickable control looks passive;
- important quantity/amount/progress hidden;
- patient identity weaker than metadata;
- wide navigation consumes work area;
- excessive cards/badges/colors/shadows;
- row density materially worse than approved reference;
- candidate visually diverges from Human-approved `index_10.html` without reason.

## 24. Review
Reviewer answers:
1. Can I understand workload in seconds?
2. Can I tell what deserves attention?
3. Are queues/states distinct?
4. Are patient identity and quantitative values easy to scan?
5. Is next action obvious?
6. Can I distinguish buttons from status labels immediately?
7. Does the page preserve the approved command-rail/work-surface grammar?
8. Is the table density and typography at least as good as the approved reference?
9. Can the real workflow continue naturally?

Any material `No` = redesign.

## 25. Final Rule
**Strong Gorilla worklists now follow the approved `index_10.html` product grammar: compact shell, dominant white ledger surface, precise hierarchy, restrained semantic states, IBM Plex Sans Thai, indigo action hierarchy and calm hospital-grade density.**
