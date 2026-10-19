# Source Version & Baseline Lock — Gorilla HIS Factory Gate

**Document Version:** 1.0.0  
**Status:** Mandatory Factory Gate (proposed on branch `mockup/factory-source-version-gate-ti`; effective on `main` after review and merge)  
**Owner:** Factory / Product Governance  
**Applies to:** Every HTML mockup, prototype, design correction, workflow change, repair, merge, regression fix, and regenerated artifact.

## 1. Non-negotiable rule

**No edit may start until the exact source artifact/version is identified and locked. No artifact may be called latest, fixed, verified, or ready without an explicit source-to-candidate lineage.**

Every change must answer, before editing:

1. Which exact file is the source?
2. What version is it?
3. Where did it come from (repo path + branch/commit/blob SHA, or exact file SHA-256 for a local/conversation artifact)?
4. Which prior candidate/version is its parent?
5. What changes are authorized, and what existing surfaces must not change?
6. What is the next candidate version?

If any answer is unknown or conflicting, set `BLOCKED — BASELINE NOT IDENTIFIED`, resolve the authority, and do not patch a guessed version.

## 2. Selecting the correct source

Use this precedence; do not use filename timestamps or words such as `FINAL`, `FIXED`, `LATEST`, or `RESTORED` as proof of authority:

1. Exact source/version explicitly named by the user in the current request.
2. Latest Human-approved / accepted artifact for the feature, verified against the approval record or explicit user confirmation.
3. Latest delivered candidate that the user is asking to continue editing or defect-fixing, provided its exact bytes can be identified.
4. Approved executable source recorded in `approved-mockups/` and its index.
5. Otherwise, stop and ask which conflicting candidate is authoritative.

`AI_INSTRUCTIONS.md` and repository `main` govern Factory rules. They do not magically make an unrelated HTML file the feature's latest source. A Factory document, approved mockup, conversational attachment, and generated candidate are distinct artifact classes.

Never:
- start from an older candidate just because it is easier to locate;
- merge multiple candidate files without a declared merge plan;
- append another override to hide a conflicting renderer without resolving patch debt;
- overwrite an approved baseline in place;
- claim a locally generated artifact is present in `main` unless its repository path/commit proves it.

## 3. Required version scheme

Every mockup candidate uses semantic versioning `MAJOR.MINOR.PATCH`:

- **MAJOR**: incompatible workflow, information architecture, data contract, or state/lifecycle change.
- **MINOR**: backward-compatible feature, screen, interaction, or workflow capability added.
- **PATCH**: correction/refinement that preserves the existing workflow and data contract.

Use `0.x.y` while the artifact remains a discovery/prototype candidate. Use `1.0.0` only after an explicit approved baseline is recorded. Do not infer approval from a filename.

Recommended filename:
`<Module>_<Feature>_v<MAJOR>.<MINOR>.<PATCH>.html`

Descriptive suffixes may be added after the version, but must not replace it. A filename like `FINAL.html` alone is invalid identity.

The candidate must expose its version in an HTML comment and/or metadata, e.g.:

```html
<!--
Artifact: Gorilla HIS Social Work Conclusion
Version: 0.4.2
Parent Version: 0.4.1
Source File: Gorilla_HIS_Social_Conclusion_v0.4.1.html
Source SHA-256: <exact hash>
Change Scope: <authorized change>
-->
```

## 4. Mandatory Source Version Manifest

Create/maintain `SOURCE_VERSION_MANIFEST.md` for the feature using `factory-gate/SOURCE_VERSION_MANIFEST_TEMPLATE.md`, or an equivalent manifest bound to the release. At minimum record:

| Field | Required evidence |
|---|---|
| Module / feature | Unique name |
| Authority class | Hospital evidence / Blueprint / approved mockup / current delivered candidate |
| Source filename + path | Exact path, not descriptive guess |
| Source version | Explicit MAJOR.MINOR.PATCH or legacy version label + content hash |
| Source locator | Branch + commit SHA + blob SHA, or exact local file path + SHA-256 |
| Parent candidate | Version and SHA-256 |
| New candidate | Version, filename and SHA-256 |
| Change scope | Explicit requested changes |
| Protected scope | Screens, functions, states and workflows that must not regress |
| Files/surfaces changed | Trace from requirement to implementation |
| Tests run | Named scenarios + observed result |
| Tests not run / blocked | State limitations honestly |
| Independent reviewer | Actual identity/role and evidence; never simulated |
| Release status | One of the statuses in Section 7 |

For an iterative local HTML conversation, include both the user-visible filename/version and SHA-256; if the source hash cannot be obtained, baseline lock is not complete.

## 5. Change isolation and lineage

For every new request:
1. Re-fetch the current designated source from its authoritative location.
2. Verify it is newer than or explicitly selected over the prior candidate; compare Git commit/blob SHAs or file hashes.
3. Declare the exact parent version and calculate the next candidate version.
4. Make only the requested change unless additional changes are explicitly authorized.
5. Preserve unrelated approved behavior and visuals.
6. Run a reverse diff/scope review: every changed surface must map to the request; every protected surface must remain unchanged or have a justified, approved change.
7. Record the result in the manifest and changelog.

A generated artifact can become the next source only when its exact identity is recorded and the user clearly continues from or accepts it. If a user reports a defect in the just-delivered artifact, use that exact artifact as the defect-reproduction baseline unless the user explicitly asks to restore another version.

## 6. Multi-Agent same-baseline rule

Builder, Runtime Tester, Visual Reviewer, Traceability Reviewer, and Release Controller must refer to the **same exact source version, parent version, candidate version, and candidate hash**. The manifest is the shared handoff contract.

- Builder must not self-certify final Runtime/Visual PASS.
- Reviewers must report the artifact version/hash actually executed or rendered.
- If one reviewer uses a different candidate hash, evidence is stale and invalid.
- Do not claim Multi-Agent PASS when independent execution was not actually performed.

## 7. Fail-closed release states

Allowed states:

- `BLOCKED — BASELINE NOT IDENTIFIED`
- `IMPLEMENTED — NOT VERIFIED`
- `BLOCKED — REQUIRED GATE NOT EXECUTED`
- `REJECTED — GATE FAILED`
- `DELIVERABLE CANDIDATE — ALL REQUIRED GATES EXECUTED`

Version, source path and candidate fingerprint must appear in the handoff. Runtime/visual evidence applies only to the exact final candidate hash. Any source mutation after testing invalidates affected tests.

A syntax check is not Runtime PASS. DOM/source inspection is not Visual PASS. A test not executed is `NOT EXECUTED`, not PASS. The downloadable “fixed/final” claim is prohibited while an applicable mandatory gate is missing.

## 8. Required response contract for each edit

Every user-facing delivery/update must state:

- **Source used:** exact filename + version + SHA / repository locator.
- **Parent version:** exact prior candidate and hash.
- **Candidate produced:** exact filename + next version + SHA-256.
- **Authorized scope changed:** concise list.
- **Protected scope checked:** concise list.
- **Gate evidence:** structural / runtime / visual / regression / independent review, each marked PASS, FAIL, or NOT EXECUTED.
- **Release status:** one status from Section 7.

If this contract cannot be completed, do not present the file as the corrected final candidate. The standard form is `factory-gate/SOURCE_VERSION_MANIFEST_TEMPLATE.md`.

## 9. Human defect reopen rule

If the user shows the defect still exists:
- mark the previous result `FALSE PASS — DEFECT REPRODUCED`;
- record a regression case;
- keep the failed source version/hash in the manifest;
- fix from that exact repro source or a clearly identified newer baseline;
- rerun all affected gates on the final hash;
- never overwrite the prior evidence or claim the source version changed without proof.
