# Gorilla HIS — Blueprint Quality Gate v2.3

Purpose: allow fast hospital prototype discovery while using broad hospital/HIS expert challenge without turning AI recommendations into false hospital requirements or low-value questions.

## Gate 1 — Source Truth
Hospital-confirmed facts clearly identified; recommendations/assumptions/TBD separated; no AI-created Hospital Confirmed. HARD FAIL: invented requirement presented as hospital truth.

## Gate 2 — Expert Coverage & Domain Activation
Expert template used; module domains identified; relevant perspectives activated with reasons; unrelated roles N/A; conditional triggers explicit; standards only where applicable. Forensic/Mortuary domain must activate Forensic Medicine/Mortuary review. HARD FAIL: critical relevant perspective omitted.

## Gate 3 — Relevance Gate
Every GAP/question is traceable, in current scope/direct dependency, material, actionable, and timed; future-only items suppressed/conditional. HARD FAIL: Critical/High or question cannot explain current relevance and decision/risk changed.

## Gate 4 — Hospital System Soundness
Users/actors known enough; context handled; permission, documentation/order/data boundaries, audit, exceptions, source-of-truth and downstream effects reviewed where relevant.

## Gate 5 — Main Workflow
Requested workflow preserved; missing steps not fabricated; recommended future flow separate; prototype coherent using confirmed facts + safe labeled assumptions.

## Gate 6 — Clinical, Data & Forensic Safety
No unconfirmed assumption causes real medication/order/clinical/legal-record effect or unsafe irreversible action. Patient/deceased identification, evidence/specimen integrity, body movement/release and sensitive handoff reviewed when relevant. HARD FAIL: unconfirmed clinical/data/legal effect treated as production truth.

## Gate 7 — Evidence Strength
Every expert-created Critical/High GAP/HSR/CR records Reviewing Agent, Evidence Basis, Trace Source, Verification, Confirmation Owner; severity proportionate. HARD FAIL: no evidence trail or speculation presented as verified fact.

## Gate 8 — Standards, Privacy, Security & Domain Authority
Relevant JCI/HA/ISO/PDPA and domain authorities reviewed only where applicable; HIPAA not assumed; claims record source/topic/applicability/verification; no fabricated clauses/mandatory claims; best practice not mislabeled formal requirement.

### Gate 8A — Forensic Standard Compliance Review — Mandatory for Forensic/Mortuary
- [ ] Forensic Compliance Coverage Matrix exists.
- [ ] MOPH/CIFS/HA/applicable Thai authority and Hospital SOP/forms were considered as relevant source families.
- [ ] Authoritative Source Registry records organization, document/resource, source type, date/effective status if known, topic, applicability, verification and URL/ref.
- [ ] At minimum relevant topics were tested: deceased/case identity; body custody/movement/release; evidence/specimen chain of custody; forensic photography/media; report governance; diagnostic source-of-truth; sensitive access/disclosure; handover/audit/history; correction/amendment.
- [ ] External guidance is not presented as the hospital's local workflow/role/field/retention/release rule without confirmation.
- [ ] Old/background sources are not called current law/standard without verification.
- [ ] Wikipedia/social media/marketing sources are not used as authoritative evidence for Critical/High compliance claims.
- [ ] Principle-level evidence uses `PRINCIPLE VERIFIED — LOCAL IMPLEMENTATION NEEDS HOSPITAL CONFIRMATION` where appropriate.

**HARD FAIL:** forensic Critical/High compliance claim has no authoritative source trail, or an external forensic manual is silently converted into Hospital Truth.

## Gate 9 — Gap Analysis Quality
GAP IDs; why matters; impact; treatment; relevance; owner; blocking; Critical/High visible; duplicates removed; failed candidates suppressed.

## Gate 10 — Independent Challenge Pass
Second-pass reviewer checks truth contamination, unsupported Critical/High, missing material risks, contradictions, irrelevant/duplicate questions, severity, conditional concerns, standards applicability; disposition recorded. HARD FAIL if omitted.

## Gate 11 — Functions, Rules & Traceability
FN/REQ/BR/HSR/CR/WA/TBD/AC IDs correctly classified; recommendations/assumptions reference gaps; only explicit confirmation promotes REQ/BR.

## Gate 12 — Working Assumption Safety
Every WA reversible, clearly labeled, non-dangerous, not false compliance, and assigned confirmation point; otherwise TBD.

## Gate 13 — Dual Deliverable Separation
File 1 Business Source of Truth and File 2 Advisory both exist; no silent contamination; promotion requires explicit confirmation. HARD FAIL on contamination/missing artifact.

## Gate 14 — Confirmation Value Gate
Every question states decision affected, why needed, owner, timing; not duplicate and cannot safely be suppressed. HARD FAIL: no decision value/current relevance.

# Readiness Decision
DRAFT — insufficient for safe prototype.
PROTOTYPE READY — enough truth for discovery mockup; recommendations/WA separate; unsafe effects contained.
HOSPITAL CONFIRMED — hospital confirmed main workflow and critical represented rules/assumptions.
READY FOR DEV HANDOFF — critical permissions/workflow/actual record-order-legal effects/integration/source-of-truth/AC confirmed or excluded; relevant compliance verification recorded.

# Hard Reject
1 AI recommendation disguised as hospital requirement.
2 Invented clinical logic/unsafe data effect.
3 Invented standard/law clause or unsupported mandatory claim.
4 HIPAA assumed without basis.
5 Critical unresolved issue hidden as assumption.
6 WA silently promoted.
7 Main workflow incoherent.
8 Critical relevant perspective omitted.
9 Expert analysis contaminates Blueprint truth.
10 Mandatory artifact missing.
11 Critical/High no evidence trail.
12 Irrelevant/speculative current question.
13 Conditional downstream effect treated current without trigger.
14 Independent Challenge omitted.
15 Question no decision value.
16 Forensic compliance review omitted when forensic/mortuary domain is active.
17 External forensic guidance presented as hospital-local truth without confirmation.

# Factory Rule
PROTOTYPE READY may enter UI Factory only as Discovery Prototype using File 1 as Business Source of Truth. File 2 is challenge/confirmation input, not automatic UI/Dev requirement. READY FOR DEV HANDOFF remains subject to project governance and technical validation.