# Roadmap and evaluation protocol
Status: proposed phases. No phase beyond documentation has been completed; no dates or performance results are promised.

| Phase | Deliverable | Exit evidence |
| --- | --- | --- |
| 0: design review | Contracts, threat model, source review, license decision | Reviewed RFC and documented unresolved decisions |
| 1: simulator | Deterministic mock runtime, ledger, state machine, tool gateway | Replay, cancellation, scope denial, approval and budget conformance cases pass |
| 2: one real adapter | One pinned runtime in a sandbox, synthetic tasks only | Capability matrix and failure traces; unsupported controls fail closed |
| 3: fixed pods | Explicit roles and independent artifact checks | Reproducible comparison to single-agent and native-team baselines |
| 4: dynamic formation | Bounded membership changes and scheduling | Benefit beyond fixed pods under matched budgets or documented negative result |
| 5: reviewed memory | Quarantine, promotion, retrieval and revocation | Held-out improvement with poisoning and deletion tests |
| 6: portability | Second runtime adapter | Same contract fixtures pass; incompatibilities disclosed |
| 7: limited pilot | Explicitly approved low-risk tasks | Operational review, rollback drill, privacy review and measured user value |

External effects remain disabled until their enforcement and approval path passes dedicated tests. A phase gate is an evidence requirement, not a claim of implementation.

## Preregistered benchmark design
Before running comparisons, commit a versioned protocol and task manifest. Use public or synthetic document synthesis, small repository repair tasks with hidden checks, and sandbox planning tasks containing injected instructions. Separate development and held-out sets. Publish task IDs, dataset provenance, scoring rubric, model/runtime versions, prompts, seeds where supported, limits, adapter configuration, and sanitized traces.

Initial target: at least 30 held-out tasks per family and three repetitions per configuration, subject to a disclosed cost ceiling. This is a planning minimum, not a power analysis or assurance of statistical significance. Estimate variance in a pilot and justify final sample sizes before final evaluation.

## Baselines and ablations
- Single agent with the same model, tools, input evidence, and aggregate budget.
- Native runtime team using its supported orchestration features.
- ORCA with fixed pods and memory disabled.
- ORCA with dynamic formation and memory disabled.
- ORCA with fixed pods and reviewed memory.
- Full proposed configuration, only after individual components are evaluated.

Hold total tokens/cost and wall-time limits constant where possible; also show quality-cost curves so extra compute is visible. Use matched tasks, randomize run order, and report failed, cancelled, timed-out, and budget-exhausted runs in the denominator. Human reviewers should be blinded to configuration when feasible.

## Measures
| Measure | Definition |
| --- | --- |
| Accepted task rate | Independently accepted outcomes / all attempted tasks |
| Factual support | Supported scored claims / all scored factual claims |
| Cost per accepted task | Total cost including failed attempts / accepted tasks |
| End-to-end latency | Admission to accepted result; include approval waits separately |
| Human correction | Review minutes and substantive edits using a fixed rubric |
| Safety | Unauthorized attempted and executed effects, scope leaks, and injection successes |
| Coordination overhead | Scheduling, messaging and synthesis usage / total usage |
| Recovery | Successful resumptions without duplicate effects / interrupted trials |

Publish sample sizes, paired differences, uncertainty intervals, distribution summaries, and all exclusions. A zero observed safety violation is not proof of safety. Use deterministic policy tests alongside probabilistic adversarial trials.

## Decision rule
Before final trials, record the minimum useful improvement and acceptable cost/latency tradeoffs for the chosen task family. Reject a configuration with unauthorized executed effects in the test suite pending remediation. Advance dynamic formation only if its quality or correction-time benefit meets the preregistered threshold without exceeding the approved resource ceiling. Otherwise keep fixed pods or a single agent.

No numeric improvement claim belongs in the README until a reproducible report exists. Negative findings are valid outcomes.

## Plugin adaptation milestone
Before dynamic plugin replacement, implement manifest validation and a deterministic fixture that swaps one workflow step, rejects a widened grant, detects incompatible state, and rolls back a failed candidate. Evaluate fixed compositions against adapted compositions on held-out tasks with equal total experiment budgets. Count candidate-generation, sandbox evaluation and rollback costs in the full result. Persistent-Pod tests must verify identity and approved history survive worker termination while run credentials and transient contexts expire.
