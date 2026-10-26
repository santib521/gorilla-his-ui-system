# Gorilla HIS — Authoritative Source Registry v1.1

This registry is a source-discovery and verification index, not a substitute for applicability review. Always apply `AUTHORITATIVE_SOURCE_POLICY.md` and the Relevance Gate first.

Verified date for this revision: 2026-09-02.

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
- Transition verified 2026-09-02: HAI states Hospital and Healthcare Standards, 6th Edition becomes effective for accreditation assessment from 1 October 2026.
- Before 1 October 2026, verify which edition governs the hospital's current assessment; for implementation/go-live on or after that date, explicitly assess 6th Edition applicability.
- Relevant topics when triggered: organization quality systems, patient/process safety, medical records/information, privacy/accountability and other applicable HA topics.
- Assurance: Level B when exact official standard/section and applicability are verified; otherwise `STANDARD PRINCIPLE — NEED VERIFICATION`.
- Guardrail: do not infer a specific HIS screen/function merely from accreditation principles.

## Thailand Forensic Medicine / Autopsy / Mortuary
- Source Owner: Institute of Forensic Science (CIFS), Ministry of Justice; Ministry of Public Health Health Administration Division; other official Thai legal/professional authorities when directly applicable.
- CIFS official `คู่มือการให้บริการงานชันสูตรศพ`, SD-FSP-007, issue date 25 September 2025: authoritative current service guidance for medicolegal autopsy service context, service steps, documents and reporting/contact process.
- CIFS official Mortuary Staff/Prosector guidance published in 2026: verified topics include direct forensic-physician supervision, evidence integrity, chain of custody, forensic photography, evidence/specimen handling and biosafety.
- MOPH official catalogue includes `คู่มือการดำเนินงานชันสูตรพลิกศพ` and `คู่มือการปฏิบัติงานนิติเวช (สำหรับแพทย์และบุคลากรทางการแพทย์)`; catalogue/procurement records also indicate an updated post-mortem operations manual in 2018. Always verify the newest accessible official edition applicable to the hospital before a formal claim.
- Mandatory Gorilla review when triggered: `FORENSIC_STANDARD_COMPLIANCE_REVIEW.md`.
- Assurance: Level B only when exact official requirement + applicability are verified; Level C for official guidance principles where mandatory status is not established.
- Guardrail: CIFS/MOPH workflow is not automatically the hospital's workflow; never promote guidance to Hospital Confirmed.

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
