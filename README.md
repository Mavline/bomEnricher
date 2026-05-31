# AI Component Data Enrichment for Excel Workflows

## What this project demonstrates

This project demonstrates an AI-enabled data enrichment workflow for Excel-based component records. It reads spreadsheet data, processes part numbers and descriptions, uses an OpenRouter-compatible LLM workflow to enrich and standardize component information, and returns a cleaner spreadsheet output for operational review.

The project is useful as proof of work for data enrichment pipelines, spreadsheet automation, and AI-assisted operational data cleanup.

## Use case

A business team has spreadsheet records that are incomplete, inconsistent, or hard to use downstream. The workflow helps standardize component descriptions, attach source information, preview changes, and produce an enriched Excel file that can be reviewed before use in procurement, operations, reporting, or production-data workflows.

## Features

- Upload and process Excel workbooks.
- Read sheets and column headers from uploaded files.
- Enrich component records with AI-assisted analysis.
- Standardize descriptions into a consistent output format.
- Track processing progress through WebSocket updates.
- Preview before and after values during processing.
- Export processed Excel files.
- Run the workflow through a web server or command-line entrypoint.

## Technical stack

- Runtime: Node.js and TypeScript.
- Backend: Express.
- Spreadsheet processing: ExcelJS.
- AI/LLM: OpenAI SDK configured for OpenRouter-compatible API access.
- Realtime updates: WebSocket.
- File handling: Multer and local storage helpers.

## Architecture

The application accepts an Excel file, extracts workbook structure and selected columns, processes rows through an enrichment pipeline, streams progress and preview updates to the browser, and writes an enriched spreadsheet output. The workflow is structured so spreadsheet parsing, AI enrichment, progress reporting, and output generation can be adapted to other data-cleanup scenarios.

## How to run locally

Prerequisites:

- Node.js 18 or newer.
- pnpm.
- An OpenRouter-compatible API key for LLM enrichment.

Commands:

```bash
pnpm install
# create .env and set OPENROUTER_API_KEY
pnpm start
```

Useful scripts:

```bash
pnpm run dev
pnpm run build
pnpm run cli
pnpm run enrich
```

## Portfolio notes

This repository is a portfolio/proof-of-work project. It does not include private client data, production credentials, internal datasets, or confidential business logic.

Related acty.dev proof page: `/examples/ai-component-data-enrichment/`.
