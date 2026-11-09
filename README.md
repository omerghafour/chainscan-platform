# ChainScan — Blockchain Intelligence, Simplified

ChainScan is a responsive Ethereum wallet explorer MVP using React, TypeScript and Vite.

Features: landing page, overview dashboard, live ETH wallet balance and recent transactions via Blockscout, source links, loading/error states, and roadmap screens for social intelligence and alerts.

## Run

```bash
npm install
npm run dev
```

## Cloudflare Pages

Connect the repository in Cloudflare Workers & Pages. Choose framework **Vite**, build command `npm run build`, output directory `dist`. The `public/_redirects` file supports SPA deep links.

Data endpoint: `https://eth.blockscout.com/api/v2/addresses/:address` and `/transactions`. Public service may rate limit. Never place API secrets in Vite client environment variables.

Social intelligence, authentication, AI summaries, multi-chain support and alert automation are **planned, not implemented**. This early version is not a fully indexed portfolio explorer or financial advice.
