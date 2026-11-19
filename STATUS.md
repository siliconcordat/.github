# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest pushed commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Planning Issue (Issue 1) | Verified Commit | Shipped v0.1 Scope and Tests | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [ada6de8](https://github.com/siliconcordat/.github/commit/ada6de8) | Org profile, `MASTER-PLAN.md`, `CONTRIBUTING.md`, live tracker | **Verified** (4/4 gates, Issue 1 live) |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issue 1 live](https://github.com/siliconcordat/mde/issues) | [7bcbcb7](https://github.com/siliconcordat/mde/commit/7bcbcb7) | Rust CST broker, CLI + stdio MCP (`15/15` cargo tests, 0 clippy warnings) | **Verified** at `7bcbcb7` (4/4 gates + live `exo` interop) |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issue 1 live](https://github.com/siliconcordat/exo/issues) | [e9a882b](https://github.com/siliconcordat/exo/commit/e9a882b) | Zero-dep stdlib kernel, gate, SIM, multi-MDE router (`29/29` unittest) | **Verified** at `e9a882b` (4/4 gates + live `mde` interop) |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issue 1 live](https://github.com/siliconcordat/warp/issues) | [1593938](https://github.com/siliconcordat/warp/commit/1593938) | `warp-modeld` 4-stage load verifier + OS blueprints (`38/38` unittest) | **Verified** at `1593938` (4/4 gates, `-W error` clean) |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issue 1 live](https://github.com/siliconcordat/weft/issues) | [f707efd](https://github.com/siliconcordat/weft/commit/f707efd) | Deterministic `BetaEdit` compiler, GGUF LoRA, E1 to E3 (`TinyStories-1M`, `23/23` pytest) | **Verified** at `f707efd` (4/4 gates, E1 to E3 reproduced) |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issue 1 live](https://github.com/siliconcordat/loom/issues) | [f435eea](https://github.com/siliconcordat/loom/commit/f435eea) | 5 research docs (`docs/01` to `docs/05`) + `verify_math.py` + `verify_convergences.py` (`10/10` unittest) | **Verified** at `f435eea` (4/4 gates) |

Note: Layer rows link to each repository's `issues` page (where Issue 1 is live) so single-file duplicate-reference checks stay clean.

## Cross-Team Handoffs

- **All 6 Repos Independently Verified (6 of 6 green):** Every repository passed privacy/secret scanning, `check-prose.py` + `--dupes` (including live Issue 1 read-back), live automated test and math verification (`115/115` passing tests across the five technical layers), and claim-honesty review.
- **Verified Cross-Layer Interop:** Live Python `exo` drove the compiled Rust `mde` stdio MCP binary across all five verbs and produced a clean Git commit while failing closed on real `mde` `isError` refusals.
- **Next Active Hardening Wave:** `siliconcordat/mde` is building native Rust `mde guard`, canonical `zone-manifest`, and real-corpus stress conformance. `siliconcordat/exo` is wiring the full 4-layer vertical integration test across live `mde`, `exo`, `warp`, and `weft`.
- **Hardware Bring-Up Queue:** Ready for live open-weights experiments on the 8 GiB VRAM compute laptop (`warp` dual-boot) and read-only user-space `llama-server` validation on the 64 GiB unified-memory Mac hub once the 4-layer vertical integration suite passes.
