# Gorilla HIS — Project Session Input Standard v1.0

Status: `FACTORY MASTER`

## 1. Purpose
Keep the launcher prompt stable while allowing each Module/Project session to provide different evidence. Variable inputs always appear at the END of the launcher prompt.

Canonical session:

```text
MODULE:
[ชื่อระบบ / Module]

1. WORKFLOW PROCESS
[workflow evidence or "ยึดตาม Standard"]

2. REQUIREMENT
[hospital requirements or "ไม่มี Requirement เพิ่มเติม"]

3. ROLE
[roles or "ยึดตาม Standard"]

4. REPORT
[reports or "ยึดตาม Standard"]

5. NOTE / REFERENCE
[forms/SOP/TOR/screenshots/files/URLs/standards/current system/benchmark/pain points/constraints]
```

## 2. Workflow Process
### When hospital workflow is supplied
Treat it as Hospital Evidence according to source strength. Reconstruct:
`Trigger → Entry → Actor → Input → Validation → Decision → Action → Transaction → Handoff → Repeat/Reassess → Exception → Closure`.

Do not "improve" it silently. Compare against applicable Standard only after local reality is visible.

### When input says `ยึดตาม Standard`
This means:
1. identify the actual domain;
2. load existing verified Domain Knowledge Pack when adequate;
3. if inadequate, research authoritative sources according to Domain Knowledge Framework;
4. build `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`;
5. identify material local decisions that the Standard cannot answer;
6. create Expert Recommendations/Options and Hospital Questions;
7. prototype only within safe boundaries.

It does NOT mean "invent a plausible workflow from AI memory".

## 3. Requirement
Hospital-supplied requirement remains tagged by evidence class.

If absent / `ไม่มี Requirement เพิ่มเติม`:
- do not manufacture Hospital Requirements;
- derive Standard Recommended Functions only after relevance/applicability challenge;
- place recommendations in the correct recommendation class;
- ask only questions that change workflow, transaction, authority, data, safety, finance, integration, compliance or implementation.

## 4. Role
### Supplied roles
Preserve hospital terminology. Determine responsibility, ownership, handoff and permission; do not infer approval authority solely from title.

### `ยึดตาม Standard`
Propose a `RECOMMENDED ROLE MODEL — NOT HOSPITAL CONFIRMED` from authoritative/domain practice. Include:
`Role → Responsibility → Work Obligation → Queue → Create/Edit/Review/Approve/Reverse authority → Handoff → Audit`.

Any material authority choice becomes a Hospital Decision when not established by source/law.

## 5. Report
### Supplied reports
Capture definition, trigger, filters, grouping, source data, recipient, frequency, drilldown/export, version/amendment and access where material.

### `ยึดตาม Standard`
Expert team evaluates only applicable outputs:
- operational work reports;
- management/KPI/statistical reports;
- audit/accountability outputs;
- finance/utilization reports;
- regulatory/accreditation outputs when source-supported.

Each proposed output is `STANDARD/EXPERT RECOMMENDATION`, never Hospital Confirmed until accepted.

## 6. Note / Reference
May contain Form, SOP, TOR, screenshot, current-system walkthrough, Excel, PDF, website, law, standard, workshop note, benchmark HTML, pain point, constraint or research direction.

Classify each source before use:
`Hospital Primary Evidence / Official Authority / Accreditation or Standard Owner / Professional Guidance / Established Practice / Benchmark / Advisory`.

A visual benchmark is design evidence, not business-rule authority unless separately supported.

## 7. Expert Workshop Pool
The Factory maintains an expert pool but activates only relevant members.

Mandatory core:
- Senior HIS BA / Requirement Lead
- Hospital Workflow & Operations
- Domain Expert
- HIS Solution Architect
- Operational UX/Product
- Independent Reality/QA Challenger

Conditional:
- Data/Integration
- Finance/Revenue Cycle
- Privacy/Security
- Thai law/MOPH/regulator
- HA
- JCI
- ISO/IEC 27001
- HIPAA
- other specialty expert

Activation matrix:
`Expert/Standard | Relevance | Applicability | Material Decision | Source Needed | Activated Y/N | Reason`.

If `N`, do not generate requirements/questions from that domain.

## 8. Interview Simulation Standard
For each material workflow, experts independently challenge from their relevant perspective, then consolidate without duplicating questions.

The consolidated workshop must discover:
- what starts the work;
- what object/transaction exists;
- who owns it now/next;
- what data/evidence is needed;
- what decision occurs;
- what is waiting and why;
- what repeats over days/visits/cycles;
- what quantity/amount/entitlement changes;
- what exceptions/corrections/reversals occur;
- what closes the work;
- what remains on paper/Excel/phone/LINE;
- what must be audited/reported;
- what a Dev cannot implement safely without a Hospital decision.

## 9. Question Quality Gate
A question is allowed only if it has decision value.

Required question record:
`Q ID | Scenario | Question | Why Asked | Current Evidence | Recommendation/Options | Decision Impact | Risk | Owner | Priority | Confirm When | Status`.

Reject questions that:
- merely ask the user to repeat supplied information;
- are generic "ต้องการอะไรเพิ่มเติมไหม";
- have no implementation/operational decision impact;
- arise only because an irrelevant standard was activated.

## 10. Standard/Compliance Rule
Standards are challenge overlays, not feature generators.

For HA/JCI/ISO27001/HIPAA/Thai law or other frameworks:
1. prove applicability;
2. identify exact principle/source when material;
3. map to actual workflow/data/control;
4. classify as compliance recommendation or decision;
5. never invent a clause or local approval role.

## 11. Session Completeness Result
At the end of discovery classify each dimension:
`CONFIRMED / PARTIAL / NOT STATED / N/A / HOSPITAL DECISION REQUIRED / RECOMMENDATION AVAILABLE`.

Missing information does not automatically block a Discovery Prototype. It blocks readiness only when the unresolved decision is material to safe/correct implementation.

## 12. Final Rule
**A sparse Project Session should trigger stronger expert discovery, not stronger invention.**

`No local input → source-backed baseline + explicit recommendations + decision-valued questions`, never `AI guess → Hospital Truth`.