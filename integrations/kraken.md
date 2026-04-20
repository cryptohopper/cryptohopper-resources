# Kraken Integration with Cryptohopper

Kraken is a US-based cryptocurrency exchange founded in 2011, making it one of the longest-operating exchanges in the industry. Known for its strong security track record and regulatory compliance, Kraken has never suffered a major security breach. The exchange offers a wide range of trading pairs, competitive fees, and advanced trading features. Connecting Kraken to Cryptohopper enables automated trading on one of the most trusted exchanges in crypto.

## Why Trade on Kraken with Cryptohopper

Kraken's combination of security, reliability, and liquidity makes it an excellent choice for automated trading. Benefits include:

- Over a decade of operation with a clean security record
- Regulated in multiple jurisdictions including the US
- Competitive fee structure with volume-based discounts
- Deep liquidity for major trading pairs
- Support for fiat currencies including USD, EUR, GBP, CAD, and more

## How to Connect Kraken to Cryptohopper

### Step 1: Create a Kraken API Key

1. Log in to your Kraken account at [kraken.com](https://kraken.pxf.io/LXGyW0).
2. Navigate to **Settings** > **API** (or go to Security > API).
3. Click **Add Key** or **Generate New Key**.
4. Enter a description for the key (e.g., "Cryptohopper Bot").

### Step 2: Configure API Key Permissions

1. Under key permissions, enable the following:
   - **Query Funds** -- allows Cryptohopper to read your balance.
   - **Query Open Orders & Trades** -- allows monitoring of order status.
   - **Query Closed Orders & Trades** -- allows trade history access.
   - **Create & Modify Orders** -- allows Cryptohopper to place and cancel orders.
   - **Cancel/Close Orders** -- allows order cancellation.
2. Do not enable **Withdraw Funds** or **Query/Manage Deposit Addresses**.
3. Optionally set an IP whitelist or a key expiration date.
4. Click **Generate Key**.
5. Copy the API Key and Private Key. The Private Key is shown only once.

### Step 3: Add the API Key to Cryptohopper

1. Log in to [cryptohopper.com](https://www.cryptohopper.com).
2. Go to **Dashboard** and select or create a hopper.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **Kraken** from the exchange dropdown.
5. Paste your API Key and Private Key.
6. Click **Save**.

### Step 4: Verify the Connection

1. After saving, check that your Kraken balance appears in Cryptohopper.
2. If the connection fails, verify API permissions and ensure no IP restrictions are blocking access.

## Supported Features on Cryptohopper

- **Spot Trading** -- Automated trading on Kraken's spot markets.
- **Multiple Base Currencies** -- Trade against USD, EUR, USDT, BTC, ETH, and other quote currencies.
- **Technical Analysis** -- Use 130+ indicators and candlestick patterns.
- **Trailing Orders** -- Trailing stop-loss and stop-buy for optimized trade execution.
- **Dollar-Cost Averaging (DCA)** -- Automatically average into losing positions.
- **Strategy Designer** -- Design and backtest strategies with historical Kraken data.
- **Marketplace** -- Access strategies and signals from the Cryptohopper marketplace.
- **Paper Trading** -- Test strategies risk-free with simulated funds.

## Supported Trading Pairs

Kraken supports a broad selection of trading pairs. Cryptohopper syncs available pairs automatically, including:

- BTC/USD, ETH/USD, SOL/USD, XRP/USD
- BTC/EUR, ETH/EUR and other EUR pairs
- BTC/USDT, ETH/USDT
- Altcoin pairs against BTC and ETH

Kraken uses unique pair naming conventions (e.g., XXBTZUSD for BTC/USD). Cryptohopper handles this mapping automatically.

## Trading Fees

Kraken uses a maker/taker fee model for spot trading:

- Taker fees start at 0.26% and decrease with volume
- Maker fees start at 0.16% and decrease with volume
- 30-day volume thresholds determine your fee tier

Cryptohopper does not add additional fees on top of exchange fees.

## Security Considerations

- Kraken is widely regarded as one of the most secure cryptocurrency exchanges.
- Never enable withdrawal permissions on API keys used for trading bots.
- Use the optional nonce window setting if you experience nonce-related errors.
- Enable two-factor authentication on your Kraken account.
- Consider using Kraken's Global Settings Lock for additional account protection.

## Useful Links

- [Kraken Official Website](https://kraken.pxf.io/LXGyW0)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper Kraken Setup Guide](https://docs.cryptohopper.com/docs/exchange-setup/kraken)
- [Kraken API Documentation](https://docs.kraken.com/rest/)

## Frequently Asked Questions

**Does Cryptohopper support Kraken Futures?**
Cryptohopper primarily supports Kraken spot trading. Check the Cryptohopper platform for the latest updates on futures support.

**Why do I see unusual ticker names on Kraken?**
Kraken uses its own naming convention for trading pairs (e.g., XBT instead of BTC). Cryptohopper translates these automatically so you can use standard ticker names.

**Can I trade with EUR on Kraken through Cryptohopper?**
Yes. Kraken supports multiple fiat quote currencies including EUR, USD, GBP, and CAD. You can configure your hopper to use any supported quote currency.

**What should I do if I get a nonce error?**
Nonce errors occur when API requests arrive out of order. Ensure only one bot or application is using each API key. You can also adjust the nonce window in Kraken's API settings.
