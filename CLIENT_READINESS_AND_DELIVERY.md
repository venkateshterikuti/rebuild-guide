# Before a client live test, and what to give the client

## What is still needed, in simple terms

The current pack is a working rehearsal: a sample client sends a loan to a simulated service, waits for updates, saves results and submits changes later. A client live test needs these additional pieces.

| Needed | Plain-language explanation | Who supplies or implements it |
| --- | --- | --- |
| The real client's application and example data | We must connect the client's actual “send for assessment” action and understand where its borrower, loan, property, income and other data come from. The sample application does not establish those meanings. | Client development/business teams provide the repository or agreed interface, representative sanitized samples and field explanations; the integration team adapts the code. |
| The actual connection and login method | The pack currently talks to a simulator. It still needs the approved client-environment connector that sends real requests and obtains/renews the correct credentials. A URL change alone is insufficient. | API owner supplies the separate authentication contract and environment instructions; client/integration developers implement and configure the adapter in the authorized environment. Credentials stay there. |
| A complete loan for the chosen test case | The synthetic example demonstrates mechanics and intentionally omits much real loan data. Schema checks and 26 selected rules do not prove a complete application. | Business owners agree the first product/scenario and all data it requires; developers complete that mapping and validation. |
| Confirmed wait/retry behavior | We need the real meaning of the service's wait interval and agreed handling of expired login, failed calls, lost responses and repeated clicks. | API documentation/owner confirms the contract; client team integrates scheduling and recovery. The mock's timing and credential settings are test assumptions. |
| A place to save and show results | The real application must retain submission/loan IDs across restarts, display appropriate results/errors and avoid sending a duplicate loan after an uncertain outcome. | Client team agrees its database, background work and user workflow; developers adapt the existing runtime interfaces. |
| A controlled test and an expected result | Start with an agreed test loan/scenario in the approved environment, compare observed results, then share sanitized feedback. Include both success and failure cases before broadening the pilot. | Client/API teams provide approved test access and expectations; user runs live tests and returns structured diagnostics or sanitized exchanges. |

The immediate material request is the client's stack/repository or integration interface, its sanitized sample data with field meanings, and the separate authentication/environment specification. Confirm timing and expected service behavior before the live run. No more recordings are required merely to try the mock demo.

Full response/feedback definitions, authoritative response-schema confirmation and additional product rules are needed as the pilot covers more cases. A missing code dictionary need not prevent the first narrow test if unknown results are surfaced for review. Before any wider rollout, resolve the gaps relevant to the supported products and check the client's regression scenarios. Live testing is evidence gathering, not a production-readiness claim.

FM API access remains prohibited from the current machine. The user's live tests belong in the separately authorized client environment.

## Does every file go to the client?

**For the client's development team starting the pilot: give the intact 0.3.0 starter ZIP.** It is approximately 2 MB compressed and already excludes videos, OCR archives, storage scans, private outputs, scratch work and virtual environments. This avoids accidentally removing a dependency or the evidence needed to understand a limitation.

The client does not need to read every file. Start with `README.md`, `docs/MOCK_INTEGRATION.md` and the entry prompt for its chosen agent. The remaining files support execution, testing and traceability.

| Part of the starter pack | Why present | Needed in a later deployed client application? |
| --- | --- | --- |
| `lpa_tools/`, `pyproject.toml`, `lpa-project.json` | Runtime, templates, installation metadata and specification paths | Runtime/configuration and installed dependencies are required; templates are primarily build-time, but retaining the package intact is simplest. |
| `kb/lpa_v6.1/`, native request XSD tree, `schemas/response_v6.1/` | Field/rule references and local request/response validation | Keep the files selected by the configuration and their complete pinned schema trees. Do not delete an apparently unused XSD: source-identity checks cover the configured tree. |
| Native request workbook | Source traceability, catalog rebuilding and release updates | Useful in the developer pack; normal validation uses its derived catalog, so deployments can keep the workbook separately once the installation is packaged and verified for that mode. |
| `skills/`, `adapters/` | Instructions for the client's coding agent | Needed during agent-assisted integration/change work; not needed by a deployed application calling the runtime directly. Keep at least the applicable entry prompt if curating a developer kit. |
| `examples/`, `tests/` | Demo, regression fixtures and verification | Keep for onboarding, development and regression testing. The `demo` command requires pilot examples, so removing them disables that workflow. |
| `scripts/` | Example regeneration and release packaging | Developer/release tooling, not the deployed assessment path. |
| `docs/`, `README.md`, `AGENTS.md`, manifests | Operating instructions, limitations, provenance and file identity | Keep with the development delivery. Deployment documentation can be curated after its exact configuration is settled. |

The client's actual mapping profile, application adapter, approved live connector and environment configuration are additional client-specific deliverables. Sending the generic ZIP does not create them automatically. The client also needs Python and the declared Python dependencies, even if its application uses a Java/C# CLI bridge. The ZIP does not embed a Python runtime or dependency wheels.

The new rebuild guide is for maintainers or another agent recreating the toolkit. It is a separate optional handoff, not a runtime dependency and not something every business user needs. Supply original material separately to that rebuilding agent, as requested. A smaller deployment bundle has not been produced or tested; do not label a hand-pruned folder as a verified distribution.
