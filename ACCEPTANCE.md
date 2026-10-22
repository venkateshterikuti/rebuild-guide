# Acceptance checks for a rebuild

Run these against the newly created project, using only local input materials and mocks. Do not call FM endpoints. Check observable behavior rather than matching implementation text or merely obtaining a test count.

## Source and mapping

- Native workbook/XSD bytes match supplied evidence; catalog extraction is deterministic. The baseline has 404 scalar records, 858 populated main-sheet source rows and six preserved reference tables. Different input versions must not be silently treated as this baseline.
- Catalog tampering, wrong schema roots, remote imports, import traversal, malformed XML, DTDs/entities and source drift fail safely.
- Reviewed mapping scope/reasons are required. Wrong-context bindings, unused mappings, unsupported transforms and stale profiles fail.
- Repeated borrowers/assets retain distinct scopes and reviewed ownership. Missing/null/zero/false differ; unknown enums and unapproved rounding do not silently pass.
- Native XSD checks precede the selected business checks. Negative cases cover boundary lengths, allowed values, presence, six cardinalities, xlink targets, borrower ownership and sibling sequences. Reports preserve partial coverage.

## Saved responses and transactions

- Reversing DEAL order or putting errors in echoed input does not change interpretation of the real response. Namespace lookalikes do not count.
- Conflicting/missing status, ambiguous fields, malformed data, invalid intervals and response-schema violations require review.
- Unknown feedback/error codes remain explicit; no invented meaning, future-length restriction or unique HTTP root cause is asserted.
- Saved replay validates chronology and explicit timing basis. Early retrieval is not applied. Changed async IDs/conflicting loan IDs fail without replacing stored identity. Blank terminal identifiers preserve existing values.
- Non-200 responses stop automatic retrieval. Processing completion remains separate from underwriting approval.

## Application behavior

- The pilot starts with an unconnected assessment action. The demo copies it, applies five reviewable file changes and runs its two existing tests plus an application integration test.
- Successful mock submission completes after changing intervals; simulated credentials refresh; result values are stored privately. The baseline simulated call times are 0, 15 and 45, an implementation test choice, not asserted FM timing.
- Repeating the same operation ID does not issue another POST. The same ID with changed data fails. Explicit resubmission preserves and serializes stored loan IDs.
- A restart resumes stored state. Concurrent changes fail their revision check. Transport reentry cannot issue a duplicate submission.
- Lost POST/GET responses create uncertain states, never automatic duplicate submissions. Explicit saved-response reconciliation needs the original request hash and reviewed correlation basis.
- Credential failure before GET preserves the existing service transaction and blocks a replacement POST. Clock reversal, excessive intervals and client polling budgets stop unsafe progress.
- All 11 mock scenarios reach their expected states: successful completion, processing error, HTTP 400/401/429/500, malformed response, uncertain submit/retrieve, identifier conflict and continuing Partial responses up to the client limit.
- Repository inventory executes nothing. Change plans reject traversal/symlinks, stale edits and tampering; failed application rolls back its own writes without overwriting unrelated edits.
- Structured feedback excludes raw payloads, credentials and identifiers, preserves allowed diagnostic fields and hashes unrecognized codes. It is not a general raw-log sanitizer.
- Synthetic upgrade identifies the affected mapping and rejects its stale profile. Original source inputs remain unchanged.

## Commands after installation

Run from the new project root. Substitute the environment's Python executable if needed. Each output directory below must be fresh.

```sh
python -m unittest discover -s tests -v
python -m lpa_tools demo --out outputs/rebuild-demo
python -m lpa_tools mock-run examples/pilot/application.json --profile examples/pilot/profile.json --resubmit --out outputs/rebuild-assessment
python -m lpa_tools feedback-export outputs/rebuild-assessment/assessment.json --out outputs/rebuild-feedback.json
python scripts/build_bundle.py
```

The baseline has 100 main-suite tests; the pilot tests run inside its demo as well. Expected fault outcomes should make the scenario test pass, not cause the harness to ignore errors. A failing individual mock run returns exit 2; the demo succeeds only after verifying each expected outcome.

## Packaging and independent installation

1. Check the ZIP allowlist and every manifest hash. Exclude recordings, extraction helpers, review scratch work, private client data, generated state/output files and virtual environments.
2. Unpack into a fresh directory and install into a separate environment/target using locally available dependencies. The existing release was tested using `--no-index --no-deps --no-build-isolation`; that requires dependencies and build tooling to already be available.
3. Verify `lpa_tools.__file__` belongs to the installed target, then run the unpacked tests from an unrelated working directory, including a path containing spaces. Block Python connection/DNS functions in the test processes; schema resolvers must independently remain local-only.
4. Exercise the demo, explicit resubmission, feedback export, handoff, saved replay, upgrade comparison and generated Python bridge using installed template resources.
5. Generate Java/C# templates; compile only if those toolchains are available and permitted. Record unperformed compiler/provider tests honestly. Do not install tools merely to hide an unavailable check.
6. Validate the shared skill's frontmatter, local references and substantive workflow. Use the local skill validator if available; it is not a runtime dependency or provider-host certification.
7. Write the rebuilt release's validation evidence with actual results. Preserve the original 0.3.0 package separately if doing a new release.
