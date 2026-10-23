# Prior art and comparison
Status: scoped documentation review, consulted 2026-10-23. These are primary-source descriptions, not a code audit or exhaustive novelty search. Upstream projects change; implementation comparisons must later pin exact versions and configuration.

ORCA is a proposed composition of established ideas: agent teams, workflow orchestration, capability security, durable execution, shared memory, and evaluation. No “first”, unique invention, or superior performance claim is justified.

| Project | Documented capabilities | Relationship to proposed ORCA |
| --- | --- | --- |
| DeepSeek Harness | Plugin-oriented agent harness built on Cordis; developer preview | Candidate execution backend. ORCA proposes cross-pod contracts and evaluation above an adapter; no adapter exists and no claim is made that DSH cannot implement similar coordination |
| LangGraph | Stateful graph orchestration, durable execution, persistence, streaming, human-in-the-loop; multi-agent patterns are possible | Substantial overlap in orchestration and recovery. Could supply implementation infrastructure; ORCA would need to justify additional abstractions through measurable benefit |
| CrewAI | Crews coordinate role-based agents and tasks; Flows organize event-driven execution and state | Pods overlap strongly with crews. ORCA emphasizes a portable pod contract, policy/budget boundaries and formation experiments; these are proposed design choices, not proven missing CrewAI features |
| AutoGen | AgentChat agents and teams, selection/handoff patterns; event-driven Core and memory support | Strong overlap in collaborative agents and messaging. Could underpin a runtime adapter; ORCA adds a proposed governance/evaluation contract rather than inventing multi-agent collaboration |
| OpenClaw | Personal assistant system with a gateway, tools, skills, multi-agent routing and channels | Possible integration surface for authorized tasks. ORCA does not claim OpenClaw lacks agents or memory. An integration must preserve its own security controls and prevent channel access from bypassing ORCA approvals |

## Primary references
- [DeepSeek Harness repository and README](https://github.com/deepseek-ai/deepseek-harness)
- [LangGraph overview](https://docs.langchain.com/oss/python/langgraph/overview)
- [LangGraph persistence](https://docs.langchain.com/oss/python/langgraph/persistence)
- [CrewAI crews](https://docs.crewai.com/en/concepts/crews)
- [CrewAI flows](https://docs.crewai.com/en/concepts/flows)
- [AutoGen AgentChat](https://microsoft.github.io/autogen/stable/user-guide/agentchat-user-guide/index.html)
- [OpenClaw repository](https://github.com/openclaw/openclaw)

## Proposed contribution and burden of proof
The research question is whether a common contract can combine logical pod isolation, bounded dynamic formation, cross-runtime substitution, reviewed memory promotion, and objective evaluation at acceptable cost. Each part has prior art. Their combination may still be useful, but usefulness and novelty require separate evidence.

A fair comparison must use upstream-supported functionality and appropriate configuration, including existing team, memory, and approval mechanisms. Compare an ORCA configuration against an equivalently configured native framework, not an artificially weakened single-agent example. Report adapter effort and runtime-specific behavior that the common contract cannot preserve.

Runtime portability is unverified. DSH, LangGraph, CrewAI, AutoGen, and OpenClaw are not drop-in substitutes with identical interfaces. Some may fit as orchestration infrastructure rather than a simple agent runtime; document that distinction in each future adapter.

## Additional work before novelty claims
Review multi-agent scheduling, blackboard systems, actor systems, workflow engines, capability security, hierarchical planning, and organizational learning literature. Conduct a broader project-name search. This document is not patent clearance or a complete literature survey. No private implementation is used as comparison evidence.

## Plugin philosophy
DeepSeek Harness explicitly describes itself as “Everything is a Plugin.” ORCA builds on that philosophy and attributes it; the phrase is not claimed as an ORCA invention. The proposed extension is an evidence-governed Adapt phase that can revise a Pod's versioned composition or replace a workflow step. Plugin systems, runtime substitution and automated workflow optimization all have prior art; no exclusive novelty is asserted.
