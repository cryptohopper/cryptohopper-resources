# Webhook Integration with Cryptohopper

Webhooks allow external applications to send trading signals to your Cryptohopper bot via HTTP requests. This is one of the most popular ways to integrate third-party tools like TradingView, custom scripts, and automated analysis platforms with Cryptohopper.

## What Are Webhooks?

A webhook is an HTTP callback -- an HTTP POST request sent from an external system to a specific URL when an event occurs. In the context of Cryptohopper, webhooks are used to deliver trading signals (buy or sell) to your bot from external sources.

## How Webhooks Work with Cryptohopper

### Setup Flow

1. In your Cryptohopper bot settings, enable webhook signals and obtain your unique webhook URL.
2. Configure your external tool (e.g., TradingView) to send HTTP POST requests to that URL when a trading condition is met.
3. When the webhook is received, Cryptohopper processes the signal and your bot executes the corresponding trade.

### Webhook URL

Each Cryptohopper bot has a unique webhook URL. This URL is specific to your bot and acts as the endpoint where signals are received. You can find it in your bot's signal configuration settings.

```
https://www.cryptohopper.com/webhooks?token=YOUR_UNIQUE_TOKEN
```

Keep your webhook URL private. Anyone with the URL can send signals to your bot.

## Payload Format

Webhook signals are sent as HTTP POST requests with a JSON payload. The payload tells Cryptohopper what action to take.

### Buy Signal

```json
{
  "action": "buy",
  "market": "BTC",
  "exchange": "binance"
}
```

### Sell Signal

```json
{
  "action": "sell",
  "market": "BTC",
  "exchange": "binance"
}
```

### Common Payload Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `action` | string | Yes | The action to perform: `buy` or `sell`. |
| `market` | string | Yes | The coin or trading pair (e.g., `BTC`, `ETH`). |
| `exchange` | string | No | Target exchange identifier. Required if your bot uses multiple exchanges. |

Additional fields may be supported depending on your bot configuration. Refer to the official API documentation for the full payload specification.

## Integrating TradingView with Cryptohopper

TradingView is one of the most common sources for webhook signals. Here is how to connect TradingView alerts to your Cryptohopper bot.

### Step 1: Create a TradingView Alert
In TradingView, set up an alert based on your chart analysis, indicator, or Pine Script strategy.

### Step 2: Configure the Webhook URL
In the TradingView alert settings:

1. Check the **Webhook URL** option.
2. Paste your Cryptohopper webhook URL.

### Step 3: Set the Alert Message
In the alert message field, enter the JSON payload that Cryptohopper expects:

```json
{
  "action": "buy",
  "market": "BTC"
}
```

### Step 4: Activate the Alert
Save and activate the alert. When TradingView triggers the alert, it sends the webhook to Cryptohopper, and your bot processes the signal.

### TradingView Dynamic Variables
TradingView supports dynamic variables in alert messages that are replaced at runtime:

```json
{
  "action": "buy",
  "market": "{{ticker}}"
}
```

The `{{ticker}}` variable is replaced with the symbol that triggered the alert, allowing you to use a single alert configuration across multiple charts.

## Security

### Protect Your Webhook URL
Your webhook URL contains a unique token that authenticates incoming signals. Treat it like a password:

- Do not share it publicly.
- Do not commit it to version control.
- Regenerate it if you suspect it has been compromised.

### IP Whitelisting
Where possible, configure IP whitelisting on your bot to accept webhook signals only from known sources (e.g., TradingView's IP ranges).

### Validate Signal Sources
Cryptohopper validates incoming webhook requests using the unique token in your webhook URL. Only requests with a valid token are processed.

### HTTPS
Always use the HTTPS webhook URL. Never send signals over unencrypted HTTP connections.

## Troubleshooting

### Signals Not Being Received
- Verify the webhook URL is correct and includes your unique token.
- Check that the sending application is making a POST request (not GET).
- Ensure the payload is valid JSON.
- Confirm your bot is enabled and has the webhook signal source activated.

### Trades Not Executing
- Check that the `market` in the payload matches an allowed coin in your bot configuration.
- Verify that your bot has sufficient funds to place the trade.
- Review your bot's activity log for error messages.
- Ensure the `action` field is correctly set to `buy` or `sell`.

### Rate Limiting
Sending too many webhook signals in a short period may trigger rate limiting. Space out signals appropriately and avoid sending duplicate signals.

## Best Practices

- **Test with paper trading first.** Before connecting webhooks to a live bot, test the integration using paper trading mode.
- **Use specific market identifiers.** Ensure the `market` field matches exactly what Cryptohopper expects for your configured trading pairs.
- **Log your signals.** Keep a record of sent webhooks for debugging and performance analysis.
- **Monitor your bot.** Regularly check that webhook signals are being received and processed correctly.

## Further Reading

- [Getting Started with the API](getting-started.md)
- [Authentication](authentication.md)
- [Cryptohopper API Reference](https://www.cryptohopper.com/api-documentation/api-reference)
