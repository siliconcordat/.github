# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest pushed commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Planning Issue (Issue 1) | Latest Pushed Commit | Step 2 Build Status | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [946825e](https://github.com/siliconcordat/.github/commit/946825e) | Live tracker synced | **Verified** at `f25e35e` (4/4 gates) |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issue 1 live](https://github.com/siliconcordat/mde/issues) | [7bcbcb7](https://github.com/siliconcordat/mde/commit/7bcbcb7) | Rust CST broker + CLI + MCP (`15/15` tests, 0 clippy warnings) | **Verified** at `7bcbcb7` (4/4 gates + live `exo` interop) |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issue 1 live](https://github.com/siliconcordat/exo/issues) | [e9a882b](https://github.com/siliconcordat/exo/commit/e9a882b) | Zero-dep stdlib kernel + gate + SIM + router (`29/29` tests) | **Verified** at `e9a882b` (4/4 gates + live `mde` interop) |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issue 1 live](https://github.com/siliconcordat/warp/issues) | [b8411bc](https://github.com/siliconcordat/warp/commit/b8411bc) | `warp-modeld` 4-stage gate + OS blueprints (`36/36` tests) | Queued for verifier audit |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issue 1 live](https://github.com/siliconcordat/weft/issues) | [ca25735](https://github.com/siliconcordat/weft/commit/ca25735) | Compiler + GGUF LoRA + E1 to E3 (`TinyStories-1M`, `19/19` tests) | In verifier audit |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issue 1 live](https://github.com/siliconcordat/loom/issues) | [bb38758](https://github.com/siliconcordat/loom/commit/bb38758) | 4 research docs + `verify_math.py` (`7/7`), authoring `docs/05` | **Verified** at `bb38758` (4/4 gates) |

Note: Layer rows link to each repository's `issues` page (where Issue 1 is live) so single-file duplicate-reference checks stay clean.

## Cross-Team Handoffs

- **Verified (4 of 6 repos):** `siliconcordat/.github` (`f25e35e`), `siliconcordat/mde` (`7bcbcb7`), `siliconcordat/exo` (`e9a882b`), and `siliconcordat/loom` (`bb38758`) passed all four independent verification gates (privacy/secrets, prose/dupes, live test/math execution, and claim honesty).
- **Live L4 to L5 Interop Verified:** Independent verifier ran `exo` `StdioJsonRpcTransport` + `MdeClient` live against the compiled Rust `mde` binary across all five verbs (`splice_locate`, `splice_trace`, `splice_patch`, `splice_verify`, `splice_project`), verified clean Git projection, and confirmed `isError` rejection handling.
- **In Verifier Queue (2 repos):** `siliconcordat/weft` (`ca25735`) is under active 4-gate audit, followed by `siliconcordat/warp` (`b8411bc`). `siliconcordat/loom` is also authoring `docs/05-spliceware-algebra-and-convergences.md` + `scripts/verify_convergences.py`.
- **Hardware Bring-Up Queue:** Once `weft` and `warp` clear independent verification, proceed to live open-weights experiments on the 8 GiB VRAM compute laptop (`warp` dual-boot) and read-only user-space `llama-server` validation on the 64 GiB unified-memory Mac hub.
