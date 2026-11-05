<!-- markdownlint-disable MD013 MD033 MD041 -->
<!-- A centred header needs inline HTML, a banner image, indented headings and
     badge lines past 80 columns, so those rules are off for this file.
     The prose below still wraps at 80. -->
<div align="center">

  <img src="jellysin-readme-banner.svg" alt="JellySin — independent plugins for Jellyfin 12" height="120" />

  <!-- README-STANDARD badge block: one group, fixed order (docs/README-STANDARD.md) -->
  <!-- 1 release/version -->
  [![Release](https://img.shields.io/static/v1?label=release&message=v0.1.1&style=for-the-badge&color=3b82f6&labelColor=111a35)](https://github.com/jellysin/.github/releases) <!-- x-release-please-version -->
  <!-- 2 CI/build -->
  [![CI](https://github.com/jellysin/.github/actions/workflows/ci.yml/badge.svg?branch=main&event=push)](https://github.com/jellysin/.github/actions/workflows/ci.yml)
  <!-- 3 security/scorecard -->
  [![CodeQL](https://github.com/jellysin/.github/actions/workflows/codeql.yml/badge.svg?branch=main&event=push)](https://github.com/jellysin/.github/actions/workflows/codeql.yml)
  [![OpenSSF Scorecard](https://img.shields.io/badge/OpenSSF-Scorecard-06b6d4?style=for-the-badge&labelColor=111a35)](https://scorecard.dev/viewer/?uri=github.com/jellysin/.github)
  [![CodeRabbit](https://img.shields.io/badge/Reviews-CodeRabbit-8b5cf6?style=for-the-badge&logo=coderabbit&logoColor=white&labelColor=111a35)](https://coderabbit.ai)
  <!-- 4 standards -->
  [![HISS-21](https://img.shields.io/badge/Standards-HISS--21-06b6d4?style=for-the-badge&logo=nasa&labelColor=111a35)](https://github.com/jellysin/.github/blob/main/AGENTS.md)
  [![Power of 10](https://img.shields.io/badge/NASA_JPL-Power_of_10-3b82f6?style=for-the-badge&logo=nasa&labelColor=111a35)](https://github.com/jellysin/.github/blob/main/docs/principles.md)
  [![Conventional Commits](https://img.shields.io/badge/Commits-Conventional-8b5cf6?style=for-the-badge&logo=conventionalcommits&logoColor=white&labelColor=111a35)](https://github.com/jellysin/.github/blob/main/CONTRIBUTING.md)
  <!-- 5 licence -->
  [![License](https://img.shields.io/badge/License-EUPL--1.2-3b82f6?style=for-the-badge&labelColor=111a35)](https://github.com/jellysin/.github/blob/main/LICENSE)

  **Independent plugins for Jellyfin 12, with shared release tooling and one Plugin Repository**

  *Jellyfin plus sin, a little temptation for your media server; said JELLY-sin*

</div>

JellySin provides independent plugins for Jellyfin 12, backed by shared release
tooling and a single Plugin Repository. Each plugin owns its code and release
cycle, while sharing common engineering principles, reproducible release
packaging, and automated governance.

## Why JellySin

A Jellyfin server gains a feature without a fork: one plugin, one
repository, one install source. Development happens in public, and the shared
release automation builds reproducible packages, verifies each release and
updates the Plugin Repository.

## Get started

Plugin Repository URL for approved plugin releases:

```text
https://raw.githubusercontent.com/jellysin/repo/main/manifest.json
```

Plugins appear after their first approved release.

## At a glance

JellySin coordinates plugin development, packaging, and distribution across
dedicated repositories:

- [Last.fm](https://github.com/jellysin/plugin-lastfm): music listening,
  favourites, metadata and discovery integration, currently in development.
- [Release helper](https://github.com/jellysin/release-helper): reproducible
  packages, verified releases and Plugin Repository updates.
- [Plugin Repository](https://github.com/jellysin/repo): one installation source
  for JellySin plugins.

## Guides and reference

- [Engineering principles](https://github.com/jellysin/.github/blob/main/docs/principles.md):
  baseline rules for small, bounded implementations, error handling, performance,
  and accessibility.
- [Release helper documentation](https://github.com/jellysin/release-helper):
  shared release automation and manifest generation workflows.

## Contribute

Development happens in public. Read
[CONTRIBUTING.md](https://github.com/jellysin/.github/blob/main/CONTRIBUTING.md)
before proposing changes. Contributions follow topic branches, pull requests
with Conventional Commit titles, and squash merges.

## Roadmap and releases

Plugins appear after their first approved release:

- **Last.fm integration**: in development
  ([plugin-lastfm](https://github.com/jellysin/plugin-lastfm)).
- **Release pipeline**: automated via release-please and
  [Release helper](https://github.com/jellysin/release-helper). See the
  [Releases](https://github.com/jellysin/.github/releases) page and track
  version history in
  [CHANGELOG.md](https://github.com/jellysin/.github/blob/main/CHANGELOG.md).

## Upstream and licence

JellySin builds independent plugins targeting
[Jellyfin 12](https://github.com/jellyfin/jellyfin).

New source code is licensed under the
[European Union Public Licence 1.2](https://github.com/jellysin/.github/blob/main/LICENSE)
(EUPL-1.2).

## Standards and governance

JellySin repositories adhere to declared engineering standards:

- **HISS-21**: High-Integrity Software Standards covering control flow, error
  handling, bounded loops, and deterministic execution
  ([AGENTS.md](https://github.com/jellysin/.github/blob/main/AGENTS.md)).
- **NASA/JPL Power of 10**: structural rules for safety-critical, bounded code
  ([principles](https://github.com/jellysin/.github/blob/main/docs/principles.md)).
- **Conventional Commits**: specification for commit messages paired with
  release-please automation
  ([CONTRIBUTING.md](https://github.com/jellysin/.github/blob/main/CONTRIBUTING.md)).
