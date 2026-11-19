# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest pushed commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Planning Issues | Latest Verified Commit | Verified Scope and Tests | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [cb64c3f](https://github.com/siliconcordat/.github/commit/cb64c3f) | Org profile, `MASTER-PLAN.md`, `CONTRIBUTING.md`, live tracker | **Verified** (4/4 gates, Issue 1 live) |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issue 1 live](https://github.com/siliconcordat/mde/issues) | [7ce5a4d](https://github.com/siliconcordat/mde/commit/7ce5a4d) | Rust CST broker, `mde guard`, `zone-manifest`, `mde integrity` (`36/36` files), `mde seam-verify` (`24/24` cargo tests). Adding `--code-audit` and Issue 2. | **Verified** at `7ce5a4d` (4/4 gates + live 4-layer stack) |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issue 1 live](https://github.com/siliconcordat/exo/issues) | [1858407](https://github.com/siliconcordat/exo/commit/1858407) | Zero-dep stdlib kernel, gate, SIM, router, `WarpUnixBridge`, live 4-layer vertical stack demo and test (`32/32` unittest, `-O` clean) | **Verified** at `1858407` (4/4 gates + live 4-layer stack) |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issues 1 and 2 live](https://github.com/siliconcordat/warp/issues) | [d3303fb](https://github.com/siliconcordat/warp/commit/d3303fb) | `warp-modeld` 4-stage gate, zero-sudo `mkosi`, `repair-ledger`, strict JSON, opt-in live `llama-server` probe (`41/41` unittest, `-O` clean, `3/3` live probe) | **Verified** at `d3303fb` (4/4 gates + live 4-layer stack) |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issue 1 live](https://github.com/siliconcordat/weft/issues) | [f707efd](https://github.com/siliconcordat/weft/commit/f707efd) | Deterministic `BetaEdit` compiler, GGUF LoRA, E1 to E3 (`TinyStories-1M`, `23/23` pytest). Building E4 asymmetric `INT8-A / INT4-B` and L2 branch excavation. | **Verified** at `f707efd` (4/4 gates + live 4-layer stack) |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issue 1 live](https://github.com/siliconcordat/loom/issues) | [982aa26](https://github.com/siliconcordat/loom/commit/982aa26) | 6 research docs (`docs/01` to `docs/06`: 80-repo unmerged branch excavation) + `verify_math.py` + `verify_convergences.py` (`10/10` unittest, `-O` clean) | **Verified** at `982aa26` (4/4 gates) |

Note: Layer rows link to each repository's `issues` page so single-file duplicate-reference checks stay clean.

## Cross-Team Handoffs

- **Full 4-Layer Vertical Stack Verified Live (`1858407`, `32/32` tests under `-O -B -W error`):** Independent verifier executed the unbroken vertical chain (`L5 mde` compiled Rust MCP -> `L4 exo` ZoneRouter, ApprovalGate, and SIM -> `L2 weft` 3 F16 GGUF LoRAs with 0-byte re-derivation -> `L3 warp` `warp-modeld` Unix socket daemon with `12.8 us` to `16.0 us` Stage 2 checks, 5/5 canaries per mount, and `O(1)` kill switch in `1.714 ms`).
- **Cross-Generation Upgrade and Schema Gaps:** Verified the full `W_old -> W_new` stale rejection, SIM recompile/retire planning, and `weft` recompilation loop with verified HMAC receipts. Four cross-layer schema gaps are documented in `exo/docs/VERTICAL-INTEGRATION.md`.
- **All 6 Repos Independently Verified (6 of 6 green, `130/130` tests + `3/3` live `llama-server` probe):** Every repository passed privacy/secret scanning, `check-prose.py` + `--dupes`, live test/math execution, and claim-honesty review.
- **Wave 2 Final Items In Flight:** `siliconcordat/weft` is running E4 asymmetric `INT8-A / INT4-B` quantization on `TinyStories-1M` and L2 public branch excavation. `siliconcordat/mde` is adding native Python CST `--code-audit` (`assert` under `-O`, bare `except`, duplicate JSON keys), empty-manifest/symlink-cycle hardening, and Issue 2. `siliconcordat/loom` `docs/06` Section 5 will absorb the L2 to L5 excavation findings next.
- **Hardware Bring-Up Queue:** Ready for live open-weights experiments on the 8 GiB VRAM compute laptop (`warp` dual-boot) and read-only user-space `llama-server` validation on the 64 GiB unified-memory Mac hub once E4 and `--code-audit` clear verification.
