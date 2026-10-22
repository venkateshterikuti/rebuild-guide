# What “the same files” can mean

The recipes preserve file roles, public interfaces, dependencies, implementation decisions and observable checks for version 0.3.0. They are intended to let another agent build an equivalent toolkit from the supplied input material. They do not make an untested promise that any model will produce identical source code.

| Goal | What is required |
| --- | --- |
| Same behavior and architecture | Follow the recipes, inspect the separately supplied evidence and pass the acceptance checks. Independent source formatting and helper structure may differ. |
| Same derived data identities | Use the exact same native inputs and canonical extraction/serialization rules. Inspect a changed hash; do not force it to match by editing a fingerprint. |
| Byte-for-byte identical existing files | Preserve or copy the original release ZIP and verify its manifest. A prose prompt cannot reliably recreate arbitrary source formatting, documentation wording or normalized transcription bytes. |
| Byte identity with unavailable original response wrapper | Not established by the current toolkit or this guide. The response wrapper is a reviewed reconstruction. |

`BASELINE_FILES.json` records historical hashes and sizes as comparison targets. A changed code/document hash can be compatible with equivalent behavior. A changed source/schema/catalog hash requires evidence review and coherent regeneration of dependent manifests/profiles; do not bypass pin checks merely to make tests pass.

Do not copy historical validation claims into a rebuilt release as if the new run established them. The baseline passed 100 tests and 11 mock scenarios; record the new run's actual result, environment and coverage. Added tests may appropriately increase the count. A count alone does not prove the checks are meaningful.

This guide was checked for coverage, file identity and internal links. A second agent has not independently rebuilt the whole product from only this guide and the input materials. Therefore reproducibility is a documented design objective with a verification procedure, not an independently demonstrated result.

The original starter ZIP remains unchanged. The guide's separate archive contains instructions and metadata only, with no original input contents, executable toolkit source snapshot, recordings or credentials.
