# Cryptohopper official SDKs and CLI

Cryptohopper ships official clients for seven languages and a standalone CLI. Every one hits the same Public API v1 at `https://api.cryptohopper.com/v1`, uses the same OAuth2 bearer-token auth, and speaks the shared error taxonomy documented below.

## At a glance

| Language | Package | Registry | Repo | Current version |
|---|---|---|---|---|
| Node.js / TypeScript | `@cryptohopper/sdk` | [npm](https://www.npmjs.com/package/@cryptohopper/sdk) | [`cryptohopper-node-sdk`](https://github.com/cryptohopper/cryptohopper-node-sdk) | 0.4.0-alpha.1 |
| Python | `cryptohopper` | [PyPI](https://pypi.org/project/cryptohopper/) | [`cryptohopper-python-sdk`](https://github.com/cryptohopper/cryptohopper-python-sdk) | 0.4.0a1 |
| Go | `github.com/cryptohopper/cryptohopper-go-sdk` | Go proxy | [`cryptohopper-go-sdk`](https://github.com/cryptohopper/cryptohopper-go-sdk) | v0.4.0-alpha.1 |
| Ruby | `cryptohopper` | [RubyGems](https://rubygems.org/gems/cryptohopper) | [`cryptohopper-ruby-sdk`](https://github.com/cryptohopper/cryptohopper-ruby-sdk) | 0.1.0.pre.alpha.1 |
| Rust | `cryptohopper` | [crates.io](https://crates.io/crates/cryptohopper) | [`cryptohopper-rust-sdk`](https://github.com/cryptohopper/cryptohopper-rust-sdk) | 0.1.0-alpha.1 |
| PHP | `cryptohopper/sdk` | [Packagist](https://packagist.org/packages/cryptohopper/sdk) | [`cryptohopper-php-sdk`](https://github.com/cryptohopper/cryptohopper-php-sdk) | 0.1.0-alpha.1 |
| Dart / Flutter | `cryptohopper` | [pub.dev](https://pub.dev/packages/cryptohopper) | [`cryptohopper-dart-sdk`](https://github.com/cryptohopper/cryptohopper-dart-sdk) | 0.1.0-alpha.1 |
| CLI | `@cryptohopper/cli` + binaries | [npm](https://www.npmjs.com/package/@cryptohopper/cli) + [Releases](https://github.com/cryptohopper/cryptohopper-cli/releases) | [`cryptohopper-cli`](https://github.com/cryptohopper/cryptohopper-cli) | 0.5.1-alpha.1 |

All SDKs currently cover the **same 18 public API domains**: `ai`, `app`, `arbitrage`, `backtest`, `chart`, `exchange`, `hoppers`, `market`, `marketmaker`, `platform`, `signals`, `social`, `strategy`, `subscription`, `template`, `tournaments`, `user`, `webhooks`. The CLI surfaces a pragmatic subset of these as subcommands; anything not yet wired into the CLI is still reachable through the Node SDK which the CLI consumes internally.

## Installing

```bash
# Node.js
npm install @cryptohopper/sdk

# Python
pip install cryptohopper

# Go
go get github.com/cryptohopper/cryptohopper-go-sdk

# Ruby
gem install cryptohopper --pre

# Rust
cargo add cryptohopper

# PHP
composer require cryptohopper/sdk:^0.1.0-alpha.1

# CLI (via npm)
npm install -g @cryptohopper/cli

# CLI (via release binaries — pick your platform)
# https://github.com/cryptohopper/cryptohopper-cli/releases/latest
```

## Authenticating

Every SDK constructor takes a bearer token. Create one via the developer dashboard on cryptohopper.com.

```ts
// Node
import { CryptohopperClient } from "@cryptohopper/sdk";
const ch = new CryptohopperClient({ apiKey: process.env.CRYPTOHOPPER_TOKEN! });
```

```python
# Python
from cryptohopper import CryptohopperClient
ch = CryptohopperClient(api_key=os.environ["CRYPTOHOPPER_TOKEN"])
```

```go
// Go
ch := cryptohopper.NewClient(os.Getenv("CRYPTOHOPPER_TOKEN"))
```

```ruby
# Ruby
ch = Cryptohopper::Client.new(api_key: ENV.fetch("CRYPTOHOPPER_TOKEN"))
```

```rust
// Rust
let ch = cryptohopper::Client::new(std::env::var("CRYPTOHOPPER_TOKEN")?)?;
```

```php
// PHP
$ch = new Cryptohopper\Sdk\Client(apiKey: getenv('CRYPTOHOPPER_TOKEN'));
```

An optional `appKey` / `app_key` / `AppKey` parameter carries your OAuth `client_id` as the `x-api-app-key` header for per-app rate-limit attribution.

## Error taxonomy

Every SDK raises a single typed error type whose `code` / `error_code` / `Code()` comes from this shared enum:

| Code | HTTP | Meaning |
|---|---|---|
| `UNAUTHORIZED` | 401 | Token missing, invalid, or revoked |
| `DEVICE_UNAUTHORIZED` | 402 | Device-based auth (internal / out of scope for v1 public SDK) |
| `FORBIDDEN` | 403 | Missing permission scope or IP-whitelist mismatch |
| `NOT_FOUND` | 404 | Resource or endpoint not found |
| `CONFLICT` | 409 | Resource state conflict |
| `VALIDATION_ERROR` | 400 / 422 | Invalid parameters |
| `RATE_LIMITED` | 429 | Rate limit exceeded — error includes `retryAfterMs` parsed from `Retry-After` |
| `SERVICE_UNAVAILABLE` | 503 | Server temporarily unavailable |
| `SERVER_ERROR` | 5xx | Upstream error |
| `NETWORK_ERROR` | — | Transport failure (DNS, connection reset, etc.) |
| `TIMEOUT` | — | Per-request timeout elapsed |
| `UNKNOWN` | — | Anything else |

Errors additionally expose the server's numeric `code`, the `ip_address` the server saw, and any `Retry-After` value.

## Rate limits

On HTTP 429 the client sleeps for `Retry-After` seconds (or an exponential-backoff fallback) and retries up to `maxRetries` times. The default is 3; pass `maxRetries: 0` to disable. The final failure surfaces as the shared error type with `code = RATE_LIMITED` and `retryAfterMs` populated, so you can log it and move on.

## Versioning and releases

All packages follow [SemVer 2.0.0](https://semver.org/). While on `0.x` we reserve the right to make breaking changes in any minor release — we call them out in each repo's `CHANGELOG.md` and in the GitHub release notes. See [VERSIONING.md](../VERSIONING.md) for the complete versioning, release, deprecation, and security-fix-ship policy.

Tag conventions per repo:

- `sdk-v*` — Node SDK
- `py-v*` — Python SDK
- `rb-v*` — Ruby SDK
- `rs-v*` — Rust SDK
- `cli-v*` — CLI
- `v*` — Go SDK (module proxy requires bare SemVer tags) and PHP SDK (Packagist requires bare SemVer tags)

Every release workflow refuses to publish if the tag and the in-repo version manifest disagree.

## Compatibility

- Minimum runtimes: Node 20+, Python 3.10+, Go 1.22+, Ruby 3.1+, Rust 1.74+, PHP 8.1+.
- CI runs against multiple versions per language (e.g. PHP 8.1/8.2/8.3/8.4; Go 1.22/1.23; Python 3.10–3.13) so you see breakage before you ship.
- Dependabot is configured on every repo with weekly checks and grouped minor/patch updates to keep the dependency surface current without flooding reviewers.

## Links

- Versioning policy — [VERSIONING.md](../VERSIONING.md)
- OpenAPI 3.1 spec — [openapi/cryptohopper.yaml](../openapi/cryptohopper.yaml)
- API docs — [docs.cryptohopper.com](https://docs.cryptohopper.com)
- Support — issues on the affected repo, or [support.cryptohopper.com](https://support.cryptohopper.com)
