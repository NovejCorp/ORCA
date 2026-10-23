# Upstream source

ORCA is an independent derivative repository, not a native GitHub fork. This import preserves the existing ORCA history and uses a squashed Git subtree so upstream files remain grouped and future changes can be merged deliberately.

- Source: https://github.com/deepseek-ai/deepseek-harness
- Upstream branch: `master`
- Pinned commit: `22ddee3792402c3e70ec5f86a63c3e3e895a2f60`
- Imported directory: `dsh/`
- Upstream/imported tree: `98266a99ba0e9bf6bac8ea39434f48605e40b368`
- ORCA base: `87c3a992e1750b1f588c352f98a7c05d38ef23cc`

All 19,188 tracked upstream entries are imported unchanged, including MIT copyright, nested licenses, third-party notices, lockfile, tests and upstream instructions. Upstream history is fetched locally; the subtree squash records the source commit without attaching the entire upstream commit history to ORCA's ancestry. Upstream automation stays under `dsh/.github/` and is not activated as ORCA root workflows. This is a source baseline, not a dependency installation or binary distribution.

## Updating

Start with a clean feature branch. Add `upstream` with the source URL above if absent, then fetch `master`. Review the new commit, licenses, notices and changes before importing. Pin the reviewed commit explicitly:

```sh
git fetch upstream master
git log --oneline 22ddee3792402c3e70ec5f86a63c3e3e895a2f60..upstream/master
git subtree merge --prefix=dsh REVIEWED_COMMIT_SHA --squash
```

Replace `REVIEWED_COMMIT_SHA` with the reviewed full SHA. Resolve conflicts without discarding ORCA changes, update this pin and tree record, and run relevant checks from `dsh/` before opening a PR. Keep subtree merge metadata; avoid squash-merging away the import/update ancestry. Prefer small ORCA commits after each import. Do not force-push or rewrite published history.

Validate an unchanged import with `git rev-parse HEAD:dsh` and `git rev-parse 'REVIEWED_COMMIT_SHA^{tree}'`. Once ORCA code changes land, those trees should differ; review that delta instead of claiming exact upstream parity.
