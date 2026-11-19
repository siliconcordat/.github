# Siliconcordat Live Build Status

This tracker records active repositories, planning issues, latest pushed commits, and independent verification status across the five-layer stack.

Last updated: 2026-11-19 UTC.

## Layer Tracker

| Layer | Repository | Role | Step 1 Plan & Issue | Step 2 Build Status | Independent Verifier |
| --- | --- | --- | --- | --- | --- |
| Hub | [siliconcordat/.github](https://github.com/siliconcordat/.github) | Org profile, master plan, collaboration guide, live tracker | Publishing Step 1 and Issue 1 | Maintaining live status | Pending Step 1 check |
| L5 | [siliconcordat/mde](https://github.com/siliconcordat/mde) | Improved MCP, 5-verb CST broker, zone tags, Plane 1 integrity | In progress | In progress | Pending |
| L4 | [siliconcordat/exo](https://github.com/siliconcordat/exo) | Harness, exact-byte gate, SIM memory, multi-MDE router | In progress | In progress | Pending |
| L3 | [siliconcordat/warp](https://github.com/siliconcordat/warp) | OS sandboxing, `warp-modeld` load verifier, btrfs recovery | In progress | In progress | Pending |
| L2 | [siliconcordat/weft](https://github.com/siliconcordat/weft) | Deterministic compiler, fixed-radix certificates, multi-MDE experiments | In progress | In progress | Pending |
| L1 | [siliconcordat/loom](https://github.com/siliconcordat/loom) | Hardware theory and frontier first-principles research | In progress | In progress | Pending |

## Milestone Sequence

1. **Step 1 (Active):** Create all six clean public repositories, push foundation architecture and plan documents, and post the initial plan as Issue 1 in each repository.
2. **Step 2 (Active):** Build minimal, tested v0.1 implementations and runnable experiments for `mde`, `exo`, `warp`, `weft`, and publication-grade research notes for `loom`.
3. **Independent Verification:** Every repository clears four hard verifier gates (privacy and secret scan, prose and duplicate-reference check, live test execution, and claim-tier honesty audit) before being marked verified here.
4. **Hardware Bring-Up (Next):** Run solo and multi-domain open-weights experiments on the 8 GiB VRAM compute laptop (`warp` dual-boot) and read-only user-space `llama-server` validation on the 64 GiB unified-memory Mac hub.
