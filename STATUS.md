# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest verified commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Open Issues | Latest Verified Commit | Verified Scope and Tests | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) | [ae572f1](https://github.com/siliconcordat/.github/commit/ae572f1) | Org profile, `MASTER-PLAN.md`, `CONTRIBUTING.md`, live tracker | **Verified** (4/4 gates, Issue 1 live) |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [Issues 1 and 2 live](https://github.com/siliconcordat/mde/issues) | [52ce017](https://github.com/siliconcordat/mde/commit/52ce017) | Rust CST broker, `mde guard` + `--code-audit` (Python CST + unicode JSON dupes), `zone-manifest/v0.1`, `mde integrity` (`36/36`), `mde seam-verify` (`26/26` cargo tests) | **Verified** at `52ce017` (4/4 gates + Issues 1 and 2) |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Issues 1 and 2 live](https://github.com/siliconcordat/exo/issues) | [9d52aa1](https://github.com/siliconcordat/exo/commit/9d52aa1) | Zero-dep stdlib kernel, `zone-manifest/v0.1` parity, pre-JSON secret redaction, monotonic human-stop fence, allowlisted tool env, live 4-layer stack (`40/40` unittest, `-O` clean) | **Verified** at `9d52aa1` (4/4 gates + Issues 1 and 2) |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [Issues 1 and 2 live](https://github.com/siliconcordat/warp/issues) | [99b1428](https://github.com/siliconcordat/warp/commit/99b1428) | `warp-modeld` 4-stage gate, native `weft` ingestion, `zone-manifest/v0.1` bank-tag rotation, zero-sudo `mkosi`, `repair-ledger`, strict JSON (`47/47` unittest, `-O` clean, `3/3` live `llama-server` probe) | **Verified** at `99b1428` (4/4 gates + Issues 1 and 2) |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Issues 1 and 2 live](https://github.com/siliconcordat/weft/issues) | [55ae677](https://github.com/siliconcordat/weft/commit/55ae677) | Deterministic `BetaEdit` compiler, GGUF LoRA, `weft-slab/v0.1` (`69.8%` smaller at 4B `W_up`), E1 to E5 on `TinyStories-1M` (`37/37` pytest cached + no-cache) | **Verified** at `55ae677` (4/4 gates + Issues 1 and 2) |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Issues 1 and 2 live](https://github.com/siliconcordat/loom/issues) | [caa8ade](https://github.com/siliconcordat/loom/commit/caa8ade) | 6 research docs (`docs/01` to `docs/06`: 103 public repos, 544 open PRs, 1,501 branches, 4 cross-org convergences) + `verify_math.py` + `verify_convergences.py` (`10/10` unittest, `-O` clean) | **Verified** at `caa8ade` (4/4 gates + Issues 1 and 2) |

Note: Layer rows link to each repository's `issues` page so single-file duplicate-reference checks stay clean.

## Verified Cross-Layer Milestones

- **All 6 Repos Independently Verified (6 of 6 green, `160/160` tests + `3/3` live `llama-server` probe):** Every repository passed privacy/secret scanning, `check-prose.py` + `--dupes`, live automated tests under `-O -B -W error`, and claim-honesty review. Native Rust `mde guard --code-audit` passed with zero findings across `exo/src`, `warp/src`, `weft/src`, and `loom/scripts`.
- **Unbroken 4-Layer Vertical Stack + Byte-Exact Zone Parity (`mde` + `exo` + `warp` + `weft`):** Live `exo` (`9d52aa1`) executed compiled Rust `mde` (`52ce017`), compiled `weft` (`55ae677`) GGUF LoRAs with 0-byte re-derivation, verified through `warp` (`99b1428`) over Unix sockets (`12.8 us` to `16.0 us` Stage 2, `1.72 ms` `O(1)` kill switch, `W_old -> W_new` recompile/retire loop), and matched `zone-manifest/v0.1` SHA-256 byte-for-byte across Rust L5, Python L4, and Python L3.
- **Pretrained Real-Checkpoint Validation (`weft` E4 + E5 on `TinyStories-1M`):** Asymmetric `int4-B / int8-A` cuts `K0` leakage `18.37x` to `20.03x` vs uniform `int4/int4` (`18.18x` to `19.80x` vs reversed control), while `int4/f16` beats `bf16/bf16` on both bytes and leakage. Seeded-noise `K0` plateaus honestly at `52%` to `55%` recovery (`eff. rank 2.42` vs `4.04`), and adding 16 public `y=0` anchors pushes recovery to `111.8%` while repairing a simulated wire-dialect readout drop (`0.125 -> 1.000`, `13/16` unseen retention).
- **103-Public-Repo Excavation Complete (`loom` `caa8ade`):** Audited `103` verified-public repos (`544` open PRs, `1,501` branches), folding unmerged hardening directly into `mde`, `exo`, `warp`, and `weft` and publishing the executive frontier map in `loom` Issue 2.
- **Next Hardware Step:** Ready for live 1.5B to 8B open-weights multi-adapter experiments on the 8 GiB VRAM compute laptop (`warp` dual-boot) and read-only user-space `llama-server` checks on the 64 GiB unified-memory Mac hub.
