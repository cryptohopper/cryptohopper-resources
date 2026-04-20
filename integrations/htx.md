# HTX Integration with Cryptohopper

HTX (formerly Huobi Global) is one of the longest-running cryptocurrency exchanges in the industry. Originally founded in 2013 as Huobi, the platform rebranded to HTX in September 2023 to mark its tenth anniversary and signal a new strategic direction. HTX serves millions of users worldwide and offers spot, futures, and derivatives trading across hundreds of digital assets. Connecting HTX to Cryptohopper enables automated trading on a platform with deep liquidity and a proven operational track record.

## Why Trade on HTX with Cryptohopper

HTX combines over a decade of operational history with a comprehensive trading platform. Key advantages include:

- Established exchange with 10+ years of operational history
- Spot and futures trading support
- Deep liquidity across major trading pairs
- Competitive fee structure starting at 0.2% for spot
- Global availability with support for users worldwide
- Automated 24/7 strategy execution through Cryptohopper

## How to Connect HTX to Cryptohopper

### Step 1: Create an HTX API Key

1. Log in to your HTX account at [htx.com](https://www.htx.co.zw/invite/en-us/1h?invite_code=9cqt3).
2. Navigate to **Account & Security** > **API Management**.
3. Click **Create API Key** or **Create New Key**.
4. Enter a label or note (e.g., "Cryptohopper").
5. Complete security verification (2FA, email, or SMS confirmation).
6. Copy both the Access Key and Secret Key immediately -- the Secret Key is only shown once.

### Step 2: Configure API Key Permissions

1. During key creation, set the following permissions:
   - Enable **Read** -- allows access to market data and account balances.
   - Enable **Trade** -- allows order placement on spot and futures markets.
2. Do not enable **Withdraw** permissions.
3. Bind the API key to specific IP addresses for added security.
4. Save your configuration and confirm the changes.

### Step 3: Add the API Key to Cryptohopper

1. Log in to [cryptohopper.com](https://www.cryptohopper.com).
2. Go to **Dashboard** and select or create a hopper.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **HTX** from the exchange dropdown (may appear as HTX or Huobi depending on the version).
5. Enter your Access Key and Secret Key in the corresponding fields.
6. Click **Save**.

### Step 4: Verify the Connection

1. Confirm your HTX balance appears in the Cryptohopper dashboard.
2. If the connection fails, verify your API credentials and that trading permissions are enabled.
3. Ensure the API key is not restricted to IP addresses that exclude Cryptohopper's servers.

## Supported Features on Cryptohopper

Cryptohopper supports the following features when connected to HTX:

- **Spot Trading** -- Automated buying and selling on HTX spot markets.
- **Futures Trading** -- Automated futures positions with leverage on supported pairs.
- **Multiple Base Currencies** -- Trade against USDT, BTC, ETH, and other available quote currencies.
- **Technical Analysis** -- Apply 130+ technical indicators and candlestick patterns.
- **Trailing Orders** -- Trailing stop-loss and trailing stop-buy for optimized entries and exits.
- **Dollar-Cost Averaging (DCA)** -- Automatically average into positions.
- **Strategy Designer** -- Backtest strategies using historical HTX data.
- **Marketplace** -- Access strategies and signals from the Cryptohopper marketplace.
- **Paper Trading** -- Test strategies with simulated funds before going live.

## Supported Trading Pairs

HTX offers a broad selection of trading pairs across spot and futures markets. Cryptohopper syncs available pairs from the HTX API, including:

- BTC/USDT, ETH/USDT, SOL/USDT and other major pairs
- Hundreds of altcoin pairs across USDT and BTC markets
- Futures contracts on major cryptocurrencies

The full list updates automatically as HTX adds or delists trading pairs.

## Trading Fees

HTX uses a tiered fee structure based on trading volume and HT token holdings:

- Spot maker/taker fees starting at 0.2%
- Futures maker fees starting at 0.02%, taker fees at 0.05%
- Fee discounts available by holding HT (Huobi Token)
- Volume-based VIP tiers for reduced rates

Cryptohopper does not charge additional fees beyond the exchange fees.

## Security Considerations

- Never enable withdrawal permissions on API keys used with trading bots.
- Bind API keys to specific IP addresses to restrict access to Cryptohopper's servers.
- Enable two-factor authentication on your HTX account.
- Regularly review API key activity in the HTX security dashboard.
- Revoke unused or compromised API keys immediately.
- Note that HTX formerly operated as Huobi -- ensure you are using the current [htx.com](https://www.htx.co.zw/invite/en-us/1h?invite_code=9cqt3) domain.

## Useful Links

- [HTX Official Website](https://www.htx.co.zw/invite/en-us/1h?invite_code=9cqt3)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper Exchange Setup Documentation](https://docs.cryptohopper.com/docs/exchange-setup/htx)
- [HTX API Documentation](https://www.htx.com/en-us/opend/newApiPages/)

## Frequently Asked Questions

**Is HTX the same as Huobi?**
Yes. Huobi Global rebranded to HTX in September 2023. The platform, technology, and services are the same. Existing Huobi accounts and API keys continue to work under the HTX brand.

**Does Cryptohopper support HTX futures?**
Yes, Cryptohopper supports both spot and futures trading on HTX. Make sure your API key has the appropriate trade permissions enabled for the market type you intend to use.

**Will my old Huobi API keys work with the HTX integration?**
In most cases, existing API keys created under Huobi will continue to function after the rebrand. If you encounter issues, generate a new API key on [htx.com](https://www.htx.co.zw/invite/en-us/1h?invite_code=9cqt3).

**How does HTX liquidity compare to other major exchanges?**
HTX consistently ranks among the top exchanges by trading volume globally. Major pairs like BTC/USDT and ETH/USDT have deep order books with minimal slippage under normal market conditions.

**Is HTX available in the United States?**
HTX does not serve U.S. residents. Users in the United States should consider U.S.-compliant alternatives such as Binance.US, Coinbase, or Kraken.
