# Gorilla HIS — Domain Standard Flow Baseline Policy v1.0

## Purpose
Blueprint Factory must not begin workflow design from Raw Requirement alone when the module has an established professional/operational domain flow.

Use this sequence:

`Domain Standard Flow Baseline → Hospital Requirement Overlay → HA/JCI/Privacy/Security Overlay → Gap/Relevance Review → Application Blueprint`

This policy strengthens completeness review without turning external guidance into Hospital Truth.

## Core Rule
A Domain Standard Flow Baseline is a **reference workflow model**, not a Hospital-Confirmed workflow.

It may be used to:
- identify expected actors/handoffs/states/records;
- detect missing scenario branches;
- detect missing safety, identity, custody, review, correction or handover points;
- structure prototype coverage;
- compare the hospital requirement against a credible domain operating model.

It MUST NOT be used to:
- invent this hospital's role authority;
- invent mandatory fields, approval levels, retention periods or legal finality;
- promote a domain-practice step to HOSPITAL CONFIRMED;
- bypass Relevance Gate or Confirmation Value Gate.

## Mandatory Analysis Layers
### Layer 1 — Domain Standard Flow
Use the current repository baseline under `blueprint-factory/domain-baselines/` when available. If unavailable, build a temporary source-backed baseline from authoritative domain sources and label it `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`.

### Layer 2 — Hospital Requirement Overlay
For every material baseline step or branch classify the hospital requirement as:
- `MATCHED` — directly supported by supplied Hospital Requirement;
- `PARTIAL` — hospital requirement covers only part of the step/branch;
- `NOT STATED` — baseline step exists but hospital requirement does not state it;
- `CONFLICT` — supplied hospital requirement materially differs;
- `N/A` — baseline step is not applicable to this module scope.

`NOT STATED` does not automatically become a GAP. It still must pass Relevance/Materiality/Actionability/Timing.

### Layer 3 — Standards Overlay
Only after the Domain Standard Flow and Hospital Overlay are visible, apply relevant external standards/governance perspectives such as HA, JCI, PDPA, ISO/IEC 27001 and domain authorities.

External standards are used to strengthen safety/quality/governance review of a relevant step; they do not create local workflow by themselves.

## Scenario Branch Rule
If the domain has materially different entry or processing scenarios, each relevant scenario must be modeled separately.

For each scenario record:
- Entry Trigger;
- Primary Identifier / Context;
- Starting Actor;
- Required Handoffs;
- Core Records / Source of Truth;
- Material Exceptions;
- End State / Output;
- Hospital Coverage status.

A single generic happy-path flow is insufficient when different scenarios materially change identity, source of truth, actor, order/result linkage, custody, authorization, or handover.

## Blueprint Output Requirement
When a Domain Standard Flow is activated, File 1 must include:
1. `Domain Standard Flow Baseline` — reference-only, source-backed.
2. `Hospital Requirement Overlay / Delta` — what hospital explicitly covers, differs from, or omits.
3. `Scenario Branches` — separate material flows.
4. `Standards Overlay` — HA/JCI/domain/privacy/security only where relevant.
5. `Prototype Coverage` — which scenario branches UI Factory must be able to play end-to-end.

## Quality Gate
Hard fail when:
- an applicable domain baseline was ignored;
- materially different scenario branches were collapsed into one generic flow;
- baseline guidance was presented as Hospital Confirmed;
- standards were applied before relevance to the actual workflow was established;
- a prototype is declared representative while a material in-scope scenario branch cannot be exercised.
