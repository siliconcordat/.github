# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest pushed commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Planning Issue (Issue 1) | Latest Pushed Commit | Step 2 Build Status | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [f4e6e68](https://github.com/siliconcordat/.github/commit/f4e6e68) | Maintaining live tracker | Submitted for check |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issue 1: MDE v0.1 protocol and Rust CST broker](https://github.com/siliconcordat/mde/issues) | [c22581d](https://github.com/siliconcordat/mde/commit/c22581d) | Step 2 building | Pending Step 2 handoff |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issue 1: L4 Exo architecture and plan](https://github.com/siliconcordat/exo/issues) | [7c4118d](https://github.com/siliconcordat/exo/commit/7c4118d) | Step 2 building | Pending Step 2 handoff |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issue 1: Warp L3 OS initial plan](https://github.com/siliconcordat/warp/issues) | [128ca4a](https://github.com/siliconcordat/warp/commit/128ca4a) | Step 2 building | Pending Step 2 handoff |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issue 1: Weft v0.1 compiler and verification plan](https://github.com/siliconcordat/weft/issues) | [3d3603d](https://github.com/siliconcordat/weft/commit/3d3603d) | Step 2 building | Pending Step 2 handoff |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issue 1: L1 hardware theory and frontier research](https://github.com/siliconcordat/loom/issues) | [d5564c2](https://github.com/siliconcordat/loom/commit/d5564c2) | Step 2 authoring | Pending Step 2 handoff |

## Cross-Team Handoffs

- **Step 1 Complete (6 of 6 repos):** All six public repositories are created, initialized on `main` under Apache-2.0 / CC BY 4.0, and carry their initial architecture and build plan in Issue 1.
- **Independent Verification Queue:** Each repository clears four independent gates (privacy and secret scan, prose and duplicate-reference check, live executable tests, and claim-tier honesty audit) before being marked verified in the table above.
- **Hardware Bring-Up Queue:** Pending Step 2 verification of `weft`, `warp`, `exo`, and `mde` before running live open-weights experiments on the 8 GiB VRAM compute laptop and read-only user-space `llama-server` checks on the 64 GiB unified-memory Mac hub.
