# Gorilla HIS — Claude UX Knowledge Adoption v1.0

Status: `DESIGN KNOWLEDGE MASTER`

Purpose: capture reusable UX/product-design knowledge learned from the Human-supplied Claude UX knowledge package without replacing Hospital Truth, Factory workflow masters, or blindly copying reference layouts.

## 1. Authority Boundary
Claude knowledge is **Design/UX knowledge evidence**, not Hospital Business Truth.

It may improve:
- UX decision architecture;
- information hierarchy;
- work-surface composition;
- clinical/operational density;
- interaction craft;
- worklist scanability;
- typography/readability;
- anti-template quality;
- premium design review.

It must never invent or override Hospital workflow, policy, authority, formula, legal decision, transaction state, integration truth, or source-of-truth ownership.

## 2. Core Derivation
`Actual Workflow → User Work Obligation → Operational Capability → Workspace/Work Surface → Transaction/State → Primary Action → Information Needed for Decision → Interaction Pattern → Screen Composition`

Never translate Requirement directly to Screen.

## 3. UX Decision Architecture
For every primary workspace:
`User Goal → Decision Question → Primary Evidence → Exception/Attention → Primary Action → Secondary Action → Detail on Demand`.

The UI must answer the user's decision before decorating the page.

## 4. 5-Second Operational Comprehension
Within approximately five seconds, the primary workspace should communicate:
- where the user is;
- what needs attention;
- which patient/work object is involved;
- current status/owner;
- next action;
- evidence supporting that action.

Recommended hierarchy:
`Context → Situation/Attention → Evidence/Work → Exception → Next Action → Detail`.

## 5. Worklist Is Operational Infrastructure
A worklist is not a dashboard and not a passive report.

First viewport prioritizes scanning, triage, ownership and action.

Recommended row grammar when applicable:
`Type → Identity → Reason/Service → Source → Priority → Status → Owner → Time/Aging → Progress → Next Action`.

Next Action must be first-class. Do not force users to infer action from a status badge.

## 6. Work Surface Before Card Grid
Use the largest useful area for real work/evidence.

Avoid generic dashboard composition:
- KPI cards dominating operational pages;
- card-sprawl;
- equal-size panels for unequal work importance;
- large decorative blank areas;
- detached actions;
- narrow content strips caused by oversized navigation.

Cards are containers with a job, not the default unit of design.

## 7. Authored Composition
Screen proportion must reflect work importance, frequency, urgency, evidence volume and decision complexity.

Ask:
`What does the user scan? compare? decide? repeat? keep visible? act on?`

Do not use symmetrical/equal layouts merely because they are easy to code.

## 8. Controlled Clinical/Operational Density
Premium does not mean sparse.

Dense screens are appropriate when users need rapid scanning and comparison, provided:
- hierarchy remains obvious;
- rows/columns are stable;
- labels are concise;
- related evidence is grouped;
- exceptions stand out selectively;
- primary action remains discoverable;
- low-value detail moves to progressive disclosure.

## 9. Typography as Hierarchy
Typography must establish hierarchy before additional containers are added.

Use differences in size, weight, contrast and spacing deliberately for:
- page/workspace context;
- patient/work identity;
- primary evidence;
- metadata;
- status;
- action.

Thai readability is a hard design requirement, not final polish.

## 10. Surface / Elevation Discipline
Use quiet resting surfaces for routine work and stronger elevation for overlays/modals.

Uniform heavy shadows on every box = template-like output.
Borders, tints, radius and shadow must communicate structure/state, not decoration.

## 11. Interaction Craft
Operational application of interaction principles:
- Hick: reduce competing choices at each lifecycle stage;
- Fitts: important/frequent actions are near the affected object and easy to acquire;
- Proximity: evidence and action stay together;
- Progressive disclosure: detail appears when needed;
- action labels name the specific state-changing intent where possible.

A state-changing action must create visible state/data/history change, not only a toast.

## 12. Anti-Template Gate
Ask: if labels were replaced, could this screen easily pass as generic CRM/ERP/Fintech/Admin UI?

If yes, challenge the design for missing hospital/domain work character.

Typical failure signals:
- generic KPI dashboard as primary operational screen;
- decorative icon/card proliferation;
- no patient/work identity anchor;
- passive table without lifecycle action;
- generic Overview landing instead of the work stage needing action;
- same visual composition reused across unrelated modules.

## 13. Reference / Gold Standard Use
Human-approved references are pattern and quality evidence.

Default Benchmark Mode rule:
`Reference → Analyze why it works → PRESERVE / IMPROVE / REPLACE → design for actual workflow`.

**Do not copy layouts blindly.**
Do not copy source implementation merely because HTML is available.
Exact source/layout replication belongs only to explicit Exact Replication Mode.

## 14. Premium Product Character
Target experience:
- precise;
- calm;
- information-rich without noise;
- intentionally composed;
- clinically/operationally serious;
- next action obvious;
- evidence close to decision;
- trustworthy interaction states;
- Gorilla HIS continuity.

Premium is demonstrated by task clarity and craft, not adjectives, gradients, excessive whitespace, or visual novelty.

## 15. Review Rule
A beautiful UI for the wrong workflow fails.
A correct workflow with weak/unusable work surfaces fails.
A function-rich candidate worse than the Human-approved benchmark fails.
A visually strong candidate that loses validated function/state continuity fails.

Final target:
`Business Truth + Workflow Fidelity + Operational Capability + Interaction Quality + Visual Quality + Runtime Proof`.