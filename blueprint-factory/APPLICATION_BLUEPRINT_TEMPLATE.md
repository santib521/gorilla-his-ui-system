# Gorilla HIS — Application Blueprint Template v2.4

**Blueprint Version:** v0.x / v1.x  
**Status:** DRAFT / PROTOTYPE READY / HOSPITAL CONFIRMED / READY FOR DEV HANDOFF  
**Related Expert Suggestion:** `Gorilla_HIS_<Module>_Expert_Suggestion_TH_v0.x`  
**Related Workshop Question Bank:** `Gorilla_HIS_<Module>_Workshop_Question_Bank_TH_v0.x`

> This file is the Business Source of Truth for UI Factory. Expert analysis and Workshop Questions are advisory until explicitly confirmed by the hospital.

## Evidence Classification
- `HOSPITAL CONFIRMED`
- `HOSPITAL STANDARD RECOMMENDATION`
- `COMPLIANCE RECOMMENDATION`
- `WORKING ASSUMPTION`
- `TBD`
- `REFERENCE BASELINE`

## 1. Product
**Application Name:**  
**Product:** Gorilla HIS  
**Objective:**

## 2. Users & Roles
| Role | Responsibility | Permission / Constraint | Evidence | Related Question IDs |
|---|---|---|---|---|
| | | | | |

## 3. Main Workflow — Hospital Requested / Confirmed
`Start → ... → End`
Clearly mark any step that is not Hospital Confirmed.

### 3A. Legal / Operational Case Classification
| Classification ID | Type / Trigger | Actor / Authority | Required Data / Evidence | Workflow Branch | End State | Evidence | Question IDs |
|---|---|---|---|---|---|---|---|
| CLS-01 | | | | | | | |

### 3B. Domain Standard Flow Baseline
Label: `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`

| Baseline ID | Scenario | Reference Step / Handoff | Source / Evidence | Applicability |
|---|---|---|---|---|
| SDF-01 | | | | RELEVANT / CONDITIONAL / N/A |

### 3C. Hospital Requirement Overlay / Delta
| Baseline ID / Scenario | Hospital REQ / Workflow Trace | Coverage | Hospital-Specific Difference / Missing Detail | Treatment | Question IDs |
|---|---|---|---|---|---|
| | | MATCHED / PARTIAL / NOT STATED / CONFLICT / N/A | | REQ/BR/HSR/CR/TBD/N/A | |

### 3D. Scenario Branches
| Scenario ID | Classification / Entry Trigger | Identifier / Context | Starting Actor | Core Handoffs | Source of Truth | Material Exceptions | End State | Hospital Coverage | Question IDs |
|---|---|---|---|---|---|---|---|---|---|
| SCN-01 | | | | | | | | IN SCOPE / PARTIAL / OUT OF SCOPE / TBD | |

### 3E. Role-Based Swimlane — DOCUMENT ONLY
For every material multi-role scenario, show Starting Event, Classification/Decision, Role, Activity, Handoff, System Action, Record/Source of Truth, Exception and End State.

### 3F. Prototype Scenario Coverage
| Scenario ID | Required in UI Factory? | Real Entry | End-to-End Path | Material Exception to Demonstrate | Safety / Assumption Boundary | Related Open Q IDs | Smoke Test Required |
|---|---|---|---|---|---|---|---|
| SCN-01 | Yes/No | | | | | | Yes/No |

## 4. Expert Requirement Discovery Coverage
Reference the full Discovery Coverage Matrix from Expert Suggestion.

| Discovery Dimension | Status | Key Missing Decision | Related Q IDs | Blueprint Treatment |
|---|---|---|---|---|
| | COVERED / PARTIAL / NOT STATED / N/A / NEED HOSPITAL CONFIRMATION | | | REQ/BR/HSR/CR/WA/TBD/N/A |

## 5. Workshop Question Summary
Do not duplicate the full Question Bank here. Carry only questions that affect Blueprint/readiness.

| Question ID | Priority | Decision Affected | Owner | Confirm When | Status | Blueprint Impact |
|---|---|---|---|---|---|---|
| Q-001 | CRITICAL/HIGH/MEDIUM | | | | OPEN / ANSWERED / DEFERRED | |

## 6. Core Functions
| ID | Function | Description | Evidence | Related REQ / Q IDs |
|---|---|---|---|---|
| FN-01 | | | | |

## 7. Hospital Requirements
| ID | Requirement | Evidence | Related Questions Resolved |
|---|---|---|---|
| REQ-01 | | HOSPITAL CONFIRMED | |

## 8. Confirmed Business Rules
| ID | Business Rule | Evidence | Source Confirmation / Q ID |
|---|---|---|---|
| BR-01 | | HOSPITAL CONFIRMED | |

Do not place AI/expert/domain-baseline recommendations in this section.

## 9. Hospital Standard Recommendations
| ID | Recommendation | Rationale | Gap Ref | Question ID | Confirmation Needed |
|---|---|---|---|---|---|
| HSR-01 | | | GAP-xx | Q-xxx | Yes/No |

## 10. Standards & Compliance Review
| ID | Standard / Source | Applicability | Topic / Principle | Workflow / Scenario Trace | Recommendation | Verification | Gap Ref | Question ID |
|---|---|---|---|---|---|---|---|---|
| CR-01 | | | | | | VERIFIED / NEED STANDARD VERIFICATION | GAP-xx | |

## 11. Data / Integration
| Data/System | Expected Relationship | Source of Truth | Scenario(s) | Failure / Correction | Evidence | Question IDs |
|---|---|---|---|---|---|---|
| | | | | | | |

## 12. Workflow / Record States
`State A → State B → ...`
Include correction/reopen/cancel/reversal states when material. Mark unconfirmed states as HSR/WA/TBD and link to Question IDs.

## 13. Permission / Accountability
| Action | Role | Create/Edit/Review/Approve/Reverse | Audit | Evidence | Question IDs |
|---|---|---|---|---|---|
| | | | | | |

## 14. Key Information Required
-

## 15. Reports / Outputs / Statistics
| Output | Definition / Trigger | Source | Version / Amendment | Recipient | Question IDs |
|---|---|---|---|---|---|
| | | | | | |

## 16. Working Assumption Register
| ID | Working Assumption | Scenario | Why Needed for Prototype | Risk if Wrong | Gap Ref | Q ID | Confirm When |
|---|---|---|---|---|---|---|---|
| WA-01 | | | | | GAP-xx | Q-xxx | Prototype Review |

## 17. TBD / Conflict Register
| ID | Missing / Conflict | Scenario | Why It Matters | Safe Prototype Treatment | Gap Ref | Q ID |
|---|---|---|---|---|---|---|
| TBD-01 | | | | | GAP-xx | Q-xxx |

## 18. Confirmation Plan
### MUST CONFIRM BEFORE DEV
| Q ID | Question / Decision | Owner | Why Blocking |
|---|---|---|---|
| | | | |

### CONFIRM DURING PROTOTYPE REVIEW
| Q ID | Question / Decision | Owner | What Prototype Demonstrates |
|---|---|---|---|
| | | | |

### SAFE TO DEFER
| Q ID | Reason Safe to Defer | Trigger |
|---|---|---|
| | | |

## 19. Acceptance Criteria
| ID | Acceptance Criterion | Scenario(s) | Related IDs | Evidence |
|---|---|---|---|---|
| AC-01 | | | REQ/BR/HSR/Q | |

## 20. Expert Review Summary
**Expert Suggestion file:**  
**Workshop Question Bank:**  
**Critical questions still open:**  
**High implementation-blocking questions still open:**  
**Discovery dimensions incomplete:**  
**Domain Baseline used:**  
**Scenario branches:**  
**Important recommendations carried as HSR/CR/WA/TBD:**  
**Advisory items intentionally not carried into Blueprint:**

## 21. Blueprint Readiness
**Status:** DRAFT / PROTOTYPE READY / HOSPITAL CONFIRMED / READY FOR DEV HANDOFF  
**Critical unresolved items:**  
**Open Question IDs:**  
**Prototype-safe assumptions:**  
**Scenario coverage required before UI Factory PASS:**  
**Compliance verification pending:**

### Readiness Rule
`PROTOTYPE READY` requires a complete Workshop Question Bank, disposition of material discovery dimensions/scenarios, all Critical/High unresolved decisions visible, and safe prototype treatment.

`READY FOR DEV HANDOFF` requires all Critical and implementation-blocking High questions answered, explicitly excluded, or converted into verified implementation rules; critical workflow, permission, record/order/legal effects, integration/source-of-truth and acceptance criteria must be confirmed.

### Separation Rule
`Domain Standard Flow ≠ Hospital Truth.`  
`Expert Suggestion ≠ Hospital Truth.`  
`Workshop Question ≠ Hospital Requirement.`  
Only explicit hospital confirmation promotes REQ/BR.