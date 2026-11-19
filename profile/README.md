# Siliconcordat

Siliconcordat builds an open, layered software stack for collaboration between people and AI agents. Every layer uses plain, checkable contracts so people keep final authority while agents work faster and with fewer silent failures.

Each layer fuses the layers above it into one working substrate, a pattern we call spliceware. High-level protocols stay legible to people and work across any agent harness. Lower layers enforce safety rules mechanically and compile repeatable habits into revocable open-weights adapters where hardware allows.

## The Five-Layer Stack

| Layer | Repository | Purpose | Current Stage |
| --- | --- | --- | --- |
| L5: Improved MCP | [siliconcordat/mde](https://github.com/siliconcordat/mde) | Universal agent interface with structural syntax-tree edits, read-before-write locks, lineage pinning, and vendor-scoped weight-slot metadata. | Active v0.1 build |
| L4: Harness | [siliconcordat/exo](https://github.com/siliconcordat/exo) | Single-memory agent runtime with exact-byte human approval gates, causal self-improvement memory, and dynamic multi-adapter routing. | Active v0.1 build |
| L3: OS | [siliconcordat/warp](https://github.com/siliconcordat/warp) | Zero-trust AI-first Linux layer with sandboxed tool execution, fail-closed model load verification, and atomic snapshot boot recovery. | Active v0.1 build |
| L2: Model | [siliconcordat/weft](https://github.com/siliconcordat/weft) | Deterministic weight-space compiler, fixed-radix safety certificates, and composable multi-domain adapters on open weights. | Active v0.1 build |
| L1: Hardware | [siliconcordat/loom](https://github.com/siliconcordat/loom) | First-principles theory and frontier research on deterministic arithmetic, native multi-adapter datapaths, and hardware-checked loading. | Research and theory only |

Layer 0 (Governance and Economics) is reserved for later work after L5 through L2 prove reliable on real tasks.

## How the Layers Fuse

- **L5 (`mde`)** replaces fragile line-based text diffs and bloated system prompts with five structural verbs, hash-pinned context, and syntax zone tags (`prose`, `code`, `formal_proof`, `ui_module`).
- **L4 (`exo`)** binds every risky outward act or code change to an exact byte hash for human approval, records causal lessons across model upgrades, and routes L5 zone tags into active L2 adapter scales.
- **L3 (`warp`)** enforces OS isolation (bubblewrap, Landlock, seccomp) and sits in front of local open-weights serving (`warp-modeld`) so unverified weights never reach a GPU.
- **L2 (`weft`)** compiles public, human-written practices into small, revocable adapters verified by exact integer certificates and verifier-owned behavioral canaries.
- **L1 (`loom`)** turns measured bottlenecks from L2 through L5 into falsifiable hardware and systems research.

## Three-Tier Trust Firewall

Every boundary in the stack preserves strict separation between human consent, mechanical checks, and learned weights:

1. **Tier 1: Human Authority (Plane 1).** Written principles, exact-byte approvals, spend caps, credential custody, and conflict resolution stay with people. None of these ever compile into model weights.
2. **Tier 2: Deterministic External Enforcement.** Protocol locks, syntax-tree validators, compilers, prose linters, secret scanners, and OS sandboxes fail closed outside the model.
3. **Tier 3: Revocable Parametric Priors (Plane 2).** Optional adapters compiled from public sources for self-hosted open weights. They save prompt tokens and improve first drafts, carry zero authority, and roll back in constant time.

## Five Hard Vetoes

These rules hold across every repository unless changed by explicit human decision:

1. **No opaque deltas.** Every Plane 2 weight artifact must be re-derivable with zero byte drift from published Plane 1 inputs using a public, deterministic compiler.
2. **No automatic resolution of contested rules.** Competing preferences or conflicting style rules escalate to the owner rather than merging silently.
3. **No closed-weight injection.** Plane 2 adapters run only on runtimes that verify at load time, expose an instant off switch, and produce a human-readable audit record.
4. **No premature protocol standardization.** New MCP fields stay inside vendor-namespaced metadata until external users test them in practice.
5. **Plane 1 is where the person lives.** Models, tools, and agents are guests. Any change to a Plane 1 source marks derived weight caches stale automatically.

## Start Reading

- Full architecture and rollout roadmap: [MASTER-PLAN.md](https://github.com/siliconcordat/.github/blob/main/MASTER-PLAN.md)
- Team rules and review checklist: [CONTRIBUTING.md](https://github.com/siliconcordat/.github/blob/main/CONTRIBUTING.md)
- Live repository and verification tracker: [STATUS.md](https://github.com/siliconcordat/.github/blob/main/STATUS.md)
