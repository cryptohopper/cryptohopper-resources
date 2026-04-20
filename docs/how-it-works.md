# How Cryptohopper Works: From Sign-Up to Automated Trading

Cryptohopper automates cryptocurrency trading by connecting to your exchange accounts through secure API keys and executing trades based on the strategies you configure. This guide walks through how the platform works, from creating your account to running a fully automated trading bot.

## Step 1: Create Your Account

Sign up for a free account at [cryptohopper.com](https://www.cryptohopper.com). No credit card is required to get started. Cryptohopper offers a free tier that lets you explore the platform, set up paper trading, and familiarize yourself with the interface before committing to a paid plan.

## Step 2: Connect Your Exchange via API Keys

Cryptohopper supports more than 15 major cryptocurrency exchanges. To connect an exchange:

1. Log in to your exchange account (e.g., Binance, Coinbase Advanced, Kraken).
2. Navigate to the API management section of your exchange.
3. Create a new API key with **trade permissions only**. Do not enable withdrawal permissions.
4. Copy the API key and secret into Cryptohopper's exchange connection settings.

Cryptohopper encrypts and stores your API keys securely. Because withdrawal permissions are not required, the platform can only place trades on your behalf and never move funds out of your exchange account.

## Step 3: Configure Your Trading Strategy

This is where you define how your bot should trade. Cryptohopper provides several approaches:

### Technical Indicators
Build strategies using popular technical indicators such as RSI, MACD, Bollinger Bands, EMA, Stochastic, and dozens more. Combine multiple indicators to create buy and sell conditions that match your trading style.

### Strategy Designer
Use the visual strategy designer to build custom strategies without writing code. Drag and drop indicators, set conditions, and define the logic your bot will follow.

### Pre-Built Templates
Choose from a library of strategy templates available on the Cryptohopper Marketplace. These templates are created by experienced traders and can be applied to your bot immediately.

### External Signals
Subscribe to signal providers who send buy and sell recommendations based on their own analysis. Signals are delivered directly to your bot and can trigger trades automatically.

### Webhooks
Integrate external tools like TradingView by sending webhook signals to Cryptohopper. When your TradingView alert fires, it sends a signal to Cryptohopper, which then executes the trade.

## Step 4: Configure Trading Parameters

Beyond strategy logic, you configure parameters that control how your bot operates:

- **Base currency** -- the currency your bot uses to buy assets (e.g., USDT, BTC, EUR).
- **Allowed coins** -- which trading pairs your bot can trade.
- **Position size** -- how much to invest per trade.
- **Maximum open positions** -- how many trades can be open simultaneously.
- **Stop-loss and take-profit** -- risk management settings for each position.
- **Trailing stop-loss and trailing stop-buy** -- dynamic exit and entry points.
- **Dollar-cost averaging (DCA)** -- automatically buy more when a position drops in value.
- **Cooldown periods** -- prevent the bot from re-buying a coin too quickly after selling.

## Step 5: Your Bot Trades 24/7

Once configured and activated, your Cryptohopper bot runs continuously in the cloud. It monitors the markets, evaluates your strategy conditions, and executes trades when criteria are met.

### What Happens During a Trade Cycle

1. **Scan**: The bot scans the market for coins that match your buy conditions.
2. **Buy**: When conditions are met, the bot places a buy order on your connected exchange.
3. **Monitor**: The bot monitors the open position, checking for sell conditions.
4. **Sell**: When sell conditions are met (take-profit, stop-loss, indicator signal), the bot places a sell order.
5. **Repeat**: The cycle continues as long as your bot is active.

## Cloud-Based Architecture: No VPS Needed

Unlike many trading bots that require a local installation or a virtual private server (VPS), Cryptohopper runs entirely in the cloud. This means:

- **No downloads or installations** -- access Cryptohopper from any web browser.
- **No VPS costs** -- your bot runs on Cryptohopper's infrastructure.
- **No uptime concerns** -- the platform handles server maintenance, updates, and reliability.
- **Access from anywhere** -- manage your bot from desktop or mobile.

Your bot keeps trading even if your computer is off, your internet connection drops, or you are away from your device.

## Paper Trading: Practice Without Risk

Cryptohopper includes a paper trading mode that simulates real trades using virtual funds. Paper trading lets you:

- Test strategies before using real money.
- Learn how the platform works without financial risk.
- Evaluate the performance of signal providers or templates.

Paper trading uses real market data, so results closely reflect how your strategy would perform in live conditions.

## Monitoring and Adjusting Your Bot

Cryptohopper provides a dashboard where you can:

- View all open and closed positions.
- Track profit and loss over time.
- Review trade history and performance metrics.
- Adjust strategy settings and trading parameters in real time.
- Receive notifications about trades and bot activity.

You can pause, restart, or reconfigure your bot at any time without losing your existing positions or settings.
