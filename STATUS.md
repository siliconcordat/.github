# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest pushed commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Planning Issue (Issue 1) | Latest Commit | Verified Scope and Active Wave | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [2e0fe03](https://github.com/siliconcordat/.github/commit/2e0fe03) | Org profile, `MASTER-PLAN.md`, `CONTRIBUTING.md`, live tracker | **Verified** (4/4 gates, Issue 1 live) |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issue 1 live](https://github.com/siliconcordat/mde/issues) | [930a6c7](https://github.com/siliconcordat/mde/commit/930a6c7) | Rust CST broker, native `mde guard`, `zone-manifest`, 19-file stress suite (`21/21` cargo tests, `190/190` 0-byte identity). Building `mde integrity` + `seam-verify`. | **Verified** at `930a6c7` (4/4 gates + live `exo` interop) |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issue 1 live](https://github.com/siliconcordat/exo/issues) | [e9a882b](https://github.com/siliconcordat/exo/commit/e9a882b) | Zero-dep stdlib kernel, gate, SIM, multi-MDE router (`29/29` unittest). Building full 4-layer vertical stack test. | **Verified** at `e9a882b` (4/4 gates + live `mde` interop) |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issue 1 live](https://github.com/siliconcordat/warp/issues) | [d3303fb](https://github.com/siliconcordat/warp/commit/d3303fb) | `warp-modeld` 4-stage gate (`38/38` verified at `1593938`). Pushed Wave 2 hardening (`d3303fb`: zero-sudo `mkosi`, `repair-ledger`, strict JSON, opt-in live `llama-server` probe). | **Verified** at `1593938`. Wave 2 `d3303fb` pending check |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issue 1 live](https://github.com/siliconcordat/weft/issues) | [f707efd](https://github.com/siliconcordat/weft/commit/f707efd) | Deterministic `BetaEdit` compiler, GGUF LoRA, E1 to E3 (`TinyStories-1M`, `23/23` pytest). Building E4 asymmetric `INT8-A / INT4-B` + L2 branch excavation. | **Verified** at `f707efd` (4/4 gates, E1 to E3 reproduced) |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issue 1 live](https://github.com/siliconcordat/loom/issues) | [982aa26](https://github.com/siliconcordat/loom/commit/982aa26) | 6 research docs (`docs/01` to `docs/06`: 80-repo unmerged branch excavation) + `verify_math.py` + `verify_convergences.py` (`10/10` unittest, `-O` clean) | **Verified** at `982aa26` (4/4 gates) |

Note: Layer rows link to each repository's `issues` page (where Issue 1 is live) so single-file duplicate-reference checks stay clean.

## Cross-Team Handoffs

- **All 6 Repos Independently Verified (6 of 6 green):** Every repository passed privacy/secret scanning, `check-prose.py` + `--dupes` (including live Issue 1 read-back), live test/math execution (`121/121` verified passing tests across the five technical layers), and claim-honesty review.
- **Wave 2 Verified Milestones:** `siliconcordat/mde` (`930a6c7`) landed native Rust `mde guard`, canonical `zone-manifest/v0.1`, and `190/190` 0-byte real-corpus CST round-trips. `siliconcordat/loom` (`982aa26`) landed the 80-public-repo unmerged branch excavation (`220` open PRs, `469` non-default branches) and the Asymmetric Factor Leakage Theorem (`17.3x` leakage reduction for `INT8-A / INT4-B`).
- **Wave 2 In Flight:** `siliconcordat/warp` pushed L3 hardening (`d3303fb`). `siliconcordat/exo` is wiring the 4-layer vertical stack test (`mde` + `exo` + `warp` + `weft`). `siliconcordat/weft` is testing `INT8-A / INT4-B` on `TinyStories-1M` and L2 branch excavation. `siliconcordat/mde` is adding native `mde integrity` and `mde seam-verify`.
- **Hardware Bring-Up Queue:** Ready for live open-weights experiments on the 8 GiB VRAM compute laptop (`warp` dual-boot) and read-only user-space `llama-server` validation on the 64 GiB unified-memory Mac hub once Wave 2 clears verification.
