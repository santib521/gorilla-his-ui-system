# Gorilla HIS — Expert Requirement Discovery Workshop Standard v1.0

Status: `UNIVERSAL FACTORY MASTER`

Purpose: force the Blueprint Factory to behave like an experienced Domain Expert + Senior HIS BA sitting in a real hospital requirement workshop, not merely reviewing a written requirement.

Core rule:
`Know the domain → reconstruct the real workflow → decompose every decision/exception/authority/data transition → compare Hospital Requirement → generate high-value workshop questions → prioritize → then finalize Blueprint.`

## 1. Workshop Mindset
The Expert must actively discover what the hospital has not yet stated.

For every workflow ask:
- What happens before this step?
- What event causes this step to exist?
- Who is allowed to initiate it?
- Who owns it now and who owns it next?
- What must be true before the next step is allowed?
- What can go wrong?
- Who decides when there is disagreement or ambiguity?
- What data/identifier/source-of-truth changes?
- What transaction goes to another system?
- What happens when the user needs to correct/reverse/cancel/reopen?
- What creates legal/clinical/financial/privacy risk?
- What proves the work is complete?

Mandatory challenge:
**If a real hospital user had to operate this application tomorrow, where would they stop, call another department, write on paper, use LINE/phone, or make an unsafe guess because the system requirement is incomplete?**

## 2. Discovery Dimensions — Mandatory
For every material scenario, review all applicable dimensions:
1. Scope / case eligibility / classification
2. Entry / request / referral / trigger
3. Actor / requester authority
4. Intake / validate / accept / reject / return / redirect
5. Identity / patient / case / encounter / episode
6. Ownership / assignment / roster / workload
7. Core professional workflow
8. Decision points / approval / dual review
9. Documents / forms / media / signatures
10. Orders / results / external services
11. Evidence / specimen / asset / physical-object custody where relevant
12. State model / lifecycle / reopen / correction / cancellation
13. Exception / fallback / missing data / duplicate / wrong identity
14. Integration / source of truth / transaction timing
15. Downtime / manual continuity / reconciliation when material
16. Finance / payer / charge / waive / refund / reversal
17. Privacy / sensitivity / masking / reveal / print / export / download
18. Audit / accountability / who-did-what-when
19. Reporting / statistics / definitions / denominator / source
20. Closure / handover / discharge / release / disposition / archive
21. SLA / priority / escalation where material
22. Configuration / master data / numbering / template / effective date
23. Search / historical correction / amendment / versioning
24. Operational usability / worklist / next action / bottleneck

Every dimension must be marked `COVERED / PARTIAL / NOT STATED / N/A / NEED HOSPITAL CONFIRMATION` with reason.

## 3. Question Generation Rule
Do not produce generic questions such as “ต้องการอะไรเพิ่มไหม?” or “ต้องการให้ระบบทำอย่างไร?”.

A workshop question must show expert understanding and narrow the decision.

Good pattern:
`Current Requirement → Missing Decision → Recommended Options → Risk/Impact → Question → Owner → Timing`

Example:
“Requirement ระบุว่าสามารถเชื่อม AF กับ HN ได้ แต่ยังไม่ระบุกรณีพบ HN หลาย Candidate หรือ Link ผิดคน. Expert แนะนำให้แยก Match Candidate → Verify → Confirm Link และมี correction audit. โรงพยาบาลต้องการให้ใครเป็นผู้ Confirm Link และต้องการ dual review หรือไม่?”

## 4. Mandatory Workshop Question Bank
Every Factory run must create `Workshop_Question_Bank_TH` as a distinct deliverable or a clearly separated full section in Expert Suggestion.

Minimum fields:
| Question ID | Domain/Scenario | Workflow Stage | Question | Why This Must Be Asked | Current Requirement Evidence | Expert Recommendation / Options | Decision Affected | Risk if Unconfirmed | Confirmation Owner | Priority | Confirm When | Status |

Priority:
- `CRITICAL` — identity, legal authority, patient/deceased safety, irreversible record/order/custody/release effect
- `HIGH` — workflow cannot operate reliably, ownership/integration/finance/privacy/report governance materially unclear
- `MEDIUM` — operational completeness, exception, reporting/configuration definition needed
- `LOW / REFINEMENT` — optimization that does not block safe prototype/dev

Status:
`OPEN / ANSWERED BY RAW REQUIREMENT / RECOMMENDATION AVAILABLE / HOSPITAL DECISION REQUIRED / DEFERRED / N/A`.

## 5. Quantity Is Not the Goal — Coverage Is
Do not impose an arbitrary question count. However, a complex hospital module producing only a handful of questions is suspicious and requires Independent Challenge.

The Expert must demonstrate that every material scenario and every applicable discovery dimension was challenged.

Quality is measured by:
- decision coverage;
- scenario coverage;
- exception coverage;
- absence of generic/duplicate questions;
- clear expert recommendation where a safe recommendation is possible;
- clear hospital-policy question where recommendation cannot substitute local authority.

## 6. Three-Way Classification of Missing Information
Every missing item must be classified as one of:
1. `ALREADY ANSWERED` — Hospital Requirement already determines it; do not ask again.
2. `EXPERT RECOMMENDATION AVAILABLE` — common/domain/HIS practice can propose a concrete design for hospital confirmation.
3. `HOSPITAL DECISION REQUIRED` — local policy/legal authority/integration/finance/privacy/role authority cannot be guessed.

Do not burden users with questions the Expert can responsibly narrow into a recommended option.

## 7. Decision Tree Expansion
For every important workflow action, explicitly challenge:
- Preconditions
- Valid action
- Invalid action
- Alternate route
- Exception route
- Cancellation/reversal
- Correction/amendment
- Re-entry/reopen
- Handoff
- Closure

If a main action exists without its material invalid/exception/reversal path, mark `PARTIAL`.

## 8. Role Interview Lens
For each relevant role, ask what that role needs to know/do at the moment of work:
- What appears in their worklist?
- How do they know a new task arrived?
- What information is needed before acting?
- Which actions are permitted?
- What is blocked and why?
- What happens after action?
- What must they hand over?
- What do they need to search/recover later?

Do not infer authority solely from job title.

## 9. Data Interview Lens
For each major object/record:
- Who creates it?
- What identifier is primary?
- What can be edited?
- What becomes immutable?
- Who may correct it?
- Is version history required?
- Which system is source of truth?
- What happens when systems disagree?
- What downstream records must be reconciled after correction?

## 10. Exception Workshop — Mandatory
At minimum challenge relevant categories:
- missing required information;
- wrong person/case/identifier;
- duplicate;
- late-arriving information;
- resource/person unavailable;
- role has insufficient permission;
- external interface unavailable;
- transaction failed/partial success;
- user cancels/reverses;
- case needs correction after finalization;
- handover recipient invalid/unavailable;
- unusual/special population or route;
- downtime/manual work and later reconciliation.

## 11. Workshop Deliverable Structure
The Expert output must include:
1. Domain/Scenario Coverage Summary
2. Discovery Dimension Coverage Matrix
3. Workshop Question Bank
4. Critical Decisions Before Dev
5. Questions Suitable for Prototype Review
6. Questions Safe to Defer
7. Expert Recommendations Ready for Hospital Confirmation
8. Unresolved Hospital Policy/Legal/Integration Decisions
9. Independent Challenge Findings

## 12. Blueprint Promotion Rule
Only confirmed answers may become Hospital Requirement / Business Rule.

An unanswered question may enter Blueprint only as:
- HSR / CR recommendation;
- WA if reversible and safe for prototype;
- TBD if not safe to assume.

## 13. Readiness Gate
`PROTOTYPE READY` requires:
- Workshop Question Bank exists;
- all material scenarios challenged;
- all applicable discovery dimensions dispositioned;
- Critical/High unresolved decisions visible;
- safe prototype treatment defined.

`READY FOR DEV HANDOFF` requires every Critical and implementation-blocking High question to be answered, explicitly excluded, or converted into a verified implementation rule.

HARD FAIL if:
- Expert asks only generic questions;
- important decisions are hidden inside prose without Question IDs;
- only happy path is explored;
- exception/correction/reversal is ignored;
- complex module has no evidence of role/data/integration/finance/privacy discovery;
- Blueprint is declared ready while Critical workshop decisions are undiscovered or hidden.