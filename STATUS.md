# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest pushed commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Planning Issues | Latest Verified Commit | Verified Scope and Tests | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [a3bb251](https://github.com/siliconcordat/.github/commit/a3bb251) | Org profile, `MASTER-PLAN.md`, `CONTRIBUTING.md`, live tracker | **Verified** (4/4 gates, Issue 1 live) |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issue 1 live](https://github.com/siliconcordat/mde/issues) | [7ce5a4d](https://github.com/siliconcordat/mde/commit/7ce5a4d) | Rust CST broker, `mde guard`, `zone-manifest`, `mde integrity` (`36/36` files), `mde seam-verify` (`24/24` cargo tests, 0 clippy warnings) | **Verified** at `7ce5a4d` (4/4 gates + live `exo` interop) |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issue 1 live](https://github.com/siliconcordat/exo/issues) | [e9a882b](https://github.com/siliconcordat/exo/commit/e9a882b) | Zero-dep stdlib kernel, gate, SIM, multi-MDE router (`29/29` unittest). Building full 4-layer vertical integration suite. | **Verified** at `e9a882b` (4/4 gates + live `mde` interop) |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issues 1 and 2 live](https://github.com/siliconcordat/warp/issues) | [d3303fb](https://github.com/siliconcordat/warp/commit/d3303fb) | `warp-modeld` 4-stage gate, zero-sudo `mkosi`, `repair-ledger`, strict JSON, opt-in live `llama-server` probe (`41/41` unittest, `-O` clean, `3/3` live probe) | **Verified** at `d3303fb` (4/4 gates + Issue 2 live) |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issue 1 live](https://github.com/siliconcordat/weft/issues) | [f707efd](https://github.com/siliconcordat/weft/commit/f707efd) | Deterministic `BetaEdit` compiler, GGUF LoRA, E1 to E3 (`TinyStories-1M`, `23/23` pytest). Building E4 asymmetric `INT8-A / INT4-B` + L2 branch excavation. | **Verified** at `f707efd` (4/4 gates, E1 to E3 reproduced) |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issue 1 live](https://github.com/siliconcordat/loom/issues) | [982aa26](https://github.com/siliconcordat/loom/commit/982aa26) | 6 research docs (`docs/01` to `docs/06`: 80-repo unmerged branch excavation) + `verify_math.py` + `verify_convergences.py` (`10/10` unittest, `-O` clean) | **Verified** at `982aa26` (4/4 gates) |

Note: Layer rows link to each repository's `issues` page so single-file duplicate-reference checks stay clean.

## Cross-Team Handoffs

- **All 6 Repos Independently Verified (6 of 6 green, `127/127` core tests + `3/3` live `llama-server` probe):** Every repository passed privacy/secret scanning, `check-prose.py` + `--dupes` (including live issue read-back), live test/math execution, and claim-honesty review.
- **Wave 2 Verified Landings:** `siliconcordat/mde` (`7ce5a4d`) completed the full L5 executable surface (`mde guard`, `zone-manifest/v0.1`, `mde integrity`, `mde seam-verify`). `siliconcordat/warp` (`d3303fb`) landed L3/L4/L5 13-public-repo excavation refinements (zero-sudo `mkosi`, trusted ancestor modes, archival `repair-ledger`, duplicate-key JSON rejection, live `llama-server` flag probe) and Issue 2. `siliconcordat/loom` (`982aa26`) landed the 80-public-repo excavation (`220` open PRs, `469` branches) and Asymmetric Factor Leakage Theorem.
- **Wave 2 Finishing:** `siliconcordat/exo` is completing the live 4-layer vertical integration test across compiled `mde` + `exo` + `warp` + `weft`. `siliconcordat/weft` is running E4 asymmetric `INT8-A / INT4-B` quantization on `TinyStories-1M` and L2 public branch excavation. `siliconcordat/loom` `docs/06` Section 5 will fold in the L2 to L5 excavation findings once `weft` posts.
- **Hardware Bring-Up Queue:** Ready for live open-weights experiments on the 8 GiB VRAM compute laptop (`warp` dual-boot) and read-only user-space `llama-server` validation on the 64 GiB unified-memory Mac hub once the 4-layer vertical suite and E4 clear verification.
