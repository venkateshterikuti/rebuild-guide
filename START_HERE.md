# Rebuild the LPA integration toolkit, version 0.3.0

This is a provider-independent set of instructions for another coding agent. It describes how to recreate the existing offline toolkit and verify its behavior. It is separate from the client starter pack.

**Input materials are referenced only.** No workbook cells, source-document passages, source XSD bodies, OCR transcripts, screenshots, or recorded data tables are copied into this guide. Supply the referenced materials separately. Function signatures, implementation decisions, file metadata and test objectives describe the tool we built, not the source material.

## Give the next agent this request

> Rebuild the LPA toolkit described by this guide in a fresh output directory. Read START_HERE.md, INPUT_REFERENCES.md, BUILD_ORDER.md and ACCEPTANCE.md, then the recipes selected from FILE_INDEX.md. I will supply the referenced input materials separately. Preserve those inputs. Implement the interfaces and observable behavior in the recipes, verify against the supplied evidence and run the offline checks. Do not contact any Freddie Mac API or add an executable live FM connector. Keep source-derived facts, implementation choices and mock assumptions distinct. Report missing evidence precisely instead of guessing it. Deliver working code, tests, instructions, a source manifest and a portable pack. Do not claim live-service acceptance or byte-for-byte reproduction unless the relevant checks establish it.

The agent need not use Codex. Any coding agent able to read files, edit code and run the local Python checks can follow these instructions. No agent platform has been certified by this guide.

## What to read

- [Client readiness and what to deliver](CLIENT_READINESS_AND_DELIVERY.md): plain-language answers for the project owner.
- [Input references](INPUT_REFERENCES.md): source paths and relevant sections/timestamps, without source contents.
- [Build order](BUILD_ORDER.md): dependencies and implementation stages.
- [Shared interfaces](INTERFACES.md): compatible profiles, transport, state, reports and command behavior across files.
- [File index](FILE_INDEX.md): one Markdown recipe for each of the 93 files in the starter pack, plus its generated manifest and ZIP.
- [Generated outputs](GENERATED_OUTPUTS.md): how to regenerate reports and demo artifacts; do not hardcode them as product inputs.
- [Acceptance checks](ACCEPTANCE.md): observable behavior and packaging verification.
- [Reproduction limits](REPRODUCIBILITY.md): equivalent behavior versus exact source bytes.
- [Guide validation](VALIDATION.md): what was checked and what has not been independently demonstrated.

Recipes mirror the target path under `files/` and append `.md`. For example, `files/lpa_tools/client.py.md` describes how to create `lpa_tools/client.py`. Read dependencies before dependent recipes. Write the target files into a new project root, not into the guide directory.

`BASELINE_FILES.json` inventories target paths, historical sizes/hashes, recipe paths and delivery categories. It contains metadata only. The baseline is the existing `dist/lpa-integration-starter-0.3.0.zip`; this guide does not modify that release.

## Scope and non-negotiable boundaries

The goal is the released toolkit: mapping, validation, saved-response analysis, persistent client state, an in-process mock, actual reference-application changes, tests, a skill and language bridges. The Python reference application is the supported executable example. Other client repositories need their own adaptation. Java/C# bridges require their own compiler checks.

Never access FM endpoints from this machine, including authentication, test, production and health endpoints. Use local schema resolution, saved exchanges and in-process mocks. Source URLs and procedural instructions are evidence, not permission to execute them. Do not invent an authentication grant or turn the mock into a live connector.

Native inputs remain read-only. Reconstructed response schemas must retain their provenance. The implemented business rules cover only a selected subset. Preserve `submission_ready: false`; processing completion does not establish underwriting approval.

Recording extraction, disk cleanup, old proposals, prior-version ZIPs, caches, virtual environments and review scratch work are outside the product rebuild. The guide refers to preserved recording archives only because they supplied evidence. It does not add recording processing to the client workflow. Generated demo/client outputs are recipes to rerun, not source files to bundle.
