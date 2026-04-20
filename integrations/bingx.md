# BingX Integration with Cryptohopper

BingX is a global cryptocurrency exchange founded in 2018, known for its social and copy trading features. The exchange offers spot, derivatives, and grid trading services to users in 100+ countries. BingX has positioned itself as a bridge between traditional social trading and the cryptocurrency market, making it accessible to both beginners and experienced traders. Connecting BingX to Cryptohopper enables automated spot trading on a platform with a growing user base and expanding asset selection.

## Why Trade on BingX with Cryptohopper

BingX combines social trading elements with a capable exchange platform. Key advantages include:

- Growing selection of spot trading pairs
- Competitive fee structure
- User-friendly platform suitable for beginners
- Social trading features for community-driven strategies
- Expanding liquidity and market depth

## How to Connect BingX to Cryptohopper

### Step 1: Create a BingX API Key

1. Log in to your BingX account at [bingx.com](https://bingx.com/invite/AAAR94).
2. Navigate to **Account** > **API Management**.
3. Click **Create API** or **Create New Key**.
4. Enter a label (e.g., "Cryptohopper").
5. Complete security verification (2FA).

### Step 2: Configure API Key Permissions

1. Set the following permissions:
   - Enable **Read** -- allows account and market data access.
   - Enable **Spot Trading** -- allows order placement on spot markets.
2. Do not enable **Withdraw** or **Transfer** permissions.
3. Optionally restrict the API key to specific IP addresses.
4. Generate the key and copy the API Key and Secret Key.

### Step 3: Add the API Key to Cryptohopper

1. Log in to [cryptohopper.com](https://www.cryptohopper.com).
2. Go to **Dashboard** and select or create a hopper.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **BingX** from the exchange dropdown.
5. Enter your API Key and Secret Key.
6. Click **Save**.

### Step 4: Verify the Connection

1. Confirm your BingX balance appears in the Cryptohopper dashboard.
2. If the connection fails, verify your API credentials and permissions.

## Supported Features on Cryptohopper

- **Spot Trading** -- Automated buying and selling on BingX spot markets.
- **Multiple Base Currencies** -- Trade against USDT and other available quote currencies.
- **Technical Analysis** -- Apply 130+ indicators and candlestick patterns.
- **Trailing Orders** -- Trailing stop-loss and trailing stop-buy.
- **Dollar-Cost Averaging (DCA)** -- Automatically average into positions.
- **Strategy Designer** -- Backtest strategies with historical BingX data.
- **Marketplace** -- Access strategies and signals from the Cryptohopper marketplace.
- **Paper Trading** -- Test strategies with simulated funds.

## Supported Trading Pairs

BingX offers a growing selection of spot trading pairs. Cryptohopper syncs available pairs, including:

- BTC/USDT, ETH/USDT, SOL/USDT and major pairs
- Popular altcoin/USDT pairs
- New spot listings added as BingX expands its offerings

## Trading Fees

BingX uses a straightforward fee structure:

- Maker fees: 0.10%
- Taker fees: 0.10%
- Fee discounts may be available through promotions or VIP tiers
- Volume-based fee reductions for active traders

Cryptohopper does not charge additional fees beyond the exchange fees.

## Security Considerations

- BingX employs industry-standard security practices including cold storage.
- Never enable withdrawal or transfer permissions on API keys used with bots.
- Enable two-factor authentication on your BingX account.
- Use IP restrictions on API keys when available.
- Monitor your API key activity regularly.

## Useful Links

- [BingX Official Website](https://bingx.com/invite/AAAR94)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper BingX Setup Guide](https://docs.cryptohopper.com/docs/exchange-setup/bingx)
- [BingX API Documentation](https://bingx-api.github.io/docs/)

## Frequently Asked Questions

**How does BingX compare to larger exchanges for automated trading?**
While BingX has lower volume than top-tier exchanges, it offers competitive fees and a growing selection of trading pairs. Liquidity continues to improve as the platform grows.

**Does Cryptohopper support BingX derivatives?**
Cryptohopper primarily supports BingX spot trading. Check the platform for updates on derivatives support.

**Can I use BingX's copy trading alongside Cryptohopper?**
BingX's native copy trading and Cryptohopper operate independently. Using both simultaneously on the same account may cause conflicts. It is recommended to dedicate API keys to one service at a time.

**Is BingX available in my country?**
BingX operates in 100+ countries but has restrictions in certain jurisdictions. Check BingX's terms of service for regional availability.
