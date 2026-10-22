# File-by-file rebuild index

Coverage: **93 payload files + the internal bundle manifest + the ZIP = 95 individual recipes**. Native inputs have preservation/copy instructions; generated files have implementation/reconstruction instructions. This is the frozen 0.3.0 product scope, not caches, private run outputs or historical intake work.

Read [START_HERE.md](START_HERE.md) and [BUILD_ORDER.md](BUILD_ORDER.md) first. Source material is referenced only; its contents are not embedded.

| Target file | Delivery role | Recipe |
| --- | --- | --- |
| `.gitignore` | instructions / metadata | [Instructions](<files/.gitignore.md>) |
| `AGENTS.md` | instructions / metadata | [Instructions](<files/AGENTS.md.md>) |
| `README.md` | instructions / metadata | [Instructions](<files/README.md.md>) |
| `adapters/README.md` | agent development workflow | [Instructions](<files/adapters/README.md.md>) |
| `adapters/anteroom.md` | agent development workflow | [Instructions](<files/adapters/anteroom.md.md>) |
| `adapters/claude.md` | agent development workflow | [Instructions](<files/adapters/claude.md.md>) |
| `adapters/codex.md` | agent development workflow | [Instructions](<files/adapters/codex.md.md>) |
| `adapters/copilot.md` | agent development workflow | [Instructions](<files/adapters/copilot.md.md>) |
| `docs/IMPLEMENTATION.md` | instructions / metadata | [Instructions](<files/docs/IMPLEMENTATION.md.md>) |
| `docs/MOCK_INTEGRATION.md` | instructions / metadata | [Instructions](<files/docs/MOCK_INTEGRATION.md.md>) |
| `docs/PRODUCT_GUIDE.md` | instructions / metadata | [Instructions](<files/docs/PRODUCT_GUIDE.md.md>) |
| `docs/RELEASE_VALIDATION.md` | instructions / metadata | [Instructions](<files/docs/RELEASE_VALIDATION.md.md>) |
| `examples/pilot/README.md` | demo / regression verification | [Instructions](<files/examples/pilot/README.md.md>) |
| `examples/pilot/application.json` | demo / regression verification | [Instructions](<files/examples/pilot/application.json.md>) |
| `examples/pilot/profile.json` | demo / regression verification | [Instructions](<files/examples/pilot/profile.json.md>) |
| `examples/pilot/repository/app.py` | demo / regression verification | [Instructions](<files/examples/pilot/repository/app.py.md>) |
| `examples/pilot/repository/tests/test_drafts.py` | demo / regression verification | [Instructions](<files/examples/pilot/repository/tests/test_drafts.py.md>) |
| `examples/responses/README.md` | demo / regression verification | [Instructions](<files/examples/responses/README.md.md>) |
| `examples/responses/completed.xml` | demo / regression verification | [Instructions](<files/examples/responses/completed.xml.md>) |
| `examples/responses/partial-updated.xml` | demo / regression verification | [Instructions](<files/examples/responses/partial-updated.xml.md>) |
| `examples/responses/partial.xml` | demo / regression verification | [Instructions](<files/examples/responses/partial.xml.md>) |
| `examples/responses/processing-error.xml` | demo / regression verification | [Instructions](<files/examples/responses/processing-error.xml.md>) |
| `examples/responses/scenario.json` | demo / regression verification | [Instructions](<files/examples/responses/scenario.json.md>) |
| `examples/synthetic/client.json` | demo / regression verification | [Instructions](<files/examples/synthetic/client.json.md>) |
| `examples/synthetic/profile.json` | demo / regression verification | [Instructions](<files/examples/synthetic/profile.json.md>) |
| `kb/lpa_v6.1/catalog.json` | runtime references / provenance | [Instructions](<files/kb/lpa_v6.1/catalog.json.md>) |
| `kb/lpa_v6.1/credit-vendors.json` | runtime references / provenance | [Instructions](<files/kb/lpa_v6.1/credit-vendors.json.md>) |
| `kb/lpa_v6.1/errors.json` | runtime references / provenance | [Instructions](<files/kb/lpa_v6.1/errors.json.md>) |
| `kb/lpa_v6.1/rules.json` | runtime references / provenance | [Instructions](<files/kb/lpa_v6.1/rules.json.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/LPA v6.1 XML Request File Data Requirements_January_2026.xlsx` | native source / catalog rebuild | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/LPA v6.1 XML Request File Data Requirements_January_2026.xlsx.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/DU_ExtensionV3_4_GENERIC_EXT.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/DU_ExtensionV3_4_GENERIC_EXT.xsd.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/LPA_ExtensionV3_4.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/LPA_ExtensionV3_4.xsd.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/LPA_ExtensionV3_4_GRP.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/LPA_ExtensionV3_4_GRP.xsd.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/ULAD_ExtensionV3_4.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/ULAD_ExtensionV3_4.xsd.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/ULAD_ExtensionV3_4_GRP.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/common/ULAD_ExtensionV3_4_GRP.xsd.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/request/GSE_Schema_WrapperV1_1.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/request/GSE_Schema_WrapperV1_1.xsd.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/request/LPALoanAssessmentServiceRequest_v1.0.0.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/lpa/request/LPALoanAssessmentServiceRequest_v1.0.0.xsd.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/mismo/MISMO_3.4.0_B324.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/mismo/MISMO_3.4.0_B324.xsd.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/mismo/xlinkMISMOB324.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/mismo/xlinkMISMOB324.xsd.md>) |
| `loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/mismo/xml.xsd` | runtime schema dependency | [Instructions](<files/loan-product-advisor-v6.1.00-request-file-requirements/XSD_LPA_6.1.00_Dec 2025_Updated 012926/mismo/xml.xsd.md>) |
| `lpa-project.json` | runtime references / provenance | [Instructions](<files/lpa-project.json.md>) |
| `lpa_tools/__init__.py` | runtime / installation | [Instructions](<files/lpa_tools/__init__.py.md>) |
| `lpa_tools/__main__.py` | runtime / installation | [Instructions](<files/lpa_tools/__main__.py.md>) |
| `lpa_tools/assistance.py` | runtime / installation | [Instructions](<files/lpa_tools/assistance.py.md>) |
| `lpa_tools/catalog.py` | runtime / installation | [Instructions](<files/lpa_tools/catalog.py.md>) |
| `lpa_tools/cli.py` | runtime / installation | [Instructions](<files/lpa_tools/cli.py.md>) |
| `lpa_tools/client.py` | runtime / installation | [Instructions](<files/lpa_tools/client.py.md>) |
| `lpa_tools/codegen.py` | runtime / installation | [Instructions](<files/lpa_tools/codegen.py.md>) |
| `lpa_tools/common.py` | runtime / installation | [Instructions](<files/lpa_tools/common.py.md>) |
| `lpa_tools/discovery.py` | runtime / installation | [Instructions](<files/lpa_tools/discovery.py.md>) |
| `lpa_tools/feedback.py` | runtime / installation | [Instructions](<files/lpa_tools/feedback.py.md>) |
| `lpa_tools/handoff.py` | runtime / installation | [Instructions](<files/lpa_tools/handoff.py.md>) |
| `lpa_tools/mapping.py` | runtime / installation | [Instructions](<files/lpa_tools/mapping.py.md>) |
| `lpa_tools/mock_service.py` | runtime / installation | [Instructions](<files/lpa_tools/mock_service.py.md>) |
| `lpa_tools/protocol.py` | runtime / installation | [Instructions](<files/lpa_tools/protocol.py.md>) |
| `lpa_tools/repository.py` | runtime / installation | [Instructions](<files/lpa_tools/repository.py.md>) |
| `lpa_tools/responses.py` | runtime / installation | [Instructions](<files/lpa_tools/responses.py.md>) |
| `lpa_tools/runtime.py` | runtime / installation | [Instructions](<files/lpa_tools/runtime.py.md>) |
| `lpa_tools/state.py` | runtime / installation | [Instructions](<files/lpa_tools/state.py.md>) |
| `lpa_tools/templates/csharp-project.txt` | generation templates | [Instructions](<files/lpa_tools/templates/csharp-project.txt.md>) |
| `lpa_tools/templates/csharp.txt` | generation templates | [Instructions](<files/lpa_tools/templates/csharp.txt.md>) |
| `lpa_tools/templates/integration-python.txt` | generation templates | [Instructions](<files/lpa_tools/templates/integration-python.txt.md>) |
| `lpa_tools/templates/java.txt` | generation templates | [Instructions](<files/lpa_tools/templates/java.txt.md>) |
| `lpa_tools/templates/pilot-test.txt` | generation templates | [Instructions](<files/lpa_tools/templates/pilot-test.txt.md>) |
| `lpa_tools/templates/python.txt` | generation templates | [Instructions](<files/lpa_tools/templates/python.txt.md>) |
| `lpa_tools/transactions.py` | runtime / installation | [Instructions](<files/lpa_tools/transactions.py.md>) |
| `lpa_tools/upgrade.py` | runtime / installation | [Instructions](<files/lpa_tools/upgrade.py.md>) |
| `lpa_tools/vendors.py` | runtime / installation | [Instructions](<files/lpa_tools/vendors.py.md>) |
| `lpa_tools/workflows.py` | runtime / installation | [Instructions](<files/lpa_tools/workflows.py.md>) |
| `lpa_tools/xml_tools.py` | runtime / installation | [Instructions](<files/lpa_tools/xml_tools.py.md>) |
| `pyproject.toml` | runtime / installation | [Instructions](<files/pyproject.toml.md>) |
| `schemas/response_v6.1/lpa/common/LPA_ExtensionV3_4.xsd` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/lpa/common/LPA_ExtensionV3_4.xsd.md>) |
| `schemas/response_v6.1/lpa/common/LPA_ExtensionV3_4_GRP.xsd` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/lpa/common/LPA_ExtensionV3_4_GRP.xsd.md>) |
| `schemas/response_v6.1/lpa/common/ULAD_ExtensionV3_4.xsd` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/lpa/common/ULAD_ExtensionV3_4.xsd.md>) |
| `schemas/response_v6.1/lpa/common/ULAD_ExtensionV3_4_GRP.xsd` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/lpa/common/ULAD_ExtensionV3_4_GRP.xsd.md>) |
| `schemas/response_v6.1/lpa/response/GSE_Schema_Wrapper_ResponseV1_1.xsd` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/lpa/response/GSE_Schema_Wrapper_ResponseV1_1.xsd.md>) |
| `schemas/response_v6.1/lpa/response/LPALoanAssessmentServiceResponse_v1.0.0.xsd` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/lpa/response/LPALoanAssessmentServiceResponse_v1.0.0.xsd.md>) |
| `schemas/response_v6.1/manifest.json` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/manifest.json.md>) |
| `schemas/response_v6.1/mismo/MISMO_3.4.0_B324.xsd` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/mismo/MISMO_3.4.0_B324.xsd.md>) |
| `schemas/response_v6.1/mismo/xlinkMISMOB324.xsd` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/mismo/xlinkMISMOB324.xsd.md>) |
| `schemas/response_v6.1/mismo/xml.xsd` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/mismo/xml.xsd.md>) |
| `schemas/response_v6.1/reconstruction.json` | runtime references / provenance | [Instructions](<files/schemas/response_v6.1/reconstruction.json.md>) |
| `scripts/build_bundle.py` | developer release tooling | [Instructions](<files/scripts/build_bundle.py.md>) |
| `scripts/create_synthetic_example.py` | developer release tooling | [Instructions](<files/scripts/create_synthetic_example.py.md>) |
| `skills/lpa-integrate/SKILL.md` | agent development workflow | [Instructions](<files/skills/lpa-integrate/SKILL.md.md>) |
| `skills/lpa-integrate/agents/openai.yaml` | agent development workflow | [Instructions](<files/skills/lpa-integrate/agents/openai.yaml.md>) |
| `skills/lpa-integrate/references/application.md` | agent development workflow | [Instructions](<files/skills/lpa-integrate/references/application.md.md>) |
| `skills/lpa-integrate/references/responses.md` | agent development workflow | [Instructions](<files/skills/lpa-integrate/references/responses.md.md>) |
| `skills/lpa-integrate/references/workflow.md` | agent development workflow | [Instructions](<files/skills/lpa-integrate/references/workflow.md.md>) |
| `tests/test_integration_runtime.py` | demo / regression verification | [Instructions](<files/tests/test_integration_runtime.py.md>) |
| `tests/test_product.py` | demo / regression verification | [Instructions](<files/tests/test_product.py.md>) |
| `tests/test_responses.py` | demo / regression verification | [Instructions](<files/tests/test_responses.py.md>) |
| `tests/test_toolkit.py` | demo / regression verification | [Instructions](<files/tests/test_toolkit.py.md>) |
| `BUNDLE_MANIFEST.json` | generated release artifact | [Instructions](<files/BUNDLE_MANIFEST.json.md>) |
| `dist/lpa-integration-starter-0.3.0.zip` | generated release artifact | [Instructions](<files/dist/lpa-integration-starter-0.3.0.zip.md>) |
