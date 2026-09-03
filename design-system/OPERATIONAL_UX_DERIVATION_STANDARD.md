# Gorilla HIS — Operational UX Derivation Standard v1.1

Status: `UNIVERSAL UX FACTORY MASTER`

Applies to **EVERY Gorilla HIS module**.

## 1. Core Principle — UNDERSTAND THE JOB, THEN DESIGN
The Factory must behave like a strong Senior HIS BA + Product Designer, not like a compliance engine assembling UI from checklists.

Mandatory thinking path:

`Hospital Actual Workflow → Understand the Job → Identify Work Objects & Decisions → Derive Essential Capabilities → Choose the Best Workspace Pattern → Compose Premium UI → Execute the Real Flow`

The Master is a **quality floor, not a layout generator**. Rules must prevent omissions and unsafe invention; they must not force visible UI chrome, equal sections, excessive documentation, or a generic Factory look.

**Design quality comes from synthesis, judgment, hierarchy and restraint — not from displaying every rule.**

## 2. Design Intent Brief — MANDATORY, SHORT
Before UI, create a concise internal brief (normally ≤1 page):
- Who is the primary user?
- What job are they trying to finish?
- What are the 2–5 most important decisions/actions?
- What information must be visible to make those decisions?
- What deserves attention now?
- What can stay hidden until needed?
- What should the product feel like? (e.g. calm, premium, precise, clinical, humane)
- What existing Gorilla/reference qualities should be preserved or improved?

If the answer is not clear, do not start visual composition.

## 3. BA/SA Derivation Boundary
A competent Factory should derive obvious application capability without interrogating the user about screens.

MAY derive as `EXPERT APPLICATION DERIVATION`:
- incoming work → worklist/queue;
- create/new transaction → entry surface;
- receive/assign → ownership action;
- assessment/scoring → professional assessment workspace;
- material handoff → review/verify;
- approval → approval inbox/decision workspace;
- repeated work → longitudinal/follow-up workspace;
- prior evidence affects current work → history/timeline/version context;
- closure → closure/outstanding-work check;
- operational volume → search/filter/sort;
- lifecycle-driven work → status/owner/next action.

MUST NOT invent as Hospital Truth:
- authority/approval thresholds;
- SLA/escalation;
- formula/score cut-off;
- local/legal policy;
- exact permissions;
- unverified source-of-truth;
- financial posting/reversal;
- clinical decision rules.

Ask the hospital about **decisions/policy**, not obvious UI capability.

## 4. Capability Coverage — THINK FIRST, TABLE ONLY WHEN USEFUL
The Factory must ensure every material workflow event has an operable capability, but it does **not** need to generate a giant derivation table unless it improves traceability or the deliverable requires it.

Minimum internal reasoning:
`Workflow Event → User Need → Capability → State/Data Change → Next Owner/Next Step`.

Missing material capability = FAIL. Lack of a ceremonial matrix = not a failure by itself.

## 5. Workspace Pattern Selection
Choose the pattern that makes the work easiest. Candidates include Worklist/Queue, split view, inspector, full-page workspace, schedule, resource board, acuity board, timeline, ledger, approval inbox, task workspace, or a hybrid.

Do not start from `Dashboard + Sidebar + KPI Cards`.
Do not force every module into the same shell.
Do not make the UI look like the Master structure.

The designer should be able to explain in one sentence why the chosen pattern fits the job.

## 6. Worklist / Queue
When work arrives and must be triaged, received, assigned, progressed or handed off, derive a work-management surface automatically.

Select only fields that improve scanning or action. Typical candidates:
`Type | Identity | Reason/Service | Source | Priority | Status | Owner | Aging/Due | Progress | Next Action`.

Exact columns are design decisions based on the workflow and volume, not a mandatory database dump.

## 7. Professional Work Surfaces
Core professional work deserves a workspace proportionate to its importance.

Examples:
- Assessment/scoring: prior evidence + current inputs + calculated/resulting classification + validation.
- Review/verify: concise decision summary + exceptions + clear handoff.
- Follow-up: authorized/planned work + previous event + current reassessment + used/remaining + next event.
- Approval: what is requested + evidence + financial/quantity context + decision.

Do not bury a core task inside a tiny generic modal merely to say the function exists. A modal is acceptable when the task is genuinely short and focused.

## 8. UX Decision Architecture
For each primary workspace reason from:

`User Goal → Decision Question → Evidence Needed → Attention/Exception → Primary Action → Detail on Demand`.

Within roughly 5 seconds an experienced user should understand where they are, what needs attention, current state, and what to do next.

## 9. 8 UX/UI Principles — USE AS DESIGN INSTINCT, NOT CHECKBOXES
Apply the principles to improve the composition; do not print or mechanically score all eight on every screen.

- **Jakob / Familiarity:** use domain conventions users can recognize.
- **Hick:** reduce and stage choices; one clear primary action per context where practical.
- **Fitts:** high-frequency/important actions are easy to reach and visually target.
- **Miller / Cognitive Load:** chunk information and reveal detail progressively.
- **Aesthetic-Usability:** polish, spacing, typography and proportion create trust and perceived quality.
- **Proximity:** related evidence and actions belong together.
- **Similarity:** same semantics share a visual grammar; different meanings are distinguishable.
- **Peak-End:** handoff, completion and closure should end with confidence and clear next state.

Also favor **Recognition over Recall**: show prior values/status/owner/remaining when they matter.

## 10. Premium Composition Direction
Target: **Premium, simple, calm, expensive, precise, professional — never decorative luxury.**

Use:
- strong but quiet information hierarchy;
- restrained palette;
- excellent Thai typography;
- deliberate whitespace;
- dense information only where it improves scanning;
- subtle depth/borders/radius;
- a small number of meaningful visual accents;
- state-driven primary actions;
- consistent alignment and rhythm;
- progressive disclosure.

Avoid:
- card sprawl;
- oversized KPI blocks;
- badge/confetti overload;
- excessive gradients/shadows;
- tiny text disguised as density;
- giant empty whitespace called premium;
- generic admin/SaaS visual language;
- explanatory labels that belong in design notes rather than the product.

## 11. Reference-Led Learning
When the user supplies a reference or a stronger candidate, study **why it works** before designing:
- hierarchy;
- density;
- composition;
- visual rhythm;
- scan path;
- action placement;
- typography;
- status encoding;
- use of whitespace;
- premium cues.

Do not copy blindly. Extract the useful design grammar and adapt it to the actual Gorilla HIS workflow.

A user-supplied candidate that clearly communicates the job better than the Factory output is evidence that the Factory must improve; do not defend the weaker output by citing Master rules.

## 12. Design Freedom Rule
The Master specifies **outcomes and failure conditions**, not pixel layouts.

A designer may simplify, combine, hide, reorder or visually reinterpret UI elements when:
- workflow fidelity remains intact;
- required decisions/actions remain discoverable;
- state/data/owner continuity remains clear;
- runtime scenario remains executable;
- no Hospital Truth is invented.

This freedom is intentional and required for high-quality design.

## 13. Operational UX Hard Failures
FAIL when:
- material work cannot be performed naturally;
- user cannot identify what to do next;
- queued work has no usable work-management surface;
- core assessment/review/follow-up is reduced to inadequate UI;
- repeated work loses history/progression;
- handoff/approval has no receiver state;
- visual hierarchy obscures the job;
- generic template dominates domain context;
- the screen is technically complete but visibly harder to use than a credible reference without workflow justification.

## 14. Final Rule
`Requirement is not a screen specification.`

`Master is not a screen specification either.`

The Factory's job is to understand the real work, derive the application intelligently, and then use product-design judgment to create a **beautiful, calm, premium operational tool that users can actually work in**.