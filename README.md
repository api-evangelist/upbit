# Upbit

Upbit is a leading South Korean cryptocurrency exchange operated by Dunamu Inc., offering REST and WebSocket APIs for market data retrieval, order management, account balances, and transaction history. Developers must register an Upbit account with security level 2 or higher to issue API keys. Authenticated requests use JWT bearer tokens (HS512) generated from an Access Key and Secret Key pair, while public quotation endpoints require no authentication.

## APIs

- **Quotation API** — Public, unauthenticated access to real-time tickers, orderbooks, OHLCV candles (second to year intervals), recent trades, and trading pair listings. No API key required.
- **Exchange API** — Authenticated access to account balances, order placement and cancellation (including batch cancel up to 300 orders and cancel-and-replace), deposit address management, KRW and digital asset withdrawals, and travel-rule compliance verification.
- **WebSocket API** — Real-time streaming for public market events (tickers, orderbooks, candles, trades) and authenticated personal events (order fills, asset balance changes).

## Authentication

API keys are issued via the Upbit PC web interface at My Profile > Open API. Security level 2 or higher is required. JWT bearer tokens are generated using the HS512 algorithm with an Access Key and Secret Key. IP allowlisting is mandatory for API keys that include order placement or withdrawal permissions. Public quotation endpoints are accessible without any authentication.

## Regional Endpoints

| Region | Base URL |
|--------|----------|
| Korea | https://api.upbit.com |
| Singapore | https://sg-api.upbit.com |
| Indonesia | https://id-api.upbit.com |
| Thailand | https://th-api.upbit.com |

## Plans and Pricing

API access is free for all registered Upbit account holders. Public quotation endpoints are free for anyone with no account required. Trading fees are 0.05% flat for both maker and taker orders across KRW, BTC, and USDT markets. Withdrawal fees vary by digital asset and network conditions.

## Rate Limits

Rate limits are tracked via the `Remaining-Req` response header (format: `group=<name>; min=<N>; sec=<N>`). Limits are isolated per group (candles, ticker, orderbook, trades, etc.). A 429 HTTP status code is returned when limits are exceeded.

## Links

- **Website**: https://upbit.com
- **Developer Portal**: https://global-docs.upbit.com/
- **API Reference**: https://global-docs.upbit.com/reference
- **Getting Started**: https://global-docs.upbit.com/docs/first-exchange-api-call
- **Rate Limits**: https://global-docs.upbit.com/reference/rate-limits
- **GitHub**: https://github.com/upbit-exchange
- **LLMs.txt**: https://global-docs.upbit.com/llms.txt
