# Gorilla HIS — Blueprint Quality Gate v2.1

Purpose: allow fast hospital prototype discovery while using broad hospital/HIS expert challenge without turning AI recommendations into false hospital requirements.

## Gate 1 — Source Truth
- [ ] Hospital-confirmed facts are clearly identified.
- [ ] Recommendations, assumptions and TBD are separated.
- [ ] No AI/expert-created item is labeled Hospital Confirmed.

**HARD FAIL:** invented requirement presented as hospital truth.

## Gate 2 — Expert Coverage
- [ ] `EXPERT_GAP_ANALYSIS_TEMPLATE.md` was used.
- [ ] Relevant clinical, operational, financial, HIM, quality/safety, HIS, integration, security/privacy perspectives were considered.
- [ ] JCI / HA / ISO 27001 were considered where relevant.
- [ ] HIPAA was considered only if applicable or explicitly used as a benchmark.
- [ ] Thailand PDPA/privacy perspective was considered when personal data is involved.
- [ ] Coverage Matrix marks each perspective RELEVANT / N/A / NEEDS REVIEW with reason.
- [ ] Relevant upstream/downstream departments and handoffs were reviewed.

**HARD FAIL:** obvious critical hospital perspective is omitted and the omission could hide patient-safety, legal-record, authorization, privacy/security, financial or integration risk.

## Gate 3 — Hospital System Soundness
- [ ] Main users/actors are known enough for intended prototype.
- [ ] Patient/encounter context is handled when relevant.
- [ ] Important permission/authorization gaps are identified.
- [ ] Clinical documentation/order/data-source boundaries are identified when relevant.
- [ ] Audit/accountability/history needs are considered.
- [ ] Exception/error/correction/cancellation/reversal paths are considered when relevant.
- [ ] Source-of-truth and downstream effects are considered.

Unknowns may be Recommendation/WA/TBD; they must not be hidden.

## Gate 4 — Main Workflow
- [ ] Hospital-confirmed/requested workflow is preserved.
- [ ] Missing workflow steps are not fabricated as confirmed.
- [ ] Recommended Future Flow is separated from Hospital Confirmed Flow.
- [ ] Prototype can demonstrate coherent flow using confirmed facts + clearly labeled safe WA.

## Gate 5 — Clinical & Data Safety
- [ ] No unconfirmed assumption causes a real medication/order/clinical action.
- [ ] No unconfirmed assumption changes legal/actual medical record.
- [ ] No unsafe irreversible action is invented.
- [ ] Real-vs-training/draft/preview effects are explicit.
- [ ] Patient identification, handoff and safety implications are reviewed where relevant.

**HARD FAIL:** unconfirmed clinical/data effect treated as production truth.

## Gate 6 — Standards, Privacy & Security
- [ ] Relevant JCI considerations reviewed where applicable.
- [ ] Relevant current HA considerations reviewed where applicable.
- [ ] Relevant ISO/IEC 27001:2022 considerations reviewed where applicable.
- [ ] HIPAA applicability is not assumed merely because this is a HIS.
- [ ] HIPAA is reviewed when legally applicable or explicitly selected as benchmark.
- [ ] Thailand PDPA/privacy is considered when relevant.
- [ ] Compliance claims identify source/topic/applicability/verification status.
- [ ] No fabricated clause numbers or unsupported mandatory claims.
- [ ] Best practice is not mislabeled as formal requirement.

**HARD FAIL:** unsupported compliance/legal claim.

## Gate 7 — Gap Analysis Quality
- [ ] Gaps use `GAP-xx`.
- [ ] Each important gap explains why it matters.
- [ ] Impact is CRITICAL / HIGH / MEDIUM / LOW.
- [ ] Proposed treatment is HSR / CR / WA / TBD as appropriate.
- [ ] Confirmation owner/perspective is identified where useful.
- [ ] Blocking point is Prototype / Dev / Neither.
- [ ] Critical/High gaps are visible in executive summary.

## Gate 8 — Functions, Rules & Traceability
- [ ] FN-xx functions.
- [ ] REQ-xx only hospital requirements.
- [ ] BR-xx only confirmed business rules.
- [ ] HSR-xx hospital-system recommendations.
- [ ] CR-xx compliance recommendations.
- [ ] WA-xx prototype assumptions.
- [ ] TBD-xx unresolved gaps/conflicts.
- [ ] AC-xx important expected behavior.
- [ ] Blueprint recommendations/WA/TBD can reference originating GAP-xx when relevant.

## Gate 9 — Working Assumption Safety
Every WA must be clearly labeled, reversible, non-clinically dangerous, not a false compliance claim and assigned a confirmation point. Otherwise convert to TBD.

## Gate 10 — Dual Deliverable Separation
- [ ] File 1 Application Blueprint exists.
- [ ] File 2 Expert Gap & Recommendation Analysis exists.
- [ ] File 1 is clearly the UI Factory Business Source of Truth.
- [ ] File 2 is clearly ADVISORY / CHALLENGE ANALYSIS.
- [ ] Expert recommendations did not silently become REQ/BR.
- [ ] Items promoted to REQ/BR have explicit hospital/user confirmation.

**HARD FAIL:** Expert Gap Analysis is merged into Hospital Truth without classification/confirmation.

## Gate 11 — Confirmation Strategy
Questions are split into:
- [ ] MUST CONFIRM BEFORE DEV
- [ ] CONFIRM DURING PROTOTYPE REVIEW
- [ ] LATER REFINEMENT

Do not block prototype for safely reversible details.

# Readiness Decision

## DRAFT
Insufficient information to build coherent/safe prototype even with reversible labeled assumptions.

## PROTOTYPE READY
Enough hospital truth exists for discovery mockup. Recommendations and WA are separated. Critical unsafe effects are safely contained. Expert Gap Analysis may still contain unresolved recommendations.

## HOSPITAL CONFIRMED
Hospital reviewed/confirmed Main Workflow and critical rules/assumptions represented in Blueprint.

## READY FOR DEV HANDOFF
Critical permissions, workflow, actual record/order effects, integration/source-of-truth behavior and acceptance criteria are confirmed or explicitly excluded. Relevant compliance claims have verification status.

# Hard Reject
1. AI/expert recommendation disguised as hospital requirement.
2. Invented clinical logic or unsafe data effect.
3. Invented JCI/HA/HIPAA/ISO/PDPA clause or unsupported mandatory claim.
4. HIPAA applicability assumed without basis.
5. Critical unresolved issue hidden as assumption.
6. Working Assumption silently promoted to Dev requirement.
7. Main Workflow cannot be explained coherently.
8. Critical relevant hospital perspective omitted.
9. Expert Gap Analysis silently contaminates Blueprint truth.
10. One of the two mandatory artifacts is missing.

# Factory Rule
`PROTOTYPE READY` may enter UI Factory only as a **Discovery Prototype** using File 1 Application Blueprint as Business Source of Truth.  
File 2 Expert Gap Analysis is used for challenge/review and hospital confirmation, not as automatic UI/Dev requirement.  
`READY FOR DEV HANDOFF` may be treated as implementation-ready business source, subject to normal project governance and technical validation.