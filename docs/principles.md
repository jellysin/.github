# Engineering principles

These rules apply to JellySin projects where the relevant behavior exists. The
Plugin Repository does not need playback tests; a Python release tool does not need a web
framework. Local instructions define stricter language-specific gates.

## Small, bounded implementations

Keep control flow simple. Prefer focused modules over speculative abstractions.
Backend functions are limited to 120 lines and 60 statements; Python additionally
limits cyclomatic complexity to 10. Frontend functions stay within 100 lines.
Prefer interfaces with at most five operations; document a concrete exception.

Bound queues, caches, batches, response sizes, retries and pagination. Every
external operation has a timeout or cancellation path. Scope mutable state to its
owner, separate users, and detach events before disposing their dependencies.
Inject clocks where behavior depends on time. Network deadlines belong at the
transport boundary and must use monotonic elapsed time.

Validate external data before use. Check outcomes, contain errors at event
boundaries, and use structured logs. Never log credentials, signatures, session
keys, authenticated URLs or unredacted response bodies. Release tooling fails
closed with bounded, redacted diagnostics.

## Evidence and performance

Test observable production behavior: failures, cancellation, isolation, missing
metadata, restart recovery and concurrency. Avoid implementation-mirroring tests.
Meaningful code coverage targets are at least 70% overall and 85% for security
boundaries; the release tooling applies an 85% combined branch-aware gate.

Run compiler/analyzer/linter and formatting gates with no unresolved findings.
Suppressions are narrow and explain a real constraint. Never weaken a gate to
make a change pass. Record checks that were not available and remaining risks.

Optimize measured hot paths. Use batching, bounded caches and reuse when evidence
shows their benefit. Add pooling only after profiling; fewer supported host
versions simplify code but do not prove faster playback. Benchmarks record their
workload, environment, baseline and result; do not invent speedup claims.

## Accessible interfaces

Give controls accessible names, preserve keyboard operation and focus, and provide
text errors. Keep account data private to the authenticated user. Where the
project controls a web page, target LCP under 2.5 seconds, INP under 200 ms and CLS
under 0.1 with an explicit measurement setup. Do not claim these metrics for
Jellyfin clients the plugin does not control.

## Reproducible delivery

Pin SDKs, packages and tools to exact stable versions; commit applicable locks.
Pin Actions to full commit SHAs and hash-check downloaded executables. New
dependencies need a concrete purpose and an alternative considered in review.
Host-provided assemblies never enter plugin archives.

Build plugin releases from their exact tag. Produce deterministic archives,
checksums and an honest software inventory, then verify signed provenance.
Published bytes and compatible Plugin Repository history are immutable. Shared tooling
stays a build-time dependency and is versioned for multiple independent plugins.

Use PRs, Conventional Commit titles and squash merges. Release-please owns versions
and changelogs. Required checks use `strict: false`. Automation uses read-only
defaults, job-scoped writes and explicit timeouts; untrusted PR code never runs
with a write token. Explicitly dispatch bot CI where normal events do not recurse.

Verify live GitHub settings after changing them. Documentation of a desired
setting is not evidence it is active. Capture consequential architecture and
tradeoffs in ADRs close to the implementation.

## Basis

This baseline adapts the applicable engineering requirements from
[GoLusoris](https://github.com/golusoris/golusoris/blob/main/docs/principles.md),
[SvelteSentio](https://github.com/golusoris/sveltesentio/blob/main/docs/principles.md)
and [20 Watts Was Enough](https://github.com/lusoris/20-watts-was-enough).
JellySin's own source is EUPL-1.2. These references do not transfer their framework
requirements, code licenses, or third-party data rights to this organization.
