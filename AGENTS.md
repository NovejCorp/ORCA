# Contributor instructions

ORCA is a DSH-based distribution under development. Cursor is the primary builder. Read CURSOR-HANDOFF.md and UPSTREAM.md first. Read dsh/AGENTS.md and applicable nested instructions before editing imported source; run upstream commands from dsh/.

Prefer existing DSH profiles, services and plugins. The retired coordination design is not the implementation plan. Keep proposed features distinct from delivered behavior and report only measured results.

Preserve upstream copyright, licenses, notices and subtree metadata. Do not publish private source, credentials, owner/client data, local configuration, runtime state or diagnostic logs. Use synthetic/public fixtures. Keep changes small and reviewable; do not merge or change repository visibility/security without authorization.

This baseline does not authorize installing dependencies, running upstream scripts, local inference/GPU work, modifying live DSH, or changing system permissions. Establish appropriate authorization before those operations in later work. Static import integrity and documentation checks are the validation scope of the baseline.
