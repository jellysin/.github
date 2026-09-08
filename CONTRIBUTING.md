# Contributing to JellySin

Describe the problem and expected behavior before changing a public interface.
Use a feature branch from main and a pull request with a Conventional Commit title.
Explain what changed, why, which checks ran and any remaining limitation. Squash
merging gives each reviewed change one release-note entry.

JellySin plugins target Jellyfin 12. Keep plugin API compatibility separate from
plugin SemVer. Shared release tooling is versioned independently and consumed at
reviewed immutable SHAs. Release-please collects merged changes into version and
changelog PRs. Ordinary main merges and release PR merges do not create tags or
GitHub releases. Selecting a version for tagging and publication requires a
separate, explicit maintainer action.

Follow [the engineering baseline](https://github.com/jellysin/.github/blob/main/docs/principles.md)
and each repository's local instructions. Requirements from another language or
framework do not apply merely because the words look similar.

Required checks use `strict: false`; no branch-up-to-date gate is required. Never
bypass checks or weaken a failing gate. Use the built-in repository token for
automation, with read-only defaults and write permissions scoped to jobs. Bot PR
checks must be explicitly dispatched when normal events do not trigger them.
GitHub may additionally require a maintainer to approve a bot-created PR's actual
workflow run. Review that run and approve it through GitHub; a successful manual
dispatch does not necessarily satisfy the pending PR check. Keep required checks
enabled and do not create synthetic passing statuses.

## Working on this repository

Changes to profile text, templates, policies and Actions go through the same PR
flow. CI runs the SHA-pinned repository policy checker and actionlint. Locally:

```sh
python ../release-helper/tools.py check-policy
actionlint
```

Run these from this repository with the tooling commit pinned in CI. Check links
and issue-form labels when editing documents. Report validation that was unavailable.
This policy repository has no publication workflow; its release automation only
maintains version and changelog PRs.

Each repository includes the complete EUPL-1.2 text. Contributions must be yours
to license; keep third-party notices and asset/API data rights distinct from code.
