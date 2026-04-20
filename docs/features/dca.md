# Dollar-Cost Averaging (DCA) on Cryptohopper

Dollar-cost averaging is a trading strategy where you invest additional funds into a position when the price drops below your initial entry point. On Cryptohopper, DCA is a built-in feature that automates this process, helping you lower your average purchase price and potentially recover losing positions faster.

## What Is Dollar-Cost Averaging?

DCA is a risk management technique that involves buying more of an asset at lower prices to reduce your overall average cost per unit. Instead of accepting a loss when a position drops in value, DCA allows you to buy more at the reduced price, bringing down your break-even point.

Example: You buy 1 BTC at $30,000. The price drops to $27,000. Instead of waiting for the price to return to $30,000 to break even, you buy another 1 BTC at $27,000. Your average entry price is now $28,500, meaning you break even at a lower price.

## How DCA Works on Cryptohopper

When you enable DCA on Cryptohopper, the bot automatically places additional buy orders when an open position drops by a configured percentage. This is fully automated and runs 24/7 alongside your regular trading strategy.

### The DCA Process

1. Your bot opens a position based on your strategy's buy conditions.
2. The price drops below your entry point by the percentage you configured.
3. The bot automatically places an additional buy order at the lower price.
4. Your average entry price decreases.
5. If the price drops further, additional DCA orders can be placed up to your configured maximum.
6. When the price recovers to your new (lower) break-even point plus your take-profit percentage, the bot sells the entire position.

## Configuration Options

### Percentage Drop Trigger
Set the percentage the price must drop before a DCA order is placed. For example, a 5% trigger means the bot will buy more only after the price has fallen 5% below your current average entry price.

### Number of DCA Orders
Define the maximum number of additional buy orders the bot can place for a single position. Setting this to 3 means the bot can make up to 3 additional purchases on top of the original buy.

### Order Size Multiplier
Configure how much to invest with each DCA order relative to the previous order. Options include:

- **Multiplier**: Each subsequent DCA order is larger than the previous one (e.g., 2x or 3x multiplier means each DCA buy is double or triple the previous).
- **Custom amounts**: Set specific investment amounts for each DCA level.

Each DCA is triggered when the price drops X% below the current average entry price, and the order size increases using a multiplier.Example with 2x multiplier:

### DCA Table Example

| Order | Current Value | Investment | Total Invested | Avg. Entry | Current P/L After DCA | Next DCA Trigger |
|-------|---------------|------------|----------------|------------|------------------------|------------------|
| Initial buy | $1.0000 | $100 | $100 | $1.0000 | 0.00% | -5.00% ($0.9500) |
| DCA 1 | $0.9500 | $100 | $200 | $0.9744 | -2.50% | -7.50% ($0.9013) |
| DCA 2 | $0.9013 | $200 | $400 | $0.9364 | -3.75% | -8.75% ($0.8547) |
| DCA 3 | $0.8547 | $400 | $800 | $0.8937 | -4.38% | -9.38% ($0.8099) |

## Best Practices for DCA on Cryptohopper

### Start Conservative
Begin with a small number of DCA orders and moderate percentage triggers. This limits your total exposure to a single position that continues to decline.

### Mind Your Total Allocation
Each DCA order ties up additional capital. Make sure you have enough funds in your account to cover all potential DCA orders across all your open positions simultaneously. Running out of funds means the bot cannot DCA and you lose the benefit of the strategy.

### Use DCA with Stop-Loss
Combine DCA with a stop-loss to protect against extended downtrends. If a position continues to drop beyond your DCA levels, a stop-loss ensures you exit the position rather than accumulating a growing loss.

### Consider Market Conditions
DCA works best in markets that experience temporary dips followed by recoveries. In strong, sustained downtrends, DCA can lead to increased losses. Monitor overall market conditions and consider pausing DCA during periods of high uncertainty.

### Pair with Solid Entry Signals
DCA is most effective when your initial buy signal is based on sound analysis. A good entry point combined with DCA creates a strong foundation for recovering from short-term volatility.

## When to Use DCA

- **Volatile markets**: When prices frequently dip and recover, DCA helps you capitalize on temporary drops.
- **High-conviction positions**: When your analysis supports a coin's long-term potential, DCA helps you accumulate at better prices.
- **Spot trading**: DCA is primarily used for spot trading where you own the underlying asset.

## Limitations

- DCA requires available capital for each additional buy. If your funds are fully allocated, the bot cannot place DCA orders.
- In a sustained downtrend, DCA increases your total exposure to a declining asset.
- DCA does not replace a solid trading strategy. It is a tool to manage positions, not a strategy in itself.
