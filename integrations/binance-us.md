# Binance.US Integration with Cryptohopper

Binance.US is the United States-regulated cryptocurrency exchange operated independently from Binance.com (the global platform). Launched in 2019, Binance.US was built to comply with U.S. federal and state regulations, offering American residents a compliant way to trade digital assets. It is important to understand that Binance.US and global Binance are separate platforms with separate accounts, separate API keys, and separate order books. Connecting Binance.US to Cryptohopper enables automated spot trading within a U.S.-regulated environment.

## Why Trade on Binance.US with Cryptohopper

Binance.US provides a regulated trading environment tailored to U.S. residents. Key advantages of using Cryptohopper with Binance.US include:

- U.S.-regulated exchange compliant with federal and state requirements
- Access to a curated selection of spot trading pairs
- Competitive trading fees starting at 0.1% for spot trades
- Familiar Binance-style interface and API structure
- Automated 24/7 trading via Cryptohopper eliminates manual monitoring

## How to Connect Binance.US to Cryptohopper

Connecting Binance.US requires generating API credentials on the Binance.US platform. These credentials are entirely separate from any global Binance account you may hold.

### Step 1: Create a Binance.US API Key

1. Log in to your Binance.US account at [binance.us](https://www.binance.us/).
2. Navigate to your profile icon and select **API Management**.
3. Enter a label for your API key (e.g., "Cryptohopper") and click **Create API**.
4. Complete the required security verification (2FA, email confirmation).
5. Copy both the API Key and Secret Key immediately -- the Secret Key is only shown once.

### Step 2: Configure API Key Permissions

1. On the API Management page, click **Edit** next to your new key.
2. Enable **Enable Spot Trading** to allow order placement.
3. Do not enable **Enable Withdrawals** -- this is critical for security.
4. Restrict access to trusted IP addresses for added protection.
5. Click **Save** and confirm the changes.

### Step 3: Add the API Key to Cryptohopper

1. Log in to your Cryptohopper account at [cryptohopper.com](https://www.cryptohopper.com).
2. Go to **Dashboard** and select your hopper, or create a new one.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **Binance.US** from the exchange dropdown (not global Binance).
5. Paste your API Key and Secret Key into the corresponding fields.
6. Click **Save** to complete the connection.

### Step 4: Verify the Connection

1. After saving, Cryptohopper will attempt to connect to Binance.US.
2. If successful, your Binance.US balance will appear in the dashboard.
3. If the connection fails, confirm you selected Binance.US (not Binance) and that your API permissions are correct.

## Supported Features on Cryptohopper

Cryptohopper supports the following features when connected to Binance.US:

- **Spot Trading** -- Buy and sell cryptocurrencies on the Binance.US spot market.
- **Multiple Base Currencies** -- Trade with USD, USDT, BTC, and other available quote currencies.
- **Technical Analysis** -- Apply 130+ technical indicators and candlestick patterns.
- **Trailing Orders** -- Trailing stop-loss and trailing stop-buy for optimized entries and exits.
- **Dollar-Cost Averaging (DCA)** -- Automatically average down on positions.
- **Strategy Designer** -- Backtest and design strategies using historical market data.
- **Marketplace Strategies** -- Use strategies and signals from the Cryptohopper marketplace.
- **Paper Trading** -- Test strategies with simulated funds before going live.

## Supported Trading Pairs

Binance.US offers a curated selection of spot trading pairs. The available pairs are synced from the Binance.US API and include:

- BTC/USD, ETH/USD, SOL/USD and other fiat-quoted pairs
- BTC/USDT, ETH/USDT and stablecoin-quoted pairs
- Select altcoin pairs across USD, USDT, and BTC markets

The selection is smaller than global Binance due to U.S. regulatory requirements. Pair availability updates automatically as Binance.US adjusts its listings.

## Trading Fees

Binance.US charges a base trading fee of 0.1% per spot trade. Fees can be reduced by:

- Holding BNB and using it to pay trading fees
- Increasing your 30-day trading volume for tier-based discounts

Cryptohopper does not add any additional trading fees on top of exchange fees.

## Security Considerations

- Never enable withdrawal permissions on API keys used with trading bots.
- Use IP whitelisting to restrict API access to Cryptohopper's servers.
- Enable two-factor authentication on both Binance.US and Cryptohopper accounts.
- Do not reuse API keys from global Binance -- Binance.US requires its own credentials.
- Regularly review API key activity in the Binance.US dashboard.

## Useful Links

- [Binance.US Official Website](https://www.binance.us/)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper Exchange Setup Documentation](https://docs.cryptohopper.com/docs/exchange-setup/binance-us)
- [Binance.US API Documentation](https://docs.binance.us/)

## Frequently Asked Questions

**Can I use my global Binance API keys with Binance.US?**
No. Binance.US and global Binance are entirely separate platforms. You must create a new API key directly on [binance.us](https://www.binance.us/). Global Binance credentials will not work.

**Does Cryptohopper support Binance.US futures trading?**
Binance.US currently offers spot trading only. Futures and margin trading are not available on the platform.

**Why does Binance.US have fewer trading pairs than global Binance?**
Binance.US must comply with U.S. federal and state securities regulations. Assets are reviewed for regulatory compliance before listing, resulting in a more selective catalog.

**Is Binance.US available in all U.S. states?**
Binance.US is available in most but not all U.S. states. Some states have additional licensing requirements that may affect availability. Check the Binance.US website for current state-level restrictions.

**How does Cryptohopper handle Binance.US rate limits?**
Cryptohopper manages API call frequency within the limits set by Binance.US. Under normal conditions, rate limits do not affect bot performance.
