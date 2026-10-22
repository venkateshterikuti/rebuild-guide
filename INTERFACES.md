# Interfaces that keep the rebuilt files compatible

These are implementation contracts for generated tool files. Domain values, complete XML paths, source schema declarations and reference-table contents must be obtained from the separately supplied materials in INPUT_REFERENCES.md.

## Shared identities and profiles

| Object | Required relationship |
| --- | --- |
| Catalog | `catalog_id` is the canonical digest of the catalog without that key. It includes source fingerprints and retained evidence. |
| Rules | `catalog_id` pins the reviewed catalog; the rule object's own digest is recorded separately. Its rule version does not have to equal the Python package version. |
| Response manifest | Its canonical digest is `response_schema_id` in configuration; its file hashes cover all nine response XSDs. |
| Mapping profile | `profile_format`, `client_id`, `catalog_id`, `scope`, `structural_review`, `mappings`, `template`, `decisions`, `unresolved`; examples also identify themselves as synthetic. |
| Mapping | `field_key`, confirmed `status`, nonblank `reason`, exactly one `source`/`constant`, optional `transform`, `enum_map`, `on_missing`, optional `code_locations`. |
| Template node | `tag`, optional `repeat`, `text`, `attributes`, `children`. A mapped value is an object naming its mapping; direct structural bindings are restricted to reviewed link/sequence attributes. |
| Runtime | Identity combines catalog ID, rules digest and response manifest ID. |
| Active assessment | Identity additionally includes the full reviewed profile digest and polling policy. Retain the original configuration for recovery. |

Root/current JSON pointers use `$`/`@`, slash segments and standard `~0`/`~1` escaping. The missing sentinel is separate from JSON null. Identity and enum transformations preserve false/zero; decimal conversion does not silently round. Values from source data are never executed as expressions.

## Transport and application boundary

- `Request`: method, relative path, string-to-string headers and byte body. Headers/body are excluded from object representation.
- `Response`: integer HTTP-style status and byte body, with body excluded from representation.
- `Transport.exchange(request)` returns a Response or raises an uncertain-delivery error. The only implementation shipped in the baseline is the in-process mock.
- `HeaderProvider.headers(now)` returns credentials for one exchange. Mock credentials are explicitly fictional; real token acquisition is not implemented.
- `Clock.now()` returns finite seconds with a consistent basis. `poll` returns a wait instruction instead of sleeping or starting its own scheduler.
- `PollPolicy` requires an interval unit and basis. Library defaults are 20 retrievals and 300 elapsed seconds; the demo uses 5 and 180. These are local client limits, not service requirements. The simulation uses seconds, a mock token lifetime of 20 and two changing intervals; see acceptance tests for the synthetic schedule.
- `Toolkit.build(data, profile)` returns `(xml, report)` on implemented-check success or `(None, report)` on validation failure. Profile errors remain explicit exceptions. `validate` and `analyze` use local pinned schemas.
- `LoanIntegration` translates the sample application's local key, stable submission ID and explicit resubmission flag into calls to `AssessmentClient`.

## Stored assessment state

The state-store record has `revision`, `identifiers` and `transactions`. Identifiers retain the two supported loan-ID kinds. Each transaction records at least:

- `operation_id`, `input_id`, `runtime_id`, `request_sha256`;
- `state`, `started_at`, `retrievals`, `events`;
- for a pending transaction, `last_response_at`, `async_id`, `interval_value`, `next_poll_at`;
- validated `results` containing interpreted loans, feedback and errors when available.

Persist intent before invoking headers/transport. Compare-and-swap writes require the prior revision; concurrent writes fail instead of silently replacing a newer record. Event metadata records operation/time, HTTP/schema/processing state, response hash and diagnostic codes/issues, without headers or raw payloads.

| State category | Values / behavior |
| --- | --- |
| No exchange yet | `not_started`; validation failures return `validation_failed` without a service call or saved transaction. |
| Active intent / waiting | `submitting`, `retrieving`, `pending`; a restart must not automatically repeat a saved submit intent. |
| Uncertain / unresolved | `submission_unknown`, `retrieval_unknown`, `review_required`, `client_limit_reached`, `credential_refresh_error`; block a replacement submission until resolved. |
| Terminal service result | `completed`, `processing_error`, `transport_error`; a new intentional submission requires explicit resubmission. |
| Failed before any submit | `credential_provider_error`; no request was sent by the transport. It differs from failed credentials during an existing retrieval transaction. |

The local stable operation ID is a duplicate guard within the same state store, not a remote-service idempotency promise. The same operation ID with changed input fails. Caller-provided `__lpa` is forbidden; the runtime injects stored-ID arrays and verifies their actual serialized request context before resubmission.

`snapshot` defaults to identifiers represented by presence, operation/async IDs removed, and `results_available` instead of actual results. `include_values=True` is the deliberate private result-access path. `reconcile` requires saved response bytes/status, the expected request hash and reviewed external correlation. It performs no new submit and does not independently prove that an external response belongs to the loan.

## Reports and command conventions

Validation keeps XML, schema and selected business results separate, using `fail`, `incomplete` or `checks_passed_partial_coverage` for overall request status. It includes source/rules identity and `submission_ready: false`. A failed request build sets `request_written: false` and preserves existing XML output.

Response reports separate `transport`, `schema`, `processing_status`, `underwriting_approval`, `issues`, `loans`, `polling`, `errors`, `feedback` and unknown-node inventory. Private values require explicit opt-in. HTTP/processing and underwriting meanings are not interchangeable. Refer to R3–R5 for actual wire structure.

Feedback exports accept structured client states and keep only toolkit version, approved statuses and allowlisted diagnostic metadata; unknown issue/code strings become hashes. They must not copy arbitrary extra keys or claim to scrub arbitrary raw logs.

CLI commands emit JSON. `--config` selects a portable local source pack. User input/output paths remain relative to the working directory. Fresh-directory workflows refuse existing destinations. Exit 2 denotes failure/review, including intentional single-scenario faults. The full demo exits 0 only when each scenario reached its expected outcome; it must not suppress unexpected failures.

Read the corresponding file recipe for each implementation. These shared contracts prevent one independently generated module from silently disagreeing with another.
