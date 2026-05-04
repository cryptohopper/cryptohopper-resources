# OpenAPI reference — Cryptohopper Public API v1

[`cryptohopper.yaml`](./cryptohopper.yaml) is the official, hand-maintained OpenAPI 3.1 spec for the **public** Cryptohopper API at `https://api.cryptohopper.com/v1`. It covers all 18 domains exposed to third-party developers.

## What this spec is for

- **Documentation** — point any OpenAPI viewer at the file for an interactive reference:
  - [Redocly](https://redocly.github.io/redoc/) — drag and drop the YAML, or host it with `redocly-cli preview-docs cryptohopper.yaml`.
  - [Swagger UI](https://petstore.swagger.io/) — paste the raw GitHub URL.
  - [Stoplight Elements](https://stoplight.io/open-source/elements) — embed in a docs site.
- **Postman / Insomnia / Bruno** — import directly to get a pre-baked collection for every endpoint.
- **Your own client** — if we don't ship an SDK in your language, code-generate one with [openapi-generator](https://openapi-generator.tech/) or any similar tool. Worth noting: the **official SDKs are handwritten**, not generated, because the handwritten surface feels idiomatic per language. A generated client from this spec will work but will have a generator-flavoured API.

## Official SDKs

The spec is the contract behind these packages. Each one is feature-equivalent and shares the same error taxonomy, auto-retry behaviour on 429, and auth model.

| Language | Install | Repository |
|---|---|---|
| Node.js / TypeScript | `npm i @cryptohopper/sdk` | [`cryptohopper-node-sdk`](https://github.com/cryptohopper/cryptohopper-node-sdk) |
| Python | `pip install cryptohopper` | [`cryptohopper-python-sdk`](https://github.com/cryptohopper/cryptohopper-python-sdk) |
| Go | `go get github.com/cryptohopper/cryptohopper-go-sdk` | [`cryptohopper-go-sdk`](https://github.com/cryptohopper/cryptohopper-go-sdk) |
| Ruby | `gem install cryptohopper --pre` | [`cryptohopper-ruby-sdk`](https://github.com/cryptohopper/cryptohopper-ruby-sdk) |
| Rust | `cargo add cryptohopper` | [`cryptohopper-rust-sdk`](https://github.com/cryptohopper/cryptohopper-rust-sdk) |
| CLI | `npm i -g @cryptohopper/cli` or binaries | [`cryptohopper-cli`](https://github.com/cryptohopper/cryptohopper-cli) |

## Authentication

Every request (except endpoints explicitly marked `security: []` in the spec) requires a bearer token:

```
Authorization: Bearer <40-char OAuth2 access token>
```

Tokens are issued via the developer dashboard on cryptohopper.com. See [Authentication](https://api.cryptohopper.com/v1/docs) in the main API docs for the consent-flow walkthrough.

An optional `x-api-app-key` header carries your OAuth `client_id` for per-app rate-limit attribution.

## Scope and exclusions

**Included** (18 domains, ~150 endpoints):

`user` · `hoppers` · `exchange` · `strategy` · `backtest` · `market` · `signals` · `arbitrage` · `marketmaker` · `template` · `ai` · `platform` · `chart` · `subscription` · `social` · `tournaments` · `webhooks` · `app`

**Not included** (out of scope for the v1 public surface):

- The **SiteAPI** (`/siteapi.php`) — session-based internal API for the Cryptohopper web app and official mobile apps.
- The **mobile device-id authorisation** flow (internal).
- **HMAC request signing** (`x-api-signature`) — optional high-volume-partner extension; all SDKs use bearer-only because it covers 99% of integrations.
- **Signal webhook publishing** (`/signal.php`) — distinct auth model (HMAC-SHA512 via `X-Hub-Signature`); see the main API docs if you're building a signal-provider integration.

## Keeping this in sync with the server

The spec is hand-edited alongside the corresponding SDK changes in each domain's resource file. When a new endpoint ships in the Cryptohopper v1 API, the update path is:

1. Add the PHP handler in `public_html/api/classes/<domain>/apis.php`.
2. Add methods to all SDKs in one lockstep minor release (alpha/beta first).
3. Add the path to `cryptohopper.yaml` and send a PR to this repo.

If you spot a drift between the spec and the live server, please open an issue.

## Validating changes locally

```bash
# Using redocly (preview + validate)
npx @redocly/cli lint openapi/cryptohopper.yaml

# Using openapi-generator (validate)
npx @openapitools/openapi-generator-cli validate -i openapi/cryptohopper.yaml
```

## License

This spec file is MIT-licensed; reuse freely.
