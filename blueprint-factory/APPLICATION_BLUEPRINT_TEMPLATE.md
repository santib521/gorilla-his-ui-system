# Gorilla HIS — Application Blueprint Template v2.0

**Blueprint Version:** v0.x / v1.x  
**Status:** DRAFT / PROTOTYPE READY / HOSPITAL CONFIRMED / READY FOR DEV HANDOFF

## Evidence Classification
- `HOSPITAL CONFIRMED` — hospital/user explicitly supplied or confirmed.
- `HOSPITAL STANDARD RECOMMENDATION` — expert HIS recommendation; not hospital-confirmed.
- `COMPLIANCE RECOMMENDATION` — recommendation tied to identified JCI/HA/ISO 27001 basis.
- `WORKING ASSUMPTION` — temporary reversible prototype choice; must be confirmed later.
- `TBD` — unknown; do not guess.

## 1. Product
**Application Name:**  
**Product:** Gorilla HIS  
**Objective:**

## 2. Users & Roles
| Role | Responsibility | Permission / Constraint | Evidence |
|---|---|---|---|
| | | | |

## 3. Main Workflow
`Start → ... → End`

Clearly mark any step that is not Hospital Confirmed.

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

Do not place AI recommendations in this section.

## 7. Hospital Standard Recommendations
| ID | Recommendation | Rationale | Confirmation Needed |
|---|---|---|---|
| HSR-01 | | | Yes/No |

## 8. Standards & Compliance Review
| ID | Standard | Topic / Principle | Recommendation | Verification |
|---|---|---|---|---|
| CR-01 | JCI / HA / ISO/IEC 27001 | | | VERIFIED / NEED STANDARD VERIFICATION |

Do not fabricate clause numbers. Accreditation principles do not automatically dictate a UI control.

## 9. Data / Integration
| Data/System | Expected Relationship | Evidence |
|---|---|---|
| | | |

## 10. Workflow / Record States
`State A → State B → ...`

Mark unconfirmed states as Working Assumption or TBD.

## 11. Key Information Required
- 

## 12. Reports / Outputs
- 

## 13. Working Assumption Register
| ID | Working Assumption | Why Needed for Prototype | Risk if Wrong | Confirm When |
|---|---|---|---|---|
| WA-01 | | | | Prototype Review |

## 14. TBD / Conflict Register
| ID | Missing / Conflict | Why It Matters | Safe Prototype Treatment |
|---|---|---|---|
| TBD-01 | | | |

## 15. Questions
### MUST CONFIRM BEFORE DEV
1. 

### CONFIRM DURING PROTOTYPE REVIEW
1. 

### LATER REFINEMENT
1. 

## 16. Acceptance Criteria
| ID | Acceptance Criterion | Related IDs | Evidence |
|---|---|---|---|
| AC-01 | | REQ/BR/HSR | |

## 17. Blueprint Readiness
**Status:** DRAFT / PROTOTYPE READY / HOSPITAL CONFIRMED / READY FOR DEV HANDOFF  
**Critical unresolved items:**  
**Prototype-safe assumptions:**  
**Compliance verification pending:**

### Readiness Rule
`PROTOTYPE READY` means enough truth exists to build a safe discovery mockup while clearly labeling reversible assumptions/recommendations.  
`READY FOR DEV HANDOFF` requires critical workflow, permission, clinical/data effects, integration behavior and implementation acceptance criteria to be confirmed or explicitly out of scope.