# BOM Component Description Enricher

Upload an Excel workbook, choose its sheet and part-number and description columns, then enrich component descriptions through the OpenRouter-backed workflow. The app shows progress and preview rows while it processes the workbook, then provides an exported Excel result.

Live app: https://descript.replit.app/

## Run locally

Requirements: Node.js 20, pnpm, and an `OPENROUTER_API_KEY` in `.env`.

```bash
git clone https://github.com/Mavline/bomEnricher.git
cd bomEnricher
pnpm install --frozen-lockfile
pnpm start
```

Useful commands:

```bash
pnpm run dev
pnpm run build
pnpm run cli
pnpm run enrich
```

## Local storage boundary

The Node.js service uses Express for HTTP routes and WebSocket updates for progress and preview events.

The server writes processed Excel files to `storage/results`, creates `storage/temp`, and keeps selected sheets in an in-memory cache during processing. These are local runtime files and cache state: their availability and retention depend on the host's writable filesystem.
