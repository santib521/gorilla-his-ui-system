# Gorilla HIS — Blueprint Quality Gate v2.6

Purpose: enforce source truth, Thailand-aware domain expertise, complete workflow challenge and safe handoff without converting recommendations/standards into false hospital requirements.

## Gate 1 — Source Truth
Hospital facts separated from recommendations/assumptions/TBD/domain baseline. HARD FAIL: invented Hospital Confirmed.

## Gate 2 — Thailand-First Domain Authority
For domains materially shaped by Thai law/MOPH/professional/public-agency/national workflow:
- authoritative Thai sources considered before generic international practice;
- legal/operational case classifications identified;
- repository Domain Pack compared against evidence;
- inadequate pack becomes research candidate/update before Dev Handoff.

HARD FAIL: generic AI/international knowledge substitutes for material Thai domain authority.

## Gate 3 — Expert Coverage & Domain Activation
Relevant domain baseline/knowledge pack loaded. Forensic must activate Forensic Knowledge + Forensic Standard Flow. HARD FAIL if omitted.

## Gate 4 — Relevance Gate
Every GAP/question traceable, current/direct dependency, material, actionable and timed. NOT STATED ≠ automatic GAP.

## Gate 5 — Standard-Flow-First Architecture
Baseline labeled REFERENCE, Hospital Overlay uses MATCHED/PARTIAL/NOT STATED/CONFLICT/N/A, standards after baseline+overlay, external guidance not promoted to local truth.

### Gate 5A — Legal/Operational Classification
Material classifications/triggers that change actor/authority/location/evidence/workflow/end state explicitly modeled. HARD FAIL if system design starts downstream of a material classification without reason.

### Gate 5B — Scenario Branch Completeness
Each material scenario has Classification/Entry, Identifier/Context, Starting Actor, Location when relevant, Handoffs, Source-of-Truth, Custody where relevant, Exceptions, End State and Hospital Coverage. No cosmetic branch collapse.

## Gate 6 — Clinical/Data/Domain Safety
No unconfirmed assumption causes unsafe clinical/legal/data/financial effect.

## Gate 7 — Evidence Strength
Critical/High records evidence basis, trace source, verification and confirmation owner. Speculation cannot be verified fact.

## Gate 8 — Standards / Privacy / Security / Domain Authority
Applicable Thai/domain authority, HA/HAI, privacy/security and JCI only when applicable/selected. No fabricated clauses.

### Gate 8A — Forensic Compliance Review
Must consider MOPH, CIFS, applicable Thai legal authority, current HA, Hospital SOP/forms; JCI only if applicable. Source registry records organization/resource/type/status/topic/applicability/verification/ref.

### Gate 8B — Forensic Lifecycle Challenge — Mandatory 20
Every forensic run dispositions `COVERED / PARTIAL / GAP / N/A / NEED HOSPITAL CONFIRMATION` for:
1 living vs deceased;
2 medico-legal death classification/trigger;
3 scene examination applicability;
4 request/referral origin + authority;
5 Accept/Reject/Return/Redirect;
6 AF/HN/VN/Encounter/provisional identity;
7 HN match/link/unlink/correction;
8 physician/team roster/assignment/handoff;
9 autopsy/examination vs no-autopsy decision;
10 diagnostic order context;
11 specimen/evidence/property/media Chain of Custody;
12 finance/payer/posting/reversal;
13 sensitive identity/name/media handling;
14 report author/review/final/amend/print/handover;
15 body receive/store/move/release/disposition;
16 unknown/unidentified → identified lifecycle;
17 custodial/special authority branch relevance;
18 external scientific testing/result return;
19 exceptions/downtime/correction/reconciliation;
20 closure/statistics/source definitions.

Any applicable silent omission = HARD FAIL.

## Gate 9 — Gap Analysis Quality
Stable IDs, why matters, impact, treatment, relevance, owner, timing/blocking, Critical/High visible, duplicates removed.

## Gate 10 — Independent Domain Challenge
Second reviewer asks: “What would a real Thai domain specialist object is missing?” Review truth contamination, missing classification, unsupported severity, scenario/lifecycle/safety/permission/source-of-truth/custody risks and standards applicability. HARD FAIL if omitted.

## Gate 11 — Functions/Rules/Traceability
REQ/BR/FN/HSR/CR/WA/TBD/AC correctly classified; only explicit confirmation promotes requirement/business rule.

## Gate 12 — Working Assumption Safety
WA reversible/labeled/non-dangerous/not false compliance/confirmation point; otherwise TBD.

## Gate 13 — Deliverable Separation
Business Source of Truth and Advisory separated. Thai-first Blueprint, Compliance Review and Expert Suggestion required by v3.7 process.

## Gate 14 — Confirmation Value
Every question states affected decision, why needed, owner, timing; no duplicate/no-value questions.

## Gate 15 — UI Handoff Readiness
Every prototype scenario declares real Entry, classification/decision gate, actor, identifier/context, material exception and end state. UI Factory must not begin only from a pre-created case when upstream stage is in scope.

## Readiness
DRAFT — insufficient for safe prototype.
PROTOTYPE READY — enough truth for discovery; unsafe effects contained; material classifications/scenarios defined.
HOSPITAL CONFIRMED — main scenarios and critical represented rules confirmed.
READY FOR DEV HANDOFF — critical classification/scenario/lifecycle/permissions/legal/order/integration/source-of-truth/AC confirmed or excluded; compliance verification recorded.

## Hard Reject
Invented Hospital Truth; invented clinical/legal/financial authority; unsupported mandatory standard; critical unresolved hidden as assumption; incoherent workflow; omitted domain baseline; missing Critical/High evidence; irrelevant speculative gap; omitted Independent Challenge; external guidance copied as hospital workflow; material scenario/classification omitted; forensic lifecycle item silently omitted.

## Factory Rule
PROTOTYPE READY enters UI Factory using Blueprint Business Source of Truth. Multiple material scenarios must each be playable and tested. UI release is additionally governed by `INTERACTION_WORKFLOW_STANDARD.md` and `PREMIUM_PRODUCT_DESIGN_GATE.md`; Blueprint PASS alone never implies Mockup PASS.