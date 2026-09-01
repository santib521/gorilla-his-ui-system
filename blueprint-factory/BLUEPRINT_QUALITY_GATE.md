# Gorilla HIS — Blueprint Quality Gate v2.2

Purpose: allow fast hospital prototype discovery while using broad hospital/HIS expert challenge without turning AI recommendations into false hospital requirements or low-value questions.

## Gate 1 — Source Truth
- [ ] Hospital-confirmed facts are clearly identified.
- [ ] Recommendations, assumptions and TBD are separated.
- [ ] No AI/expert-created item is labeled Hospital Confirmed.

**HARD FAIL:** invented requirement presented as hospital truth.

## Gate 2 — Expert Coverage & Domain Activation
- [ ] EXPERT_GAP_ANALYSIS_TEMPLATE.md was used.
- [ ] Module domain(s) were identified.
- [ ] Relevant expert perspectives were activated with reasons.
- [ ] Unrelated roles are marked N/A.
- [ ] Conditional roles identify an explicit trigger.
- [ ] Relevant clinical, operational, HIM, quality/safety, HIS, integration, security/privacy perspectives were considered.
- [ ] Standards perspectives were considered only where applicable.

**HARD FAIL:** a critical relevant perspective is omitted, or irrelevant roles are treated as active current-scope owners without a traceable trigger.

## Gate 3 — Relevance Gate
For every active GAP and confirmation question:
- [ ] Traceable to REQ/BR/workflow, direct safety/data/privacy risk, direct downstream effect, or applicable standard principle.
- [ ] In current module scope or a direct dependency.
- [ ] Material enough to change workflow, permission, record/data effect, integration/source-of-truth, safety, privacy/security, financial integrity, AC or meaningful prototype decision.
- [ ] Actionable with an identifiable decision/owner.
- [ ] Timing is justified: Prototype / Before Dev / Later.
- [ ] Future-only concerns are suppressed or marked CONDITIONALLY RELEVANT with explicit trigger.

**HARD FAIL:** a Critical/High GAP or surfaced hospital question cannot explain why it is relevant to the current module and what decision/risk it changes.

## Gate 4 — Hospital System Soundness
- [ ] Main users/actors known enough for intended prototype.
- [ ] Patient/encounter context handled when relevant.
- [ ] Permission/authorization gaps identified when material.
- [ ] Clinical documentation/order/data-source boundaries identified when relevant.
- [ ] Audit/accountability/history considered when material.
- [ ] Exceptions/correction/cancellation/reversal considered when relevant.
- [ ] Source-of-truth and downstream effects considered.

Unknowns may be Recommendation/WA/TBD; must not be hidden.

## Gate 5 — Main Workflow
- [ ] Hospital-confirmed/requested workflow preserved.
- [ ] Missing workflow steps not fabricated as confirmed.
- [ ] Recommended Future Flow separated from Hospital Confirmed Flow.
- [ ] Prototype can demonstrate coherent flow using confirmed facts + safe labeled WA.

## Gate 6 — Clinical & Data Safety
- [ ] No unconfirmed assumption causes real medication/order/clinical action.
- [ ] No unconfirmed assumption changes legal/actual medical record.
- [ ] No unsafe irreversible action invented.
- [ ] Real-vs-training/draft/preview effects explicit.
- [ ] Patient identification/handoff/safety implications reviewed when relevant.

**HARD FAIL:** unconfirmed clinical/data effect treated as production truth.

## Gate 7 — Evidence Strength
For every expert-created CRITICAL/HIGH GAP, HSR or CR:
- [ ] Reviewing Agent recorded.
- [ ] Evidence Basis recorded.
- [ ] Trace Source recorded.
- [ ] Verification Status recorded.
- [ ] Confirmation Owner recorded.
- [ ] Severity is proportionate to evidence and risk.
- [ ] EXPERT REASONING ONLY is not used to inflate severity without explicit reviewer acceptance.

Allowed Evidence Basis:
- RAW REQUIREMENT
- DIRECT WORKFLOW DEPENDENCY
- DIRECT DOWNSTREAM EFFECT
- ESTABLISHED HIS / HOSPITAL PRACTICE
- AUTHORITATIVE STANDARD / LAW
- STANDARD PRINCIPLE — NEED VERIFICATION
- EXPERT REASONING ONLY

**HARD FAIL:** Critical/High expert-created item has no evidence trail, or speculative reasoning is presented as verified fact.

## Gate 8 — Standards, Privacy & Security
- [ ] Relevant JCI/HA/ISO/PDPA considerations reviewed only where applicable.
- [ ] HIPAA applicability not assumed merely because this is HIS.
- [ ] Compliance claims identify source/topic/applicability/verification status.
- [ ] No fabricated clause numbers or unsupported mandatory claims.
- [ ] Best practice not mislabeled as formal requirement.

**HARD FAIL:** unsupported compliance/legal claim.

## Gate 9 — Gap Analysis Quality
- [ ] Gaps use GAP-xx.
- [ ] Each important gap explains why it matters.
- [ ] Impact is CRITICAL/HIGH/MEDIUM/LOW.
- [ ] Treatment is HSR/CR/WA/TBD.
- [ ] Relevance is DIRECT or CONDITIONAL.
- [ ] Confirmation owner identified.
- [ ] Blocking point identified.
- [ ] Critical/High gaps visible in summary.
- [ ] Duplicate gaps removed.
- [ ] Candidate issues that failed relevance are suppressed, not turned into questions.

## Gate 10 — Independent Challenge Pass
- [ ] Second-pass reviewer challenged the first-pass result.
- [ ] Reviewer checked Hospital Truth contamination.
- [ ] Reviewer checked unsupported Critical/High items.
- [ ] Reviewer checked missing material safety/permission/source-of-truth risks.
- [ ] Reviewer checked contradictions.
- [ ] Reviewer actively removed irrelevant/duplicate/low-value questions.
- [ ] Reviewer challenged overstated severity.
- [ ] Reviewer verified conditional downstream concerns are not presented as current requirements.
- [ ] Disposition recorded: ACCEPT / DOWNGRADE / RECLASSIFY / SUPPRESS / NEEDS VERIFICATION.

**HARD FAIL:** Independent Challenge Pass is omitted for a completed run.

## Gate 11 — Functions, Rules & Traceability
- [ ] FN-xx functions.
- [ ] REQ-xx only hospital requirements.
- [ ] BR-xx only confirmed business rules.
- [ ] HSR-xx recommendations.
- [ ] CR-xx compliance recommendations.
- [ ] WA-xx prototype assumptions.
- [ ] TBD-xx unresolved gaps/conflicts.
- [ ] AC-xx important expected behavior.
- [ ] Blueprint recommendations/WA/TBD reference originating GAP when relevant.

## Gate 12 — Working Assumption Safety
Every WA must be clearly labeled, reversible, non-clinically dangerous, not a false compliance claim, and assigned a confirmation point. Otherwise convert to TBD.

## Gate 13 — Dual Deliverable Separation
- [ ] File 1 Application Blueprint exists.
- [ ] File 2 Expert Gap & Recommendation Analysis exists.
- [ ] File 1 clearly Business Source of Truth.
- [ ] File 2 clearly ADVISORY / CHALLENGE ANALYSIS.
- [ ] Expert recommendations did not silently become REQ/BR.
- [ ] Items promoted to REQ/BR have explicit hospital/user confirmation.

**HARD FAIL:** Expert Gap Analysis contaminates Hospital Truth without classification/confirmation.

## Gate 14 — Confirmation Value Gate
Every surfaced question must have:
- [ ] Decision affected.
- [ ] Why answer is needed.
- [ ] Confirmation owner.
- [ ] Timing: Before Dev / Prototype Review / Later Refinement.
- [ ] It is not duplicative.
- [ ] It cannot be safely suppressed as a reversible prototype detail.

**HARD FAIL:** hospital is asked to confirm a question with no clear decision value, no current relevance, or only hypothetical downstream scope.

# Readiness Decision

## DRAFT
Insufficient information to build coherent/safe prototype even with reversible labeled assumptions.

## PROTOTYPE READY
Enough hospital truth exists for discovery mockup. Recommendations/WA separated. Critical unsafe effects safely contained. Expert Gap Analysis may still contain unresolved recommendations that passed relevance/evidence gates.

## HOSPITAL CONFIRMED
Hospital reviewed/confirmed Main Workflow and critical rules/assumptions represented in Blueprint.

## READY FOR DEV HANDOFF
Critical permissions, workflow, actual record/order effects, integration/source-of-truth behavior and acceptance criteria confirmed or explicitly excluded. Relevant compliance claims have verification status.

# Hard Reject
1. AI/expert recommendation disguised as hospital requirement.
2. Invented clinical logic or unsafe data effect.
3. Invented standard/law clause or unsupported mandatory claim.
4. HIPAA applicability assumed without basis.
5. Critical unresolved issue hidden as assumption.
6. Working Assumption silently promoted to Dev requirement.
7. Main Workflow cannot be explained coherently.
8. Critical relevant hospital perspective omitted.
9. Expert Gap Analysis silently contaminates Blueprint truth.
10. One mandatory artifact missing.
11. Critical/High GAP has no evidence trail.
12. Irrelevant/speculative GAP is surfaced as current hospital question.
13. Conditional downstream effect is treated as current requirement without trigger.
14. Independent Challenge Pass omitted.
15. Confirmation question has no decision value.

# Factory Rule
`PROTOTYPE READY` may enter UI Factory only as a Discovery Prototype using File 1 Application Blueprint as Business Source of Truth.
File 2 is used for challenge/review and hospital confirmation, not as automatic UI/Dev requirement.
`READY FOR DEV HANDOFF` may be treated as implementation-ready business source, subject to normal project governance and technical validation.