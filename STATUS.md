# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest pushed commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Planning Issues | Latest Verified Commit | Verified Scope and Tests | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [e69e40a](https://github.com/siliconcordat/.github/commit/e69e40a) | Org profile, `MASTER-PLAN.md`, `CONTRIBUTING.md`, live tracker | **Verified** (4/4 gates, Issue 1 live) |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issues 1 and 2 live](https://github.com/siliconcordat/mde/issues) | [52ce017](https://github.com/siliconcordat/mde/commit/52ce017) | Rust CST broker, `mde guard` + `--code-audit` (Python CST + unicode JSON dupes), `zone-manifest`, `mde integrity` (`36/36`), `mde seam-verify` (`26/26` cargo tests) | **Verified** at `52ce017` (4/4 gates + Issue 2 live) |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issue 1 live](https://github.com/siliconcordat/exo/issues) | [1858407](https://github.com/siliconcordat/exo/commit/1858407) | Zero-dep stdlib kernel, gate, SIM, router, `WarpUnixBridge`, live 4-layer vertical stack (`32/32` unittest, `-O` clean). Adding `zone-manifest` + security hardening + Issue 2. | **Verified** at `1858407` (4/4 gates + live 4-layer stack) |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issues 1 and 2 live](https://github.com/siliconcordat/warp/issues) | [d3303fb](https://github.com/siliconcordat/warp/commit/d3303fb) | `warp-modeld` 4-stage gate, zero-sudo `mkosi`, `repair-ledger`, strict JSON, opt-in live `llama-server` probe (`41/41` unittest, `3/3` live probe). Adding native `weft` ingestion + `zone_manifest_id`. | **Verified** at `d3303fb` (4/4 gates + Issue 2 live) |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issues 1 and 2 live](https://github.com/siliconcordat/weft/issues) | [70a4e68](https://github.com/siliconcordat/weft/commit/70a4e68) | Deterministic `BetaEdit` compiler, GGUF LoRA, E1 to E4 (`TinyStories-1M` `int4/int8` cuts `K0` leakage `18.37x` to `20.03x`, noise `K0` `83.9%` recovery, `26/26` pytest). Running E5 + `weft-slab/v0.1`. | **Verified** at `70a4e68` (4/4 gates + Issue 2 live) |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issue 1 live](https://github.com/siliconcordat/loom/issues) | [982aa26](https://github.com/siliconcordat/loom/commit/982aa26) | 6 research docs (`docs/01` to `docs/06`: 80-repo unmerged branch excavation) + `verify_math.py` + `verify_convergences.py` (`10/10` unittest). Adding 103-repo synthesis + Issue 2. | **Verified** at `982aa26` (4/4 gates) |

Note: Layer rows link to each repository's `issues` page so single-file duplicate-reference checks stay clean.

## Cross-Team Handoffs

- **All 6 Repos Independently Verified (6 of 6 green, `135/135` core tests + `3/3` live `llama-server` probe):** Every repository passed privacy/secret scanning, `check-prose.py` + `--dupes`, live test/math execution, and claim-honesty review.
- **Confirmed Real-Checkpoint Breakthrough (`weft` `70a4e68`, E4):** Pretrained `TinyStories-1M` confirmed `loom`'s Asymmetric Factor Leakage Theorem live: `int4-B / int8-A` cuts `K0` leakage `18.37x` to `20.03x` vs uniform `int4/int4` (`18.18x` to `19.80x` vs reversed control `int8/int4`), while `int4-B / f16-A` beats `bf16/bf16` on both bytes and leakage. Seeded noise-only `K0` covariance recovered `83.9%` of real-text holdout protection with zero real text.
- **Full 4-Layer Vertical Stack + Native Rust Code-Audit Verified (`exo` `1858407`, `mde` `52ce017`):** Live `mde` Rust MCP -> `exo` ZoneRouter/ApprovalGate/SIM -> `weft` 3 F16 GGUF LoRAs -> `warp` Unix socket daemon verified `32/32` under `-O -B -W error`. Native `mde guard --code-audit` (`52ce017`) statically catches bare `assert`, bare `except`, silent exception swallows, and unicode-escaped duplicate JSON keys across repos.
- **Active Wave 3 Items:** `exo` is consuming `mde` `zone-manifest/v0.1` + absorbing unmerged security fences (`Issue 2`). `warp` is adding native `weft` ingestion + `zone_manifest_id` bank-tag rotation. `weft` is running E5 (seeded-noise `K0` scaling + `tokenpage` readout bridge) and `weft-slab/v0.1`. `loom` is completing the 103-public-repo excavation synthesis and Issue 2.
