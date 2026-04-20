# Automated Crypto Trading with Cryptohopper

Automated trading is the core feature of Cryptohopper. The platform runs cloud-based trading bots that monitor cryptocurrency markets, analyze price data using technical indicators, and execute buy and sell orders on your connected exchanges around the clock.

## How Automated Trading Bots Work

A trading bot is a program that follows a set of predefined rules to make trading decisions. On Cryptohopper, these rules are defined by your bot and/or trading strategy and/or signaler and/or TradingView Alert configurations. The bot continuously scans the market, checks whether your buy or sell conditions are met, and places orders on your exchange when they are.

### The Trading Cycle

1. **Market scan**: The bot scans the configured trading pairs at regular intervals, checking current price data and indicator values.
2. **Buy evaluation**: If the buy conditions in your strategy are satisfied for a particular coin, the bot places a buy order.
3. **Position monitoring**: Once a position is open, the bot monitors it against your sell conditions including; take-profit, stop-loss, trailing stop-loss, auto-close, dca and shorting settings.
4. **Sell execution**: When sell conditions are triggered, the bot places a sell order and closes the position.
5. **Repeat**: The cycle continues automatically as long as your bot is active.

## Technical Indicators

Cryptohopper supports a comprehensive library of 38 technical indicators that you can use to build your trading strategies, including but not limited to:

### Trend Indicators
- **EMA (Exponential Moving Average)** -- identifies trend direction with more weight on recent prices.
- **SMA (Simple Moving Average)** -- smooths price data to identify trend direction.
- **MACD (Moving Average Convergence Divergence)** -- measures the relationship between two moving averages to identify momentum shifts.
- **ADX (Average Directional Index)** -- measures trend strength regardless of direction.
- **Ichimoku Cloud** -- provides support/resistance levels, trend direction, and momentum in a single view.

### Momentum Indicators
- **RSI (Relative Strength Index)** -- measures the speed and magnitude of price changes to identify overbought or oversold conditions.
- **Stochastic Oscillator** -- compares a closing price to a range of prices over a given period.
- **CCI (Commodity Channel Index)** -- identifies cyclical trends and overbought/oversold levels.
- **Williams %R** -- measures overbought and oversold levels similar to the Stochastic Oscillator.

### Volatility Indicators
- **Bollinger Bands** -- measures volatility using standard deviations around a moving average.
- **ATR (Average True Range)** -- measures market volatility based on the range of price movement.

### Volume Indicators
- **OBV (On-Balance Volume)** -- uses volume flow to predict price changes.
- **Volume SMA** -- smooths volume data to identify trends in trading activity.

## Building a Strategy

### Strategy Designer
The visual strategy designer lets you combine multiple indicators and set conditions without writing code. You define:

- **Buy conditions**: Which indicators must align for the bot to buy (e.g., RSI below 30 AND MACD crossing above signal line).
- **Sell conditions**: Which indicators trigger a sell (e.g., RSI above 70 OR price hits take-profit target).
- **Logic operators**: Combine conditions using AND/OR logic for precise control. Select 'Required' if there is an indicator that must signal a buy or sell before an actual buy/sell signal will be given.

### Strategy Templates
The Cryptohopper Marketplace offers pre-built strategy templates created by experienced traders. You can apply these templates to your bot directly and modify them to suit your preferences.

## Risk Management

Automated trading on Cryptohopper includes multiple risk management tools:

- **Stop-loss**: Automatically sell a position if the price drops below a set percentage to limit losses.
- **Trailing stop-loss**: A dynamic stop-loss that moves up with the price, locking in profits while protecting against reversals.
- **Take-profit**: Automatically sell when a position reaches a target profit percentage.
- **Trailing stop-buy**: A dynamic buy trigger that follows the price down and buys when the price starts to recover.
- **Maximum open positions**: Limit how many trades can be active at the same time to control exposure.
- **Maximum open positions per currency**: Limit how much exposure the bot can have to a single coin by restricting how many positions can be opened per asset.
- **Cooldown periods**: Prevent the bot from immediately re-buying a coin after selling it.
- **Reserved balance / maximum amount allocated**: Keep part of your funds unavailable for new trades so not all capital is exposed at once.
- **Only buy when there are positive pairs**: Restrict new entries to markets showing positive momentum, reducing exposure during broad downturns.
- **Only buy if not already in position**: Avoid opening another trade in the same coin when there is already a nearby open position, helping reduce overexposure.
- **Force minimum buy amount**: Prevent the bot from placing undersized orders when available funds are too low, which helps maintain more controlled position sizing.
- **Sell based on strategy**: Allow strategy signals to close positions before other exit rules are hit, adding another layer of trade management.
- **Only sell in profit**: Prevent strategy-based sells from closing positions at a loss.
- **Auto-close**: Automatically close positions after they have been open for a set amount of time, limiting long exposure.
- **Hold assets when new target is the same**: Prevent the bot from selling a coin if the strategy immediately wants to re-enter the same asset.
- **Reset stop-loss after failed orders**: Reset protection logic after a canceled sell order so risk controls can continue functioning properly.
- **DCA (Dollar Cost Averaging)**: Add to losing positions at predefined intervals or loss percentages to improve the average entry price, though this also increases exposure and risk.
- **Shorting / automatic shorting**: Use short positions as an alternative risk-management approach after a sell, allowing the bot to track price drops and potentially buy back lower.
- **Trailing stop-short**: Dynamically track price declines after a short is opened and buy back when the price starts rising again.
- **Do not buy back on loss**: Prevent short positions from being closed at an unfavorable repurchase price.
- **Triggers**: Automatically enable or disable buying, switch templates, or respond to market conditions such as trends, crashes, or quote-currency pumps.
- **Crash protection triggers**: Use trigger rules such as percent-change conditions to disable buying when the market drops sharply.
- **Pump protection triggers**: Use triggers to reduce risk when the quote currency rises too quickly, which can make profitable trading harder.
- **Trend-based triggers**: Use indicators such as EMA crossovers to only allow buying when the broader market trend is favorable.
- **Template-switching triggers**: Automatically switch between bullish and bearish templates so the bot can adapt its risk profile to changing market conditions.
- **Config Pools**: Apply different buy, sell, and strategy settings to specific coins or groups of coins, allowing stricter risk controls for more volatile assets.
- **Base Config overrides through Config Pools**: Override the default bot settings for selected currencies, which is useful for assigning tighter stop-losses, different strategies, or different exposure rules to specific markets.

**A couple of important notes:**

Config Pools override the Base Config for the coins assigned to them.
DCA and shorting cannot be used together.
Some features manage risk by reducing losses, while others manage risk by controlling exposure, adapting to market conditions, or avoiding poor entries.

## Benefits of 24/7 Cloud-Based Trading

### Never Miss an Opportunity
Cryptocurrency markets operate 24 hours a day, 7 days a week. Significant price movements can happen at any time, including nights, weekends, and holidays. An automated bot ensures you are always participating in the market.

### Remove Emotional Trading
Fear and greed are the most common causes of poor trading decisions. An automated bot follows your strategy rules without hesitation, avoiding impulsive buys during FOMO rallies or panic sells during dips.

### Trade Across Multiple Exchanges
Run bots on multiple exchanges simultaneously, diversifying your trading across different platforms and markets from a single Cryptohopper dashboard.

### Scale Your Trading
Manually monitoring dozens of trading pairs across multiple exchanges is impractical. An automated bot can scan hundreds of pairs every few minutes, identifying opportunities that a human trader would miss.

### No Infrastructure to Manage
Because Cryptohopper runs in the cloud, you do not need to set up or maintain a VPS, install software, or worry about uptime. The platform handles all infrastructure, letting you focus on your strategy.
