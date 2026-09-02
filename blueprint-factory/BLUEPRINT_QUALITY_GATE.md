# Gorilla HIS — Blueprint Quality Gate v2.5

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
- [ ] Domain Standard Flow Baseline present and labeled `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`.
- [ ] Hospital Requirement Overlay uses MATCHED / PARTIAL / NOT STATED / CONFLICT / N/A.
- [ ] Standards Overlay occurs after baseline + hospital overlay.
- [ ] Domain guidance not silently promoted to local workflow.

**HARD FAIL:** baseline ignored/converted to Hospital Truth or standards used to manufacture scope.

### Gate 5A — Scenario Branch Completeness
- [ ] materially distinct entry scenarios identified separately;
- [ ] each scenario has Entry Trigger, Identifier/Context, Starting Actor, Handoffs, Source-of-Truth, Exceptions, End State, Hospital Coverage;
- [ ] scenarios changing identity/source-of-truth/authorization/custody/handoff are not collapsed into one generic flow;
- [ ] Prototype Scenario Coverage lists branches UI Factory must play end-to-end.

**HARD FAIL:** material in-scope scenario missing/collapsed.

## Gate 6 — Clinical, Data & Domain Safety
No unconfirmed assumption causes real medication/order/clinical/legal-record effect or unsafe irreversible action.

Forensic: deceased identification, evidence/specimen integrity, body movement/release, sensitive handoff, HN/AF/VN/Encounter/order/result relationship and external-body-without-HN path reviewed.

**HARD FAIL:** unconfirmed clinical/data/legal effect treated as production truth.

## Gate 7 — Evidence Strength
Every expert-created Critical/High GAP/HSR/CR records Reviewing Agent, Evidence Basis, Trace Source, Verification, Confirmation Owner; severity proportionate.

Allowed basis includes AUTHORITATIVE DOMAIN GUIDANCE.

**HARD FAIL:** no evidence trail or speculation presented as verified fact.

## Gate 8 — Standards, Privacy, Security & Domain Authority
Relevant JCI/HA/ISO/PDPA and domain authorities reviewed only where applicable; HIPAA not assumed; claims record source/topic/applicability/verification; no fabricated clauses/mandatory claims.

### Gate 8A — Forensic Standard Compliance Review
- [ ] Forensic Compliance Coverage Matrix exists.
- [ ] MOPH/CIFS/current applicable HA/applicable Thai authority and Hospital SOP/forms considered.
- [ ] JCI considered when hospital adopts/requests JCI benchmark.
- [ ] source record contains organization, resource, source type, publication/effective status if known, topic, applicability, verification, URL/ref.
- [ ] tested: deceased/case identity; internal vs external entry; body custody/movement/release; evidence/specimen chain of custody; photography/media; report governance; diagnostic source-of-truth; sensitive access/disclosure; handover/audit/history; correction/amendment.
- [ ] external guidance not presented as hospital-local workflow/role/field/retention/release rule.
- [ ] old/background sources not called current law/standard without verification.
- [ ] Wikipedia/social media/marketing not authoritative for Critical/High claims.

**HARD FAIL:** forensic Critical/High has no authoritative trail or external manual silently becomes Hospital Truth.

### Gate 8B — Forensic Case Lifecycle Challenge — Mandatory
For every forensic run explicitly review and disposition all items below as `COVERED / PARTIAL / GAP / N/A / NEED HOSPITAL CONFIRMATION`:

1. **Living forensic patient exists?** Clinical Forensic / Forensic OPD separated from deceased flow.
2. **Request origin:** internal hospital requester vs police/external requester; requester authority/document/reference.
3. **Accept / Reject / Return-for-information:** whether intake may reject/return, reason, actor, notification and audit.
4. **AF / HN / VN / Encounter model:** AF-only, historical HN link, living HN/VN, unknown identity.
5. **HN Link Governance:** match evidence, link/unlink/correction, whether approval/dual review is required by hospital policy, audit/reversal.
6. **Physician duty/exam roster:** assignment, coverage, substitute/consult and unavailable path when operationally relevant.
7. **Diagnostic Order Context:** whether Lab/Radiology requires HN/VN/Encounter; AF-only order must not be assumed.
8. **Finance:** chargeable/non-charge, payer, HN/VN/AF billing context, posting/reversal, scenario differences.
9. **Sensitive identity/name masking:** worklist masking, restricted photos/docs, role-based reveal, print/export/download and access audit.

For each `PARTIAL/GAP/NEED HOSPITAL CONFIRMATION`, decide whether it passes Relevance Gate and whether it belongs in MUST CONFIRM BEFORE DEV or Prototype Review.

**HARD FAIL:** any of the nine lifecycle topics is silently omitted without explicit N/A/relevance reasoning.

## Gate 9 — Gap Analysis Quality
GAP IDs; why matters; impact; treatment; relevance; owner; blocking; Critical/High visible; duplicates removed; failed candidates suppressed.

## Gate 10 — Independent Challenge Pass
Second-pass reviewer checks truth contamination, unsupported Critical/High, missing material scenario/lifecycle point, missing safety/permission/source-of-truth risks, contradictions, irrelevant/duplicate questions, severity and standards applicability.

**HARD FAIL:** omitted.

## Gate 11 — Functions, Rules & Traceability
FN/REQ/BR/HSR/CR/WA/TBD/AC correctly classified; recommendations/assumptions reference gaps; only explicit confirmation promotes REQ/BR.

## Gate 12 — Working Assumption Safety
Every WA reversible, labeled, non-dangerous, not false compliance, assigned confirmation point; otherwise TBD.

## Gate 13 — Dual Deliverable Separation
File 1 Business Source of Truth and File 2 Advisory both exist; no silent contamination.

**HARD FAIL:** contamination/missing artifact.

## Gate 14 — Confirmation Value Gate
Every question states decision affected, why needed, owner, timing; not duplicate and cannot safely be suppressed.

**HARD FAIL:** no decision value/current relevance.

# Readiness Decision
DRAFT — insufficient for safe prototype.
PROTOTYPE READY — enough truth for discovery mockup; domain baseline/requirements/standards separated; in-scope scenarios and lifecycle coverage defined; unsafe effects contained.
HOSPITAL CONFIRMED — hospital confirmed main scenarios and critical represented rules/assumptions.
READY FOR DEV HANDOFF — critical scenario/lifecycle flows, permissions, record/order/legal effects, integration/source-of-truth/AC confirmed or excluded; compliance verification recorded.

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
16 Forensic compliance review omitted.
17 External forensic guidance presented as hospital-local truth.
18 Material scenario branch omitted/collapsed.
19 Prototype coverage misses in-scope material scenario.
20 Any Forensic Case Lifecycle Challenge item silently omitted.

# Factory Rule
PROTOTYPE READY may enter UI Factory only using File 1 as Business Source of Truth. File 2 is advisory.

If File 1 lists multiple in-scope material scenarios, UI Factory must make each scenario playable end-to-end and test each separately before Post-Build PASS.