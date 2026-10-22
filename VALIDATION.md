# Validation of this instruction set

The guide was checked against the frozen 0.3.0 starter archive on October 12, 2026.

- Every one of its 93 payload files has an individual recipe. The internal bundle manifest and release ZIP have two additional recipes: 95 total.
- Historical paths, sizes and SHA-256 values match the starter archive. Its hash is recorded in `BASELINE_FILES.json`; the original ZIP was not changed.
- Internal Markdown links resolve within the guide. The main separately supplied source-reference paths were checked locally.
- The guide contains original implementation instructions, interfaces, reference locations and metadata. It does not embed native workbook data, XSD bodies, source-document passages, transcripts, images or recordings.
- Runtime source files were unchanged. Verification for this task concerned guide coverage, metadata, links and packaging; the runtime test suite was not unnecessarily rerun for documentation-only work.
- No FM endpoint was contacted.

This is not an independent reproduction test. Another agent has not yet rebuilt the entire toolkit using only these instructions and separately supplied inputs. See [REPRODUCIBILITY.md](REPRODUCIBILITY.md) for the distinction between equivalent behavior, identical derived data and exact release bytes.

The separate guide ZIP includes its own `GUIDE_MANIFEST.json` with hashes of the instruction files and baseline metadata. It contains neither the original input materials nor a copy of the executable starter package.
