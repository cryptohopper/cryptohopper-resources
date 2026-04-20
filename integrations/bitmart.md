# BitMart Integration with Cryptohopper

BitMart is a global cryptocurrency exchange founded in 2017, headquartered in the Cayman Islands with offices worldwide. The platform is known for its wide selection of tokens, frequently listing new and emerging projects ahead of larger exchanges. BitMart serves millions of users across 180+ countries and offers both spot and futures trading. Connecting BitMart to Cryptohopper enables automated trading across a diverse range of assets with competitive fees.

## Why Trade on BitMart with Cryptohopper

BitMart provides access to a broad catalog of digital assets, making it attractive for traders seeking exposure to newer tokens. Key advantages include:

- Extensive selection of 1000+ tokens including early-stage listings
- Spot and futures trading support
- Competitive trading fees starting at 0.25% for spot
- Global availability across 180+ countries
- Regular listing of new and trending tokens
- Automated 24/7 trading execution via Cryptohopper

## How to Connect BitMart to Cryptohopper

### Step 1: Create a BitMart API Key

1. Log in to your BitMart account at [bitmart.com](https://www.bitmart.com/register-referral/en?r=VuEYv4).
2. Navigate to **Account** > **API Management** or find API settings under your profile.
3. Click **Create API Key**.
4. Enter a label (e.g., "Cryptohopper") and provide a memo for the key.
5. Complete security verification (2FA, email confirmation).
6. Copy the API Key, Secret Key, and Memo -- all three are required.

### Step 2: Configure API Key Permissions

1. Set the following permissions during key creation:
   - Enable **Read** -- allows market data and account balance access.
   - Enable **Trade** -- allows order placement on spot and futures markets.
2. Do not enable **Withdraw** permissions.
3. Restrict the API key to specific IP addresses if the option is available.
4. Save your configuration.

### Step 3: Add the API Key to Cryptohopper

1. Log in to [cryptohopper.com](https://www.cryptohopper.com).
2. Go to **Dashboard** and select or create a hopper.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **BitMart** from the exchange dropdown.
5. Enter your API Key, Secret Key, and Memo in the corresponding fields.
6. Click **Save**.

### Step 4: Verify the Connection

1. Confirm your BitMart balance appears in the Cryptohopper dashboard.
2. If the connection fails, verify all three credentials (API Key, Secret Key, and Memo) are entered correctly.
3. Check that API permissions include both Read and Trade access.

## Supported Features on Cryptohopper

Cryptohopper supports the following features when connected to BitMart:

- **Spot Trading** -- Automated buying and selling on BitMart spot markets.
- **Futures Trading** -- Automated futures positions with leverage on supported pairs.
- **Multiple Base Currencies** -- Trade against USDT, BTC, ETH, and other quote currencies.
- **Technical Analysis** -- Apply 130+ technical indicators and candlestick patterns.
- **Trailing Orders** -- Trailing stop-loss and trailing stop-buy for optimized trade execution.
- **Dollar-Cost Averaging (DCA)** -- Automatically average into positions over time.
- **Strategy Designer** -- Backtest strategies using historical BitMart data.
- **Marketplace** -- Access strategies and signals from the Cryptohopper marketplace.
- **Paper Trading** -- Test strategies risk-free with simulated funds.

## Supported Trading Pairs

BitMart offers one of the widest selections of trading pairs among supported exchanges. Cryptohopper syncs available pairs from the BitMart API, including:

- BTC/USDT, ETH/USDT, SOL/USDT and other major pairs
- Hundreds of altcoin/USDT pairs including newly listed tokens
- BTC-quoted pairs for select assets

The pair list updates automatically as BitMart adds or removes listings.

## Trading Fees

BitMart uses a tiered fee structure:

- Spot maker/taker fees starting at 0.25%
- Futures maker fees starting at 0.02%, taker fees at 0.06%
- Fee discounts available through BMX token holdings
- Volume-based tier reductions for active traders

Cryptohopper does not charge additional fees beyond the exchange fees.

## Security Considerations

- BitMart requires a Memo alongside the API Key and Secret Key -- store all three securely.
- Never enable withdrawal permissions on API keys used with trading bots.
- Enable two-factor authentication on your BitMart account.
- Use IP restrictions on API keys when available.
- Regularly review API key activity and revoke unused keys.
- Monitor your positions, especially on newly listed tokens with lower liquidity.

## Useful Links

- [BitMart Official Website](https://www.bitmart.com/register-referral/en?r=VuEYv4)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper Exchange Setup Documentation](https://docs.cryptohopper.com/docs/exchange-setup/bitmart)
- [BitMart API Documentation](https://developer-pro.bitmart.com/)

## Frequently Asked Questions

**Why does BitMart require a Memo in addition to the API Key and Secret?**
BitMart uses a three-part authentication system. The Memo acts as an additional security layer for API access. All three values must be entered in Cryptohopper for the connection to work.

**Does Cryptohopper support BitMart futures?**
Yes, Cryptohopper supports both spot and futures trading on BitMart. Ensure your API key has the appropriate trading permissions enabled.

**Are newly listed tokens on BitMart automatically available in Cryptohopper?**
Cryptohopper syncs trading pairs from the BitMart API. Newly listed tokens become available in Cryptohopper once they are active on BitMart and the pair data is synced.

**How does liquidity on BitMart compare to larger exchanges?**
BitMart has strong liquidity on major pairs. However, newly listed or lower-cap tokens may have thinner order books, which can result in higher slippage. Use appropriate position sizes and limit orders when trading less liquid assets.
