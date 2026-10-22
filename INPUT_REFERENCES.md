# Input references — no source contents

Paths below are relative to the supplied material folder or the original project root. Relocate that root as needed; do not require the original user's absolute home path. IDs such as `R1` are used in file recipes. These references identify evidence; they do not grant API access.

## Source material

| ID | Material / local reference | Locate the relevant part | Rebuild use |
| --- | --- | --- | --- |
| R0 | `IMG_3295.jpeg`, `IMG_3296.jpeg`, `IMG_3297.jpeg`; navigation aid `docs/ORIGINAL_README_TRANSCRIPTION.md` | Original photographed proposal | Product intent only. Proposed commands, authentication assumptions and completion claims are not implementation evidence. |
| R1 | `loan-product-advisor-v6.1.00-request-file-requirements/LPA v6.1 XML Request File Data Requirements_January_2026.xlsx` | Main requirements tab; amendments, supported enums, extensions, relationships, cardinality and revision tabs | Request catalog, rule evidence, reviewed mappings and coverage. Preserve bytes and formatting. |
| R2 | `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/` | `lpa/request/`, `lpa/common/`, `mismo/`; all ten native XSD files listed individually in FILE_INDEX.md | Request validation and seven unchanged response dependencies. Copy files; do not recreate them from general MISMO knowledge. |
| R3 | LPA S2S Technical User Guide, January 29, 2026; archive `extracted/IMG_3324/` | `transcript.md`, `frames/`, `ocr_resolved.jsonl`, `index.html`; sections IV and V, appendices | Submit/retrieve workflow, envelope/DEAL interpretation, persistent identifiers and error handling. Check uncertain OCR against images. |
| R4 | Response entry schema and first wrapper recording; archive `extracted/IMG_3325/` | Entry around 00:20; wrapper from about 00:26 onward; `supplemental/` near 11:15.8 | Response-only schema reconstruction. The recorded request wrapper is not a substitute. |
| R5 | Response wrapper continuation; archive `extracted/IMG_3326/` | Continuation to the closing schema; overlap with R4 around displayed lines 2977–3008 | Reconcile declaration order, restrictions, extension groups and primitive overrides. |
| R6 | Credit Reporting Companies and Technical Affiliates; archive `extracted/IMG_3322/` | Cover, CRC rows, technical-affiliate tables and update tabs | Historical reference lookup. Verify date from cover: filename/user labels differ. Keep product columns separate and retain leading zeroes. |
| R7 | Recorded `error_codes.json` and `response_fields.json`; archive `extracted/IMG_3329/` | Error export approximately first 80 seconds; response-field export thereafter through the final closing screen | Partial error dictionary and response navigation. Source export metadata is not proof of original-file identity. |
| R8 | `lpa-specification-bulletin-v6.1.00_12-11-25.pdf` | Release changes | Context for change review; not a replacement for a complete earlier source pack. |
| R9 | `numbered_urla_borrower_information_source_template.pdf`, `numbered_urla_lender_information_source_template.pdf`, `numbered_urla_unmarried_addendum_source_template.pdf`, `ulad-data-relationships.pdf` | Form labels and relationship context | Supplemental mapping evidence. Do not force every LPA field through URLA. |

The original videos were processed and deleted after verification at the user's direction. The preserved frame/OCR archives are the available evidence. They are sampled archives, not proof that every original page or column was captured. Do not require the deleted videos or reconstruct missing detail by guessing.

## Existing reviewed derivations, if supplied

These are development results, not additional original documents. They may accelerate a rebuild but must be labeled as reviewed derivations. They are referenced here without their contents.

| ID | Reference | Use |
| --- | --- | --- |
| D1 | `extracted/source_pack_2026-10-12/LPALoanAssessmentServiceResponse_v1.0.0.xsd` | Checked entry-schema transcription from R4. |
| D2 | `extracted/source_pack_2026-10-12/response_wrapper/wrapper_line_index.json`; `wrapper_ocr_by_capture.txt` in the same directory | Navigate raw wrapper evidence; these are not executable verified schemas. |
| D3 | `extracted/source_pack_2026-10-12/credit_reporting_reference.json` | Reviewed CRC/affiliate transcription with frame references; compare to R6. |
| D4 | `extracted/source_pack_2026-10-12/error_code_reference.json` | Reviewed partial error transcription; compare to R7. |
| D5 | `extracted/source_pack_2026-10-12/response_fields_navigation.json` | Locate response-field frames; not a validated scalar field catalog. |
| D6 | `schemas/response_v6.1/reconstruction.json` | Declaration-level response reconstruction provenance and source frames. Optional baseline audit aid; otherwise recreate from R4/R5. |
| D7 | `review/reconstruct_response_schema.py`, `review/response-reconstruction/` | Historical reconstruction helpers/evidence, if separately supplied. Do not require scratch paths for the runtime. |

The intake report `docs/RECORDING_INTAKE_2026-10-12.md` describes the earlier intake stage. Its “not yet implemented” statements are historical; the release implementation/validation documents describe later work. Neither is a substitute for checking source evidence.

## Useful guide navigation

For R3, use approximately 03:30–03:34 for async retrieval/timing, 03:44–03:56 for DEAL/status structure, 04:06 for error records, 04:10–04:22 for identifiers, 04:48 for feedback identifiers, 05:06 for HTTP handling, 05:18 for the separate authentication-guide reference, and 05:38–08:30 for appendix examples. These are navigation references, not copied source text.

For R6, examine approximately 00:46, 01:10, 01:26 and 02:18 together with the cover and table headers when reviewing dates and product combinations. For R7, inspect approximately 01:10, 01:50, 02:10, 12:46 and 25:30 for known quality/structure questions. Do not treat OCR matches or displayed sort IDs as verified field counts.

## Inputs still needed for live client testing

The separate API authentication guide, client-environment access setup, actual client repository/data semantics, representative accepted exchanges and confirmed polling timing are not supplied by this guide. Full response business definitions and full proxy/data-quality dictionaries remain incomplete. An authentic earlier release is needed to verify a real upgrade rather than the synthetic upgrade example. See [client readiness](CLIENT_READINESS_AND_DELIVERY.md).

When an input is absent, finish independent parts and name the precise blocked artifact. Do not create fake schemas, invent an authentication flow, or present fabricated service results as genuine exchanges.
