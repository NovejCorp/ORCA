# Editable diagrams
The README uses a native SVG with explicit text positioning to avoid clipped labels in GitHub's Mermaid rendering. [SVG source](../assets/orca-architecture.svg).
## Architecture
```mermaid
flowchart TB
    H["Human objectives"] --> O["ORCA coordination"]
    O --> D["Development Pod"]
    O --> R["Research Pod"]
    O --> G["Guardian Pod"]
    D --> A["Runtime adapters"]
    R --> A
    G --> A
    O --> S["Shared services"]
    A --> X["DSH / future NC Brain"]
    X --> T["Enforced tool gateway"]
    T --> I["Tools and infrastructure"]
```
Pods retain identity and approved knowledge across bounded runs. Shared services enforce policy, scoped memory, aggregate budgets and durable coordination.
## Pod cycle
```mermaid
flowchart LR
    P["Plan"] --> X["Execute"]
    X --> T["Test"]
    T --> E["Evaluate"]
    E --> A["Adapt"]
    A --> R["Remember"]
    R --> P
```
## Plugin repair
```mermaid
flowchart TB
    F["Observed failure"] --> C["Candidate plugin or flow"]
    C --> V["Contract and policy checks"]
    V --> T["Isolated tests"]
    T --> E["Independent evaluation"]
    E --> D{"Meets criteria?"}
    D -->|Yes| A["Authorized promotion"]
    D -->|No| Q["Quarantine candidate"]
    A --> M["Monitor and remember"]
    M -->|Regression| B["Roll back composition"]
```
