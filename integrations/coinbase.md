# Coinbase Advanced Trade Integration with Cryptohopper

Coinbase is one of the most trusted and widely used cryptocurrency exchanges in the United States. As a publicly traded company (NASDAQ: COIN), Coinbase operates under strict regulatory oversight, making it a preferred choice for compliance-conscious traders. Coinbase Advanced Trade (formerly Coinbase Pro) provides a professional-grade trading interface with competitive fees and deep liquidity. Connecting Coinbase to Cryptohopper allows traders to automate strategies on a fully regulated US exchange.

## Why Trade on Coinbase with Cryptohopper

Coinbase Advanced Trade offers a regulated, secure environment for cryptocurrency trading. Combined with Cryptohopper, traders gain:

- Access to a US-regulated exchange with strong compliance standards
- Deep liquidity for major trading pairs
- Competitive maker/taker fee structure
- Insurance-backed custody of digital assets
- Reliable API infrastructure for automated trading

## How to Connect Coinbase to Cryptohopper

Connecting Coinbase Advanced Trade to Cryptohopper requires creating an API key through the Coinbase developer platform.

### Step 1: Create a Coinbase API Key

1. Log in to your Coinbase account at [coinbase.com](https://coinbase-consumer.sjv.io/anKdgR).
2. Navigate to **Settings** > **API** or visit the Coinbase Cloud developer portal.
3. Click **New API Key**.
4. Complete the required security verification steps.
5. Your API Key and API Secret will be displayed. Copy and store both securely -- the secret is shown only once.

### Step 2: Configure API Key Permissions

1. When creating or editing the API key, set the following permissions:
   - Enable **Trade** permissions to allow Cryptohopper to place orders.
   - Enable **View** permissions to allow balance and market data access.
2. Do not enable **Transfer** or **Withdraw** permissions.
3. Optionally add IP address restrictions for enhanced security.
4. Confirm and save your settings.

### Step 3: Add the API Key to Cryptohopper

1. Log in to [cryptohopper.com](https://www.cryptohopper.com).
2. Go to your **Dashboard** and select or create a hopper.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **Coinbase Advanced** from the exchange dropdown.
5. Enter your API Key and API Secret.
6. Click **Save**.

### Step 4: Verify the Connection

1. After saving, your Coinbase balance should appear in the Cryptohopper dashboard.
2. If the connection fails, verify that your API key has the correct permissions and that no IP restrictions are blocking access.

## Supported Features on Cryptohopper

When connected to Coinbase Advanced Trade, Cryptohopper supports:

- **Spot Trading** -- Automated buying and selling on Coinbase spot markets.
- **Multiple Base Currencies** -- Trade against USD, USDT, EUR, BTC, and other quote currencies.
- **Technical Analysis** -- Apply 130+ indicators and candlestick patterns to Coinbase market data.
- **Trailing Orders** -- Trailing stop-loss and trailing stop-buy functionality.
- **Dollar-Cost Averaging (DCA)** -- Automatically average into positions over time.
- **Strategy Designer** -- Backtest strategies against historical Coinbase data.
- **Marketplace** -- Access community strategies, signals, and templates.
- **Paper Trading** -- Simulate trades without risking real funds.

## Supported Trading Pairs

Coinbase Advanced Trade supports a curated selection of trading pairs. Cryptohopper automatically syncs available pairs, which typically include:

- BTC/USD, ETH/USD, SOL/USD
- BTC/USDT, ETH/USDT
- Major altcoin pairs against USD, USDT, and BTC
- Select EUR and GBP trading pairs

The available pairs depend on your region and regulatory requirements. Coinbase regularly adds new assets after completing its listing review process.

## Trading Fees

Coinbase Advanced Trade uses a maker/taker fee model:

- Taker fees start at 0.60% and decrease with volume
- Maker fees start at 0.40% and decrease with volume
- High-volume traders can achieve significantly lower rates

Cryptohopper does not charge additional trading fees beyond the exchange fees.

## Security Considerations

- Coinbase is a publicly traded, US-regulated company with institutional-grade security.
- Never enable withdrawal permissions on API keys used with trading bots.
- Enable two-factor authentication on your Coinbase account.
- Use IP whitelisting when available for API keys.
- Coinbase maintains insurance on custodial funds held on the platform.

## Useful Links

- [Coinbase Official Website](https://coinbase-consumer.sjv.io/anKdgR)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper Coinbase Setup Guide](https://docs.cryptohopper.com/docs/exchange-setup/coinbase)
- [Coinbase API Documentation](https://docs.cloud.coinbase.com/)

## Frequently Asked Questions

**Is Coinbase Pro still supported?**
Coinbase Pro has been replaced by Coinbase Advanced Trade. Cryptohopper connects to the current Coinbase Advanced Trade API.

**Can I trade with USD on Coinbase through Cryptohopper?**
Yes. Coinbase supports direct USD trading pairs, and Cryptohopper can execute trades against USD quote currency.

**Are there geographic restrictions?**
Coinbase availability varies by region. Some trading pairs and features may not be available in all jurisdictions. Check Coinbase's supported regions for details.

**Does Cryptohopper support Coinbase staking or earn features?**
No. Cryptohopper focuses on spot trading automation. Staking and earn features are managed directly through Coinbase.
