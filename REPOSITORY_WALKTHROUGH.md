# Repository Walkthrough

This repository currently contains a minimal static web application deployment for **PharosPay**.

## Top-level structure

- `pharos pay v2/`
  - `pharospay.html` — Single-page HTML app containing all UI, styles, and client-side behavior.
  - `vercel.json` — Vercel static deployment configuration.

## What each file does

### `pharos pay v2/pharospay.html`

- Defines the full app shell in one document (`<!DOCTYPE html>` page).
- Includes:
  - Complete CSS styling in an inline `<style>` block (light theme with utility classes and component styles).
  - Frontend sections for header, wallet/connect flows, payroll and invoice interactions, transaction history, and NFT-related UI states.
- Because all UI logic is co-located in this file, any feature change currently requires editing this monolithic HTML file.

### `pharos pay v2/vercel.json`

- Deploys the project as a static site with Vercel (`@vercel/static`).
- Rewrites all routes to `pharospay.html`, effectively serving a single-page app entry point for every path.

## Current architecture notes

- **Deployment model:** static hosting.
- **Frontend model:** single-file SPA-style page.
- **Framework/tooling:** no package manifest or build system detected in this repo snapshot.
- **Implication:** easy deployment, but lower maintainability as complexity grows.

## Suggested next cleanup steps

1. Split CSS and JavaScript into separate files (e.g., `styles/` and `scripts/`).
2. Add a project README with run/deploy instructions.
3. Add linting/formatting tooling to keep the large HTML manageable.
4. Consider decomposing UI into components if active development continues.
