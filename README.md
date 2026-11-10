# ChainScan — One Token. One Clear View.

ChainScan is a minimalist token intelligence research page. Paste an Ethereum ERC-20 token contract address to view available onchain market metrics, recent news, public community posts, and clearly qualified evidence-based observations.

## What works

- Ethereum token contract search
- Token metadata and holder count (Blockscout public API)
- DEX price, 24-hour change, volume, liquidity and buy/sell trade counts (DexScreener)
- Google News RSS token-name search via a Cloudflare Worker
- Public Reddit search via a Cloudflare Worker when Reddit permits access
- Simple, clearly labeled keyword-tone summary of retrieved news and posts
- One-page responsive light UI, provider failures handled as unavailable, source links and timestamps

**Important limitations:** This is not an AI model, full social listening system, smart-contract security audit, trading recommendation, or comprehensive onchain index. X/Twitter is not integrated. Reddit may deny server requests. Token names can be ambiguous. Keyword classification is a crude heuristic and should not be treated as reliable sentiment. DEX buy/sell transaction counts are not capital flows. There is no wallet or social login yet.

## Run locally

```bash
npm install
npm run dev
npm run build
```

Local Vite development serves the frontend; the `/api/context` Worker endpoint requires Cloudflare Workers development or deployment. Use `npx wrangler dev` after a successful build for the integrated API.

## Deploy on Cloudflare Workers

- Build command: `npm run build`
- Deploy command: `npx wrangler deploy`
- Production branch: `main`
- `wrangler.jsonc` defines the Worker entrypoint and the Vite static asset binding.
- Do not add `public/_redirects`.

Public sources require no credentials. For commercial operation, review provider terms, use licensed data access where required, add caching, monitoring, abuse protection, token disambiguation, a dedicated blockchain indexer, and properly evaluated sentiment models.

**ChainScan is informational research, not financial advice.**
