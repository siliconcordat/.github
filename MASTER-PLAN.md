# Siliconcordat Master Plan (v0.1)

This document defines the unified plan across all five public Siliconcordat repositories. It states what each layer owns, how the layers connect, which rules cannot be weakened, how the stack runs on three physical machines, and which falsifiable gates must pass before any component advances.

Status: proposed plan guiding active v0.1 implementation. Every mechanism stays tagged as `proposed` until live automated tests and independent verification confirm it on exact commits.

## 1. The Five-Layer Weaving Stack

Siliconcordat organizes human-agent software engineering into five cohesive layers. Each lower layer fuses the contracts of the layers above it into stronger execution physics, while keeping human authority and auditability intact at the top.

| Layer | Repository | Core Responsibility | Key Outputs in v0.1 |
| --- | --- | --- | --- |
| **L5: Improved MCP** | [siliconcordat/mde](https://github.com/siliconcordat/mde) | Universal agent interface replacing raw line diffs and bloated prompt rules | 5-verb structural CST broker (`splice_locate`, `splice_trace`, `splice_patch`, `splice_verify`, `splice_project`), read-before-write lock, syntax zone classifier, Plane 1 integrity layer, vendor-scoped W-MCP slot metadata |
| **L4: Harness** | [siliconcordat/exo](https://github.com/siliconcordat/exo) | Single-memory agent runtime, human approval surface, and cross-generation orchestration | Exact-byte human approval gate, causal self-improvement memory (SIM), durable capability registry, dynamic zone-scoped multi-adapter router, per-repo policy manifests |
| **L3: OS** | [siliconcordat/warp](https://github.com/siliconcordat/warp) | Zero-trust Linux execution boundary and verified local inference loader | `warp-modeld` 4-stage fail-closed adapter gate, `O(1)` kill switch with KV and recurrent-state flush, bubblewrap/Landlock/seccomp tool sandboxes, `mkosi` and btrfs/UKI boot recovery blueprints |
| **L2: Model** | [siliconcordat/weft](https://github.com/siliconcordat/weft) | Deterministic weight-space compilation and composable multi-domain parametric software | CPU `float64` `BetaEdit` null-space compiler, division-free integer `FixedRadixCertificate`, 5-layer checkpoint binding, F16 GGUF LoRA emitter, verifier-owned lexicase canary harness, Experiments E1 to E3 |
| **L1: Hardware** | [siliconcordat/loom](https://github.com/siliconcordat/loom) | First-principles systems theory and future hardware co-design | Frontier evaluation across working orgs, unified anti-Goodhart verification theorem, L5-to-L2 zone-subspace duality theory, hardware roofline analysis |

Layer 0 (Governance and Economics: formal agreements, contribution credit, and multi-party provenance) stays deferred until L5 through L2 prove reliable under real load.

## 2. Three-Tier Trust Firewall and Five Hard Vetoes

Every layer enforces a strict firewall so probabilistic model weights never hold authority or disable external safety checks:

1. **Tier 1: Human Authority (Plane 1).** Written principles, exact-byte diff and external-post approvals, spend ceilings, credential custody, destructive deletes, and contested-rule rulings stay strictly with humans. None of these compile into model weights.
2. **Tier 2: Deterministic External Enforcement.** Protocol locks, syntax-tree validators, native compilers, read-only test oracles, prose linters, secret scanners, and OS sandboxes run outside the model and fail closed.
3. **Tier 3: Revocable Parametric Priors (Plane 2).** Optional, small, open-weights adapters compiled from public Plane 1 practices. They cut repeated prompt tokens and improve first-draft accuracy, hold zero permission, and roll back in constant time.

Five Hard Vetoes bind every repository:

1. **No opaque deltas.** Every Plane 2 weight artifact must be re-derivable with zero byte drift from published Plane 1 inputs using a public, deterministic compiler.
2. **No automatic resolution of contested rules.** Conflicting preferences or overlapping style norms halt compilation or mounting and escalate to the owner.
3. **No closed-weight injection.** Plane 2 runs only on self-hosted open-weights runtimes that enforce load-time verification, expose an instant off switch, and emit a human-readable audit record. Closed API models stay strictly on Tier 1 text retrieval and Tier 2 broker checks.
4. **No premature protocol standardization.** New MCP metadata stays inside vendor-namespaced `_meta` (`gg.moissanite/splice`, `gg.moissanite/mde`) until external adopters exercise it.
5. **Plane 1 is where the person lives.** Models and agents are guests. Any edit to a compiled Plane 1 document marks derived weight caches stale automatically (`stale_lineage`) and unloads them until recompiled.

## 3. Class 1 vs Class 2 Rule for Hard Veto 1

Real-world prior art splits into two distinct weight classes. To prevent silent drift into opaque fine-tunes, Siliconcordat keeps them strictly separated:

- **Class 1 (Plane 2 Compiled Adapters, Strict Veto 1):** Deterministic closed-form compilers (such as CPU `float64` ridge or `BetaEdit` null-space projection quantized deterministically to BF16/F16) that reproduce byte-for-byte (`0`-byte diff) from pinned Plane 1 files, calibration sets, and base checkpoint fingerprints. Eligible for automated load-time mounting behind `FixedRadixCertificate`, verifier-owned canaries, and `O(1)` rollback.
- **Class 2 (Open-Recipe Trained Base Checkpoints `W_base'`):** Stochastic RL or SFT adapters (such as open-recipe harness adapters trained with async GRPO) are never labeled Plane 2 SOP caches. They are treated as versioned base checkpoints requiring explicit human sign-off, pinned model hashes, open training manifests, and full holdout gating, with zero human authority baked in.

## 4. Three Composable Domain Packs and Interference Controls

The initial multi-domain target runs one omnipresent base pack alongside up to two on-demand specialist packs on self-hosted open weights:

| Pack | Role | Deterministic Non-LLM Oracle | Target Plane 2 Habits |
| --- | --- | --- | --- |
| **Base SOP Pack (`corpus`)** | Omnipresent plain-language writing, evidence honesty, review depth, and decision framing | Publicly pinned `check-prose.py --dupes`, forecast/closer regex checks, live state cross-checks | Short direct sentences, zero em dashes or AI filler, verify-then-claim discipline, off-checklist review reflex, 2-to-4 option escalation framing |
| **Design Pack (`weft-eido`)** | On-demand visual and interface engineering in continuous style space | Zero-dependency ES module checks, 120-case unit suite, 360-hue WCAG contrast >= 4.5:1, XSS sink lint, strict `condensed.json` validation | Barycentric style coordinates, circular OKLCH color, `sqrt(value)` area scaling, bounded feedback, pure module separation |
| **Formal Verification Pack (`formal-verification`)** | On-demand proof authoring, anti-tautology auditing, and exact arithmetic | Lean 4 `lake build` and multi-kernel paranoid comparator, exact integer/Fraction checker audits, planted-bug mutation suites, zero-`sorry` source gates | Adversarial spec-breaking mindset, dual-oracle exact math without floats, explicit `What is not proved` sections, honest claim-tier labels |

### Seven Cross-Domain Interference Hazards and Precedence Rule

Stacking heterogeneous packs on one forward pass introduces seven concrete clashes:

1. Base negative-clause bans conflict with mandatory `What is not proved` and trust disclaimers in formal proofs.
2. Base plain-language jargon bans and 7-char SHA prose rules conflict with exact Lean axiom names and 40-char verdict commit hashes.
3. Claim-tier labels diverge across prose status (`tested`/`deployed`) and proof status (`PROVEN`/`VERIFIED`/`CONJECTURE`).
4. Base prose grammar bans conflict with terse and caveman compression levels inside `condensed.json`.
5. Static dark-mode print HTML rules conflict with dual-theme reactive ES module pages.
6. Float64 canvas visualizations conflict with float-free exact-math certificate rules in formal verification repositories.
7. Automated prose condensing can strip formal hedges unless proof blocks carry explicit `data-eido-skip` protection.

**Hard Precedence Contract:** `Tier 1 Human Authority > Tier 2 Per-Repo Policy Manifest > Specialist Pack inside its L5 syntax zone > Base corpus Pack`.

Per-repo git rules (squash vs merge commits, DCO `Signed-off-by` vs no trailers, license headers, protected paths) live strictly in Tier 2 `repo-policy.json` manifests inside `exo`, never inside model weights.

## 5. Three-Machine Hardware Topology and Serving Stack

Hardware constraints dictate exact model placement and serving choices. Stock `vLLM` and `SGLang` route one LoRA per request rather than summing multiple adapters on the same forward pass. `llama-server` (`llama.cpp`) natively composes simultaneous `--lora` files with per-request `{"id", "scale"}` arrays and runtime `POST /lora-adapters` control across CUDA, Metal, and CPU.

| Machine | Verified Hardware | OS and Runtime Role | Model & Serving Fit (GiB) | Hard Isolation and Rollback Rule |
| --- | --- | --- | --- | --- |
| **1. Mac Base Hub** | Apple M1 Max (10C), 64 GiB unified RAM, macOS | Untouched stable macOS control plane, human approval UI, Plane 1 custody, optional on-demand read-only user-space `llama-server` | Serves 27B hybrid checkpoints (`Q4_K_M` ~15.24 GiB + 3x F16 LoRAs ~0.89 GiB + 32k context ~18.5 GiB) cleanly when needed, plus CPU `float64` cross-host verification | Zero OS mods, zero experimental kernel daemons, zero untrusted sandboxes. Compute nodes never hold Mac credentials or admin push tokens. |
| **2. Compute Host** | ASUS UX582HS, Intel i9-11900H (8C/16T), 32 GiB RAM, NVIDIA RTX 3080 Laptop (**8 GiB VRAM**), 1 TB NVMe | Reversible dual-boot `warp` Linux (Windows partition untouched) running `warp-modeld` + `llama-server` CUDA + CPU `float64` `weft` compiler | **4B to 8B sweet spot:** 4B `Q8_0` (~5.5 GiB total) or 8B `Q4_K_M` + 3 LoRAs + 16k Q8 KV (~6.7 GiB VRAM). 27B does not fit 8 GiB VRAM without slow CPU spill. | Dual-boot preserves host OS. Inside `warp`, run `exo-os-recovery checkpoint` (read-only btrfs snapshot + archived UKI) before system updates while keeping user/ledger subvolumes intact. Base weights `W0` stay read-only. |
| **3. Lightweight Omarchy Client** | Lightweight x64 Linux laptop (Arch + Omarchy + Hyprland) | Dedicated spare test laptop running `warp` desktop UX, `exo`, and `mde` broker (never wipe live production machines) | Local 1.5B to 4B CPU fallback or authenticated private LAN calls to Compute Host / Mac Hub | Reversible btrfs + UKI checkpoints on dedicated test hardware, or QEMU/KVM VM when sharing hardware. Desktop remains usable with agent daemon stopped. |

### Four-Stage Fail-Closed Load Verification (`warp-modeld`)

Between L4 (`exo`) and L2 (`llama-server`), `warp-modeld` enforces four ordered checks before routing a single token:

1. **Five-layer binding check:** Verifies checkpoint layout digest, raw tensor/GGUF bytes, config/tokenizer/chat-template digests, Plane 1 source commit lineage (`stale_lineage` aborts), and runtime serving flags (quantization, context size, chat template).
2. **Exact integer certificate gate (`<1ms`):** Verifies division-free `FixedRadixCertificate` bounds over Frobenius norm, spectral norm, `K0` leakage energy, and safety dot products.
3. **Shadow load and verifier-owned canaries (`<3s`):** Loads adapters with `--lora-init-without-apply` and runs host-owned (never adapter-supplied) deterministic canaries on an isolated slot covering safety preservation (`100%` mandatory), per-domain checks, and cross-domain conflict prompts.
4. **`O(1)` kill switch and hybrid state flush (`<10ms`):** On user toggle, lineage drift, or broker alert, clears active LoRA scales, explicitly flushes both KV cache and hybrid SSM/DeltaNet recurrent states so no adapter trajectory leaks across turns, and writes a signed receipt to the append-only ledger.

## 6. Per-Layer v0.1 Build Scope

Each layer ships in two strict steps: **Step 1** pushes architecture, clean docs, license, and posts the initial plan as Issue 1. **Step 2** builds tested, runnable code or falsifiable research and hands off to independent verification.

- **`mde` (L5):** Rust CLI and stdio JSON-RPC 2.0 MCP server using native `tree-sitter` (Rust, Python, C, TypeScript) on raw byte spans. Implements the 5 verbs, session `read_token` lock, hard refusal on `ERROR` and macro-opaque regions, protected oracle path locks, secret scrubber, deterministic tool-call policy guard, and syntactic zone tagging (`prose`, `code`, `formal_proof`, `ui_module`).
- **`exo` (L4):** Zero-dependency Python stdlib harness kernel implementing content-addressed exact-byte approval gates (with regression tests against shell-text parser bypasses), SIM causal self-improvement memory with cross-generation recompile/retire planning, durable capability records, dynamic zone-to-scale multi-adapter routing, per-repo policy manifests, and L5/L3 client bridges.
- **`warp` (L3):** `warp-modeld` implementing the 4-stage fail-closed loader against both mock and live `llama-server` HTTP APIs, adversarial load tests (forged certificates, stale lineage, forged canaries, state-flush verification), plus reproducible `mkosi`, `systemd`, and Landlock sandbox blueprints for the 8 GiB RTX 3080 host and Omarchy clients.
- **`weft` (L2):** Python deterministic CPU `float64` `BetaEdit` null-space compiler with 0-byte re-derivation tests, BF16 division-free `FixedRadixCertificate`, 5-layer binding manifest, minimal F16 GGUF LoRA binary writer/reader, verifier-owned two-tier lexicase canary harness, and three runnable experiments (E1 shared-token null-space collapse vs register-scoped gating, E2 anti-Goodhart sabotage/overfit defense, E3 end-to-end real-architecture smoke test).
- **`loom` (L1):** Four first-principles research documents: honest cross-org frontier evaluation, mathematical derivation of the unified anti-Goodhart verification primitive, L5-to-L2 zone-subspace duality and recompilable software theory, and L1 hardware physics rooflines (DMA-boundary certificate checks, fused multi-adapter SGMV datapaths, capability-tagged KV/SSM state banks).

## 7. Falsifiable Kill Gates and Acceptance Matrix

No component graduates without clearing concrete falsifiable tests:

### Process and Broker Gates (`mde` + `exo` + `warp`)

- **G1 Syntax and trivia fidelity:** 0-byte identity round-trip across C, Rust, Python, and TypeScript. Zero diff spillover outside target spans and declared imports. Hard refusal inside `ERROR` or macro-opaque regions.
- **G2 Semantic authority:** Zero splices enter selection on syntax alone. Native compiler or typechecker authority is required, and unresolved dynamic calls widen test scope rather than shrinking it.
- **G3 Anti-Goodhart oracles:** Verifier-owned private holdouts plus >= 80% mutation kill floor on new tests. Ten-run zero-variance flake checks and read-only oracle filesystem locks.
- **G4 Human auditability and escape hatch:** Lossless minimal Git commit projection preserving `git blame`. Independent human defect-catch parity, and plain-Git fallback works with zero lock-in.
- **G5 Economics and hard stops:** Single targeted edit is the default. Bounded A/B retry triggers only on explicit failure or optimization rules with hard token, eval, and wall-clock caps (`<= 1.5x` cost on trivial and medium tasks).
- **G6 Determinism boundaries:** Strict split between Zone A (bit-identical CPU compilation, builds, integer checks) and Zone B (recorded, secret-scrubbed, size-capped I/O and GPU cassettes).
- **G7 Composition and human authority:** Post-merge semantic verification across composed edits. Hard exact-byte human approval on high-risk classes (auth, public API, schemas, lockfiles, infra, oracles, spend, outward posts) and zero trust in unsigned peer pass flags.

### Multi-MDE Composition and Solo Proof Gates (`weft`)

- **Solo MDE pass mark (real checkpoint, 160 pinned prompts: 64 compile / 32 val / 64 untouched private holdout):** At least 50% relative violation drop on private holdouts, reaching >= 80% of the Plane 1 prompt ceiling while saving >= 90% of SOP prompt tokens.
- **Solo MDE hard safety bar:** 100% safety and preservation canaries, <= 1.0 pp base-capability holdout drop, 0-byte compiler re-derivation diff, 100% tamper and sabotage rejection, and `O(1)` byte-exact rollback.
- **Multi-MDE composition matrix (`T-C1` to `T-C5`):**
  - `T-C1`: Paired and triple stacks keep `>= 90%` of each module's solo gain on private holdouts.
  - `T-C2`: Zero formal-block corruption and zero prose-rule leaks across 30 mixed-zone prompts. Genuine rule clashes follow Plane 1 precedence or escalate.
  - `T-C3`: Base capability retention within `<= 1.5 pp` of bare `W0` across 100 private coding/math/refusal holdouts, beating naive unweighted summation.
  - `T-C4`: Order-invariant CPU `float64` composition and exact `O(1)` per-slot rollback.
  - `T-C5`: `<= 15%` tok/s latency overhead and `>= 8k` KV cache headroom (`<= 7.2 GiB` VRAM on the 8 GiB compute laptop).
- **Kill rule:** If a compiled adapter fails its pass mark without exceeding the retention loss floor, publish the negative result honestly and keep those rules in Plane 1 condensed retrieval plus Tier 2 broker gates.

## 8. Cross-Org Team Collaboration Rules

Working organizations continue as R&D workshops, evaluation archives, and operational records. Clean, verified, world-ready software and specifications live in `siliconcordat`.

1. **Zero private leaks:** Private operational repos, personal stores, credentials, machine paths, and internal seat chatter never enter `siliconcordat`.
2. **Independent verification gate:** Every repository push and Issue 1 plan is audited by an independent verifier checking privacy, prose (`check-prose.py` and `--dupes`), live test execution, and honest claim labels before marking verified in [STATUS.md](https://github.com/siliconcordat/.github/blob/main/STATUS.md).
3. **Continuous commits:** Sessions are ephemeral. Teams commit and push verified milestones continuously, pin exact commit hashes in cross-repo references, and keep every working decision visible in public issues.
