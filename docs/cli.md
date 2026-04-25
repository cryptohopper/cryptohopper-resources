# Cryptohopper CLI

`cryptohopper` is the official command-line interface for the Cryptohopper platform. It wraps the Node SDK (`@cryptohopper/sdk`) with a commander-based UI, ships as standalone binaries compiled with Bun for fast cold-starts, and is also published to npm for users who already have Node installed.

- Repository — [cryptohopper-cli](https://github.com/cryptohopper/cryptohopper-cli)
- npm — [@cryptohopper/cli](https://www.npmjs.com/package/@cryptohopper/cli)
- Releases (binaries) — [github.com/cryptohopper/cryptohopper-cli/releases](https://github.com/cryptohopper/cryptohopper-cli/releases)

## Install

```bash
# Via npm (all platforms, requires Node 20+)
npm install -g @cryptohopper/cli

# macOS (Apple Silicon)
curl -L https://github.com/cryptohopper/cryptohopper-cli/releases/latest/download/cryptohopper-darwin-arm64 \
     -o /usr/local/bin/cryptohopper && chmod +x /usr/local/bin/cryptohopper

# macOS (Intel)
curl -L https://github.com/cryptohopper/cryptohopper-cli/releases/latest/download/cryptohopper-darwin-x64 \
     -o /usr/local/bin/cryptohopper && chmod +x /usr/local/bin/cryptohopper

# Linux x64
curl -L https://github.com/cryptohopper/cryptohopper-cli/releases/latest/download/cryptohopper-linux-x64 \
     -o /usr/local/bin/cryptohopper && chmod +x /usr/local/bin/cryptohopper

# Windows x64 (PowerShell)
Invoke-WebRequest https://github.com/cryptohopper/cryptohopper-cli/releases/latest/download/cryptohopper-windows-x64.exe `
                 -OutFile cryptohopper.exe
```

Every binary release includes a `SHA256SUMS` file. Verify before installing:

```bash
sha256sum -c SHA256SUMS
```

## Authenticate

```bash
cryptohopper login
```

Opens your default browser to the Cryptohopper OAuth consent page, spins up a loopback listener on `127.0.0.1:18765`, and persists the returned token to `~/.cryptohopper/config.json` (mode 0600).

For CI or headless SSH sessions where no browser is available:

```bash
cryptohopper login --token <your-bearer-token>
```

Environment overrides (always win over the config file):

| Variable | Purpose |
|---|---|
| `CRYPTOHOPPER_TOKEN` | Override the stored token |
| `CRYPTOHOPPER_APP_KEY` | OAuth `client_id` sent as `x-api-app-key` |
| `CRYPTOHOPPER_API_URL` | Point at staging or a local dev server |
| `CRYPTOHOPPER_WEB_URL` | Origin of the OAuth `/oauth2/authorize` + `/oauth2/token` endpoints |

## Commands

Global flag: every command accepts `--json` to emit machine-readable JSON instead of a table.

### Account
```bash
cryptohopper whoami                      # Print the authenticated user
cryptohopper logout                      # Clear the local token
```

### Hoppers
```bash
cryptohopper hoppers list                # Table of all your bots (alias: ls)
cryptohopper hoppers list --exchange binance
cryptohopper hoppers get <id>            # Full JSON for one hopper
cryptohopper hoppers panic <id> --yes    # Market-sell every position (destructive)
cryptohopper positions <hopper-id>       # Open positions, table form
cryptohopper orders <hopper-id>          # Recent orders, table form
```

### Market data (public, no auth)
```bash
cryptohopper ticker <exchange> <market>     # e.g. cryptohopper ticker binance BTC/USDT
cryptohopper exchange list                   # All supported exchanges (alias: ls)
cryptohopper exchange markets <exchange>     # Trading pairs on an exchange
```

### Strategies
```bash
cryptohopper strategy list                   # All your saved strategies (alias: ls)
cryptohopper strategy get <id>               # Pretty-print a strategy's config
```

### Backtests
```bash
cryptohopper backtest new <hopper-id> --from 2026-01-01 --to 2026-03-01
cryptohopper backtest status <backtest-id>
cryptohopper backtest limits             # Your quota
```

### Signals (for providers)
```bash
cryptohopper signals list                # Signals you've published
cryptohopper signals stats               # Subscribers, total PnL
cryptohopper signals performance         # Winrate, avg profit per signal
```

### Arbitrage
```bash
cryptohopper arbitrage history
cryptohopper arbitrage total
```

### Market maker
```bash
cryptohopper marketmaker get <hopper-id>
cryptohopper marketmaker history <hopper-id>
```

### Templates
```bash
cryptohopper template list               # (alias: ls)
cryptohopper template get <id>
cryptohopper template load <template-id> <hopper-id> --yes   # Overwrites config
cryptohopper template delete <id> --yes                       # Destructive
```

### AI
```bash
cryptohopper ai credits
cryptohopper ai models
```

### Subscription
```bash
cryptohopper subscription get
cryptohopper subscription plans          # Public
cryptohopper subscription credits
```

### Tournaments
```bash
cryptohopper tournaments list
cryptohopper tournaments active
cryptohopper tournaments leaderboard <tournament-id>
```

### Maintenance
```bash
cryptohopper upgrade                     # Self-replace the binary from GitHub Releases
cryptohopper upgrade --check             # Only check, don't install
cryptohopper config get [key]            # View CLI config
cryptohopper config set <key> <value>    # apiUrl, webUrl, appKey
cryptohopper completion <shell>          # bash | zsh | fish | powershell
```

## Confirmation gates

Destructive commands require `--yes` as an explicit acknowledgement:

- `hoppers panic <id>` — market-sells every position on the hopper
- `template load <template-id> <hopper-id>` — overwrites the hopper's config
- `template delete <id>` — permanently deletes a template

`--yes` is required **in both text and JSON modes**. In JSON mode a missing `--yes` is emitted as a structured refusal on stderr:

```json
{ "ok": false, "error": { "code": "CONFIRMATION_REQUIRED", "message": "..." } }
```

and the process exits with status 1. (In versions prior to 0.5.1-alpha.1, `--json` was incorrectly bypassing the gate — see the CHANGELOG for details.)

## Exit codes

| Code | Meaning |
|---|---|
| 0 | Success |
| 1 | Generic / user error (including `CONFIRMATION_REQUIRED`) |
| 2 | Auth failure (`UNAUTHORIZED` / `FORBIDDEN` / `DEVICE_UNAUTHORIZED`) |
| 3 | Rate limited (`RATE_LIMITED`) |
| 4 | Server error (`SERVER_ERROR` / `SERVICE_UNAVAILABLE`) |
| 5 | Network or timeout (`NETWORK_ERROR` / `TIMEOUT`) |

Scripts can rely on these being stable across releases.

## JSON output contract

Every command's `--json` output is a single JSON object per invocation, written to stdout (success) or stderr (failure):

```jsonc
// Success
{ "ok": true, "hoppers": [ ... ] }

// Failure (SDK error)
{ "ok": false, "error": { "code": "UNAUTHORIZED", "status": 401, "message": "...", "serverCode": null, "ipAddress": "..." } }

// Failure (CLI-level, e.g. missing --yes)
{ "ok": false, "error": { "code": "CONFIRMATION_REQUIRED", "message": "..." } }
```

Warning output (progress lines, tables) is always suppressed under `--json`. If you see unexpected text on stdout in `--json` mode, it's a bug — please file it.

## Upgrading

The `upgrade` subcommand replaces the running binary in place with the latest GitHub Release matching your platform. Integrity check: every release ships a `SHA256SUMS` file which is fetched alongside the binary and verified before the swap.

```bash
cryptohopper upgrade
cryptohopper upgrade --check          # Check only; don't install
```

Requirements:
- The binary has to be the Bun-compiled standalone variant (not a `node dist/index.js` development install).
- The user must have write permission on the binary's directory. If not, run the command under `sudo` or move the binary into a user-writable directory.

On Windows, the old binary is renamed to `.old` and cleaned up at the start of the next run (a running executable can't delete itself).

## Runtime requirements

- npm install (`@cryptohopper/cli`) — Node.js 20+
- Standalone binaries — no runtime dependencies; each binary bundles its own JS runtime

## Changelog

The canonical changelog lives in the [repo's CHANGELOG.md](https://github.com/cryptohopper/cryptohopper-cli/blob/main/CHANGELOG.md). Release notes on each tagged release mirror the relevant section.

## Related

- [`@cryptohopper/sdk`](https://www.npmjs.com/package/@cryptohopper/sdk) — the Node SDK the CLI is built on. If a CLI command doesn't exist for an endpoint you need, the SDK covers every endpoint.
- [docs/sdks.md](sdks.md) — overview of every official SDK.
- [VERSIONING.md](../VERSIONING.md) — SDK & CLI versioning, release, and deprecation policy.
