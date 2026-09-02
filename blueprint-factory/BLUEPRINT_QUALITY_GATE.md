# Gorilla HIS — Blueprint Quality Gate v2.4

Purpose: allow fast hospital prototype discovery while using broad hospital/HIS expert challenge without turning AI recommendations, domain baselines or standards into false hospital requirements.

## Gate 1 — Source Truth
Hospital-confirmed facts clearly identified; recommendations/assumptions/TBD/domain-baseline content separated; no AI-created Hospital Confirmed.

**HARD FAIL:** invented requirement or Domain Standard Flow presented as hospital truth.

## Gate 2 — Expert Coverage & Domain Activation
Expert template used; module domains identified; relevant perspectives activated with reasons; unrelated roles N/A; conditional triggers explicit; standards only where applicable.

If a repository Domain Standard Flow baseline exists for the active domain it must be loaded.

Forensic/Mortuary domain must activate Forensic Medicine/Mortuary review and `FORENSIC_STANDARD_FLOW_BASELINE.md`.

**HARD FAIL:** critical perspective or applicable repository domain baseline omitted.

## Gate 3 — Relevance Gate
Every GAP/question is traceable, in current scope/direct dependency, material, actionable, and timed; future-only items suppressed/conditional.

A baseline step marked NOT STATED is not automatically a GAP.

**HARD FAIL:** Critical/High or question cannot explain current relevance and decision/risk changed.

## Gate 4 — Hospital System Soundness
Users/actors known enough; context handled; permission, documentation/order/data boundaries, audit, exceptions, source-of-truth and downstream effects reviewed where relevant.

## Gate 5 — Standard-Flow-First Architecture
When Domain Standard Flow exists:
- [ ] Domain Standard Flow Baseline is present and labeled `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`.
- [ ] Hospital Requirement Overlay exists using MATCHED / PARTIAL / NOT STATED / CONFLICT / N/A.
- [ ] Standards Overlay occurs after baseline + hospital overlay, not before relevance is established.
- [ ] Domain guidance has not been silently promoted to local workflow.

**HARD FAIL:** baseline ignored, baseline turned into Hospital Truth, or standards used to manufacture scope.

### Gate 5A — Scenario Branch Completeness
- [ ] materially distinct entry scenarios are identified separately;
- [ ] each scenario records Entry Trigger, Identifier/Context, Starting Actor, Handoffs, Source-of-Truth, Exceptions, End State and Hospital Coverage;
- [ ] scenarios that materially change identity/source-of-truth/authorization/custody/handoff are not collapsed into one generic happy path;
- [ ] Prototype Scenario Coverage explicitly states which in-scope branches UI Factory must play end-to-end.

**HARD FAIL:** a material in-scope scenario branch is missing or collapsed into a generic flow.

## Gate 6 — Clinical, Data & Domain Safety
No unconfirmed assumption causes real medication/order/clinical/legal-record effect or unsafe irreversible action.

Forensic when relevant: deceased identification, evidence/specimen integrity, body movement/release, sensitive handoff, HN/AF/order/result relationship and external-body-without-HN path reviewed.

**HARD FAIL:** unconfirmed clinical/data/legal effect treated as production truth.

## Gate 7 — Evidence Strength
Every expert-created Critical/High GAP/HSR/CR records Reviewing Agent, Evidence Basis, Trace Source, Verification, Confirmation Owner; severity proportionate.

Allowed basis includes AUTHORITATIVE DOMAIN GUIDANCE.

**HARD FAIL:** no evidence trail or speculation presented as verified fact.

## Gate 8 — Standards, Privacy, Security & Domain Authority
Relevant JCI/HA/ISO/PDPA and domain authorities reviewed only where applicable; HIPAA not assumed; claims record source/topic/applicability/verification; no fabricated clauses/mandatory claims; best practice not mislabeled formal requirement.

### Gate 8A — Forensic Standard Compliance Review — Mandatory for Forensic/Mortuary
- [ ] Forensic Compliance Coverage Matrix exists.
- [ ] MOPH/CIFS/current applicable HA/applicable Thai authority and Hospital SOP/forms considered.
- [ ] JCI considered only if hospital applies/adopts JCI benchmark.
- [ ] Source record has organization, document/resource, source type, publication/effective status if known, topic, applicability, verification, URL/ref.
- [ ] at minimum tested: deceased/case identity; internal vs external entry flow; body custody/movement/release; evidence/specimen chain of custody; forensic photography/media; report governance; diagnostic source-of-truth; sensitive access/disclosure; handover/audit/history; correction/amendment.
- [ ] external guidance not presented as hospital-local workflow/role/field/retention/release rule without confirmation.
- [ ] old/background sources not called current law/standard without verification.
- [ ] Wikipedia/social media/marketing not used as authoritative evidence for Critical/High compliance claims.
- [ ] principle-level evidence uses `PRINCIPLE VERIFIED — LOCAL IMPLEMENTATION NEEDS HOSPITAL CONFIRMATION` where appropriate.

**HARD FAIL:** forensic Critical/High claim has no authoritative source trail, or external forensic manual silently becomes Hospital Truth.

## Gate 9 — Gap Analysis Quality
GAP IDs; why matters; impact; treatment; relevance; owner; blocking; Critical/High visible; duplicates removed; failed candidates suppressed.

## Gate 10 — Independent Challenge Pass
Second-pass reviewer checks truth contamination, unsupported Critical/High, missing material scenario branch, missing safety/permission/source-of-truth risks, contradictions, irrelevant/duplicate questions, severity, conditional concerns, standards applicability; disposition recorded.

**HARD FAIL:** omitted.

## Gate 11 — Functions, Rules & Traceability
FN/REQ/BR/HSR/CR/WA/TBD/AC IDs correctly classified; recommendations/assumptions reference gaps; only explicit confirmation promotes REQ/BR.

## Gate 12 — Working Assumption Safety
Every WA reversible, clearly labeled, non-dangerous, not false compliance, and assigned confirmation point; otherwise TBD.

## Gate 13 — Dual Deliverable Separation
File 1 Business Source of Truth and File 2 Advisory both exist; no silent contamination; promotion requires explicit confirmation.

**HARD FAIL:** contamination or missing artifact.

## Gate 14 — Confirmation Value Gate
Every question states decision affected, why needed, owner, timing; not duplicate and cannot safely be suppressed.

**HARD FAIL:** no decision value/current relevance.

# Readiness Decision
DRAFT — insufficient for safe prototype.

PROTOTYPE READY — enough truth for discovery mockup; domain baseline/requirements/standards are separated; in-scope scenario coverage is defined; unsafe effects contained.

HOSPITAL CONFIRMED — hospital confirmed main scenario flows and critical represented rules/assumptions.

READY FOR DEV HANDOFF — critical scenario flows, permissions, actual record/order/legal effects, integration/source-of-truth/AC confirmed or excluded; compliance verification recorded.

# Hard Reject
1 AI recommendation/domain baseline disguised as hospital requirement.
2 Invented clinical logic/unsafe data effect.
3 Invented standard/law clause or unsupported mandatory claim.
4 HIPAA assumed without basis.
5 Critical unresolved issue hidden as assumption.
6 WA silently promoted.
7 Main workflow incoherent.
8 Critical perspective/domain baseline omitted.
9 Expert analysis contaminates Blueprint truth.
10 Mandatory artifact missing.
11 Critical/High no evidence trail.
12 Irrelevant/speculative current question.
13 Conditional downstream effect treated current without trigger.
14 Independent Challenge omitted.
15 Question no decision value.
16 Forensic compliance review omitted when active.
17 External forensic guidance presented as hospital-local truth.
18 Material scenario branch omitted/collapsed.
19 Prototype coverage does not include an in-scope material scenario branch.

# Factory Rule
PROTOTYPE READY may enter UI Factory only using File 1 as Business Source of Truth. File 2 is challenge/confirmation input, not automatic UI/Dev requirement.

If File 1 lists multiple in-scope material scenarios, UI Factory must make each scenario playable end-to-end and test each branch separately before Post-Build PASS.