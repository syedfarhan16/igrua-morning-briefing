# IGRUA Morning Briefing

A multi-base aviation weather and operations briefing app built for Indira Gandhi Rashtriya Uran Akademi. It brings the core briefing sequence into one projector-friendly interface and supports Fursatganj and Gondia.

**Live briefing:** [igrua-morning-briefing.vtfga.workers.dev](https://igrua-morning-briefing.vtfga.workers.dev/)

## What it does

- Collects METAR observations and marks reports that are unavailable or older than the configured limit.
- Presents satellite and radar products, plus an embedded Windy map.
- Shows local forecast and computes briefing timings from published sunset or an administrator-entered value.
- Supports keyboard-led presentation, projector view, image focus, and saved offline copies of previously loaded material.
- Provides authenticated administration for briefing settings and uploads.
- Runs as a TypeScript and React web app on Cloudflare Workers, with D1 for settings and uploaded documents.

## Run locally

Requirements: Node.js 22.13 or newer.

```sh
npm run install:ci
npm run dev
```

The local development server starts the app at the address shown in the terminal. External weather, imagery, and Windy services still need an internet connection.

## Portfolio copy and operational material

This repository contains the application source and presentation assets. It deliberately does not include the academy's Flight Order Book, diversionary charts, live account configuration, or deployment credentials. Those operational documents should be added only by an authorized administrator through the app's Admin area.

To deploy your own instance, copy `wrangler.cloudflare.example.jsonc` to `wrangler.cloudflare.jsonc`, configure your own Cloudflare account and D1 database, apply the migrations in `drizzle/`, and set the required Worker secrets in your own Cloudflare account. The account-specific config is ignored by Git. Never commit passwords, signing secrets, account credentials, or official operational documents.

This is a portfolio snapshot of a live briefing tool. The public repository does not grant permission to reuse IGRUA branding or operational information.
