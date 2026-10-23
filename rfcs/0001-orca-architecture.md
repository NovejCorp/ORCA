# RFC 0001: ORCA architecture
- Status: Proposed
- Date: 2026-10-23
- Scope: Design only
- Implementation: None
- Decision owner: Repository maintainer
- Supersedes: None

## Problem
Complex tasks may require different capabilities, independent verification, and persistent lessons. A larger collection of agents does not automatically provide bounded authority, reproducible evidence, or better outcomes. We need to test whether an explicit unit of coordination helps enough to justify its overhead.

## Proposal
Define a pod as a versioned objective contract. Give each pod a logical harness while sharing services that can enforce scope. Place ORCA above replaceable execution runtimes through an explicit adapter. Enforce tool capabilities outside model prompts. Use independent acceptance checks and reviewed memory promotion. Add dynamic formation only after fixed-pod baselines exist.

The initial backend should be selected through a capability audit, with DeepSeek Harness as a candidate rather than an assumed integration. Do not fork an upstream runtime merely to begin the experiment.

## Decisions proposed
1. Separate coordination policy from execution mechanics.
2. Treat pod boundaries as logical identities; select physical isolation by threat model.
3. Intersect grants and aggregate budgets across all descendant work.
4. Make irreversible or external effects explicit gated actions.
5. Prefer immutable evidence and provenance over unrestricted transcript sharing.
6. Require reviewed, reversible memory promotion.
7. Evaluate against strong native-framework and single-agent baselines.
8. Keep repository licensing undecided until the owner approves a specific license.

## Alternatives
| Alternative | Benefit | Tradeoff |
| --- | --- | --- |
| One agent with skills | Lowest coordination overhead | May struggle with independent checks or separable work |
| Native framework teams only | Reuse mature execution/orchestration features | Portable governance contract would remain application-specific |
| Separate full runtime per pod | Stronger deployment separation | Resource and operations overhead |
| One shared unrestricted runtime | Simple prototype | Weak isolation and unclear authority/accounting |
| DSH-specific fork | Direct access to runtime internals | Couples the experiment to upstream changes |

Native teams may prove sufficient. If so, ORCA should become a thin contract or evaluation toolkit rather than another orchestration stack.

## Consequences
Benefits are clearer ownership, auditable boundaries, and testable portability. Costs include duplicated abstractions, adapter maintenance, coordination latency, and operational complexity. A common interface may erase useful backend features or support only a narrow subset.

The orchestrator, policy service, tool gateway and storage layer form a trusted computing base. Compromise there can defeat pod-level controls. Agent independence cannot be assumed when models or context are shared.

## Acceptance for a future prototype
Demonstrate simulator conformance, aggregate budgets, denied cross-scope access, approval payload binding, revocation, interruption recovery, and nonduplicated idempotent fixture effects. Then run the roadmap's preregistered comparisons. Architecture acceptance does not equal proven task-performance benefit.

## Open questions
- Which runtime exposes enough hooks to enforce the first adapter contract?
- How should shared services attest pod identity?
- What isolation level is affordable for untrusted skills?
- When is a second pod worth its coordination cost?
- How can independent review avoid correlated errors?
- What retention and revocation semantics are practical across backups?
- Should documentation and future code use separate licenses?
- Is the working name sufficiently distinct from existing projects?

## Review and change process
Discuss concrete concerns through issues, update this RFC with rationale, and record acceptance or rejection explicitly. Material security or permission changes require a new review. Until acceptance, all decisions above remain proposals.

Related: [architecture](../docs/architecture.md), [pod contract](../docs/pod-specification.md), [prior art](../docs/prior-art.md), [roadmap](../docs/roadmap.md).
