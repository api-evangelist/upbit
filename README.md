# Upbit

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
