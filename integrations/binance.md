# Binance Integration with Cryptohopper

Binance is the world's largest cryptocurrency exchange by trading volume, serving millions of users across 180+ countries. Founded in 2017 by Changpeng Zhao, Binance offers a comprehensive trading platform with hundreds of trading pairs, deep liquidity, and competitive fees. Connecting Binance to Cryptohopper enables fully automated trading strategies on one of the most liquid exchanges in the crypto market.

## Why Trade on Binance with Cryptohopper

Binance provides access to one of the deepest order books in the industry. When combined with Cryptohopper's automated trading bot, traders can execute strategies 24/7 without manual intervention. Key advantages include:

- Access to 600+ trading pairs across spot markets
- High liquidity ensuring minimal slippage on trade execution
- Competitive trading fees starting at 0.1% for spot trades
- Fast API response times for reliable bot performance
- Support for advanced order types

## How to Connect Binance to Cryptohopper

Connecting your Binance account to Cryptohopper requires generating an API key on Binance and entering it into your Cryptohopper dashboard. Follow these steps carefully.

### Step 1: Create a Binance API Key

1. Log in to your Binance account at [binance.com](https://www.binance.com/en/register?ref=P6CD65KX).
2. Navigate to your profile icon and select **API Management**.
3. Enter a label for your API key (e.g., "Cryptohopper") and click **Create API**.
4. Complete the security verification (2FA, email confirmation).
5. Your API Key and Secret Key will be displayed. Copy both immediately -- the Secret Key is only shown once.

### Step 2: Configure API Key Permissions

1. On the API Management page, click **Edit** next to your new key.
2. Enable **Enable Spot & Margin Trading**.
3. Leave **Enable Withdrawals** disabled for security.
4. Optionally restrict access to trusted IP addresses for added security.
5. Click **Save** and confirm the changes.

### Step 3: Add the API Key to Cryptohopper

1. Log in to your Cryptohopper account at [cryptohopper.com](https://www.cryptohopper.com).
2. Go to **Dashboard** and select your hopper, or create a new one.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **Binance** from the exchange dropdown.
5. Paste your API Key and Secret Key into the corresponding fields.
6. Click **Save** to complete the connection.

### Step 4: Verify the Connection

1. After saving, Cryptohopper will attempt to connect to Binance.
2. If successful, your Binance balance will appear in the Cryptohopper dashboard.
3. If the connection fails, double-check that the API key permissions are correctly set and that no IP restrictions are blocking Cryptohopper's servers.

## Supported Features on Cryptohopper

Cryptohopper supports the following features when connected to Binance:

- **Spot Trading** -- Buy and sell cryptocurrencies on the Binance spot market.
- **Multiple Base Currencies** -- Trade with BTC, ETH, USDT, BUSD, and other quote currencies.
- **Technical Analysis** -- Apply 130+ technical indicators and candlestick patterns.
- **Trailing Orders** -- Use trailing stop-loss and trailing stop-buy for optimized entries and exits.
- **Dollar-Cost Averaging (DCA)** -- Automatically average down on positions.
- **Shorting** -- Short-sell assets using Cryptohopper's shorting feature.
- **Strategy Designer** -- Backtest and design custom strategies using historical Binance data.
- **Marketplace Strategies** -- Use strategies and signals from the Cryptohopper marketplace.
- **Paper Trading** -- Test strategies with simulated funds before going live.

## Supported Trading Pairs

Cryptohopper supports the majority of Binance spot trading pairs. The available pairs are automatically synced from the Binance API and include popular combinations such as:

- BTC/USDT, ETH/USDT, BNB/USDT
- ETH/BTC, BNB/BTC, SOL/BTC
- Hundreds of altcoin pairs across USDT, BTC, ETH, and BNB markets

The full list of available pairs updates automatically as Binance adds or removes trading pairs.

## Trading Fees

Binance charges a base trading fee of 0.1% per trade for spot markets. Fees can be further reduced by:

- Holding BNB and paying fees with BNB (25% discount)
- Increasing your 30-day trading volume for VIP tier discounts

Cryptohopper does not add any additional trading fees on top of the exchange fees.

## Security Considerations

- Never enable withdrawal permissions on your API key.
- Use IP whitelisting to restrict API access to Cryptohopper's servers only.
- Enable two-factor authentication on both your Binance and Cryptohopper accounts.
- Regularly review your API key activity in the Binance API Management panel.

## Useful Links

- [Binance Official Website](https://www.binance.com/en/register?ref=P6CD65KX)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper Binance Setup Guide](https://docs.cryptohopper.com/docs/exchange-setup/binance)
- [Binance API Documentation](https://binance-docs.github.io/apidocs/)

## Frequently Asked Questions

**Can I use Binance.US with Cryptohopper?**
Binance.US is a separate entity from Binance.com. Check the Cryptohopper documentation for the latest on Binance.US support, as availability may vary.

**Does Cryptohopper support Binance Futures?**
Cryptohopper primarily supports Binance spot trading. Check the Cryptohopper platform for the latest updates on futures support.

**How many trading pairs can I run simultaneously?**
The number of simultaneous trading pairs depends on your Cryptohopper subscription plan. Higher-tier plans support more open positions and trading pairs.

**Is there a delay between signals and trade execution?**
Cryptohopper executes trades as quickly as the Binance API allows. Under normal market conditions, execution is near-instant.
