# Privacy Policy

Last updated: April 18, 2026

## Overview

This Privacy Policy describes how the Steamolio Chrome extension handles data.

Steamolio is a Chrome extension for tracking a personal CS2 item portfolio. Portfolio data is stored locally in the browser. The extension can also make direct requests to third-party services for item price refresh and load external item preview images from catalog-derived URLs.

## Data Stored Locally

The extension stores the following data locally in browser storage:

- portfolio data
- purchase history
- current prices
- portfolio snapshots and snapshot history
- settings
- CSFloat API key, if the user provides one
- refresh status and refresh debug metadata

Saved refresh debug data is sanitized before persistence. Raw response text, raw response headers, and parsed response JSON are not persisted in debug storage.

## Data Sent To Third Parties

### Steam

When the user manually refreshes prices from Steam, the extension sends direct requests to `steamcommunity.com`, including item pricing identifiers such as the stored `market_hash_name` and request parameters required by Steam's `priceoverview` endpoint.

Portfolio data such as purchase history, buy prices, quantities, notes, and snapshots are not sent to Steam as part of price refresh.

### CSFloat

CSFloat integration is optional.

If the user adds a CSFloat API key, the extension sends direct requests to `csfloat.com` for:

- price lookups
- API key validation

Those requests use the user's CSFloat API key in the request headers and send item pricing identifiers such as `market_hash_name` and, when applicable, `paint_index`.

The CSFloat API key is stored locally and is sent to CSFloat only for price requests and API key validation.

Portfolio data such as purchase history, buy prices, quantities, notes, and snapshots is not included in CSFloat API requests.

### External Item Images

The extension UI may load item preview images from catalog-derived external image URLs. When those images are requested, the relevant image host may receive standard web request information such as the user's IP address, user agent, and request metadata.

## No Developer Backend Or Analytics

- The extension does not use a developer-operated backend for portfolio sync, data collection, or price relay.
- The extension does not use analytics or telemetry SDKs.
- The extension does not use a crash-reporting service.

The extension does not transmit portfolio data to a developer-operated server.

## Backups

Steamolio can export and import backup files in JSON format.

Backup files may contain:

- portfolio data
- purchase history
- current prices
- snapshots/history
- settings

Backup files can also include the CSFloat API key, but only if the user explicitly enables that option before export.

If a backup file includes the CSFloat API key and the user later imports that backup, the key can be restored into local extension storage.

## No Automatic Data Collection

The extension does not collect data in the background.
All external requests are triggered by user actions such as manual price refresh.

## User Controls

The extension provides controls to:

- add, edit, and delete portfolio transactions
- remove portfolio items
- import or export backup files
- reset local portfolio state
- reset local portfolio state together with the stored CSFloat API key
- remove or replace the stored CSFloat API key

## Scope And Limitations

This policy describes the current behavior of the extension.

If the extension functionality changes in future versions, this policy may be updated accordingly.
