# Gorilla HIS — Knowledge-to-Design Compilation Standard v1.0

Status: `MANDATORY DESIGN MASTER`

## Purpose
Prevent the failure mode where the Factory reads Gorilla/Claude knowledge, standards, Gold references and approved patterns but does not materially use them in the candidate.

Reading is not compliance. The Factory must **compile applicable knowledge into build constraints that are traceable to the rendered UI**.

Core:
`Knowledge Source → Applicability → KD Rule → Design Consequence → UI Surface → Render/Runtime Evidence → PASS/FAIL`

## 1. Mandatory Output Before UI Build
Create an internal artifact:
`Compiled_Design_Knowledge_<Module>.md`

This artifact is mandatory for every candidate. It may be delivered under QA/support files.

Minimum row:
`KD ID | Source | Source Rule/Strength | Applicability | Design Consequence | Required UI Evidence | Verification Method | Status`

Stable IDs: `KD-001...`

## 2. Sources to Compile
Compile only applicable rules/strengths from:
1. Human-approved Gold/benchmark executable HTML and screenshot evidence;
2. `AI_INSTRUCTIONS.md`;
3. `VISUAL_DNA.md`;
4. `OPERATIONAL_UX_DERIVATION_STANDARD.md`;
5. `ENTERPRISE_WORKLIST_STANDARD.md` / `LONGITUDINAL_MULTI_WORKLIST_STANDARD.md` when applicable;
6. `PREMIUM_PRODUCT_DESIGN_GATE.md`;
7. `INTERACTION_WORKFLOW_STANDARD.md`;
8. approved components/patterns/tokens/icons;
9. user-supplied design knowledge/reference.

Do not create filler KD rows for irrelevant rules.

## 3. Compilation Rule
For every applicable knowledge item answer:
- What real user job/decision does this affect?
- What composition/interaction consequence follows?
- Where in the candidate must the consequence be visible?
- How will an independent reviewer verify it?

Weak statement:
`Use premium styling.`

Valid compiled constraint:
`KD-014 | Enterprise Worklist | Next Action is first-class | WL-02 | every row shows a context-valid Next Action adjacent to state | first viewport rows | rendered review + click test`.

## 4. Benchmark Knowledge Compilation
When a Human-approved benchmark exists, benchmark strengths are compiled as `BM-*` evidence and linked to one or more `KD-*` constraints.

Required benchmark dimensions at minimum:
- shell/navigation geometry;
- work-surface dominance;
- first-viewport information density;
- typography hierarchy;
- worklist/table rhythm;
- search/filter/tab grammar;
- status/action distinction;
- attention/reminder treatment;
- row-action placement;
- progressive disclosure/drawer/modal behavior;
- spacing/color/border/control craft.

A benchmark must never be reduced to a prose summary such as “white topbar, dark rail, indigo buttons”.

## 5. Generic Template Rejection Test
Before coding and again after rendering ask:

`Could this composition be relabeled and used almost unchanged for CRM, HR, Inventory or another unrelated HIS module?`

If Yes and the module has material domain-specific work:
`FAIL — GENERIC TEMPLATE`.

Passing requires domain-specific decision architecture and professional workspace depth, not merely domain labels/data.

## 6. Traceability
Every primary workspace must trace:
`Work Obligation → UX Contract → KD/BM Constraint → UI Surface → Render Evidence`.

Every critical `KD-*` must resolve to:
`IMPLEMENTED / N/A-JUSTIFIED / FAIL`.

Unresolved critical KD = Design FAIL.

## 7. Prohibitions
- Reading knowledge without producing compiled constraints.
- Copying visual vocabulary while ignoring composition/interaction rules.
- Claiming knowledge use because colors, rail, table or buttons resemble Gorilla.
- Builder self-declaring compliance without evidence.
- Marking KD implemented from source code alone when the rule is visual/interaction-based and rendering is possible.

## 8. Final Rule
`Knowledge Read` is not a gate.
`Knowledge Compiled + Traceable + Render Verified` is the gate.

**Having Gorilla colors, rail, table and indigo buttons does not make a UI Gorilla-quality.**