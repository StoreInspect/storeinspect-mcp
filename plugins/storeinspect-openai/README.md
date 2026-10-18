# StoreInspect workflows for ChatGPT and Codex

This package updates the existing StoreInspect plugin with three guided workflows: find Shopify prospects, research a known store’s technology, and enrich domain lists with relevant contact previews. It preserves the listing identity, OAuth MCP connection, reviewer cases, and assets from release 1.0.1.

## Use

Connect the published StoreInspect plugin through OAuth, then ask:

- Find 10 UK fashion stores with no detected Klaviyo. Keep contacts masked.
- Research gymshark.com: show its detected apps, pixels, theme, and estimated tiers.
- Enrich allbirds.com and tentree.com and preview one founder per store. Do not spend credits.

The packaged skills are `find-shopify-prospects`, `research-shopify-store`, and `enrich-shopify-prospects`. They select valid filters from taxonomy, respect current quotas, keep unknown results visible, and require explicit approval before revealing a selected set of contacts.

## Connection and data

The remote server is `https://mcp.storeinspect.com/openai`. The seven data tools use the connected user’s StoreInspect access and current quotas. Contact previews stay masked; approved reveals use normal plan credits. The package has no scripts, hooks, local executables, app references, embedded credentials, or billing tools.

StoreInspect receives only the domains, filters, cursors, and contact IDs passed to its tools. Approved revealed details are visible in the conversation. Account, product, reveal, credit, and privacy-safe request records are retained under the StoreInspect privacy policy; some records remain longer than 30 days.

The data comes from StoreInspect’s index rather than a live scan. Missing app detection is not proof of absence. Traffic and revenue tiers are estimates, and exact advertising spend is unavailable. The workflows do not send outreach or sync a CRM.

[Website](https://storeinspect.com) · [Documentation](https://storeinspect.com/docs/mcp/overview) · [Support](https://storeinspect.com/docs/help/overview) · [Privacy](https://storeinspect.com/privacy) · [Terms](https://storeinspect.com/terms)

## Upload

Upload this complete ZIP to the existing StoreInspect plugin after its active package review finishes. Do not create a second listing or cancel the current review to upload it. Check the new skill findings and complete review requirements before submitting or publishing.

MIT; see LICENSE.
