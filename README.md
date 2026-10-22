# JellySin community and engineering defaults

<!-- praetor:readme-governance:start -->
[![HISS Adopted][praetor-hiss-badge]][praetor-hiss-agents]

Praetor manages this repository's declared governance policy. This managed
block records adoption state; it is not a verification certificate.

**Verification**: `make verify-all` runs the repository's configured
verification cascade.

**HISS Audit**: `praetorctl audit` enforces policy, generated-surface
integrity, and the debt ratchet.

**Context Sync**: `praetorctl compile-context --verify` verifies every
generated agent context against `AGENTS.md`.

**Debt Baseline**: `.standards-baseline.json` anchors the debt ratchet at
0 recorded infractions; audit forbids growth.

[praetor-hiss-badge]: https://img.shields.io/badge/Standards-HISS%20Adopted-blue
[praetor-hiss-agents]: https://github.com/jellysin/.github/blob/HEAD/AGENTS.md
<!-- praetor:readme-governance:end -->

JellySin: Jellyfin plus sin, a little temptation for your media server; said JELLY-sin.

This repository holds the organization profile, contribution and security guidance,
issue forms, and the shared engineering baseline for JellySin's independent
Jellyfin 12 plugins, build tooling and Plugin Repository.

GitHub applies supported community health files to repositories that do not supply
their own. Each repository still includes its own EUPL-1.2 license and applicable
agent instructions; GitHub does not inherit licenses or `AGENTS.md` automatically.

Read [the engineering principles](docs/principles.md) and CONTRIBUTING.md before
changing shared rules. Language-specific requirements belong in the repository
that uses that language. Release tooling lives in
[release-helper](https://github.com/jellysin/release-helper). Approved installable
builds will be listed in the [Plugin Repository](https://github.com/jellysin/repo).
