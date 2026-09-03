# Gorilla HIS — Blueprint Quality Gate v2.7

Purpose: enforce source truth, **actual hospital workflow fidelity**, Thailand-aware domain expertise, complete transaction/lifecycle challenge and safe handoff for every module.

## Gate 1 — Source Truth
Hospital facts separated from recommendations/assumptions/TBD/domain baseline. HARD FAIL: invented Hospital Confirmed.

## Gate 2 — Actual Workflow Evidence — UNIVERSAL HARD GATE
Follow `ACTUAL_WORKFLOW_DISCOVERY_STANDARD.md` for every module.

Blueprint must show evidence status for the actual operating flow. Primary evidence may include user workshop/interview, recording/transcript/minutes, SOP/form, current-system walkthrough/screenshots, observed work and confirmed TOR/requirement.

Required distinction: `HOSPITAL OBSERVED / HOSPITAL STATED / HOSPITAL DOCUMENTED / HOSPITAL CONFIRMED / EXPERT INFERENCE / REFERENCE BASELINE / TBD`.

If material actual workflow is not evidenced, mark `ACTUAL WORKFLOW NOT VERIFIED`; never silently fill it with generic HIS practice.

HARD FAIL: plausible Standard/AI workflow presented as Hospital Actual Workflow.

## Gate 3 — Core Transaction / Object Discovery — UNIVERSAL HARD GATE
Before Function List/UI design identify material business transactions/objects and their boundaries.

For each: Trigger, creator, identifier, related object, source of truth, authority, lifecycle, quantity/value when relevant, versioning, correction/reversal and closure.

HARD FAIL if materially different transactions are collapsed into one generic Case/Referral/Order merely because the same department owns them.

## Gate 4 — Lifecycle / State Transition
Every material transaction has state model and transition rules:
`From → Event/Action → Actor → Preconditions → Data Mutation → Downstream Effect → To → Audit → Failure/Recovery`.

Challenge Return/Reject/Cancel/Expire/Suspend/Correct/Reverse/Reopen where relevant.

HARD FAIL: happy-path states only when correction/reversal/partial work is material.

## Gate 5 — Repeated / Longitudinal Workflow
Determine whether workflow repeats across session/visit/cycle/episode, consumes quantity/value, requires reassessment, partial fulfillment, renewal or extension.

If applicable Blueprint must model progression, history/version and remaining obligation/quantity/value.

HARD FAIL: repeated lifecycle reduced to one Save → Complete action.

## Gate 6 — Assessment / Version / Carry-Forward
When assessment repeats, define initial/reassessment, carry-forward, changed/unchanged values, score/formula version, author/context, amendment and downstream effect. Silent history overwrite = HARD FAIL.

## Gate 7 — Role / Handoff / Waiting State
Every material transition identifies current owner, next owner, queue/worklist, waiting state, notification/SLA when relevant, return route and proof of handoff.

## Gate 8 — Data / Source-of-Truth Continuity
Major object/data source, creator, consumer, edit authority, timing, version, reconciliation and downstream dependency defined. Correction impact traced.

## Gate 9 — Thailand-First Domain Authority
For domains materially shaped by Thai law/MOPH/professional/public-agency/national workflow, authoritative Thai sources considered before generic international practice. Domain Pack compared against evidence; inadequate pack becomes research candidate/update before Dev Handoff.

HARD FAIL: generic AI/international knowledge substitutes for material Thai authority.

## Gate 10 — Standard-Flow Challenge, Not Replacement
Domain Standard Flow is `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`.

Run standard/domain challenge **after Actual Workflow Reconstruction** where Hospital Primary Evidence exists. Compare using Actual-vs-Standard Delta. External guidance may reveal missing decisions but cannot overwrite local truth.

## Gate 11 — Legal / Operational Classification
Material classifications/triggers that change actor/authority/location/evidence/workflow/end state explicitly modeled. HARD FAIL if system design starts downstream of a material classification without reason.

## Gate 12 — Scenario Branch Completeness
Each material scenario has Trigger/Entry, Transaction, Identifier/Context, Starting Actor, Handoffs, Source-of-Truth, Repeated/Longitudinal behavior, Exceptions and End State. No cosmetic branch collapse.

## Gate 13 — Relevance / Materiality / Actionability
Every GAP/question traceable, current/direct dependency, material, actionable and timed. NOT STATED ≠ automatic GAP.

## Gate 14 — Clinical/Data/Domain Safety
No unconfirmed assumption causes unsafe clinical/legal/data/financial effect.

## Gate 15 — Evidence Strength
Critical/High records evidence basis, trace source, verification and confirmation owner. Speculation cannot be verified fact.

## Gate 16 — Standards / Privacy / Security
Apply only relevant Thai/domain authority, HA/HAI, privacy/security and JCI when applicable/selected. No fabricated clauses or local authority.

## Gate 17 — Expert Requirement Discovery
All applicable discovery dimensions dispositioned. Workshop Question Bank uses stable IDs and concrete decisions. Generic questions, hidden Critical/High decisions and happy-path-only discovery = HARD FAIL.

## Gate 18 — Independent Domain + Reality Challenge
Independent reviewer asks both:
- “What would a real Thai domain specialist object is missing?”
- “Would an experienced user from this exact department recognize their real day-to-day work?”

Review truth contamination, missing transaction boundary, off-system work, state/lifecycle, repeated use, role/handoff, source-of-truth, exceptions and closure.

HARD FAIL if omitted.

## Gate 19 — Functions / Rules / Traceability
REQ/BR/FN/HSR/CR/WA/TBD/AC correctly classified; only explicit confirmation promotes Requirement/Business Rule.

## Gate 20 — Working Assumption Safety
WA reversible/labeled/non-dangerous/not false compliance/confirmation point; otherwise TBD.

## Gate 21 — Deliverable Separation
Business Source of Truth and Advisory separated. Thai-first Blueprint, Compliance Review, Expert Suggestion and Workshop Question Bank required by Factory process.

## Gate 22 — UI Handoff Readiness
Every prototype scenario declares:
`Actual Trigger/Entry → Core Transaction → Lifecycle/State → Actor/Owner → Identifier/Context → Handoff → Repeated/Reassessment/Partial Use if applicable → Material Exception → End State`.

UI Factory must not begin only from a pre-created case when upstream stage is in scope.

## Gate 23 — Workflow Fidelity Contract
Blueprint defines what the independent UI reviewer must prove against Hospital Evidence.

Required result vocabulary:
`PASS / FAIL — WRONG TRANSACTION MODEL / FAIL — WORKFLOW FIDELITY / FAIL — LIFECYCLE INCOMPLETE / FAIL — REPEATED FLOW MISSING / FAIL — HANDOFF BROKEN / BLOCKED — ACTUAL WORKFLOW NOT VERIFIED`.

## Forensic Additional Lifecycle Challenge
When Forensic is activated, additionally disposition living/deceased, medico-legal classification, scene exam, request authority, intake, identity/AF-HN, physician/team, external examination/autopsy/no-autopsy, diagnostic orders, evidence/specimen/property/media custody, finance, sensitive identity/media, report lifecycle, body receive/store/move/release, unknown identity, custodial/special branch, external testing, multidisciplinary synthesis when applicable, exceptions/downtime and closure/statistics.

Domain-specific checklists supplement — never replace — Universal Actual Workflow gates.

## Readiness
`DRAFT` — actual workflow/transaction boundary insufficient for safe prototype.

`PROTOTYPE READY` — enough Hospital Truth for bounded discovery; unresolved workflow visible and contained; material transactions/lifecycles/scenarios defined.

`HOSPITAL CONFIRMED` — actual main workflows, material transactions/lifecycles and critical represented rules confirmed.

`READY FOR DEV HANDOFF` — implementation-blocking workflow/transaction/state/authority/data/integration/AC decisions confirmed or explicitly excluded.

## Hard Reject
Invented Hospital Truth; Standard Flow copied as local workflow; wrong/merged transaction model; missing material repeated lifecycle; hidden correction/reversal; incoherent handoff; fabricated authority; unsupported mandatory standard; critical unresolved hidden as assumption; omitted Independent Reality Challenge; material scenario/classification omitted.

## Final Factory Rule
`Business Truth PASS + Workflow Fidelity PASS + Function PASS + Runtime PASS + Independent Design PASS → Candidate — Ready for Human Visual Review`.

**Visual PASS + Functional PASS + Workflow Fidelity FAIL = FACTORY FAIL.**