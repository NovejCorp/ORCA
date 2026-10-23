# Plugins and adaptation
Status: proposed contract; no plugin loader or automated replacement engine exists.

## Composition model
A persistent Pod is a versioned composition of role slots, skills, model routing, workflow nodes, evaluators and memory access components. Runtime adapters are plugins at the system boundary. A flow is a typed directed graph: each node declares accepted inputs, produced artifacts, dependencies, timeout, error policy and capability request.

Build on [DeepSeek Harness: Everything is a Plugin](https://github.com/deepseek-ai/deepseek-harness). This is an architectural influence, not a claim that DSH already supports the ORCA contracts below.

| Replacement point | Example | Required checks |
| --- | --- | --- |
| Role implementation | Replace a research worker | Input/output and evidence compatibility |
| Skill | Replace a citation procedure | Versioned instructions and relevant evaluation |
| Model router | Choose another approved model | Privacy, supported tools, budget and quality |
| Workflow node or edge | Add a deterministic source checker | Graph validity, bounded loops and failure propagation |
| Evaluator | Add a fixture-based validator | Independent oracle; no self-awarded success |
| Memory retriever | Replace ranking method | Scope filtering, provenance and poisoning tests |
| Runtime adapter | DSH to a future backend | Full adapter conformance and state compatibility |

## Manifest
A plugin manifest must name plugin_id, version, content_digest, kind, interface_version, input_schema, output_schema, requested_capabilities, dependencies, state_schema, migration_support, resource_limits, evaluation_suite and rollback_version. A composition lock records exact versions and hashes. Resolve dependencies deterministically; reject cycles, untrusted provenance, unresolved versions or incompatible interfaces.

Plugins request capabilities; they do not issue grants. Installation and code execution are separate from selection. Do not download or execute arbitrary packages because an agent proposes a name. Use a reviewed allowlist and isolated loading; verify artifact integrity. Tool and network credentials remain outside plugin payloads.

## Adapt protocol
1. **Observe:** retain failed acceptance checks, traces, cost and context.
2. **Diagnose:** identify the smallest suspected component and record competing explanations.
3. **Propose:** produce a versioned manifest/graph diff, hypothesis and success criteria.
4. **Validate:** check types, dependency graph, permission subset, migration and budget.
5. **Experiment:** run the candidate in an isolated sandbox against fixed and held-out fixtures.
6. **Evaluate:** use independent checks; include candidate-generation and experiment costs.
7. **Promote:** an authorized reviewer approves the immutable candidate hash and deployment scope.
8. **Remember:** persist the evidence, accepted composition and rollback reference.
9. **Monitor:** roll back on regression; quarantine the failed revision.

The Pod cycle remains **Plan → Execute → Test → Evaluate → Adapt → Remember**. Adapt may conclude “retain the existing workflow” or pin a corrected fixed flow. Continuous mutation is not the objective.

## State and deployment
By default, apply replacements only to new runs. Active runs remain pinned to their original lock. A live migration requires a quiescent checkpoint, validated state conversion, fresh grant, fenced old worker and a reversible migration plan. Incompatible state starts a new run with explicitly authorized artifacts; never silently reinterpret old checkpoints.

Promotion uses compare-and-swap against the reviewed baseline revision. If the baseline changed, rebase and re-evaluate. Retain a known-good composition and route new work back to it on failure. Reverting code does not undo external effects: reconcile them separately.

## Immutable authority boundary
Workload plugins cannot replace the root policy authority, approval verifier, secret broker, tenant boundary or accounting authority through the Adapt loop. Changes to that trusted base require separate maintainer review. Evaluators are extensible, but a candidate cannot modify its own acceptance oracle during an experiment.

## Example repair
A Research Pod produces claims without citations. Adapt proposes adding a source-validation node before review. Fixtures test missing sources, fabricated references and adversarial page instructions. A reviewer checks quality and overhead, then promotes the new graph for future runs. If correction time or failure rate regresses, restore the previous graph and retain the failed experiment as evidence.
