# Strategy Backtesting on Cryptohopper

Strategy Backtesting on Cryptohopper allows you to test a strategy on historical market data for a single currency. It helps you understand how your strategy and core sell settings would have behaved in the past before using them in live trading.

## What Is Strategy Backtesting?

Strategy Backtesting is the process of applying a trading strategy to historical price data to simulate how it would have performed over a specific period.

It focuses on your strategy and core exit settings, such as Take Profit and Stop-Loss, and shows how trades would have been opened and closed based on those conditions.

This allows you to evaluate whether your strategy behaves as expected under past market conditions.

### Prerequisites

Before you begin, check the following:

- You have a Cryptohopper account
- You have an Explorer, Adventurer, or Hero subscription
- How to Set Up a Strategy Backtest

Follow these steps to start a Strategy Backtest:

1. Log in to your Cryptohopper account
2. Go to the bot you want to use for a Backtest
3. Click Backtesting
4. Fill in the required fields
5. Click Start Backtest
6. Strategy Backtest Settings

**Currency**

Select the currency you want to Backtest.

**Strategy**

Select the Strategy you want to Backtest.

**Sell based on Strategy**

Enable this setting if you want your position to be sold when your Strategy signals a sell.

**Take Profit**

Fill in the percentage profit you want to make on a position before selling. When the price rises above this percentage, a sell order will be simulated.

**Stop-Loss**

Enable this setting if you want your bot to use a Stop-Loss.

**Stop-Loss percentage**

Fill in the percentage your position needs to drop before the Stop-Loss is triggered. Enter a positive number. For example, if you want to sell when the price drops 2.5%, fill in 2.5%.

**Trailing Stop-Loss**

Enable this setting if you want to use a Trailing Stop-Loss.

**Trailing Stop-Loss percentage**

Fill in the percentage the price is allowed to drop after the Trailing Stop-Loss has been armed. When this percentage is reached, the position will be sold.

**Arm Trailing Stop-Loss**

Fill in the percentage of profit required before the Trailing Stop-Loss is activated. For example, if you fill in 1%, the Trailing Stop-Loss will only start tracking after the position reaches 1% profit.

**Use Trailing Stop-Loss only**

Enable this setting if you want to disable Take Profit and only use the Trailing Stop-Loss to exit positions.

**Trailing Stop-Buy**

Enable this setting if you want to use Trailing Stop-Buy in the Backtest.

**Trailing Stop-Buy percentage**

Fill in the percentage the price should rise before a buy is triggered after a downward movement.

**Select period**

Enable this setting if you want to define a specific Backtest period. When enabled, select the desired date range.

## How Strategy Backtesting Works

After starting the Backtest, Cryptohopper simulates how your selected strategy would behave using historical data for the chosen currency.

**The Backtester evaluates:**

- when buy signals occur based on your strategy
- how positions would be closed based on your sell settings

This results in a simplified simulation of how your strategy performs over time.

### Important Information

The Strategy Backtester checks your indicator values at a fixed interval of approximately every 5 minutes.

Because of this:

- not every candle is evaluated, especially on smaller timeframes
- some signals may be skipped
- results may differ from live bot behavior

### Limitations of Strategy Backtesting

Strategy Backtesting is useful, but it has some limitations:

- Fixed Checking Interval
- Indicators are evaluated every 5 minutes, regardless of your subscription. This can lead to differences compared to live trading.
- Candle Skipping
- When using small candle sizes, some candles may not be evaluated, which can affect results.

### Simplified Execution

Backtesting assumes trades are executed based on available historical data, without accounting for real-world factors such as:

- slippage
- order book depth
- execution delays
- Historical Data Only

Strategy Backtesting is based entirely on past market data. Market conditions can change, and past performance does not guarantee future results.

## Best Practices for Strategy Backtesting
- Test Multiple Time Periods
- Test your strategy across different market conditions, such as: bullish markets, bearish markets, sideways markets
- Keep Your Strategy Simple
- Avoid overcomplicating your strategy with too many indicators or highly specific settings.
- Use Realistic Settings
- Configure your Backtest with settings you would actually use in live trading.
- Validate with Paper Trading

After Backtesting, use a Paper Trading bot to test your strategy in real-time conditions without risking funds.

## When to Use Strategy Backtesting

Strategy Backtesting is especially useful in the following situations:

- Before using a new strategy
- When adjusting Take Profit, Stop-Loss, or Trailing Stop settings
- When comparing different strategies
- When testing how a strategy behaves over a specific historical period
