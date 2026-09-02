# Gorilla HIS — Template การวิเคราะห์ช่องว่างและข้อเสนอแนะโดยผู้เชี่ยวชาญ v1.4

**Module / Application:**  
**Analysis Version:** v0.x  
**Related Blueprint:**  
**Document Type:** ADVISORY / REQUIREMENT DISCOVERY / CHALLENGE ANALYSIS — **ยังไม่ถือเป็น HOSPITAL CONFIRMED**

> ภาษาหลักคือภาษาไทย คงคำศัพท์ HIS/Clinical/Technical ภาษาอังกฤษเมื่อชัดกว่า

## 1. Executive Summary
- Requirement ที่ชัดเจน/แข็งแรง:
- Critical/High decisions ที่ยังไม่ Confirm:
- จำนวน Workshop Questions แยก Critical/High/Medium:
- ผลต่อ Prototype:
- ผลต่อ Dev Handoff:

## 2. Domain Classification & Expert Coverage
| มุมมอง / Agent | สถานะ | เหตุผล / Trigger | ประเด็นที่ตรวจ |
|---|---|---|---|
| Domain Expert / Thai Workflow | | | |
| Senior HIS BA / Clinical Informatics | | | |
| Registration / Patient Access | | | |
| Medical Records / HIM | | | |
| Physician / Clinical | | | |
| Nursing / Operations | | | |
| Lab / Blood Bank | | | |
| Radiology / PACS | | | |
| Finance / Billing | | | |
| Integration / Source of Truth | | | |
| Privacy / Security / Audit | | | |
| Quality / Patient Safety | | | |
| Forensic Medicine / Mortuary | RELEVANT / N/A | activate only for forensic/mortuary scope | classification, identity, custody, report/body/evidence/handover |
| HA / HAI | | | |
| JCI | | | |
| Thailand PDPA / Local Privacy | | | |

## 3. Legal / Operational Case Classification
| Classification ID | Case Type / Trigger | Actor / Authority | Required Evidence / Data | Workflow Branch | End State | Source | Local Confirmation |
|---|---|---|---|---|---|---|---|
| CLS-01 | | | | | | | |

## 4. Standard Domain Workflow Understanding
`Start / Classification → Entry → ... → Exception / Alternate Route → Closure`

### Actors / Handoffs
| ขั้นตอน | ผู้ปฏิบัติ | Input | Action / Decision | Output / Record | ผู้รับช่วงถัดไป | Evidence |
|---|---|---|---|---|---|---|
| | | | | | | |

## 5. Expert Requirement Discovery Coverage Matrix — Mandatory
Disposition every applicable dimension as `COVERED / PARTIAL / NOT STATED / N/A / NEED HOSPITAL CONFIRMATION`.

| Discovery Dimension | Status | Raw Requirement Trace | Missing Decision / Exception | Question IDs |
|---|---|---|---|---|
| Scope / case eligibility / classification | | | | |
| Entry / request / referral / trigger | | | | |
| Requester / actor authority | | | | |
| Accept / Reject / Return / Redirect | | | | |
| Identity / case / encounter / episode | | | | |
| Ownership / assignment / roster / handoff | | | | |
| Core professional workflow | | | | |
| Approval / dual review / decision points | | | | |
| Documents / forms / media / signatures | | | | |
| Orders / results / external services | | | | |
| Evidence / specimen / physical custody | | | | |
| State / lifecycle / reopen / correction / cancellation | | | | |
| Exception / missing data / duplicate / wrong identity | | | | |
| Integration / source of truth / timing | | | | |
| Downtime / manual continuity / reconciliation | | | | |
| Finance / payer / waive / refund / reversal | | | | |
| Privacy / masking / reveal / print / export | | | | |
| Audit / accountability | | | | |
| Reporting / statistics / definitions | | | | |
| Closure / handover / release / archive | | | | |
| SLA / priority / escalation | | | | |
| Configuration / numbering / template / master data | | | | |
| Search / history / version / amendment | | | | |
| Operational usability / worklist / next action | | | | |

## 6. Workshop Question Bank — Mandatory
Do not ask generic questions. Each question must narrow a real decision and, when possible, offer an expert recommendation or decision options.

| Question ID | Domain / Scenario | Workflow Stage | คำถาม | ทำไมต้องถาม | Requirement ปัจจุบันบอกอะไร | Expert Recommendation / Options | Decision Affected | Risk if Unconfirmed | Confirmation Owner | Priority | Confirm When | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Q-001 | | | | | | | | | | CRITICAL/HIGH/MEDIUM/LOW | | OPEN / ANSWERED / RECOMMENDATION AVAILABLE / HOSPITAL DECISION REQUIRED / DEFERRED / N/A |

### Question Quality Rule
Each question must classify missing information as one of:
1. `ALREADY ANSWERED` — do not ask again.
2. `EXPERT RECOMMENDATION AVAILABLE` — Expert proposes a concrete option for hospital confirmation.
3. `HOSPITAL DECISION REQUIRED` — local policy/legal/integration/finance/privacy/role authority cannot be guessed.

## 7. Decision Tree & Exception Challenge
For every material main action challenge:
`Precondition → Valid Action → Invalid Action → Alternate Route → Exception → Cancel/Reverse → Correct/Amend → Reopen/Re-entry → Handoff → Closure`.

| Workflow Action | Preconditions | Alternate / Invalid Route | Exception | Cancel / Reverse | Correct / Amend | Reopen | Related Q/GAP |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## 8. Role Interview Lens
| Role | Worklist / Trigger | Information Needed | Allowed Actions | Blocked Action / Reason | Handoff | Recovery / Search Need | Question IDs |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## 9. Data / Source-of-Truth Interview Lens
| Object / Record | Creator | Primary ID | Editable / Immutable Boundary | Correction Authority | Version History | Source of Truth | Conflict / Reconciliation | Q/GAP |
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |

## 10. Gap Register — Surviving Gaps Only
| ID | ด้าน | Gap / Risk | Trace Source | Relevance | ทำไมสำคัญ | Impact | Evidence Basis | Verification | Classification | Confirmation Owner | Related Question IDs | Blocks |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| GAP-01 | | | | DIRECT / CONDITIONAL | | CRITICAL/HIGH/MEDIUM/LOW | | | HSR/CR/WA/TBD | | | Prototype/Dev/Neither |

## 11. Independent Challenge Review
Reviewer must ask: **ถ้ามีผู้เชี่ยวชาญ Domain ในประเทศไทยและ User ที่ทำงานจริงนั่งอยู่ตรงนี้ เขาจะทักว่ายังขาดอะไร?**

| Ref | Reviewer Challenge | Missing Question / Gap? | Disposition | เหตุผล |
|---|---|---|---|---|
| | | | ACCEPT / DOWNGRADE / RECLASSIFY / SUPPRESS / ADD QUESTION / NEEDS VERIFICATION | |

## 12. Cross-Department / Upstream-Downstream Impact
| หน่วยงาน / ระบบ | Effect Type | Trigger / Evidence | ผลกระทบ | Gap / Recommendation / Question |
|---|---|---|---|---|
| | DIRECT / CONDITIONAL | | | |

## 13. Clinical / Domain Safety Review
- Patient/deceased identification/context:
- Medication/Order effect:
- Documentation ownership / actual record effect:
- Evidence/specimen integrity when relevant:
- Physical-object/body movement/release when relevant:
- Critical result/alert/escalation:
- Handoff/continuity:
- Correction/cancellation/reversal:

## 14. Permission / Accountability Review
| Action | Create | Edit | Review | Approve | Cancel / Reverse | Audit | Evidence / Question / Gap |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## 15. Data / Integration / Source-of-Truth Review
| Data / Object | Source of Truth | Producer | Consumer | Timing | Failure / Exception | Evidence / Question / Gap |
|---|---|---|---|---|---|---|
| | | | | | | |

## 16. Finance Review
Challenge payer, charge basis, chargeable/non-charge, waive/exempt, posting, cancellation, refund/reversal and reconciliation only where relevant.

## 17. Privacy / Security Review
Challenge Minimum Necessary Access, sensitive-data classification, masking/reveal, print/export/download, authentication/authorization, audit, disclosure, retention, correction and downtime only where relevant.

## 18. Standards / Governance Review
| มาตรฐาน / แหล่งอ้างอิง | Applicability | Topic / Principle | Evidence Source | Recommendation | Verification |
|---|---|---|---|---|---|
| Thai Domain Authority | | | | | |
| HA / HAI | | | | | |
| JCI | | | | | |
| ISO/IEC 27001:2022 | | | | | |
| Thailand PDPA / Local Privacy | | | | | |

### 18A. Authoritative Source Registry
| Source Organization | Document / Resource | Source Type | Publication / Effective Date | Topic / Principle | Applicability | Verification | URL / Repo Ref |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## 19. Recommended Future Flow
Separate clearly from Hospital Confirmed Flow; every added step references HSR/CR/WA/TBD and related Question IDs.

## 20. Recommended Requirements / Controls
| Ref | ข้อเสนอแนะ | Trace / Evidence | Risk ที่แก้ | Priority | Proposed Classification | Related Question IDs | Verification |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## 21. Confirmation Prioritization
### MUST CONFIRM BEFORE DEV
| Question ID | Decision affected | Why needed | Owner | Timing |
|---|---|---|---|---|
| | | | | |

### CONFIRM DURING PROTOTYPE REVIEW
| Question ID | Decision affected | Why needed | Owner | Timing |
|---|---|---|---|---|
| | | | | |

### SAFE TO DEFER
| Question ID | Why safe to defer | Trigger / Timing |
|---|---|---|
| | | |

## 22. Expert Panel Conclusion
- สามารถทำ Prototype ต่อได้: Yes / No / Conditional
- Critical/High gaps:
- Open Critical/High Workshop Questions:
- Discovery dimensions incomplete:
- Questions suppressed because already answered/irrelevant:
- ความเสี่ยงสำคัญที่สุด:
- หัวข้อ Workshop รอบถัดไป:

> Expert output is advisory. A recommendation/question becomes Hospital Requirement / Business Rule only after explicit hospital confirmation and Blueprint update.