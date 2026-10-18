# StoreInspect Workflows

Research Shopify prospects in Claude using StoreInspect's store index, technology detections, and contact previews. This plugin bundles three workflows and connects to StoreInspect through OAuth. It works with the same remote connector as StoreInspect's Claude integration.

## Workflows

| Workflow | What you get |
| --- | --- |
| Find Shopify prospects | A focused list of stores with the evidence behind each match. |
| Research a Shopify store | Detected apps, pixels, theme, estimated traffic and revenue tiers, and gaps in the available data. |
| Enrich Shopify prospects | Store data for a supplied domain list, with masked contact previews when requested. |

Try these prompts:

- Find 10 UK fashion stores with no detected Klaviyo. Show why they match; keep contacts masked.
- Research gymshark.com using StoreInspect. Which apps and pixels are detected, and what is unknown?
- Enrich allbirds.com and tentree.com, then preview one relevant decision-maker per store. Do not reveal contact details.

Claude can select the matching workflow from your request. You can also invoke `/storeinspect-workflows:find-shopify-prospects`, `/storeinspect-workflows:research-shopify-store`, or `/storeinspect-workflows:enrich-shopify-prospects`.

## Connect

Install the plugin, connect **StoreInspect**, and sign in to your StoreInspect account when prompted. The MCP endpoint is `https://mcp.storeinspect.com/claude`. If you already connected that endpoint, reuse the connection rather than adding another copy. Never paste an API key into the conversation or bundle.

Free accounts can use the Claude connector's search preview. Contact reveals use your StoreInspect plan's contact credits. The workflows check your current usage and respect the limits returned by the service; they do not start a subscription or manage billing.

For a local Claude Code check:

```sh
claude --plugin-dir ./plugins/storeinspect-workflows
```

For a private chat or Cowork test, upload a ZIP containing this plugin folder through **Customize → Plugins → Add → Upload plugin**. Installing privately does not publish a directory listing.

## Data and actions

StoreInspect receives the domains, search filters, pagination cursors, and selected contact IDs passed to its MCP tools under the connected account. Contact details returned by an approved reveal are visible to Claude in that conversation. The plugin contains instructions and a remote MCP configuration; it has no local scripts, hooks, bundled credentials, or independent analytics.

StoreInspect retains account and product records while the account is active, including reveal and credit records and privacy-safe request logs. Some security, billing, backup, and audit records can be retained longer. The retention disclosure for this service is therefore longer than 30 days; see the privacy policy for details.

Contacts stay masked by default. Before a reveal, Claude must identify the selected contacts and potential credit spend and obtain explicit approval for that set. A request to find contacts or export a prospect list is not approval to reveal them. The workflows do not send outreach, sync a CRM, or make billing changes.

StoreInspect searches its existing index. A request does not trigger a live scan. Missing app detection does not prove an app is absent, and traffic and revenue tiers are estimates. Unknown stores and unavailable fields remain marked as unknown.

Read the [tool reference](https://storeinspect.com/docs/mcp/tools), [privacy policy](https://storeinspect.com/privacy), and [terms](https://storeinspect.com/terms). For account or data questions, email support@storeinspect.com. Use [GitHub issues](https://github.com/StoreInspect/storeinspect-mcp/issues) for non-sensitive plugin problems.

## Verification

Run `claude plugin validate ./plugins/storeinspect-workflows --strict`. The repository’s `quality/storeinspect-workflows/` folder contains synthetic fixtures for workflow and credit-confirmation checks. From the repository root, run `claude plugin eval . --eval-dir quality/storeinspect-workflows --mocks record --no-publish`; do not enable real servers for fixture tests.

## License

MIT. See [LICENSE](LICENSE).
