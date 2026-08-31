# Gorilla HIS — Blueprint Quality Gate v2.0

Purpose: allow fast hospital prototype discovery without turning AI assumptions or generic best practices into false hospital requirements.

## Gate 1 — Source Truth
- [ ] Hospital-confirmed facts are clearly identified.
- [ ] Recommendations, assumptions and TBD are separated.
- [ ] No AI-created item is labeled Hospital Confirmed.

**HARD FAIL:** invented requirement presented as hospital truth.

## Gate 2 — Hospital System Soundness
- [ ] Main users/actors are known enough for the intended prototype.
- [ ] Patient/encounter context is handled when relevant.
- [ ] Important permission/authorization gaps are identified.
- [ ] Clinical documentation/order/data-source boundaries are identified when relevant.
- [ ] Audit/accountability/history needs are considered when relevant.

Unknowns may be Recommendation/WA/TBD; they must not be hidden.

## Gate 3 — Main Workflow
- [ ] Hospital-confirmed workflow is preserved.
- [ ] Missing workflow steps are not fabricated as confirmed.
- [ ] Prototype can demonstrate a coherent flow using only confirmed facts + clearly labeled safe Working Assumptions.

## Gate 4 — Clinical & Data Safety
- [ ] No unconfirmed assumption causes a real medication/order/clinical action.
- [ ] No unconfirmed assumption changes the legal/actual medical record.
- [ ] No unsafe irreversible action is invented.
- [ ] Real-vs-training/draft/preview effects are explicit where relevant.

**HARD FAIL:** prototype treats an unconfirmed clinical/data effect as production truth.

## Gate 5 — Standards & Compliance
- [ ] Relevant JCI considerations reviewed where applicable.
- [ ] Relevant current HA considerations reviewed where applicable.
- [ ] Relevant ISO/IEC 27001:2022 information-security considerations reviewed where applicable.
- [ ] Compliance claims identify standard/topic and verification status.
- [ ] No fabricated clause numbers or mandatory claims.
- [ ] Best practice is not mislabeled as a formal accreditation requirement.

**HARD FAIL:** unsupported compliance claim.

## Gate 6 — Functions, Rules & Traceability
- [ ] FN-xx used for functions.
- [ ] REQ-xx only for hospital requirements.
- [ ] BR-xx only for confirmed business rules.
- [ ] HSR-xx used for hospital-system recommendations.
- [ ] CR-xx used for compliance recommendations.
- [ ] WA-xx used for prototype assumptions.
- [ ] TBD-xx used for unresolved gaps/conflicts.
- [ ] AC-xx traces important expected behavior.

## Gate 7 — Working Assumption Safety
Every WA must be:
- [ ] clearly labeled;
- [ ] reversible in prototype;
- [ ] non-clinically dangerous;
- [ ] not a false compliance claim;
- [ ] assigned a confirmation point.

If not, convert it to TBD.

## Gate 8 — Confirmation Strategy
Questions are split into:
- [ ] MUST CONFIRM BEFORE DEV
- [ ] CONFIRM DURING PROTOTYPE REVIEW
- [ ] LATER REFINEMENT

Do not block prototype for a question that can safely be validated by showing the prototype.

# Readiness Decision

## DRAFT
Insufficient information to build a coherent/safe prototype even with reversible labeled assumptions.

## PROTOTYPE READY
Enough hospital truth exists for a discovery mockup. Recommendations and Working Assumptions are permitted and clearly separated. No unsafe unconfirmed clinical/data effect is treated as real.

## HOSPITAL CONFIRMED
Hospital has reviewed/confirmed Main Workflow and critical rules/assumptions represented in the Blueprint.

## READY FOR DEV HANDOFF
Critical permissions, workflow, actual record/order effects, integration/source-of-truth behavior and acceptance criteria are confirmed or explicitly excluded. Relevant compliance claims have verification status.

# Hard Reject
1. AI recommendation disguised as hospital requirement.
2. Invented clinical logic or unsafe data effect.
3. Invented JCI/HA/ISO clause or unsupported mandatory claim.
4. Critical unresolved issue hidden as an assumption.
5. Working Assumption silently promoted to Dev requirement.
6. Main Workflow cannot be explained coherently.

# Factory Rule
`PROTOTYPE READY` may enter UI Factory only as a **Discovery Prototype**.  
`READY FOR DEV HANDOFF` may be treated as an implementation-ready business source, subject to normal project governance and technical validation.