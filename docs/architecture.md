# Architecture baseline

ORCA currently contains an unchanged DeepSeek Harness source tree under `dsh/`. There is no implemented ORCA runtime layer. Use the [upstream architecture](../dsh/docs/architecture.md) as the source foundation and the [roadmap](roadmap.md) for proposed work.

Cursor should extend supported DSH profiles, plugins and services in small changes. The previous architecture proposal is retired; its history remains in Git and is not an implementation requirement.
