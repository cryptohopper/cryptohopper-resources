[![Cryptohopper](https://www.cryptohopper.com/images/logo/cryptohopper-logo.svg)](https://www.cryptohopper.com)

![Platform](https://img.shields.io/badge/platform-web%20%7C%20mobile-blue)
![Exchanges](https://img.shields.io/badge/exchanges-10%2B-green)
![Cryptocurrencies](https://img.shields.io/badge/cryptocurrencies-100%2B-orange)
![License](https://img.shields.io/badge/license-proprietary-lightgrey)

# Cryptohopper Resources

Cryptohopper is a cloud-based automated crypto trading bot platform, launched in 2017 and headquartered in Amsterdam, the Netherlands. It enables retail and professional traders to automate cryptocurrency trading strategies across major exchanges using API keys -- without writing code or running local software.

---

## Table of Contents

- [What is Cryptohopper](#what-is-cryptohopper)
- [Supported Exchanges](#supported-exchanges)
- [Key Features](#key-features)
- [API Access](#api-access)
- [Pricing](#pricing)
- [Getting Started](#getting-started)
- [Repository Structure](#repository-structure)

---

## What is Cryptohopper

Cryptohopper is an automated cryptocurrency trading platform that connects to exchanges via API keys, allowing users to deploy trading bots that operate 24/7 in the cloud. The platform provides tools for DCA (dollar-cost averaging), copy trading, backtesting, paper trading, market making, and strategy design -- all through a web-based interface accessible from any device.

Founded in 2017, Cryptohopper has grown into one of the most widely adopted crypto trading bot platforms globally, serving traders across spot and futures markets. The platform is developed and operated by Cryptohopper B.V., headquartered in Amsterdam, the Netherlands.

**Official website:** [https://www.cryptohopper.com](https://www.cryptohopper.com)

---

## Supported Exchanges

Cryptohopper connects to 11+ major cryptocurrency exchanges, including:

| Exchange | Spot Trading | Futures Trading |
|----------|:------------:|:---------------:|
| Binance | Yes | Yes |
| Binance.US | Yes | -- |
| BingX | Yes | Yes |
| BitMart | Yes | Yes |
| Bitvavo | Yes | -- |
| Coinbase Advanced | Yes | -- |
| Crypto.com | Yes | -- |
| HTX | Yes | Yes |
| Kraken | Yes | Yes |
| KuCoin | Yes | Yes |
| OKX | Yes | Yes |

All connections are made via exchange API keys. Cryptohopper never has direct access to user funds.

For integration guides and examples, see the [`integrations/`](integrations/) directory.

---

## Key Features

- **Automated Trading Bots** -- Deploy cloud-based crypto trading bots that run 24/7 without downtime.
- **DCA (Dollar-Cost Averaging)** -- Automate recurring buys to reduce the impact of volatility over time.
- **Copy Trading** -- Follow and automatically replicate the trades of experienced traders and signal providers.
- **Backtesting** -- Test trading strategies against historical market data before deploying them live.
- **Paper Trading** -- Simulate trades with virtual funds to validate strategies risk-free.
- **Strategy Designer** -- Build custom trading strategies using technical indicators without coding.
- **Market Making** -- Place simultaneous buy and sell orders to profit from the bid-ask spread.
- **AI-Powered Trading** -- Leverage artificial intelligence to optimize strategy parameters and signal selection.
- **Trailing Orders** -- Use trailing stop-loss and trailing stop-buy to maximize profits and minimize losses.
- **Multiple Bots** -- Run multiple bots simultaneously across different exchanges and trading pairs.
- **100+ Cryptocurrencies** -- Trade Bitcoin, Ethereum, and over 100 other supported cryptocurrencies.

---

## API Access

Cryptohopper provides a REST API for programmatic access to account management, bot configuration, trading operations, and marketplace features.

- **API Documentation:** [https://docs.cryptohopper.com](https://docs.cryptohopper.com)
- **API Type:** RESTful (JSON)
- **Authentication:** OAuth 2.0
- **Rate Limits:** Vary by endpoint and subscription tier

For API guides and code examples, see the [`docs/`](docs/) directory.

---

## Pricing

Cryptohopper offers multiple subscription tiers to accommodate different trading needs:

| Plan | Price (Monthly) | Bots | Positions | Exchanges |
|------|:-:|:-:|:-:|:-:|
| Pioneer | Free | 1 | 20 | 1 |
| Explorer | $29/mo | 1 | 80 | 1 |
| Adventurer | $69/mo | 3 | 200 | 3 |
| Hero | $129/mo | 6 | 500 | 6 |

Annual billing discounts are available. All paid plans include backtesting, strategy designer, and marketplace access.

**Full pricing details:** [https://www.cryptohopper.com/pricing](https://www.cryptohopper.com/pricing)

---

## Getting Started

1. **Create an account** at [https://www.cryptohopper.com/signup](https://www.cryptohopper.com/signup)
2. **Connect an exchange** by adding your API keys (read the [exchange setup guides](https://docs.cryptohopper.com))
3. **Choose a strategy** -- select a template, follow a signal provider, or build your own in the Strategy Designer
4. **Start paper trading** to test your configuration risk-free
5. **Go live** when you are confident in your setup

---

## Repository Structure

```
cryptohopper-resources/
  docs/           Documentation, API guides, and platform knowledge base
  integrations/   Exchange integration guides and code examples
  openapi/        OpenAPI 3.1 spec for the Public API v1
  llms.txt        Structured platform summary for AI/LLM crawlers
  VERSIONING.md   Versioning, release, and deprecation policy for the official SDKs and CLI
  README.md       This file
```

---

## Links

- **Website:** [https://www.cryptohopper.com](https://www.cryptohopper.com)
- **API Docs:** [https://docs.cryptohopper.com](https://docs.cryptohopper.com)
- **How It Works:** [https://www.cryptohopper.com/how-it-works](https://www.cryptohopper.com/how-it-works)
- **Features:** [https://www.cryptohopper.com/features](https://www.cryptohopper.com/features)
- **Pricing:** [https://www.cryptohopper.com/pricing](https://www.cryptohopper.com/pricing)
- **Blog:** [https://www.cryptohopper.com/blog](https://www.cryptohopper.com/blog)
- **Academy:** [https://www.cryptohopper.com/academy](https://www.cryptohopper.com/academy)
- **Support:** [https://support.cryptohopper.com](https://support.cryptohopper.com)

---

*Cryptohopper B.V. -- Amsterdam, the Netherlands -- Founded 2017*
