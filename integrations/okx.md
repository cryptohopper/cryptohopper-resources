# OKX Integration with Cryptohopper

OKX (formerly OKEx) is a global cryptocurrency exchange founded in 2017, headquartered in Seychelles with offices worldwide. OKX ranks among the top exchanges by trading volume and offers a comprehensive suite of trading products including spot, futures, options, and DeFi services. The exchange serves millions of users across 180+ countries. Connecting OKX to Cryptohopper enables automated trading on a feature-rich, high-liquidity platform.

## Why Trade on OKX with Cryptohopper

OKX provides a professional trading environment with broad market coverage. Key advantages include:

- Consistently ranks in the top 5 exchanges by global trading volume
- 300+ trading pairs on the spot market
- Advanced trading features and order types
- Competitive tiered fee structure
- High API rate limits suitable for bot trading

## How to Connect OKX to Cryptohopper

### Step 1: Create an OKX API Key

1. Log in to your OKX account at [okx.com](https://www.okx.com/join/1850952).
2. Navigate to the profile menu and select **API** under settings.
3. Click **Create API Key** (or **Create V5 API Key**).
4. Enter a label (e.g., "Cryptohopper") and set a passphrase. Save this passphrase securely.
5. Complete two-factor authentication verification.

### Step 2: Configure API Key Permissions

1. Set the following permissions:
   - Enable **Read** -- allows balance and market data access.
   - Enable **Trade** -- allows order placement and management.
2. Do not enable **Withdraw** permissions.
3. Optionally bind the API key to specific IP addresses.
4. Confirm and create the key.
5. Copy the API Key, Secret Key, and Passphrase.

### Step 3: Add the API Key to Cryptohopper

1. Log in to [cryptohopper.com](https://www.cryptohopper.com).
2. Go to **Dashboard** and select or create a hopper.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **OKX** from the exchange dropdown.
5. Enter your API Key, Secret Key, and Passphrase.
6. Click **Save**.

### Step 4: Verify the Connection

1. Check that your OKX balance appears in the Cryptohopper dashboard.
2. If the connection fails, verify that all three credentials are correct and permissions are properly set.

## Supported Features on Cryptohopper

- **Spot Trading** -- Automated trading on OKX spot markets.
- **Multiple Base Currencies** -- Trade against USDT, USDC, BTC, ETH, and other quote currencies.
- **Technical Analysis** -- Apply 130+ indicators and candlestick patterns.
- **Trailing Orders** -- Trailing stop-loss and trailing stop-buy.
- **Dollar-Cost Averaging (DCA)** -- Automatically average into positions.
- **Strategy Designer** -- Backtest strategies with historical OKX data.
- **Marketplace** -- Access strategies and signals from the Cryptohopper marketplace.
- **Paper Trading** -- Simulate trades with virtual funds.

## Supported Trading Pairs

OKX offers a wide range of spot trading pairs. Cryptohopper syncs available pairs automatically, including:

- BTC/USDT, ETH/USDT, SOL/USDT, and major pairs
- Hundreds of altcoin/USDT pairs
- Select BTC, ETH, and USDC-quoted pairs
- New listings added regularly

## Trading Fees

OKX uses a tiered maker/taker fee model:

- Taker fees start at 0.10% for regular users
- Maker fees start at 0.08% for regular users
- Fees decrease with higher trading volume and OKB token holdings
- VIP tiers offer significantly reduced rates

Cryptohopper does not add additional fees beyond the exchange fees.

## Security Considerations

- OKX uses multi-signature cold storage wallets for fund security.
- The passphrase for OKX API keys provides an extra authentication layer.
- Never enable withdrawal permissions on API keys used with trading bots.
- Enable all available security features on your OKX account (2FA, anti-phishing code).
- Use IP binding on API keys when possible.

## Useful Links

- [OKX Official Website](https://www.okx.com/join/1850952)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper OKX Setup Guide](https://docs.cryptohopper.com/docs/exchange-setup/okx)
- [OKX API Documentation](https://www.okx.com/docs-v5/en/)

## Frequently Asked Questions

**OKX requires a passphrase for API keys. Where do I enter it?**
Cryptohopper has a dedicated passphrase field when you select OKX as your exchange. Enter the passphrase you created during API key setup.

**Is OKX the same as OKEx?**
Yes. OKEx rebranded to OKX in early 2022. The platform and services remain the same.

**Does Cryptohopper support OKX Futures or Options?**
Cryptohopper primarily supports OKX spot trading. Refer to the Cryptohopper platform for the latest on derivatives support.

**Is OKX available in the United States?**
OKX is not available to residents of the United States. US-based traders should consider alternative exchanges supported by Cryptohopper.
