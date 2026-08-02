<!-- mcp-name: com.storeinspect/mcp -->

# StoreInspect MCP

StoreInspect MCP gives AI clients access to StoreInspect's Shopify store and contact data through OAuth.

Search stores by market, traffic, revenue, apps, pixels, themes, ads, or contact availability. You can also enrich known domains, preview matching contacts, and reveal selected contact details after approval.

StoreInspect runs the MCP server. This repository contains public metadata, setup examples, and prompts. The server source is private, and there is nothing to install locally.

## Connect

Use this URL in most MCP clients:

```text
https://mcp.storeinspect.com/mcp
```

For ChatGPT, use the data-only endpoint:

```text
https://mcp.storeinspect.com/openai
```

Both endpoints use OAuth. Never paste StoreInspect API keys into an AI client.

### Claude

Add a custom connector using `https://mcp.storeinspect.com/mcp`, then sign in to StoreInspect when prompted.

### Claude Code

```bash
claude mcp add --transport http storeinspect https://mcp.storeinspect.com/mcp
```

Open Claude Code, run `/mcp`, and complete the StoreInspect OAuth flow.

### Codex CLI

```bash
codex mcp add storeinspect \
  --url https://mcp.storeinspect.com/mcp \
  --oauth-resource https://mcp.storeinspect.com/mcp

codex mcp login storeinspect
```

### Cursor

[Add StoreInspect MCP to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=storeinspect&config=eyJ1cmwiOiJodHRwczovL21jcC5zdG9yZWluc3BlY3QuY29tL21jcCJ9)

After installation, open **Cursor Settings > Tools & MCP** and click **Connect** on the StoreInspect row to start OAuth.

Or add it manually:

```json
{
  "mcpServers": {
    "storeinspect": {
      "url": "https://mcp.storeinspect.com/mcp"
    }
  }
}
```

### VS Code

```json
{
  "servers": {
    "storeinspect": {
      "type": "http",
      "url": "https://mcp.storeinspect.com/mcp"
    }
  }
}
```

See the [client setup guide](https://storeinspect.com/docs/mcp/connect-clients) for ChatGPT and additional clients.

## Tools

The general MCP endpoint exposes these tools:

| Tool                         | Purpose                                                              |
| ---------------------------- | -------------------------------------------------------------------- |
| `get_usage`                  | Read plan, quota, search-row usage, and contact credits.             |
| `list_taxonomy`              | Discover supported store, technology, and contact filters.           |
| `get_shopify_store`          | Get one Shopify store by domain.                                     |
| `search_shopify_stores`      | Search Shopify stores using focused ICP filters.                     |
| `enrich_shopify_domains`     | Enrich up to 10 known domains with store and technology data.        |
| `search_shopify_contacts`    | Search masked decision-maker contact previews.                       |
| `reveal_contacts`            | Reveal selected contact channels after explicit credit confirmation. |
| `get_billing_status`         | Read subscription and billing status.                                |
| `create_subscription_link`   | Create a short-lived Stripe-hosted subscription or upgrade link.     |
| `create_billing_portal_link` | Create a short-lived Stripe-hosted account-management link.          |

Search tools return at most 25 records per call. ChatGPT's `/openai` endpoint excludes the three billing tools.

## Example prompts

```text
Use StoreInspect to find 25 US Shopify Plus beauty stores using Meta Pixel but not Klaviyo.
```

```text
Use StoreInspect to enrich allbirds.com, gymshark.com, and tentree.com. Return their themes, apps, pixels, traffic tiers, and contact availability.
```

```text
Search for founder or ecommerce decision-maker contacts at those stores. Do not reveal contact channels yet.
```

See [examples/prompts.md](examples/prompts.md) for more workflows.

## Safety and access

- Store and contact tools require an active paid StoreInspect plan.
- Contact previews keep email, phone, and LinkedIn channels masked.
- `reveal_contacts` requires `confirm_spend_credits: true` and can spend shared StoreInspect contact credits.
- Billing tools return Stripe-hosted links. A person must confirm any subscription change in Stripe.
- StoreInspect MCP searches the existing StoreInspect index. A request does not trigger a live scan.

## Resources

- [MCP quickstart](https://storeinspect.com/docs/mcp/quickstart)
- [Complete MCP documentation](https://storeinspect.com/docs/mcp/overview)
- [Tool reference](https://storeinspect.com/docs/mcp/tools)
- [Security and OAuth](https://storeinspect.com/docs/mcp/security)
- [Quotas and credits](https://storeinspect.com/docs/mcp/quotas-and-credits)
- [Official MCP Registry entry](https://registry.modelcontextprotocol.io/v0.1/servers?search=com.storeinspect%2Fmcp)
- [StoreInspect](https://storeinspect.com)

Email [support@storeinspect.com](mailto:support@storeinspect.com) for support. Open a GitHub issue for non-sensitive setup or documentation problems.

## License

The metadata, configuration examples, and documentation in this repository are licensed under the [MIT License](LICENSE).
