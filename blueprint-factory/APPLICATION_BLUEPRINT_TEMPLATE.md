# Gorilla HIS — Application Blueprint Template v2.3

**Blueprint Version:** v0.x / v1.x  
**Status:** DRAFT / PROTOTYPE READY / HOSPITAL CONFIRMED / READY FOR DEV HANDOFF  
**Related Expert Gap Analysis:** `Gorilla_HIS_<Module>_Expert_Gap_Analysis_v0.x.txt`

> This file is the Business Source of Truth for UI Factory. Expert Gap Analysis is advisory and must not silently change this Blueprint.

## Evidence Classification
- `HOSPITAL CONFIRMED` — hospital/user explicitly supplied or confirmed.
- `HOSPITAL STANDARD RECOMMENDATION` — expert HIS/hospital recommendation; not hospital-confirmed.
- `COMPLIANCE RECOMMENDATION` — recommendation tied to identified applicable authoritative basis.
- `WORKING ASSUMPTION` — temporary reversible prototype choice; must be confirmed later.
- `TBD` — unknown; do not guess.
- `REFERENCE BASELINE` — source-backed domain flow used for completeness review; NEVER Hospital Confirmed by itself.

## 1. Product
**Application Name:**  
**Product:** Gorilla HIS  
**Objective:**

## 2. Users & Roles
| Role | Responsibility | Permission / Constraint | Evidence |
|---|---|---|---|
| | | | |

## 3. Main Workflow — Hospital Requested / Confirmed
`Start → ... → End`
Clearly mark any step that is not Hospital Confirmed.

### 3A. Domain Standard Flow Baseline — Mandatory when repository baseline exists
Label: `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`

| Baseline ID | Scenario | Reference Step / Handoff | Source / Evidence | Applicability |
|---|---|---|---|---|
| SDF-01 | | | | RELEVANT / CONDITIONAL / N/A |

### 3B. Hospital Requirement Overlay / Delta
| Baseline ID / Scenario | Hospital REQ / Workflow Trace | Coverage | Hospital-Specific Difference / Missing Detail | Treatment |
|---|---|---|---|---|
| | | MATCHED / PARTIAL / NOT STATED / CONFLICT / N/A | | REQ/BR/HSR/CR/TBD/N/A |

`NOT STATED` does not automatically become a GAP; it must pass Relevance Gate.

### 3C. Scenario Branches
| Scenario ID | Scenario / Entry Trigger | Primary Identifier / Context | Starting Actor | Core Handoffs | Source of Truth / Records | Material Exceptions | End State / Output | Hospital Coverage |
|---|---|---|---|---|---|---|---|---|
| SCN-01 | | | | | | | | IN SCOPE / PARTIAL / OUT OF SCOPE / TBD |

### 3D. Prototype Scenario Coverage
| Scenario ID | Required in UI Factory? | End-to-End Path to Demonstrate | Safety / Assumption Boundary | Smoke Test Required |
|---|---|---|---|---|
| SCN-01 | Yes/No | | | Yes/No |

## 4. Core Functions
| ID | Function | Description | Evidence |
|---|---|---|---|
| FN-01 | | | |

## 5. Hospital Requirements
| ID | Requirement | Evidence |
|---|---|---|
| REQ-01 | | HOSPITAL CONFIRMED |

## 6. Confirmed Business Rules
| ID | Business Rule | Evidence |
|---|---|---|
| BR-01 | | HOSPITAL CONFIRMED |

Do not place AI/expert/domain-baseline recommendations in this section.

## 7. Hospital Standard Recommendations
| ID | Recommendation | Rationale | Gap Ref | Confirmation Needed |
|---|---|---|---|---|
| HSR-01 | | | GAP-xx | Yes/No |

## 8. Standards & Compliance Review
| ID | Standard / Source | Applicability | Topic / Principle | Workflow / Scenario Trace | Recommendation | Verification | Gap Ref |
|---|---|---|---|---|---|---|---|
| CR-01 | | | | | | VERIFIED / NEED STANDARD VERIFICATION | GAP-xx |

### 8A. Domain Compliance Coverage
| Domain Topic | Scenario / Hospital REQ Trace | Authoritative Source | Principle Supported | Coverage | Evidence Classification | Verification | Decision / Owner |
|---|---|---|---|---|---|---|---|
| | | | | COVERED / PARTIAL / GAP / N/A | HOSPITAL CONFIRMED / HSR / CR / TBD | | |

For Forensic/Mortuary this is the **Forensic Standard Compliance Review**. External guidance may expose a gap or support a principle but must not silently become Hospital Workflow or Hospital Requirement.

## 9. Data / Integration
| Data/System | Expected Relationship | Scenario(s) | Evidence |
|---|---|---|---|
| | | | |

## 10. Workflow / Record States
`State A → State B → ...`
Mark unconfirmed states as Working Assumption or TBD. Note scenario-specific state differences where material.

## 11. Key Information Required
-

## 12. Reports / Outputs
-

## 13. Working Assumption Register
| ID | Working Assumption | Scenario | Why Needed for Prototype | Risk if Wrong | Gap Ref | Confirm When |
|---|---|---|---|---|---|---|
| WA-01 | | | | | GAP-xx | Prototype Review |

## 14. TBD / Conflict Register
| ID | Missing / Conflict | Scenario | Why It Matters | Safe Prototype Treatment | Gap Ref |
|---|---|---|---|---|---|
| TBD-01 | | | | | GAP-xx |

## 15. Questions
### MUST CONFIRM BEFORE DEV
1.

### CONFIRM DURING PROTOTYPE REVIEW
1.

### LATER REFINEMENT
1.

## 16. Acceptance Criteria
| ID | Acceptance Criterion | Scenario(s) | Related IDs | Evidence |
|---|---|---|---|---|
| AC-01 | | | REQ/BR/HSR | |

## 17. Expert Review Summary
**Expert Gap Analysis file:**  
**Critical gaps:**  
**High gaps:**  
**Domain Baseline used:**  
**Scenario branches:**  
**Advisory items carried into Blueprint as HSR/CR/WA/TBD:**  
**Important advisory items intentionally not carried into Blueprint:**

## 18. Blueprint Readiness
**Status:** DRAFT / PROTOTYPE READY / HOSPITAL CONFIRMED / READY FOR DEV HANDOFF  
**Critical unresolved items:**  
**Prototype-safe assumptions:**  
**Scenario coverage required before UI Factory PASS:**  
**Compliance verification pending:**

### Readiness Rule
`PROTOTYPE READY` means enough truth exists to build a safe discovery mockup while clearly separating Domain Baseline, Hospital Requirement and Standards Overlay, and defining all material in-scope scenario branches.

`READY FOR DEV HANDOFF` requires critical scenario workflows, permission, clinical/data/legal effects, integration behavior and implementation acceptance criteria to be confirmed or explicitly out of scope.

### Separation Rule
`Domain Standard Flow ≠ Hospital Truth.`  
`Expert Gap Analysis ≠ Hospital Truth.`  
A recommendation becomes REQ/BR only after explicit hospital/user confirmation.