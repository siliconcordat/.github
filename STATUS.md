# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest pushed commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Planning Issue (Issue 1) | Latest Pushed Commit | Step 2 Build Status | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [f25e35e](https://github.com/siliconcordat/.github/commit/f25e35e) | Live tracker syncing | **Verified** at `f25e35e` (4/4 gates) |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issue 1 live](https://github.com/siliconcordat/mde/issues) | [a6d119c](https://github.com/siliconcordat/mde/commit/a6d119c) | Rust CST broker + 12 tests pushed | Fixing 3 Gate 3 findings |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issue 1 live](https://github.com/siliconcordat/exo/issues) | [a6dc867](https://github.com/siliconcordat/exo/commit/a6dc867) | Stdlib kernel + 27 tests pushed | Fixing 2 Gate 3 findings |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issue 1 live](https://github.com/siliconcordat/warp/issues) | [128ca4a](https://github.com/siliconcordat/warp/commit/128ca4a) | Step 2 building `warp-modeld` | Pending Step 2 handoff |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issue 1 live](https://github.com/siliconcordat/weft/issues) | [c46eef2](https://github.com/siliconcordat/weft/commit/c46eef2) | Compiler, GGUF codec, anchors pushed, experiments running | Pending Step 2 handoff |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issue 1 live](https://github.com/siliconcordat/loom/issues) | [bb38758](https://github.com/siliconcordat/loom/commit/bb38758) | 4 research docs + `verify_math.py` (7/7) | **Verified** at `bb38758` (4/4 gates) |

Note: Layer rows link to each repository's `issues` page (where Issue 1 is live) so single-file duplicate-reference checks stay clean.

## Cross-Team Handoffs

- **Verified (2 of 6 repos):** `siliconcordat/.github` (`f25e35e`) and `siliconcordat/loom` (`bb38758`) passed all four independent verification gates (privacy/secrets, prose/dupes, executable/math audit, and claim honesty).
- **In Active Verifier Fix Loop (2 repos):** `siliconcordat/mde` (fixing Tier 2 anchor gating, packet/bundle digest and tree checks, and `.mde/` oracle hashing) and `siliconcordat/exo` (fixing MCP `isError` / `gg.siliconcordat/mde` alignment and git `-c` / `+refspec` gate checks).
- **Step 2 Completing (2 repos):** `siliconcordat/weft` (core package pushed at `c46eef2`, finishing E1 to E3 experiments) and `siliconcordat/warp` (building `warp-modeld` and sandbox/recovery blueprints).
- **Hardware Bring-Up Queue:** Pending Step 2 verification of `weft`, `warp`, `exo`, and `mde` before running live open-weights experiments on the 8 GiB VRAM compute laptop and read-only user-space `llama-server` checks on the 64 GiB unified-memory Mac hub.
