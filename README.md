# ORCA

<p align="center"><img src="assets/orca-logo.png" width="180" alt="ORCA icon"></p>

ORCA is a DSH-based distribution in preparation. Its source foundation is [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness), developed by DeepSeek AI. Cursor is the primary development environment for the planned ORCA features.

**Status: pinned source baseline and development handoff. No ORCA feature implementation, packaged release, or performance results yet.**

## Start here

- [Cursor handoff](CURSOR-HANDOFF.md): next steps and current limitations.
- [Feature roadmap](docs/roadmap.md): proposed stages and acceptance evidence.
- [Source and update procedure](UPSTREAM.md): exact upstream revision and subtree maintenance.
- [Imported DSH source](dsh/README.md), [development guide](dsh/docs/development.md), and [safety notice](dsh/SAFETY.md).

Open this repository in Cursor. The upstream workspace root is `dsh/`; source development commands belong there. The imported README describes upstream commands, not a validated ORCA installer. No dependencies or build artifacts are included by this preparation.

The previous orchestration proposal is retired and removed from the active documentation. Existing Git history is preserved. The retained icon is branding, not an architecture specification.

## Licensing and attribution

ORCA is a derivative repository using a pinned Git subtree, not a native GitHub fork. DSH's [MIT license](dsh/LICENSE), copyright, [third-party notices](dsh/THIRD_PARTY_NOTICES.md), and nested licenses are preserved. MIT does not replace third-party terms. Original ORCA material has no newly granted license; see [licensing scope](docs/license-recommendation.md). No upstream endorsement or performance advantage is claimed.

## Contributions

Use public or synthetic examples. Keep private code, user/client data, credentials, runtime state and local diagnostics out of commits. Make small, reviewable changes using upstream extension points. See [AGENTS.md](AGENTS.md) before editing.
