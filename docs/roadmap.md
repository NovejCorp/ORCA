# Feature roadmap

All stages below are proposed work for Cursor. The current deliverable is an unchanged upstream source import plus documentation; no ORCA-specific feature is implemented.

| Stage | Proposed deliverable | Acceptance evidence |
| --- | --- | --- |
| 1 | Local-first workspace/profile setup using existing DSH services | Public fixture opens in an isolated profile; settings remain scoped; setup and supported platforms documented |
| 2 | Reliable source read/edit/test workflow | Approved disposable-workspace tests verify edits, test results, cancellation and cleanup; persistent terminal failures are reproduced or explicitly unsupported |
| 3 | Provider configuration and model selection | Config validation, secret redaction, explicit local/remote selection and actionable errors; mock-provider tests before separately authorized real inference |
| 4 | Task progress, artifacts and recovery | Existing DSH session mechanisms expose status and recoverable failures; interrupted-task fixtures avoid duplicate effects |
| 5 | Opt-in reusable skills and local project context | Explicit storage scope, retention/deletion controls, public fixtures and tests against unintended data disclosure |
| 6 | ORCA packaging and release | Product name/assets/update endpoints reviewed; third-party terms and notices verified; reproducible build, smoke checks and rollback instructions |

For each stage, inventory existing upstream support before adding code, define one small user-visible outcome, implement through supported extension points, and run focused upstream tests. Keep release and network effects behind explicit user authorization. Do not implement a second orchestration layer or reinstate the retired design.

Benchmarking is separate work. Publish no model ranking, superiority, cost or performance claim until reproducible measurements identify versions, settings, tasks, failures and limits.
