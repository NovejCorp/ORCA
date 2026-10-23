# Cursor handoff

Cursor is the primary builder of ORCA. Modify the imported DSH foundation incrementally; DSH does not need to author the changes.

## Prepared

- Exact upstream source in `dsh/`, with licenses and notices unchanged; pin and updates in [UPSTREAM.md](UPSTREAM.md).
- Retired orchestration proposal removed from active docs and diagrams; history and unrelated artwork retained.
- Proposed implementation stages in [roadmap](docs/roadmap.md). No ORCA features or release implemented.

## First Cursor session

1. Read root `AGENTS.md`, `UPSTREAM.md`, then `dsh/AGENTS.md`, `dsh/SAFETY.md` and `dsh/docs/development.md`; read scoped instructions before changing a package.
2. Review the draft baseline PR. Continue on a new feature branch from this baseline, preserving pending changes. Work from `dsh/` for upstream commands (manifest: Node >=24.9.0, pnpm 11.28.5).
3. Select one roadmap stage, inspect existing DSH capabilities, and write acceptance criteria before implementing. Prefer profiles/plugins and focused fixes over a replacement execution architecture.
4. Establish an authorized dependency/build/test environment. Run focused upstream checks for the touched surface; report failures and untested assumptions. Do not treat the static source import as a passing build.

## Existing Windows evidence and limits

A separate installed DSH investigation reproduced a persistent terminal startup failure. A built-in one-shot sandboxed PowerShell tool completed one harmless read-only command. That narrow success does not validate arbitrary builds, source edits, persistent terminals, or this imported source revision. The one-shot path emitted initialization warnings and had partial confinement; the exact terminal defect remains unresolved.

Workspace-write provisioning remains unapproved. Do not change operating-system permissions, disable sandboxing, or alter the live DSH installation/profile as part of this baseline. A future approved disposable-workspace test must separately demonstrate read/edit/test and cleanup. Cursor feature development need not wait for DSH to become its own coding agent.

No private profiles, machine details, logs, provider routes or model settings are published here. No local inference or GPU benchmark was run. Model choices and performance claims require separate evidence.

## First deliverable

A small PR for a local-first workspace/profile experience using existing DSH services, with public fixtures, explicit setup requirements, focused tests and a list of remaining limitations. Review release branding, updater destinations and third-party redistribution terms before producing an ORCA binary.
