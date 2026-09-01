# Gorilla HIS — Authoritative Source Registry v1.0

This registry is a source-discovery and verification index, not a substitute for applicability review. Always apply `AUTHORITATIVE_SOURCE_POLICY.md` and the Relevance Gate first.

## JCI — Hospitals / Academic Medical Center
- Source Owner: Joint Commission International (JCI)
- Current verified family: Joint Commission International Accreditation Standards for Hospitals, including Academic Medical Center Hospitals, 8th Edition
- Effective: 1 January 2025
- Official source: JCI official standards/manual pages and official standards publication
- Relevant topics when triggered: patient safety, medical records/information, healthcare technology, medication management, governance; Academic Medical Center chapters include medical professional education and human subjects research for eligible organizations.
- Assurance: Level B when exact official standard/section and applicability are verified; otherwise `STANDARD PRINCIPLE — NEED VERIFICATION`.
- Guardrail: Academic Medical Center standards are not automatically applicable to every hospital or every Education module.

## Thailand HA / HAI
- Source Owner: The Healthcare Accreditation Institute (Public Organization), Thailand
- Verified family: Hospital and Healthcare Standards, 5th Edition
- Official HAI source indicates 5th Edition and provides the official standard publication.
- Relevant topics when triggered: organization quality systems, patient care/process safety, information/record/accountability and other applicable HA topics.
- Assurance: Level B when exact official standard/section and applicability are verified; otherwise `STANDARD PRINCIPLE — NEED VERIFICATION`.
- Guardrail: do not infer a specific HIS screen/function merely from accreditation principles.

## ISO/IEC 27001
- Source Owner: ISO / IEC
- Verified current base standard: ISO/IEC 27001:2022, Edition 3, published 2022-10; official ISO page also lists Amendment 1:2024.
- Relevant topics when triggered: ISMS risk management, confidentiality, integrity, availability, organizational/technical controls within applicable scope.
- Assurance: Level B only for exact requirements verified from an authorized source and applicable ISMS scope.
- Guardrail: ISO/IEC 27001 does not by itself make every HIS feature mandatory.

## Thailand PDPA / Privacy
- Source Owner: Thai legal/regulatory authorities including the Personal Data Protection Committee / Office of the PDPC and official legal publications.
- Relevant topics when triggered: personal data, sensitive/health data, lawful processing, access/disclosure, data-subject rights, security/governance obligations as applicable.
- Assurance: Level B only when exact legal/regulatory text and applicability are verified from an official source.
- Guardrail: never convert a general privacy principle directly into a specific UI field/button without workflow and applicability analysis.

## HIPAA
- Source Owner: U.S. HHS / official U.S. legal sources.
- Default for Thai HIS work: `NOT APPLICABLE / NEEDS APPLICABILITY EVIDENCE` unless the project establishes legal applicability or explicitly chooses HIPAA as a benchmark.
- Never activate because the product is a HIS.

## Domain Practice Sources
Domain-specific clinical/operational guidance may be used when directly relevant, but source authority must be recorded. Prefer national regulator/professional authority or internationally recognized standards owner. If the source is guidance rather than a formal requirement, label it `AUTHORITATIVE GUIDANCE`, not `FORMAL REQUIREMENT`.

## Registry Maintenance
- Record verification date in each analysis output; do not assume this registry proves perpetual currency.
- If a source edition changes, update this registry and regression-test affected domains.
- Do not store copyrighted full-text standards unless licensed.
