# Crypto.com Exchange Integration with Cryptohopper

Crypto.com is a global cryptocurrency platform founded in 2016, serving over 80 million users worldwide. The Crypto.com Exchange offers spot trading with competitive fees, a wide range of trading pairs, and deep liquidity. The company is known for its extensive marketing presence and regulatory compliance across multiple jurisdictions. Connecting the Crypto.com Exchange to Cryptohopper enables automated trading on one of the most recognized brands in crypto.

## Why Trade on Crypto.com with Cryptohopper

Crypto.com combines brand recognition with a solid trading infrastructure. Key advantages include:

- 250+ trading pairs on the spot exchange
- Competitive fees with CRO token staking discounts
- Regulated in multiple jurisdictions
- Strong liquidity for major trading pairs
- Comprehensive ecosystem including DeFi, NFTs, and a Visa card

## How to Connect Crypto.com Exchange to Cryptohopper

### Step 1: Create a Crypto.com Exchange API Key

1. Log in to the Crypto.com Exchange at [crypto.com/exchange](https://crypto.com/exchange).
2. Note: The Crypto.com Exchange is separate from the Crypto.com App. You need an Exchange account.
3. Navigate to **Settings** > **API Keys**.
4. Click **Create a New API Key**.
5. Enter a label (e.g., "Cryptohopper").
6. Complete two-factor authentication.

### Step 2: Configure API Key Permissions

1. Set the following permissions:
   - Enable **Read** access for account data.
   - Enable **Trade** access for order management.
2. Do not enable **Withdraw** permissions.
3. Optionally set IP whitelisting for added security.
4. Confirm and generate the key.
5. Copy the API Key and Secret Key.

### Step 3: Add the API Key to Cryptohopper

1. Log in to [cryptohopper.com](https://www.cryptohopper.com).
2. Go to **Dashboard** and select or create a hopper.
3. Navigate to **Config** > **Baseconfig** > **Exchange**.
4. Select **Crypto.com** from the exchange dropdown.
5. Enter your API Key and Secret Key.
6. Click **Save**.

### Step 4: Verify the Connection

1. Confirm that your Crypto.com Exchange balance appears in Cryptohopper.
2. If the connection fails, verify credentials and ensure you are using Exchange API keys (not App API keys).

## Supported Features on Cryptohopper

- **Spot Trading** -- Automated trading on the Crypto.com Exchange.
- **Multiple Base Currencies** -- Trade against USDT, USDC, BTC, CRO, and other quote currencies.
- **Technical Analysis** -- Apply 130+ indicators and candlestick patterns.
- **Trailing Orders** -- Trailing stop-loss and trailing stop-buy.
- **Dollar-Cost Averaging (DCA)** -- Automatically average into positions.
- **Strategy Designer** -- Backtest strategies with historical exchange data.
- **Marketplace** -- Access strategies and signals from the Cryptohopper marketplace.
- **Paper Trading** -- Simulate trades without risking real funds.

## Supported Trading Pairs

Crypto.com Exchange offers a broad selection of trading pairs. Cryptohopper syncs available pairs, including:

- BTC/USDT, ETH/USDT, CRO/USDT, SOL/USDT
- Major altcoin/USDT and altcoin/USDC pairs
- CRO-quoted pairs
- BTC-quoted pairs for select assets

## Trading Fees

Crypto.com Exchange uses a tiered maker/taker model:

- Taker fees start at 0.075%
- Maker fees start at 0.075%
- CRO staking provides fee discounts of up to 10%
- Higher trading volumes unlock lower fee tiers

Cryptohopper does not charge additional fees beyond the exchange fees.

## Security Considerations

- Crypto.com holds SOC 2, PCI DSS Level 1, and ISO 27001 certifications.
- The platform uses cold storage for the majority of user funds.
- Never enable withdrawal permissions on API keys used with bots.
- Enable two-factor authentication on your Crypto.com account.
- Use the Crypto.com Exchange (not the App) API keys for Cryptohopper.

## Useful Links

- [Crypto.com Exchange](https://crypto.com/exchange)
- [Cryptohopper Official Website](https://www.cryptohopper.com)
- [Cryptohopper Crypto.com Setup Guide](https://docs.cryptohopper.com/docs/exchange-setup/crypto-com)
- [Crypto.com Exchange API Documentation](https://exchange-docs.crypto.com/)

## Frequently Asked Questions

**What is the difference between the Crypto.com App and the Crypto.com Exchange?**
The Crypto.com App is a mobile application for buying and selling crypto. The Exchange is a separate, more advanced trading platform with an order book. Cryptohopper connects to the Exchange, not the App.

**Do I need CRO tokens to trade on Crypto.com Exchange?**
No. CRO tokens are optional but staking them can reduce your trading fees on the Exchange.

**Is Crypto.com Exchange available in the US?**
Crypto.com Exchange availability varies by region. US users should check the latest availability on the Crypto.com website, as the exchange and app have different regional availability.

**Can I transfer funds between the Crypto.com App and Exchange?**
Yes. You can transfer funds between the App and Exchange through the Crypto.com ecosystem. Trading via Cryptohopper requires the funds to be on the Exchange.
