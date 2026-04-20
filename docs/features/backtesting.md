# Backtesting Trading Strategies on Cryptohopper

Backtesting is a feature on Cryptohopper that lets you test your trading strategies against historical market data. Before risking real capital, you can evaluate how a strategy would have performed in past market conditions, helping you refine your approach and build confidence in your configuration.

## What Is Backtesting?

Backtesting is the process of applying a trading strategy to historical price data to simulate how it would have performed over a specific time period. It shows you the theoretical trades your bot would have made, including entries, exits, profit, loss, and overall return.

## How Backtesting Works on Cryptohopper

### Step 1: Select Your Strategy
Choose the strategy you want to test. This can be a strategy you built using the strategy designer, a template from the marketplace, or any combination of technical indicators and conditions.

### Step 2: Choose Your Parameters
Configure the backtest settings:

- **Trading pair**: Select which coin or coins to test against (e.g., BTC/USDT, ETH/USDT).
- **Time period**: Define the historical date range for the test.
- **Position size**: Set the amount invested per trade.
- **Take-profit and stop-loss**: Include your risk management settings.
- **DCA settings**: Optionally include dollar-cost averaging parameters.

### Step 3: Run the Backtest
Cryptohopper processes your strategy against the historical data and generates a detailed report.

### Step 4: Review Results
The backtest report includes:

- **Total return**: The overall profit or loss of the strategy over the test period.
- **Number of trades**: How many buy/sell cycles were executed.
- **Win rate**: The percentage of trades that were profitable.
- **Average profit per trade**: The mean return across all trades.
- **Maximum drawdown**: The largest peak-to-trough decline during the test period.
- **Trade history**: A detailed log of every simulated trade with entry/exit prices and timestamps.

## Best Practices for Backtesting

### Test Across Multiple Time Periods
Do not rely on a single backtest period. Test your strategy across different market conditions -- bull markets, bear markets, and sideways periods. A strategy that works well in one market environment may underperform in another.

### Avoid Overfitting
Overfitting occurs when a strategy is tuned too precisely to historical data, capturing noise rather than genuine patterns. Signs of overfitting include:

- A strategy that performs exceptionally well on one specific date range but poorly on others.
- Strategies with many highly specific indicator settings.
- Results that seem too good to be true.

To avoid overfitting, keep your strategy relatively simple and test it across multiple time periods and trading pairs.

### Use Realistic Settings
Configure your backtest with the same parameters you plan to use in live trading, including realistic position sizes, fees, and risk management settings. Unrealistic settings produce misleading results.

### Account for Trading Fees
Make sure your backtest accounts for exchange trading fees. A strategy that appears profitable before fees may break even or lose money after fees are applied.

### Compare Against Buy and Hold
A useful benchmark is comparing your strategy's return against a simple buy-and-hold approach for the same asset over the same period. If your strategy does not outperform buy and hold, consider whether the added complexity is worthwhile.

### Forward Test with Paper Trading
After backtesting, run your strategy in paper trading mode with real-time market data. This validates your backtest results in live conditions without risking capital.

## Limitations of Backtesting

### Historical Performance Does Not Guarantee Future Results
Markets are dynamic. Conditions change, and a strategy that performed well historically may not perform the same way in the future.

### Simulated Execution
Backtesting assumes orders are filled at the exact prices shown in historical data. In live trading, factors like slippage, order book depth, and execution speed can affect actual fill prices.

### Data Granularity
The accuracy of a backtest depends on the granularity of the historical data. Short-timeframe strategies may require more detailed data than what is available.

### No Account for Black Swan Events
Backtesting cannot predict or account for unprecedented market events, exchange outages, or sudden regulatory changes that may impact real trading.

## When to Use Backtesting

- **Before deploying a new strategy**: Always backtest before committing real funds.
- **When modifying an existing strategy**: Test changes to see their impact before applying them to your live bot.
- **When evaluating marketplace templates**: Backtest purchased strategy templates to verify their performance in your target market.
- **When comparing strategies**: Run multiple backtests side by side to determine which approach performs best.
