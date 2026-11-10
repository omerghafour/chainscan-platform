# ChainScan — Blockchain Intelligence, Simplified

A responsive Ethereum blockchain intelligence MVP built with React, TypeScript, Vite, and Cloudflare Workers static assets.

## Current features

- Public landing page and dashboard
- Ethereum wallet explorer: live ETH balance and recent transactions via Blockscout
- **Token intelligence (V2):** search an Ethereum ERC-20 contract address, view token metadata from Blockscout and DEX market metrics from DexScreener
- Primary pool chosen by reported USD liquidity; 24h price change, volume, liquidity, buy/sell transaction counts and source-linked interpretation
- Transparent limits: buy/sell **transaction counts are not capital flows**; no trading recommendation is generated
- Responsive desktop/mobile layout, error and loading states

## Local development

```bash
npm install
npm run dev
npm run build
```

## Deploy on Cloudflare Workers

The included `wrangler.jsonc` config serves the Vite `dist` directory with SPA fallback. Connect this GitHub repository in Cloudflare Workers Builds:

- Build command: `npm run build`
- Deploy command: `npx wrangler deploy`
- Production branch: `main`

Do not add `public/_redirects`; the Workers SPA fallback already handles client-side routes.

## Data sources

- Blockscout Ethereum API: `https://eth.blockscout.com/api/v2/` (wallets and token metadata)
- DexScreener API: `https://api.dexscreener.com/token-pairs/v1/ethereum/{contract}` (market pools)

The frontend accesses public endpoints without credentials. Availability, rate limits, provider coverage and CORS behavior may change. For a commercial production release, add a Cloudflare Worker API proxy, caching, monitoring, provider fallback and explicit data licensing review.

## Roadmap (not yet implemented)

Verified social/news sentiment, contract security analysis, onchain holder flow, AI investigation reports with citations, historical data and alerts. **Offchain sentiment, AI, and security checks are not yet live.**

**Disclaimer:** ChainScan provides informational market research, not financial advice. DEX buy/sell counts do not measure investor intent or net flow. Always verify independently.
