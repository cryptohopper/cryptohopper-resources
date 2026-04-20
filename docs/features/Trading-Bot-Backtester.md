# Trading Bot Backtester on Cryptohopper

The Trading Bot Backtester on Cryptohopper allows you to test almost all of your bot or template settings on historical market data. It is designed to help you understand how your bot configuration would have behaved in the past and how changes to your settings may affect your results.

## What Is the Trading Bot Backtester?

The Trading Bot Backtester is a tool that lets you backtest your bot or template settings against historical market data.

You can use it to test almost all of your bot settings, including your buying and selling configuration, and review how the bot would have performed over a chosen period.

The Backtester does not support Triggers or TradingView Alerts.

## Why Use the Trading Bot Backtester?

Using the Backtester can help you optimize your trading results. Even small changes to your bot or template settings can have a significant effect on performance.

It is a practical way to compare configurations and understand how your settings work together before applying them in live trading.

### Important Limitations

Past performance does not guarantee future results.

Backtests are also not a complete representation of how your bot behaved in the past. For example:

bots check sell settings more often,
the Backtester checks prices and other settings every minute,
the checking moments of your strategy can differ slightly from live bot behavior.

Because of this, Backtest results should be used as guidance, not as a guarantee of future or live performance.

## Backtest Limits per Subscription

How often you can test your bots and templates depends on your subscription.

You can only test one bot or template at a time. If you start more tests, they will wait in line.

If you have multiple subscriptions, the number of Backtests you can do each day increases accordingly.

Backtest limits per subscription:

- Explorer: 1 Backtest per day
- Adventurer: 5 Backtests per day
- Hero: 10 Backtests per day

## What You Can Backtest

The Trading Bot Backtester can test nearly all of your template and bot settings.

This includes the interaction between buying, selling, position management, and asset allocation settings.

The following features are not included:

- Triggers
- TradingView Alerts

### Explanation of the Backtester Tabs

The following tabs provide different ways to review your Backtest results.

**Overview**

The Overview chart displays the total value of your assets during the Backtested period.

Below the chart, you can find information such as:

- The most traded currencies,
- The average profit per currency,
- The average holding times of your currencies.

The Overview also shows detailed information about your buy and sell activity, including:

- Total number of trades,
- Start balance,
- End balance,
- Profit or loss.
- Trades

The Trades tab shows all trades from your Backtest.

This section includes information such as:

- Currency,
- Market,
- Buy or sell action,
- Date,
- Amount,
- Price,
- Costs,
- Fee,
- Profit,
- Buy or sell trigger.

You can also view the Technical Analysis values at the moment of buying or selling.

Trades based on signals or Marketplace strategies with hidden configurations will not display these values.

You can also use the search feature to sort your trades based on any value shown in the table.

**Orders**

The Orders tab shows open orders that still exist while the Backtest is running or after it has completed.

**Positions**

The Positions tab shows open positions that still exist while the Backtest is running or after it has completed.

**Shorts**

The Shorts tab shows open shorts that remain open during or after a Backtest.

If you enable Use actual profit, the bot will display and use real profits for calculating the shorting percentage profit and the Trailing Stop-Short. This means that the percentage profit of the short is calculated in relation to the buying price, instead of the amount saved through shorting.

Keep in mind that shorting in the Backtester may still behave differently than expected.

**Assets**

The Assets tab shows which assets you still own during or after a Backtest.

Balance shows the value of the assets in the currency you are trading.
Reserved assets shows the assets that are still tied up in open orders.

Your quote currency balance can help you understand how much of your funds are being used for trading.

If you want to increase the amount of your quote currency being used, you can adjust your buy amounts in the Base Config and run a new Backtest.

**Notes**

The Notes tab allows you to leave notes about your Backtest.

This can help you track changes between tests and document why you adjusted a certain setting.

**Log**

The Log tab works similarly to the Bot Output on your Dashboard.

Here you can review everything the Backtest has done.

The Backtest checks your strategy at regular intervals of 2, 5, or 10 minutes, depending on the frequency selected when starting the Backtest. Prices and other settings are checked every minute.

A maximum of 500 logs is displayed. If you want to view more, adjust your date range.

## What to Consider

There are a few important points to keep in mind when using the Backtester:

- When you start a Backtest at a certain time, you receive a new available Backtest 24 hours later for that specific test slot.
- This applies separately to each Backtest when your subscription allows more than one per day.
- When Backtesting very illiquid trading pairs with low volume, profits and losses can become extreme because the Backtester does not take actual exchange liquidity and order book activity into account.
- Best Practices for Using the Backtester

To get the most value from the Trading Bot Backtester, it is recommended to:

- Test one change at a time,
- Compare different market periods,
- Review the Trades, Assets, and Log tabs together,
- Avoid drawing conclusions from only one successful Backtest,
- Use Backtesting together with Paper Trading before going live.

## When to Use the Trading Bot Backtester

The Trading Bot Backtester is especially useful in the following situations:

- Before applying a new template to a live bot
- When adjusting buy and sell settings in the Base Config
- When comparing different bot configurations
- When reviewing how your bot would have behaved over a specific historical period
- When optimizing position sizing, selling behavior, or asset usage