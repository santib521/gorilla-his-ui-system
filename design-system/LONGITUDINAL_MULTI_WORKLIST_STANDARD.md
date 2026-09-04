# Gorilla HIS — Longitudinal Multi-Worklist Standard v1.0

Status: `MANDATORY WHEN ONE DEPARTMENT HAS MULTIPLE MATERIAL WORK OBLIGATIONS OR LONG-RUNNING CASES`

## 1. Purpose
A worklist is not a menu, a status report, or a list of every record in the module. A worklist represents a **specific operational obligation that a user must manage**.

Core rule:
`Actual Workflow → Work Obligation → Queue Boundary → Worklist → Status/Lifecycle → Next Action`

Never derive one giant list directly from every lifecycle state.

## 2. Worklist vs Status — HARD RULE
`Worklist` answers: **What job must I do?**
`Status` answers: **Where is this case inside that job?**

Do not create a separate top-level Worklist for every status. Do not collapse materially different jobs into one generic All Cases list.

A top-level Worklist is justified when the work differs materially in one or more of:
- operational trigger;
- time horizon / scheduling basis;
- user goal;
- required evidence;
- decision/action;
- queue ownership;
- completion condition.

## 3. Canonical Three-Obligation Pattern
When supported by Hospital Actual Workflow, a department may require separate worklists such as:

### A. Longitudinal Case Management Worklist
For a case that may remain active for many days/weeks.

Typical obligation:
`Receive → Assess → Verify → Submit/Wait Decision → Approved → Notify/Coordinate → Service Started/Follow-up`

This worklist owns the **case-management lifecycle**, not each future service visit.

### B. Daily Scheduled / Return Service Worklist
For approved/active patients who return on a specific date/time.

Typical obligation:
`Scheduled Today → Arrived/Contacted → Reassessment → Review Utilization → Confirm Use → Next Appointment/Complete`

This queue is date-centered and should not be mixed with the long-running case-management queue.

### C. Planned Field / Home Visit Worklist
For field work created by an assessment or follow-up plan.

Typical obligation:
`Planned → Scheduled → Assigned/Accepted → Visit In Progress → Result Recorded → Follow-up/Complete`

The source case remains linked, but field execution has its own queue, schedule, evidence and completion state.

## 4. Long-Running Case Worklist
When cases may remain open for 20–50 days or longer, never show the user only one undifferentiated list.

The primary list must expose:
- case/patient identity;
- current lifecycle status;
- current owner;
- elapsed case age as `Day N` or equivalent;
- last meaningful activity;
- waiting-on / blocking party when material;
- next action;
- important pending evidence such as Consent or documents.

### 4.1 Elapsed Day
Elapsed day is operational context, not automatically an SLA breach.

Show:
`Started/Received date → Day N`

Do not color Day N as overdue unless the hospital has confirmed an SLA/threshold or a configurable policy exists.

### 4.2 Queue Tabs
Tabs inside a long-running case worklist should represent **operationally useful subsets**, not decorative status taxonomy.

Useful examples when supported:
- `Consult Today` — new Consults entering today;
- `Waiting Confirm / Approve` — work blocked on confirmation/approval;
- `In Progress` — accepted cases requiring active case management;
- `All Active Cases` — recovery/search view.

Default tab should match the staff member's most common immediate daily job.

## 5. Reminder / Notification Strip
The shallow strip above a worklist is for **actionable reminders**, not dashboard decoration.

Examples:
- New Consult not yet received;
- Consent missing;
- Waiting approval;
- patient return due today;
- home visit due today;
- missing required document.

Rules:
- every reminder must filter/navigate to relevant work;
- keep it shallow enough that the list remains visible in first viewport;
- do not replace the worklist with KPI cards;
- do not invent overdue thresholds without hospital-confirmed policy.

## 6. Case Management Status Model
The exact status names are hospital truth and must not be invented. When the hospital confirms a sequence, model it explicitly and preserve the terms.

A common pattern may include:
`New → Received → Assessment → Verified → Submitted for Approval → Approved → Patient Notified → Service Started`

But the Factory must support branch-specific lifecycle behavior. Example: a Consult type that requires assessment only may legitimately skip approval; this must be derived from hospital evidence, not assumed.

Status must remain passive information. `Next Action` is the control.

## 7. Daily Return / Appointment Worklist
Daily return work is a separate operational obligation from case management.

The first viewport should expose:
- appointment time/date;
- patient/HN;
- source case / authorization;
- visit sequence;
- arrival/contact state;
- current and prior assessment/score when relevant;
- used/approved quantity;
- used/approved amount;
- remaining quantity and amount;
- planned home-visit indicator when relevant;
- next action.

Typical execution:
`Scheduled → Arrived → Reassessment → Utilization Review → Confirm Use → Completed / Next Visit`

Every utilization event must update the same entitlement/authorization ledger when such an authorization exists.

## 8. Home Visit Worklist
Home Visit must not be merely a checkbox hidden inside a case when staff have to schedule and execute it later.

When Home Visit creates real future work, capture at minimum:
- source case;
- reason/topic/objective;
- planned number of visits when applicable;
- planned date/time or date window;
- owner/assignee when hospital workflow defines it;
- visit sequence;
- status;
- result/findings;
- next follow-up;
- completion/remaining visits.

Creating a Home Visit Plan in another workspace must create a visible work item in the Home Visit Worklist.

## 9. Paper Form → Digital Workspace
When a hospital supplies a paper form, the goal is **semantic fidelity with easier entry**, not a literal visual photocopy.

Use this transformation:
`Paper Section → Structured Digital Section → Reusable Data → Validation → Decision Support → Print/Document Output`

Preserve:
- section meaning;
- field meaning;
- option vocabulary;
- required signatures/consent/documents;
- clinically/operationally meaningful ordering.

Improve:
- patient demographics auto-fill from HIS when available;
- checkbox groups become selectable structured options;
- repeated financial lines become editable rows;
- dependent sections appear only when relevant;
- totals calculate automatically;
- long forms use anchored sections/progressive disclosure without hiding mandatory work;
- save draft and resume when long-running assessment is realistic.

Do not force users to type information already available from source-of-truth systems.

## 10. Worklist-to-Workspace Continuity
Clicking Next Action must open the exact stage-specific workspace.

Examples:
- New → Receive/Stamp;
- Received → Assessment + Consent;
- Assessment → Verify;
- Verified → approval preparation/submit when applicable;
- Approved → patient contact/service coordination;
- Daily Scheduled → arrival;
- Daily Arrived → reassessment/utilization;
- Home Visit Planned → visit execution.

After save, the transaction must visibly move/update in the correct queue. Toast-only success is a failure.

## 11. Capacity and Scanability
A worklist should be optimized for the real daily volume, but daily case-count assumptions are local hospital evidence, not universal Master rules.

Design for rapid scan:
- strong patient identity;
- age/timing visible;
- one obvious next action;
- rich cells rather than excessive columns;
- compact density;
- search/filter retained;
- no dashboard sprawl.

## 12. Master Gate
Before passing a multi-worklist design, reviewer must answer:
1. What are the user's materially different work obligations?
2. Does each top-level Worklist map to one obligation rather than one status?
3. Can a long-running case be found and understood without reading every row detail?
4. Is elapsed Day visible without inventing SLA meaning?
5. Is today's scheduled work separated from long-running case management?
6. Does a planned Home Visit create a real executable work item?
7. Do reminder cards navigate to real work?
8. Does every lifecycle stage expose a clear Next Action?
9. Does the New/Create workspace preserve hospital form meaning while reducing entry burden?
10. After each action, does queue/state/history visibly update?

Any material `No` = `FAIL — WORKLIST ARCHITECTURE`.

## 13. Final Rule
**Design Worklists from operational obligations first. Use statuses to manage progress inside those obligations. For long-running hospital work, separate case management, today's return work, and planned field work whenever their triggers and actions are materially different.**
