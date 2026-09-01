# Gorilla HIS — Blueprint Quality Gate v2.3

Purpose: hospital prototype discovery with broad expert challenge, strict relevance, and auditable evidence without turning AI recommendations into false requirements.

## Gate 1 — Source Truth
- Hospital-confirmed facts identified; recommendations/assumptions/TBD separate; no AI item labeled Hospital Confirmed.
**HARD FAIL:** invented requirement as hospital truth.

## Gate 2 — Expert Coverage & Domain Activation
- Expert template used; domains identified; relevant perspectives activated with reasons; unrelated roles N/A; conditional roles have trigger; standards only when applicable.
**HARD FAIL:** critical relevant perspective omitted or irrelevant role treated current-scope without trigger.

## Gate 3 — Relevance Gate
Every active GAP/question is traceable, current/direct dependency, material, actionable, and timed. Future-only concerns suppressed or conditional with trigger.
**HARD FAIL:** Critical/High GAP/question cannot explain current relevance and decision/risk changed.

## Gate 4 — Hospital System Soundness
Actors, patient/encounter context, material permissions, record/order/data boundaries, audit, exceptions, source-of-truth and downstream effects considered where relevant. Unknowns visible.

## Gate 5 — Main Workflow
Confirmed/requested flow preserved; missing steps not fabricated; recommended future flow separated; prototype coherent with safe labeled WA.

## Gate 6 — Clinical & Data Safety
No unconfirmed real medication/order/clinical action, legal/actual medical-record change, or irreversible action. Real-vs-training/draft explicit.
**HARD FAIL:** unconfirmed clinical/data effect as production truth.

## Gate 7 — Evidence Strength
For every expert-created Critical/High GAP/HSR/CR: Reviewing Agent, Evidence Basis, Trace Source, Verification Status, Confirmation Owner; severity proportionate; expert-only reasoning cannot inflate severity without reviewer acceptance.
Allowed basis: RAW REQUIREMENT / DIRECT WORKFLOW DEPENDENCY / DIRECT DOWNSTREAM EFFECT / ESTABLISHED HIS-HOSPITAL PRACTICE / AUTHORITATIVE STANDARD-LAW / STANDARD PRINCIPLE-NEED VERIFICATION / EXPERT REASONING ONLY.
**HARD FAIL:** no evidence trail or speculation as verified fact.

## Gate 8 — Standards, Privacy & Security
Relevant JCI/HA/ISO/PDPA only when applicable; HIPAA not assumed; source/topic/applicability/verification recorded; no fabricated clauses; best practice not formal requirement.
**HARD FAIL:** unsupported compliance/legal claim.

## Gate 9 — Evidence Assurance & Authoritative Source Gate — v3.3
For every expert-created Critical/High item and every formal standard/legal claim, where applicable:
- [ ] Evidence Assurance Level A/B/C/D/E recorded.
- [ ] Source Owner recorded.
- [ ] Document/Source Title recorded when external evidence is invoked.
- [ ] Edition/Version/Effective Date recorded when material to the claim.
- [ ] Section/Topic/Clause recorded only if exactly verified.
- [ ] Official Source Locator recorded for Level B/C external evidence.
- [ ] Verified Date recorded.
- [ ] Applicability recorded.
- [ ] Claim Type recorded: HOSPITAL REQUIREMENT / FORMAL REQUIREMENT / AUTHORITATIVE GUIDANCE / BEST PRACTICE / EXPERT REASONING.
- [ ] Verification Status recorded.
- [ ] Evidence Assurance was applied only AFTER Gate 3 relevance passed.
- [ ] No suppressed/irrelevant candidate was resurrected merely because a standard/source exists.
- [ ] Formal `requires/shall/mandatory/must comply` wording is used only with verified Level-B authoritative evidence + exact support + applicability.
- [ ] If formal evidence is incomplete, wording is downgraded to guidance/best-practice/standard-verification-required.

**HARD FAIL:** formal external requirement claim lacks verified authoritative source/applicability, or an authoritative source is used to manufacture relevance.

## Gate 10 — Gap Analysis Quality
Stable GAP IDs; why it matters; impact; treatment; relevance; owner; block point; Critical/High summary; duplicates removed; failed candidates suppressed.

## Gate 11 — Independent Challenge Pass
Second reviewer checks truth contamination, unsupported Critical/High, missing material risks, contradictions, irrelevant/duplicate questions, severity, conditional downstream and evidence/standards classification. Disposition recorded.
**HARD FAIL:** omitted.

## Gate 12 — Functions, Rules & Traceability
FN functions; REQ only hospital requirements; BR only confirmed rules; HSR recommendations; CR compliance recommendations; WA assumptions; TBD unresolved; AC expected behavior; advisory items trace to GAP where relevant.

## Gate 13 — Working Assumption Safety
WA labeled, reversible, non-dangerous, not false compliance claim, confirmation point assigned; otherwise TBD.

## Gate 14 — Dual Deliverable Separation
File 1 Business Source; File 2 Advisory; no silent promotion; REQ/BR promotion only with explicit hospital/user confirmation.
**HARD FAIL:** Expert Gap contaminates Hospital Truth.

## Gate 15 — Confirmation Value Gate
Every surfaced question has Decision affected, Why needed, Owner, Timing; not duplicate; cannot be safely suppressed as reversible detail.
**HARD FAIL:** no decision value/current relevance or hypothetical downstream only.

# Readiness Decision
DRAFT — insufficient for coherent/safe prototype.
PROTOTYPE READY — enough truth for discovery; recommendations/WA separated; unsafe effects contained; evidence status visible.
HOSPITAL CONFIRMED — hospital confirmed Main Workflow and critical represented rules/assumptions.
READY FOR DEV HANDOFF — critical permissions/workflow/actual record-order effects/integration/source-of-truth/AC confirmed or excluded; relevant formal compliance claims verified or explicitly marked unresolved/not applicable.

# Hard Reject
1 invented hospital requirement; 2 invented clinical logic/unsafe data effect; 3 invented standard/law clause; 4 HIPAA assumed; 5 critical issue hidden; 6 WA promoted; 7 incoherent workflow; 8 critical expert omitted; 9 advisory contaminates truth; 10 artifact missing; 11 Critical/High no evidence; 12 irrelevant/speculative question; 13 conditional downstream treated current; 14 independent challenge omitted; 15 no confirmation decision value; 16 formal requirement without Level-B authoritative verification/applicability; 17 authoritative source used to manufacture relevance; 18 best-practice/guidance mislabeled formal requirement; 19 stale/unverified edition or clause presented as verified.

# Factory Rule
PROTOTYPE READY may enter UI Factory only as Discovery Prototype using File 1 as Business Source of Truth. File 2 is challenge/review/confirmation input, not automatic UI/Dev requirement. READY FOR DEV HANDOFF remains subject to normal project governance and technical/clinical validation.
