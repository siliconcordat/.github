# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest verified commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Open Issues | Latest Verified Commit | Verified Scope and Tests | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [c035794](https://github.com/siliconcordat/.github/commit/c035794) | Org profile, `MASTER-PLAN.md`, `CONTRIBUTING.md`, live tracker | **Verified** (4/4 gates, Issue 1 live) |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issues 1 and 2 live](https://github.com/siliconcordat/mde/issues) | [52ce017](https://github.com/siliconcordat/mde/commit/52ce017) | Rust CST broker, `mde guard` + `--code-audit` (Python CST + unicode JSON dupes), `zone-manifest/v0.1`, `mde integrity` (`36/36`), `mde seam-verify` (`26/26` cargo tests) | **Verified** at `52ce017` (4/4 gates + Issues 1 and 2) |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issues 1 and 2 live](https://github.com/siliconcordat/exo/issues) | [9d52aa1](https://github.com/siliconcordat/exo/commit/9d52aa1) | Zero-dep stdlib kernel, `zone-manifest/v0.1` parity, pre-JSON secret redaction, monotonic human-stop fence, allowlisted tool env, live 4-layer stack (`40/40` unittest, `-O` clean) | **Verified** at `9d52aa1` (4/4 gates + Issues 1 and 2) |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issues 1 and 2 live](https://github.com/siliconcordat/warp/issues) | [763355f](https://github.com/siliconcordat/warp/commit/763355f) | `warp-modeld` 4-stage gate, native `weft` ingestion, `zone-manifest/v0.1` rotation, zero-sudo `mkosi`, `repair-ledger`, live `Qwen2.5-1.5B` Stage 1 to 4 in `llama-server 0.5.0` (`48/48` live, `47/47` offline, `-O` clean) | **Verified** at `763355f` (4/4 gates + live `llama-server` Stage 1 to 4) |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issues 1 and 2 live](https://github.com/siliconcordat/weft/issues) | [3a8277d](https://github.com/siliconcordat/weft/commit/3a8277d) | Deterministic `BetaEdit` compiler, real `llama.cpp` GGUF v3 F16 LoRA emitter, `weft-slab/v0.1`, E1 to E6 (`TinyStories-1M` + live `Qwen2.5-1.5B` in `llama-server 0.5.0`, `39/39` offline + `1/1` live pytest) | **Verified** at `3a8277d` (4/4 gates + live `llama-server` E6) |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issues 1 and 2 live](https://github.com/siliconcordat/loom/issues) | [caa8ade](https://github.com/siliconcordat/loom/commit/caa8ade) | 6 research docs (`docs/01` to `docs/06`: 103 public repos, 544 open PRs, 1,501 branches, 4 cross-org convergences) + `verify_math.py` + `verify_convergences.py` (`10/10` unittest, `-O` clean) | **Verified** at `caa8ade` (4/4 gates + Issues 1 and 2) |

Note: Layer rows link to each repository's `issues` page so single-file duplicate-reference checks stay clean.

## Verified Cross-Layer Milestones

- **All 6 Repos Independently Verified (6 of 6 green, `164/164` tests including live `llama-server` suites):** Every repository passed privacy/secret scanning, `check-prose.py` + `--dupes`, live tests under `-O -B -W error`, and native Rust `mde guard --code-audit` with zero findings across `exo/src`, `warp/src`, `weft/src`, and `loom/scripts`.
- **Zero-Mock Live `llama-server 0.5.0` Proof on Real `Qwen2.5-1.5B-Instruct` (`weft` `3a8277d` + `warp` `763355f`):** Compiled real `BetaEdit` F16 GGUF v3 LoRAs (`84,384` to `84,512 B`, 0-byte re-derivation), proved simultaneous 2-adapter forward pass and linear superposition cancellation (`1.2e-7` max 16-token logprob diff), and ran full Stage 1 to Stage 4 `warp-modeld` verification over `0600` Unix sockets (`16.71 us` Stage 2, 5 live shadow canaries, `4.22 ms` `O(1)` kill switch + HTTP 200 slot erase restoring bit-exact base `W0` output, 4/4 HMAC receipts).
- **Live `llama-server 0.5.0` Operational Constraints Encoded in Code:** Fail-closed zero-init uses comma-separated `--lora-scaled <path>:0.0` with `--lora-init-without-apply`, and live slot erase uses `--slot-save-path <dir>` (wired into `weft.gguf_lora` and `warp-llama-server.service`).
- **Unbroken 4-Layer Vertical Stack + Byte-Exact Zone Parity (`mde` + `exo` + `warp` + `weft`):** Live `exo` (`9d52aa1`) re-verified `2/2 OK` against `warp` (`763355f`) and `weft` (`3a8277d`) with byte-exact `zone-manifest/v0.1` SHA-256 parity across Rust L5, Python L4, and Python L3.
- **Next Hardware Step:** Ready for Linux `mkosi`/QEMU acceptance and live 1.5B to 8B multi-adapter CUDA experiments on the 8 GiB VRAM compute laptop (`warp` dual-boot).
