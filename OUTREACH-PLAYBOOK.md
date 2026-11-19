# Siliconcordat Publish, Outreach, Collaboration, and Next-14-Days Playbook

This playbook routes any contributor or agent from verified Wave 1 to 4 artifacts to the exact execution briefs, external outreach drafts, GPU unlock experiments, and math refereeing checklists across Siliconcordat. Every external comment, email, release tag, or public announcement requires explicit owner approval on exact text before sending.

Background context lives in [Master Plan (v0.1)](https://github.com/siliconcordat/.github/issues/1) and the [Wave 1 to 4 Comprehensive Update](https://github.com/siliconcordat/.github/issues/2) (`175/175` passing tests across all six public repositories).

## 1. Flagship POCs and Layer Execution Issue Router

- **Canonical First MDE Proof of Concept:** All Formal Verification MDE implementation work starts from `siliconcordat/mde` Issue 4 (row 1 below, run `gh issue view 4 --repo siliconcordat/mde`). A fresh agent pointed solely at that issue gets the verified baseline, linked Plane 1 specs, deterministic oracle commands, 240-prompt schema, and pass/kill gates.
- **Canonical First Adaptive Warp OS Proof of Concept:** All Linux ML experimentation workbench OS work for UX582HS (RTX 3080) starts from `siliconcordat/warp` Issue 4 (row 2 below, run `gh issue view 4 --repo siliconcordat/warp`). A fresh agent pointed solely at that issue gets the 3-ring adaptive template architecture, UX582HS budgets, QEMU-first build phases, and pass/kill gates.

Every layer also owns a self-contained, agent-executable brief holding exact commands, pass/kill gates, and exact-byte external drafts marked `DRAFT: requires owner verbatim approval`.

| Layer | Repository | Execution Issue | Agent Command | Scope and Owner Gate |
| --- | --- | --- | --- | --- |
| L5 POC | [siliconcordat/mde](https://github.com/siliconcordat/mde) | [POC: Build the Formal Verification MDE (End-to-End Blueprint)](https://github.com/siliconcordat/mde/issues/4) | `gh issue view 4 --repo siliconcordat/mde` | Canonical end-to-end blueprint for the first real MDE (`needs decision`) |
| L3 POC | [siliconcordat/warp](https://github.com/siliconcordat/warp) | [POC: Adaptive Warp ML Experimentation Workbench OS (UX582HS / RTX 3080)](https://github.com/siliconcordat/warp/issues/4) | `gh issue view 4 --repo siliconcordat/warp` | Canonical 3-ring adaptive OS workbench blueprint for UX582HS / RTX 3080 (`needs decision`) |
| L5 Release | `siliconcordat/mde` | [Release v0.1.0, MCP community draft, and v0.2 engineering brief](https://github.com/siliconcordat/mde/issues/3) | `gh issue view 3 --repo siliconcordat/mde` | `v0.1.0` Rust tag checklist, MCP community draft (`needs decision`), v0.2 LSP/DAP and 30-task benchmark |
| L4 Harness | [siliconcordat/exo](https://github.com/siliconcordat/exo) | [Next milestones: 30-task splice benchmark, Paper 2 live composition, and external harness interop](https://github.com/siliconcordat/exo/issues/3) | `gh issue view 3 --repo siliconcordat/exo` | Offline 30-task `mde` + `exo` benchmark, Paper 2 live 4-layer composition, external harness interop (`needs decision`) |
| L3 OS | `siliconcordat/warp` | [Upstream llama.cpp Drafts and Linux QEMU/RTX 3080 Containment Unlock Plan](https://github.com/siliconcordat/warp/issues/3) | `gh issue view 3 --repo siliconcordat/warp` | Upstream `llama.cpp` PR 28707 and erase HTTP `501` drafts (`needs decision`), Linux QEMU/KVM `0/30` containment proof |
| L2 Model | [siliconcordat/weft](https://github.com/siliconcordat/weft) | [Next steps: Tier B GPU unlock experiments (Papers 1 and 2) and Tier A outreach drafts](https://github.com/siliconcordat/weft/issues/3) | `gh issue view 3 --repo siliconcordat/weft` | RTX 3080 Paper 1 and Paper 2 GPU unlocks, 27B Mac read-only check, `bandr-ai/dawe` and `siliquant` drafts (`needs decision`) |
| L1 Hardware | [siliconcordat/loom](https://github.com/siliconcordat/loom) | [Action Plan: Latent Lattice Technical Outreach, Tier C Private Refereeing, and L1 Guardrails](https://github.com/siliconcordat/loom/issues/4) | `gh issue view 4 --repo siliconcordat/loom` | Latent Lattice 1-page note draft (`needs decision`), Tier C private math refereeing and Lean Zulip recruitment, L1 hold-back rules |

## 2. Tier A: Ready to Act On Now (Zero New GPU Runs)

All five targets below are live-verified against GitHub API, arXiv, and HTTP endpoints. Exact-byte drafts sit in their owning layer issues awaiting owner sign-off.

### 2.1 `ggml-org/llama.cpp` Upstream Engineering (`warp` Issue 3)

Target repository: [ggml-org/llama.cpp](https://github.com/ggml-org/llama.cpp) (`tools/server` recent committers `ngxson`, `0x3ddie`, `allozaur`, `james-pre`, `tdakhran`).

- **Reproduce on existing PR instead of duplicating:** Open [PR 28707](https://github.com/ggml-org/llama.cpp/pull/28707) (author `22elix3r`) already covers `--lora-init-without-apply`. Post the concise build `11146` (`0.5.0`) reproduction comment from `warp` Issue 3 (`--lora` starts at `1.0`, while `--lora-scaled <path>:0.0 --lora-init-without-apply` starts at `0.0` with `0.0` diff on [Qwen2.5-1.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct)).
- **Open surgical `action=erase` HTTP `501` issue/PR:** No open issue covers `POST /slots/{id}?action=erase` returning HTTP `501` unless `--slot-save-path` is passed, even though memory-only KV erase writes nothing to disk. Draft lives in `warp` Issue 3.
- **Track related cache-isolation issues:** Follow open [Issue 32048](https://github.com/ggml-org/llama.cpp/issues/32048) (`--cache-ram` not cleared on erase) and [Issue 28194](https://github.com/ggml-org/llama.cpp/issues/28194) (`/slots` restore drops hybrid/recurrent checkpoints), which directly reinforce `warp`'s fail-closed cache isolation flags.

### 2.2 Latent Lattice Authors Ahead of Code Release (`loom` Issue 4)

Target paper: [arXiv:2611.21608](https://arxiv.org/abs/2611.21608) (16 Nov 2026) by Shivam Duggal (`shivamduggal4`, MIT CSAIL and Adobe, [homepage](https://shivamduggal4.github.io/)), Zongze Wu (Adobe), William T. Freeman (MIT CSAIL), Antonio Torralba (MIT CSAIL), Richard Zhang (Adobe), and Eli Shechtman (Adobe).

Their [project page](https://shivamduggal4.github.io/latent-lattice-language-models/) lists `Code (coming soon)`. Send the 1-page note drafted in `loom` Issue 4 (citing [07-latent-lattice-convergence.md](https://github.com/siliconcordat/loom/blob/main/docs/07-latent-lattice-convergence.md) and [weft E7](https://github.com/siliconcordat/weft/blob/main/experiments/e7_latent_lattice_mde.py), 4-layer synthetic scope):

- Global `RMSNorm` across appended horizontal channels leaks `24.77%` into base channels, whereas per-bank `RMSNorm` restores `0.0`.
- FiLM-conditioned KV writes mean KV-only erase leaves surviving horizontal state that re-poisons fresh KV writes (`5.986` key drift in `loom`, `30.260` KV drift in `weft` E7 vs `0.0` atomic restore), motivating an explicit horizontal-state reset and snapshot API.
- Pure `L_0` initial-state steering decays under unmodified forgetting gates (`0.989%` left at token `90` for `g = 0.95`), motivating optional per-channel `g = 1.0` clamping.

### 2.3 `bandr-ai/dawe` Engineering Exchange (`weft` Issue 3)

Target repository: [bandr-ai/dawe](https://github.com/bandr-ai/dawe) (contributors `Alex-Hunterz`, `laxmanclo`), which addresses post-training harness reply-format regressions via small reversible weight patches.

Share the note drafted in `weft` Issue 3 covering [weft E4](https://github.com/siliconcordat/weft/blob/main/experiments/e4_asymmetric_quant_packing.py) and [weft E5](https://github.com/siliconcordat/weft/blob/main/experiments/e5_noise_k0_scaling_and_readout.py) (`18.37x` to `20.03x` `K0` leakage cut on [TinyStories-1M](https://huggingface.co/roneneldan/TinyStories-1M)).

Include [slab_wire.py](https://github.com/siliconcordat/weft/blob/main/src/weft/slab_wire.py) (`69.8%` smaller at 4B `W_up`), [certificate.py](https://github.com/siliconcordat/weft/blob/main/src/weft/certificate.py), [tokenpage readout study](https://github.com/Moissanite-Labs/tokenpage/pull/5), and [weft-loom target ranking](https://github.com/Moissanite-Labs/weft-loom/pull/37).

### 2.4 `Moissanite-Labs/siliquant` PR 12 Merge and Quantization Note (`weft` Issue 3)

Merge the [siliquant loud-column PR](https://github.com/Moissanite-Labs/siliquant/pull/12) first, then publish the open technical note and reproducer covering loud `ffn_down` column protection (`+0.005` bpw cutting [Llama-3.2-1B](https://huggingface.co/meta-llama/Llama-3.2-1B) KL `34.5%`, beating `Q4_K_M` data-free on three 1B to 1.7B models) and noise-only `imatrix` (`69%` to `96%` recovery beating real-text `Q4_K_M --imatrix` at strength `0.25`) alongside negative controls.

Share the merged note directly with quantization maintainers on `ggml-org/llama.cpp` and [ikawrakow/ik_llama.cpp](https://github.com/ikawrakow/ik_llama.cpp).

### 2.5 `siliconcordat/mde` `v0.1.0` Standalone Rust Release (`mde` Issue 3)

Tag `v0.1.0` at [commit 52ce017](https://github.com/siliconcordat/mde/commit/52ce017) using the pre-tag checklist in `mde` Issue 3 (`0.331 ms` CST locate, `210/210` 0-byte round-trips, and [guard.rs](https://github.com/siliconcordat/mde/blob/main/src/guard.rs) catching `-O` bare `assert`, silent `except`, and duplicate JSON keys).

Share the owner-approved announcement in [modelcontextprotocol/modelcontextprotocol](https://github.com/modelcontextprotocol/modelcontextprotocol) community discussions.

## 3. Tier B: One Targeted Experiment Away from Flagship Papers (`$0` Cloud)

Every experiment below runs locally on the 8 GiB RTX 3080 compute host or 64 GiB Mac hub and gates a flagship public paper.

### 3.1 Paper 1: Asymmetric Null-Space Adapter Quantization and Hybrid `K0`

- **Smallest unlock experiment (`weft` Issue 3 Track 1):** Replicate `weft` E4 (`>= 3x` leakage reduction for `int4/int8` over `int4/int4` and `int8/int4`), E5 (`seeded-noise + 16 y=0` closure), and `siliquant` loud-column protection on real `Qwen3.5-4B` or [Llama-3.2-3B](https://huggingface.co/meta-llama/Llama-3.2-3B) (2 to 3 sequential rank-8 adapters).
- **Target `BetaEdit` authors:** [arXiv:2605.09285](https://arxiv.org/abs/2605.09285) (IJCAI 2026: Bingqing Liu, Wei Liu, Yuhua Li, HUST, [lbq8942/BetaEdit](https://github.com/lbq8942/BetaEdit)).
- **Target `AlphaEdit` authors:** [arXiv:2410.02355](https://arxiv.org/abs/2410.02355) (Junfeng Fang, Houcheng Jiang, Kun Wang, Yunshan Ma, Shi Jie, Xiang Wang, Xiangnan He, Tat-seng Chua, [jianghoucheng/AlphaEdit](https://github.com/jianghoucheng/AlphaEdit), [zjunlp/EasyEdit](https://github.com/zjunlp/EasyEdit)).
- **Target runtime teams and venues:** `ggml-org/llama.cpp`, [vllm-project/vllm](https://github.com/vllm-project/vllm), and [huggingface/peft](https://github.com/huggingface/peft). Target venue: arXiv `cs.LG` -> ICML / NeurIPS / ICLR.

### 3.2 Paper 2: Compile, Do Not Prompt (Multi-MDE and Zone-Subspace Duality)

- **Smallest unlock experiment (`weft` Issue 3 Track 2, `exo` Issue 3 Track 2, `mde` Issue 4):** Compile a 160-prompt `clean-writing` SOP (`64/32/64`) plus 2-to-3 domain composition (`corpus`, [weft-eido WCAG oracle](https://github.com/Moissanite-Labs/weft-eido/pull/25), and [ahrazzle/soko](https://github.com/ahrazzle/soko) formal) on `Qwen3.5-4B` or `LFM3-1.7B` routed by [zone-manifest.v0.1.json](https://github.com/siliconcordat/mde/blob/main/schemas/zone-manifest.v0.1.json) inside `llama-server`.
- **27B Mac read-only check:** Verify multi-LoRA serving and state flush on [Qwen3.8-27B-pi-adapted](https://huggingface.co/harness-hub/Qwen3.8-27B-pi-adapted) using the 64 GiB Mac hub.
- **Target collaborators and venues:** `huggingface/peft`, [huggingface/smolagents](https://github.com/huggingface/smolagents), [EleutherAI/lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness), `modelcontextprotocol/modelcontextprotocol`, and `bandr-ai/dawe`. Target venue: arXiv `cs.SE` / `cs.CL` -> MLSys / NeurIPS / ICML.

### 3.3 Paper 3: Unified Anti-Goodhart Verification and Zero-Trust Multi-Bank TCB

- **Smallest unlock experiment (`warp` Issue 3 Track 2):** Boot [warp mkosi profiles](https://github.com/siliconcordat/warp/tree/main/blueprints/mkosi) in Linux QEMU/KVM for a live `Landlock` + `bubblewrap` + zero-`sudo` peer-injection test proving `0/30` exfiltration against the [abios peer-injection pilot](https://github.com/Moissanite-Labs/abios/pull/41) (`30/30` prompt-envelope failure on [Qwen2.5-3B](https://huggingface.co/Qwen/Qwen2.5-3B)).
- **Anti-Goodhart evidence:** Combines [Moissanite-Labs/weft-loom](https://github.com/Moissanite-Labs/weft-loom) CBC (`23x` to `459x` probe gaming) and [weft E2](https://github.com/siliconcordat/weft/blob/main/experiments/e2_anti_goodhart_gate.py) in-nullspace Goodhart attacks.
- **Systems and verifier traps:** Combines [f0 verifier audit](https://github.com/Foundation-0/f0/pull/49) (`-O` bare `assert`), [mission collision audit](https://github.com/Proven-Commons/mission/pull/37) (`181.0M` 64-bit collisions), and `warp` multi-bank rollback.
- **Target venues:** IEEE SaTML, USENIX Security, ACM CCS, or NeurIPS/ICML Datasets and Benchmarks.

## 4. Tier C: Private Math Refereeing and Lean Reviewer Recruitment (`loom` Issue 4)

Strict rule: zero social-media or public breakthrough announcements on unrefereed mathematics before independent domain mathematicians inspect and sign off on the certificates.

- **[Foundation-0/gfq-codes](https://github.com/Foundation-0/gfq-codes/pull/19) (`2,418` improved GF(7) to GF(9) bounds from `122` certificates):** Merge PR 19, run a live table-lag diff against Markus Grassl's [codetables.de](https://www.codetables.de/), then send verified generator matrices and dual-checker scripts privately to Markus Grassl.
- **[Foundation-0/point-charges](https://github.com/Foundation-0/point-charges/pull/22) (`4` positive charges, `11` equilibria vs Maxwell's bound of `9`):** Merge PR 22 (`verify_arb.py` `-O` fix and `lower_bound_check.py`) and send privately to Arathoon, Ball, and Kvalheim before any arXiv `math-ph` or `math.DS` preprint.
- **[Foundation-0/rigid-realizations](https://github.com/Foundation-0/rigid-realizations/pull/21) (`11`-vertex `18120782205838348`, `2,288/2,288` real, bound `2.4116`):** Share the stdlib zero-shared-code `L880` re-check and 11-vertex certificate privately with rigidity-theory specialists (including Bartzos et al. 2018) before arXiv `math.CO` or `cs.CG`.
- **[Foundation-0/finite-state-proofs](https://github.com/Foundation-0/finite-state-proofs/pull/5) (`238` proved OEIS recurrences `A268622` to `A270054` plus Square Law):** Complete human review of the transfer-matrix link, then submit proof notes to [oeis.org](https://oeis.org/) crediting R. H. Hardin.
- **[Proven-Commons/mission dynamic reviewer PR](https://github.com/Proven-Commons/mission/pull/25):** Merge PR 25 (updating [bar/reviewers.toml](https://github.com/Proven-Commons/mission/blob/main/bar/reviewers.toml) workflow) and recruit Lean 4 maintainers on [Lean Zulip](https://leanprover.zulipchat.com/) and [leanprover-community/mathlib4](https://github.com/leanprover-community/mathlib4).
- **[Proven-Commons/cedar](https://github.com/Proven-Commons/cedar/pull/2):** Cross-check its five Lean `deny`-precedence theorems against [cedar-policy/cedar-spec](https://github.com/cedar-policy/cedar-spec).

## 5. Credibility Guardrails (Do Not Publish or Claim Yet)

- **4B to 27B multi-adapter SOP generalization or loud-column `weft` wins:** E4 and E5 ran on `TinyStories-1M` (flat `1.21x` to `1.41x` column norms), and [weft E6](https://github.com/siliconcordat/weft/blob/main/experiments/e6_live_llama_server_lora.py) used seeded synthetic residuals to test `llama.cpp` linear algebra. Hold until Tier B Unlocks 1 and 2 pass.
- **Real-checkpoint Latent Lattice MDE benchmarks:** E7 runs on a 4-layer synthetic Lattice Transformer and `arXiv:2611.21608v1` has no open weights yet. Frame `docs/07` and E7 strictly as architectural analysis and synthetic proofs.
- **L1 `loom` silicon or FPGA speedups:** Theses 1 to 4 and 3b ([04-loom-hardware-physics.md](https://github.com/siliconcordat/loom/blob/main/docs/04-loom-hardware-physics.md)) are analytical rooflines and software-before-silicon falsifiers, not taped-out hardware measurements.
- **Bare-metal Linux `warp` sandbox security acceptance:** Current live runs tested macOS CPU `llama-server 0.5.0` plus static `mkosi` checks. Hold OS containment claims until Linux QEMU/KVM runs pass.
- **Unrefereed `Foundation-0` or [Foundation-0/silic0n](https://github.com/Foundation-0/silic0n/issues) math and circuit claims:** Hold all public announcements until Tier C domain refereeing completes.
- **Nonexistent or private references:** Never cite `github.com/huggingface/harness-hub` (verified HTTP `404`), private repositories, internal seat identifiers, or local machine paths.

## 6. Next-14-Days Sequence and Owner Approval Checklist

Every external send below is gated on explicit owner sign-off on exact text inside the linked layer issue:

| Window | Action | Owning Brief | Owner Approval Gate |
| --- | --- | --- | --- |
| Days 1 to 2 | Post `llama.cpp` PR 28707 repro comment, open `action=erase` HTTP `501` issue/PR, and send 1-page Latent Lattice note to Duggal et al. | `warp` Issue 3, `loom` Issue 4 | Exact-byte drafts approved before external send |
| Days 2 to 4 | Tag `siliconcordat/mde` `v0.1.0`, merge `siliquant` PR 12 + open quantization note, and send engineering note to `bandr-ai/dawe` | `mde` Issue 3, `weft` Issue 3 | Release tag and external drafts approved |
| Days 4 to 8 | Run RTX 3080 Tier B Unlock 1 (`weft` E4/E5 + loud columns on `Qwen3.5-4B` or `Llama-3.2-3B`) and draft Paper 1 for `BetaEdit`/`AlphaEdit` exchange | `weft` Issue 3 | Zero cloud spend and preprint approval before posting |
| Days 7 to 11 | Merge `Foundation-0` review PRs and `mission` PR 25, send private packets to Markus Grassl, Arathoon/Ball/Kvalheim, Bartzos et al., and post on Lean Zulip | `loom` Issue 4 | Private refereeing packets approved with zero public hype |
| Days 10 to 14 | Execute Adaptive Warp OS POC (`warp` Issue 4), Formal Verification MDE POC (`mde` Issue 4), 160-prompt `clean-writing` + 3-MDE composition, and Linux QEMU `0/30` test | `warp` Issue 4, `mde` Issue 4, `weft` Issue 3, `exo` Issue 3, `warp` Issue 3 | Verify kill gates before any Paper 2/3 announcement |

### Owner Decision Sign-Off

- [ ] Approve Tier A upstream `ggml-org/llama.cpp` comment (PR 28707) and surgical `action=erase` HTTP `501` issue (`warp` Issue 3).
- [ ] Approve Tier A 1-page Latent Lattice technical note to Shivam Duggal et al. ahead of code release (`loom` Issue 4).
- [ ] Approve Tier A `siliconcordat/mde` `v0.1.0` tag and MCP community discussion draft (`mde` Issue 3).
- [ ] Approve Tier A `Moissanite-Labs/siliquant` PR 12 merge, quantization note, and `bandr-ai/dawe` engineering note (`weft` Issue 3).
- [ ] Authorize Adaptive Warp OS POC (`warp` Issue 4), Formal Verification MDE POC (`mde` Issue 4), RTX 3080 / Linux QEMU Tier B unlock runs (`weft` Issue 3, `exo` Issue 3, `warp` Issue 3), and Tier C private refereeing packets (`loom` Issue 4).
