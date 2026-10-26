# Gorilla HIS — Baseline, Version, and Regression Lock Gate v1.0

**Status: MANDATORY HARD GATE for every edit to an existing mockup.**

## 1. Purpose

Prevent work from silently reverting to an older version, replacing accepted UI with an unrelated redesign, losing previously fixed behavior, or shipping an artifact whose lineage cannot be proven.

## 2. Non-negotiable baseline lock — before editing

Create a run record before opening the editor:

- `BASE_VERSION`: exact approved version label.
- `BASE_FILE`: exact filename and verified local path.
- `BASE_SHA256`: SHA-256 of the exact source bytes.
- `BASE_SOURCE`: source of authority (latest accepted user artifact / approved repository commit / explicitly nominated predecessor).
- `BASE_COMMIT`: repository commit SHA when applicable.
- `REQUEST_SCOPE`: numbered requested changes.
- `PRESERVE_LIST`: existing screens, layout, interactions, state, navigation, data and behavior that must not change.
- `KNOWN_FIXED_REGRESSIONS`: defects previously fixed and the acceptance assertions that prove they remain fixed.

If two sources conflict, stop and resolve the controlling baseline from explicit user instruction and verifiable lineage. Never choose a source based on memory, filename similarity, or convenience. Never silently use an older version.

Missing or ambiguous baseline = `BLOCKED — BASELINE NOT LOCKED`; do not edit or export.

## 3. One-source / one-output lineage

- Work from a byte-for-byte copy of the locked baseline.
- Assign a new candidate version only after the baseline is locked.
- Keep the source immutable; write to a new output file.
- Record input hash, output hash, parent version, changed files and a concise change manifest.
- Do not rename an old artifact to make it appear newer.
- Do not merge unrelated historical fixes opportunistically. Cherry-pick only when the request explicitly requires them and their origin is verified.
- If the output cannot be traced to the declared baseline, reject it.

## 4. Minimal-diff and preserve gate

Before testing, inspect the diff against the locked baseline.

Every changed region must map to a request item or an explicitly approved defect fix. Explain each nontrivial changed region. Reject unexplained changes to:

- page structure, shell, layout, visual hierarchy;
- navigation and route/page transitions;
- user-entered data, persistence and selected case/patient context;
- event handlers, component lifecycle and open/close state;
- other modules or previously accepted behavior.

Unrequested UI/flow replacement = `FAIL — UNAUTHORIZED REGRESSION`.

## 5. Regression contract registry

For every known fixed defect, maintain a stable regression ID, for example:

- `REG-NAV-PN-001`: Progress Note must close when navigating to another page or switching Case, per approved behavior.
- `REG-NAV-PN-002`: returning to the previous page must not reopen the panel from stale UI state.
- `REG-CASE-PN-003`: switching patient/Case must not leak draft content or patient-bound state to another Case; persistence follows the explicitly approved save/draft rule.

For `REG-NAV-PN-001`, execute in the running browser:

1. Open a known Case and open Progress Note.
2. Enter a harmless test value if needed.
3. Navigate to a different page using normal application navigation.
4. Assert Progress Note is closed.
5. Return to the original page.
6. Assert Progress Note remains closed.
7. Switch Case and assert the panel is closed and patient-bound content is not leaked.
8. Repeat with each materially different navigation mechanism that exists (tab, menu, back/route change).

A code search, event-handler inspection, JavaScript syntax check, screenshot of the source, or builder assertion is not execution evidence.

Do not erase saved clinical/social-work data merely to close a panel. Panel visibility and data persistence are separate states and must be tested separately.

## 6. Mandatory build-test loop

`LOCK BASELINE → DECLARE SCOPE → COPY → PATCH MINIMALLY → DIFF → SYNTAX/LINT → RUN BROWSER → EXECUTE REGRESSION SCENARIOS → VISUAL COMPARE → FIX → RE-RUN AFFECTED SCENARIOS → VERIFY OUTPUT HASH → RELEASE`

After any fix touching shared navigation, routing, component lifecycle, state initialization, persistence, or panel visibility, re-run all related regression scenarios from the correct starting state. Do not test only the final line or last click.

## 7. Evidence and release status

Required run report:

- baseline version, path, hash and source commit;
- candidate version, path and output hash;
- requested changes and preserve list;
- changed-file / diff summary;
- regression IDs executed with expected vs actual results;
- browser/runtime and viewport used;
- visual comparison evidence where applicable;
- known limitations and defects;
- final status.

Allowed status values:

- `PASS — REGRESSION EXECUTED`
- `FAIL — REGRESSION`
- `BLOCKED — BASELINE NOT LOCKED`
- `BLOCKED — RUNTIME NOT VERIFIED`
- `BLOCKED — DIFF NOT REVIEWED`

Syntax PASS is only a static sub-check. It cannot grant Runtime, Workflow, Visual, or Release PASS.

## 8. Hard stop conditions

Stop and do not deliver a release candidate if any applies:

- no verifiable approved baseline;
- hash/path/version mismatch;
- unexplained or broad diff;
- known fixed regression not executed;
- browser test unavailable but runtime PASS is implied;
- regression scenario fails;
- candidate output cannot be tied to its declared input.

A user-approved baseline outranks a newer but unapproved candidate. Version number alone never proves authority.