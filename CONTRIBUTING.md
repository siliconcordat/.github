# Contributing to Siliconcordat

Siliconcordat is an open-development organization. Every human contributor and AI agent team follows the same plain-language, verification-first workflow.

## Core Collaboration Rules

- **Public hygiene is mandatory.** Never commit or post private repositories, personal data, credentials, secret tokens, local filesystem paths, or internal chat logs.
- **Licensing.** All code is licensed under Apache-2.0. All documentation and specifications are licensed under CC BY 4.0.
- **Clean git authorship.** Write clear, hand-written commit messages. Do not include automated co-author trailers. Never force-push or rewrite shared history on `main`.
- **Independent verification.** The author of a code change or deploy never acts as its sole verifier or merger. A separate reviewer checks the exact commit hash against live test output.
- **Claim honesty.** Tag every technical statement by its actual standing: `verified` (checked with a rerunnable command and verbatim output), `proposed` (design intent not yet measured), or `source claim` (quoted from an external source, not yet reproduced here). Negative results are valid findings and stay recorded.

## Three Review Lanes

Review follows what a change touches, not only which repository it lives in:

| Lane | Scope | Required Checks | Merge Rule |
| --- | --- | --- | --- |
| **Build** | Source code, schemas, CI, build scripts, packaging | Reproducible build, passing automated tests on the exact commit, security and privacy scan, no skipped or faked assertions | Independent reviewer approval on exact head commit |
| **Record** | Experiment logs, benchmarks, audits, incident reports | Stated hypothesis or question, rerunnable commands, committed or hashed outputs, explicit limits | Independent reviewer checks method and evidence |
| **Idea** | Design notes, architecture proposals, roadmaps | Clearly marked as proposed, zero false claims about shipped code, no secrets or private data | One review pass or agreed review window |

A change touching two lanes must pass both checklists.

## Mandatory Pre-Publish Gates

Run every applicable check before pushing commits or opening issues and pull requests:

1. **Plain-language prose gate.** Write short, direct sentences using common words. Explain technical terms on first use. Avoid em dashes, clause-stitching semicolons, filler openers, and repeated links or issue numbers. Run the prose gate and duplicate-reference check (`check-prose.py` and `--dupes`) with exit code 0 on every markdown file and issue body.
2. **Privacy and secret scan.** Verify zero credentials, zero private repository leaks, and zero machine-specific home paths appear in diffs, logs, or test fixtures.
3. **Executable proof.** Run the full local test suite (`cargo test`, `pytest`, or `unittest`) and record exact commands and pass counts in the pull request or verification report.
4. **GitHub issue and PR format.** Pass issue and PR bodies via `--body-file`. Automated agent posts end with one disclosure line: `> Automated posting by agentic team with human oversight.` After posting, read the live item back via the API to confirm exact bytes.

## Working Across Layers

Each repository owns one clean boundary in the five-layer stack:

- `mde` owns the L5 structural broker protocol, syntax zone tags, and Plane 1 integrity layer.
- `exo` owns the L4 agent harness, exact-byte approval gate, causal improvement memory, and dynamic adapter router.
- `warp` owns the L3 OS sandboxing, fail-closed model load verifier (`warp-modeld`), and snapshot recovery layer.
- `weft` owns the L2 deterministic weight compiler, fixed-radix certificates, and multi-adapter composition experiments.
- `loom` owns L1 hardware physics theory and cross-stack frontier research.

Cross-layer changes pin exact commit hashes and contract schemas rather than copying code across repositories. Report cross-layer defects directly to the owning repository as focused issues with minimal reproduction steps.
