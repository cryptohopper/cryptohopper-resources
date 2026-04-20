# KuCoin Integration with Cryptohopper

KuCoin is a global cryptocurrency exchange founded in 2017, known for its extensive selection of altcoins and trading pairs. Often referred to as "The People's Exchange," KuCoin lists new and emerging tokens earlier than many competitors, giving traders access to a wide variety of assets. With over 700 trading pairs and competitive fees, KuCoin is a popular choice for traders seeking exposure to smaller-cap cryptocurrencies. Connecting KuCoin to Cryptohopper enables automated trading across this broad asset selection.

## Why Trade on KuCoin with Cryptohopper

KuCoin stands out for its altcoin variety and trading features. Key advantages include:

- 700+ trading pairs with early access to emerging tokens
- Competitive trading fees starting at 0.1%
- KCS token holders receive fee discounts
- Strong liquidity across both major and mid-cap assets
- Support for spot, margin, and futures markets

## How to Connect KuCoin to Cryptohopper

### Step 1: Create a KuCoin API Key

1. Log in to your KuCoin account at [kucoin.com](https://www.kucoin.com/r/af/s7ywae).
2. Navigate to your profile icon and select **API Management**.
3. Click **Create API**.
4. Enter an API name (e.g., "Cryptohopper") and create an API passphrase. Save this passphrase -- you will need it for Cryptohopper.
5. Complete the security verification (2FA, email/SMS).
6. Your API Key, Secret Key, and Passphrase will be displayed. Copy all three values.

### Step 2: Configure API Key Permissions

1. During API key creation, set the following permissions:
   - Enable **General** -- allows reading account information.
   - Enable **Trade** -- allows placing and managing orders.
2. Do not enable **Transfer** permissions.
3. Optionally set IP restrictions to limit access to Cryptohopper's servers.
4. Save the configuration.

### Step 3: Add the API Key to Cryptohopper

1. Log in to [cryptohopper.com](https://www.cryptohopper.com).
2. Go to **Dashboard** and select or create a hopper.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **KuCoin** from the exchange dropdown.
5. Enter your API Key, Secret Key, and Passphrase.
6. Click **Save**.

### Step 4: Verify the Connection

1. Check that your KuCoin balance appears in the Cryptohopper dashboard.
2. If the connection fails, verify all three credentials (API Key, Secret, and Passphrase) are entered correctly.

## Supported Features on Cryptohopper

- **Spot Trading** -- Automated trading on KuCoin spot markets.
- **Multiple Base Currencies** -- Trade against USDT, BTC, ETH, KCS, and other quote currencies.
- **Technical Analysis** -- Use 130+ indicators and candlestick patterns.
- **Trailing Orders** -- Trailing stop-loss and stop-buy functionality.
- **Dollar-Cost Averaging (DCA)** -- Automatically average down on positions.
- **Strategy Designer** -- Backtest strategies with historical KuCoin data.
- **Marketplace** -- Access strategies and signals from the Cryptohopper marketplace.
- **Paper Trading** -- Test strategies without risking real capital.

## Supported Trading Pairs

KuCoin offers one of the widest selections of trading pairs. Cryptohopper syncs available pairs automatically, including:

- BTC/USDT, ETH/USDT, SOL/USDT, and hundreds of altcoin/USDT pairs
- Altcoin/BTC pairs for BTC-denominated trading
- KCS-quoted pairs
- Newly listed tokens often available shortly after launch

## Trading Fees

KuCoin uses a tiered fee structure:

- Base spot trading fee: 0.1% for both maker and taker
- KCS holders receive a 20% fee discount when paying fees with KCS
- Higher volume traders qualify for reduced fees through VIP tiers

Cryptohopper does not charge additional fees beyond KuCoin's exchange fees.

## Security Considerations

- KuCoin uses industry-standard security measures including cold storage and encryption.
- The API passphrase adds an extra layer of security unique to KuCoin.
- Never enable transfer permissions on API keys used with trading bots.
- Enable two-factor authentication on your KuCoin account.
- Use IP restrictions on API keys when possible.

## Useful Links

- [KuCoin Official Website](https://www.kucoin.com/r/af/s7ywae)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper KuCoin Setup Guide](https://docs.cryptohopper.com/docs/exchange-setup/kucoin)
- [KuCoin API Documentation](https://docs.kucoin.com/)

## Frequently Asked Questions

**Why does KuCoin require a passphrase in addition to the API key and secret?**
KuCoin uses an additional passphrase as an extra security layer for API access. You set this passphrase during API key creation and must enter it in Cryptohopper along with the key and secret.

**Does Cryptohopper support KuCoin Futures?**
Cryptohopper primarily supports KuCoin spot trading. Check the platform for the latest updates regarding futures support.

**Can I use KuCoin's lending or staking features through Cryptohopper?**
No. Cryptohopper focuses on automated spot trading. Lending and staking must be managed directly on KuCoin.

**How quickly are new KuCoin listings available on Cryptohopper?**
New trading pairs are synced from the KuCoin API automatically. They typically become available on Cryptohopper shortly after being listed on KuCoin.
