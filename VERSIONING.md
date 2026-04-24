# Versioning policy — Cryptohopper official SDKs and CLI

This document is the single source of truth for how the official Cryptohopper developer packages — the Node.js, Python, Go, Ruby, Rust, PHP SDKs, and the `cryptohopper` CLI — are versioned, released, and deprecated. Each repo's `README.md` links here.

## Repositories covered

| Package | Registry | Repo | Tag prefix |
|---|---|---|---|
| `@cryptohopper/sdk` (Node) | npm | [`cryptohopper-node-sdk`](https://github.com/cryptohopper/cryptohopper-node-sdk) | `sdk-v*` |
| `cryptohopper` (Python) | PyPI | [`cryptohopper-python-sdk`](https://github.com/cryptohopper/cryptohopper-python-sdk) | `py-v*` |
| `github.com/cryptohopper/cryptohopper-go-sdk` | Go proxy | [`cryptohopper-go-sdk`](https://github.com/cryptohopper/cryptohopper-go-sdk) | `v*` |
| `cryptohopper` (Ruby) | RubyGems | [`cryptohopper-ruby-sdk`](https://github.com/cryptohopper/cryptohopper-ruby-sdk) | `rb-v*` |
| `cryptohopper` (Rust) | crates.io | [`cryptohopper-rust-sdk`](https://github.com/cryptohopper/cryptohopper-rust-sdk) | `rs-v*` |
| `cryptohopper/sdk` (PHP) | Packagist | [`cryptohopper-php-sdk`](https://github.com/cryptohopper/cryptohopper-php-sdk) | `v*` |
| `@cryptohopper/cli` (CLI) | npm + GitHub Releases | [`cryptohopper-cli`](https://github.com/cryptohopper/cryptohopper-cli) | `cli-v*` |

Go and PHP use bare `v*` tags. Go's module proxy reads the tag directly as the module version, and Packagist reads tags directly as the SemVer version — both reject prefixed tag names. Every other repo uses a prefixed tag so multiple languages or tools can coexist in the same org-wide release stream.

## Semantic versioning

All packages follow [SemVer 2.0.0](https://semver.org/) — `MAJOR.MINOR.PATCH`.

- **MAJOR** bumps when we ship a change that requires user code updates. Removing a public method, renaming an argument, changing a return shape, or raising the minimum supported language runtime all count.
- **MINOR** bumps add functionality in a backward-compatible way — new resource methods, new constructor options with safe defaults, new optional fields on response types.
- **PATCH** bumps ship only bug fixes, doc changes, and internal refactors that do not affect the public surface.

What is **in scope** for the public API (i.e. subject to SemVer):

- Every exported class, function, struct, enum, constant, and module in the package.
- The CLI's command names, flags, subcommands, environment variable names, and config-file layout.
- The wire-format error taxonomy (the `code` enum strings — `UNAUTHORIZED`, `RATE_LIMITED`, etc. — are a contract across SDKs and will not be renamed in a minor release).
- The minimum supported language runtime for each SDK (Node 20+, Python 3.10+, Go 1.22+, Ruby 3.1+, Rust 1.74+). Raising the floor requires a major bump.

What is **not** in scope (may change without notice):

- Anything prefixed with `_`, marked `@internal`, or in an `internal/` package/module.
- The exact text of log lines, debug output, or error messages.
- Transitive dependency versions (we pin minimum versions, not maximums, unless a specific upper bound is needed for correctness).
- The CLI's wire format to the server (`/v1` stability is governed by the server, not the CLI).

## Pre-release naming

Until a package hits `1.0.0`, pre-release identifiers follow each ecosystem's native convention:

| Ecosystem | Format | Example |
|---|---|---|
| npm / Go / Ruby / Rust | `MAJOR.MINOR.PATCH-alpha.N` | `0.3.0-alpha.1` |
| PyPI (PEP 440) | `MAJOR.MINOR.PATCHaN` / `bN` / `rcN` | `0.3.0a1`, `0.3.0rc1` |

- `alpha` = API may shift between releases, no migration notes guaranteed. Everything before `1.0.0` is implicitly in this category.
- `beta` = API frozen for the upcoming release, we are fixing bugs and waiting for confidence.
- `rc` = release candidate. No changes expected unless we find a regression.

Pre-release tags are published to registries but never marked as the default/latest version. Installing the package without specifying a version tag (`npm i @cryptohopper/sdk`, `pip install cryptohopper`, etc.) always pulls the latest **stable** release once one exists.

## 0.x policy

While a package is on `0.x`, we reserve the right to make breaking changes in any minor release — we will still call those out in the CHANGELOG and the GitHub release notes. PATCH releases remain non-breaking. We do not intend to stay on `0.x` long; `1.0.0` ships once the resource surface, error taxonomy, and retry behaviour have been stable for at least one minor cycle with no reported API-shape issues.

## 1.x compatibility

After `1.0.0`:

- No breaking changes without a MAJOR bump.
- At least 6 months of overlap between `N.x` and `N+1.x` where the previous major still gets security patches.
- Deprecations are announced in a MINOR release (`.deprecated()` annotation or equivalent, plus a CHANGELOG entry) **before** removal in the next MAJOR.

## Release cadence

There is no fixed cadence. Releases go out when there is something worth releasing — a fix, a new endpoint, a new resource, or batched dependency updates from Dependabot. In practice that lands somewhere between weekly and monthly. We do not hold fixes for a scheduled release window; if a CVE or a correctness bug needs to ship, it ships same-day as a PATCH.

Every repo runs Dependabot on a weekly schedule (`.github/dependabot.yml`), with minor and patch updates grouped into a single PR per ecosystem so reviewing and merging bumps is cheap.

## Tag and manifest parity

Every SDK's release workflow refuses to publish if the tag and the manifest disagree. Concretely:

- Node / CLI — workflow reads `package.json#version` and compares against `${GITHUB_REF_NAME#sdk-v}` (or `cli-v`).
- Python — workflow reads `pyproject.toml#project.version` and compares against `${GITHUB_REF_NAME#py-v}`.
- Go — workflow reads the bare tag and the module's version constant.
- Ruby — workflow reads `lib/cryptohopper/version.rb` and compares against `${GITHUB_REF_NAME#rb-v}`.
- Rust — workflow reads `Cargo.toml#package.version` and compares against `${GITHUB_REF_NAME#rs-v}`.
- PHP — workflow reads `src/Version.php#VERSION` and compares against `${GITHUB_REF_NAME#v}`.

If the two disagree, the workflow fails before touching the registry. This has already caught one accidental tag on the Node SDK where `package.json` had not been bumped — the publish was aborted and the tag was corrected before it ever hit npm.

## Authentication for publishing

- **npm** (Node SDK, CLI) — classic `NPM_TOKEN` secret + `--provenance` via GitHub's OIDC integration.
- **PyPI** (Python SDK) — [Trusted Publishing via OIDC](https://docs.pypi.org/trusted-publishers/). No API token is stored in the repo.
- **RubyGems** (Ruby SDK) — Trusted Publishing via OIDC using `rubygems/configure-rubygems-credentials@v1`. No API key in the repo.
- **crates.io** (Rust SDK) — classic `CARGO_REGISTRY_TOKEN` secret. crates.io does not offer OIDC publishing as of this writing; we will migrate when it does.
- **Packagist** (PHP SDK) — nothing to authenticate in the release workflow. A repo webhook pings Packagist on every push; Packagist then pulls the tag directly from the public GitHub repo.
- **Go proxy** — nothing to authenticate. The proxy fetches the tag directly from the public GitHub repo.

## Deprecation policy

Deprecated surface stays in the codebase for one full MAJOR cycle before removal. The rules are:

1. Annotate the symbol with the language's native deprecation marker (`@deprecated` JSDoc, Python `warnings.warn(DeprecationWarning)`, Go `// Deprecated:` comment, Ruby `warn`, Rust `#[deprecated]`).
2. Mention it in that release's CHANGELOG under a **Deprecated** heading with the reason and the recommended replacement.
3. In the **next** major release, remove it and mention it in that release's CHANGELOG under **Removed**.

For the CLI specifically, a deprecated command prints a one-line notice to stderr on each invocation until it is removed. We do not silently break muscle memory.

## Security releases

Critical security fixes ship as PATCH releases on every supported major, same day, regardless of where that puts us in the normal release cadence. Advisories go out through GitHub Security Advisories on the affected repo. There is no separate security mailing list yet — GitHub Advisories plus the CHANGELOG is the source of truth.

## Relationship to the public API (`/v1`)

The SDK version and the Cryptohopper public API version are **independent**. SDKs target `https://api.cryptohopper.com/v1` and will continue to target `/v1` across their own major versions. When the server eventually ships `/v2`, SDKs will add a `/v2` client alongside the `/v1` one in a MINOR release — not a MAJOR — until `/v1` is removed from the server.

In other words: upgrading `@cryptohopper/sdk` from `1.x` to `2.x` never forces you to audit API call sites for server-side breaking changes. That contract is held by the server's own versioning.

## Questions or drift?

Open an issue on the affected repo. If the drift is across multiple repos — for example an error code string that differs between Node and Python — open it on [`cryptohopper-resources`](https://github.com/cryptohopper/cryptohopper-resources) and we will coordinate the fix.
