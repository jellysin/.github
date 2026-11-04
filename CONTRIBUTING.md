# Contributing to JellySin

Describe the problem and expected behavior before changing a public interface.
Use a feature branch from main and a pull request with a Conventional Commit title.
Explain what changed, why, which checks ran and any remaining limitation. Squash
merging gives each reviewed change one release-note entry.

JellySin plugins target Jellyfin 12. Keep plugin API compatibility separate from
plugin SemVer. Shared release tooling is versioned independently and consumed at
reviewed immutable SHAs. Release-please owns versions and changelogs.

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

## Releasing this repository

The [release automation workflow](.github/workflows/release-automation.yml) manages
release PRs using [the release-please configuration](release-please-config.json).

The configured workflow path after merging the release PR is:

1. Run [Prepare release](.github/workflows/prepare-release.yml) from `main`. Set
   `tag` to `v` followed by the merged commit's [version.txt](version.txt) value
   and `commit` to that merge commit's full SHA. It creates the tag and an
   unpublished draft with notes from [CHANGELOG.md](CHANGELOG.md), then dispatches
   [Release](.github/workflows/release.yml) on that tag.
2. Follow the [Release run](.github/workflows/release.yml): it calls
   [CI](.github/workflows/ci.yml), then
   [Build and sign release](.github/workflows/build-signed.yml) to package the
   tracked source as `github-<version>.tar.gz`, metadata, checksums and SPDX SBOM,
   attest the artifacts and SBOM, and sign the artifacts with keyless Cosign. Its
   publish job verifies signatures and attestations before publishing the prepared
   draft as a source release. To retry publication, run the same Release workflow
   on the same tag.

Each repository includes the complete EUPL-1.2 text. Contributions must be yours
to license; keep third-party notices and asset/API data rights distinct from code.
