# Generated artifacts are recreated by commands

Do not bundle previous client output values or hardcode previously observed results. The recipes in FILE_INDEX.md cover the fixed release files. These additional files are outputs of those implementations and depend on the input/profile/runtime used for a run.

| Producer | Output artifacts | Reconstruction instruction |
| --- | --- | --- |
| `discover`, `map-suggest`, `coverage`, `profile-init`, `profile-check` | Structural inventory, candidate report, coverage, draft profile or checks | Derive from the current sample/catalog and preserve uncertainty. A sample's absence does not establish optionality. |
| `request-build`, `validate` | Request XML and validation report | Render only reviewed mappings; write request output only after implemented checks pass. Do not overwrite a prior valid request on failure. |
| `response-inspect`, `response-analyze`, `transaction-replay` | Structural inspection, response report or replay report | Use supplied local exchange files. Default to omitted values; preserve unknown codes, review states and explicit timing basis. |
| `error-explain`, `vendor-query`, `upgrade` | Reference lookup or upgrade impact report | Use current local references and separately supplied baseline/target; never fetch referenced service URLs. |
| `handoff` | `README.md`, `discovery.json`, `profile.json`, `profile-check.json`, `coverage.json`, `validation.json`, optional `request.xml`, response analyses, optional specification changes, `manifest.json` | Build in a fresh directory. Include generated XML only on success; combine response review into overall state; hash each artifact except the manifest itself. |
| `client-generate` | Language bridge source, optional C# project file, `profile.json`, `README.md`, `manifest.json` | Use installed template resources and the reviewed profile. Keep arguments shell-free and preserve fresh-directory behavior. |
| `repo-inspect`, `repo-plan`, `repo-apply` | Inventory; plan with original/new content and diff; application receipt | Derive from the authorized repository, bind hashes to its current contents and reject intervening edits. Plans contain client code and stay local. |
| `mock-run` | `assessment.json`, `feedback.json`, `coverage.json`, delivered `request-N.xml`, `state.sqlite`, `manifest.json` | Execute the state machine against a fresh in-process service. Do not fabricate a passing report directly. State and request artifacts contain local values; feedback has a separate allowlist. |
| `demo` | Copied `client-application/`; before/after inventories; mapping candidates; `changes.json`, `changes.patch`, `applied.json`; application test log; 11 `scenarios/` directories; synthetic upgrade and migration draft; `summary.json`, `README.md` | Start with the unconnected reference app, apply the adapter changes and run real local assertions. Mark upgrade inputs as synthetic and leave the migration draft unreviewed. |
| `feedback-export` | Allowlisted diagnostic JSON | Export only accepted structured runtime fields; do not claim arbitrary-log sanitization or upload anything. |
| `scripts/build_bundle.py` | Versioned ZIP and internal `BUNDLE_MANIFEST.json` | Follow their individual recipes. Previous ZIPs are release artifacts, not files the new runtime imports. |

The demo's five changes are the application's assessment action, `integration.py`, `lpa_profile.json`, `application.json` and `tests/test_integration.py`. The base application and its draft tests remain in the fixed release inputs; the generated connected copy belongs in the fresh output directory.

Recordings/transcripts/frame archives were input preparation, and storage-review files were a separate task. They have no regeneration role in this product's runtime or client delivery.
