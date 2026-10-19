# SOURCE_VERSION_MANIFEST — <Module / Feature>

**Manifest Version:** 1.0.0  
**Change Request / Defect ID:** <REQ-* / REG-*>  
**Date (ISO 8601):** <YYYY-MM-DD>  
**Owner / Builder:** <actual role/person>  
**Current Decision:** BLOCKED — BASELINE NOT IDENTIFIED

## 1. Source Lock (complete before editing)

| Field | Value |
|---|---|
| Module / feature / screen | |
| Authority class | Hospital evidence / Blueprint / approved mockup / latest user-directed candidate |
| Exact source filename | |
| Source artifact version | |
| Source repository path / URL | |
| Source branch / ref | |
| Source commit SHA | |
| Source blob SHA | |
| If local artifact: exact path + SHA-256 | |
| Why this is the authoritative current source | |
| Conflicting candidates checked and disposition | |

**Baseline Lock:** NOT EXECUTED / PASS / FAIL  
**Reason and evidence:** 

## 2. Parent and Candidate Lineage

| Field | Parent Candidate | New Candidate |
|---|---|---|
| Filename | | |
| Version (MAJOR.MINOR.PATCH) | | |
| SHA-256 | | |
| Repository branch/commit/blob, if applicable | | |
| Created/updated at | | |

**Version increment reason:** MAJOR / MINOR / PATCH — <why>  
**Embedded artifact metadata checked:** NOT EXECUTED / PASS / FAIL

## 3. Scope Lock

**Authorized changes (REQ/DEFECT IDs):**
- 

**Protected surfaces/functions/workflows:**
- 

**Files and functions changed:**
| Requirement / Defect | Surface / function | Intended mutation | Actual change evidence |
|---|---|---|---|

**Reverse-scope review:** NOT EXECUTED / PASS / FAIL  
List unexpected changes; explain/approve or revert them.

## 4. Regression Register

| REG-ID | Source defect / screen-state | Reproduction steps | Expected result | Actual result | Evidence artifact/hash | Result |
|---|---|---|---|---|---|---|

Previously failed scenarios affecting the same surfaces must be rerun.

## 5. Gate Evidence Bound to Candidate SHA-256

| Gate | Exact candidate SHA-256 tested | Evidence | Status: PASS / FAIL / NOT EXECUTED / BLOCKED |
|---|---|---|---|
| Structural / syntax | | | |
| Dependency / single-authority / patch debt | | | |
| Runtime main workflow | | | |
| State mutation / save / navigation / re-entry | | | |
| Visual before-after at comparable viewport | | | |
| Blueprint / requirement traceability | | | |
| Independent Runtime Tester | | | |
| Independent Visual Reviewer | | | |
| Traceability Reviewer | | | |
| Release Controller | | | |

Reviewers must use the exact same candidate hash. A hash mismatch invalidates the evidence.

## 6. Final Release Decision

Choose exactly one:
- [ ] BLOCKED — BASELINE NOT IDENTIFIED
- [ ] IMPLEMENTED — NOT VERIFIED
- [ ] BLOCKED — REQUIRED GATE NOT EXECUTED
- [ ] REJECTED — GATE FAILED
- [ ] DELIVERABLE CANDIDATE — ALL REQUIRED GATES EXECUTED

**Candidate filename/version/hash:**
**Remaining limitations:**
**Actual independent reviewers and dates:**
**Final decision owner:**

No completion claim may exceed the recorded evidence. Any post-test mutation requires affected gates to be rerun.
